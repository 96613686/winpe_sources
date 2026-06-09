# NextDataNode

- ea: `0x18000180c`
- end: `0x180001859`
- name: `NextDataNode`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fa4`
- `0x180002150`

## callees

- `0x18000180c`
- `0x180003e60`

## pseudocode

```c
__int64 __fastcall NextDataNode(__int64 a1, unsigned int a2)
{
  unsigned int AnyFreeDataNode; // eax
  unsigned int v4; // r9d
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // rdx

  AnyFreeDataNode = mwFindAnyFreeDataNode(a1, a2);
  v4 = AnyFreeDataNode;
  if ( AnyFreeDataNode == -1 )
    return 0;
  v6 = *(_QWORD *)(a1 + 104);
  v7 = 2LL * *(unsigned int *)(a1 + 120);
  result = v6 + 16LL * AnyFreeDataNode;
  *(_DWORD *)(result + 12) = *(_DWORD *)(v6 + 16LL * *(unsigned int *)(a1 + 120) + 12);
  *(_DWORD *)(v6 + 8 * v7 + 12) = v4;
  *(_DWORD *)(a1 + 120) = v4;
  *(_DWORD *)(a1 + 124) += *(_DWORD *)(v6 + 8 * v7 + 4);
  return result;
}

```

## disassembly

```asm
0x18000180c  push    rbx
0x18000180e  sub     rsp, 20h
0x180001812  mov     rbx, rcx
0x180001815  call    mwFindAnyFreeDataNode
0x18000181a  mov     r9d, eax
0x18000181d  cmp     eax, 0FFFFFFFFh
0x180001820  jnz     short loc_180001826
0x180001822  xor     eax, eax
0x180001824  jmp     short loc_180001853
0x180001826  mov     r8, [rbx+68h]
0x18000182a  mov     rax, r9
0x18000182d  mov     edx, [rbx+78h]
0x180001830  add     rdx, rdx
0x180001833  shl     rax, 4
0x180001837  add     rax, r8
0x18000183a  mov     ecx, [r8+rdx*8+0Ch]
0x18000183f  mov     [rax+0Ch], ecx
0x180001842  mov     [r8+rdx*8+0Ch], r9d
0x180001847  mov     [rbx+78h], r9d
0x18000184b  mov     ecx, [r8+rdx*8+4]
0x180001850  add     [rbx+7Ch], ecx
0x180001853  add     rsp, 20h
0x180001857  pop     rbx
0x180001858  retn
```
