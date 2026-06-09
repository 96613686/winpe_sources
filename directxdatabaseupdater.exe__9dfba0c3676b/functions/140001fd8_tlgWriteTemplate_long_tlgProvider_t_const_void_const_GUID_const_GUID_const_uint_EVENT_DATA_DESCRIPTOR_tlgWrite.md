# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001fd8`
- end: `0x140002096`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ad00`

## callees

- `0x140001fd8`
- `0x140002318`
- `0x140002f40`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v13; // [rsp+50h] [rbp-48h]
  __int64 v14; // [rsp+58h] [rbp-40h]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 *v17; // [rsp+70h] [rbp-28h]
  int v18; // [rsp+78h] [rbp-20h]
  int v19; // [rsp+7Ch] [rbp-1Ch]

  v8 = *a7;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &qword_14001C2F8;
    v10 = 2;
  }
  v18 = v10;
  v15 = a6;
  v13 = a5;
  v17 = v8;
  v19 = 0;
  v16 = 4;
  v14 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 5, v12);
}

```

## disassembly

```asm
0x140001fd8  sub     rsp, 98h
0x140001fdf  mov     rax, cs:__security_cookie
0x140001fe6  xor     rax, rsp
0x140001fe9  mov     [rsp+98h+var_18], rax
0x140001ff1  mov     rax, [rsp+98h+arg_30]
0x140001ff9  mov     r10, rcx
0x140001ffc  xor     r11d, r11d
0x140001fff  mov     rcx, [rax]
0x140002002  test    rcx, rcx
0x140002005  jz      short loc_14000201E
0x140002007  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000200b  inc     rax
0x14000200e  cmp     [rcx+rax*2], r11w
0x140002013  jnz     short loc_14000200B
0x140002015  lea     eax, ds:2[rax*2]
0x14000201c  jmp     short loc_14000202A
0x14000201e  lea     rcx, qword_14001C2F8
0x140002025  mov     eax, 2
0x14000202a  mov     [rsp+98h+var_20], eax
0x14000202e  mov     rax, [rsp+98h+arg_28]
0x140002036  mov     [rsp+98h+var_38], rax
0x14000203b  mov     rax, [rsp+98h+arg_20]
0x140002043  mov     [rsp+98h+var_48], rax
0x140002048  lea     rax, [rsp+98h+var_68]
0x14000204d  mov     [rsp+98h+var_28], rcx
0x140002052  mov     rcx, r10
0x140002055  mov     [rsp+98h+var_70], rax
0x14000205a  mov     [rsp+98h+var_78], 5
0x140002062  mov     [rsp+98h+var_1C], r11d
0x140002067  mov     [rsp+98h+var_30], 4
0x140002070  mov     [rsp+98h+var_40], 8
0x140002079  call    _tlgWriteTransfer_EventWriteTransfer
0x14000207e  mov     rcx, [rsp+98h+var_18]
0x140002086  xor     rcx, rsp; StackCookie
0x140002089  call    __security_check_cookie
0x14000208e  add     rsp, 98h
0x140002095  retn
```
