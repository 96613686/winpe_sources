# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400015b4`
- end: `0x140001883`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U1@U2@U1@U2@U2@U1@U1@U1@U1@U2@U?$_tlgWrapperByVal@$01@@U1@U1@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333AEBU?$_tlgWrapSz@G@@3434433334AEBU?$_tlgWrapperByVal@$01@@33AEBU?$_tlgWrapperByVal@$07@@6@Z`
- size: `719`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bdf0`

## callees

- `0x1400015b4`
- `0x140009bc0`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        _QWORD *a14,
        _QWORD *a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        _QWORD *a20)
{
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax

  v21 = -1;
  if ( *a20 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a20 + 2 * v22) );
  }
  if ( *a15 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(*a15 + 2 * v23) );
  }
  if ( *a14 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a14 + 2 * v24) );
  }
  if ( *a12 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a12 + 2 * v25) );
  }
  if ( *a10 )
  {
    do
      ++v21;
    while ( *(_WORD *)(*a10 + 2 * v21) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1400015b4  mov     [rsp-8+arg_10], rbx
0x1400015b9  mov     [rsp-8+arg_18], rdi
0x1400015be  push    rbp
0x1400015bf  lea     rbp, [rsp-0B0h]
0x1400015c7  sub     rsp, 1B0h
0x1400015ce  mov     rax, cs:__security_cookie
0x1400015d5  xor     rax, rsp
0x1400015d8  mov     [rbp+0B0h+var_10], rax
0x1400015df  mov     rax, [rbp+0B0h+arg_C0]
0x1400015e6  lea     rdi, qword_1400210F8
0x1400015ed  mov     [rbp+0B0h+var_20], rax
0x1400015f4  xor     r9d, r9d
0x1400015f7  mov     rax, [rbp+0B0h+arg_B8]
0x1400015fe  mov     r11, rdx
0x140001601  mov     [rbp+0B0h+var_30], rax
0x140001608  mov     r10, rcx
0x14000160b  mov     rax, [rbp+0B0h+arg_B0]
0x140001612  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001616  mov     [rbp+0B0h+var_40], rax
0x14000161a  lea     r8d, [r9+2]
0x14000161e  mov     rax, [rbp+0B0h+arg_A8]
0x140001625  mov     [rbp+0B0h+var_50], rax
0x140001629  mov     rax, [rbp+0B0h+arg_A0]
0x140001630  mov     [rbp+0B0h+var_60], rax
0x140001634  mov     rax, [rbp+0B0h+arg_98]
0x14000163b  mov     [rbp+0B0h+var_18], 8
0x140001646  mov     [rbp+0B0h+var_28], 8
0x140001651  mov     [rbp+0B0h+var_38], 4
0x140001659  mov     rdx, [rax]
0x14000165c  mov     [rbp+0B0h+var_48], 4
0x140001664  mov     [rbp+0B0h+var_58], r8
0x140001668  test    rdx, rdx
0x14000166b  jz      short loc_140001683
0x14000166d  mov     rax, rcx
0x140001670  inc     rax
0x140001673  cmp     [rdx+rax*2], r9w
0x140001678  jnz     short loc_140001670
0x14000167a  lea     eax, ds:2[rax*2]
0x140001681  jmp     short loc_140001689
0x140001683  mov     rdx, rdi
0x140001686  mov     eax, r8d
0x140001689  mov     [rbp+0B0h+var_68], eax
0x14000168c  mov     rax, [rbp+0B0h+arg_90]
0x140001693  mov     [rbp+0B0h+var_80], rax
0x140001697  mov     rax, [rbp+0B0h+arg_88]
0x14000169e  mov     [rbp+0B0h+var_90], rax
0x1400016a2  mov     rax, [rbp+0B0h+arg_80]
0x1400016a9  mov     [rbp+0B0h+var_A0], rax
0x1400016ad  mov     rax, [rbp+0B0h+arg_78]
0x1400016b4  mov     [rbp+0B0h+var_B0], rax
0x1400016b8  mov     rax, [rbp+0B0h+arg_70]
0x1400016bf  mov     [rbp+0B0h+var_70], rdx
0x1400016c3  mov     [rbp+0B0h+var_64], r9d
0x1400016c7  mov     [rbp+0B0h+var_78], 4
0x1400016cf  mov     rdx, [rax]
0x1400016d2  mov     [rbp+0B0h+var_88], 4
0x1400016da  mov     [rbp+0B0h+var_98], 4
0x1400016e2  mov     [rbp+0B0h+var_A8], 4
0x1400016ea  test    rdx, rdx
0x1400016ed  jz      short loc_140001705
0x1400016ef  mov     rax, rcx
0x1400016f2  inc     rax
0x1400016f5  cmp     [rdx+rax*2], r9w
0x1400016fa  jnz     short loc_1400016F2
0x1400016fc  lea     eax, ds:2[rax*2]
0x140001703  jmp     short loc_14000170B
0x140001705  mov     rdx, rdi
0x140001708  mov     eax, r8d
0x14000170b  mov     [rbp+0B0h+var_B8], eax
0x14000170e  mov     rax, [rbp+0B0h+arg_68]
0x140001715  mov     [rbp+0B0h+var_C0], rdx
0x140001719  mov     [rbp+0B0h+var_B4], r9d
0x14000171d  mov     rdx, [rax]
0x140001720  test    rdx, rdx
0x140001723  jz      short loc_14000173B
0x140001725  mov     rax, rcx
0x140001728  inc     rax
0x14000172b  cmp     [rdx+rax*2], r9w
0x140001730  jnz     short loc_140001728
0x140001732  lea     eax, ds:2[rax*2]
0x140001739  jmp     short loc_140001741
0x14000173b  mov     rdx, rdi
0x14000173e  mov     eax, r8d
0x140001741  mov     [rbp+0B0h+var_C8], eax
0x140001744  mov     rax, [rbp+0B0h+arg_60]
0x14000174b  mov     [rbp+0B0h+var_E0], rax
0x14000174f  mov     rax, [rbp+0B0h+arg_58]
0x140001756  mov     [rbp+0B0h+var_D0], rdx
0x14000175a  mov     [rbp+0B0h+var_C4], r9d
0x14000175e  mov     [rbp+0B0h+var_D8], 4
0x140001766  mov     rdx, [rax]
0x140001769  test    rdx, rdx
0x14000176c  jz      short loc_140001784
0x14000176e  mov     rax, rcx
0x140001771  inc     rax
0x140001774  cmp     [rdx+rax*2], r9w
0x140001779  jnz     short loc_140001771
0x14000177b  lea     eax, ds:2[rax*2]
0x140001782  jmp     short loc_14000178A
0x140001784  mov     rdx, rdi
0x140001787  mov     eax, r8d
0x14000178a  mov     [rbp+0B0h+var_E8], eax
0x14000178d  mov     rax, [rbp+0B0h+arg_50]
0x140001794  mov     [rbp+0B0h+var_100], rax
0x140001798  mov     rax, [rbp+0B0h+arg_48]
0x14000179f  mov     [rbp+0B0h+var_F0], rdx
0x1400017a3  mov     [rbp+0B0h+var_E4], r9d
0x1400017a7  mov     [rbp+0B0h+var_F8], 4
0x1400017af  mov     rdx, [rax]
0x1400017b2  test    rdx, rdx
0x1400017b5  jz      short loc_1400017CB
0x1400017b7  inc     rcx
0x1400017ba  cmp     [rdx+rcx*2], r9w
0x1400017bf  jnz     short loc_1400017B7
0x1400017c1  lea     r8d, ds:2[rcx*2]
0x1400017c9  jmp     short loc_1400017CE
0x1400017cb  mov     rdx, rdi
0x1400017ce  mov     rax, [rbp+0B0h+arg_40]
0x1400017d5  mov     rcx, r10
0x1400017d8  mov     [rbp+0B0h+var_120], rax
0x1400017dc  mov     rax, [rbp+0B0h+arg_38]
0x1400017e3  mov     [rbp+0B0h+var_130], rax
0x1400017e7  mov     rax, [rbp+0B0h+arg_30]
0x1400017ee  mov     [rsp+1B0h+var_140], rax
0x1400017f3  mov     rax, [rbp+0B0h+arg_28]
0x1400017fa  mov     [rsp+1B0h+var_150], rax
0x1400017ff  mov     rax, [rbp+0B0h+arg_20]
0x140001806  mov     [rsp+1B0h+var_160], rax
0x14000180b  lea     rax, [rsp+1B0h+var_180]
0x140001810  mov     [rbp+0B0h+var_110], rdx
0x140001814  mov     rdx, r11
0x140001817  mov     [rbp+0B0h+var_108], r8d
0x14000181b  xor     r8d, r8d
0x14000181e  mov     [rsp+1B0h+var_188], rax
0x140001823  mov     [rsp+1B0h+var_190], 17h
0x14000182b  mov     [rbp+0B0h+var_104], r9d
0x14000182f  mov     [rbp+0B0h+var_118], 4
0x140001837  mov     [rbp+0B0h+var_128], 4
0x14000183f  mov     [rsp+1B0h+var_138], 4
0x140001848  mov     [rsp+1B0h+var_148], 4
0x140001851  mov     [rsp+1B0h+var_158], 4
0x14000185a  call    _tlgWriteTransfer_EventWriteTransfer
0x14000185f  mov     rcx, [rbp+0B0h+var_10]
0x140001866  xor     rcx, rsp; StackCookie
0x140001869  call    __security_check_cookie
0x14000186e  lea     r11, [rsp+1B0h+var_s0]
0x140001876  mov     rbx, [r11+20h]
0x14000187a  mov     rdi, [r11+28h]
0x14000187e  mov     rsp, r11
0x140001881  pop     rbp
0x140001882  retn
```
