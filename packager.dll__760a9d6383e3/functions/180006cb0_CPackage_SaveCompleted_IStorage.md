# CPackage::SaveCompleted(IStorage *)

- ea: `0x180006cb0`
- end: `0x180006cf2`
- name: `?SaveCompleted@CPackage@@UEAAJPEAUIStorage@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStorage *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006cb0`

## pseudocode

```c
__int64 __fastcall CPackage::SaveCompleted(CPackage *this, struct IStorage *a2)
{
  int v2; // r8d
  __int64 v3; // rax

  v2 = *((_DWORD *)this + 17);
  if ( (unsigned int)(v2 - 2) > 1 || !a2 && v2 == 3 )
    return 2147549183LL;
  v3 = *((_QWORD *)this + 9);
  *((_DWORD *)this + 17) = 1;
  if ( !v3 || *(_QWORD *)(v3 + 600) != -1 )
    *((_DWORD *)this + 28) = 0;
  return 0;
}

```

## disassembly

```asm
0x180006cb0  mov     r8d, [rcx+44h]
0x180006cb4  lea     eax, [r8-2]
0x180006cb8  cmp     eax, 1
0x180006cbb  ja      short loc_180006CEC
0x180006cbd  test    rdx, rdx
0x180006cc0  jnz     short loc_180006CC8
0x180006cc2  cmp     r8d, 3
0x180006cc6  jz      short loc_180006CEC
0x180006cc8  mov     rax, [rcx+48h]
0x180006ccc  mov     dword ptr [rcx+44h], 1
0x180006cd3  test    rax, rax
0x180006cd6  jz      short loc_180006CE2
0x180006cd8  cmp     qword ptr [rax+258h], 0FFFFFFFFFFFFFFFFh
0x180006ce0  jz      short loc_180006CE9
0x180006ce2  mov     dword ptr [rcx+70h], 0
0x180006ce9  xor     eax, eax
0x180006ceb  retn
0x180006cec  mov     eax, 8000FFFFh
0x180006cf1  retn
```
