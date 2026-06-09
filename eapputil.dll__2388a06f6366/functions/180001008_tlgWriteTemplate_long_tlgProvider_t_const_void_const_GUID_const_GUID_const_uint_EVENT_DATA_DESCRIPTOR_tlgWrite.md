# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x1800012b3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000674c`

## callees

- `0x180001008`
- `0x18000163c`
- `0x1800021d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        __int64 a18,
        _QWORD *a19,
        _QWORD *a20)
{
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax

  v21 = -1;
  if ( *a20 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a20 + 2 * v22) );
  }
  if ( *a19 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(*a19 + v23) );
  }
  if ( *a17 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a17 + 2 * v24) );
  }
  if ( *a16 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a16 + v25) );
  }
  if ( *a14 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a14 + v26) );
  }
  if ( *a12 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a12 + 2 * v27) );
  }
  if ( *a10 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a10 + v28) );
  }
  if ( *a8 )
  {
    do
      ++v21;
    while ( *(_BYTE *)(*a8 + v21) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_10], rbx
0x18000100d  push    rbp
0x18000100e  push    rsi
0x18000100f  push    rdi
0x180001010  lea     rbp, [rsp-60h]
0x180001015  sub     rsp, 160h
0x18000101c  mov     rax, cs:__security_cookie
0x180001023  xor     rax, rsp
0x180001026  mov     [rbp+70h+var_20], rax
0x18000102a  mov     rax, [rbp+70h+arg_98]
0x180001031  mov     r11, rdx
0x180001034  mov     r10, rcx
0x180001037  xor     ebx, ebx
0x180001039  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103d  mov     r9d, 2
0x180001043  mov     rdx, [rax]
0x180001046  test    rdx, rdx
0x180001049  jz      short loc_180001060
0x18000104b  mov     rax, rcx
0x18000104e  inc     rax
0x180001051  cmp     [rdx+rax*2], bx
0x180001055  jnz     short loc_18000104E
0x180001057  lea     eax, ds:2[rax*2]
0x18000105e  jmp     short loc_18000106A
0x180001060  lea     rdx, Src
0x180001067  mov     eax, r9d
0x18000106a  mov     [rbp+70h+var_28], eax
0x18000106d  lea     rdi, word_180037512
0x180001074  mov     rax, [rbp+70h+arg_90]
0x18000107b  mov     r8d, 1
0x180001081  mov     [rbp+70h+var_30], rdx
0x180001085  mov     [rbp+70h+var_24], ebx
0x180001088  mov     rdx, [rax]
0x18000108b  test    rdx, rdx
0x18000108e  jz      short loc_18000109F
0x180001090  mov     rax, rcx
0x180001093  inc     rax
0x180001096  cmp     [rdx+rax], bl
0x180001099  jnz     short loc_180001093
0x18000109b  inc     eax
0x18000109d  jmp     short loc_1800010A5
0x18000109f  mov     rdx, rdi
0x1800010a2  mov     eax, r8d
0x1800010a5  mov     [rbp+70h+var_38], eax
0x1800010a8  mov     rax, [rbp+70h+arg_88]
0x1800010af  mov     [rbp+70h+var_50], rax
0x1800010b3  mov     rax, [rbp+70h+arg_80]
0x1800010ba  mov     [rbp+70h+var_40], rdx
0x1800010be  mov     [rbp+70h+var_34], ebx
0x1800010c1  mov     [rbp+70h+var_48], 4
0x1800010c9  mov     rdx, [rax]
0x1800010cc  test    rdx, rdx
0x1800010cf  jz      short loc_1800010E6
0x1800010d1  mov     rax, rcx
0x1800010d4  inc     rax
0x1800010d7  cmp     [rdx+rax*2], bx
0x1800010db  jnz     short loc_1800010D4
0x1800010dd  lea     eax, ds:2[rax*2]
0x1800010e4  jmp     short loc_1800010F0
0x1800010e6  lea     rdx, Src
0x1800010ed  mov     eax, r9d
0x1800010f0  mov     [rbp+70h+var_58], eax
0x1800010f3  mov     rax, [rbp+70h+arg_78]
0x1800010fa  mov     [rbp+70h+var_60], rdx
0x1800010fe  mov     [rbp+70h+var_54], ebx
0x180001101  mov     rdx, [rax]
0x180001104  test    rdx, rdx
0x180001107  jz      short loc_180001118
0x180001109  mov     rax, rcx
0x18000110c  inc     rax
0x18000110f  cmp     [rdx+rax], bl
0x180001112  jnz     short loc_18000110C
0x180001114  inc     eax
0x180001116  jmp     short loc_18000111E
0x180001118  mov     rdx, rdi
0x18000111b  mov     eax, r8d
0x18000111e  mov     [rbp+70h+var_68], eax
0x180001121  mov     rax, [rbp+70h+arg_70]
0x180001128  mov     [rbp+70h+var_80], rax
0x18000112c  mov     rax, [rbp+70h+arg_68]
0x180001133  mov     [rbp+70h+var_70], rdx
0x180001137  mov     [rbp+70h+var_64], ebx
0x18000113a  mov     [rbp+70h+var_78], 4
0x180001142  mov     rdx, [rax]
0x180001145  test    rdx, rdx
0x180001148  jz      short loc_180001159
0x18000114a  mov     rax, rcx
0x18000114d  inc     rax
0x180001150  cmp     [rdx+rax], bl
0x180001153  jnz     short loc_18000114D
0x180001155  inc     eax
0x180001157  jmp     short loc_18000115F
0x180001159  mov     rdx, rdi
0x18000115c  mov     eax, r8d
0x18000115f  mov     [rbp+70h+var_88], eax
0x180001162  mov     rax, [rbp+70h+arg_60]
0x180001169  mov     [rbp+70h+var_A0], rax
0x18000116d  mov     rax, [rbp+70h+arg_58]
0x180001174  mov     [rbp+70h+var_90], rdx
0x180001178  mov     [rbp+70h+var_84], ebx
0x18000117b  mov     [rbp+70h+var_98], 4
0x180001183  mov     rdx, [rax]
0x180001186  test    rdx, rdx
0x180001189  jz      short loc_1800011A1
0x18000118b  mov     rax, rcx
0x18000118e  inc     rax
0x180001191  cmp     [rdx+rax*2], bx
0x180001195  jnz     short loc_18000118E
0x180001197  lea     r9d, ds:2[rax*2]
0x18000119f  jmp     short loc_1800011A8
0x1800011a1  lea     rdx, Src
0x1800011a8  mov     rax, [rbp+70h+arg_50]
0x1800011af  mov     [rbp+70h+var_C0], rax
0x1800011b3  mov     rax, [rbp+70h+arg_48]
0x1800011ba  mov     [rbp+70h+var_B0], rdx
0x1800011be  mov     [rbp+70h+var_A8], r9d
0x1800011c2  mov     [rbp+70h+var_A4], ebx
0x1800011c5  mov     rdx, [rax]
0x1800011c8  mov     [rbp+70h+var_B8], 4
0x1800011d0  test    rdx, rdx
0x1800011d3  jz      short loc_1800011E4
0x1800011d5  mov     rax, rcx
0x1800011d8  inc     rax
0x1800011db  cmp     [rdx+rax], bl
0x1800011de  jnz     short loc_1800011D8
0x1800011e0  inc     eax
0x1800011e2  jmp     short loc_1800011EA
0x1800011e4  mov     rdx, rdi
0x1800011e7  mov     eax, r8d
0x1800011ea  mov     [rbp+70h+var_C8], eax
0x1800011ed  mov     rax, [rbp+70h+arg_40]
0x1800011f4  mov     [rbp+70h+var_E0], rax
0x1800011f8  mov     rax, [rbp+70h+arg_38]
0x1800011ff  mov     [rbp+70h+var_D0], rdx
0x180001203  mov     [rbp+70h+var_C4], ebx
0x180001206  mov     [rbp+70h+var_D8], 4
0x18000120e  mov     rdx, [rax]
0x180001211  test    rdx, rdx
0x180001214  jz      short loc_180001224
0x180001216  inc     rcx
0x180001219  cmp     [rdx+rcx], bl
0x18000121c  jnz     short loc_180001216
0x18000121e  lea     r8d, [rcx+1]
0x180001222  jmp     short loc_180001227
0x180001224  mov     rdx, rdi
0x180001227  mov     rax, [rbp+70h+arg_30]
0x18000122e  xor     r9d, r9d
0x180001231  mov     [rsp+170h+var_100], rax
0x180001236  mov     rcx, r10
0x180001239  mov     rax, [rbp+70h+arg_28]
0x180001240  mov     [rsp+170h+var_110], rax
0x180001245  mov     rax, [rbp+70h+arg_20]
0x18000124c  mov     [rsp+170h+var_120], rax
0x180001251  lea     rax, [rsp+170h+var_140]
0x180001256  mov     [rbp+70h+var_F0], rdx
0x18000125a  mov     rdx, r11
0x18000125d  mov     [rbp+70h+var_E8], r8d
0x180001261  xor     r8d, r8d
0x180001264  mov     [rsp+170h+var_148], rax
0x180001269  mov     [rsp+170h+var_150], 12h
0x180001271  mov     [rbp+70h+var_E4], ebx
0x180001274  mov     [rsp+170h+var_F8], 4
0x18000127d  mov     [rsp+170h+var_108], 8
0x180001286  mov     [rsp+170h+var_118], 8
0x18000128f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001294  mov     rcx, [rbp+70h+var_20]
0x180001298  xor     rcx, rsp; StackCookie
0x18000129b  call    __security_check_cookie
0x1800012a0  mov     rbx, [rsp+170h+arg_10]
0x1800012a8  add     rsp, 160h
0x1800012af  pop     rdi
0x1800012b0  pop     rsi
0x1800012b1  pop     rbp
0x1800012b2  retn
```
