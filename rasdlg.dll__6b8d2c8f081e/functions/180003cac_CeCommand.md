# CeCommand

- ea: `0x180003cac`
- end: `0x180003d7b`
- name: `CeCommand`
- size: `207`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d90`

## callees

- `0x180003cac`
- `0x180004048`
- `0x180011be0`
- `0x180011cec`

## import_xrefs

- `USER32!EndDialog` at `0x180003d60`
- `USER32!EndDialog` at `0x180003d60`
- `rtutils!TracePrintfExA` at `0x180003ceb`
- `rtutils!TracePrintfExA` at `0x180003d47`
- `rtutils!TracePrintfExA` at `0x180003ceb`
- `rtutils!TracePrintfExA` at `0x180003d47`

## string_xrefs

- `0x180003cd8`: `CeCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall CeCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  DWORD v6; // ecx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  INT_PTR v12; // rdx

  v6 = g_dwTraceId;
  v7 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "CeCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v12 = (int)CeSave(a1);
LABEL_14:
    EndDialog(*(HWND *)(a1 + 8), v12);
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v12 = 0;
    goto LABEL_14;
  }
  v10 = v9 - 1046;
  if ( !v10 )
    return (unsigned int)CuDialingRulesCbHandler(a1 + 96) != 0;
  return v10 == 6 && (unsigned int)CuCountryCodeLbHandler(a1 + 96, a2);
}

```

## disassembly

```asm
0x180003cac  mov     [rsp+arg_0], rbx
0x180003cb1  mov     [rsp+arg_8], rsi
0x180003cb6  push    rdi
0x180003cb7  sub     rsp, 30h
0x180003cbb  mov     rdi, rcx
0x180003cbe  movzx   esi, dx
0x180003cc1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180003cc7  mov     rax, r9
0x180003cca  movzx   ebx, r8w
0x180003cce  cmp     ecx, 0FFFFFFFFh
0x180003cd1  jz      short loc_180003CF7
0x180003cd3  mov     [rsp+38h+var_10], rax
0x180003cd8  lea     r8, aCecommandNDIDC; "CeCommand(n=%d,i=%d,c=$%x)"
0x180003cdf  mov     r9d, esi
0x180003ce2  mov     [rsp+38h+var_18], ebx
0x180003ce6  mov     edx, 0Ch; dwFlags
0x180003ceb  call    cs:__imp_TracePrintfExA
0x180003cf1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180003cf7  sub     ebx, 1
0x180003cfa  jz      short loc_180003D51
0x180003cfc  sub     ebx, 1
0x180003cff  jz      short loc_180003D36
0x180003d01  sub     ebx, 416h
0x180003d07  jz      short loc_180003D22
0x180003d09  cmp     ebx, 6
0x180003d0c  jnz     short loc_180003D1E
0x180003d0e  lea     rcx, [rdi+60h]
0x180003d12  movzx   edx, si
0x180003d15  call    CuCountryCodeLbHandler
0x180003d1a  test    eax, eax
0x180003d1c  jnz     short loc_180003D66
0x180003d1e  xor     eax, eax
0x180003d20  jmp     short loc_180003D6B
0x180003d22  lea     rcx, [rdi+60h]
0x180003d26  call    CuDialingRulesCbHandler
0x180003d2b  xor     ecx, ecx
0x180003d2d  test    eax, eax
0x180003d2f  setnz   cl
0x180003d32  mov     eax, ecx
0x180003d34  jmp     short loc_180003D6B
0x180003d36  cmp     ecx, 0FFFFFFFFh
0x180003d39  jz      short loc_180003D4D
0x180003d3b  lea     r8, aCancelPressed; "Cancel pressed"
0x180003d42  mov     edx, 0Ch; dwFlags
0x180003d47  call    cs:__imp_TracePrintfExA
0x180003d4d  xor     edx, edx
0x180003d4f  jmp     short loc_180003D5C
0x180003d51  mov     rcx, rdi
0x180003d54  call    CeSave
0x180003d59  movsxd  rdx, eax; nResult
0x180003d5c  mov     rcx, [rdi+8]; hDlg
0x180003d60  call    cs:__imp_EndDialog
0x180003d66  mov     eax, 1
0x180003d6b  mov     rbx, [rsp+38h+arg_0]
0x180003d70  mov     rsi, [rsp+38h+arg_8]
0x180003d75  add     rsp, 30h
0x180003d79  pop     rdi
0x180003d7a  retn
```
