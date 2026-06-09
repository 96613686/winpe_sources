# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013d0`
- end: `0x180001503`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a7f8`
- `0x18000acc4`

## callees

- `0x18000108c`
- `0x1800013d0`
- `0x18000c600`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax

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
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(*a7 + 2 * v10) );
  }
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(*a6 + 2 * v11) );
  }
  if ( *a5 )
  {
    do
      ++v8;
    while ( *(_WORD *)(*a5 + 2 * v8) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180014230, a2, 0, 0);
}

```

## disassembly

```asm
0x1800013d0  push    rbp
0x1800013d2  lea     rbp, [rsp-37h]
0x1800013d7  sub     rsp, 0A0h
0x1800013de  mov     rax, cs:__security_cookie
0x1800013e5  xor     rax, rsp
0x1800013e8  mov     [rbp+37h+var_10], rax
0x1800013ec  mov     rax, [rbp+37h+arg_38]
0x1800013f0  lea     r11, qword_180010000
0x1800013f7  mov     r10, rdx
0x1800013fa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013fe  xor     r9d, r9d
0x180001401  mov     r8d, 2
0x180001407  mov     rdx, [rax]
0x18000140a  test    rdx, rdx
0x18000140d  jz      short loc_180001425
0x18000140f  mov     rax, rcx
0x180001412  inc     rax
0x180001415  cmp     [rdx+rax*2], r9w
0x18000141a  jnz     short loc_180001412
0x18000141c  lea     eax, ds:2[rax*2]
0x180001423  jmp     short loc_18000142B
0x180001425  mov     rdx, r11
0x180001428  mov     eax, r8d
0x18000142b  mov     [rbp+37h+var_18], eax
0x18000142e  mov     rax, [rbp+37h+arg_30]
0x180001432  mov     [rbp+37h+var_20], rdx
0x180001436  mov     [rbp+37h+var_14], r9d
0x18000143a  mov     rdx, [rax]
0x18000143d  test    rdx, rdx
0x180001440  jz      short loc_180001458
0x180001442  mov     rax, rcx
0x180001445  inc     rax
0x180001448  cmp     [rdx+rax*2], r9w
0x18000144d  jnz     short loc_180001445
0x18000144f  lea     eax, ds:2[rax*2]
0x180001456  jmp     short loc_18000145E
0x180001458  mov     rdx, r11
0x18000145b  mov     eax, r8d
0x18000145e  mov     [rbp+37h+var_28], eax
0x180001461  mov     rax, [rbp+37h+arg_28]
0x180001465  mov     [rbp+37h+var_30], rdx
0x180001469  mov     [rbp+37h+var_24], r9d
0x18000146d  mov     rdx, [rax]
0x180001470  test    rdx, rdx
0x180001473  jz      short loc_18000148B
0x180001475  mov     rax, rcx
0x180001478  inc     rax
0x18000147b  cmp     [rdx+rax*2], r9w
0x180001480  jnz     short loc_180001478
0x180001482  lea     eax, ds:2[rax*2]
0x180001489  jmp     short loc_180001491
0x18000148b  mov     rdx, r11
0x18000148e  mov     eax, r8d
0x180001491  mov     [rbp+37h+var_38], eax
0x180001494  mov     rax, [rbp+37h+arg_20]
0x180001498  mov     [rbp+37h+var_40], rdx
0x18000149c  mov     [rbp+37h+var_34], r9d
0x1800014a0  mov     rdx, [rax]
0x1800014a3  test    rdx, rdx
0x1800014a6  jz      short loc_1800014BC
0x1800014a8  inc     rcx
0x1800014ab  cmp     [rdx+rcx*2], r9w
0x1800014b0  jnz     short loc_1800014A8
0x1800014b2  lea     r8d, ds:2[rcx*2]
0x1800014ba  jmp     short loc_1800014BF
0x1800014bc  mov     rdx, r11
0x1800014bf  lea     rax, [rbp+37h+var_70]
0x1800014c3  mov     [rbp+37h+var_50], rdx
0x1800014c7  mov     [rbp+37h+var_48], r8d
0x1800014cb  lea     rcx, dword_180014230
0x1800014d2  mov     [rsp+0A0h+var_78], rax
0x1800014d7  xor     r8d, r8d
0x1800014da  mov     rdx, r10
0x1800014dd  mov     [rsp+0A0h+var_80], 6
0x1800014e5  mov     [rbp+37h+var_44], r9d
0x1800014e9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014ee  mov     rcx, [rbp+37h+var_10]
0x1800014f2  xor     rcx, rsp; StackCookie
0x1800014f5  call    __security_check_cookie
0x1800014fa  add     rsp, 0A0h
0x180001501  pop     rbp
0x180001502  retn
```
