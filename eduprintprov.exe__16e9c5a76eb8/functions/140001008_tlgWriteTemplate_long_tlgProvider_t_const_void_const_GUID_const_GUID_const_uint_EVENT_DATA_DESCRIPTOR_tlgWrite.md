# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001008`
- end: `0x1400010a9`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d20c`
- `0x14000ddb8`

## callees

- `0x140001008`
- `0x1400016dc`
- `0x140002600`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  int *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]

  v15 = a6;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &dword_140015CE4;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 4u, &v11);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 88h
0x14000100f  mov     rax, cs:__security_cookie
0x140001016  xor     rax, rsp
0x140001019  mov     [rsp+88h+var_18], rax
0x14000101e  mov     rax, [rsp+88h+arg_28]
0x140001026  mov     r10, rcx
0x140001029  mov     [rsp+88h+var_28], rax
0x14000102e  xor     r9d, r9d
0x140001031  mov     rax, [rsp+88h+arg_20]
0x140001039  mov     r11d, 4
0x14000103f  mov     [rsp+88h+var_20], r11
0x140001044  mov     rcx, [rax]
0x140001047  test    rcx, rcx
0x14000104a  jz      short loc_140001063
0x14000104c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001050  inc     rax
0x140001053  cmp     [rcx+rax*2], r9w
0x140001058  jnz     short loc_140001050
0x14000105a  lea     eax, ds:2[rax*2]
0x140001061  jmp     short loc_14000106F
0x140001063  lea     rcx, dword_140015CE4
0x14000106a  mov     eax, 2
0x14000106f  mov     [rsp+88h+var_30], eax
0x140001073  lea     rax, [rsp+88h+var_58]
0x140001078  mov     [rsp+88h+var_38], rcx
0x14000107d  mov     rcx, r10
0x140001080  mov     [rsp+88h+var_60], rax
0x140001085  mov     [rsp+88h+var_68], r11d
0x14000108a  mov     [rsp+88h+var_2C], r9d
0x14000108f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001094  mov     rcx, [rsp+88h+var_18]
0x140001099  xor     rcx, rsp; StackCookie
0x14000109c  call    __security_check_cookie
0x1400010a1  add     rsp, 88h
0x1400010a8  retn
```
