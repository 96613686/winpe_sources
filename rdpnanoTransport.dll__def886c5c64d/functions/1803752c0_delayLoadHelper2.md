# __delayLoadHelper2

- ea: `0x1803752c0`
- end: `0x1803755ba`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180374c5f`

## callees

- `0x180374d98`
- `0x180374e84`
- `0x18037520c`
- `0x1803752c0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x180375411`
- `KERNEL32!LoadLibraryExA` at `0x180375411`
- `KERNEL32!GetLastError` at `0x18037541f`
- `KERNEL32!GetLastError` at `0x1803754f9`
- `KERNEL32!GetLastError` at `0x18037541f`
- `KERNEL32!GetLastError` at `0x1803754f9`
- `KERNEL32!FreeLibrary` at `0x180375482`
- `KERNEL32!FreeLibrary` at `0x180375482`
- `KERNEL32!RaiseException` at `0x18037536f`
- `KERNEL32!RaiseException` at `0x180375465`
- `KERNEL32!RaiseException` at `0x18037553f`
- `KERNEL32!RaiseException` at `0x18037536f`
- `KERNEL32!RaiseException` at `0x180375465`
- `KERNEL32!RaiseException` at `0x18037553f`
- `KERNEL32!GetProcAddress` at `0x1803754eb`
- `KERNEL32!GetProcAddress` at `0x1803754eb`

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
  GuardedWrite____delayLoadHelper2_::_2_::_lambda_1___(a2, 8u);
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
0x1803752c0  mov     [rsp-28h+arg_8], rbx
0x1803752c5  mov     [rsp-28h+arg_10], rsi
0x1803752ca  mov     [rsp-28h+arg_18], rdi
0x1803752cf  push    rbp
0x1803752d0  push    r12
0x1803752d2  push    r13
0x1803752d4  push    r14
0x1803752d6  push    r15
0x1803752d8  mov     rbp, rsp
0x1803752db  sub     rsp, 80h
0x1803752e2  mov     r15, rdx
0x1803752e5  mov     rsi, rcx
0x1803752e8  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1803752ed  mov     eax, [rsi+4]
0x1803752f0  lea     r8, __ImageBase
0x1803752f7  mov     r14d, [rsi+8]
0x1803752fb  add     rax, r8
0x1803752fe  mov     edx, [rsi+0Ch]
0x180375301  add     r14, r8
0x180375304  mov     ecx, [rsi+10h]
0x180375307  add     rdx, r8
0x18037530a  mov     r13d, [rsi+14h]
0x18037530e  add     rcx, r8
0x180375311  add     r13, r8
0x180375314  mov     [rbp+lpLibFileName], rax
0x180375318  mov     eax, [rsi]
0x18037531a  xorps   xmm0, xmm0
0x18037531d  mov     r8d, [rsi+1Ch]
0x180375321  mov     dword ptr [rbp+Arguments], r8d
0x180375325  mov     [rbp+var_50], 48h ; 'H'
0x18037532c  mov     [rbp+var_48], rsi
0x180375330  mov     [rbp+var_40], r15
0x180375334  mov     [rbp+var_20], 0
0x18037533c  mov     [rbp+var_18], 0
0x180375344  mov     [rbp+var_10], 0
0x18037534b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18037534f  test    al, 1
0x180375351  jnz     short loc_18037537C
0x180375353  lea     rax, [rbp+var_50]
0x180375357  mov     [rbp+Arguments], rax
0x18037535b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180375360  xor     edx, edx; dwExceptionFlags
0x180375362  lea     r9, [rbp+Arguments]; lpArguments
0x180375366  mov     ecx, 0C06D0057h; dwExceptionCode
0x18037536b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18037536f  call    cs:__imp_RaiseException
0x180375375  xor     eax, eax
0x180375377  jmp     loc_180375599
0x18037537c  mov     rbx, [r14]
0x18037537f  mov     r12, r15
0x180375382  sub     r12, rdx
0x180375385  sar     r12, 3
0x180375389  mov     r12d, r12d
0x18037538c  mov     rax, [rcx+r12*8]
0x180375390  shr     rax, 3Fh
0x180375394  xor     eax, 1
0x180375397  mov     dword ptr [rbp+lpProcName], eax
0x18037539a  jz      short loc_1803753B0
0x18037539c  mov     eax, [rcx+r12*8]
0x1803753a0  lea     rcx, word_180000002
0x1803753a7  add     rax, rcx
0x1803753aa  mov     [rbp+lpProcName+8], rax
0x1803753ae  jmp     short loc_1803753B8
0x1803753b0  movzx   eax, word ptr [rcx+r12*8]
0x1803753b5  mov     dword ptr [rbp+lpProcName+8], eax
0x1803753b8  mov     rax, cs:__pfnDliNotifyHook2
0x1803753bf  xor     edi, edi
0x1803753c1  test    rax, rax
0x1803753c4  jz      short loc_1803753E5
0x1803753c6  lea     rdx, [rbp+var_50]
0x1803753ca  xor     ecx, ecx
0x1803753cc  call    cs:__guard_dispatch_icall_fptr
0x1803753d2  mov     rdi, rax
0x1803753d5  test    rax, rax
0x1803753d8  jnz     loc_180375567
0x1803753de  mov     rax, cs:__pfnDliNotifyHook2
0x1803753e5  test    rbx, rbx
0x1803753e8  jnz     loc_18037548F
0x1803753ee  test    rax, rax
0x1803753f1  jz      short loc_180375408
0x1803753f3  lea     rdx, [rbp+var_50]
0x1803753f7  lea     ecx, [rbx+1]
0x1803753fa  call    cs:__guard_dispatch_icall_fptr
0x180375400  mov     rbx, rax
0x180375403  test    rax, rax
0x180375406  jnz     short loc_180375474
0x180375408  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18037540c  xor     r8d, r8d; dwFlags
0x18037540f  xor     edx, edx; hFile
0x180375411  call    cs:__imp_LoadLibraryExA
0x180375417  mov     rbx, rax
0x18037541a  test    rax, rax
0x18037541d  jnz     short loc_180375474
0x18037541f  call    cs:__imp_GetLastError
0x180375425  mov     [rbp+var_10], eax
0x180375428  mov     rax, cs:__pfnDliFailureHook2
0x18037542f  test    rax, rax
0x180375432  jz      short loc_180375449
0x180375434  lea     rdx, [rbp+var_50]
0x180375438  lea     ecx, [rbx+3]
0x18037543b  call    cs:__guard_dispatch_icall_fptr
0x180375441  mov     rbx, rax
0x180375444  test    rax, rax
0x180375447  jnz     short loc_180375474
0x180375449  lea     rax, [rbp+var_50]
0x18037544d  mov     [rbp+Arguments], rax
0x180375451  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180375456  xor     edx, edx; dwExceptionFlags
0x180375458  lea     r9, [rbp+Arguments]; lpArguments
0x18037545c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180375461  lea     r8d, [rdx+1]; nNumberOfArguments
0x180375465  call    cs:__imp_RaiseException
0x18037546b  mov     rax, [rbp+var_18]
0x18037546f  jmp     loc_180375599
0x180375474  mov     rax, rbx
0x180375477  xchg    rax, [r14]
0x18037547a  cmp     rax, rbx
0x18037547d  jnz     short loc_180375488
0x18037547f  mov     rcx, rbx; hLibModule
0x180375482  call    cs:__imp_FreeLibrary
0x180375488  mov     rax, cs:__pfnDliNotifyHook2
0x18037548f  mov     [rbp+var_20], rbx
0x180375493  test    rax, rax
0x180375496  jz      short loc_1803754AA
0x180375498  lea     rdx, [rbp+var_50]
0x18037549c  mov     ecx, 2
0x1803754a1  call    cs:__guard_dispatch_icall_fptr
0x1803754a7  mov     rdi, rax
0x1803754aa  test    rdi, rdi
0x1803754ad  jnz     loc_18037554E
0x1803754b3  cmp     [rsi+14h], edi
0x1803754b6  jz      short loc_1803754E4
0x1803754b8  cmp     [rsi+1Ch], edi
0x1803754bb  jz      short loc_1803754E4
0x1803754bd  movsxd  rax, dword ptr [rbx+3Ch]
0x1803754c1  cmp     dword ptr [rax+rbx], 4550h
0x1803754c8  jnz     short loc_1803754E4
0x1803754ca  mov     ecx, dword ptr [rbp+Arguments]
0x1803754cd  cmp     [rax+rbx+8], ecx
0x1803754d1  jnz     short loc_1803754E4
0x1803754d3  cmp     rbx, [rax+rbx+30h]
0x1803754d8  jnz     short loc_1803754E4
0x1803754da  mov     rdi, [r13+r12*8+0]
0x1803754df  test    rdi, rdi
0x1803754e2  jnz     short loc_18037554E
0x1803754e4  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x1803754e8  mov     rcx, rbx; hModule
0x1803754eb  call    cs:__imp_GetProcAddress
0x1803754f1  mov     rdi, rax
0x1803754f4  test    rax, rax
0x1803754f7  jnz     short loc_18037554E
0x1803754f9  call    cs:__imp_GetLastError
0x1803754ff  mov     [rbp+var_10], eax
0x180375502  mov     rax, cs:__pfnDliFailureHook2
0x180375509  test    rax, rax
0x18037550c  jz      short loc_180375523
0x18037550e  lea     rdx, [rbp+var_50]
0x180375512  lea     ecx, [rdi+4]
0x180375515  call    cs:__guard_dispatch_icall_fptr
0x18037551b  mov     rdi, rax
0x18037551e  test    rax, rax
0x180375521  jnz     short loc_18037554E
0x180375523  lea     rax, [rbp+var_50]
0x180375527  mov     [rbp+Arguments], rax
0x18037552b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180375530  xor     edx, edx; dwExceptionFlags
0x180375532  lea     r9, [rbp+Arguments]; lpArguments
0x180375536  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18037553b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18037553f  call    cs:__imp_RaiseException
0x180375545  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18037554a  mov     rdi, [rbp+var_18]
0x18037554e  lea     r8, [rbp+var_60]
0x180375552  mov     [rbp+var_60], r15
0x180375556  mov     edx, 8; dwSize
0x18037555b  mov     [rbp+var_58], rdi
0x18037555f  mov     rcx, r15; lpAddress
0x180375562  call    GuardedWrite____delayLoadHelper2____2____lambda_1___
0x180375567  mov     rax, cs:__pfnDliNotifyHook2
0x18037556e  test    rax, rax
0x180375571  jz      short loc_180375591
0x180375573  lea     rdx, [rbp+var_50]
0x180375577  mov     [rbp+var_10], 0
0x18037557e  mov     ecx, 5
0x180375583  mov     [rbp+var_20], rbx
0x180375587  mov     [rbp+var_18], rdi
0x18037558b  call    cs:__guard_dispatch_icall_fptr
0x180375591  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180375596  mov     rax, rdi
0x180375599  lea     r11, [rsp+80h+var_s0]
0x1803755a1  mov     rbx, [r11+38h]
0x1803755a5  mov     rsi, [r11+40h]
0x1803755a9  mov     rdi, [r11+48h]
0x1803755ad  mov     rsp, r11
0x1803755b0  pop     r15
0x1803755b2  pop     r14
0x1803755b4  pop     r13
0x1803755b6  pop     r12
0x1803755b8  pop     rbp
0x1803755b9  retn
```
