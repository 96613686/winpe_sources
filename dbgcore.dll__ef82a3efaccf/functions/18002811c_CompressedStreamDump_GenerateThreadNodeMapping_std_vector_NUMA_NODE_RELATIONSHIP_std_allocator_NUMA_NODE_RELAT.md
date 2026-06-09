# CompressedStreamDump::GenerateThreadNodeMapping(std::vector<_NUMA_NODE_RELATIONSHIP,std::allocator<_NUMA_NODE_RELATIONSHIP>> const &,uint,std::vector<ulong,std::allocator<ulong>> &)

- ea: `0x18002811c`
- end: `0x18002827d`
- name: `?GenerateThreadNodeMapping@CompressedStreamDump@@YAXAEBV?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@IAEAV?$vector@KV?$allocator@K@std@@@3@@Z`
- size: `353`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001e114`

## callees

- `0x18001f14c`
- `0x180027c08`
- `0x18002811c`
- `0x1800289b8`
- `0x180028b48`

## string_xrefs

- `0x180028140`: `GenerateThreadNodeMapping: numaNodeInfoVector is empty.\n`

## pseudocode

```c
void __fastcall CompressedStreamDump::GenerateThreadNodeMapping(unsigned __int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // r9
  const char *v5; // r8
  unsigned __int64 v6; // rdi
  __int64 v7; // rbp
  unsigned int v8; // esi
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  __int64 v13; // rsi
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rbp
  _DWORD *v16; // rdx
  __int64 v17; // rcx
  int v18; // [rsp+60h] [rbp+8h] BYREF
  char v19; // [rsp+78h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v5 = *(const char **)a1;
  v6 = a1;
  v7 = a2;
  if ( *(_QWORD *)a1 == v3 )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"GenerateThreadNodeMapping: numaNodeInfoVector is empty.\n",
      v5);
  }
  else
  {
    v8 = 0;
    v9 = 0xCCCCCCCCCCCCCCCDuLL * ((v3 - (__int64)v5) >> 3);
    v10 = 0;
    if ( !v9 )
      goto LABEL_6;
    do
    {
      v11 = 5 * v10++;
      a1 = __popcnt(*(_QWORD *)&v5[8 * v11 + 24]);
      v8 += (unsigned __int16)a1;
    }
    while ( v10 < v9 );
    if ( !v8 )
LABEL_6:
      v8 = 1;
    if ( v9 )
    {
      v12 = 0;
      do
      {
        if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v6 + 8) - (_QWORD)v5) >> 3) <= v12 )
          std::vector<MemoryBucket *>::_Xrange(a1, v10, v5, v9);
        v18 = v12;
        std::vector<unsigned long>::insert(
          a3,
          &v19,
          a3[1],
          (unsigned __int16)((unsigned int)v7 * (unsigned __int16)__popcnt(*(_QWORD *)&v5[40 * v12 + 24]) / v8),
          &v18);
        v5 = *(const char **)v6;
        ++v12;
      }
      while ( v12 < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v6 + 8) - *(_QWORD *)v6) >> 3) );
    }
    v13 = 0;
    v14 = 0;
    v15 = v7 - ((__int64)(a3[1] - *a3) >> 2);
    if ( v15 )
    {
      do
      {
        v16 = (_DWORD *)a3[1];
        v18 = v13;
        if ( v16 == (_DWORD *)a3[2] )
        {
          std::vector<unsigned long>::_Emplace_reallocate<unsigned long>(a3, v16, &v18);
        }
        else
        {
          *v16 = v13;
          a3[1] += 4LL;
        }
        v17 = v13 + 1;
        v13 = 0;
        ++v14;
        if ( v17 != 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v6 + 8) - *(_QWORD *)v6) >> 3) )
          v13 = v17;
      }
      while ( v14 < v15 );
    }
  }
}

