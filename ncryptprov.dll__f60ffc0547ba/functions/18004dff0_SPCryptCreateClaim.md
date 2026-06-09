# SPCryptCreateClaim

- ea: `0x18004dff0`
- end: `0x18004e569`
- name: `SPCryptCreateClaim`
- size: `1401`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004400`
- `0x180009440`
- `0x18000af80`
- `0x180014160`
- `0x18001a564`
- `0x18001f0a4`
- `0x1800245d0`
- `0x1800248ac`
- `0x180028a70`
- `0x180035c9c`
- `0x180040cc8`
- `0x18004db44`
- `0x18004dff0`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18004e2fd`
- `ntdll!RtlDllShutdownInProgress` at `0x18004e2fd`

## string_xrefs

- `0x18004e0f2`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004e121`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004e16e`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004e075`: `SPCryptCreateClaim`
- `0x18004e0af`: `SPCryptCreateClaim`
- `0x18004e431`: `SPCryptCreateClaim`

## pseudocode

```c
__int64 __fastcall SPCryptCreateClaim(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        unsigned int a9)
{
  int v9; // edi
  int started; // eax
  int v14; // r12d
  __int64 v15; // r15
  int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdi
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // eax
  int v27; // ecx
  PVOID *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  bool v31; // zf
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int64 *v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 *v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  __int64 *v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+E8h] [rbp-18h]
  __int64 *v52; // [rsp+F0h] [rbp-10h]
  __int64 v53; // [rsp+F8h] [rbp-8h]
  __int64 *v54; // [rsp+100h] [rbp+0h]
  __int64 v55; // [rsp+108h] [rbp+8h]

  v39 = a5;
  v9 = a4;
  v38 = a6;
  v37 = a8;
  LODWORD(v36) = a4;
  v41 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids,
      "SPCryptCreateClaim");
  started = StartPerfMeasure(&v41);
  v14 = started;
  if ( started < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids,
      (unsigned int)"SPCryptCreateClaim",
      started);
  v15 = KspValidateKeyHandle(a2);
  if ( v15 )
  {
    v21 = 0;
    if ( a3 )
    {
      v21 = KspValidateKeyHandle(a3);
      if ( !v21 )
      {
        v16 = -2146893786;
        DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 8692);
        v9 = v36;
        goto LABEL_32;
      }
    }
    v22 = KspCheckStrongKeyAndUnprotect(v15, a9);
    v16 = v22;
    if ( v22 >= 0 )
    {
      if ( v21 && (v22 = KspCheckStrongKeyAndUnprotect(v21, a9), v16 = v22, v22 < 0) )
      {
        v23 = 8717;
      }
      else
      {
        if ( !*(_QWORD *)(*(_QWORD *)(v15 + 168) + 168LL) )
        {
          v16 = -2146893783;
          v23 = 8725;
          v24 = 2148073513LL;
          goto LABEL_17;
        }
        if ( !a3 || (v22 = KspCheckAttestationProperty(a1, a3), (v16 = v22) == 0) )
        {
          if ( v21 )
            v25 = *(_QWORD *)(v21 + 112);
          else
            v25 = 0;
          v9 = v36;
          v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, __int64, int, __int64, unsigned int))(*(_QWORD *)(v15 + 168) + 168LL))(
                  *(_QWORD *)(v15 + 112),
                  v25,
                  (unsigned int)v36,
                  v39,
                  v38,
                  a7,
                  v37,
                  a9);
          v16 = v26;
          if ( !v26 )
          {
            v16 = 0;
            goto LABEL_32;
          }
          v17 = 8758;
          v18 = v26;
          goto LABEL_10;
        }
        v23 = 8737;
      }
    }
    else
    {
      v23 = 8706;
    }
    v24 = (unsigned int)v22;
LABEL_17:
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v23);
    v9 = v36;
    goto LABEL_32;
  }
  v16 = -2146893786;
  v17 = 8681;
  v18 = 2148073510LL;
