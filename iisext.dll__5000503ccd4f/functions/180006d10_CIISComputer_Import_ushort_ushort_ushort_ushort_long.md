# CIISComputer::Import(ushort *,ushort *,ushort *,ushort *,long)

- ea: `0x180006d10`
- end: `0x180006dd0`
- name: `?Import@CIISComputer@@UEAAJPEAG000J@Z`
- size: `192`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006d10`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::Import(
        CIISComputer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  unsigned __int16 *v9; // rdi
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // ebx
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( !a3 )
    return 2147500035LL;
  if ( !a4 )
    return 2147500035LL;
  v9 = a5;
  if ( !a5 )
    return 2147500035LL;
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 15);
  v13 = 0;
  v11 = (**v10)(v10, &IID_IMSAdminBase2_W, &v13);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int))(*(_QWORD *)v13 + 296LL))(
            v13,
            a2,
            a3,
            a4,
            v9,
            a6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006d10  mov     r11, rsp
0x180006d13  mov     [r11+8], rbx
0x180006d17  mov     [r11+18h], rbp
0x180006d1b  push    rsi
0x180006d1c  push    rdi
0x180006d1d  push    r14
0x180006d1f  sub     rsp, 40h
0x180006d23  mov     rsi, r9
0x180006d26  mov     rbp, r8
0x180006d29  mov     r14, rdx
0x180006d2c  test    rdx, rdx
0x180006d2f  jz      loc_180006DB8
0x180006d35  test    r8, r8
0x180006d38  jz      short loc_180006DB8
0x180006d3a  test    r9, r9
0x180006d3d  jz      short loc_180006DB8
0x180006d3f  mov     rdi, [rsp+58h+arg_20]
0x180006d47  test    rdi, rdi
0x180006d4a  jz      short loc_180006DB8
0x180006d4c  mov     rcx, [rcx+78h]
0x180006d50  lea     r8, [r11+10h]
0x180006d54  mov     qword ptr [r11+10h], 0
0x180006d5c  lea     rdx, IID_IMSAdminBase2_W
0x180006d63  mov     rax, [rcx]
0x180006d66  mov     rax, [rax]
0x180006d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6e  mov     ebx, eax
0x180006d70  test    eax, eax
0x180006d72  js      short loc_180006DB4
0x180006d74  mov     rcx, [rsp+58h+arg_8]
0x180006d79  mov     r9, rsi
0x180006d7c  mov     edx, [rsp+58h+arg_28]
0x180006d83  mov     r8, rbp
0x180006d86  mov     [rsp+58h+var_30], edx
0x180006d8a  mov     rdx, r14
0x180006d8d  mov     [rsp+58h+var_38], rdi
0x180006d92  mov     rax, [rcx]
0x180006d95  mov     rax, [rax+128h]
0x180006d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da1  mov     rcx, [rsp+58h+arg_8]
0x180006da6  mov     ebx, eax
0x180006da8  mov     rax, [rcx]
0x180006dab  mov     rax, [rax+10h]
0x180006daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db4  mov     eax, ebx
0x180006db6  jmp     short loc_180006DBD
0x180006db8  mov     eax, 80004003h
0x180006dbd  mov     rbx, [rsp+58h+arg_0]
0x180006dc2  mov     rbp, [rsp+58h+arg_10]
0x180006dc7  add     rsp, 40h
0x180006dcb  pop     r14
0x180006dcd  pop     rdi
0x180006dce  pop     rsi
0x180006dcf  retn
```
