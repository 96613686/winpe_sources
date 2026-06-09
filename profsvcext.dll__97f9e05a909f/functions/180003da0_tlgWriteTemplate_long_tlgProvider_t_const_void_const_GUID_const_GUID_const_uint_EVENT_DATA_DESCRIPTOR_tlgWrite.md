# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180003da0`
- end: `0x180003e83`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010f1c`
- `0x180010f94`
- `0x18001100c`

## callees

- `0x18000a520`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180003e65`
- `ntdll!EtwEventWriteTransfer` at `0x180003e65`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // eax
  _DWORD v8[2]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v9; // [rsp+40h] [rbp-68h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-58h] BYREF
  int v11; // [rsp+58h] [rbp-50h]
  int v12; // [rsp+5Ch] [rbp-4Ch]
  unsigned __int8 *v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]
  int v15; // [rsp+6Ch] [rbp-3Ch]
  __int64 v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]
  __int64 v18; // [rsp+80h] [rbp-28h]
  __int64 v19; // [rsp+88h] [rbp-20h]

  v18 = a6;
  v16 = a5;
  v8[0] = *a2 << 24;
  v8[1] = *(unsigned __int16 *)(a2 + 1);
  v9 = *(_QWORD *)(a2 + 3);
  v10 = *(unsigned __int16 **)(a1 + 8);
  v19 = 4;
  v17 = 4;
  v11 = *v10;
  v6 = *(unsigned __int16 *)(a2 + 11);
  v12 = 2;
  v13 = a2 + 11;
  v14 = v6;
  v15 = 1;
  return ((__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD, int, unsigned __int16 **, unsigned int))EtwEventWriteTransfer)(
           *(_QWORD *)(a1 + 32),
           v8,
           0,
           0,
           4,
           &v10,
           (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata);
}

```

## disassembly

```asm
0x180003da0  mov     r11, rsp
0x180003da3  sub     rsp, 0A8h
0x180003daa  mov     rax, cs:__security_cookie
0x180003db1  xor     rax, rsp
0x180003db4  mov     [rsp+0A8h+var_18], rax
0x180003dbc  mov     rax, [rsp+0A8h+arg_28]
0x180003dc4  mov     r10, rcx
0x180003dc7  mov     [r11-28h], rax
0x180003dcb  lea     rcx, [rdx+0Bh]
0x180003dcf  mov     rax, [rsp+0A8h+arg_20]
0x180003dd7  xor     r9d, r9d
0x180003dda  mov     [r11-38h], rax
0x180003dde  xor     r8d, r8d
0x180003de1  movzx   eax, byte ptr [rdx]
0x180003de4  shl     eax, 18h
0x180003de7  mov     [rsp+0A8h+var_70], eax
0x180003deb  movzx   eax, word ptr [rdx+1]
0x180003def  mov     [rsp+0A8h+var_6C], eax
0x180003df3  mov     rax, [rdx+3]
0x180003df7  lea     rdx, [r11-70h]
0x180003dfb  mov     [r11-68h], rax
0x180003dff  mov     rax, [r10+8]
0x180003e03  mov     [r11-58h], rax
0x180003e07  mov     qword ptr [r11-20h], 4
0x180003e0f  mov     qword ptr [r11-30h], 4
0x180003e17  movzx   eax, word ptr [rax]
0x180003e1a  mov     [rsp+0A8h+var_50], eax
0x180003e1e  movzx   eax, word ptr [rcx]
0x180003e21  mov     [rsp+0A8h+var_4C], 2
0x180003e29  mov     [r11-48h], rcx
0x180003e2d  lea     rcx, _TraceLoggingMetadata
0x180003e34  mov     [rsp+0A8h+var_40], eax
0x180003e38  lea     rax, _TraceLoggingMetadataEnd
0x180003e3f  sub     eax, ecx
0x180003e41  mov     [rsp+0A8h+var_3C], 1
0x180003e49  mov     [rsp+0A8h+var_78], eax
0x180003e4d  mov     eax, [rsp+0A8h+var_78]
0x180003e51  mov     rcx, [r10+20h]
0x180003e55  lea     rax, [r11-58h]
0x180003e59  mov     [r11-80h], rax
0x180003e5d  mov     [rsp+0A8h+var_88], 4
0x180003e65  call    cs:__imp_EtwEventWriteTransfer
0x180003e6b  mov     rcx, [rsp+0A8h+var_18]
0x180003e73  xor     rcx, rsp; StackCookie
0x180003e76  call    __security_check_cookie
0x180003e7b  add     rsp, 0A8h
0x180003e82  retn
```
