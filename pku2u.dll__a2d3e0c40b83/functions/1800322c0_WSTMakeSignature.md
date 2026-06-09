# WSTMakeSignature

- ea: `0x1800322c0`
- end: `0x180032655`
- name: `WSTMakeSignature`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024460`

## callees

- `0x18001b2b8`
- `0x1800210f0`
- `0x180023cb8`
- `0x180023d9c`
- `0x18002b408`
- `0x18002b744`
- `0x1800322c0`
- `0x18003265c`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x1800324e5`
- `cryptdll!CDLocateCSystem` at `0x1800324e5`
- `cryptdll!CDLocateCheckSum` at `0x18003248f`
- `cryptdll!CDLocateCheckSum` at `0x18003248f`

## string_xrefs

- `0x1800323b2`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x180032401`: `onecore\ds\security\protocols\pku2u\message.cxx`

## pseudocode

```c
__int64 __fastcall WSTMakeSignature(__int64 a1, int a2, __int64 a3, char a4)
{
  __int64 v4; // rdi
  unsigned int v7; // edx
  int v10; // eax
  int v11; // ebx
  int v12; // r9d
  int v13; // edx
  int v14; // r9d
  _QWORD *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  unsigned int i; // edi
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdi
  int v22; // eax
  __int64 v24; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v26; // [rsp+5Ch] [rbp-3Dh] BYREF
  __int64 v27; // [rsp+60h] [rbp-39h] BYREF
  __int64 v28; // [rsp+68h] [rbp-31h] BYREF
  __int64 v29; // [rsp+70h] [rbp-29h] BYREF
  __int64 v30; // [rsp+78h] [rbp-21h] BYREF
  __int64 v31; // [rsp+80h] [rbp-19h] BYREF
  int v32; // [rsp+88h] [rbp-11h]

  v4 = 0;
  v24 = 0;
  v28 = 0;
  v7 = 0;
  v25 = 0;
  v26 = 0;
  v29 = 0;
  v27 = 0;
  v30 = 0;
  while ( v7 < *(_DWORD *)(a3 + 4) )
  {
    v10 = *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * v7 + 4);
    if ( v10 < 0 && (v10 & 0x10000000) != 0 )
    {
      v11 = -2146893048;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v11;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
      goto LABEL_44;
    }
    if ( (v10 & 0xFFFFFFF) == 2 )
      v4 = *(_QWORD *)(a3 + 8) + 16LL * v7;
    ++v7;
  }
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        72);
    v11 = -1073741811;
    goto LABEL_44;
  }
  v12 = *(_DWORD *)(a1 + 84);
  if ( (v12 & 0x1000C) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
        v12,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        83);
    v11 = -1073741637;
    goto LABEL_44;
  }
  v11 = WSTGetChecksumAndEncryptionType(a1, 0, a2, (unsigned int)&v25, (__int64)&v26);
  if ( v11 < 0 )
    return (unsigned int)v11;
  v11 = WSTMakeSignatureToken(a1, a2, v4, v14, v13, a4, v13, (__int64)&v28, (__int64)&v29);
  if ( v11 < 0 )
    goto LABEL_44;
  v11 = CDLocateCheckSum(v25, &v27);
  if ( v11 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v16 = v25;
    v17 = 26;
LABEL_27:
    WPP_SF_dd(v15[2], v17, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, v16, v11);
    goto LABEL_44;
  }
  v11 = CDLocateCSystem(v26, &v30);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v27 + 48))(
            *(_QWORD *)(a1 + 56),
            *(unsigned int *)(a1 + 48),
            (*(_DWORD *)(a1 + 80) & 2) != 0 ? 25 : 23,
            &v24);
    if ( v11 >= 0 )
    {
      for ( i = 0; i < *(_DWORD *)(a3 + 4); ++i )
      {
        v19 = *(_QWORD *)(a3 + 8);
        if ( (*(_DWORD *)(v19 + 16LL * i + 4) & 0xFFFFFFF) != 2 && *(int *)(v19 + 16LL * i + 4) >= 0 )
        {
          v20 = *(unsigned int *)(v19 + 16LL * i);
          if ( (_DWORD)v20 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(v27 + 24))(
                    v24,
                    v20,
                    *(_QWORD *)(v19 + 16LL * i + 8));
            if ( v11 < 0 )
              goto LABEL_44;
          }
        }
      }
      v21 = v28;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v27 + 24))(v24, 16, v28 - 2);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v27 + 32))(v24, &v31);
        if ( v11 >= 0 )
        {
          v22 = (*(__int64 (__fastcall **)(__int64 *))(v27 + 40))(&v24);
          v24 = 0;
          v11 = v22;
          if ( v22 < 0 )
            return (unsigned int)v11;
          *(_QWORD *)(v21 + 14) = v31;
          *(_DWORD *)(v21 + 22) = v32;
        }
      }
    }
    goto LABEL_44;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = v26;
    v17 = 27;
    goto LABEL_27;
  }
