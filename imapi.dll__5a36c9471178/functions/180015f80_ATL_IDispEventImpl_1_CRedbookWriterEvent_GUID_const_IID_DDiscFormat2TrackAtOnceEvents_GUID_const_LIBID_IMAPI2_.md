# ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x180015f80`
- end: `0x180015f94`
- name: `?GetTypeInfoCount@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015f80`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x180015f80  test    rdx, rdx
0x180015f83  jnz     short loc_180015F8B
0x180015f85  mov     eax, 80004003h
0x180015f8a  retn
0x180015f8b  mov     dword ptr [rdx], 1
0x180015f91  xor     eax, eax
0x180015f93  retn
```
