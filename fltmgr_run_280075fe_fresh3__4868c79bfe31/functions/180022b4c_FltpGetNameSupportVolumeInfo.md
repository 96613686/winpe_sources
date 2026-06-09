# FltpGetNameSupportVolumeInfo

- ea: `0x180022b4c`
- end: `0x180022da4`
- name: `FltpGetNameSupportVolumeInfo`
- size: `600`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18000afe0`

## callees

- `0x180009f20`
- `0x180022a24`
- `0x180022b4c`
- `0x1800247a0`
- `0x180024c00`
- `0x18004dcc0`
- `0x18005c5a0`
- `0x180065a70`
- `0x180067b00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180022cf2`
- `ntoskrnl!ExAllocatePool2` at `0x180022cf2`
- `ntoskrnl!ObfDereferenceObject` at `0x180022d63`
- `ntoskrnl!ObfDereferenceObject` at `0x180022d63`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180022d27`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180022d27`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180022c6d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180022c6d`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180022c93`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180022c93`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180022ba0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180022ba0`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x180022bee`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x180022bee`

## pseudocode

```c
__int64 __fastcall FltpGetNameSupportVolumeInfo(PFILE_OBJECT FileObject, PVOID *a2)
{
  _QWORD *v4; // rax
  unsigned int BaseDeviceObjectName; // edi
  PDEVICE_OBJECT BaseFileSystemDeviceObject; // r14
  unsigned int i; // esi
  __int64 v8; // rdi
  unsigned __int16 Length; // si
  __int64 Pool2; // rax
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+20h] [rbp-E0h] BYREF
  UNICODE_STRING String1[18]; // [rsp+30h] [rbp-D0h] BYREF

  DiskDeviceObject = 0;
  memset(String1, 0, sizeof(String1));
  v4 = ExAllocateFromPagedLookasideList(&stru_18003FBC0);
  if ( v4 )
  {
    *(_OWORD *)v4 = 0;
    v4[2] = 0;
    BaseDeviceObjectName = 0;
    *a2 = v4;
  }
  else
  {
    BaseDeviceObjectName = -1073741670;
  }
  if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2514, 0) >= 0 )
  {
    BaseFileSystemDeviceObject = IoGetBaseFileSystemDeviceObject(FileObject);
    if ( BaseFileSystemDeviceObject->DeviceType == 20 )
      *(_DWORD *)*a2 |= 1u;
    *((_DWORD *)*a2 + 1) = 0;
    FltpInitNameControl(String1);
    BaseDeviceObjectName = FltpGetBaseDeviceObjectName(BaseFileSystemDeviceObject, (__int64)String1);
    if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2545, 0) >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v8 = 4LL * i;
        if ( LODWORD(FsTypes[v8]) == -1 )
          break;
        if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)&qword_18003DAF0[v8], 1u) )
        {
          *((_DWORD *)*a2 + 1) = FsTypes[v8];
          break;
        }
      }
      BaseDeviceObjectName = IoGetDiskDeviceObject(BaseFileSystemDeviceObject, &DiskDeviceObject);
      if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2567, 0) >= 0 )
      {
        BaseDeviceObjectName = FltpGetObjectName(DiskDeviceObject, (__int64)String1);
        if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2574, 0) >= 0 )
        {
          Length = String1[0].Length;
          Pool2 = ExAllocatePool2(256, String1[0].Length, 1937067334);
          if ( Pool2 )
          {
            *((_QWORD *)*a2 + 2) = Pool2;
            *((_WORD *)*a2 + 5) = Length;
            RtlCopyUnicodeString((PUNICODE_STRING)((char *)*a2 + 8), String1);
          }
          else
          {
            BaseDeviceObjectName = -1073741670;
          }
        }
      }
    }
    if ( (int)FltpDbgStatus(BaseDeviceObjectName, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 2597, 0) < 0 )
    {
      FltpFreeNameSupportVolumeInfo(*a2);
      *a2 = 0;
    }
    if ( DiskDeviceObject )
      ObfDereferenceObject(DiskDeviceObject);
    FltpCleanupNameControl(String1);
  }
  return BaseDeviceObjectName;
}

