# CiGetBuildExpiryTime

- ea: `0x18009daf0`
- end: `0x18009ddb0`
- name: `CiGetBuildExpiryTime`
- size: `704`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002c0d0`
- `0x18008eddc`
- `0x18009daf0`
- `0x18009ddb8`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x18009db94`
- `ntoskrnl!KeStackAttachProcess` at `0x18009db94`
- `ntoskrnl!ZwOpenFile` at `0x18009dbe3`
- `ntoskrnl!ZwOpenFile` at `0x18009dbe3`
- `ntoskrnl!ZwClose` at `0x18009dd41`
- `ntoskrnl!ZwClose` at `0x18009dda2`
- `ntoskrnl!ZwClose` at `0x18009dd41`
- `ntoskrnl!ZwClose` at `0x18009dda2`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009dd51`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009dd51`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009dd1a`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009dd1a`
- `ntoskrnl!ZwCreateSection` at `0x18009dc7e`
- `ntoskrnl!ZwCreateSection` at `0x18009dc7e`
- `ntoskrnl!ZwMapViewOfSection` at `0x18009dcd2`
- `ntoskrnl!ZwMapViewOfSection` at `0x18009dcd2`
- `ntoskrnl!ZwQueryInformationFile` at `0x18009dc10`
- `ntoskrnl!ZwQueryInformationFile` at `0x18009dc10`

## string_xrefs

