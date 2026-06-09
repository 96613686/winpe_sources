# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x180001bd0`
- end: `0x180001c70`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ddc8`

## callees

- `0x1800013c8`
- `0x180001bd0`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &word_180021D5A;
    v8 = 1;
  }
  v14 = v8;
  v11 = a5;
  v13 = v6;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B088, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x180001bd0  sub     rsp, 88h
0x180001bd7  mov     rax, cs:__security_cookie
0x180001bde  xor     rax, rsp
0x180001be1  mov     [rsp+88h+var_18], rax
0x180001be6  mov     rax, [rsp+88h+arg_28]
0x180001bee  xor     r8d, r8d
0x180001bf1  mov     rcx, [rax]
0x180001bf4  test    rcx, rcx
0x180001bf7  jz      short loc_180001C0A
0x180001bf9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001bfd  inc     rax
0x180001c00  cmp     [rcx+rax], r8b
0x180001c04  jnz     short loc_180001BFD
0x180001c06  inc     eax
0x180001c08  jmp     short loc_180001C16
0x180001c0a  lea     rcx, word_180021D5A
0x180001c11  mov     eax, 1
0x180001c16  mov     [rsp+88h+var_20], eax
0x180001c1a  xor     r9d, r9d
0x180001c1d  mov     rax, [rsp+88h+arg_20]
0x180001c25  mov     [rsp+88h+var_38], rax
0x180001c2a  lea     rax, [rsp+88h+var_58]
0x180001c2f  mov     [rsp+88h+var_28], rcx
0x180001c34  lea     rcx, dword_18002B088
0x180001c3b  mov     [rsp+88h+var_60], rax
0x180001c40  mov     [rsp+88h+var_68], 4
0x180001c48  mov     [rsp+88h+var_1C], r8d
0x180001c4d  mov     [rsp+88h+var_30], 8
0x180001c56  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c5b  mov     rcx, [rsp+88h+var_18]
0x180001c60  xor     rcx, rsp; StackCookie
0x180001c63  call    __security_check_cookie
0x180001c68  add     rsp, 88h
0x180001c6f  retn
```
