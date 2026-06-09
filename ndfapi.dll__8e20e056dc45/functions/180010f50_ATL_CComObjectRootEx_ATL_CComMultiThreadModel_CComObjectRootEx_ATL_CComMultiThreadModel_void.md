# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x180010f50`
- end: `0x180010f6d`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020218`
- `0x180020242`

## callees

- `0x180010f50`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180010f62`
- `KERNEL32!DeleteCriticalSection` at `0x180010f62`

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
0x180010f50  sub     rsp, 28h
0x180010f54  add     rcx, 8; lpCriticalSection
0x180010f58  cmp     byte ptr [rcx+28h], 0
0x180010f5c  jz      short loc_180010F68
0x180010f5e  mov     byte ptr [rcx+28h], 0
0x180010f62  call    cs:__imp_DeleteCriticalSection
0x180010f68  add     rsp, 28h
0x180010f6c  retn
```
