# __delayLoadHelper2

- ea: `0x180105910`
- end: `0x180105be2`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1801053b3`
- `0x180105444`
- `0x1801054ed`
- `0x180105be2`

## callees

- `0x180105568`
- `0x180105874`
- `0x180105910`
- `0x180106100`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180105a62`
- `KERNEL32!GetLastError` at `0x180105b3c`
- `KERNEL32!GetLastError` at `0x180105a62`
- `KERNEL32!GetLastError` at `0x180105b3c`
- `KERNEL32!GetProcAddress` at `0x180105b2e`
- `KERNEL32!GetProcAddress` at `0x180105b2e`
- `KERNEL32!FreeLibrary` at `0x180105ac5`
- `KERNEL32!FreeLibrary` at `0x180105ac5`
- `KERNEL32!RaiseException` at `0x1801059b2`
- `KERNEL32!RaiseException` at `0x180105aa8`
- `KERNEL32!RaiseException` at `0x180105b82`
- `KERNEL32!RaiseException` at `0x1801059b2`
- `KERNEL32!RaiseException` at `0x180105aa8`
- `KERNEL32!RaiseException` at `0x180105b82`
- `KERNEL32!LoadLibraryExA` at `0x180105a54`
- `KERNEL32!LoadLibraryExA` at `0x180105a54`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile __int64 *v4; // r14
  char *v5; // r9
  char *v6; // rcx
  char *v7; // r13
  DWORD dwTimeStamp; // edx
  DWORD grAttrs; // eax
  HMODULE Library; // rdi
  __int64 v12; // r15
  bool v13; // zf
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rbx
  __int64 v16; // rax
  struct DelayLoadInfo v17; // [rsp+20h] [rbp-50h] BYREF
  ULONG_PTR Arguments; // [rsp+A0h] [rbp+30h] BYREF

  DloadAcquireSectionWriteAccess();
  v4 = (volatile __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  v5 = (char *)&_ImageBase + a1->rvaIAT;
  v6 = (char *)&_ImageBase + a1->rvaINT;
  v7 = (char *)&_ImageBase + a1->rvaBoundIAT;
  dwTimeStamp = a1->dwTimeStamp;
  v17.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v17.cb = 72;
  v17.pidd = a1;
  v17.ppfn = a2;
  memset(&v17.dlp, 0, 36);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v17;
    DloadReleaseSectionWriteAccess();
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v12 = (unsigned int)(((char *)a2 - v5) >> 3);
  v13 = *(__int64 *)&v6[8 * v12] < 0;
  v17.dlp.fImportByName = *(_QWORD *)&v6[8 * v12] >= 0LL;
  if ( v13 )
    v17.dlp.dwOrdinal = *(unsigned __int16 *)&v6[8 * v12];
  else
    v17.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)&v6[8 * v12];
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( _pfnDliNotifyHook2 )
  {
    ProcAddress = _pfnDliNotifyHook2(0, &v17);
    if ( ProcAddress )
      goto LABEL_33;
    v14 = _pfnDliNotifyHook2;
  }
  if ( !Library )
  {
    if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v17)) == 0 )
    {
      Library = LoadLibraryExA(v17.szDll, 0, 0);
      if ( !Library )
      {
        v17.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (Library = (HMODULE)_pfnDliFailureHook2(3u, &v17)) == 0 )
        {
          Arguments = (ULONG_PTR)&v17;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007E, 0, 1u, &Arguments);
          return v17.pfnCur;
        }
      }
    }
    if ( (HMODULE)_InterlockedExchange64(v4, (__int64)Library) == Library )
      FreeLibrary(Library);
    v14 = _pfnDliNotifyHook2;
  }
  v17.hmodCur = Library;
  if ( v14 )
    ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v17);
  if ( !ProcAddress )
  {
    if ( !a1->rvaBoundIAT
      || !a1->dwTimeStamp
      || (v16 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v16) != 17744)
      || *(_DWORD *)((char *)Library + v16 + 8) != (_DWORD)Arguments
      || Library != *(HMODULE *)((char *)Library + v16 + 48)
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v7[8 * v12]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, v17.dlp.szProcName);
      if ( !ProcAddress )
      {
        v17.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (ProcAddress = _pfnDliFailureHook2(4u, &v17)) == 0 )
        {
          Arguments = (ULONG_PTR)&v17;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007F, 0, 1u, &Arguments);
          DloadAcquireSectionWriteAccess();
          ProcAddress = v17.pfnCur;
        }
      }
    }
  }
  *a2 = ProcAddress;
LABEL_33:
  if ( _pfnDliNotifyHook2 )
  {
    v17.dwLastError = 0;
    v17.hmodCur = Library;
    v17.pfnCur = ProcAddress;
    _pfnDliNotifyHook2(5u, &v17);
  }
  DloadReleaseSectionWriteAccess();
  return ProcAddress;
}

