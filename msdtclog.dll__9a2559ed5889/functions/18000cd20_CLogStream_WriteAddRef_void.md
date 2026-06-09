# CLogStream::WriteAddRef(void)

- ea: `0x18000cd20`
- end: `0x18000cd6e`
- name: `?WriteAddRef@CLogStream@@MEAAKXZ`
- size: `78`
- prototype: `__int64 __fastcall(void (__fastcall ***this)(char *))`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CLogStream::WriteAddRef(void (__fastcall ***this)(char *))
{
  __int64 *v1; // rsi
  __int64 v3; // rdx
  unsigned int v4; // ebx

  v1 = (__int64 *)(this + 2);
  (*this[2])((char *)this + 16);
  v3 = *v1;
  ++*((_DWORD *)this + 19);
  ++*((_DWORD *)this + 2);
  v4 = *((_DWORD *)this + 19);
  (*(void (__fastcall **)(__int64 *))(v3 + 8))(v1);
  return v4;
}

```

## disassembly

```asm
0x18000cd20  mov     [rsp+arg_0], rbx
0x18000cd25  mov     [rsp+arg_8], rsi
0x18000cd2a  push    rdi
0x18000cd2b  sub     rsp, 20h
0x18000cd2f  lea     rsi, [rcx+10h]
0x18000cd33  mov     rdi, rcx
0x18000cd36  mov     rax, [rsi]
0x18000cd39  mov     rcx, rsi
0x18000cd3c  mov     rax, [rax]
0x18000cd3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd44  mov     rdx, [rsi]
0x18000cd47  mov     rcx, rsi
0x18000cd4a  inc     dword ptr [rdi+4Ch]
0x18000cd4d  inc     dword ptr [rdi+8]
0x18000cd50  mov     ebx, [rdi+4Ch]
0x18000cd53  mov     rax, [rdx+8]
0x18000cd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd5c  mov     rsi, [rsp+28h+arg_8]
0x18000cd61  mov     eax, ebx
0x18000cd63  mov     rbx, [rsp+28h+arg_0]
0x18000cd68  add     rsp, 20h
0x18000cd6c  pop     rdi
0x18000cd6d  retn
```
