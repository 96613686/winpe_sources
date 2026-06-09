# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000aeb0`
- end: `0x18000b059`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008670`
- `0x18000adb0`
- `0x18000ade4`

## callees

- `0x18000aeb0`
- `0x18000b060`
- `0x18000ca68`
- `0x18000cacc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b00a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b00a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000affc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000affc`

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
0x18000aeb0  mov     [rsp+Buf1], rdx
0x18000aeb5  push    rbx
0x18000aeb6  push    rbp
0x18000aeb7  push    rsi
0x18000aeb8  push    rdi
0x18000aeb9  push    r12
0x18000aebb  push    r13
0x18000aebd  push    r14
0x18000aebf  push    r15
0x18000aec1  sub     rsp, 58h
0x18000aec5  mov     ebp, [rsp+98h+arg_28]
0x18000aecc  mov     r13, r9
0x18000aecf  mov     r12, [rsp+98h+arg_20]
0x18000aed7  mov     r15, r8
0x18000aeda  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000aede  mov     rsi, rdx
0x18000aee1  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000aee6  mov     rbx, rcx
0x18000aee9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000aeee  test    al, al
0x18000aef0  jz      short loc_18000AEF9
0x18000aef2  mov     al, 1
0x18000aef4  jmp     loc_18000B03A
0x18000aef9  lea     rdx, [r12+20h]
0x18000aefe  add     rdx, r15; unsigned __int64
0x18000af01  lea     r14, [rbx+18h]
0x18000af05  cmp     qword ptr [r14], 0
0x18000af09  jnz     loc_18000B012
0x18000af0f  xorps   xmm0, xmm0
0x18000af12  lea     rcx, [rsp+98h+var_68]; this
0x18000af17  xorps   xmm1, xmm1
0x18000af1a  add     rdx, 0Ah; unsigned __int64
0x18000af1e  movdqu  [rsp+98h+var_68], xmm0
0x18000af24  movdqu  [rsp+98h+var_58], xmm1
0x18000af2a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000af2f  test    al, al
0x18000af31  jz      loc_18000AFF2
0x18000af37  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000af3c  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000af41  sub     rdi, rsi
0x18000af44  cmp     rdi, 0Ah
0x18000af48  jb      loc_18000B04B
0x18000af4e  mov     rbp, [rbx+30h]
0x18000af52  mov     qword ptr [rbx+30h], 0
0x18000af5a  test    rbp, rbp
0x18000af5d  jz      short loc_18000AF73
0x18000af5f  call    cs:__imp_GetProcessHeap
0x18000af65  mov     r8, rbp; lpMem
0x18000af68  xor     edx, edx; dwFlags
0x18000af6a  mov     rcx, rax; hHeap
0x18000af6d  call    cs:__imp_HeapFree
0x18000af73  mov     [r14], rsi
0x18000af76  lea     rax, [rdi+rsi]
0x18000af7a  mov     [rbx+28h], rax
0x18000af7e  xor     edi, edi
0x18000af80  xor     eax, eax
0x18000af82  mov     byte ptr [rbx+39h], 0
0x18000af86  mov     [rsi], ax
0x18000af89  movzx   eax, word ptr [rbx]
0x18000af8c  mov     [rsi+2], ax
0x18000af90  movzx   eax, word ptr [rbx+2]
0x18000af94  mov     [rsi+4], ax
0x18000af98  mov     al, [rbx+4]
0x18000af9b  mov     [rsi+8], al
0x18000af9e  movzx   eax, word ptr [rbx+6]
0x18000afa2  mov     [rsi+6], ax
0x18000afa6  mov     al, [rbx+8]
0x18000afa9  mov     [rsi+9], al
0x18000afac  mov     rax, [r14]
0x18000afaf  add     rax, 0Ah
0x18000afb3  mov     [rbx+20h], rax
0x18000afb7  mov     rsi, [rbx+30h]
0x18000afbb  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000afc0  mov     [rbx+30h], rax
0x18000afc4  test    rsi, rsi
0x18000afc7  jz      short loc_18000AFDD
0x18000afc9  call    cs:__imp_GetProcessHeap
0x18000afcf  mov     r8, rsi; lpMem
0x18000afd2  xor     edx, edx; dwFlags
0x18000afd4  mov     rcx, rax; hHeap
0x18000afd7  call    cs:__imp_HeapFree
0x18000afdd  mov     rsi, [rsp+98h+Buf1]
0x18000afe5  mov     ebp, [rsp+98h+arg_28]
0x18000afec  mov     byte ptr [rbx+3Ah], 1
0x18000aff0  jmp     short loc_18000AFF7
0x18000aff2  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000aff7  test    rdi, rdi
0x18000affa  jz      short loc_18000B020
0x18000affc  call    cs:__imp_GetProcessHeap
0x18000b002  mov     r8, rdi; lpMem
0x18000b005  xor     edx, edx; dwFlags
0x18000b007  mov     rcx, rax; hHeap
0x18000b00a  call    cs:__imp_HeapFree
0x18000b010  jmp     short loc_18000B020
0x18000b012  cmp     byte ptr [rbx+3Ah], 0
0x18000b016  jz      short loc_18000B020
0x18000b018  mov     rcx, r14; this
0x18000b01b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b020  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000b024  mov     r9, r13; void *
0x18000b027  mov     r8, r15; Size
0x18000b02a  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000b02f  mov     rdx, rsi; Buf1
0x18000b032  mov     rcx, rbx; this
0x18000b035  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000b03a  add     rsp, 58h
0x18000b03e  pop     r15
0x18000b040  pop     r14
0x18000b042  pop     r13
0x18000b044  pop     r12
0x18000b046  pop     rdi
0x18000b047  pop     rsi
0x18000b048  pop     rbp
0x18000b049  pop     rbx
0x18000b04a  retn
0x18000b04b  mov     rcx, [rsp+98h]; this
0x18000b053  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
