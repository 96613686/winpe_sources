# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000112c`
- end: `0x180001242`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800083a4`
- `0x18000af48`
- `0x18000b3f0`

## callees

- `0x18000108c`
- `0x18000112c`
- `0x18000c600`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax

  v7 = -1;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*a7 + 2 * v8) );
  }
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*a6 + 2 * v9) );
  }
  if ( *a5 )
  {
    do
      ++v7;
    while ( *(_WORD *)(*a5 + 2 * v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180014230, a2, 0, 0);
}

```

## disassembly

```asm
0x18000112c  sub     rsp, 98h
0x180001133  mov     rax, cs:__security_cookie
0x18000113a  xor     rax, rsp
0x18000113d  mov     [rsp+98h+var_18], rax
0x180001145  mov     rax, [rsp+98h+arg_30]
0x18000114d  lea     r11, qword_180010000
0x180001154  mov     r10, rdx
0x180001157  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000115b  xor     r9d, r9d
0x18000115e  mov     r8d, 2
0x180001164  mov     rdx, [rax]
0x180001167  test    rdx, rdx
0x18000116a  jz      short loc_180001182
0x18000116c  mov     rax, rcx
0x18000116f  inc     rax
0x180001172  cmp     [rdx+rax*2], r9w
0x180001177  jnz     short loc_18000116F
0x180001179  lea     eax, ds:2[rax*2]
0x180001180  jmp     short loc_180001188
0x180001182  mov     rdx, r11
0x180001185  mov     eax, r8d
0x180001188  mov     [rsp+98h+var_20], eax
0x18000118c  mov     rax, [rsp+98h+arg_28]
0x180001194  mov     [rsp+98h+var_28], rdx
0x180001199  mov     [rsp+98h+var_1C], r9d
0x18000119e  mov     rdx, [rax]
0x1800011a1  test    rdx, rdx
0x1800011a4  jz      short loc_1800011BC
0x1800011a6  mov     rax, rcx
0x1800011a9  inc     rax
0x1800011ac  cmp     [rdx+rax*2], r9w
0x1800011b1  jnz     short loc_1800011A9
0x1800011b3  lea     eax, ds:2[rax*2]
0x1800011ba  jmp     short loc_1800011C2
0x1800011bc  mov     rdx, r11
0x1800011bf  mov     eax, r8d
0x1800011c2  mov     [rsp+98h+var_30], eax
0x1800011c6  mov     rax, [rsp+98h+arg_20]
0x1800011ce  mov     [rsp+98h+var_38], rdx
0x1800011d3  mov     [rsp+98h+var_2C], r9d
0x1800011d8  mov     rdx, [rax]
0x1800011db  test    rdx, rdx
0x1800011de  jz      short loc_1800011F4
0x1800011e0  inc     rcx
0x1800011e3  cmp     [rdx+rcx*2], r9w
0x1800011e8  jnz     short loc_1800011E0
0x1800011ea  lea     r8d, ds:2[rcx*2]
0x1800011f2  jmp     short loc_1800011F7
0x1800011f4  mov     rdx, r11
0x1800011f7  lea     rax, [rsp+98h+var_68]
0x1800011fc  mov     [rsp+98h+var_48], rdx
0x180001201  mov     [rsp+98h+var_40], r8d
0x180001206  lea     rcx, dword_180014230
0x18000120d  mov     [rsp+98h+var_70], rax
0x180001212  xor     r8d, r8d
0x180001215  mov     rdx, r10
0x180001218  mov     [rsp+98h+var_78], 5
0x180001220  mov     [rsp+98h+var_3C], r9d
0x180001225  call    _tlgWriteTransfer_EventWriteTransfer
0x18000122a  mov     rcx, [rsp+98h+var_18]
0x180001232  xor     rcx, rsp; StackCookie
0x180001235  call    __security_check_cookie
0x18000123a  add     rsp, 98h
0x180001241  retn
```
