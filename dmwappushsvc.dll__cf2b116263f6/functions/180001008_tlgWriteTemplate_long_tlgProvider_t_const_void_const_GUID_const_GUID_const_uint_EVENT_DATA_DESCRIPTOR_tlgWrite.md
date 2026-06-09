# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010ed`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperArray@$00@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperArray@$00@@4AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const WCHAR **, __int64 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800030e4`

## callees

- `0x180001008`
- `0x180001158`
- `0x180001a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 *a6,
        __int64 *a7,
        __int64 a8)
{
  int v9; // edx
  const WCHAR *v10; // rcx
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+30h] [rbp-59h] BYREF
  const WCHAR *v14; // [rsp+50h] [rbp-39h]
  int v15; // [rsp+58h] [rbp-31h]
  int v16; // [rsp+5Ch] [rbp-2Dh]
  __int64 *v17; // [rsp+60h] [rbp-29h]
  __int64 v18; // [rsp+68h] [rbp-21h]
  __int64 v19; // [rsp+70h] [rbp-19h]
  int v20; // [rsp+78h] [rbp-11h]
  int v21; // [rsp+7Ch] [rbp-Dh]
  __int64 *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  __int64 v24; // [rsp+90h] [rbp+7h]
  int v25; // [rsp+98h] [rbp+Fh]
  int v26; // [rsp+9Ch] [rbp+13h]
  __int64 v27; // [rsp+A0h] [rbp+17h]
  __int64 v28; // [rsp+A8h] [rbp+1Fh]

  v27 = a8;
  v28 = 4;
  v9 = 2;
  v26 = 0;
  v23 = 2;
  v18 = 2;
  v24 = *a7;
  v25 = *((unsigned __int16 *)a7 + 4);
  v22 = a7 + 1;
  v21 = 0;
  v19 = *a6;
  v20 = *((unsigned __int16 *)a6 + 4);
  v17 = a6 + 1;
  v10 = *a5;
  if ( *a5 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v9 = 2 * v11 + 2;
  }
  else
  {
    v10 = &Source;
  }
  v14 = v10;
  v15 = v9;
  v16 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C048, a2, 0, 0, 8, v13);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-37h]
0x18000100f  sub     rsp, 0C0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+37h+var_10], rax
0x180001024  mov     rax, [rbp+37h+arg_38]
0x180001028  xor     r8d, r8d
0x18000102b  mov     [rbp+37h+var_20], rax
0x18000102f  mov     r10, rdx
0x180001032  mov     rax, [rbp+37h+arg_30]
0x180001036  mov     [rbp+37h+var_18], 4
0x18000103e  lea     edx, [r8+2]
0x180001042  mov     [rbp+37h+var_24], r8d
0x180001046  mov     [rbp+37h+var_38], rdx
0x18000104a  lea     rcx, [rax+8]
0x18000104e  mov     [rbp+37h+var_58], rdx
0x180001052  mov     rax, [rax]
0x180001055  mov     [rbp+37h+var_30], rax
0x180001059  movzx   eax, word ptr [rcx]
0x18000105c  mov     [rbp+37h+var_28], eax
0x18000105f  mov     rax, [rbp+37h+arg_28]
0x180001063  mov     [rbp+37h+var_40], rcx
0x180001067  mov     [rbp+37h+var_44], r8d
0x18000106b  lea     rcx, [rax+8]
0x18000106f  mov     rax, [rax]
0x180001072  mov     [rbp+37h+var_50], rax
0x180001076  movzx   eax, word ptr [rcx]
0x180001079  mov     [rbp+37h+var_48], eax
0x18000107c  mov     rax, [rbp+37h+arg_20]
0x180001080  mov     [rbp+37h+var_60], rcx
0x180001084  mov     rcx, [rax]
0x180001087  test    rcx, rcx
0x18000108a  jz      short loc_1800010A3
0x18000108c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001090  inc     rax
0x180001093  cmp     [rcx+rax*2], r8w
0x180001098  jnz     short loc_180001090
0x18000109a  lea     edx, ds:2[rax*2]
0x1800010a1  jmp     short loc_1800010AA
0x1800010a3  lea     rcx, Source
0x1800010aa  lea     rax, [rbp+37h+var_90]
0x1800010ae  mov     [rbp+37h+var_70], rcx
0x1800010b2  mov     [rbp+37h+var_68], edx
0x1800010b5  lea     rcx, dword_18001C048
0x1800010bc  mov     [rsp+0C0h+var_98], rax
0x1800010c1  xor     r9d, r9d
0x1800010c4  mov     rdx, r10
0x1800010c7  mov     [rsp+0C0h+var_A0], 8
0x1800010cf  mov     [rbp+37h+var_64], r8d
0x1800010d3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010d8  mov     rcx, [rbp+37h+var_10]
0x1800010dc  xor     rcx, rsp; StackCookie
0x1800010df  call    __security_check_cookie
0x1800010e4  add     rsp, 0C0h
0x1800010eb  pop     rbp
0x1800010ec  retn
```
