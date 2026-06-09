# TlsDeriveSecret

- ea: `0x1800037a0`
- end: `0x180003edc`
- name: `TlsDeriveSecret`
- size: `1852`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002510`
- `0x1800029e0`
- `0x180003f10`
- `0x18000b6a0`
- `0x18001ece0`

## callees

- `0x1800037a0`
- `0x180003ef0`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`
- `0x180020cb4`
- `0x180024fb0`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180003c95`
- `bcrypt!BCryptSetProperty` at `0x180003cb5`
- `bcrypt!BCryptSetProperty` at `0x180003c95`
- `bcrypt!BCryptSetProperty` at `0x180003cb5`
- `bcrypt!BCryptKeyDerivation` at `0x180003a89`
- `bcrypt!BCryptKeyDerivation` at `0x180003a89`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180003c4a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180003c4a`
- `bcrypt!BCryptDestroyKey` at `0x180003d22`
- `bcrypt!BCryptDestroyKey` at `0x180003d22`
- `ntdll!RtlFreeHeap` at `0x180003b6f`
- `ntdll!RtlFreeHeap` at `0x180003c1f`
- `ntdll!RtlFreeHeap` at `0x180003b6f`
- `ntdll!RtlFreeHeap` at `0x180003c1f`
- `ntdll!RtlAllocateHeap` at `0x1800038ad`
- `ntdll!RtlAllocateHeap` at `0x18000391f`
- `ntdll!RtlAllocateHeap` at `0x1800039e2`
- `ntdll!RtlAllocateHeap` at `0x1800038ad`
- `ntdll!RtlAllocateHeap` at `0x18000391f`
- `ntdll!RtlAllocateHeap` at `0x1800039e2`

## string_xrefs

