# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000eb68`
- end: `0x18000ebce`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a08`
- `0x180049e80`

## callees

- `0x18000eb68`
- `0x180041824`
- `0x18004a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000ebb7`
- `KERNEL32!DeleteCriticalSection` at `0x18000ebb7`

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
0x18000eb68  mov     [rsp+arg_0], rbx
0x18000eb6d  push    rdi
0x18000eb6e  sub     rsp, 20h
0x18000eb72  lea     rdi, [rcx+8]
0x18000eb76  mov     rbx, rcx
0x18000eb79  cmp     dword ptr [rdi], 0
0x18000eb7c  jz      short loc_18000EBC3
0x18000eb7e  cmp     qword ptr [rcx+10h], 0
0x18000eb83  jz      short loc_18000EB9E
0x18000eb85  mov     rax, rcx
0x18000eb88  neg     rax
0x18000eb8b  sbb     rcx, rcx
0x18000eb8e  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18000eb91  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000eb96  mov     qword ptr [rbx+10h], 0
0x18000eb9e  mov     rcx, [rbx+40h]
0x18000eba2  test    rcx, rcx
0x18000eba5  jz      short loc_18000EBB3
0x18000eba7  mov     rax, [rcx]
0x18000ebaa  mov     rax, [rax+10h]
0x18000ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebb3  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000ebb7  call    cs:__imp_DeleteCriticalSection
0x18000ebbd  mov     dword ptr [rdi], 0
0x18000ebc3  mov     rbx, [rsp+28h+arg_0]
0x18000ebc8  add     rsp, 20h
0x18000ebcc  pop     rdi
0x18000ebcd  retn
```
