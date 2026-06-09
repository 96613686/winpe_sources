# ATL::CComAggObject<CTaskHandler>::~CComAggObject<CTaskHandler>(void)

- ea: `0x1800021e0`
- end: `0x180002248`
- name: `??1?$CComAggObject@VCTaskHandler@@@ATL@@UEAA@XZ`
- size: `104`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800024e0`

## callees

- `0x1800021e0`
- `0x1800061ec`
- `0x18000b010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000223b`
- `KERNEL32!DeleteCriticalSection` at `0x18000223b`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CTaskHandler>::~CComAggObject<CTaskHandler>(__int64 a1)
{
  __int64 v2; // rcx

  *(_QWORD *)a1 = &ATL::CComAggObject<CTaskHandler>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  CTaskHandler::FinalRelease((CTaskHandler *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = *(_QWORD *)(a1 + 88);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_BYTE *)(a1 + 80) )
  {
    *(_BYTE *)(a1 + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
}

```

## disassembly

```asm
0x1800021e0  push    rbx
0x1800021e2  sub     rsp, 20h
0x1800021e6  mov     rbx, rcx
0x1800021e9  lea     rax, ??_7?$CComAggObject@VCTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CTaskHandler>::`vftable'
0x1800021f0  mov     [rcx], rax
0x1800021f3  mov     dword ptr [rcx+8], 0C0000001h
0x1800021fa  add     rcx, 18h; this
0x1800021fe  call    ?FinalRelease@CTaskHandler@@QEAAXXZ; CTaskHandler::FinalRelease(void)
0x180002203  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000220a  mov     rax, [rcx]
0x18000220d  mov     rax, [rax+10h]
0x180002211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002216  nop
0x180002217  mov     rcx, [rbx+58h]
0x18000221b  test    rcx, rcx
0x18000221e  jz      short loc_18000222D
0x180002220  mov     rax, [rcx]
0x180002223  mov     rax, [rax+10h]
0x180002227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222c  nop
0x18000222d  lea     rcx, [rbx+28h]; lpCriticalSection
0x180002231  cmp     byte ptr [rcx+28h], 0
0x180002235  jz      short loc_180002242
0x180002237  mov     byte ptr [rcx+28h], 0
0x18000223b  call    cs:__imp_DeleteCriticalSection
0x180002241  nop
0x180002242  add     rsp, 20h
0x180002246  pop     rbx
0x180002247  retn
```
