# MSCryptKDDestroyKey

- ea: `0x180036fa0`
- end: `0x1800371d9`
- name: `MSCryptKDDestroyKey`
- size: `569`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005670`
- `0x180074150`

## callees

- `0x1800082b0`
- `0x180036fa0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180036ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003705f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003705f`
- `ntoskrnl!SkIsSecureKernel` at `0x18003719f`
- `ntoskrnl!SkIsSecureKernel` at `0x1800371bc`
- `ntoskrnl!SkIsSecureKernel` at `0x18003719f`
- `ntoskrnl!SkIsSecureKernel` at `0x1800371bc`
- `ntoskrnl!SkFreePool` at `0x180037144`
- `ntoskrnl!SkFreePool` at `0x18003715d`
- `ntoskrnl!SkFreePool` at `0x180037144`
- `ntoskrnl!SkFreePool` at `0x18003715d`

## string_xrefs

- `0x1800370a0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18003710f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180037172`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDDestroyKey(__int64 a1, __int64 a2, int a3)
{
  void *v4; // rbx
  int v5; // eax
  _BYTE *v6; // rax
  __int64 v7; // rcx
  _BYTE *v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  void *v11; // rbx
  int v13; // edx

  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297304409 )
    {
      v4 = *(void **)(a1 + 56);
      if ( v4 )
      {
        LOBYTE(v5) = g_TrustedEnvironment;
        if ( !g_TrustedEnvironment )
        {
          v5 = ((int)SkIsSecureKernel(a1, a2) >> 31) + 2;
          g_TrustedEnvironment = v5;
        }
        if ( (v5 & 2) != 0 )
          SkFreePool(512, v4);
        else
          ExFreePoolWithTag(v4, 0x62676E43u);
        *(_QWORD *)(a1 + 56) = 0;
        v6 = (_BYTE *)(a1 + 48);
        v7 = 592;
        do
        {
          *v6++ = 0;
          --v7;
        }
        while ( v7 );
      }
      v8 = *(_BYTE **)(a1 + 24);
      if ( v8 )
      {
        v9 = *(unsigned int *)(a1 + 16);
        if ( *(_DWORD *)(a1 + 16) )
        {
          do
          {
            *v8++ = 0;
            --v9;
          }
          while ( v9 );
        }
        LOBYTE(v10) = g_TrustedEnvironment;
        v11 = *(void **)(a1 + 24);
        if ( !g_TrustedEnvironment )
        {
          v10 = ((int)SkIsSecureKernel(v9, a2) >> 31) + 2;
          g_TrustedEnvironment = v10;
        }
        if ( (v10 & 2) != 0 )
          SkFreePool(512, v11);
        else
          ExFreePoolWithTag(v11, 0x62676E43u);
        *(_QWORD *)(a1 + 24) = 0;
      }
      return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        84);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      a2,
      a3,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      75);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v13 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v13 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        15);
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x180036fa0  mov     [rsp+arg_8], rbx
0x180036fa5  push    rdi
0x180036fa6  sub     rsp, 40h
0x180036faa  mov     rdi, rcx
0x180036fad  test    rcx, rcx
0x180036fb0  jz      loc_1800370F1
0x180036fb6  cmp     dword ptr [rcx+4], 4D534B59h
0x180036fbd  jnz     loc_180037082
0x180036fc3  mov     rbx, [rcx+38h]
0x180036fc7  mov     [rsp+48h+arg_0], rsi
0x180036fcc  xor     esi, esi
0x180036fce  test    rbx, rbx
0x180036fd1  jz      short loc_18003701D
0x180036fd3  mov     eax, cs:g_TrustedEnvironment
0x180036fd9  test    eax, eax
0x180036fdb  jz      loc_18003719F
0x180036fe1  test    al, 2
0x180036fe3  jnz     loc_18003713C
0x180036fe9  mov     edx, 62676E43h; Tag
0x180036fee  mov     rcx, rbx; P
0x180036ff1  call    cs:__imp_ExFreePoolWithTag
0x180036ff8  nop     dword ptr [rax+rax+00h]
0x180036ffd  mov     [rdi+38h], rsi
0x180037001  lea     rax, [rdi+30h]
0x180037005  mov     ecx, 250h
0x18003700a  nop     word ptr [rax+rax+00h]
0x180037010  mov     [rax], sil
0x180037013  lea     rax, [rax+1]
0x180037017  sub     rcx, 1
0x18003701b  jnz     short loc_180037010
0x18003701d  mov     rax, [rdi+18h]
0x180037021  test    rax, rax
0x180037024  jz      short loc_18003706F
0x180037026  mov     ecx, [rdi+10h]
0x180037029  test    rcx, rcx
0x18003702c  jz      short loc_18003703D
0x18003702e  xchg    ax, ax
0x180037030  mov     [rax], sil
0x180037033  lea     rax, [rax+1]
0x180037037  sub     rcx, 1
0x18003703b  jnz     short loc_180037030
0x18003703d  mov     eax, cs:g_TrustedEnvironment
0x180037043  mov     rbx, [rdi+18h]
0x180037047  test    eax, eax
0x180037049  jz      loc_1800371BC
0x18003704f  test    al, 2
0x180037051  jnz     loc_180037155
0x180037057  mov     edx, 62676E43h; Tag
0x18003705c  mov     rcx, rbx; P
0x18003705f  call    cs:__imp_ExFreePoolWithTag
0x180037066  nop     dword ptr [rax+rax+00h]
0x18003706b  mov     [rdi+18h], rsi
0x18003706f  mov     eax, esi
0x180037071  mov     rsi, [rsp+48h+arg_0]
0x180037076  mov     rbx, [rsp+48h+arg_8]
0x18003707b  add     rsp, 40h
0x18003707f  pop     rdi
0x180037080  retn
0x180037082  mov     rcx, cs:WPP_GLOBAL_Control
0x180037089  lea     rbx, WPP_GLOBAL_Control
0x180037090  cmp     rcx, rbx
0x180037093  jz      short loc_1800370A0
0x180037095  mov     eax, [rcx+2Ch]
0x180037098  test    al, 1
0x18003709a  jnz     loc_18003716E
0x1800370a0  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800370a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370ae  cmp     rcx, rbx
0x1800370b1  jz      short loc_1800370E0
0x1800370b3  mov     edx, [rcx+2Ch]
0x1800370b6  test    dl, 1
0x1800370b9  jz      short loc_1800370E0
0x1800370bb  mov     rcx, [rcx+18h]
0x1800370bf  lea     r9, aStatus; "Status"
0x1800370c6  mov     [rsp+48h+var_18], 60Fh
0x1800370ce  mov     [rsp+48h+var_20], rdi
0x1800370d3  mov     [rsp+48h+var_28], 0C0000008h
0x1800370db  call    WPP_SF_sDsd
0x1800370e0  mov     rbx, [rsp+48h+arg_8]
0x1800370e5  mov     eax, 0C0000008h
0x1800370ea  add     rsp, 40h
0x1800370ee  pop     rdi
0x1800370ef  retn
0x1800370f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370f8  lea     rbx, WPP_GLOBAL_Control
0x1800370ff  cmp     rcx, rbx
0x180037102  jz      short loc_1800370A0
0x180037104  mov     eax, [rcx+2Ch]
0x180037107  test    al, 1
0x180037109  jz      short loc_1800370A0
0x18003710b  mov     rcx, [rcx+18h]
0x18003710f  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037116  mov     [rsp+48h+var_18], 14Bh
0x18003711e  lea     r9, aStatus; "Status"
0x180037125  mov     [rsp+48h+var_20], rdi
0x18003712a  mov     [rsp+48h+var_28], 0C0000008h
0x180037132  call    WPP_SF_sDsd
0x180037137  jmp     loc_1800370A7
0x18003713c  mov     rdx, rbx
0x18003713f  mov     ecx, 200h
0x180037144  call    cs:__imp_SkFreePool
0x18003714b  nop     dword ptr [rax+rax+00h]
0x180037150  jmp     loc_180036FFD
0x180037155  mov     rdx, rbx
0x180037158  mov     ecx, 200h
0x18003715d  call    cs:__imp_SkFreePool
0x180037164  nop     dword ptr [rax+rax+00h]
0x180037169  jmp     loc_18003706B
0x18003716e  mov     rcx, [rcx+18h]
0x180037172  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037179  mov     [rsp+48h+var_18], 154h
0x180037181  lea     r9, aStatus; "Status"
0x180037188  mov     [rsp+48h+var_20], rdi
0x18003718d  mov     [rsp+48h+var_28], 0C0000008h
0x180037195  call    WPP_SF_sDsd
0x18003719a  jmp     loc_1800370A7
0x18003719f  call    cs:__imp_SkIsSecureKernel
0x1800371a6  nop     dword ptr [rax+rax+00h]
0x1800371ab  sar     eax, 1Fh
0x1800371ae  add     eax, 2
0x1800371b1  mov     cs:g_TrustedEnvironment, eax
0x1800371b7  jmp     loc_180036FE1
0x1800371bc  call    cs:__imp_SkIsSecureKernel
0x1800371c3  nop     dword ptr [rax+rax+00h]
0x1800371c8  sar     eax, 1Fh
0x1800371cb  add     eax, 2
0x1800371ce  mov     cs:g_TrustedEnvironment, eax
0x1800371d4  jmp     loc_18003704F
```
