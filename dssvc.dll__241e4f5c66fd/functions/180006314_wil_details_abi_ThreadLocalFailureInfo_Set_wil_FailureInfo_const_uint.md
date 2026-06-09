# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006314`
- end: `0x18000644a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006450`

## callees

- `0x180004094`
- `0x18000410c`
- `0x180005b7c`
- `0x180005fe4`
- `0x180006004`
- `0x180006314`
- `0x18001b30a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063d1`

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
0x180006314  push    rbx
0x180006316  push    rbp
0x180006317  push    rsi
0x180006318  push    rdi
0x180006319  push    r12
0x18000631b  push    r13
0x18000631d  push    r14
0x18000631f  push    r15
0x180006321  sub     rsp, 28h
0x180006325  mov     [rcx+4], r8d
0x180006329  lea     r14, [rcx+38h]
0x18000632d  mov     eax, [rdx+8]
0x180006330  mov     rsi, rcx
0x180006333  mov     [rcx+8], eax
0x180006336  mov     r15, rdx
0x180006339  mov     qword ptr [rcx+10h], 0
0x180006341  movzx   eax, word ptr [rdx+40h]
0x180006345  mov     [rcx+18h], ax
0x180006349  mov     al, [rdx]
0x18000634b  mov     [rcx+1Ah], al
0x18000634e  mov     qword ptr [rcx+20h], 0
0x180006356  mov     rax, [rdx+88h]
0x18000635d  mov     [rcx+28h], rax
0x180006361  mov     rax, [rdx+90h]
0x180006368  mov     [rcx+30h], rax
0x18000636c  mov     qword ptr [r14], 0
0x180006373  mov     rcx, [rdx+18h]; this
0x180006377  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000637c  mov     rcx, [r15+38h]; this
0x180006380  mov     rbp, rax
0x180006383  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006388  mov     rcx, [r15+80h]; this
0x18000638f  add     rbp, rax
0x180006392  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006397  add     rbp, rax
0x18000639a  lea     rdi, [rsi+48h]
0x18000639e  cmp     qword ptr [rsi+40h], 0
0x1800063a3  jz      short loc_1800063AA
0x1800063a5  cmp     [rdi], rbp
0x1800063a8  jnb     short loc_1800063E2
0x1800063aa  mov     rdx, rbp; dwBytes
0x1800063ad  mov     ecx, 8; dwFlags
0x1800063b2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800063b7  mov     r14, rax
0x1800063ba  test    rax, rax
0x1800063bd  jz      short loc_1800063DE
0x1800063bf  mov     rbx, [rsi+40h]
0x1800063c3  call    cs:__imp_GetProcessHeap
0x1800063c9  mov     r8, rbx; lpMem
0x1800063cc  xor     edx, edx; dwFlags
0x1800063ce  mov     rcx, rax; hHeap
0x1800063d1  call    cs:__imp_HeapFree
0x1800063d7  mov     [rsi+40h], r14
0x1800063db  mov     [rdi], rbp
0x1800063de  lea     r14, [rsi+38h]
0x1800063e2  mov     rcx, [rsi+40h]; Destination
0x1800063e6  test    rcx, rcx
0x1800063e9  jz      short loc_180006439
0x1800063eb  mov     rbx, [rdi]
0x1800063ee  lea     r9, [rsi+10h]
0x1800063f2  mov     r8, [r15+38h]
0x1800063f6  add     rbx, rcx
0x1800063f9  mov     rdx, rbx
0x1800063fc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006401  mov     r8, [r15+80h]
0x180006408  lea     r9, [rsi+20h]
0x18000640c  mov     rdx, rbx
0x18000640f  mov     rcx, rax; Destination
0x180006412  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006417  mov     r8, [r15+18h]
0x18000641b  mov     r9, r14
0x18000641e  mov     rdx, rbx
0x180006421  mov     rcx, rax; Destination
0x180006424  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006429  sub     rbx, rax
0x18000642c  xor     edx, edx; Val
0x18000642e  mov     r8, rbx; Size
0x180006431  mov     rcx, rax; void *
0x180006434  call    memset_0
0x180006439  add     rsp, 28h
0x18000643d  pop     r15
0x18000643f  pop     r14
0x180006441  pop     r13
0x180006443  pop     r12
0x180006445  pop     rdi
0x180006446  pop     rsi
0x180006447  pop     rbp
0x180006448  pop     rbx
0x180006449  retn
```
