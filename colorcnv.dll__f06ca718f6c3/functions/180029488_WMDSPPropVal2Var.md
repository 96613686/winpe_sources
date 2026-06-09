# WMDSPPropVal2Var

- ea: `0x180029488`
- end: `0x18002957a`
- name: `WMDSPPropVal2Var`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029790`

## callees

- `0x180029488`
- `0x180029fc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002954e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002954e`
- `OLEAUT32!__imp_SysFreeString` at `0x180029545`
- `OLEAUT32!__imp_SysFreeString` at `0x180029559`
- `OLEAUT32!__imp_SysFreeString` at `0x180029545`
- `OLEAUT32!__imp_SysFreeString` at `0x180029559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294fb`

## pseudocode

```c
void __fastcall WMDSPPropVal2Var(__int64 a1, int *a2)
{
  void *v4; // rcx
  unsigned int v5; // eax
  void *v6; // rax
  OLECHAR *v7; // rcx
  BSTR v8; // rsi

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *(_QWORD *)(a1 + 8) = *(_QWORD *)a2;
      return;
    case 8:
      v7 = *(OLECHAR **)(a1 + 8);
      v8 = 0;
      if ( *(_QWORD *)a2 )
      {
        SysFreeString(v7);
        v8 = SysAllocString(*(const OLECHAR **)a2);
      }
      else
      {
        SysFreeString(v7);
      }
      *(_QWORD *)(a1 + 8) = v8;
      return;
    case 0xB:
      *(_WORD *)(a1 + 8) = *(_WORD *)a2;
      return;
    case 0x13:
LABEL_21:
      *(_DWORD *)(a1 + 8) = *a2;
      return;
    case 0x14:
      goto LABEL_10;
  }
  if ( *(_WORD *)a1 != 65 )
  {
    if ( *(_WORD *)a1 != 72 )
      return;
    goto LABEL_10;
  }
  v4 = *(void **)(a1 + 16);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *a2;
  *(_DWORD *)(a1 + 8) = *a2;
  *(_QWORD *)(a1 + 16) = 0;
  if ( v5 )
  {
    v6 = CoTaskMemAlloc(v5);
    *(_QWORD *)(a1 + 16) = v6;
    if ( v6 )
      memcpy_0(v6, *((const void **)a2 + 1), *(unsigned int *)(a1 + 8));
  }
}

```

## disassembly

```asm
0x180029488  mov     [rsp+arg_0], rbx
0x18002948d  mov     [rsp+arg_8], rsi
0x180029492  push    rdi
0x180029493  sub     rsp, 20h
0x180029497  movzx   r8d, word ptr [rcx]
0x18002949b  mov     rdi, rdx
0x18002949e  mov     rbx, rcx
0x1800294a1  sub     r8d, 3
0x1800294a5  jz      loc_180029565
0x1800294ab  sub     r8d, 1
0x1800294af  jz      loc_180029565
0x1800294b5  sub     r8d, 1
0x1800294b9  jz      short loc_1800294E7
0x1800294bb  sub     r8d, 3
0x1800294bf  jz      short loc_18002953A
0x1800294c1  sub     r8d, 3
0x1800294c5  jz      short loc_180029531
0x1800294c7  sub     r8d, 8
0x1800294cb  jz      loc_180029565
0x1800294d1  sub     r8d, 1
0x1800294d5  jz      short loc_1800294E7
0x1800294d7  sub     r8d, 2Dh ; '-'
0x1800294db  jz      short loc_1800294F0
0x1800294dd  cmp     r8d, 7
0x1800294e1  jnz     loc_18002956A
0x1800294e7  mov     rax, [rdx]
0x1800294ea  mov     [rcx+8], rax
0x1800294ee  jmp     short loc_18002956A
0x1800294f0  mov     rcx, [rcx+10h]; pv
0x1800294f4  xor     esi, esi
0x1800294f6  test    rcx, rcx
0x1800294f9  jz      short loc_180029501
0x1800294fb  call    cs:__imp_CoTaskMemFree
0x180029501  mov     eax, [rdi]
0x180029503  mov     [rbx+8], eax
0x180029506  mov     [rbx+10h], rsi
0x18002950a  test    eax, eax
0x18002950c  jz      short loc_18002956A
0x18002950e  mov     ecx, eax; cb
0x180029510  call    cs:__imp_CoTaskMemAlloc
0x180029516  mov     [rbx+10h], rax
0x18002951a  test    rax, rax
0x18002951d  jz      short loc_18002956A
0x18002951f  mov     r8d, [rbx+8]; Size
0x180029523  mov     rcx, rax; void *
0x180029526  mov     rdx, [rdi+8]; Src
0x18002952a  call    memcpy_0
0x18002952f  jmp     short loc_18002956A
0x180029531  movzx   eax, word ptr [rdx]
0x180029534  mov     [rcx+8], ax
0x180029538  jmp     short loc_18002956A
0x18002953a  mov     rcx, [rcx+8]; bstrString
0x18002953e  xor     esi, esi
0x180029540  cmp     [rdx], rsi
0x180029543  jz      short loc_180029559
0x180029545  call    cs:__imp_SysFreeString
0x18002954b  mov     rcx, [rdi]; psz
0x18002954e  call    cs:__imp_SysAllocString
0x180029554  mov     rsi, rax
0x180029557  jmp     short loc_18002955F
0x180029559  call    cs:__imp_SysFreeString
0x18002955f  mov     [rbx+8], rsi
0x180029563  jmp     short loc_18002956A
0x180029565  mov     eax, [rdx]
0x180029567  mov     [rcx+8], eax
0x18002956a  mov     rbx, [rsp+28h+arg_0]
0x18002956f  mov     rsi, [rsp+28h+arg_8]
0x180029574  add     rsp, 20h
0x180029578  pop     rdi
0x180029579  retn
```
