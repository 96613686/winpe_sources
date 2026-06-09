# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800012bc`
- end: `0x1800015ab`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800068b4`

## callees

- `0x1800012bc`
- `0x18000163c`
- `0x1800021d0`

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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0);
}

```

## disassembly

```asm
0x1800012bc  mov     [rsp-8+arg_10], rbx
0x1800012c1  push    rbp
0x1800012c2  push    rdi
0x1800012c3  push    r14
0x1800012c5  lea     rbp, [rsp-80h]
0x1800012ca  sub     rsp, 180h
0x1800012d1  mov     rax, cs:__security_cookie
0x1800012d8  xor     rax, rsp
0x1800012db  mov     [rbp+90h+var_20], rax
0x1800012df  mov     rax, [rbp+90h+arg_A8]
0x1800012e6  lea     rdi, word_180037512
0x1800012ed  mov     r11, rdx
0x1800012f0  mov     r10, rcx
0x1800012f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800012f7  xor     ebx, ebx
0x1800012f9  mov     r8d, 1
0x1800012ff  mov     rcx, [rax]
0x180001302  test    rcx, rcx
0x180001305  jz      short loc_180001316
0x180001307  mov     rax, rdx
0x18000130a  inc     rax
0x18000130d  cmp     [rcx+rax], bl
0x180001310  jnz     short loc_18000130A
0x180001312  inc     eax
0x180001314  jmp     short loc_18000131C
0x180001316  mov     rcx, rdi
0x180001319  mov     eax, r8d
0x18000131c  mov     [rbp+90h+var_28], eax
0x18000131f  mov     r9d, 2
0x180001325  mov     rax, [rbp+90h+arg_A0]
0x18000132c  mov     [rbp+90h+var_40], rax
0x180001330  mov     rax, [rbp+90h+arg_98]
0x180001337  mov     [rbp+90h+var_50], rax
0x18000133b  mov     rax, [rbp+90h+arg_90]
0x180001342  mov     [rbp+90h+var_30], rcx
0x180001346  mov     [rbp+90h+var_24], ebx
0x180001349  mov     [rbp+90h+var_38], 4
0x180001351  mov     rcx, [rax]
0x180001354  mov     [rbp+90h+var_48], 4
0x18000135c  test    rcx, rcx
0x18000135f  jz      short loc_180001376
0x180001361  mov     rax, rdx
0x180001364  inc     rax
0x180001367  cmp     [rcx+rax*2], bx
0x18000136b  jnz     short loc_180001364
0x18000136d  lea     eax, ds:2[rax*2]
0x180001374  jmp     short loc_180001380
0x180001376  lea     rcx, Src
0x18000137d  mov     eax, r9d
0x180001380  mov     [rbp+90h+var_58], eax
0x180001383  mov     rax, [rbp+90h+arg_88]
0x18000138a  mov     [rbp+90h+var_60], rcx
0x18000138e  mov     [rbp+90h+var_54], ebx
0x180001391  mov     rcx, [rax]
0x180001394  test    rcx, rcx
0x180001397  jz      short loc_1800013A8
0x180001399  mov     rax, rdx
0x18000139c  inc     rax
0x18000139f  cmp     [rcx+rax], bl
0x1800013a2  jnz     short loc_18000139C
0x1800013a4  inc     eax
0x1800013a6  jmp     short loc_1800013AE
0x1800013a8  mov     rcx, rdi
0x1800013ab  mov     eax, r8d
0x1800013ae  mov     [rbp+90h+var_68], eax
0x1800013b1  mov     rax, [rbp+90h+arg_80]
0x1800013b8  mov     [rbp+90h+var_80], rax
0x1800013bc  mov     rax, [rbp+90h+arg_78]
0x1800013c3  mov     [rbp+90h+var_70], rcx
0x1800013c7  mov     [rbp+90h+var_64], ebx
0x1800013ca  mov     [rbp+90h+var_78], 4
0x1800013d2  mov     rcx, [rax]
0x1800013d5  test    rcx, rcx
0x1800013d8  jz      short loc_1800013EF
0x1800013da  mov     rax, rdx
0x1800013dd  inc     rax
0x1800013e0  cmp     [rcx+rax*2], bx
0x1800013e4  jnz     short loc_1800013DD
0x1800013e6  lea     eax, ds:2[rax*2]
0x1800013ed  jmp     short loc_1800013F9
0x1800013ef  lea     rcx, Src
0x1800013f6  mov     eax, r9d
0x1800013f9  mov     [rbp+90h+var_88], eax
0x1800013fc  mov     rax, [rbp+90h+arg_70]
0x180001403  mov     [rbp+90h+var_90], rcx
0x180001407  mov     [rbp+90h+var_84], ebx
0x18000140a  mov     rcx, [rax]
0x18000140d  test    rcx, rcx
0x180001410  jz      short loc_180001421
0x180001412  mov     rax, rdx
0x180001415  inc     rax
0x180001418  cmp     [rcx+rax], bl
0x18000141b  jnz     short loc_180001415
0x18000141d  inc     eax
0x18000141f  jmp     short loc_180001427
0x180001421  mov     rcx, rdi
0x180001424  mov     eax, r8d
0x180001427  mov     [rbp+90h+var_98], eax
0x18000142a  mov     rax, [rbp+90h+arg_68]
0x180001431  mov     [rbp+90h+var_B0], rax
0x180001435  mov     rax, [rbp+90h+arg_60]
0x18000143c  mov     [rbp+90h+var_A0], rcx
0x180001440  mov     [rbp+90h+var_94], ebx
0x180001443  mov     [rbp+90h+var_A8], 4
0x18000144b  mov     rcx, [rax]
0x18000144e  test    rcx, rcx
0x180001451  jz      short loc_180001462
0x180001453  mov     rax, rdx
0x180001456  inc     rax
0x180001459  cmp     [rcx+rax], bl
0x18000145c  jnz     short loc_180001456
0x18000145e  inc     eax
0x180001460  jmp     short loc_180001468
0x180001462  mov     rcx, rdi
0x180001465  mov     eax, r8d
0x180001468  mov     [rbp+90h+var_B8], eax
0x18000146b  mov     rax, [rbp+90h+arg_58]
0x180001472  mov     [rbp+90h+var_D0], rax
0x180001476  mov     rax, [rbp+90h+arg_50]
0x18000147d  mov     [rbp+90h+var_C0], rcx
0x180001481  mov     [rbp+90h+var_B4], ebx
0x180001484  mov     [rbp+90h+var_C8], 4
0x18000148c  mov     rcx, [rax]
0x18000148f  test    rcx, rcx
0x180001492  jz      short loc_1800014AA
0x180001494  mov     rax, rdx
0x180001497  inc     rax
0x18000149a  cmp     [rcx+rax*2], bx
0x18000149e  jnz     short loc_180001497
0x1800014a0  lea     r9d, ds:2[rax*2]
0x1800014a8  jmp     short loc_1800014B1
0x1800014aa  lea     rcx, Src
0x1800014b1  mov     rax, [rbp+90h+arg_48]
0x1800014b8  mov     [rbp+90h+var_F0], rax
0x1800014bc  mov     rax, [rbp+90h+arg_40]
0x1800014c3  mov     [rbp+90h+var_E0], rcx
0x1800014c7  mov     [rbp+90h+var_D8], r9d
0x1800014cb  mov     [rbp+90h+var_D4], ebx
0x1800014ce  mov     rcx, [rax]
0x1800014d1  mov     [rbp+90h+var_E8], 4
0x1800014d9  test    rcx, rcx
0x1800014dc  jz      short loc_1800014ED
0x1800014de  mov     rax, rdx
0x1800014e1  inc     rax
0x1800014e4  cmp     [rcx+rax], bl
0x1800014e7  jnz     short loc_1800014E1
0x1800014e9  inc     eax
0x1800014eb  jmp     short loc_1800014F3
0x1800014ed  mov     rcx, rdi
0x1800014f0  mov     eax, r8d
0x1800014f3  mov     [rbp+90h+var_F8], eax
0x1800014f6  mov     rax, [rbp+90h+arg_38]
0x1800014fd  mov     [rbp+90h+var_110], rax
0x180001501  mov     rax, [rbp+90h+arg_30]
0x180001508  mov     [rbp+90h+var_100], rcx
0x18000150c  mov     [rbp+90h+var_F4], ebx
0x18000150f  mov     [rbp+90h+var_108], 4
0x180001517  mov     rcx, [rax]
0x18000151a  test    rcx, rcx
0x18000151d  jz      short loc_18000152D
0x18000151f  inc     rdx
0x180001522  cmp     [rcx+rdx], bl
0x180001525  jnz     short loc_18000151F
0x180001527  lea     r8d, [rdx+1]
0x18000152b  jmp     short loc_180001530
0x18000152d  mov     rcx, rdi
0x180001530  mov     rax, [rbp+90h+arg_28]
0x180001537  xor     r9d, r9d
0x18000153a  mov     [rsp+190h+var_130], rax
0x18000153f  mov     rdx, r11
0x180001542  mov     rax, [rbp+90h+arg_20]
0x180001549  mov     [rsp+190h+var_140], rax
0x18000154e  lea     rax, [rsp+190h+var_160]
0x180001553  mov     [rsp+190h+var_120], rcx
0x180001558  mov     rcx, r10
0x18000155b  mov     [rsp+190h+var_118], r8d
0x180001560  xor     r8d, r8d
0x180001563  mov     [rsp+190h+var_168], rax
0x180001568  mov     [rsp+190h+var_170], 14h
0x180001570  mov     [rsp+190h+var_114], ebx
0x180001574  mov     [rsp+190h+var_128], 4
0x18000157d  mov     [rsp+190h+var_138], 8
0x180001586  call    _tlgWriteTransfer_EventWriteTransfer
0x18000158b  mov     rcx, [rbp+90h+var_20]
0x18000158f  xor     rcx, rsp; StackCookie
0x180001592  call    __security_check_cookie
0x180001597  mov     rbx, [rsp+190h+arg_10]
0x18000159f  add     rsp, 180h
0x1800015a6  pop     r14
0x1800015a8  pop     rdi
0x1800015a9  pop     rbp
0x1800015aa  retn
```
