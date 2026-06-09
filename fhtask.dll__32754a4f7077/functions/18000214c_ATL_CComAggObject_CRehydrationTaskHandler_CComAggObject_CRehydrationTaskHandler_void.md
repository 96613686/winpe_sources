# ATL::CComAggObject<CRehydrationTaskHandler>::~CComAggObject<CRehydrationTaskHandler>(void)

- ea: `0x18000214c`
- end: `0x1800021d8`
- name: `??1?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@UEAA@XZ`
- size: `140`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800024a0`

## callees

- `0x18000214c`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000216f`
- `KERNEL32!CloseHandle` at `0x18000216f`
- `KERNEL32!DeleteCriticalSection` at `0x1800021cb`
- `KERNEL32!DeleteCriticalSection` at `0x1800021cb`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CRehydrationTaskHandler>::~CComAggObject<CRehydrationTaskHandler>(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComAggObject<CRehydrationTaskHandler>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  v2 = *(void **)(a1 + 104);
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)(a1 + 104) = 0;
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(_QWORD *)(a1 + 96);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 88);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *(_BYTE *)(a1 + 80) )
  {
    *(_BYTE *)(a1 + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
}

```

## disassembly

```asm
0x18000214c  push    rbx
0x18000214e  sub     rsp, 20h
0x180002152  mov     rbx, rcx
0x180002155  lea     rax, ??_7?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CRehydrationTaskHandler>::`vftable'
0x18000215c  mov     [rcx], rax
0x18000215f  mov     dword ptr [rcx+8], 0C0000001h
0x180002166  mov     rcx, [rcx+68h]; hObject
0x18000216a  test    rcx, rcx
0x18000216d  jz      short loc_18000217D
0x18000216f  call    cs:__imp_CloseHandle
0x180002175  mov     qword ptr [rbx+68h], 0
0x18000217d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002184  mov     rax, [rcx]
0x180002187  mov     rax, [rax+10h]
0x18000218b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002190  nop
0x180002191  mov     rcx, [rbx+60h]
0x180002195  test    rcx, rcx
0x180002198  jz      short loc_1800021A7
0x18000219a  mov     rax, [rcx]
0x18000219d  mov     rax, [rax+10h]
0x1800021a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a6  nop
0x1800021a7  mov     rcx, [rbx+58h]
0x1800021ab  test    rcx, rcx
0x1800021ae  jz      short loc_1800021BD
0x1800021b0  mov     rax, [rcx]
0x1800021b3  mov     rax, [rax+10h]
0x1800021b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021bc  nop
0x1800021bd  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800021c1  cmp     byte ptr [rcx+28h], 0
0x1800021c5  jz      short loc_1800021D2
0x1800021c7  mov     byte ptr [rcx+28h], 0
0x1800021cb  call    cs:__imp_DeleteCriticalSection
0x1800021d1  nop
0x1800021d2  add     rsp, 20h
0x1800021d6  pop     rbx
0x1800021d7  retn
```
