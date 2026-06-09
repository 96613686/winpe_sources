# CFileStream::Unmarshal(BasedPtr<CGlobalFileStream>,void * *,ulong)

- ea: `0x18003ec7c`
- end: `0x18003ee64`
- name: `?Unmarshal@CFileStream@@SAJV?$BasedPtr@VCGlobalFileStream@@@@PEAPEAXK@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ca84`

## callees

- `0x180018680`
- `0x18001d820`
- `0x18001db94`
- `0x18001defc`
- `0x180032790`
- `0x18003ec7c`
- `0x18003f54c`
- `0x18004c638`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18003ed3f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18003ed3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ed16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ed16`

## string_xrefs

- `0x18003ee40`: `onecoreuap\com\coml2\stg\exp\filest.cxx`

## pseudocode

```c
__int64 __fastcall CFileStream::Unmarshal(__int64 a1, CFileStream **a2)
{
  struct CSmAllocator *TlsSmAllocator; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  CContextList *v7; // rdi
  DWORD CurrentProcessId; // eax
  __int64 v9; // rax
  struct IMalloc *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  CFileStream *v13; // rdi
  void *v14; // rcx
  CFileStream *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int inited; // ebx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  TlsSmAllocator = GetTlsSmAllocator();
  if ( !(*(unsigned __int8 (__fastcall **)(struct CSmAllocator *, __int64, __int64))(*(_QWORD *)TlsSmAllocator + 72LL))(
          TlsSmAllocator,
          a1,
          624) )
    goto LABEL_33;
  if ( a1 )
    v5 = a1 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v5 = 0;
  v6 = *(_QWORD *)(v5 + 16) - *(_QWORD *)&GUID_b505dc81_f56c_4e77_8760_a05a9b1c070a.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)(v5 + 24) - *(_QWORD *)GUID_b505dc81_f56c_4e77_8760_a05a9b1c070a.Data4;
  if ( v6 )
  {
LABEL_33:
    inited = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\com\\coml2\\stg\\exp\\filest.cxx",
      (const char *)0x80070005LL,
      v21);
    return (unsigned int)inited;
  }
  if ( a1 )
    v7 = (CContextList *)(a1 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
  else
    v7 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v9 = (__int64)CContextList::_Find(v7, CurrentProcessId);
  v11 = v9 - 32;
  v12 = -v9;
  v13 = (CFileStream *)(v11 & -(__int64)(v12 != 0));
  if ( v13 )
  {
    v14 = *(void **)((v11 & -(__int64)(v12 != 0)) + 0x40);
    if ( v14 == (void *)-1LL || GetFileType(v14) == 1 )
    {
      (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v13 + 8LL))(v13);
      goto LABEL_19;
    }
    *((_DWORD *)v13 + 8) = 0;
  }
  v15 = (CFileStream *)CMallocBased::operator new(0x78u, v10);
  if ( !v15 )
    return (unsigned int)-2147287032;
  v16 = a1 ? a1 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
  if ( (v13 = CFileStream::CFileStream(v15, *(struct IMalloc *const *)(v16 + 40))) == 0 )
    return (unsigned int)-2147287032;
  if ( a1 )
    v20 = a1 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v20 = 0;
  *((_QWORD *)v13 + 6) = v20;
  ++*(_DWORD *)(v20 + 8);
  CContextList::Add(*((CContextList **)v13 + 6), (CFileStream *)((char *)v13 + 32));
