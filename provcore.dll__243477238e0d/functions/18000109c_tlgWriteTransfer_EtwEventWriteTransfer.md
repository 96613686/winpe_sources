# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18000109c`
- end: `0x18000114f`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `179`
- prototype: `HRESULT __fastcall(const _tlgProvider_t *hProvider, const void *pEventMetadata, const _GUID *pActivityId, const _GUID *pRelatedActivityId, unsigned int cData, _EVENT_DATA_DESCRIPTOR *pData)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x1800012c8`
- `0x1800013cc`
- `0x180001430`

## callees

- `0x180002790`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001137`
- `ntdll!EtwEventWriteTransfer` at `0x180001137`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_EtwEventWriteTransfer(
        const _tlgProvider_t *hProvider,
        char *pEventMetadata,
        const _GUID *pActivityId,
        const _GUID *pRelatedActivityId,
        unsigned int cData,
        _EVENT_DATA_DESCRIPTOR *pData)
{
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  unsigned __int64 desc[2]; // [rsp+38h] [rbp-20h] BYREF

  LODWORD(desc[0]) = (unsigned __int8)*pEventMetadata << 24;
  HIDWORD(desc[0]) = *(unsigned __int16 *)(pEventMetadata + 1);
  v6 = *(_QWORD *)(pEventMetadata + 3);
  v7 = (unsigned __int16 *)(pEventMetadata + 11);
  desc[1] = v6;
  pData->Ptr = (unsigned __int64)hProvider->ProviderMetadataPtr;
  pData->Size = *hProvider->ProviderMetadataPtr;
  pData[1].Ptr = (unsigned __int64)v7;
  pData->Reserved = 2;
  pData[1].Size = *v7;
  pData[1].Reserved = 1;
  return EtwEventWriteTransfer(hProvider->RegHandle, desc, pActivityId, pRelatedActivityId, cData, pData);
}

```

## disassembly

```asm
0x18000109c  sub     rsp, 58h
0x1800010a0  mov     rax, cs:__security_cookie
0x1800010a7  xor     rax, rsp
0x1800010aa  mov     [rsp+58h+var_10], rax
0x1800010af  movzx   eax, byte ptr [pEventMetadata]
0x1800010b2  mov     r11, hProvider
0x1800010b5  mov     r10, [rsp+58h+arg_28]
0x1800010bd  shl     eax, 18h
0x1800010c0  mov     dword ptr [rsp+58h+desc], eax
0x1800010c4  movzx   eax, word ptr [pEventMetadata+1]
0x1800010c8  mov     dword ptr [rsp+58h+desc+4], eax
0x1800010cc  mov     rax, [pEventMetadata+3]
0x1800010d0  add     pEventMetadata, 0Bh
0x1800010d4  mov     [rsp+58h+desc+8], rax
0x1800010d9  mov     rax, [hProvider+8]
0x1800010dd  mov     [r10], rax
0x1800010e0  mov     rax, [hProvider+8]
0x1800010e4  mov     [rsp+58h+var_30], r10
0x1800010e9  movzx   ecx, word ptr [rax]
0x1800010ec  mov     [r10+8], ecx
0x1800010f0  lea     hProvider, _TraceLoggingMetadata
0x1800010f7  mov     [r10+10h], pEventMetadata
0x1800010fb  mov     dword ptr [r10+0Ch], 2
0x180001103  movzx   eax, word ptr [pEventMetadata]
0x180001106  lea     pEventMetadata, [rsp+58h+desc]
0x18000110b  mov     [r10+18h], eax
0x18000110f  lea     rax, _TraceLoggingMetadataEnd
0x180001116  sub     eax, ecx
0x180001118  mov     dword ptr [r10+1Ch], 1
0x180001120  mov     [rsp+58h+var_28], eax
0x180001124  mov     eax, [rsp+58h+var_28]
0x180001128  mov     eax, [rsp+58h+arg_20]
0x18000112f  mov     hProvider, [r11+20h]
0x180001133  mov     [rsp+58h+var_38], eax
0x180001137  call    cs:__imp_EtwEventWriteTransfer
0x18000113d  mov     hProvider, [rsp+58h+var_10]
0x180001142  xor     hProvider, rsp; StackCookie
0x180001145  call    __security_check_cookie
0x18000114a  add     rsp, 58h
0x18000114e  retn
```
