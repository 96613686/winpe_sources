# Enumerator::GetNamedItem<ISchedule>(tagVARIANT,long (ISchedule::*)(ushort * *),ISchedule * *)

- ea: `0x1800ebb70`
- end: `0x1800ebf1e`
- name: `??$GetNamedItem@UISchedule@@@Enumerator@@QEAAJUtagVARIANT@@P8ISchedule@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `942`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800eba78`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800ebb70`
- `0x180122938`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebedd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebc45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebc45`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800ebd57`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800ebd57`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800ebeec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800ebeec`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<ISchedule>(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  IRecordInfo *v8; // xmm1_8
  int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // rax
  SAFEARRAY **v12; // rbx
  HRESULT v13; // eax
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rcx
  int v16; // eax
  __int64 v17; // rax
  __int64 v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v25; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v27[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v28[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = *(_DWORD *)(a1 + 56);
  v21 = 0;
  ppvData = 0;
  v22 = v4;
  v24 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::GetNamedItem", 25, &v24, 8, &v22, 4, v19, v20);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v8 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v25.vt = *(_OWORD *)a2;
  v25.pRecInfo = v8;
  v9 = Enumerator::GetIndex<ISchedule>(a1, &v25, a3, (unsigned int *)&v21);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = (SAFEARRAY **)(a1 + 64);
    v13 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * (unsigned int)v21 + 1);
      v16 = (**v15)(v15, &GUID_0383753a_098b_11d8_9414_505054503030, a4);
      v10 = v16;
      if ( v16 >= 0 )
        goto LABEL_29;
      v22 = 0;
      v21 = v16;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_29;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v28[v17] );
    }
    else
    {
      v22 = 0;
      v21 = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_29;
      }
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v27[v14] );
    }
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v21,
      4,
      qword_180147320,
      1,
      &v22,
      4,
      "Enumerator::GetNamedItem",
      25);
    goto LABEL_29;
  }
  v22 = 0;
  v21 = v9;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v26, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v26[v11] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v21,
      4,
      qword_180147320,
      1,
      &v22,
      4,
      "Enumerator::GetNamedItem",
      25);
  }
  v12 = (SAFEARRAY **)(a1 + 64);
LABEL_29:
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v12);
  return v10;
}

```

## disassembly

