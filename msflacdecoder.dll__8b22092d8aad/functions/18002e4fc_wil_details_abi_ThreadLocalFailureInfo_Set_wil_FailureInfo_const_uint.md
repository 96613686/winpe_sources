# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002e4fc`
- end: `0x18002e632`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002eb14`

## callees

- `0x1800028ac`
- `0x180029c4c`
- `0x180029cc4`
- `0x18002df84`
- `0x18002e414`
- `0x18002e434`
- `0x18002e4fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e5ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e5ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e5b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e5b9`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18002e4fc  push    rbx
0x18002e4fe  push    rbp
0x18002e4ff  push    rsi
0x18002e500  push    rdi
0x18002e501  push    r12
0x18002e503  push    r13
0x18002e505  push    r14
0x18002e507  push    r15
0x18002e509  sub     rsp, 28h
0x18002e50d  mov     [rcx+4], r8d
0x18002e511  lea     r14, [rcx+38h]
0x18002e515  mov     eax, [rdx+8]
0x18002e518  mov     rsi, rcx
0x18002e51b  mov     [rcx+8], eax
0x18002e51e  mov     r15, rdx
0x18002e521  mov     qword ptr [rcx+10h], 0
0x18002e529  movzx   eax, word ptr [rdx+40h]
0x18002e52d  mov     [rcx+18h], ax
0x18002e531  mov     al, [rdx]
0x18002e533  mov     [rcx+1Ah], al
0x18002e536  mov     qword ptr [rcx+20h], 0
0x18002e53e  mov     rax, [rdx+88h]
0x18002e545  mov     [rcx+28h], rax
0x18002e549  mov     rax, [rdx+90h]
0x18002e550  mov     [rcx+30h], rax
0x18002e554  mov     qword ptr [r14], 0
0x18002e55b  mov     rcx, [rdx+18h]; this
0x18002e55f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002e564  mov     rcx, [r15+38h]; this
0x18002e568  mov     rbp, rax
0x18002e56b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002e570  mov     rcx, [r15+80h]; this
0x18002e577  add     rbp, rax
0x18002e57a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002e57f  add     rbp, rax
0x18002e582  lea     rdi, [rsi+48h]
0x18002e586  cmp     qword ptr [rsi+40h], 0
0x18002e58b  jz      short loc_18002E592
0x18002e58d  cmp     [rdi], rbp
0x18002e590  jnb     short loc_18002E5CA
0x18002e592  mov     rdx, rbp; dwBytes
0x18002e595  mov     ecx, 8; dwFlags
0x18002e59a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002e59f  mov     r14, rax
0x18002e5a2  test    rax, rax
0x18002e5a5  jz      short loc_18002E5C6
0x18002e5a7  mov     rbx, [rsi+40h]
0x18002e5ab  call    cs:__imp_GetProcessHeap
0x18002e5b1  mov     r8, rbx; lpMem
0x18002e5b4  xor     edx, edx; dwFlags
0x18002e5b6  mov     rcx, rax; hHeap
0x18002e5b9  call    cs:__imp_HeapFree
0x18002e5bf  mov     [rsi+40h], r14
0x18002e5c3  mov     [rdi], rbp
0x18002e5c6  lea     r14, [rsi+38h]
0x18002e5ca  mov     rcx, [rsi+40h]; Destination
0x18002e5ce  test    rcx, rcx
0x18002e5d1  jz      short loc_18002E621
0x18002e5d3  mov     rbx, [rdi]
0x18002e5d6  lea     r9, [rsi+10h]
0x18002e5da  mov     r8, [r15+38h]
0x18002e5de  add     rbx, rcx
0x18002e5e1  mov     rdx, rbx
0x18002e5e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002e5e9  mov     r8, [r15+80h]
0x18002e5f0  lea     r9, [rsi+20h]
0x18002e5f4  mov     rdx, rbx
0x18002e5f7  mov     rcx, rax; Destination
0x18002e5fa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002e5ff  mov     r8, [r15+18h]
0x18002e603  mov     r9, r14
0x18002e606  mov     rdx, rbx
0x18002e609  mov     rcx, rax; Destination
0x18002e60c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18002e611  sub     rbx, rax
0x18002e614  xor     edx, edx; Val
0x18002e616  mov     r8, rbx; Size
0x18002e619  mov     rcx, rax; void *
0x18002e61c  call    memset_0
0x18002e621  add     rsp, 28h
0x18002e625  pop     r15
0x18002e627  pop     r14
0x18002e629  pop     r13
0x18002e62b  pop     r12
0x18002e62d  pop     rdi
0x18002e62e  pop     rsi
0x18002e62f  pop     rbp
0x18002e630  pop     rbx
0x18002e631  retn
```
