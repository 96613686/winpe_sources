# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180054f3c`
- end: `0x180054fac`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180055d80`

## callees

- `0x180054f3c`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054f90`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054f90`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180054f3c  mov     [rsp+arg_0], rbx
0x180054f41  mov     [rsp+arg_8], rsi
0x180054f46  push    rdi
0x180054f47  sub     rsp, 20h
0x180054f4b  cmp     dword ptr [rcx], 0
0x180054f4e  mov     rbx, rcx
0x180054f51  jz      short loc_180054F9C
0x180054f53  mov     rdi, [rcx+10h]
0x180054f57  cmp     rdi, [rcx+18h]
0x180054f5b  jnb     short loc_180054F8C
0x180054f5d  mov     rsi, [rdi]
0x180054f60  test    rsi, rsi
0x180054f63  jz      short loc_180054F82
0x180054f65  mov     rcx, [rsi+20h]
0x180054f69  test    rcx, rcx
0x180054f6c  jz      short loc_180054F7A
0x180054f6e  mov     rax, [rcx]
0x180054f71  mov     rax, [rax+10h]
0x180054f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f7a  mov     qword ptr [rsi+20h], 0
0x180054f82  add     rdi, 8
0x180054f86  cmp     rdi, [rbx+18h]
0x180054f8a  jb      short loc_180054F5D
0x180054f8c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180054f90  call    cs:__imp_DeleteCriticalSection
0x180054f96  mov     dword ptr [rbx], 0
0x180054f9c  mov     rbx, [rsp+28h+arg_0]
0x180054fa1  mov     rsi, [rsp+28h+arg_8]
0x180054fa6  add     rsp, 20h
0x180054faa  pop     rdi
0x180054fab  retn
```
