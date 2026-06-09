# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x18000111e`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009660`

## callees

- `0x180001008`
- `0x180001124`
- `0x18001ca70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  _BYTE v18[32]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v19; // [rsp+50h] [rbp-48h]
  int v20; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+5Ch] [rbp-3Ch]
  const unsigned __int16 *v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+68h] [rbp-30h]
  int v24; // [rsp+6Ch] [rbp-2Ch]
  const unsigned __int16 *v25; // [rsp+70h] [rbp-28h]
  int v26; // [rsp+78h] [rbp-20h]
  int v27; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 2;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &byte_18002145C;
    v12 = 2;
  }
  v26 = v12;
  v25 = v10;
  v27 = 0;
  v13 = *a6;
  if ( *a6 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &byte_18002145C;
    v15 = 2;
  }
  v23 = v15;
  v22 = v13;
  v24 = 0;
  v16 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( v16[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v16 = &byte_18002145C;
  }
  v19 = v16;
  v20 = v9;
  v21 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180026010, a2, 0, 0, 5, v18);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 98h
0x18000100f  mov     rax, cs:__security_cookie
0x180001016  xor     rax, rsp
0x180001019  mov     [rsp+98h+var_18], rax
0x180001021  mov     rax, [rsp+98h+arg_30]
0x180001029  lea     r11, byte_18002145C
0x180001030  mov     r10, rdx
0x180001033  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001037  xor     r9d, r9d
0x18000103a  mov     r8d, 2
0x180001040  mov     rdx, [rax]
0x180001043  test    rdx, rdx
0x180001046  jz      short loc_18000105E
0x180001048  mov     rax, rcx
0x18000104b  inc     rax
0x18000104e  cmp     [rdx+rax*2], r9w
0x180001053  jnz     short loc_18000104B
0x180001055  lea     eax, ds:2[rax*2]
0x18000105c  jmp     short loc_180001064
0x18000105e  mov     rdx, r11
0x180001061  mov     eax, r8d
0x180001064  mov     [rsp+98h+var_20], eax
0x180001068  mov     rax, [rsp+98h+arg_28]
0x180001070  mov     [rsp+98h+var_28], rdx
0x180001075  mov     [rsp+98h+var_1C], r9d
0x18000107a  mov     rdx, [rax]
0x18000107d  test    rdx, rdx
0x180001080  jz      short loc_180001098
0x180001082  mov     rax, rcx
0x180001085  inc     rax
0x180001088  cmp     [rdx+rax*2], r9w
0x18000108d  jnz     short loc_180001085
0x18000108f  lea     eax, ds:2[rax*2]
0x180001096  jmp     short loc_18000109E
0x180001098  mov     rdx, r11
0x18000109b  mov     eax, r8d
0x18000109e  mov     [rsp+98h+var_30], eax
0x1800010a2  mov     rax, [rsp+98h+arg_20]
0x1800010aa  mov     [rsp+98h+var_38], rdx
0x1800010af  mov     [rsp+98h+var_2C], r9d
0x1800010b4  mov     rdx, [rax]
0x1800010b7  test    rdx, rdx
0x1800010ba  jz      short loc_1800010D0
0x1800010bc  inc     rcx
0x1800010bf  cmp     [rdx+rcx*2], r9w
0x1800010c4  jnz     short loc_1800010BC
0x1800010c6  lea     r8d, ds:2[rcx*2]
0x1800010ce  jmp     short loc_1800010D3
0x1800010d0  mov     rdx, r11
0x1800010d3  lea     rax, [rsp+98h+var_68]
0x1800010d8  mov     [rsp+98h+var_48], rdx
0x1800010dd  mov     [rsp+98h+var_40], r8d
0x1800010e2  lea     rcx, dword_180026010
0x1800010e9  mov     [rsp+98h+var_70], rax
0x1800010ee  xor     r8d, r8d
0x1800010f1  mov     rdx, r10
0x1800010f4  mov     [rsp+98h+var_78], 5
0x1800010fc  mov     [rsp+98h+var_3C], r9d
0x180001101  call    _tlgWriteTransfer_EventWriteTransfer
0x180001106  mov     rcx, [rsp+98h+var_18]
0x18000110e  xor     rcx, rsp; StackCookie
0x180001111  call    __security_check_cookie
0x180001116  add     rsp, 98h
0x18000111d  retn
```
