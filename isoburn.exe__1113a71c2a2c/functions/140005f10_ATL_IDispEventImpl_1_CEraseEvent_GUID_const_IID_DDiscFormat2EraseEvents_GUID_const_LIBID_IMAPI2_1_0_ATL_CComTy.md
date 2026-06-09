# ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x140005f10`
- end: `0x140005f24`
- name: `?GetTypeInfoCount@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005f10`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x140005f10  test    rdx, rdx
0x140005f13  jnz     short loc_140005F1B
0x140005f15  mov     eax, 80004003h
0x140005f1a  retn
0x140005f1b  mov     dword ptr [rdx], 1
0x140005f21  xor     eax, eax
0x140005f23  retn
```
