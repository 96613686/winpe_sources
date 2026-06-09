# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000a7a4`
- end: `0x18000a8aa`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `262`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d980`
- `0x18000e270`
- `0x18000e430`
- `0x18000e4d0`
- `0x18000e570`
- `0x18000ea1c`
- `0x180014750`
- `0x180014bd0`
- `0x180015da0`

## callees

- `0x18000a7a4`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000a877`
- `ntdll!EtwEventWriteTransfer` at `0x18000a877`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  unsigned int v11; // [rsp+30h] [rbp-29h]
  _DWORD v12[2]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h]
  _QWORD v14[5]; // [rsp+50h] [rbp-9h] BYREF
  int v15; // [rsp+78h] [rbp+1Fh]
  int v16; // [rsp+7Ch] [rbp+23h]
  __int64 v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  v17 = a6;
  v18 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_180026E50;
    v9 = 2;
  }
  v15 = v9;
  v12[0] = *a2 << 24;
  v12[1] = *(unsigned __int16 *)(a2 + 1);
  v13 = *(_QWORD *)(a2 + 3);
  v14[0] = *(_QWORD *)(a1 + 8);
  v14[4] = v7;
  v16 = 0;
  v14[1] = *(unsigned __int16 *)v14[0] | 0x200000000LL;
  v14[3] = *(unsigned __int16 *)(a2 + 11) | 0x100000000LL;
  v14[2] = a2 + 11;
  v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v12, a3, a4, 4, v14, v11);
}

```

## disassembly

```asm
0x18000a7a4  push    rbp
0x18000a7a6  lea     rbp, [rsp-47h]
0x18000a7ab  sub     rsp, 0A0h
0x18000a7b2  mov     rax, cs:__security_cookie
0x18000a7b9  xor     rax, rsp
0x18000a7bc  mov     [rbp+47h+var_10], rax
0x18000a7c0  mov     rax, [rbp+47h+arg_28]
0x18000a7c4  mov     r10, rcx
0x18000a7c7  mov     [rbp+47h+var_20], rax
0x18000a7cb  xor     r11d, r11d
0x18000a7ce  mov     rax, [rbp+47h+arg_20]
0x18000a7d2  mov     [rbp+47h+var_18], 4
0x18000a7da  mov     rcx, [rax]
0x18000a7dd  test    rcx, rcx
0x18000a7e0  jz      loc_18000A899
0x18000a7e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a7ea  inc     rax
0x18000a7ed  cmp     [rcx+rax*2], r11w
0x18000a7f2  jnz     short loc_18000A7EA
0x18000a7f4  lea     eax, ds:2[rax*2]
0x18000a7fb  mov     [rbp+47h+var_28], eax
0x18000a7fe  movzx   eax, byte ptr [rdx]
0x18000a801  shl     eax, 18h
0x18000a804  mov     [rbp+47h+var_68], eax
0x18000a807  movzx   eax, word ptr [rdx+1]
0x18000a80b  mov     [rbp+47h+var_64], eax
0x18000a80e  mov     rax, [rdx+3]
0x18000a812  mov     [rbp+47h+var_60], rax
0x18000a816  mov     rax, [r10+8]
0x18000a81a  mov     [rbp+47h+var_50], rax
0x18000a81e  mov     [rbp+47h+var_30], rcx
0x18000a822  lea     rcx, [rdx+0Bh]
0x18000a826  mov     [rbp+47h+var_24], r11d
0x18000a82a  lea     rdx, [rbp+47h+var_68]
0x18000a82e  movzx   eax, word ptr [rax]
0x18000a831  mov     dword ptr [rbp+47h+var_48], eax
0x18000a834  movzx   eax, word ptr [rcx]
0x18000a837  mov     dword ptr [rbp+47h+var_38], eax
0x18000a83a  lea     rax, _TraceLoggingMetadataEnd
0x18000a841  mov     [rbp+47h+var_40], rcx
0x18000a845  lea     rcx, _TraceLoggingMetadata
0x18000a84c  sub     eax, ecx
0x18000a84e  mov     dword ptr [rbp+47h+var_48+4], 2
0x18000a855  mov     dword ptr [rbp+47h+var_38+4], 1
0x18000a85c  mov     [rbp+47h+var_70], eax
0x18000a85f  mov     eax, [rbp+47h+var_70]
0x18000a862  mov     rcx, [r10+20h]
0x18000a866  lea     rax, [rbp+47h+var_50]
0x18000a86a  mov     [rsp+0A0h+var_78], rax
0x18000a86f  mov     [rsp+0A0h+var_80], 4
0x18000a877  call    cs:__imp_EtwEventWriteTransfer
0x18000a87e  nop     dword ptr [rax+rax+00h]
0x18000a883  mov     rcx, [rbp+47h+var_10]
0x18000a887  xor     rcx, rsp; StackCookie
0x18000a88a  call    __security_check_cookie
0x18000a88f  add     rsp, 0A0h
0x18000a896  pop     rbp
0x18000a897  retn
0x18000a899  lea     rcx, qword_180026E50
0x18000a8a0  mov     eax, 2
0x18000a8a5  jmp     loc_18000A7FB
```
