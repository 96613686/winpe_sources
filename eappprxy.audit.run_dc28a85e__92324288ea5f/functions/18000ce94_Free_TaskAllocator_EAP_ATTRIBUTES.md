# Free<TaskAllocator>(_EAP_ATTRIBUTES &)

- ea: `0x18000ce94`
- end: `0x18000cef8`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf60`
- `0x18000cf94`

## callees

- `0x18000ce94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ced5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ced5`

## pseudocode

```c
void __fastcall Free<TaskAllocator>(unsigned int *a1)
{
  unsigned __int64 i; // rsi

  for ( i = 0; i < *a1; CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 1) + 16 * i++ + 8)) )
    ;
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  *(_OWORD *)a1 = 0;
}

```

## disassembly

```asm
0x18000ce94  mov     [rsp+arg_0], rbx
0x18000ce99  mov     [rsp+arg_8], rsi
0x18000ce9e  push    rdi
0x18000ce9f  sub     rsp, 20h
0x18000cea3  xor     esi, esi
0x18000cea5  mov     rdi, rcx
0x18000cea8  cmp     [rcx], esi
0x18000ceaa  jbe     short loc_18000CED1
0x18000ceac  mov     rcx, [rdi+8]
0x18000ceb0  mov     rax, rsi
0x18000ceb3  add     rax, rax
0x18000ceb6  mov     rcx, [rcx+rax*8+8]; pv
0x18000cebb  call    cs:__imp_CoTaskMemFree
0x18000cec2  nop     dword ptr [rax+rax+00h]
0x18000cec7  mov     eax, [rdi]
0x18000cec9  inc     rsi
0x18000cecc  cmp     rsi, rax
0x18000cecf  jb      short loc_18000CEAC
0x18000ced1  mov     rcx, [rdi+8]; pv
0x18000ced5  call    cs:__imp_CoTaskMemFree
0x18000cedc  nop     dword ptr [rax+rax+00h]
0x18000cee1  mov     rbx, [rsp+28h+arg_0]
0x18000cee6  xorps   xmm0, xmm0
0x18000cee9  mov     rsi, [rsp+28h+arg_8]
0x18000ceee  movups  xmmword ptr [rdi], xmm0
0x18000cef1  add     rsp, 20h
0x18000cef5  pop     rdi
0x18000cef6  retn
```
