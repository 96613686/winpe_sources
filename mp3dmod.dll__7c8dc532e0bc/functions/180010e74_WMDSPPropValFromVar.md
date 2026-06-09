# WMDSPPropValFromVar

- ea: `0x180010e74`
- end: `0x180010f65`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010640`
- `0x1800110c0`

## callees

- `0x180010e74`
- `0x1800114b1`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010f3a`
- `OLEAUT32!__imp_SysAllocString` at `0x180010f3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180010f30`
- `OLEAUT32!__imp_SysFreeString` at `0x180010f45`
- `OLEAUT32!__imp_SysFreeString` at `0x180010f30`
- `OLEAUT32!__imp_SysFreeString` at `0x180010f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010efc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010efc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ee7`

## pseudocode

```c
void __fastcall WMDSPPropValFromVar(__int64 a1, OLECHAR **a2)
{
  OLECHAR *v4; // rcx
  unsigned int v5; // eax
  OLECHAR *v6; // rax
  BSTR v7; // rsi
  bool v8; // zf
  OLECHAR *v9; // rcx

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *a2 = *(OLECHAR **)(a1 + 8);
      return;
    case 8:
      v7 = 0;
      v8 = *(_QWORD *)(a1 + 8) == 0;
      v9 = *a2;
      if ( v8 )
      {
        SysFreeString(v9);
      }
      else
      {
        SysFreeString(v9);
        v7 = SysAllocString(*(const OLECHAR **)(a1 + 8));
      }
      *a2 = v7;
      return;
    case 0xB:
      *(_WORD *)a2 = *(_WORD *)(a1 + 8);
      return;
    case 0x13:
LABEL_21:
      *(_DWORD *)a2 = *(_DWORD *)(a1 + 8);
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
  v4 = a2[1];
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *(_DWORD *)(a1 + 8);
  *(_DWORD *)a2 = v5;
  a2[1] = 0;
  if ( v5 )
  {
    v6 = (OLECHAR *)CoTaskMemAlloc(v5);
    a2[1] = v6;
    if ( v6 )
      memcpy_0(v6, *(const void **)(a1 + 16), *(unsigned int *)a2);
  }
}

```

## disassembly

```asm
0x180010e74  mov     [rsp+arg_0], rbx
0x180010e79  mov     [rsp+arg_8], rsi
0x180010e7e  push    rdi
0x180010e7f  sub     rsp, 20h
0x180010e83  movzx   r8d, word ptr [rcx]
0x180010e87  mov     rbx, rdx
0x180010e8a  mov     rdi, rcx
0x180010e8d  sub     r8d, 3
0x180010e91  jz      loc_180010F50
0x180010e97  sub     r8d, 1
0x180010e9b  jz      loc_180010F50
0x180010ea1  sub     r8d, 1
0x180010ea5  jz      short loc_180010ED3
0x180010ea7  sub     r8d, 3
0x180010eab  jz      short loc_180010F25
0x180010ead  sub     r8d, 3
0x180010eb1  jz      short loc_180010F1C
0x180010eb3  sub     r8d, 8
0x180010eb7  jz      loc_180010F50
0x180010ebd  sub     r8d, 1
0x180010ec1  jz      short loc_180010ED3
0x180010ec3  sub     r8d, 2Dh ; '-'
0x180010ec7  jz      short loc_180010EDC
0x180010ec9  cmp     r8d, 7
0x180010ecd  jnz     loc_180010F55
0x180010ed3  mov     rax, [rcx+8]
0x180010ed7  mov     [rdx], rax
0x180010eda  jmp     short loc_180010F55
0x180010edc  mov     rcx, [rdx+8]; pv
0x180010ee0  xor     esi, esi
0x180010ee2  test    rcx, rcx
0x180010ee5  jz      short loc_180010EED
0x180010ee7  call    cs:__imp_CoTaskMemFree
0x180010eed  mov     eax, [rdi+8]
0x180010ef0  mov     [rbx], eax
0x180010ef2  mov     [rbx+8], rsi
0x180010ef6  test    eax, eax
0x180010ef8  jz      short loc_180010F55
0x180010efa  mov     ecx, eax; cb
0x180010efc  call    cs:__imp_CoTaskMemAlloc
0x180010f02  mov     [rbx+8], rax
0x180010f06  test    rax, rax
0x180010f09  jz      short loc_180010F55
0x180010f0b  mov     r8d, [rbx]; Size
0x180010f0e  mov     rcx, rax; void *
0x180010f11  mov     rdx, [rdi+10h]; Src
0x180010f15  call    memcpy_0
0x180010f1a  jmp     short loc_180010F55
0x180010f1c  movzx   eax, word ptr [rcx+8]
0x180010f20  mov     [rdx], ax
0x180010f23  jmp     short loc_180010F55
0x180010f25  xor     esi, esi
0x180010f27  cmp     [rcx+8], rsi
0x180010f2b  mov     rcx, [rdx]; bstrString
0x180010f2e  jz      short loc_180010F45
0x180010f30  call    cs:__imp_SysFreeString
0x180010f36  mov     rcx, [rdi+8]; psz
0x180010f3a  call    cs:__imp_SysAllocString
0x180010f40  mov     rsi, rax
0x180010f43  jmp     short loc_180010F4B
0x180010f45  call    cs:__imp_SysFreeString
0x180010f4b  mov     [rbx], rsi
0x180010f4e  jmp     short loc_180010F55
0x180010f50  mov     eax, [rcx+8]
0x180010f53  mov     [rdx], eax
0x180010f55  mov     rbx, [rsp+28h+arg_0]
0x180010f5a  mov     rsi, [rsp+28h+arg_8]
0x180010f5f  add     rsp, 20h
0x180010f63  pop     rdi
0x180010f64  retn
```
