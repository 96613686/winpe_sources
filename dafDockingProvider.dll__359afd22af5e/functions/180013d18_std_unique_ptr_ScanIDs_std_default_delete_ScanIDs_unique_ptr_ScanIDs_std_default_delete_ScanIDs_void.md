# std::unique_ptr<ScanIDs,std::default_delete<ScanIDs>>::~unique_ptr<ScanIDs,std::default_delete<ScanIDs>>(void)

- ea: `0x180013d18`
- end: `0x180013d58`
- name: `??1?$unique_ptr@VScanIDs@@U?$default_delete@VScanIDs@@@std@@@std@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d7f3`
- `0x18001d98f`

## callees

- `0x1800014d0`
- `0x180013d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013d44`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013d44`

## pseudocode

```c
void __fastcall std::unique_ptr<ScanIDs>::~unique_ptr<ScanIDs>(__int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    operator delete(*(void **)(v1 + 48));
    operator delete(*(void **)(v1 + 56));
    operator delete(*(void **)(v1 + 64));
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
    operator delete((void *)v1);
  }
}

```

## disassembly

```asm
0x180013d18  push    rbx
0x180013d1a  sub     rsp, 20h
0x180013d1e  mov     rbx, [rcx]
0x180013d21  test    rbx, rbx
0x180013d24  jz      short loc_180013D52
0x180013d26  mov     rcx, [rbx+30h]; Block
0x180013d2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d2f  mov     rcx, [rbx+38h]; Block
0x180013d33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d38  mov     rcx, [rbx+40h]; Block
0x180013d3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d41  mov     rcx, rbx; lpCriticalSection
0x180013d44  call    cs:__imp_DeleteCriticalSection
0x180013d4a  mov     rcx, rbx; Block
0x180013d4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d52  add     rsp, 20h
0x180013d56  pop     rbx
0x180013d57  retn
```
