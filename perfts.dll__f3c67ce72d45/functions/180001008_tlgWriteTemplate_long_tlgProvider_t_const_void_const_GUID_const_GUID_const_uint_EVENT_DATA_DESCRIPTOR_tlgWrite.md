# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x18000108f`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `135`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180004d5c`
- `0x180004e40`
- `0x180005378`
- `0x18000576c`
- `0x180006068`
- `0x180007668`
- `0x180007f88`
- `0x18000823c`

## callees

- `0x180001008`
- `0x1800011e8`
- `0x180009930`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &word_18000DE4C;
    v7 = 1;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180012020, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 78h
0x18000100c  mov     rax, cs:__security_cookie
0x180001013  xor     rax, rsp
0x180001016  mov     [rsp+78h+var_18], rax
0x18000101b  mov     rax, [rsp+78h+arg_20]
0x180001023  mov     rcx, [rax]
0x180001026  test    rcx, rcx
0x180001029  jz      short loc_18000103C
0x18000102b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000102f  inc     rax
0x180001032  cmp     byte ptr [rcx+rax], 0
0x180001036  jnz     short loc_18000102F
0x180001038  inc     eax
0x18000103a  jmp     short loc_180001048
0x18000103c  lea     rcx, word_18000DE4C
0x180001043  mov     eax, 1
0x180001048  mov     [rsp+78h+var_20], eax
0x18000104c  xor     r9d, r9d
0x18000104f  lea     rax, [rsp+78h+var_48]
0x180001054  mov     [rsp+78h+var_28], rcx
0x180001059  mov     [rsp+78h+var_50], rax
0x18000105e  lea     rcx, dword_180012020
0x180001065  xor     r8d, r8d
0x180001068  mov     [rsp+78h+var_58], 3
0x180001070  mov     [rsp+78h+var_1C], 0
0x180001078  call    _tlgWriteTransfer_EventWriteTransfer
0x18000107d  mov     rcx, [rsp+78h+var_18]
0x180001082  xor     rcx, rsp; StackCookie
0x180001085  call    __security_check_cookie
0x18000108a  add     rsp, 78h
0x18000108e  retn
```
