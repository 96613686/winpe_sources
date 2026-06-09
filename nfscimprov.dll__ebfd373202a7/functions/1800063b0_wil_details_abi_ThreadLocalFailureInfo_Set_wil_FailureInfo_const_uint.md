# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800063b0`
- end: `0x1800064e6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006838`

## callees

- `0x180002cc8`
- `0x180002d40`
- `0x180005548`
- `0x180006228`
- `0x180006248`
- `0x1800063b0`
- `0x180035b02`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000646d`
- `KERNEL32!HeapFree` at `0x18000646d`
- `KERNEL32!GetProcessHeap` at `0x18000645f`
- `KERNEL32!GetProcessHeap` at `0x18000645f`

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
0x1800063b0  push    rbx
0x1800063b2  push    rbp
0x1800063b3  push    rsi
0x1800063b4  push    rdi
0x1800063b5  push    r12
0x1800063b7  push    r13
0x1800063b9  push    r14
0x1800063bb  push    r15
0x1800063bd  sub     rsp, 28h
0x1800063c1  mov     [rcx+4], r8d
0x1800063c5  lea     r14, [rcx+38h]
0x1800063c9  mov     eax, [rdx+8]
0x1800063cc  mov     rsi, rcx
0x1800063cf  mov     [rcx+8], eax
0x1800063d2  mov     r15, rdx
0x1800063d5  mov     qword ptr [rcx+10h], 0
0x1800063dd  movzx   eax, word ptr [rdx+40h]
0x1800063e1  mov     [rcx+18h], ax
0x1800063e5  mov     al, [rdx]
0x1800063e7  mov     [rcx+1Ah], al
0x1800063ea  mov     qword ptr [rcx+20h], 0
0x1800063f2  mov     rax, [rdx+88h]
0x1800063f9  mov     [rcx+28h], rax
0x1800063fd  mov     rax, [rdx+90h]
0x180006404  mov     [rcx+30h], rax
0x180006408  mov     qword ptr [r14], 0
0x18000640f  mov     rcx, [rdx+18h]; this
0x180006413  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006418  mov     rcx, [r15+38h]; this
0x18000641c  mov     rbp, rax
0x18000641f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006424  mov     rcx, [r15+80h]; this
0x18000642b  add     rbp, rax
0x18000642e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006433  add     rbp, rax
0x180006436  lea     rdi, [rsi+48h]
0x18000643a  cmp     qword ptr [rsi+40h], 0
0x18000643f  jz      short loc_180006446
0x180006441  cmp     [rdi], rbp
0x180006444  jnb     short loc_18000647E
0x180006446  mov     rdx, rbp; dwBytes
0x180006449  mov     ecx, 8; dwFlags
0x18000644e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006453  mov     r14, rax
0x180006456  test    rax, rax
0x180006459  jz      short loc_18000647A
0x18000645b  mov     rbx, [rsi+40h]
0x18000645f  call    cs:__imp_GetProcessHeap
0x180006465  mov     r8, rbx; lpMem
0x180006468  xor     edx, edx; dwFlags
0x18000646a  mov     rcx, rax; hHeap
0x18000646d  call    cs:__imp_HeapFree
0x180006473  mov     [rsi+40h], r14
0x180006477  mov     [rdi], rbp
0x18000647a  lea     r14, [rsi+38h]
0x18000647e  mov     rcx, [rsi+40h]; Destination
0x180006482  test    rcx, rcx
0x180006485  jz      short loc_1800064D5
0x180006487  mov     rbx, [rdi]
0x18000648a  lea     r9, [rsi+10h]
0x18000648e  mov     r8, [r15+38h]
0x180006492  add     rbx, rcx
0x180006495  mov     rdx, rbx
0x180006498  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000649d  mov     r8, [r15+80h]
0x1800064a4  lea     r9, [rsi+20h]
0x1800064a8  mov     rdx, rbx
0x1800064ab  mov     rcx, rax; Destination
0x1800064ae  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800064b3  mov     r8, [r15+18h]
0x1800064b7  mov     r9, r14
0x1800064ba  mov     rdx, rbx
0x1800064bd  mov     rcx, rax; Destination
0x1800064c0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800064c5  sub     rbx, rax
0x1800064c8  xor     edx, edx; Val
0x1800064ca  mov     r8, rbx; Size
0x1800064cd  mov     rcx, rax; void *
0x1800064d0  call    memset_0
0x1800064d5  add     rsp, 28h
0x1800064d9  pop     r15
0x1800064db  pop     r14
0x1800064dd  pop     r13
0x1800064df  pop     r12
0x1800064e1  pop     rdi
0x1800064e2  pop     rsi
0x1800064e3  pop     rbp
0x1800064e4  pop     rbx
0x1800064e5  retn
```
