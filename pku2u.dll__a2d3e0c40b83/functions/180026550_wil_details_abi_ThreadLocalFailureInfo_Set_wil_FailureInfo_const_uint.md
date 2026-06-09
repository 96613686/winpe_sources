# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180026550`
- end: `0x180026686`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800268e8`

## callees

- `0x180021a54`
- `0x18002505c`
- `0x1800250d4`
- `0x180026280`
- `0x180026424`
- `0x180026444`
- `0x180026550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800265ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800265ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002660d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002660d`

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
0x180026550  push    rbx
0x180026552  push    rbp
0x180026553  push    rsi
0x180026554  push    rdi
0x180026555  push    r12
0x180026557  push    r13
0x180026559  push    r14
0x18002655b  push    r15
0x18002655d  sub     rsp, 28h
0x180026561  mov     [rcx+4], r8d
0x180026565  lea     r14, [rcx+38h]
0x180026569  mov     eax, [rdx+8]
0x18002656c  mov     rsi, rcx
0x18002656f  mov     [rcx+8], eax
0x180026572  mov     r15, rdx
0x180026575  mov     qword ptr [rcx+10h], 0
0x18002657d  movzx   eax, word ptr [rdx+40h]
0x180026581  mov     [rcx+18h], ax
0x180026585  mov     al, [rdx]
0x180026587  mov     [rcx+1Ah], al
0x18002658a  mov     qword ptr [rcx+20h], 0
0x180026592  mov     rax, [rdx+88h]
0x180026599  mov     [rcx+28h], rax
0x18002659d  mov     rax, [rdx+90h]
0x1800265a4  mov     [rcx+30h], rax
0x1800265a8  mov     qword ptr [r14], 0
0x1800265af  mov     rcx, [rdx+18h]; this
0x1800265b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800265b8  mov     rcx, [r15+38h]; this
0x1800265bc  mov     rbp, rax
0x1800265bf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800265c4  mov     rcx, [r15+80h]; this
0x1800265cb  add     rbp, rax
0x1800265ce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800265d3  add     rbp, rax
0x1800265d6  lea     rdi, [rsi+48h]
0x1800265da  cmp     qword ptr [rsi+40h], 0
0x1800265df  jz      short loc_1800265E6
0x1800265e1  cmp     [rdi], rbp
0x1800265e4  jnb     short loc_18002661E
0x1800265e6  mov     rdx, rbp; dwBytes
0x1800265e9  mov     ecx, 8; dwFlags
0x1800265ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800265f3  mov     r14, rax
0x1800265f6  test    rax, rax
0x1800265f9  jz      short loc_18002661A
0x1800265fb  mov     rbx, [rsi+40h]
0x1800265ff  call    cs:__imp_GetProcessHeap
0x180026605  mov     r8, rbx; lpMem
0x180026608  xor     edx, edx; dwFlags
0x18002660a  mov     rcx, rax; hHeap
0x18002660d  call    cs:__imp_HeapFree
0x180026613  mov     [rsi+40h], r14
0x180026617  mov     [rdi], rbp
0x18002661a  lea     r14, [rsi+38h]
0x18002661e  mov     rcx, [rsi+40h]; Destination
0x180026622  test    rcx, rcx
0x180026625  jz      short loc_180026675
0x180026627  mov     rbx, [rdi]
0x18002662a  lea     r9, [rsi+10h]
0x18002662e  mov     r8, [r15+38h]
0x180026632  add     rbx, rcx
0x180026635  mov     rdx, rbx
0x180026638  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002663d  mov     r8, [r15+80h]
0x180026644  lea     r9, [rsi+20h]
0x180026648  mov     rdx, rbx
0x18002664b  mov     rcx, rax; Destination
0x18002664e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180026653  mov     r8, [r15+18h]
0x180026657  mov     r9, r14
0x18002665a  mov     rdx, rbx
0x18002665d  mov     rcx, rax; Destination
0x180026660  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180026665  sub     rbx, rax
0x180026668  xor     edx, edx; Val
0x18002666a  mov     r8, rbx; Size
0x18002666d  mov     rcx, rax; void *
0x180026670  call    memset_0
0x180026675  add     rsp, 28h
0x180026679  pop     r15
0x18002667b  pop     r14
0x18002667d  pop     r13
0x18002667f  pop     r12
0x180026681  pop     rdi
0x180026682  pop     rsi
0x180026683  pop     rbp
0x180026684  pop     rbx
0x180026685  retn
```
