# CandidateList::GetAt(ulong)

- ea: `0x1800276b0`
- end: `0x18002787a`
- name: `?GetAt@CandidateList@@QEAA?AV?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@K@Z`
- size: `458`
- prototype: `ProfileSelection **__fastcall(CandidateList *, ProfileSelection **, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180027220`
- `0x180027880`

## callees

- `0x180002034`
- `0x180012d80`
- `0x180026240`
- `0x1800276b0`
- `0x180029d04`
- `0x18003b952`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800276fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002775d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800276fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002775d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002772d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800277bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002772d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800277bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800277da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800277da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027817`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002778c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002778c`

## pseudocode

```c
ProfileSelection **__fastcall CandidateList::GetAt(CandidateList *a1, ProfileSelection **a2, unsigned int a3)
{
  __int64 v3; // r13
  int v6; // edi
  bool v7; // zf
  char v8; // al
  __int64 v9; // rsi
  __int64 v10; // r14
  int v11; // ebx
  unsigned __int8 *v12; // rsi
  unsigned int v13; // r13d
  __int64 v14; // rdi
  unsigned __int8 *v15; // rax
  ProfileSelection *v16; // rax
  int v18; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v3 = a3;
  v6 = 0;
  if ( *((_QWORD *)a1 + 5) || (v7 = !CandidateList::LoadPersistList(a1), v8 = 1, !v7) )
    v8 = 0;
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)0x8007139FLL,
      v18);
  v9 = *((_QWORD *)a1 + 5);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 40));
  v10 = 0;
  v11 = -2147023728;
  if ( (unsigned int)v3 < *(_DWORD *)(v9 + 16) )
  {
    if ( *(_DWORD *)(v9 + 28) )
    {
      _mm_lfence();
      v10 = *(_QWORD *)(*(_QWORD *)(v9 + 8) + 8 * v3);
    }
    else
    {
      v6 = -2102788096;
    }
  }
  else
  {
    v6 = -2147023728;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 40));
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)(unsigned int)v6,
      v18);
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 32));
  v13 = 0;
  if ( *(_DWORD *)(v10 + 16) )
  {
    v14 = **(_QWORD **)(v10 + 8);
    if ( v14 )
    {
      if ( *(_DWORD *)v14 == 3 )
      {
        v15 = (unsigned __int8 *)LocalAlloc(0x40u, *(unsigned int *)(v14 + 8));
        v12 = v15;
        if ( v15 )
        {
          v11 = 0;
          memcpy_0(v15, *(const void **)(v14 + 24), *(unsigned int *)(v14 + 8));
          v13 = *(_DWORD *)(v14 + 8);
        }
        else
        {
          v11 = -2147024882;
        }
      }
      else
      {
        v11 = -2147024883;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 32));
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)(unsigned int)v11,
      v18);
  v16 = (ProfileSelection *)operator new(0x18u);
  if ( v16 )
    v16 = ProfileSelection::ProfileSelection(v16, v12, v13);
  *a2 = v16;
  if ( v12 )
    LocalFree(v12);
  return a2;
}

```

## disassembly

