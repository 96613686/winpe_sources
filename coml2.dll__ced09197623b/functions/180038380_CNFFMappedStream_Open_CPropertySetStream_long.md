# CNFFMappedStream::Open(CPropertySetStream *,long *)

- ea: `0x180038380`
- end: `0x18003850f`
- name: `?Open@CNFFMappedStream@@UEAAXPEAVCPropertySetStream@@PEAJ@Z`
- size: `399`
- prototype: `void __fastcall(CNFFMappedStream *__hidden this, struct CPropertySetStream *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180038380`
- `0x180038518`
- `0x18003e3f8`
- `0x18003f974`
- `0x18003f9a0`
- `0x180042800`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003842c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003842c`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180038422`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180038422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800384ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800384ba`

## pseudocode

```c
void __fastcall CNFFMappedStream::Open(CNFFMappedStream *this, struct CPropertySetStream *a2, int *a3)
{
  signed int v6; // ebx
  void *v7; // rsi
  __int64 v8; // rcx
  signed int LastError; // eax
  DWORD nFileSizeLow; // eax
  SIZE_T v11; // rcx
  void *v12; // rax
  unsigned int v13; // r9d
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+30h] [rbp-68h] BYREF

  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 24LL))(
    *(_QWORD *)(*((_QWORD *)this + 1) + 104LL),
    0xFFFFFFFFLL);
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) == -1 )
  {
    v6 = -2147286782;
    goto LABEL_21;
  }
  v6 = CNFFMappedStream::RollForwardIfNecessary(this);
  if ( v6 < 0 )
  {
LABEL_21:
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    goto LABEL_22;
  }
  v7 = 0;
  CNFFMappedStream::BeginUsingLatestStream(this);
  if ( a2 )
    *((_QWORD *)this + 5) = a2;
  if ( !*((_QWORD *)this + 3) )
  {
    v8 = *((_QWORD *)this + 1);
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( !GetFileInformationByHandle(*(HANDLE *)(v8 + 96), &FileInformation) )
      goto LABEL_7;
    if ( FileInformation.nFileSizeHigh )
      goto LABEL_16;
    nFileSizeLow = FileInformation.nFileSizeLow;
    if ( FileInformation.nFileSizeLow > 0x200000 )
      goto LABEL_16;
    v11 = FileInformation.nFileSizeLow;
    *((_DWORD *)this + 9) = FileInformation.nFileSizeLow;
    *((_DWORD *)this + 8) = nFileSizeLow;
    v12 = CoTaskMemAlloc(v11);
    v7 = v12;
    if ( !v12 )
    {
      v6 = -2147024882;
      goto LABEL_17;
    }
    v13 = *((_DWORD *)this + 9);
    *((_QWORD *)this + 3) = v12;
    if ( v13 )
    {
      if ( CNtfsStream::SyncReadAtFile(*((CNtfsStream **)this + 1), 0, v12, v13, (unsigned int *)this + 8) < 0 )
      {
LABEL_7:
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_17;
      }
      if ( *((_DWORD *)this + 8) == *((_DWORD *)this + 9) )
        goto LABEL_17;
LABEL_16:
      v6 = -2147286789;
    }
  }
LABEL_17:
  CNFFMappedStream::EndUsingLatestStream(this);
  if ( v6 < 0 )
  {
    if ( v7 )
      CoTaskMemFree(v7);
    goto LABEL_21;
  }
LABEL_22:
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 104LL));
  *a3 = v6;
}

