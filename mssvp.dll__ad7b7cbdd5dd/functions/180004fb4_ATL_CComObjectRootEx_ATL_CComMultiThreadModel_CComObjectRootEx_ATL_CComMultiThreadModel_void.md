# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x180004fb4`
- end: `0x180004fd1`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009fd8`
- `0x18000a1a0`
- `0x18000a340`
- `0x180013d54`
- `0x180014c2c`
- `0x180014cac`
- `0x1800166d4`
- `0x1800167e8`
- `0x180016810`
- `0x180018a68`
- `0x180018adc`
- `0x180018b04`
- `0x180018bac`
- `0x18001eb9c`
- `0x18001ebd8`
- `0x180021f00`
- `0x180021f70`
- `0x180027574`
- `0x180028ce8`
- `0x18003abee`

## callees

- `0x180004fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004fc6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004fc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180004fb4  sub     rsp, 28h
0x180004fb8  add     rcx, 8; lpCriticalSection
0x180004fbc  cmp     byte ptr [rcx+28h], 0
0x180004fc0  jz      short loc_180004FCC
0x180004fc2  mov     byte ptr [rcx+28h], 0
0x180004fc6  call    cs:__imp_DeleteCriticalSection
0x180004fcc  add     rsp, 28h
0x180004fd0  retn
```
