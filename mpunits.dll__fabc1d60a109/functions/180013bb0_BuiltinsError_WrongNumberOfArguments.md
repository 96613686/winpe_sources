# BuiltinsError_WrongNumberOfArguments

- ea: `0x180013bb0`
- end: `0x180013c4e`
- name: `BuiltinsError_WrongNumberOfArguments`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017b80`
- `0x180018830`

## callees

- `0x180006e64`
- `0x180007c80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180013bce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180013bce`

## string_xrefs

- `0x180013bc0`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BuiltinsError_WrongNumberOfArguments(__int64 a1, unsigned int a2)
{
  HMODULE ModuleHandleA; // rax

  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2068, a2);
  MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x180013bb0  mov     [rsp+arg_0], rbx
0x180013bb5  push    rdi
0x180013bb6  sub     rsp, 40h
0x180013bba  mov     rdi, rcx
0x180013bbd  xorps   xmm0, xmm0
0x180013bc0  lea     rcx, ModuleName; "mpunits.dll"
0x180013bc7  mov     ebx, edx
0x180013bc9  movups  [rsp+48h+var_18], xmm0
0x180013bce  call    cs:__imp_GetModuleHandleA
0x180013bd4  mov     r8d, ebx
0x180013bd7  mov     edx, 814h
0x180013bdc  mov     rcx, rax
0x180013bdf  call    _Intlstr_FormatString_FormatMessage
0x180013be4  mov     qword ptr [rsp+48h+var_18], rax
0x180013be9  lea     r9, [rsp+48h+var_18]
0x180013bee  mov     byte ptr [rsp+48h+var_18+8], 1
0x180013bf3  lea     rdx, aMi; "MI"
0x180013bfa  movaps  xmm0, [rsp+48h+var_18]
0x180013bff  mov     r8d, 5
0x180013c05  mov     [rsp+48h+var_20], 0; __int64
0x180013c0e  movdqa  [rsp+48h+var_18], xmm0
0x180013c14  mov     [rsp+48h+var_28], 0; __int64
0x180013c1d  lea     ecx, [r8-1]; int
0x180013c21  call    MI_ReportErrorDetails_ForCustomError
0x180013c26  mov     rbx, [rsp+48h+arg_0]
0x180013c2b  mov     eax, 0FFh
0x180013c30  and     eax, 0FFFFFFFEh
0x180013c33  xor     edx, edx
0x180013c35  xor     ecx, ecx
0x180013c37  mov     [rdi+4], edx
0x180013c3a  or      eax, 0FEh
0x180013c3f  mov     [rdi+8], rcx
0x180013c43  mov     [rdi], eax
0x180013c45  mov     rax, rdi
0x180013c48  add     rsp, 40h
0x180013c4c  pop     rdi
0x180013c4d  retn
```
