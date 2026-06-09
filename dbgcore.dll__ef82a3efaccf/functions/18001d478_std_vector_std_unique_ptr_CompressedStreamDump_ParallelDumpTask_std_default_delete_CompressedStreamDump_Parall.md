# std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>,std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>>>::_Emplace_reallocate<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>>(std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>> * const,std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>> &&)

- ea: `0x18001d478`
- end: `0x18001d632`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `442`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e114`

## callees

- `0x180001b1c`
- `0x18001d478`
- `0x18001da90`
- `0x18001f04c`
- `0x18001f10c`
- `0x18001f134`

## pseudocode

```c
char *__fastcall std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Emplace_reallocate<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v3; // r15
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // r13
  unsigned __int64 v11; // rbp
  size_t v12; // rcx
  _QWORD *v13; // rbx
  void *v14; // rax
  __int64 v15; // rsi
  _QWORD *v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  __int64 *v19; // r8
  __int64 *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // rax
  __int64 *v24; // rdx
  _QWORD *v25; // rcx
  __int64 v26; // rax
  _QWORD v28[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-60h]
  _QWORD *v30; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = a1[1] - *a1;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<_NUMA_NODE_RELATIONSHIP>::_Xlength();
  v8 = a1[2] - v3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_26;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_26;
  v12 = 8 * v11;
  if ( !(8 * v11) )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_14;
  }
  if ( v12 + 39 < v12 )
LABEL_26:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v28[0] = a1;
  v28[2] = v11;
  v15 = a2 - v3;
  v16 = &v13[v15];
  v29 = v16;
  v30 = v16 + 1;
  v17 = *a3;
  *a3 = 0;
  *v16 = v17;
  v18 = v13;
  v19 = a1[1];
  v20 = *a1;
  if ( a2 == v19 )
  {
    while ( v20 != v19 )
    {
      v21 = *v20;
      *v20++ = 0;
      *v18++ = v21;
    }
    v22 = v15;
  }
  else
  {
    while ( v20 != a2 )
    {
      v23 = *v20;
      *v20++ = 0;
      *v18++ = v23;
    }
    v24 = a1[1];
    v22 = v15;
    v29 = v13;
    v25 = &v13[v22 + 1];
    while ( a2 != v24 )
    {
      v26 = *a2;
      *a2++ = 0;
      *v25++ = v26;
    }
  }
  v28[1] = 0;
  std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Change_array(a1, v13, v10, v11);
  std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Reallocation_guard::~_Reallocation_guard(v28);
  return (char *)&v13[v22];
}