```

## disassembly

```asm
0x18002811c  mov     [rsp+arg_8], rbx
0x180028121  push    rbp
0x180028122  push    rsi
0x180028123  push    rdi
0x180028124  push    r14
0x180028126  push    r15
0x180028128  sub     rsp, 30h
0x18002812c  mov     r9, [rcx+8]
0x180028130  mov     rbx, r8
0x180028133  mov     r8, [rcx]; char *
0x180028136  mov     rdi, rcx
0x180028139  mov     ebp, edx
0x18002813b  cmp     r8, r9
0x18002813e  jnz     short loc_180028156
0x180028140  lea     rdx, aGeneratethread; "GenerateThreadNodeMapping: numaNodeInfo"...
0x180028147  mov     ecx, 4; this
0x18002814c  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180028151  jmp     loc_180028266
0x180028156  sub     r9, r8
0x180028159  mov     r15, 0CCCCCCCCCCCCCCCDh
0x180028163  sar     r9, 3
0x180028167  xor     esi, esi
0x180028169  imul    r9, r15
0x18002816d  xor     edx, edx
0x18002816f  test    r9, r9
0x180028172  jz      short loc_180028191
0x180028174  lea     rax, [rdx+rdx*4]
0x180028178  inc     rdx
0x18002817b  popcnt  rcx, qword ptr [r8+rax*8+18h]
0x180028182  movzx   eax, cx
0x180028185  add     esi, eax
0x180028187  cmp     rdx, r9
0x18002818a  jb      short loc_180028174
0x18002818c  cmp     esi, 1
0x18002818f  jnb     short loc_180028196
0x180028191  mov     esi, 1
0x180028196  test    r9, r9
0x180028199  jz      short loc_180028209
0x18002819b  xor     r14d, r14d
0x18002819e  mov     rax, [rdi+8]
0x1800281a2  sub     rax, r8
0x1800281a5  sar     rax, 3
0x1800281a9  imul    rax, r15
0x1800281ad  cmp     rax, r14
0x1800281b0  jbe     loc_180028277
0x1800281b6  lea     rax, [r14+r14*4]
0x1800281ba  mov     [rsp+58h+arg_0], r14d
0x1800281bf  popcnt  rcx, qword ptr [r8+rax*8+18h]
0x1800281c6  mov     r8, [rbx+8]
0x1800281ca  xor     edx, edx
0x1800281cc  movzx   eax, cx
0x1800281cf  mov     rcx, rbx
0x1800281d2  imul    eax, ebp
0x1800281d5  div     esi
0x1800281d7  lea     rdx, [rsp+58h+arg_18]
0x1800281dc  movzx   r9d, ax
0x1800281e0  lea     rax, [rsp+58h+arg_0]
0x1800281e5  mov     [rsp+58h+var_38], rax
0x1800281ea  call    ?insert@?$vector@KV?$allocator@K@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@2@_KAEBK@Z; std::vector<ulong>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,unsigned __int64,ulong const &)
0x1800281ef  mov     r8, [rdi]
0x1800281f2  inc     r14
0x1800281f5  mov     rax, [rdi+8]
0x1800281f9  sub     rax, r8
0x1800281fc  sar     rax, 3
0x180028200  imul    rax, r15
0x180028204  cmp     r14, rax
0x180028207  jb      short loc_18002819E
0x180028209  mov     rax, [rbx+8]
0x18002820d  xor     esi, esi
0x18002820f  sub     rax, [rbx]
0x180028212  mov     r14d, esi
0x180028215  sar     rax, 2
0x180028219  sub     rbp, rax
0x18002821c  jz      short loc_180028266
0x18002821e  mov     rdx, [rbx+8]
0x180028222  mov     [rsp+58h+arg_0], esi
0x180028226  cmp     rdx, [rbx+10h]
0x18002822a  jz      short loc_180028235
0x18002822c  mov     [rdx], esi
0x18002822e  add     qword ptr [rbx+8], 4
0x180028233  jmp     short loc_180028242
0x180028235  lea     r8, [rsp+58h+arg_0]
0x18002823a  mov     rcx, rbx
0x18002823d  call    ??$_Emplace_reallocate@K@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAK$$QEAK@Z; std::vector<ulong>::_Emplace_reallocate<ulong>(ulong * const,ulong &&)
0x180028242  mov     rax, [rdi+8]
0x180028246  lea     rcx, [rsi+1]
0x18002824a  sub     rax, [rdi]
0x18002824d  xor     esi, esi
0x18002824f  sar     rax, 3
0x180028253  inc     r14
0x180028256  imul    rax, r15
0x18002825a  cmp     rcx, rax
0x18002825d  cmovnz  rsi, rcx
0x180028261  cmp     r14, rbp
0x180028264  jb      short loc_18002821E
0x180028266  mov     rbx, [rsp+58h+arg_8]
0x18002826b  add     rsp, 30h
0x18002826f  pop     r15
0x180028271  pop     r14
0x180028273  pop     rdi
0x180028274  pop     rsi
0x180028275  pop     rbp
0x180028276  retn
0x180028277  call    ?_Xrange@?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@CAXXZ; std::vector<MemoryBucket *>::_Xrange(void)
```
