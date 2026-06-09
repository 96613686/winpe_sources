# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x180008020`
- end: `0x18000803f`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c834`
- `0x1800157ac`
- `0x180015918`
- `0x180015dc4`
- `0x18001eeb8`
- `0x18002c740`
- `0x18004087f`
- `0x1800408a7`

## callees

- `0x180008020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008037`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008037`

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
0x180008020  sub     rsp, 28h
0x180008024  add     rcx, 8; lpCriticalSection
0x180008028  cmp     byte ptr [rcx+28h], 0
0x18000802c  jnz     short loc_180008033
0x18000802e  add     rsp, 28h
0x180008032  retn
0x180008033  mov     byte ptr [rcx+28h], 0
0x180008037  call    cs:__imp_DeleteCriticalSection
0x18000803d  jmp     short loc_18000802E
```
