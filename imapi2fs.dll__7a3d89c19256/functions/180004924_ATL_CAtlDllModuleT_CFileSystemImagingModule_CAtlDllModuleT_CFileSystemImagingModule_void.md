# ATL::CAtlDllModuleT<CFileSystemImagingModule>::~CAtlDllModuleT<CFileSystemImagingModule>(void)

- ea: `0x180004924`
- end: `0x1800049bd`
- name: `??1?$CAtlDllModuleT@VCFileSystemImagingModule@@@ATL@@UEAA@XZ`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025a60`

## callees

- `0x180004924`
- `0x180026304`
- `0x180088010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800049a6`
- `KERNEL32!DeleteCriticalSection` at `0x1800049a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlDllModuleT<CFileSystemImagingModule>::~CAtlDllModuleT<CFileSystemImagingModule>(__int64 a1)
{
  struct _LIST_ENTRY *Blink; // rdi
  PLIST_ENTRY OrderedPointer; // rax
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx

  Blink = ATL::_AtlComModule.InsertOrderList.Blink;
  OrderedPointer = ATL::_AtlComModule.OrderedPointer;
  while ( Blink < OrderedPointer )
  {
    if ( Blink->Flink )
    {
      ((void (__fastcall *)(_QWORD))Blink->Flink[4].Flink)(0);
      OrderedPointer = ATL::_AtlComModule.OrderedPointer;
    }
    Blink = (struct _LIST_ENTRY *)((char *)Blink + 8);
  }
  v4 = a1 + 8;
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v4 & -(__int64)(a1 != 0)));
      *(_QWORD *)(a1 + 16) = 0;
    }
    v5 = *(_QWORD *)(a1 + 64);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    *(_DWORD *)v4 = 0;
  }
}

```

## disassembly

```asm
0x180004924  mov     [rsp+arg_0], rbx
0x180004929  push    rdi
0x18000492a  sub     rsp, 20h
0x18000492e  mov     rbx, rcx
0x180004931  mov     rdi, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.InsertOrderList.Blink; ATL::CAtlComModule ATL::_AtlComModule ...
0x180004938  mov     rax, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.OrderedPointer; ATL::CAtlComModule ATL::_AtlComModule ...
0x18000493f  jmp     short loc_18000495F
0x180004941  mov     rdx, [rdi]
0x180004944  test    rdx, rdx
0x180004947  jz      short loc_18000495B
0x180004949  xor     ecx, ecx
0x18000494b  mov     rax, [rdx+40h]
0x18000494f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004954  mov     rax, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.OrderedPointer; ATL::CAtlComModule ATL::_AtlComModule ...
0x18000495b  add     rdi, 8
0x18000495f  cmp     rdi, rax
0x180004962  jb      short loc_180004941
0x180004964  lea     rdi, [rbx+8]
0x180004968  cmp     dword ptr [rdi], 0
0x18000496b  jz      short loc_1800049B2
0x18000496d  cmp     qword ptr [rbx+10h], 0
0x180004972  jz      short loc_18000498D
0x180004974  mov     rax, rbx
0x180004977  neg     rax
0x18000497a  sbb     rcx, rcx
0x18000497d  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180004980  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180004985  mov     qword ptr [rbx+10h], 0
0x18000498d  mov     rcx, [rbx+40h]
0x180004991  test    rcx, rcx
0x180004994  jz      short loc_1800049A2
0x180004996  mov     rax, [rcx]
0x180004999  mov     rax, [rax+10h]
0x18000499d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a2  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800049a6  call    cs:__imp_DeleteCriticalSection
0x1800049ac  mov     dword ptr [rdi], 0
0x1800049b2  mov     rbx, [rsp+28h+arg_0]
0x1800049b7  add     rsp, 20h
0x1800049bb  pop     rdi
0x1800049bc  retn
```
