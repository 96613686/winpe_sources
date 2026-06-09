# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005a9c`
- end: `0x180005bd2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005e34`

## callees

- `0x1800023c0`
- `0x180003348`
- `0x1800033c0`
- `0x1800055a8`
- `0x180005978`
- `0x180005998`
- `0x180005a9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b4b`

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
0x180005a9c  push    rbx
0x180005a9e  push    rbp
0x180005a9f  push    rsi
0x180005aa0  push    rdi
0x180005aa1  push    r12
0x180005aa3  push    r13
0x180005aa5  push    r14
0x180005aa7  push    r15
0x180005aa9  sub     rsp, 28h
0x180005aad  mov     [rcx+4], r8d
0x180005ab1  lea     r14, [rcx+38h]
0x180005ab5  mov     eax, [rdx+8]
0x180005ab8  mov     rsi, rcx
0x180005abb  mov     [rcx+8], eax
0x180005abe  mov     r15, rdx
0x180005ac1  mov     qword ptr [rcx+10h], 0
0x180005ac9  movzx   eax, word ptr [rdx+40h]
0x180005acd  mov     [rcx+18h], ax
0x180005ad1  mov     al, [rdx]
0x180005ad3  mov     [rcx+1Ah], al
0x180005ad6  mov     qword ptr [rcx+20h], 0
0x180005ade  mov     rax, [rdx+88h]
0x180005ae5  mov     [rcx+28h], rax
0x180005ae9  mov     rax, [rdx+90h]
0x180005af0  mov     [rcx+30h], rax
0x180005af4  mov     qword ptr [r14], 0
0x180005afb  mov     rcx, [rdx+18h]; this
0x180005aff  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005b04  mov     rcx, [r15+38h]; this
0x180005b08  mov     rbp, rax
0x180005b0b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005b10  mov     rcx, [r15+80h]; this
0x180005b17  add     rbp, rax
0x180005b1a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005b1f  add     rbp, rax
0x180005b22  lea     rdi, [rsi+48h]
0x180005b26  cmp     qword ptr [rsi+40h], 0
0x180005b2b  jz      short loc_180005B32
0x180005b2d  cmp     [rdi], rbp
0x180005b30  jnb     short loc_180005B6A
0x180005b32  mov     rdx, rbp; dwBytes
0x180005b35  mov     ecx, 8; dwFlags
0x180005b3a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005b3f  mov     r14, rax
0x180005b42  test    rax, rax
0x180005b45  jz      short loc_180005B66
0x180005b47  mov     rbx, [rsi+40h]
0x180005b4b  call    cs:__imp_GetProcessHeap
0x180005b51  mov     r8, rbx; lpMem
0x180005b54  xor     edx, edx; dwFlags
0x180005b56  mov     rcx, rax; hHeap
0x180005b59  call    cs:__imp_HeapFree
0x180005b5f  mov     [rsi+40h], r14
0x180005b63  mov     [rdi], rbp
0x180005b66  lea     r14, [rsi+38h]
0x180005b6a  mov     rcx, [rsi+40h]; Destination
0x180005b6e  test    rcx, rcx
0x180005b71  jz      short loc_180005BC1
0x180005b73  mov     rbx, [rdi]
0x180005b76  lea     r9, [rsi+10h]
0x180005b7a  mov     r8, [r15+38h]
0x180005b7e  add     rbx, rcx
0x180005b81  mov     rdx, rbx
0x180005b84  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005b89  mov     r8, [r15+80h]
0x180005b90  lea     r9, [rsi+20h]
0x180005b94  mov     rdx, rbx
0x180005b97  mov     rcx, rax; Destination
0x180005b9a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005b9f  mov     r8, [r15+18h]
0x180005ba3  mov     r9, r14
0x180005ba6  mov     rdx, rbx
0x180005ba9  mov     rcx, rax; Destination
0x180005bac  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180005bb1  sub     rbx, rax
0x180005bb4  xor     edx, edx; Val
0x180005bb6  mov     r8, rbx; Size
0x180005bb9  mov     rcx, rax; void *
0x180005bbc  call    memset_0
0x180005bc1  add     rsp, 28h
0x180005bc5  pop     r15
0x180005bc7  pop     r14
0x180005bc9  pop     r13
0x180005bcb  pop     r12
0x180005bcd  pop     rdi
0x180005bce  pop     rsi
0x180005bcf  pop     rbp
0x180005bd0  pop     rbx
0x180005bd1  retn
```
