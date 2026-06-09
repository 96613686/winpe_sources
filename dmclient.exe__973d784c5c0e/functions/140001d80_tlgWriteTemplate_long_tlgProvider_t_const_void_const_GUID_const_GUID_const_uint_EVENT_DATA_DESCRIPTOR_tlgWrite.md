# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x140001d80`
- end: `0x140001e0b`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001505c`
- `0x1400153dc`
- `0x1400155a8`

## callees

- `0x140001840`
- `0x140001d80`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  int *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &dword_14001D5D4;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x140001d80  sub     rsp, 78h
0x140001d84  mov     rax, cs:__security_cookie
0x140001d8b  xor     rax, rsp
0x140001d8e  mov     [rsp+78h+var_18], rax
0x140001d93  mov     rax, [rsp+78h+arg_20]
0x140001d9b  xor     r8d, r8d
0x140001d9e  mov     rcx, [rax]
0x140001da1  test    rcx, rcx
0x140001da4  jz      short loc_140001DBD
0x140001da6  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001daa  inc     rax
0x140001dad  cmp     [rcx+rax*2], r8w
0x140001db2  jnz     short loc_140001DAA
0x140001db4  lea     eax, ds:2[rax*2]
0x140001dbb  jmp     short loc_140001DC9
0x140001dbd  lea     rcx, dword_14001D5D4
0x140001dc4  mov     eax, 2
0x140001dc9  mov     [rsp+78h+var_20], eax
0x140001dcd  xor     r9d, r9d
0x140001dd0  lea     rax, [rsp+78h+var_48]
0x140001dd5  mov     [rsp+78h+var_28], rcx
0x140001dda  mov     [rsp+78h+var_50], rax
0x140001ddf  lea     rcx, dword_140028000
0x140001de6  mov     [rsp+78h+var_58], 3
0x140001dee  mov     [rsp+78h+var_1C], r8d
0x140001df3  call    _tlgWriteTransfer_EventWriteTransfer
0x140001df8  mov     rcx, [rsp+78h+var_18]
0x140001dfd  xor     rcx, rsp; StackCookie
0x140001e00  call    __security_check_cookie
0x140001e05  add     rsp, 78h
0x140001e09  retn
```
