# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140009828`
- end: `0x1400099d1`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140005ab0`
- `0x140009724`
- `0x140009758`

## callees

- `0x140009828`
- `0x1400099d8`
- `0x14000ce18`
- `0x14000d04c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400098d7`
- `KERNEL32!GetProcessHeap` at `0x140009941`
- `KERNEL32!GetProcessHeap` at `0x140009974`
- `KERNEL32!GetProcessHeap` at `0x1400098d7`
- `KERNEL32!GetProcessHeap` at `0x140009941`
- `KERNEL32!GetProcessHeap` at `0x140009974`
- `KERNEL32!HeapFree` at `0x1400098e5`
- `KERNEL32!HeapFree` at `0x14000994f`
- `KERNEL32!HeapFree` at `0x140009982`
- `KERNEL32!HeapFree` at `0x1400098e5`
- `KERNEL32!HeapFree` at `0x14000994f`
- `KERNEL32!HeapFree` at `0x140009982`

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
0x140009828  mov     [rsp+Buf1], rdx
0x14000982d  push    rbx
0x14000982e  push    rbp
0x14000982f  push    rsi
0x140009830  push    rdi
0x140009831  push    r12
0x140009833  push    r13
0x140009835  push    r14
0x140009837  push    r15
0x140009839  sub     rsp, 58h
0x14000983d  mov     ebp, [rsp+98h+arg_28]
0x140009844  mov     r13, r9
0x140009847  mov     r12, [rsp+98h+arg_20]
0x14000984f  mov     r15, r8
0x140009852  mov     [rsp+98h+var_70], ebp; unsigned int
0x140009856  mov     rsi, rdx
0x140009859  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000985e  mov     rbx, rcx
0x140009861  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140009866  test    al, al
0x140009868  jz      short loc_140009871
0x14000986a  mov     al, 1
0x14000986c  jmp     loc_1400099B2
0x140009871  lea     rdx, [r12+20h]
0x140009876  add     rdx, r15; unsigned __int64
0x140009879  lea     r14, [rbx+18h]
0x14000987d  cmp     qword ptr [r14], 0
0x140009881  jnz     loc_14000998A
0x140009887  xorps   xmm0, xmm0
0x14000988a  lea     rcx, [rsp+98h+var_68]; this
0x14000988f  xorps   xmm1, xmm1
0x140009892  add     rdx, 0Ah; unsigned __int64
0x140009896  movdqu  [rsp+98h+var_68], xmm0
0x14000989c  movdqu  [rsp+98h+var_58], xmm1
0x1400098a2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400098a7  test    al, al
0x1400098a9  jz      loc_14000996A
0x1400098af  mov     rdi, qword ptr [rsp+98h+var_58]
0x1400098b4  mov     rsi, qword ptr [rsp+98h+var_68]
0x1400098b9  sub     rdi, rsi
0x1400098bc  cmp     rdi, 0Ah
0x1400098c0  jb      loc_1400099C3
0x1400098c6  mov     rbp, [rbx+30h]
0x1400098ca  mov     qword ptr [rbx+30h], 0
0x1400098d2  test    rbp, rbp
0x1400098d5  jz      short loc_1400098EB
0x1400098d7  call    cs:__imp_GetProcessHeap
0x1400098dd  mov     r8, rbp; lpMem
0x1400098e0  xor     edx, edx; dwFlags
0x1400098e2  mov     rcx, rax; hHeap
0x1400098e5  call    cs:__imp_HeapFree
0x1400098eb  mov     [r14], rsi
0x1400098ee  lea     rax, [rdi+rsi]
0x1400098f2  mov     [rbx+28h], rax
0x1400098f6  xor     edi, edi
0x1400098f8  xor     eax, eax
0x1400098fa  mov     byte ptr [rbx+39h], 0
0x1400098fe  mov     [rsi], ax
0x140009901  movzx   eax, word ptr [rbx]
0x140009904  mov     [rsi+2], ax
0x140009908  movzx   eax, word ptr [rbx+2]
0x14000990c  mov     [rsi+4], ax
0x140009910  mov     al, [rbx+4]
0x140009913  mov     [rsi+8], al
0x140009916  movzx   eax, word ptr [rbx+6]
0x14000991a  mov     [rsi+6], ax
0x14000991e  mov     al, [rbx+8]
0x140009921  mov     [rsi+9], al
0x140009924  mov     rax, [r14]
0x140009927  add     rax, 0Ah
0x14000992b  mov     [rbx+20h], rax
0x14000992f  mov     rsi, [rbx+30h]
0x140009933  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140009938  mov     [rbx+30h], rax
0x14000993c  test    rsi, rsi
0x14000993f  jz      short loc_140009955
0x140009941  call    cs:__imp_GetProcessHeap
0x140009947  mov     r8, rsi; lpMem
0x14000994a  xor     edx, edx; dwFlags
0x14000994c  mov     rcx, rax; hHeap
0x14000994f  call    cs:__imp_HeapFree
0x140009955  mov     rsi, [rsp+98h+Buf1]
0x14000995d  mov     ebp, [rsp+98h+arg_28]
0x140009964  mov     byte ptr [rbx+3Ah], 1
0x140009968  jmp     short loc_14000996F
0x14000996a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000996f  test    rdi, rdi
0x140009972  jz      short loc_140009998
0x140009974  call    cs:__imp_GetProcessHeap
0x14000997a  mov     r8, rdi; lpMem
0x14000997d  xor     edx, edx; dwFlags
0x14000997f  mov     rcx, rax; hHeap
0x140009982  call    cs:__imp_HeapFree
0x140009988  jmp     short loc_140009998
0x14000998a  cmp     byte ptr [rbx+3Ah], 0
0x14000998e  jz      short loc_140009998
0x140009990  mov     rcx, r14; this
0x140009993  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009998  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000999c  mov     r9, r13; void *
0x14000999f  mov     r8, r15; Size
0x1400099a2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400099a7  mov     rdx, rsi; Buf1
0x1400099aa  mov     rcx, rbx; this
0x1400099ad  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400099b2  add     rsp, 58h
0x1400099b6  pop     r15
0x1400099b8  pop     r14
0x1400099ba  pop     r13
0x1400099bc  pop     r12
0x1400099be  pop     rdi
0x1400099bf  pop     rsi
0x1400099c0  pop     rbp
0x1400099c1  pop     rbx
0x1400099c2  retn
0x1400099c3  mov     rcx, [rsp+98h]; this
0x1400099cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
