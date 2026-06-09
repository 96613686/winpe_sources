# CiGetBuildExpiryTime

- ea: `0x180098cc0`
- end: `0x180098f80`
- name: `CiGetBuildExpiryTime`
- size: `704`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002bf20`
- `0x18009860c`
- `0x180098cc0`
- `0x180098f88`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180098d64`
- `ntoskrnl!KeStackAttachProcess` at `0x180098d64`
- `ntoskrnl!ZwOpenFile` at `0x180098db3`
- `ntoskrnl!ZwOpenFile` at `0x180098db3`
- `ntoskrnl!ZwClose` at `0x180098f11`
- `ntoskrnl!ZwClose` at `0x180098f72`
- `ntoskrnl!ZwClose` at `0x180098f11`
- `ntoskrnl!ZwClose` at `0x180098f72`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180098f21`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180098f21`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180098eea`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180098eea`
- `ntoskrnl!ZwCreateSection` at `0x180098e4e`
- `ntoskrnl!ZwCreateSection` at `0x180098e4e`
- `ntoskrnl!ZwMapViewOfSection` at `0x180098ea2`
- `ntoskrnl!ZwMapViewOfSection` at `0x180098ea2`
- `ntoskrnl!ZwQueryInformationFile` at `0x180098de0`
- `ntoskrnl!ZwQueryInformationFile` at `0x180098de0`

## string_xrefs

- `0x180098cfb`: `\SystemRoot\System32\ci.dll`

## pseudocode

