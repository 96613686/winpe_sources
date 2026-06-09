# ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x140003520`
- end: `0x140003534`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UICtTuner@@$1?IID_ICtTuner@@3U_GUID@@B$1?LIBID_cttunesvrLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003520`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x140003520  test    rdx, rdx
0x140003523  jnz     short loc_14000352B
0x140003525  mov     eax, 80004003h
0x14000352a  retn
0x14000352b  mov     dword ptr [rdx], 1
0x140003531  xor     eax, eax
0x140003533  retn
```
