# PipelineExecutionContext_PrepareForDeleteInstance

- ea: `0x18003edc0`
- end: `0x18003ee5b`
- name: `PipelineExecutionContext_PrepareForDeleteInstance`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18003edc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003edf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003edf2`

## string_xrefs

- `0x18003ede6`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall PipelineExecutionContext_PrepareForDeleteInstance(signed __int64 *a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax

  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 24), *a1, 0) )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2134, L"MSFT_PipelineExecution");
    MI_ReportErrorDetails_ForCustomError(6, (int)L"MI", 0, 0);
    return 6;
  }
  else
  {
    *(_QWORD *)(a2 + 32) = a1[1];
    return 0;
  }
}

```

## disassembly

```asm
0x18003edc0  push    rbx
0x18003edc2  sub     rsp, 40h
0x18003edc6  mov     r8, [rcx]
0x18003edc9  xor     eax, eax
0x18003edcb  lock cmpxchg [rdx+18h], r8
0x18003edd1  jnz     short loc_18003EDDF
0x18003edd3  mov     rax, [rcx+8]
0x18003edd7  mov     [rdx+20h], rax
0x18003eddb  xor     eax, eax
0x18003eddd  jmp     short loc_18003EE55
0x18003eddf  mov     rbx, [rcx+10h]
0x18003ede3  xorps   xmm0, xmm0
0x18003ede6  lea     rcx, ModuleName; "mpunits.dll"
0x18003eded  movups  [rsp+48h+var_18], xmm0
0x18003edf2  call    cs:__imp_GetModuleHandleA
0x18003edf8  mov     r9, rbx
0x18003edfb  lea     r8, aMsftPipelineex; "MSFT_PipelineExecution"
0x18003ee02  mov     rcx, rax
0x18003ee05  mov     edx, 856h
0x18003ee0a  call    _Intlstr_FormatString_FormatMessage
0x18003ee0f  mov     qword ptr [rsp+48h+var_18], rax
0x18003ee14  lea     r9, [rsp+48h+var_18]
0x18003ee19  mov     byte ptr [rsp+48h+var_18+8], 1
0x18003ee1e  lea     rdx, aMi; "MI"
0x18003ee25  movaps  xmm0, [rsp+48h+var_18]
0x18003ee2a  mov     r8d, 0Dh
0x18003ee30  mov     [rsp+48h+var_20], 0; __int64
0x18003ee39  movdqa  [rsp+48h+var_18], xmm0
0x18003ee3f  mov     [rsp+48h+var_28], 0; __int64
0x18003ee48  lea     ebx, [r8-7]
0x18003ee4c  mov     ecx, ebx; int
0x18003ee4e  call    MI_ReportErrorDetails_ForCustomError
0x18003ee53  mov     eax, ebx
0x18003ee55  add     rsp, 40h
0x18003ee59  pop     rbx
0x18003ee5a  retn
```
