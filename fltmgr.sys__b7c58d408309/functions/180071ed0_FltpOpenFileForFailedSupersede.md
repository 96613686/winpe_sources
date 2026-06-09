# FltpOpenFileForFailedSupersede

- ea: `0x180071ed0`
- end: `0x1800722d2`
- name: `FltpOpenFileForFailedSupersede`
- size: `1026`
- prototype: `__int64 __fastcall(const UNICODE_STRING **, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180071ac0`

## callees

- `0x180009f20`
- `0x18005d850`
- `0x18005df50`
- `0x180071ed0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800721bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800721bb`
- `ntoskrnl!ExAllocatePool2` at `0x180071fec`
- `ntoskrnl!ExAllocatePool2` at `0x180071fec`
- `ntoskrnl!ObfDereferenceObject` at `0x18007227e`
- `ntoskrnl!ObfDereferenceObject` at `0x18007227e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180072014`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180072014`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180072027`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180072027`
- `ntoskrnl!RtlInitUnicodeString` at `0x180071f38`
- `ntoskrnl!RtlInitUnicodeString` at `0x180071f38`
- `ntoskrnl!ZwClose` at `0x180072194`
- `ntoskrnl!ZwClose` at `0x18007228f`
- `ntoskrnl!ZwClose` at `0x180072194`
- `ntoskrnl!ZwClose` at `0x18007228f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180072143`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180072143`
- `ntoskrnl!IoFileObjectType` at `0x180072122`
- `ntoskrnl!IoCreateFileEx` at `0x1800720e7`
- `ntoskrnl!IoCreateFileEx` at `0x1800720e7`
- `ntoskrnl!IoGetSilo` at `0x18007205a`
- `ntoskrnl!IoGetSilo` at `0x18007205a`
- `ntoskrnl!PsGetHostSilo` at `0x18007206f`
- `ntoskrnl!PsGetHostSilo` at `0x18007206f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18007aefd`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18007aefd`

## pseudocode

```c
__int64 __fastcall FltpOpenFileForFailedSupersede(const UNICODE_STRING **a1, _QWORD *a2)
{
  const UNICODE_STRING *v3; // rax
  __int64 v4; // r13
  wchar_t *Buffer; // r14
  const UNICODE_STRING *v6; // rax
  char v7; // r12
  const UNICODE_STRING *v8; // rax
  ULONG v9; // r15d
  UNICODE_STRING *v10; // rsi
  void *v11; // rcx
  const UNICODE_STRING *v12; // rdx
  const UNICODE_STRING *v13; // rcx
  unsigned int ECP; // edi
  PVOID v15; // rax
  const UNICODE_STRING *v17; // r9
  UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-70h] BYREF
  __int64 Silo; // [rsp+B0h] [rbp-50h]
  int v21[2]; // [rsp+B8h] [rbp-48h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  PVOID Object; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v25; // [rsp+158h] [rbp+58h]
  void *FileHandle; // [rsp+160h] [rbp+60h] BYREF
  HANDLE Handle; // [rsp+168h] [rbp+68h] BYREF

  v25 = a2;
  Object = 0;
  LOWORD(Silo) = 0;
  v3 = a1[2];
  FileHandle = 0;
  Handle = 0;
  v4 = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_QWORD *)v21 = 0;
  IoStatusBlock = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DestinationString = 0;
  Buffer = v3[15].Buffer;
  RtlInitUnicodeString(&DestinationString, 0);
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  v6 = a1[2];
  if ( (*(_DWORD *)(&v6->MaximumLength + 1) & 0x80u) != 0 )
  {
    v17 = *a1;
    DriverContext.DeviceObjectHint = v6[6].Buffer;
    ECP = TargetedIOCtrlGenerateECP(
            (PVOID *)v21,
            0,
            0x2000000,
            (__int64)v17[6].Buffer,
            *(PVOID *)(*((_QWORD *)Buffer + 2) + 72LL),
            *((_QWORD *)Buffer + 2),
            0,
            &DriverContext.ExtraCreateParameter,
            0);
    if ( (int)FltpDbgStatus(ECP) < 0 )
      return ECP;
    v4 = *(_QWORD *)v21;
    v7 = (*(_BYTE *)(*(_QWORD *)v21 + 6LL) & 8) != 0;
  }
  else
  {
    v7 = 0;
    DriverContext.DeviceObjectHint = *(PVOID *)(*((_QWORD *)v6[6].Buffer + 8) + 8LL);
  }
  v8 = a1[2];
  v9 = ((*((char *)Buffer + 6) >> 31) & 0xFFFFFFC0) + 576;
  if ( v8[11].Buffer )
    v10 = (UNICODE_STRING *)&v8[11];
  else
    v10 = (UNICODE_STRING *)(*(_QWORD *)&v8[7].Length + 88LL);
  v11 = *(void **)(*(_QWORD *)&v8[7].Length + 64LL);
  if ( v11 )
  {
    ECP = ObOpenObjectByPointer(v11, v9, 0, 0x1F01FFu, 0, 0, &Handle);
    if ( (int)FltpDbgStatus(ECP) >= 0 )
    {
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.ObjectName = v10;
      goto LABEL_8;
    }
  }
  else
  {
    DestinationString.MaximumLength = v10->Length + (*a1)[7].Length;
    DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, DestinationString.MaximumLength, 1853115718);
    if ( DestinationString.Buffer )
    {
      v12 = *a1 + 7;
      DestinationString.Length = 0;
      RtlCopyUnicodeString(&DestinationString, v12);
      RtlAppendUnicodeStringToString(&DestinationString, v10);
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &DestinationString;
LABEL_8:
      v13 = a1[2];
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Attributes = v9;
      ObjectAttributes.Length = 48;
      Silo = IoGetSilo(*(_QWORD *)&v13[7].Length);
      if ( !Silo )
        Silo = PsGetHostSilo();
      ECP = IoCreateFileEx(
              &FileHandle,
              0x100180u,
              &ObjectAttributes,
              &IoStatusBlock,
              (PLARGE_INTEGER)Buffer + 8,
              Buffer[20],
              7u,
              1u,
              *((_DWORD *)Buffer + 8) & 0x402241 | 0x200000,
              0,
              0,
              CreateFileTypeNone,
              0,
              0x800u,
              &DriverContext);
      if ( (int)FltpDbgStatus(ECP) >= 0 )
      {
        ECP = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
        if ( (int)FltpDbgStatus(ECP) >= 0 )
        {
          v15 = Object;
          Object = 0;
          *v25 = v15;
        }
      }
      goto LABEL_13;
    }
    ECP = -1073741670;
  }
