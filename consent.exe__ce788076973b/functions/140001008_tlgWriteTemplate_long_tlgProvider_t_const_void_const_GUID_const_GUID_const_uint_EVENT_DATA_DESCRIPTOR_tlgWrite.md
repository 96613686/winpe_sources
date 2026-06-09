# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x1400012b3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012b5c`

## callees

- `0x140001008`
- `0x140009bc0`
- `0x14001e050`

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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x140001008  mov     [rsp-8+arg_10], rbx
0x14000100d  push    rbp
0x14000100e  push    rsi
0x14000100f  push    rdi
0x140001010  lea     rbp, [rsp-60h]
0x140001015  sub     rsp, 160h
0x14000101c  mov     rax, cs:__security_cookie
0x140001023  xor     rax, rsp
0x140001026  mov     [rbp+70h+var_20], rax
0x14000102a  mov     rax, [rbp+70h+arg_98]
0x140001031  mov     r11, rdx
0x140001034  mov     r10, rcx
0x140001037  xor     ebx, ebx
0x140001039  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000103d  mov     r9d, 2
0x140001043  mov     rdx, [rax]
0x140001046  test    rdx, rdx
0x140001049  jz      short loc_140001060
0x14000104b  mov     rax, rcx
0x14000104e  inc     rax
0x140001051  cmp     [rdx+rax*2], bx
0x140001055  jnz     short loc_14000104E
0x140001057  lea     eax, ds:2[rax*2]
0x14000105e  jmp     short loc_14000106A
0x140001060  lea     rdx, qword_1400210F8
0x140001067  mov     eax, r9d
0x14000106a  mov     [rbp+70h+var_28], eax
0x14000106d  lea     rdi, qword_140021870
0x140001074  mov     rax, [rbp+70h+arg_90]
0x14000107b  mov     r8d, 1
0x140001081  mov     [rbp+70h+var_30], rdx
0x140001085  mov     [rbp+70h+var_24], ebx
0x140001088  mov     rdx, [rax]
0x14000108b  test    rdx, rdx
0x14000108e  jz      short loc_14000109F
0x140001090  mov     rax, rcx
0x140001093  inc     rax
0x140001096  cmp     [rdx+rax], bl
0x140001099  jnz     short loc_140001093
0x14000109b  inc     eax
0x14000109d  jmp     short loc_1400010A5
0x14000109f  mov     rdx, rdi
0x1400010a2  mov     eax, r8d
0x1400010a5  mov     [rbp+70h+var_38], eax
0x1400010a8  mov     rax, [rbp+70h+arg_88]
0x1400010af  mov     [rbp+70h+var_50], rax
0x1400010b3  mov     rax, [rbp+70h+arg_80]
0x1400010ba  mov     [rbp+70h+var_40], rdx
0x1400010be  mov     [rbp+70h+var_34], ebx
0x1400010c1  mov     [rbp+70h+var_48], 4
0x1400010c9  mov     rdx, [rax]
0x1400010cc  test    rdx, rdx
0x1400010cf  jz      short loc_1400010E6
0x1400010d1  mov     rax, rcx
0x1400010d4  inc     rax
0x1400010d7  cmp     [rdx+rax*2], bx
0x1400010db  jnz     short loc_1400010D4
0x1400010dd  lea     eax, ds:2[rax*2]
0x1400010e4  jmp     short loc_1400010F0
0x1400010e6  lea     rdx, qword_1400210F8
0x1400010ed  mov     eax, r9d
0x1400010f0  mov     [rbp+70h+var_58], eax
0x1400010f3  mov     rax, [rbp+70h+arg_78]
0x1400010fa  mov     [rbp+70h+var_60], rdx
0x1400010fe  mov     [rbp+70h+var_54], ebx
0x140001101  mov     rdx, [rax]
0x140001104  test    rdx, rdx
0x140001107  jz      short loc_140001118
0x140001109  mov     rax, rcx
0x14000110c  inc     rax
0x14000110f  cmp     [rdx+rax], bl
0x140001112  jnz     short loc_14000110C
0x140001114  inc     eax
0x140001116  jmp     short loc_14000111E
0x140001118  mov     rdx, rdi
0x14000111b  mov     eax, r8d
0x14000111e  mov     [rbp+70h+var_68], eax
0x140001121  mov     rax, [rbp+70h+arg_70]
0x140001128  mov     [rbp+70h+var_80], rax
0x14000112c  mov     rax, [rbp+70h+arg_68]
0x140001133  mov     [rbp+70h+var_70], rdx
0x140001137  mov     [rbp+70h+var_64], ebx
0x14000113a  mov     [rbp+70h+var_78], 4
0x140001142  mov     rdx, [rax]
0x140001145  test    rdx, rdx
0x140001148  jz      short loc_140001159
0x14000114a  mov     rax, rcx
0x14000114d  inc     rax
0x140001150  cmp     [rdx+rax], bl
0x140001153  jnz     short loc_14000114D
0x140001155  inc     eax
0x140001157  jmp     short loc_14000115F
0x140001159  mov     rdx, rdi
0x14000115c  mov     eax, r8d
0x14000115f  mov     [rbp+70h+var_88], eax
0x140001162  mov     rax, [rbp+70h+arg_60]
0x140001169  mov     [rbp+70h+var_A0], rax
0x14000116d  mov     rax, [rbp+70h+arg_58]
0x140001174  mov     [rbp+70h+var_90], rdx
0x140001178  mov     [rbp+70h+var_84], ebx
0x14000117b  mov     [rbp+70h+var_98], 4
0x140001183  mov     rdx, [rax]
0x140001186  test    rdx, rdx
0x140001189  jz      short loc_1400011A1
0x14000118b  mov     rax, rcx
0x14000118e  inc     rax
0x140001191  cmp     [rdx+rax*2], bx
0x140001195  jnz     short loc_14000118E
0x140001197  lea     r9d, ds:2[rax*2]
0x14000119f  jmp     short loc_1400011A8
0x1400011a1  lea     rdx, qword_1400210F8
0x1400011a8  mov     rax, [rbp+70h+arg_50]
0x1400011af  mov     [rbp+70h+var_C0], rax
0x1400011b3  mov     rax, [rbp+70h+arg_48]
0x1400011ba  mov     [rbp+70h+var_B0], rdx
0x1400011be  mov     [rbp+70h+var_A8], r9d
0x1400011c2  mov     [rbp+70h+var_A4], ebx
0x1400011c5  mov     rdx, [rax]
0x1400011c8  mov     [rbp+70h+var_B8], 4
0x1400011d0  test    rdx, rdx
0x1400011d3  jz      short loc_1400011E4
0x1400011d5  mov     rax, rcx
0x1400011d8  inc     rax
0x1400011db  cmp     [rdx+rax], bl
0x1400011de  jnz     short loc_1400011D8
0x1400011e0  inc     eax
0x1400011e2  jmp     short loc_1400011EA
0x1400011e4  mov     rdx, rdi
0x1400011e7  mov     eax, r8d
0x1400011ea  mov     [rbp+70h+var_C8], eax
0x1400011ed  mov     rax, [rbp+70h+arg_40]
0x1400011f4  mov     [rbp+70h+var_E0], rax
0x1400011f8  mov     rax, [rbp+70h+arg_38]
0x1400011ff  mov     [rbp+70h+var_D0], rdx
0x140001203  mov     [rbp+70h+var_C4], ebx
0x140001206  mov     [rbp+70h+var_D8], 4
0x14000120e  mov     rdx, [rax]
0x140001211  test    rdx, rdx
0x140001214  jz      short loc_140001224
0x140001216  inc     rcx
0x140001219  cmp     [rdx+rcx], bl
0x14000121c  jnz     short loc_140001216
0x14000121e  lea     r8d, [rcx+1]
0x140001222  jmp     short loc_140001227
0x140001224  mov     rdx, rdi
0x140001227  mov     rax, [rbp+70h+arg_30]
0x14000122e  xor     r9d, r9d
0x140001231  mov     [rsp+170h+var_100], rax
0x140001236  mov     rcx, r10
0x140001239  mov     rax, [rbp+70h+arg_28]
0x140001240  mov     [rsp+170h+var_110], rax
0x140001245  mov     rax, [rbp+70h+arg_20]
0x14000124c  mov     [rsp+170h+var_120], rax
0x140001251  lea     rax, [rsp+170h+var_140]
0x140001256  mov     [rbp+70h+var_F0], rdx
0x14000125a  mov     rdx, r11
0x14000125d  mov     [rbp+70h+var_E8], r8d
0x140001261  xor     r8d, r8d
0x140001264  mov     [rsp+170h+var_148], rax
0x140001269  mov     [rsp+170h+var_150], 12h
0x140001271  mov     [rbp+70h+var_E4], ebx
0x140001274  mov     [rsp+170h+var_F8], 4
0x14000127d  mov     [rsp+170h+var_108], 8
0x140001286  mov     [rsp+170h+var_118], 8
0x14000128f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001294  mov     rcx, [rbp+70h+var_20]
0x140001298  xor     rcx, rsp; StackCookie
0x14000129b  call    __security_check_cookie
0x1400012a0  mov     rbx, [rsp+170h+arg_10]
0x1400012a8  add     rsp, 160h
0x1400012af  pop     rdi
0x1400012b0  pop     rsi
0x1400012b1  pop     rbp
0x1400012b2  retn
```
