# SendIoctlToRedirector

- ea: `0x180011bd8`
- end: `0x180011fe6`
- name: `SendIoctlToRedirector`
- size: `1038`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e354`

## callees

- `0x1800016c8`
- `0x1800017f4`
- `0x180001901`
- `0x18000190d`
- `0x180011bd8`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180011d26`
- `msvcrt!wcscpy_s` at `0x180011e8a`
- `msvcrt!wcscpy_s` at `0x180011ead`
- `msvcrt!wcscpy_s` at `0x180011ee4`
- `msvcrt!wcscpy_s` at `0x180011d26`
- `msvcrt!wcscpy_s` at `0x180011e8a`
- `msvcrt!wcscpy_s` at `0x180011ead`
- `msvcrt!wcscpy_s` at `0x180011ee4`
- `msvcrt!wcsncpy_s` at `0x180011d58`
- `msvcrt!wcsncpy_s` at `0x180011d58`
- `ntdll!NtClose` at `0x180011f7e`
- `ntdll!NtClose` at `0x180011fcd`
- `ntdll!NtClose` at `0x180011f7e`
- `ntdll!NtClose` at `0x180011fcd`
- `ntdll!NtCreateFile` at `0x180011cc8`
- `ntdll!NtCreateFile` at `0x180011cc8`
- `ntdll!RtlInitUnicodeString` at `0x180011c51`
- `ntdll!RtlInitUnicodeString` at `0x180011c51`
- `ntdll!NtDeviceIoControlFile` at `0x180011f40`
- `ntdll!NtDeviceIoControlFile` at `0x180011f40`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180011f52`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180011f52`

## pseudocode

```c
__int64 __fastcall SendIoctlToRedirector(void *a1, __int64 a2)
{
  __int64 v3; // r13
  const wchar_t *v4; // rsi
  wchar_t *v5; // rdi
  int v6; // eax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r12
  __int64 v13; // r8
  __int64 v14; // rcx
  size_t v15; // r15
  char *v16; // rax
  char *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  _DWORD *v25; // rdi
  NTSTATUS v26; // eax
  ULONG v27; // eax
  int v28; // ecx
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  ULONG InputBufferLength; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  PVOID OutputBuffer; // [rsp+80h] [rbp-80h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t Destination[264]; // [rsp+D0h] [rbp-30h] BYREF

  OutputBuffer = a1;
  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  memset_0(Destination, 0, 0x208u);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\MRxNfs");
  DestinationString.MaximumLength -= 2;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtCreateFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0) )
  {
    *(_DWORD *)(a2 + 72) = 21;
    return 0;
  }
  v3 = *(_QWORD *)(a2 + 8);
  v4 = (const wchar_t *)(v3 + 16);
  if ( v3 == -16 )
  {
    *(_DWORD *)(a2 + 72) = 87;
LABEL_46:
    NtClose(FileHandle);
    return 0;
  }
  v5 = wcsstr_0((const wchar_t *)(v3 + 16), L"\\");
  if ( v5 )
  {
    v6 = 259;
    if ( (int)(((__int64)v5 - v3 - 16) >> 1) < 259 )
      v6 = ((__int64)v5 - v3 - 16) >> 1;
    v7 = v6;
    wcsncpy_s(Destination, 0x104u, (const wchar_t *)(v3 + 16), v6);
    v8 = v7;
    if ( v8 >= 260 )
      _report_rangecheckfailure();
    v4 = v5 + 1;
    Destination[v8] = 0;
  }
  else
  {
    wcscpy_s(Destination, 0x104u, &Source);
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( Destination[v10] );
  v11 = -1;
  do
    ++v11;
  while ( v4[v11] );
  v12 = v3 + 536;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(v12 + 2 * v13) );
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v3 + 2 * v14 + 1064) );
  InputBufferLength = 2 * (v13 + v14 + v11 + v10) + 80;
  v15 = InputBufferLength;
  v16 = (char *)malloc_0(InputBufferLength);
  v17 = v16;
  if ( !v16 )
  {
    *(_DWORD *)(a2 + 72) = -2147286787;
    goto LABEL_46;
  }
  memset_0(v16, 0, v15);
  v18 = -1;
  *(_QWORD *)v17 = v17 + 40;
  do
    ++v18;
  while ( v4[v18] );
  v19 = -1;
  *((_QWORD *)v17 + 1) = &v17[2 * v18 + 42];
  do
    ++v19;
  while ( v4[v19] );
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(v12 + 2 * v20) );
  *((_QWORD *)v17 + 3) = &v17[2 * v20 + 44 + 2 * v19];
  v21 = -1;
  do
    ++v21;
  while ( v4[v21] );
  v22 = -1;
  do
    ++v22;
  while ( *(_WORD *)(v12 + 2 * v22) );
  v23 = -1;
  *((_QWORD *)v17 + 4) = &v17[2 * v22 + 76 + 2 * v21];
  do
    ++v23;
  while ( v4[v23] );
  wcscpy_s((wchar_t *)v17 + 20, v23 + 1, v4);
  v24 = -1;
  do
    ++v24;
  while ( *(_WORD *)(v12 + 2 * v24) );
  wcscpy_s(*((wchar_t **)v17 + 1), v24 + 1, (const wchar_t *)(v3 + 536));
  if ( *(_DWORD *)(v3 + 1056) == 5 )
  {
    *((_DWORD *)v17 + 4) = 5;
    do
      ++v9;
    while ( Destination[v9] );
    wcscpy_s(*((wchar_t **)v17 + 4), v9 + 1, Destination);
  }
  else
  {
    *((_DWORD *)v17 + 4) = 0;
  }
  if ( (*(_BYTE *)(v3 + 1060) & 1) != 0 )
    *((_DWORD *)v17 + 5) |= 1u;
  v25 = OutputBuffer;
  v26 = NtDeviceIoControlFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          0x140800u,
          v17,
          InputBufferLength,
          OutputBuffer,
          0x4Cu);
  if ( v26 )
  {
    v27 = LsaNtStatusToWinError(v26);
    v28 = 1326;
    if ( v27 != 1326 )
      v28 = 21;
    *(_DWORD *)(a2 + 72) = v28;
    free_0(v17);
    goto LABEL_46;
  }
  if ( *v25 != -2 )
    *(_DWORD *)(a2 + 72) = 0;
  free_0(v17);
  NtClose(FileHandle);
  return 1;
}

```

