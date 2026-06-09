# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000e370`
- end: `0x18000e4a6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e708`

## callees

- `0x18000aef8`
- `0x18000c30c`
- `0x18000c384`
- `0x18000dc6c`
- `0x18000e288`
- `0x18000e2a8`
- `0x18000e370`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e42d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e42d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e41f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e41f`

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
0x18000e370  push    rbx
0x18000e372  push    rbp
0x18000e373  push    rsi
0x18000e374  push    rdi
0x18000e375  push    r12
0x18000e377  push    r13
0x18000e379  push    r14
0x18000e37b  push    r15
0x18000e37d  sub     rsp, 28h
0x18000e381  mov     [rcx+4], r8d
0x18000e385  lea     r14, [rcx+38h]
0x18000e389  mov     eax, [rdx+8]
0x18000e38c  mov     rsi, rcx
0x18000e38f  mov     [rcx+8], eax
0x18000e392  mov     r15, rdx
0x18000e395  mov     qword ptr [rcx+10h], 0
0x18000e39d  movzx   eax, word ptr [rdx+40h]
0x18000e3a1  mov     [rcx+18h], ax
0x18000e3a5  mov     al, [rdx]
0x18000e3a7  mov     [rcx+1Ah], al
0x18000e3aa  mov     qword ptr [rcx+20h], 0
0x18000e3b2  mov     rax, [rdx+88h]
0x18000e3b9  mov     [rcx+28h], rax
0x18000e3bd  mov     rax, [rdx+90h]
0x18000e3c4  mov     [rcx+30h], rax
0x18000e3c8  mov     qword ptr [r14], 0
0x18000e3cf  mov     rcx, [rdx+18h]; this
0x18000e3d3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000e3d8  mov     rcx, [r15+38h]; this
0x18000e3dc  mov     rbp, rax
0x18000e3df  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000e3e4  mov     rcx, [r15+80h]; this
0x18000e3eb  add     rbp, rax
0x18000e3ee  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000e3f3  add     rbp, rax
0x18000e3f6  lea     rdi, [rsi+48h]
0x18000e3fa  cmp     qword ptr [rsi+40h], 0
0x18000e3ff  jz      short loc_18000E406
0x18000e401  cmp     [rdi], rbp
0x18000e404  jnb     short loc_18000E43E
0x18000e406  mov     rdx, rbp; dwBytes
0x18000e409  mov     ecx, 8; dwFlags
0x18000e40e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e413  mov     r14, rax
0x18000e416  test    rax, rax
0x18000e419  jz      short loc_18000E43A
0x18000e41b  mov     rbx, [rsi+40h]
0x18000e41f  call    cs:__imp_GetProcessHeap
0x18000e425  mov     r8, rbx; lpMem
0x18000e428  xor     edx, edx; dwFlags
0x18000e42a  mov     rcx, rax; hHeap
0x18000e42d  call    cs:__imp_HeapFree
0x18000e433  mov     [rsi+40h], r14
0x18000e437  mov     [rdi], rbp
0x18000e43a  lea     r14, [rsi+38h]
0x18000e43e  mov     rcx, [rsi+40h]; Destination
0x18000e442  test    rcx, rcx
0x18000e445  jz      short loc_18000E495
0x18000e447  mov     rbx, [rdi]
0x18000e44a  lea     r9, [rsi+10h]
0x18000e44e  mov     r8, [r15+38h]
0x18000e452  add     rbx, rcx
0x18000e455  mov     rdx, rbx
0x18000e458  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000e45d  mov     r8, [r15+80h]
0x18000e464  lea     r9, [rsi+20h]
0x18000e468  mov     rdx, rbx
0x18000e46b  mov     rcx, rax; Destination
0x18000e46e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000e473  mov     r8, [r15+18h]
0x18000e477  mov     r9, r14
0x18000e47a  mov     rdx, rbx
0x18000e47d  mov     rcx, rax; Destination
0x18000e480  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000e485  sub     rbx, rax
0x18000e488  xor     edx, edx; Val
0x18000e48a  mov     r8, rbx; Size
0x18000e48d  mov     rcx, rax; void *
0x18000e490  call    memset_0
0x18000e495  add     rsp, 28h
0x18000e499  pop     r15
0x18000e49b  pop     r14
0x18000e49d  pop     r13
0x18000e49f  pop     r12
0x18000e4a1  pop     rdi
0x18000e4a2  pop     rsi
0x18000e4a3  pop     rbp
0x18000e4a4  pop     rbx
0x18000e4a5  retn
```
