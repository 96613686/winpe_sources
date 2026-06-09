# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007cb0`
- end: `0x180007e34`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `388`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007e3c`

## callees

- `0x18000634c`
- `0x180007a80`
- `0x180007bd4`
- `0x180007bf8`
- `0x180007cb0`
- `0x180009e16`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007df1`
- `msvcrt!memcpy_s` at `0x180007df1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d6c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
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
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x180007cb0  push    rbx
0x180007cb2  push    rbp
0x180007cb3  push    rsi
0x180007cb4  push    rdi
0x180007cb5  push    r12
0x180007cb7  push    r13
0x180007cb9  push    r14
0x180007cbb  push    r15
0x180007cbd  sub     rsp, 28h
0x180007cc1  mov     [rcx+4], r8d
0x180007cc5  lea     rbx, [rcx+20h]
0x180007cc9  mov     eax, [rdx+8]
0x180007ccc  lea     rsi, [rcx+38h]
0x180007cd0  mov     [rcx+8], eax
0x180007cd3  xor     r12d, r12d
0x180007cd6  mov     [rcx+10h], r12
0x180007cda  mov     rbp, rcx
0x180007cdd  movzx   eax, word ptr [rdx+40h]
0x180007ce1  mov     r14, rdx
0x180007ce4  mov     [rcx+18h], ax
0x180007ce8  mov     al, [rdx]
0x180007cea  mov     [rcx+1Ah], al
0x180007ced  mov     [rbx], r12
0x180007cf0  mov     rax, [rdx+88h]
0x180007cf7  mov     [rcx+28h], rax
0x180007cfb  mov     rax, [rdx+90h]
0x180007d02  mov     [rcx+30h], rax
0x180007d06  mov     [rsi], r12
0x180007d09  mov     rcx, [rdx+18h]; this
0x180007d0d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007d12  mov     rcx, [r14+38h]; this
0x180007d16  mov     r15, rax
0x180007d19  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007d1e  mov     rcx, [r14+80h]; this
0x180007d25  add     r15, rax
0x180007d28  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007d2d  add     r15, rax
0x180007d30  lea     rdi, [rbp+48h]
0x180007d34  cmp     [rbp+40h], r12
0x180007d38  jz      short loc_180007D3F
0x180007d3a  cmp     [rdi], r15
0x180007d3d  jnb     short loc_180007D86
0x180007d3f  mov     rdx, r15; dwBytes
0x180007d42  mov     ecx, 8; dwFlags
0x180007d47  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007d4c  mov     r12, rax
0x180007d4f  test    rax, rax
0x180007d52  jz      short loc_180007D83
0x180007d54  mov     rbx, [rbp+40h]
0x180007d58  call    cs:__imp_GetProcessHeap
0x180007d5f  nop     dword ptr [rax+rax+00h]
0x180007d64  mov     r8, rbx; lpMem
0x180007d67  xor     edx, edx; dwFlags
0x180007d69  mov     rcx, rax; hHeap
0x180007d6c  call    cs:__imp_HeapFree
0x180007d73  nop     dword ptr [rax+rax+00h]
0x180007d78  mov     [rbp+40h], r12
0x180007d7c  lea     rbx, [rbp+20h]
0x180007d80  mov     [rdi], r15
0x180007d83  xor     r12d, r12d
0x180007d86  mov     rcx, [rbp+40h]; Destination
0x180007d8a  test    rcx, rcx
0x180007d8d  jz      loc_180007E22
0x180007d93  mov     rdi, [rdi]
0x180007d96  lea     r9, [rbp+10h]
0x180007d9a  mov     r8, [r14+38h]
0x180007d9e  add     rdi, rcx
0x180007da1  mov     rdx, rdi
0x180007da4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007da9  mov     r8, [r14+80h]
0x180007db0  mov     r9, rbx
0x180007db3  mov     rdx, rdi
0x180007db6  mov     rcx, rax; Destination
0x180007db9  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007dbe  mov     rbx, rax
0x180007dc1  cmp     rax, rdi
0x180007dc4  jz      short loc_180007E0A
0x180007dc6  mov     rcx, [r14+18h]; this
0x180007dca  test    rcx, rcx
0x180007dcd  jz      short loc_180007E0A
0x180007dcf  cmp     [rcx], r12w
0x180007dd3  jz      short loc_180007E0A
0x180007dd5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007dda  mov     rdx, rdi
0x180007ddd  mov     r14, rax
0x180007de0  sub     rdx, rbx; DestinationSize
0x180007de3  cmp     rdx, rax
0x180007de6  jb      short loc_180007E0A
0x180007de8  mov     r8, rcx; Source
0x180007deb  mov     r9, rax; SourceSize
0x180007dee  mov     rcx, rbx; Destination
0x180007df1  call    cs:__imp_memcpy_s
0x180007df8  nop     dword ptr [rax+rax+00h]
0x180007dfd  test    rsi, rsi
0x180007e00  jz      short loc_180007E05
0x180007e02  mov     [rsi], rbx
0x180007e05  add     rbx, r14
0x180007e08  jmp     short loc_180007E12
0x180007e0a  test    rsi, rsi
0x180007e0d  jz      short loc_180007E12
0x180007e0f  mov     [rsi], r12
0x180007e12  sub     rdi, rbx
0x180007e15  xor     edx, edx; Val
0x180007e17  mov     r8, rdi; Size
0x180007e1a  mov     rcx, rbx; void *
0x180007e1d  call    memset_0
0x180007e22  add     rsp, 28h
0x180007e26  pop     r15
0x180007e28  pop     r14
0x180007e2a  pop     r13
0x180007e2c  pop     r12
0x180007e2e  pop     rdi
0x180007e2f  pop     rsi
0x180007e30  pop     rbp
0x180007e31  pop     rbx
0x180007e32  retn
```