```

## disassembly

```asm
0x180038380  mov     [rsp+arg_8], rbx
0x180038385  push    rbp
0x180038386  push    rsi
0x180038387  push    rdi
0x180038388  push    r14
0x18003838a  push    r15
0x18003838c  sub     rsp, 70h
0x180038390  mov     rax, cs:__security_cookie
0x180038397  xor     rax, rsp
0x18003839a  mov     [rsp+98h+var_30], rax
0x18003839f  mov     rax, [rcx+8]
0x1800383a3  mov     rdi, rcx
0x1800383a6  mov     rbp, rdx
0x1800383a9  mov     r15, r8
0x1800383ac  or      edx, 0FFFFFFFFh
0x1800383af  mov     rcx, [rax+68h]
0x1800383b3  mov     rax, [rcx]
0x1800383b6  mov     rax, [rax+18h]
0x1800383ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383bf  mov     rax, [rdi+8]
0x1800383c3  cmp     qword ptr [rax+60h], 0FFFFFFFFFFFFFFFFh
0x1800383c8  jz      loc_1800384C2
0x1800383ce  mov     rcx, rdi; this
0x1800383d1  call    ?RollForwardIfNecessary@CNFFMappedStream@@AEAAJXZ; CNFFMappedStream::RollForwardIfNecessary(void)
0x1800383d6  mov     ebx, eax
0x1800383d8  test    eax, eax
0x1800383da  js      loc_1800384C7
0x1800383e0  mov     rcx, rdi; this
0x1800383e3  xor     esi, esi
0x1800383e5  call    ?BeginUsingLatestStream@CNFFMappedStream@@AEAAXXZ; CNFFMappedStream::BeginUsingLatestStream(void)
0x1800383ea  test    rbp, rbp
0x1800383ed  jz      short loc_1800383F3
0x1800383ef  mov     [rdi+28h], rbp
0x1800383f3  cmp     [rdi+18h], rsi
0x1800383f7  jnz     loc_1800384A6
0x1800383fd  mov     rcx, [rdi+8]
0x180038401  lea     rdx, [rsp+98h+FileInformation]; lpFileInformation
0x180038406  xorps   xmm0, xmm0
0x180038409  xor     eax, eax
0x18003840b  movups  xmmword ptr [rsp+98h+FileInformation.dwFileAttributes], xmm0
0x180038410  mov     [rsp+98h+FileInformation.nFileIndexLow], eax
0x180038414  movups  xmmword ptr [rsp+98h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180038419  movups  xmmword ptr [rsp+98h+FileInformation.nFileSizeHigh], xmm0
0x18003841e  mov     rcx, [rcx+60h]; hFile
0x180038422  call    cs:__imp_GetFileInformationByHandle
0x180038428  test    eax, eax
0x18003842a  jnz     short loc_180038443
0x18003842c  call    cs:__imp_GetLastError
0x180038432  mov     ebx, eax
0x180038434  test    eax, eax
0x180038436  jle     short loc_1800384A6
0x180038438  movzx   ebx, ax
0x18003843b  or      ebx, 80070000h
0x180038441  jmp     short loc_1800384A6
0x180038443  cmp     [rsp+98h+FileInformation.nFileSizeHigh], esi
0x180038447  jnz     short loc_1800384A1
0x180038449  mov     eax, [rsp+98h+FileInformation.nFileSizeLow]
0x18003844d  cmp     eax, 200000h
0x180038452  ja      short loc_1800384A1
0x180038454  mov     ecx, eax; cb
0x180038456  lea     r14, [rdi+20h]
0x18003845a  mov     [rdi+24h], ecx
0x18003845d  mov     [r14], eax
0x180038460  call    cs:__imp_CoTaskMemAlloc
0x180038466  mov     rsi, rax
0x180038469  test    rax, rax
0x18003846c  jnz     short loc_180038475
0x18003846e  mov     ebx, 8007000Eh
0x180038473  jmp     short loc_1800384A6
0x180038475  mov     r9d, [rdi+24h]; unsigned int
0x180038479  mov     [rdi+18h], rax
0x18003847d  test    r9d, r9d
0x180038480  jz      short loc_1800384A6
0x180038482  mov     rcx, [rdi+8]; this
0x180038486  xor     edx, edx; union _ULARGE_INTEGER
0x180038488  mov     r8, rax; void *
0x18003848b  mov     [rsp+98h+var_78], r14; unsigned int *
0x180038490  call    ?SyncReadAtFile@CNtfsStream@@AEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z; CNtfsStream::SyncReadAtFile(_ULARGE_INTEGER,void *,ulong,ulong *)
0x180038495  test    eax, eax
0x180038497  js      short loc_18003842C
0x180038499  mov     eax, [rdi+24h]
0x18003849c  cmp     [r14], eax
0x18003849f  jz      short loc_1800384A6
0x1800384a1  mov     ebx, 800300FBh
0x1800384a6  mov     rcx, rdi; this
0x1800384a9  call    ?EndUsingLatestStream@CNFFMappedStream@@AEAAXXZ; CNFFMappedStream::EndUsingLatestStream(void)
0x1800384ae  test    ebx, ebx
0x1800384b0  jns     short loc_1800384D7
0x1800384b2  test    rsi, rsi
0x1800384b5  jz      short loc_1800384C7
0x1800384b7  mov     rcx, rsi; pv
0x1800384ba  call    cs:__imp_CoTaskMemFree
0x1800384c0  jmp     short loc_1800384C7
0x1800384c2  mov     ebx, 80030102h
0x1800384c7  mov     qword ptr [rdi+18h], 0
0x1800384cf  mov     qword ptr [rdi+20h], 0
0x1800384d7  mov     rax, [rdi+8]
0x1800384db  mov     rcx, [rax+68h]
0x1800384df  mov     rax, [rcx]
0x1800384e2  mov     rax, [rax+20h]
0x1800384e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384eb  mov     [r15], ebx
0x1800384ee  mov     rcx, [rsp+98h+var_30]
0x1800384f3  xor     rcx, rsp; StackCookie
0x1800384f6  call    __security_check_cookie
0x1800384fb  mov     rbx, [rsp+98h+arg_8]
0x180038503  add     rsp, 70h
0x180038507  pop     r15
0x180038509  pop     r14
0x18003850b  pop     rdi
0x18003850c  pop     rsi
0x18003850d  pop     rbp
0x18003850e  retn
```
