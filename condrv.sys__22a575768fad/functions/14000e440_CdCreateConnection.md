# CdCreateConnection

- ea: `0x14000e440`
- end: `0x14000e6cb`
- name: `CdCreateConnection`
- size: `651`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000b020`
- `0x14000b820`
- `0x14000c690`
- `0x14000e440`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e52d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e52d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e53f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e53f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e5e9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e5e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e5f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e5f5`
- `ntoskrnl!IofCompleteRequest` at `0x14000e6af`
- `ntoskrnl!IofCompleteRequest` at `0x14000e6af`
- `ntoskrnl!_stricmp` at `0x14000e486`
- `ntoskrnl!_stricmp` at `0x14000e4ae`
- `ntoskrnl!_stricmp` at `0x14000e486`
- `ntoskrnl!_stricmp` at `0x14000e4ae`
- `ntoskrnl!SeAccessCheck` at `0x14000e590`
- `ntoskrnl!SeAccessCheck` at `0x14000e590`
- `ntoskrnl!SeQueryInformationToken` at `0x14000e5c1`
- `ntoskrnl!SeQueryInformationToken` at `0x14000e5c1`

## pseudocode

```c
__int64 __fastcall CdCreateConnection(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  struct _IRP *MasterIrp; // rbx
  PFILE_OBJECT FileObject; // rsi
  struct _SECURITY_SUBJECT_CONTEXT *v5; // r14
  __int64 v6; // rax
  NTSTATUS ServerConnectionIo; // ebx
  KPROCESSOR_MODE AccessMode; // bl
  PSECURITY_DESCRIPTOR *v9; // rsi
  PACCESS_TOKEN ClientToken; // rcx
  struct _FILE_OBJECT *RelatedFileObject; // rcx
  __int64 **FsContext; // rax
  __int64 v13; // rdx
  PVOID P; // [rsp+90h] [rbp+8h] BYREF
  PVOID TokenInformation; // [rsp+A0h] [rbp+18h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  P = 0;
  FileObject = CurrentStackLocation->FileObject;
  if ( !MasterIrp )
  {
LABEL_21:
    RelatedFileObject = FileObject->RelatedFileObject;
    if ( !RelatedFileObject )
    {
      ServerConnectionIo = -1073741696;
      goto LABEL_31;
    }
    if ( RelatedFileObject->DeviceObject != (PDEVICE_OBJECT)CdDeviceObject
      || (FsContext = (__int64 **)RelatedFileObject->FsContext) == 0
      || *FsContext != CdReferenceType
      || (v13 = (__int64)FsContext[1]) == 0 )
    {
      ServerConnectionIo = -1073741816;
      goto LABEL_31;
    }
    ServerConnectionIo = CdpCreateServerConnectionIo((__int64)Irp, v13, &CurrentStackLocation->FileObject->FsContext);
    goto LABEL_27;
  }
  v5 = *(struct _SECURITY_SUBJECT_CONTEXT **)(CurrentStackLocation->Parameters.WMI.ProviderId + 8);
  if ( _stricmp((const char *)&MasterIrp->MdlAddress, "attach") )
  {
    while ( 1 )
    {
      v6 = *(unsigned int *)&MasterIrp->Type;
      if ( !(_DWORD)v6 )
        goto LABEL_21;
      MasterIrp = (struct _IRP *)((char *)MasterIrp + v6);
      if ( !_stricmp((const char *)&MasterIrp->MdlAddress, "attach") )
      {
        if ( !MasterIrp )
          goto LABEL_21;
        break;
      }
    }
  }
  if ( *(&MasterIrp->Size + 2) != 8 )
  {
    ServerConnectionIo = -1073741811;
    goto LABEL_31;
  }
  ServerConnectionIo = CdpGetProcessServerFromConnection(
                         &P,
                         Irp,
                         *(PMDL *)((char *)&MasterIrp->MdlAddress + *((unsigned __int8 *)&MasterIrp->Size + 3) + 1));
  if ( ServerConnectionIo < 0 )
    goto LABEL_31;
  AccessMode = 1;
  if ( (CurrentStackLocation->Flags & 1) == 0 )
    AccessMode = Irp->RequestorMode;
  v9 = (PSECURITY_DESCRIPTOR *)P;
  LODWORD(P) = 0;
  GrantedAccess = 0;
  LODWORD(TokenInformation) = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v9 + 5, 0);
  if ( SeAccessCheck(v9[7], v5 + 1, 0, 0x120089u, 0, 0, &CdpGenericMapping, AccessMode, &GrantedAccess, (PNTSTATUS)&P) )
    goto LABEL_17;
  if ( ((_DWORD)v9[6] & 1) != 0 )
  {
    ClientToken = v5[1].ClientToken;
    if ( !ClientToken )
      ClientToken = v5[1].PrimaryToken;
    if ( SeQueryInformationToken(ClientToken, TokenUIAccess, &TokenInformation) >= 0 && (_DWORD)TokenInformation )
LABEL_17:
      LODWORD(P) = 0;
  }
  ExReleasePushLockSharedEx(v9 + 5, 0);
  KeLeaveCriticalRegion();
  ServerConnectionIo = (int)P;
  if ( (int)P < 0 )
  {
    CdDereferenceServer(v9);
    goto LABEL_31;
  }
  ServerConnectionIo = CdpCreateServerConnectionIo(
                         (__int64)Irp,
                         (__int64)v9,
                         &CurrentStackLocation->FileObject->FsContext);
  CdDereferenceServer(v9);
LABEL_27:
  if ( ServerConnectionIo >= 0 )
    return (unsigned int)ServerConnectionIo;
LABEL_31:
  Irp->IoStatus.Status = ServerConnectionIo;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)ServerConnectionIo;
}

```

