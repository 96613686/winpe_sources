# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800016dc`
- end: `0x180001a57`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U1@U1@U3@U2@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U4@U2@U2@U2@U2@U1@U1@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@53354444AEBU?$_tlgWrapperByVal@$00@@644443344444AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b108`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x1800021d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10,
        _QWORD *a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        _QWORD *a22,
        _QWORD *a23)
{
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax

  v24 = -1;
  if ( *a23 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a23 + v25) );
  }
  if ( *a22 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a22 + v26) );
  }
  if ( *a11 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a11 + 2 * v27) );
  }
  if ( *a10 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a10 + v28) );
  }
  if ( *a9 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(*a9 + v29) );
  }
  if ( *a8 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(*a8 + 2 * v30) );
  }
  if ( *a7 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_WORD *)(*a7 + 2 * v31) );
  }
  if ( *a5 )
  {
    do
      ++v24;
    while ( *(_BYTE *)(*a5 + v24) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0);
}

```

## disassembly

```asm
0x1800016dc  mov     [rsp-8+arg_10], rbx
0x1800016e1  push    rbp
0x1800016e2  push    rsi
0x1800016e3  push    rdi
0x1800016e4  lea     rbp, [rsp-0F0h]
0x1800016ec  sub     rsp, 1F0h
0x1800016f3  mov     rax, cs:__security_cookie
0x1800016fa  xor     rax, rsp
0x1800016fd  mov     [rbp+100h+var_20], rax
0x180001704  mov     rax, [rbp+100h+arg_E0]
0x18000170b  lea     rdi, word_180037512
0x180001712  mov     [rbp+100h+var_30], rax
0x180001719  xor     ebx, ebx
0x18000171b  mov     rax, [rbp+100h+arg_D8]
0x180001722  mov     r11, rdx
0x180001725  mov     [rbp+100h+var_40], rax
0x18000172c  mov     r10, rcx
0x18000172f  mov     rax, [rbp+100h+arg_D0]
0x180001736  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000173a  mov     [rbp+100h+var_50], rax
0x180001741  lea     r8d, [rbx+1]
0x180001745  mov     rax, [rbp+100h+arg_C8]
0x18000174c  mov     [rbp+100h+var_60], rax
0x180001753  mov     rax, [rbp+100h+arg_C0]
0x18000175a  mov     [rbp+100h+var_70], rax
0x180001761  mov     rax, [rbp+100h+arg_B8]
0x180001768  mov     [rbp+100h+var_80], rax
0x18000176f  mov     rax, [rbp+100h+arg_B0]
0x180001776  mov     [rbp+100h+var_28], 8
0x180001781  mov     [rbp+100h+var_38], 4
0x18000178c  mov     [rbp+100h+var_48], 4
0x180001797  mov     rdx, [rax]
0x18000179a  mov     [rbp+100h+var_58], 4
0x1800017a5  mov     [rbp+100h+var_68], 4
0x1800017b0  mov     [rbp+100h+var_78], 4
0x1800017bb  test    rdx, rdx
0x1800017be  jz      short loc_1800017CF
0x1800017c0  mov     rax, rcx
0x1800017c3  inc     rax
0x1800017c6  cmp     [rdx+rax], bl
0x1800017c9  jnz     short loc_1800017C3
0x1800017cb  inc     eax
0x1800017cd  jmp     short loc_1800017D5
0x1800017cf  mov     rdx, rdi
0x1800017d2  mov     eax, r8d
0x1800017d5  mov     [rbp+100h+var_88], eax
0x1800017d8  mov     rax, [rbp+100h+arg_A8]
0x1800017df  mov     [rbp+100h+var_90], rdx
0x1800017e3  mov     [rbp+100h+var_84], ebx
0x1800017e6  mov     rdx, [rax]
0x1800017e9  test    rdx, rdx
0x1800017ec  jz      short loc_1800017FD
0x1800017ee  mov     rax, rcx
0x1800017f1  inc     rax
0x1800017f4  cmp     [rdx+rax], bl
0x1800017f7  jnz     short loc_1800017F1
0x1800017f9  inc     eax
0x1800017fb  jmp     short loc_180001803
0x1800017fd  mov     rdx, rdi
0x180001800  mov     eax, r8d
0x180001803  mov     [rbp+100h+var_98], eax
0x180001806  mov     r9d, 2
0x18000180c  mov     rax, [rbp+100h+arg_A0]
0x180001813  mov     [rbp+100h+var_B0], rax
0x180001817  mov     rax, [rbp+100h+arg_98]
0x18000181e  mov     [rbp+100h+var_C0], rax
0x180001822  mov     rax, [rbp+100h+arg_90]
0x180001829  mov     [rbp+100h+var_D0], rax
0x18000182d  mov     rax, [rbp+100h+arg_88]
0x180001834  mov     [rbp+100h+var_E0], rax
0x180001838  mov     rax, [rbp+100h+arg_80]
0x18000183f  mov     [rbp+100h+var_F0], rax
0x180001843  mov     rax, [rbp+100h+arg_78]
0x18000184a  mov     [rbp+100h+var_100], rax
0x18000184e  mov     rax, [rbp+100h+arg_70]
0x180001855  mov     [rbp+100h+var_110], rax
0x180001859  mov     rax, [rbp+100h+arg_68]
0x180001860  mov     [rbp+100h+var_120], rax
0x180001864  mov     rax, [rbp+100h+arg_60]
0x18000186b  mov     [rbp+100h+var_130], rax
0x18000186f  mov     rax, [rbp+100h+arg_58]
0x180001876  mov     [rbp+100h+var_140], rax
0x18000187a  mov     rax, [rbp+100h+arg_50]
0x180001881  mov     [rbp+100h+var_A0], rdx
0x180001885  mov     [rbp+100h+var_94], ebx
0x180001888  mov     [rbp+100h+var_A8], 4
0x180001890  mov     rdx, [rax]
0x180001893  mov     [rbp+100h+var_B8], 4
0x18000189b  mov     [rbp+100h+var_C8], 4
0x1800018a3  mov     [rbp+100h+var_D8], 4
0x1800018ab  mov     [rbp+100h+var_E8], r8
0x1800018af  mov     [rbp+100h+var_F8], r8
0x1800018b3  mov     [rbp+100h+var_108], 4
0x1800018bb  mov     [rbp+100h+var_118], 4
0x1800018c3  mov     [rbp+100h+var_128], 4
0x1800018cb  mov     [rbp+100h+var_138], 4
0x1800018d3  test    rdx, rdx
0x1800018d6  jz      short loc_1800018ED
0x1800018d8  mov     rax, rcx
0x1800018db  inc     rax
0x1800018de  cmp     [rdx+rax*2], bx
0x1800018e2  jnz     short loc_1800018DB
0x1800018e4  lea     eax, ds:2[rax*2]
0x1800018eb  jmp     short loc_1800018F7
0x1800018ed  lea     rdx, Src
0x1800018f4  mov     eax, r9d
0x1800018f7  mov     [rbp+100h+var_148], eax
0x1800018fa  mov     rax, [rbp+100h+arg_48]
0x180001901  mov     [rbp+100h+var_150], rdx
0x180001905  mov     [rbp+100h+var_144], ebx
0x180001908  mov     rdx, [rax]
0x18000190b  test    rdx, rdx
0x18000190e  jz      short loc_18000191F
0x180001910  mov     rax, rcx
0x180001913  inc     rax
0x180001916  cmp     [rdx+rax], bl
0x180001919  jnz     short loc_180001913
0x18000191b  inc     eax
0x18000191d  jmp     short loc_180001925
0x18000191f  mov     rdx, rdi
0x180001922  mov     eax, r8d
0x180001925  mov     [rbp+100h+var_158], eax
0x180001928  mov     rax, [rbp+100h+arg_40]
0x18000192f  mov     [rbp+100h+var_160], rdx
0x180001933  mov     [rbp+100h+var_154], ebx
0x180001936  mov     rdx, [rax]
0x180001939  test    rdx, rdx
0x18000193c  jz      short loc_18000194D
0x18000193e  mov     rax, rcx
0x180001941  inc     rax
0x180001944  cmp     [rdx+rax], bl
0x180001947  jnz     short loc_180001941
0x180001949  inc     eax
0x18000194b  jmp     short loc_180001953
0x18000194d  mov     rdx, rdi
0x180001950  mov     eax, r8d
0x180001953  mov     [rbp+100h+var_168], eax
0x180001956  mov     rax, [rbp+100h+arg_38]
0x18000195d  mov     [rbp+100h+var_170], rdx
0x180001961  mov     [rbp+100h+var_164], ebx
0x180001964  mov     rdx, [rax]
0x180001967  test    rdx, rdx
0x18000196a  jz      short loc_180001981
0x18000196c  mov     rax, rcx
0x18000196f  inc     rax
0x180001972  cmp     [rdx+rax*2], bx
0x180001976  jnz     short loc_18000196F
0x180001978  lea     eax, ds:2[rax*2]
0x18000197f  jmp     short loc_18000198B
0x180001981  lea     rdx, Src
0x180001988  mov     eax, r9d
0x18000198b  mov     [rbp+100h+var_178], eax
0x18000198e  mov     rax, [rbp+100h+arg_30]
0x180001995  mov     [rbp+100h+var_180], rdx
0x180001999  mov     [rbp+100h+var_174], ebx
0x18000199c  mov     rdx, [rax]
0x18000199f  test    rdx, rdx
0x1800019a2  jz      short loc_1800019BA
0x1800019a4  mov     rax, rcx
0x1800019a7  inc     rax
0x1800019aa  cmp     [rdx+rax*2], bx
0x1800019ae  jnz     short loc_1800019A7
0x1800019b0  lea     r9d, ds:2[rax*2]
0x1800019b8  jmp     short loc_1800019C1
0x1800019ba  lea     rdx, Src
0x1800019c1  mov     rax, [rbp+100h+arg_28]
0x1800019c8  mov     [rsp+200h+var_1A0], rax
0x1800019cd  mov     rax, [rbp+100h+arg_20]
0x1800019d4  mov     [rsp+200h+var_190], rdx
0x1800019d9  mov     [rsp+200h+var_188], r9d
0x1800019de  mov     [rsp+200h+var_184], ebx
0x1800019e2  mov     rdx, [rax]
0x1800019e5  mov     [rsp+200h+var_198], 4
0x1800019ee  test    rdx, rdx
0x1800019f1  jz      short loc_180001A01
0x1800019f3  inc     rcx
0x1800019f6  cmp     [rdx+rcx], bl
0x1800019f9  jnz     short loc_1800019F3
0x1800019fb  lea     r8d, [rcx+1]
0x1800019ff  jmp     short loc_180001A04
0x180001a01  mov     rdx, rdi
0x180001a04  lea     rax, [rsp+200h+var_1D0]
0x180001a09  mov     [rsp+200h+var_1B0], rdx
0x180001a0e  mov     [rsp+200h+var_1A8], r8d
0x180001a13  xor     r9d, r9d
0x180001a16  mov     [rsp+200h+var_1D8], rax
0x180001a1b  xor     r8d, r8d
0x180001a1e  mov     rdx, r11
0x180001a21  mov     [rsp+200h+var_1E0], 1Bh
0x180001a29  mov     rcx, r10
0x180001a2c  mov     [rsp+200h+var_1A4], ebx
0x180001a30  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a35  mov     rcx, [rbp+100h+var_20]
0x180001a3c  xor     rcx, rsp; StackCookie
0x180001a3f  call    __security_check_cookie
0x180001a44  mov     rbx, [rsp+200h+arg_10]
0x180001a4c  add     rsp, 1F0h
0x180001a53  pop     rdi
0x180001a54  pop     rsi
0x180001a55  pop     rbp
0x180001a56  retn
```
