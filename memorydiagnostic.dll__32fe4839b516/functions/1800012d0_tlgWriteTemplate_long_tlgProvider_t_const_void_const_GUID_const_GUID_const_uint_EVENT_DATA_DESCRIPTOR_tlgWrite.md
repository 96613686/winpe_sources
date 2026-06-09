# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800012d0`
- end: `0x180001391`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `193`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f2c`
- `0x180003fbc`
- `0x1800041a8`
- `0x180004238`

## callees

- `0x1800012d0`
- `0x180001a8c`
- `0x1800026b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        __int64 a6,
        __int64 a7)
{
  _WORD *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-68h] BYREF
  _WORD *v13; // [rsp+50h] [rbp-48h]
  int v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+5Ch] [rbp-3Ch]
  __int64 v16; // [rsp+60h] [rbp-38h]
  __int64 v17; // [rsp+68h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v19 = 8;
  v17 = 8;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &unk_1800261C4;
    v10 = 2;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5u, &v12);
}

```

## disassembly

```asm
0x1800012d0  mov     r11, rsp
0x1800012d3  sub     rsp, 98h
0x1800012da  mov     rax, cs:__security_cookie
0x1800012e1  xor     rax, rsp
0x1800012e4  mov     [rsp+98h+var_18], rax
0x1800012ec  mov     rax, [rsp+98h+arg_30]
0x1800012f4  mov     r10, rcx
0x1800012f7  mov     [r11-28h], rax
0x1800012fb  xor     r8d, r8d
0x1800012fe  mov     rax, [rsp+98h+arg_28]
0x180001306  mov     [r11-38h], rax
0x18000130a  mov     rax, [rsp+98h+arg_20]
0x180001312  mov     qword ptr [r11-20h], 8
0x18000131a  mov     qword ptr [r11-30h], 8
0x180001322  mov     rcx, [rax]
0x180001325  test    rcx, rcx
0x180001328  jz      short loc_180001341
0x18000132a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000132e  inc     rax
0x180001331  cmp     [rcx+rax*2], r8w
0x180001336  jnz     short loc_18000132E
0x180001338  lea     eax, ds:2[rax*2]
0x18000133f  jmp     short loc_18000134D
0x180001341  lea     rcx, unk_1800261C4
0x180001348  mov     eax, 2
0x18000134d  mov     [rsp+98h+var_40], eax
0x180001351  xor     r9d, r9d
0x180001354  lea     rax, [rsp+98h+var_68]
0x180001359  mov     [rsp+98h+var_48], rcx
0x18000135e  mov     [rsp+98h+var_70], rax
0x180001363  mov     rcx, r10
0x180001366  mov     [rsp+98h+var_78], 5
0x18000136e  mov     [rsp+98h+var_3C], r8d
0x180001373  call    _tlgWriteTransfer_EventWriteTransfer
0x180001378  mov     rcx, [rsp+98h+var_18]
0x180001380  xor     rcx, rsp; StackCookie
0x180001383  call    __security_check_cookie
0x180001388  add     rsp, 98h
0x18000138f  retn
```
