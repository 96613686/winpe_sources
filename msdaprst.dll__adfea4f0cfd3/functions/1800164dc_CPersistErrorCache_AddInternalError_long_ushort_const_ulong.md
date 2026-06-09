# CPersistErrorCache::AddInternalError(long,ushort const *,ulong)

- ea: `0x1800164dc`
- end: `0x180016566`
- name: `?AddInternalError@CPersistErrorCache@@QEAAXJPEBGK@Z`
- size: `138`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this, int, OLECHAR *psz, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dd70`
- `0x180022240`
- `0x1800239ec`

## callees

- `0x180016128`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001651d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001651d`
- `OLEAUT32!__imp_VariantInit` at `0x180016504`
- `OLEAUT32!__imp_VariantInit` at `0x180016504`
- `OLEAUT32!__imp_VariantClear` at `0x180016550`
- `OLEAUT32!__imp_VariantClear` at `0x180016550`

## pseudocode

```c
void __fastcall CPersistErrorCache::AddInternalError(
        CPersistErrorCache *this,
        unsigned int a2,
        OLECHAR *psz,
        unsigned int a4)
{
  BSTR v8; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  v8 = SysAllocString(psz);
  *((_DWORD *)this + 4) = 1;
  pvarg.llVal = (LONGLONG)v8;
  *((_QWORD *)this + 3) = &pvarg;
  CPersistErrorCache::AddInternalError(this, a2, a4);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x1800164dc  push    rbx
0x1800164de  push    rbp
0x1800164df  push    rsi
0x1800164e0  push    rdi
0x1800164e1  sub     rsp, 48h
0x1800164e5  mov     rsi, rcx
0x1800164e8  xorps   xmm0, xmm0
0x1800164eb  xor     eax, eax
0x1800164ed  lea     rcx, [rsp+68h+pvarg]; pvarg
0x1800164f2  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x1800164f7  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x1800164fc  mov     ebp, r9d
0x1800164ff  mov     rbx, r8
0x180016502  mov     edi, edx
0x180016504  call    cs:__imp_VariantInit
0x18001650b  nop     dword ptr [rax+rax+00h]
0x180016510  mov     eax, 8
0x180016515  mov     rcx, rbx; psz
0x180016518  mov     word ptr [rsp+68h+pvarg], ax
0x18001651d  call    cs:__imp_SysAllocString
0x180016524  nop     dword ptr [rax+rax+00h]
0x180016529  mov     r8d, ebp; unsigned int
0x18001652c  mov     dword ptr [rsi+10h], 1
0x180016533  mov     qword ptr [rsp+68h+pvarg+8], rax
0x180016538  mov     edx, edi; int
0x18001653a  lea     rax, [rsp+68h+pvarg]
0x18001653f  mov     rcx, rsi; this
0x180016542  mov     [rsi+18h], rax
0x180016546  call    ?AddInternalError@CPersistErrorCache@@QEAAXJK@Z; CPersistErrorCache::AddInternalError(long,ulong)
0x18001654b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180016550  call    cs:__imp_VariantClear
0x180016557  nop     dword ptr [rax+rax+00h]
0x18001655c  add     rsp, 48h
0x180016560  pop     rdi
0x180016561  pop     rsi
0x180016562  pop     rbp
0x180016563  pop     rbx
0x180016564  retn
```
