# Enumerator::RemoveNamed<IDataCollectorSet>(tagVARIANT,long (IDataCollectorSet::*)(ushort * *))

- ea: `0x180121408`
- end: `0x180121767`
- name: `??$RemoveNamed@UIDataCollectorSet@@@Enumerator@@QEAAJUtagVARIANT@@P8IDataCollectorSet@@EAAJPEAPEAG@Z@Z`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180100b50`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180120bfc`
- `0x180121408`
- `0x18013ae8e`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121725`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801214e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801214e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801216db`
- `OLEAUT32!__imp_VariantClear` at `0x1801216db`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801215ec`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801215ec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180121734`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180121734`

## string_xrefs

- `0x18012143b`: `Enumerator::RemoveNamed`
- `0x180121688`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<IDataCollectorSet>(__int64 a1, __int128 *a2, __int64 a3)
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
  v6 = Enumerator::GetIndex<IDataCollectorSet>(a1, &v19, a3, &v15);
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
0x180121408  mov     [rsp-8+arg_10], rbx
0x18012140d  push    rbp
0x18012140e  push    rsi
0x18012140f  push    rdi
0x180121410  push    r12
0x180121412  push    r13
0x180121414  push    r14
0x180121416  push    r15
0x180121418  lea     rbp, [rsp-0C0h]
0x180121420  sub     rsp, 1C0h
0x180121427  mov     rax, cs:__security_cookie
0x18012142e  xor     rax, rsp
0x180121431  mov     [rbp+0F0h+var_40], rax
0x180121438  mov     eax, [rcx+38h]
0x18012143b  lea     r15, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x180121442  xor     r12d, r12d
0x180121445  mov     [rsp+1F0h+var_178], eax
0x180121449  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121450  mov     rbx, rdx
0x180121453  mov     rsi, rcx
0x180121456  mov     [rsp+1F0h+var_180], r12d
0x18012145b  mov     [rbp+0F0h+ppvData], r12
0x18012145f  lea     edi, [r12+4]
0x180121464  mov     [rbp+0F0h+var_168], rcx
0x180121468  lea     r13d, [r12+18h]
0x18012146d  jz      short loc_1801214D6
0x18012146f  mov     rdx, 4000000000000400h
0x180121479  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121480  jz      short loc_1801214D6
0x180121482  mov     rax, cs:qword_180169748
0x180121489  and     rax, rdx
0x18012148c  cmp     cs:qword_180169748, rax
0x180121493  jnz     short loc_1801214D6
0x180121495  mov     [rsp+1F0h+var_1B0], rdi
0x18012149a  lea     rax, [rsp+1F0h+var_178]
0x18012149f  mov     [rsp+1F0h+var_1B8], rax
0x1801214a4  lea     r8d, [r12+3]
0x1801214a9  lea     rax, [rbp+0F0h+var_168]
0x1801214ad  mov     [rsp+1F0h+var_1C0], 8
0x1801214b6  mov     [rsp+1F0h+var_1C8], rax
0x1801214bb  lea     rdx, PLA_EVENT_METHOD
0x1801214c2  mov     r9, r15
0x1801214c5  mov     [rsp+1F0h+var_1D0], r13
0x1801214ca  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801214d1  call    EventingWriteEvent
0x1801214d6  cmp     [rsi+8], r12d
0x1801214da  jz      short loc_1801214E6
0x1801214dc  lea     rcx, [rsi+10h]; lpCriticalSection
0x1801214e0  call    cs:__imp_EnterCriticalSection
0x1801214e6  movaps  xmm0, xmmword ptr [rbx]
0x1801214e9  lea     r9, [rsp+1F0h+var_180]
0x1801214ee  movsd   xmm1, qword ptr [rbx+10h]
0x1801214f3  lea     rdx, [rbp+0F0h+var_160]
0x1801214f7  mov     rcx, rsi
0x1801214fa  movaps  [rbp+0F0h+var_160], xmm0
0x1801214fe  movsd   [rbp+0F0h+var_150], xmm1
0x180121503  call    ??$GetIndex@UIDataCollectorSet@@@Enumerator@@IEAAJUtagVARIANT@@P8IDataCollectorSet@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IDataCollectorSet>(tagVARIANT,long (IDataCollectorSet::*)(ushort * *),ulong *)
0x180121508  mov     r14d, eax
0x18012150b  test    eax, eax
0x18012150d  jns     loc_1801215E1
0x180121513  cmp     dword ptr cs:xmmword_180169738, r12d
0x18012151a  mov     [rsp+1F0h+var_178], r12d
0x18012151f  mov     [rsp+1F0h+var_180], eax
0x180121523  jz      loc_1801215D8
0x180121529  mov     rdx, 4000000000000800h; unsigned __int64
0x180121533  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012153a  jz      loc_1801215D8
0x180121540  mov     rax, cs:qword_180169748
0x180121547  and     rax, rdx
0x18012154a  cmp     cs:qword_180169748, rax
0x180121551  jnz     loc_1801215D8
0x180121557  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 *
0x18012155b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121560  lea     rcx, [rbp+0F0h+var_140]
0x180121564  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121568  inc     rax
0x18012156b  cmp     [rcx+rax*2], r12w
0x180121570  jnz     short loc_180121568
0x180121572  lea     ecx, [rax+rax]
0x180121575  mov     r8d, 5
0x18012157b  add     rcx, 2
0x18012157f  lea     rax, [rbp+0F0h+var_140]
0x180121583  mov     [rsp+1F0h+var_190], rcx
0x180121588  lea     r9, [rsp+1F0h+var_180]
0x18012158d  mov     [rsp+1F0h+var_198], rax
0x180121592  lea     rdx, PLA_EVENT_ERROR
0x180121599  mov     [rsp+1F0h+var_1A0], r13
0x18012159e  lea     rax, [rsp+1F0h+var_178]
0x1801215a3  mov     [rsp+1F0h+var_1A8], r15
0x1801215a8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801215af  mov     [rsp+1F0h+var_1B0], rdi
0x1801215b4  mov     [rsp+1F0h+var_1B8], rax
0x1801215b9  lea     rax, byte_180147320
0x1801215c0  mov     [rsp+1F0h+var_1C0], 1
0x1801215c9  mov     [rsp+1F0h+var_1C8], rax
0x1801215ce  mov     [rsp+1F0h+var_1D0], rdi
0x1801215d3  call    EventingWriteEvent
0x1801215d8  lea     r15, [rsi+40h]
0x1801215dc  jmp     loc_18012171B
0x1801215e1  lea     r15, [rsi+40h]
0x1801215e5  mov     rcx, [r15]; psa
0x1801215e8  lea     rdx, [rbp+0F0h+ppvData]; ppvData
0x1801215ec  call    cs:__imp_SafeArrayAccessData
0x1801215f2  mov     r14d, eax
0x1801215f5  test    eax, eax
0x1801215f7  jns     loc_1801216CB
0x1801215fd  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121604  mov     [rsp+1F0h+var_178], r12d
0x180121609  mov     [rsp+1F0h+var_180], eax
0x18012160d  jz      loc_18012171B
0x180121613  mov     rdx, 4000000000000800h; unsigned __int64
0x18012161d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121624  jz      loc_18012171B
0x18012162a  mov     rax, cs:qword_180169748
0x180121631  and     rax, rdx
0x180121634  cmp     cs:qword_180169748, rax
0x18012163b  jnz     loc_18012171B
0x180121641  lea     rcx, [rbp+0F0h+var_C0]; unsigned __int16 *
0x180121645  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012164a  lea     rcx, [rbp+0F0h+var_C0]
0x18012164e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121652  inc     rax
0x180121655  cmp     [rcx+rax*2], r12w
0x18012165a  jnz     short loc_180121652
0x18012165c  lea     ecx, [rax+rax]
0x18012165f  mov     r8d, 5
0x180121665  add     rcx, 2
0x180121669  lea     rax, [rbp+0F0h+var_C0]
0x18012166d  mov     [rsp+1F0h+var_190], rcx
0x180121672  lea     r9, [rsp+1F0h+var_180]
0x180121677  mov     [rsp+1F0h+var_198], rax
0x18012167c  lea     rdx, PLA_EVENT_ERROR
0x180121683  mov     [rsp+1F0h+var_1A0], r13
0x180121688  lea     rax, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x18012168f  mov     [rsp+1F0h+var_1A8], rax
0x180121694  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18012169b  mov     [rsp+1F0h+var_1B0], rdi
0x1801216a0  lea     rax, [rsp+1F0h+var_178]
0x1801216a5  mov     [rsp+1F0h+var_1B8], rax
0x1801216aa  lea     rax, byte_180147320
0x1801216b1  mov     [rsp+1F0h+var_1C0], 1
0x1801216ba  mov     [rsp+1F0h+var_1C8], rax
0x1801216bf  mov     [rsp+1F0h+var_1D0], rdi
0x1801216c4  call    EventingWriteEvent
0x1801216c9  jmp     short loc_18012171B
0x1801216cb  mov     rax, [rbp+0F0h+ppvData]
0x1801216cf  mov     ebx, [rsp+1F0h+var_180]
0x1801216d3  lea     rdi, [rbx+rbx*2]
0x1801216d7  lea     rcx, [rax+rdi*8]; pvarg
0x1801216db  call    cs:__imp_VariantClear
0x1801216e1  mov     eax, [rsi+4Ch]
0x1801216e4  mov     rcx, [rbp+0F0h+ppvData]
0x1801216e8  sub     eax, ebx
0x1801216ea  dec     eax
0x1801216ec  lea     r8, [rax+rax*2]
0x1801216f0  lea     eax, [rbx+1]
0x1801216f3  shl     r8, 3; Size
0x1801216f7  lea     rax, [rax+rax*2]
0x1801216fb  lea     rdx, [rcx+rax*8]; Src
0x1801216ff  lea     rcx, [rcx+rdi*8]; void *
0x180121703  call    memmove_0
0x180121708  dec     dword ptr [rsi+4Ch]
0x18012170b  mov     eax, [rsi+4Ch]
0x18012170e  lea     r8, [rax+rax*2]
0x180121712  mov     rax, [rbp+0F0h+ppvData]
0x180121716  mov     [rax+r8*8], r12w
0x18012171b  cmp     [rsi+8], r12d
0x18012171f  jz      short loc_18012172B
0x180121721  lea     rcx, [rsi+10h]; lpCriticalSection
0x180121725  call    cs:__imp_LeaveCriticalSection
0x18012172b  cmp     [rbp+0F0h+ppvData], r12
0x18012172f  jz      short loc_18012173A
0x180121731  mov     rcx, [r15]; psa
0x180121734  call    cs:__imp_SafeArrayUnaccessData
0x18012173a  mov     eax, r14d
0x18012173d  mov     rcx, [rbp+0F0h+var_40]
0x180121744  xor     rcx, rsp; StackCookie
0x180121747  call    __security_check_cookie
0x18012174c  mov     rbx, [rsp+1F0h+arg_10]
0x180121754  add     rsp, 1C0h
0x18012175b  pop     r15
0x18012175d  pop     r14
0x18012175f  pop     r13
0x180121761  pop     r12
0x180121763  pop     rdi
0x180121764  pop     rsi
0x180121765  pop     rbp
0x180121766  retn
```
