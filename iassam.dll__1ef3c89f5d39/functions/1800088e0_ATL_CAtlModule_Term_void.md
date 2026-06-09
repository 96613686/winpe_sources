# ATL::CAtlModule::Term(void)

- ea: `0x1800088e0`
- end: `0x180008946`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800038d0`
- `0x18000894c`
- `0x18002d410`

## callees

- `0x1800042b0`
- `0x1800088e0`
- `0x18002e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000892f`
- `KERNEL32!DeleteCriticalSection` at `0x18000892f`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
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
0x1800088e0  mov     [rsp+arg_0], rbx
0x1800088e5  push    rdi
0x1800088e6  sub     rsp, 20h
0x1800088ea  mov     rbx, rcx
0x1800088ed  lea     rdi, [rcx+8]
0x1800088f1  cmp     dword ptr [rdi], 0
0x1800088f4  jz      short loc_18000893B
0x1800088f6  cmp     qword ptr [rcx+10h], 0
0x1800088fb  jz      short loc_180008916
0x1800088fd  mov     rax, rcx
0x180008900  neg     rax
0x180008903  sbb     rcx, rcx
0x180008906  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180008909  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000890e  mov     qword ptr [rbx+10h], 0
0x180008916  mov     rcx, [rbx+40h]
0x18000891a  test    rcx, rcx
0x18000891d  jz      short loc_18000892B
0x18000891f  mov     rax, [rcx]
0x180008922  mov     rax, [rax+10h]
0x180008926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000892b  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000892f  call    cs:__imp_DeleteCriticalSection
0x180008935  mov     dword ptr [rdi], 0
0x18000893b  mov     rbx, [rsp+28h+arg_0]
0x180008940  add     rsp, 20h
0x180008944  pop     rdi
0x180008945  retn
```
