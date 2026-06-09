# WMDSPPropValCopy

- ea: `0x180006bcc`
- end: `0x180006cb2`
- name: `WMDSPPropValCopy`
- size: `230`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006950`
- `0x180029750`
- `0x1800299f0`

## callees

- `0x180006bcc`
- `0x180029fc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006c99`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c99`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ca4`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c43`

## pseudocode

```c
void __fastcall WMDSPPropValCopy(__int16 a1, OLECHAR **a2, int *a3)
{
  OLECHAR *v5; // rcx
  unsigned int v6; // eax
  OLECHAR *v7; // rax
  OLECHAR *v8; // rcx
  BSTR v9; // rsi

  switch ( a1 )
  {
    case 3:
    case 4:
      goto LABEL_2;
    case 5:
LABEL_12:
      *a2 = *(OLECHAR **)a3;
      return;
    case 8:
      v8 = *a2;
      v9 = 0;
      if ( *(_QWORD *)a3 )
      {
        SysFreeString(v8);
        v9 = SysAllocString(*(const OLECHAR **)a3);
      }
      else
      {
        SysFreeString(v8);
      }
      *a2 = v9;
      return;
    case 11:
      *(_WORD *)a2 = *(_WORD *)a3;
      return;
    case 19:
LABEL_2:
      *(_DWORD *)a2 = *a3;
      return;
    case 20:
      goto LABEL_12;
    case 65:
      v5 = a2[1];
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = *a3;
      *(_DWORD *)a2 = *a3;
      a2[1] = 0;
      if ( v6 )
      {
        v7 = (OLECHAR *)CoTaskMemAlloc(v6);
        a2[1] = v7;
        if ( v7 )
          memcpy_0(v7, *((const void **)a3 + 1), *(unsigned int *)a2);
      }
      break;
    case 72:
      goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180006bcc  mov     [rsp+arg_0], rbx
0x180006bd1  mov     [rsp+arg_8], rsi
0x180006bd6  push    rdi
0x180006bd7  sub     rsp, 20h
0x180006bdb  movzx   r9d, cx
0x180006bdf  mov     rdi, r8
0x180006be2  mov     rbx, rdx
0x180006be5  sub     r9d, 3
0x180006be9  jnz     short loc_180006C00
0x180006beb  mov     eax, [r8]
0x180006bee  mov     [rdx], eax
0x180006bf0  mov     rbx, [rsp+28h+arg_0]
0x180006bf5  mov     rsi, [rsp+28h+arg_8]
0x180006bfa  add     rsp, 20h
0x180006bfe  pop     rdi
0x180006bff  retn
0x180006c00  sub     r9d, 1
0x180006c04  jz      short loc_180006BEB
0x180006c06  sub     r9d, 1
0x180006c0a  jz      short loc_180006C30
0x180006c0c  sub     r9d, 3
0x180006c10  jz      short loc_180006C86
0x180006c12  sub     r9d, 3
0x180006c16  jz      short loc_180006C7A
0x180006c18  sub     r9d, 8
0x180006c1c  jz      short loc_180006BEB
0x180006c1e  sub     r9d, 1
0x180006c22  jz      short loc_180006C30
0x180006c24  sub     r9d, 2Dh ; '-'
0x180006c28  jz      short loc_180006C38
0x180006c2a  cmp     r9d, 7
0x180006c2e  jnz     short loc_180006BF0
0x180006c30  mov     rax, [r8]
0x180006c33  mov     [rdx], rax
0x180006c36  jmp     short loc_180006BF0
0x180006c38  mov     rcx, [rdx+8]; pv
0x180006c3c  xor     esi, esi
0x180006c3e  test    rcx, rcx
0x180006c41  jz      short loc_180006C49
0x180006c43  call    cs:__imp_CoTaskMemFree
0x180006c49  mov     eax, [rdi]
0x180006c4b  mov     [rbx], eax
0x180006c4d  mov     [rbx+8], rsi
0x180006c51  test    eax, eax
0x180006c53  jz      short loc_180006BF0
0x180006c55  mov     ecx, eax; cb
0x180006c57  call    cs:__imp_CoTaskMemAlloc
0x180006c5d  mov     [rbx+8], rax
0x180006c61  test    rax, rax
0x180006c64  jz      short loc_180006BF0
0x180006c66  mov     r8d, [rbx]; Size
0x180006c69  mov     rcx, rax; void *
0x180006c6c  mov     rdx, [rdi+8]; Src
0x180006c70  call    memcpy_0
0x180006c75  jmp     loc_180006BF0
0x180006c7a  movzx   eax, word ptr [r8]
0x180006c7e  mov     [rdx], ax
0x180006c81  jmp     loc_180006BF0
0x180006c86  mov     rcx, [rdx]; bstrString
0x180006c89  xor     esi, esi
0x180006c8b  cmp     [r8], rsi
0x180006c8e  jz      short loc_180006CA4
0x180006c90  call    cs:__imp_SysFreeString
0x180006c96  mov     rcx, [rdi]; psz
0x180006c99  call    cs:__imp_SysAllocString
0x180006c9f  mov     rsi, rax
0x180006ca2  jmp     short loc_180006CAA
0x180006ca4  call    cs:__imp_SysFreeString
0x180006caa  mov     [rbx], rsi
0x180006cad  jmp     loc_180006BF0
```
