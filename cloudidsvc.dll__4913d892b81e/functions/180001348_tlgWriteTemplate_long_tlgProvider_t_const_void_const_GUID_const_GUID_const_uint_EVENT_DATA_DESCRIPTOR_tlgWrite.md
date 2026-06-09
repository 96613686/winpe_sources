# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001348`
- end: `0x180001436`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ed90`

## callees

- `0x1800012a8`
- `0x180001348`
- `0x180001a50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8)
{
  __int64 v8; // rcx
  __int64 v9; // rax

  v8 = -1;
  if ( *a8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*a8 + 2 * v9) );
  }
  if ( *a7 )
  {
    do
      ++v8;
    while ( *(_WORD *)(*a7 + 2 * v8) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180019048, a2, 0);
}

```

## disassembly

```asm
0x180001348  push    rbp
0x18000134a  lea     rbp, [rsp-37h]
0x18000134f  sub     rsp, 0A0h
0x180001356  mov     rax, cs:__security_cookie
0x18000135d  xor     rax, rsp
0x180001360  mov     [rbp+37h+var_10], rax
0x180001364  mov     rax, [rbp+37h+arg_38]
0x180001368  mov     r10, rdx
0x18000136b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000136f  xor     r9d, r9d
0x180001372  mov     r8d, 2
0x180001378  mov     rdx, [rax]
0x18000137b  test    rdx, rdx
0x18000137e  jz      short loc_180001396
0x180001380  mov     rax, rcx
0x180001383  inc     rax
0x180001386  cmp     [rdx+rax*2], r9w
0x18000138b  jnz     short loc_180001383
0x18000138d  lea     eax, ds:2[rax*2]
0x180001394  jmp     short loc_1800013A0
0x180001396  lea     rdx, qword_180014598
0x18000139d  mov     eax, r8d
0x1800013a0  mov     [rbp+37h+var_18], eax
0x1800013a3  mov     rax, [rbp+37h+arg_30]
0x1800013a7  mov     [rbp+37h+var_20], rdx
0x1800013ab  mov     [rbp+37h+var_14], r9d
0x1800013af  mov     rdx, [rax]
0x1800013b2  test    rdx, rdx
0x1800013b5  jz      short loc_1800013CB
0x1800013b7  inc     rcx
0x1800013ba  cmp     [rdx+rcx*2], r9w
0x1800013bf  jnz     short loc_1800013B7
0x1800013c1  lea     r8d, ds:2[rcx*2]
0x1800013c9  jmp     short loc_1800013D2
0x1800013cb  lea     rdx, qword_180014598
0x1800013d2  mov     rax, [rbp+37h+arg_28]
0x1800013d6  lea     rcx, dword_180019048
0x1800013dd  mov     [rbp+37h+var_40], rax
0x1800013e1  mov     rax, [rbp+37h+arg_20]
0x1800013e5  mov     [rbp+37h+var_50], rax
0x1800013e9  lea     rax, [rbp+37h+var_70]
0x1800013ed  mov     [rbp+37h+var_30], rdx
0x1800013f1  mov     rdx, r10
0x1800013f4  mov     [rbp+37h+var_28], r8d
0x1800013f8  xor     r8d, r8d
0x1800013fb  mov     [rsp+0A0h+var_78], rax
0x180001400  mov     [rsp+0A0h+var_80], 6
0x180001408  mov     [rbp+37h+var_24], r9d
0x18000140c  mov     [rbp+37h+var_38], 4
0x180001414  mov     [rbp+37h+var_48], 8
0x18000141c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001421  mov     rcx, [rbp+37h+var_10]
0x180001425  xor     rcx, rsp; StackCookie
0x180001428  call    __security_check_cookie
0x18000142d  add     rsp, 0A0h
0x180001434  pop     rbp
0x180001435  retn
```
