# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400019a8`
- end: `0x140001a95`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ee98`
- `0x140012e10`

## callees

- `0x140001840`
- `0x1400019a8`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        int **a7)
{
  __int64 v8; // rcx
  int *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // ecx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  __int64 v19; // [rsp+60h] [rbp-38h]
  __int64 v20; // [rsp+68h] [rbp-30h]
  int *v21; // [rsp+70h] [rbp-28h]
  int v22; // [rsp+78h] [rbp-20h]
  int v23; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = *a7;
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &dword_14001D5D4;
    v11 = 2;
  }
  v22 = v11;
  v19 = a6;
  v21 = v9;
  v23 = 0;
  v20 = 4;
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
    v12 = &word_14001D5D2;
    v13 = 1;
  }
  v16 = v12;
  v17 = v13;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x1400019a8  sub     rsp, 98h
0x1400019af  mov     rax, cs:__security_cookie
0x1400019b6  xor     rax, rsp
0x1400019b9  mov     [rsp+98h+var_18], rax
0x1400019c1  mov     rax, [rsp+98h+arg_30]
0x1400019c9  mov     r10, rdx
0x1400019cc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400019d0  xor     r8d, r8d
0x1400019d3  mov     rdx, [rax]
0x1400019d6  test    rdx, rdx
0x1400019d9  jz      short loc_1400019F1
0x1400019db  mov     rax, rcx
0x1400019de  inc     rax
0x1400019e1  cmp     [rdx+rax*2], r8w
0x1400019e6  jnz     short loc_1400019DE
0x1400019e8  lea     eax, ds:2[rax*2]
0x1400019ef  jmp     short loc_1400019FD
0x1400019f1  lea     rdx, dword_14001D5D4
0x1400019f8  mov     eax, 2
0x1400019fd  mov     [rsp+98h+var_20], eax
0x140001a01  mov     rax, [rsp+98h+arg_28]
0x140001a09  mov     [rsp+98h+var_38], rax
0x140001a0e  mov     rax, [rsp+98h+arg_20]
0x140001a16  mov     [rsp+98h+var_28], rdx
0x140001a1b  mov     [rsp+98h+var_1C], r8d
0x140001a20  mov     [rsp+98h+var_30], 4
0x140001a29  mov     rdx, [rax]
0x140001a2c  test    rdx, rdx
0x140001a2f  jz      short loc_140001A3E
0x140001a31  inc     rcx
0x140001a34  cmp     [rdx+rcx], r8b
0x140001a38  jnz     short loc_140001A31
0x140001a3a  inc     ecx
0x140001a3c  jmp     short loc_140001A4A
0x140001a3e  lea     rdx, word_14001D5D2
0x140001a45  mov     ecx, 1
0x140001a4a  lea     rax, [rsp+98h+var_68]
0x140001a4f  mov     [rsp+98h+var_48], rdx
0x140001a54  mov     [rsp+98h+var_40], ecx
0x140001a58  xor     r9d, r9d
0x140001a5b  mov     [rsp+98h+var_70], rax
0x140001a60  lea     rcx, dword_140028000
0x140001a67  mov     rdx, r10
0x140001a6a  mov     [rsp+98h+var_78], 5
0x140001a72  mov     [rsp+98h+var_3C], r8d
0x140001a77  call    _tlgWriteTransfer_EventWriteTransfer
0x140001a7c  mov     rcx, [rsp+98h+var_18]
0x140001a84  xor     rcx, rsp; StackCookie
0x140001a87  call    __security_check_cookie
0x140001a8c  add     rsp, 98h
0x140001a93  retn
```
