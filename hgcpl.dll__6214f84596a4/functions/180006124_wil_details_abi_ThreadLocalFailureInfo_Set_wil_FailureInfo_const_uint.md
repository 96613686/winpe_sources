# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006124`
- end: `0x18000625a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006260`

## callees

- `0x180004640`
- `0x1800046b8`
- `0x180005e98`
- `0x180006008`
- `0x180006028`
- `0x180006124`
- `0x180018a52`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061d3`

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
0x180006124  push    rbx
0x180006126  push    rbp
0x180006127  push    rsi
0x180006128  push    rdi
0x180006129  push    r12
0x18000612b  push    r13
0x18000612d  push    r14
0x18000612f  push    r15
0x180006131  sub     rsp, 28h
0x180006135  mov     [rcx+4], r8d
0x180006139  lea     r14, [rcx+38h]
0x18000613d  mov     eax, [rdx+8]
0x180006140  mov     rsi, rcx
0x180006143  mov     [rcx+8], eax
0x180006146  mov     r15, rdx
0x180006149  mov     qword ptr [rcx+10h], 0
0x180006151  movzx   eax, word ptr [rdx+40h]
0x180006155  mov     [rcx+18h], ax
0x180006159  mov     al, [rdx]
0x18000615b  mov     [rcx+1Ah], al
0x18000615e  mov     qword ptr [rcx+20h], 0
0x180006166  mov     rax, [rdx+88h]
0x18000616d  mov     [rcx+28h], rax
0x180006171  mov     rax, [rdx+90h]
0x180006178  mov     [rcx+30h], rax
0x18000617c  mov     qword ptr [r14], 0
0x180006183  mov     rcx, [rdx+18h]; this
0x180006187  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000618c  mov     rcx, [r15+38h]; this
0x180006190  mov     rbp, rax
0x180006193  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006198  mov     rcx, [r15+80h]; this
0x18000619f  add     rbp, rax
0x1800061a2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800061a7  add     rbp, rax
0x1800061aa  lea     rdi, [rsi+48h]
0x1800061ae  cmp     qword ptr [rsi+40h], 0
0x1800061b3  jz      short loc_1800061BA
0x1800061b5  cmp     [rdi], rbp
0x1800061b8  jnb     short loc_1800061F2
0x1800061ba  mov     rdx, rbp; dwBytes
0x1800061bd  mov     ecx, 8; dwFlags
0x1800061c2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800061c7  mov     r14, rax
0x1800061ca  test    rax, rax
0x1800061cd  jz      short loc_1800061EE
0x1800061cf  mov     rbx, [rsi+40h]
0x1800061d3  call    cs:__imp_GetProcessHeap
0x1800061d9  mov     r8, rbx; lpMem
0x1800061dc  xor     edx, edx; dwFlags
0x1800061de  mov     rcx, rax; hHeap
0x1800061e1  call    cs:__imp_HeapFree
0x1800061e7  mov     [rsi+40h], r14
0x1800061eb  mov     [rdi], rbp
0x1800061ee  lea     r14, [rsi+38h]
0x1800061f2  mov     rcx, [rsi+40h]; Destination
0x1800061f6  test    rcx, rcx
0x1800061f9  jz      short loc_180006249
0x1800061fb  mov     rbx, [rdi]
0x1800061fe  lea     r9, [rsi+10h]
0x180006202  mov     r8, [r15+38h]
0x180006206  add     rbx, rcx
0x180006209  mov     rdx, rbx
0x18000620c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006211  mov     r8, [r15+80h]
0x180006218  lea     r9, [rsi+20h]
0x18000621c  mov     rdx, rbx
0x18000621f  mov     rcx, rax; Destination
0x180006222  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006227  mov     r8, [r15+18h]
0x18000622b  mov     r9, r14
0x18000622e  mov     rdx, rbx
0x180006231  mov     rcx, rax; Destination
0x180006234  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006239  sub     rbx, rax
0x18000623c  xor     edx, edx; Val
0x18000623e  mov     r8, rbx; Size
0x180006241  mov     rcx, rax; void *
0x180006244  call    memset_0
0x180006249  add     rsp, 28h
0x18000624d  pop     r15
0x18000624f  pop     r14
0x180006251  pop     r13
0x180006253  pop     r12
0x180006255  pop     rdi
0x180006256  pop     rsi
0x180006257  pop     rbp
0x180006258  pop     rbx
0x180006259  retn
```
