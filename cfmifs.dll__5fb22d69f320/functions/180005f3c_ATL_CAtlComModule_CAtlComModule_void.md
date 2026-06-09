# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180005f3c`
- end: `0x180005fac`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006460`

## callees

- `0x180005f3c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005f90`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005f90`

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
0x180005f3c  mov     [rsp+arg_0], rbx
0x180005f41  mov     [rsp+arg_8], rsi
0x180005f46  push    rdi
0x180005f47  sub     rsp, 20h
0x180005f4b  cmp     dword ptr [rcx], 0
0x180005f4e  mov     rbx, rcx
0x180005f51  jz      short loc_180005F9C
0x180005f53  mov     rdi, [rcx+10h]
0x180005f57  cmp     rdi, [rcx+18h]
0x180005f5b  jnb     short loc_180005F8C
0x180005f5d  mov     rsi, [rdi]
0x180005f60  test    rsi, rsi
0x180005f63  jz      short loc_180005F82
0x180005f65  mov     rcx, [rsi+20h]
0x180005f69  test    rcx, rcx
0x180005f6c  jz      short loc_180005F7A
0x180005f6e  mov     rax, [rcx]
0x180005f71  mov     rax, [rax+10h]
0x180005f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7a  mov     qword ptr [rsi+20h], 0
0x180005f82  add     rdi, 8
0x180005f86  cmp     rdi, [rbx+18h]
0x180005f8a  jb      short loc_180005F5D
0x180005f8c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180005f90  call    cs:__imp_DeleteCriticalSection
0x180005f96  mov     dword ptr [rbx], 0
0x180005f9c  mov     rbx, [rsp+28h+arg_0]
0x180005fa1  mov     rsi, [rsp+28h+arg_8]
0x180005fa6  add     rsp, 20h
0x180005faa  pop     rdi
0x180005fab  retn
```
