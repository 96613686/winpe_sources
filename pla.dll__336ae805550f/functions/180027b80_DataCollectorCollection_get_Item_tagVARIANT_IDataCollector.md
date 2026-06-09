# DataCollectorCollection::get_Item(tagVARIANT,IDataCollector * *)

- ea: `0x180027b80`
- end: `0x1800281ab`
- name: `?get_Item@DataCollectorCollection@@UEAAJUtagVARIANT@@PEAPEAUIDataCollector@@@Z`
- size: `1579`
- prototype: `__int64 __fastcall(DataCollectorCollection *__hidden this, struct tagVARIANT *__struct_ptr, struct IDataCollector **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180027b80`
- `0x1800281c0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027bfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027bfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c4e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180027ca2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180027ca2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027d09`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027d09`

## pseudocode

```c
__int64 __fastcall DataCollectorCollection::get_Item(
        DataCollectorCollection *this,
        struct tagVARIANT *a2,
        struct IDataCollector **a3)
{
  unsigned int v3; // eax
  unsigned __int64 v5; // rdx
  unsigned __int64 v7; // rcx
  __int64 v9; // r14
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned __int64 v11; // rdx
  int v12; // esi
  __int64 v13; // rdi
  SAFEARRAY **v14; // r15
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct IDataCollector **); // rcx
  int v16; // eax
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v26; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v28[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v29[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v30[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v31[64]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v3 = *((_DWORD *)this + 14);
  v5 = (unsigned int)xmmword_180169738;
  ppvData = this;
  v7 = qword_180169748;
  v22 = v3;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "DataCollectorCollection::get_Item", 34, &ppvData, 8, &v22, 4);
    v7 = qword_180169748;
    v5 = (unsigned int)xmmword_180169738;
  }
  if ( *((_DWORD *)this + 2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v7 = qword_180169748;
    v5 = (unsigned int)xmmword_180169738;
  }
  v9 = *((_QWORD *)this + 9);
  v22 = 0;
  if ( v9 )
  {
    v23 = *(_DWORD *)(v9 + 56);
    ppvData = 0;
    v25 = v9;
    if ( (_DWORD)v5 && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0 && v7 == (v7 & 0x4000000000000400LL) )
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::GetNamedItem", 25, &v25, 8, &v23, 4);
    if ( *(_DWORD *)(v9 + 8) )
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    pRecInfo = a2->pRecInfo;
    *(_OWORD *)&v26.vt = *(_OWORD *)&a2->vt;
    v26.pRecInfo = pRecInfo;
    v12 = Enumerator::GetIndex<IDataCollector>(v9, &v26, (__int64)a3, &v22);
    v13 = -1;
    if ( v12 < 0 )
    {
      v23 = 0;
      v22 = v12;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v28, v11);
        v18 = -1;
        do
          ++v18;
        while ( v28[v18] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v22, 4, byte_180147320, 1, &v23, 4);
      }
      v14 = (SAFEARRAY **)(v9 + 64);
      goto LABEL_13;
    }
    v14 = (SAFEARRAY **)(v9 + 64);
    v12 = SafeArrayAccessData(*(SAFEARRAY **)(v9 + 64), &ppvData);
    if ( v12 < 0 )
    {
      v23 = 0;
      v22 = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_13;
      }
      PlaiWhoAmI(v29, v11);
      v20 = -1;
      do
        ++v20;
      while ( v29[v20] );
    }
    else
    {
      v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IDataCollector **))*((_QWORD *)ppvData + 3 * v22 + 1);
      v16 = (**v15)(v15, &GUID_038374ff_098b_11d8_9414_505054503030, a3);
      v12 = v16;
      if ( v16 >= 0 )
        goto LABEL_13;
      v23 = 0;
      v22 = v16;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_13;
      }
      PlaiWhoAmI(v30, v11);
      v21 = -1;
      do
        ++v21;
      while ( v30[v21] );
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v22, 4, byte_180147320, 1, &v23, 4);
LABEL_13:
    if ( *(_DWORD *)(v9 + 8) )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    if ( ppvData )
      SafeArrayUnaccessData(*v14);
    if ( v12 < 0 )
    {
      v23 = 0;
      v22 = v12;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v31, v11);
          do
            ++v13;
          while ( v31[v13] );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v22, 4, byte_180147320, 1, &v23, 4);
        }
      }
    }
    goto LABEL_18;
  }
  v12 = -2147024882;
  v23 = -2147024882;
  if ( (_DWORD)v5 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v7 == (v7 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v27, v5);
    v19 = -1;
    do
      ++v19;
    while ( v27[v19] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v23, 4, byte_180147320, 1, &v22, 4);
  }
