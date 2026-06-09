# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001a8f4`
- end: `0x18001aa37`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006268`

## callees

- `0x18000c9d8`
- `0x18000f78c`
- `0x18000f988`
- `0x1800130dc`
- `0x18001a7b8`
- `0x18001a8f4`
- `0x1800227f2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a9a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a9a3`

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
0x18001a8f4  push    rbx
0x18001a8f6  push    rbp
0x18001a8f7  push    rsi
0x18001a8f8  push    rdi
0x18001a8f9  push    r12
0x18001a8fb  push    r13
0x18001a8fd  push    r14
0x18001a8ff  push    r15
0x18001a901  sub     rsp, 28h
0x18001a905  mov     [rcx+4], r8d
0x18001a909  lea     r14, [rcx+38h]
0x18001a90d  mov     eax, [rdx+8]
0x18001a910  mov     rsi, rcx
0x18001a913  mov     [rcx+8], eax
0x18001a916  mov     r15, rdx
0x18001a919  mov     qword ptr [rcx+10h], 0
0x18001a921  movzx   eax, word ptr [rdx+40h]
0x18001a925  mov     [rcx+18h], ax
0x18001a929  mov     al, [rdx]
0x18001a92b  mov     [rcx+1Ah], al
0x18001a92e  mov     qword ptr [rcx+20h], 0
0x18001a936  mov     rax, [rdx+88h]
0x18001a93d  mov     [rcx+28h], rax
0x18001a941  mov     rax, [rdx+90h]
0x18001a948  mov     [rcx+30h], rax
0x18001a94c  mov     qword ptr [r14], 0
0x18001a953  mov     rcx, [rdx+18h]; this
0x18001a957  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001a95c  mov     rcx, [r15+38h]; this
0x18001a960  mov     rbp, rax
0x18001a963  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001a968  mov     rcx, [r15+80h]; this
0x18001a96f  add     rbp, rax
0x18001a972  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001a977  add     rbp, rax
0x18001a97a  lea     rdi, [rsi+48h]
0x18001a97e  cmp     qword ptr [rsi+40h], 0
0x18001a983  jz      short loc_18001A98A
0x18001a985  cmp     [rdi], rbp
0x18001a988  jnb     short loc_18001A9CE
0x18001a98a  mov     rdx, rbp; dwBytes
0x18001a98d  mov     ecx, 8; dwFlags
0x18001a992  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001a997  mov     r14, rax
0x18001a99a  test    rax, rax
0x18001a99d  jz      short loc_18001A9CA
0x18001a99f  mov     rbx, [rsi+40h]
0x18001a9a3  call    cs:__imp_GetProcessHeap
0x18001a9aa  nop     dword ptr [rax+rax+00h]
0x18001a9af  mov     r8, rbx; lpMem
0x18001a9b2  xor     edx, edx; dwFlags
0x18001a9b4  mov     rcx, rax; hHeap
0x18001a9b7  call    cs:__imp_HeapFree
0x18001a9be  nop     dword ptr [rax+rax+00h]
0x18001a9c3  mov     [rsi+40h], r14
0x18001a9c7  mov     [rdi], rbp
0x18001a9ca  lea     r14, [rsi+38h]
0x18001a9ce  mov     rcx, [rsi+40h]; Destination
0x18001a9d2  test    rcx, rcx
0x18001a9d5  jz      short loc_18001AA25
0x18001a9d7  mov     rbx, [rdi]
0x18001a9da  lea     r9, [rsi+10h]
0x18001a9de  mov     r8, [r15+38h]
0x18001a9e2  add     rbx, rcx
0x18001a9e5  mov     rdx, rbx
0x18001a9e8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001a9ed  mov     r8, [r15+80h]
0x18001a9f4  lea     r9, [rsi+20h]
0x18001a9f8  mov     rdx, rbx
0x18001a9fb  mov     rcx, rax; Destination
0x18001a9fe  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001aa03  mov     r8, [r15+18h]
0x18001aa07  mov     r9, r14
0x18001aa0a  mov     rdx, rbx
0x18001aa0d  mov     rcx, rax; Destination
0x18001aa10  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18001aa15  sub     rbx, rax
0x18001aa18  xor     edx, edx; Val
0x18001aa1a  mov     r8, rbx; Size
0x18001aa1d  mov     rcx, rax; void *
0x18001aa20  call    memset_0
0x18001aa25  add     rsp, 28h
0x18001aa29  pop     r15
0x18001aa2b  pop     r14
0x18001aa2d  pop     r13
0x18001aa2f  pop     r12
0x18001aa31  pop     rdi
0x18001aa32  pop     rsi
0x18001aa33  pop     rbp
0x18001aa34  pop     rbx
0x18001aa35  retn
```
