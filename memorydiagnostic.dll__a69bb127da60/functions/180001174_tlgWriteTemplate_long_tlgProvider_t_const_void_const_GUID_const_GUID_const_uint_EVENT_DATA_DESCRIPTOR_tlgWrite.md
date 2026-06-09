# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001174`
- end: `0x180001218`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800043f8`
- `0x180004470`
- `0x1800044e8`
- `0x180004560`
- `0x1800045dc`
- `0x180004654`
- `0x1800046cc`
- `0x180004744`

## callees

- `0x180001174`
- `0x180001a7c`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
  v16 = 4;
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
0x180001174  sub     rsp, 88h
0x18000117b  mov     rax, cs:__security_cookie
0x180001182  xor     rax, rsp
0x180001185  mov     [rsp+88h+var_18], rax
0x18000118a  mov     rax, [rsp+88h+arg_28]
0x180001192  mov     r10, rcx
0x180001195  mov     [rsp+88h+var_28], rax
0x18000119a  xor     r8d, r8d
0x18000119d  mov     rax, [rsp+88h+arg_20]
0x1800011a5  mov     r9d, 4
0x1800011ab  mov     [rsp+88h+var_20], r9
0x1800011b0  mov     rcx, [rax]
0x1800011b3  test    rcx, rcx
0x1800011b6  jz      short loc_1800011CF
0x1800011b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011bc  inc     rax
0x1800011bf  cmp     [rcx+rax*2], r8w
0x1800011c4  jnz     short loc_1800011BC
0x1800011c6  lea     eax, ds:2[rax*2]
0x1800011cd  jmp     short loc_1800011DB
0x1800011cf  lea     rcx, dword_180025214
0x1800011d6  mov     eax, 2
0x1800011db  mov     [rsp+88h+var_30], eax
0x1800011df  lea     rax, [rsp+88h+var_58]
0x1800011e4  mov     [rsp+88h+var_60], rax
0x1800011e9  mov     [rsp+88h+var_68], r9d
0x1800011ee  xor     r9d, r9d
0x1800011f1  mov     [rsp+88h+var_38], rcx
0x1800011f6  mov     rcx, r10
0x1800011f9  mov     [rsp+88h+var_2C], r8d
0x1800011fe  call    _tlgWriteTransfer_EventWriteTransfer
0x180001203  mov     rcx, [rsp+88h+var_18]
0x180001208  xor     rcx, rsp; StackCookie
0x18000120b  call    __security_check_cookie
0x180001210  add     rsp, 88h
0x180001217  retn
```
