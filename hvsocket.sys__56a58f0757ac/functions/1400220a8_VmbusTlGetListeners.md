# VmbusTlGetListeners

- ea: `0x1400220a8`
- end: `0x1400221df`
- name: `VmbusTlGetListeners`
- size: `311`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001a9f0`

## callees

- `0x1400015dc`
- `0x14000a154`
- `0x1400220a8`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140022134`
- `ntoskrnl!PsGetProcessId` at `0x140022134`

## pseudocode

```c
__int64 __fastcall VmbusTlGetListeners(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  __int64 v4; // r12
  __int64 *v5; // rdi
  unsigned int v6; // ebp
  __int64 v7; // r13
  unsigned int v8; // esi
  BOOLEAN v9; // r8
  __int64 v10; // rbx
  unsigned int ProcessId; // eax
  _QWORD *v12; // r14

  v4 = a1 + 360;
  v5 = *(__int64 **)(a1 + 360);
  v6 = 0;
  v7 = a1;
  v8 = a2 / 0x38;
LABEL_7:
  if ( v5 == (__int64 *)v4 )
  {
    *a4 = v6;
    return 0;
  }
  else
  {
    v9 = 1;
    while ( 1 )
    {
      v12 = VmbusTlEnumerateObjectTable(a1, (struct _RTL_AVL_TABLE *)(v5 + 9), v9);
      if ( !v12 )
      {
        v5 = (__int64 *)*v5;
        goto LABEL_7;
      }
      if ( v6 == v8 )
        break;
      v10 = 56LL * v6;
      *(_OWORD *)(v10 + a3) = *(_OWORD *)((char *)v12 + 156);
      *(_OWORD *)(v10 + a3 + 16) = *(_OWORD *)((char *)v12 + 140);
      ProcessId = (unsigned int)PsGetProcessId((PEPROCESS)v12[34]);
      a1 = a3;
      ++v6;
      v9 = 0;
      *(_DWORD *)(v10 + a3 + 32) = ProcessId;
      *(_QWORD *)(v10 + a3 + 40) = v12[39];
      *(_BYTE *)(v10 + a3 + 48) = *((_BYTE *)v12 + 424);
    }
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((const int *)"VmbusTlGetListeners", 869, 3221225507LL, (__int64)(v5 + 2), v7 + 232);
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x1400220a8  mov     [rsp+arg_0], rbx
0x1400220ad  mov     [rsp+arg_18], r9
0x1400220b2  mov     [rsp+arg_10], r8
0x1400220b7  push    rbp
0x1400220b8  push    rsi
0x1400220b9  push    rdi
0x1400220ba  push    r12
0x1400220bc  push    r13
0x1400220be  push    r14
0x1400220c0  push    r15
0x1400220c2  sub     rsp, 30h
0x1400220c6  mov     esi, edx
0x1400220c8  lea     r12, [rcx+168h]
0x1400220cf  mov     rdi, [r12]
0x1400220d3  mov     rax, 2492492492492493h
0x1400220dd  mul     rsi
0x1400220e0  xor     ebp, ebp
0x1400220e2  mov     r13, rcx
0x1400220e5  sub     rsi, rdx
0x1400220e8  shr     rsi, 1
0x1400220eb  add     rsi, rdx
0x1400220ee  shr     rsi, 5
0x1400220f2  jmp     loc_14002217C
0x1400220f7  mov     r8b, 1
0x1400220fa  jmp     short loc_140022168
0x1400220fc  cmp     ebp, esi
0x1400220fe  jz      loc_1400221A7
0x140022104  mov     rax, [rsp+68h+arg_10]
0x14002210c  movups  xmm0, xmmword ptr [r14+9Ch]
0x140022114  mov     ecx, ebp
0x140022116  imul    rbx, rcx, 38h ; '8'
0x14002211a  movdqu  xmmword ptr [rbx+rax], xmm0
0x14002211f  movups  xmm1, xmmword ptr [r14+8Ch]
0x140022127  movdqu  xmmword ptr [rbx+rax+10h], xmm1
0x14002212d  mov     rcx, [r14+110h]; Process
0x140022134  call    cs:__imp_PsGetProcessId
0x14002213b  nop     dword ptr [rax+rax+00h]
0x140022140  mov     rcx, [rsp+68h+arg_10]
0x140022148  inc     ebp
0x14002214a  xor     r8d, r8d
0x14002214d  mov     [rbx+rcx+20h], eax
0x140022151  mov     rax, [r14+138h]
0x140022158  mov     [rbx+rcx+28h], rax
0x14002215d  mov     al, [r14+1A8h]
0x140022164  mov     [rbx+rcx+30h], al
0x140022168  lea     rdx, [rdi+48h]
0x14002216c  call    VmbusTlEnumerateObjectTable
0x140022171  mov     r14, rax
0x140022174  test    rax, rax
0x140022177  jnz     short loc_1400220FC
0x140022179  mov     rdi, [rdi]
0x14002217c  cmp     rdi, r12
0x14002217f  jnz     loc_1400220F7
0x140022185  mov     rax, [rsp+68h+arg_18]
0x14002218d  mov     [rax], ebp
0x14002218f  xor     eax, eax
0x140022191  mov     rbx, [rsp+68h+arg_0]
0x140022196  add     rsp, 30h
0x14002219a  pop     r15
0x14002219c  pop     r14
0x14002219e  pop     r13
0x1400221a0  pop     r12
0x1400221a2  pop     rdi
0x1400221a3  pop     rsi
0x1400221a4  pop     rbp
0x1400221a5  retn
0x1400221a7  mov     ecx, cs:dword_140013058
0x1400221ad  mov     ebx, 0C0000023h
0x1400221b2  cmp     ecx, 2
0x1400221b5  jbe     short loc_1400221DB
0x1400221b7  lea     rcx, [r13+0E8h]
0x1400221be  mov     r8d, ebx
0x1400221c1  mov     [rsp+68h+var_48], rcx
0x1400221c6  lea     r9, [rdi+10h]
0x1400221ca  lea     rcx, aVmbustlgetlist; "VmbusTlGetListeners"
0x1400221d1  mov     edx, 365h
0x1400221d6  call    HvsocketTraceServiceError
0x1400221db  mov     eax, ebx
0x1400221dd  jmp     short loc_140022191
```
