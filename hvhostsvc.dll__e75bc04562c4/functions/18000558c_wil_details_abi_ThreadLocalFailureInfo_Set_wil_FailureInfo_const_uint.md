# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000558c`
- end: `0x1800056c2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005924`

## callees

- `0x180002b0c`
- `0x180003538`
- `0x1800035b0`
- `0x180005108`
- `0x1800054a8`
- `0x1800054c8`
- `0x18000558c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005649`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000563b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000563b`

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
0x18000558c  push    rbx
0x18000558e  push    rbp
0x18000558f  push    rsi
0x180005590  push    rdi
0x180005591  push    r12
0x180005593  push    r13
0x180005595  push    r14
0x180005597  push    r15
0x180005599  sub     rsp, 28h
0x18000559d  mov     [rcx+4], r8d
0x1800055a1  lea     r14, [rcx+38h]
0x1800055a5  mov     eax, [rdx+8]
0x1800055a8  mov     rsi, rcx
0x1800055ab  mov     [rcx+8], eax
0x1800055ae  mov     r15, rdx
0x1800055b1  mov     qword ptr [rcx+10h], 0
0x1800055b9  movzx   eax, word ptr [rdx+40h]
0x1800055bd  mov     [rcx+18h], ax
0x1800055c1  mov     al, [rdx]
0x1800055c3  mov     [rcx+1Ah], al
0x1800055c6  mov     qword ptr [rcx+20h], 0
0x1800055ce  mov     rax, [rdx+88h]
0x1800055d5  mov     [rcx+28h], rax
0x1800055d9  mov     rax, [rdx+90h]
0x1800055e0  mov     [rcx+30h], rax
0x1800055e4  mov     qword ptr [r14], 0
0x1800055eb  mov     rcx, [rdx+18h]; this
0x1800055ef  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800055f4  mov     rcx, [r15+38h]; this
0x1800055f8  mov     rbp, rax
0x1800055fb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005600  mov     rcx, [r15+80h]; this
0x180005607  add     rbp, rax
0x18000560a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000560f  add     rbp, rax
0x180005612  lea     rdi, [rsi+48h]
0x180005616  cmp     qword ptr [rsi+40h], 0
0x18000561b  jz      short loc_180005622
0x18000561d  cmp     [rdi], rbp
0x180005620  jnb     short loc_18000565A
0x180005622  mov     rdx, rbp; dwBytes
0x180005625  mov     ecx, 8; dwFlags
0x18000562a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000562f  mov     r14, rax
0x180005632  test    rax, rax
0x180005635  jz      short loc_180005656
0x180005637  mov     rbx, [rsi+40h]
0x18000563b  call    cs:__imp_GetProcessHeap
0x180005641  mov     r8, rbx; lpMem
0x180005644  xor     edx, edx; dwFlags
0x180005646  mov     rcx, rax; hHeap
0x180005649  call    cs:__imp_HeapFree
0x18000564f  mov     [rsi+40h], r14
0x180005653  mov     [rdi], rbp
0x180005656  lea     r14, [rsi+38h]
0x18000565a  mov     rcx, [rsi+40h]; Destination
0x18000565e  test    rcx, rcx
0x180005661  jz      short loc_1800056B1
0x180005663  mov     rbx, [rdi]
0x180005666  lea     r9, [rsi+10h]
0x18000566a  mov     r8, [r15+38h]
0x18000566e  add     rbx, rcx
0x180005671  mov     rdx, rbx
0x180005674  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005679  mov     r8, [r15+80h]
0x180005680  lea     r9, [rsi+20h]
0x180005684  mov     rdx, rbx
0x180005687  mov     rcx, rax; Destination
0x18000568a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000568f  mov     r8, [r15+18h]
0x180005693  mov     r9, r14
0x180005696  mov     rdx, rbx
0x180005699  mov     rcx, rax; Destination
0x18000569c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800056a1  sub     rbx, rax
0x1800056a4  xor     edx, edx; Val
0x1800056a6  mov     r8, rbx; Size
0x1800056a9  mov     rcx, rax; void *
0x1800056ac  call    memset_0
0x1800056b1  add     rsp, 28h
0x1800056b5  pop     r15
0x1800056b7  pop     r14
0x1800056b9  pop     r13
0x1800056bb  pop     r12
0x1800056bd  pop     rdi
0x1800056be  pop     rsi
0x1800056bf  pop     rbp
0x1800056c0  pop     rbx
0x1800056c1  retn
```
