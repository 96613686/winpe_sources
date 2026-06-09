# ATL::CComObject<CCSCShellFolder>::~CComObject<CCSCShellFolder>(void)

- ea: `0x1800030d0`
- end: `0x1800031b6`
- name: `??1?$CComObject@VCCSCShellFolder@@@ATL@@UEAA@XZ`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800050b0`

## callees

- `0x1800030d0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031a9`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180003137`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180003137`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComObject<CCSCShellFolder>::~CComObject<CCSCShellFolder>(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CCSCShellFolder>::`vftable'{for `IShellFolder2'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CCSCShellFolder>::`vftable'{for `IPersistFolder2'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CCSCShellFolder>::`vftable'{for `IDelegateFolder'};
  *(_DWORD *)(a1 + 24) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &CCSCShellFolder::`vftable'{for `IShellFolder2'};
  *(_QWORD *)(a1 + 8) = &CCSCShellFolder::`vftable'{for `IPersistFolder2'};
  *(_QWORD *)(a1 + 16) = &CCSCShellFolder::`vftable'{for `IDelegateFolder'};
  ILFree(*(LPITEMIDLIST *)(a1 + 120));
  v2 = *(_QWORD *)(a1 + 112);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 104);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 96);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *(_QWORD *)(a1 + 88);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *(_BYTE *)(a1 + 72) )
  {
    *(_BYTE *)(a1 + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  }
}

```

## disassembly

```asm
0x1800030d0  push    rbx
0x1800030d2  sub     rsp, 20h
0x1800030d6  mov     rbx, rcx
0x1800030d9  lea     rax, ??_7?$CComObject@VCCSCShellFolder@@@ATL@@6BIShellFolder2@@@; const ATL::CComObject<CCSCShellFolder>::`vftable'{for `IShellFolder2'}
0x1800030e0  mov     [rcx], rax
0x1800030e3  lea     rax, ??_7?$CComObject@VCCSCShellFolder@@@ATL@@6BIPersistFolder2@@@; const ATL::CComObject<CCSCShellFolder>::`vftable'{for `IPersistFolder2'}
0x1800030ea  mov     [rcx+8], rax
0x1800030ee  lea     rax, ??_7?$CComObject@VCCSCShellFolder@@@ATL@@6BIDelegateFolder@@@; const ATL::CComObject<CCSCShellFolder>::`vftable'{for `IDelegateFolder'}
0x1800030f5  mov     [rcx+10h], rax
0x1800030f9  mov     dword ptr [rcx+18h], 0C0000001h
0x180003100  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003107  mov     rax, [rcx]
0x18000310a  mov     rax, [rax+10h]
0x18000310e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003113  lea     rax, ??_7CCSCShellFolder@@6BIShellFolder2@@@; const CCSCShellFolder::`vftable'{for `IShellFolder2'}
0x18000311a  mov     [rbx], rax
0x18000311d  lea     rax, ??_7CCSCShellFolder@@6BIPersistFolder2@@@; const CCSCShellFolder::`vftable'{for `IPersistFolder2'}
0x180003124  mov     [rbx+8], rax
0x180003128  lea     rax, ??_7CCSCShellFolder@@6BIDelegateFolder@@@; const CCSCShellFolder::`vftable'{for `IDelegateFolder'}
0x18000312f  mov     [rbx+10h], rax
0x180003133  mov     rcx, [rbx+78h]; pidl
0x180003137  call    cs:__imp_ILFree
0x18000313d  nop
0x18000313e  mov     rcx, [rbx+70h]
0x180003142  test    rcx, rcx
0x180003145  jz      short loc_180003154
0x180003147  mov     rax, [rcx]
0x18000314a  mov     rax, [rax+10h]
0x18000314e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003153  nop
0x180003154  mov     rcx, [rbx+68h]
0x180003158  test    rcx, rcx
0x18000315b  jz      short loc_18000316A
0x18000315d  mov     rax, [rcx]
0x180003160  mov     rax, [rax+10h]
0x180003164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003169  nop
0x18000316a  mov     rcx, [rbx+60h]
0x18000316e  test    rcx, rcx
0x180003171  jz      short loc_180003180
0x180003173  mov     rax, [rcx]
0x180003176  mov     rax, [rax+10h]
0x18000317a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317f  nop
0x180003180  mov     rcx, [rbx+58h]
0x180003184  test    rcx, rcx
0x180003187  jz      short loc_180003196
0x180003189  mov     rax, [rcx]
0x18000318c  mov     rax, [rax+10h]
0x180003190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003195  nop
0x180003196  lea     rcx, [rbx+20h]
0x18000319a  cmp     byte ptr [rcx+28h], 0
0x18000319e  jz      short loc_1800031B0
0x1800031a0  mov     byte ptr [rcx+28h], 0
0x1800031a4  add     rsp, 20h
0x1800031a8  pop     rbx
0x1800031a9  jmp     cs:__imp_DeleteCriticalSection
0x1800031b0  add     rsp, 20h
0x1800031b4  pop     rbx
0x1800031b5  retn
```