```

## disassembly

```asm
0x18001d478  push    rbx
0x18001d47a  push    rbp
0x18001d47b  push    rsi
0x18001d47c  push    rdi
0x18001d47d  push    r12
0x18001d47f  push    r13
0x18001d481  push    r14
0x18001d483  push    r15
0x18001d485  sub     rsp, 58h
0x18001d489  mov     r15, [rcx]
0x18001d48c  mov     rdi, rdx
0x18001d48f  mov     rdx, [rcx+8]
0x18001d493  mov     r9, 1FFFFFFFFFFFFFFFh
0x18001d49d  sub     rdx, r15
0x18001d4a0  mov     r12, r8
0x18001d4a3  sar     rdx, 3
0x18001d4a7  mov     r14, rcx
0x18001d4aa  cmp     rdx, r9
0x18001d4ad  jz      loc_18001D626
0x18001d4b3  mov     rcx, [rcx+10h]
0x18001d4b7  mov     rax, r9
0x18001d4ba  sub     rcx, r15
0x18001d4bd  sar     rcx, 3
0x18001d4c1  mov     r8, rcx
0x18001d4c4  shr     r8, 1
0x18001d4c7  sub     rax, r8
0x18001d4ca  cmp     rcx, rax
0x18001d4cd  ja      loc_18001D62C
0x18001d4d3  lea     r13, [rdx+1]
0x18001d4d7  lea     rax, [rcx+r8]
0x18001d4db  mov     rbp, r13
0x18001d4de  cmp     rax, r13
0x18001d4e1  cmovnb  rbp, rax
0x18001d4e5  cmp     rbp, r9
0x18001d4e8  ja      loc_18001D62C
0x18001d4ee  lea     rcx, ds:0[rbp*8]; Size
0x18001d4f6  test    rcx, rcx
0x18001d4f9  jnz     short loc_18001D4FF
0x18001d4fb  xor     ebx, ebx
0x18001d4fd  jmp     short loc_18001D53D
0x18001d4ff  cmp     rcx, 1000h
0x18001d506  jb      short loc_18001D535
0x18001d508  lea     rax, [rcx+27h]
0x18001d50c  cmp     rax, rcx
0x18001d50f  jbe     loc_18001D62C
0x18001d515  mov     rcx, rax; Size
0x18001d518  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d51d  test    rax, rax
0x18001d520  jnz     short loc_18001D527
0x18001d522  lea     ecx, [rax+5]
0x18001d525  int     29h; Win8: RtlFailFast(ecx)
0x18001d527  lea     rbx, [rax+27h]
0x18001d52b  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001d52f  mov     [rbx-8], rax
0x18001d533  jmp     short loc_18001D53D
0x18001d535  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d53a  mov     rbx, rax
0x18001d53d  mov     rsi, rdi
0x18001d540  mov     [rsp+98h+var_78], r14
0x18001d545  sub     rsi, r15
0x18001d548  mov     [rsp+98h+var_68], rbp
0x18001d54d  sar     rsi, 3
0x18001d551  lea     rdx, [rbx+rsi*8]
0x18001d555  lea     rcx, [rdx+8]
0x18001d559  mov     [rsp+98h+var_60], rdx
0x18001d55e  mov     [rsp+98h+var_58], rcx
0x18001d563  mov     rcx, [r12]
0x18001d567  mov     qword ptr [r12], 0
0x18001d56f  mov     [rdx], rcx
0x18001d572  mov     rdx, rbx
0x18001d575  mov     r8, [r14+8]
0x18001d579  mov     rcx, [r14]
0x18001d57c  cmp     rdi, r8
0x18001d57f  jnz     short loc_18001D5B8
0x18001d581  jmp     short loc_18001D598
0x18001d583  mov     rax, [rcx]
0x18001d586  mov     qword ptr [rcx], 0
0x18001d58d  add     rcx, 8
0x18001d591  mov     [rdx], rax
0x18001d594  lea     rdx, [rdx+8]
0x18001d598  cmp     rcx, r8
0x18001d59b  jnz     short loc_18001D583
0x18001d59d  shl     rsi, 3
0x18001d5a1  jmp     short loc_18001D5ED
0x18001d5a3  mov     rax, [rcx]
0x18001d5a6  mov     qword ptr [rcx], 0
0x18001d5ad  add     rcx, 8
0x18001d5b1  mov     [rdx], rax
0x18001d5b4  lea     rdx, [rdx+8]
0x18001d5b8  cmp     rcx, rdi
0x18001d5bb  jnz     short loc_18001D5A3
0x18001d5bd  mov     rdx, [r14+8]
0x18001d5c1  shl     rsi, 3
0x18001d5c5  mov     [rsp+98h+var_60], rbx
0x18001d5ca  lea     rcx, [rsi+8]
0x18001d5ce  add     rcx, rbx
0x18001d5d1  jmp     short loc_18001D5E8
0x18001d5d3  mov     rax, [rdi]
0x18001d5d6  mov     qword ptr [rdi], 0
0x18001d5dd  add     rdi, 8
0x18001d5e1  mov     [rcx], rax
0x18001d5e4  lea     rcx, [rcx+8]
0x18001d5e8  cmp     rdi, rdx
0x18001d5eb  jnz     short loc_18001D5D3
0x18001d5ed  mov     r9, rbp
0x18001d5f0  mov     [rsp+98h+var_70], 0
0x18001d5f9  mov     r8, r13
0x18001d5fc  mov     rdx, rbx
0x18001d5ff  mov     rcx, r14
0x18001d602  call    ?_Change_array@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Change_array(std::unique_ptr<CompressedStreamDump::ParallelDumpTask> * const,unsigned __int64,unsigned __int64)
0x18001d607  lea     rcx, [rsp+98h+var_78]
0x18001d60c  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001d611  lea     rax, [rsi+rbx]
0x18001d615  add     rsp, 58h
0x18001d619  pop     r15
0x18001d61b  pop     r14
0x18001d61d  pop     r13
0x18001d61f  pop     r12
0x18001d621  pop     rdi
0x18001d622  pop     rsi
0x18001d623  pop     rbp
0x18001d624  pop     rbx
0x18001d625  retn
0x18001d626  call    ?_Xlength@?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@CAXXZ; std::vector<_NUMA_NODE_RELATIONSHIP>::_Xlength(void)
0x18001d62c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
