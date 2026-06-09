# ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x180004a40`
- end: `0x180004a54`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UILogScripting@@$1?IID_ILogScripting@@3U_GUID@@B$1?LIBID_IISLog@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004a40`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x180004a40  test    rdx, rdx
0x180004a43  jnz     short loc_180004A4B
0x180004a45  mov     eax, 80070057h
0x180004a4a  retn
0x180004a4b  mov     dword ptr [rdx], 1
0x180004a51  xor     eax, eax
0x180004a53  retn
```
