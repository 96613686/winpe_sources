# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180016ea8`
- end: `0x180016fde`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800170d4`

## callees

- `0x180002320`
- `0x180002ee8`
- `0x180002f60`
- `0x180003a14`
- `0x180003a34`
- `0x180012b8c`
- `0x180016ea8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180016f57`
- `KERNEL32!GetProcessHeap` at `0x180016f57`
- `KERNEL32!HeapFree` at `0x180016f65`
- `KERNEL32!HeapFree` at `0x180016f65`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x180016ea8  push    rbx
0x180016eaa  push    rbp
0x180016eab  push    rsi
0x180016eac  push    rdi
0x180016ead  push    r12
0x180016eaf  push    r13
0x180016eb1  push    r14
0x180016eb3  push    r15
0x180016eb5  sub     rsp, 28h
0x180016eb9  mov     [rcx+4], r8d
0x180016ebd  lea     r14, [rcx+38h]
0x180016ec1  mov     eax, [rdx+8]
0x180016ec4  mov     rsi, rcx
0x180016ec7  mov     [rcx+8], eax
0x180016eca  mov     r15, rdx
0x180016ecd  mov     qword ptr [rcx+10h], 0
0x180016ed5  movzx   eax, word ptr [rdx+40h]
0x180016ed9  mov     [rcx+18h], ax
0x180016edd  mov     al, [rdx]
0x180016edf  mov     [rcx+1Ah], al
0x180016ee2  mov     qword ptr [rcx+20h], 0
0x180016eea  mov     rax, [rdx+88h]
0x180016ef1  mov     [rcx+28h], rax
0x180016ef5  mov     rax, [rdx+90h]
0x180016efc  mov     [rcx+30h], rax
0x180016f00  mov     qword ptr [r14], 0
0x180016f07  mov     rcx, [rdx+18h]; this
0x180016f0b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180016f10  mov     rcx, [r15+38h]; this
0x180016f14  mov     rbp, rax
0x180016f17  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180016f1c  mov     rcx, [r15+80h]; this
0x180016f23  add     rbp, rax
0x180016f26  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180016f2b  add     rbp, rax
0x180016f2e  lea     rdi, [rsi+48h]
0x180016f32  cmp     qword ptr [rsi+40h], 0
0x180016f37  jz      short loc_180016F3E
0x180016f39  cmp     [rdi], rbp
0x180016f3c  jnb     short loc_180016F76
0x180016f3e  mov     rdx, rbp; dwBytes
0x180016f41  mov     ecx, 8; dwFlags
0x180016f46  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180016f4b  mov     r14, rax
0x180016f4e  test    rax, rax
0x180016f51  jz      short loc_180016F72
0x180016f53  mov     rbx, [rsi+40h]
0x180016f57  call    cs:__imp_GetProcessHeap
0x180016f5d  mov     r8, rbx; lpMem
0x180016f60  xor     edx, edx; dwFlags
0x180016f62  mov     rcx, rax; hHeap
0x180016f65  call    cs:__imp_HeapFree
0x180016f6b  mov     [rsi+40h], r14
0x180016f6f  mov     [rdi], rbp
0x180016f72  lea     r14, [rsi+38h]
0x180016f76  mov     rcx, [rsi+40h]; Destination
0x180016f7a  test    rcx, rcx
0x180016f7d  jz      short loc_180016FCD
0x180016f7f  mov     rbx, [rdi]
0x180016f82  lea     r9, [rsi+10h]
0x180016f86  mov     r8, [r15+38h]
0x180016f8a  add     rbx, rcx
0x180016f8d  mov     rdx, rbx
0x180016f90  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016f95  mov     r8, [r15+80h]
0x180016f9c  lea     r9, [rsi+20h]
0x180016fa0  mov     rdx, rbx
0x180016fa3  mov     rcx, rax; Destination
0x180016fa6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016fab  mov     r8, [r15+18h]
0x180016faf  mov     r9, r14
0x180016fb2  mov     rdx, rbx
0x180016fb5  mov     rcx, rax; Destination
0x180016fb8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180016fbd  sub     rbx, rax
0x180016fc0  xor     edx, edx; Val
0x180016fc2  mov     r8, rbx; Size
0x180016fc5  mov     rcx, rax; void *
0x180016fc8  call    memset_0
0x180016fcd  add     rsp, 28h
0x180016fd1  pop     r15
0x180016fd3  pop     r14
0x180016fd5  pop     r13
0x180016fd7  pop     r12
0x180016fd9  pop     rdi
0x180016fda  pop     rsi
0x180016fdb  pop     rbp
0x180016fdc  pop     rbx
0x180016fdd  retn
```
