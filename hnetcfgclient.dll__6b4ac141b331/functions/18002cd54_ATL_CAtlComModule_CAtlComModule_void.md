# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002cd54`
- end: `0x18002cdc4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e200`

## callees

- `0x18002cd54`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cda8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cda8`

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
0x18002cd54  mov     [rsp+arg_0], rbx
0x18002cd59  mov     [rsp+arg_8], rsi
0x18002cd5e  push    rdi
0x18002cd5f  sub     rsp, 20h
0x18002cd63  cmp     dword ptr [rcx], 0
0x18002cd66  mov     rbx, rcx
0x18002cd69  jz      short loc_18002CDB4
0x18002cd6b  mov     rdi, [rcx+10h]
0x18002cd6f  cmp     rdi, [rcx+18h]
0x18002cd73  jnb     short loc_18002CDA4
0x18002cd75  mov     rsi, [rdi]
0x18002cd78  test    rsi, rsi
0x18002cd7b  jz      short loc_18002CD9A
0x18002cd7d  mov     rcx, [rsi+20h]
0x18002cd81  test    rcx, rcx
0x18002cd84  jz      short loc_18002CD92
0x18002cd86  mov     rax, [rcx]
0x18002cd89  mov     rax, [rax+10h]
0x18002cd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd92  mov     qword ptr [rsi+20h], 0
0x18002cd9a  add     rdi, 8
0x18002cd9e  cmp     rdi, [rbx+18h]
0x18002cda2  jb      short loc_18002CD75
0x18002cda4  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002cda8  call    cs:__imp_DeleteCriticalSection
0x18002cdae  mov     dword ptr [rbx], 0
0x18002cdb4  mov     rbx, [rsp+28h+arg_0]
0x18002cdb9  mov     rsi, [rsp+28h+arg_8]
0x18002cdbe  add     rsp, 20h
0x18002cdc2  pop     rdi
0x18002cdc3  retn
```
