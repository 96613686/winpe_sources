# QosLineCreate

- ea: `0x1400039d8`
- end: `0x140003aa7`
- name: `QosLineCreate`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001884`

## callees

- `0x1400023d0`
- `0x140002484`
- `0x1400039d8`
- `0x140004fe0`
- `0x140013600`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140003a16`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140003a16`

## pseudocode

```c
unsigned __int64 __fastcall QosLineCreate(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v9; // rbp
  ULONG CurrentProcessorNumber; // eax
  __int64 v11; // rdx
  unsigned __int64 CurrentTime; // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 result; // rax
  unsigned __int64 v17; // rdi

  memset(a1, 0, 0xD8u);
  v9 = -1;
  a1[4] = a4;
  a1[5] = a5;
  if ( a3 )
    v9 = a3;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v11) = 1;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v11, 0);
  *a1 = a2;
  if ( v9 != a1[1] )
  {
    a1[1] = v9;
    QosLineComputeControlInterval(a1);
    QosLineComputeBufferSizes(v13);
    v14 = a1[12];
    if ( !v14 || v14 == a1[1] )
      v15 = 0;
    else
      v15 = v14 * (unsigned __int64)*((unsigned int *)a1 + 29) / 0xF4240;
    a1[24] = v15;
  }
  result = CurrentTime / *((unsigned int *)a1 + 29);
  v17 = CurrentTime - CurrentTime % *((unsigned int *)a1 + 29);
  a1[20] = v17;
  a1[21] = v17;
  return result;
}

```

## disassembly

```asm
0x1400039d8  push    rbx
0x1400039da  push    rbp
0x1400039db  push    rsi
0x1400039dc  push    rdi
0x1400039dd  push    r14
0x1400039df  sub     rsp, 20h
0x1400039e3  mov     rdi, r8
0x1400039e6  mov     rbx, rdx
0x1400039e9  xor     edx, edx; Val
0x1400039eb  mov     r8d, 0D8h; Size
0x1400039f1  mov     rsi, r9
0x1400039f4  mov     r14, rcx
0x1400039f7  call    memset
0x1400039fc  mov     rax, [rsp+48h+arg_20]
0x140003a01  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140003a05  test    rdi, rdi
0x140003a08  mov     [r14+20h], rsi
0x140003a0c  mov     [r14+28h], rax
0x140003a10  cmovnz  rbp, rdi
0x140003a14  xor     ecx, ecx; ProcNumber
0x140003a16  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140003a1d  nop     dword ptr [rax+rax+00h]
0x140003a22  xor     r8d, r8d
0x140003a25  mov     dl, 1
0x140003a27  mov     ecx, eax
0x140003a29  call    QosTimerGetCurrentTime
0x140003a2e  mov     rdi, rax
0x140003a31  mov     [r14], rbx
0x140003a34  cmp     rbp, [r14+8]
0x140003a38  jz      short loc_140003A7E
0x140003a3a  mov     rcx, r14
0x140003a3d  mov     [r14+8], rbp
0x140003a41  call    QosLineComputeControlInterval
0x140003a46  call    QosLineComputeBufferSizes
0x140003a4b  mov     rax, [r14+60h]
0x140003a4f  test    rax, rax
0x140003a52  jz      short loc_140003A75
0x140003a54  cmp     rax, [r14+8]
0x140003a58  jz      short loc_140003A75
0x140003a5a  mov     ecx, [r14+74h]
0x140003a5e  imul    rcx, rax
0x140003a62  mov     rax, 431BDE82D7B634DBh
0x140003a6c  mul     rcx
0x140003a6f  shr     rdx, 12h
0x140003a73  jmp     short loc_140003A77
0x140003a75  xor     edx, edx
0x140003a77  mov     [r14+0C0h], rdx
0x140003a7e  mov     ecx, [r14+74h]
0x140003a82  xor     edx, edx
0x140003a84  mov     rax, rdi
0x140003a87  div     rcx
0x140003a8a  sub     rdi, rdx
0x140003a8d  mov     [r14+0A0h], rdi
0x140003a94  mov     [r14+0A8h], rdi
0x140003a9b  add     rsp, 20h
0x140003a9f  pop     r14
0x140003aa1  pop     rdi
0x140003aa2  pop     rsi
0x140003aa3  pop     rbp
0x140003aa4  pop     rbx
0x140003aa5  retn
```
