# CNtfsStorage::WriteControlStream(void)

- ea: `0x180054dd4`
- end: `0x180054eaa`
- name: `?WriteControlStream@CNtfsStorage@@IEAAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(CNtfsStorage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180054840`

## callees

- `0x180042800`
- `0x180054dd4`
- `0x180061410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e74`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180054e46`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180054e46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054e6a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180054e6a`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::WriteControlStream(CNtfsStorage *this)
{
  int v2; // eax
  __int128 *v3; // rcx
  int v4; // esi
  unsigned int v5; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF
  _WORD Buffer[2]; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+3Ch] [rbp-2Ch]
  __int128 v11; // [rsp+40h] [rbp-28h]

  NumberOfBytesWritten = 0;
  Buffer[0] = 0;
  Buffer[1] = *((_WORD *)this + 60);
  v2 = *((_DWORD *)this + 31);
  v3 = (__int128 *)((char *)this + 128);
  v10 = v2;
  v11 = *v3;
  v4 = memcmp_0(v3, &GUID_NULL, 0x10u) != 0 ? 0x10 : 0;
  if ( SetFilePointer(*((HANDLE *)this + 14), 0, 0, 0) == -1
    || (v5 = 0, !WriteFile(*((HANDLE *)this + 14), Buffer, v4 + 8, &NumberOfBytesWritten, 0)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x180054dd4  mov     [rsp+arg_8], rbx
0x180054dd9  mov     [rsp+arg_10], rsi
0x180054dde  push    rdi
0x180054ddf  sub     rsp, 60h
0x180054de3  mov     rax, cs:__security_cookie
0x180054dea  xor     rax, rsp
0x180054ded  mov     [rsp+68h+var_18], rax
0x180054df2  xor     eax, eax
0x180054df4  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180054dfc  mov     [rsp+68h+Buffer], ax
0x180054e01  lea     rdx, GUID_NULL; Buf2
0x180054e08  movzx   eax, word ptr [rcx+78h]
0x180054e0c  mov     rdi, rcx
0x180054e0f  mov     [rsp+68h+var_2E], ax
0x180054e14  mov     r8d, 10h; Size
0x180054e1a  mov     eax, [rcx+7Ch]
0x180054e1d  sub     rcx, 0FFFFFFFFFFFFFF80h; Buf1
0x180054e21  mov     [rsp+68h+var_2C], eax
0x180054e25  movups  xmm0, xmmword ptr [rcx]
0x180054e28  movdqu  [rsp+68h+var_28], xmm0
0x180054e2e  call    memcmp_0
0x180054e33  mov     rcx, [rdi+70h]; hFile
0x180054e37  neg     eax
0x180054e39  sbb     esi, esi
0x180054e3b  xor     r9d, r9d; dwMoveMethod
0x180054e3e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180054e41  xor     edx, edx; lDistanceToMove
0x180054e43  and     esi, 10h
0x180054e46  call    cs:__imp_SetFilePointer
0x180054e4c  cmp     eax, 0FFFFFFFFh
0x180054e4f  jz      short loc_180054E74
0x180054e51  mov     rcx, [rdi+70h]; hFile
0x180054e55  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180054e5a  xor     ebx, ebx
0x180054e5c  lea     r8d, [rsi+8]; nNumberOfBytesToWrite
0x180054e60  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180054e65  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x180054e6a  call    cs:__imp_WriteFile
0x180054e70  test    eax, eax
0x180054e72  jnz     short loc_180054E89
0x180054e74  call    cs:__imp_GetLastError
0x180054e7a  mov     ebx, eax
0x180054e7c  test    eax, eax
0x180054e7e  jle     short loc_180054E89
0x180054e80  movzx   ebx, ax
0x180054e83  or      ebx, 80070000h
0x180054e89  mov     eax, ebx
0x180054e8b  mov     rcx, [rsp+68h+var_18]
0x180054e90  xor     rcx, rsp; StackCookie
0x180054e93  call    __security_check_cookie
0x180054e98  lea     r11, [rsp+68h+var_8]
0x180054e9d  mov     rbx, [r11+18h]
0x180054ea1  mov     rsi, [r11+20h]
0x180054ea5  mov     rsp, r11
0x180054ea8  pop     rdi
0x180054ea9  retn
```
