# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x180001b0c`
- end: `0x180001bc8`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18001dd4c`
- `0x18001de38`
- `0x18001df24`
- `0x18001dfa0`
- `0x18001e08c`
- `0x18001e178`

## callees

- `0x1800013c8`
- `0x180001b0c`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  __int64 v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  const unsigned __int16 *v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &word_180021D5A;
    v9 = 1;
  }
  v17 = v9;
  v14 = a6;
  v12 = a5;
  v16 = v7;
  v18 = 0;
  v15 = 8;
  v13 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B000, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x180001b0c  sub     rsp, 98h
0x180001b13  mov     rax, cs:__security_cookie
0x180001b1a  xor     rax, rsp
0x180001b1d  mov     [rsp+98h+var_18], rax
0x180001b25  mov     rax, [rsp+98h+arg_30]
0x180001b2d  xor     r8d, r8d
0x180001b30  mov     rcx, [rax]
0x180001b33  test    rcx, rcx
0x180001b36  jz      short loc_180001B49
0x180001b38  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b3c  inc     rax
0x180001b3f  cmp     [rcx+rax], r8b
0x180001b43  jnz     short loc_180001B3C
0x180001b45  inc     eax
0x180001b47  jmp     short loc_180001B55
0x180001b49  lea     rcx, word_180021D5A
0x180001b50  mov     eax, 1
0x180001b55  mov     [rsp+98h+var_20], eax
0x180001b59  xor     r9d, r9d
0x180001b5c  mov     rax, [rsp+98h+arg_28]
0x180001b64  mov     [rsp+98h+var_38], rax
0x180001b69  mov     rax, [rsp+98h+arg_20]
0x180001b71  mov     [rsp+98h+var_48], rax
0x180001b76  lea     rax, [rsp+98h+var_68]
0x180001b7b  mov     [rsp+98h+var_28], rcx
0x180001b80  lea     rcx, dword_18002B000
0x180001b87  mov     [rsp+98h+var_70], rax
0x180001b8c  mov     [rsp+98h+var_78], 5
0x180001b94  mov     [rsp+98h+var_1C], r8d
0x180001b99  mov     [rsp+98h+var_30], 8
0x180001ba2  mov     [rsp+98h+var_40], 4
0x180001bab  call    _tlgWriteTransfer_EventWriteTransfer
0x180001bb0  mov     rcx, [rsp+98h+var_18]
0x180001bb8  xor     rcx, rsp; StackCookie
0x180001bbb  call    __security_check_cookie
0x180001bc0  add     rsp, 98h
0x180001bc7  retn
```