LABEL_44:
  if ( v24 && v27 )
    (*(void (__fastcall **)(__int64 *))(v27 + 40))(&v24);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800322c0  mov     [rsp-8+arg_8], rbx
0x1800322c5  mov     [rsp-8+arg_18], rsi
0x1800322ca  push    rbp
0x1800322cb  push    rdi
0x1800322cc  push    r12
0x1800322ce  push    r14
0x1800322d0  push    r15
0x1800322d2  lea     rbp, [rsp-37h]
0x1800322d7  sub     rsp, 0D0h
0x1800322de  mov     rax, cs:__security_cookie
0x1800322e5  xor     rax, rsp
0x1800322e8  mov     [rbp+57h+var_30], rax
0x1800322ec  xor     edi, edi
0x1800322ee  mov     r12d, r9d
0x1800322f1  mov     r15d, edx
0x1800322f4  mov     [rbp+57h+var_A0], rdi
0x1800322f8  mov     [rbp+57h+var_88], rdi
0x1800322fc  xor     edx, edx
0x1800322fe  mov     [rbp+57h+var_98], edi
0x180032301  mov     r14, r8
0x180032304  mov     [rbp+57h+var_94], edi
0x180032307  mov     rsi, rcx
0x18003230a  mov     [rbp+57h+var_80], rdi
0x18003230e  mov     [rbp+57h+var_90], 0
0x180032316  mov     [rbp+57h+var_78], 0
0x18003231e  cmp     edx, [r14+4]
0x180032322  jnb     short loc_18003238D
0x180032324  mov     r8d, edx
0x180032327  shl     r8, 4
0x18003232b  add     r8, [r14+8]
0x18003232f  mov     eax, [r8+4]
0x180032333  test    eax, eax
0x180032335  jns     short loc_18003233D
0x180032337  bt      eax, 1Ch
0x18003233b  jb      short loc_18003234D
0x18003233d  and     eax, 0FFFFFFFh
0x180032342  cmp     eax, 2
0x180032345  cmovz   rdi, r8
0x180032349  inc     edx
0x18003234b  jmp     short loc_18003231E
0x18003234d  mov     ebx, 80090308h
0x180032352  mov     rcx, cs:WPP_GLOBAL_Control
0x180032359  lea     rax, WPP_GLOBAL_Control
0x180032360  cmp     rcx, rax
0x180032363  jz      loc_18003262B
0x180032369  test    byte ptr [rcx+1Ch], 1
0x18003236d  jz      loc_18003262B
0x180032373  mov     rcx, [rcx+10h]
0x180032377  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x18003237e  mov     edx, 17h
0x180032383  call    WPP_SF_
0x180032388  jmp     loc_18003260E
0x18003238d  test    rdi, rdi
0x180032390  jnz     short loc_1800323D7
0x180032392  mov     rcx, cs:WPP_GLOBAL_Control
0x180032399  lea     rax, WPP_GLOBAL_Control
0x1800323a0  cmp     rcx, rax
0x1800323a3  jz      short loc_1800323CD
0x1800323a5  test    byte ptr [rcx+1Ch], 1
0x1800323a9  jz      short loc_1800323CD
0x1800323ab  mov     rcx, [rcx+10h]
0x1800323af  lea     edx, [rdi+18h]
0x1800323b2  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x1800323b9  mov     dword ptr [rsp+0F0h+var_D0], 248h
0x1800323c1  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800323c8  call    WPP_SF_sd
0x1800323cd  mov     ebx, 0C000000Dh
0x1800323d2  jmp     loc_18003260E
0x1800323d7  mov     r9d, [rcx+54h]
0x1800323db  test    r9d, 1000Ch
0x1800323e2  jnz     short loc_180032430
0x1800323e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800323eb  lea     rax, WPP_GLOBAL_Control
0x1800323f2  cmp     rcx, rax
0x1800323f5  jz      short loc_180032426
0x1800323f7  test    byte ptr [rcx+1Ch], 1
0x1800323fb  jz      short loc_180032426
0x1800323fd  mov     rcx, [rcx+10h]
0x180032401  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x180032408  mov     edx, 19h
0x18003240d  mov     dword ptr [rsp+0F0h+var_C8], 253h
0x180032415  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x18003241c  mov     [rsp+0F0h+var_D0], rax
0x180032421  call    WPP_SF_dsd
0x180032426  mov     ebx, 0C00000BBh
0x18003242b  jmp     loc_18003260E
0x180032430  lea     rax, [rbp+57h+var_94]
0x180032434  mov     r8d, r15d
0x180032437  lea     r9, [rbp+57h+var_98]
0x18003243b  mov     [rsp+0F0h+var_D0], rax
0x180032440  xor     edx, edx
0x180032442  call    WSTGetChecksumAndEncryptionType
0x180032447  mov     ebx, eax
0x180032449  test    eax, eax
0x18003244b  js      loc_18003262B
0x180032451  lea     rcx, [rbp+57h+var_80]
0x180032455  mov     r8, rdi
0x180032458  mov     [rsp+0F0h+var_B0], rcx
0x18003245d  lea     rcx, [rbp+57h+var_88]
0x180032461  mov     [rsp+0F0h+var_B8], rcx
0x180032466  mov     rcx, rsi
0x180032469  mov     [rsp+0F0h+var_C0], edx
0x18003246d  mov     [rsp+0F0h+var_C8], r12
0x180032472  mov     byte ptr [rsp+0F0h+var_D0], dl
0x180032476  mov     edx, r15d
0x180032479  call    WSTMakeSignatureToken
0x18003247e  mov     ebx, eax
0x180032480  test    eax, eax
0x180032482  js      loc_18003260E
0x180032488  mov     ecx, [rbp+57h+var_98]
0x18003248b  lea     rdx, [rbp+57h+var_90]
0x18003248f  call    cs:__imp_CDLocateCheckSum
0x180032495  mov     ebx, eax
0x180032497  test    eax, eax
0x180032499  jns     short loc_1800324DE
0x18003249b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324a2  lea     rax, WPP_GLOBAL_Control
0x1800324a9  cmp     rcx, rax
0x1800324ac  jz      loc_18003260E
0x1800324b2  test    byte ptr [rcx+1Ch], 1
0x1800324b6  jz      loc_18003260E
0x1800324bc  mov     r9d, [rbp+57h+var_98]
0x1800324c0  mov     edx, 1Ah
0x1800324c5  mov     rcx, [rcx+10h]
0x1800324c9  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800324d0  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x1800324d4  call    WPP_SF_dd
0x1800324d9  jmp     loc_18003260E
0x1800324de  mov     ecx, [rbp+57h+var_94]
0x1800324e1  lea     rdx, [rbp+57h+var_78]
0x1800324e5  call    cs:__imp_CDLocateCSystem
0x1800324eb  mov     ebx, eax
0x1800324ed  test    eax, eax
0x1800324ef  jns     short loc_18003251D
0x1800324f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324f8  lea     rax, WPP_GLOBAL_Control
0x1800324ff  cmp     rcx, rax
0x180032502  jz      loc_18003260E
0x180032508  test    byte ptr [rcx+1Ch], 1
0x18003250c  jz      loc_18003260E
0x180032512  mov     r9d, [rbp+57h+var_94]
0x180032516  mov     edx, 1Bh
0x18003251b  jmp     short loc_1800324C5
0x18003251d  mov     eax, [rsi+50h]
0x180032520  lea     r9, [rbp+57h+var_A0]
0x180032524  mov     edx, [rsi+30h]
0x180032527  and     al, 2
0x180032529  mov     rcx, [rsi+38h]
0x18003252d  neg     al
0x18003252f  mov     rax, [rbp+57h+var_90]
0x180032533  sbb     r8d, r8d
0x180032536  and     r8d, 2
0x18003253a  add     r8d, 17h
0x18003253e  mov     rax, [rax+30h]
0x180032542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032547  mov     ebx, eax
0x180032549  test    eax, eax
0x18003254b  js      loc_18003260E
0x180032551  xor     edi, edi
0x180032553  cmp     edi, [r14+4]
0x180032557  jnb     short loc_1800325A0
0x180032559  mov     rcx, [r14+8]
0x18003255d  mov     r8d, edi
0x180032560  add     r8, r8
0x180032563  mov     edx, [rcx+r8*8+4]
0x180032568  mov     eax, edx
0x18003256a  and     eax, 0FFFFFFFh
0x18003256f  cmp     eax, 2
0x180032572  jz      short loc_18003259C
0x180032574  test    edx, edx
0x180032576  js      short loc_18003259C
0x180032578  mov     edx, [rcx+r8*8]
0x18003257c  test    edx, edx
0x18003257e  jz      short loc_18003259C
0x180032580  mov     rax, [rbp+57h+var_90]
0x180032584  mov     r8, [rcx+r8*8+8]
0x180032589  mov     rcx, [rbp+57h+var_A0]
0x18003258d  mov     rax, [rax+18h]
0x180032591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032596  mov     ebx, eax
0x180032598  test    eax, eax
0x18003259a  js      short loc_18003260E
0x18003259c  inc     edi
0x18003259e  jmp     short loc_180032553
0x1800325a0  mov     rax, [rbp+57h+var_90]
0x1800325a4  mov     edx, 10h
0x1800325a9  mov     rdi, [rbp+57h+var_88]
0x1800325ad  mov     rcx, [rbp+57h+var_A0]
0x1800325b1  mov     rax, [rax+18h]
0x1800325b5  lea     r8, [rdi-2]
0x1800325b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325be  mov     ebx, eax
0x1800325c0  test    eax, eax
0x1800325c2  js      short loc_18003260E
0x1800325c4  mov     rax, [rbp+57h+var_90]
0x1800325c8  lea     rdx, [rbp+57h+var_70]
0x1800325cc  mov     rcx, [rbp+57h+var_A0]
0x1800325d0  mov     rax, [rax+20h]
0x1800325d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325d9  mov     ebx, eax
0x1800325db  test    eax, eax
0x1800325dd  js      short loc_18003260E
0x1800325df  mov     rax, [rbp+57h+var_90]
0x1800325e3  lea     rcx, [rbp+57h+var_A0]
0x1800325e7  mov     rax, [rax+28h]
0x1800325eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325f0  mov     [rbp+57h+var_A0], 0
0x1800325f8  mov     ebx, eax
0x1800325fa  test    eax, eax
0x1800325fc  js      short loc_18003262B
0x1800325fe  movsd   xmm0, [rbp+57h+var_70]
0x180032603  movsd   qword ptr [rdi+0Eh], xmm0
0x180032608  mov     eax, [rbp+57h+var_68]
0x18003260b  mov     [rdi+16h], eax
0x18003260e  cmp     [rbp+57h+var_A0], 0
0x180032613  jz      short loc_18003262B
0x180032615  mov     rax, [rbp+57h+var_90]
0x180032619  test    rax, rax
0x18003261c  jz      short loc_18003262B
0x18003261e  mov     rax, [rax+28h]
0x180032622  lea     rcx, [rbp+57h+var_A0]
0x180032626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003262b  mov     eax, ebx
0x18003262d  mov     rcx, [rbp+57h+var_30]
0x180032631  xor     rcx, rsp; StackCookie
0x180032634  call    __security_check_cookie
0x180032639  lea     r11, [rsp+0F0h+var_20]
0x180032641  mov     rbx, [r11+38h]
0x180032645  mov     rsi, [r11+48h]
0x180032649  mov     rsp, r11
0x18003264c  pop     r15
0x18003264e  pop     r14
0x180032650  pop     r12
0x180032652  pop     rdi
0x180032653  pop     rbp
0x180032654  retn
```
