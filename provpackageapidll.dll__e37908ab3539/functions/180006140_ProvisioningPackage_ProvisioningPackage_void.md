# ProvisioningPackage::ProvisioningPackage(void)

- ea: `0x180006140`
- end: `0x1800061ed`
- name: `??0ProvisioningPackage@@QEAA@XZ`
- size: `173`
- prototype: `ProvisioningPackage *__fastcall(ProvisioningPackage *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005cc0`
- `0x180005e10`
- `0x180009740`

## callees

- `0x180002110`

## pseudocode

```c
ProvisioningPackage *__fastcall ProvisioningPackage::ProvisioningPackage(ProvisioningPackage *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax

  *(_QWORD *)this = &ProvisioningPackage::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v2 = operator new(0x48u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *((_QWORD *)this + 5) = v2;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  v3 = operator new(0x30u);
  *v3 = v3;
  v3[1] = v3;
  *((_QWORD *)this + 7) = v3;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  return this;
}

```

## disassembly

```asm
0x180006140  mov     [rsp+arg_10], rbx
0x180006145  mov     [rsp+arg_0], rcx
0x18000614a  push    rdi
0x18000614b  sub     rsp, 20h
0x18000614f  mov     rdi, rcx
0x180006152  lea     rax, ??_7ProvisioningPackage@@6B@; const ProvisioningPackage::`vftable'
0x180006159  mov     [rcx], rax
0x18000615c  mov     qword ptr [rcx+8], 0
0x180006164  mov     qword ptr [rcx+10h], 0
0x18000616c  mov     qword ptr [rcx+18h], 0
0x180006174  mov     qword ptr [rcx+20h], 0
0x18000617c  mov     qword ptr [rcx+28h], 0
0x180006184  mov     qword ptr [rcx+30h], 0
0x18000618c  mov     ecx, 48h ; 'H'; Size
0x180006191  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006196  mov     [rax], rax
0x180006199  mov     [rax+8], rax
0x18000619d  mov     [rax+10h], rax
0x1800061a1  mov     word ptr [rax+18h], 101h
0x1800061a7  mov     [rdi+28h], rax
0x1800061ab  mov     qword ptr [rdi+38h], 0
0x1800061b3  mov     qword ptr [rdi+40h], 0
0x1800061bb  mov     ecx, 30h ; '0'; Size
0x1800061c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061c5  mov     [rax], rax
0x1800061c8  mov     [rax+8], rax
0x1800061cc  mov     [rdi+38h], rax
0x1800061d0  mov     qword ptr [rdi+50h], 0
0x1800061d8  mov     dword ptr [rdi+58h], 0
0x1800061df  mov     rax, rdi
0x1800061e2  mov     rbx, [rsp+28h+arg_10]
0x1800061e7  add     rsp, 20h
0x1800061eb  pop     rdi
0x1800061ec  retn
```
