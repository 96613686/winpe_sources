# InitializeLoader

- ea: `0x180013f38`
- end: `0x180013faf`
- name: `InitializeLoader`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013a7c`

## callees

- `0x18000d02c`
- `0x180013f38`
- `0x180013fb8`

## string_xrefs

- `0x180013f89`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
    if ( v0 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v1,
          v2,
          (unsigned int)"sResult",
          v0,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          172);
    }
    else
    {
      g_fLoaderInitialized = 1;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180013f38  push    rbx
0x180013f3a  sub     rsp, 40h
0x180013f3e  xor     ebx, ebx
0x180013f40  cmp     cs:g_fLoaderInitialized, ebx
0x180013f46  jnz     short loc_180013F64
0x180013f48  mov     cs:g_pLoadedProviderList, rbx
0x180013f4f  call    _InitializeLoaderLock
0x180013f54  mov     ebx, eax
0x180013f56  test    eax, eax
0x180013f58  js      short loc_180013F6C
0x180013f5a  mov     cs:g_fLoaderInitialized, 1
0x180013f64  mov     eax, ebx
0x180013f66  add     rsp, 40h
0x180013f6a  pop     rbx
0x180013f6b  retn
0x180013f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f73  lea     rax, WPP_GLOBAL_Control
0x180013f7a  cmp     rcx, rax
0x180013f7d  jz      short loc_180013F64
0x180013f7f  test    byte ptr [rcx+1Ch], 1
0x180013f83  jz      short loc_180013F64
0x180013f85  mov     rcx, [rcx+10h]
0x180013f89  lea     rax, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013f90  mov     [rsp+48h+var_18], 7ACh
0x180013f98  lea     r9, aSresult; "sResult"
0x180013f9f  mov     [rsp+48h+var_20], rax
0x180013fa4  mov     [rsp+48h+var_28], ebx
0x180013fa8  call    WPP_SF_sDsd
0x180013fad  jmp     short loc_180013F64
```