LABEL_10:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v17);
LABEL_32:
  if ( (unsigned int)dword_180079068 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180079068, 0x800000000000LL, v19, v20) )
  {
    v39 = 1;
    v45 = 8;
    v44 = &v39;
    v38 = 0x1000000;
    v46 = &v38;
    v47 = 8;
    v48 = &v36;
    LODWORD(v36) = v16;
    v50 = &v37;
    v49 = 4;
    LODWORD(v37) = v9;
    v51 = 4;
    tlgWriteAgg(v27, (int)&byte_180070897, 0, 6, &v43);
  }
  if ( !RtlDllShutdownInProgress()
    && dword_1800790F0
    && (unsigned __int8)tlgKeywordOn(&dword_1800790F0, 0x800000000000LL, v29, v30) )
  {
    v39 = 0;
    v44 = &v39;
    v45 = 8;
    v46 = &v38;
    v48 = &v36;
    v38 = 1;
    v47 = 8;
    v36 = 0;
    v49 = 8;
    LODWORD(v37) = BCryptIsoGetKGRunningInProdMode(&g_VbsRegistryData);
    v51 = 4;
    v50 = &v37;
    v40 = 2048;
    v52 = &v40;
    v53 = 8;
    tlgWriteAgg((int)&dword_1800790F0, (int)&word_180070802, 0, 7, &v43);
  }
  if ( v14 < 0 )
    goto LABEL_48;
  v31 = v16 == 0;
  if ( v16 >= 0 )
  {
    v37 = 0;
    v32 = EndPerfMeasure(v41, &v37);
    if ( v32 >= 0 )
    {
      if ( dword_180079068 && (unsigned __int8)tlgKeywordOn(&dword_180079068, 0x400000000000LL, v33, v34) )
      {
        v40 = 1;
        v44 = &v40;
        v39 = v37;
        v38 = v37;
        v36 = v37;
        v50 = &v36;
        v52 = &v37;
        v46 = &v39;
        v54 = &v42;
        v48 = &v38;
        v45 = 8;
        v47 = 8;
        v49 = 8;
        v51 = 8;
        LODWORD(v37) = v9;
        v53 = 4;
        v42 = 50331648;
        v55 = 8;
        tlgWriteAgg((int)&dword_180079068, (int)&byte_180070547, 0, 8, &v43);
      }
    }
    else
    {
      v28 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids,
          (unsigned int)"SPCryptCreateClaim",
          v32);
    }
