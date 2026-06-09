# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800014d8`
- end: `0x180001577`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000df40`
- `0x18000fa50`
- `0x18000ffe0`
- `0x180010710`

## callees

- `0x1800011cc`
- `0x1800014d8`
- `0x180002270`

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
    v6 = &byte_180016B57;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x1800014d8  sub     rsp, 88h
0x1800014df  mov     rax, cs:__security_cookie
0x1800014e6  xor     rax, rsp
0x1800014e9  mov     [rsp+88h+var_18], rax
0x1800014ee  mov     rax, [rsp+88h+arg_28]
0x1800014f6  xor     r8d, r8d
0x1800014f9  mov     [rsp+88h+var_28], rax
0x1800014fe  mov     r9d, 4
0x180001504  mov     rax, [rsp+88h+arg_20]
0x18000150c  mov     [rsp+88h+var_20], r9
0x180001511  mov     rcx, [rax]
0x180001514  test    rcx, rcx
0x180001517  jz      short loc_18000152A
0x180001519  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000151d  inc     rax
0x180001520  cmp     [rcx+rax], r8b
0x180001524  jnz     short loc_18000151D
0x180001526  inc     eax
0x180001528  jmp     short loc_180001536
0x18000152a  lea     rcx, byte_180016B57
0x180001531  mov     eax, 1
0x180001536  mov     [rsp+88h+var_30], eax
0x18000153a  lea     rax, [rsp+88h+var_58]
0x18000153f  mov     [rsp+88h+var_60], rax
0x180001544  mov     [rsp+88h+var_68], r9d
0x180001549  xor     r9d, r9d
0x18000154c  mov     [rsp+88h+var_38], rcx
0x180001551  lea     rcx, dword_18001E048
0x180001558  mov     [rsp+88h+var_2C], r8d
0x18000155d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001562  mov     rcx, [rsp+88h+var_18]
0x180001567  xor     rcx, rsp; StackCookie
0x18000156a  call    __security_check_cookie
0x18000156f  add     rsp, 88h
0x180001576  retn
```
