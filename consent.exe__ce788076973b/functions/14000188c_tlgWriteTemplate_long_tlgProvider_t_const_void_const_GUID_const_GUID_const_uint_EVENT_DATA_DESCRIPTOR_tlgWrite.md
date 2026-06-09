# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x14000188c`
- end: `0x140001b42`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapSz@G@@U1@U2@U1@U2@U2@U1@U1@U1@U1@U2@U?$_tlgWrapperByVal@$01@@U1@U1@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapSz@G@@3434433334AEBU?$_tlgWrapperByVal@$01@@33AEBU?$_tlgWrapperByVal@$07@@6@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bdf0`

## callees

- `0x14000188c`
- `0x140009bc0`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        _QWORD *a11,
        __int64 a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        _QWORD *a19)
{
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax

  v20 = -1;
  if ( *a19 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(*a19 + 2 * v21) );
  }
  if ( *a14 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a14 + 2 * v22) );
  }
  if ( *a13 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(*a13 + 2 * v23) );
  }
  if ( *a11 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a11 + 2 * v24) );
  }
  if ( *a9 )
  {
    do
      ++v20;
    while ( *(_WORD *)(*a9 + 2 * v20) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x14000188c  mov     [rsp-8+arg_10], rbx
0x140001891  mov     [rsp-8+arg_18], rdi
0x140001896  push    rbp
0x140001897  lea     rbp, [rsp-0A0h]
0x14000189f  sub     rsp, 1A0h
0x1400018a6  mov     rax, cs:__security_cookie
0x1400018ad  xor     rax, rsp
0x1400018b0  mov     [rbp+0A0h+var_10], rax
0x1400018b7  mov     rax, [rbp+0A0h+arg_B8]
0x1400018be  lea     rdi, qword_1400210F8
0x1400018c5  mov     [rbp+0A0h+var_20], rax
0x1400018cc  xor     r9d, r9d
0x1400018cf  mov     rax, [rbp+0A0h+arg_B0]
0x1400018d6  mov     r11, rdx
0x1400018d9  mov     [rbp+0A0h+var_30], rax
0x1400018dd  mov     r10, rcx
0x1400018e0  mov     rax, [rbp+0A0h+arg_A8]
0x1400018e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400018eb  mov     [rbp+0A0h+var_40], rax
0x1400018ef  lea     r8d, [r9+2]
0x1400018f3  mov     rax, [rbp+0A0h+arg_A0]
0x1400018fa  mov     [rbp+0A0h+var_50], rax
0x1400018fe  mov     rax, [rbp+0A0h+arg_98]
0x140001905  mov     [rbp+0A0h+var_60], rax
0x140001909  mov     rax, [rbp+0A0h+arg_90]
0x140001910  mov     [rbp+0A0h+var_18], 8
0x14000191b  mov     [rbp+0A0h+var_28], 8
0x140001923  mov     [rbp+0A0h+var_38], 4
0x14000192b  mov     rdx, [rax]
0x14000192e  mov     [rbp+0A0h+var_48], 4
0x140001936  mov     [rbp+0A0h+var_58], r8
0x14000193a  test    rdx, rdx
0x14000193d  jz      short loc_140001955
0x14000193f  mov     rax, rcx
0x140001942  inc     rax
0x140001945  cmp     [rdx+rax*2], r9w
0x14000194a  jnz     short loc_140001942
0x14000194c  lea     eax, ds:2[rax*2]
0x140001953  jmp     short loc_14000195B
0x140001955  mov     rdx, rdi
0x140001958  mov     eax, r8d
0x14000195b  mov     [rbp+0A0h+var_68], eax
0x14000195e  mov     rax, [rbp+0A0h+arg_88]
0x140001965  mov     [rbp+0A0h+var_80], rax
0x140001969  mov     rax, [rbp+0A0h+arg_80]
0x140001970  mov     [rbp+0A0h+var_90], rax
0x140001974  mov     rax, [rbp+0A0h+arg_78]
0x14000197b  mov     [rbp+0A0h+var_A0], rax
0x14000197f  mov     rax, [rbp+0A0h+arg_70]
0x140001986  mov     [rbp+0A0h+var_B0], rax
0x14000198a  mov     rax, [rbp+0A0h+arg_68]
0x140001991  mov     [rbp+0A0h+var_70], rdx
0x140001995  mov     [rbp+0A0h+var_64], r9d
0x140001999  mov     [rbp+0A0h+var_78], 4
0x1400019a1  mov     rdx, [rax]
0x1400019a4  mov     [rbp+0A0h+var_88], 4
0x1400019ac  mov     [rbp+0A0h+var_98], 4
0x1400019b4  mov     [rbp+0A0h+var_A8], 4
0x1400019bc  test    rdx, rdx
0x1400019bf  jz      short loc_1400019D7
0x1400019c1  mov     rax, rcx
0x1400019c4  inc     rax
0x1400019c7  cmp     [rdx+rax*2], r9w
0x1400019cc  jnz     short loc_1400019C4
0x1400019ce  lea     eax, ds:2[rax*2]
0x1400019d5  jmp     short loc_1400019DD
0x1400019d7  mov     rdx, rdi
0x1400019da  mov     eax, r8d
0x1400019dd  mov     [rbp+0A0h+var_B8], eax
0x1400019e0  mov     rax, [rbp+0A0h+arg_60]
0x1400019e7  mov     [rbp+0A0h+var_C0], rdx
0x1400019eb  mov     [rbp+0A0h+var_B4], r9d
0x1400019ef  mov     rdx, [rax]
0x1400019f2  test    rdx, rdx
0x1400019f5  jz      short loc_140001A0D
0x1400019f7  mov     rax, rcx
0x1400019fa  inc     rax
0x1400019fd  cmp     [rdx+rax*2], r9w
0x140001a02  jnz     short loc_1400019FA
0x140001a04  lea     eax, ds:2[rax*2]
0x140001a0b  jmp     short loc_140001A13
0x140001a0d  mov     rdx, rdi
0x140001a10  mov     eax, r8d
0x140001a13  mov     [rbp+0A0h+var_C8], eax
0x140001a16  mov     rax, [rbp+0A0h+arg_58]
0x140001a1d  mov     [rbp+0A0h+var_E0], rax
0x140001a21  mov     rax, [rbp+0A0h+arg_50]
0x140001a28  mov     [rbp+0A0h+var_D0], rdx
0x140001a2c  mov     [rbp+0A0h+var_C4], r9d
0x140001a30  mov     [rbp+0A0h+var_D8], 4
0x140001a38  mov     rdx, [rax]
0x140001a3b  test    rdx, rdx
0x140001a3e  jz      short loc_140001A56
0x140001a40  mov     rax, rcx
0x140001a43  inc     rax
0x140001a46  cmp     [rdx+rax*2], r9w
0x140001a4b  jnz     short loc_140001A43
0x140001a4d  lea     eax, ds:2[rax*2]
0x140001a54  jmp     short loc_140001A5C
0x140001a56  mov     rdx, rdi
0x140001a59  mov     eax, r8d
0x140001a5c  mov     [rbp+0A0h+var_E8], eax
0x140001a5f  mov     rax, [rbp+0A0h+arg_48]
0x140001a66  mov     [rbp+0A0h+var_100], rax
0x140001a6a  mov     rax, [rbp+0A0h+arg_40]
0x140001a71  mov     [rbp+0A0h+var_F0], rdx
0x140001a75  mov     [rbp+0A0h+var_E4], r9d
0x140001a79  mov     [rbp+0A0h+var_F8], 4
0x140001a81  mov     rdx, [rax]
0x140001a84  test    rdx, rdx
0x140001a87  jz      short loc_140001A9D
0x140001a89  inc     rcx
0x140001a8c  cmp     [rdx+rcx*2], r9w
0x140001a91  jnz     short loc_140001A89
0x140001a93  lea     r8d, ds:2[rcx*2]
0x140001a9b  jmp     short loc_140001AA0
0x140001a9d  mov     rdx, rdi
0x140001aa0  mov     rax, [rbp+0A0h+arg_38]
0x140001aa7  mov     rcx, r10
0x140001aaa  mov     [rbp+0A0h+var_120], rax
0x140001aae  mov     rax, [rbp+0A0h+arg_30]
0x140001ab5  mov     [rsp+1A0h+var_130], rax
0x140001aba  mov     rax, [rbp+0A0h+arg_28]
0x140001ac1  mov     [rsp+1A0h+var_140], rax
0x140001ac6  mov     rax, [rbp+0A0h+arg_20]
0x140001acd  mov     [rsp+1A0h+var_150], rax
0x140001ad2  lea     rax, [rsp+1A0h+var_170]
0x140001ad7  mov     [rbp+0A0h+var_110], rdx
0x140001adb  mov     rdx, r11
0x140001ade  mov     [rbp+0A0h+var_108], r8d
0x140001ae2  xor     r8d, r8d
0x140001ae5  mov     [rsp+1A0h+var_178], rax
0x140001aea  mov     [rsp+1A0h+var_180], 16h
0x140001af2  mov     [rbp+0A0h+var_104], r9d
0x140001af6  mov     [rbp+0A0h+var_118], 4
0x140001afe  mov     [rsp+1A0h+var_128], 4
0x140001b07  mov     [rsp+1A0h+var_138], 4
0x140001b10  mov     [rsp+1A0h+var_148], 4
0x140001b19  call    _tlgWriteTransfer_EventWriteTransfer
0x140001b1e  mov     rcx, [rbp+0A0h+var_10]
0x140001b25  xor     rcx, rsp; StackCookie
0x140001b28  call    __security_check_cookie
0x140001b2d  lea     r11, [rsp+1A0h+var_s0]
0x140001b35  mov     rbx, [r11+20h]
0x140001b39  mov     rdi, [r11+28h]
0x140001b3d  mov     rsp, r11
0x140001b40  pop     rbp
0x140001b41  retn
```
