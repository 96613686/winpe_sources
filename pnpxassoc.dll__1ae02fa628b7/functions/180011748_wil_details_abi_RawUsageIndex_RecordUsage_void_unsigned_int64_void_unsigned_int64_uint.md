# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180011748`
- end: `0x1800118f1`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800107c0`
- `0x180011648`
- `0x18001167c`

## callees

- `0x180011748`
- `0x1800118f8`
- `0x180012994`
- `0x1800129e4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180011805`
- `KERNEL32!HeapFree` at `0x18001186f`
- `KERNEL32!HeapFree` at `0x1800118a2`
- `KERNEL32!HeapFree` at `0x180011805`
- `KERNEL32!HeapFree` at `0x18001186f`
- `KERNEL32!HeapFree` at `0x1800118a2`
- `KERNEL32!GetProcessHeap` at `0x1800117f7`
- `KERNEL32!GetProcessHeap` at `0x180011861`
- `KERNEL32!GetProcessHeap` at `0x180011894`
- `KERNEL32!GetProcessHeap` at `0x1800117f7`
- `KERNEL32!GetProcessHeap` at `0x180011861`
- `KERNEL32!GetProcessHeap` at `0x180011894`

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
0x180011748  mov     [rsp+Buf1], rdx
0x18001174d  push    rbx
0x18001174e  push    rbp
0x18001174f  push    rsi
0x180011750  push    rdi
0x180011751  push    r12
0x180011753  push    r13
0x180011755  push    r14
0x180011757  push    r15
0x180011759  sub     rsp, 58h
0x18001175d  mov     ebp, [rsp+98h+arg_28]
0x180011764  mov     r13, r9
0x180011767  mov     r12, [rsp+98h+arg_20]
0x18001176f  mov     r15, r8
0x180011772  mov     [rsp+98h+var_70], ebp; unsigned int
0x180011776  mov     rsi, rdx
0x180011779  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18001177e  mov     rbx, rcx
0x180011781  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180011786  test    al, al
0x180011788  jz      short loc_180011791
0x18001178a  mov     al, 1
0x18001178c  jmp     loc_1800118D2
0x180011791  lea     rdx, [r12+20h]
0x180011796  add     rdx, r15; unsigned __int64
0x180011799  lea     r14, [rbx+18h]
0x18001179d  cmp     qword ptr [r14], 0
0x1800117a1  jnz     loc_1800118AA
0x1800117a7  xorps   xmm0, xmm0
0x1800117aa  lea     rcx, [rsp+98h+var_68]; this
0x1800117af  xorps   xmm1, xmm1
0x1800117b2  add     rdx, 0Ah; unsigned __int64
0x1800117b6  movdqu  [rsp+98h+var_68], xmm0
0x1800117bc  movdqu  [rsp+98h+var_58], xmm1
0x1800117c2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800117c7  test    al, al
0x1800117c9  jz      loc_18001188A
0x1800117cf  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800117d4  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800117d9  sub     rdi, rsi
0x1800117dc  cmp     rdi, 0Ah
0x1800117e0  jb      loc_1800118E3
0x1800117e6  mov     rbp, [rbx+30h]
0x1800117ea  mov     qword ptr [rbx+30h], 0
0x1800117f2  test    rbp, rbp
0x1800117f5  jz      short loc_18001180B
0x1800117f7  call    cs:__imp_GetProcessHeap
0x1800117fd  mov     r8, rbp; lpMem
0x180011800  xor     edx, edx; dwFlags
0x180011802  mov     rcx, rax; hHeap
0x180011805  call    cs:__imp_HeapFree
0x18001180b  mov     [r14], rsi
0x18001180e  lea     rax, [rdi+rsi]
0x180011812  mov     [rbx+28h], rax
0x180011816  xor     edi, edi
0x180011818  xor     eax, eax
0x18001181a  mov     byte ptr [rbx+39h], 0
0x18001181e  mov     [rsi], ax
0x180011821  movzx   eax, word ptr [rbx]
0x180011824  mov     [rsi+2], ax
0x180011828  movzx   eax, word ptr [rbx+2]
0x18001182c  mov     [rsi+4], ax
0x180011830  mov     al, [rbx+4]
0x180011833  mov     [rsi+8], al
0x180011836  movzx   eax, word ptr [rbx+6]
0x18001183a  mov     [rsi+6], ax
0x18001183e  mov     al, [rbx+8]
0x180011841  mov     [rsi+9], al
0x180011844  mov     rax, [r14]
0x180011847  add     rax, 0Ah
0x18001184b  mov     [rbx+20h], rax
0x18001184f  mov     rsi, [rbx+30h]
0x180011853  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180011858  mov     [rbx+30h], rax
0x18001185c  test    rsi, rsi
0x18001185f  jz      short loc_180011875
0x180011861  call    cs:__imp_GetProcessHeap
0x180011867  mov     r8, rsi; lpMem
0x18001186a  xor     edx, edx; dwFlags
0x18001186c  mov     rcx, rax; hHeap
0x18001186f  call    cs:__imp_HeapFree
0x180011875  mov     rsi, [rsp+98h+Buf1]
0x18001187d  mov     ebp, [rsp+98h+arg_28]
0x180011884  mov     byte ptr [rbx+3Ah], 1
0x180011888  jmp     short loc_18001188F
0x18001188a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18001188f  test    rdi, rdi
0x180011892  jz      short loc_1800118B8
0x180011894  call    cs:__imp_GetProcessHeap
0x18001189a  mov     r8, rdi; lpMem
0x18001189d  xor     edx, edx; dwFlags
0x18001189f  mov     rcx, rax; hHeap
0x1800118a2  call    cs:__imp_HeapFree
0x1800118a8  jmp     short loc_1800118B8
0x1800118aa  cmp     byte ptr [rbx+3Ah], 0
0x1800118ae  jz      short loc_1800118B8
0x1800118b0  mov     rcx, r14; this
0x1800118b3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800118b8  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800118bc  mov     r9, r13; void *
0x1800118bf  mov     r8, r15; Size
0x1800118c2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800118c7  mov     rdx, rsi; Buf1
0x1800118ca  mov     rcx, rbx; this
0x1800118cd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800118d2  add     rsp, 58h
0x1800118d6  pop     r15
0x1800118d8  pop     r14
0x1800118da  pop     r13
0x1800118dc  pop     r12
0x1800118de  pop     rdi
0x1800118df  pop     rsi
0x1800118e0  pop     rbp
0x1800118e1  pop     rbx
0x1800118e2  retn
0x1800118e3  mov     rcx, [rsp+98h]; this
0x1800118eb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
