# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x18002a048`
- end: `0x18002a0f7`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `175`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *)`
- caller_count: `16`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800150f8`
- `0x180032428`
- `0x180032474`
- `0x1800324f8`
- `0x180037ac4`
- `0x18004c6a8`
- `0x18004c728`
- `0x180052b04`
- `0x18005d170`
- `0x18005fc84`
- `0x180060220`
- `0x1800650b0`
- `0x1800674f8`
- `0x18006768c`
- `0x180067a00`
- `0x18007a70f`

## callees

- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002a0df`
- `ntdll!EtwEventWriteTransfer` at `0x18002a0df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2)
{
  int v2; // eax
  _DWORD v4[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v5; // [rsp+40h] [rbp-38h]
  __int16 *v6; // [rsp+48h] [rbp-30h] BYREF
  int v7; // [rsp+50h] [rbp-28h]
  int v8; // [rsp+54h] [rbp-24h]
  unsigned __int8 *v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+60h] [rbp-18h]
  int v11; // [rsp+64h] [rbp-14h]

  v4[0] = *a2 << 24;
  v4[1] = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = off_18009A050;
  v7 = (unsigned __int16)*off_18009A050;
  v2 = *(unsigned __int16 *)(a2 + 11);
  v8 = 2;
  v9 = a2 + 11;
  v10 = v2;
  v11 = 1;
  return EtwEventWriteTransfer(RegHandle, v4, 0, 0, 2, &v6);
}

```

## disassembly

```asm
0x18002a048  mov     r11, rsp
0x18002a04b  sub     rsp, 78h
0x18002a04f  mov     rax, cs:__security_cookie
0x18002a056  xor     rax, rsp
0x18002a059  mov     [rsp+78h+var_10], rax
0x18002a05e  movzx   eax, byte ptr [rdx]
0x18002a061  lea     rcx, [rdx+0Bh]
0x18002a065  shl     eax, 18h
0x18002a068  xor     r9d, r9d
0x18002a06b  mov     [rsp+78h+var_40], eax
0x18002a06f  xor     r8d, r8d
0x18002a072  movzx   eax, word ptr [rdx+1]
0x18002a076  mov     [rsp+78h+var_3C], eax
0x18002a07a  mov     rax, [rdx+3]
0x18002a07e  mov     edx, 2
0x18002a083  mov     [r11-38h], rax
0x18002a087  mov     rax, cs:off_18009A050
0x18002a08e  mov     [r11-30h], rax
0x18002a092  movzx   eax, word ptr [rax]
0x18002a095  mov     [rsp+78h+var_28], eax
0x18002a099  movzx   eax, word ptr [rcx]
0x18002a09c  mov     [rsp+78h+var_24], edx
0x18002a0a0  mov     [r11-20h], rcx
0x18002a0a4  lea     rcx, _TraceLoggingMetadata
0x18002a0ab  mov     [rsp+78h+var_18], eax
0x18002a0af  lea     rax, _TraceLoggingMetadataEnd
0x18002a0b6  sub     eax, ecx
0x18002a0b8  mov     [rsp+78h+var_14], 1
0x18002a0c0  mov     [rsp+78h+var_48], eax
0x18002a0c4  mov     eax, [rsp+78h+var_48]
0x18002a0c8  mov     rcx, cs:RegHandle
0x18002a0cf  lea     rax, [r11-30h]
0x18002a0d3  mov     [r11-50h], rax
0x18002a0d7  mov     [rsp+78h+var_58], edx
0x18002a0db  lea     rdx, [r11-40h]
0x18002a0df  call    cs:__imp_EtwEventWriteTransfer
0x18002a0e5  mov     rcx, [rsp+78h+var_10]
0x18002a0ea  xor     rcx, rsp; StackCookie
0x18002a0ed  call    __security_check_cookie
0x18002a0f2  add     rsp, 78h
0x18002a0f6  retn
```
