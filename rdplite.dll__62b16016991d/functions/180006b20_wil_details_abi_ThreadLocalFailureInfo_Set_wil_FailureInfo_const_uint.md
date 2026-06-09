# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006b20`
- end: `0x180006c56`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006eb8`

## callees

- `0x180004154`
- `0x180004870`
- `0x1800048e8`
- `0x180006658`
- `0x1800069f8`
- `0x180006a18`
- `0x180006b20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bcf`

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
0x180006b20  push    rbx
0x180006b22  push    rbp
0x180006b23  push    rsi
0x180006b24  push    rdi
0x180006b25  push    r12
0x180006b27  push    r13
0x180006b29  push    r14
0x180006b2b  push    r15
0x180006b2d  sub     rsp, 28h
0x180006b31  mov     [rcx+4], r8d
0x180006b35  lea     r14, [rcx+38h]
0x180006b39  mov     eax, [rdx+8]
0x180006b3c  mov     rsi, rcx
0x180006b3f  mov     [rcx+8], eax
0x180006b42  mov     r15, rdx
0x180006b45  mov     qword ptr [rcx+10h], 0
0x180006b4d  movzx   eax, word ptr [rdx+40h]
0x180006b51  mov     [rcx+18h], ax
0x180006b55  mov     al, [rdx]
0x180006b57  mov     [rcx+1Ah], al
0x180006b5a  mov     qword ptr [rcx+20h], 0
0x180006b62  mov     rax, [rdx+88h]
0x180006b69  mov     [rcx+28h], rax
0x180006b6d  mov     rax, [rdx+90h]
0x180006b74  mov     [rcx+30h], rax
0x180006b78  mov     qword ptr [r14], 0
0x180006b7f  mov     rcx, [rdx+18h]; this
0x180006b83  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006b88  mov     rcx, [r15+38h]; this
0x180006b8c  mov     rbp, rax
0x180006b8f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006b94  mov     rcx, [r15+80h]; this
0x180006b9b  add     rbp, rax
0x180006b9e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006ba3  add     rbp, rax
0x180006ba6  lea     rdi, [rsi+48h]
0x180006baa  cmp     qword ptr [rsi+40h], 0
0x180006baf  jz      short loc_180006BB6
0x180006bb1  cmp     [rdi], rbp
0x180006bb4  jnb     short loc_180006BEE
0x180006bb6  mov     rdx, rbp; dwBytes
0x180006bb9  mov     ecx, 8; dwFlags
0x180006bbe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006bc3  mov     r14, rax
0x180006bc6  test    rax, rax
0x180006bc9  jz      short loc_180006BEA
0x180006bcb  mov     rbx, [rsi+40h]
0x180006bcf  call    cs:__imp_GetProcessHeap
0x180006bd5  mov     r8, rbx; lpMem
0x180006bd8  xor     edx, edx; dwFlags
0x180006bda  mov     rcx, rax; hHeap
0x180006bdd  call    cs:__imp_HeapFree
0x180006be3  mov     [rsi+40h], r14
0x180006be7  mov     [rdi], rbp
0x180006bea  lea     r14, [rsi+38h]
0x180006bee  mov     rcx, [rsi+40h]; Destination
0x180006bf2  test    rcx, rcx
0x180006bf5  jz      short loc_180006C45
0x180006bf7  mov     rbx, [rdi]
0x180006bfa  lea     r9, [rsi+10h]
0x180006bfe  mov     r8, [r15+38h]
0x180006c02  add     rbx, rcx
0x180006c05  mov     rdx, rbx
0x180006c08  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006c0d  mov     r8, [r15+80h]
0x180006c14  lea     r9, [rsi+20h]
0x180006c18  mov     rdx, rbx
0x180006c1b  mov     rcx, rax; Destination
0x180006c1e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006c23  mov     r8, [r15+18h]
0x180006c27  mov     r9, r14
0x180006c2a  mov     rdx, rbx
0x180006c2d  mov     rcx, rax; Destination
0x180006c30  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006c35  sub     rbx, rax
0x180006c38  xor     edx, edx; Val
0x180006c3a  mov     r8, rbx; Size
0x180006c3d  mov     rcx, rax; void *
0x180006c40  call    memset_0
0x180006c45  add     rsp, 28h
0x180006c49  pop     r15
0x180006c4b  pop     r14
0x180006c4d  pop     r13
0x180006c4f  pop     r12
0x180006c51  pop     rdi
0x180006c52  pop     rsi
0x180006c53  pop     rbp
0x180006c54  pop     rbx
0x180006c55  retn
```
