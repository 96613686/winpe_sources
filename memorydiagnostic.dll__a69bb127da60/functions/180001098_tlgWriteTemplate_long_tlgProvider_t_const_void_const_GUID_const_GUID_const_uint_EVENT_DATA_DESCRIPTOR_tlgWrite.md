# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001098`
- end: `0x18000116e`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, int **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004b84`
- `0x180004bfc`
- `0x180004c74`

## callees

- `0x180001098`
- `0x180001a7c`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6)
{
  __int64 v8; // rcx
  int v9; // r8d
  int *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int *v13; // rdx
  _BYTE v15[32]; // [rsp+30h] [rbp-58h] BYREF
  int *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  int *v19; // [rsp+60h] [rbp-28h]
  int v20; // [rsp+68h] [rbp-20h]
  int v21; // [rsp+6Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 2;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_180025214;
    v12 = 2;
  }
  v20 = v12;
  v19 = v10;
  v21 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &dword_180025214;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           4,
           v15);
}

```

## disassembly

```asm
0x180001098  sub     rsp, 88h
0x18000109f  mov     rax, cs:__security_cookie
0x1800010a6  xor     rax, rsp
0x1800010a9  mov     [rsp+88h+var_18], rax
0x1800010ae  mov     rax, [rsp+88h+arg_28]
0x1800010b6  mov     r11, rdx
0x1800010b9  mov     r10, rcx
0x1800010bc  xor     r9d, r9d
0x1800010bf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010c3  mov     r8d, 2
0x1800010c9  mov     rdx, [rax]
0x1800010cc  test    rdx, rdx
0x1800010cf  jz      short loc_1800010E7
0x1800010d1  mov     rax, rcx
0x1800010d4  inc     rax
0x1800010d7  cmp     [rdx+rax*2], r9w
0x1800010dc  jnz     short loc_1800010D4
0x1800010de  lea     eax, ds:2[rax*2]
0x1800010e5  jmp     short loc_1800010F1
0x1800010e7  lea     rdx, dword_180025214
0x1800010ee  mov     eax, r8d
0x1800010f1  mov     [rsp+88h+var_20], eax
0x1800010f5  mov     rax, [rsp+88h+arg_20]
0x1800010fd  mov     [rsp+88h+var_28], rdx
0x180001102  mov     [rsp+88h+var_1C], r9d
0x180001107  mov     rdx, [rax]
0x18000110a  test    rdx, rdx
0x18000110d  jz      short loc_180001123
0x18000110f  inc     rcx
0x180001112  cmp     [rdx+rcx*2], r9w
0x180001117  jnz     short loc_18000110F
0x180001119  lea     r8d, ds:2[rcx*2]
0x180001121  jmp     short loc_18000112A
0x180001123  lea     rdx, dword_180025214
0x18000112a  lea     rax, [rsp+88h+var_58]
0x18000112f  mov     [rsp+88h+var_38], rdx
0x180001134  mov     [rsp+88h+var_30], r8d
0x180001139  mov     rdx, r11
0x18000113c  mov     [rsp+88h+var_60], rax
0x180001141  xor     r8d, r8d
0x180001144  mov     rcx, r10
0x180001147  mov     [rsp+88h+var_68], 4
0x18000114f  mov     [rsp+88h+var_2C], r9d
0x180001154  call    _tlgWriteTransfer_EventWriteTransfer
0x180001159  mov     rcx, [rsp+88h+var_18]
0x18000115e  xor     rcx, rsp; StackCookie
0x180001161  call    __security_check_cookie
0x180001166  add     rsp, 88h
0x18000116d  retn
```
