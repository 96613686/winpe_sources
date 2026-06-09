# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008b50`
- end: `0x180008c86`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008ee8`

## callees

- `0x18000343c`
- `0x1800048a0`
- `0x180004918`
- `0x18000871c`
- `0x180008a28`
- `0x180008a48`
- `0x180008b50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008c0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008c0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bff`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x180008b50  push    rbx
0x180008b52  push    rbp
0x180008b53  push    rsi
0x180008b54  push    rdi
0x180008b55  push    r12
0x180008b57  push    r13
0x180008b59  push    r14
0x180008b5b  push    r15
0x180008b5d  sub     rsp, 28h
0x180008b61  mov     [rcx+4], r8d
0x180008b65  lea     r14, [rcx+38h]
0x180008b69  mov     eax, [rdx+8]
0x180008b6c  mov     rsi, rcx
0x180008b6f  mov     [rcx+8], eax
0x180008b72  mov     r15, rdx
0x180008b75  mov     qword ptr [rcx+10h], 0
0x180008b7d  movzx   eax, word ptr [rdx+40h]
0x180008b81  mov     [rcx+18h], ax
0x180008b85  mov     al, [rdx]
0x180008b87  mov     [rcx+1Ah], al
0x180008b8a  mov     qword ptr [rcx+20h], 0
0x180008b92  mov     rax, [rdx+88h]
0x180008b99  mov     [rcx+28h], rax
0x180008b9d  mov     rax, [rdx+90h]
0x180008ba4  mov     [rcx+30h], rax
0x180008ba8  mov     qword ptr [r14], 0
0x180008baf  mov     rcx, [rdx+18h]; this
0x180008bb3  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180008bb8  mov     rcx, [r15+38h]; this
0x180008bbc  mov     rbp, rax
0x180008bbf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008bc4  mov     rcx, [r15+80h]; this
0x180008bcb  add     rbp, rax
0x180008bce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008bd3  add     rbp, rax
0x180008bd6  lea     rdi, [rsi+48h]
0x180008bda  cmp     qword ptr [rsi+40h], 0
0x180008bdf  jz      short loc_180008BE6
0x180008be1  cmp     [rdi], rbp
0x180008be4  jnb     short loc_180008C1E
0x180008be6  mov     rdx, rbp; dwBytes
0x180008be9  mov     ecx, 8; dwFlags
0x180008bee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008bf3  mov     r14, rax
0x180008bf6  test    rax, rax
0x180008bf9  jz      short loc_180008C1A
0x180008bfb  mov     rbx, [rsi+40h]
0x180008bff  call    cs:__imp_GetProcessHeap
0x180008c05  mov     r8, rbx; lpMem
0x180008c08  xor     edx, edx; dwFlags
0x180008c0a  mov     rcx, rax; hHeap
0x180008c0d  call    cs:__imp_HeapFree
0x180008c13  mov     [rsi+40h], r14
0x180008c17  mov     [rdi], rbp
0x180008c1a  lea     r14, [rsi+38h]
0x180008c1e  mov     rcx, [rsi+40h]; Destination
0x180008c22  test    rcx, rcx
0x180008c25  jz      short loc_180008C75
0x180008c27  mov     rbx, [rdi]
0x180008c2a  lea     r9, [rsi+10h]
0x180008c2e  mov     r8, [r15+38h]
0x180008c32  add     rbx, rcx
0x180008c35  mov     rdx, rbx
0x180008c38  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008c3d  mov     r8, [r15+80h]
0x180008c44  lea     r9, [rsi+20h]
0x180008c48  mov     rdx, rbx
0x180008c4b  mov     rcx, rax; Destination
0x180008c4e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008c53  mov     r8, [r15+18h]
0x180008c57  mov     r9, r14
0x180008c5a  mov     rdx, rbx
0x180008c5d  mov     rcx, rax; Destination
0x180008c60  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180008c65  sub     rbx, rax
0x180008c68  xor     edx, edx; Val
0x180008c6a  mov     r8, rbx; Size
0x180008c6d  mov     rcx, rax; void *
0x180008c70  call    memset_0
0x180008c75  add     rsp, 28h
0x180008c79  pop     r15
0x180008c7b  pop     r14
0x180008c7d  pop     r13
0x180008c7f  pop     r12
0x180008c81  pop     rdi
0x180008c82  pop     rsi
0x180008c83  pop     rbp
0x180008c84  pop     rbx
0x180008c85  retn
```
