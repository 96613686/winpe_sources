# IIS_CRYPTO_BASE::SetThreadImpersonationToken(void *)

- ea: `0x18002a4c0`
- end: `0x18002a4f4`
- name: `?SetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAX@Z`
- size: `52`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a058`
- `0x18002a128`
- `0x18002a1f8`
- `0x18002a2b4`
- `0x18002a35c`
- `0x18002a418`

## callees

- `0x18002a4c0`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18002a4cd`
- `ADVAPI32!SetThreadToken` at `0x18002a4cd`
- `KERNEL32!GetLastError` at `0x18002a4d7`
- `KERNEL32!GetLastError` at `0x18002a4d7`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::SetThreadImpersonationToken(HANDLE Token)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x18002a4c0  push    rbx
0x18002a4c2  sub     rsp, 20h
0x18002a4c6  mov     rdx, rcx; Token
0x18002a4c9  xor     ebx, ebx
0x18002a4cb  xor     ecx, ecx; Thread
0x18002a4cd  call    cs:__imp_SetThreadToken
0x18002a4d3  test    eax, eax
0x18002a4d5  jnz     short loc_18002A4EC
0x18002a4d7  call    cs:__imp_GetLastError
0x18002a4dd  mov     ebx, eax
0x18002a4df  test    eax, eax
0x18002a4e1  jle     short loc_18002A4EC
0x18002a4e3  movzx   ebx, ax
0x18002a4e6  or      ebx, 80070000h
0x18002a4ec  mov     eax, ebx
0x18002a4ee  add     rsp, 20h
0x18002a4f2  pop     rbx
0x18002a4f3  retn
```
