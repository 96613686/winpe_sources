# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180021c20`
- end: `0x180021d56`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800220a4`

## callees

- `0x180014610`
- `0x18001ebf8`
- `0x18001ec70`
- `0x180021260`
- `0x180021a90`
- `0x180021ab0`
- `0x180021c20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ccf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ccf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021cdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021cdd`

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
0x180021c20  push    rbx
0x180021c22  push    rbp
0x180021c23  push    rsi
0x180021c24  push    rdi
0x180021c25  push    r12
0x180021c27  push    r13
0x180021c29  push    r14
0x180021c2b  push    r15
0x180021c2d  sub     rsp, 28h
0x180021c31  mov     [rcx+4], r8d
0x180021c35  lea     r14, [rcx+38h]
0x180021c39  mov     eax, [rdx+8]
0x180021c3c  mov     rsi, rcx
0x180021c3f  mov     [rcx+8], eax
0x180021c42  mov     r15, rdx
0x180021c45  mov     qword ptr [rcx+10h], 0
0x180021c4d  movzx   eax, word ptr [rdx+40h]
0x180021c51  mov     [rcx+18h], ax
0x180021c55  mov     al, [rdx]
0x180021c57  mov     [rcx+1Ah], al
0x180021c5a  mov     qword ptr [rcx+20h], 0
0x180021c62  mov     rax, [rdx+88h]
0x180021c69  mov     [rcx+28h], rax
0x180021c6d  mov     rax, [rdx+90h]
0x180021c74  mov     [rcx+30h], rax
0x180021c78  mov     qword ptr [r14], 0
0x180021c7f  mov     rcx, [rdx+18h]; this
0x180021c83  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180021c88  mov     rcx, [r15+38h]; this
0x180021c8c  mov     rbp, rax
0x180021c8f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180021c94  mov     rcx, [r15+80h]; this
0x180021c9b  add     rbp, rax
0x180021c9e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180021ca3  add     rbp, rax
0x180021ca6  lea     rdi, [rsi+48h]
0x180021caa  cmp     qword ptr [rsi+40h], 0
0x180021caf  jz      short loc_180021CB6
0x180021cb1  cmp     [rdi], rbp
0x180021cb4  jnb     short loc_180021CEE
0x180021cb6  mov     rdx, rbp; dwBytes
0x180021cb9  mov     ecx, 8; dwFlags
0x180021cbe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180021cc3  mov     r14, rax
0x180021cc6  test    rax, rax
0x180021cc9  jz      short loc_180021CEA
0x180021ccb  mov     rbx, [rsi+40h]
0x180021ccf  call    cs:__imp_GetProcessHeap
0x180021cd5  mov     r8, rbx; lpMem
0x180021cd8  xor     edx, edx; dwFlags
0x180021cda  mov     rcx, rax; hHeap
0x180021cdd  call    cs:__imp_HeapFree
0x180021ce3  mov     [rsi+40h], r14
0x180021ce7  mov     [rdi], rbp
0x180021cea  lea     r14, [rsi+38h]
0x180021cee  mov     rcx, [rsi+40h]; Destination
0x180021cf2  test    rcx, rcx
0x180021cf5  jz      short loc_180021D45
0x180021cf7  mov     rbx, [rdi]
0x180021cfa  lea     r9, [rsi+10h]
0x180021cfe  mov     r8, [r15+38h]
0x180021d02  add     rbx, rcx
0x180021d05  mov     rdx, rbx
0x180021d08  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180021d0d  mov     r8, [r15+80h]
0x180021d14  lea     r9, [rsi+20h]
0x180021d18  mov     rdx, rbx
0x180021d1b  mov     rcx, rax; Destination
0x180021d1e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180021d23  mov     r8, [r15+18h]
0x180021d27  mov     r9, r14
0x180021d2a  mov     rdx, rbx
0x180021d2d  mov     rcx, rax; Destination
0x180021d30  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180021d35  sub     rbx, rax
0x180021d38  xor     edx, edx; Val
0x180021d3a  mov     r8, rbx; Size
0x180021d3d  mov     rcx, rax; void *
0x180021d40  call    memset_0
0x180021d45  add     rsp, 28h
0x180021d49  pop     r15
0x180021d4b  pop     r14
0x180021d4d  pop     r13
0x180021d4f  pop     r12
0x180021d51  pop     rdi
0x180021d52  pop     rsi
0x180021d53  pop     rbp
0x180021d54  pop     rbx
0x180021d55  retn
```
