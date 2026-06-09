# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180010cf8`
- end: `0x180010e2e`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001117c`

## callees

- `0x18000c7e8`
- `0x18000d88c`
- `0x18000d904`
- `0x18000fd80`
- `0x1800109a0`
- `0x1800109c0`
- `0x180010cf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010da7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010da7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010db5`

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
0x180010cf8  push    rbx
0x180010cfa  push    rbp
0x180010cfb  push    rsi
0x180010cfc  push    rdi
0x180010cfd  push    r12
0x180010cff  push    r13
0x180010d01  push    r14
0x180010d03  push    r15
0x180010d05  sub     rsp, 28h
0x180010d09  mov     [rcx+4], r8d
0x180010d0d  lea     r14, [rcx+38h]
0x180010d11  mov     eax, [rdx+8]
0x180010d14  mov     rsi, rcx
0x180010d17  mov     [rcx+8], eax
0x180010d1a  mov     r15, rdx
0x180010d1d  mov     qword ptr [rcx+10h], 0
0x180010d25  movzx   eax, word ptr [rdx+40h]
0x180010d29  mov     [rcx+18h], ax
0x180010d2d  mov     al, [rdx]
0x180010d2f  mov     [rcx+1Ah], al
0x180010d32  mov     qword ptr [rcx+20h], 0
0x180010d3a  mov     rax, [rdx+88h]
0x180010d41  mov     [rcx+28h], rax
0x180010d45  mov     rax, [rdx+90h]
0x180010d4c  mov     [rcx+30h], rax
0x180010d50  mov     qword ptr [r14], 0
0x180010d57  mov     rcx, [rdx+18h]; this
0x180010d5b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180010d60  mov     rcx, [r15+38h]; this
0x180010d64  mov     rbp, rax
0x180010d67  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010d6c  mov     rcx, [r15+80h]; this
0x180010d73  add     rbp, rax
0x180010d76  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010d7b  add     rbp, rax
0x180010d7e  lea     rdi, [rsi+48h]
0x180010d82  cmp     qword ptr [rsi+40h], 0
0x180010d87  jz      short loc_180010D8E
0x180010d89  cmp     [rdi], rbp
0x180010d8c  jnb     short loc_180010DC6
0x180010d8e  mov     rdx, rbp; dwBytes
0x180010d91  mov     ecx, 8; dwFlags
0x180010d96  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010d9b  mov     r14, rax
0x180010d9e  test    rax, rax
0x180010da1  jz      short loc_180010DC2
0x180010da3  mov     rbx, [rsi+40h]
0x180010da7  call    cs:__imp_GetProcessHeap
0x180010dad  mov     r8, rbx; lpMem
0x180010db0  xor     edx, edx; dwFlags
0x180010db2  mov     rcx, rax; hHeap
0x180010db5  call    cs:__imp_HeapFree
0x180010dbb  mov     [rsi+40h], r14
0x180010dbf  mov     [rdi], rbp
0x180010dc2  lea     r14, [rsi+38h]
0x180010dc6  mov     rcx, [rsi+40h]; Destination
0x180010dca  test    rcx, rcx
0x180010dcd  jz      short loc_180010E1D
0x180010dcf  mov     rbx, [rdi]
0x180010dd2  lea     r9, [rsi+10h]
0x180010dd6  mov     r8, [r15+38h]
0x180010dda  add     rbx, rcx
0x180010ddd  mov     rdx, rbx
0x180010de0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010de5  mov     r8, [r15+80h]
0x180010dec  lea     r9, [rsi+20h]
0x180010df0  mov     rdx, rbx
0x180010df3  mov     rcx, rax; Destination
0x180010df6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010dfb  mov     r8, [r15+18h]
0x180010dff  mov     r9, r14
0x180010e02  mov     rdx, rbx
0x180010e05  mov     rcx, rax; Destination
0x180010e08  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180010e0d  sub     rbx, rax
0x180010e10  xor     edx, edx; Val
0x180010e12  mov     r8, rbx; Size
0x180010e15  mov     rcx, rax; void *
0x180010e18  call    memset_0
0x180010e1d  add     rsp, 28h
0x180010e21  pop     r15
0x180010e23  pop     r14
0x180010e25  pop     r13
0x180010e27  pop     r12
0x180010e29  pop     rdi
0x180010e2a  pop     rsi
0x180010e2b  pop     rbp
0x180010e2c  pop     rbx
0x180010e2d  retn
```
