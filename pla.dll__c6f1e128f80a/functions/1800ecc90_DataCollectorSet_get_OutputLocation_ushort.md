# DataCollectorSet::get_OutputLocation(ushort * *)

- ea: `0x1800ecc90`
- end: `0x1800ed8e5`
- name: `?get_OutputLocation@DataCollectorSet@@UEAAJPEAPEAG@Z`
- size: `3157`
- prototype: `__int64 __fastcall(DataCollectorSet *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x180018420`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x180046c60`
- `0x18006b12c`
- `0x180072200`
- `0x1800ecc90`
- `0x1800f9c48`
- `0x180116404`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed14f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed14f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ecd6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ecd6f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800ed141`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800ed141`

## pseudocode

```c
__int64 __fastcall DataCollectorSet::get_OutputLocation(DataCollectorSet *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // r14
  unsigned int v5; // ebx
  WCHAR *v6; // r12
  __int64 v7; // rax
  DataCollectorSet **v8; // r9
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  unsigned __int64 v14; // rdx
  const unsigned __int16 *v15; // r8
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  DWORD LastError; // eax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  unsigned __int64 v27; // rdx
  __int64 v28; // rax
  LONGLONG llVal; // r8
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  unsigned __int64 v33; // rdx
  __int64 v34; // rax
  int v35; // r9d
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  unsigned int v40; // ecx
  int appended; // eax
  __int64 v42; // rax
  int v43; // eax
  const char *v44; // rdx
  int v45; // r8d
  __int64 v46; // rax
  unsigned __int16 *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+70h] [rbp-90h] BYREF
  DataCollectorSet *v54; // [rsp+78h] [rbp-88h] BYREF
  DWORD nSize; // [rsp+80h] [rbp-80h] BYREF
  struct tagVARIANT v56; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v57[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v58[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v59[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v60[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v61[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v62[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v63[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v64[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v65[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v66[64]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v67[64]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v68[64]; // [rsp+620h] [rbp+520h] BYREF
  unsigned __int16 v69[64]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v70[64]; // [rsp+720h] [rbp+620h] BYREF
  unsigned __int16 v71[64]; // [rsp+7A0h] [rbp+6A0h] BYREF
  unsigned __int16 v72[64]; // [rsp+820h] [rbp+720h] BYREF
  unsigned __int16 v73[64]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v74[64]; // [rsp+920h] [rbp+820h] BYREF

  v54 = this;
  nSize = 0;
  v53 = *((_DWORD *)this + 14);
  v4 = 0;
  memset(&v56, 0, sizeof(v56));
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    v51 = 37;
    EventingWriteEvent(
      (__int64)&g_Eventing,
      (__int64)PLA_EVENT_METHOD,
      3,
      (__int64)"DataCollectorSet::get_OutputLocation");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiVariantInit(&v56);
  if ( a2 )
  {
    v6 = (WCHAR *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v51);
    if ( !v6 )
    {
      v5 = -2147024882;
      v53 = -2147024882;
      LODWORD(v54) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v58, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v58[v9] );
      goto LABEL_139;
    }
    v4 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v52);
    if ( !v4 )
    {
      v5 = -2147024882;
      v53 = -2147024882;
      LODWORD(v54) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v59, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v59[v10] );
      goto LABEL_139;
    }
    PlaiVariantClear(&v56);
    v11 = (*(__int64 (__fastcall **)(DataCollectorSet *, CY *))(*(_QWORD *)this + 176LL))(this, &v56.cyVal);
    v5 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v54) = 0;
      v53 = v11;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v60, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v60[v12] );
      goto LABEL_139;
    }
    v56.vt = 8;
    if ( v56.llVal && *v56.bstrVal )
    {
      v13 = StringCchCopyW(v4, 0x400u, v56.bstrVal);
      v5 = v13;
      if ( v13 < 0 )
      {
        LODWORD(v54) = 0;
        v53 = v13;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_141;
        }
        PlaiWhoAmI(v61, 0x4000000000000800uLL);
        v16 = -1;
        do
          ++v16;
        while ( v61[v16] );
        goto LABEL_139;
      }
      v17 = PlaiPathCat(v4, v14, v15);
      v5 = v17;
      if ( v17 < 0 )
      {
        LODWORD(v54) = 0;
        v53 = v17;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_141;
        }
        PlaiWhoAmI(v62, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v62[v18] );
        goto LABEL_139;
      }
      if ( (*((_BYTE *)this + 168) & 2) != 0 )
      {
        nSize = 1024;
        if ( !GetComputerNameW(v6, &nSize) )
        {
          LastError = GetLastError();
          v20 = PlaiHResultFromWin32(LastError);
          v5 = v20;
          if ( v20 < 0 )
          {
            LODWORD(v54) = 0;
            v53 = v20;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_141;
            }
            PlaiWhoAmI(v63, 0x4000000000000800uLL);
            v21 = -1;
            do
              ++v21;
            while ( v63[v21] );
            goto LABEL_139;
          }
        }
        v22 = StringCchCatW(v4, 0x400u, v6);
        v5 = v22;
        if ( v22 < 0 )
        {
          LODWORD(v54) = 0;
          v53 = v22;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_141;
          }
          PlaiWhoAmI(v64, 0x4000000000000800uLL);
          v23 = -1;
          do
            ++v23;
          while ( v64[v23] );
          goto LABEL_139;
        }
        v24 = StringCchCatW(v4, 0x400u, L"_");
        v5 = v24;
        if ( v24 < 0 )
        {
          LODWORD(v54) = 0;
          v53 = v24;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_141;
          }
          PlaiWhoAmI(v65, 0x4000000000000800uLL);
          v25 = -1;
          do
            ++v25;
          while ( v65[v25] );
          goto LABEL_139;
        }
      }
      PlaiVariantClear(&v56);
      v26 = (*(__int64 (__fastcall **)(DataCollectorSet *, CY *))(*(_QWORD *)this + 272LL))(this, &v56.cyVal);
      v5 = v26;
      if ( v26 < 0 )
      {
        LODWORD(v54) = 0;
        v53 = v26;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_141;
        }
        PlaiWhoAmI(v66, 0x4000000000000800uLL);
        v28 = -1;
        do
          ++v28;
        while ( v66[v28] );
        goto LABEL_139;
      }
      llVal = v56.llVal;
      v56.vt = 8;
      if ( v56.llVal )
      {
        if ( *v56.bstrVal )
        {
          v30 = StringCchCatW(v4, 0x400u, v56.bstrVal);
          v5 = v30;
          if ( v30 < 0 )
          {
            LODWORD(v54) = 0;
            v53 = v30;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_141;
            }
            PlaiWhoAmI(v67, 0x4000000000000800uLL);
            v31 = -1;
            do
              ++v31;
            while ( v67[v31] );
            goto LABEL_139;
          }
        }
      }
      if ( (*((_BYTE *)this + 168) & 1) == 0 )
        goto LABEL_112;
      PlaiVariantClear(&v56);
      v32 = (*(__int64 (__fastcall **)(DataCollectorSet *, CY *))(*(_QWORD *)this + 304LL))(this, &v56.cyVal);
      v5 = v32;
      if ( v32 < 0 )
      {
        LODWORD(v54) = 0;
        v53 = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_141;
        }
        PlaiWhoAmI(v68, 0x4000000000000800uLL);
        v34 = -1;
        do
          ++v34;
        while ( v68[v34] );
        goto LABEL_139;
      }
      v35 = *((_DWORD *)this + 37);
      v56.vt = 8;
      v36 = PlaiExpandPattern(v6, v33, v56.bstrVal, v35);
      v5 = v36;
      if ( v36 < 0 )
      {
        LODWORD(v54) = 0;
        v53 = v36;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_141;
        }
        PlaiWhoAmI(v69, 0x4000000000000800uLL);
        v37 = -1;
        do
          ++v37;
        while ( v69[v37] );
        goto LABEL_139;
      }
      v38 = StringCchCatW(v4, 0x400u, v6);
      v5 = v38;
      if ( v38 < 0 )
      {
        LODWORD(v54) = 0;
        v53 = v38;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_141;
        }
        PlaiWhoAmI(v70, 0x4000000000000800uLL);
        v39 = -1;
        do
          ++v39;
        while ( v70[v39] );
      }
      else
      {
LABEL_112:
        v40 = *((_DWORD *)this + 42);
        if ( (v40 & 0xFF00) != 0
          && (appended = PlaiAppendAutoPattern(v40, v4, llVal, *((_DWORD *)this + 37)), v5 = appended, appended < 0) )
        {
          LODWORD(v54) = 0;
          v53 = appended;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_141;
          }
          PlaiWhoAmI(v71, 0x4000000000000800uLL);
          v42 = -1;
          do
            ++v42;
          while ( v71[v42] );
        }
        else
        {
          v43 = PlaiExpandVariables(v4, v27, v4);
          v5 = v43;
          if ( v43 >= 0 )
          {
            v47 = PlaiAllocStringEx(v4, v44, v45);
            *a2 = v47;
            if ( v47 )
              goto LABEL_141;
            v5 = -2147024882;
            v53 = -2147024882;
            LODWORD(v54) = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_141;
            }
            PlaiWhoAmI(v73, 0x4000000000000800uLL);
            v48 = -1;
            do
              ++v48;
            while ( v73[v48] );
          }
          else
          {
            LODWORD(v54) = 0;
            v53 = v43;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_141;
            }
            PlaiWhoAmI(v72, 0x4000000000000800uLL);
            v46 = -1;
            do
              ++v46;
            while ( v72[v46] );
          }
        }
      }
    }
    else
    {
      v5 = -2147467259;
      v53 = -2147467259;
      LODWORD(v54) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v74, 0x4000000000000800uLL);
      v49 = -1;
      do
        ++v49;
      while ( v74[v49] );
    }
