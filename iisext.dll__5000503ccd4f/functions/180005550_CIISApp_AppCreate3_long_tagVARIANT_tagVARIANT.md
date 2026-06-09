# CIISApp::AppCreate3(long,tagVARIANT,tagVARIANT)

- ea: `0x180005550`
- end: `0x1800055d7`
- name: `?AppCreate3@CIISApp@@UEAAJJUtagVARIANT@@0@Z`
- size: `135`
- prototype: `__int64 __fastcall(CIISApp *__hidden this, int, struct tagVARIANT *__struct_ptr, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005550`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::AppCreate3(CIISApp *this, unsigned int a2, struct tagVARIANT *a3, struct tagVARIANT *a4)
{
  __int64 v4; // r11
  int v7; // ecx
  LONGLONG llVal; // r10
  __int64 v10; // rcx

  v4 = *((_QWORD *)this + 18);
  if ( v4 )
  {
    v7 = 0;
    if ( a3->vt == 8 )
      llVal = a3->llVal;
    else
      llVal = 0;
    if ( a4->vt == 11 )
      LOBYTE(v7) = a4->iVal == -1;
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LONGLONG, int))(*(_QWORD *)v4 + 24LL))(
             v4,
             *((_QWORD *)this + 9),
             a2,
             llVal,
             v7);
  }
  else
  {
    v10 = *((_QWORD *)this + 17);
    if ( v10 )
      return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct tagVARIANT *))(*(_QWORD *)v10 + 72LL))(
               v10,
               *((_QWORD *)this + 9),
               a2,
               a4);
    else
      return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180005550  push    rbx
0x180005552  sub     rsp, 30h
0x180005556  mov     r11, [rcx+90h]
0x18000555d  mov     ebx, edx
0x18000555f  mov     rdx, rcx
0x180005562  test    r11, r11
0x180005565  jz      short loc_1800055A8
0x180005567  xor     ecx, ecx
0x180005569  cmp     word ptr [r8], 8
0x18000556e  jnz     short loc_180005576
0x180005570  mov     r10, [r8+8]
0x180005574  jmp     short loc_180005579
0x180005576  xor     r10d, r10d
0x180005579  cmp     word ptr [r9], 0Bh
0x18000557e  jnz     short loc_180005589
0x180005580  cmp     word ptr [r9+8], 0FFFFh
0x180005586  setz    cl
0x180005589  mov     rax, [r11]
0x18000558c  mov     r9, r10
0x18000558f  mov     rdx, [rdx+48h]
0x180005593  mov     r8d, ebx
0x180005596  mov     [rsp+38h+var_18], ecx
0x18000559a  mov     rcx, r11
0x18000559d  mov     rax, [rax+18h]
0x1800055a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a6  jmp     short loc_1800055D1
0x1800055a8  mov     rcx, [rcx+88h]
0x1800055af  test    rcx, rcx
0x1800055b2  jz      short loc_1800055CC
0x1800055b4  mov     rax, [rcx]
0x1800055b7  mov     r8d, ebx
0x1800055ba  mov     rdx, [rdx+48h]
0x1800055be  mov     rax, [rax+48h]
0x1800055c2  add     rsp, 30h
0x1800055c6  pop     rbx
0x1800055c7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800055cc  mov     eax, 80004002h
0x1800055d1  add     rsp, 30h
0x1800055d5  pop     rbx
0x1800055d6  retn
```
