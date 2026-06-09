# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000de48`
- end: `0x18000deae`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b284`
- `0x180022730`
- `0x180022760`

## callees

- `0x18000de48`
- `0x180018044`
- `0x180023010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000de97`
- `KERNEL32!DeleteCriticalSection` at `0x18000de97`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // rdi
  __int64 v3; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v1 & -(__int64)(this != 0)));
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18000de48  mov     [rsp+arg_0], rbx
0x18000de4d  push    rdi
0x18000de4e  sub     rsp, 20h
0x18000de52  lea     rdi, [rcx+8]
0x18000de56  mov     rbx, rcx
0x18000de59  cmp     dword ptr [rdi], 0
0x18000de5c  jz      short loc_18000DEA3
0x18000de5e  cmp     qword ptr [rcx+10h], 0
0x18000de63  jz      short loc_18000DE7E
0x18000de65  mov     rax, rcx
0x18000de68  neg     rax
0x18000de6b  sbb     rcx, rcx
0x18000de6e  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18000de71  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000de76  mov     qword ptr [rbx+10h], 0
0x18000de7e  mov     rcx, [rbx+40h]
0x18000de82  test    rcx, rcx
0x18000de85  jz      short loc_18000DE93
0x18000de87  mov     rax, [rcx]
0x18000de8a  mov     rax, [rax+10h]
0x18000de8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de93  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000de97  call    cs:__imp_DeleteCriticalSection
0x18000de9d  mov     dword ptr [rdi], 0
0x18000dea3  mov     rbx, [rsp+28h+arg_0]
0x18000dea8  add     rsp, 20h
0x18000deac  pop     rdi
0x18000dead  retn
```
