# ATL::CComAggObject<CAdvancedConfig>::`vector deleting destructor'(uint)

- ea: `0x1800031b0`
- end: `0x180003218`
- name: `??_E?$CComAggObject@VCAdvancedConfig@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001fec`
- `0x1800031b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031f1`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CAdvancedConfig>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *a1,
        char a2)
{
  a1->LockCount = -1073741823;
  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CAdvancedConfig>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( LOBYTE(a1[2].DebugInfo) )
  {
    LOBYTE(a1[2].DebugInfo) = 0;
    DeleteCriticalSection(a1 + 1);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1, 0x58u);
  return a1;
}

```

## disassembly

```asm
0x1800031b0  mov     [rsp+arg_0], rbx
0x1800031b5  push    rdi
0x1800031b6  sub     rsp, 20h
0x1800031ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800031c1  lea     rax, ??_7?$CComAggObject@VCAdvancedConfig@@@ATL@@6B@; const ATL::CComAggObject<CAdvancedConfig>::`vftable'
0x1800031c8  mov     [rcx], rax
0x1800031cb  mov     rbx, rcx
0x1800031ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800031d5  mov     edi, edx
0x1800031d7  mov     rax, [rcx]
0x1800031da  mov     rax, [rax+10h]
0x1800031de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e3  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800031e7  cmp     byte ptr [rcx+28h], 0
0x1800031eb  jz      short loc_1800031F7
0x1800031ed  mov     byte ptr [rcx+28h], 0
0x1800031f1  call    cs:__imp_DeleteCriticalSection
0x1800031f7  test    dil, 1
0x1800031fb  jz      short loc_18000320A
0x1800031fd  mov     edx, 58h ; 'X'; unsigned __int64
0x180003202  mov     rcx, rbx; void *
0x180003205  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000320a  mov     rax, rbx
0x18000320d  mov     rbx, [rsp+28h+arg_0]
0x180003212  add     rsp, 20h
0x180003216  pop     rdi
0x180003217  retn
```
