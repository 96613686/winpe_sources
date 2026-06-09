# __delayLoadHelper2

- ea: `0x18019f2c0`
- end: `0x18019f5ba`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801972fd`
- `0x180197766`
- `0x180197803`
- `0x1801978ac`
- `0x180197955`

## callees

- `0x18019ed9c`
- `0x18019ee88`
- `0x18019f210`
- `0x18019f2c0`
- `0x18019f7a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18019f41f`
- `KERNEL32!GetLastError` at `0x18019f4f9`
- `KERNEL32!GetLastError` at `0x18019f41f`
- `KERNEL32!GetLastError` at `0x18019f4f9`
- `KERNEL32!GetProcAddress` at `0x18019f4eb`
- `KERNEL32!GetProcAddress` at `0x18019f4eb`
- `KERNEL32!FreeLibrary` at `0x18019f482`
- `KERNEL32!FreeLibrary` at `0x18019f482`
- `KERNEL32!LoadLibraryExA` at `0x18019f411`
- `KERNEL32!LoadLibraryExA` at `0x18019f411`
- `KERNEL32!RaiseException` at `0x18019f36f`
- `KERNEL32!RaiseException` at `0x18019f465`
- `KERNEL32!RaiseException` at `0x18019f53f`
- `KERNEL32!RaiseException` at `0x18019f36f`
- `KERNEL32!RaiseException` at `0x18019f465`
- `KERNEL32!RaiseException` at `0x18019f53f`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile __int64 *v4; // r14
  char *v5; // rdx
  char *v6; // rcx
  char *v7; // r13
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v11; // r12
  bool v12; // zf
  PfnDliHook v13; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  __int64 v15; // rax
  struct DelayLoadInfo v16; // [rsp+30h] [rbp-50h] BYREF
  ULONG_PTR Arguments; // [rsp+B0h] [rbp+30h] BYREF

  DloadAcquireSectionWriteAccess();
  v4 = (volatile __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  v5 = (char *)&_ImageBase + a1->rvaIAT;
  v6 = (char *)&_ImageBase + a1->rvaINT;
  v7 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v16.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = a1->dwTimeStamp;
  v16.cb = 72;
  v16.pidd = a1;
  v16.ppfn = a2;
  memset(&v16.dlp, 0, 36);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v16;
    DloadReleaseSectionWriteAccess();
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v11 = (unsigned int)(((char *)a2 - v5) >> 3);
  v12 = *(__int64 *)&v6[8 * v11] < 0;
  v16.dlp.fImportByName = *(_QWORD *)&v6[8 * v11] >= 0LL;
  if ( v12 )
    v16.dlp.dwOrdinal = *(unsigned __int16 *)&v6[8 * v11];
  else
    v16.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)&v6[8 * v11];
  v13 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( _pfnDliNotifyHook2 )
  {
    ProcAddress = _pfnDliNotifyHook2(0, &v16);
    if ( ProcAddress )
      goto LABEL_33;
    v13 = _pfnDliNotifyHook2;
  }
  if ( !Library )
  {
    if ( !v13 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v13)(1, &v16)) == 0 )
    {
      Library = LoadLibraryExA(v16.szDll, 0, 0);
      if ( !Library )
      {
        v16.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (Library = (HMODULE)_pfnDliFailureHook2(3u, &v16)) == 0 )
        {
          Arguments = (ULONG_PTR)&v16;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007E, 0, 1u, &Arguments);
          return v16.pfnCur;
        }
      }
    }
    if ( (HMODULE)_InterlockedExchange64(v4, (__int64)Library) == Library )
      FreeLibrary(Library);
    v13 = _pfnDliNotifyHook2;
  }
  v16.hmodCur = Library;
  if ( v13 )
    ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v13)(2, &v16);
  if ( !ProcAddress )
  {
    if ( !a1->rvaBoundIAT
      || !a1->dwTimeStamp
      || (v15 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v15) != 17744)
      || *(_DWORD *)((char *)Library + v15 + 8) != (_DWORD)Arguments
      || Library != *(HMODULE *)((char *)Library + v15 + 48)
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v7[8 * v11]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, v16.dlp.szProcName);
      if ( !ProcAddress )
      {
        v16.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (ProcAddress = _pfnDliFailureHook2(4u, &v16)) == 0 )
        {
          Arguments = (ULONG_PTR)&v16;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007F, 0, 1u, &Arguments);
          DloadAcquireSectionWriteAccess();
          ProcAddress = v16.pfnCur;
        }
      }
    }
  }
  sub_18019ED9C(a2, 8u);
LABEL_33:
  if ( _pfnDliNotifyHook2 )
  {
    v16.dwLastError = 0;
    v16.hmodCur = Library;
    v16.pfnCur = ProcAddress;
    _pfnDliNotifyHook2(5u, &v16);
  }
  DloadReleaseSectionWriteAccess();
  return ProcAddress;
}

```

