# HTTP_COMPRESSION::CheckForExistenceOfCompressedFile(IHttpFileInfo *,STRU *,IHttpFileInfo * *,IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::enumReason *,IHttpTraceContext *)

- ea: `0x180001d80`
- end: `0x180001eb8`
- name: `?CheckForExistenceOfCompressedFile@HTTP_COMPRESSION@@CAHPEAVIHttpFileInfo@@PEAVSTRU@@PEAPEAV2@PEAW4enumReason@STATIC_COMPRESSION_NOT_SUCCESS@IISCompressionEvents@@PEAVIHttpTraceContext@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(struct IHttpFileInfo *, struct STRU *, struct IHttpFileInfo **, enum IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::enumReason *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001310`

## callees

- `0x180001d80`
- `0x180005f90`
- `0x180009010`

## import_xrefs

- `iisutil!MakePathCanonicalizationProof` at `0x1800069b4`
- `iisutil!MakePathCanonicalizationProof` at `0x1800069b4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001dcf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001ddb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800069a6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800069c3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001dcf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001ddb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800069a6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800069c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800069d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800069d7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000699d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000699d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001ea3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001ea3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800069cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800069cc`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::CheckForExistenceOfCompressedFile(
        struct IHttpFileInfo *a1,
        struct STRU *a2,
        struct IHttpFileInfo **a3,
        enum IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::enumReason *a4,
        struct IHttpTraceContext *a5)
{
  int (__fastcall *v9)(struct IHttpServer *, unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, int, struct IHttpFileInfo **, struct IHttpTraceContext *); // rsi
  unsigned __int16 *Str; // rdi
  unsigned __int16 *v11; // rax
  unsigned int v12; // ebx
  struct IHttpFileInfo *v14; // rdi
  const unsigned __int16 *v15; // rax
  const WCHAR *v16; // rax
  FILETIME FileTime2; // [rsp+50h] [rbp-A8h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v20[56]; // [rsp+68h] [rbp-90h] BYREF

  v9 = *(int (__fastcall **)(struct IHttpServer *, unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, int, struct IHttpFileInfo **, struct IHttpTraceContext *))(*(_QWORD *)g_pGlobalInfo + 64LL);
  Str = STRU::QueryStr((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory);
  v11 = STRU::QueryStr(a2);
  v12 = 1;
  if ( v9(g_pGlobalInfo, v11, 0, 0, Str, 0, 1, a3, a5) >= 0 )
  {
    v14 = *a3;
    v19 = 0;
    FileTime1 = 0;
    FileTime2 = 0;
    (*(void (__fastcall **)(struct IHttpFileInfo *, __int64 *))(*(_QWORD *)v14 + 64LL))(v14, &v19);
    (*(void (__fastcall **)(struct IHttpFileInfo *, FILETIME *))(*(_QWORD *)v14 + 104LL))(v14, &FileTime1);
    (*(void (__fastcall **)(struct IHttpFileInfo *, FILETIME *))(*(_QWORD *)a1 + 104LL))(a1, &FileTime2);
    if ( CompareFileTime(&FileTime1, &FileTime2) )
    {
      v12 = 0;
      (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v14 + 16LL))(v14);
      *a3 = 0;
      *(_DWORD *)a4 = 11;
      STRU::STRU((STRU *)v20);
      v15 = STRU::QueryStr(a2);
      if ( (int)MakePathCanonicalizationProof(v15, (struct STRU *)v20) >= 0 )
      {
        v16 = STRU::QueryStr((STRU *)v20);
        DeleteFileW(v16);
      }
      STRU::~STRU((STRU *)v20);
    }
    return v12;
  }
  else
  {
    *(_DWORD *)a4 = 10;
    return 0;
  }
}

