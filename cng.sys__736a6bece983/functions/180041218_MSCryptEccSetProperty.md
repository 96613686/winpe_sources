# MSCryptEccSetProperty

- ea: `0x180041218`
- end: `0x180041350`
- name: `MSCryptEccSetProperty`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800411f0`
- `0x1800767b0`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180041218`
- `0x180041358`
- `0x180041640`

## string_xrefs

- `0x180041286`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800412db`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a3ca6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetProperty(_DWORD *a1, const wchar_t *a2, __int64 a3, unsigned int a4, int a5, int a6)
{
  int v6; // eax
  int v7; // edx
  unsigned int v8; // edi
  int v9; // r8d
  _QWORD *v10; // rcx
  __int64 v12; // r9
  char v13; // [rsp+30h] [rbp-18h]

  if ( a5 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        112);
    return v8;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v12 = 445;
    goto LABEL_22;
  }
  v6 = a1[1];
  if ( v6 == 1297301836 )
  {
    v8 = MSCryptEccSetAlgProperty((int)a1, a2, a3, a4, a6);
    if ( (v8 & 0x80000000) != 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v13 = -107;
LABEL_9:
        WPP_SF_sDsd(
          v10[3],
          v7,
          v9,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          v13);
        return v8;
      }
      return v8;
    }
    return 0;
  }
  if ( v6 != 1297304409 )
  {
    v12 = 453;
LABEL_22:
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    v8 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3959);
    return v8;
  }
  v8 = MSCryptEccSetKeyProperty(a1);
  if ( (v8 & 0x80000000) == 0 )
    return 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v7 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v7 & 1) != 0 )
    {
      v13 = -120;
      goto LABEL_9;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180041218  mov     [rsp+arg_0], rbx
0x18004121d  push    rdi
0x18004121e  sub     rsp, 40h
0x180041222  cmp     [rsp+48h+arg_20], 0
0x180041227  jnz     loc_1800412B4
0x18004122d  test    rcx, rcx
0x180041230  jz      loc_180041345
0x180041236  cmp     dword ptr [rcx], 0Ch
0x180041239  jb      loc_180041345
0x18004123f  mov     eax, [rcx+4]
0x180041242  cmp     eax, 4D53414Ch
0x180041247  jnz     loc_18004132C
0x18004124d  mov     eax, [rsp+48h+arg_28]
0x180041251  mov     [rsp+48h+var_28], eax
0x180041255  call    MSCryptEccSetAlgProperty
0x18004125a  mov     edi, eax
0x18004125c  test    eax, eax
0x18004125e  jns     loc_18004133E
0x180041264  mov     rcx, cs:WPP_GLOBAL_Control
0x18004126b  lea     rax, WPP_GLOBAL_Control
0x180041272  cmp     rcx, rax
0x180041275  jz      short loc_1800412A6
0x180041277  mov     eax, [rcx+2Ch]
0x18004127a  test    al, 1
0x18004127c  jz      short loc_1800412A6
0x18004127e  mov     dword ptr [rsp+48h+var_18], 0F95h
0x180041286  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004128d  mov     [rsp+48h+var_20], rbx
0x180041292  mov     [rsp+48h+var_28], edi
0x180041296  mov     rcx, [rcx+18h]
0x18004129a  lea     r9, aStatus; "Status"
0x1800412a1  call    WPP_SF_sDsd
0x1800412a6  mov     rbx, [rsp+48h+arg_0]
0x1800412ab  mov     eax, edi
0x1800412ad  add     rsp, 40h
0x1800412b1  pop     rdi
0x1800412b2  retn
0x1800412b4  mov     edi, 0C000000Dh
0x1800412b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800412c0  lea     rax, WPP_GLOBAL_Control
0x1800412c7  cmp     rcx, rax
0x1800412ca  jz      short loc_1800412A6
0x1800412cc  mov     eax, [rcx+2Ch]
0x1800412cf  test    al, 1
0x1800412d1  jz      short loc_1800412A6
0x1800412d3  mov     dword ptr [rsp+48h+var_18], 0F70h
0x1800412db  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800412e2  mov     [rsp+48h+var_20], rbx
0x1800412e7  mov     [rsp+48h+var_28], 0C000000Dh
0x1800412ef  jmp     short loc_180041296
0x1800412f1  mov     eax, [rsp+48h+arg_28]
0x1800412f5  mov     [rsp+48h+var_28], eax
0x1800412f9  call    MSCryptEccSetKeyProperty
0x1800412fe  mov     edi, eax
0x180041300  test    eax, eax
0x180041302  jns     short loc_18004133E
0x180041304  mov     rcx, cs:WPP_GLOBAL_Control
0x18004130b  lea     rax, WPP_GLOBAL_Control
0x180041312  cmp     rcx, rax
0x180041315  jz      short loc_1800412A6
0x180041317  mov     edx, [rcx+2Ch]
0x18004131a  test    dl, 1
0x18004131d  jz      short loc_1800412A6
0x18004131f  mov     dword ptr [rsp+48h+var_18], 0F88h
0x180041327  jmp     loc_180041286
0x18004132c  cmp     eax, 4D534B59h
0x180041331  jz      short loc_1800412F1
0x180041333  mov     r9d, 1C5h
0x180041339  jmp     loc_1800A3CA6
0x18004133e  xor     edi, edi
0x180041340  jmp     loc_1800412A6
0x180041345  mov     r9d, 1BDh
0x18004134b  jmp     loc_1800A3CA6
0x1800a3ca6  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3cad  mov     r8, rbx
0x1800a3cb0  lea     rdx, aStatus; "Status"
0x1800a3cb7  mov     ecx, 0C0000008h
0x1800a3cbc  call    DebugTraceError
0x1800a3cc1  mov     r9d, 0F77h
0x1800a3cc7  lea     rdx, aStatus; "Status"
0x1800a3cce  mov     r8, rbx
0x1800a3cd1  mov     ecx, 0C0000008h
0x1800a3cd6  mov     edi, 0C0000008h
0x1800a3cdb  call    DebugTraceError
0x1800a3ce0  nop
0x1800a3ce1  jmp     loc_1800412A6
```
