# Enumerator::RemoveNamed<IDataCollector>(tagVARIANT,long (IDataCollector::*)(ushort * *))

- ea: `0x1801222bc`
- end: `0x18012261b`
- name: `??$RemoveNamed@UIDataCollector@@@Enumerator@@QEAAJUtagVARIANT@@P8IDataCollector@@EAAJPEAPEAG@Z@Z`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180066770`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800281c0`
- `0x1801222bc`
- `0x18013ae8e`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801225d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801225d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180122394`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180122394`
- `OLEAUT32!__imp_VariantClear` at `0x18012258f`
- `OLEAUT32!__imp_VariantClear` at `0x18012258f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801224a0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801224a0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801225e8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801225e8`

## string_xrefs

- `0x1801222ef`: `Enumerator::RemoveNamed`
- `0x18012253c`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<IDataCollector>(__int64 a1, __int128 *a2, __int64 a3)
{
  __int64 v5; // xmm1_8
  int v6; // eax
  unsigned int v7; // r14d
  __int64 v8; // rax
  SAFEARRAY **v9; // r15
  HRESULT v10; // eax
  __int64 v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  unsigned int v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  __int128 v19; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v21[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v22[64]; // [rsp+130h] [rbp+30h] BYREF

  v16 = *(_DWORD *)(a1 + 56);
  v15 = 0;
  ppvData = 0;
  v18 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::RemoveNamed", 24, &v18, 8, &v16, 4);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v5 = *((_QWORD *)a2 + 2);
  v19 = *a2;
  v20 = v5;
  v6 = Enumerator::GetIndex<IDataCollector>(a1, &v19, a3, &v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = (SAFEARRAY **)(a1 + 64);
    v10 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v12 = v15;
      v13 = 3LL * v15;
      VariantClear((VARIANTARG *)ppvData + v15);
      memmove_0((char *)ppvData + 8 * v13, (char *)ppvData + 24 * v12 + 24, 24LL * (*(_DWORD *)(a1 + 76) - v12 - 1));
      *((_WORD *)ppvData + 12 * (unsigned int)--*(_DWORD *)(a1 + 76)) = 0;
    }
    else
    {
      v16 = 0;
      v15 = v10;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v22, 0x4000000000000800uLL);
        v11 = -1;
        do
          ++v11;
        while ( v22[v11] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v15, 4, byte_180147320, 1, &v16, 4);
      }
    }
  }
  else
  {
    v16 = 0;
    v15 = v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v21, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v21[v8] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v15, 4, byte_180147320, 1, &v16, 4);
    }
    v9 = (SAFEARRAY **)(a1 + 64);
  }
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v9);
  return v7;
}