## disassembly

```asm
0x180011bd8  mov     [rsp-8+arg_10], rbx
0x180011bdd  push    rbp
0x180011bde  push    rsi
0x180011bdf  push    rdi
0x180011be0  push    r12
0x180011be2  push    r13
0x180011be4  push    r14
0x180011be6  push    r15
0x180011be8  lea     rbp, [rsp-1F0h]
0x180011bf0  sub     rsp, 2F0h
0x180011bf7  mov     rax, cs:__security_cookie
0x180011bfe  xor     rax, rsp
0x180011c01  mov     [rbp+220h+var_40], rax
0x180011c08  xorps   xmm0, xmm0
0x180011c0b  mov     [rbp+220h+OutputBuffer], rcx
0x180011c0f  mov     r14, rdx
0x180011c12  lea     rcx, [rbp+220h+Destination]; void *
0x180011c16  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm0
0x180011c1a  mov     r12d, 208h
0x180011c20  xor     r15d, r15d
0x180011c23  mov     r8d, r12d; Size
0x180011c26  mov     [rsp+320h+FileHandle], r15
0x180011c2b  xor     eax, eax
0x180011c2d  xor     edx, edx; Val
0x180011c2f  movups  xmmword ptr [rbp+220h+ObjectAttributes+1Ch], xmm0
0x180011c33  movups  xmmword ptr [rbp+220h+IoStatusBlock], xmm0
0x180011c37  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm0
0x180011c3b  movups  xmmword ptr [rsp+320h+DestinationString.Length], xmm0
0x180011c40  call    memset_0
0x180011c45  lea     rdx, SourceString; "\\Device\\MRxNfs"
0x180011c4c  lea     rcx, [rsp+320h+DestinationString]; DestinationString
0x180011c51  call    cs:__imp_RtlInitUnicodeString
0x180011c58  nop     dword ptr [rax+rax+00h]
0x180011c5d  mov     [rsp+320h+EaLength], r15d; EaLength
0x180011c62  lea     r9, [rbp+220h+IoStatusBlock]; IoStatusBlock
0x180011c66  mov     [rsp+320h+EaBuffer], r15; EaBuffer
0x180011c6b  lea     r8, [rbp+220h+ObjectAttributes]; ObjectAttributes
0x180011c6f  mov     [rsp+320h+CreateOptions], 20h ; ' '; CreateOptions
0x180011c77  lea     rcx, [rsp+320h+FileHandle]; FileHandle
0x180011c7c  mov     [rsp+320h+CreateDisposition], 1; CreateDisposition
0x180011c84  mov     eax, 0FFFEh
0x180011c89  add     [rsp+320h+DestinationString.MaximumLength], ax
0x180011c8e  xorps   xmm0, xmm0
0x180011c91  lea     rax, [rsp+320h+DestinationString]
0x180011c96  mov     [rsp+320h+ShareAccess], 7; ShareAccess
0x180011c9e  mov     [rsp+320h+FileAttributes], 80h; FileAttributes
0x180011ca6  mov     edx, 100000h; DesiredAccess
0x180011cab  mov     [rbp+220h+ObjectAttributes.ObjectName], rax
0x180011caf  mov     [rsp+320h+AllocationSize], r15; AllocationSize
0x180011cb4  mov     [rbp+220h+ObjectAttributes.Length], 30h ; '0'
0x180011cbb  mov     [rbp+220h+ObjectAttributes.RootDirectory], r15
0x180011cbf  mov     [rbp+220h+ObjectAttributes.Attributes], r15d
0x180011cc3  movdqu  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x180011cc8  call    cs:__imp_NtCreateFile
0x180011ccf  nop     dword ptr [rax+rax+00h]
0x180011cd4  test    eax, eax
0x180011cd6  jz      short loc_180011CE5
0x180011cd8  mov     dword ptr [r14+48h], 15h
0x180011ce0  jmp     loc_180011F8A
0x180011ce5  mov     r13, [r14+8]
0x180011ce9  lea     rsi, [r13+10h]
0x180011ced  test    rsi, rsi
0x180011cf0  jnz     short loc_180011CFF
0x180011cf2  mov     dword ptr [r14+48h], 57h ; 'W'
0x180011cfa  jmp     loc_180011F79
0x180011cff  lea     rdx, SubStr; "\\"
0x180011d06  mov     rcx, rsi; Str
0x180011d09  call    wcsstr_0
0x180011d0e  mov     rdi, rax
0x180011d11  mov     edx, 104h; SizeInWords
0x180011d16  test    rax, rax
0x180011d19  jnz     short loc_180011D34
0x180011d1b  lea     r8, Source; Source
0x180011d22  lea     rcx, [rbp+220h+Destination]; Destination
0x180011d26  call    cs:__imp_wcscpy_s
0x180011d2d  nop     dword ptr [rax+rax+00h]
0x180011d32  jmp     short loc_180011D7A
0x180011d34  mov     eax, 103h
0x180011d39  mov     rcx, rdi
0x180011d3c  sub     rcx, r13
0x180011d3f  mov     r8, rsi; Source
0x180011d42  sub     rcx, 10h
0x180011d46  sar     rcx, 1
0x180011d49  cmp     ecx, eax
0x180011d4b  cmovl   eax, ecx
0x180011d4e  lea     rcx, [rbp+220h+Destination]; Destination
0x180011d52  movsxd  rbx, eax
0x180011d55  mov     r9, rbx; MaxCount
0x180011d58  call    cs:__imp_wcsncpy_s
0x180011d5f  nop     dword ptr [rax+rax+00h]
0x180011d64  add     rbx, rbx
0x180011d67  cmp     rbx, r12
0x180011d6a  jnb     loc_180011FE0
0x180011d70  lea     rsi, [rdi+2]
0x180011d74  mov     [rbp+rbx+220h+Destination], r15w
0x180011d7a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011d7e  lea     rcx, [rbp+220h+Destination]
0x180011d82  mov     rax, rdi
0x180011d85  inc     rax
0x180011d88  cmp     [rcx+rax*2], r15w
0x180011d8d  jnz     short loc_180011D85
0x180011d8f  mov     rdx, rdi
0x180011d92  inc     rdx
0x180011d95  cmp     [rsi+rdx*2], r15w
0x180011d9a  jnz     short loc_180011D92
0x180011d9c  lea     r12, [r13+218h]
0x180011da3  mov     r8, rdi
0x180011da6  inc     r8
0x180011da9  cmp     [r12+r8*2], r15w
0x180011dae  jnz     short loc_180011DA6
0x180011db0  mov     rcx, rdi
0x180011db3  inc     rcx
0x180011db6  cmp     [r13+rcx*2+428h], r15w
0x180011dbf  jnz     short loc_180011DB3
0x180011dc1  add     eax, edx
0x180011dc3  add     eax, ecx
0x180011dc5  add     eax, r8d
0x180011dc8  lea     eax, ds:50h[rax*2]
0x180011dcf  mov     ecx, eax; Size
0x180011dd1  mov     [rsp+320h+InputBufferLength], eax
0x180011dd5  mov     r15d, eax
0x180011dd8  call    malloc_0
0x180011ddd  mov     rbx, rax
0x180011de0  test    rax, rax
0x180011de3  jnz     short loc_180011DF2
0x180011de5  mov     dword ptr [r14+48h], 800300FDh
0x180011ded  jmp     loc_180011F79
0x180011df2  mov     r8, r15; Size
0x180011df5  xor     edx, edx; Val
0x180011df7  mov     rcx, rbx; void *
0x180011dfa  call    memset_0
0x180011dff  lea     r9, [rbx+28h]
0x180011e03  mov     rax, rdi
0x180011e06  mov     [rbx], r9
0x180011e09  xor     r15d, r15d
0x180011e0c  inc     rax
0x180011e0f  cmp     [rsi+rax*2], r15w
0x180011e14  jnz     short loc_180011E0C
0x180011e16  add     rax, 15h
0x180011e1a  mov     rcx, rdi
0x180011e1d  lea     rax, [rbx+rax*2]
0x180011e21  mov     [rbx+8], rax
0x180011e25  inc     rcx
0x180011e28  cmp     [rsi+rcx*2], r15w
0x180011e2d  jnz     short loc_180011E25
0x180011e2f  mov     rax, rdi
0x180011e32  inc     rax
0x180011e35  cmp     [r12+rax*2], r15w
0x180011e3a  jnz     short loc_180011E32
0x180011e3c  add     rcx, 16h
0x180011e40  add     rcx, rax
0x180011e43  lea     rcx, [rbx+rcx*2]
0x180011e47  mov     [rbx+18h], rcx
0x180011e4b  mov     rcx, rdi
0x180011e4e  inc     rcx
0x180011e51  cmp     [rsi+rcx*2], r15w
0x180011e56  jnz     short loc_180011E4E
0x180011e58  mov     rax, rdi
0x180011e5b  inc     rax
0x180011e5e  cmp     [r12+rax*2], r15w
0x180011e63  jnz     short loc_180011E5B
0x180011e65  add     rcx, 26h ; '&'
0x180011e69  mov     rdx, rdi
0x180011e6c  add     rcx, rax
0x180011e6f  lea     rcx, [rbx+rcx*2]
0x180011e73  mov     [rbx+20h], rcx
0x180011e77  inc     rdx
0x180011e7a  cmp     [rsi+rdx*2], r15w
0x180011e7f  jnz     short loc_180011E77
0x180011e81  inc     rdx; SizeInWords
0x180011e84  mov     r8, rsi; Source
0x180011e87  mov     rcx, r9; Destination
0x180011e8a  call    cs:__imp_wcscpy_s
0x180011e91  nop     dword ptr [rax+rax+00h]
0x180011e96  mov     rdx, rdi
0x180011e99  inc     rdx
0x180011e9c  cmp     [r12+rdx*2], r15w
0x180011ea1  jnz     short loc_180011E99
0x180011ea3  mov     rcx, [rbx+8]; Destination
0x180011ea7  inc     rdx; SizeInWords
0x180011eaa  mov     r8, r12; Source
0x180011ead  call    cs:__imp_wcscpy_s
0x180011eb4  nop     dword ptr [rax+rax+00h]
0x180011eb9  cmp     dword ptr [r13+420h], 5
0x180011ec1  jnz     short loc_180011EF2
0x180011ec3  mov     dword ptr [rbx+10h], 5
0x180011eca  lea     rax, [rbp+220h+Destination]
0x180011ece  inc     rdi
0x180011ed1  cmp     [rax+rdi*2], r15w
0x180011ed6  jnz     short loc_180011ECE
0x180011ed8  mov     rcx, [rbx+20h]; Destination
0x180011edc  lea     rdx, [rdi+1]; SizeInWords
0x180011ee0  lea     r8, [rbp+220h+Destination]; Source
0x180011ee4  call    cs:__imp_wcscpy_s
0x180011eeb  nop     dword ptr [rax+rax+00h]
0x180011ef0  jmp     short loc_180011EF6
0x180011ef2  mov     [rbx+10h], r15d
0x180011ef6  test    byte ptr [r13+424h], 1
0x180011efe  jz      short loc_180011F04
0x180011f00  or      dword ptr [rbx+14h], 1
0x180011f04  mov     eax, [rsp+320h+InputBufferLength]
0x180011f08  xor     r9d, r9d; ApcContext
0x180011f0b  mov     rdi, [rbp+220h+OutputBuffer]
0x180011f0f  xor     r8d, r8d; ApcRoutine
0x180011f12  mov     rcx, [rsp+320h+FileHandle]; FileHandle
0x180011f17  xor     edx, edx; Event
0x180011f19  mov     dword ptr [rsp+320h+EaBuffer], 4Ch ; 'L'; OutputBufferLength
0x180011f21  mov     qword ptr [rsp+320h+CreateOptions], rdi; OutputBuffer
0x180011f26  mov     [rsp+320h+CreateDisposition], eax; InputBufferLength
0x180011f2a  lea     rax, [rbp+220h+IoStatusBlock]
0x180011f2e  mov     qword ptr [rsp+320h+ShareAccess], rbx; InputBuffer
0x180011f33  mov     [rsp+320h+FileAttributes], 140800h; IoControlCode
0x180011f3b  mov     [rsp+320h+AllocationSize], rax; IoStatusBlock
0x180011f40  call    cs:__imp_NtDeviceIoControlFile
0x180011f47  nop     dword ptr [rax+rax+00h]
0x180011f4c  test    eax, eax
0x180011f4e  jz      short loc_180011FB7
0x180011f50  mov     ecx, eax; Status
0x180011f52  call    cs:__imp_LsaNtStatusToWinError
0x180011f59  nop     dword ptr [rax+rax+00h]
0x180011f5e  mov     ecx, 52Eh
0x180011f63  mov     edx, 15h
0x180011f68  cmp     eax, ecx
0x180011f6a  cmovnz  ecx, edx
0x180011f6d  mov     [r14+48h], ecx
0x180011f71  mov     rcx, rbx; Block
0x180011f74  call    free_0
0x180011f79  mov     rcx, [rsp+320h+FileHandle]; Handle
0x180011f7e  call    cs:__imp_NtClose
0x180011f85  nop     dword ptr [rax+rax+00h]
0x180011f8a  xor     eax, eax
0x180011f8c  mov     rcx, [rbp+220h+var_40]
0x180011f93  xor     rcx, rsp; StackCookie
0x180011f96  call    __security_check_cookie
0x180011f9b  mov     rbx, [rsp+320h+arg_10]
0x180011fa3  add     rsp, 2F0h
0x180011faa  pop     r15
0x180011fac  pop     r14
0x180011fae  pop     r13
0x180011fb0  pop     r12
0x180011fb2  pop     rdi
0x180011fb3  pop     rsi
0x180011fb4  pop     rbp
0x180011fb5  retn
0x180011fb7  cmp     dword ptr [rdi], 0FFFFFFFEh
0x180011fba  jz      short loc_180011FC0
0x180011fbc  mov     [r14+48h], r15d
0x180011fc0  mov     rcx, rbx; Block
0x180011fc3  call    free_0
0x180011fc8  mov     rcx, [rsp+320h+FileHandle]; Handle
0x180011fcd  call    cs:__imp_NtClose
0x180011fd4  nop     dword ptr [rax+rax+00h]
0x180011fd9  mov     eax, 1
0x180011fde  jmp     short loc_180011F8C
0x180011fe0  call    __report_rangecheckfailure
```
