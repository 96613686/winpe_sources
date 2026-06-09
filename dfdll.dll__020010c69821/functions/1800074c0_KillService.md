# KillService

- ea: `0x1800074c0`
- end: `0x180007550`
- name: `KillService`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001ad0`
- `0x180007928`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180007503`
- `OLEAUT32!__imp_VariantInit` at `0x180007503`
- `OLEAUT32!__imp_VariantClear` at `0x18000752c`
- `OLEAUT32!__imp_VariantClear` at `0x18000752c`

## string_xrefs

- `0x180007516`: `EndServiceRightNow`

## pseudocode

```c
__int64 KillService()
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
  v0 = InvokeServer(L"EndServiceRightNow", v5, v7, (struct Dfdll::CVariant *)&v2);
  v2 = &Dfdll::CVariant::`vftable';
  VariantClear(&pvarg);
  Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v4);
  return v0;
}

```

## disassembly

```asm
0x1800074c0  mov     [rsp-8+arg_0], rbx
0x1800074c5  mov     [rsp-8+arg_8], rdi
0x1800074ca  push    rbp
0x1800074cb  mov     rbp, rsp
0x1800074ce  sub     rsp, 70h
0x1800074d2  lea     rax, ??_7CVariantArray@Dfdll@@6B@; const Dfdll::CVariantArray::`vftable'
0x1800074d9  mov     [rbp+var_30], rax
0x1800074dd  xor     ecx, ecx
0x1800074df  mov     [rbp+var_20], rcx
0x1800074e3  mov     [rbp+var_18], ecx
0x1800074e6  lea     rax, ??_7CVariantBufferBase@Dfdll@@6B@; const Dfdll::CVariantBufferBase::`vftable'
0x1800074ed  mov     [rbp+var_28], rax
0x1800074f1  mov     [rbp+var_10], ecx
0x1800074f4  lea     rdi, ??_7CVariant@Dfdll@@6B@; const Dfdll::CVariant::`vftable'
0x1800074fb  mov     [rbp+var_50], rdi
0x1800074ff  lea     rcx, [rbp+pvarg]; pvarg
0x180007503  call    cs:__imp_VariantInit
0x180007509  nop
0x18000750a  lea     r9, [rbp+var_50]; struct Dfdll::CVariant *
0x18000750e  mov     r8d, [rbp+var_10]; unsigned int
0x180007512  mov     rdx, [rbp+var_20]; struct tagVARIANT *
0x180007516  lea     rcx, aEndservicerigh; "EndServiceRightNow"
0x18000751d  call    ?InvokeServer@@YAJPEBGPEBUtagVARIANT@@IAEAVCVariant@Dfdll@@@Z; InvokeServer(ushort const *,tagVARIANT const *,uint,Dfdll::CVariant &)
0x180007522  mov     ebx, eax
0x180007524  mov     [rbp+var_50], rdi
0x180007528  lea     rcx, [rbp+pvarg]; pvarg
0x18000752c  call    cs:__imp_VariantClear
0x180007532  nop
0x180007533  lea     rcx, [rbp+var_30]; this
0x180007537  call    ??1CVariantArray@Dfdll@@UEAA@XZ; Dfdll::CVariantArray::~CVariantArray(void)
0x18000753c  mov     eax, ebx
0x18000753e  lea     r11, [rsp+70h+var_s0]
0x180007543  mov     rbx, [r11+10h]
0x180007547  mov     rdi, [r11+18h]
0x18000754b  mov     rsp, r11
0x18000754e  pop     rbp
0x18000754f  retn
```
