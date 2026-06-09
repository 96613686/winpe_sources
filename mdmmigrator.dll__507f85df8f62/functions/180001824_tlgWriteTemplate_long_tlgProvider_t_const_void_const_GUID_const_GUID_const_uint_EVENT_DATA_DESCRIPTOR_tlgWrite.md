# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001824`
- end: `0x1800018c3`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000be00`

## callees

- `0x1800013c8`
- `0x180001824`
- `0x1800022e0`

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
    v6 = &word_180021D5A;
    v8 = 1;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x180001824  sub     rsp, 88h
0x18000182b  mov     rax, cs:__security_cookie
0x180001832  xor     rax, rsp
0x180001835  mov     [rsp+88h+var_18], rax
0x18000183a  mov     rax, [rsp+88h+arg_28]
0x180001842  xor     r8d, r8d
0x180001845  mov     [rsp+88h+var_28], rax
0x18000184a  mov     r9d, 4
0x180001850  mov     rax, [rsp+88h+arg_20]
0x180001858  mov     [rsp+88h+var_20], r9
0x18000185d  mov     rcx, [rax]
0x180001860  test    rcx, rcx
0x180001863  jz      short loc_180001876
0x180001865  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001869  inc     rax
0x18000186c  cmp     [rcx+rax], r8b
0x180001870  jnz     short loc_180001869
0x180001872  inc     eax
0x180001874  jmp     short loc_180001882
0x180001876  lea     rcx, word_180021D5A
0x18000187d  mov     eax, 1
0x180001882  mov     [rsp+88h+var_30], eax
0x180001886  lea     rax, [rsp+88h+var_58]
0x18000188b  mov     [rsp+88h+var_60], rax
0x180001890  mov     [rsp+88h+var_68], r9d
0x180001895  xor     r9d, r9d
0x180001898  mov     [rsp+88h+var_38], rcx
0x18000189d  lea     rcx, dword_18002B0C0
0x1800018a4  mov     [rsp+88h+var_2C], r8d
0x1800018a9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018ae  mov     rcx, [rsp+88h+var_18]
0x1800018b3  xor     rcx, rsp; StackCookie
0x1800018b6  call    __security_check_cookie
0x1800018bb  add     rsp, 88h
0x1800018c2  retn
```
