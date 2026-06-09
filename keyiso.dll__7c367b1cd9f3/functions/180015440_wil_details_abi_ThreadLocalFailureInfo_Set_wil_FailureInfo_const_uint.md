# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180015440`
- end: `0x180015576`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800158c4`

## callees

- `0x18000d0ac`
- `0x180011e88`
- `0x180011f00`
- `0x180014754`
- `0x1800152b8`
- `0x1800152d8`
- `0x180015440`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800154ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800154ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800154fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800154fd`

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
0x180015440  push    rbx
0x180015442  push    rbp
0x180015443  push    rsi
0x180015444  push    rdi
0x180015445  push    r12
0x180015447  push    r13
0x180015449  push    r14
0x18001544b  push    r15
0x18001544d  sub     rsp, 28h
0x180015451  mov     [rcx+4], r8d
0x180015455  lea     r14, [rcx+38h]
0x180015459  mov     eax, [rdx+8]
0x18001545c  mov     rsi, rcx
0x18001545f  mov     [rcx+8], eax
0x180015462  mov     r15, rdx
0x180015465  mov     qword ptr [rcx+10h], 0
0x18001546d  movzx   eax, word ptr [rdx+40h]
0x180015471  mov     [rcx+18h], ax
0x180015475  mov     al, [rdx]
0x180015477  mov     [rcx+1Ah], al
0x18001547a  mov     qword ptr [rcx+20h], 0
0x180015482  mov     rax, [rdx+88h]
0x180015489  mov     [rcx+28h], rax
0x18001548d  mov     rax, [rdx+90h]
0x180015494  mov     [rcx+30h], rax
0x180015498  mov     qword ptr [r14], 0
0x18001549f  mov     rcx, [rdx+18h]; this
0x1800154a3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800154a8  mov     rcx, [r15+38h]; this
0x1800154ac  mov     rbp, rax
0x1800154af  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800154b4  mov     rcx, [r15+80h]; this
0x1800154bb  add     rbp, rax
0x1800154be  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800154c3  add     rbp, rax
0x1800154c6  lea     rdi, [rsi+48h]
0x1800154ca  cmp     qword ptr [rsi+40h], 0
0x1800154cf  jz      short loc_1800154D6
0x1800154d1  cmp     [rdi], rbp
0x1800154d4  jnb     short loc_18001550E
0x1800154d6  mov     rdx, rbp; dwBytes
0x1800154d9  mov     ecx, 8; dwFlags
0x1800154de  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800154e3  mov     r14, rax
0x1800154e6  test    rax, rax
0x1800154e9  jz      short loc_18001550A
0x1800154eb  mov     rbx, [rsi+40h]
0x1800154ef  call    cs:__imp_GetProcessHeap
0x1800154f5  mov     r8, rbx; lpMem
0x1800154f8  xor     edx, edx; dwFlags
0x1800154fa  mov     rcx, rax; hHeap
0x1800154fd  call    cs:__imp_HeapFree
0x180015503  mov     [rsi+40h], r14
0x180015507  mov     [rdi], rbp
0x18001550a  lea     r14, [rsi+38h]
0x18001550e  mov     rcx, [rsi+40h]; Destination
0x180015512  test    rcx, rcx
0x180015515  jz      short loc_180015565
0x180015517  mov     rbx, [rdi]
0x18001551a  lea     r9, [rsi+10h]
0x18001551e  mov     r8, [r15+38h]
0x180015522  add     rbx, rcx
0x180015525  mov     rdx, rbx
0x180015528  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001552d  mov     r8, [r15+80h]
0x180015534  lea     r9, [rsi+20h]
0x180015538  mov     rdx, rbx
0x18001553b  mov     rcx, rax; Destination
0x18001553e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180015543  mov     r8, [r15+18h]
0x180015547  mov     r9, r14
0x18001554a  mov     rdx, rbx
0x18001554d  mov     rcx, rax; Destination
0x180015550  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180015555  sub     rbx, rax
0x180015558  xor     edx, edx; Val
0x18001555a  mov     r8, rbx; Size
0x18001555d  mov     rcx, rax; void *
0x180015560  call    memset_0
0x180015565  add     rsp, 28h
0x180015569  pop     r15
0x18001556b  pop     r14
0x18001556d  pop     r13
0x18001556f  pop     r12
0x180015571  pop     rdi
0x180015572  pop     rsi
0x180015573  pop     rbp
0x180015574  pop     rbx
0x180015575  retn
```
