# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140015b40`
- end: `0x140015ce9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140013300`
- `0x140015a40`
- `0x140015a74`

## callees

- `0x140015b40`
- `0x140015cf0`
- `0x1400176f8`
- `0x140017744`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140015bfd`
- `KERNEL32!HeapFree` at `0x140015c67`
- `KERNEL32!HeapFree` at `0x140015c9a`
- `KERNEL32!HeapFree` at `0x140015bfd`
- `KERNEL32!HeapFree` at `0x140015c67`
- `KERNEL32!HeapFree` at `0x140015c9a`
- `KERNEL32!GetProcessHeap` at `0x140015bef`
- `KERNEL32!GetProcessHeap` at `0x140015c59`
- `KERNEL32!GetProcessHeap` at `0x140015c8c`
- `KERNEL32!GetProcessHeap` at `0x140015bef`
- `KERNEL32!GetProcessHeap` at `0x140015c59`
- `KERNEL32!GetProcessHeap` at `0x140015c8c`

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
0x140015b40  mov     [rsp+Buf1], rdx
0x140015b45  push    rbx
0x140015b46  push    rbp
0x140015b47  push    rsi
0x140015b48  push    rdi
0x140015b49  push    r12
0x140015b4b  push    r13
0x140015b4d  push    r14
0x140015b4f  push    r15
0x140015b51  sub     rsp, 58h
0x140015b55  mov     ebp, [rsp+98h+arg_28]
0x140015b5c  mov     r13, r9
0x140015b5f  mov     r12, [rsp+98h+arg_20]
0x140015b67  mov     r15, r8
0x140015b6a  mov     [rsp+98h+var_70], ebp; unsigned int
0x140015b6e  mov     rsi, rdx
0x140015b71  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140015b76  mov     rbx, rcx
0x140015b79  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140015b7e  test    al, al
0x140015b80  jz      short loc_140015B89
0x140015b82  mov     al, 1
0x140015b84  jmp     loc_140015CCA
0x140015b89  lea     rdx, [r12+20h]
0x140015b8e  add     rdx, r15; unsigned __int64
0x140015b91  lea     r14, [rbx+18h]
0x140015b95  cmp     qword ptr [r14], 0
0x140015b99  jnz     loc_140015CA2
0x140015b9f  xorps   xmm0, xmm0
0x140015ba2  lea     rcx, [rsp+98h+var_68]; this
0x140015ba7  xorps   xmm1, xmm1
0x140015baa  add     rdx, 0Ah; unsigned __int64
0x140015bae  movdqu  [rsp+98h+var_68], xmm0
0x140015bb4  movdqu  [rsp+98h+var_58], xmm1
0x140015bba  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140015bbf  test    al, al
0x140015bc1  jz      loc_140015C82
0x140015bc7  mov     rdi, qword ptr [rsp+98h+var_58]
0x140015bcc  mov     rsi, qword ptr [rsp+98h+var_68]
0x140015bd1  sub     rdi, rsi
0x140015bd4  cmp     rdi, 0Ah
0x140015bd8  jb      loc_140015CDB
0x140015bde  mov     rbp, [rbx+30h]
0x140015be2  mov     qword ptr [rbx+30h], 0
0x140015bea  test    rbp, rbp
0x140015bed  jz      short loc_140015C03
0x140015bef  call    cs:__imp_GetProcessHeap
0x140015bf5  mov     r8, rbp; lpMem
0x140015bf8  xor     edx, edx; dwFlags
0x140015bfa  mov     rcx, rax; hHeap
0x140015bfd  call    cs:__imp_HeapFree
0x140015c03  mov     [r14], rsi
0x140015c06  lea     rax, [rdi+rsi]
0x140015c0a  mov     [rbx+28h], rax
0x140015c0e  xor     edi, edi
0x140015c10  xor     eax, eax
0x140015c12  mov     byte ptr [rbx+39h], 0
0x140015c16  mov     [rsi], ax
0x140015c19  movzx   eax, word ptr [rbx]
0x140015c1c  mov     [rsi+2], ax
0x140015c20  movzx   eax, word ptr [rbx+2]
0x140015c24  mov     [rsi+4], ax
0x140015c28  mov     al, [rbx+4]
0x140015c2b  mov     [rsi+8], al
0x140015c2e  movzx   eax, word ptr [rbx+6]
0x140015c32  mov     [rsi+6], ax
0x140015c36  mov     al, [rbx+8]
0x140015c39  mov     [rsi+9], al
0x140015c3c  mov     rax, [r14]
0x140015c3f  add     rax, 0Ah
0x140015c43  mov     [rbx+20h], rax
0x140015c47  mov     rsi, [rbx+30h]
0x140015c4b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140015c50  mov     [rbx+30h], rax
0x140015c54  test    rsi, rsi
0x140015c57  jz      short loc_140015C6D
0x140015c59  call    cs:__imp_GetProcessHeap
0x140015c5f  mov     r8, rsi; lpMem
0x140015c62  xor     edx, edx; dwFlags
0x140015c64  mov     rcx, rax; hHeap
0x140015c67  call    cs:__imp_HeapFree
0x140015c6d  mov     rsi, [rsp+98h+Buf1]
0x140015c75  mov     ebp, [rsp+98h+arg_28]
0x140015c7c  mov     byte ptr [rbx+3Ah], 1
0x140015c80  jmp     short loc_140015C87
0x140015c82  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x140015c87  test    rdi, rdi
0x140015c8a  jz      short loc_140015CB0
0x140015c8c  call    cs:__imp_GetProcessHeap
0x140015c92  mov     r8, rdi; lpMem
0x140015c95  xor     edx, edx; dwFlags
0x140015c97  mov     rcx, rax; hHeap
0x140015c9a  call    cs:__imp_HeapFree
0x140015ca0  jmp     short loc_140015CB0
0x140015ca2  cmp     byte ptr [rbx+3Ah], 0
0x140015ca6  jz      short loc_140015CB0
0x140015ca8  mov     rcx, r14; this
0x140015cab  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140015cb0  mov     [rsp+98h+var_70], ebp; unsigned int
0x140015cb4  mov     r9, r13; void *
0x140015cb7  mov     r8, r15; Size
0x140015cba  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140015cbf  mov     rdx, rsi; Buf1
0x140015cc2  mov     rcx, rbx; this
0x140015cc5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140015cca  add     rsp, 58h
0x140015cce  pop     r15
0x140015cd0  pop     r14
0x140015cd2  pop     r13
0x140015cd4  pop     r12
0x140015cd6  pop     rdi
0x140015cd7  pop     rsi
0x140015cd8  pop     rbp
0x140015cd9  pop     rbx
0x140015cda  retn
0x140015cdb  mov     rcx, [rsp+98h]; this
0x140015ce3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