## disassembly

```asm
0x18019f2c0  mov     [rsp-28h+arg_8], rbx
0x18019f2c5  mov     [rsp-28h+arg_10], rsi
0x18019f2ca  mov     [rsp-28h+arg_18], rdi
0x18019f2cf  push    rbp
0x18019f2d0  push    r12
0x18019f2d2  push    r13
0x18019f2d4  push    r14
0x18019f2d6  push    r15
0x18019f2d8  mov     rbp, rsp
0x18019f2db  sub     rsp, 80h
0x18019f2e2  mov     r15, rdx
0x18019f2e5  mov     rsi, rcx
0x18019f2e8  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18019f2ed  mov     eax, [rsi+4]
0x18019f2f0  lea     r8, __ImageBase
0x18019f2f7  mov     r14d, [rsi+8]
0x18019f2fb  add     rax, r8
0x18019f2fe  mov     edx, [rsi+0Ch]
0x18019f301  add     r14, r8
0x18019f304  mov     ecx, [rsi+10h]
0x18019f307  add     rdx, r8
0x18019f30a  mov     r13d, [rsi+14h]
0x18019f30e  add     rcx, r8
0x18019f311  add     r13, r8
0x18019f314  mov     [rbp+lpLibFileName], rax
0x18019f318  mov     eax, [rsi]
0x18019f31a  xorps   xmm0, xmm0
0x18019f31d  mov     r8d, [rsi+1Ch]
0x18019f321  mov     dword ptr [rbp+Arguments], r8d
0x18019f325  mov     [rbp+var_50], 48h ; 'H'
0x18019f32c  mov     [rbp+var_48], rsi
0x18019f330  mov     [rbp+var_40], r15
0x18019f334  mov     [rbp+var_20], 0
0x18019f33c  mov     [rbp+var_18], 0
0x18019f344  mov     [rbp+var_10], 0
0x18019f34b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18019f34f  test    al, 1
0x18019f351  jnz     short loc_18019F37C
0x18019f353  lea     rax, [rbp+var_50]
0x18019f357  mov     [rbp+Arguments], rax
0x18019f35b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18019f360  xor     edx, edx; dwExceptionFlags
0x18019f362  lea     r9, [rbp+Arguments]; lpArguments
0x18019f366  mov     ecx, 0C06D0057h; dwExceptionCode
0x18019f36b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18019f36f  call    cs:__imp_RaiseException
0x18019f375  xor     eax, eax
0x18019f377  jmp     loc_18019F599
0x18019f37c  mov     rbx, [r14]
0x18019f37f  mov     r12, r15
0x18019f382  sub     r12, rdx
0x18019f385  sar     r12, 3
0x18019f389  mov     r12d, r12d
0x18019f38c  mov     rax, [rcx+r12*8]
0x18019f390  shr     rax, 3Fh
0x18019f394  xor     eax, 1
0x18019f397  mov     dword ptr [rbp+lpProcName], eax
0x18019f39a  jz      short loc_18019F3B0
0x18019f39c  mov     eax, [rcx+r12*8]
0x18019f3a0  lea     rcx, word_180000002
0x18019f3a7  add     rax, rcx
0x18019f3aa  mov     [rbp+lpProcName+8], rax
0x18019f3ae  jmp     short loc_18019F3B8
0x18019f3b0  movzx   eax, word ptr [rcx+r12*8]
0x18019f3b5  mov     dword ptr [rbp+lpProcName+8], eax
0x18019f3b8  mov     rax, cs:__pfnDliNotifyHook2
0x18019f3bf  xor     edi, edi
0x18019f3c1  test    rax, rax
0x18019f3c4  jz      short loc_18019F3E5
0x18019f3c6  lea     rdx, [rbp+var_50]
0x18019f3ca  xor     ecx, ecx
0x18019f3cc  call    cs:__guard_dispatch_icall_fptr
0x18019f3d2  mov     rdi, rax
0x18019f3d5  test    rax, rax
0x18019f3d8  jnz     loc_18019F567
0x18019f3de  mov     rax, cs:__pfnDliNotifyHook2
0x18019f3e5  test    rbx, rbx
0x18019f3e8  jnz     loc_18019F48F
0x18019f3ee  test    rax, rax
0x18019f3f1  jz      short loc_18019F408
0x18019f3f3  lea     rdx, [rbp+var_50]
0x18019f3f7  lea     ecx, [rbx+1]
0x18019f3fa  call    cs:__guard_dispatch_icall_fptr
0x18019f400  mov     rbx, rax
0x18019f403  test    rax, rax
0x18019f406  jnz     short loc_18019F474
0x18019f408  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18019f40c  xor     r8d, r8d; dwFlags
0x18019f40f  xor     edx, edx; hFile
0x18019f411  call    cs:__imp_LoadLibraryExA
0x18019f417  mov     rbx, rax
0x18019f41a  test    rax, rax
0x18019f41d  jnz     short loc_18019F474
0x18019f41f  call    cs:__imp_GetLastError
0x18019f425  mov     [rbp+var_10], eax
0x18019f428  mov     rax, cs:__pfnDliFailureHook2
0x18019f42f  test    rax, rax
0x18019f432  jz      short loc_18019F449
0x18019f434  lea     rdx, [rbp+var_50]
0x18019f438  lea     ecx, [rbx+3]
0x18019f43b  call    cs:__guard_dispatch_icall_fptr
0x18019f441  mov     rbx, rax
0x18019f444  test    rax, rax
0x18019f447  jnz     short loc_18019F474
0x18019f449  lea     rax, [rbp+var_50]
0x18019f44d  mov     [rbp+Arguments], rax
0x18019f451  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18019f456  xor     edx, edx; dwExceptionFlags
0x18019f458  lea     r9, [rbp+Arguments]; lpArguments
0x18019f45c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18019f461  lea     r8d, [rdx+1]; nNumberOfArguments
0x18019f465  call    cs:__imp_RaiseException
0x18019f46b  mov     rax, [rbp+var_18]
0x18019f46f  jmp     loc_18019F599
0x18019f474  mov     rax, rbx
0x18019f477  xchg    rax, [r14]
0x18019f47a  cmp     rax, rbx
0x18019f47d  jnz     short loc_18019F488
0x18019f47f  mov     rcx, rbx; hLibModule
0x18019f482  call    cs:__imp_FreeLibrary
0x18019f488  mov     rax, cs:__pfnDliNotifyHook2
0x18019f48f  mov     [rbp+var_20], rbx
0x18019f493  test    rax, rax
0x18019f496  jz      short loc_18019F4AA
0x18019f498  lea     rdx, [rbp+var_50]
0x18019f49c  mov     ecx, 2
0x18019f4a1  call    cs:__guard_dispatch_icall_fptr
0x18019f4a7  mov     rdi, rax
0x18019f4aa  test    rdi, rdi
0x18019f4ad  jnz     loc_18019F54E
0x18019f4b3  cmp     [rsi+14h], edi
0x18019f4b6  jz      short loc_18019F4E4
0x18019f4b8  cmp     [rsi+1Ch], edi
0x18019f4bb  jz      short loc_18019F4E4
0x18019f4bd  movsxd  rax, dword ptr [rbx+3Ch]
0x18019f4c1  cmp     dword ptr [rax+rbx], 4550h
0x18019f4c8  jnz     short loc_18019F4E4
0x18019f4ca  mov     ecx, dword ptr [rbp+Arguments]
0x18019f4cd  cmp     [rax+rbx+8], ecx
0x18019f4d1  jnz     short loc_18019F4E4
0x18019f4d3  cmp     rbx, [rax+rbx+30h]
0x18019f4d8  jnz     short loc_18019F4E4
0x18019f4da  mov     rdi, [r13+r12*8+0]
0x18019f4df  test    rdi, rdi
0x18019f4e2  jnz     short loc_18019F54E
0x18019f4e4  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x18019f4e8  mov     rcx, rbx; hModule
0x18019f4eb  call    cs:__imp_GetProcAddress
0x18019f4f1  mov     rdi, rax
0x18019f4f4  test    rax, rax
0x18019f4f7  jnz     short loc_18019F54E
0x18019f4f9  call    cs:__imp_GetLastError
0x18019f4ff  mov     [rbp+var_10], eax
0x18019f502  mov     rax, cs:__pfnDliFailureHook2
0x18019f509  test    rax, rax
0x18019f50c  jz      short loc_18019F523
0x18019f50e  lea     rdx, [rbp+var_50]
0x18019f512  lea     ecx, [rdi+4]
0x18019f515  call    cs:__guard_dispatch_icall_fptr
0x18019f51b  mov     rdi, rax
0x18019f51e  test    rax, rax
0x18019f521  jnz     short loc_18019F54E
0x18019f523  lea     rax, [rbp+var_50]
0x18019f527  mov     [rbp+Arguments], rax
0x18019f52b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18019f530  xor     edx, edx; dwExceptionFlags
0x18019f532  lea     r9, [rbp+Arguments]; lpArguments
0x18019f536  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18019f53b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18019f53f  call    cs:__imp_RaiseException
0x18019f545  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18019f54a  mov     rdi, [rbp+var_18]
0x18019f54e  lea     r8, [rbp+var_60]
0x18019f552  mov     [rbp+var_60], r15
0x18019f556  mov     edx, 8; dwSize
0x18019f55b  mov     [rbp+var_58], rdi
0x18019f55f  mov     rcx, r15; lpAddress
0x18019f562  call    sub_18019ED9C
0x18019f567  mov     rax, cs:__pfnDliNotifyHook2
0x18019f56e  test    rax, rax
0x18019f571  jz      short loc_18019F591
0x18019f573  lea     rdx, [rbp+var_50]
0x18019f577  mov     [rbp+var_10], 0
0x18019f57e  mov     ecx, 5
0x18019f583  mov     [rbp+var_20], rbx
0x18019f587  mov     [rbp+var_18], rdi
0x18019f58b  call    cs:__guard_dispatch_icall_fptr
0x18019f591  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18019f596  mov     rax, rdi
0x18019f599  lea     r11, [rsp+80h+var_s0]
0x18019f5a1  mov     rbx, [r11+38h]
0x18019f5a5  mov     rsi, [r11+40h]
0x18019f5a9  mov     rdi, [r11+48h]
0x18019f5ad  mov     rsp, r11
0x18019f5b0  pop     r15
0x18019f5b2  pop     r14
0x18019f5b4  pop     r13
0x18019f5b6  pop     r12
0x18019f5b8  pop     rbp
0x18019f5b9  retn
```
