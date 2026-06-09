# CIISApp::AppDeleteRecursive(void)

- ea: `0x1800056a0`
- end: `0x1800056d7`
- name: `?AppDeleteRecursive@CIISApp@@UEAAJXZ`
- size: `55`
- prototype: `__int64 __fastcall(CIISApp *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800056a0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::AppDeleteRecursive(CIISApp *this)
{
  __int64 v1; // r9

  v1 = *((_QWORD *)this + 18);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v1 + 32LL))(v1, *((_QWORD *)this + 9), 1);
  v1 = *((_QWORD *)this + 16);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v1 + 32LL))(v1, *((_QWORD *)this + 9), 1);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x1800056a0  mov     r9, [rcx+90h]
0x1800056a7  test    r9, r9
0x1800056aa  jnz     short loc_1800056B8
0x1800056ac  mov     r9, [rcx+80h]
0x1800056b3  test    r9, r9
0x1800056b6  jz      short loc_1800056D1
0x1800056b8  mov     rax, [r9]
0x1800056bb  mov     r8d, 1
0x1800056c1  mov     rdx, [rcx+48h]
0x1800056c5  mov     rcx, r9
0x1800056c8  mov     rax, [rax+20h]
0x1800056cc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d1  mov     eax, 80004002h
0x1800056d6  retn
```
