# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000d72c`
- end: `0x18000d79c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010d70`

## callees

- `0x18000d72c`
- `0x180011010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000d780`
- `KERNEL32!DeleteCriticalSection` at `0x18000d780`

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
0x18000d72c  mov     [rsp+arg_0], rbx
0x18000d731  mov     [rsp+arg_8], rsi
0x18000d736  push    rdi
0x18000d737  sub     rsp, 20h
0x18000d73b  cmp     dword ptr [rcx], 0
0x18000d73e  mov     rbx, rcx
0x18000d741  jz      short loc_18000D78C
0x18000d743  mov     rdi, [rcx+10h]
0x18000d747  cmp     rdi, [rcx+18h]
0x18000d74b  jnb     short loc_18000D77C
0x18000d74d  mov     rsi, [rdi]
0x18000d750  test    rsi, rsi
0x18000d753  jz      short loc_18000D772
0x18000d755  mov     rcx, [rsi+20h]
0x18000d759  test    rcx, rcx
0x18000d75c  jz      short loc_18000D76A
0x18000d75e  mov     rax, [rcx]
0x18000d761  mov     rax, [rax+10h]
0x18000d765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d76a  mov     qword ptr [rsi+20h], 0
0x18000d772  add     rdi, 8
0x18000d776  cmp     rdi, [rbx+18h]
0x18000d77a  jb      short loc_18000D74D
0x18000d77c  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000d780  call    cs:__imp_DeleteCriticalSection
0x18000d786  mov     dword ptr [rbx], 0
0x18000d78c  mov     rbx, [rsp+28h+arg_0]
0x18000d791  mov     rsi, [rsp+28h+arg_8]
0x18000d796  add     rsp, 20h
0x18000d79a  pop     rdi
0x18000d79b  retn
```