LABEL_19:
  if ( a1 )
    v17 = a1 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v17 = 0;
  if ( !*(_WORD *)(v17 + 72) || (inited = CFileStream::InitWorker(v13, 0, 1u, 0), inited >= 0) )
  {
    *a2 = v13;
    return 0;
  }
  (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18003ec7c  push    rbx
0x18003ec7e  push    rbp
0x18003ec7f  push    rsi
0x18003ec80  push    rdi
0x18003ec81  sub     rsp, 28h
0x18003ec85  mov     rsi, rdx
0x18003ec88  mov     rbx, rcx
0x18003ec8b  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18003ec90  mov     r9, rax
0x18003ec93  mov     r8d, 270h
0x18003ec99  mov     rdx, rbx
0x18003ec9c  mov     rcx, [rax]
0x18003ec9f  mov     rax, [rcx+48h]
0x18003eca3  mov     rcx, r9
0x18003eca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecab  xor     ebp, ebp
0x18003ecad  test    al, al
0x18003ecaf  jz      loc_18003EE3B
0x18003ecb5  test    rbx, rbx
0x18003ecb8  jz      short loc_18003ECD2
0x18003ecba  mov     rax, gs:30h
0x18003ecc3  mov     rcx, [rax+1758h]
0x18003ecca  mov     rcx, [rcx]
0x18003eccd  add     rcx, rbx
0x18003ecd0  jmp     short loc_18003ECD5
0x18003ecd2  mov     rcx, rbp
0x18003ecd5  mov     rax, [rcx+10h]
0x18003ecd9  sub     rax, qword ptr cs:_GUID_b505dc81_f56c_4e77_8760_a05a9b1c070a.Data1
0x18003ece0  jnz     short loc_18003ECED
0x18003ece2  mov     rax, [rcx+18h]
0x18003ece6  sub     rax, qword ptr cs:_GUID_b505dc81_f56c_4e77_8760_a05a9b1c070a.Data4
0x18003eced  test    rax, rax
0x18003ecf0  jnz     loc_18003EE3B
0x18003ecf6  test    rbx, rbx
0x18003ecf9  jz      short loc_18003ED13
0x18003ecfb  mov     rax, gs:30h
0x18003ed04  mov     rcx, [rax+1758h]
0x18003ed0b  mov     rdi, [rcx]
0x18003ed0e  add     rdi, rbx
0x18003ed11  jmp     short loc_18003ED16
0x18003ed13  mov     rdi, rbp
0x18003ed16  call    cs:__imp_GetCurrentProcessId
0x18003ed1c  mov     edx, eax; unsigned int
0x18003ed1e  mov     rcx, rdi; this
0x18003ed21  call    ?_Find@CContextList@@QEAAPEAVCContext@@K@Z; CContextList::_Find(ulong)
0x18003ed26  lea     rcx, [rax-20h]
0x18003ed2a  neg     rax
0x18003ed2d  sbb     rdi, rdi
0x18003ed30  and     rdi, rcx
0x18003ed33  jz      short loc_18003ED4D
0x18003ed35  mov     rcx, [rdi+40h]; hFile
0x18003ed39  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003ed3d  jz      short loc_18003ED7D
0x18003ed3f  call    cs:__imp_GetFileType
0x18003ed45  cmp     eax, 1
0x18003ed48  jz      short loc_18003ED7D
0x18003ed4a  mov     [rdi+20h], ebp
0x18003ed4d  mov     ecx, 78h ; 'x'; unsigned __int64
0x18003ed52  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18003ed57  test    rax, rax
0x18003ed5a  jz      loc_18003EE34
0x18003ed60  test    rbx, rbx
0x18003ed63  jz      short loc_18003EDD3
0x18003ed65  mov     rcx, gs:30h
0x18003ed6e  mov     rdx, [rcx+1758h]
0x18003ed75  mov     rdx, [rdx]
0x18003ed78  add     rdx, rbx
0x18003ed7b  jmp     short loc_18003EDD6
0x18003ed7d  mov     rax, [rdi]
0x18003ed80  mov     rcx, rdi
0x18003ed83  mov     rax, [rax+8]
0x18003ed87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed8c  test    rbx, rbx
0x18003ed8f  jz      short loc_18003EDA9
0x18003ed91  mov     rax, gs:30h
0x18003ed9a  mov     rcx, [rax+1758h]
0x18003eda1  mov     rcx, [rcx]
0x18003eda4  add     rcx, rbx
0x18003eda7  jmp     short loc_18003EDAC
0x18003eda9  mov     rcx, rbp
0x18003edac  cmp     [rcx+48h], bp
0x18003edb0  jz      short loc_18003EDC9
0x18003edb2  xor     r9d, r9d; void *
0x18003edb5  xor     edx, edx; unsigned __int16 *
0x18003edb7  mov     rcx, rdi; this
0x18003edba  lea     r8d, [r9+1]; unsigned int
0x18003edbe  call    ?InitWorker@CFileStream@@AEAAJPEBGKPEAX@Z; CFileStream::InitWorker(ushort const *,ulong,void *)
0x18003edc3  mov     ebx, eax
0x18003edc5  test    eax, eax
0x18003edc7  js      short loc_18003EE23
0x18003edc9  mov     [rsi], rdi
0x18003edcc  xor     eax, eax
0x18003edce  jmp     loc_18003EE5B
0x18003edd3  mov     rdx, rbp
0x18003edd6  mov     rdx, [rdx+28h]; struct IMalloc *
0x18003edda  mov     rcx, rax; this
0x18003eddd  call    ??0CFileStream@@QEAA@QEAUIMalloc@@@Z; CFileStream::CFileStream(IMalloc * const)
0x18003ede2  mov     rdi, rax
0x18003ede5  test    rax, rax
0x18003ede8  jz      short loc_18003EE34
0x18003edea  test    rbx, rbx
0x18003eded  jz      short loc_18003EE07
0x18003edef  mov     rax, gs:30h
0x18003edf8  mov     rcx, [rax+1758h]
0x18003edff  mov     rcx, [rcx]
0x18003ee02  add     rcx, rbx
0x18003ee05  jmp     short loc_18003EE0A
0x18003ee07  mov     rcx, rbp
0x18003ee0a  mov     [rdi+30h], rcx
0x18003ee0e  lea     rdx, [rdi+20h]; struct CContext *
0x18003ee12  inc     dword ptr [rcx+8]
0x18003ee15  mov     rcx, [rdi+30h]; this
0x18003ee19  call    ?Add@CContextList@@QEAAXPEAVCContext@@@Z; CContextList::Add(CContext *)
0x18003ee1e  jmp     loc_18003ED8C
0x18003ee23  mov     rax, [rdi]
0x18003ee26  mov     rcx, rdi
0x18003ee29  mov     rax, [rax+10h]
0x18003ee2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee32  jmp     short loc_18003EE59
0x18003ee34  mov     ebx, 80030008h
0x18003ee39  jmp     short loc_18003EE59
0x18003ee3b  mov     rcx, [rsp+48h]; this
0x18003ee40  lea     r8, aOnecoreuapComC_3; "onecoreuap\\com\\coml2\\stg\\exp\\files"...
0x18003ee47  mov     ebx, 80070005h
0x18003ee4c  mov     edx, 148h; void *
0x18003ee51  mov     r9d, ebx; char *
0x18003ee54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee59  mov     eax, ebx
0x18003ee5b  add     rsp, 28h
0x18003ee5f  pop     rdi
0x18003ee60  pop     rsi
0x18003ee61  pop     rbp
0x18003ee62  pop     rbx
0x18003ee63  retn
```
