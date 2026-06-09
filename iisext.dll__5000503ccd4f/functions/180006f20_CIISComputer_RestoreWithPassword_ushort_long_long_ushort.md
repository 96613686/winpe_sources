# CIISComputer::RestoreWithPassword(ushort *,long,long,ushort *)

- ea: `0x180006f20`
- end: `0x180006fc4`
- name: `?RestoreWithPassword@CIISComputer@@UEAAJPEAGJJ0@Z`
- size: `164`
- prototype: `__int64 __fastcall(CIISComputer *this, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006f20`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::RestoreWithPassword(
        CIISComputer *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v8; // rdi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  int v10; // ebx
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v8 = a5;
  if ( !a5 )
    return 2147500035LL;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 15);
  v12 = 0;
  v10 = (**v9)(v9, &IID_IMSAdminBase2_W, &v12);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)v12 + 280LL))(
            v12,
            a2,
            a3,
            a4,
            v8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006f20  mov     r11, rsp
0x180006f23  mov     [r11+8], rbx
0x180006f27  mov     [r11+18h], rbp
0x180006f2b  push    rsi
0x180006f2c  push    rdi
0x180006f2d  push    r14
0x180006f2f  sub     rsp, 30h
0x180006f33  mov     ebp, r9d
0x180006f36  mov     r14d, r8d
0x180006f39  mov     rsi, rdx
0x180006f3c  test    rdx, rdx
0x180006f3f  jz      short loc_180006FAC
0x180006f41  mov     rdi, [rsp+48h+arg_20]
0x180006f46  test    rdi, rdi
0x180006f49  jz      short loc_180006FAC
0x180006f4b  mov     rcx, [rcx+78h]
0x180006f4f  lea     r8, [r11+10h]
0x180006f53  mov     qword ptr [r11+10h], 0
0x180006f5b  lea     rdx, IID_IMSAdminBase2_W
0x180006f62  mov     rax, [rcx]
0x180006f65  mov     rax, [rax]
0x180006f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6d  mov     ebx, eax
0x180006f6f  test    eax, eax
0x180006f71  js      short loc_180006FA8
0x180006f73  mov     rcx, [rsp+48h+arg_8]
0x180006f78  mov     r9d, ebp
0x180006f7b  mov     r8d, r14d
0x180006f7e  mov     [rsp+48h+var_28], rdi
0x180006f83  mov     rdx, rsi
0x180006f86  mov     rax, [rcx]
0x180006f89  mov     rax, [rax+118h]
0x180006f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f95  mov     rcx, [rsp+48h+arg_8]
0x180006f9a  mov     ebx, eax
0x180006f9c  mov     rax, [rcx]
0x180006f9f  mov     rax, [rax+10h]
0x180006fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa8  mov     eax, ebx
0x180006faa  jmp     short loc_180006FB1
0x180006fac  mov     eax, 80004003h
0x180006fb1  mov     rbx, [rsp+48h+arg_0]
0x180006fb6  mov     rbp, [rsp+48h+arg_10]
0x180006fbb  add     rsp, 30h
0x180006fbf  pop     r14
0x180006fc1  pop     rdi
0x180006fc2  pop     rsi
0x180006fc3  retn
```
