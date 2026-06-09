# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000a760`
- end: `0x18000a7cb`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `107`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001570c`

## callees

- `0x18000a760`
- `0x180016784`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a78a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a78a`

## pseudocode

```c
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
0x18000a760  mov     [rsp+arg_0], rbx
0x18000a765  push    rdi
0x18000a766  sub     rsp, 20h
0x18000a76a  mov     rbx, rcx
0x18000a76d  lea     rdi, [rcx+8]
0x18000a771  cmp     dword ptr [rdi], 0
0x18000a774  jz      short loc_18000A796
0x18000a776  cmp     qword ptr [rcx+10h], 0
0x18000a77b  jnz     short loc_18000A7A1
0x18000a77d  mov     rcx, [rbx+40h]
0x18000a781  test    rcx, rcx
0x18000a784  jnz     short loc_18000A7BC
0x18000a786  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000a78a  call    cs:__imp_DeleteCriticalSection
0x18000a790  mov     dword ptr [rdi], 0
0x18000a796  mov     rbx, [rsp+28h+arg_0]
0x18000a79b  add     rsp, 20h
0x18000a79f  pop     rdi
0x18000a7a0  retn
0x18000a7a1  mov     rax, rbx
0x18000a7a4  neg     rax
0x18000a7a7  sbb     rcx, rcx
0x18000a7aa  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18000a7ad  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000a7b2  mov     qword ptr [rbx+10h], 0
0x18000a7ba  jmp     short loc_18000A77D
0x18000a7bc  mov     rax, [rcx]
0x18000a7bf  mov     rax, [rax+10h]
0x18000a7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c8  jmp     short loc_18000A786
```
