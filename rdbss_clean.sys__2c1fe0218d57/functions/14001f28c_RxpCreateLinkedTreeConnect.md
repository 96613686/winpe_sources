# RxpCreateLinkedTreeConnect

- ea: `0x14001f28c`
- end: `0x14001f58f`
- name: `RxpCreateLinkedTreeConnect`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001ed50`

## callees

- `0x140017310`
- `0x14001f28c`
- `0x140025d80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001f389`
- `ntoskrnl!ExAllocatePool2` at `0x14001f389`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001f4dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001f4dd`
- `ntoskrnl!ObfDereferenceObject` at `0x14001f53b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001f53b`
- `ntoskrnl!ZwClose` at `0x14001f558`
- `ntoskrnl!ZwClose` at `0x14001f558`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f56e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f56e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001f508`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001f508`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001f52b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001f52b`
- `ntoskrnl!ZwCreateFile` at `0x14001f4a9`
- `ntoskrnl!ZwCreateFile` at `0x14001f4a9`
- `ksecdd!MapSecurityError` at `0x14001f308`
- `ksecdd!MapSecurityError` at `0x14001f308`
- `ksecdd!SspiMarshalAuthIdentity` at `0x14001f2f7`
- `ksecdd!SspiMarshalAuthIdentity` at `0x14001f2f7`
- `ksecdd!SspiLocalFree` at `0x14001f3a1`
- `ksecdd!SspiLocalFree` at `0x14001f438`
- `ksecdd!SspiLocalFree` at `0x14001f3a1`
- `ksecdd!SspiLocalFree` at `0x14001f438`

## pseudocode

```c
__int64 __fastcall RxpCreateLinkedTreeConnect(__int64 a1, UNICODE_STRING *a2)
{
  __int64 v3; // rcx
  void *EaBuffer; // rsi
  ULONG EaLength; // ebx
  void *v7; // rcx
  SECURITY_STATUS v8; // r14d
  NTSTATUS v9; // edi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 Pool2; // rax
  __int64 v14; // rbx
  void *FileHandle; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  unsigned int AuthIdentityLength; // [rsp+F0h] [rbp+67h] BYREF
  char *AuthIdentityByteArray; // [rsp+100h] [rbp+77h] BYREF
  PVOID Object; // [rsp+108h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v3 = *(_QWORD *)(a1 + 104);
  EaBuffer = 0;
  EaLength = 0;
  Object = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !v3 || (v7 = *(void **)(v3 + 8)) == 0 )
  {
LABEL_17:
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a2;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwCreateFile(
           &FileHandle,
           0x100000u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           2u,
           7u,
           1u,
           0xA0u,
           EaBuffer,
           EaLength);
    if ( v9 >= 0 )
    {
      v9 = ObReferenceObjectByHandle(FileHandle, 0, 0, 0, &Object, 0);
      if ( v9 >= 0 )
      {
        v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Object + 4) + 32LL) + 40LL);
        ExAcquirePushLockExclusiveEx(&RxLinkedConnectionLock, 0);
        *(_QWORD *)(a1 + 432) = v14;
        *(_QWORD *)(v14 + 432) = a1;
        ExReleasePushLockExclusiveEx(&RxLinkedConnectionLock, 0);
        ObfDereferenceObject(Object);
        Object = 0;
      }
    }
    goto LABEL_20;
  }
  AuthIdentityByteArray = 0;
  AuthIdentityLength = 0;
  v8 = SspiMarshalAuthIdentity(v7, &AuthIdentityLength, &AuthIdentityByteArray);
  v9 = MapSecurityError(v8);
  if ( v9 < 0 )
  {
LABEL_6:
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v11 = 10;
      v12 = (unsigned int)v9;
LABEL_10:
      WPP_SF_Dd(v10->AttachedDevice, v11, &WPP_e01a4f2c5ae23c78cfc8b6f416d17e00_Traceguids, v12, v8);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  if ( (int)AuthIdentityLength >= 0xFFFF )
  {
    v9 = -2147483643;
    goto LABEL_6;
  }
  EaLength = AuthIdentityLength + 29;
  Pool2 = ExAllocatePool2(258, (int)(AuthIdentityLength + 29), 1934456914);
  EaBuffer = (void *)Pool2;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 5) = 12;
    *(_WORD *)(Pool2 + 6) = AuthIdentityLength;
    *(_BYTE *)(Pool2 + 4) = 0;
    *(_DWORD *)Pool2 = 0;
    strcpy((char *)(Pool2 + 8), "AuthIdentity");
    memmove((void *)(Pool2 + *(unsigned __int8 *)(Pool2 + 5) + 9LL), AuthIdentityByteArray, (int)AuthIdentityLength);
    SspiLocalFree(AuthIdentityByteArray);
    goto LABEL_17;
  }
  SspiLocalFree(AuthIdentityByteArray);
  v9 = -1073741670;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v11 = 11;
    v12 = 3221225626LL;
    goto LABEL_10;
  }
