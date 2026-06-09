# ATL::CComObject<CFileStream>::`vector deleting destructor'(uint)

- ea: `0x180006930`
- end: `0x180006990`
- name: `??_E?$CComObject@VCFileStream@@@ATL@@UEAAPEAXI@Z`
- size: `96`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006930`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000697c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000697c`
- `KERNEL32!CloseHandle` at `0x18000696d`
- `KERNEL32!CloseHandle` at `0x18000696d`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CFileStream>::`vector deleting destructor'(_DWORD *a1, char a2)
{
  void *v4; // rcx

  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CFileStream>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = (void *)*((_QWORD *)a1 + 3);
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180006930  mov     [rsp+arg_0], rbx
0x180006935  push    rdi
0x180006936  sub     rsp, 20h
0x18000693a  mov     dword ptr [rcx+8], 0C0000001h
0x180006941  lea     rax, ??_7?$CComObject@VCFileStream@@@ATL@@6B@; const ATL::CComObject<CFileStream>::`vftable'
0x180006948  mov     [rcx], rax
0x18000694b  mov     rbx, rcx
0x18000694e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006955  mov     edi, edx
0x180006957  mov     rax, [rcx]
0x18000695a  mov     rax, [rax+10h]
0x18000695e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006963  mov     rcx, [rbx+18h]; hObject
0x180006967  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000696b  jz      short loc_180006973
0x18000696d  call    cs:__imp_CloseHandle
0x180006973  test    dil, 1
0x180006977  jz      short loc_180006982
0x180006979  mov     rcx, rbx
0x18000697c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006982  mov     rax, rbx
0x180006985  mov     rbx, [rsp+28h+arg_0]
0x18000698a  add     rsp, 20h
0x18000698e  pop     rdi
0x18000698f  retn
```
