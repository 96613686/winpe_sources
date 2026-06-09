# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800078a4`
- end: `0x180007914`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b6d0`

## callees

- `0x1800078a4`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800078f8`
- `KERNEL32!DeleteCriticalSection` at `0x1800078f8`

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
0x1800078a4  mov     [rsp+arg_0], rbx
0x1800078a9  mov     [rsp+arg_8], rsi
0x1800078ae  push    rdi
0x1800078af  sub     rsp, 20h
0x1800078b3  cmp     dword ptr [rcx], 0
0x1800078b6  mov     rbx, rcx
0x1800078b9  jz      short loc_180007904
0x1800078bb  mov     rdi, [rcx+10h]
0x1800078bf  cmp     rdi, [rcx+18h]
0x1800078c3  jnb     short loc_1800078F4
0x1800078c5  mov     rsi, [rdi]
0x1800078c8  test    rsi, rsi
0x1800078cb  jz      short loc_1800078EA
0x1800078cd  mov     rcx, [rsi+20h]
0x1800078d1  test    rcx, rcx
0x1800078d4  jz      short loc_1800078E2
0x1800078d6  mov     rax, [rcx]
0x1800078d9  mov     rax, [rax+10h]
0x1800078dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e2  mov     qword ptr [rsi+20h], 0
0x1800078ea  add     rdi, 8
0x1800078ee  cmp     rdi, [rbx+18h]
0x1800078f2  jb      short loc_1800078C5
0x1800078f4  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800078f8  call    cs:__imp_DeleteCriticalSection
0x1800078fe  mov     dword ptr [rbx], 0
0x180007904  mov     rbx, [rsp+28h+arg_0]
0x180007909  mov     rsi, [rsp+28h+arg_8]
0x18000790e  add     rsp, 20h
0x180007912  pop     rdi
0x180007913  retn
```
