# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180013d54`
- end: `0x180013ec5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013fb8`

## callees

- `0x18001069c`
- `0x180012ef4`
- `0x180013bd4`
- `0x180013bf4`
- `0x180013d54`
- `0x18001ecee`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013e89`
- `msvcrt!memcpy_s` at `0x180013e89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013e0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013dfc`

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
0x180013d54  push    rbx
0x180013d56  push    rbp
0x180013d57  push    rsi
0x180013d58  push    rdi
0x180013d59  push    r12
0x180013d5b  push    r13
0x180013d5d  push    r14
0x180013d5f  push    r15
0x180013d61  sub     rsp, 28h
0x180013d65  mov     [rcx+4], r8d
0x180013d69  lea     rbx, [rcx+20h]
0x180013d6d  mov     eax, [rdx+8]
0x180013d70  lea     rsi, [rcx+38h]
0x180013d74  mov     [rcx+8], eax
0x180013d77  xor     r12d, r12d
0x180013d7a  mov     [rcx+10h], r12
0x180013d7e  mov     rbp, rcx
0x180013d81  movzx   eax, word ptr [rdx+40h]
0x180013d85  mov     r14, rdx
0x180013d88  mov     [rcx+18h], ax
0x180013d8c  mov     al, [rdx]
0x180013d8e  mov     [rcx+1Ah], al
0x180013d91  mov     [rbx], r12
0x180013d94  mov     rax, [rdx+88h]
0x180013d9b  mov     [rcx+28h], rax
0x180013d9f  mov     rax, [rdx+90h]
0x180013da6  mov     [rcx+30h], rax
0x180013daa  mov     [rsi], r12
0x180013dad  mov     rcx, [rdx+18h]; this
0x180013db1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180013db6  mov     rcx, [r14+38h]; this
0x180013dba  mov     r15, rax
0x180013dbd  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180013dc2  mov     rcx, [r14+80h]; this
0x180013dc9  add     r15, rax
0x180013dcc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180013dd1  add     r15, rax
0x180013dd4  lea     rdi, [rbp+48h]
0x180013dd8  cmp     [rbp+40h], r12
0x180013ddc  jz      short loc_180013DE3
0x180013dde  cmp     [rdi], r15
0x180013de1  jnb     short loc_180013E1E
0x180013de3  mov     rdx, r15; dwBytes
0x180013de6  mov     ecx, 8; dwFlags
0x180013deb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013df0  mov     r12, rax
0x180013df3  test    rax, rax
0x180013df6  jz      short loc_180013E1B
0x180013df8  mov     rbx, [rbp+40h]
0x180013dfc  call    cs:__imp_GetProcessHeap
0x180013e02  mov     r8, rbx; lpMem
0x180013e05  xor     edx, edx; dwFlags
0x180013e07  mov     rcx, rax; hHeap
0x180013e0a  call    cs:__imp_HeapFree
0x180013e10  mov     [rbp+40h], r12
0x180013e14  lea     rbx, [rbp+20h]
0x180013e18  mov     [rdi], r15
0x180013e1b  xor     r12d, r12d
0x180013e1e  mov     rcx, [rbp+40h]; Destination
0x180013e22  test    rcx, rcx
0x180013e25  jz      loc_180013EB4
0x180013e2b  mov     rdi, [rdi]
0x180013e2e  lea     r9, [rbp+10h]
0x180013e32  mov     r8, [r14+38h]
0x180013e36  add     rdi, rcx
0x180013e39  mov     rdx, rdi
0x180013e3c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180013e41  mov     r8, [r14+80h]
0x180013e48  mov     r9, rbx
0x180013e4b  mov     rdx, rdi
0x180013e4e  mov     rcx, rax; Destination
0x180013e51  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180013e56  mov     rbx, rax
0x180013e59  cmp     rax, rdi
0x180013e5c  jz      short loc_180013E9C
0x180013e5e  mov     rcx, [r14+18h]; this
0x180013e62  test    rcx, rcx
0x180013e65  jz      short loc_180013E9C
0x180013e67  cmp     [rcx], r12w
0x180013e6b  jz      short loc_180013E9C
0x180013e6d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180013e72  mov     rdx, rdi
0x180013e75  mov     r14, rax
0x180013e78  sub     rdx, rbx; DestinationSize
0x180013e7b  cmp     rdx, rax
0x180013e7e  jb      short loc_180013E9C
0x180013e80  mov     r8, rcx; Source
0x180013e83  mov     r9, rax; SourceSize
0x180013e86  mov     rcx, rbx; Destination
0x180013e89  call    cs:__imp_memcpy_s
0x180013e8f  test    rsi, rsi
0x180013e92  jz      short loc_180013E97
0x180013e94  mov     [rsi], rbx
0x180013e97  add     rbx, r14
0x180013e9a  jmp     short loc_180013EA4
0x180013e9c  test    rsi, rsi
0x180013e9f  jz      short loc_180013EA4
0x180013ea1  mov     [rsi], r12
0x180013ea4  sub     rdi, rbx
0x180013ea7  xor     edx, edx; Val
0x180013ea9  mov     r8, rdi; Size
0x180013eac  mov     rcx, rbx; void *
0x180013eaf  call    memset_0
0x180013eb4  add     rsp, 28h
0x180013eb8  pop     r15
0x180013eba  pop     r14
0x180013ebc  pop     r13
0x180013ebe  pop     r12
0x180013ec0  pop     rdi
0x180013ec1  pop     rsi
0x180013ec2  pop     rbp
0x180013ec3  pop     rbx
0x180013ec4  retn
```
