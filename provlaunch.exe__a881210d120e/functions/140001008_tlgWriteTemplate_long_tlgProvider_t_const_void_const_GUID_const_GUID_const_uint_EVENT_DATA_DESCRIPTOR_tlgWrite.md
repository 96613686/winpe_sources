# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x14000111e`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z`
- size: `278`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003bd4`
- `0x1400088ac`
- `0x140008ce4`

## callees

- `0x140001008`
- `0x1400011ac`
- `0x14000a370`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        int **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  int *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int *v16; // rdx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-68h] BYREF
  int *v19; // [rsp+50h] [rbp-48h]
  int v20; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+5Ch] [rbp-3Ch]
  int *v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+68h] [rbp-30h]
  int v24; // [rsp+6Ch] [rbp-2Ch]
  int *v25; // [rsp+70h] [rbp-28h]
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
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_14000C834;
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
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &dword_14000C834;
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
    while ( *((_WORD *)v16 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v16 = &dword_14000C834;
  }
  v19 = v16;
  v20 = v9;
  v21 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140010000, a2, 0, 0, 5u, &v18);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 98h
0x14000100f  mov     rax, cs:__security_cookie
0x140001016  xor     rax, rsp
0x140001019  mov     [rsp+98h+var_18], rax
0x140001021  mov     rax, [rsp+98h+arg_30]
0x140001029  lea     r11, dword_14000C834
0x140001030  mov     r10, rdx
0x140001033  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001037  xor     r9d, r9d
0x14000103a  mov     r8d, 2
0x140001040  mov     rdx, [rax]
0x140001043  test    rdx, rdx
0x140001046  jz      short loc_14000105E
0x140001048  mov     rax, rcx
0x14000104b  inc     rax
0x14000104e  cmp     [rdx+rax*2], r9w
0x140001053  jnz     short loc_14000104B
0x140001055  lea     eax, ds:2[rax*2]
0x14000105c  jmp     short loc_140001064
0x14000105e  mov     rdx, r11
0x140001061  mov     eax, r8d
0x140001064  mov     [rsp+98h+var_20], eax
0x140001068  mov     rax, [rsp+98h+arg_28]
0x140001070  mov     [rsp+98h+var_28], rdx
0x140001075  mov     [rsp+98h+var_1C], r9d
0x14000107a  mov     rdx, [rax]
0x14000107d  test    rdx, rdx
0x140001080  jz      short loc_140001098
0x140001082  mov     rax, rcx
0x140001085  inc     rax
0x140001088  cmp     [rdx+rax*2], r9w
0x14000108d  jnz     short loc_140001085
0x14000108f  lea     eax, ds:2[rax*2]
0x140001096  jmp     short loc_14000109E
0x140001098  mov     rdx, r11
0x14000109b  mov     eax, r8d
0x14000109e  mov     [rsp+98h+var_30], eax
0x1400010a2  mov     rax, [rsp+98h+arg_20]
0x1400010aa  mov     [rsp+98h+var_38], rdx
0x1400010af  mov     [rsp+98h+var_2C], r9d
0x1400010b4  mov     rdx, [rax]
0x1400010b7  test    rdx, rdx
0x1400010ba  jz      short loc_1400010D0
0x1400010bc  inc     rcx
0x1400010bf  cmp     [rdx+rcx*2], r9w
0x1400010c4  jnz     short loc_1400010BC
0x1400010c6  lea     r8d, ds:2[rcx*2]
0x1400010ce  jmp     short loc_1400010D3
0x1400010d0  mov     rdx, r11
0x1400010d3  lea     rax, [rsp+98h+var_68]
0x1400010d8  mov     [rsp+98h+var_48], rdx
0x1400010dd  mov     [rsp+98h+var_40], r8d
0x1400010e2  lea     rcx, dword_140010000
0x1400010e9  mov     [rsp+98h+var_70], rax
0x1400010ee  xor     r8d, r8d
0x1400010f1  mov     rdx, r10
0x1400010f4  mov     [rsp+98h+var_78], 5
0x1400010fc  mov     [rsp+98h+var_3C], r9d
0x140001101  call    _tlgWriteTransfer_EventWriteTransfer
0x140001106  mov     rcx, [rsp+98h+var_18]
0x14000110e  xor     rcx, rsp; StackCookie
0x140001111  call    __security_check_cookie
0x140001116  add     rsp, 98h
0x14000111d  retn
```
