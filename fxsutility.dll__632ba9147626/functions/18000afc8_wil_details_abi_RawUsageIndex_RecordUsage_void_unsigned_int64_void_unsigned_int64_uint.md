# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000afc8`
- end: `0x18000b171`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008750`
- `0x18000aec4`
- `0x18000aef8`

## callees

- `0x18000afc8`
- `0x18000b178`
- `0x18000cf08`
- `0x18000d020`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000b085`
- `KERNEL32!HeapFree` at `0x18000b0ef`
- `KERNEL32!HeapFree` at `0x18000b122`
- `KERNEL32!HeapFree` at `0x18000b085`
- `KERNEL32!HeapFree` at `0x18000b0ef`
- `KERNEL32!HeapFree` at `0x18000b122`
- `KERNEL32!GetProcessHeap` at `0x18000b077`
- `KERNEL32!GetProcessHeap` at `0x18000b0e1`
- `KERNEL32!GetProcessHeap` at `0x18000b114`
- `KERNEL32!GetProcessHeap` at `0x18000b077`
- `KERNEL32!GetProcessHeap` at `0x18000b0e1`
- `KERNEL32!GetProcessHeap` at `0x18000b114`

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
0x18000afc8  mov     [rsp+Buf1], rdx
0x18000afcd  push    rbx
0x18000afce  push    rbp
0x18000afcf  push    rsi
0x18000afd0  push    rdi
0x18000afd1  push    r12
0x18000afd3  push    r13
0x18000afd5  push    r14
0x18000afd7  push    r15
0x18000afd9  sub     rsp, 58h
0x18000afdd  mov     ebp, [rsp+98h+arg_28]
0x18000afe4  mov     r13, r9
0x18000afe7  mov     r12, [rsp+98h+arg_20]
0x18000afef  mov     r15, r8
0x18000aff2  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000aff6  mov     rsi, rdx
0x18000aff9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000affe  mov     rbx, rcx
0x18000b001  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000b006  test    al, al
0x18000b008  jz      short loc_18000B011
0x18000b00a  mov     al, 1
0x18000b00c  jmp     loc_18000B152
0x18000b011  lea     rdx, [r12+20h]
0x18000b016  add     rdx, r15; unsigned __int64
0x18000b019  lea     r14, [rbx+18h]
0x18000b01d  cmp     qword ptr [r14], 0
0x18000b021  jnz     loc_18000B12A
0x18000b027  xorps   xmm0, xmm0
0x18000b02a  lea     rcx, [rsp+98h+var_68]; this
0x18000b02f  xorps   xmm1, xmm1
0x18000b032  add     rdx, 0Ah; unsigned __int64
0x18000b036  movdqu  [rsp+98h+var_68], xmm0
0x18000b03c  movdqu  [rsp+98h+var_58], xmm1
0x18000b042  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b047  test    al, al
0x18000b049  jz      loc_18000B10A
0x18000b04f  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000b054  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000b059  sub     rdi, rsi
0x18000b05c  cmp     rdi, 0Ah
0x18000b060  jb      loc_18000B163
0x18000b066  mov     rbp, [rbx+30h]
0x18000b06a  mov     qword ptr [rbx+30h], 0
0x18000b072  test    rbp, rbp
0x18000b075  jz      short loc_18000B08B
0x18000b077  call    cs:__imp_GetProcessHeap
0x18000b07d  mov     r8, rbp; lpMem
0x18000b080  xor     edx, edx; dwFlags
0x18000b082  mov     rcx, rax; hHeap
0x18000b085  call    cs:__imp_HeapFree
0x18000b08b  mov     [r14], rsi
0x18000b08e  lea     rax, [rdi+rsi]
0x18000b092  mov     [rbx+28h], rax
0x18000b096  xor     edi, edi
0x18000b098  xor     eax, eax
0x18000b09a  mov     byte ptr [rbx+39h], 0
0x18000b09e  mov     [rsi], ax
0x18000b0a1  movzx   eax, word ptr [rbx]
0x18000b0a4  mov     [rsi+2], ax
0x18000b0a8  movzx   eax, word ptr [rbx+2]
0x18000b0ac  mov     [rsi+4], ax
0x18000b0b0  mov     al, [rbx+4]
0x18000b0b3  mov     [rsi+8], al
0x18000b0b6  movzx   eax, word ptr [rbx+6]
0x18000b0ba  mov     [rsi+6], ax
0x18000b0be  mov     al, [rbx+8]
0x18000b0c1  mov     [rsi+9], al
0x18000b0c4  mov     rax, [r14]
0x18000b0c7  add     rax, 0Ah
0x18000b0cb  mov     [rbx+20h], rax
0x18000b0cf  mov     rsi, [rbx+30h]
0x18000b0d3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000b0d8  mov     [rbx+30h], rax
0x18000b0dc  test    rsi, rsi
0x18000b0df  jz      short loc_18000B0F5
0x18000b0e1  call    cs:__imp_GetProcessHeap
0x18000b0e7  mov     r8, rsi; lpMem
0x18000b0ea  xor     edx, edx; dwFlags
0x18000b0ec  mov     rcx, rax; hHeap
0x18000b0ef  call    cs:__imp_HeapFree
0x18000b0f5  mov     rsi, [rsp+98h+Buf1]
0x18000b0fd  mov     ebp, [rsp+98h+arg_28]
0x18000b104  mov     byte ptr [rbx+3Ah], 1
0x18000b108  jmp     short loc_18000B10F
0x18000b10a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000b10f  test    rdi, rdi
0x18000b112  jz      short loc_18000B138
0x18000b114  call    cs:__imp_GetProcessHeap
0x18000b11a  mov     r8, rdi; lpMem
0x18000b11d  xor     edx, edx; dwFlags
0x18000b11f  mov     rcx, rax; hHeap
0x18000b122  call    cs:__imp_HeapFree
0x18000b128  jmp     short loc_18000B138
0x18000b12a  cmp     byte ptr [rbx+3Ah], 0
0x18000b12e  jz      short loc_18000B138
0x18000b130  mov     rcx, r14; this
0x18000b133  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b138  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000b13c  mov     r9, r13; void *
0x18000b13f  mov     r8, r15; Size
0x18000b142  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000b147  mov     rdx, rsi; Buf1
0x18000b14a  mov     rcx, rbx; this
0x18000b14d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000b152  add     rsp, 58h
0x18000b156  pop     r15
0x18000b158  pop     r14
0x18000b15a  pop     r13
0x18000b15c  pop     r12
0x18000b15e  pop     rdi
0x18000b15f  pop     rsi
0x18000b160  pop     rbp
0x18000b161  pop     rbx
0x18000b162  retn
0x18000b163  mov     rcx, [rsp+98h]; this
0x18000b16b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
