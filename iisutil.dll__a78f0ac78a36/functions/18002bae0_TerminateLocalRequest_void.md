# TerminateLocalRequest(void)

- ea: `0x18002bae0`
- end: `0x18002bb32`
- name: `?TerminateLocalRequest@@YAJXZ`
- size: `82`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18002bae0`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x18002baf4`
- `WS2_32!FreeAddrInfoW` at `0x18002baf4`
- `WS2_32!__imp_WSACleanup` at `0x18002bb09`
- `WS2_32!__imp_WSACleanup` at `0x18002bb09`

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
0x18002bae0  push    rbx
0x18002bae2  sub     rsp, 20h
0x18002bae6  mov     rcx, cs:?g_pHostAddrInfo@@3PEAUaddrinfoW@@EA; pAddrInfo
0x18002baed  xor     ebx, ebx
0x18002baef  test    rcx, rcx
0x18002baf2  jz      short loc_18002BB01
0x18002baf4  call    cs:__imp_FreeAddrInfoW
0x18002bafa  mov     cs:?g_pHostAddrInfo@@3PEAUaddrinfoW@@EA, rbx; addrinfoW * g_pHostAddrInfo
0x18002bb01  cmp     cs:?g_fLocalRequestWSAStartupCalled@@3HA, ebx; int g_fLocalRequestWSAStartupCalled
0x18002bb07  jz      short loc_18002BB2A
0x18002bb09  call    cs:__imp_WSACleanup
0x18002bb0f  test    eax, eax
0x18002bb11  jz      short loc_18002BB24
0x18002bb13  jg      short loc_18002BB19
0x18002bb15  mov     ebx, eax
0x18002bb17  jmp     short loc_18002BB2A
0x18002bb19  movzx   ebx, ax
0x18002bb1c  or      ebx, 80070000h
0x18002bb22  jmp     short loc_18002BB2A
0x18002bb24  mov     cs:?g_fLocalRequestWSAStartupCalled@@3HA, ebx; int g_fLocalRequestWSAStartupCalled
0x18002bb2a  mov     eax, ebx
0x18002bb2c  add     rsp, 20h
0x18002bb30  pop     rbx
0x18002bb31  retn
```
