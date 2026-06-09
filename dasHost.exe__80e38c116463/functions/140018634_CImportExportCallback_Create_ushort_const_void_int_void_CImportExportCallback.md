# CImportExportCallback::Create(ushort const *,void *,int,void *,CImportExportCallback * *)

- ea: `0x140018634`
- end: `0x140018714`
- name: `?Create@CImportExportCallback@@SAJPEBGPEAXH1PEAPEAV1@@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, void *, int, void *, struct CImportExportCallback **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000d1f0`
- `0x14000d590`

## callees

- `0x14000190c`
- `0x140009060`
- `0x140009090`
- `0x140018634`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400186e1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400186e1`

## pseudocode

```c
__int64 __fastcall CImportExportCallback::Create(
        const unsigned __int16 *Src,
        void *a2,
        int a3,
        void *a4,
        struct CImportExportCallback **a5)
{
  unsigned int v9; // edi
  __int64 v10; // rax
  size_t v11; // r14
  void *v12; // rax
  void *v13; // rsi
  char *v14; // rbx
  void *v16; // [rsp+28h] [rbp-40h]

  v9 = 0;
  v10 = -1;
  do
    ++v10;
  while ( Src[v10] );
  v11 = (unsigned int)(2 * v10 + 2);
  v12 = DAF_user_alloc(v11);
  v13 = v12;
  v16 = v12;
  if ( v12 )
  {
    memcpy_0(v12, Src, v11);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v14 = (char *)operator new(0x70u);
      *(_QWORD *)v14 = &CImportExportCallback::`vftable'{for `IAepImportExportCallback'};
      *((_QWORD *)v14 + 1) = &CImportExportCallback::`vftable'{for `IDafPrivImpersonationToken'};
      *((_QWORD *)v14 + 2) = &CImportExportCallback::`vftable'{for `IServiceProvider'};
      *((_DWORD *)v14 + 6) = 1;
      *((_QWORD *)v14 + 4) = v13;
      *((_QWORD *)v14 + 5) = a2;
      *((_DWORD *)v14 + 22) = 1;
      *((_QWORD *)v14 + 12) = a4;
      *((_DWORD *)v14 + 26) = a3;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v14 + 48));
      *a5 = (struct CImportExportCallback *)v14;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1400186F4);
        MIDL_user_free(v16);
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x140018634  push    rbx
0x140018636  push    rsi
0x140018637  push    rdi
0x140018638  push    r12
0x14001863a  push    r13
0x14001863c  push    r14
0x14001863e  push    r15
0x140018640  sub     rsp, 30h
0x140018644  mov     r15, r9
0x140018647  mov     r12d, r8d
0x14001864a  mov     r13, rdx
0x14001864d  mov     rbx, rcx
0x140018650  xor     ecx, ecx
0x140018652  mov     edi, ecx
0x140018654  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018658  inc     rax
0x14001865b  cmp     [rbx+rax*2], cx
0x14001865f  jnz     short loc_140018658
0x140018661  lea     eax, ds:2[rax*2]
0x140018668  mov     r14d, eax
0x14001866b  mov     ecx, eax
0x14001866d  call    DAF_user_alloc
0x140018672  mov     rsi, rax
0x140018675  mov     [rsp+68h+var_40], rax
0x14001867a  test    rax, rax
0x14001867d  jnz     short loc_140018686
0x14001867f  mov     edi, 8007000Eh
0x140018684  jmp     short loc_140018702
0x140018686  mov     r8, r14; Size
0x140018689  mov     rdx, rbx; Src
0x14001868c  mov     rcx, rsi; void *
0x14001868f  call    memcpy_0
0x140018694  nop
0x140018695  mov     ecx, 70h ; 'p'; Size
0x14001869a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001869f  mov     rbx, rax
0x1400186a2  lea     rax, ??_7CImportExportCallback@@6BIAepImportExportCallback@@@; const CImportExportCallback::`vftable'{for `IAepImportExportCallback'}
0x1400186a9  mov     [rbx], rax
0x1400186ac  lea     rax, ??_7CImportExportCallback@@6BIDafPrivImpersonationToken@@@; const CImportExportCallback::`vftable'{for `IDafPrivImpersonationToken'}
0x1400186b3  mov     [rbx+8], rax
0x1400186b7  lea     rax, ??_7CImportExportCallback@@6BIServiceProvider@@@; const CImportExportCallback::`vftable'{for `IServiceProvider'}
0x1400186be  mov     [rbx+10h], rax
0x1400186c2  mov     eax, 1
0x1400186c7  mov     [rbx+18h], eax
0x1400186ca  mov     [rbx+20h], rsi
0x1400186ce  mov     [rbx+28h], r13
0x1400186d2  mov     [rbx+58h], eax
0x1400186d5  mov     [rbx+60h], r15
0x1400186d9  mov     [rbx+68h], r12d
0x1400186dd  lea     rcx, [rbx+30h]; lpCriticalSection
0x1400186e1  call    cs:__imp_InitializeCriticalSection
0x1400186e7  mov     rax, [rsp+68h+arg_20]
0x1400186ef  mov     [rax], rbx
0x1400186f2  jmp     short loc_140018702
0x1400186f4  mov     rcx, [rsp+68h+var_40]; void *
0x1400186f9  call    MIDL_user_free
0x1400186fe  mov     edi, [rsp+68h+var_48]
0x140018702  mov     eax, edi
0x140018704  add     rsp, 30h
0x140018708  pop     r15
0x14001870a  pop     r14
0x14001870c  pop     r13
0x14001870e  pop     r12
0x140018710  pop     rdi
0x140018711  pop     rsi
0x140018712  pop     rbx
0x140018713  retn
```
