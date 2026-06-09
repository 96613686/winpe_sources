# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000cc28`
- end: `0x18000cc45`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180058dc3`
- `0x18005b33b`

## callees

- `0x18000cc28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cc3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cc3a`

## pseudocode

```c
void __fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 v1; // rcx

  v1 = a1 + 8;
  if ( *(_BYTE *)(v1 + 40) )
  {
    *(_BYTE *)(v1 + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x18000cc28  sub     rsp, 28h
0x18000cc2c  add     rcx, 8; lpCriticalSection
0x18000cc30  cmp     byte ptr [rcx+28h], 0
0x18000cc34  jz      short loc_18000CC40
0x18000cc36  mov     byte ptr [rcx+28h], 0
0x18000cc3a  call    cs:__imp_DeleteCriticalSection
0x18000cc40  add     rsp, 28h
0x18000cc44  retn
```
