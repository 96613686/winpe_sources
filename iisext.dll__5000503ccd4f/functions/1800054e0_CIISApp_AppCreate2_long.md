# CIISApp::AppCreate2(long)

- ea: `0x1800054e0`
- end: `0x180005543`
- name: `?AppCreate2@CIISApp@@UEAAJJ@Z`
- size: `99`
- prototype: `__int64 __fastcall(CIISApp *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800054e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::AppCreate2(CIISApp *this, unsigned int a2)
{
  __int64 v2; // r10
  __int64 v4; // r9

  v2 = *((_QWORD *)this + 18);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v2 + 24LL))(
             *((_QWORD *)this + 18),
             *((_QWORD *)this + 9),
             a2,
             0,
             0);
  v4 = *((_QWORD *)this + 17);
  if ( v4 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 72LL))(
             *((_QWORD *)this + 17),
             *((_QWORD *)this + 9),
             a2);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x1800054e0  sub     rsp, 38h
0x1800054e4  mov     r10, [rcx+90h]
0x1800054eb  test    r10, r10
0x1800054ee  jz      short loc_180005513
0x1800054f0  mov     rax, [r10]
0x1800054f3  mov     r8d, edx
0x1800054f6  mov     rdx, [rcx+48h]
0x1800054fa  xor     r9d, r9d
0x1800054fd  mov     rcx, r10
0x180005500  mov     [rsp+38h+var_18], 0
0x180005508  mov     rax, [rax+18h]
0x18000550c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005511  jmp     short loc_18000553E
0x180005513  mov     r9, [rcx+88h]
0x18000551a  test    r9, r9
0x18000551d  jz      short loc_180005539
0x18000551f  mov     rax, [r9]
0x180005522  mov     r8d, edx
0x180005525  mov     rdx, [rcx+48h]
0x180005529  mov     rcx, r9
0x18000552c  mov     rax, [rax+48h]
0x180005530  add     rsp, 38h
0x180005534  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005539  mov     eax, 80004002h
0x18000553e  add     rsp, 38h
0x180005542  retn
```
