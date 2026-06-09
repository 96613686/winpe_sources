# DhcpCApiInitialize

- ea: `0x180003170`
- end: `0x1800031b6`
- name: `DhcpCApiInitialize`
- size: `70`
- prototype: `DWORD __stdcall(LPDWORD Version)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003170`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003195`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180003195`

## pseudocode

```c
DWORD __stdcall DhcpCApiInitialize(LPDWORD Version)
{
  DWORD result; // eax
  LPWSTR CommandLineW; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 111, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  result = 0;
  if ( Version )
    *Version = 2;
  return result;
}

```

## disassembly

```asm
0x180003170  push    rbx
0x180003172  sub     rsp, 20h
0x180003176  mov     rbx, rcx
0x180003179  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180003180  jnz     short loc_180003195
0x180003182  xor     eax, eax
0x180003184  test    rbx, rbx
0x180003187  jz      short loc_18000318F
0x180003189  mov     dword ptr [rbx], 2
0x18000318f  add     rsp, 20h
0x180003193  pop     rbx
0x180003194  retn
0x180003195  call    cs:__imp_GetCommandLineW
0x18000319b  mov     edx, 6Fh ; 'o'
0x1800031a0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800031a7  mov     r9, rax
0x1800031aa  mov     ecx, 404h
0x1800031af  call    WPP_SF_S
0x1800031b4  jmp     short loc_180003182
```
