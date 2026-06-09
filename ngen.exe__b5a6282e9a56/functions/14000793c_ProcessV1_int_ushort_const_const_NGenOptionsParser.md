# ProcessV1(int,ushort const * * const,NGenOptionsParser *)

- ea: `0x14000793c`
- end: `0x140007bab`
- name: `?ProcessV1@@YAJHQEAPEBGPEAVNGenOptionsParser@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **const, struct NGenOptionsParser *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140009104`

## callees

- `0x140001574`
- `0x14000793c`
- `0x14000a05c`
- `0x14000a0d4`
- `0x14000a10c`
- `0x140013200`
- `0x140013ce8`
- `0x140013f04`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x140007b1c`
- `KERNEL32!CreateProcessW` at `0x140007b1c`
- `KERNEL32!SetLastError` at `0x140007ac1`
- `KERNEL32!SetLastError` at `0x140007b42`
- `KERNEL32!SetLastError` at `0x140007ac1`
- `KERNEL32!SetLastError` at `0x140007b42`
- `KERNEL32!GetLastError` at `0x140007b24`
- `KERNEL32!GetLastError` at `0x140007b24`
- `KERNEL32!CloseHandle` at `0x140007b66`
- `KERNEL32!CloseHandle` at `0x140007b71`
- `KERNEL32!CloseHandle` at `0x140007b66`
- `KERNEL32!CloseHandle` at `0x140007b71`
- `KERNEL32!WaitForSingleObject` at `0x140007b5b`
- `KERNEL32!WaitForSingleObject` at `0x140007b5b`
- `ucrtbase_clr0400!wcscat_s` at `0x140007a3c`
- `ucrtbase_clr0400!wcscat_s` at `0x140007a4c`
- `ucrtbase_clr0400!wcscat_s` at `0x140007a3c`
- `ucrtbase_clr0400!wcscat_s` at `0x140007a4c`
- `mscoree!GetCORSystemDirectory` at `0x140007988`
- `mscoree!GetCORSystemDirectory` at `0x140007988`

## pseudocode

```c
__int64 __fastcall ProcessV1(int a1, const unsigned __int16 **const a2, struct NGenOptionsParser *a3)
{
  __int64 v4; // rbx
  int CORSystemDirectory; // esi
  __int64 v6; // rcx
  int v7; // edx
  __int64 v8; // r14
  __int64 v9; // rdi
  __int64 i; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // r15
  wchar_t *v13; // rbx
  __int64 v14; // rdi
  unsigned __int64 v15; // rdi
  unsigned __int128 v16; // rax
  WCHAR *v17; // rax
  WCHAR *v18; // r14
  BOOL v19; // r15d
  BOOL v20; // edi
  DWORD LastError; // r12d
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v24; // [rsp+58h] [rbp-A8h]
  BOOL v25; // [rsp+60h] [rbp-A0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _WORD v28[264]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = a1;
  v23 = 0;
  CORSystemDirectory = GetCORSystemDirectory(v28, 260, &v23);
  if ( CORSystemDirectory >= 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v28[v6] );
    v7 = v6 + v4 + 7;
    v8 = v4;
    v9 = 1;
    if ( v4 > 1 )
    {
      for ( i = 1; i < v4; ++i )
      {
        v11 = -1;
        do
          ++v11;
        while ( a2[i][v11] );
        v7 += v11;
      }
    }
    v12 = v7 + 9;
    v13 = (wchar_t *)operator new(saturated_mul(v12, 2u));
    if ( !v13 )
      return (unsigned int)-2147024882;
    StringCchPrintfW(v13, v12, L"%s%s /nologo", v28, L"ngen.exe");
    if ( v8 > 1 )
    {
      do
      {
        wcscat_s(v13, v12, L" ");
        wcscat_s(v13, v12, a2[v9++]);
      }
      while ( v9 < v8 );
    }
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v15 = v14 + 1;
    v16 = v15 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v15, 2u) )
      *(_QWORD *)&v16 = -1;
    v17 = (WCHAR *)operator new[](v16, *((const struct NoThrow **)&v16 + 1));
    v18 = v17;
    v24 = v17;
    v19 = v17 != 0;
    v25 = v19;
    if ( v17 )
    {
      memcpy_0(v17, v13, 2 * v15);
      v20 = CreateProcessW(0, v18, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation);
      LastError = GetLastError();
      if ( v19 )
      {
        operator delete(v18);
        v25 = 0;
      }
      SetLastError(LastError);
      if ( v20 )
      {
        WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
        goto LABEL_25;
      }
    }
    else
    {
      SetLastError(0xEu);
      if ( v19 )
      {
        operator delete(0);
        v25 = 0;
      }
    }
    CORSystemDirectory = -2147467259;
