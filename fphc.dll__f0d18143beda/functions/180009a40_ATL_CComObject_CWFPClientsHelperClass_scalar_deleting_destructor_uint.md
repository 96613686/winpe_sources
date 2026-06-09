# ATL::CComObject<CWFPClientsHelperClass>::`scalar deleting destructor'(uint)

- ea: `0x180009a40`
- end: `0x180009aaf`
- name: `??_G?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAPEAXI@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009a40`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009a9b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009a9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a8c`

## pseudocode

```c
char *__fastcall ATL::CComObject<CWFPClientsHelperClass>::`scalar deleting destructor'(char *a1, char a2)
{
  *((_DWORD *)a1 + 4) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagExtensibleHelper'};
  *((_QWORD *)a1 + 1) = &ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( a1[64] )
  {
    a1[64] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009a40  mov     [rsp+arg_0], rbx
0x180009a45  push    rdi
0x180009a46  sub     rsp, 20h
0x180009a4a  mov     dword ptr [rcx+10h], 0C0000001h
0x180009a51  lea     rax, ??_7?$CComObject@VCWFPClientsHelperClass@@@ATL@@6BINetDiagExtensibleHelper@@@; const ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagExtensibleHelper'}
0x180009a58  mov     [rcx], rax
0x180009a5b  mov     rbx, rcx
0x180009a5e  lea     rax, ??_7?$CComObject@VCWFPClientsHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CWFPClientsHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180009a65  mov     edi, edx
0x180009a67  mov     [rcx+8], rax
0x180009a6b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009a72  mov     rax, [rcx]
0x180009a75  mov     rax, [rax+10h]
0x180009a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7e  lea     rcx, [rbx+18h]; lpCriticalSection
0x180009a82  cmp     byte ptr [rcx+28h], 0
0x180009a86  jz      short loc_180009A92
0x180009a88  mov     byte ptr [rcx+28h], 0
0x180009a8c  call    cs:__imp_DeleteCriticalSection
0x180009a92  test    dil, 1
0x180009a96  jz      short loc_180009AA1
0x180009a98  mov     rcx, rbx
0x180009a9b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009aa1  mov     rax, rbx
0x180009aa4  mov     rbx, [rsp+28h+arg_0]
0x180009aa9  add     rsp, 20h
0x180009aad  pop     rdi
0x180009aae  retn
```
