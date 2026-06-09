# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001bb4`
- end: `0x140001c54`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140011580`
- `0x1400119f0`
- `0x140011cd0`
- `0x140012120`

## callees

- `0x140001840`
- `0x140001bb4`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
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
  v15 = 4;
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
    v6 = &word_14001D5D2;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x140001bb4  sub     rsp, 88h
0x140001bbb  mov     rax, cs:__security_cookie
0x140001bc2  xor     rax, rsp
0x140001bc5  mov     [rsp+88h+var_18], rax
0x140001bca  mov     rax, [rsp+88h+arg_28]
0x140001bd2  xor     r8d, r8d
0x140001bd5  mov     [rsp+88h+var_28], rax
0x140001bda  mov     r9d, 4
0x140001be0  mov     rax, [rsp+88h+arg_20]
0x140001be8  mov     [rsp+88h+var_20], r9
0x140001bed  mov     rcx, [rax]
0x140001bf0  test    rcx, rcx
0x140001bf3  jz      short loc_140001C06
0x140001bf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001bf9  inc     rax
0x140001bfc  cmp     [rcx+rax], r8b
0x140001c00  jnz     short loc_140001BF9
0x140001c02  inc     eax
0x140001c04  jmp     short loc_140001C12
0x140001c06  lea     rcx, word_14001D5D2
0x140001c0d  mov     eax, 1
0x140001c12  mov     [rsp+88h+var_30], eax
0x140001c16  lea     rax, [rsp+88h+var_58]
0x140001c1b  mov     [rsp+88h+var_60], rax
0x140001c20  mov     [rsp+88h+var_68], r9d
0x140001c25  xor     r9d, r9d
0x140001c28  mov     [rsp+88h+var_38], rcx
0x140001c2d  lea     rcx, dword_140028000
0x140001c34  mov     [rsp+88h+var_2C], r8d
0x140001c39  call    _tlgWriteTransfer_EventWriteTransfer
0x140001c3e  mov     rcx, [rsp+88h+var_18]
0x140001c43  xor     rcx, rsp; StackCookie
0x140001c46  call    __security_check_cookie
0x140001c4b  add     rsp, 88h
0x140001c52  retn
```
