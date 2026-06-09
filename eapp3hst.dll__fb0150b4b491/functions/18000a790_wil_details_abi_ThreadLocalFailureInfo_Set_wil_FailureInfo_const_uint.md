# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a790`
- end: `0x18000a8c6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a9b8`

## callees

- `0x18000213c`
- `0x1800026dc`
- `0x180002754`
- `0x1800031a4`
- `0x1800031c4`
- `0x1800094f4`
- `0x18000a790`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a83f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a83f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a84d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a84d`

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
0x18000a790  push    rbx
0x18000a792  push    rbp
0x18000a793  push    rsi
0x18000a794  push    rdi
0x18000a795  push    r12
0x18000a797  push    r13
0x18000a799  push    r14
0x18000a79b  push    r15
0x18000a79d  sub     rsp, 28h
0x18000a7a1  mov     [rcx+4], r8d
0x18000a7a5  lea     r14, [rcx+38h]
0x18000a7a9  mov     eax, [rdx+8]
0x18000a7ac  mov     rsi, rcx
0x18000a7af  mov     [rcx+8], eax
0x18000a7b2  mov     r15, rdx
0x18000a7b5  mov     qword ptr [rcx+10h], 0
0x18000a7bd  movzx   eax, word ptr [rdx+40h]
0x18000a7c1  mov     [rcx+18h], ax
0x18000a7c5  mov     al, [rdx]
0x18000a7c7  mov     [rcx+1Ah], al
0x18000a7ca  mov     qword ptr [rcx+20h], 0
0x18000a7d2  mov     rax, [rdx+88h]
0x18000a7d9  mov     [rcx+28h], rax
0x18000a7dd  mov     rax, [rdx+90h]
0x18000a7e4  mov     [rcx+30h], rax
0x18000a7e8  mov     qword ptr [r14], 0
0x18000a7ef  mov     rcx, [rdx+18h]; this
0x18000a7f3  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18000a7f8  mov     rcx, [r15+38h]; this
0x18000a7fc  mov     rbp, rax
0x18000a7ff  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000a804  mov     rcx, [r15+80h]; this
0x18000a80b  add     rbp, rax
0x18000a80e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000a813  add     rbp, rax
0x18000a816  lea     rdi, [rsi+48h]
0x18000a81a  cmp     qword ptr [rsi+40h], 0
0x18000a81f  jz      short loc_18000A826
0x18000a821  cmp     [rdi], rbp
0x18000a824  jnb     short loc_18000A85E
0x18000a826  mov     rdx, rbp; dwBytes
0x18000a829  mov     ecx, 8; dwFlags
0x18000a82e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a833  mov     r14, rax
0x18000a836  test    rax, rax
0x18000a839  jz      short loc_18000A85A
0x18000a83b  mov     rbx, [rsi+40h]
0x18000a83f  call    cs:__imp_GetProcessHeap
0x18000a845  mov     r8, rbx; lpMem
0x18000a848  xor     edx, edx; dwFlags
0x18000a84a  mov     rcx, rax; hHeap
0x18000a84d  call    cs:__imp_HeapFree
0x18000a853  mov     [rsi+40h], r14
0x18000a857  mov     [rdi], rbp
0x18000a85a  lea     r14, [rsi+38h]
0x18000a85e  mov     rcx, [rsi+40h]; Destination
0x18000a862  test    rcx, rcx
0x18000a865  jz      short loc_18000A8B5
0x18000a867  mov     rbx, [rdi]
0x18000a86a  lea     r9, [rsi+10h]
0x18000a86e  mov     r8, [r15+38h]
0x18000a872  add     rbx, rcx
0x18000a875  mov     rdx, rbx
0x18000a878  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a87d  mov     r8, [r15+80h]
0x18000a884  lea     r9, [rsi+20h]
0x18000a888  mov     rdx, rbx
0x18000a88b  mov     rcx, rax; Destination
0x18000a88e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a893  mov     r8, [r15+18h]
0x18000a897  mov     r9, r14
0x18000a89a  mov     rdx, rbx
0x18000a89d  mov     rcx, rax; Destination
0x18000a8a0  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x18000a8a5  sub     rbx, rax
0x18000a8a8  xor     edx, edx; Val
0x18000a8aa  mov     r8, rbx; Size
0x18000a8ad  mov     rcx, rax; void *
0x18000a8b0  call    memset_0
0x18000a8b5  add     rsp, 28h
0x18000a8b9  pop     r15
0x18000a8bb  pop     r14
0x18000a8bd  pop     r13
0x18000a8bf  pop     r12
0x18000a8c1  pop     rdi
0x18000a8c2  pop     rsi
0x18000a8c3  pop     rbp
0x18000a8c4  pop     rbx
0x18000a8c5  retn
```
