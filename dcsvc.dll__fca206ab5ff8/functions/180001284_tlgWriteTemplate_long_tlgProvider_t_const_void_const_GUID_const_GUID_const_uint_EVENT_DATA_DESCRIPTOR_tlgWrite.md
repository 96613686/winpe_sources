# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001284`
- end: `0x180001323`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f00c`
- `0x18000f0b8`
- `0x180010098`

## callees

- `0x1800011e4`
- `0x180001284`
- `0x180001cf0`

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
    v6 = &qword_1800162C0;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001B0E8, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x180001284  sub     rsp, 88h
0x18000128b  mov     rax, cs:__security_cookie
0x180001292  xor     rax, rsp
0x180001295  mov     [rsp+88h+var_18], rax
0x18000129a  mov     rax, [rsp+88h+arg_28]
0x1800012a2  xor     r8d, r8d
0x1800012a5  mov     [rsp+88h+var_28], rax
0x1800012aa  mov     r9d, 4
0x1800012b0  mov     rax, [rsp+88h+arg_20]
0x1800012b8  mov     [rsp+88h+var_20], r9
0x1800012bd  mov     rcx, [rax]
0x1800012c0  test    rcx, rcx
0x1800012c3  jz      short loc_1800012D6
0x1800012c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800012c9  inc     rax
0x1800012cc  cmp     [rcx+rax], r8b
0x1800012d0  jnz     short loc_1800012C9
0x1800012d2  inc     eax
0x1800012d4  jmp     short loc_1800012E2
0x1800012d6  lea     rcx, qword_1800162C0
0x1800012dd  mov     eax, 1
0x1800012e2  mov     [rsp+88h+var_30], eax
0x1800012e6  lea     rax, [rsp+88h+var_58]
0x1800012eb  mov     [rsp+88h+var_60], rax
0x1800012f0  mov     [rsp+88h+var_68], r9d
0x1800012f5  xor     r9d, r9d
0x1800012f8  mov     [rsp+88h+var_38], rcx
0x1800012fd  lea     rcx, dword_18001B0E8
0x180001304  mov     [rsp+88h+var_2C], r8d
0x180001309  call    _tlgWriteTransfer_EventWriteTransfer
0x18000130e  mov     rcx, [rsp+88h+var_18]
0x180001313  xor     rcx, rsp; StackCookie
0x180001316  call    __security_check_cookie
0x18000131b  add     rsp, 88h
0x180001322  retn
```
