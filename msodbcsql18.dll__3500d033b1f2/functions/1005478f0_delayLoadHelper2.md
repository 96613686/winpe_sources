# __delayLoadHelper2

- ea: `0x1005478f0`
- end: `0x100547be9`
- name: `__delayLoadHelper2`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x100546e57`
- `0x100546ee2`

## callees

- `0x1004385b0`
- `0x100547500`
- `0x100547838`
- `0x1005478f0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x100547a47`
- `KERNEL32!LoadLibraryExA` at `0x100547a47`
- `KERNEL32!RaiseException` at `0x10054799a`
- `KERNEL32!RaiseException` at `0x100547aa2`
- `KERNEL32!RaiseException` at `0x100547b8e`
- `KERNEL32!RaiseException` at `0x10054799a`
- `KERNEL32!RaiseException` at `0x100547aa2`
- `KERNEL32!RaiseException` at `0x100547b8e`
- `KERNEL32!GetLastError` at `0x100547a55`
- `KERNEL32!GetLastError` at `0x100547b41`
- `KERNEL32!GetLastError` at `0x100547a55`
- `KERNEL32!GetLastError` at `0x100547b41`
- `KERNEL32!GetProcAddress` at `0x100547b33`
- `KERNEL32!GetProcAddress` at `0x100547b33`
- `KERNEL32!FreeLibrary` at `0x100547ac0`
- `KERNEL32!FreeLibrary` at `0x100547ac0`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  const CHAR *v4; // rax
  char *v5; // r8
  int v6; // r9d
  volatile __int64 *v7; // r12
  __int64 rvaINT; // rcx
  char *v9; // rdx
  char *v10; // rcx
  HMODULE Library; // rdi
  __int64 v13; // r14
  bool v14; // zf
  PfnDliHook v15; // rsi
  INT_PTR (__stdcall *ProcAddress)(); // rbx
  __int64 v17; // rax
  ULONG_PTR v18[2]; // [rsp+20h] [rbp-49h] BYREF
  DelayLoadInfo pdli; // [rsp+30h] [rbp-39h] BYREF
  DWORD dwTimeStamp; // [rsp+D0h] [rbp+67h]
  ULONG_PTR Arguments; // [rsp+D8h] [rbp+6Fh] BYREF
  ULONG_PTR p_pdli; // [rsp+E0h] [rbp+77h] BYREF
  char *v23; // [rsp+E8h] [rbp+7Fh]

  DloadAcquireSectionWriteAccess();
  v4 = (char *)&_ImageBase + a1->rvaDLLName;
  v5 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v6 = a1->grAttrs & 1;
  v7 = (volatile __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  rvaINT = a1->rvaINT;
  v9 = (char *)&_ImageBase + a1->rvaIAT;
  pdli.dlp.fImportByName = 0;
  v10 = (char *)&_ImageBase + rvaINT;
  pdli.szDll = v4;
  v23 = v5;
  dwTimeStamp = a1->dwTimeStamp;
  pdli.cb = 72;
  pdli.pidd = a1;
  pdli.ppfn = a2;
  memset(&pdli.dlp.szProcName, 0, 28);
  if ( !(_BYTE)v6 )
  {
    Arguments = (ULONG_PTR)&pdli;
    DloadReleaseSectionWriteAccess();
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v7;
  v13 = (unsigned int)(((char *)a2 - v9) >> 3);
  v14 = *(__int64 *)&v10[8 * v13] < 0;
  pdli.dlp.fImportByName = *(_QWORD *)&v10[8 * v13] >= 0LL;
  if ( v14 )
    pdli.dlp.dwOrdinal = *(unsigned __int16 *)&v10[8 * v13];
  else
    pdli.dlp.szProcName = (char *)&word_100400002 + *(unsigned int *)&v10[8 * v13];
  v15 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( _pfnDliNotifyHook2 )
  {
    ProcAddress = _pfnDliNotifyHook2(0, &pdli);
    if ( ProcAddress )
      goto LABEL_33;
    v15 = _pfnDliNotifyHook2;
  }
  if ( !Library )
  {
    if ( !v15 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, DelayLoadInfo *))v15)(1, &pdli)) == 0 )
    {
      Library = LoadLibraryExA(pdli.szDll, 0, 0);
      if ( !Library )
      {
        pdli.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (Library = (HMODULE)_pfnDliFailureHook2(3u, &pdli)) == 0 )
        {
          p_pdli = (ULONG_PTR)&pdli;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007E, 0, 1u, &p_pdli);
          return pdli.pfnCur;
        }
      }
    }
    if ( (HMODULE)_InterlockedExchange64(v7, (__int64)Library) == Library )
      FreeLibrary(Library);
    v15 = _pfnDliNotifyHook2;
  }
  pdli.hmodCur = Library;
  if ( v15 )
    ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, DelayLoadInfo *))v15)(2, &pdli);
  if ( !ProcAddress )
  {
    if ( !a1->rvaBoundIAT
      || !a1->dwTimeStamp
      || (v17 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v17) != 17744)
      || *(_DWORD *)((char *)Library + v17 + 8) != dwTimeStamp
      || Library != *(HMODULE *)((char *)Library + v17 + 48)
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v23[8 * v13]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, pdli.dlp.szProcName);
      if ( !ProcAddress )
      {
        pdli.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (ProcAddress = _pfnDliFailureHook2(4u, &pdli)) == 0 )
        {
          v18[0] = (ULONG_PTR)&pdli;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007F, 0, 1u, v18);
          DloadAcquireSectionWriteAccess();
          ProcAddress = pdli.pfnCur;
        }
      }
    }
  }
  *a2 = ProcAddress;
LABEL_33:
  if ( _pfnDliNotifyHook2 )
  {
    pdli.dwLastError = 0;
    pdli.hmodCur = Library;
    pdli.pfnCur = ProcAddress;
    _pfnDliNotifyHook2(5u, &pdli);
  }
  DloadReleaseSectionWriteAccess();
  return ProcAddress;
}

```

