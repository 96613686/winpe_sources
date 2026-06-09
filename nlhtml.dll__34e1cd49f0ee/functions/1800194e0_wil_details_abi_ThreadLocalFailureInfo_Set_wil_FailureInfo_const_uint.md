# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800194e0`
- end: `0x180019616`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019968`

## callees

- `0x180014ff0`
- `0x1800159d8`
- `0x180015a50`
- `0x1800183ec`
- `0x180019378`
- `0x180019398`
- `0x1800194e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001959d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001959d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001958f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001958f`

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
0x1800194e0  push    rbx
0x1800194e2  push    rbp
0x1800194e3  push    rsi
0x1800194e4  push    rdi
0x1800194e5  push    r12
0x1800194e7  push    r13
0x1800194e9  push    r14
0x1800194eb  push    r15
0x1800194ed  sub     rsp, 28h
0x1800194f1  mov     [rcx+4], r8d
0x1800194f5  lea     r14, [rcx+38h]
0x1800194f9  mov     eax, [rdx+8]
0x1800194fc  mov     rsi, rcx
0x1800194ff  mov     [rcx+8], eax
0x180019502  mov     r15, rdx
0x180019505  mov     qword ptr [rcx+10h], 0
0x18001950d  movzx   eax, word ptr [rdx+40h]
0x180019511  mov     [rcx+18h], ax
0x180019515  mov     al, [rdx]
0x180019517  mov     [rcx+1Ah], al
0x18001951a  mov     qword ptr [rcx+20h], 0
0x180019522  mov     rax, [rdx+88h]
0x180019529  mov     [rcx+28h], rax
0x18001952d  mov     rax, [rdx+90h]
0x180019534  mov     [rcx+30h], rax
0x180019538  mov     qword ptr [r14], 0
0x18001953f  mov     rcx, [rdx+18h]; this
0x180019543  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180019548  mov     rcx, [r15+38h]; this
0x18001954c  mov     rbp, rax
0x18001954f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180019554  mov     rcx, [r15+80h]; this
0x18001955b  add     rbp, rax
0x18001955e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180019563  add     rbp, rax
0x180019566  lea     rdi, [rsi+48h]
0x18001956a  cmp     qword ptr [rsi+40h], 0
0x18001956f  jz      short loc_180019576
0x180019571  cmp     [rdi], rbp
0x180019574  jnb     short loc_1800195AE
0x180019576  mov     rdx, rbp; dwBytes
0x180019579  mov     ecx, 8; dwFlags
0x18001957e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019583  mov     r14, rax
0x180019586  test    rax, rax
0x180019589  jz      short loc_1800195AA
0x18001958b  mov     rbx, [rsi+40h]
0x18001958f  call    cs:__imp_GetProcessHeap
0x180019595  mov     r8, rbx; lpMem
0x180019598  xor     edx, edx; dwFlags
0x18001959a  mov     rcx, rax; hHeap
0x18001959d  call    cs:__imp_HeapFree
0x1800195a3  mov     [rsi+40h], r14
0x1800195a7  mov     [rdi], rbp
0x1800195aa  lea     r14, [rsi+38h]
0x1800195ae  mov     rcx, [rsi+40h]; Destination
0x1800195b2  test    rcx, rcx
0x1800195b5  jz      short loc_180019605
0x1800195b7  mov     rbx, [rdi]
0x1800195ba  lea     r9, [rsi+10h]
0x1800195be  mov     r8, [r15+38h]
0x1800195c2  add     rbx, rcx
0x1800195c5  mov     rdx, rbx
0x1800195c8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800195cd  mov     r8, [r15+80h]
0x1800195d4  lea     r9, [rsi+20h]
0x1800195d8  mov     rdx, rbx
0x1800195db  mov     rcx, rax; Destination
0x1800195de  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800195e3  mov     r8, [r15+18h]
0x1800195e7  mov     r9, r14
0x1800195ea  mov     rdx, rbx
0x1800195ed  mov     rcx, rax; Destination
0x1800195f0  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x1800195f5  sub     rbx, rax
0x1800195f8  xor     edx, edx; Val
0x1800195fa  mov     r8, rbx; Size
0x1800195fd  mov     rcx, rax; void *
0x180019600  call    memset_0
0x180019605  add     rsp, 28h
0x180019609  pop     r15
0x18001960b  pop     r14
0x18001960d  pop     r13
0x18001960f  pop     r12
0x180019611  pop     rdi
0x180019612  pop     rsi
0x180019613  pop     rbp
0x180019614  pop     rbx
0x180019615  retn
```