LABEL_20:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( EaBuffer )
    ExFreePoolWithTag(EaBuffer, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001f28c  push    rbp
0x14001f28e  push    rbx
0x14001f28f  push    rsi
0x14001f290  push    rdi
0x14001f291  push    r12
0x14001f293  push    r14
0x14001f295  push    r15
0x14001f297  lea     rbp, [rsp-27h]
0x14001f29c  sub     rsp, 0B0h
0x14001f2a3  xorps   xmm0, xmm0
0x14001f2a6  mov     [rbp+57h+FileHandle], 0
0x14001f2ae  xor     eax, eax
0x14001f2b0  mov     r15, rcx
0x14001f2b3  mov     rcx, [rcx+68h]
0x14001f2b7  xor     esi, esi
0x14001f2b9  xor     ebx, ebx
0x14001f2bb  mov     [rbp+57h+Object], rax
0x14001f2bf  mov     r12, rdx
0x14001f2c2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14001f2c6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001f2ca  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001f2ce  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14001f2d2  test    rcx, rcx
0x14001f2d5  jz      loc_14001F444
0x14001f2db  mov     rcx, [rcx+8]; AuthIdentity
0x14001f2df  test    rcx, rcx
0x14001f2e2  jz      loc_14001F444
0x14001f2e8  lea     r8, [rbp+57h+AuthIdentityByteArray]; AuthIdentityByteArray
0x14001f2ec  mov     [rbp+57h+AuthIdentityByteArray], rax
0x14001f2f0  lea     rdx, [rbp+57h+AuthIdentityLength]; AuthIdentityLength
0x14001f2f4  mov     [rbp+57h+AuthIdentityLength], eax
0x14001f2f7  call    cs:__imp_SspiMarshalAuthIdentity
0x14001f2fe  nop     dword ptr [rax+rax+00h]
0x14001f303  mov     ecx, eax; SecStatus
0x14001f305  mov     r14d, eax
0x14001f308  call    cs:__imp_MapSecurityError
0x14001f30f  nop     dword ptr [rax+rax+00h]
0x14001f314  mov     edi, eax
0x14001f316  test    eax, eax
0x14001f318  js      short loc_14001F32A
0x14001f31a  mov     ecx, [rbp+57h+AuthIdentityLength]
0x14001f31d  cmp     ecx, 0FFFFh
0x14001f323  jl      short loc_14001F378
0x14001f325  mov     edi, 80000005h
0x14001f32a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f331  lea     rax, WPP_GLOBAL_Control
0x14001f338  cmp     rcx, rax
0x14001f33b  jz      loc_14001F54F
0x14001f341  mov     eax, [rcx+2Ch]
0x14001f344  test    al, 1
0x14001f346  jz      loc_14001F54F
0x14001f34c  cmp     byte ptr [rcx+29h], 1
0x14001f350  jb      loc_14001F54F
0x14001f356  mov     edx, 0Ah
0x14001f35b  mov     r9d, edi
0x14001f35e  mov     rcx, [rcx+18h]
0x14001f362  lea     r8, WPP_e01a4f2c5ae23c78cfc8b6f416d17e00_Traceguids
0x14001f369  mov     dword ptr [rsp+0E0h+AllocationSize], r14d
0x14001f36e  call    WPP_SF_Dd
0x14001f373  jmp     loc_14001F54F
0x14001f378  lea     ebx, [rcx+1Dh]
0x14001f37b  mov     r8d, 734D7852h
0x14001f381  movsxd  rdx, ebx
0x14001f384  mov     ecx, 102h
0x14001f389  call    cs:__imp_ExAllocatePool2
0x14001f390  nop     dword ptr [rax+rax+00h]
0x14001f395  mov     rsi, rax
0x14001f398  test    rax, rax
0x14001f39b  jnz     short loc_14001F3EC
0x14001f39d  mov     rcx, [rbp+57h+AuthIdentityByteArray]; DataBuffer
0x14001f3a1  call    cs:__imp_SspiLocalFree
0x14001f3a8  nop     dword ptr [rax+rax+00h]
0x14001f3ad  mov     edi, 0C000009Ah
0x14001f3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3b9  lea     rax, WPP_GLOBAL_Control
0x14001f3c0  cmp     rcx, rax
0x14001f3c3  jz      loc_14001F54F
0x14001f3c9  mov     eax, [rcx+2Ch]
0x14001f3cc  test    al, 1
0x14001f3ce  jz      loc_14001F54F
0x14001f3d4  cmp     byte ptr [rcx+29h], 1
0x14001f3d8  jb      loc_14001F54F
0x14001f3de  lea     edx, [rsi+0Bh]
0x14001f3e1  mov     r9d, 0C000009Ah
0x14001f3e7  jmp     loc_14001F35E
0x14001f3ec  mov     byte ptr [rax+5], 0Ch
0x14001f3f0  movzx   eax, word ptr [rbp+57h+AuthIdentityLength]
0x14001f3f4  mov     [rsi+6], ax
0x14001f3f8  mov     byte ptr [rsi+4], 0
0x14001f3fc  mov     dword ptr [rsi], 0
0x14001f402  movsd   xmm0, qword ptr cs:aAuthidentity; "AuthIdentity"
0x14001f40a  movsd   qword ptr [rsi+8], xmm0
0x14001f40f  mov     eax, dword ptr cs:aAuthidentity+8; "tity"
0x14001f415  mov     [rsi+10h], eax
0x14001f418  mov     byte ptr [rsi+14h], 0
0x14001f41c  movzx   ecx, byte ptr [rsi+5]
0x14001f420  movsxd  r8, [rbp+57h+AuthIdentityLength]; Size
0x14001f424  add     rcx, 9
0x14001f428  mov     rdx, [rbp+57h+AuthIdentityByteArray]; Src
0x14001f42c  add     rcx, rsi; void *
0x14001f42f  call    memmove
0x14001f434  mov     rcx, [rbp+57h+AuthIdentityByteArray]; DataBuffer
0x14001f438  call    cs:__imp_SspiLocalFree
0x14001f43f  nop     dword ptr [rax+rax+00h]
0x14001f444  mov     [rsp+0E0h+EaLength], ebx; EaLength
0x14001f448  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001f44c  mov     [rsp+0E0h+EaBuffer], rsi; EaBuffer
0x14001f451  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001f455  mov     [rsp+0E0h+CreateOptions], 0A0h; CreateOptions
0x14001f45d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001f461  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x14001f469  xorps   xmm0, xmm0
0x14001f46c  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x14001f474  mov     edx, 100000h; DesiredAccess
0x14001f479  mov     [rsp+0E0h+FileAttributes], 2; FileAttributes
0x14001f481  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x14001f48a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001f491  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001f499  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001f4a0  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x14001f4a4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001f4a9  call    cs:__imp_ZwCreateFile
0x14001f4b0  nop     dword ptr [rax+rax+00h]
0x14001f4b5  mov     edi, eax
0x14001f4b7  test    eax, eax
0x14001f4b9  js      loc_14001F54F
0x14001f4bf  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001f4c3  lea     rax, [rbp+57h+Object]
0x14001f4c7  mov     qword ptr [rsp+0E0h+FileAttributes], 0; HandleInformation
0x14001f4d0  xor     r9d, r9d; AccessMode
0x14001f4d3  xor     r8d, r8d; ObjectType
0x14001f4d6  mov     [rsp+0E0h+AllocationSize], rax; Object
0x14001f4db  xor     edx, edx; DesiredAccess
0x14001f4dd  call    cs:__imp_ObReferenceObjectByHandle
0x14001f4e4  nop     dword ptr [rax+rax+00h]
0x14001f4e9  mov     edi, eax
0x14001f4eb  test    eax, eax
0x14001f4ed  js      short loc_14001F54F
0x14001f4ef  mov     rax, [rbp+57h+Object]
0x14001f4f3  xor     edx, edx
0x14001f4f5  mov     rcx, [rax+20h]
0x14001f4f9  mov     rax, [rcx+20h]
0x14001f4fd  lea     rcx, RxLinkedConnectionLock
0x14001f504  mov     rbx, [rax+28h]
0x14001f508  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001f50f  nop     dword ptr [rax+rax+00h]
0x14001f514  mov     [r15+1B0h], rbx
0x14001f51b  lea     rcx, RxLinkedConnectionLock
0x14001f522  xor     edx, edx
0x14001f524  mov     [rbx+1B0h], r15
0x14001f52b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001f532  nop     dword ptr [rax+rax+00h]
0x14001f537  mov     rcx, [rbp+57h+Object]; Object
0x14001f53b  call    cs:__imp_ObfDereferenceObject
0x14001f542  nop     dword ptr [rax+rax+00h]
0x14001f547  mov     [rbp+57h+Object], 0
0x14001f54f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001f553  test    rcx, rcx
0x14001f556  jz      short loc_14001F564
0x14001f558  call    cs:__imp_ZwClose
0x14001f55f  nop     dword ptr [rax+rax+00h]
0x14001f564  test    rsi, rsi
0x14001f567  jz      short loc_14001F57A
0x14001f569  xor     edx, edx; Tag
0x14001f56b  mov     rcx, rsi; P
0x14001f56e  call    cs:__imp_ExFreePoolWithTag
0x14001f575  nop     dword ptr [rax+rax+00h]
0x14001f57a  mov     eax, edi
0x14001f57c  add     rsp, 0B0h
0x14001f583  pop     r15
0x14001f585  pop     r14
0x14001f587  pop     r12
0x14001f589  pop     rdi
0x14001f58a  pop     rsi
0x14001f58b  pop     rbx
0x14001f58c  pop     rbp
0x14001f58d  retn
```
