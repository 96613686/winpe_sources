# ATL::CComObject<CRehydrationTaskHandler>::~CComObject<CRehydrationTaskHandler>(void)

- ea: `0x180002250`
- end: `0x1800022dc`
- name: `??1?$CComObject@VCRehydrationTaskHandler@@@ATL@@UEAA@XZ`
- size: `140`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002520`

## callees

- `0x180002250`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180002273`
- `KERNEL32!CloseHandle` at `0x180002273`
- `KERNEL32!DeleteCriticalSection` at `0x1800022cf`
- `KERNEL32!DeleteCriticalSection` at `0x1800022cf`

## pseudocode

```c
void __fastcall ATL::CComObject<CRehydrationTaskHandler>::~CComObject<CRehydrationTaskHandler>(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CRehydrationTaskHandler>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  v2 = *(void **)(a1 + 80);
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)(a1 + 80) = 0;
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(_QWORD *)(a1 + 72);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 64);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180002250  push    rbx
0x180002252  sub     rsp, 20h
0x180002256  mov     rbx, rcx
0x180002259  lea     rax, ??_7?$CComObject@VCRehydrationTaskHandler@@@ATL@@6B@; const ATL::CComObject<CRehydrationTaskHandler>::`vftable'
0x180002260  mov     [rcx], rax
0x180002263  mov     dword ptr [rcx+8], 0C0000001h
0x18000226a  mov     rcx, [rcx+50h]; hObject
0x18000226e  test    rcx, rcx
0x180002271  jz      short loc_180002281
0x180002273  call    cs:__imp_CloseHandle
0x180002279  mov     qword ptr [rbx+50h], 0
0x180002281  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002288  mov     rax, [rcx]
0x18000228b  mov     rax, [rax+10h]
0x18000228f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002294  nop
0x180002295  mov     rcx, [rbx+48h]
0x180002299  test    rcx, rcx
0x18000229c  jz      short loc_1800022AB
0x18000229e  mov     rax, [rcx]
0x1800022a1  mov     rax, [rax+10h]
0x1800022a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022aa  nop
0x1800022ab  mov     rcx, [rbx+40h]
0x1800022af  test    rcx, rcx
0x1800022b2  jz      short loc_1800022C1
0x1800022b4  mov     rax, [rcx]
0x1800022b7  mov     rax, [rax+10h]
0x1800022bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c0  nop
0x1800022c1  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800022c5  cmp     byte ptr [rcx+28h], 0
0x1800022c9  jz      short loc_1800022D6
0x1800022cb  mov     byte ptr [rcx+28h], 0
0x1800022cf  call    cs:__imp_DeleteCriticalSection
0x1800022d5  nop
0x1800022d6  add     rsp, 20h
0x1800022da  pop     rbx
0x1800022db  retn
```
