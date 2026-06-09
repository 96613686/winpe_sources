# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001a84`
- end: `0x140001b93`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, int **, int **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010e70`

## callees

- `0x14000182c`
- `0x140001a84`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        int **a6,
        int **a7,
        __int64 a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  int *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int *v14; // rdx
  __int64 v15; // rax
  const unsigned __int16 *v16; // rdx
  int v17; // ecx
  _BYTE v19[32]; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-19h]
  int v21; // [rsp+58h] [rbp-11h]
  int v22; // [rsp+5Ch] [rbp-Dh]
  int *v23; // [rsp+60h] [rbp-9h]
  int v24; // [rsp+68h] [rbp-1h]
  int v25; // [rsp+6Ch] [rbp+3h]
  int *v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  int v28; // [rsp+7Ch] [rbp+13h]
  __int64 v29; // [rsp+80h] [rbp+17h]
  __int64 v30; // [rsp+88h] [rbp+1Fh]

  v29 = a8;
  v9 = -1;
  v30 = 4;
  v10 = 2;
  v11 = *a7;
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_14001C5D4;
    v13 = 2;
  }
  v27 = v13;
  v26 = v11;
  v28 = 0;
  v14 = *a6;
  if ( *a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v10 = 2 * v15 + 2;
  }
  else
  {
    v14 = &dword_14001C5D4;
  }
  v23 = v14;
  v24 = v10;
  v25 = 0;
  v16 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v16 + v9) );
    v17 = v9 + 1;
  }
  else
  {
    v16 = &word_14001C5D2;
    v17 = 1;
  }
  v20 = v16;
  v21 = v17;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027000, a2, 0, 0, 6, v19);
}

```

## disassembly

```asm
0x140001a84  push    rbp
0x140001a86  lea     rbp, [rsp-37h]
0x140001a8b  sub     rsp, 0A0h
0x140001a92  mov     rax, cs:__security_cookie
0x140001a99  xor     rax, rsp
0x140001a9c  mov     [rbp+37h+var_10], rax
0x140001aa0  mov     rax, [rbp+37h+arg_38]
0x140001aa4  xor     r9d, r9d
0x140001aa7  mov     [rbp+37h+var_20], rax
0x140001aab  mov     r10, rdx
0x140001aae  mov     rax, [rbp+37h+arg_30]
0x140001ab2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001ab6  mov     [rbp+37h+var_18], 4
0x140001abe  lea     r8d, [r9+2]
0x140001ac2  mov     rdx, [rax]
0x140001ac5  test    rdx, rdx
0x140001ac8  jz      short loc_140001AE0
0x140001aca  mov     rax, rcx
0x140001acd  inc     rax
0x140001ad0  cmp     [rdx+rax*2], r9w
0x140001ad5  jnz     short loc_140001ACD
0x140001ad7  lea     eax, ds:2[rax*2]
0x140001ade  jmp     short loc_140001AEA
0x140001ae0  lea     rdx, dword_14001C5D4
0x140001ae7  mov     eax, r8d
0x140001aea  mov     [rbp+37h+var_28], eax
0x140001aed  mov     rax, [rbp+37h+arg_28]
0x140001af1  mov     [rbp+37h+var_30], rdx
0x140001af5  mov     [rbp+37h+var_24], r9d
0x140001af9  mov     rdx, [rax]
0x140001afc  test    rdx, rdx
0x140001aff  jz      short loc_140001B18
0x140001b01  mov     rax, rcx
0x140001b04  inc     rax
0x140001b07  cmp     [rdx+rax*2], r9w
0x140001b0c  jnz     short loc_140001B04
0x140001b0e  lea     r8d, ds:2[rax*2]
0x140001b16  jmp     short loc_140001B1F
0x140001b18  lea     rdx, dword_14001C5D4
0x140001b1f  mov     rax, [rbp+37h+arg_20]
0x140001b23  mov     [rbp+37h+var_40], rdx
0x140001b27  mov     [rbp+37h+var_38], r8d
0x140001b2b  mov     [rbp+37h+var_34], r9d
0x140001b2f  mov     rdx, [rax]
0x140001b32  test    rdx, rdx
0x140001b35  jz      short loc_140001B44
0x140001b37  inc     rcx
0x140001b3a  cmp     [rdx+rcx], r9b
0x140001b3e  jnz     short loc_140001B37
0x140001b40  inc     ecx
0x140001b42  jmp     short loc_140001B50
0x140001b44  lea     rdx, word_14001C5D2
0x140001b4b  mov     ecx, 1
0x140001b50  lea     rax, [rbp+37h+var_70]
0x140001b54  mov     [rbp+37h+var_50], rdx
0x140001b58  mov     [rbp+37h+var_48], ecx
0x140001b5b  xor     r8d, r8d
0x140001b5e  mov     [rsp+0A0h+var_78], rax
0x140001b63  lea     rcx, dword_140027000
0x140001b6a  mov     rdx, r10
0x140001b6d  mov     [rsp+0A0h+var_80], 6
0x140001b75  mov     [rbp+37h+var_44], r9d
0x140001b79  call    _tlgWriteTransfer_EventWriteTransfer
0x140001b7e  mov     rcx, [rbp+37h+var_10]
0x140001b82  xor     rcx, rsp; StackCookie
0x140001b85  call    __security_check_cookie
0x140001b8a  add     rsp, 0A0h
0x140001b91  pop     rbp
0x140001b92  retn
```
