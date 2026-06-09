# Enumerator::GetNamedItem<ITraceDataProvider>(tagVARIANT,long (ITraceDataProvider::*)(ushort * *),ITraceDataProvider * *)

- ea: `0x180005d70`
- end: `0x180006165`
- name: `??$GetNamedItem@UITraceDataProvider@@@Enumerator@@QEAAJUtagVARIANT@@P8ITraceDataProvider@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `1013`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 (__fastcall *)(__int64, BSTR *), __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800e0f40`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180005d70`
- `0x180006170`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005def`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005def`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005e30`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005e30`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005e89`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005e89`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<ITraceDataProvider>(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, BSTR *),
        __int64 a4)
{
  IRecordInfo *v8; // xmm1_8
  int v9; // eax
  unsigned int v10; // esi
  SAFEARRAY **v11; // rdi
  HRESULT v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64); // rcx
  int v14; // eax
  __int64 v16; // rax
  bool v17; // zf
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

  v23 = *(_DWORD *)(a1 + 56);
  v22 = 0;
  ppvData = 0;
  v25 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::GetNamedItem", 25, &v25, 8, &v23, 4, v20, v21);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v8 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v26.vt = *(_OWORD *)a2;
  v26.pRecInfo = v8;
  v9 = Enumerator::GetIndex<ITraceDataProvider>(a1, &v26, a3, (unsigned int *)&v22);
  v10 = v9;
  if ( v9 < 0 )
  {
    v23 = 0;
    v22 = v9;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v16 = -1;
      do
        v17 = v27[++v16] == 0;
      while ( !v17 );
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
    v11 = (SAFEARRAY **)(a1 + 64);
  }
  else
  {
    v11 = (SAFEARRAY **)(a1 + 64);
    v12 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v10 = v12;
    if ( v12 < 0 )
    {
      v23 = 0;
      v22 = v12;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        v18 = -1;
        do
          v17 = v28[++v18] == 0;
        while ( !v17 );
        goto LABEL_23;
      }
    }
    else
    {
      v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * (unsigned int)v22 + 1);
      v14 = (**v13)(v13, &GUID_03837512_098b_11d8_9414_505054503030, a4);
      v10 = v14;
      if ( v14 < 0 )
      {
        v23 = 0;
        v22 = v14;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v29, 0x4000000000000800uLL);
            v19 = -1;
            do
              v17 = v29[++v19] == 0;
            while ( !v17 );
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
    SafeArrayUnaccessData(*v11);
  return v10;
}

```

## disassembly