```

## disassembly

```asm
0x1801222bc  mov     [rsp-8+arg_10], rbx
0x1801222c1  push    rbp
0x1801222c2  push    rsi
0x1801222c3  push    rdi
0x1801222c4  push    r12
0x1801222c6  push    r13
0x1801222c8  push    r14
0x1801222ca  push    r15
0x1801222cc  lea     rbp, [rsp-0C0h]
0x1801222d4  sub     rsp, 1C0h
0x1801222db  mov     rax, cs:__security_cookie
0x1801222e2  xor     rax, rsp
0x1801222e5  mov     [rbp+0F0h+var_40], rax
0x1801222ec  mov     eax, [rcx+38h]
0x1801222ef  lea     r15, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x1801222f6  xor     r12d, r12d
0x1801222f9  mov     [rsp+1F0h+var_178], eax
0x1801222fd  cmp     dword ptr cs:xmmword_180169738, r12d
0x180122304  mov     rbx, rdx
0x180122307  mov     rsi, rcx
0x18012230a  mov     [rsp+1F0h+var_180], r12d
0x18012230f  mov     [rbp+0F0h+ppvData], r12
0x180122313  lea     edi, [r12+4]
0x180122318  mov     [rbp+0F0h+var_168], rcx
0x18012231c  lea     r13d, [r12+18h]
0x180122321  jz      short loc_18012238A
0x180122323  mov     rdx, 4000000000000400h
0x18012232d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180122334  jz      short loc_18012238A
0x180122336  mov     rax, cs:qword_180169748
0x18012233d  and     rax, rdx
0x180122340  cmp     cs:qword_180169748, rax
0x180122347  jnz     short loc_18012238A
0x180122349  mov     [rsp+1F0h+var_1B0], rdi
0x18012234e  lea     rax, [rsp+1F0h+var_178]
0x180122353  mov     [rsp+1F0h+var_1B8], rax
0x180122358  lea     r8d, [r12+3]
0x18012235d  lea     rax, [rbp+0F0h+var_168]
0x180122361  mov     [rsp+1F0h+var_1C0], 8
0x18012236a  mov     [rsp+1F0h+var_1C8], rax
0x18012236f  lea     rdx, PLA_EVENT_METHOD
0x180122376  mov     r9, r15
0x180122379  mov     [rsp+1F0h+var_1D0], r13
0x18012237e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180122385  call    EventingWriteEvent
0x18012238a  cmp     [rsi+8], r12d
0x18012238e  jz      short loc_18012239A
0x180122390  lea     rcx, [rsi+10h]; lpCriticalSection
0x180122394  call    cs:__imp_EnterCriticalSection
0x18012239a  movaps  xmm0, xmmword ptr [rbx]
0x18012239d  lea     r9, [rsp+1F0h+var_180]
0x1801223a2  movsd   xmm1, qword ptr [rbx+10h]
0x1801223a7  lea     rdx, [rbp+0F0h+var_160]
0x1801223ab  mov     rcx, rsi
0x1801223ae  movaps  [rbp+0F0h+var_160], xmm0
0x1801223b2  movsd   [rbp+0F0h+var_150], xmm1
0x1801223b7  call    ??$GetIndex@UIDataCollector@@@Enumerator@@IEAAJUtagVARIANT@@P8IDataCollector@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IDataCollector>(tagVARIANT,long (IDataCollector::*)(ushort * *),ulong *)
0x1801223bc  mov     r14d, eax
0x1801223bf  test    eax, eax
0x1801223c1  jns     loc_180122495
0x1801223c7  cmp     dword ptr cs:xmmword_180169738, r12d
0x1801223ce  mov     [rsp+1F0h+var_178], r12d
0x1801223d3  mov     [rsp+1F0h+var_180], eax
0x1801223d7  jz      loc_18012248C
0x1801223dd  mov     rdx, 4000000000000800h; unsigned __int64
0x1801223e7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801223ee  jz      loc_18012248C
0x1801223f4  mov     rax, cs:qword_180169748
0x1801223fb  and     rax, rdx
0x1801223fe  cmp     cs:qword_180169748, rax
0x180122405  jnz     loc_18012248C
0x18012240b  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x18012240f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180122414  lea     rcx, [rbp+0F0h+var_140]
0x180122418  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012241c  inc     rax
0x18012241f  cmp     [rcx+rax*2], r12w
0x180122424  jnz     short loc_18012241C
0x180122426  lea     ecx, [rax+rax]
0x180122429  mov     r8d, 5
0x18012242f  add     rcx, 2
0x180122433  lea     rax, [rbp+0F0h+var_140]
0x180122437  mov     [rsp+1F0h+var_190], rcx
0x18012243c  lea     r9, [rsp+1F0h+var_180]
0x180122441  mov     [rsp+1F0h+var_198], rax
0x180122446  lea     rdx, PLA_EVENT_ERROR
0x18012244d  mov     [rsp+1F0h+var_1A0], r13
0x180122452  lea     rax, [rsp+1F0h+var_178]
0x180122457  mov     [rsp+1F0h+var_1A8], r15
0x18012245c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180122463  mov     [rsp+1F0h+var_1B0], rdi
0x180122468  mov     [rsp+1F0h+var_1B8], rax
0x18012246d  lea     rax, byte_180147320
0x180122474  mov     [rsp+1F0h+var_1C0], 1
0x18012247d  mov     [rsp+1F0h+var_1C8], rax
0x180122482  mov     [rsp+1F0h+var_1D0], rdi
0x180122487  call    EventingWriteEvent
0x18012248c  lea     r15, [rsi+40h]
0x180122490  jmp     loc_1801225CF
0x180122495  lea     r15, [rsi+40h]
0x180122499  mov     rcx, [r15]; psa
0x18012249c  lea     rdx, [rbp+0F0h+ppvData]; ppvData
0x1801224a0  call    cs:__imp_SafeArrayAccessData
0x1801224a6  mov     r14d, eax
0x1801224a9  test    eax, eax
0x1801224ab  jns     loc_18012257F
0x1801224b1  cmp     dword ptr cs:xmmword_180169738, r12d
0x1801224b8  mov     [rsp+1F0h+var_178], r12d
0x1801224bd  mov     [rsp+1F0h+var_180], eax
0x1801224c1  jz      loc_1801225CF
0x1801224c7  mov     rdx, 4000000000000800h; unsigned __int64
0x1801224d1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801224d8  jz      loc_1801225CF
0x1801224de  mov     rax, cs:qword_180169748
0x1801224e5  and     rax, rdx
0x1801224e8  cmp     cs:qword_180169748, rax
0x1801224ef  jnz     loc_1801225CF
0x1801224f5  lea     rcx, [rbp+0F0h+var_C0]; unsigned __int16 *
0x1801224f9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801224fe  lea     rcx, [rbp+0F0h+var_C0]
0x180122502  or      rax, 0FFFFFFFFFFFFFFFFh
0x180122506  inc     rax
0x180122509  cmp     [rcx+rax*2], r12w
0x18012250e  jnz     short loc_180122506
0x180122510  lea     ecx, [rax+rax]
0x180122513  mov     r8d, 5
0x180122519  add     rcx, 2
0x18012251d  lea     rax, [rbp+0F0h+var_C0]
0x180122521  mov     [rsp+1F0h+var_190], rcx
0x180122526  lea     r9, [rsp+1F0h+var_180]
0x18012252b  mov     [rsp+1F0h+var_198], rax
0x180122530  lea     rdx, PLA_EVENT_ERROR
0x180122537  mov     [rsp+1F0h+var_1A0], r13
0x18012253c  lea     rax, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x180122543  mov     [rsp+1F0h+var_1A8], rax
0x180122548  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18012254f  mov     [rsp+1F0h+var_1B0], rdi
0x180122554  lea     rax, [rsp+1F0h+var_178]
0x180122559  mov     [rsp+1F0h+var_1B8], rax
0x18012255e  lea     rax, byte_180147320
0x180122565  mov     [rsp+1F0h+var_1C0], 1
0x18012256e  mov     [rsp+1F0h+var_1C8], rax
0x180122573  mov     [rsp+1F0h+var_1D0], rdi
0x180122578  call    EventingWriteEvent
0x18012257d  jmp     short loc_1801225CF
0x18012257f  mov     rax, [rbp+0F0h+ppvData]
0x180122583  mov     ebx, [rsp+1F0h+var_180]
0x180122587  lea     rdi, [rbx+rbx*2]
0x18012258b  lea     rcx, [rax+rdi*8]; pvarg
0x18012258f  call    cs:__imp_VariantClear
0x180122595  mov     eax, [rsi+4Ch]
0x180122598  mov     rcx, [rbp+0F0h+ppvData]
0x18012259c  sub     eax, ebx
0x18012259e  dec     eax
0x1801225a0  lea     r8, [rax+rax*2]
0x1801225a4  lea     eax, [rbx+1]
0x1801225a7  shl     r8, 3; Size
0x1801225ab  lea     rax, [rax+rax*2]
0x1801225af  lea     rdx, [rcx+rax*8]; Src
0x1801225b3  lea     rcx, [rcx+rdi*8]; void *
0x1801225b7  call    memmove_0
0x1801225bc  dec     dword ptr [rsi+4Ch]
0x1801225bf  mov     eax, [rsi+4Ch]
0x1801225c2  lea     r8, [rax+rax*2]
0x1801225c6  mov     rax, [rbp+0F0h+ppvData]
0x1801225ca  mov     [rax+r8*8], r12w
0x1801225cf  cmp     [rsi+8], r12d
0x1801225d3  jz      short loc_1801225DF
0x1801225d5  lea     rcx, [rsi+10h]; lpCriticalSection
0x1801225d9  call    cs:__imp_LeaveCriticalSection
0x1801225df  cmp     [rbp+0F0h+ppvData], r12
0x1801225e3  jz      short loc_1801225EE
0x1801225e5  mov     rcx, [r15]; psa
0x1801225e8  call    cs:__imp_SafeArrayUnaccessData
0x1801225ee  mov     eax, r14d
0x1801225f1  mov     rcx, [rbp+0F0h+var_40]
0x1801225f8  xor     rcx, rsp; StackCookie
0x1801225fb  call    __security_check_cookie
0x180122600  mov     rbx, [rsp+1F0h+arg_10]
0x180122608  add     rsp, 1C0h
0x18012260f  pop     r15
0x180122611  pop     r14
0x180122613  pop     r13
0x180122615  pop     r12
0x180122617  pop     rdi
0x180122618  pop     rsi
0x180122619  pop     rbp
0x18012261a  retn
```
