# DevicePause(_MCIGRAPHIC *,ulong,unsigned __int64)

- ea: `0x180002b00`
- end: `0x180002b71`
- name: `?DevicePause@@YAKPEAU_MCIGRAPHIC@@K_K@Z`
- size: `113`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, unsigned int, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003604`
- `0x18000485c`

## callees

- `0x180001e7c`
- `0x180002b00`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall DevicePause(struct _MCIGRAPHIC *a1, char a2)
{
  int v4; // esi
  __int64 v5; // rcx
  int v7; // [rsp+38h] [rbp+10h] BYREF

  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 64LL))(*((_QWORD *)a1 + 19));
  if ( (a2 & 2) != 0 )
  {
    v5 = *((_QWORD *)a1 + 19);
    v7 = 0;
    (*(void (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v5 + 80LL))(v5, 0xFFFFFFFFLL, &v7);
  }
  *((_DWORD *)a1 + 72) = 529;
  return CheckResult(v4);
}

```

## disassembly

```asm
0x180002b00  mov     [rsp+arg_0], rbx
0x180002b05  mov     [rsp+arg_10], rsi
0x180002b0a  push    rdi
0x180002b0b  sub     rsp, 20h
0x180002b0f  mov     rdi, rcx
0x180002b12  mov     ebx, edx
0x180002b14  mov     rcx, [rcx+98h]
0x180002b1b  mov     rax, [rcx]
0x180002b1e  mov     rax, [rax+40h]
0x180002b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b27  mov     esi, eax
0x180002b29  test    bl, 2
0x180002b2c  jz      short loc_180002B51
0x180002b2e  mov     rcx, [rdi+98h]
0x180002b35  lea     r8, [rsp+28h+arg_8]
0x180002b3a  mov     [rsp+28h+arg_8], 0
0x180002b42  mov     rdx, [rcx]
0x180002b45  mov     rax, [rdx+50h]
0x180002b49  or      edx, 0FFFFFFFFh
0x180002b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b51  mov     ecx, esi; int
0x180002b53  mov     dword ptr [rdi+120h], 211h
0x180002b5d  mov     rbx, [rsp+28h+arg_0]
0x180002b62  mov     rsi, [rsp+28h+arg_10]
0x180002b67  add     rsp, 20h
0x180002b6b  pop     rdi
0x180002b6c  jmp     ?CheckResult@@YAKJ@Z; CheckResult(long)
```
