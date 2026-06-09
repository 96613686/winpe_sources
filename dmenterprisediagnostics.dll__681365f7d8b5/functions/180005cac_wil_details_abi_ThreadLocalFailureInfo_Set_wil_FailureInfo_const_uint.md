# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005cac`
- end: `0x180005def`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006060`

## callees

- `0x1800023e0`
- `0x180003398`
- `0x180003410`
- `0x180005764`
- `0x180005b68`
- `0x180005b8c`
- `0x180005cac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d5b`

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
0x180005cac  push    rbx
0x180005cae  push    rbp
0x180005caf  push    rsi
0x180005cb0  push    rdi
0x180005cb1  push    r12
0x180005cb3  push    r13
0x180005cb5  push    r14
0x180005cb7  push    r15
0x180005cb9  sub     rsp, 28h
0x180005cbd  mov     [rcx+4], r8d
0x180005cc1  lea     r14, [rcx+38h]
0x180005cc5  mov     eax, [rdx+8]
0x180005cc8  mov     rsi, rcx
0x180005ccb  mov     [rcx+8], eax
0x180005cce  mov     r15, rdx
0x180005cd1  mov     qword ptr [rcx+10h], 0
0x180005cd9  movzx   eax, word ptr [rdx+40h]
0x180005cdd  mov     [rcx+18h], ax
0x180005ce1  mov     al, [rdx]
0x180005ce3  mov     [rcx+1Ah], al
0x180005ce6  mov     qword ptr [rcx+20h], 0
0x180005cee  mov     rax, [rdx+88h]
0x180005cf5  mov     [rcx+28h], rax
0x180005cf9  mov     rax, [rdx+90h]
0x180005d00  mov     [rcx+30h], rax
0x180005d04  mov     qword ptr [r14], 0
0x180005d0b  mov     rcx, [rdx+18h]; this
0x180005d0f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005d14  mov     rcx, [r15+38h]; this
0x180005d18  mov     rbp, rax
0x180005d1b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005d20  mov     rcx, [r15+80h]; this
0x180005d27  add     rbp, rax
0x180005d2a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005d2f  add     rbp, rax
0x180005d32  lea     rdi, [rsi+48h]
0x180005d36  cmp     qword ptr [rsi+40h], 0
0x180005d3b  jz      short loc_180005D42
0x180005d3d  cmp     [rdi], rbp
0x180005d40  jnb     short loc_180005D86
0x180005d42  mov     rdx, rbp; dwBytes
0x180005d45  mov     ecx, 8; dwFlags
0x180005d4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005d4f  mov     r14, rax
0x180005d52  test    rax, rax
0x180005d55  jz      short loc_180005D82
0x180005d57  mov     rbx, [rsi+40h]
0x180005d5b  call    cs:__imp_GetProcessHeap
0x180005d62  nop     dword ptr [rax+rax+00h]
0x180005d67  mov     r8, rbx; lpMem
0x180005d6a  xor     edx, edx; dwFlags
0x180005d6c  mov     rcx, rax; hHeap
0x180005d6f  call    cs:__imp_HeapFree
0x180005d76  nop     dword ptr [rax+rax+00h]
0x180005d7b  mov     [rsi+40h], r14
0x180005d7f  mov     [rdi], rbp
0x180005d82  lea     r14, [rsi+38h]
0x180005d86  mov     rcx, [rsi+40h]; Destination
0x180005d8a  test    rcx, rcx
0x180005d8d  jz      short loc_180005DDD
0x180005d8f  mov     rbx, [rdi]
0x180005d92  lea     r9, [rsi+10h]
0x180005d96  mov     r8, [r15+38h]
0x180005d9a  add     rbx, rcx
0x180005d9d  mov     rdx, rbx
0x180005da0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005da5  mov     r8, [r15+80h]
0x180005dac  lea     r9, [rsi+20h]
0x180005db0  mov     rdx, rbx
0x180005db3  mov     rcx, rax; Destination
0x180005db6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005dbb  mov     r8, [r15+18h]
0x180005dbf  mov     r9, r14
0x180005dc2  mov     rdx, rbx
0x180005dc5  mov     rcx, rax; Destination
0x180005dc8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180005dcd  sub     rbx, rax
0x180005dd0  xor     edx, edx; Val
0x180005dd2  mov     r8, rbx; Size
0x180005dd5  mov     rcx, rax; void *
0x180005dd8  call    memset_0
0x180005ddd  add     rsp, 28h
0x180005de1  pop     r15
0x180005de3  pop     r14
0x180005de5  pop     r13
0x180005de7  pop     r12
0x180005de9  pop     rdi
0x180005dea  pop     rsi
0x180005deb  pop     rbp
0x180005dec  pop     rbx
0x180005ded  retn
```