## disassembly

```asm
0x1005478f0  push    rbp
0x1005478f2  push    rbx
0x1005478f3  push    rsi
0x1005478f4  push    rdi
0x1005478f5  push    r12
0x1005478f7  push    r13
0x1005478f9  push    r14
0x1005478fb  push    r15
0x1005478fd  lea     rbp, [rsp-1Fh]
0x100547902  sub     rsp, 88h
0x100547909  mov     r13, rdx
0x10054790c  mov     r15, rcx
0x10054790f  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100547914  mov     eax, [r15+4]
0x100547918  lea     r10, __ImageBase
0x10054791f  mov     r8d, [r15+14h]
0x100547923  add     rax, r10
0x100547926  mov     r9d, [r15]
0x100547929  add     r8, r10
0x10054792c  mov     r12d, [r15+8]
0x100547930  and     r9d, 1
0x100547934  mov     edx, [r15+0Ch]
0x100547938  add     r12, r10
0x10054793b  mov     ecx, [r15+10h]
0x10054793f  add     rdx, r10; unsigned int
0x100547942  and     [rbp+57h+pdli.dlp.fImportByName], 0
0x100547946  add     rcx, r10
0x100547949  mov     [rbp+57h+pdli.szDll], rax
0x10054794d  xor     eax, eax
0x10054794f  and     [rbp+57h+pdli.hmodCur], rax
0x100547953  and     [rbp+57h+pdli.pfnCur], rax
0x100547957  and     [rbp+57h+pdli.dwLastError], eax
0x10054795a  mov     [rbp+57h+arg_18], r8
0x10054795e  mov     r8d, [r15+1Ch]
0x100547962  mov     [rbp+57h+arg_0], r8d
0x100547966  mov     [rbp+57h+pdli.cb], 48h ; 'H'
0x10054796d  mov     [rbp+57h+pdli.pidd], r15
0x100547971  mov     [rbp+57h+pdli.ppfn], r13
0x100547975  mov     qword ptr [rbp+57h+pdli.dlp.8], rax
0x100547979  test    r9b, r9b
0x10054797c  jnz     short loc_1005479A7
0x10054797e  lea     rax, [rbp+57h+pdli]
0x100547982  mov     [rbp+57h+Arguments], rax
0x100547986  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10054798b  xor     edx, edx; dwExceptionFlags
0x10054798d  lea     r9, [rbp+57h+Arguments]; lpArguments
0x100547991  mov     ecx, 0C06D0057h; dwExceptionCode
0x100547996  lea     r8d, [rdx+1]; nNumberOfArguments
0x10054799a  call    cs:__imp_RaiseException
0x1005479a0  xor     eax, eax
0x1005479a2  jmp     loc_100547BD5
0x1005479a7  mov     rdi, [r12]
0x1005479ab  mov     r14, r13
0x1005479ae  sub     r14, rdx
0x1005479b1  sar     r14, 3
0x1005479b5  mov     r14d, r14d
0x1005479b8  mov     rax, [rcx+r14*8]
0x1005479bc  shr     rax, 3Fh
0x1005479c0  xor     eax, 1
0x1005479c3  mov     [rbp+57h+pdli.dlp.fImportByName], eax
0x1005479c6  jz      short loc_1005479DC
0x1005479c8  mov     eax, [rcx+r14*8]
0x1005479cc  lea     rcx, word_100400002
0x1005479d3  add     rax, rcx
0x1005479d6  mov     qword ptr [rbp+57h+pdli.dlp.8], rax
0x1005479da  jmp     short loc_1005479E4
0x1005479dc  movzx   eax, word ptr [rcx+r14*8]
0x1005479e1  mov     dword ptr [rbp+57h+pdli.dlp.8], eax
0x1005479e4  mov     rsi, cs:__pfnDliNotifyHook2
0x1005479eb  xor     ebx, ebx
0x1005479ed  test    rsi, rsi
0x1005479f0  jz      short loc_100547A16
0x1005479f2  mov     rcx, rsi; this
0x1005479f5  call    cs:__guard_check_icall_fptr; SNI_IOCPIOQueue::Poll(ulong) ...
0x1005479fb  lea     rdx, [rbp+57h+pdli]; pdli
0x1005479ff  xor     ecx, ecx; dliNotify
0x100547a01  call    rsi ; __pfnDliNotifyHook2
0x100547a03  mov     rbx, rax
0x100547a06  test    rax, rax
0x100547a09  jnz     loc_100547BA1
0x100547a0f  mov     rsi, cs:__pfnDliNotifyHook2
0x100547a16  test    rdi, rdi
0x100547a19  jnz     loc_100547ACD
0x100547a1f  test    rsi, rsi
0x100547a22  jz      short loc_100547A3E
0x100547a24  mov     rcx, rsi; this
0x100547a27  call    cs:__guard_check_icall_fptr; SNI_IOCPIOQueue::Poll(ulong) ...
0x100547a2d  lea     rdx, [rbp+57h+pdli]; pdli
0x100547a31  lea     ecx, [rdi+1]; dliNotify
0x100547a34  call    rsi ; __pfnDliNotifyHook2
0x100547a36  mov     rdi, rax
0x100547a39  test    rax, rax
0x100547a3c  jnz     short loc_100547AB1
0x100547a3e  mov     rcx, [rbp+57h+pdli.szDll]; lpLibFileName
0x100547a42  xor     r8d, r8d; dwFlags
0x100547a45  xor     edx, edx; hFile
0x100547a47  call    cs:__imp_LoadLibraryExA
0x100547a4d  mov     rdi, rax
0x100547a50  test    rax, rax
0x100547a53  jnz     short loc_100547AB1
0x100547a55  call    cs:__imp_GetLastError
0x100547a5b  mov     rdi, cs:__pfnDliFailureHook2
0x100547a62  mov     [rbp+57h+pdli.dwLastError], eax
0x100547a65  test    rdi, rdi
0x100547a68  jz      short loc_100547A86
0x100547a6a  mov     rcx, rdi; this
0x100547a6d  call    cs:__guard_check_icall_fptr; SNI_IOCPIOQueue::Poll(ulong) ...
0x100547a73  lea     rdx, [rbp+57h+pdli]; pdli
0x100547a77  mov     ecx, 3; dliNotify
0x100547a7c  call    rdi ; __pfnDliFailureHook2
0x100547a7e  mov     rdi, rax
0x100547a81  test    rax, rax
0x100547a84  jnz     short loc_100547AB1
0x100547a86  lea     rax, [rbp+57h+pdli]
0x100547a8a  mov     [rbp+57h+arg_10], rax
0x100547a8e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100547a93  xor     edx, edx; dwExceptionFlags
0x100547a95  lea     r9, [rbp+57h+arg_10]; lpArguments
0x100547a99  mov     ecx, 0C06D007Eh; dwExceptionCode
0x100547a9e  lea     r8d, [rdx+1]; nNumberOfArguments
0x100547aa2  call    cs:__imp_RaiseException
0x100547aa8  mov     rax, [rbp+57h+pdli.pfnCur]
0x100547aac  jmp     loc_100547BD5
0x100547ab1  mov     rax, rdi
0x100547ab4  xchg    rax, [r12]
0x100547ab8  cmp     rax, rdi
0x100547abb  jnz     short loc_100547AC6
0x100547abd  mov     rcx, rdi; hLibModule
0x100547ac0  call    cs:__imp_FreeLibrary
0x100547ac6  mov     rsi, cs:__pfnDliNotifyHook2
0x100547acd  mov     [rbp+57h+pdli.hmodCur], rdi
0x100547ad1  test    rsi, rsi
0x100547ad4  jz      short loc_100547AED
0x100547ad6  mov     rcx, rsi; this
0x100547ad9  call    cs:__guard_check_icall_fptr; SNI_IOCPIOQueue::Poll(ulong) ...
0x100547adf  lea     rdx, [rbp+57h+pdli]; pdli
0x100547ae3  mov     ecx, 2; dliNotify
0x100547ae8  call    rsi ; __pfnDliNotifyHook2
0x100547aea  mov     rbx, rax
0x100547aed  test    rbx, rbx
0x100547af0  jnz     loc_100547B9D
0x100547af6  cmp     [r15+14h], ebx
0x100547afa  jz      short loc_100547B2C
0x100547afc  cmp     [r15+1Ch], ebx
0x100547b00  jz      short loc_100547B2C
0x100547b02  movsxd  rax, dword ptr [rdi+3Ch]
0x100547b06  cmp     dword ptr [rax+rdi], 4550h
0x100547b0d  jnz     short loc_100547B2C
0x100547b0f  mov     ecx, [rbp+57h+arg_0]
0x100547b12  cmp     [rax+rdi+8], ecx
0x100547b16  jnz     short loc_100547B2C
0x100547b18  cmp     rdi, [rax+rdi+30h]
0x100547b1d  jnz     short loc_100547B2C
0x100547b1f  mov     rbx, [rbp+57h+arg_18]
0x100547b23  mov     rbx, [rbx+r14*8]
0x100547b27  test    rbx, rbx
0x100547b2a  jnz     short loc_100547B9D
0x100547b2c  mov     rdx, qword ptr [rbp+57h+pdli.dlp.8]; lpProcName
0x100547b30  mov     rcx, rdi; hModule
0x100547b33  call    cs:__imp_GetProcAddress
0x100547b39  mov     rbx, rax
0x100547b3c  test    rax, rax
0x100547b3f  jnz     short loc_100547B9D
0x100547b41  call    cs:__imp_GetLastError
0x100547b47  mov     rbx, cs:__pfnDliFailureHook2
0x100547b4e  mov     [rbp+57h+pdli.dwLastError], eax
0x100547b51  test    rbx, rbx
0x100547b54  jz      short loc_100547B72
0x100547b56  mov     rcx, rbx; this
0x100547b59  call    cs:__guard_check_icall_fptr; SNI_IOCPIOQueue::Poll(ulong) ...
0x100547b5f  lea     rdx, [rbp+57h+pdli]; pdli
0x100547b63  mov     ecx, 4; dliNotify
0x100547b68  call    rbx ; __pfnDliFailureHook2
0x100547b6a  mov     rbx, rax
0x100547b6d  test    rax, rax
0x100547b70  jnz     short loc_100547B9D
0x100547b72  lea     rax, [rbp+57h+pdli]
0x100547b76  mov     [rbp+57h+var_A0], rax
0x100547b7a  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100547b7f  xor     edx, edx; dwExceptionFlags
0x100547b81  lea     r9, [rbp+57h+var_A0]; lpArguments
0x100547b85  mov     ecx, 0C06D007Fh; dwExceptionCode
0x100547b8a  lea     r8d, [rdx+1]; nNumberOfArguments
0x100547b8e  call    cs:__imp_RaiseException
0x100547b94  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100547b99  mov     rbx, [rbp+57h+pdli.pfnCur]
0x100547b9d  mov     [r13+0], rbx
0x100547ba1  mov     rsi, cs:__pfnDliNotifyHook2
0x100547ba8  test    rsi, rsi
0x100547bab  jz      short loc_100547BCD
0x100547bad  and     [rbp+57h+pdli.dwLastError], 0
0x100547bb1  mov     rcx, rsi; this
0x100547bb4  mov     [rbp+57h+pdli.hmodCur], rdi
0x100547bb8  mov     [rbp+57h+pdli.pfnCur], rbx
0x100547bbc  call    cs:__guard_check_icall_fptr; SNI_IOCPIOQueue::Poll(ulong) ...
0x100547bc2  lea     rdx, [rbp+57h+pdli]; pdli
0x100547bc6  mov     ecx, 5; dliNotify
0x100547bcb  call    rsi ; __pfnDliNotifyHook2
0x100547bcd  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100547bd2  mov     rax, rbx
0x100547bd5  add     rsp, 88h
0x100547bdc  pop     r15
0x100547bde  pop     r14
0x100547be0  pop     r13
0x100547be2  pop     r12
0x100547be4  pop     rdi
0x100547be5  pop     rsi
0x100547be6  pop     rbx
0x100547be7  pop     rbp
0x100547be8  retn
```
