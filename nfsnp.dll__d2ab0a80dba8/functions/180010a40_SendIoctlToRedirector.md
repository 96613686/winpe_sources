# SendIoctlToRedirector

- ea: `0x180010a40`
- end: `0x180010e0b`
- name: `SendIoctlToRedirector`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d758`

## callees

- `0x1800016c8`
- `0x1800017f4`
- `0x180001901`
- `0x18000190d`
- `0x180010a40`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010b82`
- `msvcrt!wcscpy_s` at `0x180010cda`
- `msvcrt!wcscpy_s` at `0x180010cf7`
- `msvcrt!wcscpy_s` at `0x180010d28`
- `msvcrt!wcscpy_s` at `0x180010b82`
- `msvcrt!wcscpy_s` at `0x180010cda`
- `msvcrt!wcscpy_s` at `0x180010cf7`
- `msvcrt!wcscpy_s` at `0x180010d28`
- `msvcrt!wcsncpy_s` at `0x180010bae`
- `msvcrt!wcsncpy_s` at `0x180010bae`
- `ntdll!NtClose` at `0x180010db0`
- `ntdll!NtClose` at `0x180010df8`
- `ntdll!NtClose` at `0x180010db0`
- `ntdll!NtClose` at `0x180010df8`
- `ntdll!NtCreateFile` at `0x180010b2a`
- `ntdll!NtCreateFile` at `0x180010b2a`
- `ntdll!RtlInitUnicodeString` at `0x180010ab9`
- `ntdll!RtlInitUnicodeString` at `0x180010ab9`
- `ntdll!NtDeviceIoControlFile` at `0x180010d7e`
- `ntdll!NtDeviceIoControlFile` at `0x180010d7e`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180010d8a`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180010d8a`

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
0x180010a40  mov     [rsp-8+arg_10], rbx
0x180010a45  push    rbp
0x180010a46  push    rsi
0x180010a47  push    rdi
0x180010a48  push    r12
0x180010a4a  push    r13
0x180010a4c  push    r14
0x180010a4e  push    r15
0x180010a50  lea     rbp, [rsp-1F0h]
0x180010a58  sub     rsp, 2F0h
0x180010a5f  mov     rax, cs:__security_cookie
0x180010a66  xor     rax, rsp
0x180010a69  mov     [rbp+220h+var_40], rax
0x180010a70  xorps   xmm0, xmm0
0x180010a73  mov     [rbp+220h+OutputBuffer], rcx
0x180010a77  mov     r14, rdx
0x180010a7a  lea     rcx, [rbp+220h+Destination]; void *
0x180010a7e  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm0
0x180010a82  mov     r12d, 208h
0x180010a88  xor     r15d, r15d
0x180010a8b  mov     r8d, r12d; Size
0x180010a8e  mov     [rsp+320h+FileHandle], r15
0x180010a93  xor     eax, eax
0x180010a95  xor     edx, edx; Val
0x180010a97  movups  xmmword ptr [rbp+220h+ObjectAttributes+1Ch], xmm0
0x180010a9b  movups  xmmword ptr [rbp+220h+IoStatusBlock], xmm0
0x180010a9f  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm0
0x180010aa3  movups  xmmword ptr [rsp+320h+DestinationString.Length], xmm0
0x180010aa8  call    memset_0
0x180010aad  lea     rdx, SourceString; "\\Device\\MRxNfs"
0x180010ab4  lea     rcx, [rsp+320h+DestinationString]; DestinationString
0x180010ab9  call    cs:__imp_RtlInitUnicodeString
0x180010abf  mov     [rsp+320h+EaLength], r15d; EaLength
0x180010ac4  lea     r9, [rbp+220h+IoStatusBlock]; IoStatusBlock
0x180010ac8  mov     [rsp+320h+EaBuffer], r15; EaBuffer
0x180010acd  lea     r8, [rbp+220h+ObjectAttributes]; ObjectAttributes
0x180010ad1  mov     [rsp+320h+CreateOptions], 20h ; ' '; CreateOptions
0x180010ad9  lea     rcx, [rsp+320h+FileHandle]; FileHandle
0x180010ade  mov     [rsp+320h+CreateDisposition], 1; CreateDisposition
0x180010ae6  mov     eax, 0FFFEh
0x180010aeb  add     [rsp+320h+DestinationString.MaximumLength], ax
0x180010af0  xorps   xmm0, xmm0
0x180010af3  lea     rax, [rsp+320h+DestinationString]
0x180010af8  mov     [rsp+320h+ShareAccess], 7; ShareAccess
0x180010b00  mov     [rsp+320h+FileAttributes], 80h; FileAttributes
0x180010b08  mov     edx, 100000h; DesiredAccess
0x180010b0d  mov     [rbp+220h+ObjectAttributes.ObjectName], rax
0x180010b11  mov     [rsp+320h+AllocationSize], r15; AllocationSize
0x180010b16  mov     [rbp+220h+ObjectAttributes.Length], 30h ; '0'
0x180010b1d  mov     [rbp+220h+ObjectAttributes.RootDirectory], r15
0x180010b21  mov     [rbp+220h+ObjectAttributes.Attributes], r15d
0x180010b25  movdqu  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010b2a  call    cs:__imp_NtCreateFile
0x180010b30  test    eax, eax
0x180010b32  jz      short loc_180010B41
0x180010b34  mov     dword ptr [r14+48h], 15h
0x180010b3c  jmp     loc_180010DB6
0x180010b41  mov     r13, [r14+8]
0x180010b45  lea     rsi, [r13+10h]
0x180010b49  test    rsi, rsi
0x180010b4c  jnz     short loc_180010B5B
0x180010b4e  mov     dword ptr [r14+48h], 57h ; 'W'
0x180010b56  jmp     loc_180010DAB
0x180010b5b  lea     rdx, SubStr; "\\"
0x180010b62  mov     rcx, rsi; Str
0x180010b65  call    wcsstr_0
0x180010b6a  mov     rdi, rax
0x180010b6d  mov     edx, 104h; SizeInWords
0x180010b72  test    rax, rax
0x180010b75  jnz     short loc_180010B8A
0x180010b77  lea     r8, Source; Source
0x180010b7e  lea     rcx, [rbp+220h+Destination]; Destination
0x180010b82  call    cs:__imp_wcscpy_s
0x180010b88  jmp     short loc_180010BCA
0x180010b8a  mov     eax, 103h
0x180010b8f  mov     rcx, rdi
0x180010b92  sub     rcx, r13
0x180010b95  mov     r8, rsi; Source
0x180010b98  sub     rcx, 10h
0x180010b9c  sar     rcx, 1
0x180010b9f  cmp     ecx, eax
0x180010ba1  cmovl   eax, ecx
0x180010ba4  lea     rcx, [rbp+220h+Destination]; Destination
0x180010ba8  movsxd  rbx, eax
0x180010bab  mov     r9, rbx; MaxCount
0x180010bae  call    cs:__imp_wcsncpy_s
0x180010bb4  add     rbx, rbx
0x180010bb7  cmp     rbx, r12
0x180010bba  jnb     loc_180010E05
0x180010bc0  lea     rsi, [rdi+2]
0x180010bc4  mov     [rbp+rbx+220h+Destination], r15w
0x180010bca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010bce  lea     rcx, [rbp+220h+Destination]
0x180010bd2  mov     rax, rdi
0x180010bd5  inc     rax
0x180010bd8  cmp     [rcx+rax*2], r15w
0x180010bdd  jnz     short loc_180010BD5
0x180010bdf  mov     rdx, rdi
0x180010be2  inc     rdx
0x180010be5  cmp     [rsi+rdx*2], r15w
0x180010bea  jnz     short loc_180010BE2
0x180010bec  lea     r12, [r13+218h]
0x180010bf3  mov     r8, rdi
0x180010bf6  inc     r8
0x180010bf9  cmp     [r12+r8*2], r15w
0x180010bfe  jnz     short loc_180010BF6
0x180010c00  mov     rcx, rdi
0x180010c03  inc     rcx
0x180010c06  cmp     [r13+rcx*2+428h], r15w
0x180010c0f  jnz     short loc_180010C03
0x180010c11  add     eax, edx
0x180010c13  add     eax, ecx
0x180010c15  add     eax, r8d
0x180010c18  lea     eax, ds:50h[rax*2]
0x180010c1f  mov     ecx, eax; Size
0x180010c21  mov     [rsp+320h+InputBufferLength], eax
0x180010c25  mov     r15d, eax
0x180010c28  call    malloc_0
0x180010c2d  mov     rbx, rax
0x180010c30  test    rax, rax
0x180010c33  jnz     short loc_180010C42
0x180010c35  mov     dword ptr [r14+48h], 800300FDh
0x180010c3d  jmp     loc_180010DAB
0x180010c42  mov     r8, r15; Size
0x180010c45  xor     edx, edx; Val
0x180010c47  mov     rcx, rbx; void *
0x180010c4a  call    memset_0
0x180010c4f  lea     r9, [rbx+28h]
0x180010c53  mov     rax, rdi
0x180010c56  mov     [rbx], r9
0x180010c59  xor     r15d, r15d
0x180010c5c  inc     rax
0x180010c5f  cmp     [rsi+rax*2], r15w
0x180010c64  jnz     short loc_180010C5C
0x180010c66  add     rax, 15h
0x180010c6a  mov     rcx, rdi
0x180010c6d  lea     rax, [rbx+rax*2]
0x180010c71  mov     [rbx+8], rax
0x180010c75  inc     rcx
0x180010c78  cmp     [rsi+rcx*2], r15w
0x180010c7d  jnz     short loc_180010C75
0x180010c7f  mov     rax, rdi
0x180010c82  inc     rax
0x180010c85  cmp     [r12+rax*2], r15w
0x180010c8a  jnz     short loc_180010C82
0x180010c8c  add     rcx, 16h
0x180010c90  add     rcx, rax
0x180010c93  lea     rcx, [rbx+rcx*2]
0x180010c97  mov     [rbx+18h], rcx
0x180010c9b  mov     rcx, rdi
0x180010c9e  inc     rcx
0x180010ca1  cmp     [rsi+rcx*2], r15w
0x180010ca6  jnz     short loc_180010C9E
0x180010ca8  mov     rax, rdi
0x180010cab  inc     rax
0x180010cae  cmp     [r12+rax*2], r15w
0x180010cb3  jnz     short loc_180010CAB
0x180010cb5  add     rcx, 26h ; '&'
0x180010cb9  mov     rdx, rdi
0x180010cbc  add     rcx, rax
0x180010cbf  lea     rcx, [rbx+rcx*2]
0x180010cc3  mov     [rbx+20h], rcx
0x180010cc7  inc     rdx
0x180010cca  cmp     [rsi+rdx*2], r15w
0x180010ccf  jnz     short loc_180010CC7
0x180010cd1  inc     rdx; SizeInWords
0x180010cd4  mov     r8, rsi; Source
0x180010cd7  mov     rcx, r9; Destination
0x180010cda  call    cs:__imp_wcscpy_s
0x180010ce0  mov     rdx, rdi
0x180010ce3  inc     rdx
0x180010ce6  cmp     [r12+rdx*2], r15w
0x180010ceb  jnz     short loc_180010CE3
0x180010ced  mov     rcx, [rbx+8]; Destination
0x180010cf1  inc     rdx; SizeInWords
0x180010cf4  mov     r8, r12; Source
0x180010cf7  call    cs:__imp_wcscpy_s
0x180010cfd  cmp     dword ptr [r13+420h], 5
0x180010d05  jnz     short loc_180010D30
0x180010d07  mov     dword ptr [rbx+10h], 5
0x180010d0e  lea     rax, [rbp+220h+Destination]
0x180010d12  inc     rdi
0x180010d15  cmp     [rax+rdi*2], r15w
0x180010d1a  jnz     short loc_180010D12
0x180010d1c  mov     rcx, [rbx+20h]; Destination
0x180010d20  lea     rdx, [rdi+1]; SizeInWords
0x180010d24  lea     r8, [rbp+220h+Destination]; Source
0x180010d28  call    cs:__imp_wcscpy_s
0x180010d2e  jmp     short loc_180010D34
0x180010d30  mov     [rbx+10h], r15d
0x180010d34  test    byte ptr [r13+424h], 1
0x180010d3c  jz      short loc_180010D42
0x180010d3e  or      dword ptr [rbx+14h], 1
0x180010d42  mov     eax, [rsp+320h+InputBufferLength]
0x180010d46  xor     r9d, r9d; ApcContext
0x180010d49  mov     rdi, [rbp+220h+OutputBuffer]
0x180010d4d  xor     r8d, r8d; ApcRoutine
0x180010d50  mov     rcx, [rsp+320h+FileHandle]; FileHandle
0x180010d55  xor     edx, edx; Event
0x180010d57  mov     dword ptr [rsp+320h+EaBuffer], 4Ch ; 'L'; OutputBufferLength
0x180010d5f  mov     qword ptr [rsp+320h+CreateOptions], rdi; OutputBuffer
0x180010d64  mov     [rsp+320h+CreateDisposition], eax; InputBufferLength
0x180010d68  lea     rax, [rbp+220h+IoStatusBlock]
0x180010d6c  mov     qword ptr [rsp+320h+ShareAccess], rbx; InputBuffer
0x180010d71  mov     [rsp+320h+FileAttributes], 140800h; IoControlCode
0x180010d79  mov     [rsp+320h+AllocationSize], rax; IoStatusBlock
0x180010d7e  call    cs:__imp_NtDeviceIoControlFile
0x180010d84  test    eax, eax
0x180010d86  jz      short loc_180010DE2
0x180010d88  mov     ecx, eax; Status
0x180010d8a  call    cs:__imp_LsaNtStatusToWinError
0x180010d90  mov     ecx, 52Eh
0x180010d95  mov     edx, 15h
0x180010d9a  cmp     eax, ecx
0x180010d9c  cmovnz  ecx, edx
0x180010d9f  mov     [r14+48h], ecx
0x180010da3  mov     rcx, rbx; Block
0x180010da6  call    free_0
0x180010dab  mov     rcx, [rsp+320h+FileHandle]; Handle
0x180010db0  call    cs:__imp_NtClose
0x180010db6  xor     eax, eax
0x180010db8  mov     rcx, [rbp+220h+var_40]
0x180010dbf  xor     rcx, rsp; StackCookie
0x180010dc2  call    __security_check_cookie
0x180010dc7  mov     rbx, [rsp+320h+arg_10]
0x180010dcf  add     rsp, 2F0h
0x180010dd6  pop     r15
0x180010dd8  pop     r14
0x180010dda  pop     r13
0x180010ddc  pop     r12
0x180010dde  pop     rdi
0x180010ddf  pop     rsi
0x180010de0  pop     rbp
0x180010de1  retn
0x180010de2  cmp     dword ptr [rdi], 0FFFFFFFEh
0x180010de5  jz      short loc_180010DEB
0x180010de7  mov     [r14+48h], r15d
0x180010deb  mov     rcx, rbx; Block
0x180010dee  call    free_0
0x180010df3  mov     rcx, [rsp+320h+FileHandle]; Handle
0x180010df8  call    cs:__imp_NtClose
0x180010dfe  mov     eax, 1
0x180010e03  jmp     short loc_180010DB8
0x180010e05  call    __report_rangecheckfailure
```
