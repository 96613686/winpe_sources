# ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::AddRef(void)

- ea: `0x18000b480`
- end: `0x18000b4a9`
- name: `?AddRef@?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b480`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 48);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 48), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18000b480  mov     r9d, 7FFFFFFFh
0x18000b486  jmp     short loc_18000B496
0x18000b488  lea     edx, [r8+1]
0x18000b48c  mov     eax, r8d
0x18000b48f  lock cmpxchg [rcx+30h], edx
0x18000b494  jz      short loc_18000B4A1
0x18000b496  mov     r8d, [rcx+30h]
0x18000b49a  cmp     r8d, r9d
0x18000b49d  jnz     short loc_18000B488
0x18000b49f  jmp     short loc_18000B4A5
0x18000b4a1  lea     r9d, [r8+1]
0x18000b4a5  mov     eax, r9d
0x18000b4a8  retn
```
