# Enumerator::GetNamedItem<IValueMapItem>(tagVARIANT,long (IValueMapItem::*)(ushort * *),IValueMapItem * *)

- ea: `0x1800335d8`
- end: `0x1800339ab`
- name: `??$GetNamedItem@UIValueMapItem@@@Enumerator@@QEAAJUtagVARIANT@@P8IValueMapItem@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 (__fastcall *)(__int64, wchar_t **), __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180032f60`
- `0x1800334cc`
- `0x18006e7f0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800335d8`
- `0x1800339b4`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800336e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800336e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003365a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003365a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003369a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003369a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180033718`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180033718`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<IValueMapItem>(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, wchar_t **),
        __int64 a4)
{
  int v4; // eax
  IRecordInfo *v9; // xmm1_8
  int v10; // eax
  unsigned int v11; // esi
  SAFEARRAY **v12; // rbx
  HRESULT v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64); // rcx
  int v15; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v26; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v28[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v29[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = *(_DWORD *)(a1 + 56);
  v22 = 0;
  ppvData = 0;
  v23 = v4;
  v25 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::GetNamedItem", 25, &v25, 8, &v23, 4, v20, v21);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v9 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v26.vt = *(_OWORD *)a2;
  v26.pRecInfo = v9;
  v10 = Enumerator::GetIndex<IValueMapItem>(a1, &v26, a3, (unsigned int *)&v22);
  v11 = v10;
  if ( v10 < 0 )
  {
    v23 = 0;
    v22 = v10;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v27[v17] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v22,
        4,
        qword_180147320,
        1,
        &v23,
        4,
        "Enumerator::GetNamedItem",
        25);
    }
    v12 = (SAFEARRAY **)(a1 + 64);
  }
  else
  {
    v12 = (SAFEARRAY **)(a1 + 64);
    v13 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v11 = v13;
    if ( v13 < 0 )
    {
      v23 = 0;
      v22 = v13;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v28[v18] );
        goto LABEL_23;
      }
    }
    else
    {
      v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * (unsigned int)v22 + 1);
      v15 = (**v14)(v14, &GUID_03837533_098b_11d8_9414_505054503030, a4);
      v11 = v15;
      if ( v15 < 0 )
      {
        v23 = 0;
        v22 = v15;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v29, 0x4000000000000800uLL);
            v19 = -1;
            do
              ++v19;
            while ( v29[v19] );
LABEL_23:
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              &v22,
              4,
              qword_180147320,
              1,
              &v23,
              4,
              "Enumerator::GetNamedItem",
              25);
          }
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v12);
  return v11;
}

