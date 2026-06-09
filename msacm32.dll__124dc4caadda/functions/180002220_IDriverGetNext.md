# IDriverGetNext

- ea: `0x180002220`
- end: `0x1800023ac`
- name: `IDriverGetNext`
- size: `396`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012a0`
- `0x180001570`
- `0x180001940`
- `0x180001ad0`
- `0x180002540`
- `0x180002900`
- `0x180007cf0`
- `0x180007ef0`
- `0x180008160`
- `0x1800089c0`
- `0x180008dd8`
- `0x18000ad3c`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c130`
- `0x18000ca28`
- `0x18000cfe0`
- `0x18000d7b0`

## callees

- `0x180002220`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000236c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000236c`

## pseudocode

```c
__int64 __fastcall IDriverGetNext(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  int v6; // r14d
  BOOL v7; // r15d
  int v8; // r12d
  BOOL v9; // r13d
  int v10; // esi
  __int64 CurrentThreadId; // rcx
  __int64 v12; // rbx
  __int64 v13; // rax

  if ( !a2 )
    return 11;
  *a2 = 0;
  if ( a4 == -1 )
  {
    v6 = 1;
    v7 = 1;
    v8 = 1;
    v9 = 1;
    v10 = 1;
  }
  else
  {
    if ( (a4 & 0xFFFFFFF) != 0 )
      return 10;
    v7 = (a4 & 0x40000000) == 0;
    v10 = 0;
    v8 = (a4 >> 28) & 1;
    v6 = a4 >> 31;
    v9 = (a4 & 0x20000000) != 0;
  }
  if ( a3 )
  {
    if ( a1 != *(_QWORD *)(a3 + 4) )
      return 5;
    CurrentThreadId = *(_QWORD *)(a3 + 36);
    v12 = *(_QWORD *)(a3 + 20);
  }
  else
  {
    v12 = *(_QWORD *)(a1 + 96);
    CurrentThreadId = GetCurrentThreadId();
  }
  v13 = 0;
  if ( !v10 )
    v13 = CurrentThreadId;
  while ( 1 )
  {
    while ( v12 )
    {
      if ( v10
        || *(_QWORD *)(v12 + 36) == v13
        && (v8 || (*(_DWORD *)(v12 + 56) & 0x10000000) == 0)
        && (v7 || (*(_DWORD *)(v12 + 56) & 0x40000000) == 0)
        && (v6 || *(int *)(v12 + 56) >= 0)
        && (v9 || !*(_DWORD *)(v12 + 12)) )
      {
        *a2 = v12;
        return 0;
      }
      v12 = *(_QWORD *)(v12 + 20);
    }
    if ( !v13 )
      break;
    v12 = *(_QWORD *)(a1 + 96);
    v13 = 0;
  }
  return 2;
}

