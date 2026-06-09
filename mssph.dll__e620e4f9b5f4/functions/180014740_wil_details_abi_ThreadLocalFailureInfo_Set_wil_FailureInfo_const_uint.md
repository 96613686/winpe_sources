# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180014740`
- end: `0x180014876`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014ad8`

## callees

- `0x18000aaa0`
- `0x180010b2c`
- `0x180011bbc`
- `0x180011c34`
- `0x1800145cc`
- `0x1800145ec`
- `0x180014740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147fd`

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
0x180014740  push    rbx
0x180014742  push    rbp
0x180014743  push    rsi
0x180014744  push    rdi
0x180014745  push    r12
0x180014747  push    r13
0x180014749  push    r14
0x18001474b  push    r15
0x18001474d  sub     rsp, 28h
0x180014751  mov     [rcx+4], r8d
0x180014755  lea     r14, [rcx+38h]
0x180014759  mov     eax, [rdx+8]
0x18001475c  mov     rsi, rcx
0x18001475f  mov     [rcx+8], eax
0x180014762  mov     r15, rdx
0x180014765  mov     qword ptr [rcx+10h], 0
0x18001476d  movzx   eax, word ptr [rdx+40h]
0x180014771  mov     [rcx+18h], ax
0x180014775  mov     al, [rdx]
0x180014777  mov     [rcx+1Ah], al
0x18001477a  mov     qword ptr [rcx+20h], 0
0x180014782  mov     rax, [rdx+88h]
0x180014789  mov     [rcx+28h], rax
0x18001478d  mov     rax, [rdx+90h]
0x180014794  mov     [rcx+30h], rax
0x180014798  mov     qword ptr [r14], 0
0x18001479f  mov     rcx, [rdx+18h]; this
0x1800147a3  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1800147a8  mov     rcx, [r15+38h]; this
0x1800147ac  mov     rbp, rax
0x1800147af  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800147b4  mov     rcx, [r15+80h]; this
0x1800147bb  add     rbp, rax
0x1800147be  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800147c3  add     rbp, rax
0x1800147c6  lea     rdi, [rsi+48h]
0x1800147ca  cmp     qword ptr [rsi+40h], 0
0x1800147cf  jz      short loc_1800147D6
0x1800147d1  cmp     [rdi], rbp
0x1800147d4  jnb     short loc_18001480E
0x1800147d6  mov     rdx, rbp; dwBytes
0x1800147d9  mov     ecx, 8; dwFlags
0x1800147de  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800147e3  mov     r14, rax
0x1800147e6  test    rax, rax
0x1800147e9  jz      short loc_18001480A
0x1800147eb  mov     rbx, [rsi+40h]
0x1800147ef  call    cs:__imp_GetProcessHeap
0x1800147f5  mov     r8, rbx; lpMem
0x1800147f8  xor     edx, edx; dwFlags
0x1800147fa  mov     rcx, rax; hHeap
0x1800147fd  call    cs:__imp_HeapFree
0x180014803  mov     [rsi+40h], r14
0x180014807  mov     [rdi], rbp
0x18001480a  lea     r14, [rsi+38h]
0x18001480e  mov     rcx, [rsi+40h]; Destination
0x180014812  test    rcx, rcx
0x180014815  jz      short loc_180014865
0x180014817  mov     rbx, [rdi]
0x18001481a  lea     r9, [rsi+10h]
0x18001481e  mov     r8, [r15+38h]
0x180014822  add     rbx, rcx
0x180014825  mov     rdx, rbx
0x180014828  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001482d  mov     r8, [r15+80h]
0x180014834  lea     r9, [rsi+20h]
0x180014838  mov     rdx, rbx
0x18001483b  mov     rcx, rax; Destination
0x18001483e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014843  mov     r8, [r15+18h]
0x180014847  mov     r9, r14
0x18001484a  mov     rdx, rbx
0x18001484d  mov     rcx, rax; Destination
0x180014850  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180014855  sub     rbx, rax
0x180014858  xor     edx, edx; Val
0x18001485a  mov     r8, rbx; Size
0x18001485d  mov     rcx, rax; void *
0x180014860  call    memset_0
0x180014865  add     rsp, 28h
0x180014869  pop     r15
0x18001486b  pop     r14
0x18001486d  pop     r13
0x18001486f  pop     r12
0x180014871  pop     rdi
0x180014872  pop     rsi
0x180014873  pop     rbp
0x180014874  pop     rbx
0x180014875  retn
```
