# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180004524`
- end: `0x180004594`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004d20`

## callees

- `0x180004524`
- `0x180005010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004578`
- `KERNEL32!DeleteCriticalSection` at `0x180004578`

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
0x180004524  mov     [rsp+arg_0], rbx
0x180004529  mov     [rsp+arg_8], rsi
0x18000452e  push    rdi
0x18000452f  sub     rsp, 20h
0x180004533  cmp     dword ptr [rcx], 0
0x180004536  mov     rbx, rcx
0x180004539  jz      short loc_180004584
0x18000453b  mov     rdi, [rcx+10h]
0x18000453f  cmp     rdi, [rcx+18h]
0x180004543  jnb     short loc_180004574
0x180004545  mov     rsi, [rdi]
0x180004548  test    rsi, rsi
0x18000454b  jz      short loc_18000456A
0x18000454d  mov     rcx, [rsi+20h]
0x180004551  test    rcx, rcx
0x180004554  jz      short loc_180004562
0x180004556  mov     rax, [rcx]
0x180004559  mov     rax, [rax+10h]
0x18000455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004562  mov     qword ptr [rsi+20h], 0
0x18000456a  add     rdi, 8
0x18000456e  cmp     rdi, [rbx+18h]
0x180004572  jb      short loc_180004545
0x180004574  lea     rcx, [rbx+20h]; lpCriticalSection
0x180004578  call    cs:__imp_DeleteCriticalSection
0x18000457e  mov     dword ptr [rbx], 0
0x180004584  mov     rbx, [rsp+28h+arg_0]
0x180004589  mov     rsi, [rsp+28h+arg_8]
0x18000458e  add     rsp, 20h
0x180004592  pop     rdi
0x180004593  retn
```
