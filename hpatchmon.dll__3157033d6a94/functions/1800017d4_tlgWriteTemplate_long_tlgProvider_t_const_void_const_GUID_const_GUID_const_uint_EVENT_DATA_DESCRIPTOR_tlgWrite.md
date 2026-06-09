# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800017d4`
- end: `0x180001874`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ffe0`
- `0x180010650`

## callees

- `0x1800011cc`
- `0x1800017d4`
- `0x180002270`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
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
  v15 = 8;
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
0x1800017d4  sub     rsp, 88h
0x1800017db  mov     rax, cs:__security_cookie
0x1800017e2  xor     rax, rsp
0x1800017e5  mov     [rsp+88h+var_18], rax
0x1800017ea  mov     rax, [rsp+88h+arg_28]
0x1800017f2  xor     r8d, r8d
0x1800017f5  mov     [rsp+88h+var_28], rax
0x1800017fa  mov     rax, [rsp+88h+arg_20]
0x180001802  mov     [rsp+88h+var_20], 8
0x18000180b  mov     rcx, [rax]
0x18000180e  test    rcx, rcx
0x180001811  jz      short loc_180001824
0x180001813  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001817  inc     rax
0x18000181a  cmp     [rcx+rax], r8b
0x18000181e  jnz     short loc_180001817
0x180001820  inc     eax
0x180001822  jmp     short loc_180001830
0x180001824  lea     rcx, byte_180016B57
0x18000182b  mov     eax, 1
0x180001830  mov     [rsp+88h+var_30], eax
0x180001834  xor     r9d, r9d
0x180001837  lea     rax, [rsp+88h+var_58]
0x18000183c  mov     [rsp+88h+var_38], rcx
0x180001841  mov     [rsp+88h+var_60], rax
0x180001846  lea     rcx, dword_18001E048
0x18000184d  mov     [rsp+88h+var_68], 4
0x180001855  mov     [rsp+88h+var_2C], r8d
0x18000185a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000185f  mov     rcx, [rsp+88h+var_18]
0x180001864  xor     rcx, rsp; StackCookie
0x180001867  call    __security_check_cookie
0x18000186c  add     rsp, 88h
0x180001873  retn
```
