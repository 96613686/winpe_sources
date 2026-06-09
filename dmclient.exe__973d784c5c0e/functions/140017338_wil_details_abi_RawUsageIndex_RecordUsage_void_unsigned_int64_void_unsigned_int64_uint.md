# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140017338`
- end: `0x140017506`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `462`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140015f10`
- `0x140017224`
- `0x14001725c`

## callees

- `0x140017338`
- `0x14001750c`
- `0x140018924`
- `0x14001898c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400173e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001745d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001749c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400173e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001745d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001749c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400173fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400174b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400173fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400174b0`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
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
0x140017338  mov     [rsp+Buf1], rdx
0x14001733d  push    rbx
0x14001733e  push    rbp
0x14001733f  push    rsi
0x140017340  push    rdi
0x140017341  push    r12
0x140017343  push    r13
0x140017345  push    r14
0x140017347  push    r15
0x140017349  sub     rsp, 58h
0x14001734d  mov     ebp, [rsp+98h+arg_28]
0x140017354  mov     r13, r9
0x140017357  mov     r12, [rsp+98h+arg_20]
0x14001735f  mov     r15, r8
0x140017362  mov     [rsp+98h+var_70], ebp; unsigned int
0x140017366  mov     rsi, rdx
0x140017369  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14001736e  mov     rbx, rcx
0x140017371  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140017376  test    al, al
0x140017378  jz      short loc_140017381
0x14001737a  mov     al, 1
0x14001737c  jmp     loc_1400174E6
0x140017381  lea     rdx, [r12+20h]
0x140017386  add     rdx, r15; unsigned __int64
0x140017389  lea     r14, [rbx+18h]
0x14001738d  cmp     qword ptr [r14], 0
0x140017391  jnz     loc_1400174BE
0x140017397  xorps   xmm0, xmm0
0x14001739a  lea     rcx, [rsp+98h+var_68]; this
0x14001739f  xorps   xmm1, xmm1
0x1400173a2  add     rdx, 0Ah; unsigned __int64
0x1400173a6  movdqu  [rsp+98h+var_68], xmm0
0x1400173ac  movdqu  [rsp+98h+var_58], xmm1
0x1400173b2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400173b7  test    al, al
0x1400173b9  jz      loc_140017492
0x1400173bf  mov     rdi, qword ptr [rsp+98h+var_58]
0x1400173c4  mov     rsi, qword ptr [rsp+98h+var_68]
0x1400173c9  sub     rdi, rsi
0x1400173cc  cmp     rdi, 0Ah
0x1400173d0  jb      loc_1400174F8
0x1400173d6  mov     rbp, [rbx+30h]
0x1400173da  mov     qword ptr [rbx+30h], 0
0x1400173e2  test    rbp, rbp
0x1400173e5  jz      short loc_140017407
0x1400173e7  call    cs:__imp_GetProcessHeap
0x1400173ee  nop     dword ptr [rax+rax+00h]
0x1400173f3  mov     r8, rbp; lpMem
0x1400173f6  xor     edx, edx; dwFlags
0x1400173f8  mov     rcx, rax; hHeap
0x1400173fb  call    cs:__imp_HeapFree
0x140017402  nop     dword ptr [rax+rax+00h]
0x140017407  mov     [r14], rsi
0x14001740a  lea     rax, [rdi+rsi]
0x14001740e  mov     [rbx+28h], rax
0x140017412  xor     edi, edi
0x140017414  xor     eax, eax
0x140017416  mov     byte ptr [rbx+39h], 0
0x14001741a  mov     [rsi], ax
0x14001741d  movzx   eax, word ptr [rbx]
0x140017420  mov     [rsi+2], ax
0x140017424  movzx   eax, word ptr [rbx+2]
0x140017428  mov     [rsi+4], ax
0x14001742c  mov     al, [rbx+4]
0x14001742f  mov     [rsi+8], al
0x140017432  movzx   eax, word ptr [rbx+6]
0x140017436  mov     [rsi+6], ax
0x14001743a  mov     al, [rbx+8]
0x14001743d  mov     [rsi+9], al
0x140017440  mov     rax, [r14]
0x140017443  add     rax, 0Ah
0x140017447  mov     [rbx+20h], rax
0x14001744b  mov     rsi, [rbx+30h]
0x14001744f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140017454  mov     [rbx+30h], rax
0x140017458  test    rsi, rsi
0x14001745b  jz      short loc_14001747D
0x14001745d  call    cs:__imp_GetProcessHeap
0x140017464  nop     dword ptr [rax+rax+00h]
0x140017469  mov     r8, rsi; lpMem
0x14001746c  xor     edx, edx; dwFlags
0x14001746e  mov     rcx, rax; hHeap
0x140017471  call    cs:__imp_HeapFree
0x140017478  nop     dword ptr [rax+rax+00h]
0x14001747d  mov     rsi, [rsp+98h+Buf1]
0x140017485  mov     ebp, [rsp+98h+arg_28]
0x14001748c  mov     byte ptr [rbx+3Ah], 1
0x140017490  jmp     short loc_140017497
0x140017492  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x140017497  test    rdi, rdi
0x14001749a  jz      short loc_1400174CC
0x14001749c  call    cs:__imp_GetProcessHeap
0x1400174a3  nop     dword ptr [rax+rax+00h]
0x1400174a8  mov     r8, rdi; lpMem
0x1400174ab  xor     edx, edx; dwFlags
0x1400174ad  mov     rcx, rax; hHeap
0x1400174b0  call    cs:__imp_HeapFree
0x1400174b7  nop     dword ptr [rax+rax+00h]
0x1400174bc  jmp     short loc_1400174CC
0x1400174be  cmp     byte ptr [rbx+3Ah], 0
0x1400174c2  jz      short loc_1400174CC
0x1400174c4  mov     rcx, r14; this
0x1400174c7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400174cc  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400174d0  mov     r9, r13; void *
0x1400174d3  mov     r8, r15; Size
0x1400174d6  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400174db  mov     rdx, rsi; Buf1
0x1400174de  mov     rcx, rbx; this
0x1400174e1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400174e6  add     rsp, 58h
0x1400174ea  pop     r15
0x1400174ec  pop     r14
0x1400174ee  pop     r13
0x1400174f0  pop     r12
0x1400174f2  pop     rdi
0x1400174f3  pop     rsi
0x1400174f4  pop     rbp
0x1400174f5  pop     rbx
0x1400174f6  retn
0x1400174f8  mov     rcx, [rsp+98h]; this
0x140017500  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
