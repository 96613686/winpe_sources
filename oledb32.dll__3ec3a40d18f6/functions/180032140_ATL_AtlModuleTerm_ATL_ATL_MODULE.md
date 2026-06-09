# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x180032140`
- end: `0x1800321c8`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `136`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011370`

## callees

- `0x180032140`
- `0x180087010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x1800321b5`
- `KERNEL32!HeapDestroy` at `0x1800321b5`
- `KERNEL32!DeleteCriticalSection` at `0x18003218f`
- `KERNEL32!DeleteCriticalSection` at `0x180032199`
- `KERNEL32!DeleteCriticalSection` at `0x1800321a6`
- `KERNEL32!DeleteCriticalSection` at `0x18003218f`
- `KERNEL32!DeleteCriticalSection` at `0x180032199`
- `KERNEL32!DeleteCriticalSection` at `0x1800321a6`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
{
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  void *v5; // rcx

  if ( !a1 )
    return 2147942487LL;
  v3 = (_QWORD *)*((_QWORD *)a1 + 4);
  if ( v3 )
  {
    while ( *v3 )
    {
      v4 = v3[4];
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      v3[4] = 0;
      v3 += 7;
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  v5 = (void *)*((_QWORD *)a1 + 6);
  if ( v5 )
    HeapDestroy(v5);
  return 0;
}

```

## disassembly

```asm
0x180032140  mov     [rsp+arg_0], rbx
0x180032145  push    rdi
0x180032146  sub     rsp, 20h
0x18003214a  mov     rdi, rcx
0x18003214d  test    rcx, rcx
0x180032150  jnz     short loc_180032159
0x180032152  mov     eax, 80070057h
0x180032157  jmp     short loc_1800321BD
0x180032159  mov     rbx, [rcx+20h]
0x18003215d  test    rbx, rbx
0x180032160  jz      short loc_18003218B
0x180032162  jmp     short loc_180032185
0x180032164  mov     rcx, [rbx+20h]
0x180032168  test    rcx, rcx
0x18003216b  jz      short loc_180032179
0x18003216d  mov     rax, [rcx]
0x180032170  mov     rax, [rax+10h]
0x180032174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032179  mov     qword ptr [rbx+20h], 0
0x180032181  add     rbx, 38h ; '8'
0x180032185  cmp     qword ptr [rbx], 0
0x180032189  jnz     short loc_180032164
0x18003218b  lea     rcx, [rdi+38h]; lpCriticalSection
0x18003218f  call    cs:__imp_DeleteCriticalSection
0x180032195  lea     rcx, [rdi+60h]; lpCriticalSection
0x180032199  call    cs:__imp_DeleteCriticalSection
0x18003219f  lea     rcx, [rdi+88h]; lpCriticalSection
0x1800321a6  call    cs:__imp_DeleteCriticalSection
0x1800321ac  mov     rcx, [rdi+30h]; hHeap
0x1800321b0  test    rcx, rcx
0x1800321b3  jz      short loc_1800321BB
0x1800321b5  call    cs:__imp_HeapDestroy
0x1800321bb  xor     eax, eax
0x1800321bd  mov     rbx, [rsp+28h+arg_0]
0x1800321c2  add     rsp, 20h
0x1800321c6  pop     rdi
0x1800321c7  retn
```
