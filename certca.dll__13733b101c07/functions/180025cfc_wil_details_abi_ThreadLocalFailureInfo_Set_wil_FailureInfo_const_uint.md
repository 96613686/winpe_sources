# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180025cfc`
- end: `0x180025e32`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025f28`

## callees

- `0x18001c374`
- `0x18001c3ec`
- `0x18001cea4`
- `0x18001cec4`
- `0x180024f90`
- `0x180025cfc`
- `0x180038262`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025db9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025db9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025dab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025dab`

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
0x180025cfc  push    rbx
0x180025cfe  push    rbp
0x180025cff  push    rsi
0x180025d00  push    rdi
0x180025d01  push    r12
0x180025d03  push    r13
0x180025d05  push    r14
0x180025d07  push    r15
0x180025d09  sub     rsp, 28h
0x180025d0d  mov     [rcx+4], r8d
0x180025d11  lea     r14, [rcx+38h]
0x180025d15  mov     eax, [rdx+8]
0x180025d18  mov     rsi, rcx
0x180025d1b  mov     [rcx+8], eax
0x180025d1e  mov     r15, rdx
0x180025d21  mov     qword ptr [rcx+10h], 0
0x180025d29  movzx   eax, word ptr [rdx+40h]
0x180025d2d  mov     [rcx+18h], ax
0x180025d31  mov     al, [rdx]
0x180025d33  mov     [rcx+1Ah], al
0x180025d36  mov     qword ptr [rcx+20h], 0
0x180025d3e  mov     rax, [rdx+88h]
0x180025d45  mov     [rcx+28h], rax
0x180025d49  mov     rax, [rdx+90h]
0x180025d50  mov     [rcx+30h], rax
0x180025d54  mov     qword ptr [r14], 0
0x180025d5b  mov     rcx, [rdx+18h]; this
0x180025d5f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180025d64  mov     rcx, [r15+38h]; this
0x180025d68  mov     rbp, rax
0x180025d6b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180025d70  mov     rcx, [r15+80h]; this
0x180025d77  add     rbp, rax
0x180025d7a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180025d7f  add     rbp, rax
0x180025d82  lea     rdi, [rsi+48h]
0x180025d86  cmp     qword ptr [rsi+40h], 0
0x180025d8b  jz      short loc_180025D92
0x180025d8d  cmp     [rdi], rbp
0x180025d90  jnb     short loc_180025DCA
0x180025d92  mov     rdx, rbp; dwBytes
0x180025d95  mov     ecx, 8; dwFlags
0x180025d9a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180025d9f  mov     r14, rax
0x180025da2  test    rax, rax
0x180025da5  jz      short loc_180025DC6
0x180025da7  mov     rbx, [rsi+40h]
0x180025dab  call    cs:__imp_GetProcessHeap
0x180025db1  mov     r8, rbx; lpMem
0x180025db4  xor     edx, edx; dwFlags
0x180025db6  mov     rcx, rax; hHeap
0x180025db9  call    cs:__imp_HeapFree
0x180025dbf  mov     [rsi+40h], r14
0x180025dc3  mov     [rdi], rbp
0x180025dc6  lea     r14, [rsi+38h]
0x180025dca  mov     rcx, [rsi+40h]; Destination
0x180025dce  test    rcx, rcx
0x180025dd1  jz      short loc_180025E21
0x180025dd3  mov     rbx, [rdi]
0x180025dd6  lea     r9, [rsi+10h]
0x180025dda  mov     r8, [r15+38h]
0x180025dde  add     rbx, rcx
0x180025de1  mov     rdx, rbx
0x180025de4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180025de9  mov     r8, [r15+80h]
0x180025df0  lea     r9, [rsi+20h]
0x180025df4  mov     rdx, rbx
0x180025df7  mov     rcx, rax; Destination
0x180025dfa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180025dff  mov     r8, [r15+18h]
0x180025e03  mov     r9, r14
0x180025e06  mov     rdx, rbx
0x180025e09  mov     rcx, rax; Destination
0x180025e0c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180025e11  sub     rbx, rax
0x180025e14  xor     edx, edx; Val
0x180025e16  mov     r8, rbx; Size
0x180025e19  mov     rcx, rax; void *
0x180025e1c  call    memset_0
0x180025e21  add     rsp, 28h
0x180025e25  pop     r15
0x180025e27  pop     r14
0x180025e29  pop     r13
0x180025e2b  pop     r12
0x180025e2d  pop     rdi
0x180025e2e  pop     rsi
0x180025e2f  pop     rbp
0x180025e30  pop     rbx
0x180025e31  retn
```
