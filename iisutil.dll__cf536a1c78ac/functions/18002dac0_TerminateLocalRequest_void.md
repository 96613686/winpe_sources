# TerminateLocalRequest(void)

- ea: `0x18002dac0`
- end: `0x18002db1f`
- name: `?TerminateLocalRequest@@YAJXZ`
- size: `95`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18002dac0`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x18002dad4`
- `WS2_32!FreeAddrInfoW` at `0x18002dad4`
- `WS2_32!__imp_WSACleanup` at `0x18002daef`
- `WS2_32!__imp_WSACleanup` at `0x18002daef`

## pseudocode

```c
__int64 TerminateLocalRequest(void)
{
  unsigned int v0; // ebx
  int v1; // eax

  v0 = 0;
  if ( g_pHostAddrInfo )
  {
    FreeAddrInfoW(g_pHostAddrInfo);
    g_pHostAddrInfo = 0;
  }
  if ( g_fLocalRequestWSAStartupCalled )
  {
    v1 = WSACleanup();
    if ( v1 )
    {
      if ( v1 > 0 )
        return (unsigned __int16)v1 | 0x80070000;
      else
        return (unsigned int)v1;
    }
    else
    {
      g_fLocalRequestWSAStartupCalled = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18002dac0  push    rbx
0x18002dac2  sub     rsp, 20h
0x18002dac6  mov     rcx, cs:?g_pHostAddrInfo@@3PEAUaddrinfoW@@EA; pAddrInfo
0x18002dacd  xor     ebx, ebx
0x18002dacf  test    rcx, rcx
0x18002dad2  jz      short loc_18002DAE7
0x18002dad4  call    cs:__imp_FreeAddrInfoW
0x18002dadb  nop     dword ptr [rax+rax+00h]
0x18002dae0  mov     cs:?g_pHostAddrInfo@@3PEAUaddrinfoW@@EA, rbx; addrinfoW * g_pHostAddrInfo
0x18002dae7  cmp     cs:?g_fLocalRequestWSAStartupCalled@@3HA, ebx; int g_fLocalRequestWSAStartupCalled
0x18002daed  jz      short loc_18002DB16
0x18002daef  call    cs:__imp_WSACleanup
0x18002daf6  nop     dword ptr [rax+rax+00h]
0x18002dafb  test    eax, eax
0x18002dafd  jz      short loc_18002DB10
0x18002daff  jg      short loc_18002DB05
0x18002db01  mov     ebx, eax
0x18002db03  jmp     short loc_18002DB16
0x18002db05  movzx   ebx, ax
0x18002db08  or      ebx, 80070000h
0x18002db0e  jmp     short loc_18002DB16
0x18002db10  mov     cs:?g_fLocalRequestWSAStartupCalled@@3HA, ebx; int g_fLocalRequestWSAStartupCalled
0x18002db16  mov     eax, ebx
0x18002db18  add     rsp, 20h
0x18002db1c  pop     rbx
0x18002db1d  retn
```
