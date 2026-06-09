# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000cd54`
- end: `0x18000ce8a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d0ec`

## callees

- `0x180006e9c`
- `0x180007fbc`
- `0x180008034`
- `0x18000c2d8`
- `0x18000cbb8`
- `0x18000cbd8`
- `0x18000cd54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce11`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
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
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
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
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18000cd54  push    rbx
0x18000cd56  push    rbp
0x18000cd57  push    rsi
0x18000cd58  push    rdi
0x18000cd59  push    r12
0x18000cd5b  push    r13
0x18000cd5d  push    r14
0x18000cd5f  push    r15
0x18000cd61  sub     rsp, 28h
0x18000cd65  mov     [rcx+4], r8d
0x18000cd69  lea     r14, [rcx+38h]
0x18000cd6d  mov     eax, [rdx+8]
0x18000cd70  mov     rsi, rcx
0x18000cd73  mov     [rcx+8], eax
0x18000cd76  mov     r15, rdx
0x18000cd79  mov     qword ptr [rcx+10h], 0
0x18000cd81  movzx   eax, word ptr [rdx+40h]
0x18000cd85  mov     [rcx+18h], ax
0x18000cd89  mov     al, [rdx]
0x18000cd8b  mov     [rcx+1Ah], al
0x18000cd8e  mov     qword ptr [rcx+20h], 0
0x18000cd96  mov     rax, [rdx+88h]
0x18000cd9d  mov     [rcx+28h], rax
0x18000cda1  mov     rax, [rdx+90h]
0x18000cda8  mov     [rcx+30h], rax
0x18000cdac  mov     qword ptr [r14], 0
0x18000cdb3  mov     rcx, [rdx+18h]; this
0x18000cdb7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000cdbc  mov     rcx, [r15+38h]; this
0x18000cdc0  mov     rbp, rax
0x18000cdc3  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000cdc8  mov     rcx, [r15+80h]; this
0x18000cdcf  add     rbp, rax
0x18000cdd2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000cdd7  add     rbp, rax
0x18000cdda  lea     rdi, [rsi+48h]
0x18000cdde  cmp     qword ptr [rsi+40h], 0
0x18000cde3  jz      short loc_18000CDEA
0x18000cde5  cmp     [rdi], rbp
0x18000cde8  jnb     short loc_18000CE22
0x18000cdea  mov     rdx, rbp; dwBytes
0x18000cded  mov     ecx, 8; dwFlags
0x18000cdf2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000cdf7  mov     r14, rax
0x18000cdfa  test    rax, rax
0x18000cdfd  jz      short loc_18000CE1E
0x18000cdff  mov     rbx, [rsi+40h]
0x18000ce03  call    cs:__imp_GetProcessHeap
0x18000ce09  mov     r8, rbx; lpMem
0x18000ce0c  xor     edx, edx; dwFlags
0x18000ce0e  mov     rcx, rax; hHeap
0x18000ce11  call    cs:__imp_HeapFree
0x18000ce17  mov     [rsi+40h], r14
0x18000ce1b  mov     [rdi], rbp
0x18000ce1e  lea     r14, [rsi+38h]
0x18000ce22  mov     rcx, [rsi+40h]; Destination
0x18000ce26  test    rcx, rcx
0x18000ce29  jz      short loc_18000CE79
0x18000ce2b  mov     rbx, [rdi]
0x18000ce2e  lea     r9, [rsi+10h]
0x18000ce32  mov     r8, [r15+38h]
0x18000ce36  add     rbx, rcx
0x18000ce39  mov     rdx, rbx
0x18000ce3c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ce41  mov     r8, [r15+80h]
0x18000ce48  lea     r9, [rsi+20h]
0x18000ce4c  mov     rdx, rbx
0x18000ce4f  mov     rcx, rax; Destination
0x18000ce52  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ce57  mov     r8, [r15+18h]
0x18000ce5b  mov     r9, r14
0x18000ce5e  mov     rdx, rbx
0x18000ce61  mov     rcx, rax; Destination
0x18000ce64  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000ce69  sub     rbx, rax
0x18000ce6c  xor     edx, edx; Val
0x18000ce6e  mov     r8, rbx; Size
0x18000ce71  mov     rcx, rax; void *
0x18000ce74  call    memset_0
0x18000ce79  add     rsp, 28h
0x18000ce7d  pop     r15
0x18000ce7f  pop     r14
0x18000ce81  pop     r13
0x18000ce83  pop     r12
0x18000ce85  pop     rdi
0x18000ce86  pop     rsi
0x18000ce87  pop     rbp
0x18000ce88  pop     rbx
0x18000ce89  retn
```
