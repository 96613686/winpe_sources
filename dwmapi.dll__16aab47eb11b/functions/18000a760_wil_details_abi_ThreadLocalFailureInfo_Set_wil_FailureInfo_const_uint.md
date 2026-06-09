# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a760`
- end: `0x18000a896`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006530`

## callees

- `0x18000a760`
- `0x18000a89c`
- `0x18000c5c4`
- `0x18000c720`
- `0x18000ddc4`
- `0x18000e310`
- `0x18000e388`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a80f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a80f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a81d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a81d`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
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
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18000a760  push    rbx
0x18000a762  push    rbp
0x18000a763  push    rsi
0x18000a764  push    rdi
0x18000a765  push    r12
0x18000a767  push    r13
0x18000a769  push    r14
0x18000a76b  push    r15
0x18000a76d  sub     rsp, 28h
0x18000a771  mov     [rcx+4], r8d
0x18000a775  lea     r14, [rcx+38h]
0x18000a779  mov     eax, [rdx+8]
0x18000a77c  mov     rsi, rcx
0x18000a77f  mov     [rcx+8], eax
0x18000a782  mov     r15, rdx
0x18000a785  mov     qword ptr [rcx+10h], 0
0x18000a78d  movzx   eax, word ptr [rdx+40h]
0x18000a791  mov     [rcx+18h], ax
0x18000a795  mov     al, [rdx]
0x18000a797  mov     [rcx+1Ah], al
0x18000a79a  mov     qword ptr [rcx+20h], 0
0x18000a7a2  mov     rax, [rdx+88h]
0x18000a7a9  mov     [rcx+28h], rax
0x18000a7ad  mov     rax, [rdx+90h]
0x18000a7b4  mov     [rcx+30h], rax
0x18000a7b8  mov     qword ptr [r14], 0
0x18000a7bf  mov     rcx, [rdx+18h]; this
0x18000a7c3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000a7c8  mov     rcx, [r15+38h]; this
0x18000a7cc  mov     rbp, rax
0x18000a7cf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000a7d4  mov     rcx, [r15+80h]; this
0x18000a7db  add     rbp, rax
0x18000a7de  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000a7e3  add     rbp, rax
0x18000a7e6  lea     rdi, [rsi+48h]
0x18000a7ea  cmp     qword ptr [rsi+40h], 0
0x18000a7ef  jz      short loc_18000A7F6
0x18000a7f1  cmp     [rdi], rbp
0x18000a7f4  jnb     short loc_18000A82E
0x18000a7f6  mov     rdx, rbp; dwBytes
0x18000a7f9  mov     ecx, 8; dwFlags
0x18000a7fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a803  mov     r14, rax
0x18000a806  test    rax, rax
0x18000a809  jz      short loc_18000A82A
0x18000a80b  mov     rbx, [rsi+40h]
0x18000a80f  call    cs:__imp_GetProcessHeap
0x18000a815  mov     r8, rbx; lpMem
0x18000a818  xor     edx, edx; dwFlags
0x18000a81a  mov     rcx, rax; hHeap
0x18000a81d  call    cs:__imp_HeapFree
0x18000a823  mov     [rsi+40h], r14
0x18000a827  mov     [rdi], rbp
0x18000a82a  lea     r14, [rsi+38h]
0x18000a82e  mov     rcx, [rsi+40h]; Destination
0x18000a832  test    rcx, rcx
0x18000a835  jz      short loc_18000A885
0x18000a837  mov     rbx, [rdi]
0x18000a83a  lea     r9, [rsi+10h]
0x18000a83e  mov     r8, [r15+38h]
0x18000a842  add     rbx, rcx
0x18000a845  mov     rdx, rbx
0x18000a848  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a84d  mov     r8, [r15+80h]
0x18000a854  lea     r9, [rsi+20h]
0x18000a858  mov     rdx, rbx
0x18000a85b  mov     rcx, rax; Destination
0x18000a85e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a863  mov     r8, [r15+18h]
0x18000a867  mov     r9, r14
0x18000a86a  mov     rdx, rbx
0x18000a86d  mov     rcx, rax; Destination
0x18000a870  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000a875  sub     rbx, rax
0x18000a878  xor     edx, edx; Val
0x18000a87a  mov     r8, rbx; Size
0x18000a87d  mov     rcx, rax; void *
0x18000a880  call    memset_0
0x18000a885  add     rsp, 28h
0x18000a889  pop     r15
0x18000a88b  pop     r14
0x18000a88d  pop     r13
0x18000a88f  pop     r12
0x18000a891  pop     rdi
0x18000a892  pop     rsi
0x18000a893  pop     rbp
0x18000a894  pop     rbx
0x18000a895  retn
```