```asm
0x1800ebb70  mov     [rsp-8+arg_10], rbx
0x1800ebb75  push    rbp
0x1800ebb76  push    rsi
0x1800ebb77  push    rdi
0x1800ebb78  push    r12
0x1800ebb7a  push    r13
0x1800ebb7c  push    r14
0x1800ebb7e  push    r15
0x1800ebb80  lea     rbp, [rsp-140h]
0x1800ebb88  sub     rsp, 240h
0x1800ebb8f  mov     rax, cs:__security_cookie
0x1800ebb96  xor     rax, rsp
0x1800ebb99  mov     [rbp+170h+var_40], rax
0x1800ebba0  mov     eax, [rcx+38h]
0x1800ebba3  xor     r15d, r15d
0x1800ebba6  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800ebbad  mov     r14, r9
0x1800ebbb0  mov     rbx, rdx
0x1800ebbb3  mov     [rsp+270h+var_200], r15d
0x1800ebbb8  mov     rdi, rcx
0x1800ebbbb  mov     [rbp+170h+ppvData], r15
0x1800ebbbf  lea     r12d, [r15+4]
0x1800ebbc3  mov     [rsp+270h+var_1F8], eax
0x1800ebbc7  lea     r13d, [r15+19h]
0x1800ebbcb  mov     [rbp+170h+var_1E8], rcx
0x1800ebbcf  jz      short loc_1800EBC3B
0x1800ebbd1  mov     rdx, 4000000000000400h
0x1800ebbdb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ebbe2  jz      short loc_1800EBC3B
0x1800ebbe4  mov     rax, cs:qword_180169748
0x1800ebbeb  and     rax, rdx
0x1800ebbee  cmp     cs:qword_180169748, rax
0x1800ebbf5  jnz     short loc_1800EBC3B
0x1800ebbf7  mov     [rsp+270h+var_230], r12
0x1800ebbfc  lea     rax, [rsp+270h+var_1F8]
0x1800ebc01  mov     [rsp+270h+var_238], rax
0x1800ebc06  lea     r9, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1800ebc0d  lea     rax, [rbp+170h+var_1E8]
0x1800ebc11  mov     [rsp+270h+var_240], 8
0x1800ebc1a  mov     [rsp+270h+var_248], rax
0x1800ebc1f  lea     r8d, [r15+3]
0x1800ebc23  lea     rdx, PLA_EVENT_METHOD
0x1800ebc2a  mov     [rsp+270h+var_250], r13
0x1800ebc2f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ebc36  call    EventingWriteEvent
0x1800ebc3b  cmp     [rdi+8], r15d
0x1800ebc3f  jz      short loc_1800EBC4B
0x1800ebc41  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800ebc45  call    cs:__imp_EnterCriticalSection
0x1800ebc4b  movaps  xmm0, xmmword ptr [rbx]
0x1800ebc4e  lea     r9, [rsp+270h+var_200]
0x1800ebc53  movsd   xmm1, qword ptr [rbx+10h]
0x1800ebc58  lea     rdx, [rbp+170h+var_1E0]
0x1800ebc5c  mov     rcx, rdi
0x1800ebc5f  movaps  [rbp+170h+var_1E0], xmm0
0x1800ebc63  movsd   [rbp+170h+var_1D0], xmm1
0x1800ebc68  call    ??$GetIndex@UISchedule@@@Enumerator@@IEAAJUtagVARIANT@@P8ISchedule@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<ISchedule>(tagVARIANT,long (ISchedule::*)(ushort * *),ulong *)
0x1800ebc6d  mov     esi, eax
0x1800ebc6f  test    eax, eax
0x1800ebc71  jns     loc_1800EBD4C
0x1800ebc77  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800ebc7e  mov     [rsp+270h+var_1F8], r15d
0x1800ebc83  mov     [rsp+270h+var_200], eax
0x1800ebc87  jz      loc_1800EBD43
0x1800ebc8d  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ebc97  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ebc9e  jz      loc_1800EBD43
0x1800ebca4  mov     rax, cs:qword_180169748
0x1800ebcab  and     rax, rdx
0x1800ebcae  cmp     cs:qword_180169748, rax
0x1800ebcb5  jnz     loc_1800EBD43
0x1800ebcbb  lea     rcx, [rbp+170h+var_1C0]; unsigned __int16 *
0x1800ebcbf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ebcc4  lea     rcx, [rbp+170h+var_1C0]
0x1800ebcc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ebccc  inc     rax
0x1800ebccf  cmp     [rcx+rax*2], r15w
0x1800ebcd4  jnz     short loc_1800EBCCC
0x1800ebcd6  lea     ecx, [rax+rax]
0x1800ebcd9  mov     r8d, 5
0x1800ebcdf  add     rcx, 2
0x1800ebce3  lea     rax, [rbp+170h+var_1C0]
0x1800ebce7  mov     [rsp+270h+var_210], rcx
0x1800ebcec  lea     r9, [rsp+270h+var_200]
0x1800ebcf1  mov     [rsp+270h+var_218], rax
0x1800ebcf6  lea     rdx, PLA_EVENT_ERROR
0x1800ebcfd  mov     [rsp+270h+var_220], r13
0x1800ebd02  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1800ebd09  mov     [rsp+270h+var_228], rax
0x1800ebd0e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ebd15  mov     [rsp+270h+var_230], r12
0x1800ebd1a  lea     rax, [rsp+270h+var_1F8]
0x1800ebd1f  mov     [rsp+270h+var_238], rax
0x1800ebd24  lea     rax, qword_180147320
0x1800ebd2b  mov     [rsp+270h+var_240], 1
0x1800ebd34  mov     [rsp+270h+var_248], rax
0x1800ebd39  mov     [rsp+270h+var_250], r12
0x1800ebd3e  call    EventingWriteEvent
0x1800ebd43  lea     rbx, [rdi+40h]
0x1800ebd47  jmp     loc_1800EBED3
0x1800ebd4c  lea     rbx, [rdi+40h]
0x1800ebd50  mov     rcx, [rbx]; psa
0x1800ebd53  lea     rdx, [rbp+170h+ppvData]; ppvData
0x1800ebd57  call    cs:__imp_SafeArrayAccessData
0x1800ebd5d  mov     esi, eax
0x1800ebd5f  test    eax, eax
0x1800ebd61  jns     short loc_1800EBDCE
0x1800ebd63  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800ebd6a  mov     [rsp+270h+var_1F8], r15d
0x1800ebd6f  mov     [rsp+270h+var_200], eax
0x1800ebd73  jz      loc_1800EBED3
0x1800ebd79  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ebd83  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ebd8a  jz      loc_1800EBED3
0x1800ebd90  mov     rax, cs:qword_180169748
0x1800ebd97  and     rax, rdx
0x1800ebd9a  cmp     cs:qword_180169748, rax
0x1800ebda1  jnz     loc_1800EBED3
0x1800ebda7  lea     rcx, [rbp+170h+var_140]; unsigned __int16 *
0x1800ebdab  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ebdb0  lea     rcx, [rbp+170h+var_140]
0x1800ebdb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ebdb8  inc     rax
0x1800ebdbb  cmp     [rcx+rax*2], r15w
0x1800ebdc0  jnz     short loc_1800EBDB8
0x1800ebdc2  lea     ecx, [rax+rax]
0x1800ebdc5  lea     rax, [rbp+170h+var_140]
0x1800ebdc9  jmp     loc_1800EBE6D
0x1800ebdce  mov     eax, [rsp+270h+var_200]
0x1800ebdd2  lea     rdx, _GUID_0383753a_098b_11d8_9414_505054503030
0x1800ebdd9  mov     r8, r14
0x1800ebddc  lea     rcx, [rax+rax*2]
0x1800ebde0  mov     rax, [rbp+170h+ppvData]
0x1800ebde4  mov     rcx, [rax+rcx*8+8]
0x1800ebde9  mov     rax, [rcx]
0x1800ebdec  mov     rax, [rax]
0x1800ebdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebdf4  mov     esi, eax
0x1800ebdf6  test    eax, eax
0x1800ebdf8  jns     loc_1800EBED3
0x1800ebdfe  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800ebe05  mov     [rsp+270h+var_1F8], r15d
0x1800ebe0a  mov     [rsp+270h+var_200], eax
0x1800ebe0e  jz      loc_1800EBED3
0x1800ebe14  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ebe1e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ebe25  jz      loc_1800EBED3
0x1800ebe2b  mov     rax, cs:qword_180169748
0x1800ebe32  and     rax, rdx
0x1800ebe35  cmp     cs:qword_180169748, rax
0x1800ebe3c  jnz     loc_1800EBED3
0x1800ebe42  lea     rcx, [rbp+170h+var_C0]; unsigned __int16 *
0x1800ebe49  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ebe4e  lea     rcx, [rbp+170h+var_C0]
0x1800ebe55  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ebe59  inc     rax
0x1800ebe5c  cmp     [rcx+rax*2], r15w
0x1800ebe61  jnz     short loc_1800EBE59
0x1800ebe63  lea     ecx, [rax+rax]
0x1800ebe66  lea     rax, [rbp+170h+var_C0]
0x1800ebe6d  add     rcx, 2
0x1800ebe71  lea     r9, [rsp+270h+var_200]
0x1800ebe76  mov     [rsp+270h+var_210], rcx
0x1800ebe7b  lea     rdx, PLA_EVENT_ERROR
0x1800ebe82  mov     [rsp+270h+var_218], rax
0x1800ebe87  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ebe8e  mov     [rsp+270h+var_220], r13
0x1800ebe93  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1800ebe9a  mov     [rsp+270h+var_228], rax
0x1800ebe9f  mov     r8d, 5
0x1800ebea5  mov     [rsp+270h+var_230], r12
0x1800ebeaa  lea     rax, [rsp+270h+var_1F8]
0x1800ebeaf  mov     [rsp+270h+var_238], rax
0x1800ebeb4  lea     rax, qword_180147320
0x1800ebebb  mov     [rsp+270h+var_240], 1
0x1800ebec4  mov     [rsp+270h+var_248], rax
0x1800ebec9  mov     [rsp+270h+var_250], r12
0x1800ebece  call    EventingWriteEvent
0x1800ebed3  cmp     [rdi+8], r15d
0x1800ebed7  jz      short loc_1800EBEE3
0x1800ebed9  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800ebedd  call    cs:__imp_LeaveCriticalSection
0x1800ebee3  cmp     [rbp+170h+ppvData], r15
0x1800ebee7  jz      short loc_1800EBEF2
0x1800ebee9  mov     rcx, [rbx]; psa
0x1800ebeec  call    cs:__imp_SafeArrayUnaccessData
0x1800ebef2  mov     eax, esi
0x1800ebef4  mov     rcx, [rbp+170h+var_40]
0x1800ebefb  xor     rcx, rsp; StackCookie
0x1800ebefe  call    __security_check_cookie
0x1800ebf03  mov     rbx, [rsp+270h+arg_10]
0x1800ebf0b  add     rsp, 240h
0x1800ebf12  pop     r15
0x1800ebf14  pop     r14
0x1800ebf16  pop     r13
0x1800ebf18  pop     r12
0x1800ebf1a  pop     rdi
0x1800ebf1b  pop     rsi
0x1800ebf1c  pop     rbp
0x1800ebf1d  retn
```