## disassembly

```asm
0x14000e440  push    rbx
0x14000e442  push    rbp
0x14000e443  push    rsi
0x14000e444  push    rdi
0x14000e445  push    r12
0x14000e447  push    r14
0x14000e449  sub     rsp, 58h
0x14000e44d  mov     rbp, [rcx+0B8h]
0x14000e454  xor     r12d, r12d
0x14000e457  mov     rbx, [rcx+18h]
0x14000e45b  mov     rdi, rcx
0x14000e45e  mov     [rsp+88h+P], r12
0x14000e466  mov     rsi, [rbp+30h]
0x14000e46a  test    rbx, rbx
0x14000e46d  jz      loc_14000E63D
0x14000e473  mov     rax, [rbp+8]
0x14000e477  lea     rcx, [rbx+8]; Str1
0x14000e47b  lea     rdx, aAttach; "attach"
0x14000e482  mov     r14, [rax+8]
0x14000e486  call    cs:__imp__stricmp
0x14000e48d  nop     dword ptr [rax+rax+00h]
0x14000e492  test    eax, eax
0x14000e494  jz      short loc_14000E4C7
0x14000e496  mov     eax, [rbx]
0x14000e498  test    eax, eax
0x14000e49a  jz      loc_14000E63D
0x14000e4a0  add     rbx, rax
0x14000e4a3  lea     rdx, aAttach; "attach"
0x14000e4aa  lea     rcx, [rbx+8]; Str1
0x14000e4ae  call    cs:__imp__stricmp
0x14000e4b5  nop     dword ptr [rax+rax+00h]
0x14000e4ba  test    eax, eax
0x14000e4bc  jnz     short loc_14000E496
0x14000e4be  test    rbx, rbx
0x14000e4c1  jz      loc_14000E63D
0x14000e4c7  cmp     word ptr [rbx+6], 8
0x14000e4cc  jz      short loc_14000E4D8
0x14000e4ce  mov     ebx, 0C000000Dh
0x14000e4d3  jmp     loc_14000E6A3
0x14000e4d8  movzx   r8d, byte ptr [rbx+5]
0x14000e4dd  lea     rcx, [rsp+88h+P]
0x14000e4e5  mov     rdx, rdi
0x14000e4e8  mov     r8, [r8+rbx+9]
0x14000e4ed  call    CdpGetProcessServerFromConnection
0x14000e4f2  mov     ebx, eax
0x14000e4f4  test    eax, eax
0x14000e4f6  js      loc_14000E6A3
0x14000e4fc  test    byte ptr [rbp+2], 1
0x14000e500  mov     bl, 1
0x14000e502  mov     [rsp+88h+var_38], r15
0x14000e507  jnz     short loc_14000E50D
0x14000e509  movzx   ebx, byte ptr [rdi+40h]
0x14000e50d  mov     rsi, [rsp+88h+P]
0x14000e515  mov     dword ptr [rsp+88h+P], r12d
0x14000e51d  mov     [rsp+88h+arg_18], r12d
0x14000e525  mov     dword ptr [rsp+88h+TokenInformation], r12d
0x14000e52d  call    cs:__imp_KeEnterCriticalRegion
0x14000e534  nop     dword ptr [rax+rax+00h]
0x14000e539  xor     edx, edx
0x14000e53b  lea     rcx, [rsi+28h]
0x14000e53f  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000e546  nop     dword ptr [rax+rax+00h]
0x14000e54b  mov     rcx, [rsi+38h]; SecurityDescriptor
0x14000e54f  lea     rax, [rsp+88h+P]
0x14000e557  mov     [rsp+88h+AccessStatus], rax; AccessStatus
0x14000e55c  lea     rdx, [r14+20h]; SubjectSecurityContext
0x14000e560  lea     rax, [rsp+88h+arg_18]
0x14000e568  mov     r9d, 120089h; DesiredAccess
0x14000e56e  mov     [rsp+88h+GrantedAccess], rax; GrantedAccess
0x14000e573  xor     r8d, r8d; SubjectContextLocked
0x14000e576  mov     [rsp+88h+AccessMode], bl; AccessMode
0x14000e57a  lea     rax, CdpGenericMapping
0x14000e581  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x14000e586  mov     [rsp+88h+Privileges], r12; Privileges
0x14000e58b  mov     [rsp+88h+PreviouslyGrantedAccess], r12d; PreviouslyGrantedAccess
0x14000e590  call    cs:__imp_SeAccessCheck
0x14000e597  nop     dword ptr [rax+rax+00h]
0x14000e59c  test    al, al
0x14000e59e  jnz     short loc_14000E5DB
0x14000e5a0  mov     eax, [rsi+30h]
0x14000e5a3  test    al, 1
0x14000e5a5  jz      short loc_14000E5E3
0x14000e5a7  mov     rcx, [r14+20h]
0x14000e5ab  test    rcx, rcx
0x14000e5ae  jnz     short loc_14000E5B4
0x14000e5b0  mov     rcx, [r14+30h]; Token
0x14000e5b4  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x14000e5bc  mov     edx, 1Ah; TokenInformationClass
0x14000e5c1  call    cs:__imp_SeQueryInformationToken
0x14000e5c8  nop     dword ptr [rax+rax+00h]
0x14000e5cd  test    eax, eax
0x14000e5cf  js      short loc_14000E5E3
0x14000e5d1  cmp     dword ptr [rsp+88h+TokenInformation], r12d
0x14000e5d9  jz      short loc_14000E5E3
0x14000e5db  mov     dword ptr [rsp+88h+P], r12d
0x14000e5e3  xor     edx, edx
0x14000e5e5  lea     rcx, [rsi+28h]
0x14000e5e9  call    cs:__imp_ExReleasePushLockSharedEx
0x14000e5f0  nop     dword ptr [rax+rax+00h]
0x14000e5f5  call    cs:__imp_KeLeaveCriticalRegion
0x14000e5fc  nop     dword ptr [rax+rax+00h]
0x14000e601  mov     ebx, dword ptr [rsp+88h+P]
0x14000e608  mov     r15, [rsp+88h+var_38]
0x14000e60d  test    ebx, ebx
0x14000e60f  jns     short loc_14000E61E
0x14000e611  mov     rcx, rsi; P
0x14000e614  call    CdDereferenceServer
0x14000e619  jmp     loc_14000E6A3
0x14000e61e  mov     r8, [rbp+30h]
0x14000e622  mov     rdx, rsi
0x14000e625  add     r8, 18h
0x14000e629  mov     rcx, rdi
0x14000e62c  call    CdpCreateServerConnectionIo
0x14000e631  mov     rcx, rsi; P
0x14000e634  mov     ebx, eax
0x14000e636  call    CdDereferenceServer
0x14000e63b  jmp     short loc_14000E683
0x14000e63d  mov     rcx, [rsi+40h]
0x14000e641  test    rcx, rcx
0x14000e644  jz      short loc_14000E69E
0x14000e646  mov     rax, cs:CdDeviceObject
0x14000e64d  cmp     [rcx+8], rax
0x14000e651  jnz     short loc_14000E697
0x14000e653  mov     rax, [rcx+18h]
0x14000e657  test    rax, rax
0x14000e65a  jz      short loc_14000E697
0x14000e65c  lea     rcx, CdReferenceType
0x14000e663  cmp     [rax], rcx
0x14000e666  jnz     short loc_14000E697
0x14000e668  mov     rdx, [rax+8]
0x14000e66c  test    rdx, rdx
0x14000e66f  jz      short loc_14000E697
0x14000e671  mov     r8, [rbp+30h]
0x14000e675  mov     rcx, rdi
0x14000e678  add     r8, 18h
0x14000e67c  call    CdpCreateServerConnectionIo
0x14000e681  mov     ebx, eax
0x14000e683  test    ebx, ebx
0x14000e685  js      short loc_14000E6A3
0x14000e687  mov     eax, ebx
0x14000e689  add     rsp, 58h
0x14000e68d  pop     r14
0x14000e68f  pop     r12
0x14000e691  pop     rdi
0x14000e692  pop     rsi
0x14000e693  pop     rbp
0x14000e694  pop     rbx
0x14000e695  retn
0x14000e697  mov     ebx, 0C0000008h
0x14000e69c  jmp     short loc_14000E6A3
0x14000e69e  mov     ebx, 0C0000080h
0x14000e6a3  xor     edx, edx; PriorityBoost
0x14000e6a5  mov     [rdi+30h], ebx
0x14000e6a8  mov     rcx, rdi; Irp
0x14000e6ab  mov     [rdi+38h], r12
0x14000e6af  call    cs:__imp_IofCompleteRequest
0x14000e6b6  nop     dword ptr [rax+rax+00h]
0x14000e6bb  mov     eax, ebx
0x14000e6bd  add     rsp, 58h
0x14000e6c1  pop     r14
0x14000e6c3  pop     r12
0x14000e6c5  pop     rdi
0x14000e6c6  pop     rsi
0x14000e6c7  pop     rbp
0x14000e6c8  pop     rbx
0x14000e6c9  retn
```
