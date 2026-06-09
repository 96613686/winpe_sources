# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b300`
- end: `0x18000b436`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b784`

## callees

- `0x180002774`
- `0x180003fd0`
- `0x180004048`
- `0x18000a2f0`
- `0x18000b09c`
- `0x18000b0bc`
- `0x18000b300`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000b3bd`
- `KERNEL32!HeapFree` at `0x18000b3bd`
- `KERNEL32!GetProcessHeap` at `0x18000b3af`
- `KERNEL32!GetProcessHeap` at `0x18000b3af`

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
0x18000b300  push    rbx
0x18000b302  push    rbp
0x18000b303  push    rsi
0x18000b304  push    rdi
0x18000b305  push    r12
0x18000b307  push    r13
0x18000b309  push    r14
0x18000b30b  push    r15
0x18000b30d  sub     rsp, 28h
0x18000b311  mov     [rcx+4], r8d
0x18000b315  lea     r14, [rcx+38h]
0x18000b319  mov     eax, [rdx+8]
0x18000b31c  mov     rsi, rcx
0x18000b31f  mov     [rcx+8], eax
0x18000b322  mov     r15, rdx
0x18000b325  mov     qword ptr [rcx+10h], 0
0x18000b32d  movzx   eax, word ptr [rdx+40h]
0x18000b331  mov     [rcx+18h], ax
0x18000b335  mov     al, [rdx]
0x18000b337  mov     [rcx+1Ah], al
0x18000b33a  mov     qword ptr [rcx+20h], 0
0x18000b342  mov     rax, [rdx+88h]
0x18000b349  mov     [rcx+28h], rax
0x18000b34d  mov     rax, [rdx+90h]
0x18000b354  mov     [rcx+30h], rax
0x18000b358  mov     qword ptr [r14], 0
0x18000b35f  mov     rcx, [rdx+18h]; this
0x18000b363  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b368  mov     rcx, [r15+38h]; this
0x18000b36c  mov     rbp, rax
0x18000b36f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b374  mov     rcx, [r15+80h]; this
0x18000b37b  add     rbp, rax
0x18000b37e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b383  add     rbp, rax
0x18000b386  lea     rdi, [rsi+48h]
0x18000b38a  cmp     qword ptr [rsi+40h], 0
0x18000b38f  jz      short loc_18000B396
0x18000b391  cmp     [rdi], rbp
0x18000b394  jnb     short loc_18000B3CE
0x18000b396  mov     rdx, rbp; dwBytes
0x18000b399  mov     ecx, 8; dwFlags
0x18000b39e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b3a3  mov     r14, rax
0x18000b3a6  test    rax, rax
0x18000b3a9  jz      short loc_18000B3CA
0x18000b3ab  mov     rbx, [rsi+40h]
0x18000b3af  call    cs:__imp_GetProcessHeap
0x18000b3b5  mov     r8, rbx; lpMem
0x18000b3b8  xor     edx, edx; dwFlags
0x18000b3ba  mov     rcx, rax; hHeap
0x18000b3bd  call    cs:__imp_HeapFree
0x18000b3c3  mov     [rsi+40h], r14
0x18000b3c7  mov     [rdi], rbp
0x18000b3ca  lea     r14, [rsi+38h]
0x18000b3ce  mov     rcx, [rsi+40h]; Destination
0x18000b3d2  test    rcx, rcx
0x18000b3d5  jz      short loc_18000B425
0x18000b3d7  mov     rbx, [rdi]
0x18000b3da  lea     r9, [rsi+10h]
0x18000b3de  mov     r8, [r15+38h]
0x18000b3e2  add     rbx, rcx
0x18000b3e5  mov     rdx, rbx
0x18000b3e8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b3ed  mov     r8, [r15+80h]
0x18000b3f4  lea     r9, [rsi+20h]
0x18000b3f8  mov     rdx, rbx
0x18000b3fb  mov     rcx, rax; Destination
0x18000b3fe  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b403  mov     r8, [r15+18h]
0x18000b407  mov     r9, r14
0x18000b40a  mov     rdx, rbx
0x18000b40d  mov     rcx, rax; Destination
0x18000b410  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000b415  sub     rbx, rax
0x18000b418  xor     edx, edx; Val
0x18000b41a  mov     r8, rbx; Size
0x18000b41d  mov     rcx, rax; void *
0x18000b420  call    memset_0
0x18000b425  add     rsp, 28h
0x18000b429  pop     r15
0x18000b42b  pop     r14
0x18000b42d  pop     r13
0x18000b42f  pop     r12
0x18000b431  pop     rdi
0x18000b432  pop     rsi
0x18000b433  pop     rbp
0x18000b434  pop     rbx
0x18000b435  retn
```
