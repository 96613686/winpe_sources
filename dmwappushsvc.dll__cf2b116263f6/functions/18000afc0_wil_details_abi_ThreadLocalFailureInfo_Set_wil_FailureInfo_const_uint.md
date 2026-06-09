# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000afc0`
- end: `0x18000b0f6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b1e8`

## callees

- `0x180002554`
- `0x180004c44`
- `0x180004cbc`
- `0x1800056d4`
- `0x1800056f4`
- `0x180009c48`
- `0x18000afc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b07d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b07d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b06f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b06f`

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
0x18000afc0  push    rbx
0x18000afc2  push    rbp
0x18000afc3  push    rsi
0x18000afc4  push    rdi
0x18000afc5  push    r12
0x18000afc7  push    r13
0x18000afc9  push    r14
0x18000afcb  push    r15
0x18000afcd  sub     rsp, 28h
0x18000afd1  mov     [rcx+4], r8d
0x18000afd5  lea     r14, [rcx+38h]
0x18000afd9  mov     eax, [rdx+8]
0x18000afdc  mov     rsi, rcx
0x18000afdf  mov     [rcx+8], eax
0x18000afe2  mov     r15, rdx
0x18000afe5  mov     qword ptr [rcx+10h], 0
0x18000afed  movzx   eax, word ptr [rdx+40h]
0x18000aff1  mov     [rcx+18h], ax
0x18000aff5  mov     al, [rdx]
0x18000aff7  mov     [rcx+1Ah], al
0x18000affa  mov     qword ptr [rcx+20h], 0
0x18000b002  mov     rax, [rdx+88h]
0x18000b009  mov     [rcx+28h], rax
0x18000b00d  mov     rax, [rdx+90h]
0x18000b014  mov     [rcx+30h], rax
0x18000b018  mov     qword ptr [r14], 0
0x18000b01f  mov     rcx, [rdx+18h]; this
0x18000b023  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b028  mov     rcx, [r15+38h]; this
0x18000b02c  mov     rbp, rax
0x18000b02f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b034  mov     rcx, [r15+80h]; this
0x18000b03b  add     rbp, rax
0x18000b03e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b043  add     rbp, rax
0x18000b046  lea     rdi, [rsi+48h]
0x18000b04a  cmp     qword ptr [rsi+40h], 0
0x18000b04f  jz      short loc_18000B056
0x18000b051  cmp     [rdi], rbp
0x18000b054  jnb     short loc_18000B08E
0x18000b056  mov     rdx, rbp; dwBytes
0x18000b059  mov     ecx, 8; dwFlags
0x18000b05e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b063  mov     r14, rax
0x18000b066  test    rax, rax
0x18000b069  jz      short loc_18000B08A
0x18000b06b  mov     rbx, [rsi+40h]
0x18000b06f  call    cs:__imp_GetProcessHeap
0x18000b075  mov     r8, rbx; lpMem
0x18000b078  xor     edx, edx; dwFlags
0x18000b07a  mov     rcx, rax; hHeap
0x18000b07d  call    cs:__imp_HeapFree
0x18000b083  mov     [rsi+40h], r14
0x18000b087  mov     [rdi], rbp
0x18000b08a  lea     r14, [rsi+38h]
0x18000b08e  mov     rcx, [rsi+40h]; Destination
0x18000b092  test    rcx, rcx
0x18000b095  jz      short loc_18000B0E5
0x18000b097  mov     rbx, [rdi]
0x18000b09a  lea     r9, [rsi+10h]
0x18000b09e  mov     r8, [r15+38h]
0x18000b0a2  add     rbx, rcx
0x18000b0a5  mov     rdx, rbx
0x18000b0a8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b0ad  mov     r8, [r15+80h]
0x18000b0b4  lea     r9, [rsi+20h]
0x18000b0b8  mov     rdx, rbx
0x18000b0bb  mov     rcx, rax; Destination
0x18000b0be  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b0c3  mov     r8, [r15+18h]
0x18000b0c7  mov     r9, r14
0x18000b0ca  mov     rdx, rbx
0x18000b0cd  mov     rcx, rax; Destination
0x18000b0d0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000b0d5  sub     rbx, rax
0x18000b0d8  xor     edx, edx; Val
0x18000b0da  mov     r8, rbx; Size
0x18000b0dd  mov     rcx, rax; void *
0x18000b0e0  call    memset_0
0x18000b0e5  add     rsp, 28h
0x18000b0e9  pop     r15
0x18000b0eb  pop     r14
0x18000b0ed  pop     r13
0x18000b0ef  pop     r12
0x18000b0f1  pop     rdi
0x18000b0f2  pop     rsi
0x18000b0f3  pop     rbp
0x18000b0f4  pop     rbx
0x18000b0f5  retn
```
