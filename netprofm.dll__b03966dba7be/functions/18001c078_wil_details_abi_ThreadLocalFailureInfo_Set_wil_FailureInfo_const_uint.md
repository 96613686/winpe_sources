# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001c078`
- end: `0x18001c1ae`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c500`

## callees

- `0x180012f40`
- `0x180014c14`
- `0x180014c8c`
- `0x18001a66c`
- `0x18001bef8`
- `0x18001bf18`
- `0x18001c078`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c135`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c127`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c127`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  wchar_t **v3; // r14
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
  char *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (wchar_t **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v3 = (wchar_t **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = wil::details::WriteResultString<char const *>(v17, v16, *((wil::details **)a2 + 16), (char **)this + 4);
    v19 = wil::details::WriteResultString<wchar_t const *>(
            (wchar_t *)v18,
            (const wchar_t *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18001c078  push    rbx
0x18001c07a  push    rbp
0x18001c07b  push    rsi
0x18001c07c  push    rdi
0x18001c07d  push    r12
0x18001c07f  push    r13
0x18001c081  push    r14
0x18001c083  push    r15
0x18001c085  sub     rsp, 28h
0x18001c089  mov     [rcx+4], r8d
0x18001c08d  lea     r14, [rcx+38h]
0x18001c091  mov     eax, [rdx+8]
0x18001c094  mov     rsi, rcx
0x18001c097  mov     [rcx+8], eax
0x18001c09a  mov     r15, rdx
0x18001c09d  mov     qword ptr [rcx+10h], 0
0x18001c0a5  movzx   eax, word ptr [rdx+40h]
0x18001c0a9  mov     [rcx+18h], ax
0x18001c0ad  mov     al, [rdx]
0x18001c0af  mov     [rcx+1Ah], al
0x18001c0b2  mov     qword ptr [rcx+20h], 0
0x18001c0ba  mov     rax, [rdx+88h]
0x18001c0c1  mov     [rcx+28h], rax
0x18001c0c5  mov     rax, [rdx+90h]
0x18001c0cc  mov     [rcx+30h], rax
0x18001c0d0  mov     qword ptr [r14], 0
0x18001c0d7  mov     rcx, [rdx+18h]; this
0x18001c0db  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18001c0e0  mov     rcx, [r15+38h]; this
0x18001c0e4  mov     rbp, rax
0x18001c0e7  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001c0ec  mov     rcx, [r15+80h]; this
0x18001c0f3  add     rbp, rax
0x18001c0f6  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001c0fb  add     rbp, rax
0x18001c0fe  lea     rdi, [rsi+48h]
0x18001c102  cmp     qword ptr [rsi+40h], 0
0x18001c107  jz      short loc_18001C10E
0x18001c109  cmp     [rdi], rbp
0x18001c10c  jnb     short loc_18001C146
0x18001c10e  mov     rdx, rbp; dwBytes
0x18001c111  mov     ecx, 8; dwFlags
0x18001c116  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001c11b  mov     r14, rax
0x18001c11e  test    rax, rax
0x18001c121  jz      short loc_18001C142
0x18001c123  mov     rbx, [rsi+40h]
0x18001c127  call    cs:__imp_GetProcessHeap
0x18001c12d  mov     r8, rbx; lpMem
0x18001c130  xor     edx, edx; dwFlags
0x18001c132  mov     rcx, rax; hHeap
0x18001c135  call    cs:__imp_HeapFree
0x18001c13b  mov     [rsi+40h], r14
0x18001c13f  mov     [rdi], rbp
0x18001c142  lea     r14, [rsi+38h]
0x18001c146  mov     rcx, [rsi+40h]; Destination
0x18001c14a  test    rcx, rcx
0x18001c14d  jz      short loc_18001C19D
0x18001c14f  mov     rbx, [rdi]
0x18001c152  lea     r9, [rsi+10h]
0x18001c156  mov     r8, [r15+38h]
0x18001c15a  add     rbx, rcx
0x18001c15d  mov     rdx, rbx
0x18001c160  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001c165  mov     r8, [r15+80h]
0x18001c16c  lea     r9, [rsi+20h]
0x18001c170  mov     rdx, rbx
0x18001c173  mov     rcx, rax; Destination
0x18001c176  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001c17b  mov     r8, [r15+18h]
0x18001c17f  mov     r9, r14
0x18001c182  mov     rdx, rbx
0x18001c185  mov     rcx, rax; Destination
0x18001c188  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x18001c18d  sub     rbx, rax
0x18001c190  xor     edx, edx; Val
0x18001c192  mov     r8, rbx; Size
0x18001c195  mov     rcx, rax; void *
0x18001c198  call    memset_0
0x18001c19d  add     rsp, 28h
0x18001c1a1  pop     r15
0x18001c1a3  pop     r14
0x18001c1a5  pop     r13
0x18001c1a7  pop     r12
0x18001c1a9  pop     rdi
0x18001c1aa  pop     rsi
0x18001c1ab  pop     rbp
0x18001c1ac  pop     rbx
0x18001c1ad  retn
```
