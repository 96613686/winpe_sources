# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000ddd0`
- end: `0x18000de40`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022870`

## callees

- `0x18000ddd0`
- `0x180023010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000de24`
- `KERNEL32!DeleteCriticalSection` at `0x18000de24`

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
0x18000ddd0  mov     [rsp+arg_0], rbx
0x18000ddd5  mov     [rsp+arg_8], rsi
0x18000ddda  push    rdi
0x18000dddb  sub     rsp, 20h
0x18000dddf  cmp     dword ptr [rcx], 0
0x18000dde2  mov     rbx, rcx
0x18000dde5  jz      short loc_18000DE30
0x18000dde7  mov     rdi, [rcx+10h]
0x18000ddeb  cmp     rdi, [rcx+18h]
0x18000ddef  jnb     short loc_18000DE20
0x18000ddf1  mov     rsi, [rdi]
0x18000ddf4  test    rsi, rsi
0x18000ddf7  jz      short loc_18000DE16
0x18000ddf9  mov     rcx, [rsi+20h]
0x18000ddfd  test    rcx, rcx
0x18000de00  jz      short loc_18000DE0E
0x18000de02  mov     rax, [rcx]
0x18000de05  mov     rax, [rax+10h]
0x18000de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0e  mov     qword ptr [rsi+20h], 0
0x18000de16  add     rdi, 8
0x18000de1a  cmp     rdi, [rbx+18h]
0x18000de1e  jb      short loc_18000DDF1
0x18000de20  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000de24  call    cs:__imp_DeleteCriticalSection
0x18000de2a  mov     dword ptr [rbx], 0
0x18000de30  mov     rbx, [rsp+28h+arg_0]
0x18000de35  mov     rsi, [rsp+28h+arg_8]
0x18000de3a  add     rsp, 20h
0x18000de3e  pop     rdi
0x18000de3f  retn
```