```

## disassembly

```asm
0x180001d80  push    rbx
0x180001d82  push    rbp
0x180001d83  push    rsi
0x180001d84  push    rdi
0x180001d85  push    r12
0x180001d87  push    r13
0x180001d89  push    r14
0x180001d8b  push    r15
0x180001d8d  sub     rsp, 0B8h
0x180001d94  mov     rax, cs:__security_cookie
0x180001d9b  xor     rax, rsp
0x180001d9e  mov     [rsp+0F8h+var_58], rax
0x180001da6  mov     rax, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001dad  mov     rbp, rcx
0x180001db0  mov     rbx, [rsp+0F8h+arg_20]
0x180001db8  mov     r14, r9
0x180001dbb  mov     r15, r8
0x180001dbe  mov     r12, rdx
0x180001dc1  mov     rcx, [rax]
0x180001dc4  mov     rsi, [rcx+40h]
0x180001dc8  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180001dcf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001dd5  mov     rcx, r12
0x180001dd8  mov     rdi, rax
0x180001ddb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001de1  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001de8  xor     r13d, r13d
0x180001deb  mov     [rsp+0F8h+var_B8], rbx
0x180001df0  mov     rdx, rax
0x180001df3  mov     [rsp+0F8h+var_C0], r15
0x180001df8  mov     ebx, 1
0x180001dfd  mov     [rsp+0F8h+var_C8], ebx
0x180001e01  xor     r9d, r9d
0x180001e04  mov     [rsp+0F8h+var_D0], r13
0x180001e09  xor     r8d, r8d
0x180001e0c  mov     rax, rsi
0x180001e0f  mov     [rsp+0F8h+var_D8], rdi
0x180001e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e19  test    eax, eax
0x180001e1b  jns     short loc_180001E4A
0x180001e1d  mov     dword ptr [r14], 0Ah
0x180001e24  xor     eax, eax
0x180001e26  mov     rcx, [rsp+0F8h+var_58]
0x180001e2e  xor     rcx, rsp; StackCookie
0x180001e31  call    __security_check_cookie
0x180001e36  add     rsp, 0B8h
0x180001e3d  pop     r15
0x180001e3f  pop     r14
0x180001e41  pop     r13
0x180001e43  pop     r12
0x180001e45  pop     rdi
0x180001e46  pop     rsi
0x180001e47  pop     rbp
0x180001e48  pop     rbx
0x180001e49  retn
0x180001e4a  mov     rdi, [r15]
0x180001e4d  lea     rdx, [rsp+0F8h+var_98]
0x180001e52  mov     [rsp+0F8h+var_98], r13
0x180001e57  mov     rcx, rdi
0x180001e5a  mov     qword ptr [rsp+0F8h+FileTime1.dwLowDateTime], r13
0x180001e5f  mov     qword ptr [rsp+0F8h+FileTime2.dwLowDateTime], r13
0x180001e64  mov     rax, [rdi]
0x180001e67  mov     rax, [rax+40h]
0x180001e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e70  mov     rax, [rdi]
0x180001e73  lea     rdx, [rsp+0F8h+FileTime1]
0x180001e78  mov     rcx, rdi
0x180001e7b  mov     rax, [rax+68h]
0x180001e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e84  mov     rax, [rbp+0]
0x180001e88  lea     rdx, [rsp+0F8h+FileTime2]
0x180001e8d  mov     rcx, rbp
0x180001e90  mov     rax, [rax+68h]
0x180001e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e99  lea     rdx, [rsp+0F8h+FileTime2]; lpFileTime2
0x180001e9e  lea     rcx, [rsp+0F8h+FileTime1]; lpFileTime1
0x180001ea3  call    cs:__imp_CompareFileTime
0x180001ea9  test    eax, eax
0x180001eab  jnz     loc_18000697C
0x180001eb1  mov     eax, ebx
0x180001eb3  jmp     loc_180001E26
0x18000697c  mov     rax, [rdi]
0x18000697f  mov     rcx, rdi
0x180006982  mov     ebx, r13d
0x180006985  mov     rax, [rax+10h]
0x180006989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698e  mov     [r15], r13
0x180006991  lea     rcx, [rsp+0F8h+var_90]
0x180006996  mov     dword ptr [r14], 0Bh
0x18000699d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800069a3  mov     rcx, r12
0x1800069a6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800069ac  mov     rcx, rax
0x1800069af  lea     rdx, [rsp+0F8h+var_90]
0x1800069b4  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x1800069ba  test    eax, eax
0x1800069bc  js      short loc_1800069D2
0x1800069be  lea     rcx, [rsp+0F8h+var_90]
0x1800069c3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800069c9  mov     rcx, rax; lpFileName
0x1800069cc  call    cs:__imp_DeleteFileW
0x1800069d2  lea     rcx, [rsp+0F8h+var_90]
0x1800069d7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800069dd  nop
0x1800069de  jmp     loc_180001EB1
```
