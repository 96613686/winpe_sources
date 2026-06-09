# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800079f4`
- end: `0x180007b65`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007c5c`

## callees

- `0x1800044bc`
- `0x180006a5c`
- `0x1800077d8`
- `0x1800077f8`
- `0x1800079f4`
- `0x180009922`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007b29`
- `msvcrt!memcpy_s` at `0x180007b29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aaa`

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
0x1800079f4  push    rbx
0x1800079f6  push    rbp
0x1800079f7  push    rsi
0x1800079f8  push    rdi
0x1800079f9  push    r12
0x1800079fb  push    r13
0x1800079fd  push    r14
0x1800079ff  push    r15
0x180007a01  sub     rsp, 28h
0x180007a05  mov     [rcx+4], r8d
0x180007a09  lea     rbx, [rcx+20h]
0x180007a0d  mov     eax, [rdx+8]
0x180007a10  lea     rsi, [rcx+38h]
0x180007a14  mov     [rcx+8], eax
0x180007a17  xor     r12d, r12d
0x180007a1a  mov     [rcx+10h], r12
0x180007a1e  mov     rbp, rcx
0x180007a21  movzx   eax, word ptr [rdx+40h]
0x180007a25  mov     r14, rdx
0x180007a28  mov     [rcx+18h], ax
0x180007a2c  mov     al, [rdx]
0x180007a2e  mov     [rcx+1Ah], al
0x180007a31  mov     [rbx], r12
0x180007a34  mov     rax, [rdx+88h]
0x180007a3b  mov     [rcx+28h], rax
0x180007a3f  mov     rax, [rdx+90h]
0x180007a46  mov     [rcx+30h], rax
0x180007a4a  mov     [rsi], r12
0x180007a4d  mov     rcx, [rdx+18h]; this
0x180007a51  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007a56  mov     rcx, [r14+38h]; this
0x180007a5a  mov     r15, rax
0x180007a5d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007a62  mov     rcx, [r14+80h]; this
0x180007a69  add     r15, rax
0x180007a6c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007a71  add     r15, rax
0x180007a74  lea     rdi, [rbp+48h]
0x180007a78  cmp     [rbp+40h], r12
0x180007a7c  jz      short loc_180007A83
0x180007a7e  cmp     [rdi], r15
0x180007a81  jnb     short loc_180007ABE
0x180007a83  mov     rdx, r15; dwBytes
0x180007a86  mov     ecx, 8; dwFlags
0x180007a8b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007a90  mov     r12, rax
0x180007a93  test    rax, rax
0x180007a96  jz      short loc_180007ABB
0x180007a98  mov     rbx, [rbp+40h]
0x180007a9c  call    cs:__imp_GetProcessHeap
0x180007aa2  mov     r8, rbx; lpMem
0x180007aa5  xor     edx, edx; dwFlags
0x180007aa7  mov     rcx, rax; hHeap
0x180007aaa  call    cs:__imp_HeapFree
0x180007ab0  mov     [rbp+40h], r12
0x180007ab4  lea     rbx, [rbp+20h]
0x180007ab8  mov     [rdi], r15
0x180007abb  xor     r12d, r12d
0x180007abe  mov     rcx, [rbp+40h]; Destination
0x180007ac2  test    rcx, rcx
0x180007ac5  jz      loc_180007B54
0x180007acb  mov     rdi, [rdi]
0x180007ace  lea     r9, [rbp+10h]
0x180007ad2  mov     r8, [r14+38h]
0x180007ad6  add     rdi, rcx
0x180007ad9  mov     rdx, rdi
0x180007adc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007ae1  mov     r8, [r14+80h]
0x180007ae8  mov     r9, rbx
0x180007aeb  mov     rdx, rdi
0x180007aee  mov     rcx, rax; Destination
0x180007af1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007af6  mov     rbx, rax
0x180007af9  cmp     rax, rdi
0x180007afc  jz      short loc_180007B3C
0x180007afe  mov     rcx, [r14+18h]; this
0x180007b02  test    rcx, rcx
0x180007b05  jz      short loc_180007B3C
0x180007b07  cmp     [rcx], r12w
0x180007b0b  jz      short loc_180007B3C
0x180007b0d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007b12  mov     rdx, rdi
0x180007b15  mov     r14, rax
0x180007b18  sub     rdx, rbx; DestinationSize
0x180007b1b  cmp     rdx, rax
0x180007b1e  jb      short loc_180007B3C
0x180007b20  mov     r8, rcx; Source
0x180007b23  mov     r9, rax; SourceSize
0x180007b26  mov     rcx, rbx; Destination
0x180007b29  call    cs:__imp_memcpy_s
0x180007b2f  test    rsi, rsi
0x180007b32  jz      short loc_180007B37
0x180007b34  mov     [rsi], rbx
0x180007b37  add     rbx, r14
0x180007b3a  jmp     short loc_180007B44
0x180007b3c  test    rsi, rsi
0x180007b3f  jz      short loc_180007B44
0x180007b41  mov     [rsi], r12
0x180007b44  sub     rdi, rbx
0x180007b47  xor     edx, edx; Val
0x180007b49  mov     r8, rdi; Size
0x180007b4c  mov     rcx, rbx; void *
0x180007b4f  call    memset_0
0x180007b54  add     rsp, 28h
0x180007b58  pop     r15
0x180007b5a  pop     r14
0x180007b5c  pop     r13
0x180007b5e  pop     r12
0x180007b60  pop     rdi
0x180007b61  pop     rsi
0x180007b62  pop     rbp
0x180007b63  pop     rbx
0x180007b64  retn
```
