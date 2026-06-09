# SSI_INCLUDE_FILE::CreateInstance(STRU &,STRU &,SSI_REQUEST *,SSI_INCLUDE_FILE *,SSI_INCLUDE_FILE * *)

- ea: `0x180003c24`
- end: `0x180003d84`
- name: `?CreateInstance@SSI_INCLUDE_FILE@@SAJAEAVSTRU@@0PEAVSSI_REQUEST@@PEAV1@PEAPEAV1@@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct STRU *, struct STRU *, struct SSI_REQUEST *, struct SSI_INCLUDE_FILE *, struct SSI_INCLUDE_FILE **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180003530`
- `0x180004afc`

## callees

- `0x180002648`
- `0x180003b7c`
- `0x180003c24`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180003cd7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180003ced`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180003cd7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180003ced`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003d07`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003d07`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003c7c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003c93`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003c7c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003c93`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003cca`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003cca`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180003d52`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180003d52`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180003c42`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180003c42`

## pseudocode

```c
__int64 __fastcall SSI_INCLUDE_FILE::CreateInstance(
        struct STRU *a1,
        struct STRU *a2,
        struct SSI_REQUEST *a3,
        struct SSI_INCLUDE_FILE *a4,
        struct SSI_INCLUDE_FILE **a5)
{
  char *v9; // rax
  char *v10; // rbx
  int ReferencedInstance; // edi
  int v12; // eax
  __int64 result; // rax

  v9 = (char *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles);
  v10 = v9;
  if ( !v9 )
    return 2147942408LL;
  *((_QWORD *)v9 + 3) = a4;
  *((_QWORD *)v9 + 2) = a3;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  STRU::STRU((STRU *)(v9 + 48), (unsigned __int16 *)v9 + 52, 0x81u);
  STRU::STRU((STRU *)(v10 + 368), (unsigned __int16 *)v10 + 212, 0x81u);
  *((_DWORD *)v10 + 171) = 0;
  *((_QWORD *)v10 + 86) = 0;
  *((_DWORD *)v10 + 174) = 0;
  STRA::STRA((STRA *)(v10 + 704), v10 + 760, 0x15u);
  ReferencedInstance = STRU::Copy((STRU *)(v10 + 48), a1);
  if ( ReferencedInstance < 0
    || (ReferencedInstance = STRU::Copy((STRU *)(v10 + 368), a2), ReferencedInstance < 0)
    || (ReferencedInstance = STRA::Copy((STRA *)(v10 + 704), "%A %B %d %Y"), ReferencedInstance < 0)
    || (ReferencedInstance = SSI_FILE::GetReferencedInstance(
                               *((struct SSI_REQUEST **)v10 + 2),
                               (struct STRU *)(v10 + 48),
                               (struct SSI_FILE **)v10 + 4),
        ReferencedInstance < 0) )
  {
    v12 = 5;
  }
  else
  {
    ReferencedInstance = 0;
    v12 = 1;
  }
  *((_DWORD *)v10 + 171) = v12;
  if ( ReferencedInstance >= 0 )
  {
    *a5 = (struct SSI_INCLUDE_FILE *)v10;
    return 0;
  }
  else
  {
    SSI_INCLUDE_FILE::~SSI_INCLUDE_FILE((SSI_INCLUDE_FILE *)v10);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles, v10);
    result = (unsigned int)ReferencedInstance;
    *a5 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003c24  push    rbx
0x180003c26  push    rbp
0x180003c27  push    rsi
0x180003c28  push    rdi
0x180003c29  push    r14
0x180003c2b  sub     rsp, 20h
0x180003c2f  mov     r14, rcx
0x180003c32  mov     rdi, r9
0x180003c35  mov     rcx, cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x180003c3c  mov     rbp, r8
0x180003c3f  mov     rsi, rdx
0x180003c42  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180003c48  mov     rbx, rax
0x180003c4b  test    rax, rax
0x180003c4e  jz      loc_180003D74
0x180003c54  mov     [rax+18h], rdi
0x180003c58  lea     rdx, [rax+68h]
0x180003c5c  mov     edi, 81h
0x180003c61  mov     [rax+10h], rbp
0x180003c65  mov     r8d, edi
0x180003c68  mov     qword ptr [rax+20h], 0
0x180003c70  lea     rcx, [rax+30h]
0x180003c74  mov     qword ptr [rax+28h], 0
0x180003c7c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003c82  lea     rdx, [rbx+1A8h]
0x180003c89  mov     r8d, edi
0x180003c8c  lea     rcx, [rbx+170h]
0x180003c93  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003c99  lea     rdx, [rbx+2F8h]
0x180003ca0  mov     dword ptr [rbx+2ACh], 0
0x180003caa  lea     rcx, [rbx+2C0h]
0x180003cb1  mov     qword ptr [rbx+2B0h], 0
0x180003cbc  lea     r8d, [rdi-6Ch]
0x180003cc0  mov     dword ptr [rbx+2B8h], 0
0x180003cca  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003cd0  mov     rdx, r14
0x180003cd3  lea     rcx, [rbx+30h]
0x180003cd7  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180003cdd  mov     edi, eax
0x180003cdf  test    eax, eax
0x180003ce1  js      short loc_180003D31
0x180003ce3  lea     rcx, [rbx+170h]
0x180003cea  mov     rdx, rsi
0x180003ced  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180003cf3  mov     edi, eax
0x180003cf5  test    eax, eax
0x180003cf7  js      short loc_180003D31
0x180003cf9  lea     rcx, [rbx+2C0h]
0x180003d00  lea     rdx, aABDY; "%A %B %d %Y"
0x180003d07  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003d0d  mov     edi, eax
0x180003d0f  test    eax, eax
0x180003d11  js      short loc_180003D31
0x180003d13  mov     rcx, [rbx+10h]; struct SSI_REQUEST *
0x180003d17  lea     r8, [rbx+20h]; struct SSI_FILE **
0x180003d1b  lea     rdx, [rbx+30h]; struct STRU *
0x180003d1f  call    ?GetReferencedInstance@SSI_FILE@@SAJPEAVSSI_REQUEST@@AEAVSTRU@@PEAPEAV1@@Z; SSI_FILE::GetReferencedInstance(SSI_REQUEST *,STRU &,SSI_FILE * *)
0x180003d24  mov     edi, eax
0x180003d26  test    eax, eax
0x180003d28  js      short loc_180003D31
0x180003d2a  xor     edi, edi
0x180003d2c  lea     eax, [rdi+1]
0x180003d2f  jmp     short loc_180003D36
0x180003d31  mov     eax, 5
0x180003d36  mov     [rbx+2ACh], eax
0x180003d3c  test    edi, edi
0x180003d3e  jns     short loc_180003D68
0x180003d40  mov     rcx, rbx; this
0x180003d43  call    ??1SSI_INCLUDE_FILE@@QEAA@XZ; SSI_INCLUDE_FILE::~SSI_INCLUDE_FILE(void)
0x180003d48  mov     rcx, cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x180003d4f  mov     rdx, rbx
0x180003d52  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180003d58  mov     rcx, [rsp+48h+arg_20]
0x180003d5d  mov     eax, edi
0x180003d5f  mov     qword ptr [rcx], 0
0x180003d66  jmp     short loc_180003D79
0x180003d68  mov     rax, [rsp+48h+arg_20]
0x180003d6d  mov     [rax], rbx
0x180003d70  xor     eax, eax
0x180003d72  jmp     short loc_180003D79
0x180003d74  mov     eax, 80070008h
0x180003d79  add     rsp, 20h
0x180003d7d  pop     r14
0x180003d7f  pop     rdi
0x180003d80  pop     rsi
0x180003d81  pop     rbp
0x180003d82  pop     rbx
0x180003d83  retn
```
