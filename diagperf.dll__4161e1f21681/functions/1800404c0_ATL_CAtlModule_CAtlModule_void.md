# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800404c0`
- end: `0x180040526`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18004049c`
- `0x1800d58b0`

## callees

- `0x1800404c0`
- `0x18005c470`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004050f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004050f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v2 & -(__int64)(this != 0)));
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800404c0  mov     [rsp+arg_0], rbx
0x1800404c5  push    rdi
0x1800404c6  sub     rsp, 20h
0x1800404ca  mov     rbx, rcx
0x1800404cd  lea     rdi, [rcx+8]
0x1800404d1  cmp     dword ptr [rdi], 0
0x1800404d4  jz      short loc_18004051B
0x1800404d6  cmp     qword ptr [rcx+10h], 0
0x1800404db  jz      short loc_1800404F6
0x1800404dd  mov     rax, rcx
0x1800404e0  neg     rax
0x1800404e3  sbb     rcx, rcx
0x1800404e6  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x1800404e9  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800404ee  mov     qword ptr [rbx+10h], 0
0x1800404f6  mov     rcx, [rbx+40h]
0x1800404fa  test    rcx, rcx
0x1800404fd  jz      short loc_18004050B
0x1800404ff  mov     rax, [rcx]
0x180040502  mov     rax, [rax+10h]
0x180040506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004050b  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004050f  call    cs:__imp_DeleteCriticalSection
0x180040515  mov     dword ptr [rdi], 0
0x18004051b  mov     rbx, [rsp+28h+arg_0]
0x180040520  add     rsp, 20h
0x180040524  pop     rdi
0x180040525  retn
```
