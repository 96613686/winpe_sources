# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000132c`
- end: `0x180001418`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, char **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010404`
- `0x180010db4`

## callees

- `0x1800011e4`
- `0x18000132c`
- `0x180001cf0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        char **a6,
        __int64 a7)
{
  __int64 v8; // rdx
  char *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  int v13; // edx
  _BYTE v15[32]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  char *v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+6Ch] [rbp-2Ch]
  __int64 v22; // [rsp+70h] [rbp-28h]
  __int64 v23; // [rsp+78h] [rbp-20h]

  v22 = a7;
  v8 = -1;
  v23 = 4;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v9[2 * v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = byte_180016578;
    v11 = 2;
  }
  v20 = v11;
  v19 = v9;
  v21 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v12 + v8) );
    v13 = v8 + 1;
  }
  else
  {
    v12 = &qword_1800162C0;
    v13 = 1;
  }
  v16 = v12;
  v17 = v13;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001B0E8, a2, 0, 0, 5, v15);
}

```

## disassembly

```asm
0x18000132c  sub     rsp, 98h
0x180001333  mov     rax, cs:__security_cookie
0x18000133a  xor     rax, rsp
0x18000133d  mov     [rsp+98h+var_18], rax
0x180001345  mov     rax, [rsp+98h+arg_30]
0x18000134d  mov     r10, rdx
0x180001350  mov     [rsp+98h+var_28], rax
0x180001355  xor     r8d, r8d
0x180001358  mov     rax, [rsp+98h+arg_28]
0x180001360  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001364  mov     [rsp+98h+var_20], 4
0x18000136d  mov     rcx, [rax]
0x180001370  test    rcx, rcx
0x180001373  jz      short loc_18000138B
0x180001375  mov     rax, rdx
0x180001378  inc     rax
0x18000137b  cmp     [rcx+rax*2], r8w
0x180001380  jnz     short loc_180001378
0x180001382  lea     eax, ds:2[rax*2]
0x180001389  jmp     short loc_180001397
0x18000138b  lea     rcx, byte_180016578
0x180001392  mov     eax, 2
0x180001397  mov     [rsp+98h+var_30], eax
0x18000139b  mov     rax, [rsp+98h+arg_20]
0x1800013a3  mov     [rsp+98h+var_38], rcx
0x1800013a8  mov     [rsp+98h+var_2C], r8d
0x1800013ad  mov     rcx, [rax]
0x1800013b0  test    rcx, rcx
0x1800013b3  jz      short loc_1800013C2
0x1800013b5  inc     rdx
0x1800013b8  cmp     [rcx+rdx], r8b
0x1800013bc  jnz     short loc_1800013B5
0x1800013be  inc     edx
0x1800013c0  jmp     short loc_1800013CE
0x1800013c2  lea     rcx, qword_1800162C0
0x1800013c9  mov     edx, 1
0x1800013ce  lea     rax, [rsp+98h+var_68]
0x1800013d3  mov     [rsp+98h+var_48], rcx
0x1800013d8  mov     [rsp+98h+var_40], edx
0x1800013dc  lea     rcx, dword_18001B0E8
0x1800013e3  mov     [rsp+98h+var_70], rax
0x1800013e8  xor     r9d, r9d
0x1800013eb  mov     rdx, r10
0x1800013ee  mov     [rsp+98h+var_78], 5
0x1800013f6  mov     [rsp+98h+var_3C], r8d
0x1800013fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001400  mov     rcx, [rsp+98h+var_18]
0x180001408  xor     rcx, rsp; StackCookie
0x18000140b  call    __security_check_cookie
0x180001410  add     rsp, 98h
0x180001417  retn
```
