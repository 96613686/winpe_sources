# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008590`
- end: `0x1800086c6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008a14`

## callees

- `0x180003114`
- `0x180004b60`
- `0x180004bd8`
- `0x180007688`
- `0x1800083fc`
- `0x18000841c`
- `0x180008590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000864d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000864d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000863f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000863f`

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
0x180008590  push    rbx
0x180008592  push    rbp
0x180008593  push    rsi
0x180008594  push    rdi
0x180008595  push    r12
0x180008597  push    r13
0x180008599  push    r14
0x18000859b  push    r15
0x18000859d  sub     rsp, 28h
0x1800085a1  mov     [rcx+4], r8d
0x1800085a5  lea     r14, [rcx+38h]
0x1800085a9  mov     eax, [rdx+8]
0x1800085ac  mov     rsi, rcx
0x1800085af  mov     [rcx+8], eax
0x1800085b2  mov     r15, rdx
0x1800085b5  mov     qword ptr [rcx+10h], 0
0x1800085bd  movzx   eax, word ptr [rdx+40h]
0x1800085c1  mov     [rcx+18h], ax
0x1800085c5  mov     al, [rdx]
0x1800085c7  mov     [rcx+1Ah], al
0x1800085ca  mov     qword ptr [rcx+20h], 0
0x1800085d2  mov     rax, [rdx+88h]
0x1800085d9  mov     [rcx+28h], rax
0x1800085dd  mov     rax, [rdx+90h]
0x1800085e4  mov     [rcx+30h], rax
0x1800085e8  mov     qword ptr [r14], 0
0x1800085ef  mov     rcx, [rdx+18h]; this
0x1800085f3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800085f8  mov     rcx, [r15+38h]; this
0x1800085fc  mov     rbp, rax
0x1800085ff  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008604  mov     rcx, [r15+80h]; this
0x18000860b  add     rbp, rax
0x18000860e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008613  add     rbp, rax
0x180008616  lea     rdi, [rsi+48h]
0x18000861a  cmp     qword ptr [rsi+40h], 0
0x18000861f  jz      short loc_180008626
0x180008621  cmp     [rdi], rbp
0x180008624  jnb     short loc_18000865E
0x180008626  mov     rdx, rbp; dwBytes
0x180008629  mov     ecx, 8; dwFlags
0x18000862e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008633  mov     r14, rax
0x180008636  test    rax, rax
0x180008639  jz      short loc_18000865A
0x18000863b  mov     rbx, [rsi+40h]
0x18000863f  call    cs:__imp_GetProcessHeap
0x180008645  mov     r8, rbx; lpMem
0x180008648  xor     edx, edx; dwFlags
0x18000864a  mov     rcx, rax; hHeap
0x18000864d  call    cs:__imp_HeapFree
0x180008653  mov     [rsi+40h], r14
0x180008657  mov     [rdi], rbp
0x18000865a  lea     r14, [rsi+38h]
0x18000865e  mov     rcx, [rsi+40h]; Destination
0x180008662  test    rcx, rcx
0x180008665  jz      short loc_1800086B5
0x180008667  mov     rbx, [rdi]
0x18000866a  lea     r9, [rsi+10h]
0x18000866e  mov     r8, [r15+38h]
0x180008672  add     rbx, rcx
0x180008675  mov     rdx, rbx
0x180008678  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000867d  mov     r8, [r15+80h]
0x180008684  lea     r9, [rsi+20h]
0x180008688  mov     rdx, rbx
0x18000868b  mov     rcx, rax; Destination
0x18000868e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008693  mov     r8, [r15+18h]
0x180008697  mov     r9, r14
0x18000869a  mov     rdx, rbx
0x18000869d  mov     rcx, rax; Destination
0x1800086a0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800086a5  sub     rbx, rax
0x1800086a8  xor     edx, edx; Val
0x1800086aa  mov     r8, rbx; Size
0x1800086ad  mov     rcx, rax; void *
0x1800086b0  call    memset_0
0x1800086b5  add     rsp, 28h
0x1800086b9  pop     r15
0x1800086bb  pop     r14
0x1800086bd  pop     r13
0x1800086bf  pop     r12
0x1800086c1  pop     rdi
0x1800086c2  pop     rsi
0x1800086c3  pop     rbp
0x1800086c4  pop     rbx
0x1800086c5  retn
```
