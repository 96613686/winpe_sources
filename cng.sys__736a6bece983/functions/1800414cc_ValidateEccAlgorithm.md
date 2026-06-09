# ValidateEccAlgorithm

- ea: `0x1800414cc`
- end: `0x1800415f5`
- name: `ValidateEccAlgorithm`
- size: `297`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180041358`
- `0x180076cd4`
- `0x180077200`
- `0x1800772ec`
- `0x1800779e8`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x1800414cc`
- `0x1800415fc`

## string_xrefs

- `0x180041583`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a3d6a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ValidateEccAlgorithm(_DWORD *a1, int a2, unsigned int a3, _DWORD *a4, _QWORD *a5)
{
  int v7; // edx
  int v8; // r8d
  __int64 v9; // r11
  _QWORD *v10; // rcx
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // ebx
  __int64 v15; // r9

  if ( a1 && a5 )
  {
    if ( a1[1] != 1297301836 || *a1 != 24 )
    {
      v15 = 497;
      goto LABEL_22;
    }
    if ( CryptAuditTranslateAlgID((unsigned int)a1[2], a3) )
    {
      v10 = *(_QWORD **)(v9 + 16);
      if ( v10 )
      {
        v11 = *(_DWORD *)(v10[1] + 12LL);
        v12 = *(_DWORD *)(*v10 + 12LL);
      }
      else
      {
        v11 = 0;
        v12 = 0;
      }
      *a4 = v12;
      if ( a2 && v11 != a2 )
      {
        v15 = 526;
LABEL_22:
        v13 = -1073741811;
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v15);
        return v13;
      }
      *a5 = v9;
      return 0;
    }
    else
    {
      v13 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v7,
          v8,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          249);
    }
  }
  else
  {
    v13 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        231);
  }
  return v13;
}

```

## disassembly

```asm
0x1800414cc  mov     [rsp+arg_0], rbx
0x1800414d1  mov     [rsp+arg_8], rsi
0x1800414d6  push    rdi
0x1800414d7  sub     rsp, 40h
0x1800414db  mov     rsi, r9
0x1800414de  mov     edi, edx
0x1800414e0  mov     r11, rcx
0x1800414e3  test    rcx, rcx
0x1800414e6  jz      short loc_180041558
0x1800414e8  mov     rbx, [rsp+48h+arg_20]
0x1800414ed  test    rbx, rbx
0x1800414f0  jz      short loc_180041558
0x1800414f2  cmp     dword ptr [rcx+4], 4D53414Ch
0x1800414f9  jnz     loc_1800415EA
0x1800414ff  cmp     dword ptr [rcx], 18h
0x180041502  jnz     loc_1800415EA
0x180041508  mov     ecx, [rcx+8]
0x18004150b  mov     edx, r8d
0x18004150e  call    CryptAuditTranslateAlgID
0x180041513  test    rax, rax
0x180041516  jz      loc_1800415A5
0x18004151c  mov     rcx, [r11+10h]
0x180041520  test    rcx, rcx
0x180041523  jz      loc_1800415CE
0x180041529  mov     rax, [rcx+8]
0x18004152d  mov     edx, [rax+0Ch]
0x180041530  mov     rax, [rcx]
0x180041533  mov     ecx, [rax+0Ch]
0x180041536  mov     [rsi], ecx
0x180041538  test    edi, edi
0x18004153a  jnz     loc_1800415D7
0x180041540  mov     [rbx], r11
0x180041543  xor     ebx, ebx
0x180041545  mov     rsi, [rsp+48h+arg_8]
0x18004154a  mov     eax, ebx
0x18004154c  mov     rbx, [rsp+48h+arg_0]
0x180041551  add     rsp, 40h
0x180041555  pop     rdi
0x180041556  retn
0x180041558  mov     ebx, 0C000000Dh
0x18004155d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041564  lea     rax, WPP_GLOBAL_Control
0x18004156b  cmp     rcx, rax
0x18004156e  jz      short loc_180041545
0x180041570  mov     eax, [rcx+2Ch]
0x180041573  test    al, 1
0x180041575  jz      short loc_180041545
0x180041577  mov     [rsp+48h+var_18], 1E7h
0x18004157f  mov     rcx, [rcx+18h]
0x180041583  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004158a  mov     [rsp+48h+var_20], rax
0x18004158f  lea     r9, aStatus; "Status"
0x180041596  mov     [rsp+48h+var_28], 0C000000Dh
0x18004159e  call    WPP_SF_sDsd
0x1800415a3  jmp     short loc_180041545
0x1800415a5  mov     ebx, 0C000000Dh
0x1800415aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415b1  lea     rax, WPP_GLOBAL_Control
0x1800415b8  cmp     rcx, rax
0x1800415bb  jz      short loc_180041545
0x1800415bd  mov     eax, [rcx+2Ch]
0x1800415c0  test    al, 1
0x1800415c2  jz      short loc_180041545
0x1800415c4  mov     [rsp+48h+var_18], 1F9h
0x1800415cc  jmp     short loc_18004157F
0x1800415ce  xor     edx, edx
0x1800415d0  xor     ecx, ecx
0x1800415d2  jmp     loc_180041536
0x1800415d7  cmp     edx, edi
0x1800415d9  jz      loc_180041540
0x1800415df  mov     r9d, 20Eh
0x1800415e5  jmp     loc_1800A3D6A
0x1800415ea  mov     r9d, 1F1h
0x1800415f0  jmp     loc_1800A3D6A
0x1800a3d6a  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3d71  mov     ecx, 0C000000Dh
0x1800a3d76  lea     rdx, aStatus; "Status"
0x1800a3d7d  mov     ebx, 0C000000Dh
0x1800a3d82  call    DebugTraceError
0x1800a3d87  nop
0x1800a3d88  jmp     loc_180041545
```
