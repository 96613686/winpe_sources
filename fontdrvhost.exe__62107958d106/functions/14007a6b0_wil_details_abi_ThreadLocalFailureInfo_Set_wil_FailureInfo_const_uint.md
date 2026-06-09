# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14007a6b0`
- end: `0x14007a7e6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14007ab34`

## callees

- `0x14007680c`
- `0x140077838`
- `0x1400778b0`
- `0x140079c0c`
- `0x14007a544`
- `0x14007a564`
- `0x14007a6b0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14007a75f`
- `KERNEL32!GetProcessHeap` at `0x14007a75f`
- `KERNEL32!HeapFree` at `0x14007a76d`
- `KERNEL32!HeapFree` at `0x14007a76d`

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
0x14007a6b0  push    rbx
0x14007a6b2  push    rbp
0x14007a6b3  push    rsi
0x14007a6b4  push    rdi
0x14007a6b5  push    r12
0x14007a6b7  push    r13
0x14007a6b9  push    r14
0x14007a6bb  push    r15
0x14007a6bd  sub     rsp, 28h
0x14007a6c1  mov     [rcx+4], r8d
0x14007a6c5  lea     r14, [rcx+38h]
0x14007a6c9  mov     eax, [rdx+8]
0x14007a6cc  mov     rsi, rcx
0x14007a6cf  mov     [rcx+8], eax
0x14007a6d2  mov     r15, rdx
0x14007a6d5  mov     qword ptr [rcx+10h], 0
0x14007a6dd  movzx   eax, word ptr [rdx+40h]
0x14007a6e1  mov     [rcx+18h], ax
0x14007a6e5  mov     al, [rdx]
0x14007a6e7  mov     [rcx+1Ah], al
0x14007a6ea  mov     qword ptr [rcx+20h], 0
0x14007a6f2  mov     rax, [rdx+88h]
0x14007a6f9  mov     [rcx+28h], rax
0x14007a6fd  mov     rax, [rdx+90h]
0x14007a704  mov     [rcx+30h], rax
0x14007a708  mov     qword ptr [r14], 0
0x14007a70f  mov     rcx, [rdx+18h]; this
0x14007a713  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14007a718  mov     rcx, [r15+38h]; this
0x14007a71c  mov     rbp, rax
0x14007a71f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14007a724  mov     rcx, [r15+80h]; this
0x14007a72b  add     rbp, rax
0x14007a72e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14007a733  add     rbp, rax
0x14007a736  lea     rdi, [rsi+48h]
0x14007a73a  cmp     qword ptr [rsi+40h], 0
0x14007a73f  jz      short loc_14007A746
0x14007a741  cmp     [rdi], rbp
0x14007a744  jnb     short loc_14007A77E
0x14007a746  mov     rdx, rbp; dwBytes
0x14007a749  mov     ecx, 8; dwFlags
0x14007a74e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14007a753  mov     r14, rax
0x14007a756  test    rax, rax
0x14007a759  jz      short loc_14007A77A
0x14007a75b  mov     rbx, [rsi+40h]
0x14007a75f  call    cs:__imp_GetProcessHeap
0x14007a765  mov     r8, rbx; lpMem
0x14007a768  xor     edx, edx; dwFlags
0x14007a76a  mov     rcx, rax; hHeap
0x14007a76d  call    cs:__imp_HeapFree
0x14007a773  mov     [rsi+40h], r14
0x14007a777  mov     [rdi], rbp
0x14007a77a  lea     r14, [rsi+38h]
0x14007a77e  mov     rcx, [rsi+40h]; Destination
0x14007a782  test    rcx, rcx
0x14007a785  jz      short loc_14007A7D5
0x14007a787  mov     rbx, [rdi]
0x14007a78a  lea     r9, [rsi+10h]
0x14007a78e  mov     r8, [r15+38h]
0x14007a792  add     rbx, rcx
0x14007a795  mov     rdx, rbx
0x14007a798  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14007a79d  mov     r8, [r15+80h]
0x14007a7a4  lea     r9, [rsi+20h]
0x14007a7a8  mov     rdx, rbx
0x14007a7ab  mov     rcx, rax; Destination
0x14007a7ae  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14007a7b3  mov     r8, [r15+18h]
0x14007a7b7  mov     r9, r14
0x14007a7ba  mov     rdx, rbx
0x14007a7bd  mov     rcx, rax; Destination
0x14007a7c0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x14007a7c5  sub     rbx, rax
0x14007a7c8  xor     edx, edx; Val
0x14007a7ca  mov     r8, rbx; Size
0x14007a7cd  mov     rcx, rax; void *
0x14007a7d0  call    memset_0
0x14007a7d5  add     rsp, 28h
0x14007a7d9  pop     r15
0x14007a7db  pop     r14
0x14007a7dd  pop     r13
0x14007a7df  pop     r12
0x14007a7e1  pop     rdi
0x14007a7e2  pop     rsi
0x14007a7e3  pop     rbp
0x14007a7e4  pop     rbx
0x14007a7e5  retn
```