LABEL_48:
    v31 = v16 == 0;
  }
  if ( !v31 && v16 != -2146893778 )
    KspCryptAuditCryptOperation(0, (_DWORD)v28, v15, 2502, v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18004dff0  push    rbp
0x18004dff2  push    rbx
0x18004dff3  push    rsi
0x18004dff4  push    rdi
0x18004dff5  push    r12
0x18004dff7  push    r13
0x18004dff9  push    r14
0x18004dffb  push    r15
0x18004dffd  lea     rbp, [rsp-28h]
0x18004e002  sub     rsp, 128h
0x18004e009  mov     rax, cs:__security_cookie
0x18004e010  xor     rax, rsp
0x18004e013  mov     [rbp+60h+var_50], rax
0x18004e017  mov     rax, [rbp+60h+arg_20]
0x18004e01e  xor     r14d, r14d
0x18004e021  mov     [rsp+160h+var_F8], rax
0x18004e026  mov     edi, r9d
0x18004e029  mov     rax, [rbp+60h+arg_28]
0x18004e030  mov     rsi, r8
0x18004e033  mov     [rsp+160h+var_100], rax
0x18004e038  mov     rbx, rdx
0x18004e03b  mov     rax, [rbp+60h+arg_38]
0x18004e042  mov     r13, rcx
0x18004e045  mov     [rsp+160h+var_108], rax
0x18004e04a  mov     dword ptr [rsp+160h+var_110], r9d
0x18004e04f  mov     [rsp+160h+var_E8], r14
0x18004e054  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e05b  lea     r15, WPP_GLOBAL_Control
0x18004e062  cmp     rcx, r15
0x18004e065  jz      short loc_18004E088
0x18004e067  test    byte ptr [rcx+1Ch], 8
0x18004e06b  jz      short loc_18004E088
0x18004e06d  mov     rcx, [rcx+10h]
0x18004e071  lea     edx, [r14+1Dh]
0x18004e075  lea     r9, aSpcryptcreatec; "SPCryptCreateClaim"
0x18004e07c  lea     r8, WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids
0x18004e083  call    WPP_SF_s
0x18004e088  lea     rcx, [rsp+160h+var_E8]
0x18004e08d  call    StartPerfMeasure
0x18004e092  mov     r12d, eax
0x18004e095  test    eax, eax
0x18004e097  jns     short loc_18004E0CB
0x18004e099  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e0a0  cmp     rcx, r15
0x18004e0a3  jz      short loc_18004E0CB
0x18004e0a5  test    byte ptr [rcx+1Ch], 1
0x18004e0a9  jz      short loc_18004E0CB
0x18004e0ab  mov     rcx, [rcx+10h]
0x18004e0af  lea     r9, aSpcryptcreatec; "SPCryptCreateClaim"
0x18004e0b6  mov     edx, 1Eh
0x18004e0bb  mov     dword ptr [rsp+160h+var_140], eax
0x18004e0bf  lea     r8, WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids
0x18004e0c6  call    WPP_SF_sD
0x18004e0cb  mov     rcx, rbx
0x18004e0ce  call    KspValidateKeyHandle
0x18004e0d3  mov     r15, rax
0x18004e0d6  test    rax, rax
0x18004e0d9  jnz     short loc_18004E103
0x18004e0db  mov     ebx, 80090026h
0x18004e0e0  mov     r9d, 21E9h
0x18004e0e6  mov     ecx, 80090026h
0x18004e0eb  lea     rdx, aStatus; "Status"
0x18004e0f2  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004e0f9  call    DebugTraceError
0x18004e0fe  jmp     loc_18004E251
0x18004e103  mov     rdi, r14
0x18004e106  test    rsi, rsi
0x18004e109  jz      short loc_18004E147
0x18004e10b  mov     rcx, rsi
0x18004e10e  call    KspValidateKeyHandle
0x18004e113  mov     rdi, rax
0x18004e116  test    rax, rax
0x18004e119  jnz     short loc_18004E147
0x18004e11b  mov     r9d, 21F4h
0x18004e121  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004e128  lea     rdx, aStatus; "Status"
0x18004e12f  mov     ecx, 80090026h
0x18004e134  mov     ebx, 80090026h
0x18004e139  call    DebugTraceError
0x18004e13e  mov     edi, dword ptr [rsp+160h+var_110]
0x18004e142  jmp     loc_18004E251
0x18004e147  mov     r14d, [rbp+60h+arg_40]
0x18004e14e  mov     rcx, r15
0x18004e151  mov     edx, r14d
0x18004e154  call    KspCheckStrongKeyAndUnprotect
0x18004e159  mov     ebx, eax
0x18004e15b  test    eax, eax
0x18004e15d  jns     short loc_18004E186
0x18004e15f  mov     r9d, 2202h
0x18004e165  mov     ecx, eax
0x18004e167  lea     rdx, aStatus; "Status"
0x18004e16e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004e175  call    DebugTraceError
0x18004e17a  mov     edi, dword ptr [rsp+160h+var_110]
0x18004e17e  xor     r14d, r14d
0x18004e181  jmp     loc_18004E251
0x18004e186  test    rdi, rdi
0x18004e189  jz      short loc_18004E1A4
0x18004e18b  mov     edx, r14d
0x18004e18e  mov     rcx, rdi
0x18004e191  call    KspCheckStrongKeyAndUnprotect
0x18004e196  mov     ebx, eax
0x18004e198  test    eax, eax
0x18004e19a  jns     short loc_18004E1A4
0x18004e19c  mov     r9d, 220Dh
0x18004e1a2  jmp     short loc_18004E165
0x18004e1a4  mov     rax, [r15+0A8h]
0x18004e1ab  cmp     qword ptr [rax+0A8h], 0
0x18004e1b3  jnz     short loc_18004E1C7
0x18004e1b5  mov     ebx, 80090029h
0x18004e1ba  mov     r9d, 2215h
0x18004e1c0  mov     ecx, 80090029h
0x18004e1c5  jmp     short loc_18004E167
0x18004e1c7  test    rsi, rsi
0x18004e1ca  jz      short loc_18004E1E5
0x18004e1cc  mov     rdx, rsi
0x18004e1cf  mov     rcx, r13
0x18004e1d2  call    KspCheckAttestationProperty
0x18004e1d7  mov     ebx, eax
0x18004e1d9  test    eax, eax
0x18004e1db  jz      short loc_18004E1E5
0x18004e1dd  mov     r9d, 2221h
0x18004e1e3  jmp     short loc_18004E165
0x18004e1e5  test    rdi, rdi
0x18004e1e8  jz      short loc_18004E1F0
0x18004e1ea  mov     rdx, [rdi+70h]
0x18004e1ee  jmp     short loc_18004E1F2
0x18004e1f0  xor     edx, edx
0x18004e1f2  mov     rcx, [rsp+160h+var_108]
0x18004e1f7  mov     rax, [r15+0A8h]
0x18004e1fe  mov     edi, dword ptr [rsp+160h+var_110]
0x18004e202  mov     r8d, edi
0x18004e205  mov     r9, [rsp+160h+var_F8]
0x18004e20a  mov     [rsp+160h+var_128], r14d
0x18004e20f  mov     rax, [rax+0A8h]
0x18004e216  mov     [rsp+160h+var_130], rcx
0x18004e21b  mov     ecx, [rbp+60h+arg_30]
0x18004e221  mov     [rsp+160h+var_138], ecx
0x18004e225  mov     rcx, [rsp+160h+var_100]
0x18004e22a  mov     [rsp+160h+var_140], rcx
0x18004e22f  mov     rcx, [r15+70h]
0x18004e233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e238  xor     r14d, r14d
0x18004e23b  mov     ebx, eax
0x18004e23d  test    eax, eax
0x18004e23f  jz      short loc_18004E24E
0x18004e241  mov     r9d, 2236h
0x18004e247  mov     ecx, eax
0x18004e249  jmp     loc_18004E0EB
0x18004e24e  mov     ebx, r14d
0x18004e251  mov     eax, cs:dword_180079068
0x18004e257  lea     rsi, dword_180079068
0x18004e25e  cmp     eax, 5
0x18004e261  jbe     loc_18004E2F7
0x18004e267  mov     rdx, 800000000000h
0x18004e271  mov     rcx, rsi
0x18004e274  call    _tlgKeywordOn
0x18004e279  test    al, al
0x18004e27b  jz      short loc_18004E2F7
0x18004e27d  mov     r13d, 8
0x18004e283  mov     [rsp+160h+var_F8], 1
0x18004e28c  lea     rax, [rsp+160h+var_F8]
0x18004e291  mov     [rbp+60h+var_A8], r13
0x18004e295  mov     [rbp+60h+var_B0], rax
0x18004e299  lea     rdx, byte_180070897; int
0x18004e2a0  lea     rax, [rsp+160h+var_100]
0x18004e2a5  mov     [rsp+160h+var_100], 1000000h
0x18004e2ae  mov     [rbp+60h+var_A0], rax
0x18004e2b2  lea     r9d, [r13-2]; int
0x18004e2b6  lea     rax, [rsp+160h+var_110]
0x18004e2bb  mov     [rbp+60h+var_98], r13
0x18004e2bf  mov     [rbp+60h+var_90], rax
0x18004e2c3  xor     r8d, r8d; int
0x18004e2c6  lea     rax, [rsp+160h+var_108]
0x18004e2cb  mov     dword ptr [rsp+160h+var_110], ebx
0x18004e2cf  mov     [rbp+60h+var_80], rax
0x18004e2d3  lea     rax, [rbp+60h+var_D0]
0x18004e2d7  mov     [rsp+160h+var_140], rax; PEVENT_DATA_DESCRIPTOR
0x18004e2dc  mov     [rbp+60h+var_88], 4
0x18004e2e4  mov     dword ptr [rsp+160h+var_108], edi
0x18004e2e8  mov     [rbp+60h+var_78], 4
0x18004e2f0  call    _tlgWriteAgg
0x18004e2f5  jmp     short loc_18004E2FD
0x18004e2f7  mov     r13d, 8
0x18004e2fd  call    cs:__imp_RtlDllShutdownInProgress
0x18004e304  nop     dword ptr [rax+rax+00h]
0x18004e309  test    al, al
0x18004e30b  jnz     loc_18004E3E3
0x18004e311  mov     eax, cs:dword_1800790F0
0x18004e317  test    eax, eax
0x18004e319  jz      loc_18004E3E3
0x18004e31f  mov     rdx, 800000000000h
0x18004e329  lea     rcx, dword_1800790F0
0x18004e330  call    _tlgKeywordOn
0x18004e335  test    al, al
0x18004e337  jz      loc_18004E3E3
0x18004e33d  lea     rax, [rsp+160h+var_F8]
0x18004e342  mov     [rsp+160h+var_F8], r14
0x18004e347  mov     [rbp+60h+var_B0], rax
0x18004e34b  lea     rcx, g_VbsRegistryData
0x18004e352  lea     rax, [rsp+160h+var_100]
0x18004e357  mov     [rbp+60h+var_A8], 8
0x18004e35f  mov     [rbp+60h+var_A0], rax
0x18004e363  lea     rax, [rsp+160h+var_110]
0x18004e368  mov     [rbp+60h+var_90], rax
0x18004e36c  mov     [rsp+160h+var_100], 1
0x18004e375  mov     [rbp+60h+var_98], 8
0x18004e37d  mov     [rsp+160h+var_110], r14
0x18004e382  mov     [rbp+60h+var_88], 8
0x18004e38a  call    BCryptIsoGetKGRunningInProdMode
0x18004e38f  mov     dword ptr [rsp+160h+var_108], eax
0x18004e393  lea     rdx, word_180070802; int
0x18004e39a  lea     rax, [rsp+160h+var_108]
0x18004e39f  mov     [rbp+60h+var_78], 4
0x18004e3a7  mov     [rbp+60h+var_80], rax
0x18004e3ab  lea     rcx, dword_1800790F0; int
0x18004e3b2  lea     rax, [rsp+160h+var_F0]
0x18004e3b7  mov     [rsp+160h+var_F0], 800h
0x18004e3c0  mov     [rbp+60h+var_70], rax
0x18004e3c4  mov     r9d, 7; int
0x18004e3ca  lea     rax, [rbp+60h+var_D0]
0x18004e3ce  mov     [rbp+60h+var_68], 8
0x18004e3d6  xor     r8d, r8d; int
0x18004e3d9  mov     [rsp+160h+var_140], rax; PEVENT_DATA_DESCRIPTOR
0x18004e3de  call    _tlgWriteAgg
0x18004e3e3  test    r12d, r12d
0x18004e3e6  js      loc_18004E526
0x18004e3ec  test    ebx, ebx
0x18004e3ee  js      loc_18004E528
0x18004e3f4  mov     rcx, [rsp+160h+var_E8]
0x18004e3f9  lea     rdx, [rsp+160h+var_108]
0x18004e3fe  mov     [rsp+160h+var_108], r14
0x18004e403  call    EndPerfMeasure
0x18004e408  test    eax, eax
0x18004e40a  jns     short loc_18004E452
0x18004e40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e413  lea     rdx, WPP_GLOBAL_Control
0x18004e41a  cmp     rcx, rdx
0x18004e41d  jz      loc_18004E526
0x18004e423  test    byte ptr [rcx+1Ch], 1
0x18004e427  jz      loc_18004E526
0x18004e42d  mov     rcx, [rcx+10h]
0x18004e431  lea     r9, aSpcryptcreatec; "SPCryptCreateClaim"
0x18004e438  mov     edx, 1Fh
0x18004e43d  mov     dword ptr [rsp+160h+var_140], eax
0x18004e441  lea     r8, WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids
0x18004e448  call    WPP_SF_sD
0x18004e44d  jmp     loc_18004E526
0x18004e452  mov     eax, cs:dword_180079068
0x18004e458  test    eax, eax
0x18004e45a  jz      loc_18004E526
0x18004e460  mov     rdx, 400000000000h
0x18004e46a  mov     rcx, rsi
0x18004e46d  call    _tlgKeywordOn
0x18004e472  test    al, al
0x18004e474  jz      loc_18004E526
0x18004e47a  lea     rax, [rsp+160h+var_F0]
0x18004e47f  mov     [rsp+160h+var_F0], 1
0x18004e488  mov     [rbp+60h+var_B0], rax
0x18004e48c  lea     rcx, [rsp+160h+var_F8]
0x18004e491  mov     rax, [rsp+160h+var_108]
0x18004e496  lea     rdx, byte_180070547; int
0x18004e49d  mov     [rsp+160h+var_F8], rax
0x18004e4a2  mov     r9d, r13d; int
0x18004e4a5  mov     [rsp+160h+var_100], rax
0x18004e4aa  xor     r8d, r8d; int
0x18004e4ad  mov     [rsp+160h+var_110], rax
0x18004e4b2  lea     rax, [rsp+160h+var_110]
0x18004e4b7  mov     [rbp+60h+var_80], rax
0x18004e4bb  lea     rax, [rsp+160h+var_108]
0x18004e4c0  mov     [rbp+60h+var_70], rax
0x18004e4c4  lea     rax, [rbp+60h+var_E0]
0x18004e4c8  mov     [rbp+60h+var_A0], rcx
0x18004e4cc  lea     rcx, [rsp+160h+var_100]
0x18004e4d1  mov     [rbp+60h+var_60], rax
0x18004e4d5  lea     rax, [rbp+60h+var_D0]
0x18004e4d9  mov     [rbp+60h+var_90], rcx
0x18004e4dd  mov     rcx, rsi; int
0x18004e4e0  mov     [rsp+160h+var_140], rax; PEVENT_DATA_DESCRIPTOR
0x18004e4e5  mov     [rbp+60h+var_A8], 8
0x18004e4ed  mov     [rbp+60h+var_98], 8
0x18004e4f5  mov     [rbp+60h+var_88], 8
0x18004e4fd  mov     [rbp+60h+var_78], 8
0x18004e505  mov     dword ptr [rsp+160h+var_108], edi
0x18004e509  mov     [rbp+60h+var_68], 4
0x18004e511  mov     [rbp+60h+var_E0], 3000000h
0x18004e519  mov     [rbp+60h+var_58], 8
0x18004e521  call    _tlgWriteAgg
0x18004e526  test    ebx, ebx
0x18004e528  jz      short loc_18004E546
0x18004e52a  cmp     ebx, 8009002Eh
0x18004e530  jz      short loc_18004E546
0x18004e532  mov     r9d, 9C6h
0x18004e538  mov     dword ptr [rsp+160h+var_140], ebx
0x18004e53c  mov     r8, r15
0x18004e53f  xor     ecx, ecx
0x18004e541  call    KspCryptAuditCryptOperation
0x18004e546  mov     eax, ebx
0x18004e548  mov     rcx, [rbp+60h+var_50]
0x18004e54c  xor     rcx, rsp; StackCookie
  ... truncated ...
```
