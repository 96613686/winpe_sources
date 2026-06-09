# CsrAllocateProcess

- ea: `0x180005010`
- end: `0x1800050ad`
- name: `CsrAllocateProcess`
- size: `157`
- prototype: `_DWORD *()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004f60`
- `0x180009370`

## callees

- `0x180005010`
- `0x18000ab61`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000503d`
- `ntdll!RtlAllocateHeap` at `0x18000503d`

## pseudocode

```c
_DWORD *CsrAllocateProcess()
{
  unsigned int v0; // edi
  _DWORD *result; // rax
  _DWORD *v2; // rbx
  int v3; // eax

  v0 = CsrTotalPerProcessDataLength + 192;
  result = RtlAllocateHeap(CsrHeap, CsrBaseTag + 786432, (unsigned int)(CsrTotalPerProcessDataLength + 192));
  v2 = result;
  if ( result )
  {
    memset_0(result, 0, v0);
    v3 = ProcessSequenceCount;
    v2[22] = ProcessSequenceCount;
    ProcessSequenceCount = v3 + 1;
    if ( (unsigned int)(v3 + 1) < 5 )
      ProcessSequenceCount = 5;
    v2[25] = 1;
    *((_QWORD *)v2 + 5) = v2 + 8;
    *((_QWORD *)v2 + 4) = v2 + 8;
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180005010  mov     [rsp+arg_0], rbx
0x180005015  push    rdi
0x180005016  sub     rsp, 20h
0x18000501a  mov     eax, cs:CsrTotalPerProcessDataLength
0x180005020  mov     edx, cs:CsrBaseTag
0x180005026  add     eax, 0C0h
0x18000502b  mov     rcx, cs:CsrHeap; HeapHandle
0x180005032  add     edx, 0C0000h; Flags
0x180005038  mov     r8d, eax; Size
0x18000503b  mov     edi, eax
0x18000503d  call    cs:__imp_RtlAllocateHeap
0x180005044  nop     dword ptr [rax+rax+00h]
0x180005049  mov     rbx, rax
0x18000504c  test    rax, rax
0x18000504f  jz      short loc_180005095
0x180005051  mov     r8d, edi; Size
0x180005054  xor     edx, edx; Val
0x180005056  mov     rcx, rax; void *
0x180005059  call    memset_0
0x18000505e  mov     eax, cs:ProcessSequenceCount
0x180005064  mov     [rbx+58h], eax
0x180005067  inc     eax
0x180005069  mov     cs:ProcessSequenceCount, eax
0x18000506f  cmp     eax, 5
0x180005072  jb      short loc_1800050A1
0x180005074  lea     rax, [rbx+20h]
0x180005078  mov     dword ptr [rbx+64h], 1
0x18000507f  mov     [rax+8], rax
0x180005083  mov     [rax], rax
0x180005086  mov     rax, rbx
0x180005089  mov     rbx, [rsp+28h+arg_0]
0x18000508e  add     rsp, 20h
0x180005092  pop     rdi
0x180005093  retn
0x180005095  mov     rbx, [rsp+28h+arg_0]
0x18000509a  add     rsp, 20h
0x18000509e  pop     rdi
0x18000509f  retn
0x1800050a1  mov     cs:ProcessSequenceCount, 5
0x1800050ab  jmp     short loc_180005074
```
