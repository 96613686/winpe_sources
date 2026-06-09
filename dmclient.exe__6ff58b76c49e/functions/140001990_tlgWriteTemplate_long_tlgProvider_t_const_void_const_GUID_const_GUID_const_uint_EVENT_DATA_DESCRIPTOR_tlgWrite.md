# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001990`
- end: `0x140001a7c`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e924`
- `0x14001248c`

## callees

- `0x14000182c`
- `0x140001990`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
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
  _BYTE v15[32]; // [rsp+30h] [rbp-68h] BYREF
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
    v9 = &dword_14001C5D4;
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
    v12 = &word_14001C5D2;
    v13 = 1;
  }
  v16 = v12;
  v17 = v13;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027000, a2, 0, 0, 5, v15);
}

```

## disassembly

```asm
0x140001990  sub     rsp, 98h
0x140001997  mov     rax, cs:__security_cookie
0x14000199e  xor     rax, rsp
0x1400019a1  mov     [rsp+98h+var_18], rax
0x1400019a9  mov     rax, [rsp+98h+arg_30]
0x1400019b1  mov     r10, rdx
0x1400019b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400019b8  xor     r8d, r8d
0x1400019bb  mov     rdx, [rax]
0x1400019be  test    rdx, rdx
0x1400019c1  jz      short loc_1400019D9
0x1400019c3  mov     rax, rcx
0x1400019c6  inc     rax
0x1400019c9  cmp     [rdx+rax*2], r8w
0x1400019ce  jnz     short loc_1400019C6
0x1400019d0  lea     eax, ds:2[rax*2]
0x1400019d7  jmp     short loc_1400019E5
0x1400019d9  lea     rdx, dword_14001C5D4
0x1400019e0  mov     eax, 2
0x1400019e5  mov     [rsp+98h+var_20], eax
0x1400019e9  mov     rax, [rsp+98h+arg_28]
0x1400019f1  mov     [rsp+98h+var_38], rax
0x1400019f6  mov     rax, [rsp+98h+arg_20]
0x1400019fe  mov     [rsp+98h+var_28], rdx
0x140001a03  mov     [rsp+98h+var_1C], r8d
0x140001a08  mov     [rsp+98h+var_30], 4
0x140001a11  mov     rdx, [rax]
0x140001a14  test    rdx, rdx
0x140001a17  jz      short loc_140001A26
0x140001a19  inc     rcx
0x140001a1c  cmp     [rdx+rcx], r8b
0x140001a20  jnz     short loc_140001A19
0x140001a22  inc     ecx
0x140001a24  jmp     short loc_140001A32
0x140001a26  lea     rdx, word_14001C5D2
0x140001a2d  mov     ecx, 1
0x140001a32  lea     rax, [rsp+98h+var_68]
0x140001a37  mov     [rsp+98h+var_48], rdx
0x140001a3c  mov     [rsp+98h+var_40], ecx
0x140001a40  xor     r9d, r9d
0x140001a43  mov     [rsp+98h+var_70], rax
0x140001a48  lea     rcx, dword_140027000
0x140001a4f  mov     rdx, r10
0x140001a52  mov     [rsp+98h+var_78], 5
0x140001a5a  mov     [rsp+98h+var_3C], r8d
0x140001a5f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001a64  mov     rcx, [rsp+98h+var_18]
0x140001a6c  xor     rcx, rsp; StackCookie
0x140001a6f  call    __security_check_cookie
0x140001a74  add     rsp, 98h
0x140001a7b  retn
```
