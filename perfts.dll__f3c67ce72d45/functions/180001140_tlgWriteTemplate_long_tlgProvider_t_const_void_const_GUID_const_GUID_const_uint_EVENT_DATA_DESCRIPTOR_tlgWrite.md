# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001140`
- end: `0x1800011e0`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058b8`
- `0x180006c50`
- `0x180007668`

## callees

- `0x180001140`
- `0x1800011e8`
- `0x180009930`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 8;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &word_18000DE4C;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180012020, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x180001140  sub     rsp, 88h
0x180001147  mov     rax, cs:__security_cookie
0x18000114e  xor     rax, rsp
0x180001151  mov     [rsp+88h+var_18], rax
0x180001156  mov     rax, [rsp+88h+arg_28]
0x18000115e  xor     r8d, r8d
0x180001161  mov     [rsp+88h+var_28], rax
0x180001166  mov     rax, [rsp+88h+arg_20]
0x18000116e  mov     [rsp+88h+var_20], 8
0x180001177  mov     rcx, [rax]
0x18000117a  test    rcx, rcx
0x18000117d  jz      short loc_180001190
0x18000117f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001183  inc     rax
0x180001186  cmp     [rcx+rax], r8b
0x18000118a  jnz     short loc_180001183
0x18000118c  inc     eax
0x18000118e  jmp     short loc_18000119C
0x180001190  lea     rcx, word_18000DE4C
0x180001197  mov     eax, 1
0x18000119c  mov     [rsp+88h+var_30], eax
0x1800011a0  xor     r9d, r9d
0x1800011a3  lea     rax, [rsp+88h+var_58]
0x1800011a8  mov     [rsp+88h+var_38], rcx
0x1800011ad  mov     [rsp+88h+var_60], rax
0x1800011b2  lea     rcx, dword_180012020
0x1800011b9  mov     [rsp+88h+var_68], 4
0x1800011c1  mov     [rsp+88h+var_2C], r8d
0x1800011c6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011cb  mov     rcx, [rsp+88h+var_18]
0x1800011d0  xor     rcx, rsp; StackCookie
0x1800011d3  call    __security_check_cookie
0x1800011d8  add     rsp, 88h
0x1800011df  retn
```
