# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800087fc`
- end: `0x180008932`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008b94`

## callees

- `0x1800028e8`
- `0x180006a0c`
- `0x180006a84`
- `0x180008378`
- `0x180008718`
- `0x180008738`
- `0x1800087fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088ab`

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
0x1800087fc  push    rbx
0x1800087fe  push    rbp
0x1800087ff  push    rsi
0x180008800  push    rdi
0x180008801  push    r12
0x180008803  push    r13
0x180008805  push    r14
0x180008807  push    r15
0x180008809  sub     rsp, 28h
0x18000880d  mov     [rcx+4], r8d
0x180008811  lea     r14, [rcx+38h]
0x180008815  mov     eax, [rdx+8]
0x180008818  mov     rsi, rcx
0x18000881b  mov     [rcx+8], eax
0x18000881e  mov     r15, rdx
0x180008821  mov     qword ptr [rcx+10h], 0
0x180008829  movzx   eax, word ptr [rdx+40h]
0x18000882d  mov     [rcx+18h], ax
0x180008831  mov     al, [rdx]
0x180008833  mov     [rcx+1Ah], al
0x180008836  mov     qword ptr [rcx+20h], 0
0x18000883e  mov     rax, [rdx+88h]
0x180008845  mov     [rcx+28h], rax
0x180008849  mov     rax, [rdx+90h]
0x180008850  mov     [rcx+30h], rax
0x180008854  mov     qword ptr [r14], 0
0x18000885b  mov     rcx, [rdx+18h]; this
0x18000885f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180008864  mov     rcx, [r15+38h]; this
0x180008868  mov     rbp, rax
0x18000886b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008870  mov     rcx, [r15+80h]; this
0x180008877  add     rbp, rax
0x18000887a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000887f  add     rbp, rax
0x180008882  lea     rdi, [rsi+48h]
0x180008886  cmp     qword ptr [rsi+40h], 0
0x18000888b  jz      short loc_180008892
0x18000888d  cmp     [rdi], rbp
0x180008890  jnb     short loc_1800088CA
0x180008892  mov     rdx, rbp; dwBytes
0x180008895  mov     ecx, 8; dwFlags
0x18000889a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000889f  mov     r14, rax
0x1800088a2  test    rax, rax
0x1800088a5  jz      short loc_1800088C6
0x1800088a7  mov     rbx, [rsi+40h]
0x1800088ab  call    cs:__imp_GetProcessHeap
0x1800088b1  mov     r8, rbx; lpMem
0x1800088b4  xor     edx, edx; dwFlags
0x1800088b6  mov     rcx, rax; hHeap
0x1800088b9  call    cs:__imp_HeapFree
0x1800088bf  mov     [rsi+40h], r14
0x1800088c3  mov     [rdi], rbp
0x1800088c6  lea     r14, [rsi+38h]
0x1800088ca  mov     rcx, [rsi+40h]; Destination
0x1800088ce  test    rcx, rcx
0x1800088d1  jz      short loc_180008921
0x1800088d3  mov     rbx, [rdi]
0x1800088d6  lea     r9, [rsi+10h]
0x1800088da  mov     r8, [r15+38h]
0x1800088de  add     rbx, rcx
0x1800088e1  mov     rdx, rbx
0x1800088e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800088e9  mov     r8, [r15+80h]
0x1800088f0  lea     r9, [rsi+20h]
0x1800088f4  mov     rdx, rbx
0x1800088f7  mov     rcx, rax; Destination
0x1800088fa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800088ff  mov     r8, [r15+18h]
0x180008903  mov     r9, r14
0x180008906  mov     rdx, rbx
0x180008909  mov     rcx, rax; Destination
0x18000890c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180008911  sub     rbx, rax
0x180008914  xor     edx, edx; Val
0x180008916  mov     r8, rbx; Size
0x180008919  mov     rcx, rax; void *
0x18000891c  call    memset_0
0x180008921  add     rsp, 28h
0x180008925  pop     r15
0x180008927  pop     r14
0x180008929  pop     r13
0x18000892b  pop     r12
0x18000892d  pop     rdi
0x18000892e  pop     rsi
0x18000892f  pop     rbp
0x180008930  pop     rbx
0x180008931  retn
```
