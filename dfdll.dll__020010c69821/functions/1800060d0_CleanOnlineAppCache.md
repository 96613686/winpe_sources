# CleanOnlineAppCache

- ea: `0x1800060d0`
- end: `0x180006160`
- name: `CleanOnlineAppCache`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001ad0`
- `0x180007928`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180006113`
- `OLEAUT32!__imp_VariantInit` at `0x180006113`
- `OLEAUT32!__imp_VariantClear` at `0x18000613c`
- `OLEAUT32!__imp_VariantClear` at `0x18000613c`

## string_xrefs

- `0x180006126`: `CleanOnlineAppCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 CleanOnlineAppCache()
{
  unsigned int v0; // ebx
  void **v2; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v4[2]; // [rsp+40h] [rbp-30h] BYREF
  struct tagVARIANT *v5; // [rsp+50h] [rbp-20h]
  int v6; // [rsp+58h] [rbp-18h]
  unsigned int v7; // [rsp+60h] [rbp-10h]

  v4[0] = &Dfdll::CVariantArray::`vftable';
  v5 = 0;
  v6 = 0;
  v4[1] = &Dfdll::CVariantBufferBase::`vftable';
  v7 = 0;
  v2 = &Dfdll::CVariant::`vftable';
  VariantInit(&pvarg);
  v0 = InvokeServer(L"CleanOnlineAppCache", v5, v7, (struct Dfdll::CVariant *)&v2);
  v2 = &Dfdll::CVariant::`vftable';
  VariantClear(&pvarg);
  Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v4);
  return v0;
}

```

## disassembly

```asm
0x1800060d0  mov     [rsp-8+arg_0], rbx
0x1800060d5  mov     [rsp-8+arg_8], rdi
0x1800060da  push    rbp
0x1800060db  mov     rbp, rsp
0x1800060de  sub     rsp, 70h
0x1800060e2  lea     rax, ??_7CVariantArray@Dfdll@@6B@; const Dfdll::CVariantArray::`vftable'
0x1800060e9  mov     [rbp+var_30], rax
0x1800060ed  xor     ecx, ecx
0x1800060ef  mov     [rbp+var_20], rcx
0x1800060f3  mov     [rbp+var_18], ecx
0x1800060f6  lea     rax, ??_7CVariantBufferBase@Dfdll@@6B@; const Dfdll::CVariantBufferBase::`vftable'
0x1800060fd  mov     [rbp+var_28], rax
0x180006101  mov     [rbp+var_10], ecx
0x180006104  lea     rdi, ??_7CVariant@Dfdll@@6B@; const Dfdll::CVariant::`vftable'
0x18000610b  mov     [rbp+var_50], rdi
0x18000610f  lea     rcx, [rbp+pvarg]; pvarg
0x180006113  call    cs:__imp_VariantInit
0x180006119  nop
0x18000611a  lea     r9, [rbp+var_50]; struct Dfdll::CVariant *
0x18000611e  mov     r8d, [rbp+var_10]; unsigned int
0x180006122  mov     rdx, [rbp+var_20]; struct tagVARIANT *
0x180006126  lea     rcx, aCleanonlineapp_0; "CleanOnlineAppCache"
0x18000612d  call    ?InvokeServer@@YAJPEBGPEBUtagVARIANT@@IAEAVCVariant@Dfdll@@@Z; InvokeServer(ushort const *,tagVARIANT const *,uint,Dfdll::CVariant &)
0x180006132  mov     ebx, eax
0x180006134  mov     [rbp+var_50], rdi
0x180006138  lea     rcx, [rbp+pvarg]; pvarg
0x18000613c  call    cs:__imp_VariantClear
0x180006142  nop
0x180006143  lea     rcx, [rbp+var_30]; this
0x180006147  call    ??1CVariantArray@Dfdll@@UEAA@XZ; Dfdll::CVariantArray::~CVariantArray(void)
0x18000614c  mov     eax, ebx
0x18000614e  lea     r11, [rsp+70h+var_s0]
0x180006153  mov     rbx, [r11+10h]
0x180006157  mov     rdi, [r11+18h]
0x18000615b  mov     rsp, r11
0x18000615e  pop     rbp
0x18000615f  retn
```
