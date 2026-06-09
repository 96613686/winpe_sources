# CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001b900`
- end: `0x18001b996`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x1800026d4`
- `0x18001ae90`
- `0x18001b900`
- `0x180024010`

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
0x18001b900  mov     [rsp+arg_0], rbx
0x18001b905  mov     [rsp+arg_8], rsi
0x18001b90a  push    rdi
0x18001b90b  sub     rsp, 20h
0x18001b90f  mov     rbx, r9
0x18001b912  mov     rsi, r8
0x18001b915  test    r9, r9
0x18001b918  jnz     short loc_18001B921
0x18001b91a  mov     ebx, 80070057h
0x18001b91f  jmp     short loc_18001B983
0x18001b921  and     qword ptr [r9], 0
0x18001b925  test    rdx, rdx
0x18001b928  jz      short loc_18001B931
0x18001b92a  mov     ebx, 80040110h
0x18001b92f  jmp     short loc_18001B983
0x18001b931  mov     ecx, 0A8h; Size
0x18001b936  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b93b  mov     rcx, rax; this
0x18001b93e  mov     [rsp+28h+arg_18], rax
0x18001b943  call    ??0CMemoryDiagnosticHandler@@QEAA@XZ; CMemoryDiagnosticHandler::CMemoryDiagnosticHandler(void)
0x18001b948  mov     rdi, rax
0x18001b94b  test    rax, rax
0x18001b94e  jnz     short loc_18001B957
0x18001b950  mov     ebx, 8007000Eh
0x18001b955  jmp     short loc_18001B983
0x18001b957  mov     dword ptr [rax+10h], 1
0x18001b95e  mov     r8, rbx
0x18001b961  mov     rax, [rax]
0x18001b964  mov     rdx, rsi
0x18001b967  mov     rcx, rdi
0x18001b96a  mov     rax, [rax]
0x18001b96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b972  mov     rcx, [rdi]
0x18001b975  mov     ebx, eax
0x18001b977  mov     rax, [rcx+10h]
0x18001b97b  mov     rcx, rdi
0x18001b97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b983  mov     rsi, [rsp+28h+arg_8]
0x18001b988  mov     eax, ebx
0x18001b98a  mov     rbx, [rsp+28h+arg_0]
0x18001b98f  add     rsp, 20h
0x18001b993  pop     rdi
0x18001b994  retn
```
