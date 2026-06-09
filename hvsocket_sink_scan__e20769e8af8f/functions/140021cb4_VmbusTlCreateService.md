# VmbusTlCreateService

- ea: `0x140021cb4`
- end: `0x140021d9c`
- name: `VmbusTlCreateService`
- size: `232`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140021da4`
- `0x1400222b0`
- `0x140022634`

## callees

- `0x140001350`
- `0x1400017ec`
- `0x140009cf8`
- `0x140021cb4`

## string_xrefs

- `0x140021cf7`: `Failed to create service.`
- `0x140021d06`: `VmbusTlCreateService`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateService(int **a1)
{
  int v2; // eax
  unsigned int v3; // edi
  int *v4; // rbx
  int *v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  v2 = VmbusTlCreateObject(5, 0x148u, &v6);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = v6;
    *((_QWORD *)v6 + 10) = VmbusTlServiceDestructor;
    *((_BYTE *)v4 + 152) = 0;
    *((_QWORD *)v4 + 18) = 0;
    *((_QWORD *)v4 + 17) = 0;
    v4[40] = 0;
    *((_QWORD *)v4 + 40) = v4 + 78;
    *((_QWORD *)v4 + 39) = v4 + 78;
    *((_QWORD *)v4 + 37) = v4 + 72;
    *((_QWORD *)v4 + 36) = v4 + 72;
    *((_QWORD *)v4 + 35) = v4 + 68;
    *((_QWORD *)v4 + 34) = v4 + 68;
    VmbusTlInitializeObjectTable((PVOID)0x694C6353, (PRTL_AVL_TABLE)(v4 + 42));
    *a1 = v4;
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceError("VmbusTlCreateService", 354, (unsigned int)v2, "Failed to create service.");
  }
  return v3;
}

```

## disassembly

```asm
0x140021cb4  mov     rax, rsp
0x140021cb7  mov     [rax+8], rbx
0x140021cbb  mov     [rax+18h], rsi
0x140021cbf  push    rdi
0x140021cc0  sub     rsp, 20h
0x140021cc4  mov     rsi, rcx
0x140021cc7  mov     qword ptr [rax+10h], 0
0x140021ccf  mov     ecx, 5
0x140021cd4  lea     r8, [rax+10h]
0x140021cd8  mov     edx, 148h
0x140021cdd  call    VmbusTlCreateObject
0x140021ce2  mov     edi, eax
0x140021ce4  test    eax, eax
0x140021ce6  jns     short loc_140021D14
0x140021ce8  mov     ecx, cs:dword_140013058
0x140021cee  cmp     ecx, 2
0x140021cf1  jbe     loc_140021D89
0x140021cf7  lea     r9, aFailedToCreate_1; "Failed to create service."
0x140021cfe  mov     r8d, eax
0x140021d01  mov     edx, 162h
0x140021d06  lea     rcx, aVmbustlcreates; "VmbusTlCreateService"
0x140021d0d  call    HvsocketTraceError
0x140021d12  jmp     short loc_140021D89
0x140021d14  mov     rbx, [rsp+28h+arg_8]
0x140021d19  lea     rax, VmbusTlServiceDestructor
0x140021d20  mov     ecx, 694C6353h; TableContext
0x140021d25  mov     [rbx+50h], rax
0x140021d29  lea     rdx, [rbx+0A8h]; Table
0x140021d30  mov     byte ptr [rbx+98h], 0
0x140021d37  lea     rax, [rbx+138h]
0x140021d3e  mov     qword ptr [rbx+90h], 0
0x140021d49  mov     qword ptr [rbx+88h], 0
0x140021d54  mov     dword ptr [rbx+0A0h], 0
0x140021d5e  mov     [rax+8], rax
0x140021d62  mov     [rax], rax
0x140021d65  lea     rax, [rbx+120h]
0x140021d6c  mov     [rax+8], rax
0x140021d70  mov     [rax], rax
0x140021d73  lea     rax, [rbx+110h]
0x140021d7a  mov     [rax+8], rax
0x140021d7e  mov     [rax], rax
0x140021d81  call    VmbusTlInitializeObjectTable
0x140021d86  mov     [rsi], rbx
0x140021d89  mov     rbx, [rsp+28h+arg_0]
0x140021d8e  mov     eax, edi
0x140021d90  mov     rsi, [rsp+28h+arg_10]
0x140021d95  add     rsp, 20h
0x140021d99  pop     rdi
0x140021d9a  retn
```
