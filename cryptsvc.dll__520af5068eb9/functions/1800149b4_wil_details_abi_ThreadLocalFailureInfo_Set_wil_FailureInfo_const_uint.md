# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800149b4`
- end: `0x180014b24`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014c18`

## callees

- `0x18000ec1c`
- `0x18000ec40`
- `0x180011dc8`
- `0x180014130`
- `0x180014900`
- `0x180014928`
- `0x1800149b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014a5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014a5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014a6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014a6a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x1800149b4  push    rbx
0x1800149b6  push    rbp
0x1800149b7  push    rsi
0x1800149b8  push    rdi
0x1800149b9  push    r12
0x1800149bb  push    r13
0x1800149bd  push    r14
0x1800149bf  push    r15
0x1800149c1  sub     rsp, 28h
0x1800149c5  mov     [rcx+4], r8d
0x1800149c9  lea     rbx, [rcx+20h]
0x1800149cd  mov     eax, [rdx+8]
0x1800149d0  lea     rsi, [rcx+38h]
0x1800149d4  mov     [rcx+8], eax
0x1800149d7  xor     r12d, r12d
0x1800149da  mov     [rcx+10h], r12
0x1800149de  mov     rbp, rcx
0x1800149e1  movzx   eax, word ptr [rdx+40h]
0x1800149e5  mov     r14, rdx
0x1800149e8  mov     [rcx+18h], ax
0x1800149ec  mov     al, [rdx]
0x1800149ee  mov     [rcx+1Ah], al
0x1800149f1  mov     [rbx], r12
0x1800149f4  mov     rax, [rdx+88h]
0x1800149fb  mov     [rcx+28h], rax
0x1800149ff  mov     rax, [rdx+90h]
0x180014a06  mov     [rcx+30h], rax
0x180014a0a  mov     [rsi], r12
0x180014a0d  mov     rcx, [rdx+18h]; this
0x180014a11  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180014a16  mov     rcx, [r14+38h]; this
0x180014a1a  mov     r15, rax
0x180014a1d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180014a22  mov     rcx, [r14+80h]; this
0x180014a29  add     r15, rax
0x180014a2c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180014a31  add     r15, rax
0x180014a34  lea     rdi, [rbp+48h]
0x180014a38  cmp     [rbp+40h], r12
0x180014a3c  jz      short loc_180014A43
0x180014a3e  cmp     [rdi], r15
0x180014a41  jnb     short loc_180014A7E
0x180014a43  mov     rdx, r15; dwBytes
0x180014a46  mov     ecx, 8; dwFlags
0x180014a4b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014a50  mov     r12, rax
0x180014a53  test    rax, rax
0x180014a56  jz      short loc_180014A7B
0x180014a58  mov     rbx, [rbp+40h]
0x180014a5c  call    cs:__imp_GetProcessHeap
0x180014a62  mov     r8, rbx; lpMem
0x180014a65  xor     edx, edx; dwFlags
0x180014a67  mov     rcx, rax; hHeap
0x180014a6a  call    cs:__imp_HeapFree
0x180014a70  mov     [rbp+40h], r12
0x180014a74  lea     rbx, [rbp+20h]
0x180014a78  mov     [rdi], r15
0x180014a7b  xor     r12d, r12d
0x180014a7e  mov     rcx, [rbp+40h]; Destination
0x180014a82  test    rcx, rcx
0x180014a85  jz      loc_180014B13
0x180014a8b  mov     rdi, [rdi]
0x180014a8e  lea     r9, [rbp+10h]
0x180014a92  mov     r8, [r14+38h]
0x180014a96  add     rdi, rcx
0x180014a99  mov     rdx, rdi
0x180014a9c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014aa1  mov     r8, [r14+80h]
0x180014aa8  mov     r9, rbx
0x180014aab  mov     rdx, rdi
0x180014aae  mov     rcx, rax; Destination
0x180014ab1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014ab6  mov     rbx, rax
0x180014ab9  cmp     rax, rdi
0x180014abc  jz      short loc_180014AFB
0x180014abe  mov     rcx, [r14+18h]; this
0x180014ac2  test    rcx, rcx
0x180014ac5  jz      short loc_180014AFB
0x180014ac7  cmp     [rcx], r12w
0x180014acb  jz      short loc_180014AFB
0x180014acd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180014ad2  mov     rdx, rdi
0x180014ad5  mov     r14, rax
0x180014ad8  sub     rdx, rbx; DestinationSize
0x180014adb  cmp     rdx, rax
0x180014ade  jb      short loc_180014AFB
0x180014ae0  mov     r8, rcx; Source
0x180014ae3  mov     r9, rax; SourceSize
0x180014ae6  mov     rcx, rbx; Destination
0x180014ae9  call    memcpy_s
0x180014aee  test    rsi, rsi
0x180014af1  jz      short loc_180014AF6
0x180014af3  mov     [rsi], rbx
0x180014af6  add     rbx, r14
0x180014af9  jmp     short loc_180014B03
0x180014afb  test    rsi, rsi
0x180014afe  jz      short loc_180014B03
0x180014b00  mov     [rsi], r12
0x180014b03  sub     rdi, rbx
0x180014b06  xor     edx, edx; Val
0x180014b08  mov     r8, rdi; Size
0x180014b0b  mov     rcx, rbx; void *
0x180014b0e  call    memset_0
0x180014b13  add     rsp, 28h
0x180014b17  pop     r15
0x180014b19  pop     r14
0x180014b1b  pop     r13
0x180014b1d  pop     r12
0x180014b1f  pop     rdi
0x180014b20  pop     rsi
0x180014b21  pop     rbp
0x180014b22  pop     rbx
0x180014b23  retn
```
