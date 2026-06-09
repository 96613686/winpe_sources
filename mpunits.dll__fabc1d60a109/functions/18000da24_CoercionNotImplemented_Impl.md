# CoercionNotImplemented_Impl

- ea: `0x18000da24`
- end: `0x18000dad3`
- name: `CoercionNotImplemented_Impl`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e4f0`
- `0x18000ee20`
- `0x18000f040`

## callees

- `0x180006e64`
- `0x180007c80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000da4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000da4b`

## string_xrefs

- `0x18000da39`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall CoercionNotImplemented_Impl(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax

  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2087, a2);
  MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x18000da24  mov     [rsp+arg_0], rbx
0x18000da29  mov     [rsp+arg_8], rsi
0x18000da2e  push    rdi
0x18000da2f  sub     rsp, 40h
0x18000da33  mov     rsi, rcx
0x18000da36  xorps   xmm0, xmm0
0x18000da39  lea     rcx, ModuleName; "mpunits.dll"
0x18000da40  mov     rbx, r8
0x18000da43  movups  [rsp+48h+var_18], xmm0
0x18000da48  mov     rdi, rdx
0x18000da4b  call    cs:__imp_GetModuleHandleA
0x18000da51  mov     r9, rbx
0x18000da54  mov     r8, rdi
0x18000da57  mov     rcx, rax
0x18000da5a  mov     edx, 827h
0x18000da5f  call    _Intlstr_FormatString_FormatMessage
0x18000da64  mov     qword ptr [rsp+48h+var_18], rax
0x18000da69  lea     r9, [rsp+48h+var_18]
0x18000da6e  mov     byte ptr [rsp+48h+var_18+8], 1
0x18000da73  lea     rdx, aMi; "MI"
0x18000da7a  movaps  xmm0, [rsp+48h+var_18]
0x18000da7f  mov     r8d, 5
0x18000da85  mov     [rsp+48h+var_20], 0; __int64
0x18000da8e  movdqa  [rsp+48h+var_18], xmm0
0x18000da94  mov     [rsp+48h+var_28], 0; __int64
0x18000da9d  lea     ecx, [r8-1]; int
0x18000daa1  call    MI_ReportErrorDetails_ForCustomError
0x18000daa6  mov     rbx, [rsp+48h+arg_0]
0x18000daab  mov     eax, 0FFh
0x18000dab0  and     eax, 0FFFFFFFEh
0x18000dab3  xor     edx, edx
0x18000dab5  xor     ecx, ecx
0x18000dab7  mov     [rsi+4], edx
0x18000daba  or      eax, 0FEh
0x18000dabf  mov     [rsi+8], rcx
0x18000dac3  mov     [rsi], eax
0x18000dac5  mov     rax, rsi
0x18000dac8  mov     rsi, [rsp+48h+arg_8]
0x18000dacd  add     rsp, 40h
0x18000dad1  pop     rdi
0x18000dad2  retn
```
