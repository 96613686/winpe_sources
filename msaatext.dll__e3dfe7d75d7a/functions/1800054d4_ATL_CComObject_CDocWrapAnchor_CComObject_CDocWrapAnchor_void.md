# ATL::CComObject<CDocWrapAnchor>::~CComObject<CDocWrapAnchor>(void)

- ea: `0x1800054d4`
- end: `0x180005589`
- name: `??1?$CComObject@VCDocWrapAnchor@@@ATL@@QEAA@XZ`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a7e0`

## callees

- `0x1800054d4`
- `0x1800056cc`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000554e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000556b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000554e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000556b`

## pseudocode

```c
void __fastcall ATL::CComObject<CDocWrapAnchor>::~CComObject<CDocWrapAnchor>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_DWORD *)(a1 + 80) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchor'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchorEx'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IClonableWrapper'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IInternalDocWrap'};
  *(_QWORD *)(a1 + 32) = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ICoCreateLocally'};
  *(_QWORD *)(a1 + 40) = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `CVersionInfo'};
  *(_QWORD *)(a1 + 72) = &ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IServiceProvider'};
  _InterlockedDecrement(&dword_180024B28);
  *(_QWORD *)(a1 + 188) = 0;
  v2 = *(void **)(a1 + 200);
  if ( v2 )
  {
    operator delete[](v2);
    *(_QWORD *)(a1 + 200) = 0;
  }
  v3 = *(void **)(a1 + 208);
  if ( v3 )
  {
    operator delete[](v3);
    *(_QWORD *)(a1 + 208) = 0;
  }
  CDocWrapBase<DocTraitsAnchor>::~CDocWrapBase<DocTraitsAnchor>(a1);
}

```

## disassembly

```asm
0x1800054d4  push    rbx
0x1800054d6  sub     rsp, 20h
0x1800054da  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BITextStoreAnchor@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchor'}
0x1800054e1  mov     dword ptr [rcx+50h], 1
0x1800054e8  mov     [rcx], rax
0x1800054eb  mov     rbx, rcx
0x1800054ee  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BITextStoreAnchorEx@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ITextStoreAnchorEx'}
0x1800054f5  mov     [rcx+8], rax
0x1800054f9  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BIClonableWrapper@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IClonableWrapper'}
0x180005500  mov     [rcx+10h], rax
0x180005504  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BIInternalDocWrap@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IInternalDocWrap'}
0x18000550b  mov     [rcx+18h], rax
0x18000550f  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BICoCreateLocally@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `ICoCreateLocally'}
0x180005516  mov     [rcx+20h], rax
0x18000551a  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BCVersionInfo@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `CVersionInfo'}
0x180005521  mov     [rcx+28h], rax
0x180005525  lea     rax, ??_7?$CComObject@VCDocWrapAnchor@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CDocWrapAnchor>::`vftable'{for `IServiceProvider'}
0x18000552c  mov     [rcx+48h], rax
0x180005530  lock dec cs:dword_180024B28
0x180005537  mov     qword ptr [rcx+0BCh], 0
0x180005542  mov     rcx, [rcx+0C8h]
0x180005549  test    rcx, rcx
0x18000554c  jz      short loc_18000555F
0x18000554e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005554  mov     qword ptr [rbx+0C8h], 0
0x18000555f  mov     rcx, [rbx+0D0h]
0x180005566  test    rcx, rcx
0x180005569  jz      short loc_18000557C
0x18000556b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005571  mov     qword ptr [rbx+0D0h], 0
0x18000557c  mov     rcx, rbx
0x18000557f  add     rsp, 20h
0x180005583  pop     rbx
0x180005584  jmp     ??1?$CDocWrapBase@VDocTraitsAnchor@@@@QEAA@XZ; CDocWrapBase<DocTraitsAnchor>::~CDocWrapBase<DocTraitsAnchor>(void)
```
