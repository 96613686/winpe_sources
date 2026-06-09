# QosTimerGetCurrentTime

- ea: `0x140004fe0`
- end: `0x140005164`
- name: `QosTimerGetCurrentTime`
- size: `388`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039d8`
- `0x140003ab0`
- `0x140004c58`
- `0x140009860`
- `0x14000b868`
- `0x14000bcb4`
- `0x14000bdf4`
- `0x14000cce0`
- `0x1400101c0`
- `0x140011904`
- `0x140011fa8`
- `0x1400120f8`
- `0x140012918`

## callees

- `0x140004fe0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140005107`
- `ntoskrnl!KfRaiseIrql` at `0x140005107`
- `ntoskrnl!KeLowerIrql` at `0x140005153`
- `ntoskrnl!KeLowerIrql` at `0x140005153`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005119`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005119`
- `HAL!KeQueryPerformanceCounter` at `0x140005055`
- `HAL!KeQueryPerformanceCounter` at `0x140005055`

## pseudocode

```c
__int64 __fastcall QosTimerGetCurrentTime(ULONG CurrentProcessorNumber, char a2, char a3)
{
  KIRQL v3; // r15
  unsigned __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rbx
  LARGE_INTEGER v11; // rax
  union _LARGE_INTEGER v12; // r8
  LARGE_INTEGER v13; // r9
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int8 v16; // al
  unsigned __int8 v17; // al
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  if ( !a3 )
  {
    v3 = KfRaiseIrql(2u);
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  }
  v7 = *(_QWORD *)QosgTimerTable + ((unsigned __int64)CurrentProcessorNumber << 7);
  v8 = MEMORY[0xFFFFF78000000008];
  if ( a2 || MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v7 + 8) )
  {
    PerformanceFrequency.QuadPart = 0;
    v11 = KeQueryPerformanceCounter(&PerformanceFrequency);
    v12 = PerformanceFrequency;
    v13 = v11;
    v14 = *(unsigned __int8 *)(v7 + 112);
    v15 = ((1000000 * HIDWORD(v11.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
        + (1000000LL * v11.LowPart
         + ((1000000 * HIDWORD(v11.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
        / PerformanceFrequency.QuadPart;
    if ( (_BYTE)v14 )
      v16 = v14 - 1;
    else
      v16 = 2;
    if ( (__int64)(*(_QWORD *)(v7 + 8LL * v16 + 64) - v15) > 0 )
    {
      *(_QWORD *)(v7 + 8 * v14 + 16) = *(_QWORD *)(v7 + 8LL * v16 + 16);
      *(_QWORD *)(v7 + 8 * v14 + 40) = *(_QWORD *)(v7 + 8LL * v16 + 40);
      *(_QWORD *)(v7 + 8 * v14 + 64) = *(_QWORD *)(v7 + 8LL * v16 + 64);
      v15 = *(_QWORD *)(v7 + 8LL * v16 + 64);
    }
    else
    {
      *(LARGE_INTEGER *)(v7 + 8 * v14 + 16) = v13;
      *(union _LARGE_INTEGER *)(v7 + 8 * v14 + 40) = v12;
      *(_QWORD *)(v7 + 8 * v14 + 64) = v15;
    }
    *(_QWORD *)(v7 + 8 * v14 + 88) = v8;
    v17 = *(_BYTE *)(v7 + 112) + 1;
    *(_QWORD *)v7 = v15;
    *(_QWORD *)(v7 + 8) = v8;
    *(_BYTE *)(v7 + 112) = v17 % 3u;
  }
  v9 = *(_QWORD *)v7;
  if ( !a3 )
    KeLowerIrql(v3);
  return v9;
}

```

## disassembly

```asm
0x140004fe0  push    rbx
0x140004fe2  push    rbp
0x140004fe3  push    rsi
0x140004fe4  push    rdi
0x140004fe5  push    r14
0x140004fe7  push    r15
0x140004fe9  sub     rsp, 28h
0x140004fed  xor     r15b, r15b
0x140004ff0  movzx   esi, r8b
0x140004ff4  movzx   ebp, dl
0x140004ff7  mov     eax, ecx
0x140004ff9  test    r8b, r8b
0x140004ffc  jz      loc_140005105
0x140005002  mov     rcx, cs:QosgTimerTable
0x140005009  mov     rbx, 0FFFFF78000000008h
0x140005013  mov     edi, eax
0x140005015  shl     rdi, 7
0x140005019  add     rdi, [rcx]
0x14000501c  mov     rbx, [rbx]
0x14000501f  test    bpl, bpl
0x140005022  jnz     short loc_140005047
0x140005024  cmp     rbx, [rdi+8]
0x140005028  jnz     short loc_140005047
0x14000502a  mov     rbx, [rdi]
0x14000502d  test    sil, sil
0x140005030  jz      loc_14000514F
0x140005036  mov     rax, rbx
0x140005039  add     rsp, 28h
0x14000503d  pop     r15
0x14000503f  pop     r14
0x140005041  pop     rdi
0x140005042  pop     rsi
0x140005043  pop     rbp
0x140005044  pop     rbx
0x140005045  retn
0x140005047  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14000504c  mov     qword ptr [rsp+58h+PerformanceFrequency], 0
0x140005055  call    cs:__imp_KeQueryPerformanceCounter
0x14000505c  nop     dword ptr [rax+rax+00h]
0x140005061  mov     r8, qword ptr [rsp+58h+PerformanceFrequency]
0x140005066  xor     edx, edx
0x140005068  mov     r9, rax
0x14000506b  shr     rax, 20h
0x14000506f  imul    r10, rax, 0F4240h
0x140005076  mov     ecx, r9d
0x140005079  mov     rax, r10
0x14000507c  div     r8
0x14000507f  mov     rax, rdx
0x140005082  shl     rax, 20h
0x140005086  imul    rdx, rcx, 0F4240h
0x14000508d  add     rax, rdx
0x140005090  xor     edx, edx
0x140005092  div     r8
0x140005095  xor     edx, edx
0x140005097  mov     rcx, rax
0x14000509a  mov     rax, r10
0x14000509d  div     r8
0x1400050a0  movzx   edx, byte ptr [rdi+70h]
0x1400050a4  shl     rax, 20h
0x1400050a8  add     rcx, rax
0x1400050ab  test    dl, dl
0x1400050ad  jz      short loc_140005101
0x1400050af  lea     eax, [rdx-1]
0x1400050b2  movzx   r10d, al
0x1400050b6  mov     rax, [rdi+r10*8+40h]
0x1400050bb  sub     rax, rcx
0x1400050be  test    rax, rax
0x1400050c1  jg      short loc_14000512A
0x1400050c3  mov     [rdi+rdx*8+10h], r9
0x1400050c8  mov     [rdi+rdx*8+28h], r8
0x1400050cd  mov     [rdi+rdx*8+40h], rcx
0x1400050d2  mov     [rdi+rdx*8+58h], rbx
0x1400050d7  movzx   eax, byte ptr [rdi+70h]
0x1400050db  inc     al
0x1400050dd  mov     [rdi], rcx
0x1400050e0  movzx   r8d, al
0x1400050e4  mov     eax, 0AAAAAAABh
0x1400050e9  mul     r8d
0x1400050ec  mov     [rdi+8], rbx
0x1400050f0  shr     edx, 1
0x1400050f2  lea     eax, [rdx+rdx*2]
0x1400050f5  sub     r8d, eax
0x1400050f8  mov     [rdi+70h], r8b
0x1400050fc  jmp     loc_14000502A
0x140005101  mov     al, 2
0x140005103  jmp     short loc_1400050B2
0x140005105  mov     cl, 2; NewIrql
0x140005107  call    cs:__imp_KfRaiseIrql
0x14000510e  nop     dword ptr [rax+rax+00h]
0x140005113  xor     ecx, ecx; ProcNumber
0x140005115  movzx   r15d, al
0x140005119  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140005120  nop     dword ptr [rax+rax+00h]
0x140005125  jmp     loc_140005002
0x14000512a  mov     rax, [rdi+r10*8+10h]
0x14000512f  mov     [rdi+rdx*8+10h], rax
0x140005134  mov     rax, [rdi+r10*8+28h]
0x140005139  mov     [rdi+rdx*8+28h], rax
0x14000513e  mov     rax, [rdi+r10*8+40h]
0x140005143  mov     [rdi+rdx*8+40h], rax
0x140005148  mov     rcx, [rdi+r10*8+40h]
0x14000514d  jmp     short loc_1400050D2
0x14000514f  movzx   ecx, r15b; NewIrql
0x140005153  call    cs:__imp_KeLowerIrql
0x14000515a  nop     dword ptr [rax+rax+00h]
0x14000515f  jmp     loc_140005036
```
