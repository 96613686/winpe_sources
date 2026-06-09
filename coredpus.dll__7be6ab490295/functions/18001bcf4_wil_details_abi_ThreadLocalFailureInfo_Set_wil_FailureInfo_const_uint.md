# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001bcf4`
- end: `0x18001be37`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c1fc`

## callees

- `0x180015174`
- `0x1800175e4`
- `0x18001765c`
- `0x18001adc0`
- `0x18001b8ec`
- `0x18001b910`
- `0x18001bcf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bdb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bdb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bda3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bda3`

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
0x18001bcf4  push    rbx
0x18001bcf6  push    rbp
0x18001bcf7  push    rsi
0x18001bcf8  push    rdi
0x18001bcf9  push    r12
0x18001bcfb  push    r13
0x18001bcfd  push    r14
0x18001bcff  push    r15
0x18001bd01  sub     rsp, 28h
0x18001bd05  mov     [rcx+4], r8d
0x18001bd09  lea     r14, [rcx+38h]
0x18001bd0d  mov     eax, [rdx+8]
0x18001bd10  mov     rsi, rcx
0x18001bd13  mov     [rcx+8], eax
0x18001bd16  mov     r15, rdx
0x18001bd19  mov     qword ptr [rcx+10h], 0
0x18001bd21  movzx   eax, word ptr [rdx+40h]
0x18001bd25  mov     [rcx+18h], ax
0x18001bd29  mov     al, [rdx]
0x18001bd2b  mov     [rcx+1Ah], al
0x18001bd2e  mov     qword ptr [rcx+20h], 0
0x18001bd36  mov     rax, [rdx+88h]
0x18001bd3d  mov     [rcx+28h], rax
0x18001bd41  mov     rax, [rdx+90h]
0x18001bd48  mov     [rcx+30h], rax
0x18001bd4c  mov     qword ptr [r14], 0
0x18001bd53  mov     rcx, [rdx+18h]; this
0x18001bd57  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001bd5c  mov     rcx, [r15+38h]; this
0x18001bd60  mov     rbp, rax
0x18001bd63  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001bd68  mov     rcx, [r15+80h]; this
0x18001bd6f  add     rbp, rax
0x18001bd72  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001bd77  add     rbp, rax
0x18001bd7a  lea     rdi, [rsi+48h]
0x18001bd7e  cmp     qword ptr [rsi+40h], 0
0x18001bd83  jz      short loc_18001BD8A
0x18001bd85  cmp     [rdi], rbp
0x18001bd88  jnb     short loc_18001BDCE
0x18001bd8a  mov     rdx, rbp; dwBytes
0x18001bd8d  mov     ecx, 8; dwFlags
0x18001bd92  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001bd97  mov     r14, rax
0x18001bd9a  test    rax, rax
0x18001bd9d  jz      short loc_18001BDCA
0x18001bd9f  mov     rbx, [rsi+40h]
0x18001bda3  call    cs:__imp_GetProcessHeap
0x18001bdaa  nop     dword ptr [rax+rax+00h]
0x18001bdaf  mov     r8, rbx; lpMem
0x18001bdb2  xor     edx, edx; dwFlags
0x18001bdb4  mov     rcx, rax; hHeap
0x18001bdb7  call    cs:__imp_HeapFree
0x18001bdbe  nop     dword ptr [rax+rax+00h]
0x18001bdc3  mov     [rsi+40h], r14
0x18001bdc7  mov     [rdi], rbp
0x18001bdca  lea     r14, [rsi+38h]
0x18001bdce  mov     rcx, [rsi+40h]; Destination
0x18001bdd2  test    rcx, rcx
0x18001bdd5  jz      short loc_18001BE25
0x18001bdd7  mov     rbx, [rdi]
0x18001bdda  lea     r9, [rsi+10h]
0x18001bdde  mov     r8, [r15+38h]
0x18001bde2  add     rbx, rcx
0x18001bde5  mov     rdx, rbx
0x18001bde8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001bded  mov     r8, [r15+80h]
0x18001bdf4  lea     r9, [rsi+20h]
0x18001bdf8  mov     rdx, rbx
0x18001bdfb  mov     rcx, rax; Destination
0x18001bdfe  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001be03  mov     r8, [r15+18h]
0x18001be07  mov     r9, r14
0x18001be0a  mov     rdx, rbx
0x18001be0d  mov     rcx, rax; Destination
0x18001be10  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18001be15  sub     rbx, rax
0x18001be18  xor     edx, edx; Val
0x18001be1a  mov     r8, rbx; Size
0x18001be1d  mov     rcx, rax; void *
0x18001be20  call    memset_0
0x18001be25  add     rsp, 28h
0x18001be29  pop     r15
0x18001be2b  pop     r14
0x18001be2d  pop     r13
0x18001be2f  pop     r12
0x18001be31  pop     rdi
0x18001be32  pop     rsi
0x18001be33  pop     rbp
0x18001be34  pop     rbx
0x18001be35  retn
```
