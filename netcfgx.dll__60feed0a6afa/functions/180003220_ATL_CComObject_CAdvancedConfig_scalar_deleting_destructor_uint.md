# ATL::CComObject<CAdvancedConfig>::`scalar deleting destructor'(uint)

- ea: `0x180003220`
- end: `0x180003288`
- name: `??_G?$CComObject@VCAdvancedConfig@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001fec`
- `0x180003220`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003261`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003261`

## pseudocode

```c
char *__fastcall ATL::CComObject<CAdvancedConfig>::`scalar deleting destructor'(char *a1, char a2)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CAdvancedConfig>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( a1[56] )
  {
    a1[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1, 0x40u);
  return a1;
}

```

## disassembly

```asm
0x180003220  mov     [rsp+arg_0], rbx
0x180003225  push    rdi
0x180003226  sub     rsp, 20h
0x18000322a  mov     dword ptr [rcx+8], 0C0000001h
0x180003231  lea     rax, ??_7?$CComObject@VCAdvancedConfig@@@ATL@@6B@; const ATL::CComObject<CAdvancedConfig>::`vftable'
0x180003238  mov     [rcx], rax
0x18000323b  mov     rbx, rcx
0x18000323e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003245  mov     edi, edx
0x180003247  mov     rax, [rcx]
0x18000324a  mov     rax, [rax+10h]
0x18000324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003253  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003257  cmp     byte ptr [rcx+28h], 0
0x18000325b  jz      short loc_180003267
0x18000325d  mov     byte ptr [rcx+28h], 0
0x180003261  call    cs:__imp_DeleteCriticalSection
0x180003267  test    dil, 1
0x18000326b  jz      short loc_18000327A
0x18000326d  mov     edx, 40h ; '@'; unsigned __int64
0x180003272  mov     rcx, rbx; void *
0x180003275  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000327a  mov     rax, rbx
0x18000327d  mov     rbx, [rsp+28h+arg_0]
0x180003282  add     rsp, 20h
0x180003286  pop     rdi
0x180003287  retn
```
