# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x18000113c`
- end: `0x1800011dc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e8a8`
- `0x18000e91c`

## callees

- `0x18000113c`
- `0x1800011e4`
- `0x180001cf0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
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
  v14 = v8;
  v11 = a5;
  v13 = v6;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001B060, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x18000113c  sub     rsp, 88h
0x180001143  mov     rax, cs:__security_cookie
0x18000114a  xor     rax, rsp
0x18000114d  mov     [rsp+88h+var_18], rax
0x180001152  mov     rax, [rsp+88h+arg_28]
0x18000115a  xor     r8d, r8d
0x18000115d  mov     rcx, [rax]
0x180001160  test    rcx, rcx
0x180001163  jz      short loc_180001176
0x180001165  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001169  inc     rax
0x18000116c  cmp     [rcx+rax], r8b
0x180001170  jnz     short loc_180001169
0x180001172  inc     eax
0x180001174  jmp     short loc_180001182
0x180001176  lea     rcx, qword_1800162C0
0x18000117d  mov     eax, 1
0x180001182  mov     [rsp+88h+var_20], eax
0x180001186  xor     r9d, r9d
0x180001189  mov     rax, [rsp+88h+arg_20]
0x180001191  mov     [rsp+88h+var_38], rax
0x180001196  lea     rax, [rsp+88h+var_58]
0x18000119b  mov     [rsp+88h+var_28], rcx
0x1800011a0  lea     rcx, dword_18001B060
0x1800011a7  mov     [rsp+88h+var_60], rax
0x1800011ac  mov     [rsp+88h+var_68], 4
0x1800011b4  mov     [rsp+88h+var_1C], r8d
0x1800011b9  mov     [rsp+88h+var_30], 8
0x1800011c2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011c7  mov     rcx, [rsp+88h+var_18]
0x1800011cc  xor     rcx, rsp; StackCookie
0x1800011cf  call    __security_check_cookie
0x1800011d4  add     rsp, 88h
0x1800011db  retn
```
