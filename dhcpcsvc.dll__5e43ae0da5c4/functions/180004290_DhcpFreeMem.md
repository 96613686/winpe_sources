# DhcpFreeMem

- ea: `0x180004290`
- end: `0x1800042ce`
- name: `DhcpFreeMem`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b180`

## callees

- `0x180002160`
- `0x180004290`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800042a2`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800042a2`

## pseudocode

```c
__int64 __fastcall DhcpFreeMem(__int64 a1)
{
  LPWSTR CommandLineW; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 210, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  return DhcpFree(a1);
}

```

## disassembly

```asm
0x180004290  push    rbx
0x180004292  sub     rsp, 20h
0x180004296  mov     rbx, rcx
0x180004299  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800042a0  jz      short loc_1800042C1
0x1800042a2  call    cs:__imp_GetCommandLineW
0x1800042a8  mov     edx, 0D2h
0x1800042ad  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800042b4  mov     r9, rax
0x1800042b7  mov     ecx, 404h
0x1800042bc  call    WPP_SF_S
0x1800042c1  mov     rcx, rbx
0x1800042c4  add     rsp, 20h
0x1800042c8  pop     rbx
0x1800042c9  jmp     DhcpFree
```
