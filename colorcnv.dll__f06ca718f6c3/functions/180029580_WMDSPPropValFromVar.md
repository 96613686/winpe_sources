# WMDSPPropValFromVar

- ea: `0x180029580`
- end: `0x180029671`
- name: `WMDSPPropValFromVar`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800291b0`
- `0x1800297c0`

## callees

- `0x180029580`
- `0x180029fc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029646`
- `OLEAUT32!__imp_SysAllocString` at `0x180029646`
- `OLEAUT32!__imp_SysFreeString` at `0x18002963c`
- `OLEAUT32!__imp_SysFreeString` at `0x180029651`
- `OLEAUT32!__imp_SysFreeString` at `0x18002963c`
- `OLEAUT32!__imp_SysFreeString` at `0x180029651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295f3`

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
0x180029580  mov     [rsp+arg_0], rbx
0x180029585  mov     [rsp+arg_8], rsi
0x18002958a  push    rdi
0x18002958b  sub     rsp, 20h
0x18002958f  movzx   r8d, word ptr [rcx]
0x180029593  mov     rbx, rdx
0x180029596  mov     rdi, rcx
0x180029599  sub     r8d, 3
0x18002959d  jz      loc_18002965C
0x1800295a3  sub     r8d, 1
0x1800295a7  jz      loc_18002965C
0x1800295ad  sub     r8d, 1
0x1800295b1  jz      short loc_1800295DF
0x1800295b3  sub     r8d, 3
0x1800295b7  jz      short loc_180029631
0x1800295b9  sub     r8d, 3
0x1800295bd  jz      short loc_180029628
0x1800295bf  sub     r8d, 8
0x1800295c3  jz      loc_18002965C
0x1800295c9  sub     r8d, 1
0x1800295cd  jz      short loc_1800295DF
0x1800295cf  sub     r8d, 2Dh ; '-'
0x1800295d3  jz      short loc_1800295E8
0x1800295d5  cmp     r8d, 7
0x1800295d9  jnz     loc_180029661
0x1800295df  mov     rax, [rcx+8]
0x1800295e3  mov     [rdx], rax
0x1800295e6  jmp     short loc_180029661
0x1800295e8  mov     rcx, [rdx+8]; pv
0x1800295ec  xor     esi, esi
0x1800295ee  test    rcx, rcx
0x1800295f1  jz      short loc_1800295F9
0x1800295f3  call    cs:__imp_CoTaskMemFree
0x1800295f9  mov     eax, [rdi+8]
0x1800295fc  mov     [rbx], eax
0x1800295fe  mov     [rbx+8], rsi
0x180029602  test    eax, eax
0x180029604  jz      short loc_180029661
0x180029606  mov     ecx, eax; cb
0x180029608  call    cs:__imp_CoTaskMemAlloc
0x18002960e  mov     [rbx+8], rax
0x180029612  test    rax, rax
0x180029615  jz      short loc_180029661
0x180029617  mov     r8d, [rbx]; Size
0x18002961a  mov     rcx, rax; void *
0x18002961d  mov     rdx, [rdi+10h]; Src
0x180029621  call    memcpy_0
0x180029626  jmp     short loc_180029661
0x180029628  movzx   eax, word ptr [rcx+8]
0x18002962c  mov     [rdx], ax
0x18002962f  jmp     short loc_180029661
0x180029631  xor     esi, esi
0x180029633  cmp     [rcx+8], rsi
0x180029637  mov     rcx, [rdx]; bstrString
0x18002963a  jz      short loc_180029651
0x18002963c  call    cs:__imp_SysFreeString
0x180029642  mov     rcx, [rdi+8]; psz
0x180029646  call    cs:__imp_SysAllocString
0x18002964c  mov     rsi, rax
0x18002964f  jmp     short loc_180029657
0x180029651  call    cs:__imp_SysFreeString
0x180029657  mov     [rbx], rsi
0x18002965a  jmp     short loc_180029661
0x18002965c  mov     eax, [rcx+8]
0x18002965f  mov     [rdx], eax
0x180029661  mov     rbx, [rsp+28h+arg_0]
0x180029666  mov     rsi, [rsp+28h+arg_8]
0x18002966b  add     rsp, 20h
0x18002966f  pop     rdi
0x180029670  retn
```
