# QosLineQueryQueueFeedback

- ea: `0x140011a34`
- end: `0x140011a84`
- name: `QosLineQueryQueueFeedback`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140003ab0`
- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000cce0`

## pseudocode

```c
__int64 __fastcall QosLineQueryQueueFeedback(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // eax
  __int64 result; // rax

  ++*(_DWORD *)(a1 + 152);
  *(_DWORD *)(a1 + 156) += *a3;
  v3 = *(_DWORD *)(a1 + 112);
  if ( v3 <= *a3 )
    v3 = *a3;
  *(_DWORD *)(a1 + 112) = v3;
  a3[2] = *(_DWORD *)(a1 + 120);
  a3[3] = *(_DWORD *)(a1 + 108);
  *((_QWORD *)a3 + 3) = *(_QWORD *)(a1 + 176);
  a3[5] = *(_DWORD *)(a1 + 116);
  *((_QWORD *)a3 + 4) = *(_QWORD *)(a1 + 192);
  result = *(unsigned int *)(a1 + 112);
  a3[4] = result;
  return result;
}

```

## disassembly

```asm
0x140011a34  inc     dword ptr [rcx+98h]
0x140011a3a  mov     eax, [r8]
0x140011a3d  add     [rcx+9Ch], eax
0x140011a43  mov     eax, [rcx+70h]
0x140011a46  mov     edx, [r8]
0x140011a49  cmp     eax, edx
0x140011a4b  cmovbe  eax, edx
0x140011a4e  mov     [rcx+70h], eax
0x140011a51  mov     eax, [rcx+78h]
0x140011a54  mov     [r8+8], eax
0x140011a58  mov     eax, [rcx+6Ch]
0x140011a5b  mov     [r8+0Ch], eax
0x140011a5f  mov     rax, [rcx+0B0h]
0x140011a66  mov     [r8+18h], rax
0x140011a6a  mov     eax, [rcx+74h]
0x140011a6d  mov     [r8+14h], eax
0x140011a71  mov     rax, [rcx+0C0h]
0x140011a78  mov     [r8+20h], rax
0x140011a7c  mov     eax, [rcx+70h]
0x140011a7f  mov     [r8+10h], eax
0x140011a83  retn
```
