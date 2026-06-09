# ATL::CComObject<CTaskHandler>::~CComObject<CTaskHandler>(void)

- ea: `0x1800022e4`
- end: `0x180002348`
- name: `??1?$CComObject@VCTaskHandler@@@ATL@@UEAA@XZ`
- size: `100`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002560`

## callees

- `0x1800022e4`
- `0x1800061ec`
- `0x18000b010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000233b`
- `KERNEL32!DeleteCriticalSection` at `0x18000233b`

## pseudocode

```c
void __fastcall ATL::CComObject<CTaskHandler>::~CComObject<CTaskHandler>(__int64 a1)
{
  __int64 v2; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CTaskHandler>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  CTaskHandler::FinalRelease((CTaskHandler *)a1);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = *(_QWORD *)(a1 + 64);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x1800022e4  push    rbx
0x1800022e6  sub     rsp, 20h
0x1800022ea  mov     rbx, rcx
0x1800022ed  lea     rax, ??_7?$CComObject@VCTaskHandler@@@ATL@@6B@; const ATL::CComObject<CTaskHandler>::`vftable'
0x1800022f4  mov     [rcx], rax
0x1800022f7  mov     dword ptr [rcx+8], 0C0000001h
0x1800022fe  call    ?FinalRelease@CTaskHandler@@QEAAXXZ; CTaskHandler::FinalRelease(void)
0x180002303  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000230a  mov     rax, [rcx]
0x18000230d  mov     rax, [rax+10h]
0x180002311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002316  nop
0x180002317  mov     rcx, [rbx+40h]
0x18000231b  test    rcx, rcx
0x18000231e  jz      short loc_18000232D
0x180002320  mov     rax, [rcx]
0x180002323  mov     rax, [rax+10h]
0x180002327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000232c  nop
0x18000232d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002331  cmp     byte ptr [rcx+28h], 0
0x180002335  jz      short loc_180002342
0x180002337  mov     byte ptr [rcx+28h], 0
0x18000233b  call    cs:__imp_DeleteCriticalSection
0x180002341  nop
0x180002342  add     rsp, 20h
0x180002346  pop     rbx
0x180002347  retn
```
