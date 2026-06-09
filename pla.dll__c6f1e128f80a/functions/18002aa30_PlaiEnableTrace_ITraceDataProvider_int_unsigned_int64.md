# PlaiEnableTrace(ITraceDataProvider *,int,unsigned __int64)

- ea: `0x18002aa30`
- end: `0x18002b38b`
- name: `?PlaiEnableTrace@@YAJPEAUITraceDataProvider@@H_K@Z`
- size: `2395`
- prototype: `int(struct ITraceDataProvider *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180028bf0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002aa30`
- `0x18002b3a0`
- `0x180100de0`
- `0x18011a5f8`
- `0x18011a7f0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-eventing-legacy-l1-1-0!EnableTraceEx` at `0x18002b220`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTraceEx` at `0x18002b220`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002b0ca`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002b349`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002b0ca`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002b349`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002b0b7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002b336`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002b0b7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002b336`

## pseudocode

```c
__int64 __fastcall PlaiEnableTrace(struct ITraceDataProvider *a1, ULONG a2, TRACEHANDLE a3)
{
  struct ITraceDataProviderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_Guid)(ITraceDataProvider *, GUID *); // rax
  signed int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // rbx
  signed int v12; // eax
  signed int Ul; // eax
  signed int v14; // eax
  signed int Ull; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  struct _EVENT_FILTER_DESCRIPTOR *EnableFilterDesc; // rax
  ULONG v25; // eax
  signed int v26; // eax
  ULONG EnableProperty; // [rsp+70h] [rbp-90h] BYREF
  UCHAR Level[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  __int16 v31; // [rsp+88h] [rbp-78h] BYREF
  SAFEARRAY *psa; // [rsp+90h] [rbp-70h] BYREF
  ULONGLONG MatchAllKeyword; // [rsp+98h] [rbp-68h] BYREF
  ULONGLONG MatchAnyKeyword; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_FILTER_DESCRIPTOR v35; // [rsp+A8h] [rbp-58h] BYREF
  GUID ProviderId; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v37[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v38[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v39[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v40[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v41[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v42[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v43[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v44[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v45[64]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v46[64]; // [rsp+550h] [rbp+450h] BYREF
  unsigned __int16 v47[64]; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 v48[64]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v49[64]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v50[64]; // [rsp+750h] [rbp+650h] BYREF

  lpVtbl = a1->lpVtbl;
  *(_DWORD *)Level = 0;
  EnableProperty = 0;
  MatchAnyKeyword = 0;
  get_Guid = lpVtbl->get_Guid;
  MatchAllKeyword = 0;
  ProviderId = 0;
  v30 = 0;
  psa = 0;
  v35 = 0;
  v31 = 0;
  v8 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, GUID *))get_Guid)(a1, &ProviderId);
  v9 = v8;
  if ( v8 < 0 )
  {
    *(_DWORD *)Level = 0;
    EnableProperty = v8;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v37, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v37[v10] );
LABEL_118:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &EnableProperty,
        4,
        qword_180147320,
        1,
        Level,
        4,
        "PlaiEnableTrace",
        16);
      goto LABEL_119;
    }
    goto LABEL_119;
  }
  v11 = -1;
  if ( !a2 )
    goto LABEL_105;
  v12 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))a1->lpVtbl->get_Level)(a1, &v30);
  v9 = v12;
  if ( v12 >= 0 )
  {
    Ul = PlaiGetUlValue<IValueMap>(v30, Level);
    v9 = Ul;
    if ( Ul < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = Ul;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v39, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v39[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v30 = 0;
    }
    v14 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))a1->lpVtbl->get_KeywordsAny)(a1, &v30);
    v9 = v14;
    if ( v14 < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = v14;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v40, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v40[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    Ull = PlaiGetUllValue<IValueMap>(v30, &MatchAnyKeyword);
    v9 = Ull;
    if ( Ull < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = Ull;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v41, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v41[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v30 = 0;
    }
    v16 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))a1->lpVtbl->get_KeywordsAll)(a1, &v30);
    v9 = v16;
    if ( v16 < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = v16;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v42, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v42[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    v17 = PlaiGetUllValue<IValueMap>(v30, &MatchAllKeyword);
    v9 = v17;
    if ( v17 < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = v17;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v43, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v43[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v30 = 0;
    }
    v18 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))a1->lpVtbl->get_Properties)(a1, &v30);
    v9 = v18;
    if ( v18 < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = v18;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v44, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v44[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    v19 = PlaiGetUlValue<IValueMap>(v30, &EnableProperty);
    v9 = v19;
    if ( v19 < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = v19;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v45, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v45[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    v20 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int16 *))a1->lpVtbl->get_FilterEnabled)(a1, &v31);
    v9 = v20;
    if ( v20 < 0 )
    {
      *(_DWORD *)Level = 0;
      EnableProperty = v20;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v46, 0x4000000000000800uLL);
        do
          ++v11;
        while ( v46[v11] );
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    if ( v31 == -1 )
    {
      v21 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, ULONG *))a1->lpVtbl->get_FilterType)(a1, &v35.Type);
      v9 = v21;
      if ( v21 < 0 )
      {
        *(_DWORD *)Level = 0;
        EnableProperty = v21;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v47, 0x4000000000000800uLL);
          do
            ++v11;
          while ( v47[v11] );
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      if ( v35.Ptr )
      {
        SafeArrayUnaccessData(psa);
        v35.Ptr = 0;
      }
      if ( psa )
      {
        SafeArrayDestroy(psa);
        psa = 0;
      }
      v22 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, SAFEARRAY **))a1->lpVtbl->get_FilterData)(a1, &psa);
      v9 = v22;
      if ( v22 < 0 )
      {
        *(_DWORD *)Level = 0;
        EnableProperty = v22;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v48, 0x4000000000000800uLL);
          do
            ++v11;
          while ( v48[v11] );
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      v23 = PlaiInitializeFilterBlob(psa, &v35);
      v9 = v23;
      if ( v23 < 0 )
      {
        *(_DWORD *)Level = 0;
        EnableProperty = v23;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v49, 0x4000000000000800uLL);
          do
            ++v11;
          while ( v49[v11] );
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      EnableFilterDesc = &v35;
      if ( v31 == -1 )
      {
LABEL_106:
        v25 = EnableTraceEx(
                &ProviderId,
                0,
                a3,
                a2,
                Level[0],
                MatchAnyKeyword,
                MatchAllKeyword,
                EnableProperty,
                EnableFilterDesc);
        if ( v25 == 4201 )
        {
          v9 = -2144337918;
        }
        else
        {
          if ( v25 != 183 )
          {
            v26 = PlaiHResultFromWin32(v25);
            v9 = v26;
            if ( v26 >= 0 )
              goto LABEL_119;
            goto LABEL_113;
          }
          v9 = -2144337750;
        }
        v26 = v9;
LABEL_113:
        *(_DWORD *)Level = 0;
        EnableProperty = v26;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v50, 0x4000000000000800uLL);
          do
            ++v11;
          while ( v50[v11] );
          goto LABEL_118;
        }
        goto LABEL_119;
      }
    }