LABEL_139:
    v8 = (DataCollectorSet **)&v53;
LABEL_140:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v8);
    goto LABEL_141;
  }
  v5 = -2147467261;
  LODWORD(v54) = -2147467261;
  v6 = 0;
  v53 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v57, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v57[v7] );
    v8 = &v54;
    goto LABEL_140;
  }
LABEL_141:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v6 )
    PlaiFree(v6, 1);
  if ( v4 )
    PlaiFree(v4, 1);
  PlaiVariantClear(&v56);
  return v5;
}

```

## disassembly

```asm
0x1800ecc90  mov     [rsp-8+arg_10], rbx
0x1800ecc95  push    rbp
0x1800ecc96  push    rsi
0x1800ecc97  push    rdi
0x1800ecc98  push    r12
0x1800ecc9a  push    r13
0x1800ecc9c  push    r14
0x1800ecc9e  push    r15
0x1800ecca0  lea     rbp, [rsp-8B0h]
0x1800ecca8  sub     rsp, 9B0h
0x1800eccaf  mov     rax, cs:__security_cookie
0x1800eccb6  xor     rax, rsp
0x1800eccb9  mov     [rbp+8E0h+var_40], rax
0x1800eccc0  xor     r13d, r13d
0x1800eccc3  mov     [rsp+9E0h+var_968], rcx
0x1800eccc8  xor     eax, eax
0x1800eccca  mov     [rbp+8E0h+nSize], r13d
0x1800eccce  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800eccd5  xorps   xmm0, xmm0
0x1800eccd8  mov     qword ptr [rbp+8E0h+var_958+10h], rax
0x1800eccdc  mov     rdi, rdx
0x1800eccdf  mov     eax, [rcx+38h]
0x1800ecce2  lea     r15d, [r13+4]
0x1800ecce6  mov     rsi, rcx
0x1800ecce9  mov     [rsp+9E0h+var_970], eax
0x1800ecced  mov     r14d, r13d
0x1800eccf0  movups  xmmword ptr [rbp+8E0h+var_958], xmm0
0x1800eccf4  jz      short loc_1800ECD65
0x1800eccf6  mov     rdx, 4000000000000400h
0x1800ecd00  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ecd07  jz      short loc_1800ECD65
0x1800ecd09  mov     rax, cs:qword_180169748
0x1800ecd10  and     rax, rdx
0x1800ecd13  cmp     cs:qword_180169748, rax
0x1800ecd1a  jnz     short loc_1800ECD65
0x1800ecd1c  mov     [rsp+9E0h+var_9A0], r15
0x1800ecd21  lea     rax, [rsp+9E0h+var_970]
0x1800ecd26  mov     [rsp+9E0h+var_9A8], rax
0x1800ecd2b  lea     r9, aDatacollectors_66; "DataCollectorSet::get_OutputLocation"
0x1800ecd32  lea     rax, [rsp+9E0h+var_968]
0x1800ecd37  mov     [rsp+9E0h+var_9B0], 8
0x1800ecd40  mov     [rsp+9E0h+var_9B8], rax
0x1800ecd45  lea     r8d, [r13+3]
0x1800ecd49  lea     rdx, PLA_EVENT_METHOD
0x1800ecd50  mov     qword ptr [rsp+9E0h+var_9C0], 25h ; '%'; int
0x1800ecd59  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ecd60  call    EventingWriteEvent
0x1800ecd65  cmp     [rsi+8], r13d
0x1800ecd69  jz      short loc_1800ECD75
0x1800ecd6b  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800ecd6f  call    cs:__imp_EnterCriticalSection
0x1800ecd75  lea     rcx, [rbp+8E0h+var_958]; struct tagVARIANT *
0x1800ecd79  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800ecd7e  test    rdi, rdi
0x1800ecd81  jnz     loc_1800ECE38
0x1800ecd87  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ecd8e  mov     ebx, 80004003h
0x1800ecd93  mov     dword ptr [rsp+9E0h+var_968], ebx
0x1800ecd97  mov     r12, r13
0x1800ecd9a  mov     [rsp+9E0h+var_970], r13d
0x1800ecd9f  jz      loc_1800ED87C
0x1800ecda5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ecdaf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ecdb6  jz      loc_1800ED87C
0x1800ecdbc  mov     rax, cs:qword_180169748
0x1800ecdc3  and     rax, rdx
0x1800ecdc6  cmp     cs:qword_180169748, rax
0x1800ecdcd  jnz     loc_1800ED87C
0x1800ecdd3  lea     rcx, [rbp+8E0h+var_940]; unsigned __int16 *
0x1800ecdd7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ecddc  lea     rcx, [rbp+8E0h+var_940]
0x1800ecde0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ecde4  inc     rax
0x1800ecde7  cmp     [rcx+rax*2], r13w
0x1800ecdec  jnz     short loc_1800ECDE4
0x1800ecdee  lea     ecx, [rax+rax]
0x1800ecdf1  mov     edx, 4
0x1800ecdf6  lea     rax, [rbp+8E0h+var_940]
0x1800ecdfa  add     rcx, 2
0x1800ecdfe  mov     [rsp+9E0h+var_980], rcx
0x1800ece03  lea     r9, [rsp+9E0h+var_968]
0x1800ece08  mov     [rsp+9E0h+var_988], rax
0x1800ece0d  lea     rax, aDatacollectors_66; "DataCollectorSet::get_OutputLocation"
0x1800ece14  mov     [rsp+9E0h+var_990], 25h ; '%'
0x1800ece1d  mov     [rsp+9E0h+var_998], rax
0x1800ece22  lea     rax, [rsp+9E0h+var_970]
0x1800ece27  mov     [rsp+9E0h+var_9A0], r15
0x1800ece2c  lea     r15, qword_180147320
0x1800ece33  jmp     loc_1800ED84B
0x1800ece38  xor     r8d, r8d; int
0x1800ece3b  lea     r15, qword_180147320
0x1800ece42  mov     ebx, 800h
0x1800ece47  mov     r9, r15; char *
0x1800ece4a  mov     ecx, ebx; dwBytes
0x1800ece4c  lea     edx, [r8+1]; int
0x1800ece50  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800ece55  mov     r12, rax
0x1800ece58  test    rax, rax
0x1800ece5b  jnz     short loc_1800ECECF
0x1800ece5d  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ece64  mov     eax, 8007000Eh
0x1800ece69  mov     ebx, eax
0x1800ece6b  mov     [rsp+9E0h+var_970], eax
0x1800ece6f  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ece74  jz      loc_1800ED87C
0x1800ece7a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ece84  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ece8b  jz      loc_1800ED87C
0x1800ece91  mov     rax, cs:qword_180169748
0x1800ece98  and     rax, rdx
0x1800ece9b  cmp     cs:qword_180169748, rax
0x1800ecea2  jnz     loc_1800ED87C
0x1800ecea8  lea     rcx, [rbp+8E0h+var_8C0]; unsigned __int16 *
0x1800eceac  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800eceb1  lea     rcx, [rbp+8E0h+var_8C0]
0x1800eceb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800eceb9  inc     rax
0x1800ecebc  cmp     [rcx+rax*2], r13w
0x1800ecec1  jnz     short loc_1800ECEB9
0x1800ecec3  lea     ecx, [rax+rax]
0x1800ecec6  lea     rax, [rbp+8E0h+var_8C0]
0x1800ececa  jmp     loc_1800ED814
0x1800ececf  xor     r8d, r8d; int
0x1800eced2  mov     r9, r15; char *
0x1800eced5  mov     rcx, rbx; dwBytes
0x1800eced8  lea     edx, [r8+1]; int
0x1800ecedc  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800ecee1  mov     r14, rax
0x1800ecee4  test    rax, rax
0x1800ecee7  jnz     short loc_1800ECF64
0x1800ecee9  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ecef0  mov     eax, 8007000Eh
0x1800ecef5  mov     ebx, eax
0x1800ecef7  mov     [rsp+9E0h+var_970], eax
0x1800ecefb  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ecf00  jz      loc_1800ED87C
0x1800ecf06  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ecf10  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ecf17  jz      loc_1800ED87C
0x1800ecf1d  mov     rax, cs:qword_180169748
0x1800ecf24  and     rax, rdx
0x1800ecf27  cmp     cs:qword_180169748, rax
0x1800ecf2e  jnz     loc_1800ED87C
0x1800ecf34  lea     rcx, [rbp+8E0h+var_840]; unsigned __int16 *
0x1800ecf3b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ecf40  lea     rcx, [rbp+8E0h+var_840]
0x1800ecf47  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ecf4b  inc     rax
0x1800ecf4e  cmp     [rcx+rax*2], r13w
0x1800ecf53  jnz     short loc_1800ECF4B
0x1800ecf55  lea     ecx, [rax+rax]
0x1800ecf58  lea     rax, [rbp+8E0h+var_840]
0x1800ecf5f  jmp     loc_1800ED814
0x1800ecf64  lea     rcx, [rbp+8E0h+var_958]; struct tagVARIANT *
0x1800ecf68  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800ecf6d  mov     rax, [rsi]
0x1800ecf70  lea     rdx, [rbp+8E0h+var_958+8]
0x1800ecf74  mov     rcx, rsi
0x1800ecf77  mov     rax, [rax+0B0h]
0x1800ecf7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf83  mov     ebx, eax
0x1800ecf85  test    eax, eax
0x1800ecf87  jns     short loc_1800ECFFD
0x1800ecf89  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ecf90  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ecf95  mov     [rsp+9E0h+var_970], eax
0x1800ecf99  jz      loc_1800ED87C
0x1800ecf9f  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ecfa9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ecfb0  jz      loc_1800ED87C
0x1800ecfb6  mov     rax, cs:qword_180169748
0x1800ecfbd  and     rax, rdx
0x1800ecfc0  cmp     cs:qword_180169748, rax
0x1800ecfc7  jnz     loc_1800ED87C
0x1800ecfcd  lea     rcx, [rbp+8E0h+var_7C0]; unsigned __int16 *
0x1800ecfd4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ecfd9  lea     rcx, [rbp+8E0h+var_7C0]
0x1800ecfe0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ecfe4  inc     rax
0x1800ecfe7  cmp     [rcx+rax*2], r13w
0x1800ecfec  jnz     short loc_1800ECFE4
0x1800ecfee  lea     ecx, [rax+rax]
0x1800ecff1  lea     rax, [rbp+8E0h+var_7C0]
0x1800ecff8  jmp     loc_1800ED814
0x1800ecffd  mov     r8, qword ptr [rbp+8E0h+var_958+8]; unsigned __int16 *
0x1800ed001  mov     eax, 8
0x1800ed006  mov     word ptr [rbp+8E0h+var_958], ax
0x1800ed00a  test    r8, r8
0x1800ed00d  jz      loc_1800ED7A0
0x1800ed013  cmp     r13w, [r8]
0x1800ed017  jz      loc_1800ED7A0
0x1800ed01d  mov     edx, 400h; unsigned __int64
0x1800ed022  mov     rcx, r14; unsigned __int16 *
0x1800ed025  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ed02a  mov     ebx, eax
0x1800ed02c  test    eax, eax
0x1800ed02e  jns     short loc_1800ED0A4
0x1800ed030  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ed037  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ed03c  mov     [rsp+9E0h+var_970], eax
0x1800ed040  jz      loc_1800ED87C
0x1800ed046  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ed050  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ed057  jz      loc_1800ED87C
0x1800ed05d  mov     rax, cs:qword_180169748
0x1800ed064  and     rax, rdx
0x1800ed067  cmp     cs:qword_180169748, rax
0x1800ed06e  jnz     loc_1800ED87C
0x1800ed074  lea     rcx, [rbp+8E0h+var_740]; unsigned __int16 *
0x1800ed07b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ed080  lea     rcx, [rbp+8E0h+var_740]
0x1800ed087  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ed08b  inc     rax
0x1800ed08e  cmp     [rcx+rax*2], r13w
0x1800ed093  jnz     short loc_1800ED08B
0x1800ed095  lea     ecx, [rax+rax]
0x1800ed098  lea     rax, [rbp+8E0h+var_740]
0x1800ed09f  jmp     loc_1800ED814
0x1800ed0a4  mov     rcx, r14; unsigned __int16 *
0x1800ed0a7  call    ?PlaiPathCat@@YAJPEAG_KPEBG@Z; PlaiPathCat(ushort *,unsigned __int64,ushort const *)
0x1800ed0ac  mov     ebx, eax
0x1800ed0ae  test    eax, eax
0x1800ed0b0  jns     short loc_1800ED126
0x1800ed0b2  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ed0b9  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ed0be  mov     [rsp+9E0h+var_970], eax
0x1800ed0c2  jz      loc_1800ED87C
0x1800ed0c8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ed0d2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ed0d9  jz      loc_1800ED87C
0x1800ed0df  mov     rax, cs:qword_180169748
0x1800ed0e6  and     rax, rdx
0x1800ed0e9  cmp     cs:qword_180169748, rax
0x1800ed0f0  jnz     loc_1800ED87C
0x1800ed0f6  lea     rcx, [rbp+8E0h+var_6C0]; unsigned __int16 *
0x1800ed0fd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ed102  lea     rcx, [rbp+8E0h+var_6C0]
0x1800ed109  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ed10d  inc     rax
0x1800ed110  cmp     [rcx+rax*2], r13w
0x1800ed115  jnz     short loc_1800ED10D
0x1800ed117  lea     ecx, [rax+rax]
0x1800ed11a  lea     rax, [rbp+8E0h+var_6C0]
0x1800ed121  jmp     loc_1800ED814
0x1800ed126  test    byte ptr [rsi+0A8h], 2
0x1800ed12d  jz      loc_1800ED2EE
0x1800ed133  lea     rdx, [rbp+8E0h+nSize]; nSize
0x1800ed137  mov     [rbp+8E0h+nSize], 400h
0x1800ed13e  mov     rcx, r12; lpBuffer
0x1800ed141  call    cs:__imp_GetComputerNameW
0x1800ed147  test    eax, eax
0x1800ed149  jnz     loc_1800ED1D6
0x1800ed14f  call    cs:__imp_GetLastError
0x1800ed155  mov     ecx, eax; unsigned int
0x1800ed157  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800ed15c  mov     ebx, eax
0x1800ed15e  test    eax, eax
0x1800ed160  jns     short loc_1800ED1D6
0x1800ed162  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ed169  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ed16e  mov     [rsp+9E0h+var_970], eax
0x1800ed172  jz      loc_1800ED87C
0x1800ed178  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ed182  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ed189  jz      loc_1800ED87C
0x1800ed18f  mov     rax, cs:qword_180169748
0x1800ed196  and     rax, rdx
0x1800ed199  cmp     cs:qword_180169748, rax
0x1800ed1a0  jnz     loc_1800ED87C
0x1800ed1a6  lea     rcx, [rbp+8E0h+var_640]; unsigned __int16 *
0x1800ed1ad  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ed1b2  lea     rcx, [rbp+8E0h+var_640]
0x1800ed1b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ed1bd  inc     rax
0x1800ed1c0  cmp     [rcx+rax*2], r13w
0x1800ed1c5  jnz     short loc_1800ED1BD
0x1800ed1c7  lea     ecx, [rax+rax]
0x1800ed1ca  lea     rax, [rbp+8E0h+var_640]
0x1800ed1d1  jmp     loc_1800ED814
0x1800ed1d6  mov     r8, r12; unsigned __int16 *
0x1800ed1d9  mov     edx, 400h; unsigned __int64
0x1800ed1de  mov     rcx, r14; unsigned __int16 *
0x1800ed1e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ed1e6  mov     ebx, eax
0x1800ed1e8  test    eax, eax
0x1800ed1ea  jns     short loc_1800ED260
0x1800ed1ec  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800ed1f3  mov     dword ptr [rsp+9E0h+var_968], r13d
0x1800ed1f8  mov     [rsp+9E0h+var_970], eax
0x1800ed1fc  jz      loc_1800ED87C
0x1800ed202  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ed20c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ed213  jz      loc_1800ED87C
0x1800ed219  mov     rax, cs:qword_180169748
0x1800ed220  and     rax, rdx
0x1800ed223  cmp     cs:qword_180169748, rax
0x1800ed22a  jnz     loc_1800ED87C
0x1800ed230  lea     rcx, [rbp+8E0h+var_5C0]; unsigned __int16 *
0x1800ed237  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ed23c  lea     rcx, [rbp+8E0h+var_5C0]
  ... truncated ...
```
