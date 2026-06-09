# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009940`
- end: `0x180009a6c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `300`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009e08`

## callees

- `0x180005508`
- `0x180005590`
- `0x180008a4c`
- `0x1800097b0`
- `0x1800097d8`
- `0x180009940`
- `0x18002f0ba`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800099f3`
- `KERNEL32!HeapFree` at `0x1800099f3`
- `KERNEL32!GetProcessHeap` at `0x1800099e5`
- `KERNEL32!GetProcessHeap` at `0x1800099e5`

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
  const wchar_t *v8; // rdx
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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), (const char *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), v8) + v7;
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
0x180009940  push    rbx
0x180009942  push    rbp
0x180009943  push    rsi
0x180009944  push    rdi
0x180009945  push    r12
0x180009947  push    r13
0x180009949  push    r14
0x18000994b  push    r15
0x18000994d  sub     rsp, 28h
0x180009951  mov     rsi, rcx
0x180009954  mov     [rcx+4], r8d
0x180009958  mov     eax, [rdx+8]
0x18000995b  mov     r15, rdx
0x18000995e  mov     [rcx+8], eax
0x180009961  xor     ecx, ecx
0x180009963  mov     [rsi+10h], rcx
0x180009967  lea     r14, [rsi+38h]
0x18000996b  movzx   eax, word ptr [rdx+40h]
0x18000996f  mov     [rsi+18h], ax
0x180009973  mov     al, [rdx]
0x180009975  mov     [rsi+1Ah], al
0x180009978  mov     [rsi+20h], rcx
0x18000997c  mov     rax, [rdx+88h]
0x180009983  mov     [rsi+28h], rax
0x180009987  mov     rax, [rdx+90h]
0x18000998e  mov     [rsi+30h], rax
0x180009992  mov     [r14], rcx
0x180009995  mov     rcx, [rdx+80h]; this
0x18000999c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800099a1  mov     rcx, [r15+38h]; this
0x1800099a5  mov     rbp, rax
0x1800099a8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800099ad  mov     rcx, [r15+18h]; this
0x1800099b1  add     rbp, rax
0x1800099b4  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1800099b9  add     rbp, rax
0x1800099bc  lea     rdi, [rsi+48h]
0x1800099c0  cmp     qword ptr [rsi+40h], 0
0x1800099c5  jz      short loc_1800099CC
0x1800099c7  cmp     [rdi], rbp
0x1800099ca  jnb     short loc_180009A04
0x1800099cc  mov     rdx, rbp; dwBytes
0x1800099cf  mov     ecx, 8; dwFlags
0x1800099d4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800099d9  mov     r14, rax
0x1800099dc  test    rax, rax
0x1800099df  jz      short loc_180009A00
0x1800099e1  mov     rbx, [rsi+40h]
0x1800099e5  call    cs:__imp_GetProcessHeap
0x1800099eb  mov     r8, rbx; lpMem
0x1800099ee  xor     edx, edx; dwFlags
0x1800099f0  mov     rcx, rax; hHeap
0x1800099f3  call    cs:__imp_HeapFree
0x1800099f9  mov     [rsi+40h], r14
0x1800099fd  mov     [rdi], rbp
0x180009a00  lea     r14, [rsi+38h]
0x180009a04  mov     rcx, [rsi+40h]; Destination
0x180009a08  test    rcx, rcx
0x180009a0b  jz      short loc_180009A5B
0x180009a0d  mov     rbx, [rdi]
0x180009a10  lea     r9, [rsi+10h]
0x180009a14  mov     r8, [r15+38h]
0x180009a18  add     rbx, rcx
0x180009a1b  mov     rdx, rbx
0x180009a1e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009a23  mov     r8, [r15+80h]
0x180009a2a  lea     r9, [rsi+20h]
0x180009a2e  mov     rdx, rbx
0x180009a31  mov     rcx, rax; Destination
0x180009a34  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009a39  mov     r8, [r15+18h]
0x180009a3d  mov     r9, r14
0x180009a40  mov     rdx, rbx
0x180009a43  mov     rcx, rax; Destination
0x180009a46  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180009a4b  sub     rbx, rax
0x180009a4e  xor     edx, edx; Val
0x180009a50  mov     r8, rbx; Size
0x180009a53  mov     rcx, rax; void *
0x180009a56  call    memset_0
0x180009a5b  add     rsp, 28h
0x180009a5f  pop     r15
0x180009a61  pop     r14
0x180009a63  pop     r13
0x180009a65  pop     r12
0x180009a67  pop     rdi
0x180009a68  pop     rsi
0x180009a69  pop     rbp
0x180009a6a  pop     rbx
0x180009a6b  retn
```