```

## disassembly

```asm
0x180002220  push    rbp
0x180002222  push    rdi
0x180002223  sub     rsp, 38h
0x180002227  mov     rdi, rdx
0x18000222a  mov     rbp, rcx
0x18000222d  test    rdx, rdx
0x180002230  jz      loc_180002383
0x180002236  mov     [rsp+48h+arg_8], rsi
0x18000223b  mov     [rsp+48h+arg_10], r12
0x180002240  mov     [rsp+48h+var_18], r13
0x180002245  mov     [rsp+48h+var_20], r14
0x18000224a  mov     [rsp+48h+var_28], r15
0x18000224f  mov     qword ptr [rdx], 0
0x180002256  cmp     r9d, 0FFFFFFFFh
0x18000225a  jnz     loc_18000230D
0x180002260  mov     r14d, 1
0x180002266  mov     r15d, r14d
0x180002269  mov     r12d, r14d
0x18000226c  mov     r13d, r14d
0x18000226f  mov     esi, r14d
0x180002272  mov     [rsp+48h+arg_0], rbx
0x180002277  test    r8, r8
0x18000227a  jz      loc_180002368
0x180002280  cmp     rbp, [r8+4]
0x180002284  jnz     loc_1800023A2
0x18000228a  mov     rcx, [r8+24h]
0x18000228e  mov     rbx, [r8+14h]
0x180002292  xor     eax, eax
0x180002294  test    esi, esi
0x180002296  cmovz   rax, rcx
0x18000229a  test    rbx, rbx
0x18000229d  jz      loc_180002349
0x1800022a3  test    esi, esi
0x1800022a5  jnz     short loc_1800022E3
0x1800022a7  cmp     [rbx+24h], rax
0x1800022ab  jz      short loc_1800022B3
0x1800022ad  mov     rbx, [rbx+14h]
0x1800022b1  jmp     short loc_18000229A
0x1800022b3  test    r12d, r12d
0x1800022b6  jnz     short loc_1800022C1
0x1800022b8  test    dword ptr [rbx+38h], 10000000h
0x1800022bf  jnz     short loc_1800022AD
0x1800022c1  test    r15d, r15d
0x1800022c4  jnz     short loc_1800022CF
0x1800022c6  test    dword ptr [rbx+38h], 40000000h
0x1800022cd  jnz     short loc_1800022AD
0x1800022cf  test    r14d, r14d
0x1800022d2  jz      loc_180002359
0x1800022d8  test    r13d, r13d
0x1800022db  jnz     short loc_1800022E3
0x1800022dd  cmp     [rbx+0Ch], r13d
0x1800022e1  jnz     short loc_1800022AD
0x1800022e3  mov     [rdi], rbx
0x1800022e6  xor     eax, eax
0x1800022e8  mov     rbx, [rsp+48h+arg_0]
0x1800022ed  mov     r13, [rsp+48h+var_18]
0x1800022f2  mov     r12, [rsp+48h+arg_10]
0x1800022f7  mov     rsi, [rsp+48h+arg_8]
0x1800022fc  mov     r14, [rsp+48h+var_20]
0x180002301  mov     r15, [rsp+48h+var_28]
0x180002306  add     rsp, 38h
0x18000230a  pop     rdi
0x18000230b  pop     rbp
0x18000230c  retn
0x18000230d  test    r9d, 0FFFFFFFh
0x180002314  jnz     short loc_18000238D
0x180002316  mov     r15d, r9d
0x180002319  mov     r12d, r9d
0x18000231c  shr     r15d, 1Eh
0x180002320  mov     eax, r9d
0x180002323  shr     r12d, 1Ch
0x180002327  not     r15d
0x18000232a  shr     eax, 1Fh
0x18000232d  and     r15d, 1
0x180002331  xor     esi, esi
0x180002333  and     r12d, 1
0x180002337  mov     r14d, eax
0x18000233a  bt      r9d, 1Dh
0x18000233f  jb      short loc_180002397
0x180002341  xor     r13d, r13d
0x180002344  jmp     loc_180002272
0x180002349  test    rax, rax
0x18000234c  jz      short loc_180002379
0x18000234e  mov     rbx, [rbp+60h]
0x180002352  xor     eax, eax
0x180002354  jmp     loc_18000229A
0x180002359  cmp     dword ptr [rbx+38h], 0
0x18000235d  jge     loc_1800022D8
0x180002363  jmp     loc_1800022AD
0x180002368  mov     rbx, [rcx+60h]
0x18000236c  call    cs:__imp_GetCurrentThreadId
0x180002372  mov     ecx, eax
0x180002374  jmp     loc_180002292
0x180002379  mov     eax, 2
0x18000237e  jmp     loc_1800022E8
0x180002383  mov     eax, 0Bh
0x180002388  jmp     loc_180002306
0x18000238d  mov     eax, 0Ah
0x180002392  jmp     loc_1800022ED
0x180002397  mov     r13d, 1
0x18000239d  jmp     loc_180002272
0x1800023a2  mov     eax, 5
0x1800023a7  jmp     loc_1800022E8
```
