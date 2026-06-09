# GetMacAdressFromDriver(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180017c08`
- end: `0x180017d89`
- name: `?GetMacAdressFromDriver@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18005b584`

## callees

- `0x1800067a0`
- `0x180017c08`
- `0x180017de4`
- `0x18002e1a0`
- `0x18004c38c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ccb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017c4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017c4c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180017cc1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180017cc1`

## pseudocode

```c
__int64 __fastcall GetMacAdressFromDriver(const WCHAR *a1, __int64 a2)
{
  HANDLE FileW; // rax
  __int64 v4; // rbx
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  char v8; // al
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-39h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-31h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-29h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-21h]
  DWORD BytesReturned; // [rsp+50h] [rbp-9h] BYREF
  int InBuffer; // [rsp+54h] [rbp-5h] BYREF
  HANDLE v16; // [rsp+58h] [rbp-1h] BYREF
  int OutBuffer; // [rsp+60h] [rbp+7h] BYREF
  __int16 v18; // [rsp+64h] [rbp+Bh]
  unsigned __int16 v19[20]; // [rsp+68h] [rbp+Fh] BYREF

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v4 = -1;
  v16 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_14;
  }
  OutBuffer = 0;
  v18 = 0;
  BytesReturned = 0;
  InBuffer = 16843009;
  if ( !DeviceIoControl(FileW, 0x170002u, &InBuffer, 4u, &OutBuffer, 6u, &BytesReturned, 0) )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_7:
    v6 = v7;
    goto LABEL_14;
  }
  if ( BytesReturned != 6 )
  {
    v6 = -2147418113;
    goto LABEL_14;
  }
  LODWORD(lpOverlapped) = (unsigned __int8)v18;
  LODWORD(hTemplateFile) = HIBYTE(OutBuffer);
  LODWORD(dwFlagsAndAttributes) = BYTE2(OutBuffer);
  dwCreationDisposition[0] = BYTE1(OutBuffer);
  v7 = StringCchPrintfW(
         v19,
         0x12u,
         L"%.2X-%.2X-%.2X-%.2X-%.2X-%.2X",
         (unsigned __int8)OutBuffer,
         *(_QWORD *)dwCreationDisposition,
         dwFlagsAndAttributes,
         hTemplateFile,
         lpOverlapped,
         HIBYTE(v18));
  if ( v7 < 0 )
    goto LABEL_7;
  do
    ++v4;
  while ( v19[v4] );
  v8 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
         a2,
         v19,
         v4);
  v6 = -2147024882;
  if ( v8 )
    v6 = 0;
LABEL_14:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  return v6;
}

```

## disassembly

