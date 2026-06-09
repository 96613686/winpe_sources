# BCryptCreateHash

- ea: `0x18000d5d0`
- end: `0x18000dae2`
- name: `BCryptCreateHash`
- size: `1298`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbSecret, ULONG cbSecret, ULONG dwFlags)`
- caller_count: `12`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000b9b0`
- `0x18000bbd0`
- `0x180053184`
- `0x180062240`
- `0x180072064`
- `0x1800726a0`
- `0x180072958`
- `0x180072f38`
- `0x18008ca78`
- `0x18008cc30`
- `0x18008d914`
- `0x18008dc2c`

## callees

- `0x18000d5d0`
- `0x18000daf0`
- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x180065d2c`
- `0x1800a4300`
- `0x1800a45c0`

## string_xrefs

- `0x18000d7a4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d7ed`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d855`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d8a8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d8de`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d989`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d9c3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000da63`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000da8c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a54f1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a5586`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  int v24; // r8d
  __int64 v25; // rax
  int v26; // edx
  UCHAR *v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  UCHAR *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8
  unsigned int i; // ecx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  unsigned int v39; // ebp
  int v40; // eax
  __int64 v41; // r9
  unsigned __int64 v42; // r9
  unsigned __int64 v43; // r8
  __int64 v44; // r9
  __int64 (__fastcall *v45)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // rbp
  __int64 v46; // rax
  __int64 (__fastcall *v47)(_QWORD, UCHAR *, __int64, _QWORD); // rbp
  int v48; // eax
  __int64 v49; // r8
  unsigned int j; // ecx
  __int64 v51; // rax
  int v52; // eax
  unsigned int v53; // [rsp+50h] [rbp-78h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-74h] BYREF
  unsigned int v55; // [rsp+58h] [rbp-70h]
  ULONG pcbResult; // [rsp+5Ch] [rbp-6Ch] BYREF
  int v57; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v58; // [rsp+68h] [rbp-60h]
  __int64 (__fastcall *v59)(_QWORD, UCHAR *, __int64, _QWORD); // [rsp+70h] [rbp-58h]
  __int64 (__fastcall *v60)(_QWORD, _QWORD *, unsigned __int64, _QWORD, _QWORD, _DWORD, _DWORD); // [rsp+78h] [rbp-50h]
  __int64 (__fastcall *v61)(_QWORD, const wchar_t *, unsigned int *, __int64, int *, _DWORD); // [rsp+80h] [rbp-48h]
  __int64 (__fastcall *v62)(_QWORD, UCHAR *, _QWORD, _QWORD); // [rsp+88h] [rbp-40h]
  __int64 (__fastcall *v63)(_QWORD, UCHAR *); // [rsp+90h] [rbp-38h]

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
        v25 = MSCryptAlloc(*(unsigned int *)pbOutput, v23);
        v14 = (void *)v25;
        if ( v25 )
        {
          v7 = *(_DWORD *)pbOutput;
          v8 = (PUCHAR)v25;
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
            v60 = v16;
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
              v29 = 6052;
              goto LABEL_66;
            }
            v37 = *(unsigned int *)(v12 + 12);
            v53 = 0;
            v57 = 0;
            if ( v18 <= (unsigned int)v37 )
            {
              v29 = 5876;
LABEL_64:
              Property = -1073741811;
              v38 = 3221225485LL;
LABEL_67:
              DebugTraceError(v38, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v29);
              goto LABEL_34;
            }
            v59 = *(__int64 (__fastcall **)(_QWORD, UCHAR *, __int64, _QWORD))(v12 + 96);
            v62 = *(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, _QWORD))(v12 + 104);
            v63 = *(__int64 (__fastcall **)(_QWORD, UCHAR *))(v12 + 120);
            v61 = *(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *, __int64, int *, _DWORD))(v12 + 64);
            v39 = (v18 - (unsigned int)v37) >> 1;
            v58 = (unsigned __int64)&v19[v37 + 15] & 0xFFFFFFFFFFFFFFF0uLL;
            v55 = v39 + (_DWORD)v19 + v37 - (((_DWORD)v19 + v37 + 15) & 0xFFFFFFF0);
            v40 = v16(*(_QWORD *)(v12 + 24), v15 + 2, v58, v55, 0, 0, 0);
            Property = v40;
            if ( v40 < 0 )
            {
              v41 = 5903;
LABEL_71:
              DebugTraceError(
                (unsigned int)v40,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                v41);
LABEL_34:
              if ( v14 )
                MSCryptFree(v14);
              goto LABEL_29;
            }
            v42 = v58 + v55;
            v43 = (v42 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
            v44 = v39 + (_DWORD)v42 - (_DWORD)v43;
            v45 = v60;
            v40 = v60(*(_QWORD *)(v12 + 24), v15 + 3, v43, v44, 0, 0, 0);
            Property = v40;
            if ( v40 < 0 )
            {
              v41 = 5919;
              goto LABEL_71;
            }
            if ( *(_DWORD *)(v12 + 12) >= cbSecret )
            {
              memmove(v19, pbSecret, cbSecret);
              v30 = &v19[cbSecret];
              v31 = *(_DWORD *)(v12 + 12) - cbSecret;
              if ( (_DWORD)v31 )
              {
                do
                {
                  *v30++ = 0;
                  --v31;
                }
                while ( v31 );
              }
            }
            else
            {
              v40 = v61(*(_QWORD *)(v12 + 24), L"HashDigestLength", &v53, 4, &v57, 0);
              Property = v40;
              if ( v40 < 0 )
              {
                v41 = 5936;
                goto LABEL_71;
              }
              if ( *(_DWORD *)(v12 + 12) < v53 )
              {
                v29 = 5944;
                goto LABEL_64;
              }
              v20 = v59(v15[2], pbSecret, cbSecret, 0);
              Property = v20;
              if ( v20 < 0 )
              {
                v29 = 5955;
                goto LABEL_66;
              }
              v20 = v62(v15[2], v19, v53, 0);
              Property = v20;
              if ( v20 < 0 )
              {
                v29 = 5966;
                goto LABEL_66;
              }
              v27 = &v19[v53];
              v28 = *(_DWORD *)(v12 + 12) - v53;
              if ( (_DWORD)v28 )
              {
                do
                {
                  *v27++ = 0;
                  --v28;
                }
                while ( v28 );
              }
              v20 = v63(v15[2], v27);
              Property = v20;
              if ( v20 < 0 )
              {
                v29 = 5976;
LABEL_66:
                v38 = (unsigned int)v20;
                goto LABEL_67;
              }
              v20 = v45(*(_QWORD *)(v12 + 24), v15 + 2, v58, v55, 0, 0, 0);
              Property = v20;
              if ( v20 < 0 )
              {
                v29 = 5989;
                goto LABEL_66;
              }
            }
            v32 = *(unsigned int *)(v12 + 12);
            for ( i = 0; i < (unsigned int)v32; v32 = *(unsigned int *)(v12 + 12) )
            {
              v46 = i++;
              v19[v46] ^= 0x36u;
            }
            v47 = v59;
            v48 = v59(v15[2], v19, v32, 0);
            Property = v48;
            if ( v48 < 0 )
            {
              DebugTraceError(
                (unsigned int)v48,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                6012);
              v34 = *(unsigned int *)(v12 + 12);
              if ( *(_DWORD *)(v12 + 12) )
              {
                do
                {
                  *v19++ = 0;
                  --v34;
                }
                while ( v34 );
              }
            }
            else
            {
              v49 = *(unsigned int *)(v12 + 12);
              for ( j = 0; j < (unsigned int)v49; v49 = *(unsigned int *)(v12 + 12) )
              {
                v51 = j++;
                v19[v51] ^= 0x6Au;
              }
              v52 = v47(v15[3], v19, v49, 0);
              Property = v52;
              if ( v52 >= 0 )
              {
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
                goto LABEL_12;
              }
              DebugTraceError(
                (unsigned int)v52,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                6030);
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
    v26 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v26 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
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
0x18000d5d0  mov     [rsp+arg_10], rbx
0x18000d5d5  push    rbp
0x18000d5d6  push    rsi
0x18000d5d7  push    rdi
0x18000d5d8  push    r12
0x18000d5da  push    r14
0x18000d5dc  sub     rsp, 0A0h
0x18000d5e3  mov     ebp, r9d
0x18000d5e6  mov     rdi, r8
0x18000d5e9  mov     r12, rdx
0x18000d5ec  mov     rsi, rcx
0x18000d5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5f6  lea     r14, WPP_GLOBAL_Control
0x18000d5fd  cmp     rcx, r14
0x18000d600  jz      short loc_18000D60D
0x18000d602  mov     eax, [rcx+2Ch]
0x18000d605  test    al, 4
0x18000d607  jnz     loc_18000DA16
0x18000d60d  mov     rcx, rsi
0x18000d610  call    ValidateBaseAlgHandle
0x18000d615  mov     rbx, rax
0x18000d618  test    rax, rax
0x18000d61b  jz      loc_18000D78C
0x18000d621  mov     [rsp+0C8h+arg_0], r13
0x18000d629  mov     [rsp+0C8h+arg_8], r15
0x18000d631  test    rdi, rdi
0x18000d634  jz      loc_18000D727
0x18000d63a  xor     r15d, r15d
0x18000d63d  mov     r13d, r15d
0x18000d640  test    rdi, rdi
0x18000d643  jz      loc_18000D835
0x18000d649  test    r12, r12
0x18000d64c  jz      loc_18000D835
0x18000d652  cmp     ebp, 46h ; 'F'
0x18000d655  jb      loc_18000D888
0x18000d65b  lea     rsi, [rdi+0Fh]
0x18000d65f  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18000d663  cmp     dword ptr [rbx+24h], 2
0x18000d667  jnz     loc_18000D8BE
0x18000d66d  mov     r10, [rbx+58h]
0x18000d671  mov     eax, esi
0x18000d673  sub     eax, edi
0x18000d675  mov     dword ptr [rsi], 28h ; '('
0x18000d67b  sub     ebp, eax
0x18000d67d  mov     dword ptr [rsi+4], 55555553h
0x18000d684  mov     [rsi+8], rbx
0x18000d688  add     ebp, 0FFFFFFD8h
0x18000d68b  mov     [rsi+20h], r13
0x18000d68f  lea     r14, [rax+28h]
0x18000d693  mov     [rsp+0C8h+var_50], r10
0x18000d698  mov     eax, [rbx+8]
0x18000d69b  add     r14, rdi
0x18000d69e  test    al, 8
0x18000d6a0  jnz     loc_18000DAB7
0x18000d6a6  mov     eax, [rsp+0C8h+dwFlags]
0x18000d6ad  lea     r8, [r14+0Fh]
0x18000d6b1  mov     rcx, [rbx+18h]
0x18000d6b5  lea     rdx, [rsi+10h]
0x18000d6b9  mov     [rsp+0C8h+var_98], eax
0x18000d6bd  and     r8, 0FFFFFFFFFFFFFFF0h
0x18000d6c1  mov     eax, [rsp+0C8h+cbSecret]
0x18000d6c8  sub     r14d, r8d
0x18000d6cb  mov     [rsp+0C8h+var_A0], eax
0x18000d6cf  mov     rax, [rsp+0C8h+pbSecret]
0x18000d6d7  mov     [rsp+0C8h+pcbResult], rax
0x18000d6dc  mov     rax, r10
0x18000d6df  lea     r9d, [r14+rbp]
0x18000d6e3  call    _guard_dispatch_icall
0x18000d6e8  mov     edi, eax
0x18000d6ea  test    eax, eax
0x18000d6ec  js      loc_18000DAD7
0x18000d6f2  mov     [r12], rsi
0x18000d6f6  mov     edi, r15d
0x18000d6f9  lock inc dword ptr [rbx+10h]
0x18000d6fd  mov     r13, [rsp+0C8h+arg_0]
0x18000d705  mov     eax, edi
0x18000d707  mov     r15, [rsp+0C8h+arg_8]
0x18000d70f  mov     rbx, [rsp+0C8h+arg_10]
0x18000d717  add     rsp, 0A0h
0x18000d71e  pop     r14
0x18000d720  pop     r12
0x18000d722  pop     rdi
0x18000d723  pop     rsi
0x18000d724  pop     rbp
0x18000d725  retn
0x18000d727  test    ebp, ebp
0x18000d729  jnz     loc_18000D63A
0x18000d72f  xor     r15d, r15d
0x18000d732  lea     rax, [rsp+0C8h+var_6C]
0x18000d737  mov     [rsp+0C8h+var_A0], r15d; dwFlags
0x18000d73c  lea     r8, [rsp+0C8h+pbOutput]; pbOutput
0x18000d741  mov     r9d, 4; cbOutput
0x18000d747  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x18000d74c  lea     rdx, aObjectlength; "ObjectLength"
0x18000d753  mov     dword ptr [rsp+0C8h+pbOutput], r15d
0x18000d758  mov     rcx, rsi; hObject
0x18000d75b  mov     [rsp+0C8h+var_6C], r15d
0x18000d760  call    BCryptGetProperty
0x18000d765  mov     edi, eax
0x18000d767  test    eax, eax
0x18000d769  js      short loc_18000D7D6
0x18000d76b  mov     ecx, dword ptr [rsp+0C8h+pbOutput]
0x18000d76f  call    MSCryptAlloc
0x18000d774  mov     r13, rax
0x18000d777  test    rax, rax
0x18000d77a  jz      loc_18000DA8C
0x18000d780  mov     ebp, dword ptr [rsp+0C8h+pbOutput]
0x18000d784  mov     rdi, rax
0x18000d787  jmp     loc_18000D649
0x18000d78c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d793  cmp     rcx, r14
0x18000d796  jz      short loc_18000D7CC
0x18000d798  mov     edx, [rcx+2Ch]
0x18000d79b  test    dl, 1
0x18000d79e  jz      short loc_18000D7CC
0x18000d7a0  mov     rcx, [rcx+18h]
0x18000d7a4  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d7ab  mov     [rsp+0C8h+var_98], 1688h
0x18000d7b3  lea     r9, aStatus; "Status"
0x18000d7ba  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000d7bf  mov     dword ptr [rsp+0C8h+pcbResult], 0C0000008h
0x18000d7c7  call    WPP_SF_sDsd
0x18000d7cc  mov     eax, 0C0000008h
0x18000d7d1  jmp     loc_18000D70F
0x18000d7d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7dd  cmp     rcx, r14
0x18000d7e0  jz      short loc_18000D7ED
0x18000d7e2  mov     eax, [rcx+2Ch]
0x18000d7e5  test    al, 1
0x18000d7e7  jnz     loc_18000DA5F
0x18000d7ed  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7fb  cmp     rcx, r14
0x18000d7fe  jz      short loc_18000D828
0x18000d800  mov     eax, [rcx+2Ch]
0x18000d803  test    al, 1
0x18000d805  jz      short loc_18000D828
0x18000d807  mov     rcx, [rcx+18h]
0x18000d80b  lea     r9, aStatus; "Status"
0x18000d812  mov     [rsp+0C8h+var_98], 1694h
0x18000d81a  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000d81f  mov     dword ptr [rsp+0C8h+pcbResult], edi
0x18000d823  call    WPP_SF_sDsd
0x18000d828  test    edi, edi
0x18000d82a  jns     loc_18000D6F9
0x18000d830  jmp     loc_18000D6FD
0x18000d835  mov     edi, 0C000000Dh
0x18000d83a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d841  cmp     rcx, r14
0x18000d844  jz      short loc_18000D879
0x18000d846  mov     eax, [rcx+2Ch]
0x18000d849  test    al, 1
0x18000d84b  jz      short loc_18000D879
0x18000d84d  mov     [rsp+0C8h+var_98], 16A4h
0x18000d855  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d85c  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000d861  mov     dword ptr [rsp+0C8h+pcbResult], 0C000000Dh
0x18000d869  mov     rcx, [rcx+18h]
0x18000d86d  lea     r9, aStatus; "Status"
0x18000d874  call    WPP_SF_sDsd
0x18000d879  test    r13, r13
0x18000d87c  jz      short loc_18000D828
0x18000d87e  mov     rcx, r13; P
0x18000d881  call    MSCryptFree
0x18000d886  jmp     short loc_18000D828
0x18000d888  mov     edi, 0C0000023h
0x18000d88d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d894  cmp     rcx, r14
0x18000d897  jz      short loc_18000D879
0x18000d899  mov     eax, [rcx+2Ch]
0x18000d89c  test    al, 1
0x18000d89e  jz      short loc_18000D879
0x18000d8a0  mov     [rsp+0C8h+var_98], 16ABh
0x18000d8a8  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d8af  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000d8b4  mov     dword ptr [rsp+0C8h+pcbResult], 0C0000023h
0x18000d8bc  jmp     short loc_18000D869
0x18000d8be  mov     edi, 0C00000BBh
0x18000d8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8ca  cmp     rcx, r14
0x18000d8cd  jz      short loc_18000D879
0x18000d8cf  mov     eax, [rcx+2Ch]
0x18000d8d2  test    al, 1
0x18000d8d4  jz      short loc_18000D879
0x18000d8d6  mov     [rsp+0C8h+var_98], 16B8h
0x18000d8de  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d8e5  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000d8ea  mov     dword ptr [rsp+0C8h+pcbResult], 0C00000BBh
0x18000d8f2  jmp     loc_18000D869
0x18000d8f7  mov     ecx, [rsp+0C8h+var_78]
0x18000d8fb  mov     r8d, [rbx+0Ch]
0x18000d8ff  lea     rdx, [r14+rcx]
0x18000d903  sub     r8d, ecx
0x18000d906  jz      short loc_18000D915
0x18000d908  mov     byte ptr [rdx], 0
0x18000d90b  lea     rdx, [rdx+1]
0x18000d90f  sub     r8, 1
0x18000d913  jnz     short loc_18000D908
0x18000d915  mov     rcx, [rsi+10h]
0x18000d919  mov     rax, [rsp+0C8h+var_38]
0x18000d921  call    _guard_dispatch_icall
0x18000d926  mov     edi, eax
0x18000d928  test    eax, eax
0x18000d92a  jns     loc_1800A56A0
0x18000d930  mov     r9d, 1758h
0x18000d936  jmp     loc_1800A54E8
0x18000d93b  mov     rdx, [rsp+0C8h+pbSecret]; Src
0x18000d943  mov     r8, rax; Size
0x18000d946  mov     rcx, r14; void *
0x18000d949  mov     rdi, rax
0x18000d94c  call    memmove
0x18000d951  mov     ecx, [rbx+0Ch]
0x18000d954  lea     rax, [rdi+r14]
0x18000d958  sub     ecx, [rsp+0C8h+cbSecret]
0x18000d95f  jz      short loc_18000D96E
0x18000d961  mov     byte ptr [rax], 0
0x18000d964  lea     rax, [rax+1]
0x18000d968  sub     rcx, 1
0x18000d96c  jnz     short loc_18000D961
0x18000d96e  mov     r8d, [rbx+0Ch]
0x18000d972  mov     ecx, r15d
0x18000d975  test    r8d, r8d
0x18000d978  jnz     loc_1800A56DE
0x18000d97e  jmp     loc_1800A56F0
0x18000d983  mov     r9d, 177Ch
0x18000d989  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d990  lea     rdx, aStatus; "Status"
0x18000d997  mov     ecx, eax
0x18000d999  call    DebugTraceError
0x18000d99e  mov     eax, [rbx+0Ch]
0x18000d9a1  test    rax, rax
0x18000d9a4  jz      loc_18000D879
0x18000d9aa  mov     byte ptr [r14], 0
0x18000d9ae  lea     r14, [r14+1]
0x18000d9b2  sub     rax, 1
0x18000d9b6  jnz     short loc_18000D9AA
0x18000d9b8  jmp     loc_18000D879
0x18000d9bd  mov     r9d, 178Eh
0x18000d9c3  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d9ca  lea     rdx, aStatus; "Status"
0x18000d9d1  mov     ecx, eax
0x18000d9d3  call    DebugTraceError
0x18000d9d8  mov     eax, [rbx+0Ch]
0x18000d9db  test    rax, rax
0x18000d9de  jz      loc_18000D879
0x18000d9e4  mov     byte ptr [r14], 0
0x18000d9e8  lea     r14, [r14+1]
0x18000d9ec  sub     rax, 1
0x18000d9f0  jnz     short loc_18000D9E4
0x18000d9f2  jmp     loc_18000D879
0x18000d9f7  mov     eax, [rbx+0Ch]
0x18000d9fa  test    rax, rax
0x18000d9fd  jz      loc_18000D6F2
0x18000da03  mov     byte ptr [r14], 0
0x18000da07  lea     r14, [r14+1]
0x18000da0b  sub     rax, 1
0x18000da0f  jnz     short loc_18000DA03
0x18000da11  jmp     loc_18000D6F2
0x18000da16  mov     eax, [rsp+0C8h+dwFlags]
0x18000da1d  mov     edx, 21h ; '!'
0x18000da22  mov     r8d, [rsp+0C8h+cbSecret]
0x18000da2a  mov     r9, rsi
0x18000da2d  mov     rcx, [rcx+18h]
0x18000da31  mov     [rsp+0C8h+var_80], eax
0x18000da35  mov     rax, [rsp+0C8h+pbSecret]
0x18000da3d  mov     [rsp+0C8h+var_88], r8d
0x18000da42  mov     [rsp+0C8h+var_90], rax
0x18000da47  mov     [rsp+0C8h+var_98], ebp
0x18000da4b  mov     qword ptr [rsp+0C8h+var_A0], rdi
0x18000da50  mov     [rsp+0C8h+pcbResult], r12
0x18000da55  call    WPP_SF_qqqdqdD
0x18000da5a  jmp     loc_18000D60D
0x18000da5f  mov     rcx, [rcx+18h]
0x18000da63  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da6a  mov     [rsp+0C8h+var_98], 3E3h
0x18000da72  lea     r9, aStatus; "Status"
0x18000da79  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x18000da7e  mov     dword ptr [rsp+0C8h+pcbResult], edi
0x18000da82  call    WPP_SF_sDsd
0x18000da87  jmp     loc_18000D7F4
0x18000da8c  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da93  mov     r9d, 3EBh
0x18000da99  mov     r8, rsi
0x18000da9c  lea     rdx, aStatus; "Status"
0x18000daa3  mov     ecx, 0C0000017h
0x18000daa8  mov     edi, 0C0000017h
0x18000daad  call    DebugTraceError
0x18000dab2  jmp     loc_18000D7F4
0x18000dab7  mov     eax, [rbx+0Ch]
0x18000daba  mov     [rsp+0C8h+var_78], r15d
0x18000dabf  mov     [rsp+0C8h+var_68], r15d
0x18000dac4  cmp     ebp, eax
0x18000dac6  ja      loc_1800A5503
0x18000dacc  mov     r9d, 16F4h
0x18000dad2  jmp     loc_1800A54D6
0x18000dad7  mov     r9d, 17A4h
0x18000dadd  jmp     loc_1800A54E8
0x1800a54d0  mov     r9d, 1738h
0x1800a54d6  mov     edi, 0C000000Dh
0x1800a54db  mov     ecx, 0C000000Dh
  ... truncated ...
```
