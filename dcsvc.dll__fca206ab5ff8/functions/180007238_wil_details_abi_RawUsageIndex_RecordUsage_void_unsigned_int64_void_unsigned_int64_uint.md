# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007238`
- end: `0x1800073e1`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042a0`
- `0x180007134`
- `0x180007168`

## callees

- `0x180007238`
- `0x1800073e8`
- `0x18000a158`
- `0x18000a270`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007384`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007384`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000735f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007392`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000735f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007392`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebp
  void *v9; // rsi
  unsigned __int64 v12; // rdx
  _QWORD *v13; // r14
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rsi
  __int64 v18; // rdi
  void *v19; // rbp
  HANDLE ProcessHeap; // rax
  void *v21; // rdi
  void *v22; // rsi
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int128 v25; // [rsp+30h] [rbp-68h] BYREF
  __int128 v26; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a6;
  v9 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, a2, a3, a4, a5, a6) )
    return 1;
  v12 = a3 + a5 + 32;
  v13 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v12);
  }
  else
  {
    v25 = 0;
    v26 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v25, v12 + 10) )
    {
      v17 = v25;
      v18 = v26 - v25;
      if ( (_QWORD)v26 - (_QWORD)v25 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(retaddr, v14, v15, v16);
      v19 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v19 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
      *v13 = v17;
      *((_QWORD *)this + 5) = v18 + v17;
      v21 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v17 = 0;
      *(_WORD *)(v17 + 2) = *(_WORD *)this;
      *(_WORD *)(v17 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v17 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v17 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v17 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v22 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v26 + 1);
      if ( v22 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v22);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v21 = (void *)*((_QWORD *)&v26 + 1);
    }
    if ( v21 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v21);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x180007238  mov     [rsp+Buf1], rdx
0x18000723d  push    rbx
0x18000723e  push    rbp
0x18000723f  push    rsi
0x180007240  push    rdi
0x180007241  push    r12
0x180007243  push    r13
0x180007245  push    r14
0x180007247  push    r15
0x180007249  sub     rsp, 58h
0x18000724d  mov     ebp, [rsp+98h+arg_28]
0x180007254  mov     r13, r9
0x180007257  mov     r12, [rsp+98h+arg_20]
0x18000725f  mov     r15, r8
0x180007262  mov     [rsp+98h+var_70], ebp; unsigned int
0x180007266  mov     rsi, rdx
0x180007269  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000726e  mov     rbx, rcx
0x180007271  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007276  test    al, al
0x180007278  jz      short loc_180007281
0x18000727a  mov     al, 1
0x18000727c  jmp     loc_1800073C2
0x180007281  lea     rdx, [r12+20h]
0x180007286  add     rdx, r15; unsigned __int64
0x180007289  lea     r14, [rbx+18h]
0x18000728d  cmp     qword ptr [r14], 0
0x180007291  jnz     loc_18000739A
0x180007297  xorps   xmm0, xmm0
0x18000729a  lea     rcx, [rsp+98h+var_68]; this
0x18000729f  xorps   xmm1, xmm1
0x1800072a2  add     rdx, 0Ah; unsigned __int64
0x1800072a6  movdqu  [rsp+98h+var_68], xmm0
0x1800072ac  movdqu  [rsp+98h+var_58], xmm1
0x1800072b2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800072b7  test    al, al
0x1800072b9  jz      loc_18000737A
0x1800072bf  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800072c4  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800072c9  sub     rdi, rsi
0x1800072cc  cmp     rdi, 0Ah
0x1800072d0  jb      loc_1800073D3
0x1800072d6  mov     rbp, [rbx+30h]
0x1800072da  mov     qword ptr [rbx+30h], 0
0x1800072e2  test    rbp, rbp
0x1800072e5  jz      short loc_1800072FB
0x1800072e7  call    cs:__imp_GetProcessHeap
0x1800072ed  mov     r8, rbp; lpMem
0x1800072f0  xor     edx, edx; dwFlags
0x1800072f2  mov     rcx, rax; hHeap
0x1800072f5  call    cs:__imp_HeapFree
0x1800072fb  mov     [r14], rsi
0x1800072fe  lea     rax, [rdi+rsi]
0x180007302  mov     [rbx+28h], rax
0x180007306  xor     edi, edi
0x180007308  xor     eax, eax
0x18000730a  mov     byte ptr [rbx+39h], 0
0x18000730e  mov     [rsi], ax
0x180007311  movzx   eax, word ptr [rbx]
0x180007314  mov     [rsi+2], ax
0x180007318  movzx   eax, word ptr [rbx+2]
0x18000731c  mov     [rsi+4], ax
0x180007320  mov     al, [rbx+4]
0x180007323  mov     [rsi+8], al
0x180007326  movzx   eax, word ptr [rbx+6]
0x18000732a  mov     [rsi+6], ax
0x18000732e  mov     al, [rbx+8]
0x180007331  mov     [rsi+9], al
0x180007334  mov     rax, [r14]
0x180007337  add     rax, 0Ah
0x18000733b  mov     [rbx+20h], rax
0x18000733f  mov     rsi, [rbx+30h]
0x180007343  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180007348  mov     [rbx+30h], rax
0x18000734c  test    rsi, rsi
0x18000734f  jz      short loc_180007365
0x180007351  call    cs:__imp_GetProcessHeap
0x180007357  mov     r8, rsi; lpMem
0x18000735a  xor     edx, edx; dwFlags
0x18000735c  mov     rcx, rax; hHeap
0x18000735f  call    cs:__imp_HeapFree
0x180007365  mov     rsi, [rsp+98h+Buf1]
0x18000736d  mov     ebp, [rsp+98h+arg_28]
0x180007374  mov     byte ptr [rbx+3Ah], 1
0x180007378  jmp     short loc_18000737F
0x18000737a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000737f  test    rdi, rdi
0x180007382  jz      short loc_1800073A8
0x180007384  call    cs:__imp_GetProcessHeap
0x18000738a  mov     r8, rdi; lpMem
0x18000738d  xor     edx, edx; dwFlags
0x18000738f  mov     rcx, rax; hHeap
0x180007392  call    cs:__imp_HeapFree
0x180007398  jmp     short loc_1800073A8
0x18000739a  cmp     byte ptr [rbx+3Ah], 0
0x18000739e  jz      short loc_1800073A8
0x1800073a0  mov     rcx, r14; this
0x1800073a3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800073a8  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800073ac  mov     r9, r13; void *
0x1800073af  mov     r8, r15; Size
0x1800073b2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800073b7  mov     rdx, rsi; Buf1
0x1800073ba  mov     rcx, rbx; this
0x1800073bd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800073c2  add     rsp, 58h
0x1800073c6  pop     r15
0x1800073c8  pop     r14
0x1800073ca  pop     r13
0x1800073cc  pop     r12
0x1800073ce  pop     rdi
0x1800073cf  pop     rsi
0x1800073d0  pop     rbp
0x1800073d1  pop     rbx
0x1800073d2  retn
0x1800073d3  mov     rcx, [rsp+98h]; this
0x1800073db  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
