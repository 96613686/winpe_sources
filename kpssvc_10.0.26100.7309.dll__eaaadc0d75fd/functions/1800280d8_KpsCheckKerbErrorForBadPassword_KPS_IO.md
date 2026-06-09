# KpsCheckKerbErrorForBadPassword(_KPS_IO *)

- ea: `0x1800280d8`
- end: `0x1800284e3`
- name: `?KpsCheckKerbErrorForBadPassword@@YAKPEAU_KPS_IO@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(struct _KPS_IO *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028030`

## callees

- `0x18001ae38`
- `0x180026bc0`
- `0x180026d9c`
- `0x180027530`
- `0x1800276c8`
- `0x1800280d8`
- `0x180028dc0`
- `0x180028e1c`
- `0x18002a180`
- `0x18002a2b8`
- `0x18002a838`
- `0x18002b94c`
- `0x18002bf2c`
- `0x18002c074`
- `0x18002c3f4`
- `0x18002c534`
- `0x18002c5dc`
- `0x18002ffd8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180028328`
- `ntdll!RtlLeaveCriticalSection` at `0x180028328`
- `ntdll!RtlEnterCriticalSection` at `0x180028145`
- `ntdll!RtlEnterCriticalSection` at `0x180028145`

## string_xrefs

- `0x1800281bb`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsCheckKerbErrorForBadPassword(struct _KPS_IO *a1)
{
  unsigned int v1; // edi
  char v2; // r13
  char v3; // r12
  _QWORD *v5; // rcx
  __int64 v6; // r8
  _QWORD *v7; // rcx
  struct _KPS_DOMAIN_HASH_ENTRY *v8; // r15
  struct _KPS_USER_HASH_ENTRY *v9; // rax
  struct _KPS_USER_HASH_ENTRY *v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // r8
  _QWORD *v14; // rcx
  int v15; // eax
  unsigned __int128 v16; // rax
  __int64 v17; // rcx
  struct _KPS_USER_HASH_ENTRY *lpMem; // [rsp+80h] [rbp+8h] BYREF
  struct _KPS_DOMAIN_HASH_ENTRY *v19; // [rsp+88h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
    v5 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(*((_QWORD *)a1 + 31) + 52LL) == 24 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
    v19 = KpsLookupDomainHashEntry(qword_18003ACE8, (struct _UNICODE_STRING *)((char *)a1 + 168));
    if ( !v19 )
    {
      KpsSqmIncrement(1u);
      v1 = KpsAddDomainHashEntry(qword_18003ACE8, (struct _UNICODE_STRING *)((char *)a1 + 168), &v19);
      if ( v1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_ZDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v1,
            (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
            29);
LABEL_25:
        if ( v19 && !v2 )
          KpsDereferenceDomainHashEntry(v19);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
        v5 = WPP_GLOBAL_Control;
        goto LABEL_29;
      }
      v2 = 1;
      KpsRebalanceHashTable(qword_18003ACE8);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_qZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 168);
          v7 = WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
          WPP_SF_ddd(
            v7[2],
            115,
            v6,
            *((unsigned int *)qword_18003ACE8 + 6),
            *((_DWORD *)qword_18003ACE8 + 2),
            *((_DWORD *)qword_18003ACE8 + 5));
      }
    }
    v8 = v19;
    v9 = KpsLookupUserHashEntry(
           *((struct _RTL_DYNAMIC_HASH_TABLE **)v19 + 12),
           (struct _UNICODE_STRING *)((char *)a1 + 152),
           0);
    lpMem = v9;
    v10 = v9;
    if ( v9 )
    {
      v15 = *((_DWORD *)v9 + 12) + 1;
      *((_DWORD *)v10 + 12) = v15;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_qZZL(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 168, (__int64)a1 + 152, v15);
      if ( *((_DWORD *)v10 + 12) > (unsigned int)dword_18003A9B0 )
      {
        v1 = 1909;
        v10 = lpMem;
        v16 = ((unsigned __int64)MEMORY[0x7FFE0004] << 32)
            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8);
        v17 = *((_QWORD *)&v16 + 1) + (unsigned int)(60000 * dword_18003A9B4);
        *((_QWORD *)lpMem + 8) = v17;
        if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 0x10) != 0 )
          McTemplateU0zzqq_EventWriteTransfer(
            v17,
            DWORD2(v16),
            *((_QWORD *)a1 + 22),
            *((_QWORD *)a1 + 20),
            *((_DWORD *)v10 + 12),
            60 * dword_18003A9B4);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_ZZLD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 152, *((_DWORD *)v10 + 12));
      }
      goto LABEL_22;
    }
    KpsSqmIncrement(2u);
    v11 = KpsAddUserHashEntry(
            *((struct _RTL_DYNAMIC_HASH_TABLE **)v8 + 12),
            (struct _UNICODE_STRING *)((char *)a1 + 152),
            &lpMem);
    v1 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZZDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 168, v11);
    }
    else
    {
      v3 = 1;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v10 = lpMem;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_qZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 152);
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x40) != 0 )
          WPP_SF_ddd(
            v14[2],
            118,
            v12,
            *(unsigned int *)(*((_QWORD *)v8 + 12) + 24LL),
            *(_DWORD *)(*((_QWORD *)v8 + 12) + 8LL),
            *(_DWORD *)(*((_QWORD *)v8 + 12) + 20LL));
        goto LABEL_22;
      }
    }
    v10 = lpMem;
