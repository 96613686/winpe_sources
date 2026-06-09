# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180029cf4`
- end: `0x180029db6`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d09c`
- `0x1800150f8`
- `0x1800324f8`
- `0x180032558`
- `0x180052b04`
- `0x18005d170`
- `0x18005fc84`
- `0x180060250`
- `0x18006082c`
- `0x18007a1af`
- `0x18007a1fc`

## callees

- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180029d9b`
- `ntdll!EtwEventWriteTransfer` at `0x180029d9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _DWORD v6[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v7; // [rsp+40h] [rbp-40h]
  __int16 *v8; // [rsp+48h] [rbp-38h] BYREF
  int v9; // [rsp+50h] [rbp-30h]
  int v10; // [rsp+54h] [rbp-2Ch]
  unsigned __int8 *v11; // [rsp+58h] [rbp-28h]
  int v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+64h] [rbp-1Ch]
  __int64 v14; // [rsp+68h] [rbp-18h]
  __int64 v15; // [rsp+70h] [rbp-10h]

  v14 = a5;
  v6[0] = *a2 << 24;
  v6[1] = *(unsigned __int16 *)(a2 + 1);
  v7 = *(_QWORD *)(a2 + 3);
  v8 = off_18009A050;
  v15 = 4;
  v9 = (unsigned __int16)*off_18009A050;
  v12 = *(unsigned __int16 *)(a2 + 11);
  v11 = a2 + 11;
  v10 = 2;
  v13 = 1;
  return EtwEventWriteTransfer(RegHandle, v6, 0, 0, 3, &v8);
}

```

## disassembly

```asm
0x180029cf4  push    rbp
0x180029cf6  mov     rbp, rsp
0x180029cf9  sub     rsp, 80h
0x180029d00  mov     rax, cs:__security_cookie
0x180029d07  xor     rax, rsp
0x180029d0a  mov     [rbp+var_8], rax
0x180029d0e  mov     rax, [rbp+arg_20]
0x180029d12  lea     rcx, [rdx+0Bh]
0x180029d16  mov     [rbp+var_18], rax
0x180029d1a  xor     r9d, r9d
0x180029d1d  movzx   eax, byte ptr [rdx]
0x180029d20  xor     r8d, r8d
0x180029d23  shl     eax, 18h
0x180029d26  mov     [rbp+var_48], eax
0x180029d29  movzx   eax, word ptr [rdx+1]
0x180029d2d  mov     [rbp+var_44], eax
0x180029d30  mov     rax, [rdx+3]
0x180029d34  lea     rdx, [rbp+var_48]
0x180029d38  mov     [rbp+var_40], rax
0x180029d3c  mov     rax, cs:off_18009A050
0x180029d43  mov     [rbp+var_38], rax
0x180029d47  mov     [rbp+var_10], 4
0x180029d4f  movzx   eax, word ptr [rax]
0x180029d52  mov     [rbp+var_30], eax
0x180029d55  movzx   eax, word ptr [rcx]
0x180029d58  mov     [rbp+var_20], eax
0x180029d5b  lea     rax, _TraceLoggingMetadataEnd
0x180029d62  mov     [rbp+var_28], rcx
0x180029d66  lea     rcx, _TraceLoggingMetadata
0x180029d6d  sub     eax, ecx
0x180029d6f  mov     [rbp+var_2C], 2
0x180029d76  mov     [rbp+var_1C], 1
0x180029d7d  mov     [rbp+var_50], eax
0x180029d80  mov     eax, [rbp+var_50]
0x180029d83  mov     rcx, cs:RegHandle
0x180029d8a  lea     rax, [rbp+var_38]
0x180029d8e  mov     [rsp+80h+var_58], rax
0x180029d93  mov     [rsp+80h+var_60], 3
0x180029d9b  call    cs:__imp_EtwEventWriteTransfer
0x180029da1  mov     rcx, [rbp+var_8]
0x180029da5  xor     rcx, rsp; StackCookie
0x180029da8  call    __security_check_cookie
0x180029dad  add     rsp, 80h
0x180029db4  pop     rbp
0x180029db5  retn
```
