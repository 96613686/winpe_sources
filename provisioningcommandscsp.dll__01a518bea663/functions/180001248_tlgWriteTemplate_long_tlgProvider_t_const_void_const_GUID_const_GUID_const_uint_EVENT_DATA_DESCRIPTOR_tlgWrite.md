# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001248`
- end: `0x180001339`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009080`

## callees

- `0x18000108c`
- `0x180001248`
- `0x18000c600`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v6; // rcx
  __int64 v7; // rax

  v6 = -1;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*a6 + 2 * v7) );
  }
  if ( *a5 )
  {
    do
      ++v6;
    while ( *(_WORD *)(*a5 + 2 * v6) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180014230, a2, 0, 0);
}

```

## disassembly

```asm
0x180001248  sub     rsp, 98h
0x18000124f  mov     rax, cs:__security_cookie
0x180001256  xor     rax, rsp
0x180001259  mov     [rsp+98h+var_18], rax
0x180001261  mov     rax, [rsp+98h+arg_30]
0x180001269  xor     r9d, r9d
0x18000126c  mov     [rsp+98h+var_28], rax
0x180001271  mov     r10, rdx
0x180001274  mov     rax, [rsp+98h+arg_28]
0x18000127c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001280  mov     [rsp+98h+var_20], 4
0x180001289  lea     r8d, [r9+2]
0x18000128d  mov     rdx, [rax]
0x180001290  test    rdx, rdx
0x180001293  jz      short loc_1800012AB
0x180001295  mov     rax, rcx
0x180001298  inc     rax
0x18000129b  cmp     [rdx+rax*2], r9w
0x1800012a0  jnz     short loc_180001298
0x1800012a2  lea     eax, ds:2[rax*2]
0x1800012a9  jmp     short loc_1800012B5
0x1800012ab  lea     rdx, qword_180010000
0x1800012b2  mov     eax, r8d
0x1800012b5  mov     [rsp+98h+var_30], eax
0x1800012b9  mov     rax, [rsp+98h+arg_20]
0x1800012c1  mov     [rsp+98h+var_38], rdx
0x1800012c6  mov     [rsp+98h+var_2C], r9d
0x1800012cb  mov     rdx, [rax]
0x1800012ce  test    rdx, rdx
0x1800012d1  jz      short loc_1800012E7
0x1800012d3  inc     rcx
0x1800012d6  cmp     [rdx+rcx*2], r9w
0x1800012db  jnz     short loc_1800012D3
0x1800012dd  lea     r8d, ds:2[rcx*2]
0x1800012e5  jmp     short loc_1800012EE
0x1800012e7  lea     rdx, qword_180010000
0x1800012ee  lea     rax, [rsp+98h+var_68]
0x1800012f3  mov     [rsp+98h+var_48], rdx
0x1800012f8  mov     [rsp+98h+var_40], r8d
0x1800012fd  lea     rcx, dword_180014230
0x180001304  mov     [rsp+98h+var_70], rax
0x180001309  xor     r8d, r8d
0x18000130c  mov     rdx, r10
0x18000130f  mov     [rsp+98h+var_78], 5
0x180001317  mov     [rsp+98h+var_3C], r9d
0x18000131c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001321  mov     rcx, [rsp+98h+var_18]
0x180001329  xor     rcx, rsp; StackCookie
0x18000132c  call    __security_check_cookie
0x180001331  add     rsp, 98h
0x180001338  retn
```
