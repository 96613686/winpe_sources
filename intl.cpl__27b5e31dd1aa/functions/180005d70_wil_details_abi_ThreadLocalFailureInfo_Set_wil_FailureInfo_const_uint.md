# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005d70`
- end: `0x180005ea6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006108`

## callees

- `0x1800040e0`
- `0x180004158`
- `0x180005ad8`
- `0x180005c48`
- `0x180005c68`
- `0x180005d70`
- `0x18002a112`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e2d`

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
0x180005d70  push    rbx
0x180005d72  push    rbp
0x180005d73  push    rsi
0x180005d74  push    rdi
0x180005d75  push    r12
0x180005d77  push    r13
0x180005d79  push    r14
0x180005d7b  push    r15
0x180005d7d  sub     rsp, 28h
0x180005d81  mov     [rcx+4], r8d
0x180005d85  lea     r14, [rcx+38h]
0x180005d89  mov     eax, [rdx+8]
0x180005d8c  mov     rsi, rcx
0x180005d8f  mov     [rcx+8], eax
0x180005d92  mov     r15, rdx
0x180005d95  mov     qword ptr [rcx+10h], 0
0x180005d9d  movzx   eax, word ptr [rdx+40h]
0x180005da1  mov     [rcx+18h], ax
0x180005da5  mov     al, [rdx]
0x180005da7  mov     [rcx+1Ah], al
0x180005daa  mov     qword ptr [rcx+20h], 0
0x180005db2  mov     rax, [rdx+88h]
0x180005db9  mov     [rcx+28h], rax
0x180005dbd  mov     rax, [rdx+90h]
0x180005dc4  mov     [rcx+30h], rax
0x180005dc8  mov     qword ptr [r14], 0
0x180005dcf  mov     rcx, [rdx+18h]; this
0x180005dd3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005dd8  mov     rcx, [r15+38h]; this
0x180005ddc  mov     rbp, rax
0x180005ddf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005de4  mov     rcx, [r15+80h]; this
0x180005deb  add     rbp, rax
0x180005dee  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005df3  add     rbp, rax
0x180005df6  lea     rdi, [rsi+48h]
0x180005dfa  cmp     qword ptr [rsi+40h], 0
0x180005dff  jz      short loc_180005E06
0x180005e01  cmp     [rdi], rbp
0x180005e04  jnb     short loc_180005E3E
0x180005e06  mov     rdx, rbp; dwBytes
0x180005e09  mov     ecx, 8; dwFlags
0x180005e0e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005e13  mov     r14, rax
0x180005e16  test    rax, rax
0x180005e19  jz      short loc_180005E3A
0x180005e1b  mov     rbx, [rsi+40h]
0x180005e1f  call    cs:__imp_GetProcessHeap
0x180005e25  mov     r8, rbx; lpMem
0x180005e28  xor     edx, edx; dwFlags
0x180005e2a  mov     rcx, rax; hHeap
0x180005e2d  call    cs:__imp_HeapFree
0x180005e33  mov     [rsi+40h], r14
0x180005e37  mov     [rdi], rbp
0x180005e3a  lea     r14, [rsi+38h]
0x180005e3e  mov     rcx, [rsi+40h]; Destination
0x180005e42  test    rcx, rcx
0x180005e45  jz      short loc_180005E95
0x180005e47  mov     rbx, [rdi]
0x180005e4a  lea     r9, [rsi+10h]
0x180005e4e  mov     r8, [r15+38h]
0x180005e52  add     rbx, rcx
0x180005e55  mov     rdx, rbx
0x180005e58  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005e5d  mov     r8, [r15+80h]
0x180005e64  lea     r9, [rsi+20h]
0x180005e68  mov     rdx, rbx
0x180005e6b  mov     rcx, rax; Destination
0x180005e6e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005e73  mov     r8, [r15+18h]
0x180005e77  mov     r9, r14
0x180005e7a  mov     rdx, rbx
0x180005e7d  mov     rcx, rax; Destination
0x180005e80  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180005e85  sub     rbx, rax
0x180005e88  xor     edx, edx; Val
0x180005e8a  mov     r8, rbx; Size
0x180005e8d  mov     rcx, rax; void *
0x180005e90  call    memset_0
0x180005e95  add     rsp, 28h
0x180005e99  pop     r15
0x180005e9b  pop     r14
0x180005e9d  pop     r13
0x180005e9f  pop     r12
0x180005ea1  pop     rdi
0x180005ea2  pop     rsi
0x180005ea3  pop     rbp
0x180005ea4  pop     rbx
0x180005ea5  retn
```
