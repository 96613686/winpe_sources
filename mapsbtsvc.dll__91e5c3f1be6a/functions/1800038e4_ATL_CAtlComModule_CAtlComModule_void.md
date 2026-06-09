# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800038e4`
- end: `0x180003954`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800148b0`

## callees

- `0x1800038e4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003938`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003938`

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
0x1800038e4  mov     [rsp+arg_0], rbx
0x1800038e9  mov     [rsp+arg_8], rsi
0x1800038ee  push    rdi
0x1800038ef  sub     rsp, 20h
0x1800038f3  cmp     dword ptr [rcx], 0
0x1800038f6  mov     rbx, rcx
0x1800038f9  jz      short loc_180003944
0x1800038fb  mov     rdi, [rcx+10h]
0x1800038ff  cmp     rdi, [rcx+18h]
0x180003903  jnb     short loc_180003934
0x180003905  mov     rsi, [rdi]
0x180003908  test    rsi, rsi
0x18000390b  jz      short loc_18000392A
0x18000390d  mov     rcx, [rsi+20h]
0x180003911  test    rcx, rcx
0x180003914  jz      short loc_180003922
0x180003916  mov     rax, [rcx]
0x180003919  mov     rax, [rax+10h]
0x18000391d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003922  mov     qword ptr [rsi+20h], 0
0x18000392a  add     rdi, 8
0x18000392e  cmp     rdi, [rbx+18h]
0x180003932  jb      short loc_180003905
0x180003934  lea     rcx, [rbx+20h]; lpCriticalSection
0x180003938  call    cs:__imp_DeleteCriticalSection
0x18000393e  mov     dword ptr [rbx], 0
0x180003944  mov     rbx, [rsp+28h+arg_0]
0x180003949  mov     rsi, [rsp+28h+arg_8]
0x18000394e  add     rsp, 20h
0x180003952  pop     rdi
0x180003953  retn
```
