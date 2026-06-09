# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x1800021d0`
- end: `0x1800021ed`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e2a6`

## callees

- `0x1800021d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800021e2`
- `KERNEL32!DeleteCriticalSection` at `0x1800021e2`

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
0x1800021d0  sub     rsp, 28h
0x1800021d4  add     rcx, 8; lpCriticalSection
0x1800021d8  cmp     byte ptr [rcx+28h], 0
0x1800021dc  jz      short loc_1800021E8
0x1800021de  mov     byte ptr [rcx+28h], 0
0x1800021e2  call    cs:__imp_DeleteCriticalSection
0x1800021e8  add     rsp, 28h
0x1800021ec  retn
```
