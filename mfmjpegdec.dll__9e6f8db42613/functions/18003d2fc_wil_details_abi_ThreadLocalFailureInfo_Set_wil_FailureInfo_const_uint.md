# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18003d2fc`
- end: `0x18003d432`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003d438`

## callees

- `0x180024bf4`
- `0x18003ad28`
- `0x18003ada0`
- `0x18003cb48`
- `0x18003d234`
- `0x18003d254`
- `0x18003d2fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d3b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d3b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d3ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d3ab`

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
0x18003d2fc  push    rbx
0x18003d2fe  push    rbp
0x18003d2ff  push    rsi
0x18003d300  push    rdi
0x18003d301  push    r12
0x18003d303  push    r13
0x18003d305  push    r14
0x18003d307  push    r15
0x18003d309  sub     rsp, 28h
0x18003d30d  mov     [rcx+4], r8d
0x18003d311  lea     r14, [rcx+38h]
0x18003d315  mov     eax, [rdx+8]
0x18003d318  mov     rsi, rcx
0x18003d31b  mov     [rcx+8], eax
0x18003d31e  mov     r15, rdx
0x18003d321  mov     qword ptr [rcx+10h], 0
0x18003d329  movzx   eax, word ptr [rdx+40h]
0x18003d32d  mov     [rcx+18h], ax
0x18003d331  mov     al, [rdx]
0x18003d333  mov     [rcx+1Ah], al
0x18003d336  mov     qword ptr [rcx+20h], 0
0x18003d33e  mov     rax, [rdx+88h]
0x18003d345  mov     [rcx+28h], rax
0x18003d349  mov     rax, [rdx+90h]
0x18003d350  mov     [rcx+30h], rax
0x18003d354  mov     qword ptr [r14], 0
0x18003d35b  mov     rcx, [rdx+18h]; this
0x18003d35f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18003d364  mov     rcx, [r15+38h]; this
0x18003d368  mov     rbp, rax
0x18003d36b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18003d370  mov     rcx, [r15+80h]; this
0x18003d377  add     rbp, rax
0x18003d37a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18003d37f  add     rbp, rax
0x18003d382  lea     rdi, [rsi+48h]
0x18003d386  cmp     qword ptr [rsi+40h], 0
0x18003d38b  jz      short loc_18003D392
0x18003d38d  cmp     [rdi], rbp
0x18003d390  jnb     short loc_18003D3CA
0x18003d392  mov     rdx, rbp; dwBytes
0x18003d395  mov     ecx, 8; dwFlags
0x18003d39a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003d39f  mov     r14, rax
0x18003d3a2  test    rax, rax
0x18003d3a5  jz      short loc_18003D3C6
0x18003d3a7  mov     rbx, [rsi+40h]
0x18003d3ab  call    cs:__imp_GetProcessHeap
0x18003d3b1  mov     r8, rbx; lpMem
0x18003d3b4  xor     edx, edx; dwFlags
0x18003d3b6  mov     rcx, rax; hHeap
0x18003d3b9  call    cs:__imp_HeapFree
0x18003d3bf  mov     [rsi+40h], r14
0x18003d3c3  mov     [rdi], rbp
0x18003d3c6  lea     r14, [rsi+38h]
0x18003d3ca  mov     rcx, [rsi+40h]; Destination
0x18003d3ce  test    rcx, rcx
0x18003d3d1  jz      short loc_18003D421
0x18003d3d3  mov     rbx, [rdi]
0x18003d3d6  lea     r9, [rsi+10h]
0x18003d3da  mov     r8, [r15+38h]
0x18003d3de  add     rbx, rcx
0x18003d3e1  mov     rdx, rbx
0x18003d3e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18003d3e9  mov     r8, [r15+80h]
0x18003d3f0  lea     r9, [rsi+20h]
0x18003d3f4  mov     rdx, rbx
0x18003d3f7  mov     rcx, rax; Destination
0x18003d3fa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18003d3ff  mov     r8, [r15+18h]
0x18003d403  mov     r9, r14
0x18003d406  mov     rdx, rbx
0x18003d409  mov     rcx, rax; Destination
0x18003d40c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18003d411  sub     rbx, rax
0x18003d414  xor     edx, edx; Val
0x18003d416  mov     r8, rbx; Size
0x18003d419  mov     rcx, rax; void *
0x18003d41c  call    memset_0
0x18003d421  add     rsp, 28h
0x18003d425  pop     r15
0x18003d427  pop     r14
0x18003d429  pop     r13
0x18003d42b  pop     r12
0x18003d42d  pop     rdi
0x18003d42e  pop     rsi
0x18003d42f  pop     rbp
0x18003d430  pop     rbx
0x18003d431  retn
```
