# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)

- ea: `0x140001538`
- end: `0x1400015f6`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@5@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ff8`
- `0x14000c47c`

## callees

- `0x140001538`
- `0x14000182c`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 *a7,
        __int64 *a8)
{
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v14; // [rsp+50h] [rbp-19h]
  int v15; // [rsp+58h] [rbp-11h]
  int v16; // [rsp+5Ch] [rbp-Dh]
  __int64 v17; // [rsp+60h] [rbp-9h]
  __int64 v18; // [rsp+68h] [rbp-1h]
  __int64 v19; // [rsp+70h] [rbp+7h]
  __int64 v20; // [rsp+78h] [rbp+Fh]
  __int64 v21; // [rsp+80h] [rbp+17h]
  __int64 v22; // [rsp+88h] [rbp+1Fh]

  v22 = 16;
  v20 = 16;
  v18 = 4;
  v21 = *a8;
  v8 = *a7;
  v17 = a6;
  v19 = v8;
  v9 = *a5;
  if ( *a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v9 = &word_14001C5D2;
    v11 = 1;
  }
  v15 = v11;
  v14 = v9;
  v16 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027038, a2, 0, 0, 6, v13);
}

```

## disassembly

```asm
0x140001538  push    rbp
0x14000153a  lea     rbp, [rsp-37h]
0x14000153f  sub     rsp, 0A0h
0x140001546  mov     rax, cs:__security_cookie
0x14000154d  xor     rax, rsp
0x140001550  mov     [rbp+37h+var_10], rax
0x140001554  mov     rax, [rbp+37h+arg_38]
0x140001558  xor     r9d, r9d
0x14000155b  mov     [rbp+37h+var_18], 10h
0x140001563  mov     [rbp+37h+var_28], 10h
0x14000156b  mov     [rbp+37h+var_38], 4
0x140001573  mov     rcx, [rax]
0x140001576  mov     rax, [rbp+37h+arg_30]
0x14000157a  mov     [rbp+37h+var_20], rcx
0x14000157e  mov     rcx, [rax]
0x140001581  mov     rax, [rbp+37h+arg_28]
0x140001585  mov     [rbp+37h+var_40], rax
0x140001589  mov     rax, [rbp+37h+arg_20]
0x14000158d  mov     [rbp+37h+var_30], rcx
0x140001591  mov     rcx, [rax]
0x140001594  test    rcx, rcx
0x140001597  jz      short loc_1400015AA
0x140001599  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000159d  inc     rax
0x1400015a0  cmp     [rcx+rax], r9b
0x1400015a4  jnz     short loc_14000159D
0x1400015a6  inc     eax
0x1400015a8  jmp     short loc_1400015B6
0x1400015aa  lea     rcx, word_14001C5D2
0x1400015b1  mov     eax, 1
0x1400015b6  mov     [rbp+37h+var_48], eax
0x1400015b9  xor     r8d, r8d
0x1400015bc  lea     rax, [rbp+37h+var_70]
0x1400015c0  mov     [rbp+37h+var_50], rcx
0x1400015c4  mov     [rsp+0A0h+var_78], rax
0x1400015c9  lea     rcx, dword_140027038
0x1400015d0  mov     [rsp+0A0h+var_80], 6
0x1400015d8  mov     [rbp+37h+var_44], r9d
0x1400015dc  call    _tlgWriteTransfer_EventWriteTransfer
0x1400015e1  mov     rcx, [rbp+37h+var_10]
0x1400015e5  xor     rcx, rsp; StackCookie
0x1400015e8  call    __security_check_cookie
0x1400015ed  add     rsp, 0A0h
0x1400015f4  pop     rbp
0x1400015f5  retn
```