```

## disassembly

```asm
0x180022b4c  mov     [rsp-8+arg_10], rbx
0x180022b51  mov     [rsp-8+arg_18], rsi
0x180022b56  push    rbp
0x180022b57  push    rdi
0x180022b58  push    r12
0x180022b5a  push    r13
0x180022b5c  push    r14
0x180022b5e  lea     rbp, [rsp-60h]
0x180022b63  sub     rsp, 160h
0x180022b6a  mov     rax, cs:__security_cookie
0x180022b71  xor     rax, rsp
0x180022b74  mov     [rbp+80h+var_30], rax
0x180022b78  mov     rbx, rdx
0x180022b7b  mov     [rsp+180h+DiskDeviceObject], 0
0x180022b84  mov     rsi, rcx
0x180022b87  xor     edx, edx; Val
0x180022b89  lea     rcx, [rsp+180h+String1]; void *
0x180022b8e  mov     r8d, 120h; Size
0x180022b94  call    memset
0x180022b99  lea     rcx, stru_18003FBC0; Lookaside
0x180022ba0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180022ba7  nop     dword ptr [rax+rax+00h]
0x180022bac  test    rax, rax
0x180022baf  jnz     short loc_180022BB8
0x180022bb1  mov     edi, 0C000009Ah
0x180022bb6  jmp     short loc_180022BC9
0x180022bb8  xor     ecx, ecx
0x180022bba  xorps   xmm0, xmm0
0x180022bbd  movups  xmmword ptr [rax], xmm0
0x180022bc0  mov     [rax+10h], rcx
0x180022bc4  xor     edi, edi
0x180022bc6  mov     [rbx], rax
0x180022bc9  lea     r13, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x180022bd0  mov     r8d, 9D2h
0x180022bd6  mov     rdx, r13
0x180022bd9  xor     r9d, r9d
0x180022bdc  mov     ecx, edi
0x180022bde  call    FltpDbgStatus
0x180022be3  test    eax, eax
0x180022be5  js      loc_180022D79
0x180022beb  mov     rcx, rsi; FileObject
0x180022bee  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x180022bf5  nop     dword ptr [rax+rax+00h]
0x180022bfa  mov     r14, rax
0x180022bfd  cmp     dword ptr [rax+48h], 14h
0x180022c01  jnz     short loc_180022C09
0x180022c03  mov     rcx, [rbx]
0x180022c06  or      dword ptr [rcx], 1
0x180022c09  mov     rcx, [rbx]
0x180022c0c  mov     dword ptr [rcx+4], 0
0x180022c13  lea     rcx, [rsp+180h+String1]
0x180022c18  call    FltpInitNameControl
0x180022c1d  lea     rdx, [rsp+180h+String1]
0x180022c22  mov     rcx, r14
0x180022c25  call    FltpGetBaseDeviceObjectName
0x180022c2a  mov     r8d, 9F1h
0x180022c30  xor     r9d, r9d
0x180022c33  mov     rdx, r13
0x180022c36  mov     ecx, eax
0x180022c38  mov     edi, eax
0x180022c3a  call    FltpDbgStatus
0x180022c3f  test    eax, eax
0x180022c41  js      loc_180022D33
0x180022c47  xor     esi, esi
0x180022c49  lea     r12, FsTypes
0x180022c50  mov     edi, esi
0x180022c52  shl     rdi, 5
0x180022c56  cmp     dword ptr [rdi+r12], 0FFFFFFFFh
0x180022c5b  jz      short loc_180022C8B
0x180022c5d  lea     rdx, [r12+10h]
0x180022c62  mov     r8b, 1; CaseInSensitive
0x180022c65  add     rdx, rdi; String2
0x180022c68  lea     rcx, [rsp+180h+String1]; String1
0x180022c6d  call    cs:__imp_RtlEqualUnicodeString
0x180022c74  nop     dword ptr [rax+rax+00h]
0x180022c79  test    al, al
0x180022c7b  jnz     short loc_180022C81
0x180022c7d  inc     esi
0x180022c7f  jmp     short loc_180022C50
0x180022c81  mov     rcx, [rbx]
0x180022c84  mov     eax, [rdi+r12]
0x180022c88  mov     [rcx+4], eax
0x180022c8b  lea     rdx, [rsp+180h+DiskDeviceObject]; DiskDeviceObject
0x180022c90  mov     rcx, r14; FileSystemDeviceObject
0x180022c93  call    cs:__imp_IoGetDiskDeviceObject
0x180022c9a  nop     dword ptr [rax+rax+00h]
0x180022c9f  mov     r8d, 0A07h
0x180022ca5  xor     r9d, r9d
0x180022ca8  mov     ecx, eax
0x180022caa  mov     rdx, r13
0x180022cad  mov     edi, eax
0x180022caf  call    FltpDbgStatus
0x180022cb4  test    eax, eax
0x180022cb6  js      short loc_180022D33
0x180022cb8  mov     rcx, [rsp+180h+DiskDeviceObject]; Object
0x180022cbd  lea     rdx, [rsp+180h+String1]
0x180022cc2  call    FltpGetObjectName
0x180022cc7  mov     r8d, 0A0Eh
0x180022ccd  xor     r9d, r9d
0x180022cd0  mov     rdx, r13
0x180022cd3  mov     ecx, eax
0x180022cd5  mov     edi, eax
0x180022cd7  call    FltpDbgStatus
0x180022cdc  test    eax, eax
0x180022cde  js      short loc_180022D33
0x180022ce0  movzx   esi, [rsp+180h+String1.Length]
0x180022ce5  mov     ecx, 100h
0x180022cea  mov     edx, esi
0x180022cec  mov     r8d, 73754D46h
0x180022cf2  call    cs:__imp_ExAllocatePool2
0x180022cf9  nop     dword ptr [rax+rax+00h]
0x180022cfe  mov     rcx, rax
0x180022d01  test    rax, rax
0x180022d04  jnz     short loc_180022D0D
0x180022d06  mov     edi, 0C000009Ah
0x180022d0b  jmp     short loc_180022D33
0x180022d0d  mov     rax, [rbx]
0x180022d10  lea     rdx, [rsp+180h+String1]; SourceString
0x180022d15  mov     [rax+10h], rcx
0x180022d19  mov     rax, [rbx]
0x180022d1c  mov     [rax+0Ah], si
0x180022d20  mov     rcx, [rbx]
0x180022d23  add     rcx, 8; DestinationString
0x180022d27  call    cs:__imp_RtlCopyUnicodeString
0x180022d2e  nop     dword ptr [rax+rax+00h]
0x180022d33  mov     r8d, 0A25h
0x180022d39  xor     r9d, r9d
0x180022d3c  mov     rdx, r13
0x180022d3f  mov     ecx, edi
0x180022d41  call    FltpDbgStatus
0x180022d46  test    eax, eax
0x180022d48  jns     short loc_180022D59
0x180022d4a  mov     rcx, [rbx]; Entry
0x180022d4d  call    FltpFreeNameSupportVolumeInfo
0x180022d52  mov     qword ptr [rbx], 0
0x180022d59  mov     rcx, [rsp+180h+DiskDeviceObject]; Object
0x180022d5e  test    rcx, rcx
0x180022d61  jz      short loc_180022D6F
0x180022d63  call    cs:__imp_ObfDereferenceObject
0x180022d6a  nop     dword ptr [rax+rax+00h]
0x180022d6f  lea     rcx, [rsp+180h+String1]
0x180022d74  call    FltpCleanupNameControl
0x180022d79  mov     eax, edi
0x180022d7b  mov     rcx, [rbp+80h+var_30]
0x180022d7f  xor     rcx, rsp; StackCookie
0x180022d82  call    __security_check_cookie
0x180022d87  lea     r11, [rsp+180h+var_20]
0x180022d8f  mov     rbx, [r11+40h]
0x180022d93  mov     rsi, [r11+48h]
0x180022d97  mov     rsp, r11
0x180022d9a  pop     r14
0x180022d9c  pop     r13
0x180022d9e  pop     r12
0x180022da0  pop     rdi
0x180022da1  pop     rbp
0x180022da2  retn
```