```asm
0x180005d70  push    rbp
0x180005d72  push    rbx
0x180005d73  push    rsi
0x180005d74  push    rdi
0x180005d75  push    r12
0x180005d77  push    r14
0x180005d79  push    r15
0x180005d7b  lea     rbp, [rsp-140h]
0x180005d83  sub     rsp, 240h
0x180005d8a  mov     rax, cs:__security_cookie
0x180005d91  xor     rax, rsp
0x180005d94  mov     [rbp+170h+var_40], rax
0x180005d9b  mov     eax, [rcx+38h]
0x180005d9e  lea     r12, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180005da5  xor     r15d, r15d
0x180005da8  mov     [rsp+270h+var_1F8], eax
0x180005dac  cmp     dword ptr cs:xmmword_180169738, r15d
0x180005db3  mov     r14, r9
0x180005db6  mov     rsi, r8
0x180005db9  mov     [rsp+270h+var_200], r15d
0x180005dbe  mov     rdi, rdx
0x180005dc1  mov     [rbp+170h+ppvData], r15
0x180005dc5  mov     rbx, rcx
0x180005dc8  mov     [rbp+170h+var_1E8], rcx
0x180005dcc  jz      short loc_180005DE5
0x180005dce  mov     rdx, 4000000000000400h
0x180005dd8  test    qword ptr cs:xmmword_180169738+8, rdx
0x180005ddf  jnz     loc_180005EB2
0x180005de5  cmp     [rbx+8], r15d
0x180005de9  jz      short loc_180005DF5
0x180005deb  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005def  call    cs:__imp_EnterCriticalSection
0x180005df5  movaps  xmm0, xmmword ptr [rdi]
0x180005df8  lea     r9, [rsp+270h+var_200]
0x180005dfd  movsd   xmm1, qword ptr [rdi+10h]
0x180005e02  lea     rdx, [rbp+170h+var_1E0]
0x180005e06  mov     r8, rsi
0x180005e09  movaps  [rbp+170h+var_1E0], xmm0
0x180005e0d  mov     rcx, rbx
0x180005e10  movsd   [rbp+170h+var_1D0], xmm1
0x180005e15  call    ??$GetIndex@UITraceDataProvider@@@Enumerator@@IEAAJUtagVARIANT@@P8ITraceDataProvider@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<ITraceDataProvider>(tagVARIANT,long (ITraceDataProvider::*)(ushort * *),ulong *)
0x180005e1a  mov     esi, eax
0x180005e1c  test    eax, eax
0x180005e1e  js      loc_1800060CF
0x180005e24  mov     rcx, [rbx+40h]; psa
0x180005e28  lea     rdi, [rbx+40h]
0x180005e2c  lea     rdx, [rbp+170h+ppvData]; ppvData
0x180005e30  call    cs:__imp_SafeArrayAccessData
0x180005e36  mov     esi, eax
0x180005e38  test    eax, eax
0x180005e3a  js      loc_180006101
0x180005e40  mov     eax, [rsp+270h+var_200]
0x180005e44  lea     rdx, _GUID_03837512_098b_11d8_9414_505054503030
0x180005e4b  mov     r8, r14
0x180005e4e  lea     rcx, [rax+rax*2]
0x180005e52  mov     rax, [rbp+170h+ppvData]
0x180005e56  mov     rcx, [rax+rcx*8+8]
0x180005e5b  mov     rax, [rcx]
0x180005e5e  mov     rax, [rax]
0x180005e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e66  mov     esi, eax
0x180005e68  test    eax, eax
0x180005e6a  js      loc_180006133
0x180005e70  cmp     [rbx+8], r15d
0x180005e74  jz      short loc_180005E80
0x180005e76  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005e7a  call    cs:__imp_LeaveCriticalSection
0x180005e80  cmp     [rbp+170h+ppvData], r15
0x180005e84  jz      short loc_180005E8F
0x180005e86  mov     rcx, [rdi]; psa
0x180005e89  call    cs:__imp_SafeArrayUnaccessData
0x180005e8f  mov     eax, esi
0x180005e91  mov     rcx, [rbp+170h+var_40]
0x180005e98  xor     rcx, rsp; StackCookie
0x180005e9b  call    __security_check_cookie
0x180005ea0  add     rsp, 240h
0x180005ea7  pop     r15
0x180005ea9  pop     r14
0x180005eab  pop     r12
0x180005ead  pop     rdi
0x180005eae  pop     rsi
0x180005eaf  pop     rbx
0x180005eb0  pop     rbp
0x180005eb1  retn
0x180005eb2  mov     rax, cs:qword_180169748
0x180005eb9  and     rax, rdx
0x180005ebc  cmp     cs:qword_180169748, rax
0x180005ec3  jnz     loc_180005DE5
0x180005ec9  mov     [rsp+270h+var_230], 4
0x180005ed2  lea     rax, [rsp+270h+var_1F8]
0x180005ed7  mov     [rsp+270h+var_238], rax
0x180005edc  lea     rdx, PLA_EVENT_METHOD
0x180005ee3  lea     rax, [rbp+170h+var_1E8]
0x180005ee7  mov     [rsp+270h+var_240], 8
0x180005ef0  mov     [rsp+270h+var_248], rax
0x180005ef5  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180005efc  mov     r9, r12
0x180005eff  mov     [rsp+270h+var_250], 19h
0x180005f08  mov     r8d, 3
0x180005f0e  call    EventingWriteEvent
0x180005f13  jmp     loc_180005DE5
0x180005f18  mov     rax, cs:qword_180169748
0x180005f1f  and     rax, rdx
0x180005f22  cmp     cs:qword_180169748, rax
0x180005f29  jnz     loc_180005FC1
0x180005f2f  lea     rcx, [rbp+170h+var_1C0]; unsigned __int16 *
0x180005f33  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180005f38  lea     rcx, [rbp+170h+var_1C0]
0x180005f3c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005f43  cmp     [rcx+rax*2+2], r15w
0x180005f49  lea     rax, [rax+1]
0x180005f4d  jnz     short loc_180005F43
0x180005f4f  lea     ecx, [rax+rax]
0x180005f52  mov     r8d, 5
0x180005f58  add     rcx, 2
0x180005f5c  lea     rax, [rbp+170h+var_1C0]
0x180005f60  mov     [rsp+270h+var_210], rcx
0x180005f65  lea     r9, [rsp+270h+var_200]
0x180005f6a  mov     [rsp+270h+var_218], rax
0x180005f6f  lea     rdx, PLA_EVENT_ERROR
0x180005f76  mov     [rsp+270h+var_220], 19h
0x180005f7f  lea     rax, [rsp+270h+var_1F8]
0x180005f84  mov     [rsp+270h+var_228], r12
0x180005f89  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180005f90  mov     [rsp+270h+var_230], 4
0x180005f99  mov     [rsp+270h+var_238], rax
0x180005f9e  lea     rax, qword_180147320
0x180005fa5  mov     [rsp+270h+var_240], 1
0x180005fae  mov     [rsp+270h+var_248], rax
0x180005fb3  mov     [rsp+270h+var_250], 4
0x180005fbc  call    EventingWriteEvent
0x180005fc1  lea     rdi, [rbx+40h]
0x180005fc5  jmp     loc_180005E70
0x180005fca  mov     rax, cs:qword_180169748
0x180005fd1  and     rax, rdx
0x180005fd4  cmp     cs:qword_180169748, rax
0x180005fdb  jnz     loc_180005E70
0x180005fe1  lea     rcx, [rbp+170h+var_140]; unsigned __int16 *
0x180005fe5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180005fea  lea     rcx, [rbp+170h+var_140]
0x180005fee  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005ff5  nop     word ptr [rax+rax+00000000h]
0x180006000  cmp     [rcx+rax*2+2], r15w
0x180006006  lea     rax, [rax+1]
0x18000600a  jnz     short loc_180006000
0x18000600c  lea     ecx, [rax+rax]
0x18000600f  lea     rax, [rbp+170h+var_140]
0x180006013  add     rcx, 2
0x180006017  lea     r9, [rsp+270h+var_200]
0x18000601c  mov     [rsp+270h+var_210], rcx
0x180006021  lea     rdx, PLA_EVENT_ERROR
0x180006028  mov     [rsp+270h+var_218], rax
0x18000602d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180006034  mov     [rsp+270h+var_220], 19h
0x18000603d  lea     rax, [rsp+270h+var_1F8]
0x180006042  mov     [rsp+270h+var_228], r12
0x180006047  mov     r8d, 5
0x18000604d  mov     [rsp+270h+var_230], 4
0x180006056  mov     [rsp+270h+var_238], rax
0x18000605b  lea     rax, qword_180147320
0x180006062  mov     [rsp+270h+var_240], 1
0x18000606b  mov     [rsp+270h+var_248], rax
0x180006070  mov     [rsp+270h+var_250], 4
0x180006079  call    EventingWriteEvent
0x18000607e  jmp     loc_180005E70
0x180006083  mov     rax, cs:qword_180169748
0x18000608a  and     rax, rdx
0x18000608d  cmp     cs:qword_180169748, rax
0x180006094  jnz     loc_180005E70
0x18000609a  lea     rcx, [rbp+170h+var_C0]; unsigned __int16 *
0x1800060a1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800060a6  lea     rcx, [rbp+170h+var_C0]
0x1800060ad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800060b4  cmp     [rcx+rax*2+2], r15w
0x1800060ba  lea     rax, [rax+1]
0x1800060be  jnz     short loc_1800060B4
0x1800060c0  lea     ecx, [rax+rax]
0x1800060c3  lea     rax, [rbp+170h+var_C0]
0x1800060ca  jmp     loc_180006013
0x1800060cf  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800060d6  mov     [rsp+270h+var_1F8], r15d
0x1800060db  mov     [rsp+270h+var_200], eax
0x1800060df  jz      loc_180005FC1
0x1800060e5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800060ef  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800060f6  jz      loc_180005FC1
0x1800060fc  jmp     loc_180005F18
0x180006101  cmp     dword ptr cs:xmmword_180169738, r15d
0x180006108  mov     [rsp+270h+var_1F8], r15d
0x18000610d  mov     [rsp+270h+var_200], eax
0x180006111  jz      loc_180005E70
0x180006117  mov     rdx, 4000000000000800h; unsigned __int64
0x180006121  test    qword ptr cs:xmmword_180169738+8, rdx
0x180006128  jz      loc_180005E70
0x18000612e  jmp     loc_180005FCA
0x180006133  cmp     dword ptr cs:xmmword_180169738, r15d
0x18000613a  mov     [rsp+270h+var_1F8], r15d
0x18000613f  mov     [rsp+270h+var_200], eax
0x180006143  jz      loc_180005E70
0x180006149  mov     rdx, 4000000000000800h; unsigned __int64
0x180006153  test    qword ptr cs:xmmword_180169738+8, rdx
0x18000615a  jz      loc_180005E70
0x180006160  jmp     loc_180006083
```
