# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180011000`
- end: `0x180011136`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800115c0`

## callees

- `0x180002c2c`
- `0x1800074c0`
- `0x180007538`
- `0x18000f700`
- `0x180010ec8`
- `0x180010ee8`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110af`

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
0x180011000  push    rbx
0x180011002  push    rbp
0x180011003  push    rsi
0x180011004  push    rdi
0x180011005  push    r12
0x180011007  push    r13
0x180011009  push    r14
0x18001100b  push    r15
0x18001100d  sub     rsp, 28h
0x180011011  mov     [rcx+4], r8d
0x180011015  lea     r14, [rcx+38h]
0x180011019  mov     eax, [rdx+8]
0x18001101c  mov     rsi, rcx
0x18001101f  mov     [rcx+8], eax
0x180011022  mov     r15, rdx
0x180011025  mov     qword ptr [rcx+10h], 0
0x18001102d  movzx   eax, word ptr [rdx+40h]
0x180011031  mov     [rcx+18h], ax
0x180011035  mov     al, [rdx]
0x180011037  mov     [rcx+1Ah], al
0x18001103a  mov     qword ptr [rcx+20h], 0
0x180011042  mov     rax, [rdx+88h]
0x180011049  mov     [rcx+28h], rax
0x18001104d  mov     rax, [rdx+90h]
0x180011054  mov     [rcx+30h], rax
0x180011058  mov     qword ptr [r14], 0
0x18001105f  mov     rcx, [rdx+18h]; this
0x180011063  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180011068  mov     rcx, [r15+38h]; this
0x18001106c  mov     rbp, rax
0x18001106f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180011074  mov     rcx, [r15+80h]; this
0x18001107b  add     rbp, rax
0x18001107e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180011083  add     rbp, rax
0x180011086  lea     rdi, [rsi+48h]
0x18001108a  cmp     qword ptr [rsi+40h], 0
0x18001108f  jz      short loc_180011096
0x180011091  cmp     [rdi], rbp
0x180011094  jnb     short loc_1800110CE
0x180011096  mov     rdx, rbp; dwBytes
0x180011099  mov     ecx, 8; dwFlags
0x18001109e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800110a3  mov     r14, rax
0x1800110a6  test    rax, rax
0x1800110a9  jz      short loc_1800110CA
0x1800110ab  mov     rbx, [rsi+40h]
0x1800110af  call    cs:__imp_GetProcessHeap
0x1800110b5  mov     r8, rbx; lpMem
0x1800110b8  xor     edx, edx; dwFlags
0x1800110ba  mov     rcx, rax; hHeap
0x1800110bd  call    cs:__imp_HeapFree
0x1800110c3  mov     [rsi+40h], r14
0x1800110c7  mov     [rdi], rbp
0x1800110ca  lea     r14, [rsi+38h]
0x1800110ce  mov     rcx, [rsi+40h]; Destination
0x1800110d2  test    rcx, rcx
0x1800110d5  jz      short loc_180011125
0x1800110d7  mov     rbx, [rdi]
0x1800110da  lea     r9, [rsi+10h]
0x1800110de  mov     r8, [r15+38h]
0x1800110e2  add     rbx, rcx
0x1800110e5  mov     rdx, rbx
0x1800110e8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800110ed  mov     r8, [r15+80h]
0x1800110f4  lea     r9, [rsi+20h]
0x1800110f8  mov     rdx, rbx
0x1800110fb  mov     rcx, rax; Destination
0x1800110fe  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180011103  mov     r8, [r15+18h]
0x180011107  mov     r9, r14
0x18001110a  mov     rdx, rbx
0x18001110d  mov     rcx, rax; Destination
0x180011110  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180011115  sub     rbx, rax
0x180011118  xor     edx, edx; Val
0x18001111a  mov     r8, rbx; Size
0x18001111d  mov     rcx, rax; void *
0x180011120  call    memset_0
0x180011125  add     rsp, 28h
0x180011129  pop     r15
0x18001112b  pop     r14
0x18001112d  pop     r13
0x18001112f  pop     r12
0x180011131  pop     rdi
0x180011132  pop     rsi
0x180011133  pop     rbp
0x180011134  pop     rbx
0x180011135  retn
```
