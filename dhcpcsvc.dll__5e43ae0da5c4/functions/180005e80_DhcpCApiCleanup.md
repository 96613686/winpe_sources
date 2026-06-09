# DhcpCApiCleanup

- ea: `0x180005e80`
- end: `0x180005eb1`
- name: `DhcpCApiCleanup`
- size: `49`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005e80`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005e8d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005e8d`

## pseudocode

```c
void __stdcall DhcpCApiCleanup()
{
  LPWSTR CommandLineW; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 112, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
}

```

## disassembly

```asm
0x180005e80  sub     rsp, 28h
0x180005e84  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005e8b  jz      short loc_180005EAC
0x180005e8d  call    cs:__imp_GetCommandLineW
0x180005e93  mov     edx, 70h ; 'p'
0x180005e98  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005e9f  mov     r9, rax
0x180005ea2  mov     ecx, 404h
0x180005ea7  call    WPP_SF_S
0x180005eac  add     rsp, 28h
0x180005eb0  retn
```
