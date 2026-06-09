# ATL::CComObject<CDpSearchProtocol>::`vector deleting destructor'(uint)

- ea: `0x1800032c0`
- end: `0x180003324`
- name: `??_E?$CComObject@VCDpSearchProtocol@@@ATL@@UEAAPEAXI@Z`
- size: `100`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800032c0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003310`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003310`
- `KERNEL32!DeleteCriticalSection` at `0x180003301`
- `KERNEL32!DeleteCriticalSection` at `0x180003301`

## pseudocode

```c
char *__fastcall ATL::CComObject<CDpSearchProtocol>::`vector deleting destructor'(char *a1, char a2)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CDpSearchProtocol>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( a1[56] )
  {
    a1[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800032c0  mov     [rsp+arg_0], rbx
0x1800032c5  push    rdi
0x1800032c6  sub     rsp, 20h
0x1800032ca  mov     dword ptr [rcx+8], 0C0000001h
0x1800032d1  lea     rax, ??_7?$CComObject@VCDpSearchProtocol@@@ATL@@6B@; const ATL::CComObject<CDpSearchProtocol>::`vftable'
0x1800032d8  mov     [rcx], rax
0x1800032db  mov     rbx, rcx
0x1800032de  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800032e5  mov     edi, edx
0x1800032e7  mov     rax, [rcx]
0x1800032ea  mov     rax, [rax+10h]
0x1800032ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800032f7  cmp     byte ptr [rcx+28h], 0
0x1800032fb  jz      short loc_180003307
0x1800032fd  mov     byte ptr [rcx+28h], 0
0x180003301  call    cs:__imp_DeleteCriticalSection
0x180003307  test    dil, 1
0x18000330b  jz      short loc_180003316
0x18000330d  mov     rcx, rbx
0x180003310  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003316  mov     rax, rbx
0x180003319  mov     rbx, [rsp+28h+arg_0]
0x18000331e  add     rsp, 20h
0x180003322  pop     rdi
0x180003323  retn
```
