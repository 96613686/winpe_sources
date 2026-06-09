# _AlertDataCollector::get_AlertThresholds(tagSAFEARRAY * *)

- ea: `0x18007a080`
- end: `0x18007a85f`
- name: `?get_AlertThresholds@_AlertDataCollector@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `2015`
- prototype: `__int64 __fastcall(_AlertDataCollector *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18002b3a0`
- `0x18007a080`
- `0x180116404`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a7df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a7df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a263`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a263`
- `pdh!PdhTranslateLocaleCounterW` at `0x18007a4cf`
- `pdh!PdhTranslateLocaleCounterW` at `0x18007a4cf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18007a82d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18007a82d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007a284`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007a3cf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007a284`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007a3cf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007a804`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007a817`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007a804`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007a817`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007a33e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007a33e`

## pseudocode

```c
__int64 __fastcall _AlertDataCollector::get_AlertThresholds(_AlertDataCollector *this, struct tagSAFEARRAY **a2)
{
  int v2; // eax
  int v3; // ebx
  SAFEARRAY *v6; // r12
  unsigned __int16 *v7; // r13
  __int64 v8; // rdi
  struct tagSAFEARRAY ***v9; // r9
  struct tagSAFEARRAY ***v10; // rax
  SAFEARRAY *v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rdi
  SAFEARRAY *Vector; // rax
  __int64 v15; // rdi
  HRESULT v16; // eax
  __int64 v17; // rdi
  unsigned int v18; // r13d
  __int64 v19; // rdi
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int16 *i; // r15
  unsigned __int16 v23; // bx
  unsigned __int16 *v24; // rdx
  unsigned int v25; // eax
  int v26; // eax
  const char *v27; // rdx
  int v28; // r8d
  unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // r8
  unsigned __int16 *v31; // r15
  int v32; // eax
  const char *v33; // rdx
  int v34; // r8d
  unsigned __int16 *v35; // rax
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+70h] [rbp-90h] BYREF
  struct tagSAFEARRAY **v39; // [rsp+78h] [rbp-88h] BYREF
  void *v40; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v41; // [rsp+88h] [rbp-78h]
  _AlertDataCollector *v42; // [rsp+90h] [rbp-70h] BYREF
  void *ppvData; // [rsp+98h] [rbp-68h] BYREF
  int v44[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v45[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v46[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v47[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v48[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v49[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v50[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v51[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v52[64]; // [rsp+430h] [rbp+330h] BYREF

  v2 = *((_DWORD *)this + 14);
  v3 = 0;
  v39 = a2;
  v44[0] = 0;
  v6 = 0;
  ppvData = 0;
  v40 = 0;
  v38 = v2;
  v42 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      &PLA_EVENT_METHOD,
      3,
      "_AlertDataCollector::get_AlertThresholds",
      41,
      &v42,
      8,
      &v38,
      4);
  }
  v41 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v37);
  v7 = v41;
  if ( v41 )
  {
    if ( *((_DWORD *)this + 2) )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v11 = (SAFEARRAY *)*((_QWORD *)this + 20);
    if ( !v11 )
    {
      *a2 = 0;
      goto LABEL_80;
    }
    v12 = SafeArrayAccessData(v11, &ppvData);
    v3 = v12;
    if ( v12 >= 0 )
    {
      Vector = SafeArrayCreateVector(8u, 0, *(_DWORD *)(*((_QWORD *)this + 20) + 24LL));
      v42 = (_AlertDataCollector *)Vector;
      v6 = Vector;
      if ( Vector )
      {
        v16 = SafeArrayAccessData(Vector, &v40);
        v3 = v16;
        if ( v16 >= 0 )
        {
          v18 = 0;
          v19 = -1;
          while ( v18 < *(_DWORD *)(*((_QWORD *)this + 20) + 24LL) )
          {
            v20 = *((_QWORD *)ppvData + v18);
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)(v20 + 2 * v21) );
            for ( i = (unsigned __int16 *)(v20 + 2 * (v21 - 1)); (unsigned __int64)i > v20; --i )
            {
              if ( *i == 62 )
                goto LABEL_48;
              if ( *i == 60 )
                break;
            }
            if ( (unsigned __int64)i <= v20 )
            {
              v3 = -2147467259;
              LODWORD(v39) = 0;
              v38 = -2147467259;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v52, 0x4000000000000800uLL);
                do
                  ++v19;
                while ( v52[v19] );
LABEL_55:
                EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v38, 4, byte_180147320, 1, &v39, 4);
              }
LABEL_56:
              v6 = (SAFEARRAY *)v42;
              goto LABEL_79;
            }
LABEL_48:
            v23 = *i;
            v24 = v41;
            *i = 0;
            v44[0] = 1024;
            v25 = PdhTranslateLocaleCounterW(*((_QWORD *)ppvData + v18), v24, v44);
            v26 = PlaiHResultFromWin32(v25);
            *i = v23;
            if ( v26 >= 0 )
            {
              v30 = i;
              v31 = v41;
              v32 = StringCchCatW(v41, 0x400u, v30);
              v3 = v32;
              if ( v32 < 0 )
              {
                v38 = v32;
                LODWORD(v39) = 0;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v51, 0x4000000000000800uLL);
                  do
                    ++v19;
                  while ( v51[v19] );
                  goto LABEL_55;
                }
                goto LABEL_56;
              }
              PlaiFreeString(*((BSTR *)v40 + v18));
              *((_QWORD *)v40 + v18) = 0;
              v35 = PlaiAllocStringEx(v31, v33, v34);
              *((_QWORD *)v40 + v18) = v35;
              if ( !*((_QWORD *)v40 + v18) )
              {
                v3 = -2147024882;
                v38 = -2147024882;
                LODWORD(v39) = 0;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v50, 0x4000000000000800uLL);
                  do
                    ++v19;
                  while ( v50[v19] );
                  goto LABEL_55;
                }
                goto LABEL_56;
              }
            }
            else
            {
              PlaiFreeString(*((BSTR *)v40 + v18));
              *((_QWORD *)v40 + v18) = 0;
              v29 = PlaiAllocStringEx(*((const unsigned __int16 **)ppvData + v18), v27, v28);
              *((_QWORD *)v40 + v18) = v29;
              if ( !*((_QWORD *)v40 + v18) )
              {
                v3 = -2147024882;
                v38 = -2147024882;
                LODWORD(v39) = 0;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v49, 0x4000000000000800uLL);
                  do
                    ++v19;
                  while ( v49[v19] );
                  goto LABEL_55;
                }
                goto LABEL_56;
              }
            }
            ++v18;
          }
          v3 = 0;
          v6 = (SAFEARRAY *)v42;
          *v39 = (struct tagSAFEARRAY *)v42;
