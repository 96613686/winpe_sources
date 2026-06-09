# Enumerator::RemoveNamed<IValueMapItem>(tagVARIANT,long (IValueMapItem::*)(ushort * *))

- ea: `0x18011bfe4`
- end: `0x18011c34a`
- name: `??$RemoveNamed@UIValueMapItem@@@Enumerator@@QEAAJUtagVARIANT@@P8IValueMapItem@@EAAJPEAPEAG@Z@Z`
- size: `870`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009dea0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800339b4`
- `0x18011bfe4`
- `0x18013ae8e`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011c308`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011c308`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011c0bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011c0bc`
- `OLEAUT32!__imp_VariantClear` at `0x18011c2be`
- `OLEAUT32!__imp_VariantClear` at `0x18011c2be`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011c1cf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011c1cf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011c317`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011c317`

## string_xrefs

- `0x18011c017`: `Enumerator::RemoveNamed`
- `0x18011c26b`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<IValueMapItem>(__int64 a1, __int64 a2)
{
  IRecordInfo *v4; // xmm1_8
  int v5; // eax
  unsigned int v6; // r14d
  __int64 v7; // rax
  SAFEARRAY **v8; // r15
  HRESULT v9; // eax
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  HRESULT v16; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v20; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v21[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v22[64]; // [rsp+130h] [rbp+30h] BYREF

  v17 = *(_DWORD *)(a1 + 56);
  v16 = 0;
  ppvData = 0;
  v19 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::RemoveNamed", 24, &v19, 8, &v17, 4, v14, v15);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v4 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v20.vt = *(_OWORD *)a2;
  v20.pRecInfo = v4;
  v5 = Enumerator::GetIndex<IValueMapItem>(
         a1,
         &v20,
         (__int64 (__fastcall *)(__int64, wchar_t **)) IValueMapItem::`vcall'{88,{flat}},
         (unsigned int *)&v16);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = (SAFEARRAY **)(a1 + 64);
    v9 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v11 = v16;
      v12 = 3LL * (unsigned int)v16;
      VariantClear((VARIANTARG *)ppvData + (unsigned int)v16);
      memmove_0((char *)ppvData + 8 * v12, (char *)ppvData + 24 * v11 + 24, 24LL * (*(_DWORD *)(a1 + 76) - v11 - 1));
      *((_WORD *)ppvData + 12 * (unsigned int)--*(_DWORD *)(a1 + 76)) = 0;
    }
    else
    {
      v17 = 0;
      v16 = v9;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v22, 0x4000000000000800uLL);
        v10 = -1;
        do
          ++v10;
        while ( v22[v10] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v16,
          4,
          qword_180147320,
          1,
          &v17,
          4,
          "Enumerator::RemoveNamed",
          24);
      }
    }
  }
  else
  {
    v17 = 0;
    v16 = v5;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v21, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v21[v7] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v16,
        4,
        qword_180147320,
        1,
        &v17,
        4,
        "Enumerator::RemoveNamed",
        24);
    }
    v8 = (SAFEARRAY **)(a1 + 64);
  }
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v8);
  return v6;
}

```

## disassembly

```asm
0x18011bfe4  mov     [rsp-8+arg_10], rbx
0x18011bfe9  push    rbp
0x18011bfea  push    rsi
0x18011bfeb  push    rdi
0x18011bfec  push    r12
0x18011bfee  push    r13
0x18011bff0  push    r14
0x18011bff2  push    r15
0x18011bff4  lea     rbp, [rsp-0C0h]
0x18011bffc  sub     rsp, 1C0h
0x18011c003  mov     rax, cs:__security_cookie
0x18011c00a  xor     rax, rsp
0x18011c00d  mov     [rbp+0F0h+var_40], rax
0x18011c014  mov     eax, [rcx+38h]
0x18011c017  lea     r15, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x18011c01e  xor     r12d, r12d
0x18011c021  mov     [rsp+1F0h+var_178], eax
0x18011c025  cmp     dword ptr cs:xmmword_180169738, r12d
0x18011c02c  mov     rbx, rdx
0x18011c02f  mov     rsi, rcx
0x18011c032  mov     [rsp+1F0h+var_180], r12d
0x18011c037  mov     [rbp+0F0h+ppvData], r12
0x18011c03b  lea     edi, [r12+4]
0x18011c040  mov     [rbp+0F0h+var_168], rcx
0x18011c044  lea     r13d, [r12+18h]
0x18011c049  jz      short loc_18011C0B2
0x18011c04b  mov     rdx, 4000000000000400h
0x18011c055  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011c05c  jz      short loc_18011C0B2
0x18011c05e  mov     rax, cs:qword_180169748
0x18011c065  and     rax, rdx
0x18011c068  cmp     cs:qword_180169748, rax
0x18011c06f  jnz     short loc_18011C0B2
0x18011c071  mov     [rsp+1F0h+var_1B0], rdi
0x18011c076  lea     rax, [rsp+1F0h+var_178]
0x18011c07b  mov     [rsp+1F0h+var_1B8], rax
0x18011c080  lea     r8d, [r12+3]
0x18011c085  lea     rax, [rbp+0F0h+var_168]
0x18011c089  mov     [rsp+1F0h+var_1C0], 8
0x18011c092  mov     [rsp+1F0h+var_1C8], rax
0x18011c097  lea     rdx, PLA_EVENT_METHOD
0x18011c09e  mov     r9, r15
0x18011c0a1  mov     [rsp+1F0h+var_1D0], r13
0x18011c0a6  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18011c0ad  call    EventingWriteEvent
0x18011c0b2  cmp     [rsi+8], r12d
0x18011c0b6  jz      short loc_18011C0C2
0x18011c0b8  lea     rcx, [rsi+10h]; lpCriticalSection
0x18011c0bc  call    cs:__imp_EnterCriticalSection
0x18011c0c2  movaps  xmm0, xmmword ptr [rbx]
0x18011c0c5  lea     r9, [rsp+1F0h+var_180]
0x18011c0ca  movsd   xmm1, qword ptr [rbx+10h]
0x18011c0cf  lea     r8, ??_9IValueMapItem@@$BFI@AA; [thunk]: IValueMapItem::`vcall'{88,{flat}}
0x18011c0d6  lea     rdx, [rbp+0F0h+var_160]
0x18011c0da  movaps  [rbp+0F0h+var_160], xmm0
0x18011c0de  mov     rcx, rsi
0x18011c0e1  movsd   [rbp+0F0h+var_150], xmm1
0x18011c0e6  call    ??$GetIndex@UIValueMapItem@@@Enumerator@@IEAAJUtagVARIANT@@P8IValueMapItem@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IValueMapItem>(tagVARIANT,long (IValueMapItem::*)(ushort * *),ulong *)
0x18011c0eb  mov     r14d, eax
0x18011c0ee  test    eax, eax
0x18011c0f0  jns     loc_18011C1C4
0x18011c0f6  cmp     dword ptr cs:xmmword_180169738, r12d
0x18011c0fd  mov     [rsp+1F0h+var_178], r12d
0x18011c102  mov     [rsp+1F0h+var_180], eax
0x18011c106  jz      loc_18011C1BB
0x18011c10c  mov     rdx, 4000000000000800h; unsigned __int64
0x18011c116  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011c11d  jz      loc_18011C1BB
0x18011c123  mov     rax, cs:qword_180169748
0x18011c12a  and     rax, rdx
0x18011c12d  cmp     cs:qword_180169748, rax
0x18011c134  jnz     loc_18011C1BB
0x18011c13a  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x18011c13e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18011c143  lea     rcx, [rbp+0F0h+var_140]
0x18011c147  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011c14b  inc     rax
0x18011c14e  cmp     [rcx+rax*2], r12w
0x18011c153  jnz     short loc_18011C14B
0x18011c155  lea     ecx, [rax+rax]
0x18011c158  mov     r8d, 5
0x18011c15e  add     rcx, 2
0x18011c162  lea     rax, [rbp+0F0h+var_140]
0x18011c166  mov     [rsp+1F0h+var_190], rcx
0x18011c16b  lea     r9, [rsp+1F0h+var_180]
0x18011c170  mov     [rsp+1F0h+var_198], rax
0x18011c175  lea     rdx, PLA_EVENT_ERROR
0x18011c17c  mov     [rsp+1F0h+var_1A0], r13
0x18011c181  lea     rax, [rsp+1F0h+var_178]
0x18011c186  mov     [rsp+1F0h+var_1A8], r15
0x18011c18b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18011c192  mov     [rsp+1F0h+var_1B0], rdi
0x18011c197  mov     [rsp+1F0h+var_1B8], rax
0x18011c19c  lea     rax, qword_180147320
0x18011c1a3  mov     [rsp+1F0h+var_1C0], 1
0x18011c1ac  mov     [rsp+1F0h+var_1C8], rax
0x18011c1b1  mov     [rsp+1F0h+var_1D0], rdi
0x18011c1b6  call    EventingWriteEvent
0x18011c1bb  lea     r15, [rsi+40h]
0x18011c1bf  jmp     loc_18011C2FE
0x18011c1c4  lea     r15, [rsi+40h]
0x18011c1c8  mov     rcx, [r15]; psa
0x18011c1cb  lea     rdx, [rbp+0F0h+ppvData]; ppvData
0x18011c1cf  call    cs:__imp_SafeArrayAccessData
0x18011c1d5  mov     r14d, eax
0x18011c1d8  test    eax, eax
0x18011c1da  jns     loc_18011C2AE
0x18011c1e0  cmp     dword ptr cs:xmmword_180169738, r12d
0x18011c1e7  mov     [rsp+1F0h+var_178], r12d
0x18011c1ec  mov     [rsp+1F0h+var_180], eax
0x18011c1f0  jz      loc_18011C2FE
0x18011c1f6  mov     rdx, 4000000000000800h; unsigned __int64
0x18011c200  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011c207  jz      loc_18011C2FE
0x18011c20d  mov     rax, cs:qword_180169748
0x18011c214  and     rax, rdx
0x18011c217  cmp     cs:qword_180169748, rax
0x18011c21e  jnz     loc_18011C2FE
0x18011c224  lea     rcx, [rbp+0F0h+var_C0]; unsigned __int16 *
0x18011c228  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18011c22d  lea     rcx, [rbp+0F0h+var_C0]
0x18011c231  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011c235  inc     rax
0x18011c238  cmp     [rcx+rax*2], r12w
0x18011c23d  jnz     short loc_18011C235
0x18011c23f  lea     ecx, [rax+rax]
0x18011c242  mov     r8d, 5
0x18011c248  add     rcx, 2
0x18011c24c  lea     rax, [rbp+0F0h+var_C0]
0x18011c250  mov     [rsp+1F0h+var_190], rcx
0x18011c255  lea     r9, [rsp+1F0h+var_180]
0x18011c25a  mov     [rsp+1F0h+var_198], rax
0x18011c25f  lea     rdx, PLA_EVENT_ERROR
0x18011c266  mov     [rsp+1F0h+var_1A0], r13
0x18011c26b  lea     rax, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x18011c272  mov     [rsp+1F0h+var_1A8], rax
0x18011c277  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18011c27e  mov     [rsp+1F0h+var_1B0], rdi
0x18011c283  lea     rax, [rsp+1F0h+var_178]
0x18011c288  mov     [rsp+1F0h+var_1B8], rax
0x18011c28d  lea     rax, qword_180147320
0x18011c294  mov     [rsp+1F0h+var_1C0], 1
0x18011c29d  mov     [rsp+1F0h+var_1C8], rax
0x18011c2a2  mov     [rsp+1F0h+var_1D0], rdi
0x18011c2a7  call    EventingWriteEvent
0x18011c2ac  jmp     short loc_18011C2FE
0x18011c2ae  mov     rax, [rbp+0F0h+ppvData]
0x18011c2b2  mov     ebx, [rsp+1F0h+var_180]
0x18011c2b6  lea     rdi, [rbx+rbx*2]
0x18011c2ba  lea     rcx, [rax+rdi*8]; pvarg
0x18011c2be  call    cs:__imp_VariantClear
0x18011c2c4  mov     eax, [rsi+4Ch]
0x18011c2c7  mov     rcx, [rbp+0F0h+ppvData]
0x18011c2cb  sub     eax, ebx
0x18011c2cd  dec     eax
0x18011c2cf  lea     r8, [rax+rax*2]
0x18011c2d3  lea     eax, [rbx+1]
0x18011c2d6  shl     r8, 3; Size
0x18011c2da  lea     rax, [rax+rax*2]
0x18011c2de  lea     rdx, [rcx+rax*8]; Src
0x18011c2e2  lea     rcx, [rcx+rdi*8]; void *
0x18011c2e6  call    memmove_0
0x18011c2eb  dec     dword ptr [rsi+4Ch]
0x18011c2ee  mov     eax, [rsi+4Ch]
0x18011c2f1  lea     r8, [rax+rax*2]
0x18011c2f5  mov     rax, [rbp+0F0h+ppvData]
0x18011c2f9  mov     [rax+r8*8], r12w
0x18011c2fe  cmp     [rsi+8], r12d
0x18011c302  jz      short loc_18011C30E
0x18011c304  lea     rcx, [rsi+10h]; lpCriticalSection
0x18011c308  call    cs:__imp_LeaveCriticalSection
0x18011c30e  cmp     [rbp+0F0h+ppvData], r12
0x18011c312  jz      short loc_18011C31D
0x18011c314  mov     rcx, [r15]; psa
0x18011c317  call    cs:__imp_SafeArrayUnaccessData
0x18011c31d  mov     eax, r14d
0x18011c320  mov     rcx, [rbp+0F0h+var_40]
0x18011c327  xor     rcx, rsp; StackCookie
0x18011c32a  call    __security_check_cookie
0x18011c32f  mov     rbx, [rsp+1F0h+arg_10]
0x18011c337  add     rsp, 1C0h
0x18011c33e  pop     r15
0x18011c340  pop     r14
0x18011c342  pop     r13
0x18011c344  pop     r12
0x18011c346  pop     rdi
0x18011c347  pop     rsi
0x18011c348  pop     rbp
0x18011c349  retn
```
