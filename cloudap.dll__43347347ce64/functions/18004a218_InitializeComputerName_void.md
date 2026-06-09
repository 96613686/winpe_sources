# InitializeComputerName(void)

- ea: `0x18004a218`
- end: `0x18004a33a`
- name: `?InitializeComputerName@@YAJXZ`
- size: `290`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b1e0`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180042830`
- `0x18004a218`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18004a235`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18004a235`

## string_xrefs

- `0x18004a23f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a27f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a2ec`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a25f`: `GetComputerNameW`
- `0x18004a29f`: `GetComputerNameW length too large`

## pseudocode

```c
__int64 InitializeComputerName(void)
{
  unsigned int v0; // ebx
  const char *v1; // r9
  const char *v2; // r9
  unsigned __int64 v3; // rcx
  const char *v4; // r9
  int v6; // [rsp+20h] [rbp-28h]
  int v7; // [rsp+20h] [rbp-28h]
  int v8; // [rsp+20h] [rbp-28h]
  DWORD nSize; // [rsp+50h] [rbp+8h] BYREF

  nSize = 16;
  if ( GetComputerNameW(&g_awchComputerName, &nSize) )
  {
    if ( nSize <= 0xF )
    {
      v3 = 2LL * nSize;
      if ( v3 >= 0x20 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)&g_awchComputerName + v3) = 0;
      nSize = 17;
      v0 = RtlStringCchPrintfW(&g_awchComputerName$, 0x11u, L"%ws$", &g_awchComputerName);
      if ( v0 )
      {
        v4 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v8 = 356;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v0, v4, v8, "RtlStringCchPrintfW", &Class);
      }
    }
    else
    {
      v0 = -1073741595;
      v2 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v7 = 344;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v2, v7, "GetComputerNameW length too large", &Class);
    }
  }
  else
  {
    v0 = -1073741801;
    v1 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v6 = 338;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v1, v6, "GetComputerNameW", &Class);
  }
  return v0;
}

```

## disassembly

```asm
0x18004a218  push    rbx
0x18004a21a  sub     rsp, 40h
0x18004a21e  lea     rbx, ?g_awchComputerName@@3PAGA; ushort near * g_awchComputerName
0x18004a225  mov     [rsp+48h+nSize], 10h
0x18004a22d  mov     rcx, rbx; lpBuffer
0x18004a230  lea     rdx, [rsp+48h+nSize]; nSize
0x18004a235  call    cs:__imp_GetComputerNameW
0x18004a23b  test    eax, eax
0x18004a23d  jnz     short loc_18004A278
0x18004a23f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a246  mov     ebx, 0C0000017h
0x18004a24b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a250  mov     r9, rax
0x18004a253  lea     rax, Class
0x18004a25a  mov     [rsp+48h+var_18], rax
0x18004a25f  lea     rax, aGetcomputernam; "GetComputerNameW"
0x18004a266  mov     [rsp+48h+var_20], rax
0x18004a26b  mov     [rsp+48h+var_28], 152h
0x18004a273  jmp     loc_18004A31B
0x18004a278  cmp     [rsp+48h+nSize], 0Fh
0x18004a27d  jbe     short loc_18004A2B5
0x18004a27f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a286  mov     ebx, 0C00000E5h
0x18004a28b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a290  mov     r9, rax
0x18004a293  lea     rax, Class
0x18004a29a  mov     [rsp+48h+var_18], rax
0x18004a29f  lea     rax, aGetcomputernam_0; "GetComputerNameW length too large"
0x18004a2a6  mov     [rsp+48h+var_20], rax
0x18004a2ab  mov     [rsp+48h+var_28], 158h
0x18004a2b3  jmp     short loc_18004A31B
0x18004a2b5  mov     eax, [rsp+48h+nSize]
0x18004a2b9  lea     rcx, [rax+rax]
0x18004a2bd  cmp     rcx, 20h ; ' '
0x18004a2c1  jnb     short loc_18004A334
0x18004a2c3  xor     eax, eax
0x18004a2c5  lea     r8, aWs; "%ws$"
0x18004a2cc  mov     [rcx+rbx], ax
0x18004a2d0  mov     r9, rbx
0x18004a2d3  lea     rcx, ?g_awchComputerName$@@3PAGA; unsigned __int16 *
0x18004a2da  lea     edx, [rax+11h]; unsigned __int64
0x18004a2dd  mov     [rsp+48h+nSize], edx
0x18004a2e1  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a2e6  mov     ebx, eax
0x18004a2e8  test    eax, eax
0x18004a2ea  jz      short loc_18004A32C
0x18004a2ec  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a2f3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a2f8  mov     r9, rax
0x18004a2fb  lea     rax, Class
0x18004a302  mov     [rsp+48h+var_18], rax
0x18004a307  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18004a30e  mov     [rsp+48h+var_20], rax
0x18004a313  mov     [rsp+48h+var_28], 164h
0x18004a31b  mov     r8d, ebx
0x18004a31e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a325  xor     ecx, ecx
0x18004a327  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a32c  mov     eax, ebx
0x18004a32e  add     rsp, 40h
0x18004a332  pop     rbx
0x18004a333  retn
0x18004a334  call    __report_rangecheckfailure
```
