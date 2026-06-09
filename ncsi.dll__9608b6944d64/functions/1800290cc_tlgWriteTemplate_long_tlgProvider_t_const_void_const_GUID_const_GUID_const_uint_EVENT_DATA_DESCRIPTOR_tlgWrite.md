# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x1800290cc`
- end: `0x1800291cc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003bc20`
- `0x18003c2b0`
- `0x18003c4c0`

## callees

- `0x1800290cc`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800291a2`
- `ntdll!EtwEventWriteTransfer` at `0x1800291a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _DWORD v10[2]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h]
  __int16 *v12; // [rsp+50h] [rbp-9h] BYREF
  int v13; // [rsp+58h] [rbp-1h]
  int v14; // [rsp+5Ch] [rbp+3h]
  unsigned __int8 *v15; // [rsp+60h] [rbp+7h]
  int v16; // [rsp+68h] [rbp+Fh]
  int v17; // [rsp+6Ch] [rbp+13h]
  __int64 v18; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]
  const unsigned __int16 *v20; // [rsp+80h] [rbp+27h]
  int v21; // [rsp+88h] [rbp+2Fh]
  int v22; // [rsp+8Ch] [rbp+33h]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &qword_18007F760;
    v8 = 1;
  }
  v21 = v8;
  v18 = a5;
  v10[0] = *a2 << 24;
  v10[1] = *(unsigned __int16 *)(a2 + 1);
  v11 = *(_QWORD *)(a2 + 3);
  v12 = off_18009A050;
  v20 = v6;
  v22 = 0;
  v19 = 8;
  v13 = (unsigned __int16)*off_18009A050;
  v16 = *(unsigned __int16 *)(a2 + 11);
  v15 = a2 + 11;
  v17 = 1;
  v14 = 2;
  return EtwEventWriteTransfer(RegHandle, v10, 0, 0, 4, &v12);
}

```

## disassembly

```asm
0x1800290cc  push    rbp
0x1800290ce  lea     rbp, [rsp-47h]
0x1800290d3  sub     rsp, 0A0h
0x1800290da  mov     rax, cs:__security_cookie
0x1800290e1  xor     rax, rsp
0x1800290e4  mov     [rbp+47h+var_10], rax
0x1800290e8  mov     rax, [rbp+47h+arg_28]
0x1800290ec  xor     r8d, r8d
0x1800290ef  mov     r9d, 1
0x1800290f5  mov     rcx, [rax]
0x1800290f8  test    rcx, rcx
0x1800290fb  jz      loc_1800291BD
0x180029101  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029105  inc     rax
0x180029108  cmp     [rcx+rax], r8b
0x18002910c  jnz     short loc_180029105
0x18002910e  inc     eax
0x180029110  mov     [rbp+47h+var_18], eax
0x180029113  mov     rax, [rbp+47h+arg_20]
0x180029117  mov     [rbp+47h+var_30], rax
0x18002911b  movzx   eax, byte ptr [rdx]
0x18002911e  shl     eax, 18h
0x180029121  mov     [rbp+47h+var_68], eax
0x180029124  movzx   eax, word ptr [rdx+1]
0x180029128  mov     [rbp+47h+var_64], eax
0x18002912b  mov     rax, [rdx+3]
0x18002912f  mov     [rbp+47h+var_60], rax
0x180029133  mov     rax, cs:off_18009A050
0x18002913a  mov     [rbp+47h+var_50], rax
0x18002913e  mov     [rbp+47h+var_20], rcx
0x180029142  lea     rcx, [rdx+0Bh]
0x180029146  mov     [rbp+47h+var_14], r8d
0x18002914a  lea     rdx, [rbp+47h+var_68]
0x18002914e  mov     [rbp+47h+var_28], 8
0x180029156  movzx   eax, word ptr [rax]
0x180029159  mov     [rbp+47h+var_48], eax
0x18002915c  movzx   eax, word ptr [rcx]
0x18002915f  mov     [rbp+47h+var_38], eax
0x180029162  lea     rax, _TraceLoggingMetadataEnd
0x180029169  mov     [rbp+47h+var_40], rcx
0x18002916d  lea     rcx, _TraceLoggingMetadata
0x180029174  sub     eax, ecx
0x180029176  mov     [rbp+47h+var_34], r9d
0x18002917a  mov     [rbp+47h+var_44], 2
0x180029181  xor     r9d, r9d
0x180029184  mov     [rbp+47h+var_70], eax
0x180029187  mov     eax, [rbp+47h+var_70]
0x18002918a  mov     rcx, cs:RegHandle
0x180029191  lea     rax, [rbp+47h+var_50]
0x180029195  mov     [rsp+0A0h+var_78], rax
0x18002919a  mov     [rsp+0A0h+var_80], 4
0x1800291a2  call    cs:__imp_EtwEventWriteTransfer
0x1800291a8  mov     rcx, [rbp+47h+var_10]
0x1800291ac  xor     rcx, rsp; StackCookie
0x1800291af  call    __security_check_cookie
0x1800291b4  add     rsp, 0A0h
0x1800291bb  pop     rbp
0x1800291bc  retn
0x1800291bd  lea     rcx, qword_18007F760
0x1800291c4  mov     eax, r9d
0x1800291c7  jmp     loc_180029110
```
