# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000c6f8`
- end: `0x18000c768`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d470`

## callees

- `0x18000c6f8`
- `0x18002e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c74c`
- `KERNEL32!DeleteCriticalSection` at `0x18000c74c`

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
0x18000c6f8  mov     [rsp+arg_0], rbx
0x18000c6fd  mov     [rsp+arg_8], rsi
0x18000c702  push    rdi
0x18000c703  sub     rsp, 20h
0x18000c707  cmp     dword ptr [rcx], 0
0x18000c70a  mov     rbx, rcx
0x18000c70d  jz      short loc_18000C758
0x18000c70f  mov     rdi, [rcx+10h]
0x18000c713  cmp     rdi, [rcx+18h]
0x18000c717  jnb     short loc_18000C748
0x18000c719  mov     rsi, [rdi]
0x18000c71c  test    rsi, rsi
0x18000c71f  jz      short loc_18000C73E
0x18000c721  mov     rcx, [rsi+20h]
0x18000c725  test    rcx, rcx
0x18000c728  jz      short loc_18000C736
0x18000c72a  mov     rax, [rcx]
0x18000c72d  mov     rax, [rax+10h]
0x18000c731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c736  mov     qword ptr [rsi+20h], 0
0x18000c73e  add     rdi, 8
0x18000c742  cmp     rdi, [rbx+18h]
0x18000c746  jb      short loc_18000C719
0x18000c748  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000c74c  call    cs:__imp_DeleteCriticalSection
0x18000c752  mov     dword ptr [rbx], 0
0x18000c758  mov     rbx, [rsp+28h+arg_0]
0x18000c75d  mov     rsi, [rsp+28h+arg_8]
0x18000c762  add     rsp, 20h
0x18000c766  pop     rdi
0x18000c767  retn
```
