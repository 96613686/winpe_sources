# SmartPtr<CWorkerThread>::RefCounter::Dec_nRefs(void)

- ea: `0x18000f11c`
- end: `0x18000f144`
- name: `?Dec_nRefs@RefCounter@?$SmartPtr@VCWorkerThread@@@@QEAAHXZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bd64`
- `0x18000ee10`

## callees

- `0x18000eee0`
- `0x18000f11c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f136`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f136`

## pseudocode

```c
__int64 __fastcall SmartPtr<CWorkerThread>::RefCounter::Dec_nRefs(__int64 a1, unsigned int a2)
{
  bool v2; // zf
  __int64 result; // rax

  v2 = (*(_DWORD *)(a1 + 8))-- == 1;
  result = *(unsigned int *)(a1 + 8);
  if ( v2 )
  {
    SmartPtr<CWorkerThread>::RefCounter::~RefCounter((CWorkerThread **)a1, a2);
    operator delete((void *)a1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f11c  push    rbx
0x18000f11e  sub     rsp, 20h
0x18000f122  sub     dword ptr [rcx+8], 1
0x18000f126  mov     rbx, rcx
0x18000f129  mov     eax, [rcx+8]
0x18000f12c  jnz     short loc_18000F13E
0x18000f12e  call    ??1RefCounter@?$SmartPtr@VCWorkerThread@@@@QEAA@XZ; SmartPtr<CWorkerThread>::RefCounter::~RefCounter(void)
0x18000f133  mov     rcx, rbx
0x18000f136  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f13c  xor     eax, eax
0x18000f13e  add     rsp, 20h
0x18000f142  pop     rbx
0x18000f143  retn
```
