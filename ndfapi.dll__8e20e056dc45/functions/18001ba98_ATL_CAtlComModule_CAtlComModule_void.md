# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18001ba98`
- end: `0x18001bb08`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020ab0`

## callees

- `0x18001ba98`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001baec`
- `KERNEL32!DeleteCriticalSection` at `0x18001baec`

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
0x18001ba98  mov     [rsp+arg_0], rbx
0x18001ba9d  mov     [rsp+arg_8], rsi
0x18001baa2  push    rdi
0x18001baa3  sub     rsp, 20h
0x18001baa7  cmp     dword ptr [rcx], 0
0x18001baaa  mov     rbx, rcx
0x18001baad  jz      short loc_18001BAF8
0x18001baaf  mov     rdi, [rcx+10h]
0x18001bab3  cmp     rdi, [rcx+18h]
0x18001bab7  jnb     short loc_18001BAE8
0x18001bab9  mov     rsi, [rdi]
0x18001babc  test    rsi, rsi
0x18001babf  jz      short loc_18001BADE
0x18001bac1  mov     rcx, [rsi+20h]
0x18001bac5  test    rcx, rcx
0x18001bac8  jz      short loc_18001BAD6
0x18001baca  mov     rax, [rcx]
0x18001bacd  mov     rax, [rax+10h]
0x18001bad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bad6  mov     qword ptr [rsi+20h], 0
0x18001bade  add     rdi, 8
0x18001bae2  cmp     rdi, [rbx+18h]
0x18001bae6  jb      short loc_18001BAB9
0x18001bae8  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001baec  call    cs:__imp_DeleteCriticalSection
0x18001baf2  mov     dword ptr [rbx], 0
0x18001baf8  mov     rbx, [rsp+28h+arg_0]
0x18001bafd  mov     rsi, [rsp+28h+arg_8]
0x18001bb02  add     rsp, 20h
0x18001bb06  pop     rdi
0x18001bb07  retn
```
