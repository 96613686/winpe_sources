# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180028e04`
- end: `0x180028f74`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180029068`

## callees

- `0x18001c10c`
- `0x180026194`
- `0x180028114`
- `0x180028cb0`
- `0x180028cd0`
- `0x180028e04`
- `0x18002cb58`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028eac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028eba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028eba`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x180028e04  push    rbx
0x180028e06  push    rbp
0x180028e07  push    rsi
0x180028e08  push    rdi
0x180028e09  push    r12
0x180028e0b  push    r13
0x180028e0d  push    r14
0x180028e0f  push    r15
0x180028e11  sub     rsp, 28h
0x180028e15  mov     [rcx+4], r8d
0x180028e19  lea     rbx, [rcx+20h]
0x180028e1d  mov     eax, [rdx+8]
0x180028e20  lea     rsi, [rcx+38h]
0x180028e24  mov     [rcx+8], eax
0x180028e27  xor     r12d, r12d
0x180028e2a  mov     [rcx+10h], r12
0x180028e2e  mov     rbp, rcx
0x180028e31  movzx   eax, word ptr [rdx+40h]
0x180028e35  mov     r14, rdx
0x180028e38  mov     [rcx+18h], ax
0x180028e3c  mov     al, [rdx]
0x180028e3e  mov     [rcx+1Ah], al
0x180028e41  mov     [rbx], r12
0x180028e44  mov     rax, [rdx+88h]
0x180028e4b  mov     [rcx+28h], rax
0x180028e4f  mov     rax, [rdx+90h]
0x180028e56  mov     [rcx+30h], rax
0x180028e5a  mov     [rsi], r12
0x180028e5d  mov     rcx, [rdx+18h]; this
0x180028e61  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180028e66  mov     rcx, [r14+38h]; this
0x180028e6a  mov     r15, rax
0x180028e6d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180028e72  mov     rcx, [r14+80h]; this
0x180028e79  add     r15, rax
0x180028e7c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180028e81  add     r15, rax
0x180028e84  lea     rdi, [rbp+48h]
0x180028e88  cmp     [rbp+40h], r12
0x180028e8c  jz      short loc_180028E93
0x180028e8e  cmp     [rdi], r15
0x180028e91  jnb     short loc_180028ECE
0x180028e93  mov     rdx, r15; dwBytes
0x180028e96  mov     ecx, 8; dwFlags
0x180028e9b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180028ea0  mov     r12, rax
0x180028ea3  test    rax, rax
0x180028ea6  jz      short loc_180028ECB
0x180028ea8  mov     rbx, [rbp+40h]
0x180028eac  call    cs:__imp_GetProcessHeap
0x180028eb2  mov     r8, rbx; lpMem
0x180028eb5  xor     edx, edx; dwFlags
0x180028eb7  mov     rcx, rax; hHeap
0x180028eba  call    cs:__imp_HeapFree
0x180028ec0  mov     [rbp+40h], r12
0x180028ec4  lea     rbx, [rbp+20h]
0x180028ec8  mov     [rdi], r15
0x180028ecb  xor     r12d, r12d
0x180028ece  mov     rcx, [rbp+40h]; Destination
0x180028ed2  test    rcx, rcx
0x180028ed5  jz      loc_180028F63
0x180028edb  mov     rdi, [rdi]
0x180028ede  lea     r9, [rbp+10h]
0x180028ee2  mov     r8, [r14+38h]
0x180028ee6  add     rdi, rcx
0x180028ee9  mov     rdx, rdi
0x180028eec  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180028ef1  mov     r8, [r14+80h]
0x180028ef8  mov     r9, rbx
0x180028efb  mov     rdx, rdi
0x180028efe  mov     rcx, rax; Destination
0x180028f01  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180028f06  mov     rbx, rax
0x180028f09  cmp     rax, rdi
0x180028f0c  jz      short loc_180028F4B
0x180028f0e  mov     rcx, [r14+18h]; this
0x180028f12  test    rcx, rcx
0x180028f15  jz      short loc_180028F4B
0x180028f17  cmp     [rcx], r12w
0x180028f1b  jz      short loc_180028F4B
0x180028f1d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180028f22  mov     rdx, rdi
0x180028f25  mov     r14, rax
0x180028f28  sub     rdx, rbx; DestinationSize
0x180028f2b  cmp     rdx, rax
0x180028f2e  jb      short loc_180028F4B
0x180028f30  mov     r8, rcx; Source
0x180028f33  mov     r9, rax; SourceSize
0x180028f36  mov     rcx, rbx; Destination
0x180028f39  call    memcpy_s
0x180028f3e  test    rsi, rsi
0x180028f41  jz      short loc_180028F46
0x180028f43  mov     [rsi], rbx
0x180028f46  add     rbx, r14
0x180028f49  jmp     short loc_180028F53
0x180028f4b  test    rsi, rsi
0x180028f4e  jz      short loc_180028F53
0x180028f50  mov     [rsi], r12
0x180028f53  sub     rdi, rbx
0x180028f56  xor     edx, edx; Val
0x180028f58  mov     r8, rdi; Size
0x180028f5b  mov     rcx, rbx; void *
0x180028f5e  call    memset_0
0x180028f63  add     rsp, 28h
0x180028f67  pop     r15
0x180028f69  pop     r14
0x180028f6b  pop     r13
0x180028f6d  pop     r12
0x180028f6f  pop     rdi
0x180028f70  pop     rsi
0x180028f71  pop     rbp
0x180028f72  pop     rbx
0x180028f73  retn
```
