# CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001a930`
- end: `0x18001a9c8`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180002e74`
- `0x180019f60`
- `0x18001a930`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  CMemoryDiagnosticHandler *v7; // rax
  CMemoryDiagnosticHandler *v8; // rdi
  CMemoryDiagnosticHandler *v10; // [rsp+48h] [rbp+20h]

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v10 = (CMemoryDiagnosticHandler *)operator new(0xA8u);
      v7 = CMemoryDiagnosticHandler::CMemoryDiagnosticHandler(v10);
      v8 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 4) = 1;
        v6 = (**(__int64 (__fastcall ***)(CMemoryDiagnosticHandler *, __int64, _QWORD *))v7)(v7, a3, a4);
        (*(void (__fastcall **)(CMemoryDiagnosticHandler *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18001a930  mov     [rsp+arg_0], rbx
0x18001a935  mov     [rsp+arg_8], rsi
0x18001a93a  push    rdi
0x18001a93b  sub     rsp, 20h
0x18001a93f  mov     rbx, r9
0x18001a942  mov     rsi, r8
0x18001a945  test    r9, r9
0x18001a948  jnz     short loc_18001A951
0x18001a94a  mov     ebx, 80070057h
0x18001a94f  jmp     short loc_18001A9B6
0x18001a951  mov     qword ptr [r9], 0
0x18001a958  test    rdx, rdx
0x18001a95b  jz      short loc_18001A964
0x18001a95d  mov     ebx, 80040110h
0x18001a962  jmp     short loc_18001A9B6
0x18001a964  mov     ecx, 0A8h; Size
0x18001a969  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a96e  mov     rcx, rax; this
0x18001a971  mov     [rsp+28h+arg_18], rax
0x18001a976  call    ??0CMemoryDiagnosticHandler@@QEAA@XZ; CMemoryDiagnosticHandler::CMemoryDiagnosticHandler(void)
0x18001a97b  mov     rdi, rax
0x18001a97e  test    rax, rax
0x18001a981  jnz     short loc_18001A98A
0x18001a983  mov     ebx, 8007000Eh
0x18001a988  jmp     short loc_18001A9B6
0x18001a98a  mov     dword ptr [rax+10h], 1
0x18001a991  mov     r8, rbx
0x18001a994  mov     rax, [rax]
0x18001a997  mov     rdx, rsi
0x18001a99a  mov     rcx, rdi
0x18001a99d  mov     rax, [rax]
0x18001a9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a5  mov     rcx, [rdi]
0x18001a9a8  mov     ebx, eax
0x18001a9aa  mov     rax, [rcx+10h]
0x18001a9ae  mov     rcx, rdi
0x18001a9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9b6  mov     rsi, [rsp+28h+arg_8]
0x18001a9bb  mov     eax, ebx
0x18001a9bd  mov     rbx, [rsp+28h+arg_0]
0x18001a9c2  add     rsp, 20h
0x18001a9c6  pop     rdi
0x18001a9c7  retn
```
