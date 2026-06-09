# XPerfCore::CAtlGlobalPtr<ATL::CComAutoCriticalSection>::~CAtlGlobalPtr<ATL::CComAutoCriticalSection>(void)

- ea: `0x180044368`
- end: `0x18004438d`
- name: `??1?$CAtlGlobalPtr@VCComAutoCriticalSection@ATL@@@XPerfCore@@QEAA@XZ`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800d59c0`
- `0x1800d5a00`
- `0x1800d5a40`

## callees

- `0x180044368`
- `0x180056c14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044379`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044379`

## pseudocode

```c
void __fastcall XPerfCore::CAtlGlobalPtr<ATL::CComAutoCriticalSection>::~CAtlGlobalPtr<ATL::CComAutoCriticalSection>(
        LPCRITICAL_SECTION *a1)
{
  LPCRITICAL_SECTION v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    DeleteCriticalSection(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180044368  push    rbx
0x18004436a  sub     rsp, 20h
0x18004436e  mov     rbx, [rcx]
0x180044371  test    rbx, rbx
0x180044374  jz      short loc_180044387
0x180044376  mov     rcx, rbx; lpCriticalSection
0x180044379  call    cs:__imp_DeleteCriticalSection
0x18004437f  mov     rcx, rbx; Block
0x180044382  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180044387  add     rsp, 20h
0x18004438b  pop     rbx
0x18004438c  retn
```
