# ATL::CComObject<CINDFHelperClassImpl>::`vector deleting destructor'(uint)

- ea: `0x180005c00`
- end: `0x180005c71`
- name: `??_E?$CComObject@VCINDFHelperClassImpl@@@ATL@@UEAAPEAXI@Z`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005c00`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005c56`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005c56`
- `KERNEL32!DeleteCriticalSection` at `0x180005c41`
- `KERNEL32!DeleteCriticalSection` at `0x180005c41`

## pseudocode

```c
char *__fastcall ATL::CComObject<CINDFHelperClassImpl>::`vector deleting destructor'(char *a1, char a2)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CINDFHelperClassImpl>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
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
0x180005c00  mov     [rsp+arg_0], rbx
0x180005c05  push    rdi
0x180005c06  sub     rsp, 20h
0x180005c0a  mov     dword ptr [rcx+8], 0C0000001h
0x180005c11  lea     rax, ??_7?$CComObject@VCINDFHelperClassImpl@@@ATL@@6B@; const ATL::CComObject<CINDFHelperClassImpl>::`vftable'
0x180005c18  mov     [rcx], rax
0x180005c1b  mov     rbx, rcx
0x180005c1e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c25  mov     edi, edx
0x180005c27  mov     rax, [rcx]
0x180005c2a  mov     rax, [rax+10h]
0x180005c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c33  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005c37  cmp     byte ptr [rcx+28h], 0
0x180005c3b  jz      short loc_180005C4D
0x180005c3d  mov     byte ptr [rcx+28h], 0
0x180005c41  call    cs:__imp_DeleteCriticalSection
0x180005c48  nop     dword ptr [rax+rax+00h]
0x180005c4d  test    dil, 1
0x180005c51  jz      short loc_180005C62
0x180005c53  mov     rcx, rbx
0x180005c56  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005c5d  nop     dword ptr [rax+rax+00h]
0x180005c62  mov     rax, rbx
0x180005c65  mov     rbx, [rsp+28h+arg_0]
0x180005c6a  add     rsp, 20h
0x180005c6e  pop     rdi
0x180005c6f  retn
```