```

## disassembly

```asm
0x180105910  mov     [rsp-28h+arg_8], rbx
0x180105915  mov     [rsp-28h+arg_10], rsi
0x18010591a  mov     [rsp-28h+arg_18], rdi
0x18010591f  push    rbp
0x180105920  push    r12
0x180105922  push    r13
0x180105924  push    r14
0x180105926  push    r15
0x180105928  mov     rbp, rsp
0x18010592b  sub     rsp, 70h
0x18010592f  mov     r12, rdx
0x180105932  mov     rsi, rcx
0x180105935  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18010593a  mov     eax, [rsi+4]
0x18010593d  lea     rdx, __ImageBase
0x180105944  mov     r14d, [rsi+8]
0x180105948  add     rax, rdx
0x18010594b  mov     r9d, [rsi+0Ch]
0x18010594f  add     r14, rdx
0x180105952  mov     ecx, [rsi+10h]
0x180105955  add     r9, rdx
0x180105958  mov     r13d, [rsi+14h]
0x18010595c  add     rcx, rdx
0x18010595f  and     [rbp+var_20], 0
0x180105964  add     r13, rdx
0x180105967  and     [rbp+var_18], 0
0x18010596c  xorps   xmm0, xmm0
0x18010596f  and     [rbp+var_10], 0
0x180105973  mov     edx, [rsi+1Ch]
0x180105976  mov     [rbp+lpLibFileName], rax
0x18010597a  mov     eax, [rsi]
0x18010597c  mov     dword ptr [rbp+Arguments], edx
0x18010597f  mov     [rbp+var_50], 48h ; 'H'
0x180105986  mov     [rbp+var_48], rsi
0x18010598a  mov     [rbp+var_40], r12
0x18010598e  movups  xmmword ptr [rbp+lpProcName], xmm0
0x180105992  test    al, 1
0x180105994  jnz     short loc_1801059BF
0x180105996  lea     rax, [rbp+var_50]
0x18010599a  mov     [rbp+Arguments], rax
0x18010599e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1801059a3  xor     edx, edx; dwExceptionFlags
0x1801059a5  lea     r9, [rbp+Arguments]; lpArguments
0x1801059a9  mov     ecx, 0C06D0057h; dwExceptionCode
0x1801059ae  lea     r8d, [rdx+1]; nNumberOfArguments
0x1801059b2  call    cs:__imp_RaiseException
0x1801059b8  xor     eax, eax
0x1801059ba  jmp     loc_180105BC4
0x1801059bf  mov     rdi, [r14]
0x1801059c2  mov     r15, r12
0x1801059c5  sub     r15, r9
0x1801059c8  sar     r15, 3
0x1801059cc  mov     r15d, r15d
0x1801059cf  mov     rax, [rcx+r15*8]
0x1801059d3  shr     rax, 3Fh
0x1801059d7  xor     eax, 1
0x1801059da  mov     dword ptr [rbp+lpProcName], eax
0x1801059dd  jz      short loc_1801059F3
0x1801059df  mov     eax, [rcx+r15*8]
0x1801059e3  lea     rcx, word_180000002
0x1801059ea  add     rax, rcx
0x1801059ed  mov     [rbp+lpProcName+8], rax
0x1801059f1  jmp     short loc_1801059FB
0x1801059f3  movzx   eax, word ptr [rcx+r15*8]
0x1801059f8  mov     dword ptr [rbp+lpProcName+8], eax
0x1801059fb  mov     rax, cs:__pfnDliNotifyHook2
0x180105a02  xor     ebx, ebx
0x180105a04  test    rax, rax
0x180105a07  jz      short loc_180105A28
0x180105a09  lea     rdx, [rbp+var_50]
0x180105a0d  xor     ecx, ecx
0x180105a0f  call    cs:__guard_dispatch_icall_fptr
0x180105a15  mov     rbx, rax
0x180105a18  test    rax, rax
0x180105a1b  jnz     loc_180105B95
0x180105a21  mov     rax, cs:__pfnDliNotifyHook2
0x180105a28  test    rdi, rdi
0x180105a2b  jnz     loc_180105AD2
0x180105a31  test    rax, rax
0x180105a34  jz      short loc_180105A4B
0x180105a36  lea     rdx, [rbp+var_50]
0x180105a3a  lea     ecx, [rdi+1]
0x180105a3d  call    cs:__guard_dispatch_icall_fptr
0x180105a43  mov     rdi, rax
0x180105a46  test    rax, rax
0x180105a49  jnz     short loc_180105AB7
0x180105a4b  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180105a4f  xor     r8d, r8d; dwFlags
0x180105a52  xor     edx, edx; hFile
0x180105a54  call    cs:__imp_LoadLibraryExA
0x180105a5a  mov     rdi, rax
0x180105a5d  test    rax, rax
0x180105a60  jnz     short loc_180105AB7
0x180105a62  call    cs:__imp_GetLastError
0x180105a68  mov     [rbp+var_10], eax
0x180105a6b  mov     rax, cs:__pfnDliFailureHook2
0x180105a72  test    rax, rax
0x180105a75  jz      short loc_180105A8C
0x180105a77  lea     rdx, [rbp+var_50]
0x180105a7b  lea     ecx, [rdi+3]
0x180105a7e  call    cs:__guard_dispatch_icall_fptr
0x180105a84  mov     rdi, rax
0x180105a87  test    rax, rax
0x180105a8a  jnz     short loc_180105AB7
0x180105a8c  lea     rax, [rbp+var_50]
0x180105a90  mov     [rbp+Arguments], rax
0x180105a94  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180105a99  xor     edx, edx; dwExceptionFlags
0x180105a9b  lea     r9, [rbp+Arguments]; lpArguments
0x180105a9f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180105aa4  lea     r8d, [rdx+1]; nNumberOfArguments
0x180105aa8  call    cs:__imp_RaiseException
0x180105aae  mov     rax, [rbp+var_18]
0x180105ab2  jmp     loc_180105BC4
0x180105ab7  mov     rax, rdi
0x180105aba  xchg    rax, [r14]
0x180105abd  cmp     rax, rdi
0x180105ac0  jnz     short loc_180105ACB
0x180105ac2  mov     rcx, rdi; hLibModule
0x180105ac5  call    cs:__imp_FreeLibrary
0x180105acb  mov     rax, cs:__pfnDliNotifyHook2
0x180105ad2  mov     [rbp+var_20], rdi
0x180105ad6  test    rax, rax
0x180105ad9  jz      short loc_180105AED
0x180105adb  lea     rdx, [rbp+var_50]
0x180105adf  mov     ecx, 2
0x180105ae4  call    cs:__guard_dispatch_icall_fptr
0x180105aea  mov     rbx, rax
0x180105aed  test    rbx, rbx
0x180105af0  jnz     loc_180105B91
0x180105af6  cmp     [rsi+14h], ebx
0x180105af9  jz      short loc_180105B27
0x180105afb  cmp     [rsi+1Ch], ebx
0x180105afe  jz      short loc_180105B27
0x180105b00  movsxd  rax, dword ptr [rdi+3Ch]
0x180105b04  cmp     dword ptr [rax+rdi], 4550h
0x180105b0b  jnz     short loc_180105B27
0x180105b0d  mov     ecx, dword ptr [rbp+Arguments]
0x180105b10  cmp     [rax+rdi+8], ecx
0x180105b14  jnz     short loc_180105B27
0x180105b16  cmp     rdi, [rax+rdi+30h]
0x180105b1b  jnz     short loc_180105B27
0x180105b1d  mov     rbx, [r13+r15*8+0]
0x180105b22  test    rbx, rbx
0x180105b25  jnz     short loc_180105B91
0x180105b27  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x180105b2b  mov     rcx, rdi; hModule
0x180105b2e  call    cs:__imp_GetProcAddress
0x180105b34  mov     rbx, rax
0x180105b37  test    rax, rax
0x180105b3a  jnz     short loc_180105B91
0x180105b3c  call    cs:__imp_GetLastError
0x180105b42  mov     [rbp+var_10], eax
0x180105b45  mov     rax, cs:__pfnDliFailureHook2
0x180105b4c  test    rax, rax
0x180105b4f  jz      short loc_180105B66
0x180105b51  lea     rdx, [rbp+var_50]
0x180105b55  lea     ecx, [rbx+4]
0x180105b58  call    cs:__guard_dispatch_icall_fptr
0x180105b5e  mov     rbx, rax
0x180105b61  test    rax, rax
0x180105b64  jnz     short loc_180105B91
0x180105b66  lea     rax, [rbp+var_50]
0x180105b6a  mov     [rbp+Arguments], rax
0x180105b6e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180105b73  xor     edx, edx; dwExceptionFlags
0x180105b75  lea     r9, [rbp+Arguments]; lpArguments
0x180105b79  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180105b7e  lea     r8d, [rdx+1]; nNumberOfArguments
0x180105b82  call    cs:__imp_RaiseException
0x180105b88  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x180105b8d  mov     rbx, [rbp+var_18]
0x180105b91  mov     [r12], rbx
0x180105b95  mov     rax, cs:__pfnDliNotifyHook2
0x180105b9c  test    rax, rax
0x180105b9f  jz      short loc_180105BBC
0x180105ba1  and     [rbp+var_10], 0
0x180105ba5  lea     rdx, [rbp+var_50]
0x180105ba9  mov     ecx, 5
0x180105bae  mov     [rbp+var_20], rdi
0x180105bb2  mov     [rbp+var_18], rbx
0x180105bb6  call    cs:__guard_dispatch_icall_fptr
0x180105bbc  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180105bc1  mov     rax, rbx
0x180105bc4  lea     r11, [rsp+70h+var_s0]
0x180105bc9  mov     rbx, [r11+38h]
0x180105bcd  mov     rsi, [r11+40h]
0x180105bd1  mov     rdi, [r11+48h]
0x180105bd5  mov     rsp, r11
0x180105bd8  pop     r15
0x180105bda  pop     r14
0x180105bdc  pop     r13
0x180105bde  pop     r12
0x180105be0  pop     rbp
0x180105be1  retn
```
