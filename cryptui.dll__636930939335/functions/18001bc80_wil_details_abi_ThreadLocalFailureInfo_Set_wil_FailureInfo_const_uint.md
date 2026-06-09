# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001bc80`
- end: `0x18001bdb6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c104`

## callees

- `0x1800161bc`
- `0x180016234`
- `0x18001aeb4`
- `0x18001baf0`
- `0x18001bb10`
- `0x18001bc80`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd2f`

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
0x18001bc80  push    rbx
0x18001bc82  push    rbp
0x18001bc83  push    rsi
0x18001bc84  push    rdi
0x18001bc85  push    r12
0x18001bc87  push    r13
0x18001bc89  push    r14
0x18001bc8b  push    r15
0x18001bc8d  sub     rsp, 28h
0x18001bc91  mov     [rcx+4], r8d
0x18001bc95  lea     r14, [rcx+38h]
0x18001bc99  mov     eax, [rdx+8]
0x18001bc9c  mov     rsi, rcx
0x18001bc9f  mov     [rcx+8], eax
0x18001bca2  mov     r15, rdx
0x18001bca5  mov     qword ptr [rcx+10h], 0
0x18001bcad  movzx   eax, word ptr [rdx+40h]
0x18001bcb1  mov     [rcx+18h], ax
0x18001bcb5  mov     al, [rdx]
0x18001bcb7  mov     [rcx+1Ah], al
0x18001bcba  mov     qword ptr [rcx+20h], 0
0x18001bcc2  mov     rax, [rdx+88h]
0x18001bcc9  mov     [rcx+28h], rax
0x18001bccd  mov     rax, [rdx+90h]
0x18001bcd4  mov     [rcx+30h], rax
0x18001bcd8  mov     qword ptr [r14], 0
0x18001bcdf  mov     rcx, [rdx+18h]; this
0x18001bce3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001bce8  mov     rcx, [r15+38h]; this
0x18001bcec  mov     rbp, rax
0x18001bcef  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001bcf4  mov     rcx, [r15+80h]; this
0x18001bcfb  add     rbp, rax
0x18001bcfe  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001bd03  add     rbp, rax
0x18001bd06  lea     rdi, [rsi+48h]
0x18001bd0a  cmp     qword ptr [rsi+40h], 0
0x18001bd0f  jz      short loc_18001BD16
0x18001bd11  cmp     [rdi], rbp
0x18001bd14  jnb     short loc_18001BD4E
0x18001bd16  mov     rdx, rbp; dwBytes
0x18001bd19  mov     ecx, 8; dwFlags
0x18001bd1e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001bd23  mov     r14, rax
0x18001bd26  test    rax, rax
0x18001bd29  jz      short loc_18001BD4A
0x18001bd2b  mov     rbx, [rsi+40h]
0x18001bd2f  call    cs:__imp_GetProcessHeap
0x18001bd35  mov     r8, rbx; lpMem
0x18001bd38  xor     edx, edx; dwFlags
0x18001bd3a  mov     rcx, rax; hHeap
0x18001bd3d  call    cs:__imp_HeapFree
0x18001bd43  mov     [rsi+40h], r14
0x18001bd47  mov     [rdi], rbp
0x18001bd4a  lea     r14, [rsi+38h]
0x18001bd4e  mov     rcx, [rsi+40h]; Destination
0x18001bd52  test    rcx, rcx
0x18001bd55  jz      short loc_18001BDA5
0x18001bd57  mov     rbx, [rdi]
0x18001bd5a  lea     r9, [rsi+10h]
0x18001bd5e  mov     r8, [r15+38h]
0x18001bd62  add     rbx, rcx
0x18001bd65  mov     rdx, rbx
0x18001bd68  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001bd6d  mov     r8, [r15+80h]
0x18001bd74  lea     r9, [rsi+20h]
0x18001bd78  mov     rdx, rbx
0x18001bd7b  mov     rcx, rax; Destination
0x18001bd7e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001bd83  mov     r8, [r15+18h]
0x18001bd87  mov     r9, r14
0x18001bd8a  mov     rdx, rbx
0x18001bd8d  mov     rcx, rax; Destination
0x18001bd90  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18001bd95  sub     rbx, rax
0x18001bd98  xor     edx, edx; Val
0x18001bd9a  mov     r8, rbx; Size
0x18001bd9d  mov     rcx, rax; void *
0x18001bda0  call    memset_0
0x18001bda5  add     rsp, 28h
0x18001bda9  pop     r15
0x18001bdab  pop     r14
0x18001bdad  pop     r13
0x18001bdaf  pop     r12
0x18001bdb1  pop     rdi
0x18001bdb2  pop     rsi
0x18001bdb3  pop     rbp
0x18001bdb4  pop     rbx
0x18001bdb5  retn
```
