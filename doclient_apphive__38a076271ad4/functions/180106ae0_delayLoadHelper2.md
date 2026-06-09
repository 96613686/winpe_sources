# __delayLoadHelper2

- ea: `0x180106ae0`
- end: `0x180106dda`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800f7cfd`
- `0x1800f7da6`
- `0x1800f7e3d`
- `0x180106e52`
- `0x180107045`
- `0x1801070d0`
- `0x1801071df`
- `0x18010726a`
- `0x1801072f5`
- `0x1801073a4`
- `0x1801075fd`
- `0x1801078b6`
- `0x180108b67`

## callees

- `0x180106594`
- `0x180106688`
- `0x180106a2c`
- `0x180106ae0`
- `0x180108e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180106b8f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180106c85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180106d5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180106b8f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180106c85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180106d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106d19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106d0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106d0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180106ca2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180106ca2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180106c31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180106c31`

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
0x180106ae0  mov     [rsp-28h+arg_8], rbx
0x180106ae5  mov     [rsp-28h+arg_10], rsi
0x180106aea  mov     [rsp-28h+arg_18], rdi
0x180106aef  push    rbp
0x180106af0  push    r12
0x180106af2  push    r13
0x180106af4  push    r14
0x180106af6  push    r15
0x180106af8  mov     rbp, rsp
0x180106afb  sub     rsp, 80h
0x180106b02  mov     r15, rdx
0x180106b05  mov     rsi, rcx
0x180106b08  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x180106b0d  mov     eax, [rsi+4]
0x180106b10  lea     r8, __ImageBase
0x180106b17  mov     r14d, [rsi+8]
0x180106b1b  add     rax, r8
0x180106b1e  mov     edx, [rsi+0Ch]
0x180106b21  add     r14, r8
0x180106b24  mov     ecx, [rsi+10h]
0x180106b27  add     rdx, r8
0x180106b2a  mov     r13d, [rsi+14h]
0x180106b2e  add     rcx, r8
0x180106b31  add     r13, r8
0x180106b34  mov     [rbp+lpLibFileName], rax
0x180106b38  mov     eax, [rsi]
0x180106b3a  xorps   xmm0, xmm0
0x180106b3d  mov     r8d, [rsi+1Ch]
0x180106b41  mov     dword ptr [rbp+Arguments], r8d
0x180106b45  mov     [rbp+var_50], 48h ; 'H'
0x180106b4c  mov     [rbp+var_48], rsi
0x180106b50  mov     [rbp+var_40], r15
0x180106b54  mov     [rbp+var_20], 0
0x180106b5c  mov     [rbp+var_18], 0
0x180106b64  mov     [rbp+var_10], 0
0x180106b6b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x180106b6f  test    al, 1
0x180106b71  jnz     short loc_180106B9C
0x180106b73  lea     rax, [rbp+var_50]
0x180106b77  mov     [rbp+Arguments], rax
0x180106b7b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180106b80  xor     edx, edx; dwExceptionFlags
0x180106b82  lea     r9, [rbp+Arguments]; lpArguments
0x180106b86  mov     ecx, 0C06D0057h; dwExceptionCode
0x180106b8b  lea     r8d, [rdx+1]; nNumberOfArguments
0x180106b8f  call    cs:__imp_RaiseException
0x180106b95  xor     eax, eax
0x180106b97  jmp     loc_180106DB9
0x180106b9c  mov     rbx, [r14]
0x180106b9f  mov     r12, r15
0x180106ba2  sub     r12, rdx
0x180106ba5  sar     r12, 3
0x180106ba9  mov     r12d, r12d
0x180106bac  mov     rax, [rcx+r12*8]
0x180106bb0  shr     rax, 3Fh
0x180106bb4  xor     eax, 1
0x180106bb7  mov     dword ptr [rbp+lpProcName], eax
0x180106bba  jz      short loc_180106BD0
0x180106bbc  mov     eax, [rcx+r12*8]
0x180106bc0  lea     rcx, word_180000002
0x180106bc7  add     rax, rcx
0x180106bca  mov     [rbp+lpProcName+8], rax
0x180106bce  jmp     short loc_180106BD8
0x180106bd0  movzx   eax, word ptr [rcx+r12*8]
0x180106bd5  mov     dword ptr [rbp+lpProcName+8], eax
0x180106bd8  mov     rax, cs:__pfnDliNotifyHook2
0x180106bdf  xor     edi, edi
0x180106be1  test    rax, rax
0x180106be4  jz      short loc_180106C05
0x180106be6  lea     rdx, [rbp+var_50]
0x180106bea  xor     ecx, ecx
0x180106bec  call    cs:__guard_dispatch_icall_fptr
0x180106bf2  mov     rdi, rax
0x180106bf5  test    rax, rax
0x180106bf8  jnz     loc_180106D87
0x180106bfe  mov     rax, cs:__pfnDliNotifyHook2
0x180106c05  test    rbx, rbx
0x180106c08  jnz     loc_180106CAF
0x180106c0e  test    rax, rax
0x180106c11  jz      short loc_180106C28
0x180106c13  lea     rdx, [rbp+var_50]
0x180106c17  lea     ecx, [rbx+1]
0x180106c1a  call    cs:__guard_dispatch_icall_fptr
0x180106c20  mov     rbx, rax
0x180106c23  test    rax, rax
0x180106c26  jnz     short loc_180106C94
0x180106c28  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180106c2c  xor     r8d, r8d; dwFlags
0x180106c2f  xor     edx, edx; hFile
0x180106c31  call    cs:__imp_LoadLibraryExA
0x180106c37  mov     rbx, rax
0x180106c3a  test    rax, rax
0x180106c3d  jnz     short loc_180106C94
0x180106c3f  call    cs:__imp_GetLastError
0x180106c45  mov     [rbp+var_10], eax
0x180106c48  mov     rax, cs:__pfnDliFailureHook2
0x180106c4f  test    rax, rax
0x180106c52  jz      short loc_180106C69
0x180106c54  lea     rdx, [rbp+var_50]
0x180106c58  lea     ecx, [rbx+3]
0x180106c5b  call    cs:__guard_dispatch_icall_fptr
0x180106c61  mov     rbx, rax
0x180106c64  test    rax, rax
0x180106c67  jnz     short loc_180106C94
0x180106c69  lea     rax, [rbp+var_50]
0x180106c6d  mov     [rbp+Arguments], rax
0x180106c71  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180106c76  xor     edx, edx; dwExceptionFlags
0x180106c78  lea     r9, [rbp+Arguments]; lpArguments
0x180106c7c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180106c81  lea     r8d, [rdx+1]; nNumberOfArguments
0x180106c85  call    cs:__imp_RaiseException
0x180106c8b  mov     rax, [rbp+var_18]
0x180106c8f  jmp     loc_180106DB9
0x180106c94  mov     rax, rbx
0x180106c97  xchg    rax, [r14]
0x180106c9a  cmp     rax, rbx
0x180106c9d  jnz     short loc_180106CA8
0x180106c9f  mov     rcx, rbx; hLibModule
0x180106ca2  call    cs:__imp_FreeLibrary
0x180106ca8  mov     rax, cs:__pfnDliNotifyHook2
0x180106caf  mov     [rbp+var_20], rbx
0x180106cb3  test    rax, rax
0x180106cb6  jz      short loc_180106CCA
0x180106cb8  lea     rdx, [rbp+var_50]
0x180106cbc  mov     ecx, 2
0x180106cc1  call    cs:__guard_dispatch_icall_fptr
0x180106cc7  mov     rdi, rax
0x180106cca  test    rdi, rdi
0x180106ccd  jnz     loc_180106D6E
0x180106cd3  cmp     [rsi+14h], edi
0x180106cd6  jz      short loc_180106D04
0x180106cd8  cmp     [rsi+1Ch], edi
0x180106cdb  jz      short loc_180106D04
0x180106cdd  movsxd  rax, dword ptr [rbx+3Ch]
0x180106ce1  cmp     dword ptr [rax+rbx], 4550h
0x180106ce8  jnz     short loc_180106D04
0x180106cea  mov     ecx, dword ptr [rbp+Arguments]
0x180106ced  cmp     [rax+rbx+8], ecx
0x180106cf1  jnz     short loc_180106D04
0x180106cf3  cmp     rbx, [rax+rbx+30h]
0x180106cf8  jnz     short loc_180106D04
0x180106cfa  mov     rdi, [r13+r12*8+0]
0x180106cff  test    rdi, rdi
0x180106d02  jnz     short loc_180106D6E
0x180106d04  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x180106d08  mov     rcx, rbx; hModule
0x180106d0b  call    cs:__imp_GetProcAddress
0x180106d11  mov     rdi, rax
0x180106d14  test    rax, rax
0x180106d17  jnz     short loc_180106D6E
0x180106d19  call    cs:__imp_GetLastError
0x180106d1f  mov     [rbp+var_10], eax
0x180106d22  mov     rax, cs:__pfnDliFailureHook2
0x180106d29  test    rax, rax
0x180106d2c  jz      short loc_180106D43
0x180106d2e  lea     rdx, [rbp+var_50]
0x180106d32  lea     ecx, [rdi+4]
0x180106d35  call    cs:__guard_dispatch_icall_fptr
0x180106d3b  mov     rdi, rax
0x180106d3e  test    rax, rax
0x180106d41  jnz     short loc_180106D6E
0x180106d43  lea     rax, [rbp+var_50]
0x180106d47  mov     [rbp+Arguments], rax
0x180106d4b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180106d50  xor     edx, edx; dwExceptionFlags
0x180106d52  lea     r9, [rbp+Arguments]; lpArguments
0x180106d56  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180106d5b  lea     r8d, [rdx+1]; nNumberOfArguments
0x180106d5f  call    cs:__imp_RaiseException
0x180106d65  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x180106d6a  mov     rdi, [rbp+var_18]
0x180106d6e  lea     r8, [rbp+var_60]
0x180106d72  mov     [rbp+var_60], r15
0x180106d76  mov     edx, 8; dwSize
0x180106d7b  mov     [rbp+var_58], rdi
0x180106d7f  mov     rcx, r15; lpAddress
0x180106d82  call    GuardedWrite____delayLoadHelper2____2____lambda_1___
0x180106d87  mov     rax, cs:__pfnDliNotifyHook2
0x180106d8e  test    rax, rax
0x180106d91  jz      short loc_180106DB1
0x180106d93  lea     rdx, [rbp+var_50]
0x180106d97  mov     [rbp+var_10], 0
0x180106d9e  mov     ecx, 5
0x180106da3  mov     [rbp+var_20], rbx
0x180106da7  mov     [rbp+var_18], rdi
0x180106dab  call    cs:__guard_dispatch_icall_fptr
0x180106db1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180106db6  mov     rax, rdi
0x180106db9  lea     r11, [rsp+80h+var_s0]
0x180106dc1  mov     rbx, [r11+38h]
0x180106dc5  mov     rsi, [r11+40h]
0x180106dc9  mov     rdi, [r11+48h]
0x180106dcd  mov     rsp, r11
0x180106dd0  pop     r15
0x180106dd2  pop     r14
0x180106dd4  pop     r13
0x180106dd6  pop     r12
0x180106dd8  pop     rbp
0x180106dd9  retn
```
