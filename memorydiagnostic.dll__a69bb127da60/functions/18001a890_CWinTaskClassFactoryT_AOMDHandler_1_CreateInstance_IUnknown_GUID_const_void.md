# CWinTaskClassFactoryT<AOMDHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001a890`
- end: `0x18001a928`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180002e74`
- `0x180006fd8`
- `0x18001a890`
- `0x180023010`

## pseudocode

```c
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
0x18001a890  mov     [rsp+arg_0], rbx
0x18001a895  mov     [rsp+arg_8], rsi
0x18001a89a  push    rdi
0x18001a89b  sub     rsp, 20h
0x18001a89f  mov     rbx, r9
0x18001a8a2  mov     rsi, r8
0x18001a8a5  test    r9, r9
0x18001a8a8  jnz     short loc_18001A8B1
0x18001a8aa  mov     ebx, 80070057h
0x18001a8af  jmp     short loc_18001A916
0x18001a8b1  mov     qword ptr [r9], 0
0x18001a8b8  test    rdx, rdx
0x18001a8bb  jz      short loc_18001A8C4
0x18001a8bd  mov     ebx, 80040110h
0x18001a8c2  jmp     short loc_18001A916
0x18001a8c4  mov     ecx, 0A8h; Size
0x18001a8c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a8ce  mov     [rsp+28h+arg_18], rax
0x18001a8d3  mov     rcx, rax; this
0x18001a8d6  call    ??0AOMDHandler@@QEAA@XZ; AOMDHandler::AOMDHandler(void)
0x18001a8db  mov     rdi, rax
0x18001a8de  test    rax, rax
0x18001a8e1  jnz     short loc_18001A8EA
0x18001a8e3  mov     ebx, 8007000Eh
0x18001a8e8  jmp     short loc_18001A916
0x18001a8ea  mov     dword ptr [rax+10h], 1
0x18001a8f1  mov     rax, [rax]
0x18001a8f4  mov     r8, rbx
0x18001a8f7  mov     rdx, rsi
0x18001a8fa  mov     rcx, rdi
0x18001a8fd  mov     rax, [rax]
0x18001a900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a905  mov     ebx, eax
0x18001a907  mov     rcx, [rdi]
0x18001a90a  mov     rax, [rcx+10h]
0x18001a90e  mov     rcx, rdi
0x18001a911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a916  mov     eax, ebx
0x18001a918  mov     rbx, [rsp+28h+arg_0]
0x18001a91d  mov     rsi, [rsp+28h+arg_8]
0x18001a922  add     rsp, 20h
0x18001a926  pop     rdi
0x18001a927  retn
```
