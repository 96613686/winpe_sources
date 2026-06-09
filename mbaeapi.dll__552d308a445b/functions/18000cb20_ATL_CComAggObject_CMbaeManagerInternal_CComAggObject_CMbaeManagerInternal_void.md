# ATL::CComAggObject<CMbaeManagerInternal>::~CComAggObject<CMbaeManagerInternal>(void)

- ea: `0x18000cb20`
- end: `0x18000cba4`
- name: `??1?$CComAggObject@VCMbaeManagerInternal@@@ATL@@UEAA@XZ`
- size: `132`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d510`

## callees

- `0x18000cb20`
- `0x180014c38`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cb6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cb6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb92`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CMbaeManagerInternal>::~CComAggObject<CMbaeManagerInternal>(__int64 a1)
{
  void *v2; // rcx

  *(_QWORD *)a1 = &ATL::CComAggObject<CMbaeManagerInternal>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  CMbaeManagerInternal::FinalRelease((CMbaeManagerInternal *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)(a1 + 24) = &CMbaeManagerInternal::`vftable';
  v2 = *(void **)(a1 + 112);
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)(a1 + 112) = 0;
  }
  *(_QWORD *)(a1 + 120) = 0;
  if ( *(_BYTE *)(a1 + 80) )
  {
    *(_BYTE *)(a1 + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
}

```

## disassembly

```asm
0x18000cb20  mov     [rsp+arg_0], rbx
0x18000cb25  push    rdi
0x18000cb26  sub     rsp, 20h
0x18000cb2a  mov     rbx, rcx
0x18000cb2d  lea     rax, ??_7?$CComAggObject@VCMbaeManagerInternal@@@ATL@@6B@; const ATL::CComAggObject<CMbaeManagerInternal>::`vftable'
0x18000cb34  mov     [rcx], rax
0x18000cb37  mov     dword ptr [rcx+8], 0C0000001h
0x18000cb3e  add     rcx, 18h; this
0x18000cb42  call    ?FinalRelease@CMbaeManagerInternal@@QEAAXXZ; CMbaeManagerInternal::FinalRelease(void)
0x18000cb47  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cb4e  mov     rax, [rcx]
0x18000cb51  mov     rax, [rax+10h]
0x18000cb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5a  lea     rax, ??_7CMbaeManagerInternal@@6B@; const CMbaeManagerInternal::`vftable'
0x18000cb61  mov     [rbx+18h], rax
0x18000cb65  mov     rcx, [rbx+70h]; Block
0x18000cb69  test    rcx, rcx
0x18000cb6c  jz      short loc_18000CB7C
0x18000cb6e  call    cs:__imp_free
0x18000cb74  mov     qword ptr [rbx+70h], 0
0x18000cb7c  mov     qword ptr [rbx+78h], 0
0x18000cb84  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000cb88  cmp     byte ptr [rcx+28h], 0
0x18000cb8c  jz      short loc_18000CB99
0x18000cb8e  mov     byte ptr [rcx+28h], 0
0x18000cb92  call    cs:__imp_DeleteCriticalSection
0x18000cb98  nop
0x18000cb99  mov     rbx, [rsp+28h+arg_0]
0x18000cb9e  add     rsp, 20h
0x18000cba2  pop     rdi
0x18000cba3  retn
```
