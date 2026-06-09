# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000174c`
- end: `0x18000181c`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c214`

## callees

- `0x1800013c8`
- `0x18000174c`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6)
{
  __int64 v7; // rcx
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // ecx
  _BYTE v14[32]; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v15; // [rsp+50h] [rbp-38h]
  int v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+5Ch] [rbp-2Ch]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-28h]
  int v19; // [rsp+68h] [rbp-20h]
  int v20; // [rsp+6Ch] [rbp-1Ch]

  v7 = -1;
  v8 = *a6;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &dword_18002237C;
    v10 = 2;
  }
  v19 = v10;
  v18 = v8;
  v20 = 0;
  v11 = *a5;
  if ( *a5 )
  {
    do
      ++v7;
    while ( *((_BYTE *)v11 + v7) );
    v12 = v7 + 1;
  }
  else
  {
    v11 = &word_180021D5A;
    v12 = 1;
  }
  v15 = v11;
  v16 = v12;
  v17 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 4, v14);
}

```

## disassembly

```asm
0x18000174c  sub     rsp, 88h
0x180001753  mov     rax, cs:__security_cookie
0x18000175a  xor     rax, rsp
0x18000175d  mov     [rsp+88h+var_18], rax
0x180001762  mov     rax, [rsp+88h+arg_28]
0x18000176a  mov     r10, rdx
0x18000176d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001771  xor     r8d, r8d
0x180001774  mov     rdx, [rax]
0x180001777  test    rdx, rdx
0x18000177a  jz      short loc_180001792
0x18000177c  mov     rax, rcx
0x18000177f  inc     rax
0x180001782  cmp     [rdx+rax*2], r8w
0x180001787  jnz     short loc_18000177F
0x180001789  lea     eax, ds:2[rax*2]
0x180001790  jmp     short loc_18000179E
0x180001792  lea     rdx, dword_18002237C
0x180001799  mov     eax, 2
0x18000179e  mov     [rsp+88h+var_20], eax
0x1800017a2  mov     rax, [rsp+88h+arg_20]
0x1800017aa  mov     [rsp+88h+var_28], rdx
0x1800017af  mov     [rsp+88h+var_1C], r8d
0x1800017b4  mov     rdx, [rax]
0x1800017b7  test    rdx, rdx
0x1800017ba  jz      short loc_1800017C9
0x1800017bc  inc     rcx
0x1800017bf  cmp     [rdx+rcx], r8b
0x1800017c3  jnz     short loc_1800017BC
0x1800017c5  inc     ecx
0x1800017c7  jmp     short loc_1800017D5
0x1800017c9  lea     rdx, word_180021D5A
0x1800017d0  mov     ecx, 1
0x1800017d5  lea     rax, [rsp+88h+var_58]
0x1800017da  mov     [rsp+88h+var_38], rdx
0x1800017df  mov     [rsp+88h+var_30], ecx
0x1800017e3  xor     r9d, r9d
0x1800017e6  mov     [rsp+88h+var_60], rax
0x1800017eb  lea     rcx, dword_18002B0C0
0x1800017f2  mov     rdx, r10
0x1800017f5  mov     [rsp+88h+var_68], 4
0x1800017fd  mov     [rsp+88h+var_2C], r8d
0x180001802  call    _tlgWriteTransfer_EventWriteTransfer
0x180001807  mov     rcx, [rsp+88h+var_18]
0x18000180c  xor     rcx, rsp; StackCookie
0x18000180f  call    __security_check_cookie
0x180001814  add     rsp, 88h
0x18000181b  retn
```
