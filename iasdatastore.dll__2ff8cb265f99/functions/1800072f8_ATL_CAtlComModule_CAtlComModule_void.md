# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800072f8`
- end: `0x180007368`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f030`

## callees

- `0x1800072f8`
- `0x180010010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000734c`
- `KERNEL32!DeleteCriticalSection` at `0x18000734c`

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
0x1800072f8  mov     [rsp+arg_0], rbx
0x1800072fd  mov     [rsp+arg_8], rsi
0x180007302  push    rdi
0x180007303  sub     rsp, 20h
0x180007307  cmp     dword ptr [rcx], 0
0x18000730a  mov     rbx, rcx
0x18000730d  jz      short loc_180007358
0x18000730f  mov     rdi, [rcx+10h]
0x180007313  cmp     rdi, [rcx+18h]
0x180007317  jnb     short loc_180007348
0x180007319  mov     rsi, [rdi]
0x18000731c  test    rsi, rsi
0x18000731f  jz      short loc_18000733E
0x180007321  mov     rcx, [rsi+20h]
0x180007325  test    rcx, rcx
0x180007328  jz      short loc_180007336
0x18000732a  mov     rax, [rcx]
0x18000732d  mov     rax, [rax+10h]
0x180007331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007336  mov     qword ptr [rsi+20h], 0
0x18000733e  add     rdi, 8
0x180007342  cmp     rdi, [rbx+18h]
0x180007346  jb      short loc_180007319
0x180007348  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000734c  call    cs:__imp_DeleteCriticalSection
0x180007352  mov     dword ptr [rbx], 0
0x180007358  mov     rbx, [rsp+28h+arg_0]
0x18000735d  mov     rsi, [rsp+28h+arg_8]
0x180007362  add     rsp, 20h
0x180007366  pop     rdi
0x180007367  retn
```
