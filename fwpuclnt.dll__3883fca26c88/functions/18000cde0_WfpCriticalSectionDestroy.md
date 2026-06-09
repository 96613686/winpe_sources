# WfpCriticalSectionDestroy

- ea: `0x18000cde0`
- end: `0x18000ce09`
- name: `WfpCriticalSectionDestroy`
- size: `41`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003704`
- `0x180005190`
- `0x18000b8c0`
- `0x18001125c`
- `0x180013bb4`
- `0x18003c204`
- `0x18003d6cc`
- `0x180040108`
- `0x180042970`
- `0x180042ef0`
- `0x180049f38`

## callees

- `0x18000cde0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cdef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cdef`

## pseudocode

```c
void __fastcall WfpCriticalSectionDestroy(__int64 a1)
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
0x18000cde0  push    rbx
0x18000cde2  sub     rsp, 20h
0x18000cde6  cmp     dword ptr [rcx+28h], 0
0x18000cdea  mov     rbx, rcx
0x18000cded  jz      short loc_18000CE02
0x18000cdef  call    cs:__imp_DeleteCriticalSection
0x18000cdf6  nop     dword ptr [rax+rax+00h]
0x18000cdfb  mov     dword ptr [rbx+28h], 0
0x18000ce02  add     rsp, 20h
0x18000ce06  pop     rbx
0x18000ce07  retn
```
