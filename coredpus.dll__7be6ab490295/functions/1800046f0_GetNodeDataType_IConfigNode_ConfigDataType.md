# GetNodeDataType(IConfigNode *,ConfigDataType *)

- ea: `0x1800046f0`
- end: `0x180004778`
- name: `?GetNodeDataType@@YAJPEAUIConfigNode@@PEAW4ConfigDataType@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(struct IConfigNode *, enum ConfigDataType *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b560`
- `0x18001f290`

## callees

- `0x1800046f0`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180004714`
- `OLEAUT32!__imp_VariantInit` at `0x180004714`
- `OLEAUT32!__imp_VariantClear` at `0x18000475e`
- `OLEAUT32!__imp_VariantClear` at `0x18000475e`

## pseudocode

```c
__int64 __fastcall GetNodeDataType(struct IConfigNode *a1, enum ConfigDataType *a2)
{
  int v4; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64 *, VARIANTARG *))(*(_QWORD *)a1 + 160LL))(
         a1,
         CFGMGR_PROPERTY_DATATYPE,
         &pvarg);
  if ( v4 >= 0 )
  {
    if ( pvarg.vt == 3 )
      *(_DWORD *)a2 = pvarg.lVal;
    else
      v4 = -2147467259;
  }
  VariantClear(&pvarg);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800046f0  mov     [rsp+arg_0], rbx
0x1800046f5  push    rdi
0x1800046f6  sub     rsp, 40h
0x1800046fa  mov     rbx, rcx
0x1800046fd  xorps   xmm0, xmm0
0x180004700  xor     eax, eax
0x180004702  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180004707  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x18000470c  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x180004711  mov     rdi, rdx
0x180004714  call    cs:__imp_VariantInit
0x18000471b  nop     dword ptr [rax+rax+00h]
0x180004720  mov     rax, [rbx]
0x180004723  lea     r8, [rsp+48h+pvarg]
0x180004728  lea     rdx, CFGMGR_PROPERTY_DATATYPE
0x18000472f  mov     rcx, rbx
0x180004732  mov     rax, [rax+0A0h]
0x180004739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473e  mov     ebx, eax
0x180004740  test    eax, eax
0x180004742  js      short loc_180004759
0x180004744  cmp     word ptr [rsp+48h+pvarg], 3
0x18000474a  jz      short loc_180004753
0x18000474c  mov     ebx, 80004005h
0x180004751  jmp     short loc_180004759
0x180004753  mov     eax, dword ptr [rsp+48h+pvarg+8]
0x180004757  mov     [rdi], eax
0x180004759  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18000475e  call    cs:__imp_VariantClear
0x180004765  nop     dword ptr [rax+rax+00h]
0x18000476a  mov     eax, ebx
0x18000476c  mov     rbx, [rsp+48h+arg_0]
0x180004771  add     rsp, 40h
0x180004775  pop     rdi
0x180004776  retn
```
