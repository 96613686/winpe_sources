# LOG_PIPE_SERVER::RespondWithMultiString(IPM2_MESSAGE const *,IPM2_OPCODE,MULTISZ * *,ulong)

- ea: `0x180005420`
- end: `0x18000559c`
- name: `?RespondWithMultiString@LOG_PIPE_SERVER@@CAJPEBVIPM2_MESSAGE@@W4IPM2_OPCODE@@PEAPEAVMULTISZ@@K@Z`
- size: `380`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f40`

## callees

- `0x180005420`
- `0x1800056e6`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005575`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005583`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18000547c`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x1800054e5`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18000547c`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x1800054e5`
- `iisutil!?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@KKPEAXK1@Z` at `0x18000556d`
- `iisutil!?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@KKPEAXK1@Z` at `0x18000556d`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800054f0`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800054f0`

## pseudocode

```c
__int64 __fastcall LOG_PIPE_SERVER::RespondWithMultiString(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // r13
  __int64 v6; // r14
  __int64 v7; // rbx
  unsigned int i; // r12d
  MULTISZ *v9; // rcx
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // r15
  __int64 v15; // rbp
  char *v16; // r15
  int v17; // r12d
  MULTISZ *v18; // r13
  unsigned int CB; // ebx
  unsigned __int16 *Str; // rax
  unsigned int v21; // eax
  HANDLE v22; // rax
  __int64 v24; // [rsp+40h] [rbp-58h]

  v5 = a3;
  v6 = a1;
  v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
  v7 = 0;
  for ( i = 8 * a4 + 12; (unsigned int)v7 < a4; v7 = (unsigned int)(v7 + 1) )
  {
    v9 = *(MULTISZ **)(v5 + 8 * v7);
    if ( v9 )
      i += MULTISZ::QueryCB(v9);
  }
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, i);
  v12 = v11;
  if ( v11 )
  {
    v14 = 8 * a4 + 12;
    v15 = 0;
    v11[2] = v14;
    v16 = (char *)v11 + v14;
    *v11 = a4;
    v11[1] = 12;
    if ( a4 )
    {
      v17 = 0;
      do
      {
        v18 = *(MULTISZ **)(v5 + 8 * v15);
        if ( v18 )
        {
          CB = MULTISZ::QueryCB(v18);
          Str = MULTISZ::QueryStr(v18);
          v12[2 * v15 + 3] = CB;
          v12[2 * v15 + 4] = v17;
          memcpy_0(&v16[v17], Str, CB);
          v17 += CB;
        }
        else
        {
          *(_QWORD *)&v12[2 * v15 + 3] = 0;
        }
        v5 = a3;
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < a4 );
      v6 = a1;
    }
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
    v13 = IPM2_MESSAGE_PIPE::WriteMessage(v24, 5, v21);
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v12);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v13;
}

