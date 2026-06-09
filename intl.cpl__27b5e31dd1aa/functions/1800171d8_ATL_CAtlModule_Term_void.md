# ATL::CAtlModule::Term(void)

- ea: `0x1800171d8`
- end: `0x18001723e`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800135d0`
- `0x180017244`
- `0x18002ac90`

## callees

- `0x180013e90`
- `0x1800171d8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017227`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017227`

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
0x1800171d8  mov     [rsp+arg_0], rbx
0x1800171dd  push    rdi
0x1800171de  sub     rsp, 20h
0x1800171e2  mov     rbx, rcx
0x1800171e5  lea     rdi, [rcx+8]
0x1800171e9  cmp     dword ptr [rdi], 0
0x1800171ec  jz      short loc_180017233
0x1800171ee  cmp     qword ptr [rcx+10h], 0
0x1800171f3  jz      short loc_18001720E
0x1800171f5  mov     rax, rcx
0x1800171f8  neg     rax
0x1800171fb  sbb     rcx, rcx
0x1800171fe  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180017201  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180017206  mov     qword ptr [rbx+10h], 0
0x18001720e  mov     rcx, [rbx+40h]
0x180017212  test    rcx, rcx
0x180017215  jz      short loc_180017223
0x180017217  mov     rax, [rcx]
0x18001721a  mov     rax, [rax+10h]
0x18001721e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017223  lea     rcx, [rbx+18h]; lpCriticalSection
0x180017227  call    cs:__imp_DeleteCriticalSection
0x18001722d  mov     dword ptr [rdi], 0
0x180017233  mov     rbx, [rsp+28h+arg_0]
0x180017238  add     rsp, 20h
0x18001723c  pop     rdi
0x18001723d  retn
```
