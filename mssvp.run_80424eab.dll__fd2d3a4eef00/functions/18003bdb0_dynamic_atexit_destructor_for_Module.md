# _dynamic_atexit_destructor_for__Module__

- ea: `0x18003bdb0`
- end: `0x18003be2b`
- name: `_dynamic_atexit_destructor_for__Module__`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005120`
- `0x18000bca0`
- `0x18003bdb0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003be0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003be0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 dynamic_atexit_destructor_for__Module__()
{
  Module = &ATL::CComModule::`vftable';
  if ( dword_1800546A8 )
  {
    if ( qword_1800546B0 )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)&dword_1800546A8);
      qword_1800546B0 = 0;
    }
    if ( qword_1800546E0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800546E0 + 16LL))(qword_1800546E0);
    DeleteCriticalSection(&stru_1800546B8);
    dword_1800546A8 = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&dword_1800546A8);
}

```

## disassembly

```asm
0x18003bdb0  sub     rsp, 28h
0x18003bdb4  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18003bdbb  mov     cs:?Module@@3VCComModule@ATL@@A, rax; ATL::CComModule Module
0x18003bdc2  cmp     cs:dword_1800546A8, 0
0x18003bdc9  jz      short loc_18003BE1B
0x18003bdcb  cmp     cs:qword_1800546B0, 0
0x18003bdd3  jz      short loc_18003BDEC
0x18003bdd5  lea     rcx, dword_1800546A8; struct ATL::_ATL_MODULE70 *
0x18003bddc  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18003bde1  mov     cs:qword_1800546B0, 0
0x18003bdec  mov     rcx, cs:qword_1800546E0
0x18003bdf3  test    rcx, rcx
0x18003bdf6  jz      short loc_18003BE04
0x18003bdf8  mov     rax, [rcx]
0x18003bdfb  mov     rax, [rax+10h]
0x18003bdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be04  lea     rcx, stru_1800546B8; lpCriticalSection
0x18003be0b  call    cs:__imp_DeleteCriticalSection
0x18003be11  mov     cs:dword_1800546A8, 0
0x18003be1b  lea     rcx, dword_1800546A8
0x18003be22  add     rsp, 28h
0x18003be26  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```
