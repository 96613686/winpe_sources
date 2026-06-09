# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001468`
- end: `0x18000150d`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008940`

## callees

- `0x1800013c8`
- `0x180001468`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
    while ( v6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_18002237C;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x180001468  sub     rsp, 88h
0x18000146f  mov     rax, cs:__security_cookie
0x180001476  xor     rax, rsp
0x180001479  mov     [rsp+88h+var_18], rax
0x18000147e  mov     rax, [rsp+88h+arg_28]
0x180001486  xor     r8d, r8d
0x180001489  mov     [rsp+88h+var_28], rax
0x18000148e  mov     r9d, 4
0x180001494  mov     rax, [rsp+88h+arg_20]
0x18000149c  mov     [rsp+88h+var_20], r9
0x1800014a1  mov     rcx, [rax]
0x1800014a4  test    rcx, rcx
0x1800014a7  jz      short loc_1800014C0
0x1800014a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800014ad  inc     rax
0x1800014b0  cmp     [rcx+rax*2], r8w
0x1800014b5  jnz     short loc_1800014AD
0x1800014b7  lea     eax, ds:2[rax*2]
0x1800014be  jmp     short loc_1800014CC
0x1800014c0  lea     rcx, dword_18002237C
0x1800014c7  mov     eax, 2
0x1800014cc  mov     [rsp+88h+var_30], eax
0x1800014d0  lea     rax, [rsp+88h+var_58]
0x1800014d5  mov     [rsp+88h+var_60], rax
0x1800014da  mov     [rsp+88h+var_68], r9d
0x1800014df  xor     r9d, r9d
0x1800014e2  mov     [rsp+88h+var_38], rcx
0x1800014e7  lea     rcx, dword_18002B0C0
0x1800014ee  mov     [rsp+88h+var_2C], r8d
0x1800014f3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014f8  mov     rcx, [rsp+88h+var_18]
0x1800014fd  xor     rcx, rsp; StackCookie
0x180001500  call    __security_check_cookie
0x180001505  add     rsp, 88h
0x18000150c  retn
```
