# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001134`
- end: `0x18000124b`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z`
- size: `279`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008768`
- `0x18000b570`
- `0x18000ba60`

## callees

- `0x180001090`
- `0x180001134`
- `0x18000ccc0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 *v16; // rdx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v19; // [rsp+50h] [rbp-48h]
  int v20; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+5Ch] [rbp-3Ch]
  __int64 *v22; // [rsp+60h] [rbp-38h]
  int v23; // [rsp+68h] [rbp-30h]
  int v24; // [rsp+6Ch] [rbp-2Ch]
  __int64 *v25; // [rsp+70h] [rbp-28h]
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
    v10 = &qword_180010000;
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
    v13 = &qword_180010000;
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
    v16 = &qword_180010000;
  }
  v19 = v16;
  v20 = v9;
  v21 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, a2, 0, 0, 5u, &v18);
}

```

## disassembly

```asm
0x180001134  sub     rsp, 98h
0x18000113b  mov     rax, cs:__security_cookie
0x180001142  xor     rax, rsp
0x180001145  mov     [rsp+98h+var_18], rax
0x18000114d  mov     rax, [rsp+98h+arg_30]
0x180001155  lea     r11, qword_180010000
0x18000115c  mov     r10, rdx
0x18000115f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001163  xor     r9d, r9d
0x180001166  mov     r8d, 2
0x18000116c  mov     rdx, [rax]
0x18000116f  test    rdx, rdx
0x180001172  jz      short loc_18000118A
0x180001174  mov     rax, rcx
0x180001177  inc     rax
0x18000117a  cmp     [rdx+rax*2], r9w
0x18000117f  jnz     short loc_180001177
0x180001181  lea     eax, ds:2[rax*2]
0x180001188  jmp     short loc_180001190
0x18000118a  mov     rdx, r11
0x18000118d  mov     eax, r8d
0x180001190  mov     [rsp+98h+var_20], eax
0x180001194  mov     rax, [rsp+98h+arg_28]
0x18000119c  mov     [rsp+98h+var_28], rdx
0x1800011a1  mov     [rsp+98h+var_1C], r9d
0x1800011a6  mov     rdx, [rax]
0x1800011a9  test    rdx, rdx
0x1800011ac  jz      short loc_1800011C4
0x1800011ae  mov     rax, rcx
0x1800011b1  inc     rax
0x1800011b4  cmp     [rdx+rax*2], r9w
0x1800011b9  jnz     short loc_1800011B1
0x1800011bb  lea     eax, ds:2[rax*2]
0x1800011c2  jmp     short loc_1800011CA
0x1800011c4  mov     rdx, r11
0x1800011c7  mov     eax, r8d
0x1800011ca  mov     [rsp+98h+var_30], eax
0x1800011ce  mov     rax, [rsp+98h+arg_20]
0x1800011d6  mov     [rsp+98h+var_38], rdx
0x1800011db  mov     [rsp+98h+var_2C], r9d
0x1800011e0  mov     rdx, [rax]
0x1800011e3  test    rdx, rdx
0x1800011e6  jz      short loc_1800011FC
0x1800011e8  inc     rcx
0x1800011eb  cmp     [rdx+rcx*2], r9w
0x1800011f0  jnz     short loc_1800011E8
0x1800011f2  lea     r8d, ds:2[rcx*2]
0x1800011fa  jmp     short loc_1800011FF
0x1800011fc  mov     rdx, r11
0x1800011ff  lea     rax, [rsp+98h+var_68]
0x180001204  mov     [rsp+98h+var_48], rdx
0x180001209  mov     [rsp+98h+var_40], r8d
0x18000120e  lea     rcx, dword_180014230
0x180001215  mov     [rsp+98h+var_70], rax
0x18000121a  xor     r8d, r8d
0x18000121d  mov     rdx, r10
0x180001220  mov     [rsp+98h+var_78], 5
0x180001228  mov     [rsp+98h+var_3C], r9d
0x18000122d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001232  mov     rcx, [rsp+98h+var_18]
0x18000123a  xor     rcx, rsp; StackCookie
0x18000123d  call    __security_check_cookie
0x180001242  add     rsp, 98h
0x180001249  retn
```
