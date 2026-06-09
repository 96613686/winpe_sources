# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140004a9c`
- end: `0x140004c0d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140004c14`

## callees

- `0x140001fc3`
- `0x140002ccc`
- `0x140004768`
- `0x14000496c`
- `0x14000498c`
- `0x140004a9c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140004bd1`
- `msvcrt!memcpy_s` at `0x140004bd1`
- `KERNEL32!GetProcessHeap` at `0x140004b44`
- `KERNEL32!GetProcessHeap` at `0x140004b44`
- `KERNEL32!HeapFree` at `0x140004b52`
- `KERNEL32!HeapFree` at `0x140004b52`

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
0x140004a9c  push    rbx
0x140004a9e  push    rbp
0x140004a9f  push    rsi
0x140004aa0  push    rdi
0x140004aa1  push    r12
0x140004aa3  push    r13
0x140004aa5  push    r14
0x140004aa7  push    r15
0x140004aa9  sub     rsp, 28h
0x140004aad  mov     [rcx+4], r8d
0x140004ab1  lea     rbx, [rcx+20h]
0x140004ab5  mov     eax, [rdx+8]
0x140004ab8  lea     rsi, [rcx+38h]
0x140004abc  mov     [rcx+8], eax
0x140004abf  xor     r12d, r12d
0x140004ac2  mov     [rcx+10h], r12
0x140004ac6  mov     rbp, rcx
0x140004ac9  movzx   eax, word ptr [rdx+40h]
0x140004acd  mov     r14, rdx
0x140004ad0  mov     [rcx+18h], ax
0x140004ad4  mov     al, [rdx]
0x140004ad6  mov     [rcx+1Ah], al
0x140004ad9  mov     [rbx], r12
0x140004adc  mov     rax, [rdx+88h]
0x140004ae3  mov     [rcx+28h], rax
0x140004ae7  mov     rax, [rdx+90h]
0x140004aee  mov     [rcx+30h], rax
0x140004af2  mov     [rsi], r12
0x140004af5  mov     rcx, [rdx+18h]; this
0x140004af9  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140004afe  mov     rcx, [r14+38h]; this
0x140004b02  mov     r15, rax
0x140004b05  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004b0a  mov     rcx, [r14+80h]; this
0x140004b11  add     r15, rax
0x140004b14  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004b19  add     r15, rax
0x140004b1c  lea     rdi, [rbp+48h]
0x140004b20  cmp     [rbp+40h], r12
0x140004b24  jz      short loc_140004B2B
0x140004b26  cmp     [rdi], r15
0x140004b29  jnb     short loc_140004B66
0x140004b2b  mov     rdx, r15; dwBytes
0x140004b2e  mov     ecx, 8; dwFlags
0x140004b33  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004b38  mov     r12, rax
0x140004b3b  test    rax, rax
0x140004b3e  jz      short loc_140004B63
0x140004b40  mov     rbx, [rbp+40h]
0x140004b44  call    cs:__imp_GetProcessHeap
0x140004b4a  mov     r8, rbx; lpMem
0x140004b4d  xor     edx, edx; dwFlags
0x140004b4f  mov     rcx, rax; hHeap
0x140004b52  call    cs:__imp_HeapFree
0x140004b58  mov     [rbp+40h], r12
0x140004b5c  lea     rbx, [rbp+20h]
0x140004b60  mov     [rdi], r15
0x140004b63  xor     r12d, r12d
0x140004b66  mov     rcx, [rbp+40h]; Destination
0x140004b6a  test    rcx, rcx
0x140004b6d  jz      loc_140004BFC
0x140004b73  mov     rdi, [rdi]
0x140004b76  lea     r9, [rbp+10h]
0x140004b7a  mov     r8, [r14+38h]
0x140004b7e  add     rdi, rcx
0x140004b81  mov     rdx, rdi
0x140004b84  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140004b89  mov     r8, [r14+80h]
0x140004b90  mov     r9, rbx
0x140004b93  mov     rdx, rdi
0x140004b96  mov     rcx, rax; Destination
0x140004b99  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140004b9e  mov     rbx, rax
0x140004ba1  cmp     rax, rdi
0x140004ba4  jz      short loc_140004BE4
0x140004ba6  mov     rcx, [r14+18h]; this
0x140004baa  test    rcx, rcx
0x140004bad  jz      short loc_140004BE4
0x140004baf  cmp     [rcx], r12w
0x140004bb3  jz      short loc_140004BE4
0x140004bb5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140004bba  mov     rdx, rdi
0x140004bbd  mov     r14, rax
0x140004bc0  sub     rdx, rbx; DestinationSize
0x140004bc3  cmp     rdx, rax
0x140004bc6  jb      short loc_140004BE4
0x140004bc8  mov     r8, rcx; Source
0x140004bcb  mov     r9, rax; SourceSize
0x140004bce  mov     rcx, rbx; Destination
0x140004bd1  call    cs:__imp_memcpy_s
0x140004bd7  test    rsi, rsi
0x140004bda  jz      short loc_140004BDF
0x140004bdc  mov     [rsi], rbx
0x140004bdf  add     rbx, r14
0x140004be2  jmp     short loc_140004BEC
0x140004be4  test    rsi, rsi
0x140004be7  jz      short loc_140004BEC
0x140004be9  mov     [rsi], r12
0x140004bec  sub     rdi, rbx
0x140004bef  xor     edx, edx; Val
0x140004bf1  mov     r8, rdi; Size
0x140004bf4  mov     rcx, rbx; void *
0x140004bf7  call    memset_0
0x140004bfc  add     rsp, 28h
0x140004c00  pop     r15
0x140004c02  pop     r14
0x140004c04  pop     r13
0x140004c06  pop     r12
0x140004c08  pop     rdi
0x140004c09  pop     rsi
0x140004c0a  pop     rbp
0x140004c0b  pop     rbx
0x140004c0c  retn
```
