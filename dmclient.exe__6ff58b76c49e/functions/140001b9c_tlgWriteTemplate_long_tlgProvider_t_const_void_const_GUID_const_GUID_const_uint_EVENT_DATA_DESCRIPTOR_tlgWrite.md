# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001b9c`
- end: `0x140001c3b`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140010e70`
- `0x140011250`
- `0x14001150c`
- `0x140011928`

## callees

- `0x14000182c`
- `0x140001b9c`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
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
    v6 = &word_14001C5D2;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x140001b9c  sub     rsp, 88h
0x140001ba3  mov     rax, cs:__security_cookie
0x140001baa  xor     rax, rsp
0x140001bad  mov     [rsp+88h+var_18], rax
0x140001bb2  mov     rax, [rsp+88h+arg_28]
0x140001bba  xor     r8d, r8d
0x140001bbd  mov     [rsp+88h+var_28], rax
0x140001bc2  mov     r9d, 4
0x140001bc8  mov     rax, [rsp+88h+arg_20]
0x140001bd0  mov     [rsp+88h+var_20], r9
0x140001bd5  mov     rcx, [rax]
0x140001bd8  test    rcx, rcx
0x140001bdb  jz      short loc_140001BEE
0x140001bdd  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001be1  inc     rax
0x140001be4  cmp     [rcx+rax], r8b
0x140001be8  jnz     short loc_140001BE1
0x140001bea  inc     eax
0x140001bec  jmp     short loc_140001BFA
0x140001bee  lea     rcx, word_14001C5D2
0x140001bf5  mov     eax, 1
0x140001bfa  mov     [rsp+88h+var_30], eax
0x140001bfe  lea     rax, [rsp+88h+var_58]
0x140001c03  mov     [rsp+88h+var_60], rax
0x140001c08  mov     [rsp+88h+var_68], r9d
0x140001c0d  xor     r9d, r9d
0x140001c10  mov     [rsp+88h+var_38], rcx
0x140001c15  lea     rcx, dword_140027000
0x140001c1c  mov     [rsp+88h+var_2C], r8d
0x140001c21  call    _tlgWriteTransfer_EventWriteTransfer
0x140001c26  mov     rcx, [rsp+88h+var_18]
0x140001c2b  xor     rcx, rsp; StackCookie
0x140001c2e  call    __security_check_cookie
0x140001c33  add     rsp, 88h
0x140001c3a  retn
```
