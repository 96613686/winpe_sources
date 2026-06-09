# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800235f4`
- end: `0x180023765`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180023858`

## callees

- `0x180020b58`
- `0x180022b88`
- `0x1800234d0`
- `0x1800234f8`
- `0x1800235f4`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002369c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002369c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800236aa`
- `ntdll!memcpy_s` at `0x180023729`
- `ntdll!memcpy_s` at `0x180023729`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x1800235f4  push    rbx
0x1800235f6  push    rbp
0x1800235f7  push    rsi
0x1800235f8  push    rdi
0x1800235f9  push    r12
0x1800235fb  push    r13
0x1800235fd  push    r14
0x1800235ff  push    r15
0x180023601  sub     rsp, 28h
0x180023605  mov     [rcx+4], r8d
0x180023609  lea     rbx, [rcx+20h]
0x18002360d  mov     eax, [rdx+8]
0x180023610  lea     rsi, [rcx+38h]
0x180023614  mov     [rcx+8], eax
0x180023617  xor     r12d, r12d
0x18002361a  mov     [rcx+10h], r12
0x18002361e  mov     rbp, rcx
0x180023621  movzx   eax, word ptr [rdx+40h]
0x180023625  mov     r14, rdx
0x180023628  mov     [rcx+18h], ax
0x18002362c  mov     al, [rdx]
0x18002362e  mov     [rcx+1Ah], al
0x180023631  mov     [rbx], r12
0x180023634  mov     rax, [rdx+88h]
0x18002363b  mov     [rcx+28h], rax
0x18002363f  mov     rax, [rdx+90h]
0x180023646  mov     [rcx+30h], rax
0x18002364a  mov     [rsi], r12
0x18002364d  mov     rcx, [rdx+18h]; this
0x180023651  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180023656  mov     rcx, [r14+38h]; this
0x18002365a  mov     r15, rax
0x18002365d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180023662  mov     rcx, [r14+80h]; this
0x180023669  add     r15, rax
0x18002366c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180023671  add     r15, rax
0x180023674  lea     rdi, [rbp+48h]
0x180023678  cmp     [rbp+40h], r12
0x18002367c  jz      short loc_180023683
0x18002367e  cmp     [rdi], r15
0x180023681  jnb     short loc_1800236BE
0x180023683  mov     rdx, r15; dwBytes
0x180023686  mov     ecx, 8; dwFlags
0x18002368b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180023690  mov     r12, rax
0x180023693  test    rax, rax
0x180023696  jz      short loc_1800236BB
0x180023698  mov     rbx, [rbp+40h]
0x18002369c  call    cs:__imp_GetProcessHeap
0x1800236a2  mov     r8, rbx; lpMem
0x1800236a5  xor     edx, edx; dwFlags
0x1800236a7  mov     rcx, rax; hHeap
0x1800236aa  call    cs:__imp_HeapFree
0x1800236b0  mov     [rbp+40h], r12
0x1800236b4  lea     rbx, [rbp+20h]
0x1800236b8  mov     [rdi], r15
0x1800236bb  xor     r12d, r12d
0x1800236be  mov     rcx, [rbp+40h]; Destination
0x1800236c2  test    rcx, rcx
0x1800236c5  jz      loc_180023754
0x1800236cb  mov     rdi, [rdi]
0x1800236ce  lea     r9, [rbp+10h]
0x1800236d2  mov     r8, [r14+38h]
0x1800236d6  add     rdi, rcx
0x1800236d9  mov     rdx, rdi
0x1800236dc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800236e1  mov     r8, [r14+80h]
0x1800236e8  mov     r9, rbx
0x1800236eb  mov     rdx, rdi
0x1800236ee  mov     rcx, rax; Destination
0x1800236f1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800236f6  mov     rbx, rax
0x1800236f9  cmp     rax, rdi
0x1800236fc  jz      short loc_18002373C
0x1800236fe  mov     rcx, [r14+18h]; this
0x180023702  test    rcx, rcx
0x180023705  jz      short loc_18002373C
0x180023707  cmp     [rcx], r12w
0x18002370b  jz      short loc_18002373C
0x18002370d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180023712  mov     rdx, rdi
0x180023715  mov     r14, rax
0x180023718  sub     rdx, rbx; DestinationSize
0x18002371b  cmp     rdx, rax
0x18002371e  jb      short loc_18002373C
0x180023720  mov     r8, rcx; Source
0x180023723  mov     r9, rax; SourceSize
0x180023726  mov     rcx, rbx; Destination
0x180023729  call    cs:__imp_memcpy_s
0x18002372f  test    rsi, rsi
0x180023732  jz      short loc_180023737
0x180023734  mov     [rsi], rbx
0x180023737  add     rbx, r14
0x18002373a  jmp     short loc_180023744
0x18002373c  test    rsi, rsi
0x18002373f  jz      short loc_180023744
0x180023741  mov     [rsi], r12
0x180023744  sub     rdi, rbx
0x180023747  xor     edx, edx; Val
0x180023749  mov     r8, rdi; Size
0x18002374c  mov     rcx, rbx; void *
0x18002374f  call    memset_0
0x180023754  add     rsp, 28h
0x180023758  pop     r15
0x18002375a  pop     r14
0x18002375c  pop     r13
0x18002375e  pop     r12
0x180023760  pop     rdi
0x180023761  pop     rsi
0x180023762  pop     rbp
0x180023763  pop     rbx
0x180023764  retn
```
