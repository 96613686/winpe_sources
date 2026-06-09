# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180041fa0`
- end: `0x180042025`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ba80`
- `0x180041fa0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041fff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041fff`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rbx
  unsigned __int64 v1; // rax
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = (__int64 *)qword_1800600D0;
    v1 = qword_1800600D8;
    while ( (unsigned __int64)v0 < v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v1 = qword_1800600D8;
      }
      ++v0;
    }
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlComModule = 0;
  }
  return wil_StagingConfig_LogFeatureProcessUsage(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x180041fa0  mov     [rsp+arg_0], rbx
0x180041fa5  push    rdi
0x180041fa6  sub     rsp, 20h
0x180041faa  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180041fb1  jz      short loc_18004200F
0x180041fb3  mov     rbx, cs:qword_1800600D0
0x180041fba  mov     rax, cs:qword_1800600D8
0x180041fc1  jmp     short loc_180041FF3
0x180041fc3  mov     rdi, [rbx]
0x180041fc6  test    rdi, rdi
0x180041fc9  jz      short loc_180041FEF
0x180041fcb  mov     rcx, [rdi+20h]
0x180041fcf  test    rcx, rcx
0x180041fd2  jz      short loc_180041FE0
0x180041fd4  mov     rax, [rcx]
0x180041fd7  mov     rax, [rax+10h]
0x180041fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fe0  mov     qword ptr [rdi+20h], 0
0x180041fe8  mov     rax, cs:qword_1800600D8
0x180041fef  add     rbx, 8
0x180041ff3  cmp     rbx, rax
0x180041ff6  jb      short loc_180041FC3
0x180041ff8  lea     rcx, CriticalSection; lpCriticalSection
0x180041fff  call    cs:__imp_DeleteCriticalSection
0x180042005  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18004200f  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180042016  mov     rbx, [rsp+28h+arg_0]
0x18004201b  add     rsp, 20h
0x18004201f  pop     rdi
0x180042020  jmp     wil_StagingConfig_LogFeatureProcessUsage
```
