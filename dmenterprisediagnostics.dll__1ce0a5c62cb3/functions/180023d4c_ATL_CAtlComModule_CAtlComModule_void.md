# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180023d4c`
- end: `0x180023dbc`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025be0`

## callees

- `0x180023d4c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023da0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023da0`

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
0x180023d4c  mov     [rsp+arg_0], rbx
0x180023d51  mov     [rsp+arg_8], rsi
0x180023d56  push    rdi
0x180023d57  sub     rsp, 20h
0x180023d5b  cmp     dword ptr [rcx], 0
0x180023d5e  mov     rbx, rcx
0x180023d61  jz      short loc_180023DAC
0x180023d63  mov     rdi, [rcx+10h]
0x180023d67  cmp     rdi, [rcx+18h]
0x180023d6b  jnb     short loc_180023D9C
0x180023d6d  mov     rsi, [rdi]
0x180023d70  test    rsi, rsi
0x180023d73  jz      short loc_180023D92
0x180023d75  mov     rcx, [rsi+20h]
0x180023d79  test    rcx, rcx
0x180023d7c  jz      short loc_180023D8A
0x180023d7e  mov     rax, [rcx]
0x180023d81  mov     rax, [rax+10h]
0x180023d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d8a  mov     qword ptr [rsi+20h], 0
0x180023d92  add     rdi, 8
0x180023d96  cmp     rdi, [rbx+18h]
0x180023d9a  jb      short loc_180023D6D
0x180023d9c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180023da0  call    cs:__imp_DeleteCriticalSection
0x180023da6  mov     dword ptr [rbx], 0
0x180023dac  mov     rbx, [rsp+28h+arg_0]
0x180023db1  mov     rsi, [rsp+28h+arg_8]
0x180023db6  add     rsp, 20h
0x180023dba  pop     rdi
0x180023dbb  retn
```
