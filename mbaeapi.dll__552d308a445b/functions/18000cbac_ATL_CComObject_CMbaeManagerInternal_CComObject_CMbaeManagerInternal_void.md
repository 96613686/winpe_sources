# ATL::CComObject<CMbaeManagerInternal>::~CComObject<CMbaeManagerInternal>(void)

- ea: `0x18000cbac`
- end: `0x18000cc22`
- name: `??1?$CComObject@VCMbaeManagerInternal@@@ATL@@UEAA@XZ`
- size: `118`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d720`

## callees

- `0x18000cbac`
- `0x180014c38`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cbf1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cbf1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cc15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cc15`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ATL::CComObject<CMbaeManagerInternal>::~CComObject<CMbaeManagerInternal>(__int64 a1)
{
  void *v2; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CMbaeManagerInternal>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  CMbaeManagerInternal::FinalRelease((CMbaeManagerInternal *)a1);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &CMbaeManagerInternal::`vftable';
  v2 = *(void **)(a1 + 88);
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)(a1 + 88) = 0;
  }
  *(_QWORD *)(a1 + 96) = 0;
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x18000cbac  push    rbx
0x18000cbae  sub     rsp, 20h
0x18000cbb2  mov     rbx, rcx
0x18000cbb5  lea     rax, ??_7?$CComObject@VCMbaeManagerInternal@@@ATL@@6B@; const ATL::CComObject<CMbaeManagerInternal>::`vftable'
0x18000cbbc  mov     [rcx], rax
0x18000cbbf  mov     dword ptr [rcx+8], 0C0000001h
0x18000cbc6  call    ?FinalRelease@CMbaeManagerInternal@@QEAAXXZ; CMbaeManagerInternal::FinalRelease(void)
0x18000cbcb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cbd2  mov     rax, [rcx]
0x18000cbd5  mov     rax, [rax+10h]
0x18000cbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbde  lea     rax, ??_7CMbaeManagerInternal@@6B@; const CMbaeManagerInternal::`vftable'
0x18000cbe5  mov     [rbx], rax
0x18000cbe8  mov     rcx, [rbx+58h]; Block
0x18000cbec  test    rcx, rcx
0x18000cbef  jz      short loc_18000CBFF
0x18000cbf1  call    cs:__imp_free
0x18000cbf7  mov     qword ptr [rbx+58h], 0
0x18000cbff  mov     qword ptr [rbx+60h], 0
0x18000cc07  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000cc0b  cmp     byte ptr [rcx+28h], 0
0x18000cc0f  jz      short loc_18000CC1C
0x18000cc11  mov     byte ptr [rcx+28h], 0
0x18000cc15  call    cs:__imp_DeleteCriticalSection
0x18000cc1b  nop
0x18000cc1c  add     rsp, 20h
0x18000cc20  pop     rbx
0x18000cc21  retn
```
