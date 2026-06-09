# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x140001008`
- end: `0x14000108f`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c47c`
- `0x14001150c`
- `0x140011928`

## callees

- `0x140001008`
- `0x14000182c`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _BYTE v9[32]; // [rsp+30h] [rbp-48h] BYREF
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
    v5 = &word_14001C5D2;
    v7 = 1;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027000, a2, 0, 0, 3, v9);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 78h
0x14000100c  mov     rax, cs:__security_cookie
0x140001013  xor     rax, rsp
0x140001016  mov     [rsp+78h+var_18], rax
0x14000101b  mov     rax, [rsp+78h+arg_20]
0x140001023  mov     rcx, [rax]
0x140001026  test    rcx, rcx
0x140001029  jz      short loc_14000103C
0x14000102b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000102f  inc     rax
0x140001032  cmp     byte ptr [rcx+rax], 0
0x140001036  jnz     short loc_14000102F
0x140001038  inc     eax
0x14000103a  jmp     short loc_140001048
0x14000103c  lea     rcx, word_14001C5D2
0x140001043  mov     eax, 1
0x140001048  mov     [rsp+78h+var_20], eax
0x14000104c  xor     r9d, r9d
0x14000104f  lea     rax, [rsp+78h+var_48]
0x140001054  mov     [rsp+78h+var_28], rcx
0x140001059  mov     [rsp+78h+var_50], rax
0x14000105e  lea     rcx, dword_140027000
0x140001065  xor     r8d, r8d
0x140001068  mov     [rsp+78h+var_58], 3
0x140001070  mov     [rsp+78h+var_1C], 0
0x140001078  call    _tlgWriteTransfer_EventWriteTransfer
0x14000107d  mov     rcx, [rsp+78h+var_18]
0x140001082  xor     rcx, rsp; StackCookie
0x140001085  call    __security_check_cookie
0x14000108a  add     rsp, 78h
0x14000108e  retn
```
