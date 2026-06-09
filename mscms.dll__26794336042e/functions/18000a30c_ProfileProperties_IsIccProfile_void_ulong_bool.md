# ProfileProperties::IsIccProfile(void *,ulong,bool *)

- ea: `0x18000a30c`
- end: `0x18000a3f5`
- name: `?IsIccProfile@ProfileProperties@@YAJPEAXKPEA_N@Z`
- size: `233`
- prototype: `__int64 __fastcall(HANDLE hFile, void *, _BYTE *, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009e34`
- `0x180048b80`

## callees

- `0x18000a30c`
- `0x18002e5f0`
- `0x18002f2f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a373`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000a368`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000a368`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a3a2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a3a2`

## pseudocode

```c
__int64 __fastcall ProfileProperties::IsIccProfile(HANDLE hFile, void *a2, _BYTE *a3, bool *a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE Buffer[36]; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v11; // [rsp+64h] [rbp-74h]

  v4 = 0;
  *a3 = 0;
  if ( (unsigned int)a2 >= 0x84 )
  {
    NumberOfBytesRead = 0;
    memset_0(Buffer, 0, 0x80u);
    if ( SetFilePointer(hFile, 0, 0, 0) == -1 || !ReadFile(hFile, Buffer, 0x80u, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else if ( NumberOfBytesRead == 128 )
    {
      if ( _byteswap_ulong(v11) == 1633907568 )
        *a3 = 1;
    }
    else
    {
      return (unsigned int)-2147221500;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000a30c  mov     [rsp+arg_8], rbx
0x18000a311  mov     [rsp+arg_18], rsi
0x18000a316  push    rdi
0x18000a317  sub     rsp, 0D0h
0x18000a31e  mov     rax, cs:__security_cookie
0x18000a325  xor     rax, rsp
0x18000a328  mov     [rsp+0D8h+var_18], rax
0x18000a330  xor     ebx, ebx
0x18000a332  mov     rdi, r8
0x18000a335  mov     [r8], bl
0x18000a338  mov     rsi, rcx
0x18000a33b  cmp     edx, 84h
0x18000a341  jb      loc_18000A3CE
0x18000a347  xor     edx, edx; Val
0x18000a349  mov     [rsp+0D8h+NumberOfBytesRead], ebx
0x18000a34d  mov     r8d, 80h; Size
0x18000a353  lea     rcx, [rsp+0D8h+Buffer]; void *
0x18000a358  call    memset_0
0x18000a35d  xor     r9d, r9d; dwMoveMethod
0x18000a360  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000a363  xor     edx, edx; lDistanceToMove
0x18000a365  mov     rcx, rsi; hFile
0x18000a368  call    cs:__imp_SetFilePointer
0x18000a36e  cmp     eax, 0FFFFFFFFh
0x18000a371  jnz     short loc_18000A38A
0x18000a373  call    cs:__imp_GetLastError
0x18000a379  mov     ebx, eax
0x18000a37b  test    eax, eax
0x18000a37d  jle     short loc_18000A3CE
0x18000a37f  movzx   ebx, ax
0x18000a382  or      ebx, 80070000h
0x18000a388  jmp     short loc_18000A3CE
0x18000a38a  lea     r9, [rsp+0D8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000a38f  mov     [rsp+0D8h+lpOverlapped], rbx; lpOverlapped
0x18000a394  mov     r8d, 80h; nNumberOfBytesToRead
0x18000a39a  lea     rdx, [rsp+0D8h+Buffer]; lpBuffer
0x18000a39f  mov     rcx, rsi; hFile
0x18000a3a2  call    cs:__imp_ReadFile
0x18000a3a8  test    eax, eax
0x18000a3aa  jz      short loc_18000A373
0x18000a3ac  cmp     [rsp+0D8h+NumberOfBytesRead], 80h
0x18000a3b4  jz      short loc_18000A3BD
0x18000a3b6  mov     ebx, 80040004h
0x18000a3bb  jmp     short loc_18000A3CE
0x18000a3bd  mov     ecx, [rsp+0D8h+var_74]
0x18000a3c1  bswap   ecx
0x18000a3c3  cmp     ecx, 61637370h
0x18000a3c9  jnz     short loc_18000A3CE
0x18000a3cb  mov     byte ptr [rdi], 1
0x18000a3ce  mov     eax, ebx
0x18000a3d0  mov     rcx, [rsp+0D8h+var_18]
0x18000a3d8  xor     rcx, rsp; StackCookie
0x18000a3db  call    __security_check_cookie
0x18000a3e0  lea     r11, [rsp+0D8h+var_8]
0x18000a3e8  mov     rbx, [r11+18h]
0x18000a3ec  mov     rsi, [r11+28h]
0x18000a3f0  mov     rsp, r11
0x18000a3f3  pop     rdi
0x18000a3f4  retn
```
