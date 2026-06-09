# BCryptCreateHash

- ea: `0x1800034b0`
- end: `0x1800039c2`
- name: `BCryptCreateHash`
- size: `1298`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `12`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001ab0`
- `0x180049b14`
- `0x180058960`
- `0x1800688c4`
- `0x180068f00`
- `0x1800691b8`
- `0x180069798`
- `0x180083878`
- `0x180083a30`
- `0x180084714`
- `0x180084a2c`

## callees

- `0x1800034b0`
- `0x1800039d0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18005c44c`
- `0x18009f6d0`
- `0x18009f780`

## string_xrefs

- `0x180003684`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800036cd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003735`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003788`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800037be`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003869`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800038a3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003943`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000396c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a0583`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a0618`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptCreateHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_HASH_HANDLE *phHash,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbSecret,
        ULONG cbSecret,
        ULONG dwFlags)
{
  ULONG v7; // ebp
  PUCHAR v8; // rdi
  int v11; // edx
  __int64 v12; // rbx
  int v13; // r8d
  void *v14; // r13
  _QWORD *v15; // rsi
  __int64 (__fastcall *v16)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // r10
  __int64 v17; // rax
  unsigned int v18; // ebp
  UCHAR *v19; // r14
  int v20; // eax
  int Property; // edi
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  int v27; // edx
  UCHAR *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  UCHAR *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  unsigned int i; // ecx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // ebp
  int v41; // eax
  __int64 v42; // r9
  unsigned __int64 v43; // r9
  unsigned __int64 v44; // r8
  __int64 v45; // r9
  __int64 (__fastcall *v46)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // rbp
  __int64 v47; // rax
  __int64 (__fastcall *v48)(_QWORD, UCHAR *, __int64, _QWORD); // rbp
  int v49; // eax
  __int64 v50; // r8
  unsigned int j; // ecx
  __int64 v52; // rax
  int v53; // eax
  unsigned int v54; // [rsp+50h] [rbp-78h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-74h] BYREF
  unsigned int v56; // [rsp+58h] [rbp-70h]
  ULONG pcbResult; // [rsp+5Ch] [rbp-6Ch] BYREF
  int v58; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v59; // [rsp+68h] [rbp-60h]
  __int64 (__fastcall *v60)(_QWORD, UCHAR *, __int64, _QWORD); // [rsp+70h] [rbp-58h]
  __int64 (__fastcall *v61)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // [rsp+78h] [rbp-50h]
  __int64 (__fastcall *v62)(_QWORD, const wchar_t *, unsigned int *, __int64, int *, _DWORD); // [rsp+80h] [rbp-48h]
  __int64 (__fastcall *v63)(_QWORD, UCHAR *, _QWORD, _QWORD); // [rsp+88h] [rbp-40h]
  __int64 (__fastcall *v64)(_QWORD, UCHAR *); // [rsp+90h] [rbp-38h]

  v7 = cbHashObject;
  v8 = pbHashObject;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      33,
      cbSecret,
      hAlgorithm,
      phHash,
      pbHashObject,
      cbHashObject,
      pbSecret,
      cbSecret,
      dwFlags);
  v12 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v12 )
  {
    if ( !v8 && !v7 )
    {
      *(_DWORD *)pbOutput = 0;
      pcbResult = 0;
      Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v23,
            v24,
            (unsigned int)"Status",
            Property,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            227);
      }
      else
      {
        v26 = MSCryptAlloc(*(unsigned int *)pbOutput, v23, v24, v25);
        v14 = (void *)v26;
        if ( v26 )
        {
          v7 = *(_DWORD *)pbOutput;
          v8 = (PUCHAR)v26;
LABEL_7:
          if ( phHash )
          {
            if ( v7 < 0x46 )
            {
              Property = -1073741789;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  v11,
                  v13,
                  (unsigned int)"Status",
                  35,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  171);
              }
              goto LABEL_34;
            }
            v15 = (_QWORD *)((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
            if ( *(_DWORD *)(v12 + 36) != 2 )
            {
              Property = -1073741637;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  v11,
                  v13,
                  (unsigned int)"Status",
                  187,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  184);
              }
              goto LABEL_34;
            }
            v16 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD))(v12 + 88);
            v17 = (unsigned int)((_DWORD)v15 - (_DWORD)v8);
            *(_DWORD *)v15 = 40;
            *(_DWORD *)(((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 4) = 1431655763;
            *(_QWORD *)(((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v12;
            v18 = v7 - v17 - 40;
            *(_QWORD *)(((unsigned __int64)(v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 0x20) = v14;
            v61 = v16;
            v19 = &v8[v17 + 40];
            if ( (*(_DWORD *)(v12 + 8) & 8) == 0 )
            {
              v20 = v16(
                      *(_QWORD *)(v12 + 24),
                      v15 + 2,
                      (unsigned __int64)(v19 + 15) & 0xFFFFFFFFFFFFFFF0uLL,
                      (_DWORD)v19 - (((_DWORD)v19 + 15) & 0xFFFFFFF0) + v18,
                      pbSecret,
                      cbSecret,
                      dwFlags);
              Property = v20;
              if ( v20 >= 0 )
              {
LABEL_12:
                *phHash = v15;
                Property = 0;
LABEL_13:
                _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
                return Property;
              }
              v30 = 6052;
              goto LABEL_66;
            }
            v38 = *(unsigned int *)(v12 + 12);
            v54 = 0;
            v58 = 0;
            if ( v18 <= (unsigned int)v38 )
            {
              v30 = 5876;
LABEL_64:
              Property = -1073741811;
              v39 = 3221225485LL;
LABEL_67:
              DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v30);
              goto LABEL_34;
            }
            v60 = *(__int64 (__fastcall **)(_QWORD, UCHAR *, __int64, _QWORD))(v12 + 96);
            v63 = *(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, _QWORD))(v12 + 104);
            v64 = *(__int64 (__fastcall **)(_QWORD, UCHAR *))(v12 + 120);
            v62 = *(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *, __int64, int *, _DWORD))(v12 + 64);
            v40 = (v18 - (unsigned int)v38) >> 1;
            v59 = (unsigned __int64)&v19[v38 + 15] & 0xFFFFFFFFFFFFFFF0uLL;
            v56 = v40 + (_DWORD)v19 + v38 - (((_DWORD)v19 + v38 + 15) & 0xFFFFFFF0);
            v41 = v16(*(_QWORD *)(v12 + 24), v15 + 2, v59, v56, 0, 0, 0);
            Property = v41;
            if ( v41 < 0 )
            {
              v42 = 5903;
LABEL_71:
              DebugTraceError(
                (unsigned int)v41,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                v42);
LABEL_34:
              if ( v14 )
                MSCryptFree(v14);
              goto LABEL_29;
            }
            v43 = v59 + v56;
            v44 = (v43 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
            v45 = v40 + (_DWORD)v43 - (_DWORD)v44;
            v46 = v61;
            v41 = v61(*(_QWORD *)(v12 + 24), v15 + 3, v44, v45, 0, 0, 0);
            Property = v41;
            if ( v41 < 0 )
            {
              v42 = 5919;
              goto LABEL_71;
            }
            if ( *(_DWORD *)(v12 + 12) >= cbSecret )
            {
              memmove(v19, pbSecret, cbSecret);
              v31 = &v19[cbSecret];
              v32 = *(_DWORD *)(v12 + 12) - cbSecret;
              if ( (_DWORD)v32 )
              {
                do
                {
                  *v31++ = 0;
                  --v32;
                }
                while ( v32 );
              }
            }
            else
            {
              v41 = v62(*(_QWORD *)(v12 + 24), L"HashDigestLength", &v54, 4, &v58, 0);
              Property = v41;
              if ( v41 < 0 )
              {
                v42 = 5936;
                goto LABEL_71;
              }
              if ( *(_DWORD *)(v12 + 12) < v54 )
              {
                v30 = 5944;
                goto LABEL_64;
              }
              v20 = v60(v15[2], pbSecret, cbSecret, 0);
              Property = v20;
              if ( v20 < 0 )
              {
                v30 = 5955;
                goto LABEL_66;
              }
              v20 = v63(v15[2], v19, v54, 0);
              Property = v20;
              if ( v20 < 0 )
              {
                v30 = 5966;
                goto LABEL_66;
              }
              v28 = &v19[v54];
              v29 = *(_DWORD *)(v12 + 12) - v54;
              if ( (_DWORD)v29 )
              {
                do
                {
                  *v28++ = 0;
                  --v29;
                }
                while ( v29 );
              }
              v20 = v64(v15[2], v28);
              Property = v20;
              if ( v20 < 0 )
              {
                v30 = 5976;
LABEL_66:
                v39 = (unsigned int)v20;
                goto LABEL_67;
              }
              v20 = v46(*(_QWORD *)(v12 + 24), v15 + 2, v59, v56, 0, 0, 0);
              Property = v20;
              if ( v20 < 0 )
              {
                v30 = 5989;
                goto LABEL_66;
              }
            }
            v33 = *(unsigned int *)(v12 + 12);
            for ( i = 0; i < (unsigned int)v33; v33 = *(unsigned int *)(v12 + 12) )
            {
              v47 = i++;
              v19[v47] ^= 0x36u;
            }
            v48 = v60;
            v49 = v60(v15[2], v19, v33, 0);
            Property = v49;
            if ( v49 < 0 )
            {
              DebugTraceError(
                (unsigned int)v49,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                6012);
              v35 = *(unsigned int *)(v12 + 12);
              if ( *(_DWORD *)(v12 + 12) )
              {
                do
                {
                  *v19++ = 0;
                  --v35;
                }
                while ( v35 );
              }
            }
            else
            {
              v50 = *(unsigned int *)(v12 + 12);
              for ( j = 0; j < (unsigned int)v50; v50 = *(unsigned int *)(v12 + 12) )
              {
                v52 = j++;
                v19[v52] ^= 0x6Au;
              }
              v53 = v48(v15[3], v19, v50, 0);
              Property = v53;
              if ( v53 >= 0 )
              {
                v37 = *(unsigned int *)(v12 + 12);
                if ( *(_DWORD *)(v12 + 12) )
                {
                  do
                  {
                    *v19++ = 0;
                    --v37;
                  }
                  while ( v37 );
                }
                goto LABEL_12;
              }
              DebugTraceError(
                (unsigned int)v53,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                6030);
              v36 = *(unsigned int *)(v12 + 12);
              if ( *(_DWORD *)(v12 + 12) )
              {
                do
                {
                  *v19++ = 0;
                  --v36;
                }
                while ( v36 );
              }
            }
            goto LABEL_34;
          }
LABEL_31:
          Property = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v11,
              v13,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              164);
          goto LABEL_34;
        }
        Property = -1073741801;
        DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 1003);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v23,
          v24,
          (unsigned int)"Status",
          Property,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          148);
