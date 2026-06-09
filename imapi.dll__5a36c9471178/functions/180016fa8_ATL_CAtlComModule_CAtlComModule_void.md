# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180016fa8`
- end: `0x180017018`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018990`

## callees

- `0x180016fa8`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180016ffc`
- `KERNEL32!DeleteCriticalSection` at `0x180016ffc`

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
0x180016fa8  mov     [rsp+arg_0], rbx
0x180016fad  mov     [rsp+arg_8], rsi
0x180016fb2  push    rdi
0x180016fb3  sub     rsp, 20h
0x180016fb7  cmp     dword ptr [rcx], 0
0x180016fba  mov     rbx, rcx
0x180016fbd  jz      short loc_180017008
0x180016fbf  mov     rdi, [rcx+10h]
0x180016fc3  cmp     rdi, [rcx+18h]
0x180016fc7  jnb     short loc_180016FF8
0x180016fc9  mov     rsi, [rdi]
0x180016fcc  test    rsi, rsi
0x180016fcf  jz      short loc_180016FEE
0x180016fd1  mov     rcx, [rsi+20h]
0x180016fd5  test    rcx, rcx
0x180016fd8  jz      short loc_180016FE6
0x180016fda  mov     rax, [rcx]
0x180016fdd  mov     rax, [rax+10h]
0x180016fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe6  mov     qword ptr [rsi+20h], 0
0x180016fee  add     rdi, 8
0x180016ff2  cmp     rdi, [rbx+18h]
0x180016ff6  jb      short loc_180016FC9
0x180016ff8  lea     rcx, [rbx+20h]; lpCriticalSection
0x180016ffc  call    cs:__imp_DeleteCriticalSection
0x180017002  mov     dword ptr [rbx], 0
0x180017008  mov     rbx, [rsp+28h+arg_0]
0x18001700d  mov     rsi, [rsp+28h+arg_8]
0x180017012  add     rsp, 20h
0x180017016  pop     rdi
0x180017017  retn
```
