# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x18003bca0`
- end: `0x18003bd30`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005120`
- `0x18003bca0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bd0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003bd0b`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rax
  __int64 *i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = off_180053458;
    for ( i = off_180053450[0]; i < v0; ++i )
    {
      v2 = *i;
      if ( *i )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v0 = off_180053458;
      }
    }
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlComModule = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x18003bca0  sub     rsp, 28h
0x18003bca4  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18003bcab  jz      short loc_18003BD20
0x18003bcad  mov     rax, cs:off_180053458
0x18003bcb4  mov     [rsp+28h+arg_0], rbx
0x18003bcb9  mov     rbx, cs:off_180053450
0x18003bcc0  cmp     rbx, rax
0x18003bcc3  jnb     short loc_18003BD04
0x18003bcc5  mov     [rsp+28h+var_8], rdi
0x18003bcca  mov     rdi, [rbx]
0x18003bccd  test    rdi, rdi
0x18003bcd0  jz      short loc_18003BCF6
0x18003bcd2  mov     rcx, [rdi+20h]
0x18003bcd6  test    rcx, rcx
0x18003bcd9  jz      short loc_18003BCE7
0x18003bcdb  mov     rax, [rcx]
0x18003bcde  mov     rax, [rax+10h]
0x18003bce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bce7  mov     qword ptr [rdi+20h], 0
0x18003bcef  mov     rax, cs:off_180053458
0x18003bcf6  add     rbx, 8
0x18003bcfa  cmp     rbx, rax
0x18003bcfd  jb      short loc_18003BCCA
0x18003bcff  mov     rdi, [rsp+28h+var_8]
0x18003bd04  lea     rcx, CriticalSection; lpCriticalSection
0x18003bd0b  call    cs:__imp_DeleteCriticalSection
0x18003bd11  mov     rbx, [rsp+28h+arg_0]
0x18003bd16  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18003bd20  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x18003bd27  add     rsp, 28h
0x18003bd2b  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```