LABEL_29:
      if ( Property < 0 )
        return Property;
      goto LABEL_13;
    }
    v14 = 0;
    if ( !v8 )
      goto LABEL_31;
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v27 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v27 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v27,
        v13,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        136);
  }
  return -1073741816;
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp+arg_10], rbx
0x1800034b5  push    rbp
0x1800034b6  push    rsi
0x1800034b7  push    rdi
0x1800034b8  push    r12
0x1800034ba  push    r14
0x1800034bc  sub     rsp, 0A0h
0x1800034c3  mov     ebp, r9d
0x1800034c6  mov     rdi, r8
0x1800034c9  mov     r12, rdx
0x1800034cc  mov     rsi, rcx
0x1800034cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034d6  lea     r14, WPP_GLOBAL_Control
0x1800034dd  cmp     rcx, r14
0x1800034e0  jz      short loc_1800034ED
0x1800034e2  mov     eax, [rcx+2Ch]
0x1800034e5  test    al, 4
0x1800034e7  jnz     loc_1800038F6
0x1800034ed  mov     rcx, rsi
0x1800034f0  call    ValidateBaseAlgHandle
0x1800034f5  mov     rbx, rax
0x1800034f8  test    rax, rax
0x1800034fb  jz      loc_18000366C
0x180003501  mov     [rsp+0C8h+arg_0], r13
0x180003509  mov     [rsp+0C8h+arg_8], r15
0x180003511  test    rdi, rdi
0x180003514  jz      loc_180003607
0x18000351a  xor     r15d, r15d
0x18000351d  mov     r13d, r15d
0x180003520  test    rdi, rdi
0x180003523  jz      loc_180003715
0x180003529  test    r12, r12
0x18000352c  jz      loc_180003715
0x180003532  cmp     ebp, 46h ; 'F'
0x180003535  jb      loc_180003768
0x18000353b  lea     rsi, [rdi+0Fh]
0x18000353f  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180003543  cmp     dword ptr [rbx+24h], 2
0x180003547  jnz     loc_18000379E
0x18000354d  mov     r10, [rbx+58h]
0x180003551  mov     eax, esi
0x180003553  sub     eax, edi
0x180003555  mov     dword ptr [rsi], 28h ; '('
0x18000355b  sub     ebp, eax
0x18000355d  mov     dword ptr [rsi+4], 55555553h
0x180003564  mov     [rsi+8], rbx
0x180003568  add     ebp, 0FFFFFFD8h
0x18000356b  mov     [rsi+20h], r13
0x18000356f  lea     r14, [rax+28h]
0x180003573  mov     [rsp+0C8h+var_50], r10
0x180003578  mov     eax, [rbx+8]
0x18000357b  add     r14, rdi
0x18000357e  test    al, 8
0x180003580  jnz     loc_180003997
0x180003586  mov     eax, [rsp+0C8h+dwFlags]
0x18000358d  lea     r8, [r14+0Fh]
0x180003591  mov     rcx, [rbx+18h]
0x180003595  lea     rdx, [rsi+10h]
0x180003599  mov     [rsp+0C8h+var_98], eax
0x18000359d  and     r8, 0FFFFFFFFFFFFFFF0h
0x1800035a1  mov     eax, [rsp+0C8h+cbSecret]
0x1800035a8  sub     r14d, r8d
0x1800035ab  mov     [rsp+0C8h+var_A0], eax
0x1800035af  mov     rax, [rsp+0C8h+pbSecret]
0x1800035b7  mov     [rsp+0C8h+pcbResult], rax
0x1800035bc  mov     rax, r10
0x1800035bf  lea     r9d, [r14+rbp]
0x1800035c3  call    _guard_dispatch_icall
0x1800035c8  mov     edi, eax
0x1800035ca  test    eax, eax
0x1800035cc  js      loc_1800039B7
0x1800035d2  mov     [r12], rsi
0x1800035d6  mov     edi, r15d
0x1800035d9  lock inc dword ptr [rbx+10h]
0x1800035dd  mov     r13, [rsp+0C8h+arg_0]
0x1800035e5  mov     eax, edi
0x1800035e7  mov     r15, [rsp+0C8h+arg_8]
0x1800035ef  mov     rbx, [rsp+0C8h+arg_10]
0x1800035f7  add     rsp, 0A0h
0x1800035fe  pop     r14
0x180003600  pop     r12
0x180003602  pop     rdi
0x180003603  pop     rsi
0x180003604  pop     rbp
0x180003605  retn
0x180003607  test    ebp, ebp
0x180003609  jnz     loc_18000351A
0x18000360f  xor     r15d, r15d
0x180003612  lea     rax, [rsp+0C8h+var_6C]
0x180003617  mov     [rsp+0C8h+var_A0], r15d; dwFlags
0x18000361c  lea     r8, [rsp+0C8h+pbOutput]; pbOutput
0x180003621  mov     r9d, 4; cbOutput
0x180003627  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x18000362c  lea     rdx, aObjectlength; "ObjectLength"
0x180003633  mov     dword ptr [rsp+0C8h+pbOutput], r15d
0x180003638  mov     rcx, rsi; hObject
0x18000363b  mov     [rsp+0C8h+var_6C], r15d
0x180003640  call    BCryptGetProperty
0x180003645  mov     edi, eax
0x180003647  test    eax, eax
0x180003649  js      short loc_1800036B6
0x18000364b  mov     ecx, dword ptr [rsp+0C8h+pbOutput]
0x18000364f  call    MSCryptAlloc
0x180003654  mov     r13, rax
0x180003657  test    rax, rax
0x18000365a  jz      loc_18000396C
0x180003660  mov     ebp, dword ptr [rsp+0C8h+pbOutput]
0x180003664  mov     rdi, rax
0x180003667  jmp     loc_180003529
0x18000366c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003673  cmp     rcx, r14
0x180003676  jz      short loc_1800036AC
0x180003678  mov     edx, [rcx+2Ch]
0x18000367b  test    dl, 1
0x18000367e  jz      short loc_1800036AC
0x180003680  mov     rcx, [rcx+18h]
0x180003684  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000368b  mov     [rsp+0C8h+var_98], 1688h
0x180003693  lea     r9, aStatus; "Status"
0x18000369a  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000369f  mov     dword ptr [rsp+0C8h+pcbResult], 0C0000008h
0x1800036a7  call    WPP_SF_sDsd
0x1800036ac  mov     eax, 0C0000008h
0x1800036b1  jmp     loc_1800035EF
0x1800036b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036bd  cmp     rcx, r14
0x1800036c0  jz      short loc_1800036CD
0x1800036c2  mov     eax, [rcx+2Ch]
0x1800036c5  test    al, 1
0x1800036c7  jnz     loc_18000393F
0x1800036cd  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800036d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036db  cmp     rcx, r14
0x1800036de  jz      short loc_180003708
0x1800036e0  mov     eax, [rcx+2Ch]
0x1800036e3  test    al, 1
0x1800036e5  jz      short loc_180003708
0x1800036e7  mov     rcx, [rcx+18h]
0x1800036eb  lea     r9, aStatus; "Status"
0x1800036f2  mov     [rsp+0C8h+var_98], 1694h
0x1800036fa  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x1800036ff  mov     dword ptr [rsp+0C8h+pcbResult], edi
0x180003703  call    WPP_SF_sDsd
0x180003708  test    edi, edi
0x18000370a  jns     loc_1800035D9
0x180003710  jmp     loc_1800035DD
0x180003715  mov     edi, 0C000000Dh
0x18000371a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003721  cmp     rcx, r14
0x180003724  jz      short loc_180003759
0x180003726  mov     eax, [rcx+2Ch]
0x180003729  test    al, 1
0x18000372b  jz      short loc_180003759
0x18000372d  mov     [rsp+0C8h+var_98], 16A4h
0x180003735  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000373c  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x180003741  mov     dword ptr [rsp+0C8h+pcbResult], 0C000000Dh
0x180003749  mov     rcx, [rcx+18h]
0x18000374d  lea     r9, aStatus; "Status"
0x180003754  call    WPP_SF_sDsd
0x180003759  test    r13, r13
0x18000375c  jz      short loc_180003708
0x18000375e  mov     rcx, r13; P
0x180003761  call    MSCryptFree
0x180003766  jmp     short loc_180003708
0x180003768  mov     edi, 0C0000023h
0x18000376d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003774  cmp     rcx, r14
0x180003777  jz      short loc_180003759
0x180003779  mov     eax, [rcx+2Ch]
0x18000377c  test    al, 1
0x18000377e  jz      short loc_180003759
0x180003780  mov     [rsp+0C8h+var_98], 16ABh
0x180003788  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000378f  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x180003794  mov     dword ptr [rsp+0C8h+pcbResult], 0C0000023h
0x18000379c  jmp     short loc_180003749
0x18000379e  mov     edi, 0C00000BBh
0x1800037a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037aa  cmp     rcx, r14
0x1800037ad  jz      short loc_180003759
0x1800037af  mov     eax, [rcx+2Ch]
0x1800037b2  test    al, 1
0x1800037b4  jz      short loc_180003759
0x1800037b6  mov     [rsp+0C8h+var_98], 16B8h
0x1800037be  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800037c5  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x1800037ca  mov     dword ptr [rsp+0C8h+pcbResult], 0C00000BBh
0x1800037d2  jmp     loc_180003749
0x1800037d7  mov     ecx, [rsp+0C8h+var_78]
0x1800037db  mov     r8d, [rbx+0Ch]
0x1800037df  lea     rdx, [r14+rcx]
0x1800037e3  sub     r8d, ecx
0x1800037e6  jz      short loc_1800037F5
0x1800037e8  mov     byte ptr [rdx], 0
0x1800037eb  lea     rdx, [rdx+1]
0x1800037ef  sub     r8, 1
0x1800037f3  jnz     short loc_1800037E8
0x1800037f5  mov     rcx, [rsi+10h]
0x1800037f9  mov     rax, [rsp+0C8h+var_38]
0x180003801  call    _guard_dispatch_icall
0x180003806  mov     edi, eax
0x180003808  test    eax, eax
0x18000380a  jns     loc_1800A0732
0x180003810  mov     r9d, 1758h
0x180003816  jmp     loc_1800A057A
0x18000381b  mov     rdx, [rsp+0C8h+pbSecret]; Src
0x180003823  mov     r8, rax; Size
0x180003826  mov     rcx, r14; void *
0x180003829  mov     rdi, rax
0x18000382c  call    memmove
0x180003831  mov     ecx, [rbx+0Ch]
0x180003834  lea     rax, [rdi+r14]
0x180003838  sub     ecx, [rsp+0C8h+cbSecret]
0x18000383f  jz      short loc_18000384E
0x180003841  mov     byte ptr [rax], 0
0x180003844  lea     rax, [rax+1]
0x180003848  sub     rcx, 1
0x18000384c  jnz     short loc_180003841
0x18000384e  mov     r8d, [rbx+0Ch]
0x180003852  mov     ecx, r15d
0x180003855  test    r8d, r8d
0x180003858  jnz     loc_1800A0770
0x18000385e  jmp     loc_1800A0782
0x180003863  mov     r9d, 177Ch
0x180003869  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003870  lea     rdx, aStatus; "Status"
0x180003877  mov     ecx, eax
0x180003879  call    DebugTraceError
0x18000387e  mov     eax, [rbx+0Ch]
0x180003881  test    rax, rax
0x180003884  jz      loc_180003759
0x18000388a  mov     byte ptr [r14], 0
0x18000388e  lea     r14, [r14+1]
0x180003892  sub     rax, 1
0x180003896  jnz     short loc_18000388A
0x180003898  jmp     loc_180003759
0x18000389d  mov     r9d, 178Eh
0x1800038a3  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800038aa  lea     rdx, aStatus; "Status"
0x1800038b1  mov     ecx, eax
0x1800038b3  call    DebugTraceError
0x1800038b8  mov     eax, [rbx+0Ch]
0x1800038bb  test    rax, rax
0x1800038be  jz      loc_180003759
0x1800038c4  mov     byte ptr [r14], 0
0x1800038c8  lea     r14, [r14+1]
0x1800038cc  sub     rax, 1
0x1800038d0  jnz     short loc_1800038C4
0x1800038d2  jmp     loc_180003759
0x1800038d7  mov     eax, [rbx+0Ch]
0x1800038da  test    rax, rax
0x1800038dd  jz      loc_1800035D2
0x1800038e3  mov     byte ptr [r14], 0
0x1800038e7  lea     r14, [r14+1]
0x1800038eb  sub     rax, 1
0x1800038ef  jnz     short loc_1800038E3
0x1800038f1  jmp     loc_1800035D2
0x1800038f6  mov     eax, [rsp+0C8h+dwFlags]
0x1800038fd  mov     edx, 21h ; '!'
0x180003902  mov     r8d, [rsp+0C8h+cbSecret]
0x18000390a  mov     r9, rsi
0x18000390d  mov     rcx, [rcx+18h]
0x180003911  mov     [rsp+0C8h+var_80], eax
0x180003915  mov     rax, [rsp+0C8h+pbSecret]
0x18000391d  mov     [rsp+0C8h+var_88], r8d
0x180003922  mov     [rsp+0C8h+var_90], rax
0x180003927  mov     [rsp+0C8h+var_98], ebp
0x18000392b  mov     qword ptr [rsp+0C8h+var_A0], rdi
0x180003930  mov     [rsp+0C8h+pcbResult], r12
0x180003935  call    WPP_SF_qqqdqdD
0x18000393a  jmp     loc_1800034ED
0x18000393f  mov     rcx, [rcx+18h]
0x180003943  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000394a  mov     [rsp+0C8h+var_98], 3E3h
0x180003952  lea     r9, aStatus; "Status"
0x180003959  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000395e  mov     dword ptr [rsp+0C8h+pcbResult], edi
0x180003962  call    WPP_SF_sDsd
0x180003967  jmp     loc_1800036D4
0x18000396c  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003973  mov     r9d, 3EBh
0x180003979  mov     r8, rsi
0x18000397c  lea     rdx, aStatus; "Status"
0x180003983  mov     ecx, 0C0000017h
0x180003988  mov     edi, 0C0000017h
0x18000398d  call    DebugTraceError
0x180003992  jmp     loc_1800036D4
0x180003997  mov     eax, [rbx+0Ch]
0x18000399a  mov     [rsp+0C8h+var_78], r15d
0x18000399f  mov     [rsp+0C8h+var_68], r15d
0x1800039a4  cmp     ebp, eax
0x1800039a6  ja      loc_1800A0595
0x1800039ac  mov     r9d, 16F4h
0x1800039b2  jmp     loc_1800A0568
0x1800039b7  mov     r9d, 17A4h
0x1800039bd  jmp     loc_1800A057A
0x1800a0562  mov     r9d, 1738h
0x1800a0568  mov     edi, 0C000000Dh
0x1800a056d  mov     ecx, 0C000000Dh
  ... truncated ...
```
