# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400018cc`
- end: `0x140001987`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `187`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f65c`
- `0x140011250`

## callees

- `0x14000182c`
- `0x1400018cc`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 4;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &word_14001C5D2;
    v9 = 1;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027000, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x1400018cc  mov     r11, rsp
0x1400018cf  sub     rsp, 98h
0x1400018d6  mov     rax, cs:__security_cookie
0x1400018dd  xor     rax, rsp
0x1400018e0  mov     [rsp+98h+var_18], rax
0x1400018e8  mov     rax, [rsp+98h+arg_30]
0x1400018f0  xor     r8d, r8d
0x1400018f3  mov     [r11-28h], rax
0x1400018f7  mov     rax, [rsp+98h+arg_28]
0x1400018ff  mov     [r11-38h], rax
0x140001903  mov     rax, [rsp+98h+arg_20]
0x14000190b  mov     qword ptr [r11-20h], 4
0x140001913  mov     qword ptr [r11-30h], 4
0x14000191b  mov     rcx, [rax]
0x14000191e  test    rcx, rcx
0x140001921  jz      short loc_140001934
0x140001923  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001927  inc     rax
0x14000192a  cmp     [rcx+rax], r8b
0x14000192e  jnz     short loc_140001927
0x140001930  inc     eax
0x140001932  jmp     short loc_140001940
0x140001934  lea     rcx, word_14001C5D2
0x14000193b  mov     eax, 1
0x140001940  mov     [rsp+98h+var_40], eax
0x140001944  xor     r9d, r9d
0x140001947  lea     rax, [rsp+98h+var_68]
0x14000194c  mov     [rsp+98h+var_48], rcx
0x140001951  mov     [rsp+98h+var_70], rax
0x140001956  lea     rcx, dword_140027000
0x14000195d  mov     [rsp+98h+var_78], 5
0x140001965  mov     [rsp+98h+var_3C], r8d
0x14000196a  call    _tlgWriteTransfer_EventWriteTransfer
0x14000196f  mov     rcx, [rsp+98h+var_18]
0x140001977  xor     rcx, rsp; StackCookie
0x14000197a  call    __security_check_cookie
0x14000197f  add     rsp, 98h
0x140001986  retn
```
