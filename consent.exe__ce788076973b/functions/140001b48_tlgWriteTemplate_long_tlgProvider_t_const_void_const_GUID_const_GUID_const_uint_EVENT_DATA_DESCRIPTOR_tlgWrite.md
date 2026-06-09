# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001b48`
- end: `0x140001e3b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U?$_tlgWrapSz@G@@U3@U4@U3@U4@U4@U3@U3@U3@U3@U4@U?$_tlgWrapperByVal@$01@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@5555AEBU?$_tlgWrapSz@G@@5656655556AEBU?$_tlgWrapperByVal@$01@@53@Z`
- size: `755`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bdf0`
- `0x14001c528`

## callees

- `0x140001b48`
- `0x140009bc0`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        _QWORD *a22)
{
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax

  v23 = -1;
  if ( *a22 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a22 + 2 * v24) );
  }
  if ( *a17 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a17 + 2 * v25) );
  }
  if ( *a16 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(*a16 + 2 * v26) );
  }
  if ( *a14 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a14 + 2 * v27) );
  }
  if ( *a12 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)(*a12 + 2 * v28) );
  }
  if ( *a6 )
  {
    do
      ++v23;
    while ( *(_BYTE *)(*a6 + v23) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x140001b48  mov     [rsp-8+arg_10], rbx
0x140001b4d  mov     [rsp-8+arg_18], rdi
0x140001b52  push    rbp
0x140001b53  lea     rbp, [rsp-0B0h]
0x140001b5b  sub     rsp, 1B0h
0x140001b62  mov     rax, cs:__security_cookie
0x140001b69  xor     rax, rsp
0x140001b6c  mov     [rbp+0B0h+var_10], rax
0x140001b73  mov     rax, [rbp+0B0h+arg_C0]
0x140001b7a  lea     rdi, qword_1400210F8
0x140001b81  mov     [rbp+0B0h+var_20], rax
0x140001b88  xor     r9d, r9d
0x140001b8b  mov     rax, [rbp+0B0h+arg_B8]
0x140001b92  mov     r11, rdx
0x140001b95  mov     [rbp+0B0h+var_30], rax
0x140001b9c  mov     r10, rcx
0x140001b9f  mov     rax, [rbp+0B0h+arg_B0]
0x140001ba6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001baa  mov     [rbp+0B0h+var_40], rax
0x140001bae  lea     r8d, [r9+2]
0x140001bb2  mov     rax, [rbp+0B0h+arg_A8]
0x140001bb9  mov     [rbp+0B0h+var_18], 8
0x140001bc4  mov     [rbp+0B0h+var_28], 4
0x140001bcf  mov     [rbp+0B0h+var_38], r8
0x140001bd3  mov     rdx, [rax]
0x140001bd6  test    rdx, rdx
0x140001bd9  jz      short loc_140001BF1
0x140001bdb  mov     rax, rcx
0x140001bde  inc     rax
0x140001be1  cmp     [rdx+rax*2], r9w
0x140001be6  jnz     short loc_140001BDE
0x140001be8  lea     eax, ds:2[rax*2]
0x140001bef  jmp     short loc_140001BF7
0x140001bf1  mov     rdx, rdi
0x140001bf4  mov     eax, r8d
0x140001bf7  mov     [rbp+0B0h+var_48], eax
0x140001bfa  mov     rax, [rbp+0B0h+arg_A0]
0x140001c01  mov     [rbp+0B0h+var_60], rax
0x140001c05  mov     rax, [rbp+0B0h+arg_98]
0x140001c0c  mov     [rbp+0B0h+var_70], rax
0x140001c10  mov     rax, [rbp+0B0h+arg_90]
0x140001c17  mov     [rbp+0B0h+var_80], rax
0x140001c1b  mov     rax, [rbp+0B0h+arg_88]
0x140001c22  mov     [rbp+0B0h+var_90], rax
0x140001c26  mov     rax, [rbp+0B0h+arg_80]
0x140001c2d  mov     [rbp+0B0h+var_50], rdx
0x140001c31  mov     [rbp+0B0h+var_44], r9d
0x140001c35  mov     [rbp+0B0h+var_58], 4
0x140001c3d  mov     rdx, [rax]
0x140001c40  mov     [rbp+0B0h+var_68], 4
0x140001c48  mov     [rbp+0B0h+var_78], 4
0x140001c50  mov     [rbp+0B0h+var_88], 4
0x140001c58  test    rdx, rdx
0x140001c5b  jz      short loc_140001C73
0x140001c5d  mov     rax, rcx
0x140001c60  inc     rax
0x140001c63  cmp     [rdx+rax*2], r9w
0x140001c68  jnz     short loc_140001C60
0x140001c6a  lea     eax, ds:2[rax*2]
0x140001c71  jmp     short loc_140001C79
0x140001c73  mov     rdx, rdi
0x140001c76  mov     eax, r8d
0x140001c79  mov     [rbp+0B0h+var_98], eax
0x140001c7c  mov     rax, [rbp+0B0h+arg_78]
0x140001c83  mov     [rbp+0B0h+var_A0], rdx
0x140001c87  mov     [rbp+0B0h+var_94], r9d
0x140001c8b  mov     rdx, [rax]
0x140001c8e  test    rdx, rdx
0x140001c91  jz      short loc_140001CA9
0x140001c93  mov     rax, rcx
0x140001c96  inc     rax
0x140001c99  cmp     [rdx+rax*2], r9w
0x140001c9e  jnz     short loc_140001C96
0x140001ca0  lea     eax, ds:2[rax*2]
0x140001ca7  jmp     short loc_140001CAF
0x140001ca9  mov     rdx, rdi
0x140001cac  mov     eax, r8d
0x140001caf  mov     [rbp+0B0h+var_A8], eax
0x140001cb2  mov     rax, [rbp+0B0h+arg_70]
0x140001cb9  mov     [rbp+0B0h+var_C0], rax
0x140001cbd  mov     rax, [rbp+0B0h+arg_68]
0x140001cc4  mov     [rbp+0B0h+var_B0], rdx
0x140001cc8  mov     [rbp+0B0h+var_A4], r9d
0x140001ccc  mov     [rbp+0B0h+var_B8], 4
0x140001cd4  mov     rdx, [rax]
0x140001cd7  test    rdx, rdx
0x140001cda  jz      short loc_140001CF2
0x140001cdc  mov     rax, rcx
0x140001cdf  inc     rax
0x140001ce2  cmp     [rdx+rax*2], r9w
0x140001ce7  jnz     short loc_140001CDF
0x140001ce9  lea     eax, ds:2[rax*2]
0x140001cf0  jmp     short loc_140001CF8
0x140001cf2  mov     rdx, rdi
0x140001cf5  mov     eax, r8d
0x140001cf8  mov     [rbp+0B0h+var_C8], eax
0x140001cfb  mov     rax, [rbp+0B0h+arg_60]
0x140001d02  mov     [rbp+0B0h+var_E0], rax
0x140001d06  mov     rax, [rbp+0B0h+arg_58]
0x140001d0d  mov     [rbp+0B0h+var_D0], rdx
0x140001d11  mov     [rbp+0B0h+var_C4], r9d
0x140001d15  mov     [rbp+0B0h+var_D8], 4
0x140001d1d  mov     rdx, [rax]
0x140001d20  test    rdx, rdx
0x140001d23  jz      short loc_140001D3C
0x140001d25  mov     rax, rcx
0x140001d28  inc     rax
0x140001d2b  cmp     [rdx+rax*2], r9w
0x140001d30  jnz     short loc_140001D28
0x140001d32  lea     r8d, ds:2[rax*2]
0x140001d3a  jmp     short loc_140001D3F
0x140001d3c  mov     rdx, rdi
0x140001d3f  mov     rax, [rbp+0B0h+arg_50]
0x140001d46  mov     [rbp+0B0h+var_100], rax
0x140001d4a  mov     rax, [rbp+0B0h+arg_48]
0x140001d51  mov     [rbp+0B0h+var_110], rax
0x140001d55  mov     rax, [rbp+0B0h+arg_40]
0x140001d5c  mov     [rbp+0B0h+var_120], rax
0x140001d60  mov     rax, [rbp+0B0h+arg_38]
0x140001d67  mov     [rbp+0B0h+var_130], rax
0x140001d6b  mov     rax, [rbp+0B0h+arg_30]
0x140001d72  mov     [rsp+1B0h+var_140], rax
0x140001d77  mov     rax, [rbp+0B0h+arg_28]
0x140001d7e  mov     [rbp+0B0h+var_F0], rdx
0x140001d82  mov     [rbp+0B0h+var_E8], r8d
0x140001d86  mov     [rbp+0B0h+var_E4], r9d
0x140001d8a  mov     rdx, [rax]
0x140001d8d  mov     [rbp+0B0h+var_F8], 4
0x140001d95  mov     [rbp+0B0h+var_108], 4
0x140001d9d  mov     [rbp+0B0h+var_118], 4
0x140001da5  mov     [rbp+0B0h+var_128], 4
0x140001dad  mov     [rsp+1B0h+var_138], 4
0x140001db6  test    rdx, rdx
0x140001db9  jz      short loc_140001DC8
0x140001dbb  inc     rcx
0x140001dbe  cmp     [rdx+rcx], r9b
0x140001dc2  jnz     short loc_140001DBB
0x140001dc4  inc     ecx
0x140001dc6  jmp     short loc_140001DD4
0x140001dc8  lea     rdx, qword_140021870
0x140001dcf  mov     ecx, 1
0x140001dd4  mov     rax, [rbp+0B0h+arg_20]
0x140001ddb  xor     r8d, r8d
0x140001dde  mov     [rsp+1B0h+var_160], rax
0x140001de3  lea     rax, [rsp+1B0h+var_180]
0x140001de8  mov     [rsp+1B0h+var_150], rdx
0x140001ded  mov     rdx, r11
0x140001df0  mov     [rsp+1B0h+var_148], ecx
0x140001df4  mov     rcx, r10
0x140001df7  mov     [rsp+1B0h+var_188], rax
0x140001dfc  mov     [rsp+1B0h+var_190], 17h
0x140001e04  mov     [rsp+1B0h+var_144], r9d
0x140001e09  mov     [rsp+1B0h+var_158], 8
0x140001e12  call    _tlgWriteTransfer_EventWriteTransfer
0x140001e17  mov     rcx, [rbp+0B0h+var_10]
0x140001e1e  xor     rcx, rsp; StackCookie
0x140001e21  call    __security_check_cookie
0x140001e26  lea     r11, [rsp+1B0h+var_s0]
0x140001e2e  mov     rbx, [r11+20h]
0x140001e32  mov     rdi, [r11+28h]
0x140001e36  mov     rsp, r11
0x140001e39  pop     rbp
0x140001e3a  retn
```
