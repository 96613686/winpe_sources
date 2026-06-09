# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001220`
- end: `0x1800012c5`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800048ec`
- `0x180004964`
- `0x1800049dc`

## callees

- `0x180001220`
- `0x180001a7c`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  int *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]

  v15 = a6;
  v16 = 8;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &dword_180025214;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           4,
           v11);
}

```

## disassembly

```asm
0x180001220  sub     rsp, 88h
0x180001227  mov     rax, cs:__security_cookie
0x18000122e  xor     rax, rsp
0x180001231  mov     [rsp+88h+var_18], rax
0x180001236  mov     rax, [rsp+88h+arg_28]
0x18000123e  mov     r10, rcx
0x180001241  mov     [rsp+88h+var_28], rax
0x180001246  xor     r8d, r8d
0x180001249  mov     rax, [rsp+88h+arg_20]
0x180001251  mov     [rsp+88h+var_20], 8
0x18000125a  mov     rcx, [rax]
0x18000125d  test    rcx, rcx
0x180001260  jz      short loc_180001279
0x180001262  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001266  inc     rax
0x180001269  cmp     [rcx+rax*2], r8w
0x18000126e  jnz     short loc_180001266
0x180001270  lea     eax, ds:2[rax*2]
0x180001277  jmp     short loc_180001285
0x180001279  lea     rcx, dword_180025214
0x180001280  mov     eax, 2
0x180001285  mov     [rsp+88h+var_30], eax
0x180001289  xor     r9d, r9d
0x18000128c  lea     rax, [rsp+88h+var_58]
0x180001291  mov     [rsp+88h+var_38], rcx
0x180001296  mov     [rsp+88h+var_60], rax
0x18000129b  mov     rcx, r10
0x18000129e  mov     [rsp+88h+var_68], 4
0x1800012a6  mov     [rsp+88h+var_2C], r8d
0x1800012ab  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b0  mov     rcx, [rsp+88h+var_18]
0x1800012b5  xor     rcx, rsp; StackCookie
0x1800012b8  call    __security_check_cookie
0x1800012bd  add     rsp, 88h
0x1800012c4  retn
```
