# CIISComputer::Export(ushort *,ushort *,ushort *,long)

- ea: `0x180006c70`
- end: `0x180006d08`
- name: `?Export@CIISComputer@@UEAAJPEAG00J@Z`
- size: `152`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006c70`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::Export(
        CIISComputer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  int v9; // ebx
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 15);
  v11 = 0;
  v9 = (**v8)(v8, &IID_IMSAdminBase2_W, &v11);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int))(*(_QWORD *)v11 + 288LL))(
           v11,
           a2,
           a3,
           a4,
           a5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006c70  push    rbx
0x180006c72  push    rbp
0x180006c73  push    rsi
0x180006c74  push    rdi
0x180006c75  sub     rsp, 38h
0x180006c79  mov     rdi, r9
0x180006c7c  mov     rsi, r8
0x180006c7f  mov     rbp, rdx
0x180006c82  test    rdx, rdx
0x180006c85  jz      short loc_180006CFA
0x180006c87  test    r8, r8
0x180006c8a  jz      short loc_180006CFA
0x180006c8c  test    r9, r9
0x180006c8f  jz      short loc_180006CFA
0x180006c91  mov     rcx, [rcx+78h]
0x180006c95  lea     r8, [rsp+58h+arg_8]
0x180006c9a  mov     [rsp+58h+arg_8], 0
0x180006ca3  lea     rdx, IID_IMSAdminBase2_W
0x180006caa  mov     rax, [rcx]
0x180006cad  mov     rax, [rax]
0x180006cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb5  mov     ebx, eax
0x180006cb7  test    eax, eax
0x180006cb9  js      short loc_180006CF6
0x180006cbb  mov     rcx, [rsp+58h+arg_8]
0x180006cc0  mov     r9, rdi
0x180006cc3  mov     edx, [rsp+58h+arg_20]
0x180006cca  mov     r8, rsi
0x180006ccd  mov     [rsp+58h+var_38], edx
0x180006cd1  mov     rdx, rbp
0x180006cd4  mov     rax, [rcx]
0x180006cd7  mov     rax, [rax+120h]
0x180006cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce3  mov     rcx, [rsp+58h+arg_8]
0x180006ce8  mov     ebx, eax
0x180006cea  mov     rax, [rcx]
0x180006ced  mov     rax, [rax+10h]
0x180006cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf6  mov     eax, ebx
0x180006cf8  jmp     short loc_180006CFF
0x180006cfa  mov     eax, 80004003h
0x180006cff  add     rsp, 38h
0x180006d03  pop     rdi
0x180006d04  pop     rsi
0x180006d05  pop     rbp
0x180006d06  pop     rbx
0x180006d07  retn
```