```c
__int64 __fastcall CiGetBuildExpiryTime(_QWORD *a1)
{
  int v2; // ebx
  int v3; // r8d
  int v5; // [rsp+30h] [rbp-D0h]
  ULONG Win32Protect; // [rsp+48h] [rbp-B8h]
  PVOID BaseAddress; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  void *SectionHandle; // [rsp+90h] [rbp-70h] BYREF
  ULONG_PTR ViewSize; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v12[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v14; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v15; // [rsp+100h] [rbp+0h]
  __int128 v16; // [rsp+110h] [rbp+10h]
  _OWORD FileInformation[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v18; // [rsp+140h] [rbp+40h]
  __int64 v19; // [rsp+150h] [rbp+50h]
  struct _KAPC_STATE ApcState; // [rsp+158h] [rbp+58h] BYREF

  v12[0] = 3670070;
  v12[1] = L"\\SystemRoot\\System32\\ci.dll";
  FileHandle = 0;
  v19 = 0;
  SectionHandle = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  BaseAddress = 0;
  ViewSize = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v18 = 0;
  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  KeStackAttachProcess(g_CiSystemProcess, &ApcState);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 704;
  v2 = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 1u, 0x60u);
  if ( v2 >= 0 )
  {
    v2 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x38u, FileNetworkOpenInformation);
    if ( v2 >= 0 )
    {
      if ( HIDWORD(v18) || !DWORD2(v18) )
      {
        v2 = -1073741792;
      }
      else
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v2 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
        if ( v2 >= 0 )
        {
          ViewSize = DWORD2(v18);
          BaseAddress = 0;
          v2 = ZwMapViewOfSection(
                 SectionHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &BaseAddress,
                 0,
                 0,
                 0,
                 &ViewSize,
                 ViewUnmap,
                 0,
                 2u);
          if ( v2 >= 0 )
          {
            v2 = CipValidateDataMappedFile(
                   (_DWORD)BaseAddress,
                   DWORD2(v18),
                   v3,
                   1,
                   12,
                   1,
                   v5,
                   0,
                   (__int64)&v14,
                   Win32Protect);
            ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
            if ( v2 >= 0 )
              *a1 = *((_QWORD *)&v16 + 1);
          }
        }
      }
    }
  }
  if ( (_DWORD)v14 )
    I_MincryptFreeChainInfo(v15);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  KeUnstackDetachProcess(&ApcState);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180098cc0  mov     [rsp-8+arg_8], rbx
0x180098cc5  mov     [rsp-8+arg_10], rsi
0x180098cca  push    rbp
0x180098ccb  push    rdi
0x180098ccc  push    r14
0x180098cce  lea     rbp, [rsp-90h]
0x180098cd6  sub     rsp, 190h
0x180098cdd  mov     rax, cs:__security_cookie
0x180098ce4  xor     rax, rsp
0x180098ce7  mov     [rbp+0A0h+var_18], rax
0x180098cee  xorps   xmm0, xmm0
0x180098cf1  mov     [rbp+0A0h+var_D0], 380036h
0x180098cf9  xor     esi, esi
0x180098cfb  lea     rax, aSystemrootSyst_1; "\\SystemRoot\\System32\\ci.dll"
0x180098d02  mov     [rbp+0A0h+var_C8], rax
0x180098d06  lea     rdx, [rbp+0A0h+ApcState]; ApcState
0x180098d0a  xor     eax, eax
0x180098d0c  mov     [rbp+0A0h+FileHandle], rsi
0x180098d10  mov     rdi, rcx
0x180098d13  mov     [rbp+0A0h+var_50], rax
0x180098d17  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180098d1e  mov     r14d, 38h ; '8'
0x180098d24  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x180098d28  mov     [rbp+0A0h+SectionHandle], rsi
0x180098d2c  movups  xmmword ptr [rbp+0A0h+ApcState.ApcListHead.Flink], xmm0
0x180098d30  mov     [rbp+0A0h+BaseAddress], rsi
0x180098d34  movups  xmmword ptr [rbp+0A0h+ApcState.ApcListHead.Flink+10h], xmm0
0x180098d38  mov     [rbp+0A0h+ViewSize], rsi
0x180098d3c  movups  xmmword ptr [rbp+0A0h+ApcState.Process], xmm0
0x180098d40  movups  [rbp+0A0h+FileInformation], xmm0
0x180098d44  movups  [rbp+0A0h+var_70], xmm0
0x180098d48  movups  [rbp+0A0h+var_60], xmm0
0x180098d4c  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x180098d50  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x180098d54  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x180098d58  movups  [rbp+0A0h+var_B0], xmm0
0x180098d5c  movups  [rbp+0A0h+var_A0], xmm0
0x180098d60  movups  [rbp+0A0h+var_90], xmm0
0x180098d64  call    cs:__imp_KeStackAttachProcess
0x180098d6b  nop     dword ptr [rax+rax+00h]
0x180098d70  lea     rax, [rbp+0A0h+var_D0]
0x180098d74  mov     [rsp+1A0h+OpenOptions], 60h ; '`'; OpenOptions
0x180098d7c  xorps   xmm0, xmm0
0x180098d7f  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x180098d83  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x180098d87  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x180098d8e  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x180098d92  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rsi
0x180098d96  mov     edx, 80000000h; DesiredAccess
0x180098d9b  mov     [rbp+0A0h+ObjectAttributes.Attributes], 2C0h
0x180098da2  lea     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x180098da6  mov     [rsp+1A0h+ShareAccess], 1; ShareAccess
0x180098dae  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180098db3  call    cs:__imp_ZwOpenFile
0x180098dba  nop     dword ptr [rax+rax+00h]
0x180098dbf  mov     ebx, eax
0x180098dc1  test    eax, eax
0x180098dc3  js      loc_180098EFA
0x180098dc9  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x180098dcd  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x180098dd1  mov     r9d, r14d; Length
0x180098dd4  mov     [rsp+1A0h+ShareAccess], 22h ; '"'; FileInformationClass
0x180098ddc  lea     rdx, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x180098de0  call    cs:__imp_ZwQueryInformationFile
0x180098de7  nop     dword ptr [rax+rax+00h]
0x180098dec  mov     ebx, eax
0x180098dee  test    eax, eax
0x180098df0  js      loc_180098EFA
0x180098df6  cmp     dword ptr [rbp+0A0h+var_60+0Ch], esi
0x180098df9  jnz     loc_180098F6B
0x180098dff  cmp     dword ptr [rbp+0A0h+var_60+8], esi
0x180098e02  jz      loc_180098F6B
0x180098e08  mov     rax, [rbp+0A0h+FileHandle]
0x180098e0c  lea     r14d, [rsi+2]
0x180098e10  mov     [rsp+1A0h+var_170], rax; FileHandle
0x180098e15  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x180098e19  xorps   xmm0, xmm0
0x180098e1c  mov     [rsp+1A0h+OpenOptions], 8000000h; AllocationAttributes
0x180098e24  xor     r9d, r9d; MaximumSize
0x180098e27  mov     [rsp+1A0h+ShareAccess], r14d; SectionPageProtection
0x180098e2c  lea     edx, [rsi+4]; DesiredAccess
0x180098e2f  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x180098e36  lea     rcx, [rbp+0A0h+SectionHandle]; SectionHandle
0x180098e3a  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rsi
0x180098e3e  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x180098e45  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rsi
0x180098e49  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180098e4e  call    cs:__imp_ZwCreateSection
0x180098e55  nop     dword ptr [rax+rax+00h]
0x180098e5a  mov     ebx, eax
0x180098e5c  test    eax, eax
0x180098e5e  js      loc_180098EFA
0x180098e64  mov     eax, dword ptr [rbp+0A0h+var_60+8]
0x180098e67  lea     r8, [rbp+0A0h+BaseAddress]; BaseAddress
0x180098e6b  mov     rcx, [rbp+0A0h+SectionHandle]; SectionHandle
0x180098e6f  xor     r9d, r9d; ZeroBits
0x180098e72  mov     [rsp+1A0h+Win32Protect], r14d; Win32Protect
0x180098e77  mov     [rsp+1A0h+AllocationType], esi; AllocationType
0x180098e7b  mov     [rsp+1A0h+InheritDisposition], r14d; InheritDisposition
0x180098e80  or      r14, 0FFFFFFFFFFFFFFFFh
0x180098e84  mov     [rbp+0A0h+ViewSize], rax
0x180098e88  mov     rdx, r14; ProcessHandle
0x180098e8b  lea     rax, [rbp+0A0h+ViewSize]
0x180098e8f  mov     [rbp+0A0h+BaseAddress], rsi
0x180098e93  mov     [rsp+1A0h+var_170], rax; ViewSize
0x180098e98  mov     qword ptr [rsp+1A0h+OpenOptions], rsi; SectionOffset
0x180098e9d  mov     qword ptr [rsp+1A0h+ShareAccess], rsi; CommitSize
0x180098ea2  call    cs:__imp_ZwMapViewOfSection
0x180098ea9  nop     dword ptr [rax+rax+00h]
0x180098eae  mov     ebx, eax
0x180098eb0  test    eax, eax
0x180098eb2  js      short loc_180098EFA
0x180098eb4  mov     edx, dword ptr [rbp+0A0h+var_60+8]
0x180098eb7  lea     rax, [rbp+0A0h+var_B0]
0x180098ebb  mov     rcx, [rbp+0A0h+BaseAddress]
0x180098ebf  lea     r9d, [rsi+1]
0x180098ec3  mov     [rsp+1A0h+var_138], rsi
0x180098ec8  mov     qword ptr [rsp+1A0h+AllocationType], rax
0x180098ecd  mov     qword ptr [rsp+1A0h+InheritDisposition], rsi
0x180098ed2  mov     byte ptr [rsp+1A0h+OpenOptions], 1
0x180098ed7  mov     byte ptr [rsp+1A0h+ShareAccess], 0Ch
0x180098edc  call    CipValidateDataMappedFile
0x180098ee1  mov     rdx, [rbp+0A0h+BaseAddress]; BaseAddress
0x180098ee5  mov     rcx, r14; ProcessHandle
0x180098ee8  mov     ebx, eax
0x180098eea  call    cs:__imp_ZwUnmapViewOfSection
0x180098ef1  nop     dword ptr [rax+rax+00h]
0x180098ef6  test    ebx, ebx
0x180098ef8  jns     short loc_180098F62
0x180098efa  cmp     dword ptr [rbp+0A0h+var_B0], esi
0x180098efd  jnz     short loc_180098F57
0x180098eff  mov     rcx, [rbp+0A0h+SectionHandle]; Handle
0x180098f03  test    rcx, rcx
0x180098f06  jnz     short loc_180098F72
0x180098f08  mov     rcx, [rbp+0A0h+FileHandle]; Handle
0x180098f0c  test    rcx, rcx
0x180098f0f  jz      short loc_180098F1D
0x180098f11  call    cs:__imp_ZwClose
0x180098f18  nop     dword ptr [rax+rax+00h]
0x180098f1d  lea     rcx, [rbp+0A0h+ApcState]; ApcState
0x180098f21  call    cs:__imp_KeUnstackDetachProcess
0x180098f28  nop     dword ptr [rax+rax+00h]
0x180098f2d  mov     eax, ebx
0x180098f2f  mov     rcx, [rbp+0A0h+var_18]
0x180098f36  xor     rcx, rsp; StackCookie
0x180098f39  call    __security_check_cookie
0x180098f3e  lea     r11, [rsp+1A0h+var_10]
0x180098f46  mov     rbx, [r11+28h]
0x180098f4a  mov     rsi, [r11+30h]
0x180098f4e  mov     rsp, r11
0x180098f51  pop     r14
0x180098f53  pop     rdi
0x180098f54  pop     rbp
0x180098f55  retn
0x180098f57  mov     rcx, qword ptr [rbp+0A0h+var_A0]
0x180098f5b  call    I_MincryptFreeChainInfo
0x180098f60  jmp     short loc_180098EFF
0x180098f62  mov     rax, qword ptr [rbp+0A0h+var_90+8]
0x180098f66  mov     [rdi], rax
0x180098f69  jmp     short loc_180098EFA
0x180098f6b  mov     ebx, 0C0000020h
0x180098f70  jmp     short loc_180098EFA
0x180098f72  call    cs:__imp_ZwClose
0x180098f79  nop     dword ptr [rax+rax+00h]
0x180098f7e  jmp     short loc_180098F08
```
