# NdisuioEnumerateInterfaces(_NDIS_ENUM_INTF *,ulong,ulong)

- ea: `0x180025b3c`
- end: `0x180025dc8`
- name: `?NdisuioEnumerateInterfaces@@YAKPEAU_NDIS_ENUM_INTF@@KK@Z`
- size: `652`
- prototype: `__int64 __fastcall(void **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000fdac`

## callees

- `0x1800025f0`
- `0x1800030fc`
- `0x180003114`
- `0x180025b3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d89`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180025bb2`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180025bb2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025bf7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025c59`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025bf7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025c59`

## pseudocode

```c
__int64 __fastcall NdisuioEnumerateInterfaces(void **a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rsi
  HANDLE FileA; // r14
  DWORD LastError; // ebx
  char *v8; // rsi
  unsigned int v9; // r15d
  unsigned int i; // eax
  char *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v16[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD OutBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int Size; // [rsp+58h] [rbp-A8h]
  unsigned int Size_4; // [rsp+5Ch] [rbp-A4h]
  size_t v20; // [rsp+60h] [rbp-A0h]

  v3 = a3;
  BytesReturned = 0;
  v16[0] = 0;
  FileA = CreateFileA(NdisuioDevice, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileA == (HANDLE)-1LL )
    return GetLastError();
  if ( DeviceIoControl(FileA, 0x12C810u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    LastError = 0;
    v8 = (char *)a1 + v3;
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      OutBuffer[0] = i;
      if ( i >= a2 )
        break;
      if ( !DeviceIoControl(FileA, 0x12C80Cu, OutBuffer, 0x14u, OutBuffer, 0x400u, v16, 0) )
      {
        LastError = GetLastError();
        if ( LastError == 259 )
          LastError = 0;
        break;
      }
      v11 = &v8[-((Size + 7) & 0xFFFFFFF8)];
      v12 = 4LL * *(unsigned int *)a1;
      if ( &v11[-(v12 * 8)] - (char *)a1 - 16 <= 0
        || (a1[v12 + 3] = v11,
            memcpy_0(a1[4 * *(unsigned int *)a1 + 3], (char *)OutBuffer + OutBuffer[1], Size),
            LOWORD(a1[4 * *(unsigned int *)a1 + 2]) = Size,
            WORD1(a1[4 * *(unsigned int *)a1 + 2]) = Size,
            v8 = &v11[-(((_DWORD)v20 + 7) & 0xFFFFFFF8)],
            v13 = 4LL * *(unsigned int *)a1,
            &v8[-(v13 * 8)] - (char *)a1 - 16 <= 0) )
      {
        LastError = 13;
        break;
      }
      a1[v13 + 5] = v8;
      memcpy_0(a1[4 * *(unsigned int *)a1 + 5], (char *)OutBuffer + Size_4, (unsigned int)v20);
      LOWORD(a1[4 * *(unsigned int *)a1 + 4]) = v20;
      WORD1(a1[4 * (unsigned int)(*(_DWORD *)a1)++ + 4]) = v20;
      memset_0(OutBuffer, 0, 0x400u);
      ++v9;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !CloseHandle(FileA) )
    return GetLastError();
  return LastError;
}

```

## disassembly

```asm
0x180025b3c  mov     [rsp-8+arg_8], rbx
0x180025b41  mov     [rsp-8+arg_10], rsi
0x180025b46  push    rbp
0x180025b47  push    rdi
0x180025b48  push    r12
0x180025b4a  push    r14
0x180025b4c  push    r15
0x180025b4e  lea     rbp, [rsp-360h]
0x180025b56  sub     rsp, 460h
0x180025b5d  mov     rax, cs:__security_cookie
0x180025b64  xor     rax, rsp
0x180025b67  mov     [rbp+380h+var_30], rax
0x180025b6e  mov     esi, r8d
0x180025b71  mov     r12d, edx
0x180025b74  mov     r8d, 3; dwShareMode
0x180025b7a  mov     [rsp+480h+hTemplateFile], 0; hTemplateFile
0x180025b83  mov     rdi, rcx
0x180025b86  mov     [rsp+480h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180025b8e  xor     r9d, r9d; lpSecurityAttributes
0x180025b91  mov     [rsp+480h+dwCreationDisposition], r8d; dwCreationDisposition
0x180025b96  mov     edx, 0C0000000h; dwDesiredAccess
0x180025b9b  mov     [rsp+480h+BytesReturned], 0
0x180025ba3  lea     rcx, ?NdisuioDevice@@3PADA; "\\\\.\\\\Ndisuio"
0x180025baa  mov     [rsp+480h+var_43C], 0
0x180025bb2  call    cs:__imp_CreateFileA
0x180025bb8  mov     r14, rax
0x180025bbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025bbf  jz      loc_180025D93
0x180025bc5  mov     [rsp+480h+lpOverlapped], 0; lpOverlapped
0x180025bce  lea     rax, [rsp+480h+BytesReturned]
0x180025bd3  mov     [rsp+480h+hTemplateFile], rax; lpBytesReturned
0x180025bd8  xor     r9d, r9d; nInBufferSize
0x180025bdb  mov     [rsp+480h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180025be3  xor     r8d, r8d; lpInBuffer
0x180025be6  mov     edx, 12C810h; dwIoControlCode
0x180025beb  mov     qword ptr [rsp+480h+dwCreationDisposition], 0; lpOutBuffer
0x180025bf4  mov     rcx, r14; hDevice
0x180025bf7  call    cs:__imp_DeviceIoControl
0x180025bfd  test    eax, eax
0x180025bff  jnz     short loc_180025C0E
0x180025c01  call    cs:__imp_GetLastError
0x180025c07  mov     ebx, eax
0x180025c09  jmp     loc_180025D86
0x180025c0e  xor     ebx, ebx
0x180025c10  add     rsi, rdi
0x180025c13  xor     r15d, r15d
0x180025c16  xor     eax, eax
0x180025c18  mov     [rsp+480h+OutBuffer], eax
0x180025c1c  cmp     eax, r12d
0x180025c1f  jnb     loc_180025D86
0x180025c25  mov     [rsp+480h+lpOverlapped], rbx; lpOverlapped
0x180025c2a  lea     rax, [rsp+480h+var_43C]
0x180025c2f  mov     [rsp+480h+hTemplateFile], rax; lpBytesReturned
0x180025c34  lea     r8, [rsp+480h+OutBuffer]; lpInBuffer
0x180025c39  lea     rax, [rsp+480h+OutBuffer]
0x180025c3e  mov     [rsp+480h+dwFlagsAndAttributes], 400h; nOutBufferSize
0x180025c46  mov     r9d, 14h; nInBufferSize
0x180025c4c  mov     qword ptr [rsp+480h+dwCreationDisposition], rax; lpOutBuffer
0x180025c51  mov     edx, 12C80Ch; dwIoControlCode
0x180025c56  mov     rcx, r14; hDevice
0x180025c59  call    cs:__imp_DeviceIoControl
0x180025c5f  test    eax, eax
0x180025c61  jz      loc_180025D73
0x180025c67  mov     eax, dword ptr [rsp+480h+Size]
0x180025c6b  mov     ecx, 0FFFFFFF8h
0x180025c70  add     eax, 7
0x180025c73  and     rax, rcx
0x180025c76  mov     ecx, [rdi]
0x180025c78  sub     rsi, rax
0x180025c7b  shl     rcx, 5
0x180025c7f  mov     rax, rsi
0x180025c82  sub     rax, rcx
0x180025c85  sub     rax, rdi
0x180025c88  sub     rax, 10h
0x180025c8c  test    rax, rax
0x180025c8f  jle     loc_180025D6C
0x180025c95  mov     [rcx+rdi+18h], rsi
0x180025c9a  lea     rdx, [rsp+480h+OutBuffer]
0x180025c9f  mov     ecx, [rdi]
0x180025ca1  mov     eax, [rsp+480h+var_42C]
0x180025ca5  mov     r8d, dword ptr [rsp+480h+Size]; Size
0x180025caa  add     rdx, rax; Src
0x180025cad  shl     rcx, 5
0x180025cb1  mov     rcx, [rcx+rdi+18h]; void *
0x180025cb6  call    memcpy_0
0x180025cbb  movzx   eax, word ptr [rsp+480h+Size]
0x180025cc0  mov     ecx, [rdi]
0x180025cc2  shl     rcx, 5
0x180025cc6  mov     [rcx+rdi+10h], ax
0x180025ccb  movzx   eax, word ptr [rsp+480h+Size]
0x180025cd0  mov     ecx, [rdi]
0x180025cd2  shl     rcx, 5
0x180025cd6  mov     [rcx+rdi+12h], ax
0x180025cdb  mov     ecx, 0FFFFFFF8h
0x180025ce0  mov     eax, dword ptr [rsp+480h+var_420]
0x180025ce4  add     eax, 7
0x180025ce7  and     rax, rcx
0x180025cea  mov     ecx, [rdi]
0x180025cec  sub     rsi, rax
0x180025cef  shl     rcx, 5
0x180025cf3  mov     rax, rsi
0x180025cf6  sub     rax, rcx
0x180025cf9  sub     rax, rdi
0x180025cfc  sub     rax, 10h
0x180025d00  test    rax, rax
0x180025d03  jle     short loc_180025D6C
0x180025d05  mov     [rcx+rdi+28h], rsi
0x180025d0a  lea     rdx, [rsp+480h+OutBuffer]
0x180025d0f  mov     ecx, [rdi]
0x180025d11  mov     eax, dword ptr [rsp+480h+Size+4]
0x180025d15  mov     r8d, dword ptr [rsp+480h+var_420]; Size
0x180025d1a  add     rdx, rax; Src
0x180025d1d  shl     rcx, 5
0x180025d21  mov     rcx, [rcx+rdi+28h]; void *
0x180025d26  call    memcpy_0
0x180025d2b  mov     ecx, [rdi]
0x180025d2d  xor     edx, edx; Val
0x180025d2f  movzx   eax, word ptr [rsp+480h+var_420]
0x180025d34  inc     rcx
0x180025d37  shl     rcx, 5
0x180025d3b  mov     r8d, 400h; Size
0x180025d41  mov     [rcx+rdi], ax
0x180025d45  mov     ecx, [rdi]
0x180025d47  movzx   eax, word ptr [rsp+480h+var_420]
0x180025d4c  shl     rcx, 5
0x180025d50  mov     [rcx+rdi+22h], ax
0x180025d55  lea     rcx, [rsp+480h+OutBuffer]; void *
0x180025d5a  inc     dword ptr [rdi]
0x180025d5c  call    memset_0
0x180025d61  inc     r15d
0x180025d64  mov     eax, r15d
0x180025d67  jmp     loc_180025C18
0x180025d6c  mov     ebx, 0Dh
0x180025d71  jmp     short loc_180025D86
0x180025d73  call    cs:__imp_GetLastError
0x180025d79  mov     ebx, eax
0x180025d7b  xor     eax, eax
0x180025d7d  cmp     ebx, 103h
0x180025d83  cmovz   ebx, eax
0x180025d86  mov     rcx, r14; hObject
0x180025d89  call    cs:__imp_CloseHandle
0x180025d8f  test    eax, eax
0x180025d91  jnz     short loc_180025D9B
0x180025d93  call    cs:__imp_GetLastError
0x180025d99  mov     ebx, eax
0x180025d9b  mov     eax, ebx
0x180025d9d  mov     rcx, [rbp+380h+var_30]
0x180025da4  xor     rcx, rsp; StackCookie
0x180025da7  call    __security_check_cookie
0x180025dac  lea     r11, [rsp+480h+var_20]
0x180025db4  mov     rbx, [r11+38h]
0x180025db8  mov     rsi, [r11+40h]
0x180025dbc  mov     rsp, r11
0x180025dbf  pop     r15
0x180025dc1  pop     r14
0x180025dc3  pop     r12
0x180025dc5  pop     rdi
0x180025dc6  pop     rbp
0x180025dc7  retn
```
