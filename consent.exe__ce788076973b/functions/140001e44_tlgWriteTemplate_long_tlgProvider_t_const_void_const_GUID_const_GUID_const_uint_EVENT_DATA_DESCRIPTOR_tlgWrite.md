# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001e44`
- end: `0x14000211e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U?$_tlgWrapSz@G@@U3@U4@U3@U4@U4@U3@U3@U3@U3@U4@U?$_tlgWrapperByVal@$01@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@555AEBU?$_tlgWrapSz@G@@5656655556AEBU?$_tlgWrapperByVal@$01@@53@Z`
- size: `730`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bdf0`
- `0x14001c528`

## callees

- `0x140001e44`
- `0x140009bc0`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
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
        _QWORD *a11,
        __int64 a12,
        _QWORD *a13,
        __int64 a14,
        _QWORD *a15,
        _QWORD *a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        _QWORD *a21)
{
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax

  v22 = -1;
  if ( *a21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(*a21 + 2 * v23) );
  }
  if ( *a16 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a16 + 2 * v24) );
  }
  if ( *a15 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a15 + 2 * v25) );
  }
  if ( *a13 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(*a13 + 2 * v26) );
  }
  if ( *a11 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a11 + 2 * v27) );
  }
  if ( *a6 )
  {
    do
      ++v22;
    while ( *(_BYTE *)(*a6 + v22) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x140001e44  mov     [rsp-8+arg_10], rbx
0x140001e49  mov     [rsp-8+arg_18], rdi
0x140001e4e  push    rbp
0x140001e4f  lea     rbp, [rsp-0A0h]
0x140001e57  sub     rsp, 1A0h
0x140001e5e  mov     rax, cs:__security_cookie
0x140001e65  xor     rax, rsp
0x140001e68  mov     [rbp+0A0h+var_10], rax
0x140001e6f  mov     rax, [rbp+0A0h+arg_B8]
0x140001e76  lea     rdi, qword_1400210F8
0x140001e7d  mov     [rbp+0A0h+var_20], rax
0x140001e84  xor     r9d, r9d
0x140001e87  mov     rax, [rbp+0A0h+arg_B0]
0x140001e8e  mov     r11, rdx
0x140001e91  mov     [rbp+0A0h+var_30], rax
0x140001e95  mov     r10, rcx
0x140001e98  mov     rax, [rbp+0A0h+arg_A8]
0x140001e9f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001ea3  mov     [rbp+0A0h+var_40], rax
0x140001ea7  lea     r8d, [r9+2]
0x140001eab  mov     rax, [rbp+0A0h+arg_A0]
0x140001eb2  mov     [rbp+0A0h+var_18], 8
0x140001ebd  mov     [rbp+0A0h+var_28], 4
0x140001ec5  mov     [rbp+0A0h+var_38], r8
0x140001ec9  mov     rdx, [rax]
0x140001ecc  test    rdx, rdx
0x140001ecf  jz      short loc_140001EE7
0x140001ed1  mov     rax, rcx
0x140001ed4  inc     rax
0x140001ed7  cmp     [rdx+rax*2], r9w
0x140001edc  jnz     short loc_140001ED4
0x140001ede  lea     eax, ds:2[rax*2]
0x140001ee5  jmp     short loc_140001EED
0x140001ee7  mov     rdx, rdi
0x140001eea  mov     eax, r8d
0x140001eed  mov     [rbp+0A0h+var_48], eax
0x140001ef0  mov     rax, [rbp+0A0h+arg_98]
0x140001ef7  mov     [rbp+0A0h+var_60], rax
0x140001efb  mov     rax, [rbp+0A0h+arg_90]
0x140001f02  mov     [rbp+0A0h+var_70], rax
0x140001f06  mov     rax, [rbp+0A0h+arg_88]
0x140001f0d  mov     [rbp+0A0h+var_80], rax
0x140001f11  mov     rax, [rbp+0A0h+arg_80]
0x140001f18  mov     [rbp+0A0h+var_90], rax
0x140001f1c  mov     rax, [rbp+0A0h+arg_78]
0x140001f23  mov     [rbp+0A0h+var_50], rdx
0x140001f27  mov     [rbp+0A0h+var_44], r9d
0x140001f2b  mov     [rbp+0A0h+var_58], 4
0x140001f33  mov     rdx, [rax]
0x140001f36  mov     [rbp+0A0h+var_68], 4
0x140001f3e  mov     [rbp+0A0h+var_78], 4
0x140001f46  mov     [rbp+0A0h+var_88], 4
0x140001f4e  test    rdx, rdx
0x140001f51  jz      short loc_140001F69
0x140001f53  mov     rax, rcx
0x140001f56  inc     rax
0x140001f59  cmp     [rdx+rax*2], r9w
0x140001f5e  jnz     short loc_140001F56
0x140001f60  lea     eax, ds:2[rax*2]
0x140001f67  jmp     short loc_140001F6F
0x140001f69  mov     rdx, rdi
0x140001f6c  mov     eax, r8d
0x140001f6f  mov     [rbp+0A0h+var_98], eax
0x140001f72  mov     rax, [rbp+0A0h+arg_70]
0x140001f79  mov     [rbp+0A0h+var_A0], rdx
0x140001f7d  mov     [rbp+0A0h+var_94], r9d
0x140001f81  mov     rdx, [rax]
0x140001f84  test    rdx, rdx
0x140001f87  jz      short loc_140001F9F
0x140001f89  mov     rax, rcx
0x140001f8c  inc     rax
0x140001f8f  cmp     [rdx+rax*2], r9w
0x140001f94  jnz     short loc_140001F8C
0x140001f96  lea     eax, ds:2[rax*2]
0x140001f9d  jmp     short loc_140001FA5
0x140001f9f  mov     rdx, rdi
0x140001fa2  mov     eax, r8d
0x140001fa5  mov     [rbp+0A0h+var_A8], eax
0x140001fa8  mov     rax, [rbp+0A0h+arg_68]
0x140001faf  mov     [rbp+0A0h+var_C0], rax
0x140001fb3  mov     rax, [rbp+0A0h+arg_60]
0x140001fba  mov     [rbp+0A0h+var_B0], rdx
0x140001fbe  mov     [rbp+0A0h+var_A4], r9d
0x140001fc2  mov     [rbp+0A0h+var_B8], 4
0x140001fca  mov     rdx, [rax]
0x140001fcd  test    rdx, rdx
0x140001fd0  jz      short loc_140001FE8
0x140001fd2  mov     rax, rcx
0x140001fd5  inc     rax
0x140001fd8  cmp     [rdx+rax*2], r9w
0x140001fdd  jnz     short loc_140001FD5
0x140001fdf  lea     eax, ds:2[rax*2]
0x140001fe6  jmp     short loc_140001FEE
0x140001fe8  mov     rdx, rdi
0x140001feb  mov     eax, r8d
0x140001fee  mov     [rbp+0A0h+var_C8], eax
0x140001ff1  mov     rax, [rbp+0A0h+arg_58]
0x140001ff8  mov     [rbp+0A0h+var_E0], rax
0x140001ffc  mov     rax, [rbp+0A0h+arg_50]
0x140002003  mov     [rbp+0A0h+var_D0], rdx
0x140002007  mov     [rbp+0A0h+var_C4], r9d
0x14000200b  mov     [rbp+0A0h+var_D8], 4
0x140002013  mov     rdx, [rax]
0x140002016  test    rdx, rdx
0x140002019  jz      short loc_140002032
0x14000201b  mov     rax, rcx
0x14000201e  inc     rax
0x140002021  cmp     [rdx+rax*2], r9w
0x140002026  jnz     short loc_14000201E
0x140002028  lea     r8d, ds:2[rax*2]
0x140002030  jmp     short loc_140002035
0x140002032  mov     rdx, rdi
0x140002035  mov     rax, [rbp+0A0h+arg_48]
0x14000203c  mov     [rbp+0A0h+var_100], rax
0x140002040  mov     rax, [rbp+0A0h+arg_40]
0x140002047  mov     [rbp+0A0h+var_110], rax
0x14000204b  mov     rax, [rbp+0A0h+arg_38]
0x140002052  mov     [rbp+0A0h+var_120], rax
0x140002056  mov     rax, [rbp+0A0h+arg_30]
0x14000205d  mov     [rsp+1A0h+var_130], rax
0x140002062  mov     rax, [rbp+0A0h+arg_28]
0x140002069  mov     [rbp+0A0h+var_F0], rdx
0x14000206d  mov     [rbp+0A0h+var_E8], r8d
0x140002071  mov     [rbp+0A0h+var_E4], r9d
0x140002075  mov     rdx, [rax]
0x140002078  mov     [rbp+0A0h+var_F8], 4
0x140002080  mov     [rbp+0A0h+var_108], 4
0x140002088  mov     [rbp+0A0h+var_118], 4
0x140002090  mov     [rsp+1A0h+var_128], 4
0x140002099  test    rdx, rdx
0x14000209c  jz      short loc_1400020AB
0x14000209e  inc     rcx
0x1400020a1  cmp     [rdx+rcx], r9b
0x1400020a5  jnz     short loc_14000209E
0x1400020a7  inc     ecx
0x1400020a9  jmp     short loc_1400020B7
0x1400020ab  lea     rdx, qword_140021870
0x1400020b2  mov     ecx, 1
0x1400020b7  mov     rax, [rbp+0A0h+arg_20]
0x1400020be  xor     r8d, r8d
0x1400020c1  mov     [rsp+1A0h+var_150], rax
0x1400020c6  lea     rax, [rsp+1A0h+var_170]
0x1400020cb  mov     [rsp+1A0h+var_140], rdx
0x1400020d0  mov     rdx, r11
0x1400020d3  mov     [rsp+1A0h+var_138], ecx
0x1400020d7  mov     rcx, r10
0x1400020da  mov     [rsp+1A0h+var_178], rax
0x1400020df  mov     [rsp+1A0h+var_180], 16h
0x1400020e7  mov     [rsp+1A0h+var_134], r9d
0x1400020ec  mov     [rsp+1A0h+var_148], 8
0x1400020f5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400020fa  mov     rcx, [rbp+0A0h+var_10]
0x140002101  xor     rcx, rsp; StackCookie
0x140002104  call    __security_check_cookie
0x140002109  lea     r11, [rsp+1A0h+var_s0]
0x140002111  mov     rbx, [r11+20h]
0x140002115  mov     rdi, [r11+28h]
0x140002119  mov     rsp, r11
0x14000211c  pop     rbp
0x14000211d  retn
```
