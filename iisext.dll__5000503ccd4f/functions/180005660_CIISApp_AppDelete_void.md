# CIISApp::AppDelete(void)

- ea: `0x180005660`
- end: `0x180005694`
- name: `?AppDelete@CIISApp@@UEAAJXZ`
- size: `52`
- prototype: `__int64 __fastcall(CIISApp *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005660`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::AppDelete(CIISApp *this)
{
  __int64 v1; // r9

  v1 = *((_QWORD *)this + 18);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v1 + 32LL))(v1, *((_QWORD *)this + 9), 0);
  v1 = *((_QWORD *)this + 16);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v1 + 32LL))(v1, *((_QWORD *)this + 9), 0);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x180005660  mov     r9, [rcx+90h]
0x180005667  test    r9, r9
0x18000566a  jnz     short loc_180005678
0x18000566c  mov     r9, [rcx+80h]
0x180005673  test    r9, r9
0x180005676  jz      short loc_18000568E
0x180005678  mov     rax, [r9]
0x18000567b  xor     r8d, r8d
0x18000567e  mov     rdx, [rcx+48h]
0x180005682  mov     rcx, r9
0x180005685  mov     rax, [rax+20h]
0x180005689  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000568e  mov     eax, 80004002h
0x180005693  retn
```