```

## disassembly

```asm
0x180005420  mov     [rsp+arg_10], r8
0x180005425  mov     [rsp+arg_8], edx
0x180005429  mov     [rsp+arg_0], rcx
0x18000542e  push    rbx
0x18000542f  push    rbp
0x180005430  push    rsi
0x180005431  push    rdi
0x180005432  push    r12
0x180005434  push    r13
0x180005436  push    r14
0x180005438  push    r15
0x18000543a  sub     rsp, 58h
0x18000543e  mov     rax, [rcx]
0x180005441  mov     esi, r9d
0x180005444  mov     r13, r8
0x180005447  mov     r14, rcx
0x18000544a  mov     rax, [rax+30h]
0x18000544e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005453  lea     ebp, ds:0[rsi*8]
0x18000545a  mov     [rsp+98h+var_58], rax
0x18000545f  add     ebp, 0Ch
0x180005462  xor     ebx, ebx
0x180005464  mov     [rsp+98h+arg_8], ebp
0x18000546b  mov     r12d, ebp
0x18000546e  test    esi, esi
0x180005470  jz      short loc_180005493
0x180005472  mov     rcx, [r13+rbx*8+0]
0x180005477  test    rcx, rcx
0x18000547a  jz      short loc_180005485
0x18000547c  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x180005482  add     r12d, eax
0x180005485  inc     ebx
0x180005487  cmp     ebx, esi
0x180005489  jb      short loc_180005472
0x18000548b  mov     [rsp+98h+arg_8], r12d
0x180005493  call    cs:__imp_GetProcessHeap
0x180005499  mov     r8d, r12d; dwBytes
0x18000549c  mov     edx, 8; dwFlags
0x1800054a1  mov     rcx, rax; hHeap
0x1800054a4  call    cs:__imp_HeapAlloc
0x1800054aa  mov     rdi, rax
0x1800054ad  test    rax, rax
0x1800054b0  jnz     short loc_1800054BC
0x1800054b2  mov     ebx, 8007000Eh
0x1800054b7  jmp     loc_180005589
0x1800054bc  mov     r15d, ebp
0x1800054bf  xor     ebp, ebp
0x1800054c1  mov     [rax+8], r15d
0x1800054c5  add     r15, rdi
0x1800054c8  mov     [rax], esi
0x1800054ca  mov     dword ptr [rax+4], 0Ch
0x1800054d1  test    esi, esi
0x1800054d3  jz      short loc_18000553C
0x1800054d5  mov     r12d, ebp
0x1800054d8  mov     r13, [r13+rbp*8+0]
0x1800054dd  test    r13, r13
0x1800054e0  jz      short loc_180005515
0x1800054e2  mov     rcx, r13
0x1800054e5  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x1800054eb  mov     rcx, r13
0x1800054ee  mov     ebx, eax
0x1800054f0  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x1800054f6  mov     ecx, r12d
0x1800054f9  mov     r8d, ebx; Size
0x1800054fc  add     rcx, r15; void *
0x1800054ff  mov     [rdi+rbp*8+0Ch], ebx
0x180005503  mov     rdx, rax; Src
0x180005506  mov     [rdi+rbp*8+10h], r12d
0x18000550b  call    memcpy_0
0x180005510  add     r12d, ebx
0x180005513  jmp     short loc_18000551E
0x180005515  mov     qword ptr [rdi+rbp*8+0Ch], 0
0x18000551e  mov     r13, [rsp+98h+arg_10]
0x180005526  inc     ebp
0x180005528  cmp     ebp, esi
0x18000552a  jb      short loc_1800054D8
0x18000552c  mov     r12d, [rsp+98h+arg_8]
0x180005534  mov     r14, [rsp+98h+arg_0]
0x18000553c  mov     rax, [r14]
0x18000553f  mov     rcx, r14
0x180005542  mov     rax, [rax+28h]
0x180005546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554b  mov     rcx, [rsp+98h+var_58]
0x180005550  xor     r9d, r9d
0x180005553  mov     [rsp+98h+var_68], rdi
0x180005558  mov     r8d, eax
0x18000555b  mov     [rsp+98h+var_70], r12d
0x180005560  mov     [rsp+98h+var_78], 0
0x180005569  lea     edx, [r9+5]
0x18000556d  call    cs:__imp_?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@KKPEAXK1@Z; IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,ulong,ulong,void *,ulong,void *)
0x180005573  mov     ebx, eax
0x180005575  call    cs:__imp_GetProcessHeap
0x18000557b  mov     r8, rdi; lpMem
0x18000557e  xor     edx, edx; dwFlags
0x180005580  mov     rcx, rax; hHeap
0x180005583  call    cs:__imp_HeapFree
0x180005589  mov     eax, ebx
0x18000558b  add     rsp, 58h
0x18000558f  pop     r15
0x180005591  pop     r14
0x180005593  pop     r13
0x180005595  pop     r12
0x180005597  pop     rdi
0x180005598  pop     rsi
0x180005599  pop     rbp
0x18000559a  pop     rbx
0x18000559b  retn
```
