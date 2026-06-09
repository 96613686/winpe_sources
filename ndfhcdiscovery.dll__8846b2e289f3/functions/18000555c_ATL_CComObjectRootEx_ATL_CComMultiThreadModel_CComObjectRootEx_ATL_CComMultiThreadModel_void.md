# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000555c`
- end: `0x180005580`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013be0`

## callees

- `0x18000555c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000556e`
- `KERNEL32!DeleteCriticalSection` at `0x18000556e`

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
0x18000555c  sub     rsp, 28h
0x180005560  add     rcx, 8; lpCriticalSection
0x180005564  cmp     byte ptr [rcx+28h], 0
0x180005568  jz      short loc_18000557A
0x18000556a  mov     byte ptr [rcx+28h], 0
0x18000556e  call    cs:__imp_DeleteCriticalSection
0x180005575  nop     dword ptr [rax+rax+00h]
0x18000557a  add     rsp, 28h
0x18000557e  retn
```