- `0x180003a98`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003b1a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003bc9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003cfa`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003d56`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003dfd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003e40`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003e68`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003e92`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003eaf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsDeriveSecret(
        __int64 a1,
        const char *a2,
        const void *a3,
        unsigned __int8 a4,
        int a5,
        BCRYPT_KEY_HANDLE **a6)
{
  size_t v6; // r12
  __int64 v9; // r15
  wchar_t *v10; // rsi
  __int64 i; // rbx
  const wchar_t **v12; // rax
  __int64 *v13; // rdi
  ULONG v14; // edi
  char *Heap; // rax
  BCRYPT_KEY_HANDLE *v16; // r14
  __int64 v17; // rsi
  size_t v18; // rdx
  int v19; // r8d
  _BYTE *pbSecret; // r15
  int v21; // edx
  int v22; // r8d
  unsigned __int8 v23; // bl
  SIZE_T v24; // rbp
  int v25; // edx
  int v26; // r8d
  char *v27; // rcx
  __int64 v28; // rbx
  size_t v29; // r8
  char *v30; // rdi
  _BYTE *v31; // r12
  unsigned int SymmetricKey; // edi
  int v33; // r8d
  _BYTE *j; // rax
  _BYTE *v36; // rax
  int v37; // edx
  int v38; // r8d
  BCRYPT_KEY_HANDLE v39; // rbx
  __int64 v40; // r9
  int v42; // edx
  int v43; // r8d
  int v44; // edx
  int v45; // r8d
  ULONG Size; // [rsp+40h] [rbp-88h]
  int Size_4; // [rsp+44h] [rbp-84h] BYREF
  char v48; // [rsp+4Ah] [rbp-7Eh]
  PUCHAR pbInput; // [rsp+50h] [rbp-78h]
  _DWORD v50[2]; // [rsp+58h] [rbp-70h] BYREF
  PVOID v51; // [rsp+60h] [rbp-68h]
  size_t v52; // [rsp+68h] [rbp-60h]
  PVOID P; // [rsp+70h] [rbp-58h]
  __int64 v54; // [rsp+78h] [rbp-50h]
  _DWORD v55[2]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD *v56; // [rsp+88h] [rbp-40h]

  v6 = a4;
  if ( a1 && (v54 = *(_QWORD *)(a1 + 32)) != 0 && (v9 = *(_QWORD *)(a1 + 16)) != 0 && a2 && a6 )
  {
    v10 = *(wchar_t **)(v9 + 136);
    Size = 0;
    pbInput = 0;
    if ( !v10 || !*v10 )
      v10 = L"SHA256";
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= g_dwHashInfoTotalCount )
        goto LABEL_15;
      v12 = (const wchar_t **)g_pHashInfo[i];
      v13 = &g_pHashInfo[i];
      if ( v12 )
      {
        if ( *v12 && !wcsnicmp(v10, *v12, 0x40u) )
          break;
      }
    }
    _mm_lfence();
    if ( !*v13 )
    {
LABEL_15:
      v14 = 0;
      goto LABEL_16;
    }
    v14 = *(_DWORD *)(*v13 + 8);
    Size = v14;
    pbInput = (PUCHAR)v10;
LABEL_16:
    if ( a3 )
    {
      if ( (_BYTE)v6 )
        goto LABEL_18;
    }
    else if ( !(_BYTE)v6 )
    {
LABEL_18:
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x70u);
      v16 = (BCRYPT_KEY_HANDLE *)Heap;
      if ( !Heap )
      {
        SymmetricKey = -2146893810;
        DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4104);
        return SymmetricKey;
      }
      *(_OWORD *)(Heap + 8) = 0;
      *(_OWORD *)(Heap + 24) = 0;
      v17 = v14;
      *(_OWORD *)(Heap + 40) = 0;
      *(_OWORD *)(Heap + 56) = 0;
      *(_OWORD *)(Heap + 72) = 0;
      *(_OWORD *)(Heap + 88) = 0;
      *((_QWORD *)Heap + 13) = 0;
      *(_DWORD *)Heap = 112;
      *((_DWORD *)Heap + 1) = 1936944179;
      *((_DWORD *)Heap + 2) = *(_DWORD *)(a1 + 8);
      *((_DWORD *)Heap + 27) = a5;
      *((_QWORD *)Heap + 2) = v9;
      pbSecret = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      if ( !pbSecret )
      {
        SymmetricKey = -2146893810;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v18,
            v19,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            23);
LABEL_34:
        MSCryptFree(v16);
        if ( pbSecret )
        {
LABEL_35:
          for ( j = pbSecret; v17; --v17 )
            *j++ = 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pbSecret);
        }
        return SymmetricKey;
      }
      v48 = aTls13[6];
      v52 = strnlen_s(a2, v18);
      v50[0] = 0;
      v50[1] = 20;
      v23 = v52 + 6;
      v51 = 0;
      v55[0] = 0;
      v56 = v50;
      v55[1] = 1;
      Size_4 = 0;
      if ( (_BYTE)v52 == 0xF9 )
        goto LABEL_68;
      if ( a3 )
      {
        if ( !(_BYTE)v6 )
          goto LABEL_68;
      }
      else if ( (_BYTE)v6 )
      {
        goto LABEL_68;
      }
      if ( (_WORD)Size )
      {
        v24 = (unsigned __int16)(v6 + 4 + v23);
        P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
        v27 = (char *)P;
        if ( P )
        {
          *((_BYTE *)P + 1) = Size;
          v27[2] = v23;
          v28 = (unsigned __int8)v52;
          v29 = (unsigned __int8)v52;
          *v27 = BYTE1(Size);
          *(_DWORD *)(v27 + 3) = *(_DWORD *)"tls13 ";
          v30 = v27 + 9;
          *(_WORD *)(v27 + 7) = *(_WORD *)"3 ";
          memmove(v27 + 9, a2, v29);
          v30[v28] = v6;
          memmove(&v30[v28 + 1], a3, v6);
          v31 = P;
          v50[0] = v24;
          v51 = P;
          SymmetricKey = BCryptKeyDerivation(v54, v55, pbSecret, (unsigned __int16)Size, &Size_4, 0);
          if ( (SymmetricKey || Size_4 != (unsigned __int16)Size)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v33,
              (unsigned int)"Status",
              SymmetricKey,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              195);
          }
          v36 = v31;
          do
          {
            *v36++ = 0;
            --v24;
          }
          while ( v24 );
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v31);
          if ( (SymmetricKey & 0x80000000) == 0 )
          {
            SymmetricKey = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x391, v16 + 4, 0, 0, pbSecret, Size, 0);
            if ( SymmetricKey )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v37,
                  v38,
                  (unsigned int)"Status",
                  SymmetricKey,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                  50);
              }
            }
            else
            {
              v39 = v16[4];
              v40 = -1;
              while ( *(_WORD *)&pbInput[2 * v40++ + 2] != 0 )
                ;
              SymmetricKey = BCryptSetProperty(v39, L"HkdfHashAlgorithm", pbInput, 2 * v40 + 2, 0);
              if ( SymmetricKey )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v42,
                    v43,
                    (unsigned int)"Status",
                    SymmetricKey,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                    64);
                }
              }
              else
              {
                SymmetricKey = BCryptSetProperty(v39, L"HkdfPrkAndFinalize", 0, 0, 0);
                if ( !SymmetricKey )
                {
                  *a6 = v16;
                  goto LABEL_35;
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v44,
                    v45,
                    (unsigned int)"Status",
                    SymmetricKey,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                    75);
                }
              }
              if ( v39 )
                BCryptDestroyKey(v39);
            }
            goto LABEL_34;
          }
        }
        else
        {
          SymmetricKey = -1073741801;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v25,
              v26,
              (unsigned int)"Status",
              23,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              169);
        }
        goto LABEL_33;
      }
LABEL_68:
      SymmetricKey = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          v22,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          150);
LABEL_33:
      DebugTraceError(SymmetricKey, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4131);
      goto LABEL_34;
    }
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4095);
    return 2148073511LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        240);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x1800037a0  mov     r11, rsp
0x1800037a3  mov     [r11+10h], rdx
0x1800037a7  push    rbp
0x1800037a8  push    rdi
0x1800037a9  push    r12
0x1800037ab  push    r13
0x1800037ad  push    r15
0x1800037af  sub     rsp, 0A0h
0x1800037b6  movzx   r12d, r9b
0x1800037ba  mov     r13, r8
0x1800037bd  mov     rbp, rcx
0x1800037c0  test    rcx, rcx
0x1800037c3  jz      loc_180003D9D
0x1800037c9  mov     rax, [rcx+20h]
0x1800037cd  mov     [rsp+0C8h+var_50], rax
0x1800037d2  test    rax, rax
0x1800037d5  jz      loc_180003D9D
0x1800037db  mov     r15, [rcx+10h]
0x1800037df  test    r15, r15
0x1800037e2  jz      loc_180003D9D
0x1800037e8  test    rdx, rdx
0x1800037eb  jz      loc_180003D9D
0x1800037f1  cmp     [rsp+0C8h+arg_28], 0
0x1800037fa  jz      loc_180003D9D
0x180003800  xor     edi, edi
0x180003802  mov     [r11+18h], rbx
0x180003806  mov     [r11-30h], rsi
0x18000380a  mov     rsi, [r15+88h]
0x180003811  mov     [r11-38h], r14
0x180003815  mov     dword ptr [rsp+0C8h+Size], edi
0x180003819  mov     [rsp+0C8h+pbInput], rdi
0x18000381e  test    rsi, rsi
0x180003821  jz      loc_180003D91
0x180003827  cmp     [rsi], di
0x18000382a  jz      loc_180003D91
0x180003830  xor     ebx, ebx
0x180003832  lea     r14, g_pHashInfo
0x180003839  nop     dword ptr [rax+00000000h]
0x180003840  cmp     ebx, cs:g_dwHashInfoTotalCount
0x180003846  jnb     short loc_180003882
0x180003848  mov     rax, [r14+rbx*8]
0x18000384c  lea     rdi, [r14+rbx*8]
0x180003850  test    rax, rax
0x180003853  jz      short loc_18000386F
0x180003855  mov     rdx, [rax]; String2
0x180003858  test    rdx, rdx
0x18000385b  jz      short loc_18000386F
0x18000385d  mov     r8d, 40h ; '@'; MaxCount
0x180003863  mov     rcx, rsi; String1
0x180003866  call    _wcsnicmp
0x18000386b  test    eax, eax
0x18000386d  jz      short loc_180003873
0x18000386f  inc     ebx
0x180003871  jmp     short loc_180003840
0x180003873  lfence
0x180003876  mov     rax, [rdi]
0x180003879  test    rax, rax
0x18000387c  jnz     loc_180003AE7
0x180003882  mov     edi, dword ptr [rsp+0C8h+Size]
0x180003886  test    r13, r13
0x180003889  jz      loc_180003E31
0x18000388f  test    r12b, r12b
0x180003892  jz      loc_180003E3A
0x180003898  mov     rcx, gs:60h
0x1800038a1  xor     edx, edx; Flags
0x1800038a3  mov     r8d, 70h ; 'p'; Size
0x1800038a9  mov     rcx, [rcx+30h]; HeapHandle
0x1800038ad  call    cs:__imp_RtlAllocateHeap
0x1800038b3  mov     r14, rax
0x1800038b6  test    rax, rax
0x1800038b9  jz      loc_180003E62
0x1800038bf  xorps   xmm0, xmm0
0x1800038c2  mov     r8d, edi; Size
0x1800038c5  movups  xmmword ptr [r14+8], xmm0
0x1800038ca  xor     eax, eax
0x1800038cc  xor     edx, edx; Flags
0x1800038ce  movups  xmmword ptr [r14+18h], xmm0
0x1800038d3  mov     esi, edi
0x1800038d5  movups  xmmword ptr [r14+28h], xmm0
0x1800038da  movups  xmmword ptr [r14+38h], xmm0
0x1800038df  movups  xmmword ptr [r14+48h], xmm0
0x1800038e4  movups  xmmword ptr [r14+58h], xmm0
0x1800038e9  mov     [r14+68h], rax
0x1800038ed  mov     dword ptr [r14], 70h ; 'p'
0x1800038f4  mov     dword ptr [r14+4], 73736C33h
0x1800038fc  mov     eax, [rbp+8]
0x1800038ff  mov     [r14+8], eax
0x180003903  mov     eax, [rsp+0C8h+arg_20]
0x18000390a  mov     [r14+6Ch], eax
0x18000390e  mov     [r14+10h], r15
0x180003912  mov     rcx, gs:60h
0x18000391b  mov     rcx, [rcx+30h]; HeapHandle
0x18000391f  call    cs:__imp_RtlAllocateHeap
0x180003925  mov     r15, rax
0x180003928  test    rax, rax
0x18000392b  jz      loc_180003B9F
0x180003931  movzx   eax, word ptr cs:aTls13+4; "3 "
0x180003938  mov     rcx, [rsp+0C8h+String]; String
0x180003940  mov     edi, dword ptr cs:aTls13; "tls13 "
0x180003946  mov     [rsp+0C8h+arg_0], ax
0x18000394e  movzx   eax, byte ptr cs:aTls13+6; ""
0x180003955  mov     [rsp+0C8h+var_7E], al
0x180003959  call    strnlen_s
0x18000395e  xor     ecx, ecx
0x180003960  mov     [rsp+0C8h+var_60], rax
0x180003965  mov     [rsp+0C8h+var_70], ecx
0x180003969  mov     [rsp+0C8h+var_6C], 14h
0x180003971  lea     ebx, [rax+6]
0x180003974  mov     [rsp+0C8h+var_68], rcx
0x180003979  mov     [rsp+0C8h+var_48], ecx
0x180003980  lea     rax, [rsp+0C8h+var_70]
0x180003985  mov     [rsp+0C8h+var_40], rax
0x18000398d  mov     [rsp+0C8h+var_44], 1
0x180003998  mov     dword ptr [rsp+0C8h+Size+4], ecx
0x18000399c  cmp     bl, 0FFh
0x18000399f  jnb     loc_180003DCF
0x1800039a5  test    r13, r13
0x1800039a8  jz      loc_180003E26
0x1800039ae  test    r12b, r12b
0x1800039b1  jz      loc_180003DCF
0x1800039b7  cmp     word ptr [rsp+0C8h+Size], cx
0x1800039bc  jz      loc_180003DCF
0x1800039c2  movzx   ecx, bl
0x1800039c5  lea     eax, [r12+4]
0x1800039ca  add     cx, ax
0x1800039cd  xor     edx, edx; Flags
0x1800039cf  movzx   ebp, cx
0x1800039d2  mov     rcx, gs:60h
0x1800039db  mov     r8d, ebp; Size
0x1800039de  mov     rcx, [rcx+30h]; HeapHandle
0x1800039e2  call    cs:__imp_RtlAllocateHeap
0x1800039e8  mov     [rsp+0C8h+P], rax
0x1800039ed  mov     rcx, rax
0x1800039f0  test    rax, rax
0x1800039f3  jz      loc_180003AF8
0x1800039f9  mov     edx, dword ptr [rsp+0C8h+Size]
0x1800039fd  movzx   eax, dx
0x180003a00  mov     [rcx+1], dl
0x180003a03  mov     rdx, [rsp+0C8h+String]; Src
0x180003a0b  mov     [rcx+2], bl
0x180003a0e  movzx   ebx, byte ptr [rsp+0C8h+var_60]
0x180003a13  shr     ax, 8
0x180003a17  mov     r8d, ebx; Size
0x180003a1a  mov     [rcx], al
0x180003a1c  movzx   eax, [rsp+0C8h+arg_0]
0x180003a24  mov     [rcx+3], edi
0x180003a27  lea     rdi, [rcx+9]
0x180003a2b  mov     [rcx+7], ax
0x180003a2f  mov     rcx, rdi; void *
0x180003a32  call    memmove
0x180003a37  lea     rcx, [rbx+1]
0x180003a3b  mov     [rbx+rdi], r12b
0x180003a3f  add     rcx, rdi; void *
0x180003a42  mov     r8, r12; Size
0x180003a45  mov     rdx, r13; Src
0x180003a48  call    memmove
0x180003a4d  mov     r13d, dword ptr [rsp+0C8h+Size]
0x180003a52  lea     rax, [rsp+0C8h+Size+4]
0x180003a57  mov     r12, [rsp+0C8h+P]
0x180003a5c  lea     rdx, [rsp+0C8h+var_48]
0x180003a64  mov     rcx, [rsp+0C8h+var_50]
0x180003a69  mov     r8, r15
0x180003a6c  movzx   ebx, r13w
0x180003a70  mov     r9d, ebx
0x180003a73  mov     [rsp+0C8h+cbSecret], 0
0x180003a7b  mov     [rsp+0C8h+var_70], ebp
0x180003a7f  mov     [rsp+0C8h+var_68], r12
0x180003a84  mov     [rsp+0C8h+pbSecret], rax
0x180003a89  call    cs:__imp_BCryptKeyDerivation
0x180003a8f  mov     edi, eax
0x180003a91  lea     rdx, WPP_GLOBAL_Control
0x180003a98  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003a9f  test    edi, edi
0x180003aa1  jz      loc_180003BF2
0x180003aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003aae  cmp     rcx, rdx
0x180003ab1  jz      loc_180003BFC
0x180003ab7  test    byte ptr [rcx+1Ch], 1
0x180003abb  jz      loc_180003BFC
0x180003ac1  mov     rcx, [rcx+10h]
0x180003ac5  lea     r9, aStatus; "Status"
0x180003acc  mov     [rsp+0C8h+dwFlags], 0FC3h
0x180003ad4  mov     qword ptr [rsp+0C8h+cbSecret], rax
0x180003ad9  mov     dword ptr [rsp+0C8h+pbSecret], edi
0x180003add  call    WPP_SF_sDsd
0x180003ae2  jmp     loc_180003BFC
0x180003ae7  mov     edi, [rax+8]
0x180003aea  mov     dword ptr [rsp+0C8h+Size], edi
0x180003aee  mov     [rsp+0C8h+pbInput], rsi
0x180003af3  jmp     loc_180003886
0x180003af8  mov     edi, 0C0000017h
0x180003afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b04  lea     rax, WPP_GLOBAL_Control
0x180003b0b  cmp     rcx, rax
0x180003b0e  jz      short loc_180003B1A
0x180003b10  test    byte ptr [rcx+1Ch], 1
0x180003b14  jnz     loc_180003E8A
0x180003b1a  lea     rbp, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003b21  mov     r9d, 1023h
0x180003b27  lea     rdx, aStatus; "Status"
0x180003b2e  mov     r8, rbp
0x180003b31  mov     ecx, edi
0x180003b33  call    DebugTraceError
0x180003b38  mov     rcx, r14
0x180003b3b  call    MSCryptFree
0x180003b40  test    r15, r15
0x180003b43  jz      short loc_180003B75
0x180003b45  mov     rax, r15
0x180003b48  test    rsi, rsi
0x180003b4b  jz      short loc_180003B5D
0x180003b4d  nop     dword ptr [rax]
0x180003b50  mov     byte ptr [rax], 0
0x180003b53  lea     rax, [rax+1]
0x180003b57  sub     rsi, 1
0x180003b5b  jnz     short loc_180003B50
0x180003b5d  mov     rcx, gs:60h
0x180003b66  mov     r8, r15; P
0x180003b69  xor     edx, edx; Flags
0x180003b6b  mov     rcx, [rcx+30h]; HeapHandle
0x180003b6f  call    cs:__imp_RtlFreeHeap
0x180003b75  mov     eax, edi
0x180003b77  mov     rsi, [rsp+0C8h+var_30]
0x180003b7f  mov     rbx, [rsp+0C8h+arg_10]
0x180003b87  mov     r14, [rsp+0C8h+var_38]
0x180003b8f  add     rsp, 0A0h
0x180003b96  pop     r15
0x180003b98  pop     r13
0x180003b9a  pop     r12
0x180003b9c  pop     rdi
0x180003b9d  pop     rbp
0x180003b9e  retn
0x180003b9f  mov     edi, 8009000Eh
0x180003ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bab  lea     rax, WPP_GLOBAL_Control
0x180003bb2  cmp     rcx, rax
0x180003bb5  jz      short loc_180003B38
0x180003bb7  test    byte ptr [rcx+1Ch], 1
0x180003bbb  jz      loc_180003B38
0x180003bc1  mov     [rsp+0C8h+dwFlags], 1017h
0x180003bc9  lea     rbp, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003bd0  mov     qword ptr [rsp+0C8h+cbSecret], rbp
0x180003bd5  mov     dword ptr [rsp+0C8h+pbSecret], 8009000Eh
0x180003bdd  mov     rcx, [rcx+10h]
0x180003be1  lea     r9, aStatus; "Status"
0x180003be8  call    WPP_SF_sDsd
0x180003bed  jmp     loc_180003B38
0x180003bf2  cmp     dword ptr [rsp+0C8h+Size+4], ebx
0x180003bf6  jnz     loc_180003AA7
0x180003bfc  mov     rax, r12
0x180003bff  nop
0x180003c00  mov     byte ptr [rax], 0
0x180003c03  lea     rax, [rax+1]
0x180003c07  sub     rbp, 1
0x180003c0b  jnz     short loc_180003C00
0x180003c0d  mov     rcx, gs:60h
0x180003c16  mov     r8, r12; P
0x180003c19  xor     edx, edx; Flags
0x180003c1b  mov     rcx, [rcx+30h]; HeapHandle
0x180003c1f  call    cs:__imp_RtlFreeHeap
0x180003c25  test    edi, edi
0x180003c27  js      loc_180003B1A
0x180003c2d  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x180003c31  lea     rdx, [r14+20h]; phKey
0x180003c35  mov     [rsp+0C8h+cbSecret], r13d; cbSecret
0x180003c3a  xor     r9d, r9d; cbKeyObject
0x180003c3d  xor     r8d, r8d; pbKeyObject
0x180003c40  mov     [rsp+0C8h+pbSecret], r15; pbSecret
0x180003c45  mov     ecx, 391h; hAlgorithm
0x180003c4a  call    cs:__imp_BCryptGenerateSymmetricKey
0x180003c50  mov     edi, eax
0x180003c52  test    eax, eax
0x180003c54  jnz     loc_180003D2D
0x180003c5a  mov     rbx, [r14+20h]
0x180003c5e  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180003c65  mov     rax, [rsp+0C8h+pbInput]
0x180003c6a  nop     word ptr [rax+rax+00h]
0x180003c70  cmp     [rax+r9*2+2], bp
0x180003c76  lea     r9, [r9+1]
0x180003c7a  jnz     short loc_180003C70
0x180003c7c  lea     r9d, ds:2[r9*2]; cbInput
0x180003c84  mov     dword ptr [rsp+0C8h+pbSecret], ebp; dwFlags
0x180003c88  mov     r8, rax; pbInput
0x180003c8b  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x180003c92  mov     rcx, rbx; hObject
0x180003c95  call    cs:__imp_BCryptSetProperty
0x180003c9b  mov     edi, eax
0x180003c9d  test    eax, eax
0x180003c9f  jnz     short loc_180003CD5
0x180003ca1  xor     r9d, r9d; cbInput
0x180003ca4  mov     dword ptr [rsp+0C8h+pbSecret], ebp; dwFlags
0x180003ca8  xor     r8d, r8d; pbInput
0x180003cab  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x180003cb2  mov     rcx, rbx; hObject
0x180003cb5  call    cs:__imp_BCryptSetProperty
0x180003cbb  mov     edi, eax
0x180003cbd  test    eax, eax
0x180003cbf  jnz     loc_180003D6B
0x180003cc5  mov     rax, [rsp+0C8h+arg_28]
0x180003ccd  mov     [rax], r14
0x180003cd0  jmp     loc_180003B45
  ... truncated ...
```
