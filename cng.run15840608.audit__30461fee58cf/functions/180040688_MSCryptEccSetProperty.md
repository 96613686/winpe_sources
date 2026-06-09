# MSCryptEccSetProperty

- ea: `0x180040688`
- end: `0x1800407c0`
- name: `MSCryptEccSetProperty`
- size: `312`
- prototype: `__int64 __fastcall(_DWORD *, int, int, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180040660`
- `0x180075da0`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180040688`
- `0x1800407c8`
- `0x180040ab0`

## string_xrefs

- `0x1800406f6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004074b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a1e76`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetProperty(_DWORD *a1, int a2, int a3, __int64 a4, int a5)
{
  int v5; // eax
  int v6; // edx
  unsigned int v7; // edi
  int v8; // r8d
  _QWORD *v9; // rcx
  __int64 v11; // r9
  char v12; // [rsp+30h] [rbp-18h]

  if ( a5 )
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        112);
    return v7;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v11 = 445;
    goto LABEL_22;
  }
  v5 = a1[1];
  if ( v5 == 1297301836 )
  {
    v7 = MSCryptEccSetAlgProperty(a1);
    if ( (v7 & 0x80000000) != 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v12 = -107;
LABEL_9:
        WPP_SF_sDsd(
          v9[3],
          v6,
          v8,
          (unsigned int)"Status",
          v7,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          v12);
        return v7;
      }
      return v7;
    }
    return 0;
  }
  if ( v5 != 1297304409 )
  {
    v11 = 453;
LABEL_22:
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v11);
    v7 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3959);
    return v7;
  }
  v7 = MSCryptEccSetKeyProperty(a1);
  if ( (v7 & 0x80000000) == 0 )
    return 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v6 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v6 & 1) != 0 )
    {
      v12 = -120;
      goto LABEL_9;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180040688  mov     [rsp+arg_0], rbx
0x18004068d  push    rdi
0x18004068e  sub     rsp, 40h
0x180040692  cmp     [rsp+48h+arg_20], 0
0x180040697  jnz     loc_180040724
0x18004069d  test    rcx, rcx
0x1800406a0  jz      loc_1800407B5
0x1800406a6  cmp     dword ptr [rcx], 0Ch
0x1800406a9  jb      loc_1800407B5
0x1800406af  mov     eax, [rcx+4]
0x1800406b2  cmp     eax, 4D53414Ch
0x1800406b7  jnz     loc_18004079C
0x1800406bd  mov     eax, [rsp+48h+arg_28]
0x1800406c1  mov     [rsp+48h+var_28], eax
0x1800406c5  call    MSCryptEccSetAlgProperty
0x1800406ca  mov     edi, eax
0x1800406cc  test    eax, eax
0x1800406ce  jns     loc_1800407AE
0x1800406d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406db  lea     rax, WPP_GLOBAL_Control
0x1800406e2  cmp     rcx, rax
0x1800406e5  jz      short loc_180040716
0x1800406e7  mov     eax, [rcx+2Ch]
0x1800406ea  test    al, 1
0x1800406ec  jz      short loc_180040716
0x1800406ee  mov     dword ptr [rsp+48h+var_18], 0F95h
0x1800406f6  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800406fd  mov     [rsp+48h+var_20], rbx
0x180040702  mov     [rsp+48h+var_28], edi
0x180040706  mov     rcx, [rcx+18h]
0x18004070a  lea     r9, aStatus; "Status"
0x180040711  call    WPP_SF_sDsd
0x180040716  mov     rbx, [rsp+48h+arg_0]
0x18004071b  mov     eax, edi
0x18004071d  add     rsp, 40h
0x180040721  pop     rdi
0x180040722  retn
0x180040724  mov     edi, 0C000000Dh
0x180040729  mov     rcx, cs:WPP_GLOBAL_Control
0x180040730  lea     rax, WPP_GLOBAL_Control
0x180040737  cmp     rcx, rax
0x18004073a  jz      short loc_180040716
0x18004073c  mov     eax, [rcx+2Ch]
0x18004073f  test    al, 1
0x180040741  jz      short loc_180040716
0x180040743  mov     dword ptr [rsp+48h+var_18], 0F70h
0x18004074b  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040752  mov     [rsp+48h+var_20], rbx
0x180040757  mov     [rsp+48h+var_28], 0C000000Dh
0x18004075f  jmp     short loc_180040706
0x180040761  mov     eax, [rsp+48h+arg_28]
0x180040765  mov     [rsp+48h+var_28], eax
0x180040769  call    MSCryptEccSetKeyProperty
0x18004076e  mov     edi, eax
0x180040770  test    eax, eax
0x180040772  jns     short loc_1800407AE
0x180040774  mov     rcx, cs:WPP_GLOBAL_Control
0x18004077b  lea     rax, WPP_GLOBAL_Control
0x180040782  cmp     rcx, rax
0x180040785  jz      short loc_180040716
0x180040787  mov     edx, [rcx+2Ch]
0x18004078a  test    dl, 1
0x18004078d  jz      short loc_180040716
0x18004078f  mov     dword ptr [rsp+48h+var_18], 0F88h
0x180040797  jmp     loc_1800406F6
0x18004079c  cmp     eax, 4D534B59h
0x1800407a1  jz      short loc_180040761
0x1800407a3  mov     r9d, 1C5h
0x1800407a9  jmp     loc_1800A1E76
0x1800407ae  xor     edi, edi
0x1800407b0  jmp     loc_180040716
0x1800407b5  mov     r9d, 1BDh
0x1800407bb  jmp     loc_1800A1E76
0x1800a1e76  lea     rbx, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1e7d  mov     r8, rbx
0x1800a1e80  lea     rdx, aStatus; "Status"
0x1800a1e87  mov     ecx, 0C0000008h
0x1800a1e8c  call    DebugTraceError
0x1800a1e91  mov     r9d, 0F77h
0x1800a1e97  lea     rdx, aStatus; "Status"
0x1800a1e9e  mov     r8, rbx
0x1800a1ea1  mov     ecx, 0C0000008h
0x1800a1ea6  mov     edi, 0C0000008h
0x1800a1eab  call    DebugTraceError
0x1800a1eb0  nop
0x1800a1eb1  jmp     loc_180040716
```
