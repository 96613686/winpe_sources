# SpInstanceInit(ulong,_SECPKG_DLL_FUNCTIONS *,void * *)

- ea: `0x1800197d0`
- end: `0x180019835`
- name: `?SpInstanceInit@@YAJKPEAU_SECPKG_DLL_FUNCTIONS@@PEAPEAX@Z`
- size: `101`
- prototype: `__int64 __fastcall(unsigned int, struct _SECPKG_DLL_FUNCTIONS *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e710`
- `0x180019348`
- `0x1800197d0`

## string_xrefs

- `0x180019805`: `onecore\ds\security\protocols\negoexts\userapi.cxx`

## pseudocode

```c
__int64 __fastcall SpInstanceInit(__int64 a1, struct _SECPKG_DLL_FUNCTIONS *a2, void **a3)
{
  int v3; // ebx

  NegoExtsGlobaDllFunctions = a2;
  v3 = WSTInitUserModeContextList();
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids,
      v3,
      (__int64)"onecore\\ds\\security\\protocols\\negoexts\\userapi.cxx",
      199);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800197d0  push    rbx
0x1800197d2  sub     rsp, 30h
0x1800197d6  mov     cs:?NegoExtsGlobaDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA, rdx; _SECPKG_DLL_FUNCTIONS * NegoExtsGlobaDllFunctions
0x1800197dd  call    ?WSTInitUserModeContextList@@YAJXZ; WSTInitUserModeContextList(void)
0x1800197e2  mov     ebx, eax
0x1800197e4  test    eax, eax
0x1800197e6  jns     short loc_18001982D
0x1800197e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197ef  lea     rax, WPP_GLOBAL_Control
0x1800197f6  cmp     rcx, rax
0x1800197f9  jz      short loc_18001982D
0x1800197fb  test    byte ptr [rcx+1Ch], 1
0x1800197ff  jz      short loc_18001982D
0x180019801  mov     rcx, [rcx+10h]
0x180019805  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\negoe"...
0x18001980c  mov     edx, 0Fh
0x180019811  mov     [rsp+38h+var_10], 0C7h
0x180019819  mov     r9d, ebx
0x18001981c  mov     [rsp+38h+var_18], rax
0x180019821  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x180019828  call    WPP_SF_Dsd
0x18001982d  mov     eax, ebx
0x18001982f  add     rsp, 30h
0x180019833  pop     rbx
0x180019834  retn
```
