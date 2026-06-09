# CIISApp::AppCreate(short)

- ea: `0x1800055e0`
- end: `0x180005651`
- name: `?AppCreate@CIISApp@@UEAAJF@Z`
- size: `113`
- prototype: `__int64 __fastcall(CIISApp *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800055e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::AppCreate(CIISApp *this, __int16 a2)
{
  __int64 v2; // r10
  __int64 v4; // r9

  v2 = *((_QWORD *)this + 18);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, bool, _QWORD, _DWORD))(*(_QWORD *)v2 + 24LL))(
             v2,
             *((_QWORD *)this + 9),
             a2 == 0,
             0,
             0);
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, bool))(*(_QWORD *)v4 + 24LL))(
             *((_QWORD *)this + 16),
             *((_QWORD *)this + 9),
             a2 != 0);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x1800055e0  sub     rsp, 38h
0x1800055e4  mov     r10, [rcx+90h]
0x1800055eb  xor     r11d, r11d
0x1800055ee  test    r10, r10
0x1800055f1  jz      short loc_18000561A
0x1800055f3  mov     rax, [r10]
0x1800055f6  test    dx, dx
0x1800055f9  mov     rdx, [rcx+48h]
0x1800055fd  mov     r8d, r11d
0x180005600  setz    r8b
0x180005604  mov     [rsp+38h+var_18], r11d
0x180005609  xor     r9d, r9d
0x18000560c  mov     rcx, r10
0x18000560f  mov     rax, [rax+18h]
0x180005613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005618  jmp     short loc_18000564C
0x18000561a  mov     r9, [rcx+80h]
0x180005621  test    r9, r9
0x180005624  jz      short loc_180005647
0x180005626  mov     rax, [r9]
0x180005629  test    dx, dx
0x18000562c  mov     rdx, [rcx+48h]
0x180005630  mov     r8d, r11d
0x180005633  setnz   r8b
0x180005637  mov     rcx, r9
0x18000563a  mov     rax, [rax+18h]
0x18000563e  add     rsp, 38h
0x180005642  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005647  mov     eax, 80004002h
0x18000564c  add     rsp, 38h
0x180005650  retn
```
