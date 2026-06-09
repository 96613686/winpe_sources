# ATL::CComAggObject<CDpSearchProtocol>::`scalar deleting destructor'(uint)

- ea: `0x1800031f0`
- end: `0x180003254`
- name: `??_G?$CComAggObject@VCDpSearchProtocol@@@ATL@@UEAAPEAXI@Z`
- size: `100`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800031f0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003240`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003240`
- `KERNEL32!DeleteCriticalSection` at `0x180003231`
- `KERNEL32!DeleteCriticalSection` at `0x180003231`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CDpSearchProtocol>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *a1,
        char a2)
{
  a1->LockCount = -1073741823;
  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CDpSearchProtocol>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( LOBYTE(a1[2].DebugInfo) )
  {
    LOBYTE(a1[2].DebugInfo) = 0;
    DeleteCriticalSection(a1 + 1);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800031f0  mov     [rsp+arg_0], rbx
0x1800031f5  push    rdi
0x1800031f6  sub     rsp, 20h
0x1800031fa  mov     dword ptr [rcx+8], 0C0000001h
0x180003201  lea     rax, ??_7?$CComAggObject@VCDpSearchProtocol@@@ATL@@6B@; const ATL::CComAggObject<CDpSearchProtocol>::`vftable'
0x180003208  mov     [rcx], rax
0x18000320b  mov     rbx, rcx
0x18000320e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003215  mov     edi, edx
0x180003217  mov     rax, [rcx]
0x18000321a  mov     rax, [rax+10h]
0x18000321e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003223  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003227  cmp     byte ptr [rcx+28h], 0
0x18000322b  jz      short loc_180003237
0x18000322d  mov     byte ptr [rcx+28h], 0
0x180003231  call    cs:__imp_DeleteCriticalSection
0x180003237  test    dil, 1
0x18000323b  jz      short loc_180003246
0x18000323d  mov     rcx, rbx
0x180003240  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003246  mov     rax, rbx
0x180003249  mov     rbx, [rsp+28h+arg_0]
0x18000324e  add     rsp, 20h
0x180003252  pop     rdi
0x180003253  retn
```
