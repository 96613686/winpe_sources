# CheckForUpdate(Dfdll::CString &)

- ea: `0x180002720`
- end: `0x18000280a`
- name: `?CheckForUpdate@@YAJAEAVCString@Dfdll@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct Dfdll::CString *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000444c`
- `0x180004580`

## callees

- `0x180001ad0`
- `0x180001e84`
- `0x180002720`
- `0x180007928`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180002767`
- `OLEAUT32!__imp_VariantInit` at `0x180002767`
- `OLEAUT32!__imp_VariantClear` at `0x180002784`
- `OLEAUT32!__imp_VariantClear` at `0x1800027a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800027d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800027e6`
- `OLEAUT32!__imp_VariantClear` at `0x180002784`
- `OLEAUT32!__imp_VariantClear` at `0x1800027a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800027d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800027e6`

## string_xrefs

- `0x1800027b9`: `CheckForDeploymentUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CheckForUpdate(struct Dfdll::CString *a1)
{
  OLECHAR *v2; // rdx
  int v3; // ebx
  void **v5; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v7[2]; // [rsp+40h] [rbp-30h] BYREF
  struct tagVARIANT *v8; // [rsp+50h] [rbp-20h]
  int v9; // [rsp+58h] [rbp-18h]
  unsigned int v10; // [rsp+60h] [rbp-10h]

  v7[0] = &Dfdll::CVariantArray::`vftable';
  v8 = 0;
  v9 = 0;
  v7[1] = &Dfdll::CVariantBufferBase::`vftable';
  v10 = 0;
  v5 = &Dfdll::CVariant::`vftable';
  VariantInit(&pvarg);
  v2 = (OLECHAR *)*((_QWORD *)a1 + 2);
  if ( v2 )
  {
    v3 = Dfdll::CVariantArray::Add((Dfdll::CVariantArray *)v7, v2);
    if ( v3 >= 0 )
    {
      v3 = InvokeServer(L"CheckForDeploymentUpdate", v8, v10, (struct Dfdll::CVariant *)&v5);
      if ( v3 >= 0 )
        v3 = 0;
      v5 = &Dfdll::CVariant::`vftable';
      VariantClear(&pvarg);
    }
    else
    {
      v5 = &Dfdll::CVariant::`vftable';
      VariantClear(&pvarg);
    }
  }
  else
  {
    v3 = -2147024809;
    v5 = &Dfdll::CVariant::`vftable';
    VariantClear(&pvarg);
  }
  Dfdll::CVariantArray::~CVariantArray((Dfdll::CVariantArray *)v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002720  mov     [rsp-8+arg_0], rbx
0x180002725  mov     [rsp-8+arg_8], rdi
0x18000272a  push    rbp
0x18000272b  mov     rbp, rsp
0x18000272e  sub     rsp, 70h
0x180002732  mov     rbx, rcx
0x180002735  lea     rax, ??_7CVariantArray@Dfdll@@6B@; const Dfdll::CVariantArray::`vftable'
0x18000273c  mov     [rbp+var_30], rax
0x180002740  and     [rbp+var_20], 0
0x180002745  and     [rbp+var_18], 0
0x180002749  lea     rax, ??_7CVariantBufferBase@Dfdll@@6B@; const Dfdll::CVariantBufferBase::`vftable'
0x180002750  mov     [rbp+var_28], rax
0x180002754  and     [rbp+var_10], 0
0x180002758  lea     rdi, ??_7CVariant@Dfdll@@6B@; const Dfdll::CVariant::`vftable'
0x18000275f  mov     [rbp+var_50], rdi
0x180002763  lea     rcx, [rbp+pvarg]; pvarg
0x180002767  call    cs:__imp_VariantInit
0x18000276d  nop
0x18000276e  mov     rdx, [rbx+10h]; psz
0x180002772  test    rdx, rdx
0x180002775  jnz     short loc_18000278D
0x180002777  mov     ebx, 80070057h
0x18000277c  mov     [rbp+var_50], rdi
0x180002780  lea     rcx, [rbp+pvarg]; pvarg
0x180002784  call    cs:__imp_VariantClear
0x18000278a  nop
0x18000278b  jmp     short loc_1800027ED
0x18000278d  lea     rcx, [rbp+var_30]; this
0x180002791  call    ?Add@CVariantArray@Dfdll@@QEAAJPEBG@Z; Dfdll::CVariantArray::Add(ushort const *)
0x180002796  mov     ebx, eax
0x180002798  test    eax, eax
0x18000279a  jns     short loc_1800027AD
0x18000279c  mov     [rbp+var_50], rdi
0x1800027a0  lea     rcx, [rbp+pvarg]; pvarg
0x1800027a4  call    cs:__imp_VariantClear
0x1800027aa  nop
0x1800027ab  jmp     short loc_1800027ED
0x1800027ad  lea     r9, [rbp+var_50]; struct Dfdll::CVariant *
0x1800027b1  mov     r8d, [rbp+var_10]; unsigned int
0x1800027b5  mov     rdx, [rbp+var_20]; struct tagVARIANT *
0x1800027b9  lea     rcx, aCheckfordeploy; "CheckForDeploymentUpdate"
0x1800027c0  call    ?InvokeServer@@YAJPEBGPEBUtagVARIANT@@IAEAVCVariant@Dfdll@@@Z; InvokeServer(ushort const *,tagVARIANT const *,uint,Dfdll::CVariant &)
0x1800027c5  mov     ebx, eax
0x1800027c7  test    eax, eax
0x1800027c9  jns     short loc_1800027DC
0x1800027cb  mov     [rbp+var_50], rdi
0x1800027cf  lea     rcx, [rbp+pvarg]; pvarg
0x1800027d3  call    cs:__imp_VariantClear
0x1800027d9  nop
0x1800027da  jmp     short loc_1800027ED
0x1800027dc  xor     ebx, ebx
0x1800027de  mov     [rbp+var_50], rdi
0x1800027e2  lea     rcx, [rbp+pvarg]; pvarg
0x1800027e6  call    cs:__imp_VariantClear
0x1800027ec  nop
0x1800027ed  lea     rcx, [rbp+var_30]; this
0x1800027f1  call    ??1CVariantArray@Dfdll@@UEAA@XZ; Dfdll::CVariantArray::~CVariantArray(void)
0x1800027f6  mov     eax, ebx
0x1800027f8  lea     r11, [rsp+70h+var_s0]
0x1800027fd  mov     rbx, [r11+10h]
0x180002801  mov     rdi, [r11+18h]
0x180002805  mov     rsp, r11
0x180002808  pop     rbp
0x180002809  retn
```