LABEL_25:
    operator delete(v13);
  }
  return (unsigned int)CORSystemDirectory;
}

```

## disassembly

```asm
0x14000793c  mov     [rsp-8+arg_10], rbx
0x140007941  push    rbp
0x140007942  push    rsi
0x140007943  push    rdi
0x140007944  push    r12
0x140007946  push    r13
0x140007948  push    r14
0x14000794a  push    r15
0x14000794c  lea     rbp, [rsp-210h]
0x140007954  sub     rsp, 310h
0x14000795b  mov     rax, cs:__security_cookie
0x140007962  xor     rax, rsp
0x140007965  mov     [rbp+240h+var_40], rax
0x14000796c  mov     r12, rdx
0x14000796f  movsxd  rbx, ecx
0x140007972  xor     r13d, r13d
0x140007975  mov     [rsp+340h+var_2F0], r13d
0x14000797a  lea     r8, [rsp+340h+var_2F0]
0x14000797f  mov     edx, 104h
0x140007984  lea     rcx, [rbp+240h+var_250]
0x140007988  call    cs:__imp_GetCORSystemDirectory
0x14000798e  mov     esi, eax
0x140007990  test    eax, eax
0x140007992  js      loc_140007B7F
0x140007998  lea     rax, [rbp+240h+var_250]
0x14000799c  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400079a0  mov     rcx, r9
0x1400079a3  inc     rcx
0x1400079a6  cmp     [rax+rcx*2], r13w
0x1400079ab  jnz     short loc_1400079A3
0x1400079ad  lea     edx, [rbx+7]
0x1400079b0  add     edx, ecx
0x1400079b2  mov     r14, rbx
0x1400079b5  mov     edi, 1
0x1400079ba  cmp     rbx, rdi
0x1400079bd  jle     short loc_1400079DC
0x1400079bf  mov     eax, edi
0x1400079c1  mov     r8, [r12+rax*8]
0x1400079c5  mov     rcx, r9
0x1400079c8  inc     rcx
0x1400079cb  cmp     [r8+rcx*2], r13w
0x1400079d0  jnz     short loc_1400079C8
0x1400079d2  add     edx, ecx
0x1400079d4  add     rax, rdi
0x1400079d7  cmp     rax, r14
0x1400079da  jl      short loc_1400079C1
0x1400079dc  lea     eax, [rdx+9]
0x1400079df  movsxd  r15, eax
0x1400079e2  mov     eax, 2
0x1400079e7  mul     r15
0x1400079ea  cmovo   rax, r9
0x1400079ee  mov     rcx, rax; dwBytes
0x1400079f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400079f6  mov     rbx, rax
0x1400079f9  test    rax, rax
0x1400079fc  jnz     short loc_140007A08
0x1400079fe  mov     esi, 8007000Eh
0x140007a03  jmp     loc_140007B7F
0x140007a08  lea     rax, ModuleName; "ngen.exe"
0x140007a0f  mov     qword ptr [rsp+340h+bInheritHandles], rax
0x140007a14  lea     r9, [rbp+240h+var_250]
0x140007a18  lea     r8, aSSNologo; "%s%s /nologo"
0x140007a1f  mov     rdx, r15; unsigned __int64
0x140007a22  mov     rcx, rbx; Buffer
0x140007a25  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007a2a  cmp     r14, rdi
0x140007a2d  jle     short loc_140007A5A
0x140007a2f  lea     r8, Source; " "
0x140007a36  mov     rdx, r15; SizeInWords
0x140007a39  mov     rcx, rbx; Destination
0x140007a3c  call    cs:__imp_wcscat_s
0x140007a42  mov     r8, [r12+rdi*8]; Source
0x140007a46  mov     rdx, r15; SizeInWords
0x140007a49  mov     rcx, rbx; Destination
0x140007a4c  call    cs:__imp_wcscat_s
0x140007a52  inc     rdi
0x140007a55  cmp     rdi, r14
0x140007a58  jl      short loc_140007A2F
0x140007a5a  xor     edx, edx; Val
0x140007a5c  lea     r8d, [rdx+64h]; Size
0x140007a60  lea     rcx, [rbp+240h+StartupInfo+4]; void *
0x140007a64  call    memset_0
0x140007a69  mov     [rbp+240h+StartupInfo.cb], 68h ; 'h'
0x140007a70  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140007a74  mov     rdi, rcx
0x140007a77  inc     rdi
0x140007a7a  cmp     [rbx+rdi*2], r13w
0x140007a7f  jnz     short loc_140007A77
0x140007a81  mov     r12d, 1
0x140007a87  add     rdi, r12
0x140007a8a  lea     eax, [r12+1]
0x140007a8f  mul     rdi
0x140007a92  cmovo   rax, rcx
0x140007a96  mov     rcx, rax; dwBytes
0x140007a99  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x140007a9e  mov     r14, rax
0x140007aa1  mov     [rsp+340h+var_2E8], rax
0x140007aa6  mov     [rsp+340h+var_2E0], r13d
0x140007aab  mov     r15d, r13d
0x140007aae  test    rax, rax
0x140007ab1  cmovnz  r15d, r12d
0x140007ab5  mov     [rsp+340h+var_2E0], r15d
0x140007aba  jnz     short loc_140007ADB
0x140007abc  lea     ecx, [r12+0Dh]; dwErrCode
0x140007ac1  call    cs:__imp_SetLastError
0x140007ac7  nop
0x140007ac8  test    r15d, r15d
0x140007acb  jz      short loc_140007B4C
0x140007acd  xor     ecx, ecx; lpMem
0x140007acf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007ad4  mov     [rsp+340h+var_2E0], r13d
0x140007ad9  jmp     short loc_140007B4C
0x140007adb  lea     r8, [rdi+rdi]; Size
0x140007adf  mov     rdx, rbx; Src
0x140007ae2  mov     rcx, r14; void *
0x140007ae5  call    memcpy_0
0x140007aea  lea     rax, [rsp+340h+ProcessInformation]
0x140007aef  mov     [rsp+340h+lpProcessInformation], rax; lpProcessInformation
0x140007af4  lea     rax, [rbp+240h+StartupInfo]
0x140007af8  mov     [rsp+340h+lpStartupInfo], rax; lpStartupInfo
0x140007afd  mov     [rsp+340h+lpCurrentDirectory], r13; lpCurrentDirectory
0x140007b02  mov     [rsp+340h+lpEnvironment], r13; lpEnvironment
0x140007b07  mov     [rsp+340h+dwCreationFlags], r13d; dwCreationFlags
0x140007b0c  mov     [rsp+340h+bInheritHandles], r13d; bInheritHandles
0x140007b11  xor     r9d, r9d; lpThreadAttributes
0x140007b14  xor     r8d, r8d; lpProcessAttributes
0x140007b17  mov     rdx, r14; lpCommandLine
0x140007b1a  xor     ecx, ecx; lpApplicationName
0x140007b1c  call    cs:__imp_CreateProcessW
0x140007b22  mov     edi, eax
0x140007b24  call    cs:__imp_GetLastError
0x140007b2a  mov     r12d, eax
0x140007b2d  test    r15d, r15d
0x140007b30  jz      short loc_140007B3F
0x140007b32  mov     rcx, r14; lpMem
0x140007b35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007b3a  mov     [rsp+340h+var_2E0], r13d
0x140007b3f  mov     ecx, r12d; dwErrCode
0x140007b42  call    cs:__imp_SetLastError
0x140007b48  test    edi, edi
0x140007b4a  jnz     short loc_140007B53
0x140007b4c  mov     esi, 80004005h
0x140007b51  jmp     short loc_140007B77
0x140007b53  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007b56  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hHandle
0x140007b5b  call    cs:__imp_WaitForSingleObject
0x140007b61  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hObject
0x140007b66  call    cs:__imp_CloseHandle
0x140007b6c  mov     rcx, [rsp+340h+ProcessInformation.hThread]; hObject
0x140007b71  call    cs:__imp_CloseHandle
0x140007b77  mov     rcx, rbx; lpMem
0x140007b7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007b7f  mov     eax, esi
0x140007b81  mov     rcx, [rbp+240h+var_40]
0x140007b88  xor     rcx, rsp; StackCookie
0x140007b8b  call    __security_check_cookie
0x140007b90  mov     rbx, [rsp+340h+arg_10]
0x140007b98  add     rsp, 310h
0x140007b9f  pop     r15
0x140007ba1  pop     r14
0x140007ba3  pop     r13
0x140007ba5  pop     r12
0x140007ba7  pop     rdi
0x140007ba8  pop     rsi
0x140007ba9  pop     rbp
0x140007baa  retn
```
