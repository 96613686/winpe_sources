# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001308`
- end: `0x1400013a5`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x14001fa90`
- `0x140020168`
- `0x1400203ec`
- `0x140023ba0`
- `0x140024564`
- `0x140024c84`
- `0x140024d88`
- `0x14002537c`
- `0x14002595c`
- `0x14002dd08`
- `0x14002de6c`
- `0x140030da8`
- `0x14003377c`
- `0x140033a3c`
- `0x140034cf8`

## callees

- `0x1400011d8`
- `0x140001308`
- `0x140002f60`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
    v6 = &byte_14005E3A8;
    v8 = 1;
  }
  v14 = v8;
  v13 = v6;
  v11 = a5;
  v12 = 4;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140075078, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x140001308  sub     rsp, 88h
0x14000130f  mov     rax, cs:__security_cookie
0x140001316  xor     rax, rsp
0x140001319  mov     [rsp+88h+var_18], rax
0x14000131e  mov     rax, [rsp+88h+arg_28]
0x140001326  xor     r8d, r8d
0x140001329  mov     rcx, [rax]
0x14000132c  test    rcx, rcx
0x14000132f  jz      short loc_140001342
0x140001331  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001335  inc     rax
0x140001338  cmp     [rcx+rax], r8b
0x14000133c  jnz     short loc_140001335
0x14000133e  inc     eax
0x140001340  jmp     short loc_14000134E
0x140001342  lea     rcx, byte_14005E3A8
0x140001349  mov     eax, 1
0x14000134e  mov     [rsp+88h+var_20], eax
0x140001352  xor     r9d, r9d
0x140001355  mov     rax, [rsp+88h+arg_20]
0x14000135d  mov     [rsp+88h+var_28], rcx
0x140001362  mov     ecx, 4
0x140001367  mov     [rsp+88h+var_38], rax
0x14000136c  lea     rax, [rsp+88h+var_58]
0x140001371  mov     [rsp+88h+var_60], rax
0x140001376  mov     [rsp+88h+var_68], ecx
0x14000137a  mov     [rsp+88h+var_30], rcx
0x14000137f  lea     rcx, dword_140075078
0x140001386  mov     [rsp+88h+var_1C], r8d
0x14000138b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001390  mov     rcx, [rsp+88h+var_18]
0x140001395  xor     rcx, rsp; StackCookie
0x140001398  call    __security_check_cookie
0x14000139d  add     rsp, 88h
0x1400013a4  retn
```