```asm
0x180017c08  mov     [rsp-8+arg_10], rbx
0x180017c0d  push    rbp
0x180017c0e  push    rsi
0x180017c0f  push    rdi
0x180017c10  lea     rbp, [rsp-47h]
0x180017c15  sub     rsp, 0A0h
0x180017c1c  mov     rax, cs:__security_cookie
0x180017c23  xor     rax, rsp
0x180017c26  mov     [rbp+57h+var_20], rax
0x180017c2a  xor     esi, esi
0x180017c2c  mov     rdi, rdx
0x180017c2f  mov     [rsp+0B0h+hTemplateFile], rsi; hTemplateFile
0x180017c34  xor     r9d, r9d; lpSecurityAttributes
0x180017c37  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180017c3b  mov     edx, 80000000h; dwDesiredAccess
0x180017c40  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180017c48  lea     r8d, [rsi+1]; dwShareMode
0x180017c4c  call    cs:__imp_CreateFileW
0x180017c52  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017c56  mov     [rbp+57h+var_58], rax
0x180017c5a  cmp     rax, rbx
0x180017c5d  jnz     short loc_180017C7D
0x180017c5f  call    cs:__imp_GetLastError
0x180017c65  mov     ebx, eax
0x180017c67  test    eax, eax
0x180017c69  jle     loc_180017D5F
0x180017c6f  movzx   ebx, ax
0x180017c72  or      ebx, 80070000h
0x180017c78  jmp     loc_180017D5F
0x180017c7d  xor     ecx, ecx
0x180017c7f  mov     [rsp+0B0h+lpOverlapped], rsi; lpOverlapped
0x180017c84  mov     [rbp+57h+OutBuffer], ecx
0x180017c87  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180017c8b  mov     [rbp+57h+var_4C], cx
0x180017c8f  mov     r9d, 4; nInBufferSize
0x180017c95  lea     rcx, [rbp+57h+BytesReturned]
0x180017c99  mov     [rbp+57h+BytesReturned], esi
0x180017c9c  mov     [rsp+0B0h+hTemplateFile], rcx; lpBytesReturned
0x180017ca1  mov     edx, 170002h; dwIoControlCode
0x180017ca6  lea     rcx, [rbp+57h+OutBuffer]
0x180017caa  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], 6; nOutBufferSize
0x180017cb2  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rcx; lpOutBuffer
0x180017cb7  mov     rcx, rax; hDevice
0x180017cba  mov     [rbp+57h+InBuffer], 1010101h
0x180017cc1  call    cs:__imp_DeviceIoControl
0x180017cc7  test    eax, eax
0x180017cc9  jnz     short loc_180017CE1
0x180017ccb  call    cs:__imp_GetLastError
0x180017cd1  test    eax, eax
0x180017cd3  jle     short loc_180017CDD
0x180017cd5  movzx   eax, ax
0x180017cd8  or      eax, 80070000h
0x180017cdd  mov     ebx, eax
0x180017cdf  jmp     short loc_180017D5F
0x180017ce1  cmp     [rbp+57h+BytesReturned], 6
0x180017ce5  jz      short loc_180017CEE
0x180017ce7  mov     ebx, 8000FFFFh
0x180017cec  jmp     short loc_180017D5F
0x180017cee  movzx   ecx, byte ptr [rbp+57h+var_4C]
0x180017cf2  movzx   edx, byte ptr [rbp+57h+OutBuffer+3]
0x180017cf6  movzx   r8d, byte ptr [rbp+57h+OutBuffer+2]
0x180017cfb  movzx   eax, byte ptr [rbp+57h+var_4C+1]
0x180017cff  movzx   r10d, byte ptr [rbp+57h+OutBuffer+1]
0x180017d04  movzx   r9d, byte ptr [rbp+57h+OutBuffer]
0x180017d09  mov     [rsp+0B0h+var_70], eax
0x180017d0d  mov     dword ptr [rsp+0B0h+lpOverlapped], ecx
0x180017d11  lea     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x180017d15  mov     dword ptr [rsp+0B0h+hTemplateFile], edx
0x180017d19  mov     edx, 12h; unsigned __int64
0x180017d1e  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], r8d
0x180017d23  lea     r8, a2x2x2x2x2x2x; "%.2X-%.2X-%.2X-%.2X-%.2X-%.2X"
0x180017d2a  mov     [rsp+0B0h+dwCreationDisposition], r10d
0x180017d2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017d34  test    eax, eax
0x180017d36  js      short loc_180017CDD
0x180017d38  lea     rax, [rbp+57h+var_48]
0x180017d3c  inc     rbx
0x180017d3f  cmp     [rax+rbx*2], si
0x180017d43  jnz     short loc_180017D3C
0x180017d45  mov     r8, rbx
0x180017d48  lea     rdx, [rbp+57h+var_48]
0x180017d4c  mov     rcx, rdi
0x180017d4f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180017d54  mov     ebx, 8007000Eh
0x180017d59  test    al, al
0x180017d5b  jz      short loc_180017D5F
0x180017d5d  mov     ebx, esi
0x180017d5f  lea     rcx, [rbp+57h+var_58]
0x180017d63  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017d68  mov     eax, ebx
0x180017d6a  mov     rcx, [rbp+57h+var_20]
0x180017d6e  xor     rcx, rsp; StackCookie
0x180017d71  call    __security_check_cookie
0x180017d76  mov     rbx, [rsp+0B0h+arg_10]
0x180017d7e  add     rsp, 0A0h
0x180017d85  pop     rdi
0x180017d86  pop     rsi
0x180017d87  pop     rbp
0x180017d88  retn
```
