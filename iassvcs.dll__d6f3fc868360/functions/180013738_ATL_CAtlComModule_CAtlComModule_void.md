# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180013738`
- end: `0x1800137a8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018d60`

## callees

- `0x180013738`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001378c`
- `KERNEL32!DeleteCriticalSection` at `0x18001378c`

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
0x180013738  mov     [rsp+arg_0], rbx
0x18001373d  mov     [rsp+arg_8], rsi
0x180013742  push    rdi
0x180013743  sub     rsp, 20h
0x180013747  cmp     dword ptr [rcx], 0
0x18001374a  mov     rbx, rcx
0x18001374d  jz      short loc_180013798
0x18001374f  mov     rdi, [rcx+10h]
0x180013753  cmp     rdi, [rcx+18h]
0x180013757  jnb     short loc_180013788
0x180013759  mov     rsi, [rdi]
0x18001375c  test    rsi, rsi
0x18001375f  jz      short loc_18001377E
0x180013761  mov     rcx, [rsi+20h]
0x180013765  test    rcx, rcx
0x180013768  jz      short loc_180013776
0x18001376a  mov     rax, [rcx]
0x18001376d  mov     rax, [rax+10h]
0x180013771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013776  mov     qword ptr [rsi+20h], 0
0x18001377e  add     rdi, 8
0x180013782  cmp     rdi, [rbx+18h]
0x180013786  jb      short loc_180013759
0x180013788  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001378c  call    cs:__imp_DeleteCriticalSection
0x180013792  mov     dword ptr [rbx], 0
0x180013798  mov     rbx, [rsp+28h+arg_0]
0x18001379d  mov     rsi, [rsp+28h+arg_8]
0x1800137a2  add     rsp, 20h
0x1800137a6  pop     rdi
0x1800137a7  retn
```
