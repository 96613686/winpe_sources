# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001224`
- end: `0x1800012ca`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000404c`
- `0x1800040c0`
- `0x180004134`

## callees

- `0x180001224`
- `0x180001a8c`
- `0x1800026b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        __int64 a6)
{
  _WORD *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  _WORD *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]

  v15 = a6;
  v16 = 8;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &unk_1800261C4;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4u, &v11);
}

```

## disassembly

```asm
0x180001224  sub     rsp, 88h
0x18000122b  mov     rax, cs:__security_cookie
0x180001232  xor     rax, rsp
0x180001235  mov     [rsp+88h+var_18], rax
0x18000123a  mov     rax, [rsp+88h+arg_28]
0x180001242  mov     r10, rcx
0x180001245  mov     [rsp+88h+var_28], rax
0x18000124a  xor     r8d, r8d
0x18000124d  mov     rax, [rsp+88h+arg_20]
0x180001255  mov     [rsp+88h+var_20], 8
0x18000125e  mov     rcx, [rax]
0x180001261  test    rcx, rcx
0x180001264  jz      short loc_18000127D
0x180001266  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000126a  inc     rax
0x18000126d  cmp     [rcx+rax*2], r8w
0x180001272  jnz     short loc_18000126A
0x180001274  lea     eax, ds:2[rax*2]
0x18000127b  jmp     short loc_180001289
0x18000127d  lea     rcx, unk_1800261C4
0x180001284  mov     eax, 2
0x180001289  mov     [rsp+88h+var_30], eax
0x18000128d  xor     r9d, r9d
0x180001290  lea     rax, [rsp+88h+var_58]
0x180001295  mov     [rsp+88h+var_38], rcx
0x18000129a  mov     [rsp+88h+var_60], rax
0x18000129f  mov     rcx, r10
0x1800012a2  mov     [rsp+88h+var_68], 4
0x1800012aa  mov     [rsp+88h+var_2C], r8d
0x1800012af  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b4  mov     rcx, [rsp+88h+var_18]
0x1800012b9  xor     rcx, rsp; StackCookie
0x1800012bc  call    __security_check_cookie
0x1800012c1  add     rsp, 88h
0x1800012c8  retn
```
