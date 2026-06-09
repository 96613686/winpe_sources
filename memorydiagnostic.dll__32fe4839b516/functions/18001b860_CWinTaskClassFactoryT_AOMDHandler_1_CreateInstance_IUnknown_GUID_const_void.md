# CWinTaskClassFactoryT<AOMDHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001b860`
- end: `0x18001b8f6`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x1800026d4`
- `0x180007074`
- `0x18001b860`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinTaskClassFactoryT<AOMDHandler,1>::CreateInstance(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int v6; // ebx
  AOMDHandler *v7; // rax
  AOMDHandler *v8; // rdi
  AOMDHandler *v10; // [rsp+48h] [rbp+20h]

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v10 = (AOMDHandler *)operator new(0xA8u);
      v7 = AOMDHandler::AOMDHandler(v10);
      v8 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 4) = 1;
        v6 = (**(__int64 (__fastcall ***)(AOMDHandler *, __int64, _QWORD *))v7)(v7, a3, a4);
        (*(void (__fastcall **)(AOMDHandler *))(*(_QWORD *)v8 + 16LL))(v8);
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
0x18001b860  mov     [rsp+arg_0], rbx
0x18001b865  mov     [rsp+arg_8], rsi
0x18001b86a  push    rdi
0x18001b86b  sub     rsp, 20h
0x18001b86f  mov     rbx, r9
0x18001b872  mov     rsi, r8
0x18001b875  test    r9, r9
0x18001b878  jnz     short loc_18001B881
0x18001b87a  mov     ebx, 80070057h
0x18001b87f  jmp     short loc_18001B8E3
0x18001b881  and     qword ptr [r9], 0
0x18001b885  test    rdx, rdx
0x18001b888  jz      short loc_18001B891
0x18001b88a  mov     ebx, 80040110h
0x18001b88f  jmp     short loc_18001B8E3
0x18001b891  mov     ecx, 0A8h; Size
0x18001b896  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b89b  mov     [rsp+28h+arg_18], rax
0x18001b8a0  mov     rcx, rax; this
0x18001b8a3  call    ??0AOMDHandler@@QEAA@XZ; AOMDHandler::AOMDHandler(void)
0x18001b8a8  mov     rdi, rax
0x18001b8ab  test    rax, rax
0x18001b8ae  jnz     short loc_18001B8B7
0x18001b8b0  mov     ebx, 8007000Eh
0x18001b8b5  jmp     short loc_18001B8E3
0x18001b8b7  mov     dword ptr [rax+10h], 1
0x18001b8be  mov     rax, [rax]
0x18001b8c1  mov     r8, rbx
0x18001b8c4  mov     rdx, rsi
0x18001b8c7  mov     rcx, rdi
0x18001b8ca  mov     rax, [rax]
0x18001b8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8d2  mov     ebx, eax
0x18001b8d4  mov     rcx, [rdi]
0x18001b8d7  mov     rax, [rcx+10h]
0x18001b8db  mov     rcx, rdi
0x18001b8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8e3  mov     eax, ebx
0x18001b8e5  mov     rbx, [rsp+28h+arg_0]
0x18001b8ea  mov     rsi, [rsp+28h+arg_8]
0x18001b8ef  add     rsp, 20h
0x18001b8f3  pop     rdi
0x18001b8f4  retn
```
