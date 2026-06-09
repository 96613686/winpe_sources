# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800114c0`
- end: `0x1800115f6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002220`

## callees

- `0x18000bed0`
- `0x18000d548`
- `0x18001039c`
- `0x180010a14`
- `0x180010a8c`
- `0x180011438`
- `0x1800114c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001157d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001157d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001156f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001156f`

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
0x1800114c0  push    rbx
0x1800114c2  push    rbp
0x1800114c3  push    rsi
0x1800114c4  push    rdi
0x1800114c5  push    r12
0x1800114c7  push    r13
0x1800114c9  push    r14
0x1800114cb  push    r15
0x1800114cd  sub     rsp, 28h
0x1800114d1  mov     [rcx+4], r8d
0x1800114d5  lea     r14, [rcx+38h]
0x1800114d9  mov     eax, [rdx+8]
0x1800114dc  mov     rsi, rcx
0x1800114df  mov     [rcx+8], eax
0x1800114e2  mov     r15, rdx
0x1800114e5  mov     qword ptr [rcx+10h], 0
0x1800114ed  movzx   eax, word ptr [rdx+40h]
0x1800114f1  mov     [rcx+18h], ax
0x1800114f5  mov     al, [rdx]
0x1800114f7  mov     [rcx+1Ah], al
0x1800114fa  mov     qword ptr [rcx+20h], 0
0x180011502  mov     rax, [rdx+88h]
0x180011509  mov     [rcx+28h], rax
0x18001150d  mov     rax, [rdx+90h]
0x180011514  mov     [rcx+30h], rax
0x180011518  mov     qword ptr [r14], 0
0x18001151f  mov     rcx, [rdx+18h]; this
0x180011523  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180011528  mov     rcx, [r15+38h]; this
0x18001152c  mov     rbp, rax
0x18001152f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180011534  mov     rcx, [r15+80h]; this
0x18001153b  add     rbp, rax
0x18001153e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180011543  add     rbp, rax
0x180011546  lea     rdi, [rsi+48h]
0x18001154a  cmp     qword ptr [rsi+40h], 0
0x18001154f  jz      short loc_180011556
0x180011551  cmp     [rdi], rbp
0x180011554  jnb     short loc_18001158E
0x180011556  mov     rdx, rbp; dwBytes
0x180011559  mov     ecx, 8; dwFlags
0x18001155e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011563  mov     r14, rax
0x180011566  test    rax, rax
0x180011569  jz      short loc_18001158A
0x18001156b  mov     rbx, [rsi+40h]
0x18001156f  call    cs:__imp_GetProcessHeap
0x180011575  mov     r8, rbx; lpMem
0x180011578  xor     edx, edx; dwFlags
0x18001157a  mov     rcx, rax; hHeap
0x18001157d  call    cs:__imp_HeapFree
0x180011583  mov     [rsi+40h], r14
0x180011587  mov     [rdi], rbp
0x18001158a  lea     r14, [rsi+38h]
0x18001158e  mov     rcx, [rsi+40h]; Destination
0x180011592  test    rcx, rcx
0x180011595  jz      short loc_1800115E5
0x180011597  mov     rbx, [rdi]
0x18001159a  lea     r9, [rsi+10h]
0x18001159e  mov     r8, [r15+38h]
0x1800115a2  add     rbx, rcx
0x1800115a5  mov     rdx, rbx
0x1800115a8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800115ad  mov     r8, [r15+80h]
0x1800115b4  lea     r9, [rsi+20h]
0x1800115b8  mov     rdx, rbx
0x1800115bb  mov     rcx, rax; Destination
0x1800115be  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800115c3  mov     r8, [r15+18h]
0x1800115c7  mov     r9, r14
0x1800115ca  mov     rdx, rbx
0x1800115cd  mov     rcx, rax; Destination
0x1800115d0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800115d5  sub     rbx, rax
0x1800115d8  xor     edx, edx; Val
0x1800115da  mov     r8, rbx; Size
0x1800115dd  mov     rcx, rax; void *
0x1800115e0  call    memset_0
0x1800115e5  add     rsp, 28h
0x1800115e9  pop     r15
0x1800115eb  pop     r14
0x1800115ed  pop     r13
0x1800115ef  pop     r12
0x1800115f1  pop     rdi
0x1800115f2  pop     rsi
0x1800115f3  pop     rbp
0x1800115f4  pop     rbx
0x1800115f5  retn
```
