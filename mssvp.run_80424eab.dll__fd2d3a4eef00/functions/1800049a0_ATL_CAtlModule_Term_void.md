# ATL::CAtlModule::Term(void)

- ea: `0x1800049a0`
- end: `0x180004a05`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011c4c`

## callees

- `0x1800049a0`
- `0x18000bca0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049ed`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  struct ATL::_ATL_MODULE70 *v2; // rcx
  __int64 v3; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v2 = (ATL::CAtlModule *)((char *)this + 8);
      if ( !this )
        v2 = 0;
      ATL::AtlCallTermFunc(v2);
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800049a0  mov     [rsp+arg_0], rbx
0x1800049a5  push    rdi
0x1800049a6  sub     rsp, 20h
0x1800049aa  mov     rbx, rcx
0x1800049ad  cmp     dword ptr [rcx+8], 0
0x1800049b1  jz      short loc_1800049FA
0x1800049b3  cmp     qword ptr [rcx+10h], 0
0x1800049b8  jz      short loc_1800049D4
0x1800049ba  add     rcx, 8
0x1800049be  xor     eax, eax
0x1800049c0  test    rbx, rbx
0x1800049c3  cmovz   rcx, rax; struct ATL::_ATL_MODULE70 *
0x1800049c7  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800049cc  mov     qword ptr [rbx+10h], 0
0x1800049d4  mov     rcx, [rbx+40h]
0x1800049d8  test    rcx, rcx
0x1800049db  jz      short loc_1800049E9
0x1800049dd  mov     rax, [rcx]
0x1800049e0  mov     rax, [rax+10h]
0x1800049e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049e9  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800049ed  call    cs:__imp_DeleteCriticalSection
0x1800049f3  mov     dword ptr [rbx+8], 0
0x1800049fa  mov     rbx, [rsp+28h+arg_0]
0x1800049ff  add     rsp, 20h
0x180004a03  pop     rdi
0x180004a04  retn
```