LABEL_105:
    EnableFilterDesc = 0;
    goto LABEL_106;
  }
  *(_DWORD *)Level = 0;
  EnableProperty = v12;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v38, 0x4000000000000800uLL);
    do
      ++v11;
    while ( v38[v11] );
    goto LABEL_118;
  }
LABEL_119:
  if ( v35.Ptr )
  {
    SafeArrayUnaccessData(psa);
    v35.Ptr = 0;
  }
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return v9;
}

```

## disassembly

```asm
0x18002aa30  push    rbp
0x18002aa32  push    rbx
0x18002aa33  push    rsi
0x18002aa34  push    rdi
0x18002aa35  push    r12
0x18002aa37  push    r14
0x18002aa39  push    r15
0x18002aa3b  lea     rbp, [rsp-6E0h]
0x18002aa43  sub     rsp, 7E0h
0x18002aa4a  mov     rax, cs:__security_cookie
0x18002aa51  xor     rax, rsp
0x18002aa54  mov     [rbp+710h+var_40], rax
0x18002aa5b  mov     rax, [rcx]
0x18002aa5e  xor     r12d, r12d
0x18002aa61  xorps   xmm0, xmm0
0x18002aa64  mov     dword ptr [rsp+810h+var_798], r12d
0x18002aa69  mov     r14d, edx
0x18002aa6c  mov     [rsp+810h+var_7A0], r12d
0x18002aa71  lea     rdx, [rbp+710h+ProviderId]
0x18002aa75  mov     [rbp+710h+var_770], r12
0x18002aa79  mov     rax, [rax+48h]
0x18002aa7d  mov     r15, r8
0x18002aa80  mov     rsi, rcx
0x18002aa83  mov     [rbp+710h+var_778], r12
0x18002aa87  movups  xmmword ptr [rbp+710h+ProviderId.Data1], xmm0
0x18002aa8b  mov     [rbp+710h+var_790], r12
0x18002aa8f  mov     [rbp+710h+psa], r12
0x18002aa93  movups  xmmword ptr [rbp+710h+var_768.Ptr], xmm0
0x18002aa97  mov     [rbp+710h+var_788], r12w
0x18002aa9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaa1  mov     edi, eax
0x18002aaa3  test    eax, eax
0x18002aaa5  jns     short loc_18002AB0F
0x18002aaa7  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002aaae  mov     dword ptr [rsp+810h+var_798], r12d
0x18002aab3  mov     [rsp+810h+var_7A0], eax
0x18002aab7  jz      loc_18002B32C
0x18002aabd  mov     rdx, 4000000000000800h; unsigned __int64
0x18002aac7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002aace  jz      loc_18002B32C
0x18002aad4  mov     rax, cs:qword_180169748
0x18002aadb  and     rax, rdx
0x18002aade  cmp     cs:qword_180169748, rax
0x18002aae5  jnz     loc_18002B32C
0x18002aaeb  lea     rcx, [rbp+710h+var_740]; unsigned __int16 *
0x18002aaef  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002aaf4  lea     rax, [rbp+710h+var_740]
0x18002aaf8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002aafc  inc     rbx
0x18002aaff  cmp     [rax+rbx*2], r12w
0x18002ab04  jnz     short loc_18002AAFC
0x18002ab06  lea     rax, [rbp+710h+var_740]
0x18002ab0a  jmp     loc_18002B2BC
0x18002ab0f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ab13  test    r14d, r14d
0x18002ab16  jz      loc_18002B1EA
0x18002ab1c  mov     rcx, [rbp+710h+var_790]
0x18002ab20  test    rcx, rcx
0x18002ab23  jz      short loc_18002AB35
0x18002ab25  mov     rax, [rcx]
0x18002ab28  mov     rax, [rax+10h]
0x18002ab2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab31  mov     [rbp+710h+var_790], r12
0x18002ab35  mov     rax, [rsi]
0x18002ab38  lea     rdx, [rbp+710h+var_790]
0x18002ab3c  mov     rcx, rsi
0x18002ab3f  mov     rax, [rax+58h]
0x18002ab43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab48  mov     edi, eax
0x18002ab4a  test    eax, eax
0x18002ab4c  jns     short loc_18002ABB2
0x18002ab4e  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002ab55  mov     dword ptr [rsp+810h+var_798], r12d
0x18002ab5a  mov     [rsp+810h+var_7A0], eax
0x18002ab5e  jz      loc_18002B32C
0x18002ab64  mov     rdx, 4000000000000800h; unsigned __int64
0x18002ab6e  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002ab75  jz      loc_18002B32C
0x18002ab7b  mov     rax, cs:qword_180169748
0x18002ab82  and     rax, rdx
0x18002ab85  cmp     cs:qword_180169748, rax
0x18002ab8c  jnz     loc_18002B32C
0x18002ab92  lea     rcx, [rbp+710h+var_6C0]; unsigned __int16 *
0x18002ab96  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002ab9b  lea     rax, [rbp+710h+var_6C0]
0x18002ab9f  inc     rbx
0x18002aba2  cmp     [rax+rbx*2], r12w
0x18002aba7  jnz     short loc_18002AB9F
0x18002aba9  lea     rax, [rbp+710h+var_6C0]
0x18002abad  jmp     loc_18002B2BC
0x18002abb2  mov     rcx, [rbp+710h+var_790]
0x18002abb6  lea     rdx, [rsp+810h+var_798]
0x18002abbb  call    ??$PlaiGetUlValue@UIValueMap@@@@YAJPEAUIValueMap@@PEAK@Z; PlaiGetUlValue<IValueMap>(IValueMap *,ulong *)
0x18002abc0  mov     edi, eax
0x18002abc2  test    eax, eax
0x18002abc4  jns     short loc_18002AC33
0x18002abc6  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002abcd  mov     dword ptr [rsp+810h+var_798], r12d
0x18002abd2  mov     [rsp+810h+var_7A0], eax
0x18002abd6  jz      loc_18002B32C
0x18002abdc  mov     rdx, 4000000000000800h; unsigned __int64
0x18002abe6  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002abed  jz      loc_18002B32C
0x18002abf3  mov     rax, cs:qword_180169748
0x18002abfa  and     rax, rdx
0x18002abfd  cmp     cs:qword_180169748, rax
0x18002ac04  jnz     loc_18002B32C
0x18002ac0a  lea     rcx, [rbp+710h+var_640]; unsigned __int16 *
0x18002ac11  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002ac16  lea     rax, [rbp+710h+var_640]
0x18002ac1d  inc     rbx
0x18002ac20  cmp     [rax+rbx*2], r12w
0x18002ac25  jnz     short loc_18002AC1D
0x18002ac27  lea     rax, [rbp+710h+var_640]
0x18002ac2e  jmp     loc_18002B2BC
0x18002ac33  mov     rcx, [rbp+710h+var_790]
0x18002ac37  test    rcx, rcx
0x18002ac3a  jz      short loc_18002AC4C
0x18002ac3c  mov     rax, [rcx]
0x18002ac3f  mov     rax, [rax+10h]
0x18002ac43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac48  mov     [rbp+710h+var_790], r12
0x18002ac4c  mov     rax, [rsi]
0x18002ac4f  lea     rdx, [rbp+710h+var_790]
0x18002ac53  mov     rcx, rsi
0x18002ac56  mov     rax, [rax+60h]
0x18002ac5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac5f  mov     edi, eax
0x18002ac61  test    eax, eax
0x18002ac63  jns     short loc_18002ACD2
0x18002ac65  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002ac6c  mov     dword ptr [rsp+810h+var_798], r12d
0x18002ac71  mov     [rsp+810h+var_7A0], eax
0x18002ac75  jz      loc_18002B32C
0x18002ac7b  mov     rdx, 4000000000000800h; unsigned __int64
0x18002ac85  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002ac8c  jz      loc_18002B32C
0x18002ac92  mov     rax, cs:qword_180169748
0x18002ac99  and     rax, rdx
0x18002ac9c  cmp     cs:qword_180169748, rax
0x18002aca3  jnz     loc_18002B32C
0x18002aca9  lea     rcx, [rbp+710h+var_5C0]; unsigned __int16 *
0x18002acb0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002acb5  lea     rax, [rbp+710h+var_5C0]
0x18002acbc  inc     rbx
0x18002acbf  cmp     [rax+rbx*2], r12w
0x18002acc4  jnz     short loc_18002ACBC
0x18002acc6  lea     rax, [rbp+710h+var_5C0]
0x18002accd  jmp     loc_18002B2BC
0x18002acd2  mov     rcx, [rbp+710h+var_790]
0x18002acd6  lea     rdx, [rbp+710h+var_770]
0x18002acda  call    ??$PlaiGetUllValue@UIValueMap@@@@YAJPEAUIValueMap@@PEA_K@Z; PlaiGetUllValue<IValueMap>(IValueMap *,unsigned __int64 *)
0x18002acdf  mov     edi, eax
0x18002ace1  test    eax, eax
0x18002ace3  jns     short loc_18002AD52
0x18002ace5  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002acec  mov     dword ptr [rsp+810h+var_798], r12d
0x18002acf1  mov     [rsp+810h+var_7A0], eax
0x18002acf5  jz      loc_18002B32C
0x18002acfb  mov     rdx, 4000000000000800h; unsigned __int64
0x18002ad05  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002ad0c  jz      loc_18002B32C
0x18002ad12  mov     rax, cs:qword_180169748
0x18002ad19  and     rax, rdx
0x18002ad1c  cmp     cs:qword_180169748, rax
0x18002ad23  jnz     loc_18002B32C
0x18002ad29  lea     rcx, [rbp+710h+var_540]; unsigned __int16 *
0x18002ad30  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002ad35  lea     rax, [rbp+710h+var_540]
0x18002ad3c  inc     rbx
0x18002ad3f  cmp     [rax+rbx*2], r12w
0x18002ad44  jnz     short loc_18002AD3C
0x18002ad46  lea     rax, [rbp+710h+var_540]
0x18002ad4d  jmp     loc_18002B2BC
0x18002ad52  mov     rcx, [rbp+710h+var_790]
0x18002ad56  test    rcx, rcx
0x18002ad59  jz      short loc_18002AD6B
0x18002ad5b  mov     rax, [rcx]
0x18002ad5e  mov     rax, [rax+10h]
0x18002ad62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad67  mov     [rbp+710h+var_790], r12
0x18002ad6b  mov     rax, [rsi]
0x18002ad6e  lea     rdx, [rbp+710h+var_790]
0x18002ad72  mov     rcx, rsi
0x18002ad75  mov     rax, [rax+68h]
0x18002ad79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad7e  mov     edi, eax
0x18002ad80  test    eax, eax
0x18002ad82  jns     short loc_18002ADF1
0x18002ad84  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002ad8b  mov     dword ptr [rsp+810h+var_798], r12d
0x18002ad90  mov     [rsp+810h+var_7A0], eax
0x18002ad94  jz      loc_18002B32C
0x18002ad9a  mov     rdx, 4000000000000800h; unsigned __int64
0x18002ada4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002adab  jz      loc_18002B32C
0x18002adb1  mov     rax, cs:qword_180169748
0x18002adb8  and     rax, rdx
0x18002adbb  cmp     cs:qword_180169748, rax
0x18002adc2  jnz     loc_18002B32C
0x18002adc8  lea     rcx, [rbp+710h+var_4C0]; unsigned __int16 *
0x18002adcf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002add4  lea     rax, [rbp+710h+var_4C0]
0x18002addb  inc     rbx
0x18002adde  cmp     [rax+rbx*2], r12w
0x18002ade3  jnz     short loc_18002ADDB
0x18002ade5  lea     rax, [rbp+710h+var_4C0]
0x18002adec  jmp     loc_18002B2BC
0x18002adf1  mov     rcx, [rbp+710h+var_790]
0x18002adf5  lea     rdx, [rbp+710h+var_778]
0x18002adf9  call    ??$PlaiGetUllValue@UIValueMap@@@@YAJPEAUIValueMap@@PEA_K@Z; PlaiGetUllValue<IValueMap>(IValueMap *,unsigned __int64 *)
0x18002adfe  mov     edi, eax
0x18002ae00  test    eax, eax
0x18002ae02  jns     short loc_18002AE71
0x18002ae04  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002ae0b  mov     dword ptr [rsp+810h+var_798], r12d
0x18002ae10  mov     [rsp+810h+var_7A0], eax
0x18002ae14  jz      loc_18002B32C
0x18002ae1a  mov     rdx, 4000000000000800h; unsigned __int64
0x18002ae24  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002ae2b  jz      loc_18002B32C
0x18002ae31  mov     rax, cs:qword_180169748
0x18002ae38  and     rax, rdx
0x18002ae3b  cmp     cs:qword_180169748, rax
0x18002ae42  jnz     loc_18002B32C
0x18002ae48  lea     rcx, [rbp+710h+var_440]; unsigned __int16 *
0x18002ae4f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002ae54  lea     rax, [rbp+710h+var_440]
0x18002ae5b  inc     rbx
0x18002ae5e  cmp     [rax+rbx*2], r12w
0x18002ae63  jnz     short loc_18002AE5B
0x18002ae65  lea     rax, [rbp+710h+var_440]
0x18002ae6c  jmp     loc_18002B2BC
0x18002ae71  mov     rcx, [rbp+710h+var_790]
0x18002ae75  test    rcx, rcx
0x18002ae78  jz      short loc_18002AE8A
0x18002ae7a  mov     rax, [rcx]
0x18002ae7d  mov     rax, [rax+10h]
0x18002ae81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae86  mov     [rbp+710h+var_790], r12
0x18002ae8a  mov     rax, [rsi]
0x18002ae8d  lea     rdx, [rbp+710h+var_790]
0x18002ae91  mov     rcx, rsi
0x18002ae94  mov     rax, [rax+70h]
0x18002ae98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae9d  mov     edi, eax
0x18002ae9f  test    eax, eax
0x18002aea1  jns     short loc_18002AF10
0x18002aea3  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002aeaa  mov     dword ptr [rsp+810h+var_798], r12d
0x18002aeaf  mov     [rsp+810h+var_7A0], eax
0x18002aeb3  jz      loc_18002B32C
0x18002aeb9  mov     rdx, 4000000000000800h; unsigned __int64
0x18002aec3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002aeca  jz      loc_18002B32C
0x18002aed0  mov     rax, cs:qword_180169748
0x18002aed7  and     rax, rdx
0x18002aeda  cmp     cs:qword_180169748, rax
0x18002aee1  jnz     loc_18002B32C
0x18002aee7  lea     rcx, [rbp+710h+var_3C0]; unsigned __int16 *
0x18002aeee  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002aef3  lea     rax, [rbp+710h+var_3C0]
0x18002aefa  inc     rbx
0x18002aefd  cmp     [rax+rbx*2], r12w
0x18002af02  jnz     short loc_18002AEFA
0x18002af04  lea     rax, [rbp+710h+var_3C0]
0x18002af0b  jmp     loc_18002B2BC
0x18002af10  mov     rcx, [rbp+710h+var_790]
0x18002af14  lea     rdx, [rsp+810h+var_7A0]
0x18002af19  call    ??$PlaiGetUlValue@UIValueMap@@@@YAJPEAUIValueMap@@PEAK@Z; PlaiGetUlValue<IValueMap>(IValueMap *,ulong *)
0x18002af1e  mov     edi, eax
0x18002af20  test    eax, eax
0x18002af22  jns     short loc_18002AF91
0x18002af24  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002af2b  mov     dword ptr [rsp+810h+var_798], r12d
0x18002af30  mov     [rsp+810h+var_7A0], eax
0x18002af34  jz      loc_18002B32C
0x18002af3a  mov     rdx, 4000000000000800h; unsigned __int64
0x18002af44  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002af4b  jz      loc_18002B32C
0x18002af51  mov     rax, cs:qword_180169748
0x18002af58  and     rax, rdx
0x18002af5b  cmp     cs:qword_180169748, rax
0x18002af62  jnz     loc_18002B32C
0x18002af68  lea     rcx, [rbp+710h+var_340]; unsigned __int16 *
0x18002af6f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002af74  lea     rax, [rbp+710h+var_340]
0x18002af7b  inc     rbx
0x18002af7e  cmp     [rax+rbx*2], r12w
0x18002af83  jnz     short loc_18002AF7B
0x18002af85  lea     rax, [rbp+710h+var_340]
0x18002af8c  jmp     loc_18002B2BC
0x18002af91  mov     rax, [rsi]
0x18002af94  lea     rdx, [rbp+710h+var_788]
0x18002af98  mov     rcx, rsi
0x18002af9b  mov     rax, [rax+78h]
0x18002af9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afa4  mov     edi, eax
0x18002afa6  test    eax, eax
0x18002afa8  jns     short loc_18002B017
  ... truncated ...
```
