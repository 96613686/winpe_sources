# ATL::CAtlModule::Term(void)

- ea: `0x18000e2c0`
- end: `0x18000e326`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800169a0`
- `0x18001b9ec`
- `0x180026ce0`

## callees

- `0x18000e2c0`
- `0x180017480`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e30f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e30f`

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
0x18000e2c0  mov     [rsp+arg_0], rbx
0x18000e2c5  push    rdi
0x18000e2c6  sub     rsp, 20h
0x18000e2ca  mov     rbx, rcx
0x18000e2cd  lea     rdi, [rcx+8]
0x18000e2d1  cmp     dword ptr [rdi], 0
0x18000e2d4  jz      short loc_18000E31B
0x18000e2d6  cmp     qword ptr [rcx+10h], 0
0x18000e2db  jz      short loc_18000E2F6
0x18000e2dd  mov     rax, rcx
0x18000e2e0  neg     rax
0x18000e2e3  sbb     rcx, rcx
0x18000e2e6  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18000e2e9  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000e2ee  mov     qword ptr [rbx+10h], 0
0x18000e2f6  mov     rcx, [rbx+40h]
0x18000e2fa  test    rcx, rcx
0x18000e2fd  jz      short loc_18000E30B
0x18000e2ff  mov     rax, [rcx]
0x18000e302  mov     rax, [rax+10h]
0x18000e306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e30b  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000e30f  call    cs:__imp_DeleteCriticalSection
0x18000e315  mov     dword ptr [rdi], 0
0x18000e31b  mov     rbx, [rsp+28h+arg_0]
0x18000e320  add     rsp, 20h
0x18000e324  pop     rdi
0x18000e325  retn
```
