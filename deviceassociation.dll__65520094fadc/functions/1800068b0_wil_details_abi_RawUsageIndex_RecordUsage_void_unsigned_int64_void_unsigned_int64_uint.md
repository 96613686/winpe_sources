# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800068b0`
- end: `0x180006a59`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004070`
- `0x1800067b0`
- `0x1800067e4`

## callees

- `0x1800068b0`
- `0x180006a60`
- `0x180008468`
- `0x1800084cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000695f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000695f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000696d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000696d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a0a`

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
0x1800068b0  mov     [rsp+Buf1], rdx
0x1800068b5  push    rbx
0x1800068b6  push    rbp
0x1800068b7  push    rsi
0x1800068b8  push    rdi
0x1800068b9  push    r12
0x1800068bb  push    r13
0x1800068bd  push    r14
0x1800068bf  push    r15
0x1800068c1  sub     rsp, 58h
0x1800068c5  mov     ebp, [rsp+98h+arg_28]
0x1800068cc  mov     r13, r9
0x1800068cf  mov     r12, [rsp+98h+arg_20]
0x1800068d7  mov     r15, r8
0x1800068da  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800068de  mov     rsi, rdx
0x1800068e1  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800068e6  mov     rbx, rcx
0x1800068e9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800068ee  test    al, al
0x1800068f0  jz      short loc_1800068F9
0x1800068f2  mov     al, 1
0x1800068f4  jmp     loc_180006A3A
0x1800068f9  lea     rdx, [r12+20h]
0x1800068fe  add     rdx, r15; unsigned __int64
0x180006901  lea     r14, [rbx+18h]
0x180006905  cmp     qword ptr [r14], 0
0x180006909  jnz     loc_180006A12
0x18000690f  xorps   xmm0, xmm0
0x180006912  lea     rcx, [rsp+98h+var_68]; this
0x180006917  xorps   xmm1, xmm1
0x18000691a  add     rdx, 0Ah; unsigned __int64
0x18000691e  movdqu  [rsp+98h+var_68], xmm0
0x180006924  movdqu  [rsp+98h+var_58], xmm1
0x18000692a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000692f  test    al, al
0x180006931  jz      loc_1800069F2
0x180006937  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000693c  mov     rsi, qword ptr [rsp+98h+var_68]
0x180006941  sub     rdi, rsi
0x180006944  cmp     rdi, 0Ah
0x180006948  jb      loc_180006A4B
0x18000694e  mov     rbp, [rbx+30h]
0x180006952  mov     qword ptr [rbx+30h], 0
0x18000695a  test    rbp, rbp
0x18000695d  jz      short loc_180006973
0x18000695f  call    cs:__imp_GetProcessHeap
0x180006965  mov     r8, rbp; lpMem
0x180006968  xor     edx, edx; dwFlags
0x18000696a  mov     rcx, rax; hHeap
0x18000696d  call    cs:__imp_HeapFree
0x180006973  mov     [r14], rsi
0x180006976  lea     rax, [rdi+rsi]
0x18000697a  mov     [rbx+28h], rax
0x18000697e  xor     edi, edi
0x180006980  xor     eax, eax
0x180006982  mov     byte ptr [rbx+39h], 0
0x180006986  mov     [rsi], ax
0x180006989  movzx   eax, word ptr [rbx]
0x18000698c  mov     [rsi+2], ax
0x180006990  movzx   eax, word ptr [rbx+2]
0x180006994  mov     [rsi+4], ax
0x180006998  mov     al, [rbx+4]
0x18000699b  mov     [rsi+8], al
0x18000699e  movzx   eax, word ptr [rbx+6]
0x1800069a2  mov     [rsi+6], ax
0x1800069a6  mov     al, [rbx+8]
0x1800069a9  mov     [rsi+9], al
0x1800069ac  mov     rax, [r14]
0x1800069af  add     rax, 0Ah
0x1800069b3  mov     [rbx+20h], rax
0x1800069b7  mov     rsi, [rbx+30h]
0x1800069bb  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800069c0  mov     [rbx+30h], rax
0x1800069c4  test    rsi, rsi
0x1800069c7  jz      short loc_1800069DD
0x1800069c9  call    cs:__imp_GetProcessHeap
0x1800069cf  mov     r8, rsi; lpMem
0x1800069d2  xor     edx, edx; dwFlags
0x1800069d4  mov     rcx, rax; hHeap
0x1800069d7  call    cs:__imp_HeapFree
0x1800069dd  mov     rsi, [rsp+98h+Buf1]
0x1800069e5  mov     ebp, [rsp+98h+arg_28]
0x1800069ec  mov     byte ptr [rbx+3Ah], 1
0x1800069f0  jmp     short loc_1800069F7
0x1800069f2  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800069f7  test    rdi, rdi
0x1800069fa  jz      short loc_180006A20
0x1800069fc  call    cs:__imp_GetProcessHeap
0x180006a02  mov     r8, rdi; lpMem
0x180006a05  xor     edx, edx; dwFlags
0x180006a07  mov     rcx, rax; hHeap
0x180006a0a  call    cs:__imp_HeapFree
0x180006a10  jmp     short loc_180006A20
0x180006a12  cmp     byte ptr [rbx+3Ah], 0
0x180006a16  jz      short loc_180006A20
0x180006a18  mov     rcx, r14; this
0x180006a1b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006a20  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006a24  mov     r9, r13; void *
0x180006a27  mov     r8, r15; Size
0x180006a2a  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006a2f  mov     rdx, rsi; Buf1
0x180006a32  mov     rcx, rbx; this
0x180006a35  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006a3a  add     rsp, 58h
0x180006a3e  pop     r15
0x180006a40  pop     r14
0x180006a42  pop     r13
0x180006a44  pop     r12
0x180006a46  pop     rdi
0x180006a47  pop     rsi
0x180006a48  pop     rbp
0x180006a49  pop     rbx
0x180006a4a  retn
0x180006a4b  mov     rcx, [rsp+98h]; this
0x180006a53  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
