# ATL::CComObjectCached<AuditChannel>::Release(void)

- ea: `0x180011d30`
- end: `0x180011dd1`
- name: `?Release@?$CComObjectCached@VAuditChannel@@@ATL@@UEAAKXZ`
- size: `161`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011de0`

## callees

- `0x18000d7ac`
- `0x180011d30`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x180011da4`
- `msvcrt!free` at `0x180011da4`
- `KERNEL32!DeleteCriticalSection` at `0x180011d9b`
- `KERNEL32!DeleteCriticalSection` at `0x180011d9b`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<AuditChannel>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 4, i - 1, i);
        i = *((_DWORD *)Block + 4) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 4) = -1073741823;
      *(_QWORD *)Block = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'};
      *((_QWORD *)Block + 1) = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'};
      std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>((__int64)(Block + 72));
      if ( Block[64] != (_BYTE)v3 )
      {
        Block[64] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 24));
      }
      free(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180011d30  mov     [rsp+arg_0], rbx
0x180011d35  push    rdi
0x180011d36  sub     rsp, 20h
0x180011d3a  mov     rbx, rcx
0x180011d3d  mov     r8d, 7FFFFFFFh
0x180011d43  mov     ecx, [rcx+10h]
0x180011d46  jmp     short loc_180011D57
0x180011d48  lea     edx, [rcx-1]
0x180011d4b  mov     eax, ecx
0x180011d4d  lock cmpxchg [rbx+10h], edx
0x180011d52  jz      short loc_180011D5C
0x180011d54  mov     ecx, [rbx+10h]
0x180011d57  cmp     ecx, r8d
0x180011d5a  jnz     short loc_180011D48
0x180011d5c  lea     edi, [rcx-1]
0x180011d5f  test    edi, edi
0x180011d61  jnz     short loc_180011DAC
0x180011d63  test    rbx, rbx
0x180011d66  jz      short loc_180011DC4
0x180011d68  lea     rax, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSink@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'}
0x180011d6f  mov     dword ptr [rbx+10h], 0C0000001h
0x180011d76  mov     [rbx], rax
0x180011d79  lea     rcx, [rbx+48h]
0x180011d7d  lea     rax, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSource@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'}
0x180011d84  mov     [rbx+8], rax
0x180011d88  call    ??1?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAA@XZ; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(void)
0x180011d8d  lea     rcx, [rbx+18h]; lpCriticalSection
0x180011d91  cmp     [rcx+28h], dil
0x180011d95  jz      short loc_180011DA1
0x180011d97  mov     [rcx+28h], dil
0x180011d9b  call    cs:__imp_DeleteCriticalSection
0x180011da1  mov     rcx, rbx; Block
0x180011da4  call    cs:__imp_free
0x180011daa  jmp     short loc_180011DC4
0x180011dac  cmp     edi, 1
0x180011daf  jnz     short loc_180011DC4
0x180011db1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011db8  mov     rdx, [rcx]
0x180011dbb  mov     rax, [rdx+10h]
0x180011dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc4  mov     rbx, [rsp+28h+arg_0]
0x180011dc9  mov     eax, edi
0x180011dcb  add     rsp, 20h
0x180011dcf  pop     rdi
0x180011dd0  retn
```
