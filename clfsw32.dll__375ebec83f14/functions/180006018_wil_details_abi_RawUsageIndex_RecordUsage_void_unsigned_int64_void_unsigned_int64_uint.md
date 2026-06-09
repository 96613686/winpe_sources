# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006018`
- end: `0x1800061e6`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `462`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003750`
- `0x180005f08`
- `0x180005f40`

## callees

- `0x180006018`
- `0x1800061ec`
- `0x180007e2c`
- `0x180007f3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000613d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000617c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000613d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000617c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006190`

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
0x180006018  mov     [rsp+Buf1], rdx
0x18000601d  push    rbx
0x18000601e  push    rbp
0x18000601f  push    rsi
0x180006020  push    rdi
0x180006021  push    r12
0x180006023  push    r13
0x180006025  push    r14
0x180006027  push    r15
0x180006029  sub     rsp, 58h
0x18000602d  mov     ebp, [rsp+98h+arg_28]
0x180006034  mov     r13, r9
0x180006037  mov     r12, [rsp+98h+arg_20]
0x18000603f  mov     r15, r8
0x180006042  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006046  mov     rsi, rdx
0x180006049  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000604e  mov     rbx, rcx
0x180006051  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006056  test    al, al
0x180006058  jz      short loc_180006061
0x18000605a  mov     al, 1
0x18000605c  jmp     loc_1800061C6
0x180006061  lea     rdx, [r12+20h]
0x180006066  add     rdx, r15; unsigned __int64
0x180006069  lea     r14, [rbx+18h]
0x18000606d  cmp     qword ptr [r14], 0
0x180006071  jnz     loc_18000619E
0x180006077  xorps   xmm0, xmm0
0x18000607a  lea     rcx, [rsp+98h+var_68]; this
0x18000607f  xorps   xmm1, xmm1
0x180006082  add     rdx, 0Ah; unsigned __int64
0x180006086  movdqu  [rsp+98h+var_68], xmm0
0x18000608c  movdqu  [rsp+98h+var_58], xmm1
0x180006092  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006097  test    al, al
0x180006099  jz      loc_180006172
0x18000609f  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800060a4  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800060a9  sub     rdi, rsi
0x1800060ac  cmp     rdi, 0Ah
0x1800060b0  jb      loc_1800061D8
0x1800060b6  mov     rbp, [rbx+30h]
0x1800060ba  mov     qword ptr [rbx+30h], 0
0x1800060c2  test    rbp, rbp
0x1800060c5  jz      short loc_1800060E7
0x1800060c7  call    cs:__imp_GetProcessHeap
0x1800060ce  nop     dword ptr [rax+rax+00h]
0x1800060d3  mov     r8, rbp; lpMem
0x1800060d6  xor     edx, edx; dwFlags
0x1800060d8  mov     rcx, rax; hHeap
0x1800060db  call    cs:__imp_HeapFree
0x1800060e2  nop     dword ptr [rax+rax+00h]
0x1800060e7  mov     [r14], rsi
0x1800060ea  lea     rax, [rdi+rsi]
0x1800060ee  mov     [rbx+28h], rax
0x1800060f2  xor     edi, edi
0x1800060f4  xor     eax, eax
0x1800060f6  mov     byte ptr [rbx+39h], 0
0x1800060fa  mov     [rsi], ax
0x1800060fd  movzx   eax, word ptr [rbx]
0x180006100  mov     [rsi+2], ax
0x180006104  movzx   eax, word ptr [rbx+2]
0x180006108  mov     [rsi+4], ax
0x18000610c  mov     al, [rbx+4]
0x18000610f  mov     [rsi+8], al
0x180006112  movzx   eax, word ptr [rbx+6]
0x180006116  mov     [rsi+6], ax
0x18000611a  mov     al, [rbx+8]
0x18000611d  mov     [rsi+9], al
0x180006120  mov     rax, [r14]
0x180006123  add     rax, 0Ah
0x180006127  mov     [rbx+20h], rax
0x18000612b  mov     rsi, [rbx+30h]
0x18000612f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180006134  mov     [rbx+30h], rax
0x180006138  test    rsi, rsi
0x18000613b  jz      short loc_18000615D
0x18000613d  call    cs:__imp_GetProcessHeap
0x180006144  nop     dword ptr [rax+rax+00h]
0x180006149  mov     r8, rsi; lpMem
0x18000614c  xor     edx, edx; dwFlags
0x18000614e  mov     rcx, rax; hHeap
0x180006151  call    cs:__imp_HeapFree
0x180006158  nop     dword ptr [rax+rax+00h]
0x18000615d  mov     rsi, [rsp+98h+Buf1]
0x180006165  mov     ebp, [rsp+98h+arg_28]
0x18000616c  mov     byte ptr [rbx+3Ah], 1
0x180006170  jmp     short loc_180006177
0x180006172  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180006177  test    rdi, rdi
0x18000617a  jz      short loc_1800061AC
0x18000617c  call    cs:__imp_GetProcessHeap
0x180006183  nop     dword ptr [rax+rax+00h]
0x180006188  mov     r8, rdi; lpMem
0x18000618b  xor     edx, edx; dwFlags
0x18000618d  mov     rcx, rax; hHeap
0x180006190  call    cs:__imp_HeapFree
0x180006197  nop     dword ptr [rax+rax+00h]
0x18000619c  jmp     short loc_1800061AC
0x18000619e  cmp     byte ptr [rbx+3Ah], 0
0x1800061a2  jz      short loc_1800061AC
0x1800061a4  mov     rcx, r14; this
0x1800061a7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800061ac  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800061b0  mov     r9, r13; void *
0x1800061b3  mov     r8, r15; Size
0x1800061b6  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800061bb  mov     rdx, rsi; Buf1
0x1800061be  mov     rcx, rbx; this
0x1800061c1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800061c6  add     rsp, 58h
0x1800061ca  pop     r15
0x1800061cc  pop     r14
0x1800061ce  pop     r13
0x1800061d0  pop     r12
0x1800061d2  pop     rdi
0x1800061d3  pop     rsi
0x1800061d4  pop     rbp
0x1800061d5  pop     rbx
0x1800061d6  retn
0x1800061d8  mov     rcx, [rsp+98h]; this
0x1800061e0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
