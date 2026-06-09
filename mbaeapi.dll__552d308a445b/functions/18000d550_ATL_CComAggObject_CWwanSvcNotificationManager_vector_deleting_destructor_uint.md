# ATL::CComAggObject<CWwanSvcNotificationManager>::`vector deleting destructor'(uint)

- ea: `0x18000d550`
- end: `0x18000d5b8`
- name: `??_E?$CComAggObject@VCWwanSvcNotificationManager@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800028b0`
- `0x18000d550`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d591`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d591`

## pseudocode

```c
char *__fastcall ATL::CComAggObject<CWwanSvcNotificationManager>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CWwanSvcNotificationManager>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[88] )
  {
    Block[88] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 48));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000d550  mov     [rsp+arg_0], rbx
0x18000d555  push    rdi
0x18000d556  sub     rsp, 20h
0x18000d55a  mov     dword ptr [rcx+8], 0C0000001h
0x18000d561  lea     rax, ??_7?$CComAggObject@VCWwanSvcNotificationManager@@@ATL@@6B@; const ATL::CComAggObject<CWwanSvcNotificationManager>::`vftable'
0x18000d568  mov     [rcx], rax
0x18000d56b  mov     rbx, rcx
0x18000d56e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d575  mov     edi, edx
0x18000d577  mov     rax, [rcx]
0x18000d57a  mov     rax, [rax+10h]
0x18000d57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d583  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000d587  cmp     byte ptr [rcx+28h], 0
0x18000d58b  jz      short loc_18000D597
0x18000d58d  mov     byte ptr [rcx+28h], 0
0x18000d591  call    cs:__imp_DeleteCriticalSection
0x18000d597  test    dil, 1
0x18000d59b  jz      short loc_18000D5AA
0x18000d59d  mov     edx, 60h ; '`'
0x18000d5a2  mov     rcx, rbx; Block
0x18000d5a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d5aa  mov     rax, rbx
0x18000d5ad  mov     rbx, [rsp+28h+arg_0]
0x18000d5b2  add     rsp, 20h
0x18000d5b6  pop     rdi
0x18000d5b7  retn
```
