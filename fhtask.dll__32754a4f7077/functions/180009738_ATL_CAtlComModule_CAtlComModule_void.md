# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180009738`
- end: `0x1800097a8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0f0`

## callees

- `0x180009738`
- `0x18000b010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000978c`
- `KERNEL32!DeleteCriticalSection` at `0x18000978c`

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
0x180009738  mov     [rsp+arg_0], rbx
0x18000973d  mov     [rsp+arg_8], rsi
0x180009742  push    rdi
0x180009743  sub     rsp, 20h
0x180009747  cmp     dword ptr [rcx], 0
0x18000974a  mov     rbx, rcx
0x18000974d  jz      short loc_180009798
0x18000974f  mov     rdi, [rcx+10h]
0x180009753  cmp     rdi, [rcx+18h]
0x180009757  jnb     short loc_180009788
0x180009759  mov     rsi, [rdi]
0x18000975c  test    rsi, rsi
0x18000975f  jz      short loc_18000977E
0x180009761  mov     rcx, [rsi+20h]
0x180009765  test    rcx, rcx
0x180009768  jz      short loc_180009776
0x18000976a  mov     rax, [rcx]
0x18000976d  mov     rax, [rax+10h]
0x180009771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009776  mov     qword ptr [rsi+20h], 0
0x18000977e  add     rdi, 8
0x180009782  cmp     rdi, [rbx+18h]
0x180009786  jb      short loc_180009759
0x180009788  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000978c  call    cs:__imp_DeleteCriticalSection
0x180009792  mov     dword ptr [rbx], 0
0x180009798  mov     rbx, [rsp+28h+arg_0]
0x18000979d  mov     rsi, [rsp+28h+arg_8]
0x1800097a2  add     rsp, 20h
0x1800097a6  pop     rdi
0x1800097a7  retn
```
