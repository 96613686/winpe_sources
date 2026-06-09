# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001340`
- end: `0x1800013ca`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b1c8`
- `0x18000b660`
- `0x18000b7dc`

## callees

- `0x18000108c`
- `0x180001340`
- `0x18000c600`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rax

  if ( *a5 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(*a5 + 2 * v5) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180014230, a2, 0, 0);
}

```

## disassembly

```asm
0x180001340  sub     rsp, 78h
0x180001344  mov     rax, cs:__security_cookie
0x18000134b  xor     rax, rsp
0x18000134e  mov     [rsp+78h+var_18], rax
0x180001353  mov     rax, [rsp+78h+arg_20]
0x18000135b  xor     r8d, r8d
0x18000135e  mov     rcx, [rax]
0x180001361  test    rcx, rcx
0x180001364  jz      short loc_18000137D
0x180001366  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000136a  inc     rax
0x18000136d  cmp     [rcx+rax*2], r8w
0x180001372  jnz     short loc_18000136A
0x180001374  lea     eax, ds:2[rax*2]
0x18000137b  jmp     short loc_180001389
0x18000137d  lea     rcx, qword_180010000
0x180001384  mov     eax, 2
0x180001389  mov     [rsp+78h+var_20], eax
0x18000138d  xor     r9d, r9d
0x180001390  lea     rax, [rsp+78h+var_48]
0x180001395  mov     [rsp+78h+var_28], rcx
0x18000139a  mov     [rsp+78h+var_50], rax
0x18000139f  lea     rcx, dword_180014230
0x1800013a6  mov     [rsp+78h+var_58], 3
0x1800013ae  mov     [rsp+78h+var_1C], r8d
0x1800013b3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013b8  mov     rcx, [rsp+78h+var_18]
0x1800013bd  xor     rcx, rsp; StackCookie
0x1800013c0  call    __security_check_cookie
0x1800013c5  add     rsp, 78h
0x1800013c9  retn
```
