# FwCriticalSectionDestroy

- ea: `0x1800120b0`
- end: `0x1800120d2`
- name: `FwCriticalSectionDestroy`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800120b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800120bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800120bf`

## pseudocode

```c
void __fastcall FwCriticalSectionDestroy(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)a1);
    *(_DWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x1800120b0  push    rbx
0x1800120b2  sub     rsp, 20h
0x1800120b6  cmp     dword ptr [rcx+28h], 0
0x1800120ba  mov     rbx, rcx
0x1800120bd  jz      short loc_1800120CC
0x1800120bf  call    cs:__imp_DeleteCriticalSection
0x1800120c5  mov     dword ptr [rbx+28h], 0
0x1800120cc  add     rsp, 20h
0x1800120d0  pop     rbx
0x1800120d1  retn
```
