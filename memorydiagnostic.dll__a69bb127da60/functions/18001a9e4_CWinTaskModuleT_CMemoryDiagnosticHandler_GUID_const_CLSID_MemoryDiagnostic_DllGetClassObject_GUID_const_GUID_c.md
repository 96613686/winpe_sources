# CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18001a9e4`
- end: `0x18001aa8d`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VCMemoryDiagnosticHandler@@$1?CLSID_MemoryDiagnostic@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001de90`

## callees

- `0x180002e74`
- `0x18001a9e4`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v7; // edi
  _DWORD *v8; // [rsp+30h] [rbp+8h]

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( *(_QWORD *)&CLSID_MemoryDiagnostic.Data1 == *a2 && *(_QWORD *)CLSID_MemoryDiagnostic.Data4 == a2[1] )
  {
    v8 = operator new(0x10u);
    *(_QWORD *)v8 = &CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`vftable';
    v8[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a3, a4);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    return (unsigned int)-2147221231;
  }
  return v7;
}

```

## disassembly

```asm
0x18001a9e4  mov     [rsp+arg_8], rbx
0x18001a9e9  mov     [rsp+arg_10], rsi
0x18001a9ee  push    rdi
0x18001a9ef  sub     rsp, 20h
0x18001a9f3  mov     rdi, r9
0x18001a9f6  mov     rsi, r8
0x18001a9f9  test    r9, r9
0x18001a9fc  jnz     short loc_18001AA05
0x18001a9fe  mov     eax, 80070057h
0x18001aa03  jmp     short loc_18001AA7D
0x18001aa05  mov     qword ptr [r9], 0
0x18001aa0c  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data1
0x18001aa13  cmp     rax, [rdx]
0x18001aa16  jnz     short loc_18001AA76
0x18001aa18  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data4
0x18001aa1f  cmp     rax, [rdx+8]
0x18001aa23  jnz     short loc_18001AA76
0x18001aa25  mov     ecx, 10h; Size
0x18001aa2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aa2f  mov     rbx, rax
0x18001aa32  mov     [rsp+28h+arg_0], rax
0x18001aa37  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`vftable'
0x18001aa3e  mov     [rbx], rax
0x18001aa41  mov     dword ptr [rbx+8], 1
0x18001aa48  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001aa4f  mov     rcx, [rbx]
0x18001aa52  mov     r8, rdi
0x18001aa55  mov     rdx, rsi
0x18001aa58  mov     rax, [rcx]
0x18001aa5b  mov     rcx, rbx
0x18001aa5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa63  mov     edi, eax
0x18001aa65  mov     rcx, [rbx]
0x18001aa68  mov     rax, [rcx+10h]
0x18001aa6c  mov     rcx, rbx
0x18001aa6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa74  jmp     short loc_18001AA7B
0x18001aa76  mov     edi, 80040111h
0x18001aa7b  mov     eax, edi
0x18001aa7d  mov     rbx, [rsp+28h+arg_8]
0x18001aa82  mov     rsi, [rsp+28h+arg_10]
0x18001aa87  add     rsp, 20h
0x18001aa8b  pop     rdi
0x18001aa8c  retn
```
