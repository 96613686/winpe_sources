# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001ad0`
- end: `0x140001b8e`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const WCHAR **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f314`

## callees

- `0x1400019e8`
- `0x140001ad0`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 a6,
        __int64 a7)
{
  const WCHAR *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  const WCHAR *v13; // [rsp+50h] [rbp-48h]
  int v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+5Ch] [rbp-3Ch]
  __int64 v16; // [rsp+60h] [rbp-38h]
  __int64 v17; // [rsp+68h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v19 = 4;
  v17 = 4;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &String;
    v10 = 2;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 5, v12);
}

```

## disassembly

```asm
0x140001ad0  sub     rsp, 98h
0x140001ad7  mov     rax, cs:__security_cookie
0x140001ade  xor     rax, rsp
0x140001ae1  mov     [rsp+98h+var_18], rax
0x140001ae9  mov     rax, [rsp+98h+arg_30]
0x140001af1  mov     r10, rcx
0x140001af4  mov     [rsp+98h+var_28], rax
0x140001af9  xor     r11d, r11d
0x140001afc  mov     rax, [rsp+98h+arg_28]
0x140001b04  mov     [rsp+98h+var_38], rax
0x140001b09  mov     rax, [rsp+98h+arg_20]
0x140001b11  mov     [rsp+98h+var_20], 4
0x140001b1a  mov     [rsp+98h+var_30], 4
0x140001b23  mov     rcx, [rax]
0x140001b26  test    rcx, rcx
0x140001b29  jz      short loc_140001B42
0x140001b2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001b2f  inc     rax
0x140001b32  cmp     [rcx+rax*2], r11w
0x140001b37  jnz     short loc_140001B2F
0x140001b39  lea     eax, ds:2[rax*2]
0x140001b40  jmp     short loc_140001B4E
0x140001b42  lea     rcx, String
0x140001b49  mov     eax, 2
0x140001b4e  mov     [rsp+98h+var_40], eax
0x140001b52  lea     rax, [rsp+98h+var_68]
0x140001b57  mov     [rsp+98h+var_48], rcx
0x140001b5c  mov     rcx, r10
0x140001b5f  mov     [rsp+98h+var_70], rax
0x140001b64  mov     [rsp+98h+var_78], 5
0x140001b6c  mov     [rsp+98h+var_3C], r11d
0x140001b71  call    _tlgWriteTransfer_EventWriteTransfer
0x140001b76  mov     rcx, [rsp+98h+var_18]
0x140001b7e  xor     rcx, rsp; StackCookie
0x140001b81  call    __security_check_cookie
0x140001b86  add     rsp, 98h
0x140001b8d  retn
```
