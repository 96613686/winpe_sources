# SetFileIntegrityLevelByNameW(ushort const *,int)

- ea: `0x14000b248`
- end: `0x14000b32e`
- name: `?SetFileIntegrityLevelByNameW@@YAJPEBGH@Z`
- size: `230`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140009240`
- `0x1400094a4`
- `0x14000b334`

## callees

- `0x14000b248`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14000b2a0`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000b2a0`
- `KERNEL32!CloseHandle` at `0x14000b2f7`
- `KERNEL32!CloseHandle` at `0x14000b2f7`
- `KERNEL32!LocalFree` at `0x14000b2cb`
- `KERNEL32!LocalFree` at `0x14000b2cb`
- `KERNEL32!CreateFileW` at `0x14000b276`
- `KERNEL32!CreateFileW` at `0x14000b276`
- `KERNEL32!GetLastError` at `0x14000b2d9`
- `KERNEL32!GetLastError` at `0x14000b305`
- `KERNEL32!GetLastError` at `0x14000b2d9`
- `KERNEL32!GetLastError` at `0x14000b305`
- `iertutil!__imp_?SetFileHandleIntegrityLevel@@YAJPEAX0@Z` at `0x14000b2b8`
- `iertutil!__imp_?SetFileHandleIntegrityLevel@@YAJPEAX0@Z` at `0x14000b2b8`

## pseudocode

```c
__int64 __fastcall SetFileIntegrityLevelByNameW(const unsigned __int16 *a1)
{
  HANDLE FileW; // rdi
  unsigned int v2; // ebx
  signed int v3; // eax
  signed int LastError; // eax
  PSID Sid; // [rsp+60h] [rbp+18h] BYREF

  FileW = CreateFileW(a1, 0xA0000u, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"ME", &Sid) )
    {
      v2 = SetFileHandleIntegrityLevel(FileW, Sid);
      LocalFree(Sid);
    }
    else
    {
      v3 = GetLastError();
      v2 = v3;
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
    }
    CloseHandle(FileW);
  }
  return v2;
}

```

## disassembly

```asm
0x14000b248  mov     rax, rsp
0x14000b24b  mov     [rax+8], rbx
0x14000b24f  push    rdi
0x14000b250  sub     rsp, 40h
0x14000b254  mov     qword ptr [rax-18h], 0
0x14000b25c  xor     r9d, r9d; lpSecurityAttributes
0x14000b25f  mov     dword ptr [rax-20h], 80h
0x14000b266  mov     edx, 0A0000h; dwDesiredAccess
0x14000b26b  mov     dword ptr [rax-28h], 3
0x14000b272  lea     r8d, [r9+1]; dwShareMode
0x14000b276  call    cs:__imp_CreateFileW
0x14000b27d  nop     dword ptr [rax+rax+00h]
0x14000b282  mov     rdi, rax
0x14000b285  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b289  jz      short loc_14000B305
0x14000b28b  lea     rdx, [rsp+48h+Sid]; Sid
0x14000b290  mov     [rsp+48h+Sid], 0
0x14000b299  lea     rcx, aMe; "ME"
0x14000b2a0  call    cs:__imp_ConvertStringSidToSidW
0x14000b2a7  nop     dword ptr [rax+rax+00h]
0x14000b2ac  test    eax, eax
0x14000b2ae  jz      short loc_14000B2D9
0x14000b2b0  mov     rdx, [rsp+48h+Sid]
0x14000b2b5  mov     rcx, rdi
0x14000b2b8  call    cs:__imp_?SetFileHandleIntegrityLevel@@YAJPEAX0@Z; SetFileHandleIntegrityLevel(void *,void *)
0x14000b2bf  nop     dword ptr [rax+rax+00h]
0x14000b2c4  mov     rcx, [rsp+48h+Sid]; hMem
0x14000b2c9  mov     ebx, eax
0x14000b2cb  call    cs:__imp_LocalFree
0x14000b2d2  nop     dword ptr [rax+rax+00h]
0x14000b2d7  jmp     short loc_14000B2F4
0x14000b2d9  call    cs:__imp_GetLastError
0x14000b2e0  nop     dword ptr [rax+rax+00h]
0x14000b2e5  mov     ebx, eax
0x14000b2e7  test    eax, eax
0x14000b2e9  jle     short loc_14000B2F4
0x14000b2eb  movzx   ebx, ax
0x14000b2ee  or      ebx, 80070000h
0x14000b2f4  mov     rcx, rdi; hObject
0x14000b2f7  call    cs:__imp_CloseHandle
0x14000b2fe  nop     dword ptr [rax+rax+00h]
0x14000b303  jmp     short loc_14000B320
0x14000b305  call    cs:__imp_GetLastError
0x14000b30c  nop     dword ptr [rax+rax+00h]
0x14000b311  mov     ebx, eax
0x14000b313  test    eax, eax
0x14000b315  jle     short loc_14000B320
0x14000b317  movzx   ebx, ax
0x14000b31a  or      ebx, 80070000h
0x14000b320  mov     eax, ebx
0x14000b322  mov     rbx, [rsp+48h+arg_0]
0x14000b327  add     rsp, 40h
0x14000b32b  pop     rdi
0x14000b32c  retn
```