- `0x18009db2b`: `\SystemRoot\System32\ci.dll`

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
0x18009daf0  mov     [rsp-8+arg_8], rbx
0x18009daf5  mov     [rsp-8+arg_10], rsi
0x18009dafa  push    rbp
0x18009dafb  push    rdi
0x18009dafc  push    r14
0x18009dafe  lea     rbp, [rsp-90h]
0x18009db06  sub     rsp, 190h
0x18009db0d  mov     rax, cs:__security_cookie
0x18009db14  xor     rax, rsp
0x18009db17  mov     [rbp+0A0h+var_18], rax
0x18009db1e  xorps   xmm0, xmm0
0x18009db21  mov     [rbp+0A0h+var_D0], 380036h
0x18009db29  xor     esi, esi
0x18009db2b  lea     rax, aSystemrootSyst_1; "\\SystemRoot\\System32\\ci.dll"
0x18009db32  mov     [rbp+0A0h+var_C8], rax
0x18009db36  lea     rdx, [rbp+0A0h+ApcState]; ApcState
0x18009db3a  xor     eax, eax
0x18009db3c  mov     [rbp+0A0h+FileHandle], rsi
0x18009db40  mov     rdi, rcx
0x18009db43  mov     [rbp+0A0h+var_50], rax
0x18009db47  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18009db4e  mov     r14d, 38h ; '8'
0x18009db54  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x18009db58  mov     [rbp+0A0h+SectionHandle], rsi
0x18009db5c  movups  xmmword ptr [rbp+0A0h+ApcState.ApcListHead.Flink], xmm0
0x18009db60  mov     [rbp+0A0h+BaseAddress], rsi
0x18009db64  movups  xmmword ptr [rbp+0A0h+ApcState.ApcListHead.Flink+10h], xmm0
0x18009db68  mov     [rbp+0A0h+ViewSize], rsi
0x18009db6c  movups  xmmword ptr [rbp+0A0h+ApcState.Process], xmm0
0x18009db70  movups  [rbp+0A0h+FileInformation], xmm0
0x18009db74  movups  [rbp+0A0h+var_70], xmm0
0x18009db78  movups  [rbp+0A0h+var_60], xmm0
0x18009db7c  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x18009db80  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x18009db84  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x18009db88  movups  [rbp+0A0h+var_B0], xmm0
0x18009db8c  movups  [rbp+0A0h+var_A0], xmm0
0x18009db90  movups  [rbp+0A0h+var_90], xmm0
0x18009db94  call    cs:__imp_KeStackAttachProcess
0x18009db9b  nop     dword ptr [rax+rax+00h]
0x18009dba0  lea     rax, [rbp+0A0h+var_D0]
0x18009dba4  mov     [rsp+1A0h+OpenOptions], 60h ; '`'; OpenOptions
0x18009dbac  xorps   xmm0, xmm0
0x18009dbaf  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x18009dbb3  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x18009dbb7  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18009dbbe  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x18009dbc2  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rsi
0x18009dbc6  mov     edx, 80000000h; DesiredAccess
0x18009dbcb  mov     [rbp+0A0h+ObjectAttributes.Attributes], 2C0h
0x18009dbd2  lea     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x18009dbd6  mov     [rsp+1A0h+ShareAccess], 1; ShareAccess
0x18009dbde  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009dbe3  call    cs:__imp_ZwOpenFile
0x18009dbea  nop     dword ptr [rax+rax+00h]
0x18009dbef  mov     ebx, eax
0x18009dbf1  test    eax, eax
0x18009dbf3  js      loc_18009DD2A
0x18009dbf9  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x18009dbfd  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x18009dc01  mov     r9d, r14d; Length
0x18009dc04  mov     [rsp+1A0h+ShareAccess], 22h ; '"'; FileInformationClass
0x18009dc0c  lea     rdx, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x18009dc10  call    cs:__imp_ZwQueryInformationFile
0x18009dc17  nop     dword ptr [rax+rax+00h]
0x18009dc1c  mov     ebx, eax
0x18009dc1e  test    eax, eax
0x18009dc20  js      loc_18009DD2A
0x18009dc26  cmp     dword ptr [rbp+0A0h+var_60+0Ch], esi
0x18009dc29  jnz     loc_18009DD9B
0x18009dc2f  cmp     dword ptr [rbp+0A0h+var_60+8], esi
0x18009dc32  jz      loc_18009DD9B
0x18009dc38  mov     rax, [rbp+0A0h+FileHandle]
0x18009dc3c  lea     r14d, [rsi+2]
0x18009dc40  mov     [rsp+1A0h+var_170], rax; FileHandle
0x18009dc45  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x18009dc49  xorps   xmm0, xmm0
0x18009dc4c  mov     [rsp+1A0h+OpenOptions], 8000000h; AllocationAttributes
0x18009dc54  xor     r9d, r9d; MaximumSize
0x18009dc57  mov     [rsp+1A0h+ShareAccess], r14d; SectionPageProtection
0x18009dc5c  lea     edx, [rsi+4]; DesiredAccess
0x18009dc5f  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18009dc66  lea     rcx, [rbp+0A0h+SectionHandle]; SectionHandle
0x18009dc6a  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rsi
0x18009dc6e  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x18009dc75  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rsi
0x18009dc79  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009dc7e  call    cs:__imp_ZwCreateSection
0x18009dc85  nop     dword ptr [rax+rax+00h]
0x18009dc8a  mov     ebx, eax
0x18009dc8c  test    eax, eax
0x18009dc8e  js      loc_18009DD2A
0x18009dc94  mov     eax, dword ptr [rbp+0A0h+var_60+8]
0x18009dc97  lea     r8, [rbp+0A0h+BaseAddress]; BaseAddress
0x18009dc9b  mov     rcx, [rbp+0A0h+SectionHandle]; SectionHandle
0x18009dc9f  xor     r9d, r9d; ZeroBits
0x18009dca2  mov     [rsp+1A0h+Win32Protect], r14d; Win32Protect
0x18009dca7  mov     [rsp+1A0h+AllocationType], esi; AllocationType
0x18009dcab  mov     [rsp+1A0h+InheritDisposition], r14d; InheritDisposition
0x18009dcb0  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009dcb4  mov     [rbp+0A0h+ViewSize], rax
0x18009dcb8  mov     rdx, r14; ProcessHandle
0x18009dcbb  lea     rax, [rbp+0A0h+ViewSize]
0x18009dcbf  mov     [rbp+0A0h+BaseAddress], rsi
0x18009dcc3  mov     [rsp+1A0h+var_170], rax; ViewSize
0x18009dcc8  mov     qword ptr [rsp+1A0h+OpenOptions], rsi; SectionOffset
0x18009dccd  mov     qword ptr [rsp+1A0h+ShareAccess], rsi; CommitSize
0x18009dcd2  call    cs:__imp_ZwMapViewOfSection
0x18009dcd9  nop     dword ptr [rax+rax+00h]
0x18009dcde  mov     ebx, eax
0x18009dce0  test    eax, eax
0x18009dce2  js      short loc_18009DD2A
0x18009dce4  mov     edx, dword ptr [rbp+0A0h+var_60+8]
0x18009dce7  lea     rax, [rbp+0A0h+var_B0]
0x18009dceb  mov     rcx, [rbp+0A0h+BaseAddress]
0x18009dcef  lea     r9d, [rsi+1]
0x18009dcf3  mov     [rsp+1A0h+var_138], rsi
0x18009dcf8  mov     qword ptr [rsp+1A0h+AllocationType], rax
0x18009dcfd  mov     qword ptr [rsp+1A0h+InheritDisposition], rsi
0x18009dd02  mov     byte ptr [rsp+1A0h+OpenOptions], 1
0x18009dd07  mov     byte ptr [rsp+1A0h+ShareAccess], 0Ch
0x18009dd0c  call    CipValidateDataMappedFile
0x18009dd11  mov     rdx, [rbp+0A0h+BaseAddress]; BaseAddress
0x18009dd15  mov     rcx, r14; ProcessHandle
0x18009dd18  mov     ebx, eax
0x18009dd1a  call    cs:__imp_ZwUnmapViewOfSection
0x18009dd21  nop     dword ptr [rax+rax+00h]
0x18009dd26  test    ebx, ebx
0x18009dd28  jns     short loc_18009DD92
0x18009dd2a  cmp     dword ptr [rbp+0A0h+var_B0], esi
0x18009dd2d  jnz     short loc_18009DD87
0x18009dd2f  mov     rcx, [rbp+0A0h+SectionHandle]; Handle
0x18009dd33  test    rcx, rcx
0x18009dd36  jnz     short loc_18009DDA2
0x18009dd38  mov     rcx, [rbp+0A0h+FileHandle]; Handle
0x18009dd3c  test    rcx, rcx
0x18009dd3f  jz      short loc_18009DD4D
0x18009dd41  call    cs:__imp_ZwClose
0x18009dd48  nop     dword ptr [rax+rax+00h]
0x18009dd4d  lea     rcx, [rbp+0A0h+ApcState]; ApcState
0x18009dd51  call    cs:__imp_KeUnstackDetachProcess
0x18009dd58  nop     dword ptr [rax+rax+00h]
0x18009dd5d  mov     eax, ebx
0x18009dd5f  mov     rcx, [rbp+0A0h+var_18]
0x18009dd66  xor     rcx, rsp; StackCookie
0x18009dd69  call    __security_check_cookie
0x18009dd6e  lea     r11, [rsp+1A0h+var_10]
0x18009dd76  mov     rbx, [r11+28h]
0x18009dd7a  mov     rsi, [r11+30h]
0x18009dd7e  mov     rsp, r11
0x18009dd81  pop     r14
0x18009dd83  pop     rdi
0x18009dd84  pop     rbp
0x18009dd85  retn
0x18009dd87  mov     rcx, qword ptr [rbp+0A0h+var_A0]
0x18009dd8b  call    I_MincryptFreeChainInfo
0x18009dd90  jmp     short loc_18009DD2F
0x18009dd92  mov     rax, qword ptr [rbp+0A0h+var_90+8]
0x18009dd96  mov     [rdi], rax
0x18009dd99  jmp     short loc_18009DD2A
0x18009dd9b  mov     ebx, 0C0000020h
0x18009dda0  jmp     short loc_18009DD2A
0x18009dda2  call    cs:__imp_ZwClose
0x18009dda9  nop     dword ptr [rax+rax+00h]
0x18009ddae  jmp     short loc_18009DD38
```
