# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400018e4`
- end: `0x1400019a0`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fbf8`
- `0x1400119f0`

## callees

- `0x140001840`
- `0x1400018e4`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 4;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &word_14001D5D2;
    v9 = 1;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x1400018e4  mov     r11, rsp
0x1400018e7  sub     rsp, 98h
0x1400018ee  mov     rax, cs:__security_cookie
0x1400018f5  xor     rax, rsp
0x1400018f8  mov     [rsp+98h+var_18], rax
0x140001900  mov     rax, [rsp+98h+arg_30]
0x140001908  xor     r8d, r8d
0x14000190b  mov     [r11-28h], rax
0x14000190f  mov     rax, [rsp+98h+arg_28]
0x140001917  mov     [r11-38h], rax
0x14000191b  mov     rax, [rsp+98h+arg_20]
0x140001923  mov     qword ptr [r11-20h], 4
0x14000192b  mov     qword ptr [r11-30h], 4
0x140001933  mov     rcx, [rax]
0x140001936  test    rcx, rcx
0x140001939  jz      short loc_14000194C
0x14000193b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000193f  inc     rax
0x140001942  cmp     [rcx+rax], r8b
0x140001946  jnz     short loc_14000193F
0x140001948  inc     eax
0x14000194a  jmp     short loc_140001958
0x14000194c  lea     rcx, word_14001D5D2
0x140001953  mov     eax, 1
0x140001958  mov     [rsp+98h+var_40], eax
0x14000195c  xor     r9d, r9d
0x14000195f  lea     rax, [rsp+98h+var_68]
0x140001964  mov     [rsp+98h+var_48], rcx
0x140001969  mov     [rsp+98h+var_70], rax
0x14000196e  lea     rcx, dword_140028000
0x140001975  mov     [rsp+98h+var_78], 5
0x14000197d  mov     [rsp+98h+var_3C], r8d
0x140001982  call    _tlgWriteTransfer_EventWriteTransfer
0x140001987  mov     rcx, [rsp+98h+var_18]
0x14000198f  xor     rcx, rsp; StackCookie
0x140001992  call    __security_check_cookie
0x140001997  add     rsp, 98h
0x14000199e  retn
```
