# Enumerator::RemoveNamed<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *))

- ea: `0x180121e20`
- end: `0x18012217f`
- name: `??$RemoveNamed@UIUnknown@@@Enumerator@@QEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@Z@Z`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800c029c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1801219c8`
- `0x180121e20`
- `0x18013ae8e`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012213d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012213d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121ef8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121ef8`
- `OLEAUT32!__imp_VariantClear` at `0x1801220f3`
- `OLEAUT32!__imp_VariantClear` at `0x1801220f3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180122004`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180122004`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18012214c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18012214c`

## string_xrefs

- `0x180121e53`: `Enumerator::RemoveNamed`
- `0x1801220a0`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<IUnknown>(__int64 a1, __int128 *a2, __int64 a3)
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
  v6 = Enumerator::GetIndex<IUnknown>(a1, &v19, a3, &v15);
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
0x180121e20  mov     [rsp-8+arg_10], rbx
0x180121e25  push    rbp
0x180121e26  push    rsi
0x180121e27  push    rdi
0x180121e28  push    r12
0x180121e2a  push    r13
0x180121e2c  push    r14
0x180121e2e  push    r15
0x180121e30  lea     rbp, [rsp-0C0h]
0x180121e38  sub     rsp, 1C0h
0x180121e3f  mov     rax, cs:__security_cookie
0x180121e46  xor     rax, rsp
0x180121e49  mov     [rbp+0F0h+var_40], rax
0x180121e50  mov     eax, [rcx+38h]
0x180121e53  lea     r15, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x180121e5a  xor     r12d, r12d
0x180121e5d  mov     [rsp+1F0h+var_178], eax
0x180121e61  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121e68  mov     rbx, rdx
0x180121e6b  mov     rsi, rcx
0x180121e6e  mov     [rsp+1F0h+var_180], r12d
0x180121e73  mov     [rbp+0F0h+ppvData], r12
0x180121e77  lea     edi, [r12+4]
0x180121e7c  mov     [rbp+0F0h+var_168], rcx
0x180121e80  lea     r13d, [r12+18h]
0x180121e85  jz      short loc_180121EEE
0x180121e87  mov     rdx, 4000000000000400h
0x180121e91  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121e98  jz      short loc_180121EEE
0x180121e9a  mov     rax, cs:qword_180169748
0x180121ea1  and     rax, rdx
0x180121ea4  cmp     cs:qword_180169748, rax
0x180121eab  jnz     short loc_180121EEE
0x180121ead  mov     [rsp+1F0h+var_1B0], rdi
0x180121eb2  lea     rax, [rsp+1F0h+var_178]
0x180121eb7  mov     [rsp+1F0h+var_1B8], rax
0x180121ebc  lea     r8d, [r12+3]
0x180121ec1  lea     rax, [rbp+0F0h+var_168]
0x180121ec5  mov     [rsp+1F0h+var_1C0], 8
0x180121ece  mov     [rsp+1F0h+var_1C8], rax
0x180121ed3  lea     rdx, PLA_EVENT_METHOD
0x180121eda  mov     r9, r15
0x180121edd  mov     [rsp+1F0h+var_1D0], r13
0x180121ee2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180121ee9  call    EventingWriteEvent
0x180121eee  cmp     [rsi+8], r12d
0x180121ef2  jz      short loc_180121EFE
0x180121ef4  lea     rcx, [rsi+10h]; lpCriticalSection
0x180121ef8  call    cs:__imp_EnterCriticalSection
0x180121efe  movaps  xmm0, xmmword ptr [rbx]
0x180121f01  lea     r9, [rsp+1F0h+var_180]
0x180121f06  movsd   xmm1, qword ptr [rbx+10h]
0x180121f0b  lea     rdx, [rbp+0F0h+var_160]
0x180121f0f  mov     rcx, rsi
0x180121f12  movaps  [rbp+0F0h+var_160], xmm0
0x180121f16  movsd   [rbp+0F0h+var_150], xmm1
0x180121f1b  call    ??$GetIndex@UIUnknown@@@Enumerator@@IEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *),ulong *)
0x180121f20  mov     r14d, eax
0x180121f23  test    eax, eax
0x180121f25  jns     loc_180121FF9
0x180121f2b  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121f32  mov     [rsp+1F0h+var_178], r12d
0x180121f37  mov     [rsp+1F0h+var_180], eax
0x180121f3b  jz      loc_180121FF0
0x180121f41  mov     rdx, 4000000000000800h; unsigned __int64
0x180121f4b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121f52  jz      loc_180121FF0
0x180121f58  mov     rax, cs:qword_180169748
0x180121f5f  and     rax, rdx
0x180121f62  cmp     cs:qword_180169748, rax
0x180121f69  jnz     loc_180121FF0
0x180121f6f  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x180121f73  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121f78  lea     rcx, [rbp+0F0h+var_140]
0x180121f7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121f80  inc     rax
0x180121f83  cmp     [rcx+rax*2], r12w
0x180121f88  jnz     short loc_180121F80
0x180121f8a  lea     ecx, [rax+rax]
0x180121f8d  mov     r8d, 5
0x180121f93  add     rcx, 2
0x180121f97  lea     rax, [rbp+0F0h+var_140]
0x180121f9b  mov     [rsp+1F0h+var_190], rcx
0x180121fa0  lea     r9, [rsp+1F0h+var_180]
0x180121fa5  mov     [rsp+1F0h+var_198], rax
0x180121faa  lea     rdx, PLA_EVENT_ERROR
0x180121fb1  mov     [rsp+1F0h+var_1A0], r13
0x180121fb6  lea     rax, [rsp+1F0h+var_178]
0x180121fbb  mov     [rsp+1F0h+var_1A8], r15
0x180121fc0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180121fc7  mov     [rsp+1F0h+var_1B0], rdi
0x180121fcc  mov     [rsp+1F0h+var_1B8], rax
0x180121fd1  lea     rax, byte_180147320
0x180121fd8  mov     [rsp+1F0h+var_1C0], 1
0x180121fe1  mov     [rsp+1F0h+var_1C8], rax
0x180121fe6  mov     [rsp+1F0h+var_1D0], rdi
0x180121feb  call    EventingWriteEvent
0x180121ff0  lea     r15, [rsi+40h]
0x180121ff4  jmp     loc_180122133
0x180121ff9  lea     r15, [rsi+40h]
0x180121ffd  mov     rcx, [r15]; psa
0x180122000  lea     rdx, [rbp+0F0h+ppvData]; ppvData
0x180122004  call    cs:__imp_SafeArrayAccessData
0x18012200a  mov     r14d, eax
0x18012200d  test    eax, eax
0x18012200f  jns     loc_1801220E3
0x180122015  cmp     dword ptr cs:xmmword_180169738, r12d
0x18012201c  mov     [rsp+1F0h+var_178], r12d
0x180122021  mov     [rsp+1F0h+var_180], eax
0x180122025  jz      loc_180122133
0x18012202b  mov     rdx, 4000000000000800h; unsigned __int64
0x180122035  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012203c  jz      loc_180122133
0x180122042  mov     rax, cs:qword_180169748
0x180122049  and     rax, rdx
0x18012204c  cmp     cs:qword_180169748, rax
0x180122053  jnz     loc_180122133
0x180122059  lea     rcx, [rbp+0F0h+var_C0]; unsigned __int16 *
0x18012205d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180122062  lea     rcx, [rbp+0F0h+var_C0]
0x180122066  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012206a  inc     rax
0x18012206d  cmp     [rcx+rax*2], r12w
0x180122072  jnz     short loc_18012206A
0x180122074  lea     ecx, [rax+rax]
0x180122077  mov     r8d, 5
0x18012207d  add     rcx, 2
0x180122081  lea     rax, [rbp+0F0h+var_C0]
0x180122085  mov     [rsp+1F0h+var_190], rcx
0x18012208a  lea     r9, [rsp+1F0h+var_180]
0x18012208f  mov     [rsp+1F0h+var_198], rax
0x180122094  lea     rdx, PLA_EVENT_ERROR
0x18012209b  mov     [rsp+1F0h+var_1A0], r13
0x1801220a0  lea     rax, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x1801220a7  mov     [rsp+1F0h+var_1A8], rax
0x1801220ac  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801220b3  mov     [rsp+1F0h+var_1B0], rdi
0x1801220b8  lea     rax, [rsp+1F0h+var_178]
0x1801220bd  mov     [rsp+1F0h+var_1B8], rax
0x1801220c2  lea     rax, byte_180147320
0x1801220c9  mov     [rsp+1F0h+var_1C0], 1
0x1801220d2  mov     [rsp+1F0h+var_1C8], rax
0x1801220d7  mov     [rsp+1F0h+var_1D0], rdi
0x1801220dc  call    EventingWriteEvent
0x1801220e1  jmp     short loc_180122133
0x1801220e3  mov     rax, [rbp+0F0h+ppvData]
0x1801220e7  mov     ebx, [rsp+1F0h+var_180]
0x1801220eb  lea     rdi, [rbx+rbx*2]
0x1801220ef  lea     rcx, [rax+rdi*8]; pvarg
0x1801220f3  call    cs:__imp_VariantClear
0x1801220f9  mov     eax, [rsi+4Ch]
0x1801220fc  mov     rcx, [rbp+0F0h+ppvData]
0x180122100  sub     eax, ebx
0x180122102  dec     eax
0x180122104  lea     r8, [rax+rax*2]
0x180122108  lea     eax, [rbx+1]
0x18012210b  shl     r8, 3; Size
0x18012210f  lea     rax, [rax+rax*2]
0x180122113  lea     rdx, [rcx+rax*8]; Src
0x180122117  lea     rcx, [rcx+rdi*8]; void *
0x18012211b  call    memmove_0
0x180122120  dec     dword ptr [rsi+4Ch]
0x180122123  mov     eax, [rsi+4Ch]
0x180122126  lea     r8, [rax+rax*2]
0x18012212a  mov     rax, [rbp+0F0h+ppvData]
0x18012212e  mov     [rax+r8*8], r12w
0x180122133  cmp     [rsi+8], r12d
0x180122137  jz      short loc_180122143
0x180122139  lea     rcx, [rsi+10h]; lpCriticalSection
0x18012213d  call    cs:__imp_LeaveCriticalSection
0x180122143  cmp     [rbp+0F0h+ppvData], r12
0x180122147  jz      short loc_180122152
0x180122149  mov     rcx, [r15]; psa
0x18012214c  call    cs:__imp_SafeArrayUnaccessData
0x180122152  mov     eax, r14d
0x180122155  mov     rcx, [rbp+0F0h+var_40]
0x18012215c  xor     rcx, rsp; StackCookie
0x18012215f  call    __security_check_cookie
0x180122164  mov     rbx, [rsp+1F0h+arg_10]
0x18012216c  add     rsp, 1C0h
0x180122173  pop     r15
0x180122175  pop     r14
0x180122177  pop     r13
0x180122179  pop     r12
0x18012217b  pop     rdi
0x18012217c  pop     rsi
0x18012217d  pop     rbp
0x18012217e  retn
```
