# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x18001936c`
- end: `0x180019401`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x18001936c`
- `0x180031010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x1800193ec`
- `KERNEL32!HeapDestroy` at `0x1800193ec`
- `MSDART!MPDeleteCriticalSection` at `0x1800193ae`
- `MSDART!MPDeleteCriticalSection` at `0x1800193c1`
- `MSDART!MPDeleteCriticalSection` at `0x1800193d4`
- `MSDART!MPDeleteCriticalSection` at `0x1800193ae`
- `MSDART!MPDeleteCriticalSection` at `0x1800193c1`
- `MSDART!MPDeleteCriticalSection` at `0x1800193d4`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx

  v1 = (_QWORD *)qword_1800464E0;
  if ( qword_1800464E0 )
  {
    while ( *v1 )
    {
      v2 = v1[3];
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      v1[3] = 0;
      v1 += 6;
    }
  }
  MPDeleteCriticalSection(&qword_1800464F8);
  MPDeleteCriticalSection(&qword_180046500);
  MPDeleteCriticalSection(&qword_180046508);
  if ( hHeap )
    HeapDestroy(hHeap);
  return 0;
}

```

## disassembly

```asm
0x18001936c  push    rbx
0x18001936e  sub     rsp, 20h
0x180019372  mov     rbx, cs:qword_1800464E0
0x180019379  test    rbx, rbx
0x18001937c  jz      short loc_1800193A7
0x18001937e  jmp     short loc_1800193A1
0x180019380  mov     rcx, [rbx+18h]
0x180019384  test    rcx, rcx
0x180019387  jz      short loc_180019395
0x180019389  mov     rax, [rcx]
0x18001938c  mov     rax, [rax+10h]
0x180019390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019395  mov     qword ptr [rbx+18h], 0
0x18001939d  add     rbx, 30h ; '0'
0x1800193a1  cmp     qword ptr [rbx], 0
0x1800193a5  jnz     short loc_180019380
0x1800193a7  lea     rcx, qword_1800464F8
0x1800193ae  call    cs:__imp_MPDeleteCriticalSection
0x1800193b5  nop     dword ptr [rax+rax+00h]
0x1800193ba  lea     rcx, qword_180046500
0x1800193c1  call    cs:__imp_MPDeleteCriticalSection
0x1800193c8  nop     dword ptr [rax+rax+00h]
0x1800193cd  lea     rcx, qword_180046508
0x1800193d4  call    cs:__imp_MPDeleteCriticalSection
0x1800193db  nop     dword ptr [rax+rax+00h]
0x1800193e0  mov     rcx, cs:hHeap; hHeap
0x1800193e7  test    rcx, rcx
0x1800193ea  jz      short loc_1800193F8
0x1800193ec  call    cs:__imp_HeapDestroy
0x1800193f3  nop     dword ptr [rax+rax+00h]
0x1800193f8  xor     eax, eax
0x1800193fa  add     rsp, 20h
0x1800193fe  pop     rbx
0x1800193ff  retn
```
