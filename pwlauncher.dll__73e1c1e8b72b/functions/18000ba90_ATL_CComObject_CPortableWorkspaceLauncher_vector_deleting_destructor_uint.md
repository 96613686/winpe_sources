# ATL::CComObject<CPortableWorkspaceLauncher>::`vector deleting destructor'(uint)

- ea: `0x18000ba90`
- end: `0x18000badf`
- name: `??_E?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ba90`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bacb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bacb`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CPortableWorkspaceLauncher>::`vector deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CPortableWorkspaceLauncher>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ba90  mov     [rsp+arg_0], rbx
0x18000ba95  push    rdi
0x18000ba96  sub     rsp, 20h
0x18000ba9a  mov     dword ptr [rcx+8], 0C0000001h
0x18000baa1  lea     rax, ??_7?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@6B@; const ATL::CComObject<CPortableWorkspaceLauncher>::`vftable'
0x18000baa8  mov     [rcx], rax
0x18000baab  mov     rdi, rcx
0x18000baae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bab5  mov     ebx, edx
0x18000bab7  mov     rax, [rcx]
0x18000baba  mov     rax, [rax+10h]
0x18000babe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac3  test    bl, 1
0x18000bac6  jz      short loc_18000BAD1
0x18000bac8  mov     rcx, rdi
0x18000bacb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bad1  mov     rbx, [rsp+28h+arg_0]
0x18000bad6  mov     rax, rdi
0x18000bad9  add     rsp, 20h
0x18000badd  pop     rdi
0x18000bade  retn
```