LABEL_79:
          v7 = v41;
          goto LABEL_80;
        }
        LODWORD(v39) = 0;
        v38 = v16;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_80;
        }
        PlaiWhoAmI(v48, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v48[v17] );
      }
      else
      {
        v3 = -2147024882;
        v38 = -2147024882;
        LODWORD(v39) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_80;
        }
        PlaiWhoAmI(v47, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v47[v15] );
      }
    }
    else
    {
      LODWORD(v39) = 0;
      v38 = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_80;
      }
      PlaiWhoAmI(v46, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v46[v13] );
    }
    v9 = (struct tagSAFEARRAY ***)&v38;
    v10 = &v39;
LABEL_12:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v9, 4, byte_180147320, 1, v10, 4);
    goto LABEL_80;
  }
  v3 = -2147024882;
  v38 = 0;
  LODWORD(v39) = -2147024882;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v45, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v45[v8] );
    v9 = &v39;
    v10 = (struct tagSAFEARRAY ***)&v38;
    goto LABEL_12;
  }
LABEL_80:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v7 )
    PlaiFree(v7, 1);
  if ( ppvData )
  {
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 20));
    ppvData = 0;
  }
  if ( v40 )
  {
    SafeArrayUnaccessData(v6);
    v40 = 0;
  }
  if ( v3 < 0 && v6 )
    SafeArrayDestroy(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007a080  mov     [rsp-8+arg_10], rbx
0x18007a085  push    rbp
0x18007a086  push    rsi
0x18007a087  push    rdi
0x18007a088  push    r12
0x18007a08a  push    r13
0x18007a08c  push    r14
0x18007a08e  push    r15
0x18007a090  lea     rbp, [rsp-3C0h]
0x18007a098  sub     rsp, 4C0h
0x18007a09f  mov     rax, cs:__security_cookie
0x18007a0a6  xor     rax, rsp
0x18007a0a9  mov     [rbp+3F0h+var_40], rax
0x18007a0b0  mov     eax, [rcx+38h]
0x18007a0b3  xor     ebx, ebx
0x18007a0b5  cmp     dword ptr cs:xmmword_180169738, ebx
0x18007a0bb  mov     r15, rdx
0x18007a0be  mov     [rsp+4F0h+var_478], rdx
0x18007a0c3  mov     r14, rcx
0x18007a0c6  mov     [rbp+3F0h+var_450], ebx
0x18007a0c9  mov     r12d, ebx
0x18007a0cc  lea     esi, [rbx+8]
0x18007a0cf  mov     [rbp+3F0h+ppvData], rbx
0x18007a0d3  mov     [rbp+3F0h+var_470], rbx
0x18007a0d7  mov     [rsp+4F0h+var_480], eax
0x18007a0db  mov     [rbp+3F0h+var_460], rcx
0x18007a0df  jz      short loc_18007A14F
0x18007a0e1  mov     rdx, 4000000000000400h
0x18007a0eb  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007a0f2  jz      short loc_18007A14F
0x18007a0f4  mov     rax, cs:qword_180169748
0x18007a0fb  and     rax, rdx
0x18007a0fe  cmp     cs:qword_180169748, rax
0x18007a105  jnz     short loc_18007A14F
0x18007a107  mov     [rsp+4F0h+var_4B0], 4
0x18007a110  lea     rax, [rsp+4F0h+var_480]
0x18007a115  mov     [rsp+4F0h+var_4B8], rax
0x18007a11a  lea     r9, aAlertdatacolle_8; "_AlertDataCollector::get_AlertThreshold"...
0x18007a121  lea     rax, [rbp+3F0h+var_460]
0x18007a125  mov     [rsp+4F0h+var_4C0], rsi
0x18007a12a  mov     [rsp+4F0h+var_4C8], rax
0x18007a12f  lea     r8d, [rbx+3]
0x18007a133  lea     rdx, PLA_EVENT_METHOD
0x18007a13a  mov     qword ptr [rsp+4F0h+var_4D0], 29h ; ')'; int
0x18007a143  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18007a14a  call    EventingWriteEvent
0x18007a14f  xor     r8d, r8d; int
0x18007a152  lea     r9, byte_180147320; char *
0x18007a159  mov     ecx, 800h; dwBytes
0x18007a15e  lea     edx, [r8+1]; int
0x18007a162  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18007a167  mov     [rbp+3F0h+var_468], rax
0x18007a16b  mov     r13, rax
0x18007a16e  test    rax, rax
0x18007a171  jnz     loc_18007A259
0x18007a177  xor     r15d, r15d
0x18007a17a  mov     eax, 8007000Eh
0x18007a17f  cmp     dword ptr cs:xmmword_180169738, r15d
0x18007a186  mov     ebx, eax
0x18007a188  mov     [rsp+4F0h+var_480], r15d
0x18007a18d  mov     dword ptr [rsp+4F0h+var_478], eax
0x18007a191  jz      loc_18007A7CF
0x18007a197  mov     rdx, 4000000000000800h; unsigned __int64
0x18007a1a1  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007a1a8  jz      loc_18007A7CF
0x18007a1ae  mov     rax, cs:qword_180169748
0x18007a1b5  and     rax, rdx
0x18007a1b8  cmp     cs:qword_180169748, rax
0x18007a1bf  jnz     loc_18007A7CF
0x18007a1c5  lea     rcx, [rbp+3F0h+var_440]; unsigned __int16 *
0x18007a1c9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007a1ce  lea     rax, [rbp+3F0h+var_440]
0x18007a1d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a1d6  inc     rdi
0x18007a1d9  cmp     [rax+rdi*2], r15w
0x18007a1de  jnz     short loc_18007A1D6
0x18007a1e0  lea     rax, [rbp+3F0h+var_440]
0x18007a1e4  lea     ecx, [rdi+rdi]
0x18007a1e7  add     rcx, 2
0x18007a1eb  lea     r9, [rsp+4F0h+var_478]
0x18007a1f0  mov     [rsp+4F0h+var_490], rcx
0x18007a1f5  mov     [rsp+4F0h+var_498], rax
0x18007a1fa  lea     rax, aAlertdatacolle_8; "_AlertDataCollector::get_AlertThreshold"...
0x18007a201  mov     [rsp+4F0h+var_4A0], 29h ; ')'
0x18007a20a  mov     [rsp+4F0h+var_4A8], rax
0x18007a20f  lea     rax, [rsp+4F0h+var_480]
0x18007a214  mov     ecx, 4
0x18007a219  lea     rdx, PLA_EVENT_ERROR
0x18007a220  mov     [rsp+4F0h+var_4B0], rcx
0x18007a225  mov     [rsp+4F0h+var_4B8], rax
0x18007a22a  lea     rax, byte_180147320
0x18007a231  mov     [rsp+4F0h+var_4C0], 1
0x18007a23a  mov     [rsp+4F0h+var_4C8], rax
0x18007a23f  lea     r8d, [rcx+1]
0x18007a243  mov     qword ptr [rsp+4F0h+var_4D0], rcx
0x18007a248  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18007a24f  call    EventingWriteEvent
0x18007a254  jmp     loc_18007A7CF
0x18007a259  cmp     [r14+8], ebx
0x18007a25d  jz      short loc_18007A269
0x18007a25f  lea     rcx, [r14+10h]; lpCriticalSection
0x18007a263  call    cs:__imp_EnterCriticalSection
0x18007a269  mov     rcx, [r14+0A0h]; psa
0x18007a270  test    rcx, rcx
0x18007a273  jnz     short loc_18007A280
0x18007a275  mov     [r15], rbx
0x18007a278  xor     r15d, r15d
0x18007a27b  jmp     loc_18007A7CF
0x18007a280  lea     rdx, [rbp+3F0h+ppvData]; ppvData
0x18007a284  call    cs:__imp_SafeArrayAccessData
0x18007a28a  xor     r15d, r15d
0x18007a28d  mov     ebx, eax
0x18007a28f  test    eax, eax
0x18007a291  jns     loc_18007A32F
0x18007a297  cmp     dword ptr cs:xmmword_180169738, r15d
0x18007a29e  mov     dword ptr [rsp+4F0h+var_478], r15d
0x18007a2a3  mov     [rsp+4F0h+var_480], eax
0x18007a2a7  jz      loc_18007A7CF
0x18007a2ad  mov     rdx, 4000000000000800h; unsigned __int64
0x18007a2b7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007a2be  jz      loc_18007A7CF
0x18007a2c4  mov     rax, cs:qword_180169748
0x18007a2cb  and     rax, rdx
0x18007a2ce  cmp     cs:qword_180169748, rax
0x18007a2d5  jnz     loc_18007A7CF
0x18007a2db  lea     rcx, [rbp+3F0h+var_3C0]; unsigned __int16 *
0x18007a2df  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007a2e4  lea     rax, [rbp+3F0h+var_3C0]
0x18007a2e8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a2ec  inc     rdi
0x18007a2ef  cmp     [rax+rdi*2], r15w
0x18007a2f4  jnz     short loc_18007A2EC
0x18007a2f6  lea     rax, [rbp+3F0h+var_3C0]
0x18007a2fa  lea     ecx, [rdi+rdi]
0x18007a2fd  add     rcx, 2
0x18007a301  lea     r9, [rsp+4F0h+var_480]
0x18007a306  mov     [rsp+4F0h+var_490], rcx
0x18007a30b  mov     [rsp+4F0h+var_498], rax
0x18007a310  lea     rax, aAlertdatacolle_8; "_AlertDataCollector::get_AlertThreshold"...
0x18007a317  mov     [rsp+4F0h+var_4A0], 29h ; ')'
0x18007a320  mov     [rsp+4F0h+var_4A8], rax
0x18007a325  lea     rax, [rsp+4F0h+var_478]
0x18007a32a  jmp     loc_18007A214
0x18007a32f  mov     r8, [r14+0A0h]
0x18007a336  mov     ecx, esi; vt
0x18007a338  xor     edx, edx; lLbound
0x18007a33a  mov     r8d, [r8+18h]; cElements
0x18007a33e  call    cs:__imp_SafeArrayCreateVector
0x18007a344  mov     [rbp+3F0h+var_460], rax
0x18007a348  mov     r12, rax
0x18007a34b  test    rax, rax
0x18007a34e  jnz     short loc_18007A3C8
0x18007a350  cmp     dword ptr cs:xmmword_180169738, r15d
0x18007a357  mov     eax, 8007000Eh
0x18007a35c  mov     ebx, eax
0x18007a35e  mov     [rsp+4F0h+var_480], eax
0x18007a362  mov     dword ptr [rsp+4F0h+var_478], r15d
0x18007a367  jz      loc_18007A7CF
0x18007a36d  mov     rdx, 4000000000000800h; unsigned __int64
0x18007a377  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007a37e  jz      loc_18007A7CF
0x18007a384  mov     rax, cs:qword_180169748
0x18007a38b  and     rax, rdx
0x18007a38e  cmp     cs:qword_180169748, rax
0x18007a395  jnz     loc_18007A7CF
0x18007a39b  lea     rcx, [rbp+3F0h+var_340]; unsigned __int16 *
0x18007a3a2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007a3a7  lea     rax, [rbp+3F0h+var_340]
0x18007a3ae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a3b2  inc     rdi
0x18007a3b5  cmp     [rax+rdi*2], r15w
0x18007a3ba  jnz     short loc_18007A3B2
0x18007a3bc  lea     rax, [rbp+3F0h+var_340]
0x18007a3c3  jmp     loc_18007A2FA
0x18007a3c8  lea     rdx, [rbp+3F0h+var_470]; ppvData
0x18007a3cc  mov     rcx, rax; psa
0x18007a3cf  call    cs:__imp_SafeArrayAccessData
0x18007a3d5  mov     ebx, eax
0x18007a3d7  test    eax, eax
0x18007a3d9  jns     short loc_18007A44C
0x18007a3db  cmp     dword ptr cs:xmmword_180169738, r15d
0x18007a3e2  mov     dword ptr [rsp+4F0h+var_478], r15d
0x18007a3e7  mov     [rsp+4F0h+var_480], eax
0x18007a3eb  jz      loc_18007A7CF
0x18007a3f1  mov     rdx, 4000000000000800h; unsigned __int64
0x18007a3fb  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007a402  jz      loc_18007A7CF
0x18007a408  mov     rax, cs:qword_180169748
0x18007a40f  and     rax, rdx
0x18007a412  cmp     cs:qword_180169748, rax
0x18007a419  jnz     loc_18007A7CF
0x18007a41f  lea     rcx, [rbp+3F0h+var_2C0]; unsigned __int16 *
0x18007a426  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007a42b  lea     rax, [rbp+3F0h+var_2C0]
0x18007a432  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a436  inc     rdi
0x18007a439  cmp     [rax+rdi*2], r15w
0x18007a43e  jnz     short loc_18007A436
0x18007a440  lea     rax, [rbp+3F0h+var_2C0]
0x18007a447  jmp     loc_18007A2FA
0x18007a44c  mov     r13d, r15d
0x18007a44f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a453  mov     rax, [r14+0A0h]
0x18007a45a  cmp     r13d, [rax+18h]
0x18007a45e  jnb     loc_18007A7BC
0x18007a464  mov     rax, [rbp+3F0h+ppvData]
0x18007a468  mov     r12d, r13d
0x18007a46b  mov     rcx, [rax+r12*8]
0x18007a46f  mov     rax, rdi
0x18007a472  inc     rax
0x18007a475  cmp     [rcx+rax*2], r15w
0x18007a47a  jnz     short loc_18007A472
0x18007a47c  lea     r15, [rax-1]
0x18007a480  lea     r15, [rcx+r15*2]
0x18007a484  jmp     short loc_18007A4A0
0x18007a486  mov     eax, 3Eh ; '>'
0x18007a48b  cmp     ax, [r15]
0x18007a48f  jz      short loc_18007A4AE
0x18007a491  mov     eax, 3Ch ; '<'
0x18007a496  cmp     ax, [r15]
0x18007a49a  jz      short loc_18007A4A5
0x18007a49c  sub     r15, 2
0x18007a4a0  cmp     r15, rcx
0x18007a4a3  ja      short loc_18007A486
0x18007a4a5  cmp     r15, rcx
0x18007a4a8  jbe     loc_18007A747
0x18007a4ae  movzx   ebx, word ptr [r15]
0x18007a4b2  lea     r8, [rbp+3F0h+var_450]
0x18007a4b6  mov     rdx, [rbp+3F0h+var_468]
0x18007a4ba  xor     eax, eax
0x18007a4bc  mov     [r15], ax
0x18007a4c0  mov     rcx, [rbp+3F0h+ppvData]
0x18007a4c4  mov     [rbp+3F0h+var_450], 400h
0x18007a4cb  mov     rcx, [rcx+r12*8]
0x18007a4cf  call    cs:__imp_PdhTranslateLocaleCounterW
0x18007a4d5  mov     ecx, eax; unsigned int
0x18007a4d7  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18007a4dc  mov     [r15], bx
0x18007a4e0  test    eax, eax
0x18007a4e2  jns     loc_18007A60B
0x18007a4e8  mov     rcx, [rbp+3F0h+var_470]
0x18007a4ec  mov     rcx, [rcx+r12*8]; bstrString
0x18007a4f0  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18007a4f5  mov     rax, [rbp+3F0h+var_470]
0x18007a4f9  xor     r15d, r15d
0x18007a4fc  mov     [rax+r12*8], r15
0x18007a500  mov     rcx, [rbp+3F0h+ppvData]
0x18007a504  mov     rcx, [rcx+r12*8]; unsigned __int16 *
0x18007a508  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18007a50d  mov     rcx, [rbp+3F0h+var_470]
0x18007a511  mov     [rcx+r12*8], rax
0x18007a515  mov     rax, [rbp+3F0h+var_470]
0x18007a519  cmp     [rax+r12*8], r15
0x18007a51d  jnz     loc_18007A65F
0x18007a523  cmp     dword ptr cs:xmmword_180169738, r15d
0x18007a52a  mov     eax, 8007000Eh
0x18007a52f  mov     ebx, eax
0x18007a531  mov     [rsp+4F0h+var_480], eax
0x18007a535  mov     dword ptr [rsp+4F0h+var_478], r15d
0x18007a53a  jz      loc_18007A602
0x18007a540  mov     rdx, 4000000000000800h; unsigned __int64
0x18007a54a  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007a551  jz      loc_18007A602
0x18007a557  mov     rax, cs:qword_180169748
0x18007a55e  and     rax, rdx
0x18007a561  cmp     cs:qword_180169748, rax
0x18007a568  jnz     loc_18007A602
0x18007a56e  lea     rcx, [rbp+3F0h+var_240]; unsigned __int16 *
0x18007a575  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007a57a  lea     rax, [rbp+3F0h+var_240]
0x18007a581  inc     rdi
0x18007a584  cmp     [rax+rdi*2], r15w
0x18007a589  jnz     short loc_18007A581
0x18007a58b  lea     rax, [rbp+3F0h+var_240]
0x18007a592  lea     ecx, [rdi+rdi]
0x18007a595  add     rcx, 2
0x18007a599  lea     r9, [rsp+4F0h+var_480]
0x18007a59e  mov     [rsp+4F0h+var_490], rcx
0x18007a5a3  lea     rdx, PLA_EVENT_ERROR
0x18007a5aa  mov     [rsp+4F0h+var_498], rax
0x18007a5af  mov     ecx, 4
0x18007a5b4  mov     [rsp+4F0h+var_4A0], 29h ; ')'
0x18007a5bd  lea     rax, aAlertdatacolle_8; "_AlertDataCollector::get_AlertThreshold"...
0x18007a5c4  mov     [rsp+4F0h+var_4A8], rax
0x18007a5c9  lea     rax, [rsp+4F0h+var_478]
0x18007a5ce  mov     [rsp+4F0h+var_4B0], rcx
0x18007a5d3  mov     [rsp+4F0h+var_4B8], rax
0x18007a5d8  lea     r8d, [rcx+1]
0x18007a5dc  lea     rax, byte_180147320
0x18007a5e3  mov     [rsp+4F0h+var_4C0], 1
0x18007a5ec  mov     [rsp+4F0h+var_4C8], rax
0x18007a5f1  mov     qword ptr [rsp+4F0h+var_4D0], rcx
0x18007a5f6  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18007a5fd  call    EventingWriteEvent
0x18007a602  mov     r12, [rbp+3F0h+var_460]
0x18007a606  jmp     loc_18007A7CB
0x18007a60b  mov     r8, r15; unsigned __int16 *
0x18007a60e  mov     edx, 400h; unsigned __int64
0x18007a613  mov     r15, [rbp+3F0h+var_468]
0x18007a617  mov     rcx, r15; unsigned __int16 *
  ... truncated ...
```
