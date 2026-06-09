# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001178`
- end: `0x18000121d`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180003e4c`
- `0x180003ebc`
- `0x18000df2c`
- `0x18000e790`
- `0x180013df0`

## callees

- `0x180001178`
- `0x180001a8c`
- `0x1800026b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
  v16 = 4;
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
0x180001178  sub     rsp, 88h
0x18000117f  mov     rax, cs:__security_cookie
0x180001186  xor     rax, rsp
0x180001189  mov     [rsp+88h+var_18], rax
0x18000118e  mov     rax, [rsp+88h+arg_28]
0x180001196  mov     r10, rcx
0x180001199  mov     [rsp+88h+var_28], rax
0x18000119e  xor     r8d, r8d
0x1800011a1  mov     rax, [rsp+88h+arg_20]
0x1800011a9  mov     r9d, 4
0x1800011af  mov     [rsp+88h+var_20], r9
0x1800011b4  mov     rcx, [rax]
0x1800011b7  test    rcx, rcx
0x1800011ba  jz      short loc_1800011D3
0x1800011bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011c0  inc     rax
0x1800011c3  cmp     [rcx+rax*2], r8w
0x1800011c8  jnz     short loc_1800011C0
0x1800011ca  lea     eax, ds:2[rax*2]
0x1800011d1  jmp     short loc_1800011DF
0x1800011d3  lea     rcx, unk_1800261C4
0x1800011da  mov     eax, 2
0x1800011df  mov     [rsp+88h+var_30], eax
0x1800011e3  lea     rax, [rsp+88h+var_58]
0x1800011e8  mov     [rsp+88h+var_60], rax
0x1800011ed  mov     [rsp+88h+var_68], r9d
0x1800011f2  xor     r9d, r9d
0x1800011f5  mov     [rsp+88h+var_38], rcx
0x1800011fa  mov     rcx, r10
0x1800011fd  mov     [rsp+88h+var_2C], r8d
0x180001202  call    _tlgWriteTransfer_EventWriteTransfer
0x180001207  mov     rcx, [rsp+88h+var_18]
0x18000120c  xor     rcx, rsp; StackCookie
0x18000120f  call    __security_check_cookie
0x180001214  add     rsp, 88h
0x18000121b  retn
```
