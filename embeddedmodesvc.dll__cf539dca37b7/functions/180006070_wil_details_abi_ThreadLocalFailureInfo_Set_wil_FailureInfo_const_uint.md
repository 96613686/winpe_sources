# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006070`
- end: `0x1800061a6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006408`

## callees

- `0x1800035a0`
- `0x1800040e4`
- `0x18000415c`
- `0x180005ba8`
- `0x180005f48`
- `0x180005f68`
- `0x180006070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000611f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000611f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000612d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000612d`

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
0x180006070  push    rbx
0x180006072  push    rbp
0x180006073  push    rsi
0x180006074  push    rdi
0x180006075  push    r12
0x180006077  push    r13
0x180006079  push    r14
0x18000607b  push    r15
0x18000607d  sub     rsp, 28h
0x180006081  mov     [rcx+4], r8d
0x180006085  lea     r14, [rcx+38h]
0x180006089  mov     eax, [rdx+8]
0x18000608c  mov     rsi, rcx
0x18000608f  mov     [rcx+8], eax
0x180006092  mov     r15, rdx
0x180006095  mov     qword ptr [rcx+10h], 0
0x18000609d  movzx   eax, word ptr [rdx+40h]
0x1800060a1  mov     [rcx+18h], ax
0x1800060a5  mov     al, [rdx]
0x1800060a7  mov     [rcx+1Ah], al
0x1800060aa  mov     qword ptr [rcx+20h], 0
0x1800060b2  mov     rax, [rdx+88h]
0x1800060b9  mov     [rcx+28h], rax
0x1800060bd  mov     rax, [rdx+90h]
0x1800060c4  mov     [rcx+30h], rax
0x1800060c8  mov     qword ptr [r14], 0
0x1800060cf  mov     rcx, [rdx+18h]; this
0x1800060d3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800060d8  mov     rcx, [r15+38h]; this
0x1800060dc  mov     rbp, rax
0x1800060df  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800060e4  mov     rcx, [r15+80h]; this
0x1800060eb  add     rbp, rax
0x1800060ee  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800060f3  add     rbp, rax
0x1800060f6  lea     rdi, [rsi+48h]
0x1800060fa  cmp     qword ptr [rsi+40h], 0
0x1800060ff  jz      short loc_180006106
0x180006101  cmp     [rdi], rbp
0x180006104  jnb     short loc_18000613E
0x180006106  mov     rdx, rbp; dwBytes
0x180006109  mov     ecx, 8; dwFlags
0x18000610e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006113  mov     r14, rax
0x180006116  test    rax, rax
0x180006119  jz      short loc_18000613A
0x18000611b  mov     rbx, [rsi+40h]
0x18000611f  call    cs:__imp_GetProcessHeap
0x180006125  mov     r8, rbx; lpMem
0x180006128  xor     edx, edx; dwFlags
0x18000612a  mov     rcx, rax; hHeap
0x18000612d  call    cs:__imp_HeapFree
0x180006133  mov     [rsi+40h], r14
0x180006137  mov     [rdi], rbp
0x18000613a  lea     r14, [rsi+38h]
0x18000613e  mov     rcx, [rsi+40h]; Destination
0x180006142  test    rcx, rcx
0x180006145  jz      short loc_180006195
0x180006147  mov     rbx, [rdi]
0x18000614a  lea     r9, [rsi+10h]
0x18000614e  mov     r8, [r15+38h]
0x180006152  add     rbx, rcx
0x180006155  mov     rdx, rbx
0x180006158  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000615d  mov     r8, [r15+80h]
0x180006164  lea     r9, [rsi+20h]
0x180006168  mov     rdx, rbx
0x18000616b  mov     rcx, rax; Destination
0x18000616e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006173  mov     r8, [r15+18h]
0x180006177  mov     r9, r14
0x18000617a  mov     rdx, rbx
0x18000617d  mov     rcx, rax; Destination
0x180006180  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006185  sub     rbx, rax
0x180006188  xor     edx, edx; Val
0x18000618a  mov     r8, rbx; Size
0x18000618d  mov     rcx, rax; void *
0x180006190  call    memset_0
0x180006195  add     rsp, 28h
0x180006199  pop     r15
0x18000619b  pop     r14
0x18000619d  pop     r13
0x18000619f  pop     r12
0x1800061a1  pop     rdi
0x1800061a2  pop     rsi
0x1800061a3  pop     rbp
0x1800061a4  pop     rbx
0x1800061a5  retn
```
