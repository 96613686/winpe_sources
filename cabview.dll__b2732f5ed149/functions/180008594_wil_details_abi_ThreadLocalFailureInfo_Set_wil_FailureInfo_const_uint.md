# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008594`
- end: `0x1800086ca`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800087bc`

## callees

- `0x180002f40`
- `0x1800039c8`
- `0x180003a40`
- `0x180007460`
- `0x1800083c8`
- `0x1800083e8`
- `0x180008594`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008651`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008643`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008643`

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
0x180008594  push    rbx
0x180008596  push    rbp
0x180008597  push    rsi
0x180008598  push    rdi
0x180008599  push    r12
0x18000859b  push    r13
0x18000859d  push    r14
0x18000859f  push    r15
0x1800085a1  sub     rsp, 28h
0x1800085a5  mov     [rcx+4], r8d
0x1800085a9  lea     r14, [rcx+38h]
0x1800085ad  mov     eax, [rdx+8]
0x1800085b0  mov     rsi, rcx
0x1800085b3  mov     [rcx+8], eax
0x1800085b6  mov     r15, rdx
0x1800085b9  mov     qword ptr [rcx+10h], 0
0x1800085c1  movzx   eax, word ptr [rdx+40h]
0x1800085c5  mov     [rcx+18h], ax
0x1800085c9  mov     al, [rdx]
0x1800085cb  mov     [rcx+1Ah], al
0x1800085ce  mov     qword ptr [rcx+20h], 0
0x1800085d6  mov     rax, [rdx+88h]
0x1800085dd  mov     [rcx+28h], rax
0x1800085e1  mov     rax, [rdx+90h]
0x1800085e8  mov     [rcx+30h], rax
0x1800085ec  mov     qword ptr [r14], 0
0x1800085f3  mov     rcx, [rdx+18h]; this
0x1800085f7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800085fc  mov     rcx, [r15+38h]; this
0x180008600  mov     rbp, rax
0x180008603  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008608  mov     rcx, [r15+80h]; this
0x18000860f  add     rbp, rax
0x180008612  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008617  add     rbp, rax
0x18000861a  lea     rdi, [rsi+48h]
0x18000861e  cmp     qword ptr [rsi+40h], 0
0x180008623  jz      short loc_18000862A
0x180008625  cmp     [rdi], rbp
0x180008628  jnb     short loc_180008662
0x18000862a  mov     rdx, rbp; dwBytes
0x18000862d  mov     ecx, 8; dwFlags
0x180008632  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008637  mov     r14, rax
0x18000863a  test    rax, rax
0x18000863d  jz      short loc_18000865E
0x18000863f  mov     rbx, [rsi+40h]
0x180008643  call    cs:__imp_GetProcessHeap
0x180008649  mov     r8, rbx; lpMem
0x18000864c  xor     edx, edx; dwFlags
0x18000864e  mov     rcx, rax; hHeap
0x180008651  call    cs:__imp_HeapFree
0x180008657  mov     [rsi+40h], r14
0x18000865b  mov     [rdi], rbp
0x18000865e  lea     r14, [rsi+38h]
0x180008662  mov     rcx, [rsi+40h]; Destination
0x180008666  test    rcx, rcx
0x180008669  jz      short loc_1800086B9
0x18000866b  mov     rbx, [rdi]
0x18000866e  lea     r9, [rsi+10h]
0x180008672  mov     r8, [r15+38h]
0x180008676  add     rbx, rcx
0x180008679  mov     rdx, rbx
0x18000867c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008681  mov     r8, [r15+80h]
0x180008688  lea     r9, [rsi+20h]
0x18000868c  mov     rdx, rbx
0x18000868f  mov     rcx, rax; Destination
0x180008692  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008697  mov     r8, [r15+18h]
0x18000869b  mov     r9, r14
0x18000869e  mov     rdx, rbx
0x1800086a1  mov     rcx, rax; Destination
0x1800086a4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800086a9  sub     rbx, rax
0x1800086ac  xor     edx, edx; Val
0x1800086ae  mov     r8, rbx; Size
0x1800086b1  mov     rcx, rax; void *
0x1800086b4  call    memset_0
0x1800086b9  add     rsp, 28h
0x1800086bd  pop     r15
0x1800086bf  pop     r14
0x1800086c1  pop     r13
0x1800086c3  pop     r12
0x1800086c5  pop     rdi
0x1800086c6  pop     rsi
0x1800086c7  pop     rbp
0x1800086c8  pop     rbx
0x1800086c9  retn
```
