# WildcardBracketExpr_AddRange

- ea: `0x18001143c`
- end: `0x1800114f5`
- name: `WildcardBracketExpr_AddRange`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011ac4`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180007ea0`
- `0x18001143c`
- `0x1800137d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180011464`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180011464`

## string_xrefs

- `0x180011456`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall WildcardBracketExpr_AddRange(unsigned __int16 a1, unsigned __int16 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 v6; // rsi
  HMODULE ModuleHandleA; // rax
  __int64 v8; // rax

  v5 = a1;
  if ( a1 <= a2 )
  {
    v8 = PoolTls_Allocate(16);
    v6 = v8;
    if ( v8 )
    {
      *(_QWORD *)(v8 + 8) = *(_QWORD *)(a3 + 8);
      *(_DWORD *)v8 = 0;
      *(_WORD *)(v8 + 4) = v5;
      *(_WORD *)(v8 + 6) = a2;
      *(_QWORD *)(a3 + 8) = v8;
    }
    else
    {
      MI_ReportErrorDetails_OutOfMemory();
    }
  }
  else
  {
    v6 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2090, v5);
    MI_ReportErrorDetails_ForCustomError(1, (int)L"MI", 0, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x18001143c  push    rbx
0x18001143e  push    rbp
0x18001143f  push    rsi
0x180011440  push    rdi
0x180011441  sub     rsp, 48h
0x180011445  movzx   ebx, dx
0x180011448  mov     rbp, r8
0x18001144b  movzx   edi, cx
0x18001144e  cmp     di, bx
0x180011451  jbe     short loc_1800114B6
0x180011453  xorps   xmm0, xmm0
0x180011456  lea     rcx, ModuleName; "mpunits.dll"
0x18001145d  movups  [rsp+68h+var_38], xmm0
0x180011462  xor     esi, esi
0x180011464  call    cs:__imp_GetModuleHandleA
0x18001146a  mov     r9d, ebx
0x18001146d  mov     r8d, edi
0x180011470  mov     rcx, rax
0x180011473  mov     edx, 82Ah
0x180011478  call    _Intlstr_FormatString_FormatMessage
0x18001147d  mov     qword ptr [rsp+68h+var_38], rax
0x180011482  lea     r9, [rsp+68h+var_38]
0x180011487  mov     byte ptr [rsp+68h+var_38+8], 1
0x18001148c  lea     r8d, [rsi+5]
0x180011490  movaps  xmm0, [rsp+68h+var_38]
0x180011495  lea     rdx, aMi; "MI"
0x18001149c  mov     [rsp+68h+var_40], rsi; __int64
0x1800114a1  lea     ecx, [rsi+1]; int
0x1800114a4  movdqa  [rsp+68h+var_38], xmm0
0x1800114aa  mov     [rsp+68h+var_48], rsi; __int64
0x1800114af  call    MI_ReportErrorDetails_ForCustomError
0x1800114b4  jmp     short loc_1800114E9
0x1800114b6  mov     ecx, 10h
0x1800114bb  call    PoolTls_Allocate
0x1800114c0  mov     rsi, rax
0x1800114c3  test    rax, rax
0x1800114c6  jnz     short loc_1800114CF
0x1800114c8  call    MI_ReportErrorDetails_OutOfMemory
0x1800114cd  jmp     short loc_1800114E9
0x1800114cf  mov     rcx, [rbp+8]
0x1800114d3  mov     [rax+8], rcx
0x1800114d7  mov     dword ptr [rax], 0
0x1800114dd  mov     [rax+4], di
0x1800114e1  mov     [rax+6], bx
0x1800114e5  mov     [rbp+8], rax
0x1800114e9  mov     rax, rsi
0x1800114ec  add     rsp, 48h
0x1800114f0  pop     rdi
0x1800114f1  pop     rsi
0x1800114f2  pop     rbp
0x1800114f3  pop     rbx
0x1800114f4  retn
```
