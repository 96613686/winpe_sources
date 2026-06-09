# Enumerator::RemoveNamed<ITraceDataProvider>(tagVARIANT,long (ITraceDataProvider::*)(ushort * *))

- ea: `0x18011bab8`
- end: `0x18011be1e`
- name: `??$RemoveNamed@UITraceDataProvider@@@Enumerator@@QEAAJUtagVARIANT@@P8ITraceDataProvider@@EAAJPEAPEAG@Z@Z`
- size: `870`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800c8760`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180006170`
- `0x18011bab8`
- `0x18013ae8e`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011bb90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011bb90`
- `OLEAUT32!__imp_VariantClear` at `0x18011bd92`
- `OLEAUT32!__imp_VariantClear` at `0x18011bd92`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011bca3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011bca3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011bdeb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011bdeb`

## string_xrefs

- `0x18011baeb`: `Enumerator::RemoveNamed`
- `0x18011bd3f`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<ITraceDataProvider>(__int64 a1, __int64 a2)
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
  v5 = Enumerator::GetIndex<ITraceDataProvider>(
         a1,
         &v20,
         (__int64 (__fastcall *)(__int64, BSTR *)) ITraceDataProvider::`vcall'{56,{flat}},
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
0x18011bab8  mov     [rsp-8+arg_10], rbx
0x18011babd  push    rbp
0x18011babe  push    rsi
0x18011babf  push    rdi
0x18011bac0  push    r12
0x18011bac2  push    r13
0x18011bac4  push    r14
0x18011bac6  push    r15
0x18011bac8  lea     rbp, [rsp-0C0h]
0x18011bad0  sub     rsp, 1C0h
0x18011bad7  mov     rax, cs:__security_cookie
0x18011bade  xor     rax, rsp
0x18011bae1  mov     [rbp+0F0h+var_40], rax
0x18011bae8  mov     eax, [rcx+38h]
0x18011baeb  lea     r15, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x18011baf2  xor     r12d, r12d
0x18011baf5  mov     [rsp+1F0h+var_178], eax
0x18011baf9  cmp     dword ptr cs:xmmword_180169738, r12d
0x18011bb00  mov     rbx, rdx
0x18011bb03  mov     rsi, rcx
0x18011bb06  mov     [rsp+1F0h+var_180], r12d
0x18011bb0b  mov     [rbp+0F0h+ppvData], r12
0x18011bb0f  lea     edi, [r12+4]
0x18011bb14  mov     [rbp+0F0h+var_168], rcx
0x18011bb18  lea     r13d, [r12+18h]
0x18011bb1d  jz      short loc_18011BB86
0x18011bb1f  mov     rdx, 4000000000000400h
0x18011bb29  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011bb30  jz      short loc_18011BB86
0x18011bb32  mov     rax, cs:qword_180169748
0x18011bb39  and     rax, rdx
0x18011bb3c  cmp     cs:qword_180169748, rax
0x18011bb43  jnz     short loc_18011BB86
0x18011bb45  mov     [rsp+1F0h+var_1B0], rdi
0x18011bb4a  lea     rax, [rsp+1F0h+var_178]
0x18011bb4f  mov     [rsp+1F0h+var_1B8], rax
0x18011bb54  lea     r8d, [r12+3]
0x18011bb59  lea     rax, [rbp+0F0h+var_168]
0x18011bb5d  mov     [rsp+1F0h+var_1C0], 8
0x18011bb66  mov     [rsp+1F0h+var_1C8], rax
0x18011bb6b  lea     rdx, PLA_EVENT_METHOD
0x18011bb72  mov     r9, r15
0x18011bb75  mov     [rsp+1F0h+var_1D0], r13
0x18011bb7a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18011bb81  call    EventingWriteEvent
0x18011bb86  cmp     [rsi+8], r12d
0x18011bb8a  jz      short loc_18011BB96
0x18011bb8c  lea     rcx, [rsi+10h]; lpCriticalSection
0x18011bb90  call    cs:__imp_EnterCriticalSection
0x18011bb96  movaps  xmm0, xmmword ptr [rbx]
0x18011bb99  lea     r9, [rsp+1F0h+var_180]
0x18011bb9e  movsd   xmm1, qword ptr [rbx+10h]
0x18011bba3  lea     r8, ??_9ITraceDataProvider@@$BDI@AA; [thunk]: ITraceDataProvider::`vcall'{56,{flat}}
0x18011bbaa  lea     rdx, [rbp+0F0h+var_160]
0x18011bbae  movaps  [rbp+0F0h+var_160], xmm0
0x18011bbb2  mov     rcx, rsi
0x18011bbb5  movsd   [rbp+0F0h+var_150], xmm1
0x18011bbba  call    ??$GetIndex@UITraceDataProvider@@@Enumerator@@IEAAJUtagVARIANT@@P8ITraceDataProvider@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<ITraceDataProvider>(tagVARIANT,long (ITraceDataProvider::*)(ushort * *),ulong *)
0x18011bbbf  mov     r14d, eax
0x18011bbc2  test    eax, eax
0x18011bbc4  jns     loc_18011BC98
0x18011bbca  cmp     dword ptr cs:xmmword_180169738, r12d
0x18011bbd1  mov     [rsp+1F0h+var_178], r12d
0x18011bbd6  mov     [rsp+1F0h+var_180], eax
0x18011bbda  jz      loc_18011BC8F
0x18011bbe0  mov     rdx, 4000000000000800h; unsigned __int64
0x18011bbea  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011bbf1  jz      loc_18011BC8F
0x18011bbf7  mov     rax, cs:qword_180169748
0x18011bbfe  and     rax, rdx
0x18011bc01  cmp     cs:qword_180169748, rax
0x18011bc08  jnz     loc_18011BC8F
0x18011bc0e  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x18011bc12  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18011bc17  lea     rcx, [rbp+0F0h+var_140]
0x18011bc1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011bc1f  inc     rax
0x18011bc22  cmp     [rcx+rax*2], r12w
0x18011bc27  jnz     short loc_18011BC1F
0x18011bc29  lea     ecx, [rax+rax]
0x18011bc2c  mov     r8d, 5
0x18011bc32  add     rcx, 2
0x18011bc36  lea     rax, [rbp+0F0h+var_140]
0x18011bc3a  mov     [rsp+1F0h+var_190], rcx
0x18011bc3f  lea     r9, [rsp+1F0h+var_180]
0x18011bc44  mov     [rsp+1F0h+var_198], rax
0x18011bc49  lea     rdx, PLA_EVENT_ERROR
0x18011bc50  mov     [rsp+1F0h+var_1A0], r13
0x18011bc55  lea     rax, [rsp+1F0h+var_178]
0x18011bc5a  mov     [rsp+1F0h+var_1A8], r15
0x18011bc5f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18011bc66  mov     [rsp+1F0h+var_1B0], rdi
0x18011bc6b  mov     [rsp+1F0h+var_1B8], rax
0x18011bc70  lea     rax, qword_180147320
0x18011bc77  mov     [rsp+1F0h+var_1C0], 1
0x18011bc80  mov     [rsp+1F0h+var_1C8], rax
0x18011bc85  mov     [rsp+1F0h+var_1D0], rdi
0x18011bc8a  call    EventingWriteEvent
0x18011bc8f  lea     r15, [rsi+40h]
0x18011bc93  jmp     loc_18011BDD2
0x18011bc98  lea     r15, [rsi+40h]
0x18011bc9c  mov     rcx, [r15]; psa
0x18011bc9f  lea     rdx, [rbp+0F0h+ppvData]; ppvData
0x18011bca3  call    cs:__imp_SafeArrayAccessData
0x18011bca9  mov     r14d, eax
0x18011bcac  test    eax, eax
0x18011bcae  jns     loc_18011BD82
0x18011bcb4  cmp     dword ptr cs:xmmword_180169738, r12d
0x18011bcbb  mov     [rsp+1F0h+var_178], r12d
0x18011bcc0  mov     [rsp+1F0h+var_180], eax
0x18011bcc4  jz      loc_18011BDD2
0x18011bcca  mov     rdx, 4000000000000800h; unsigned __int64
0x18011bcd4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011bcdb  jz      loc_18011BDD2
0x18011bce1  mov     rax, cs:qword_180169748
0x18011bce8  and     rax, rdx
0x18011bceb  cmp     cs:qword_180169748, rax
0x18011bcf2  jnz     loc_18011BDD2
0x18011bcf8  lea     rcx, [rbp+0F0h+var_C0]; unsigned __int16 *
0x18011bcfc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18011bd01  lea     rcx, [rbp+0F0h+var_C0]
0x18011bd05  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011bd09  inc     rax
0x18011bd0c  cmp     [rcx+rax*2], r12w
0x18011bd11  jnz     short loc_18011BD09
0x18011bd13  lea     ecx, [rax+rax]
0x18011bd16  mov     r8d, 5
0x18011bd1c  add     rcx, 2
0x18011bd20  lea     rax, [rbp+0F0h+var_C0]
0x18011bd24  mov     [rsp+1F0h+var_190], rcx
0x18011bd29  lea     r9, [rsp+1F0h+var_180]
0x18011bd2e  mov     [rsp+1F0h+var_198], rax
0x18011bd33  lea     rdx, PLA_EVENT_ERROR
0x18011bd3a  mov     [rsp+1F0h+var_1A0], r13
0x18011bd3f  lea     rax, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x18011bd46  mov     [rsp+1F0h+var_1A8], rax
0x18011bd4b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18011bd52  mov     [rsp+1F0h+var_1B0], rdi
0x18011bd57  lea     rax, [rsp+1F0h+var_178]
0x18011bd5c  mov     [rsp+1F0h+var_1B8], rax
0x18011bd61  lea     rax, qword_180147320
0x18011bd68  mov     [rsp+1F0h+var_1C0], 1
0x18011bd71  mov     [rsp+1F0h+var_1C8], rax
0x18011bd76  mov     [rsp+1F0h+var_1D0], rdi
0x18011bd7b  call    EventingWriteEvent
0x18011bd80  jmp     short loc_18011BDD2
0x18011bd82  mov     rax, [rbp+0F0h+ppvData]
0x18011bd86  mov     ebx, [rsp+1F0h+var_180]
0x18011bd8a  lea     rdi, [rbx+rbx*2]
0x18011bd8e  lea     rcx, [rax+rdi*8]; pvarg
0x18011bd92  call    cs:__imp_VariantClear
0x18011bd98  mov     eax, [rsi+4Ch]
0x18011bd9b  mov     rcx, [rbp+0F0h+ppvData]
0x18011bd9f  sub     eax, ebx
0x18011bda1  dec     eax
0x18011bda3  lea     r8, [rax+rax*2]
0x18011bda7  lea     eax, [rbx+1]
0x18011bdaa  shl     r8, 3; Size
0x18011bdae  lea     rax, [rax+rax*2]
0x18011bdb2  lea     rdx, [rcx+rax*8]; Src
0x18011bdb6  lea     rcx, [rcx+rdi*8]; void *
0x18011bdba  call    memmove_0
0x18011bdbf  dec     dword ptr [rsi+4Ch]
0x18011bdc2  mov     eax, [rsi+4Ch]
0x18011bdc5  lea     r8, [rax+rax*2]
0x18011bdc9  mov     rax, [rbp+0F0h+ppvData]
0x18011bdcd  mov     [rax+r8*8], r12w
0x18011bdd2  cmp     [rsi+8], r12d
0x18011bdd6  jz      short loc_18011BDE2
0x18011bdd8  lea     rcx, [rsi+10h]; lpCriticalSection
0x18011bddc  call    cs:__imp_LeaveCriticalSection
0x18011bde2  cmp     [rbp+0F0h+ppvData], r12
0x18011bde6  jz      short loc_18011BDF1
0x18011bde8  mov     rcx, [r15]; psa
0x18011bdeb  call    cs:__imp_SafeArrayUnaccessData
0x18011bdf1  mov     eax, r14d
0x18011bdf4  mov     rcx, [rbp+0F0h+var_40]
0x18011bdfb  xor     rcx, rsp; StackCookie
0x18011bdfe  call    __security_check_cookie
0x18011be03  mov     rbx, [rsp+1F0h+arg_10]
0x18011be0b  add     rsp, 1C0h
0x18011be12  pop     r15
0x18011be14  pop     r14
0x18011be16  pop     r13
0x18011be18  pop     r12
0x18011be1a  pop     rdi
0x18011be1b  pop     rsi
0x18011be1c  pop     rbp
0x18011be1d  retn
```
