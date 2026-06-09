# CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18001b9b8`
- end: `0x18001ba5f`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VCMemoryDiagnosticHandler@@$1?CLSID_MemoryDiagnostic@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f1f0`

## callees

- `0x1800026d4`
- `0x18001b9b8`
- `0x180024010`

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
0x18001b9b8  mov     [rsp+arg_8], rbx
0x18001b9bd  mov     [rsp+arg_10], rsi
0x18001b9c2  push    rdi
0x18001b9c3  sub     rsp, 20h
0x18001b9c7  mov     rdi, r9
0x18001b9ca  mov     rsi, r8
0x18001b9cd  test    r9, r9
0x18001b9d0  jnz     short loc_18001B9D9
0x18001b9d2  mov     eax, 80070057h
0x18001b9d7  jmp     short loc_18001BA4E
0x18001b9d9  and     qword ptr [r9], 0
0x18001b9dd  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data1
0x18001b9e4  cmp     rax, [rdx]
0x18001b9e7  jnz     short loc_18001BA47
0x18001b9e9  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data4
0x18001b9f0  cmp     rax, [rdx+8]
0x18001b9f4  jnz     short loc_18001BA47
0x18001b9f6  mov     ecx, 10h; Size
0x18001b9fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba00  mov     rbx, rax
0x18001ba03  mov     [rsp+28h+arg_0], rax
0x18001ba08  lea     rax, ??_7?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@6B@; const CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::`vftable'
0x18001ba0f  mov     [rbx], rax
0x18001ba12  mov     dword ptr [rbx+8], 1
0x18001ba19  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001ba20  mov     rcx, [rbx]
0x18001ba23  mov     r8, rdi
0x18001ba26  mov     rdx, rsi
0x18001ba29  mov     rax, [rcx]
0x18001ba2c  mov     rcx, rbx
0x18001ba2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba34  mov     edi, eax
0x18001ba36  mov     rcx, [rbx]
0x18001ba39  mov     rax, [rcx+10h]
0x18001ba3d  mov     rcx, rbx
0x18001ba40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba45  jmp     short loc_18001BA4C
0x18001ba47  mov     edi, 80040111h
0x18001ba4c  mov     eax, edi
0x18001ba4e  mov     rbx, [rsp+28h+arg_8]
0x18001ba53  mov     rsi, [rsp+28h+arg_10]
0x18001ba58  add     rsp, 20h
0x18001ba5c  pop     rdi
0x18001ba5d  retn
```
