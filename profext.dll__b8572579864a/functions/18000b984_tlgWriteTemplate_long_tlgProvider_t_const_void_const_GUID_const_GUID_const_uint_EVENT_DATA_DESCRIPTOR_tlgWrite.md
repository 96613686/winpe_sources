# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x18000b984`
- end: `0x18000ba47`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `195`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a2f8`
- `0x18000d610`
- `0x18000d980`
- `0x18000e270`
- `0x18000e650`
- `0x18000ea1c`
- `0x180013d94`
- `0x1800140bc`
- `0x180015da0`

## callees

- `0x180022830`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000ba25`
- `ntdll!EtwEventWriteTransfer` at `0x18000ba25`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v6; // [rsp+30h] [rbp-50h]
  _DWORD v7[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v8; // [rsp+40h] [rbp-40h]
  _QWORD v9[6]; // [rsp+48h] [rbp-38h] BYREF

  v9[4] = a5;
  v7[0] = *a2 << 24;
  v7[1] = *(unsigned __int16 *)(a2 + 1);
  v8 = *(_QWORD *)(a2 + 3);
  v9[0] = *(_QWORD *)(a1 + 8);
  v9[5] = 4;
  v9[1] = *(unsigned __int16 *)v9[0] | 0x200000000LL;
  v9[3] = *(unsigned __int16 *)(a2 + 11) | 0x100000000LL;
  v9[2] = a2 + 11;
  v6 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v7, a3, 0, 3, v9, v6);
}

```

## disassembly

```asm
0x18000b984  push    rbp
0x18000b986  mov     rbp, rsp
0x18000b989  sub     rsp, 80h
0x18000b990  mov     rax, cs:__security_cookie
0x18000b997  xor     rax, rsp
0x18000b99a  mov     [rbp+var_8], rax
0x18000b99e  mov     rax, [rbp+arg_20]
0x18000b9a2  mov     r10, rcx
0x18000b9a5  mov     [rbp+var_18], rax
0x18000b9a9  lea     rcx, [rdx+0Bh]
0x18000b9ad  movzx   eax, byte ptr [rdx]
0x18000b9b0  xor     r9d, r9d
0x18000b9b3  shl     eax, 18h
0x18000b9b6  mov     [rbp+var_48], eax
0x18000b9b9  movzx   eax, word ptr [rdx+1]
0x18000b9bd  mov     [rbp+var_44], eax
0x18000b9c0  mov     rax, [rdx+3]
0x18000b9c4  lea     rdx, [rbp+var_48]
0x18000b9c8  mov     [rbp+var_40], rax
0x18000b9cc  mov     rax, [r10+8]
0x18000b9d0  mov     [rbp+var_38], rax
0x18000b9d4  mov     [rbp+var_10], 4
0x18000b9dc  movzx   eax, word ptr [rax]
0x18000b9df  mov     dword ptr [rbp+var_30], eax
0x18000b9e2  movzx   eax, word ptr [rcx]
0x18000b9e5  mov     dword ptr [rbp+var_20], eax
0x18000b9e8  lea     rax, _TraceLoggingMetadataEnd
0x18000b9ef  mov     [rbp+var_28], rcx
0x18000b9f3  lea     rcx, _TraceLoggingMetadata
0x18000b9fa  sub     eax, ecx
0x18000b9fc  mov     dword ptr [rbp+var_30+4], 2
0x18000ba03  mov     dword ptr [rbp+var_20+4], 1
0x18000ba0a  mov     [rbp+var_50], eax
0x18000ba0d  mov     eax, [rbp+var_50]
0x18000ba10  mov     rcx, [r10+20h]
0x18000ba14  lea     rax, [rbp+var_38]
0x18000ba18  mov     [rsp+80h+var_58], rax
0x18000ba1d  mov     [rsp+80h+var_60], 3
0x18000ba25  call    cs:__imp_EtwEventWriteTransfer
0x18000ba2c  nop     dword ptr [rax+rax+00h]
0x18000ba31  mov     rcx, [rbp+var_8]
0x18000ba35  xor     rcx, rsp; StackCookie
0x18000ba38  call    __security_check_cookie
0x18000ba3d  add     rsp, 80h
0x18000ba44  pop     rbp
0x18000ba45  retn
```