LABEL_13:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E744D46u);
  if ( Handle )
    ZwClose(Handle);
  if ( v4 )
  {
    if ( (int)FltpDbgStatus(ECP) < 0 )
      v4 = 0;
    CleanupTargetedIo(v4, &DriverContext.ExtraCreateParameter, v7);
  }
  return ECP;
}

```

## disassembly

```asm
0x180071ed0  mov     [rsp-8+arg_8], rdx
0x180071ed5  push    rbp
0x180071ed6  push    rbx
0x180071ed7  push    rdi
0x180071ed8  push    r12
0x180071eda  push    r13
0x180071edc  push    r14
0x180071ede  lea     rbp, [rsp-18h]
0x180071ee3  sub     rsp, 118h
0x180071eea  xorps   xmm0, xmm0
0x180071eed  xor     edi, edi
0x180071eef  xor     eax, eax
0x180071ef1  mov     [rbp+40h+Object], rdi
0x180071ef5  mov     word ptr [rbp+40h+var_90], ax
0x180071ef9  mov     rbx, rcx
0x180071efc  mov     rax, [rcx+10h]
0x180071f00  xor     edx, edx; SourceString
0x180071f02  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x180071f06  mov     [rbp+40h+FileHandle], rdi
0x180071f0a  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x180071f0e  mov     [rbp+40h+Handle], rdi
0x180071f12  mov     r13d, edi
0x180071f15  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x180071f19  mov     qword ptr [rbp+40h+var_88], rdi
0x180071f1d  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x180071f21  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x180071f25  movups  xmmword ptr [rbp+40h+var_B0.Size], xmm0
0x180071f29  movups  xmmword ptr [rbp+40h+var_B0.DeviceObjectHint], xmm0
0x180071f2d  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x180071f31  mov     r14, [rax+0F8h]
0x180071f38  call    cs:__imp_RtlInitUnicodeString
0x180071f3f  nop     dword ptr [rax+rax+00h]
0x180071f44  xorps   xmm0, xmm0
0x180071f47  mov     [rbp+40h+var_90], 1
0x180071f4f  movups  xmmword ptr [rbp+40h+var_B0.Size], xmm0
0x180071f53  mov     eax, 28h ; '('
0x180071f58  mov     [rbp+40h+var_B0.Size], ax
0x180071f5c  mov     rax, [rbx+10h]
0x180071f60  movups  xmmword ptr [rbp+40h+var_B0.DeviceObjectHint], xmm0
0x180071f64  mov     ecx, [rax+4]
0x180071f67  mov     rdx, [rax+68h]
0x180071f6b  test    cl, cl
0x180071f6d  js      loc_1800721FE
0x180071f73  mov     rax, [rdx+40h]
0x180071f77  xor     r12b, r12b
0x180071f7a  mov     rcx, [rax+8]
0x180071f7e  mov     [rbp+40h+var_B0.DeviceObjectHint], rcx
0x180071f82  mov     rax, [rbx+10h]
0x180071f86  mov     [rsp+140h+var_30], rsi
0x180071f8e  mov     [rsp+140h+var_38], r15
0x180071f96  movsx   r15d, byte ptr [r14+6]
0x180071f9b  sar     r15d, 1Fh
0x180071f9f  and     r15d, 0FFFFFFC0h
0x180071fa3  add     r15d, 240h
0x180071faa  cmp     qword ptr [rax+0B8h], 0
0x180071fb2  jz      loc_1800721F1
0x180071fb8  lea     rsi, [rax+0B0h]
0x180071fbf  mov     rax, [rax+70h]
0x180071fc3  mov     rcx, [rax+40h]; Object
0x180071fc7  test    rcx, rcx
0x180071fca  jnz     loc_18007AEDE
0x180071fd0  mov     rax, [rbx]
0x180071fd3  mov     ecx, 100h
0x180071fd8  mov     r8d, 6E744D46h
0x180071fde  movzx   edx, word ptr [rax+70h]
0x180071fe2  add     dx, [rsi]
0x180071fe5  movzx   edx, dx
0x180071fe8  mov     [rbp+40h+DestinationString.MaximumLength], dx
0x180071fec  call    cs:__imp_ExAllocatePool2
0x180071ff3  nop     dword ptr [rax+rax+00h]
0x180071ff8  mov     [rbp+40h+DestinationString.Buffer], rax
0x180071ffc  test    rax, rax
0x180071fff  jz      loc_180072274
0x180072005  mov     rdx, [rbx]
0x180072008  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x18007200c  add     rdx, 70h ; 'p'; SourceString
0x180072010  mov     [rbp+40h+DestinationString.Length], di
0x180072014  call    cs:__imp_RtlCopyUnicodeString
0x18007201b  nop     dword ptr [rax+rax+00h]
0x180072020  mov     rdx, rsi; Source
0x180072023  lea     rcx, [rbp+40h+DestinationString]; Destination
0x180072027  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007202e  nop     dword ptr [rax+rax+00h]
0x180072033  lea     rax, [rbp+40h+DestinationString]
0x180072037  mov     [rbp+40h+ObjectAttributes.RootDirectory], rdi
0x18007203b  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18007203f  mov     rcx, [rbx+10h]
0x180072043  xorps   xmm0, xmm0
0x180072046  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007204b  mov     [rbp+40h+ObjectAttributes.Attributes], r15d
0x18007204f  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x180072056  mov     rcx, [rcx+70h]
0x18007205a  call    cs:__imp_IoGetSilo
0x180072061  nop     dword ptr [rax+rax+00h]
0x180072066  mov     [rbp+40h+var_90], rax
0x18007206a  test    rax, rax
0x18007206d  jnz     short loc_18007207F
0x18007206f  call    cs:__imp_PsGetHostSilo
0x180072076  nop     dword ptr [rax+rax+00h]
0x18007207b  mov     [rbp+40h+var_90], rax
0x18007207f  mov     edx, [r14+20h]
0x180072083  lea     r8, [rbp+40h+var_B0]
0x180072087  movzx   eax, word ptr [r14+28h]
0x18007208c  lea     rcx, [r14+40h]
0x180072090  mov     [rsp+140h+DriverContext], r8; DriverContext
0x180072095  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x180072099  mov     [rsp+140h+Options], 800h; Options
0x1800720a1  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1800720a5  mov     [rsp+140h+InternalParameters], rdi; InternalParameters
0x1800720aa  and     edx, 402241h
0x1800720b0  mov     [rsp+140h+CreateFileType], edi; CreateFileType
0x1800720b4  bts     edx, 15h
0x1800720b8  mov     [rsp+140h+EaLength], edi; EaLength
0x1800720bc  mov     [rsp+140h+EaBuffer], rdi; EaBuffer
0x1800720c1  mov     [rsp+140h+CreateOptions], edx; CreateOptions
0x1800720c5  mov     edx, 100180h; DesiredAccess
0x1800720ca  mov     [rsp+140h+Disposition], 1; Disposition
0x1800720d2  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x1800720da  mov     [rsp+140h+FileAttributes], eax; FileAttributes
0x1800720de  mov     [rsp+140h+AllocationSize], rcx; AllocationSize
0x1800720e3  lea     rcx, [rbp+40h+FileHandle]; FileHandle
0x1800720e7  call    cs:__imp_IoCreateFileEx
0x1800720ee  nop     dword ptr [rax+rax+00h]
0x1800720f3  xor     ebx, ebx
0x1800720f5  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x1800720fc  mov     qword ptr [rsp+140h+FileAttributes], rbx
0x180072101  mov     ecx, eax
0x180072103  mov     r8d, 567h
0x180072109  mov     dword ptr [rsp+140h+AllocationSize], 0C000003Ah
0x180072111  mov     r9d, 0C0000368h
0x180072117  mov     edi, eax
0x180072119  call    FltpDbgStatus
0x18007211e  test    eax, eax
0x180072120  js      short loc_18007217B
0x180072122  mov     r8, cs:__imp_IoFileObjectType
0x180072129  lea     rax, [rbp+40h+Object]
0x18007212d  mov     rcx, [rbp+40h+FileHandle]; Handle
0x180072131  xor     r9d, r9d; AccessMode
0x180072134  mov     qword ptr [rsp+140h+FileAttributes], rbx; HandleInformation
0x180072139  xor     edx, edx; DesiredAccess
0x18007213b  mov     [rsp+140h+AllocationSize], rax; Object
0x180072140  mov     r8, [r8]; ObjectType
0x180072143  call    cs:__imp_ObReferenceObjectByHandle
0x18007214a  nop     dword ptr [rax+rax+00h]
0x18007214f  mov     r8d, 576h
0x180072155  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18007215c  mov     ecx, eax
0x18007215e  xor     r9d, r9d
0x180072161  mov     edi, eax
0x180072163  call    FltpDbgStatus
0x180072168  test    eax, eax
0x18007216a  js      short loc_18007217B
0x18007216c  mov     rax, [rbp+40h+Object]
0x180072170  mov     rcx, [rbp+40h+arg_8]
0x180072174  mov     [rbp+40h+Object], rbx
0x180072178  mov     [rcx], rax
0x18007217b  mov     rcx, [rbp+40h+FileHandle]; Handle
0x18007217f  mov     r15, [rsp+140h+var_38]
0x180072187  mov     rsi, [rsp+140h+var_30]
0x18007218f  test    rcx, rcx
0x180072192  jz      short loc_1800721A0
0x180072194  call    cs:__imp_ZwClose
0x18007219b  nop     dword ptr [rax+rax+00h]
0x1800721a0  mov     rcx, [rbp+40h+Object]; Object
0x1800721a4  test    rcx, rcx
0x1800721a7  jnz     loc_18007227E
0x1800721ad  mov     rcx, [rbp+40h+DestinationString.Buffer]; P
0x1800721b1  test    rcx, rcx
0x1800721b4  jz      short loc_1800721C7
0x1800721b6  mov     edx, 6E744D46h; Tag
0x1800721bb  call    cs:__imp_ExFreePoolWithTag
0x1800721c2  nop     dword ptr [rax+rax+00h]
0x1800721c7  mov     rcx, [rbp+40h+Handle]; Handle
0x1800721cb  test    rcx, rcx
0x1800721ce  jnz     loc_18007228F
0x1800721d4  test    r13, r13
0x1800721d7  jnz     loc_1800722A0
0x1800721dd  mov     eax, edi
0x1800721df  add     rsp, 118h
0x1800721e6  pop     r14
0x1800721e8  pop     r13
0x1800721ea  pop     r12
0x1800721ec  pop     rdi
0x1800721ed  pop     rbx
0x1800721ee  pop     rbp
0x1800721ef  retn
0x1800721f1  mov     rsi, [rax+70h]
0x1800721f5  add     rsi, 58h ; 'X'
0x1800721f9  jmp     loc_180071FBF
0x1800721fe  mov     r9, [rbx]
0x180072201  lea     rcx, [rbp+40h+var_B0.ExtraCreateParameter]
0x180072205  mov     [rbp+40h+var_B0.DeviceObjectHint], rdx
0x180072209  mov     r8d, 2000000h; int
0x18007220f  mov     rax, [r14+10h]
0x180072213  xor     edx, edx; int
0x180072215  mov     qword ptr [rsp+140h+CreateOptions], rdi; __int64
0x18007221a  mov     r9, [r9+68h]; int
0x18007221e  mov     qword ptr [rsp+140h+Disposition], rcx; EcpList
0x180072223  lea     rcx, [rbp+40h+var_88]; int
0x180072227  mov     qword ptr [rsp+140h+ShareAccess], rdi; PVOID
0x18007222c  mov     qword ptr [rsp+140h+FileAttributes], rax; __int64
0x180072231  mov     rax, [rax+48h]
0x180072235  mov     [rsp+140h+AllocationSize], rax; FltObject
0x18007223a  call    TargetedIOCtrlGenerateECP
0x18007223f  mov     r8d, 4EFh
0x180072245  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18007224c  xor     r9d, r9d
0x18007224f  mov     ecx, eax
0x180072251  mov     edi, eax
0x180072253  call    FltpDbgStatus
0x180072258  test    eax, eax
0x18007225a  js      short loc_1800721DD
0x18007225c  mov     r13, qword ptr [rbp+40h+var_88]
0x180072260  movzx   r12d, byte ptr [r13+6]
0x180072265  shr     r12b, 3
0x180072269  and     r12b, 1
0x18007226d  xor     edi, edi
0x18007226f  jmp     loc_180071F82
0x180072274  mov     edi, 0C000009Ah
0x180072279  jmp     loc_18007AF39
0x18007227e  call    cs:__imp_ObfDereferenceObject
0x180072285  nop     dword ptr [rax+rax+00h]
0x18007228a  jmp     loc_1800721AD
0x18007228f  call    cs:__imp_ZwClose
0x180072296  nop     dword ptr [rax+rax+00h]
0x18007229b  jmp     loc_1800721D4
0x1800722a0  xor     r9d, r9d
0x1800722a3  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x1800722aa  mov     r8d, 59Ah
0x1800722b0  mov     ecx, edi
0x1800722b2  call    FltpDbgStatus
0x1800722b7  test    eax, eax
0x1800722b9  lea     rdx, [rbp+40h+var_B0.ExtraCreateParameter]
0x1800722bd  movzx   r8d, r12b
0x1800722c1  cmovs   r13, rbx
0x1800722c5  mov     rcx, r13
0x1800722c8  call    CleanupTargetedIo
0x1800722cd  jmp     loc_1800721DD
0x18007aede  lea     rax, [rbp+40h+Handle]
0x18007aee2  mov     r9d, 1F01FFh; DesiredAccess
0x18007aee8  mov     qword ptr [rsp+140h+ShareAccess], rax; Handle
0x18007aeed  xor     r8d, r8d; PassedAccessState
0x18007aef0  mov     byte ptr [rsp+140h+FileAttributes], 0; AccessMode
0x18007aef5  mov     edx, r15d; HandleAttributes
0x18007aef8  mov     [rsp+140h+AllocationSize], rdi; ObjectType
0x18007aefd  call    cs:__imp_ObOpenObjectByPointer
0x18007af04  nop     dword ptr [rax+rax+00h]
0x18007af09  mov     r8d, 519h
0x18007af0f  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18007af16  mov     ecx, eax
0x18007af18  xor     r9d, r9d
0x18007af1b  mov     edi, eax
0x18007af1d  call    FltpDbgStatus
0x18007af22  test    eax, eax
0x18007af24  js      short loc_18007AF39
0x18007af26  mov     rax, [rbp+40h+Handle]
0x18007af2a  xor     edi, edi
0x18007af2c  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x18007af30  mov     [rbp+40h+ObjectAttributes.ObjectName], rsi
0x18007af34  jmp     loc_18007203F
0x18007af39  xor     ebx, ebx
0x18007af3b  jmp     loc_18007217B
```
