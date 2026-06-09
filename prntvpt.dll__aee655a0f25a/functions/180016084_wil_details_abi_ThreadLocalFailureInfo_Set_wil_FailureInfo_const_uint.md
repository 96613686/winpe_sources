# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180016084`
- end: `0x1800161f4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800162e8`

## callees

- `0x18000d3c8`
- `0x1800103e8`
- `0x180010d60`
- `0x18001498c`
- `0x180015f00`
- `0x180015f20`
- `0x180016084`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001612c`
- `KERNEL32!GetProcessHeap` at `0x18001612c`
- `KERNEL32!HeapFree` at `0x18001613a`
- `KERNEL32!HeapFree` at `0x18001613a`

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
0x180016084  push    rbx
0x180016086  push    rbp
0x180016087  push    rsi
0x180016088  push    rdi
0x180016089  push    r12
0x18001608b  push    r13
0x18001608d  push    r14
0x18001608f  push    r15
0x180016091  sub     rsp, 28h
0x180016095  mov     [rcx+4], r8d
0x180016099  lea     rbx, [rcx+20h]
0x18001609d  mov     eax, [rdx+8]
0x1800160a0  lea     rsi, [rcx+38h]
0x1800160a4  mov     [rcx+8], eax
0x1800160a7  xor     r12d, r12d
0x1800160aa  mov     [rcx+10h], r12
0x1800160ae  mov     rbp, rcx
0x1800160b1  movzx   eax, word ptr [rdx+40h]
0x1800160b5  mov     r14, rdx
0x1800160b8  mov     [rcx+18h], ax
0x1800160bc  mov     al, [rdx]
0x1800160be  mov     [rcx+1Ah], al
0x1800160c1  mov     [rbx], r12
0x1800160c4  mov     rax, [rdx+88h]
0x1800160cb  mov     [rcx+28h], rax
0x1800160cf  mov     rax, [rdx+90h]
0x1800160d6  mov     [rcx+30h], rax
0x1800160da  mov     [rsi], r12
0x1800160dd  mov     rcx, [rdx+18h]; this
0x1800160e1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800160e6  mov     rcx, [r14+38h]; this
0x1800160ea  mov     r15, rax
0x1800160ed  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800160f2  mov     rcx, [r14+80h]; this
0x1800160f9  add     r15, rax
0x1800160fc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180016101  add     r15, rax
0x180016104  lea     rdi, [rbp+48h]
0x180016108  cmp     [rbp+40h], r12
0x18001610c  jz      short loc_180016113
0x18001610e  cmp     [rdi], r15
0x180016111  jnb     short loc_18001614E
0x180016113  mov     rdx, r15; dwBytes
0x180016116  mov     ecx, 8; dwFlags
0x18001611b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180016120  mov     r12, rax
0x180016123  test    rax, rax
0x180016126  jz      short loc_18001614B
0x180016128  mov     rbx, [rbp+40h]
0x18001612c  call    cs:__imp_GetProcessHeap
0x180016132  mov     r8, rbx; lpMem
0x180016135  xor     edx, edx; dwFlags
0x180016137  mov     rcx, rax; hHeap
0x18001613a  call    cs:__imp_HeapFree
0x180016140  mov     [rbp+40h], r12
0x180016144  lea     rbx, [rbp+20h]
0x180016148  mov     [rdi], r15
0x18001614b  xor     r12d, r12d
0x18001614e  mov     rcx, [rbp+40h]; Destination
0x180016152  test    rcx, rcx
0x180016155  jz      loc_1800161E3
0x18001615b  mov     rdi, [rdi]
0x18001615e  lea     r9, [rbp+10h]
0x180016162  mov     r8, [r14+38h]
0x180016166  add     rdi, rcx
0x180016169  mov     rdx, rdi
0x18001616c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016171  mov     r8, [r14+80h]
0x180016178  mov     r9, rbx
0x18001617b  mov     rdx, rdi
0x18001617e  mov     rcx, rax; Destination
0x180016181  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016186  mov     rbx, rax
0x180016189  cmp     rax, rdi
0x18001618c  jz      short loc_1800161CB
0x18001618e  mov     rcx, [r14+18h]; this
0x180016192  test    rcx, rcx
0x180016195  jz      short loc_1800161CB
0x180016197  cmp     [rcx], r12w
0x18001619b  jz      short loc_1800161CB
0x18001619d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800161a2  mov     rdx, rdi
0x1800161a5  mov     r14, rax
0x1800161a8  sub     rdx, rbx; DestinationSize
0x1800161ab  cmp     rdx, rax
0x1800161ae  jb      short loc_1800161CB
0x1800161b0  mov     r8, rcx; Source
0x1800161b3  mov     r9, rax; SourceSize
0x1800161b6  mov     rcx, rbx; Destination
0x1800161b9  call    memcpy_s
0x1800161be  test    rsi, rsi
0x1800161c1  jz      short loc_1800161C6
0x1800161c3  mov     [rsi], rbx
0x1800161c6  add     rbx, r14
0x1800161c9  jmp     short loc_1800161D3
0x1800161cb  test    rsi, rsi
0x1800161ce  jz      short loc_1800161D3
0x1800161d0  mov     [rsi], r12
0x1800161d3  sub     rdi, rbx
0x1800161d6  xor     edx, edx; Val
0x1800161d8  mov     r8, rdi; Size
0x1800161db  mov     rcx, rbx; void *
0x1800161de  call    memset_0
0x1800161e3  add     rsp, 28h
0x1800161e7  pop     r15
0x1800161e9  pop     r14
0x1800161eb  pop     r13
0x1800161ed  pop     r12
0x1800161ef  pop     rdi
0x1800161f0  pop     rsi
0x1800161f1  pop     rbp
0x1800161f2  pop     rbx
0x1800161f3  retn
```