LABEL_22:
    if ( v10 && !v3 )
      KpsDereferenceUserHashEntry(v10);
    goto LABEL_25;
  }
LABEL_29:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_D(v5[2], 121, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800280d8  mov     [rsp+arg_10], rbx
0x1800280dd  push    rbp
0x1800280de  push    rsi
0x1800280df  push    rdi
0x1800280e0  push    r12
0x1800280e2  push    r13
0x1800280e4  push    r14
0x1800280e6  push    r15
0x1800280e8  sub     rsp, 40h
0x1800280ec  xor     edi, edi
0x1800280ee  xor     r13b, r13b
0x1800280f1  xor     r12b, r12b
0x1800280f4  mov     rsi, rcx
0x1800280f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280fe  lea     r15, WPP_GLOBAL_Control
0x180028105  cmp     rcx, r15
0x180028108  jz      short loc_18002812D
0x18002810a  test    byte ptr [rcx+1Ch], 20h
0x18002810e  jz      short loc_18002812D
0x180028110  mov     rcx, [rcx+10h]
0x180028114  lea     edx, [rdi+70h]
0x180028117  mov     r9, rsi
0x18002811a  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028121  call    WPP_SF_q
0x180028126  mov     rcx, cs:WPP_GLOBAL_Control
0x18002812d  mov     rax, [rsi+0F8h]
0x180028134  cmp     dword ptr [rax+34h], 18h
0x180028138  jnz     loc_18002833B
0x18002813e  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x180028145  call    cs:__imp_RtlEnterCriticalSection
0x18002814c  nop     dword ptr [rax+rax+00h]
0x180028151  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x180028158  lea     rbp, [rsi+0A8h]
0x18002815f  mov     rdx, rbp; struct _UNICODE_STRING *
0x180028162  call    ?KpsLookupDomainHashEntry@@YAPEAU_KPS_DOMAIN_HASH_ENTRY@@PEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@@Z; KpsLookupDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *)
0x180028167  mov     [rsp+78h+arg_8], rax
0x18002816f  test    rax, rax
0x180028172  jnz     loc_180028263
0x180028178  lea     ecx, [rax+1]; unsigned int
0x18002817b  call    ?KpsSqmIncrement@@YAXK@Z; KpsSqmIncrement(ulong)
0x180028180  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x180028187  lea     r8, [rsp+78h+arg_8]; struct _KPS_DOMAIN_HASH_ENTRY **
0x18002818f  mov     rdx, rbp; struct _UNICODE_STRING *
0x180028192  call    ?KpsAddDomainHashEntry@@YAKPEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@PEAPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsAddDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *,_KPS_DOMAIN_HASH_ENTRY * *)
0x180028197  mov     edi, eax
0x180028199  test    eax, eax
0x18002819b  jz      short loc_1800281EC
0x18002819d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281a4  cmp     rcx, r15
0x1800281a7  jz      loc_18002830A
0x1800281ad  test    byte ptr [rcx+1Ch], 1
0x1800281b1  jz      loc_18002830A
0x1800281b7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800281bb  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x1800281c2  mov     dword ptr [rsp+78h+var_48], 81Dh; char
0x1800281ca  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800281d1  mov     qword ptr [rsp+78h+var_50], rax; __int64
0x1800281d6  mov     edx, 71h ; 'q'
0x1800281db  mov     r9, rbp
0x1800281de  mov     dword ptr [rsp+78h+var_58], edi; char
0x1800281e2  call    WPP_SF_ZDsd
0x1800281e7  jmp     loc_18002830A
0x1800281ec  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x1800281f3  mov     r13b, 1
0x1800281f6  call    ?KpsRebalanceHashTable@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@@Z; KpsRebalanceHashTable(_RTL_DYNAMIC_HASH_TABLE *)
0x1800281fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028202  cmp     rcx, r15
0x180028205  jz      short loc_180028263
0x180028207  test    byte ptr [rcx+1Ch], 40h
0x18002820b  jz      short loc_18002822F
0x18002820d  mov     r9, [rsp+78h+arg_8]
0x180028215  mov     edx, 72h ; 'r'
0x18002821a  mov     rcx, [rcx+10h]; LoggerHandle
0x18002821e  mov     qword ptr [rsp+78h+var_58], rbp; __int64
0x180028223  call    WPP_SF_qZ
0x180028228  mov     rcx, cs:WPP_GLOBAL_Control
0x18002822f  cmp     rcx, r15
0x180028232  jz      short loc_180028263
0x180028234  test    byte ptr [rcx+1Ch], 40h
0x180028238  jz      short loc_180028263
0x18002823a  mov     r9, cs:qword_18003ACE8
0x180028241  mov     edx, 73h ; 's'
0x180028246  mov     rcx, [rcx+10h]
0x18002824a  mov     eax, [r9+14h]
0x18002824e  mov     dword ptr [rsp+78h+var_50], eax
0x180028252  mov     eax, [r9+8]
0x180028256  mov     r9d, [r9+18h]
0x18002825a  mov     dword ptr [rsp+78h+var_58], eax
0x18002825e  call    WPP_SF_ddd
0x180028263  mov     r15, [rsp+78h+arg_8]
0x18002826b  lea     r14, [rsi+98h]
0x180028272  xor     r8d, r8d; unsigned __int8
0x180028275  mov     rdx, r14; struct _UNICODE_STRING *
0x180028278  mov     rcx, [r15+60h]; struct _RTL_DYNAMIC_HASH_TABLE *
0x18002827c  call    ?KpsLookupUserHashEntry@@YAPEAU_KPS_USER_HASH_ENTRY@@PEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@E@Z; KpsLookupUserHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *,uchar)
0x180028281  mov     [rsp+78h+lpMem], rax
0x180028289  mov     rbx, rax
0x18002828c  test    rax, rax
0x18002828f  jnz     loc_1800283FC
0x180028295  lea     ecx, [rax+2]; unsigned int
0x180028298  call    ?KpsSqmIncrement@@YAXK@Z; KpsSqmIncrement(ulong)
0x18002829d  mov     rcx, [r15+60h]; struct _RTL_DYNAMIC_HASH_TABLE *
0x1800282a1  lea     r8, [rsp+78h+lpMem]; struct _KPS_USER_HASH_ENTRY **
0x1800282a9  mov     rdx, r14; struct _UNICODE_STRING *
0x1800282ac  call    ?KpsAddUserHashEntry@@YAKPEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@PEAPEAU_KPS_USER_HASH_ENTRY@@@Z; KpsAddUserHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *,_KPS_USER_HASH_ENTRY * *)
0x1800282b1  mov     edi, eax
0x1800282b3  test    eax, eax
0x1800282b5  jz      loc_180028379
0x1800282bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282c2  lea     rsi, WPP_GLOBAL_Control
0x1800282c9  cmp     rcx, rsi
0x1800282cc  jz      short loc_1800282E9
0x1800282ce  test    byte ptr [rcx+1Ch], 1
0x1800282d2  jz      short loc_1800282E9
0x1800282d4  mov     rcx, [rcx+10h]; LoggerHandle
0x1800282d8  mov     r9, r14
0x1800282db  mov     dword ptr [rsp+78h+var_50], eax; char
0x1800282df  mov     qword ptr [rsp+78h+var_58], rbp; __int64
0x1800282e4  call    WPP_SF_ZZDsd
0x1800282e9  mov     rbx, [rsp+78h+lpMem]
0x1800282f1  lea     r15, WPP_GLOBAL_Control
0x1800282f8  test    rbx, rbx
0x1800282fb  jz      short loc_18002830A
0x1800282fd  test    r12b, r12b
0x180028300  jnz     short loc_18002830A
0x180028302  mov     rcx, rbx; lpMem
0x180028305  call    ?KpsDereferenceUserHashEntry@@YAXPEAU_KPS_USER_HASH_ENTRY@@@Z; KpsDereferenceUserHashEntry(_KPS_USER_HASH_ENTRY *)
0x18002830a  mov     rcx, [rsp+78h+arg_8]; lpMem
0x180028312  test    rcx, rcx
0x180028315  jz      short loc_180028321
0x180028317  test    r13b, r13b
0x18002831a  jnz     short loc_180028321
0x18002831c  call    ?KpsDereferenceDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsDereferenceDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x180028321  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x180028328  call    cs:__imp_RtlLeaveCriticalSection
0x18002832f  nop     dword ptr [rax+rax+00h]
0x180028334  mov     rcx, cs:WPP_GLOBAL_Control
0x18002833b  cmp     rcx, r15
0x18002833e  jz      short loc_18002835E
0x180028340  test    byte ptr [rcx+1Ch], 20h
0x180028344  jz      short loc_18002835E
0x180028346  mov     rcx, [rcx+10h]
0x18002834a  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028351  mov     edx, 79h ; 'y'
0x180028356  mov     r9d, edi
0x180028359  call    WPP_SF_D
0x18002835e  mov     rbx, [rsp+78h+arg_10]
0x180028366  mov     eax, edi
0x180028368  add     rsp, 40h
0x18002836c  pop     r15
0x18002836e  pop     r14
0x180028370  pop     r13
0x180028372  pop     r12
0x180028374  pop     rdi
0x180028375  pop     rsi
0x180028376  pop     rbp
0x180028377  retn
0x180028379  mov     r12b, 1
0x18002837c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028383  lea     rsi, WPP_GLOBAL_Control
0x18002838a  cmp     rcx, rsi
0x18002838d  jz      loc_1800282E9
0x180028393  test    byte ptr [rcx+1Ch], 40h
0x180028397  mov     rbx, [rsp+78h+lpMem]
0x18002839f  jz      short loc_1800283BE
0x1800283a1  mov     rcx, [rcx+10h]; LoggerHandle
0x1800283a5  mov     edx, 75h ; 'u'
0x1800283aa  mov     r9, rbx
0x1800283ad  mov     qword ptr [rsp+78h+var_58], r14; __int64
0x1800283b2  call    WPP_SF_qZ
0x1800283b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283be  cmp     rcx, rsi
0x1800283c1  jz      loc_1800282F1
0x1800283c7  test    byte ptr [rcx+1Ch], 40h
0x1800283cb  jz      loc_1800282F1
0x1800283d1  mov     r9, [r15+60h]
0x1800283d5  mov     edx, 76h ; 'v'
0x1800283da  mov     rcx, [rcx+10h]
0x1800283de  mov     eax, [r9+14h]
0x1800283e2  mov     dword ptr [rsp+78h+var_50], eax
0x1800283e6  mov     eax, [r9+8]
0x1800283ea  mov     r9d, [r9+18h]
0x1800283ee  mov     dword ptr [rsp+78h+var_58], eax
0x1800283f2  call    WPP_SF_ddd
0x1800283f7  jmp     loc_1800282F1
0x1800283fc  mov     eax, [rax+30h]
0x1800283ff  inc     eax
0x180028401  mov     [rbx+30h], eax
0x180028404  mov     rcx, cs:WPP_GLOBAL_Control
0x18002840b  lea     r15, WPP_GLOBAL_Control
0x180028412  cmp     rcx, r15
0x180028415  jz      short loc_180028437
0x180028417  test    byte ptr [rcx+1Ch], 40h
0x18002841b  jz      short loc_180028437
0x18002841d  mov     rcx, [rcx+10h]; LoggerHandle
0x180028421  mov     r9, rbx
0x180028424  mov     dword ptr [rsp+78h+var_48], eax; char
0x180028428  mov     qword ptr [rsp+78h+var_50], r14; __int64
0x18002842d  mov     qword ptr [rsp+78h+var_58], rbp; __int64
0x180028432  call    WPP_SF_qZZL
0x180028437  mov     eax, cs:dword_18003A9B0
0x18002843d  cmp     [rbx+30h], eax
0x180028440  jbe     loc_1800282F8
0x180028446  mov     ecx, ds:7FFE0004h
0x18002844d  mov     eax, 7FFE0320h
0x180028452  shl     rcx, 20h
0x180028456  mov     edi, 775h
0x18002845b  mov     rax, [rax]
0x18002845e  mov     rbx, [rsp+78h+lpMem]
0x180028466  shl     rax, 8
0x18002846a  mul     rcx
0x18002846d  imul    ecx, cs:dword_18003A9B4, 0EA60h
0x180028477  add     rcx, rdx
0x18002847a  mov     [rbx+40h], rcx
0x18002847e  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 10h
0x180028485  jz      short loc_1800284AC
0x180028487  imul    eax, cs:dword_18003A9B4, 3Ch ; '<'
0x18002848e  mov     r9, [rsi+0A0h]
0x180028495  mov     r8, [rsi+0B0h]
0x18002849c  mov     dword ptr [rsp+78h+var_50], eax
0x1800284a0  mov     eax, [rbx+30h]
0x1800284a3  mov     dword ptr [rsp+78h+var_58], eax
0x1800284a7  call    McTemplateU0zzqq_EventWriteTransfer
0x1800284ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284b3  cmp     rcx, r15
0x1800284b6  jz      loc_1800282F8
0x1800284bc  test    byte ptr [rcx+1Ch], 10h
0x1800284c0  jz      loc_1800282F8
0x1800284c6  mov     eax, [rbx+30h]
0x1800284c9  mov     r9, rbp
0x1800284cc  mov     rcx, [rcx+10h]; LoggerHandle
0x1800284d0  mov     dword ptr [rsp+78h+var_50], eax; char
0x1800284d4  mov     qword ptr [rsp+78h+var_58], r14; __int64
0x1800284d9  call    WPP_SF_ZZLD
0x1800284de  jmp     loc_1800282F8
```
