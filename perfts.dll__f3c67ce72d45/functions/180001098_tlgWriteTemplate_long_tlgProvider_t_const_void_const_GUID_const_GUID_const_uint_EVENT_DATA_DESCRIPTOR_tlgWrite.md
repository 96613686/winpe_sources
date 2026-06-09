# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001098`
- end: `0x180001137`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `159`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180004e40`
- `0x180005378`
- `0x18000576c`
- `0x180006068`
- `0x180007b10`
- `0x180008bac`

## callees

- `0x180001098`
- `0x1800011e8`
- `0x180009930`

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
0x180001098  sub     rsp, 88h
0x18000109f  mov     rax, cs:__security_cookie
0x1800010a6  xor     rax, rsp
0x1800010a9  mov     [rsp+88h+var_18], rax
0x1800010ae  mov     rax, [rsp+88h+arg_28]
0x1800010b6  xor     r8d, r8d
0x1800010b9  mov     [rsp+88h+var_28], rax
0x1800010be  mov     r9d, 4
0x1800010c4  mov     rax, [rsp+88h+arg_20]
0x1800010cc  mov     [rsp+88h+var_20], r9
0x1800010d1  mov     rcx, [rax]
0x1800010d4  test    rcx, rcx
0x1800010d7  jz      short loc_1800010EA
0x1800010d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800010dd  inc     rax
0x1800010e0  cmp     [rcx+rax], r8b
0x1800010e4  jnz     short loc_1800010DD
0x1800010e6  inc     eax
0x1800010e8  jmp     short loc_1800010F6
0x1800010ea  lea     rcx, word_18000DE4C
0x1800010f1  mov     eax, 1
0x1800010f6  mov     [rsp+88h+var_30], eax
0x1800010fa  lea     rax, [rsp+88h+var_58]
0x1800010ff  mov     [rsp+88h+var_60], rax
0x180001104  mov     [rsp+88h+var_68], r9d
0x180001109  xor     r9d, r9d
0x18000110c  mov     [rsp+88h+var_38], rcx
0x180001111  lea     rcx, dword_180012020
0x180001118  mov     [rsp+88h+var_2C], r8d
0x18000111d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001122  mov     rcx, [rsp+88h+var_18]
0x180001127  xor     rcx, rsp; StackCookie
0x18000112a  call    __security_check_cookie
0x18000112f  add     rsp, 88h
0x180001136  retn
```
