# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x18005829c`
- end: `0x180058331`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c8970`

## callees

- `0x18005829c`
- `0x1800d0010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x1800582de`
- `MSDART!MPDeleteCriticalSection` at `0x1800582f1`
- `MSDART!MPDeleteCriticalSection` at `0x180058304`
- `MSDART!MPDeleteCriticalSection` at `0x1800582de`
- `MSDART!MPDeleteCriticalSection` at `0x1800582f1`
- `MSDART!MPDeleteCriticalSection` at `0x180058304`
- `KERNEL32!HeapDestroy` at `0x18005831c`
- `KERNEL32!HeapDestroy` at `0x18005831c`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx

  v1 = (_QWORD *)qword_180122C80;
  if ( qword_180122C80 )
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
  MPDeleteCriticalSection(&qword_180122C98);
  MPDeleteCriticalSection(&qword_180122CA0);
  MPDeleteCriticalSection(&qword_180122CA8);
  if ( hHeap )
    HeapDestroy(hHeap);
  return 0;
}

```

## disassembly

```asm
0x18005829c  push    rbx
0x18005829e  sub     rsp, 20h
0x1800582a2  mov     rbx, cs:qword_180122C80
0x1800582a9  test    rbx, rbx
0x1800582ac  jz      short loc_1800582D7
0x1800582ae  jmp     short loc_1800582D1
0x1800582b0  mov     rcx, [rbx+18h]
0x1800582b4  test    rcx, rcx
0x1800582b7  jz      short loc_1800582C5
0x1800582b9  mov     rax, [rcx]
0x1800582bc  mov     rax, [rax+10h]
0x1800582c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582c5  mov     qword ptr [rbx+18h], 0
0x1800582cd  add     rbx, 30h ; '0'
0x1800582d1  cmp     qword ptr [rbx], 0
0x1800582d5  jnz     short loc_1800582B0
0x1800582d7  lea     rcx, qword_180122C98
0x1800582de  call    cs:__imp_MPDeleteCriticalSection
0x1800582e5  nop     dword ptr [rax+rax+00h]
0x1800582ea  lea     rcx, qword_180122CA0
0x1800582f1  call    cs:__imp_MPDeleteCriticalSection
0x1800582f8  nop     dword ptr [rax+rax+00h]
0x1800582fd  lea     rcx, qword_180122CA8
0x180058304  call    cs:__imp_MPDeleteCriticalSection
0x18005830b  nop     dword ptr [rax+rax+00h]
0x180058310  mov     rcx, cs:hHeap; hHeap
0x180058317  test    rcx, rcx
0x18005831a  jz      short loc_180058328
0x18005831c  call    cs:__imp_HeapDestroy
0x180058323  nop     dword ptr [rax+rax+00h]
0x180058328  xor     eax, eax
0x18005832a  add     rsp, 20h
0x18005832e  pop     rbx
0x18005832f  retn
```
