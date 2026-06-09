# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001316c`
- end: `0x1800132dc`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800133b8`

## callees

- `0x18000b468`
- `0x18000f8f4`
- `0x1800115ac`
- `0x1800130bc`
- `0x1800130dc`
- `0x18001316c`
- `0x180014cf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013222`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013214`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
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
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18001316c  push    rbx
0x18001316e  push    rbp
0x18001316f  push    rsi
0x180013170  push    rdi
0x180013171  push    r12
0x180013173  push    r13
0x180013175  push    r14
0x180013177  push    r15
0x180013179  sub     rsp, 28h
0x18001317d  mov     [rcx+4], r8d
0x180013181  lea     rbx, [rcx+20h]
0x180013185  mov     eax, [rdx+8]
0x180013188  lea     rsi, [rcx+38h]
0x18001318c  mov     [rcx+8], eax
0x18001318f  xor     r12d, r12d
0x180013192  mov     [rcx+10h], r12
0x180013196  mov     rbp, rcx
0x180013199  movzx   eax, word ptr [rdx+40h]
0x18001319d  mov     r14, rdx
0x1800131a0  mov     [rcx+18h], ax
0x1800131a4  mov     al, [rdx]
0x1800131a6  mov     [rcx+1Ah], al
0x1800131a9  mov     [rbx], r12
0x1800131ac  mov     rax, [rdx+88h]
0x1800131b3  mov     [rcx+28h], rax
0x1800131b7  mov     rax, [rdx+90h]
0x1800131be  mov     [rcx+30h], rax
0x1800131c2  mov     [rsi], r12
0x1800131c5  mov     rcx, [rdx+18h]; this
0x1800131c9  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800131ce  mov     rcx, [r14+38h]; this
0x1800131d2  mov     r15, rax
0x1800131d5  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800131da  mov     rcx, [r14+80h]; this
0x1800131e1  add     r15, rax
0x1800131e4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800131e9  add     r15, rax
0x1800131ec  lea     rdi, [rbp+48h]
0x1800131f0  cmp     [rbp+40h], r12
0x1800131f4  jz      short loc_1800131FB
0x1800131f6  cmp     [rdi], r15
0x1800131f9  jnb     short loc_180013236
0x1800131fb  mov     rdx, r15; dwBytes
0x1800131fe  mov     ecx, 8; dwFlags
0x180013203  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013208  mov     r12, rax
0x18001320b  test    rax, rax
0x18001320e  jz      short loc_180013233
0x180013210  mov     rbx, [rbp+40h]
0x180013214  call    cs:__imp_GetProcessHeap
0x18001321a  mov     r8, rbx; lpMem
0x18001321d  xor     edx, edx; dwFlags
0x18001321f  mov     rcx, rax; hHeap
0x180013222  call    cs:__imp_HeapFree
0x180013228  mov     [rbp+40h], r12
0x18001322c  lea     rbx, [rbp+20h]
0x180013230  mov     [rdi], r15
0x180013233  xor     r12d, r12d
0x180013236  mov     rcx, [rbp+40h]; Destination
0x18001323a  test    rcx, rcx
0x18001323d  jz      loc_1800132CB
0x180013243  mov     rdi, [rdi]
0x180013246  lea     r9, [rbp+10h]
0x18001324a  mov     r8, [r14+38h]
0x18001324e  add     rdi, rcx
0x180013251  mov     rdx, rdi
0x180013254  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180013259  mov     r8, [r14+80h]
0x180013260  mov     r9, rbx
0x180013263  mov     rdx, rdi
0x180013266  mov     rcx, rax; Destination
0x180013269  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001326e  mov     rbx, rax
0x180013271  cmp     rax, rdi
0x180013274  jz      short loc_1800132B3
0x180013276  mov     rcx, [r14+18h]; this
0x18001327a  test    rcx, rcx
0x18001327d  jz      short loc_1800132B3
0x18001327f  cmp     [rcx], r12w
0x180013283  jz      short loc_1800132B3
0x180013285  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001328a  mov     rdx, rdi
0x18001328d  mov     r14, rax
0x180013290  sub     rdx, rbx; DestinationSize
0x180013293  cmp     rdx, rax
0x180013296  jb      short loc_1800132B3
0x180013298  mov     r8, rcx; Source
0x18001329b  mov     r9, rax; SourceSize
0x18001329e  mov     rcx, rbx; Destination
0x1800132a1  call    memcpy_s
0x1800132a6  test    rsi, rsi
0x1800132a9  jz      short loc_1800132AE
0x1800132ab  mov     [rsi], rbx
0x1800132ae  add     rbx, r14
0x1800132b1  jmp     short loc_1800132BB
0x1800132b3  test    rsi, rsi
0x1800132b6  jz      short loc_1800132BB
0x1800132b8  mov     [rsi], r12
0x1800132bb  sub     rdi, rbx
0x1800132be  xor     edx, edx; Val
0x1800132c0  mov     r8, rdi; Size
0x1800132c3  mov     rcx, rbx; void *
0x1800132c6  call    memset_0
0x1800132cb  add     rsp, 28h
0x1800132cf  pop     r15
0x1800132d1  pop     r14
0x1800132d3  pop     r13
0x1800132d5  pop     r12
0x1800132d7  pop     rdi
0x1800132d8  pop     rsi
0x1800132d9  pop     rbp
0x1800132da  pop     rbx
0x1800132db  retn
```