```asm
0x1800276b0  mov     [rsp-38h+arg_8], rbx
0x1800276b5  push    rbp
0x1800276b6  push    rsi
0x1800276b7  push    rdi
0x1800276b8  push    r12
0x1800276ba  push    r13
0x1800276bc  push    r14
0x1800276be  push    r15
0x1800276c0  mov     rbp, rsp
0x1800276c3  sub     rsp, 40h
0x1800276c7  mov     r13d, r8d
0x1800276ca  mov     r15, rdx
0x1800276cd  mov     rsi, rcx
0x1800276d0  xor     edi, edi
0x1800276d2  cmp     [rcx+28h], rdi
0x1800276d6  jnz     short loc_1800276E3
0x1800276d8  call    ?LoadPersistList@CandidateList@@IEAA_NXZ; CandidateList::LoadPersistList(void)
0x1800276dd  test    al, al
0x1800276df  mov     al, 1
0x1800276e1  jz      short loc_1800276E6
0x1800276e3  mov     al, dil
0x1800276e6  mov     rcx, [rbp+38h]; this
0x1800276ea  test    al, al
0x1800276ec  jnz     loc_18002784D
0x1800276f2  mov     rsi, [rsi+28h]
0x1800276f6  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800276fa  call    cs:__imp_EnterCriticalSection
0x180027700  mov     r14, rdi
0x180027703  mov     ebx, 80070490h
0x180027708  cmp     r13d, [rsi+10h]
0x18002770c  jb      short loc_180027712
0x18002770e  mov     edi, ebx
0x180027710  jmp     short loc_180027729
0x180027712  cmp     [rsi+1Ch], edi
0x180027715  jnz     short loc_18002771E
0x180027717  mov     edi, 82AA0000h
0x18002771c  jmp     short loc_180027729
0x18002771e  lfence
0x180027721  mov     rax, [rsi+8]
0x180027725  mov     r14, [rax+r13*8]
0x180027729  lea     rcx, [rsi+28h]; lpCriticalSection
0x18002772d  call    cs:__imp_LeaveCriticalSection
0x180027733  mov     rcx, [rbp+38h]; this
0x180027737  test    edi, edi
0x180027739  js      loc_180027865
0x18002773f  mov     [rbp+hMem], 0
0x180027747  lea     rax, [rbp+hMem]
0x18002774b  mov     [rbp+var_18], rax
0x18002774f  xor     esi, esi
0x180027751  mov     [rbp+var_10], rsi
0x180027755  mov     [rbp+var_8], 1
0x180027759  lea     rcx, [r14+20h]; lpCriticalSection
0x18002775d  call    cs:__imp_EnterCriticalSection
0x180027763  xor     r13d, r13d
0x180027766  cmp     [r14+10h], r13d
0x18002776a  jbe     short loc_1800277BB
0x18002776c  mov     rax, [r14+8]
0x180027770  mov     rdi, [rax]
0x180027773  test    rdi, rdi
0x180027776  jz      short loc_1800277BB
0x180027778  cmp     dword ptr [rdi], 3
0x18002777b  jz      short loc_180027784
0x18002777d  mov     ebx, 8007000Dh
0x180027782  jmp     short loc_1800277BB
0x180027784  mov     edx, [rdi+8]; uBytes
0x180027787  mov     ecx, 40h ; '@'; uFlags
0x18002778c  call    cs:__imp_LocalAlloc
0x180027792  mov     rsi, rax
0x180027795  mov     [rbp+var_10], rax
0x180027799  test    rax, rax
0x18002779c  jnz     short loc_1800277A5
0x18002779e  mov     ebx, 8007000Eh
0x1800277a3  jmp     short loc_1800277BB
0x1800277a5  xor     ebx, ebx
0x1800277a7  mov     r8d, [rdi+8]; Size
0x1800277ab  mov     rdx, [rdi+18h]; Src
0x1800277af  mov     rcx, rax; void *
0x1800277b2  call    memcpy_0
0x1800277b7  mov     r13d, [rdi+8]
0x1800277bb  lea     rcx, [r14+20h]; lpCriticalSection
0x1800277bf  call    cs:__imp_LeaveCriticalSection
0x1800277c5  mov     rcx, [rbp+38h]; this
0x1800277c9  test    ebx, ebx
0x1800277cb  js      short loc_180027838
0x1800277cd  mov     rcx, [rbp+hMem]; hMem
0x1800277d1  mov     [rbp+hMem], rsi
0x1800277d5  test    rcx, rcx
0x1800277d8  jz      short loc_1800277E0
0x1800277da  call    cs:__imp_LocalFree
0x1800277e0  mov     ecx, 18h; Size
0x1800277e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800277ea  mov     [rbp+arg_18], rax
0x1800277ee  test    rax, rax
0x1800277f1  jz      short loc_180027803
0x1800277f3  mov     r8d, r13d; unsigned int
0x1800277f6  mov     rdx, [rbp+hMem]; unsigned __int8 *
0x1800277fa  mov     rcx, rax; this
0x1800277fd  call    ??0ProfileSelection@@QEAA@PEBEK@Z; ProfileSelection::ProfileSelection(uchar const *,ulong)
0x180027802  nop
0x180027803  mov     [r15], rax
0x180027806  mov     rcx, [rbp+hMem]; hMem
0x18002780a  mov     [rbp+hMem], 0
0x180027812  test    rcx, rcx
0x180027815  jz      short loc_18002781D
0x180027817  call    cs:__imp_LocalFree
0x18002781d  mov     rax, r15
0x180027820  mov     rbx, [rsp+40h+arg_8]
0x180027828  add     rsp, 40h
0x18002782c  pop     r15
0x18002782e  pop     r14
0x180027830  pop     r13
0x180027832  pop     r12
0x180027834  pop     rdi
0x180027835  pop     rsi
0x180027836  pop     rbp
0x180027837  retn
0x180027838  mov     r9d, ebx; char *
0x18002783b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180027842  mov     edx, 0E7h; void *
0x180027847  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002784d  mov     r9d, 8007139Fh; char *
0x180027853  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002785a  mov     edx, 0DDh; void *
0x18002785f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027865  mov     r9d, edi; char *
0x180027868  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002786f  mov     edx, 0E1h; void *
0x180027874  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
