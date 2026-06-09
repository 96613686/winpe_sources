# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180003eb0`
- end: `0x180003f15`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae60`

## callees

- `0x180003eb0`
- `0x18000bca0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003efd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003efd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
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
0x180003eb0  mov     [rsp+arg_0], rbx
0x180003eb5  push    rdi
0x180003eb6  sub     rsp, 20h
0x180003eba  mov     rbx, rcx
0x180003ebd  cmp     dword ptr [rcx+8], 0
0x180003ec1  jz      short loc_180003F0A
0x180003ec3  cmp     qword ptr [rcx+10h], 0
0x180003ec8  jz      short loc_180003EE4
0x180003eca  add     rcx, 8
0x180003ece  xor     eax, eax
0x180003ed0  test    rbx, rbx
0x180003ed3  cmovz   rcx, rax; struct ATL::_ATL_MODULE70 *
0x180003ed7  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180003edc  mov     qword ptr [rbx+10h], 0
0x180003ee4  mov     rcx, [rbx+40h]
0x180003ee8  test    rcx, rcx
0x180003eeb  jz      short loc_180003EF9
0x180003eed  mov     rax, [rcx]
0x180003ef0  mov     rax, [rax+10h]
0x180003ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef9  lea     rcx, [rbx+18h]; lpCriticalSection
0x180003efd  call    cs:__imp_DeleteCriticalSection
0x180003f03  mov     dword ptr [rbx+8], 0
0x180003f0a  mov     rbx, [rsp+28h+arg_0]
0x180003f0f  add     rsp, 20h
0x180003f13  pop     rdi
0x180003f14  retn
```