LABEL_18:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027b80  mov     [rsp-8+arg_18], rbx
0x180027b85  push    rbp
0x180027b86  push    rsi
0x180027b87  push    rdi
0x180027b88  push    r12
0x180027b8a  push    r13
0x180027b8c  push    r14
0x180027b8e  push    r15
0x180027b90  lea     rbp, [rsp-240h]
0x180027b98  sub     rsp, 340h
0x180027b9f  mov     rax, cs:__security_cookie
0x180027ba6  xor     rax, rsp
0x180027ba9  mov     [rbp+270h+var_40], rax
0x180027bb0  mov     eax, [rcx+38h]
0x180027bb3  mov     rbx, rdx
0x180027bb6  mov     edx, dword ptr cs:xmmword_180169738
0x180027bbc  xor     r15d, r15d
0x180027bbf  mov     [rbp+270h+ppvData], rcx
0x180027bc3  mov     r13, rcx
0x180027bc6  mov     rcx, cs:qword_180169748
0x180027bcd  mov     r12, r8
0x180027bd0  mov     [rsp+370h+var_300], eax
0x180027bd4  mov     rdi, 4000000000000400h
0x180027bde  mov     esi, 8
0x180027be3  test    edx, edx
0x180027be5  jz      short loc_180027BF4
0x180027be7  test    qword ptr cs:xmmword_180169738+8, rdi
0x180027bee  jnz     loc_180027E25
0x180027bf4  cmp     [r13+8], r15d
0x180027bf8  jz      short loc_180027C11
0x180027bfa  lea     rcx, [r13+10h]; lpCriticalSection
0x180027bfe  call    cs:__imp_EnterCriticalSection
0x180027c04  mov     rcx, cs:qword_180169748
0x180027c0b  mov     edx, dword ptr cs:xmmword_180169738; unsigned __int64
0x180027c11  mov     r14, [r13+48h]
0x180027c15  mov     [rsp+370h+var_300], r15d
0x180027c1a  test    r14, r14
0x180027c1d  jz      loc_180028130
0x180027c23  mov     eax, [r14+38h]
0x180027c27  mov     [rsp+370h+var_2F8], eax
0x180027c2b  mov     [rbp+270h+ppvData], r15
0x180027c2f  mov     [rbp+270h+var_2E8], r14
0x180027c33  test    edx, edx
0x180027c35  jz      short loc_180027C44
0x180027c37  test    qword ptr cs:xmmword_180169738+8, rdi
0x180027c3e  jnz     loc_180027E90
0x180027c44  cmp     [r14+8], r15d
0x180027c48  jz      short loc_180027C54
0x180027c4a  lea     rcx, [r14+10h]; lpCriticalSection
0x180027c4e  call    cs:__imp_EnterCriticalSection
0x180027c54  movups  xmm0, xmmword ptr [rbx]
0x180027c57  lea     r9, [rsp+370h+var_300]
0x180027c5c  mov     rcx, r14
0x180027c5f  movsd   xmm1, qword ptr [rbx+10h]
0x180027c64  lea     rdx, [rbp+270h+var_2E0]
0x180027c68  movaps  [rbp+270h+var_2E0], xmm0
0x180027c6c  movsd   [rbp+270h+var_2D0], xmm1
0x180027c71  call    ??$GetIndex@UIDataCollector@@@Enumerator@@IEAAJUtagVARIANT@@P8IDataCollector@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IDataCollector>(tagVARIANT,long (IDataCollector::*)(ushort * *),ulong *)
0x180027c76  mov     esi, eax
0x180027c78  lea     r15, byte_180147320
0x180027c7f  xor     eax, eax
0x180027c81  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027c85  mov     rbx, 4000000000000800h
0x180027c8f  test    esi, esi
0x180027c91  js      loc_180027D52
0x180027c97  lea     r15, [r14+40h]
0x180027c9b  mov     rcx, [r15]; psa
0x180027c9e  lea     rdx, [rbp+270h+ppvData]; ppvData
0x180027ca2  call    cs:__imp_SafeArrayAccessData
0x180027ca8  mov     esi, eax
0x180027caa  xor     eax, eax
0x180027cac  test    esi, esi
0x180027cae  js      loc_18002815D
0x180027cb4  mov     eax, [rsp+370h+var_300]
0x180027cb8  lea     rdx, _GUID_038374ff_098b_11d8_9414_505054503030
0x180027cbf  mov     r8, r12
0x180027cc2  lea     rcx, [rax+rax*2]
0x180027cc6  mov     rax, [rbp+270h+ppvData]
0x180027cca  mov     rcx, [rax+rcx*8+8]
0x180027ccf  mov     rax, [rcx]
0x180027cd2  mov     rax, [rax]
0x180027cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cda  xor     r12d, r12d
0x180027cdd  mov     esi, eax
0x180027cdf  test    eax, eax
0x180027ce1  js      loc_180028183
0x180027ce7  lea     r12, byte_180147320
0x180027cee  cmp     dword ptr [r14+8], 0
0x180027cf3  jz      short loc_180027CFF
0x180027cf5  lea     rcx, [r14+10h]; lpCriticalSection
0x180027cf9  call    cs:__imp_LeaveCriticalSection
0x180027cff  cmp     [rbp+270h+ppvData], 0
0x180027d04  jz      short loc_180027D0F
0x180027d06  mov     rcx, [r15]; psa
0x180027d09  call    cs:__imp_SafeArrayUnaccessData
0x180027d0f  xor     r15d, r15d
0x180027d12  test    esi, esi
0x180027d14  js      short loc_180027D78
0x180027d16  cmp     [r13+8], r15d
0x180027d1a  jz      short loc_180027D26
0x180027d1c  lea     rcx, [r13+10h]; lpCriticalSection
0x180027d20  call    cs:__imp_LeaveCriticalSection
0x180027d26  mov     eax, esi
0x180027d28  mov     rcx, [rbp+270h+var_40]
0x180027d2f  xor     rcx, rsp; StackCookie
0x180027d32  call    __security_check_cookie
0x180027d37  mov     rbx, [rsp+370h+arg_18]
0x180027d3f  add     rsp, 340h
0x180027d46  pop     r15
0x180027d48  pop     r14
0x180027d4a  pop     r13
0x180027d4c  pop     r12
0x180027d4e  pop     rdi
0x180027d4f  pop     rsi
0x180027d50  pop     rbp
0x180027d51  retn
0x180027d52  cmp     dword ptr cs:xmmword_180169738, eax
0x180027d58  mov     [rsp+370h+var_2F8], eax
0x180027d5c  mov     [rsp+370h+var_300], esi
0x180027d60  jz      short loc_180027D6F
0x180027d62  test    qword ptr cs:xmmword_180169738+8, rbx
0x180027d69  jnz     loc_180027EED
0x180027d6f  lea     r15, [r14+40h]
0x180027d73  jmp     loc_180027CE7
0x180027d78  cmp     dword ptr cs:xmmword_180169738, r15d
0x180027d7f  mov     [rsp+370h+var_2F8], r15d
0x180027d84  mov     [rsp+370h+var_300], esi
0x180027d88  jz      short loc_180027D16
0x180027d8a  test    qword ptr cs:xmmword_180169738+8, rbx
0x180027d91  jz      short loc_180027D16
0x180027d93  mov     rax, cs:qword_180169748
0x180027d9a  and     rax, rbx
0x180027d9d  cmp     cs:qword_180169748, rax
0x180027da4  jnz     loc_180027D16
0x180027daa  lea     rcx, [rbp+270h+var_C0]; unsigned __int16 *
0x180027db1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180027db6  lea     rax, [rbp+270h+var_C0]
0x180027dbd  inc     rdi
0x180027dc0  cmp     [rax+rdi*2], r15w
0x180027dc5  jnz     short loc_180027DBD
0x180027dc7  lea     rax, [rbp+270h+var_C0]
0x180027dce  lea     ecx, [rdi+rdi]
0x180027dd1  add     rcx, 2
0x180027dd5  lea     r9, [rsp+370h+var_300]
0x180027dda  mov     [rsp+370h+var_310], rcx
0x180027ddf  mov     ecx, 4
0x180027de4  mov     [rsp+370h+var_318], rax
0x180027de9  lea     rax, aDatacollectorc_0; "DataCollectorCollection::get_Item"
0x180027df0  mov     [rsp+370h+var_320], 22h ; '"'
0x180027df9  mov     [rsp+370h+var_328], rax
0x180027dfe  lea     rax, [rsp+370h+var_2F8]
0x180027e03  mov     [rsp+370h+var_330], rcx
0x180027e08  mov     [rsp+370h+var_338], rax
0x180027e0d  mov     [rsp+370h+var_340], 1
0x180027e16  mov     [rsp+370h+var_348], r12
0x180027e1b  mov     [rsp+370h+var_350], rcx
0x180027e20  jmp     loc_180028018
0x180027e25  mov     rax, rcx
0x180027e28  and     rax, rdi
0x180027e2b  cmp     rcx, rax
0x180027e2e  jnz     loc_180027BF4
0x180027e34  mov     [rsp+370h+var_330], 4
0x180027e3d  lea     rax, [rsp+370h+var_300]
0x180027e42  mov     [rsp+370h+var_338], rax
0x180027e47  lea     r9, aDatacollectorc_0; "DataCollectorCollection::get_Item"
0x180027e4e  lea     rax, [rbp+270h+ppvData]
0x180027e52  mov     [rsp+370h+var_340], rsi
0x180027e57  mov     [rsp+370h+var_348], rax
0x180027e5c  lea     rdx, PLA_EVENT_METHOD
0x180027e63  mov     r8d, 3
0x180027e69  mov     [rsp+370h+var_350], 22h ; '"'
0x180027e72  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180027e79  call    EventingWriteEvent
0x180027e7e  mov     rcx, cs:qword_180169748
0x180027e85  mov     edx, dword ptr cs:xmmword_180169738
0x180027e8b  jmp     loc_180027BF4
0x180027e90  mov     rax, rcx
0x180027e93  and     rax, rdi
0x180027e96  cmp     rcx, rax
0x180027e99  jnz     loc_180027C44
0x180027e9f  mov     edx, 4
0x180027ea4  lea     rax, [rsp+370h+var_2F8]
0x180027ea9  mov     [rsp+370h+var_330], rdx
0x180027eae  lea     r9, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180027eb5  mov     [rsp+370h+var_338], rax
0x180027eba  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180027ec1  lea     rax, [rbp+270h+var_2E8]
0x180027ec5  mov     [rsp+370h+var_340], rsi
0x180027eca  lea     r8d, [rdx-1]
0x180027ece  mov     [rsp+370h+var_348], rax
0x180027ed3  lea     rdx, PLA_EVENT_METHOD
0x180027eda  mov     [rsp+370h+var_350], 19h
0x180027ee3  call    EventingWriteEvent
0x180027ee8  jmp     loc_180027C44
0x180027eed  mov     rax, cs:qword_180169748
0x180027ef4  and     rax, rbx
0x180027ef7  cmp     cs:qword_180169748, rax
0x180027efe  jnz     loc_180027D6F
0x180027f04  lea     rcx, [rbp+270h+var_240]; unsigned __int16 *
0x180027f08  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180027f0d  lea     rdx, [rbp+270h+var_240]
0x180027f11  mov     rax, rdi
0x180027f14  xor     ecx, ecx
0x180027f16  inc     rax
0x180027f19  cmp     [rdx+rax*2], cx
0x180027f1d  jnz     short loc_180027F16
0x180027f1f  lea     ecx, [rax+rax]
0x180027f22  add     rcx, 2
0x180027f26  lea     rax, [rbp+270h+var_240]
0x180027f2a  mov     [rsp+370h+var_310], rcx
0x180027f2f  lea     r9, [rsp+370h+var_300]
0x180027f34  mov     [rsp+370h+var_318], rax
0x180027f39  lea     rdx, PLA_EVENT_ERROR
0x180027f40  mov     [rsp+370h+var_320], 19h
0x180027f49  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180027f50  mov     [rsp+370h+var_328], rax
0x180027f55  mov     ecx, 4
0x180027f5a  mov     [rsp+370h+var_330], rcx
0x180027f5f  lea     rax, [rsp+370h+var_2F8]
0x180027f64  mov     [rsp+370h+var_338], rax
0x180027f69  mov     [rsp+370h+var_340], 1
0x180027f72  lea     r8d, [rcx+1]
0x180027f76  mov     [rsp+370h+var_348], r15
0x180027f7b  mov     [rsp+370h+var_350], rcx
0x180027f80  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180027f87  call    EventingWriteEvent
0x180027f8c  jmp     loc_180027D6F
0x180027f91  mov     rax, rcx
0x180027f94  and     rax, rbx
0x180027f97  cmp     rcx, rax
0x180027f9a  jnz     loc_180027D16
0x180027fa0  lea     rcx, [rbp+270h+var_2C0]; unsigned __int16 *
0x180027fa4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180027fa9  lea     rax, [rbp+270h+var_2C0]
0x180027fad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027fb1  inc     rdi
0x180027fb4  cmp     [rax+rdi*2], r15w
0x180027fb9  jnz     short loc_180027FB1
0x180027fbb  lea     rax, [rbp+270h+var_2C0]
0x180027fbf  mov     edx, 4
0x180027fc4  lea     ecx, [rdi+rdi]
0x180027fc7  add     rcx, 2
0x180027fcb  lea     r9, [rsp+370h+var_2F8]
0x180027fd0  mov     [rsp+370h+var_310], rcx
0x180027fd5  mov     [rsp+370h+var_318], rax
0x180027fda  lea     rax, aDatacollectorc_0; "DataCollectorCollection::get_Item"
0x180027fe1  mov     [rsp+370h+var_320], 22h ; '"'
0x180027fea  mov     [rsp+370h+var_328], rax
0x180027fef  lea     rax, [rsp+370h+var_300]
0x180027ff4  mov     [rsp+370h+var_330], rdx
0x180027ff9  mov     [rsp+370h+var_338], rax
0x180027ffe  lea     rax, byte_180147320
0x180028005  mov     [rsp+370h+var_340], 1
0x18002800e  mov     [rsp+370h+var_348], rax
0x180028013  mov     [rsp+370h+var_350], rdx
0x180028018  mov     r8d, 5
0x18002801e  lea     rdx, PLA_EVENT_ERROR
0x180028025  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002802c  call    EventingWriteEvent
0x180028031  jmp     loc_180027D16
0x180028036  mov     rax, cs:qword_180169748
0x18002803d  and     rax, rbx
0x180028040  cmp     cs:qword_180169748, rax
0x180028047  jnz     loc_180027CE7
0x18002804d  lea     rcx, [rbp+270h+var_1C0]; unsigned __int16 *
0x180028054  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180028059  lea     rdx, [rbp+270h+var_1C0]
0x180028060  mov     rax, rdi
0x180028063  xor     ecx, ecx
0x180028065  inc     rax
0x180028068  cmp     [rdx+rax*2], cx
0x18002806c  jnz     short loc_180028065
0x18002806e  lea     ecx, [rax+rax]
0x180028071  lea     rax, [rbp+270h+var_1C0]
0x180028078  add     rcx, 2
0x18002807c  lea     r12, byte_180147320
0x180028083  mov     [rsp+370h+var_310], rcx
0x180028088  lea     r9, [rsp+370h+var_300]
0x18002808d  mov     [rsp+370h+var_318], rax
0x180028092  lea     rdx, PLA_EVENT_ERROR
0x180028099  mov     [rsp+370h+var_320], 19h
0x1800280a2  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1800280a9  mov     [rsp+370h+var_328], rax
0x1800280ae  mov     ecx, 4
0x1800280b3  mov     [rsp+370h+var_330], rcx
0x1800280b8  lea     rax, [rsp+370h+var_2F8]
0x1800280bd  mov     [rsp+370h+var_338], rax
0x1800280c2  mov     [rsp+370h+var_340], 1
0x1800280cb  lea     r8d, [rcx+1]
0x1800280cf  mov     [rsp+370h+var_348], r12
0x1800280d4  mov     [rsp+370h+var_350], rcx
0x1800280d9  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800280e0  call    EventingWriteEvent
0x1800280e5  jmp     loc_180027CEE
0x1800280ea  mov     rax, cs:qword_180169748
0x1800280f1  and     rax, rbx
0x1800280f4  cmp     cs:qword_180169748, rax
0x1800280fb  jnz     loc_180027CE7
0x180028101  lea     rcx, [rbp+270h+var_140]; unsigned __int16 *
0x180028108  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
  ... truncated ...
```
