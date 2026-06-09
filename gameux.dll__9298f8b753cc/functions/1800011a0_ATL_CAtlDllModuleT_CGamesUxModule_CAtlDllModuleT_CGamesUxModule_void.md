# ATL::CAtlDllModuleT<CGamesUxModule>::~CAtlDllModuleT<CGamesUxModule>(void)

- ea: `0x1800011a0`
- end: `0x18000123b`
- name: `??1?$CAtlDllModuleT@VCGamesUxModule@@@ATL@@UEAA@XZ`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ce0`

## callees

- `0x1800011a0`
- `0x180002d44`
- `0x180004010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180001223`
- `KERNEL32!DeleteCriticalSection` at `0x180001223`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CGamesUxModule>::~CAtlDllModuleT<CGamesUxModule>(__int64 a1)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v1; // rbx
  __int64 *i; // rax
  struct ATL::_ATL_MODULE70 *v4; // rcx
  __int64 v5; // rcx

  v1 = off_1800070B0;
  for ( i = off_1800070B8; v1 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v1 )
  {
    if ( *v1 )
    {
      (*((void (__fastcall **)(_QWORD))*v1 + 8))(0);
      i = off_1800070B8;
    }
  }
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      v4 = (struct ATL::_ATL_MODULE70 *)(a1 + 8);
      if ( !a1 )
        v4 = 0;
      ATL::AtlCallTermFunc(v4);
      *(_QWORD *)(a1 + 16) = 0;
    }
    v5 = *(_QWORD *)(a1 + 64);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800011a0  mov     [rsp+arg_0], rbx
0x1800011a5  push    rdi
0x1800011a6  sub     rsp, 20h
0x1800011aa  mov     rbx, cs:off_1800070B0
0x1800011b1  mov     rdi, rcx
0x1800011b4  mov     rax, cs:off_1800070B8
0x1800011bb  cmp     rbx, rax
0x1800011be  jnb     short loc_1800011E3
0x1800011c0  mov     rdx, [rbx]
0x1800011c3  test    rdx, rdx
0x1800011c6  jz      short loc_1800011DA
0x1800011c8  mov     rax, [rdx+40h]
0x1800011cc  xor     ecx, ecx
0x1800011ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011d3  mov     rax, cs:off_1800070B8
0x1800011da  add     rbx, 8
0x1800011de  cmp     rbx, rax
0x1800011e1  jb      short loc_1800011C0
0x1800011e3  cmp     dword ptr [rdi+8], 0
0x1800011e7  jz      short loc_180001230
0x1800011e9  cmp     qword ptr [rdi+10h], 0
0x1800011ee  jz      short loc_18000120A
0x1800011f0  xor     eax, eax
0x1800011f2  lea     rcx, [rdi+8]
0x1800011f6  test    rdi, rdi
0x1800011f9  cmovz   rcx, rax; struct ATL::_ATL_MODULE70 *
0x1800011fd  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180001202  mov     qword ptr [rdi+10h], 0
0x18000120a  mov     rcx, [rdi+40h]
0x18000120e  test    rcx, rcx
0x180001211  jz      short loc_18000121F
0x180001213  mov     rax, [rcx]
0x180001216  mov     rax, [rax+10h]
0x18000121a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121f  lea     rcx, [rdi+18h]; lpCriticalSection
0x180001223  call    cs:__imp_DeleteCriticalSection
0x180001229  mov     dword ptr [rdi+8], 0
0x180001230  mov     rbx, [rsp+28h+arg_0]
0x180001235  add     rsp, 20h
0x180001239  pop     rdi
0x18000123a  retn
```
