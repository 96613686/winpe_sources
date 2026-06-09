# CSDTFxd::GetTableMetaQuery(__MIDL___MIDL_itf_catalog_0000_0000_0001 const *,ulong,ushort const * &,ushort const * &)

- ea: `0x180027f44`
- end: `0x180028007`
- name: `?GetTableMetaQuery@CSDTFxd@@AEBAJPEBU__MIDL___MIDL_itf_catalog_0000_0000_0001@@KAEAPEBG1@Z`
- size: `195`
- prototype: `__int64 __fastcall(CSDTFxd *__hidden this, const struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180028010`

## callees

- `0x180027f44`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180027ffa`
- `IisRTL!PuDbgPrint` at `0x180027ffa`

## string_xrefs

- `0x180027ff3`: `inetsrv\iis\mb\config\src\stores\fixedtable\sdtfxd.cpp`

## pseudocode

```c
__int64 __fastcall CSDTFxd::GetTableMetaQuery(
        CSDTFxd *this,
        const struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *a2,
        int a3,
        const unsigned __int16 **a4,
        const unsigned __int16 **a5)
{
  int v5; // eax

  *a4 = 0;
  *a5 = 0;
  while ( a3 )
  {
    v5 = *((_DWORD *)a2 + 3);
    if ( v5 )
    {
      if ( v5 == 1 )
      {
        if ( *a5 || *((_DWORD *)a2 + 2) != 2 || *((_DWORD *)a2 + 4) != 130 || !*(_QWORD *)a2 )
          return 2149648395LL;
        *a5 = *(const unsigned __int16 **)a2;
      }
      else if ( (v5 & 0xF0000000) == 0 )
      {
        return 2149648395LL;
      }
    }
    else
    {
      if ( *a4 || *((_DWORD *)a2 + 2) != 2 || *((_DWORD *)a2 + 4) != 130 || !*(_QWORD *)a2 )
        return 2149648395LL;
      *a4 = *(const unsigned __int16 **)a2;
    }
    --a3;
    a2 = (const struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *)((char *)a2 + 24);
  }
  if ( *a4 && *a5 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\config\\src\\stores\\fixedtable\\sdtfxd.cpp",
      1573,
      "CSDTFxd::GetTableMetaQuery",
      "Warning! Users should NOT query TableMeta by both DatabaseName AND TableName.  It is redundant.  Just query by iTA"
      "BLEMETA_InternalName.\n");
  return 0;
}

```

## disassembly

```asm
0x180027f44  sub     rsp, 38h
0x180027f48  mov     rcx, [rsp+38h+arg_20]
0x180027f4d  xor     r10d, r10d
0x180027f50  mov     [r9], r10
0x180027f53  mov     r11d, 82h
0x180027f59  mov     [rcx], r10
0x180027f5c  test    r8d, r8d
0x180027f5f  jz      short loc_180027FC0
0x180027f61  mov     eax, [rdx+0Ch]
0x180027f64  test    eax, eax
0x180027f66  jnz     short loc_180027F86
0x180027f68  cmp     [r9], r10
0x180027f6b  jnz     short loc_180027FB9
0x180027f6d  cmp     dword ptr [rdx+8], 2
0x180027f71  jnz     short loc_180027FB9
0x180027f73  cmp     [rdx+10h], r11d
0x180027f77  jnz     short loc_180027FB9
0x180027f79  mov     rax, [rdx]
0x180027f7c  test    rax, rax
0x180027f7f  jz      short loc_180027FB9
0x180027f81  mov     [r9], rax
0x180027f84  jmp     short loc_180027FB0
0x180027f86  cmp     eax, 1
0x180027f89  jnz     short loc_180027FA9
0x180027f8b  cmp     [rcx], r10
0x180027f8e  jnz     short loc_180027FB9
0x180027f90  cmp     dword ptr [rdx+8], 2
0x180027f94  jnz     short loc_180027FB9
0x180027f96  cmp     [rdx+10h], r11d
0x180027f9a  jnz     short loc_180027FB9
0x180027f9c  mov     rax, [rdx]
0x180027f9f  test    rax, rax
0x180027fa2  jz      short loc_180027FB9
0x180027fa4  mov     [rcx], rax
0x180027fa7  jmp     short loc_180027FB0
0x180027fa9  test    eax, 0F0000000h
0x180027fae  jz      short loc_180027FB9
0x180027fb0  dec     r8d
0x180027fb3  add     rdx, 18h
0x180027fb7  jmp     short loc_180027F5C
0x180027fb9  mov     eax, 8021080Bh
0x180027fbe  jmp     short loc_180028002
0x180027fc0  cmp     [r9], r10
0x180027fc3  jz      short loc_180028000
0x180027fc5  cmp     [rcx], r10
0x180027fc8  jz      short loc_180028000
0x180027fca  test    byte ptr cs:g_dwDebugFlags, 3
0x180027fd1  jz      short loc_180028000
0x180027fd3  mov     rcx, cs:g_pDebug
0x180027fda  lea     rax, aWarningUsersSh; "Warning! Users should NOT query TableMe"...
0x180027fe1  lea     r9, aCsdtfxdGettabl; "CSDTFxd::GetTableMetaQuery"
0x180027fe8  mov     [rsp+38h+var_18], rax
0x180027fed  mov     r8d, 625h
0x180027ff3  lea     rdx, aInetsrvIisMbCo_1; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180027ffa  call    cs:__imp_PuDbgPrint
0x180028000  xor     eax, eax
0x180028002  add     rsp, 38h
0x180028006  retn
```
