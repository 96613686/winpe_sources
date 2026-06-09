# InitializeLoader

- ea: `0x180009c20`
- end: `0x180009c97`
- name: `InitializeLoader`
- size: `119`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b45c`

## callees

- `0x180004470`
- `0x180009c20`
- `0x18000bb18`

## string_xrefs

- `0x180009c5f`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 InitializeLoader()
{
  int v0; // ebx
  int v1; // edx
  int v2; // r8d

  v0 = 0;
  if ( !g_fLoaderInitialized )
  {
    g_pLoadedProviderList = 0;
    v0 = InitializeLoaderLock();
    if ( v0 >= 0 )
    {
      g_fLoaderInitialized = 1;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v1,
        v2,
        (unsigned int)"sResult",
        v0,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        172);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180009c20  push    rbx
0x180009c22  sub     rsp, 40h
0x180009c26  xor     ebx, ebx
0x180009c28  cmp     cs:g_fLoaderInitialized, ebx
0x180009c2e  jnz     short loc_180009C8F
0x180009c30  mov     cs:g_pLoadedProviderList, rbx
0x180009c37  call    _InitializeLoaderLock
0x180009c3c  mov     ebx, eax
0x180009c3e  test    eax, eax
0x180009c40  jns     short loc_180009C85
0x180009c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c49  lea     rax, WPP_GLOBAL_Control
0x180009c50  cmp     rcx, rax
0x180009c53  jz      short loc_180009C8F
0x180009c55  test    byte ptr [rcx+1Ch], 1
0x180009c59  jz      short loc_180009C8F
0x180009c5b  mov     rcx, [rcx+10h]
0x180009c5f  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009c66  mov     [rsp+48h+var_18], 7ACh
0x180009c6e  lea     r9, aSresult; "sResult"
0x180009c75  mov     [rsp+48h+var_20], rax
0x180009c7a  mov     [rsp+48h+var_28], ebx
0x180009c7e  call    WPP_SF_sDsd
0x180009c83  jmp     short loc_180009C8F
0x180009c85  mov     cs:g_fLoaderInitialized, 1
0x180009c8f  mov     eax, ebx
0x180009c91  add     rsp, 40h
0x180009c95  pop     rbx
0x180009c96  retn
```
