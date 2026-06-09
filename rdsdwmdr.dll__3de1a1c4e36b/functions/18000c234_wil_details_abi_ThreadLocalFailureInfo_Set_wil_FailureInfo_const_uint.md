# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c234`
- end: `0x18000c3a5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c3ac`

## callees

- `0x1800075f4`
- `0x18000b98c`
- `0x18000bcf4`
- `0x18000bd14`
- `0x18000c234`
- `0x18002b93a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c369`
- `msvcrt!memcpy_s` at `0x18000c369`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2dc`

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
0x18000c234  push    rbx
0x18000c236  push    rbp
0x18000c237  push    rsi
0x18000c238  push    rdi
0x18000c239  push    r12
0x18000c23b  push    r13
0x18000c23d  push    r14
0x18000c23f  push    r15
0x18000c241  sub     rsp, 28h
0x18000c245  mov     [rcx+4], r8d
0x18000c249  lea     rbx, [rcx+20h]
0x18000c24d  mov     eax, [rdx+8]
0x18000c250  lea     rsi, [rcx+38h]
0x18000c254  mov     [rcx+8], eax
0x18000c257  xor     r12d, r12d
0x18000c25a  mov     [rcx+10h], r12
0x18000c25e  mov     rbp, rcx
0x18000c261  movzx   eax, word ptr [rdx+40h]
0x18000c265  mov     r14, rdx
0x18000c268  mov     [rcx+18h], ax
0x18000c26c  mov     al, [rdx]
0x18000c26e  mov     [rcx+1Ah], al
0x18000c271  mov     [rbx], r12
0x18000c274  mov     rax, [rdx+88h]
0x18000c27b  mov     [rcx+28h], rax
0x18000c27f  mov     rax, [rdx+90h]
0x18000c286  mov     [rcx+30h], rax
0x18000c28a  mov     [rsi], r12
0x18000c28d  mov     rcx, [rdx+18h]; this
0x18000c291  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c296  mov     rcx, [r14+38h]; this
0x18000c29a  mov     r15, rax
0x18000c29d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c2a2  mov     rcx, [r14+80h]; this
0x18000c2a9  add     r15, rax
0x18000c2ac  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c2b1  add     r15, rax
0x18000c2b4  lea     rdi, [rbp+48h]
0x18000c2b8  cmp     [rbp+40h], r12
0x18000c2bc  jz      short loc_18000C2C3
0x18000c2be  cmp     [rdi], r15
0x18000c2c1  jnb     short loc_18000C2FE
0x18000c2c3  mov     rdx, r15; dwBytes
0x18000c2c6  mov     ecx, 8; dwFlags
0x18000c2cb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c2d0  mov     r12, rax
0x18000c2d3  test    rax, rax
0x18000c2d6  jz      short loc_18000C2FB
0x18000c2d8  mov     rbx, [rbp+40h]
0x18000c2dc  call    cs:__imp_GetProcessHeap
0x18000c2e2  mov     r8, rbx; lpMem
0x18000c2e5  xor     edx, edx; dwFlags
0x18000c2e7  mov     rcx, rax; hHeap
0x18000c2ea  call    cs:__imp_HeapFree
0x18000c2f0  mov     [rbp+40h], r12
0x18000c2f4  lea     rbx, [rbp+20h]
0x18000c2f8  mov     [rdi], r15
0x18000c2fb  xor     r12d, r12d
0x18000c2fe  mov     rcx, [rbp+40h]; Destination
0x18000c302  test    rcx, rcx
0x18000c305  jz      loc_18000C394
0x18000c30b  mov     rdi, [rdi]
0x18000c30e  lea     r9, [rbp+10h]
0x18000c312  mov     r8, [r14+38h]
0x18000c316  add     rdi, rcx
0x18000c319  mov     rdx, rdi
0x18000c31c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c321  mov     r8, [r14+80h]
0x18000c328  mov     r9, rbx
0x18000c32b  mov     rdx, rdi
0x18000c32e  mov     rcx, rax; Destination
0x18000c331  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c336  mov     rbx, rax
0x18000c339  cmp     rax, rdi
0x18000c33c  jz      short loc_18000C37C
0x18000c33e  mov     rcx, [r14+18h]; this
0x18000c342  test    rcx, rcx
0x18000c345  jz      short loc_18000C37C
0x18000c347  cmp     [rcx], r12w
0x18000c34b  jz      short loc_18000C37C
0x18000c34d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c352  mov     rdx, rdi
0x18000c355  mov     r14, rax
0x18000c358  sub     rdx, rbx; DestinationSize
0x18000c35b  cmp     rdx, rax
0x18000c35e  jb      short loc_18000C37C
0x18000c360  mov     r8, rcx; Source
0x18000c363  mov     r9, rax; SourceSize
0x18000c366  mov     rcx, rbx; Destination
0x18000c369  call    cs:__imp_memcpy_s
0x18000c36f  test    rsi, rsi
0x18000c372  jz      short loc_18000C377
0x18000c374  mov     [rsi], rbx
0x18000c377  add     rbx, r14
0x18000c37a  jmp     short loc_18000C384
0x18000c37c  test    rsi, rsi
0x18000c37f  jz      short loc_18000C384
0x18000c381  mov     [rsi], r12
0x18000c384  sub     rdi, rbx
0x18000c387  xor     edx, edx; Val
0x18000c389  mov     r8, rdi; Size
0x18000c38c  mov     rcx, rbx; void *
0x18000c38f  call    memset_0
0x18000c394  add     rsp, 28h
0x18000c398  pop     r15
0x18000c39a  pop     r14
0x18000c39c  pop     r13
0x18000c39e  pop     r12
0x18000c3a0  pop     rdi
0x18000c3a1  pop     rsi
0x18000c3a2  pop     rbp
0x18000c3a3  pop     rbx
0x18000c3a4  retn
```
