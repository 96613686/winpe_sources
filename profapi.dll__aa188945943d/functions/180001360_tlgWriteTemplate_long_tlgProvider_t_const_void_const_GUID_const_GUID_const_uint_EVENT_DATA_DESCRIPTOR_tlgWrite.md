# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001360`
- end: `0x180001421`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800166e0`

## callees

- `0x180001360`
- `0x18000b468`
- `0x18000fa10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6,
        __int64 a7)
{
  int *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v13; // [rsp+50h] [rbp-48h]
  __int64 v14; // [rsp+58h] [rbp-40h]
  int *v15; // [rsp+60h] [rbp-38h]
  int v16; // [rsp+68h] [rbp-30h]
  int v17; // [rsp+6Ch] [rbp-2Ch]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v19 = 8;
  v8 = *a6;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &dword_18001A40C;
    v10 = 2;
  }
  v16 = v10;
  v13 = a5;
  v15 = v8;
  v17 = 0;
  v14 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v12);
}

```

## disassembly

```asm
0x180001360  sub     rsp, 98h
0x180001367  mov     rax, cs:__security_cookie
0x18000136e  xor     rax, rsp
0x180001371  mov     [rsp+98h+var_18], rax
0x180001379  mov     rax, [rsp+98h+arg_30]
0x180001381  mov     r10, rcx
0x180001384  mov     [rsp+98h+var_28], rax
0x180001389  xor     r8d, r8d
0x18000138c  mov     rax, [rsp+98h+arg_28]
0x180001394  mov     [rsp+98h+var_20], 8
0x18000139d  mov     rcx, [rax]
0x1800013a0  test    rcx, rcx
0x1800013a3  jz      short loc_1800013BC
0x1800013a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800013a9  inc     rax
0x1800013ac  cmp     [rcx+rax*2], r8w
0x1800013b1  jnz     short loc_1800013A9
0x1800013b3  lea     eax, ds:2[rax*2]
0x1800013ba  jmp     short loc_1800013C8
0x1800013bc  lea     rcx, dword_18001A40C
0x1800013c3  mov     eax, 2
0x1800013c8  mov     [rsp+98h+var_30], eax
0x1800013cc  xor     r9d, r9d
0x1800013cf  mov     rax, [rsp+98h+arg_20]
0x1800013d7  mov     [rsp+98h+var_48], rax
0x1800013dc  lea     rax, [rsp+98h+var_68]
0x1800013e1  mov     [rsp+98h+var_38], rcx
0x1800013e6  mov     rcx, r10
0x1800013e9  mov     [rsp+98h+var_70], rax
0x1800013ee  mov     [rsp+98h+var_78], 5
0x1800013f6  mov     [rsp+98h+var_2C], r8d
0x1800013fb  mov     [rsp+98h+var_40], 4
0x180001404  call    _tlgWriteTransfer_EventWriteTransfer
0x180001409  mov     rcx, [rsp+98h+var_18]
0x180001411  xor     rcx, rsp; StackCookie
0x180001414  call    __security_check_cookie
0x180001419  add     rsp, 98h
0x180001420  retn
```
