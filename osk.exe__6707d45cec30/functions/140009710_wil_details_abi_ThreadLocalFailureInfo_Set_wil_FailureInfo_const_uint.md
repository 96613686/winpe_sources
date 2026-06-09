# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140009710`
- end: `0x140009846`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140009bc8`

## callees

- `0x140002de3`
- `0x140004028`
- `0x1400040a0`
- `0x140008894`
- `0x140009580`
- `0x1400095a0`
- `0x140009710`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400097bf`
- `KERNEL32!GetProcessHeap` at `0x1400097bf`
- `KERNEL32!HeapFree` at `0x1400097cd`
- `KERNEL32!HeapFree` at `0x1400097cd`

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
0x140009710  push    rbx
0x140009712  push    rbp
0x140009713  push    rsi
0x140009714  push    rdi
0x140009715  push    r12
0x140009717  push    r13
0x140009719  push    r14
0x14000971b  push    r15
0x14000971d  sub     rsp, 28h
0x140009721  mov     [rcx+4], r8d
0x140009725  lea     r14, [rcx+38h]
0x140009729  mov     eax, [rdx+8]
0x14000972c  mov     rsi, rcx
0x14000972f  mov     [rcx+8], eax
0x140009732  mov     r15, rdx
0x140009735  mov     qword ptr [rcx+10h], 0
0x14000973d  movzx   eax, word ptr [rdx+40h]
0x140009741  mov     [rcx+18h], ax
0x140009745  mov     al, [rdx]
0x140009747  mov     [rcx+1Ah], al
0x14000974a  mov     qword ptr [rcx+20h], 0
0x140009752  mov     rax, [rdx+88h]
0x140009759  mov     [rcx+28h], rax
0x14000975d  mov     rax, [rdx+90h]
0x140009764  mov     [rcx+30h], rax
0x140009768  mov     qword ptr [r14], 0
0x14000976f  mov     rcx, [rdx+18h]; this
0x140009773  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140009778  mov     rcx, [r15+38h]; this
0x14000977c  mov     rbp, rax
0x14000977f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140009784  mov     rcx, [r15+80h]; this
0x14000978b  add     rbp, rax
0x14000978e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140009793  add     rbp, rax
0x140009796  lea     rdi, [rsi+48h]
0x14000979a  cmp     qword ptr [rsi+40h], 0
0x14000979f  jz      short loc_1400097A6
0x1400097a1  cmp     [rdi], rbp
0x1400097a4  jnb     short loc_1400097DE
0x1400097a6  mov     rdx, rbp; dwBytes
0x1400097a9  mov     ecx, 8; dwFlags
0x1400097ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400097b3  mov     r14, rax
0x1400097b6  test    rax, rax
0x1400097b9  jz      short loc_1400097DA
0x1400097bb  mov     rbx, [rsi+40h]
0x1400097bf  call    cs:__imp_GetProcessHeap
0x1400097c5  mov     r8, rbx; lpMem
0x1400097c8  xor     edx, edx; dwFlags
0x1400097ca  mov     rcx, rax; hHeap
0x1400097cd  call    cs:__imp_HeapFree
0x1400097d3  mov     [rsi+40h], r14
0x1400097d7  mov     [rdi], rbp
0x1400097da  lea     r14, [rsi+38h]
0x1400097de  mov     rcx, [rsi+40h]; Destination
0x1400097e2  test    rcx, rcx
0x1400097e5  jz      short loc_140009835
0x1400097e7  mov     rbx, [rdi]
0x1400097ea  lea     r9, [rsi+10h]
0x1400097ee  mov     r8, [r15+38h]
0x1400097f2  add     rbx, rcx
0x1400097f5  mov     rdx, rbx
0x1400097f8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400097fd  mov     r8, [r15+80h]
0x140009804  lea     r9, [rsi+20h]
0x140009808  mov     rdx, rbx
0x14000980b  mov     rcx, rax; Destination
0x14000980e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140009813  mov     r8, [r15+18h]
0x140009817  mov     r9, r14
0x14000981a  mov     rdx, rbx
0x14000981d  mov     rcx, rax; Destination
0x140009820  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140009825  sub     rbx, rax
0x140009828  xor     edx, edx; Val
0x14000982a  mov     r8, rbx; Size
0x14000982d  mov     rcx, rax; void *
0x140009830  call    memset_0
0x140009835  add     rsp, 28h
0x140009839  pop     r15
0x14000983b  pop     r14
0x14000983d  pop     r13
0x14000983f  pop     r12
0x140009841  pop     rdi
0x140009842  pop     rsi
0x140009843  pop     rbp
0x140009844  pop     rbx
0x140009845  retn
```
