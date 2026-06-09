# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005954`
- end: `0x180005a97`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005d08`

## callees

- `0x180002088`
- `0x1800038ac`
- `0x180003924`
- `0x180005444`
- `0x180005818`
- `0x18000583c`
- `0x180005954`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a03`

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
0x180005954  push    rbx
0x180005956  push    rbp
0x180005957  push    rsi
0x180005958  push    rdi
0x180005959  push    r12
0x18000595b  push    r13
0x18000595d  push    r14
0x18000595f  push    r15
0x180005961  sub     rsp, 28h
0x180005965  mov     [rcx+4], r8d
0x180005969  lea     r14, [rcx+38h]
0x18000596d  mov     eax, [rdx+8]
0x180005970  mov     rsi, rcx
0x180005973  mov     [rcx+8], eax
0x180005976  mov     r15, rdx
0x180005979  mov     qword ptr [rcx+10h], 0
0x180005981  movzx   eax, word ptr [rdx+40h]
0x180005985  mov     [rcx+18h], ax
0x180005989  mov     al, [rdx]
0x18000598b  mov     [rcx+1Ah], al
0x18000598e  mov     qword ptr [rcx+20h], 0
0x180005996  mov     rax, [rdx+88h]
0x18000599d  mov     [rcx+28h], rax
0x1800059a1  mov     rax, [rdx+90h]
0x1800059a8  mov     [rcx+30h], rax
0x1800059ac  mov     qword ptr [r14], 0
0x1800059b3  mov     rcx, [rdx+18h]; this
0x1800059b7  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1800059bc  mov     rcx, [r15+38h]; this
0x1800059c0  mov     rbp, rax
0x1800059c3  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800059c8  mov     rcx, [r15+80h]; this
0x1800059cf  add     rbp, rax
0x1800059d2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800059d7  add     rbp, rax
0x1800059da  lea     rdi, [rsi+48h]
0x1800059de  cmp     qword ptr [rsi+40h], 0
0x1800059e3  jz      short loc_1800059EA
0x1800059e5  cmp     [rdi], rbp
0x1800059e8  jnb     short loc_180005A2E
0x1800059ea  mov     rdx, rbp; dwBytes
0x1800059ed  mov     ecx, 8; dwFlags
0x1800059f2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800059f7  mov     r14, rax
0x1800059fa  test    rax, rax
0x1800059fd  jz      short loc_180005A2A
0x1800059ff  mov     rbx, [rsi+40h]
0x180005a03  call    cs:__imp_GetProcessHeap
0x180005a0a  nop     dword ptr [rax+rax+00h]
0x180005a0f  mov     r8, rbx; lpMem
0x180005a12  xor     edx, edx; dwFlags
0x180005a14  mov     rcx, rax; hHeap
0x180005a17  call    cs:__imp_HeapFree
0x180005a1e  nop     dword ptr [rax+rax+00h]
0x180005a23  mov     [rsi+40h], r14
0x180005a27  mov     [rdi], rbp
0x180005a2a  lea     r14, [rsi+38h]
0x180005a2e  mov     rcx, [rsi+40h]; Destination
0x180005a32  test    rcx, rcx
0x180005a35  jz      short loc_180005A85
0x180005a37  mov     rbx, [rdi]
0x180005a3a  lea     r9, [rsi+10h]
0x180005a3e  mov     r8, [r15+38h]
0x180005a42  add     rbx, rcx
0x180005a45  mov     rdx, rbx
0x180005a48  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005a4d  mov     r8, [r15+80h]
0x180005a54  lea     r9, [rsi+20h]
0x180005a58  mov     rdx, rbx
0x180005a5b  mov     rcx, rax; Destination
0x180005a5e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005a63  mov     r8, [r15+18h]
0x180005a67  mov     r9, r14
0x180005a6a  mov     rdx, rbx
0x180005a6d  mov     rcx, rax; Destination
0x180005a70  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180005a75  sub     rbx, rax
0x180005a78  xor     edx, edx; Val
0x180005a7a  mov     r8, rbx; Size
0x180005a7d  mov     rcx, rax; void *
0x180005a80  call    memset_0
0x180005a85  add     rsp, 28h
0x180005a89  pop     r15
0x180005a8b  pop     r14
0x180005a8d  pop     r13
0x180005a8f  pop     r12
0x180005a91  pop     rdi
0x180005a92  pop     rsi
0x180005a93  pop     rbp
0x180005a94  pop     rbx
0x180005a95  retn
```
