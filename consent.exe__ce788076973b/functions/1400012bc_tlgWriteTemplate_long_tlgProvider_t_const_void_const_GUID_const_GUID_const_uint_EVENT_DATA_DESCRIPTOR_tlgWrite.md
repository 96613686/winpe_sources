# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400012bc`
- end: `0x1400015ab`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012ccc`

## callees

- `0x1400012bc`
- `0x140009bc0`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        _QWORD *a11,
        __int64 a12,
        _QWORD *a13,
        __int64 a14,
        _QWORD *a15,
        _QWORD *a16,
        __int64 a17,
        _QWORD *a18,
        _QWORD *a19,
        __int64 a20,
        __int64 a21,
        _QWORD *a22)
{
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax

  v23 = -1;
  if ( *a22 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(*a22 + v24) );
  }
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a19 + 2 * v25) );
  }
  if ( *a18 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a18 + v26) );
  }
  if ( *a16 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a16 + 2 * v27) );
  }
  if ( *a15 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a15 + v28) );
  }
  if ( *a13 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(*a13 + v29) );
  }
  if ( *a11 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(*a11 + 2 * v30) );
  }
  if ( *a9 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_BYTE *)(*a9 + v31) );
  }
  if ( *a7 )
  {
    do
      ++v23;
    while ( *(_BYTE *)(*a7 + v23) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1400012bc  mov     [rsp-8+arg_10], rbx
0x1400012c1  push    rbp
0x1400012c2  push    rdi
0x1400012c3  push    r14
0x1400012c5  lea     rbp, [rsp-80h]
0x1400012ca  sub     rsp, 180h
0x1400012d1  mov     rax, cs:__security_cookie
0x1400012d8  xor     rax, rsp
0x1400012db  mov     [rbp+90h+var_20], rax
0x1400012df  mov     rax, [rbp+90h+arg_A8]
0x1400012e6  lea     rdi, qword_140021870
0x1400012ed  mov     r11, rdx
0x1400012f0  mov     r10, rcx
0x1400012f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400012f7  xor     ebx, ebx
0x1400012f9  mov     r8d, 1
0x1400012ff  mov     rcx, [rax]
0x140001302  test    rcx, rcx
0x140001305  jz      short loc_140001316
0x140001307  mov     rax, rdx
0x14000130a  inc     rax
0x14000130d  cmp     [rcx+rax], bl
0x140001310  jnz     short loc_14000130A
0x140001312  inc     eax
0x140001314  jmp     short loc_14000131C
0x140001316  mov     rcx, rdi
0x140001319  mov     eax, r8d
0x14000131c  mov     [rbp+90h+var_28], eax
0x14000131f  mov     r9d, 2
0x140001325  mov     rax, [rbp+90h+arg_A0]
0x14000132c  mov     [rbp+90h+var_40], rax
0x140001330  mov     rax, [rbp+90h+arg_98]
0x140001337  mov     [rbp+90h+var_50], rax
0x14000133b  mov     rax, [rbp+90h+arg_90]
0x140001342  mov     [rbp+90h+var_30], rcx
0x140001346  mov     [rbp+90h+var_24], ebx
0x140001349  mov     [rbp+90h+var_38], 4
0x140001351  mov     rcx, [rax]
0x140001354  mov     [rbp+90h+var_48], 4
0x14000135c  test    rcx, rcx
0x14000135f  jz      short loc_140001376
0x140001361  mov     rax, rdx
0x140001364  inc     rax
0x140001367  cmp     [rcx+rax*2], bx
0x14000136b  jnz     short loc_140001364
0x14000136d  lea     eax, ds:2[rax*2]
0x140001374  jmp     short loc_140001380
0x140001376  lea     rcx, qword_1400210F8
0x14000137d  mov     eax, r9d
0x140001380  mov     [rbp+90h+var_58], eax
0x140001383  mov     rax, [rbp+90h+arg_88]
0x14000138a  mov     [rbp+90h+var_60], rcx
0x14000138e  mov     [rbp+90h+var_54], ebx
0x140001391  mov     rcx, [rax]
0x140001394  test    rcx, rcx
0x140001397  jz      short loc_1400013A8
0x140001399  mov     rax, rdx
0x14000139c  inc     rax
0x14000139f  cmp     [rcx+rax], bl
0x1400013a2  jnz     short loc_14000139C
0x1400013a4  inc     eax
0x1400013a6  jmp     short loc_1400013AE
0x1400013a8  mov     rcx, rdi
0x1400013ab  mov     eax, r8d
0x1400013ae  mov     [rbp+90h+var_68], eax
0x1400013b1  mov     rax, [rbp+90h+arg_80]
0x1400013b8  mov     [rbp+90h+var_80], rax
0x1400013bc  mov     rax, [rbp+90h+arg_78]
0x1400013c3  mov     [rbp+90h+var_70], rcx
0x1400013c7  mov     [rbp+90h+var_64], ebx
0x1400013ca  mov     [rbp+90h+var_78], 4
0x1400013d2  mov     rcx, [rax]
0x1400013d5  test    rcx, rcx
0x1400013d8  jz      short loc_1400013EF
0x1400013da  mov     rax, rdx
0x1400013dd  inc     rax
0x1400013e0  cmp     [rcx+rax*2], bx
0x1400013e4  jnz     short loc_1400013DD
0x1400013e6  lea     eax, ds:2[rax*2]
0x1400013ed  jmp     short loc_1400013F9
0x1400013ef  lea     rcx, qword_1400210F8
0x1400013f6  mov     eax, r9d
0x1400013f9  mov     [rbp+90h+var_88], eax
0x1400013fc  mov     rax, [rbp+90h+arg_70]
0x140001403  mov     [rbp+90h+var_90], rcx
0x140001407  mov     [rbp+90h+var_84], ebx
0x14000140a  mov     rcx, [rax]
0x14000140d  test    rcx, rcx
0x140001410  jz      short loc_140001421
0x140001412  mov     rax, rdx
0x140001415  inc     rax
0x140001418  cmp     [rcx+rax], bl
0x14000141b  jnz     short loc_140001415
0x14000141d  inc     eax
0x14000141f  jmp     short loc_140001427
0x140001421  mov     rcx, rdi
0x140001424  mov     eax, r8d
0x140001427  mov     [rbp+90h+var_98], eax
0x14000142a  mov     rax, [rbp+90h+arg_68]
0x140001431  mov     [rbp+90h+var_B0], rax
0x140001435  mov     rax, [rbp+90h+arg_60]
0x14000143c  mov     [rbp+90h+var_A0], rcx
0x140001440  mov     [rbp+90h+var_94], ebx
0x140001443  mov     [rbp+90h+var_A8], 4
0x14000144b  mov     rcx, [rax]
0x14000144e  test    rcx, rcx
0x140001451  jz      short loc_140001462
0x140001453  mov     rax, rdx
0x140001456  inc     rax
0x140001459  cmp     [rcx+rax], bl
0x14000145c  jnz     short loc_140001456
0x14000145e  inc     eax
0x140001460  jmp     short loc_140001468
0x140001462  mov     rcx, rdi
0x140001465  mov     eax, r8d
0x140001468  mov     [rbp+90h+var_B8], eax
0x14000146b  mov     rax, [rbp+90h+arg_58]
0x140001472  mov     [rbp+90h+var_D0], rax
0x140001476  mov     rax, [rbp+90h+arg_50]
0x14000147d  mov     [rbp+90h+var_C0], rcx
0x140001481  mov     [rbp+90h+var_B4], ebx
0x140001484  mov     [rbp+90h+var_C8], 4
0x14000148c  mov     rcx, [rax]
0x14000148f  test    rcx, rcx
0x140001492  jz      short loc_1400014AA
0x140001494  mov     rax, rdx
0x140001497  inc     rax
0x14000149a  cmp     [rcx+rax*2], bx
0x14000149e  jnz     short loc_140001497
0x1400014a0  lea     r9d, ds:2[rax*2]
0x1400014a8  jmp     short loc_1400014B1
0x1400014aa  lea     rcx, qword_1400210F8
0x1400014b1  mov     rax, [rbp+90h+arg_48]
0x1400014b8  mov     [rbp+90h+var_F0], rax
0x1400014bc  mov     rax, [rbp+90h+arg_40]
0x1400014c3  mov     [rbp+90h+var_E0], rcx
0x1400014c7  mov     [rbp+90h+var_D8], r9d
0x1400014cb  mov     [rbp+90h+var_D4], ebx
0x1400014ce  mov     rcx, [rax]
0x1400014d1  mov     [rbp+90h+var_E8], 4
0x1400014d9  test    rcx, rcx
0x1400014dc  jz      short loc_1400014ED
0x1400014de  mov     rax, rdx
0x1400014e1  inc     rax
0x1400014e4  cmp     [rcx+rax], bl
0x1400014e7  jnz     short loc_1400014E1
0x1400014e9  inc     eax
0x1400014eb  jmp     short loc_1400014F3
0x1400014ed  mov     rcx, rdi
0x1400014f0  mov     eax, r8d
0x1400014f3  mov     [rbp+90h+var_F8], eax
0x1400014f6  mov     rax, [rbp+90h+arg_38]
0x1400014fd  mov     [rbp+90h+var_110], rax
0x140001501  mov     rax, [rbp+90h+arg_30]
0x140001508  mov     [rbp+90h+var_100], rcx
0x14000150c  mov     [rbp+90h+var_F4], ebx
0x14000150f  mov     [rbp+90h+var_108], 4
0x140001517  mov     rcx, [rax]
0x14000151a  test    rcx, rcx
0x14000151d  jz      short loc_14000152D
0x14000151f  inc     rdx
0x140001522  cmp     [rcx+rdx], bl
0x140001525  jnz     short loc_14000151F
0x140001527  lea     r8d, [rdx+1]
0x14000152b  jmp     short loc_140001530
0x14000152d  mov     rcx, rdi
0x140001530  mov     rax, [rbp+90h+arg_28]
0x140001537  xor     r9d, r9d
0x14000153a  mov     [rsp+190h+var_130], rax
0x14000153f  mov     rdx, r11
0x140001542  mov     rax, [rbp+90h+arg_20]
0x140001549  mov     [rsp+190h+var_140], rax
0x14000154e  lea     rax, [rsp+190h+var_160]
0x140001553  mov     [rsp+190h+var_120], rcx
0x140001558  mov     rcx, r10
0x14000155b  mov     [rsp+190h+var_118], r8d
0x140001560  xor     r8d, r8d
0x140001563  mov     [rsp+190h+var_168], rax
0x140001568  mov     [rsp+190h+var_170], 14h
0x140001570  mov     [rsp+190h+var_114], ebx
0x140001574  mov     [rsp+190h+var_128], 4
0x14000157d  mov     [rsp+190h+var_138], 8
0x140001586  call    _tlgWriteTransfer_EventWriteTransfer
0x14000158b  mov     rcx, [rbp+90h+var_20]
0x14000158f  xor     rcx, rsp; StackCookie
0x140001592  call    __security_check_cookie
0x140001597  mov     rbx, [rsp+190h+arg_10]
0x14000159f  add     rsp, 180h
0x1400015a6  pop     r14
0x1400015a8  pop     rdi
0x1400015a9  pop     rbp
0x1400015aa  retn
```