```

## disassembly

```asm
0x1800335d8  push    rbp
0x1800335da  push    rbx
0x1800335db  push    rsi
0x1800335dc  push    rdi
0x1800335dd  push    r12
0x1800335df  push    r13
0x1800335e1  push    r14
0x1800335e3  push    r15
0x1800335e5  lea     rbp, [rsp-148h]
0x1800335ed  sub     rsp, 248h
0x1800335f4  mov     rax, cs:__security_cookie
0x1800335fb  xor     rax, rsp
0x1800335fe  mov     [rbp+180h+var_50], rax
0x180033605  mov     eax, [rcx+38h]
0x180033608  xor     r15d, r15d
0x18003360b  cmp     dword ptr cs:xmmword_180169738, r15d
0x180033612  mov     r14, r9
0x180033615  mov     rsi, r8
0x180033618  mov     [rsp+280h+var_210], r15d
0x18003361d  mov     rbx, rdx
0x180033620  mov     [rbp+180h+ppvData], r15
0x180033624  lea     r12d, [r15+4]
0x180033628  mov     [rsp+280h+var_208], eax
0x18003362c  lea     r13d, [r15+19h]
0x180033630  mov     [rbp+180h+var_1F8], rcx
0x180033634  mov     rdi, rcx
0x180033637  jz      short loc_180033650
0x180033639  mov     rdx, 4000000000000400h
0x180033643  test    qword ptr cs:xmmword_180169738+8, rdx
0x18003364a  jnz     loc_180033720
0x180033650  cmp     [rdi+8], r15d
0x180033654  jz      short loc_180033660
0x180033656  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003365a  call    cs:__imp_EnterCriticalSection
0x180033660  movaps  xmm0, xmmword ptr [rbx]
0x180033663  lea     r9, [rsp+280h+var_210]
0x180033668  movsd   xmm1, qword ptr [rbx+10h]
0x18003366d  lea     rdx, [rbp+180h+var_1F0]
0x180033671  mov     r8, rsi
0x180033674  movaps  [rbp+180h+var_1F0], xmm0
0x180033678  mov     rcx, rdi
0x18003367b  movsd   [rbp+180h+var_1E0], xmm1
0x180033680  call    ??$GetIndex@UIValueMapItem@@@Enumerator@@IEAAJUtagVARIANT@@P8IValueMapItem@@EAAJPEAPEAG@ZPEAK@Z
0x180033685  mov     esi, eax
0x180033687  test    eax, eax
0x180033689  js      loc_180033915
0x18003368f  lea     rbx, [rdi+40h]
0x180033693  mov     rcx, [rbx]; psa
0x180033696  lea     rdx, [rbp+180h+ppvData]; ppvData
0x18003369a  call    cs:__imp_SafeArrayAccessData
0x1800336a0  mov     esi, eax
0x1800336a2  test    eax, eax
0x1800336a4  js      loc_180033947
0x1800336aa  mov     eax, [rsp+280h+var_210]
0x1800336ae  lea     rdx, _GUID_03837533_098b_11d8_9414_505054503030
0x1800336b5  mov     r8, r14
0x1800336b8  lea     rcx, [rax+rax*2]
0x1800336bc  mov     rax, [rbp+180h+ppvData]
0x1800336c0  mov     rcx, [rax+rcx*8+8]
0x1800336c5  mov     rax, [rcx]
0x1800336c8  mov     rax, [rax]
0x1800336cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336d0  mov     esi, eax
0x1800336d2  test    eax, eax
0x1800336d4  js      loc_180033979
0x1800336da  cmp     [rdi+8], r15d
0x1800336de  jz      short loc_1800336EA
0x1800336e0  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800336e4  call    cs:__imp_LeaveCriticalSection
0x1800336ea  cmp     [rbp+180h+ppvData], r15
0x1800336ee  jnz     short loc_180033715
0x1800336f0  mov     eax, esi
0x1800336f2  mov     rcx, [rbp+180h+var_50]
0x1800336f9  xor     rcx, rsp; StackCookie
0x1800336fc  call    __security_check_cookie
0x180033701  add     rsp, 248h
0x180033708  pop     r15
0x18003370a  pop     r14
0x18003370c  pop     r13
0x18003370e  pop     r12
0x180033710  pop     rdi
0x180033711  pop     rsi
0x180033712  pop     rbx
0x180033713  pop     rbp
0x180033714  retn
0x180033715  mov     rcx, [rbx]; psa
0x180033718  call    cs:__imp_SafeArrayUnaccessData
0x18003371e  jmp     short loc_1800336F0
0x180033720  mov     rax, cs:qword_180169748
0x180033727  and     rax, rdx
0x18003372a  cmp     cs:qword_180169748, rax
0x180033731  jnz     loc_180033650
0x180033737  mov     [rsp+280h+var_240], r12
0x18003373c  lea     rax, [rsp+280h+var_208]
0x180033741  mov     [rsp+280h+var_248], rax
0x180033746  lea     r9, aEnumeratorGetn
0x18003374d  lea     rax, [rbp+180h+var_1F8]
0x180033751  mov     [rsp+280h+var_250], 8
0x18003375a  mov     [rsp+280h+var_258], rax
0x18003375f  lea     rdx, PLA_EVENT_METHOD
0x180033766  mov     r8d, 3
0x18003376c  mov     [rsp+280h+var_260], r13
0x180033771  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A
0x180033778  call    EventingWriteEvent
0x18003377d  jmp     loc_180033650
0x180033782  mov     rax, cs:qword_180169748
0x180033789  and     rax, rdx
0x18003378c  cmp     cs:qword_180169748, rax
0x180033793  jnz     loc_180033821
0x180033799  lea     rcx, [rbp+180h+var_1D0]; unsigned __int16 *
0x18003379d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z
0x1800337a2  lea     rcx, [rbp+180h+var_1D0]
0x1800337a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800337aa  inc     rax
0x1800337ad  cmp     [rcx+rax*2], r15w
0x1800337b2  jnz     short loc_1800337AA
0x1800337b4  lea     ecx, [rax+rax]
0x1800337b7  mov     r8d, 5
0x1800337bd  add     rcx, 2
0x1800337c1  lea     rax, [rbp+180h+var_1D0]
0x1800337c5  mov     [rsp+280h+var_220], rcx
0x1800337ca  lea     r9, [rsp+280h+var_210]
0x1800337cf  mov     [rsp+280h+var_228], rax
0x1800337d4  lea     rdx, PLA_EVENT_ERROR
0x1800337db  mov     [rsp+280h+var_230], r13
0x1800337e0  lea     rax, aEnumeratorGetn
0x1800337e7  mov     [rsp+280h+var_238], rax
0x1800337ec  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A
0x1800337f3  mov     [rsp+280h+var_240], r12
0x1800337f8  lea     rax, [rsp+280h+var_208]
0x1800337fd  mov     [rsp+280h+var_248], rax
0x180033802  lea     rax, qword_180147320
0x180033809  mov     [rsp+280h+var_250], 1
0x180033812  mov     [rsp+280h+var_258], rax
0x180033817  mov     [rsp+280h+var_260], r12
0x18003381c  call    EventingWriteEvent
0x180033821  lea     rbx, [rdi+40h]
0x180033825  jmp     loc_1800336DA
0x18003382a  mov     rax, cs:qword_180169748
0x180033831  and     rax, rdx
0x180033834  cmp     cs:qword_180169748, rax
0x18003383b  jnz     loc_1800336DA
0x180033841  lea     rcx, [rbp+180h+var_150]; unsigned __int16 *
0x180033845  call    ?PlaiWhoAmI@@YAJPEAG_K@Z
0x18003384a  lea     rcx, [rbp+180h+var_150]
0x18003384e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033852  inc     rax
0x180033855  cmp     [rcx+rax*2], r15w
0x18003385a  jnz     short loc_180033852
0x18003385c  lea     ecx, [rax+rax]
0x18003385f  lea     rax, [rbp+180h+var_150]
0x180033863  add     rcx, 2
0x180033867  lea     r9, [rsp+280h+var_210]
0x18003386c  mov     [rsp+280h+var_220], rcx
0x180033871  lea     rdx, PLA_EVENT_ERROR
0x180033878  mov     [rsp+280h+var_228], rax
0x18003387d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A
0x180033884  mov     [rsp+280h+var_230], r13
0x180033889  lea     rax, aEnumeratorGetn
0x180033890  mov     [rsp+280h+var_238], rax
0x180033895  mov     r8d, 5
0x18003389b  mov     [rsp+280h+var_240], r12
0x1800338a0  lea     rax, [rsp+280h+var_208]
0x1800338a5  mov     [rsp+280h+var_248], rax
0x1800338aa  lea     rax, qword_180147320
0x1800338b1  mov     [rsp+280h+var_250], 1
0x1800338ba  mov     [rsp+280h+var_258], rax
0x1800338bf  mov     [rsp+280h+var_260], r12
0x1800338c4  call    EventingWriteEvent
0x1800338c9  jmp     loc_1800336DA
0x1800338ce  mov     rax, cs:qword_180169748
0x1800338d5  and     rax, rdx
0x1800338d8  cmp     cs:qword_180169748, rax
0x1800338df  jnz     loc_1800336DA
0x1800338e5  lea     rcx, [rbp+180h+var_D0]; unsigned __int16 *
0x1800338ec  call    ?PlaiWhoAmI@@YAJPEAG_K@Z
0x1800338f1  lea     rcx, [rbp+180h+var_D0]
0x1800338f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800338fc  inc     rax
0x1800338ff  cmp     [rcx+rax*2], r15w
0x180033904  jnz     short loc_1800338FC
0x180033906  lea     ecx, [rax+rax]
0x180033909  lea     rax, [rbp+180h+var_D0]
0x180033910  jmp     loc_180033863
0x180033915  cmp     dword ptr cs:xmmword_180169738, r15d
0x18003391c  mov     [rsp+280h+var_208], r15d
0x180033921  mov     [rsp+280h+var_210], eax
0x180033925  jz      loc_180033821
0x18003392b  mov     rdx, 4000000000000800h; unsigned __int64
0x180033935  test    qword ptr cs:xmmword_180169738+8, rdx
0x18003393c  jz      loc_180033821
0x180033942  jmp     loc_180033782
0x180033947  cmp     dword ptr cs:xmmword_180169738, r15d
0x18003394e  mov     [rsp+280h+var_208], r15d
0x180033953  mov     [rsp+280h+var_210], eax
0x180033957  jz      loc_1800336DA
0x18003395d  mov     rdx, 4000000000000800h; unsigned __int64
0x180033967  test    qword ptr cs:xmmword_180169738+8, rdx
0x18003396e  jz      loc_1800336DA
0x180033974  jmp     loc_18003382A
0x180033979  cmp     dword ptr cs:xmmword_180169738, r15d
0x180033980  mov     [rsp+280h+var_208], r15d
0x180033985  mov     [rsp+280h+var_210], eax
0x180033989  jz      loc_1800336DA
0x18003398f  mov     rdx, 4000000000000800h; unsigned __int64
0x180033999  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800339a0  jz      loc_1800336DA
0x1800339a6  jmp     loc_1800338CE
```
