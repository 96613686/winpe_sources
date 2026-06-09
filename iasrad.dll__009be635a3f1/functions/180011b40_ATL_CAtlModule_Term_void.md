# ATL::CAtlModule::Term(void)

- ea: `0x180011b40`
- end: `0x180011ba6`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e610`
- `0x180011bac`
- `0x18002fda0`

## callees

- `0x18000ef40`
- `0x180011b40`
- `0x180030010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011b8f`
- `KERNEL32!DeleteCriticalSection` at `0x180011b8f`

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
0x180011b40  mov     [rsp+arg_0], rbx
0x180011b45  push    rdi
0x180011b46  sub     rsp, 20h
0x180011b4a  mov     rbx, rcx
0x180011b4d  lea     rdi, [rcx+8]
0x180011b51  cmp     dword ptr [rdi], 0
0x180011b54  jz      short loc_180011B9B
0x180011b56  cmp     qword ptr [rcx+10h], 0
0x180011b5b  jz      short loc_180011B76
0x180011b5d  mov     rax, rcx
0x180011b60  neg     rax
0x180011b63  sbb     rcx, rcx
0x180011b66  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180011b69  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180011b6e  mov     qword ptr [rbx+10h], 0
0x180011b76  mov     rcx, [rbx+40h]
0x180011b7a  test    rcx, rcx
0x180011b7d  jz      short loc_180011B8B
0x180011b7f  mov     rax, [rcx]
0x180011b82  mov     rax, [rax+10h]
0x180011b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b8b  lea     rcx, [rbx+18h]; lpCriticalSection
0x180011b8f  call    cs:__imp_DeleteCriticalSection
0x180011b95  mov     dword ptr [rdi], 0
0x180011b9b  mov     rbx, [rsp+28h+arg_0]
0x180011ba0  add     rsp, 20h
0x180011ba4  pop     rdi
0x180011ba5  retn
```
