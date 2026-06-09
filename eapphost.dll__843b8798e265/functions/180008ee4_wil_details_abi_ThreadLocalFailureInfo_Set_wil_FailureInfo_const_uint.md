# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008ee4`
- end: `0x180009027`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009298`

## callees

- `0x1800034cc`
- `0x180004a10`
- `0x180004a88`
- `0x180008a6c`
- `0x180008da8`
- `0x180008dcc`
- `0x180008ee4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f93`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x180008ee4  push    rbx
0x180008ee6  push    rbp
0x180008ee7  push    rsi
0x180008ee8  push    rdi
0x180008ee9  push    r12
0x180008eeb  push    r13
0x180008eed  push    r14
0x180008eef  push    r15
0x180008ef1  sub     rsp, 28h
0x180008ef5  mov     [rcx+4], r8d
0x180008ef9  lea     r14, [rcx+38h]
0x180008efd  mov     eax, [rdx+8]
0x180008f00  mov     rsi, rcx
0x180008f03  mov     [rcx+8], eax
0x180008f06  mov     r15, rdx
0x180008f09  mov     qword ptr [rcx+10h], 0
0x180008f11  movzx   eax, word ptr [rdx+40h]
0x180008f15  mov     [rcx+18h], ax
0x180008f19  mov     al, [rdx]
0x180008f1b  mov     [rcx+1Ah], al
0x180008f1e  mov     qword ptr [rcx+20h], 0
0x180008f26  mov     rax, [rdx+88h]
0x180008f2d  mov     [rcx+28h], rax
0x180008f31  mov     rax, [rdx+90h]
0x180008f38  mov     [rcx+30h], rax
0x180008f3c  mov     qword ptr [r14], 0
0x180008f43  mov     rcx, [rdx+18h]; this
0x180008f47  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180008f4c  mov     rcx, [r15+38h]; this
0x180008f50  mov     rbp, rax
0x180008f53  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008f58  mov     rcx, [r15+80h]; this
0x180008f5f  add     rbp, rax
0x180008f62  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008f67  add     rbp, rax
0x180008f6a  lea     rdi, [rsi+48h]
0x180008f6e  cmp     qword ptr [rsi+40h], 0
0x180008f73  jz      short loc_180008F7A
0x180008f75  cmp     [rdi], rbp
0x180008f78  jnb     short loc_180008FBE
0x180008f7a  mov     rdx, rbp; dwBytes
0x180008f7d  mov     ecx, 8; dwFlags
0x180008f82  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008f87  mov     r14, rax
0x180008f8a  test    rax, rax
0x180008f8d  jz      short loc_180008FBA
0x180008f8f  mov     rbx, [rsi+40h]
0x180008f93  call    cs:__imp_GetProcessHeap
0x180008f9a  nop     dword ptr [rax+rax+00h]
0x180008f9f  mov     r8, rbx; lpMem
0x180008fa2  xor     edx, edx; dwFlags
0x180008fa4  mov     rcx, rax; hHeap
0x180008fa7  call    cs:__imp_HeapFree
0x180008fae  nop     dword ptr [rax+rax+00h]
0x180008fb3  mov     [rsi+40h], r14
0x180008fb7  mov     [rdi], rbp
0x180008fba  lea     r14, [rsi+38h]
0x180008fbe  mov     rcx, [rsi+40h]; Destination
0x180008fc2  test    rcx, rcx
0x180008fc5  jz      short loc_180009015
0x180008fc7  mov     rbx, [rdi]
0x180008fca  lea     r9, [rsi+10h]
0x180008fce  mov     r8, [r15+38h]
0x180008fd2  add     rbx, rcx
0x180008fd5  mov     rdx, rbx
0x180008fd8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008fdd  mov     r8, [r15+80h]
0x180008fe4  lea     r9, [rsi+20h]
0x180008fe8  mov     rdx, rbx
0x180008feb  mov     rcx, rax; Destination
0x180008fee  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008ff3  mov     r8, [r15+18h]
0x180008ff7  mov     r9, r14
0x180008ffa  mov     rdx, rbx
0x180008ffd  mov     rcx, rax; Destination
0x180009000  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180009005  sub     rbx, rax
0x180009008  xor     edx, edx; Val
0x18000900a  mov     r8, rbx; Size
0x18000900d  mov     rcx, rax; void *
0x180009010  call    memset_0
0x180009015  add     rsp, 28h
0x180009019  pop     r15
0x18000901b  pop     r14
0x18000901d  pop     r13
0x18000901f  pop     r12
0x180009021  pop     rdi
0x180009022  pop     rsi
0x180009023  pop     rbp
0x180009024  pop     rbx
0x180009025  retn
```
