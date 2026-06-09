# __delayLoadHelper2

- ea: `0x140069990`
- end: `0x140069c8c`
- name: `__delayLoadHelper2`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140069326`

## callees

- `0x1400338f0`
- `0x140069468`
- `0x140069554`
- `0x1400698dc`
- `0x140069990`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x140069ad9`
- `KERNEL32!LoadLibraryExA` at `0x140069ad9`
- `KERNEL32!RaiseException` at `0x140069a3a`
- `KERNEL32!RaiseException` at `0x140069b2d`
- `KERNEL32!RaiseException` at `0x140069c0b`
- `KERNEL32!RaiseException` at `0x140069a3a`
- `KERNEL32!RaiseException` at `0x140069b2d`
- `KERNEL32!RaiseException` at `0x140069c0b`
- `KERNEL32!FreeLibrary` at `0x140069b4a`
- `KERNEL32!FreeLibrary` at `0x140069b4a`
- `KERNEL32!GetProcAddress` at `0x140069bb7`
- `KERNEL32!GetProcAddress` at `0x140069bb7`
- `KERNEL32!GetLastError` at `0x140069ae7`
- `KERNEL32!GetLastError` at `0x140069bc5`
- `KERNEL32!GetLastError` at `0x140069ae7`
- `KERNEL32!GetLastError` at `0x140069bc5`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile __int64 *v4; // r15
  char *v5; // rcx
  char *v6; // rdx
  char *v7; // r13
  DWORD dwTimeStamp; // r8d
  DWORD grAttrs; // eax
  HMODULE Library; // rdi
  __int64 v12; // rsi
  bool v13; // zf
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rbx
  __int64 v16; // rax
  struct DelayLoadInfo v17; // [rsp+30h] [rbp-50h] BYREF
  ULONG_PTR Arguments; // [rsp+B0h] [rbp+30h] BYREF

  DloadAcquireSectionWriteAccess();
  v4 = (volatile __int64 *)((char *)IMM32_NULL_THUNK_DATA + a1->rvaHmod);
  v5 = (char *)IMM32_NULL_THUNK_DATA + a1->rvaIAT;
  v6 = (char *)IMM32_NULL_THUNK_DATA + a1->rvaINT;
  v7 = (char *)IMM32_NULL_THUNK_DATA + a1->rvaBoundIAT;
  dwTimeStamp = a1->dwTimeStamp;
  v17.szDll = (char *)IMM32_NULL_THUNK_DATA + a1->rvaDLLName;
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
  v12 = ((char *)a2 - v5) >> 3;
  v13 = *(__int64 *)&v6[8 * (unsigned int)v12] < 0;
  v17.dlp.fImportByName = *(_QWORD *)&v6[8 * (unsigned int)v12] >= 0LL;
  if ( v13 )
    v17.dlp.dwOrdinal = *(unsigned __int16 *)&v6[8 * (unsigned int)v12];
  else
    v17.dlp.szProcName = (char *)word_140000002 + *(unsigned int *)&v6[8 * (unsigned int)v12];
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
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v7[8 * (unsigned int)v12]) == 0 )
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
  GuardedWrite__lambda_7ce9785d57ad9101eca44ba76fd23ffb_(a2, 8u);
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
0x140069990  mov     [rsp-28h+arg_8], rbx
0x140069995  mov     [rsp-28h+arg_10], rsi
0x14006999a  mov     [rsp-28h+arg_18], rdi
0x14006999f  push    rbp
0x1400699a0  push    r12
0x1400699a2  push    r13
0x1400699a4  push    r14
0x1400699a6  push    r15
0x1400699a8  mov     rbp, rsp
0x1400699ab  sub     rsp, 80h
0x1400699b2  mov     r12, rdx
0x1400699b5  mov     r14, rcx
0x1400699b8  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1400699bd  mov     eax, [r14+4]
0x1400699c1  lea     r8, _IMM32_NULL_THUNK_DATA; "MZ"
0x1400699c8  mov     r15d, [r14+8]
0x1400699cc  add     rax, r8
0x1400699cf  mov     ecx, [r14+0Ch]
0x1400699d3  add     r15, r8
0x1400699d6  mov     edx, [r14+10h]
0x1400699da  add     rcx, r8
0x1400699dd  mov     r13d, [r14+14h]
0x1400699e1  add     rdx, r8
0x1400699e4  and     [rbp+var_20], 0
0x1400699e9  add     r13, r8
0x1400699ec  and     [rbp+var_18], 0
0x1400699f1  xorps   xmm0, xmm0
0x1400699f4  and     [rbp+var_10], 0
0x1400699f8  mov     r8d, [r14+1Ch]
0x1400699fc  mov     [rbp+lpLibFileName], rax
0x140069a00  mov     eax, [r14]
0x140069a03  mov     dword ptr [rbp+Arguments], r8d
0x140069a07  mov     [rbp+var_50], 48h ; 'H'
0x140069a0e  mov     [rbp+var_48], r14
0x140069a12  mov     [rbp+var_40], r12
0x140069a16  movups  xmmword ptr [rbp+lpProcName], xmm0
0x140069a1a  test    al, 1
0x140069a1c  jnz     short loc_140069A47
0x140069a1e  lea     rax, [rbp+var_50]
0x140069a22  mov     [rbp+Arguments], rax
0x140069a26  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140069a2b  xor     edx, edx; dwExceptionFlags
0x140069a2d  lea     r9, [rbp+Arguments]; lpArguments
0x140069a31  mov     ecx, 0C06D0057h; dwExceptionCode
0x140069a36  lea     r8d, [rdx+1]; nNumberOfArguments
0x140069a3a  call    cs:__imp_RaiseException
0x140069a40  xor     eax, eax
0x140069a42  jmp     loc_140069C6B
0x140069a47  mov     rdi, [r15]
0x140069a4a  mov     rsi, r12
0x140069a4d  sub     rsi, rcx
0x140069a50  sar     rsi, 3
0x140069a54  mov     ecx, esi
0x140069a56  mov     rax, [rdx+rcx*8]
0x140069a5a  shr     rax, 3Fh
0x140069a5e  xor     eax, 1
0x140069a61  mov     dword ptr [rbp+lpProcName], eax
0x140069a64  jz      short loc_140069A79
0x140069a66  mov     eax, [rdx+rcx*8]
0x140069a69  lea     rdx, word_140000002
0x140069a70  add     rax, rdx
0x140069a73  mov     [rbp+lpProcName+8], rax
0x140069a77  jmp     short loc_140069A80
0x140069a79  movzx   eax, word ptr [rdx+rcx*8]
0x140069a7d  mov     dword ptr [rbp+lpProcName+8], eax
0x140069a80  mov     rax, cs:__pfnDliNotifyHook2
0x140069a87  xor     ebx, ebx
0x140069a89  test    rax, rax
0x140069a8c  jz      short loc_140069AAD
0x140069a8e  lea     rdx, [rbp+var_50]
0x140069a92  xor     ecx, ecx
0x140069a94  call    cs:__guard_dispatch_icall_fptr
0x140069a9a  mov     rbx, rax
0x140069a9d  test    rax, rax
0x140069aa0  jnz     loc_140069C3C
0x140069aa6  mov     rax, cs:__pfnDliNotifyHook2
0x140069aad  test    rdi, rdi
0x140069ab0  jnz     loc_140069B57
0x140069ab6  test    rax, rax
0x140069ab9  jz      short loc_140069AD0
0x140069abb  lea     rdx, [rbp+var_50]
0x140069abf  lea     ecx, [rdi+1]
0x140069ac2  call    cs:__guard_dispatch_icall_fptr
0x140069ac8  mov     rdi, rax
0x140069acb  test    rax, rax
0x140069ace  jnz     short loc_140069B3C
0x140069ad0  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x140069ad4  xor     r8d, r8d; dwFlags
0x140069ad7  xor     edx, edx; hFile
0x140069ad9  call    cs:__imp_LoadLibraryExA
0x140069adf  mov     rdi, rax
0x140069ae2  test    rax, rax
0x140069ae5  jnz     short loc_140069B3C
0x140069ae7  call    cs:__imp_GetLastError
0x140069aed  mov     [rbp+var_10], eax
0x140069af0  mov     rax, cs:__pfnDliFailureHook2
0x140069af7  test    rax, rax
0x140069afa  jz      short loc_140069B11
0x140069afc  lea     rdx, [rbp+var_50]
0x140069b00  lea     ecx, [rdi+3]
0x140069b03  call    cs:__guard_dispatch_icall_fptr
0x140069b09  mov     rdi, rax
0x140069b0c  test    rax, rax
0x140069b0f  jnz     short loc_140069B3C
0x140069b11  lea     rax, [rbp+var_50]
0x140069b15  mov     [rbp+Arguments], rax
0x140069b19  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140069b1e  xor     edx, edx; dwExceptionFlags
0x140069b20  lea     r9, [rbp+Arguments]; lpArguments
0x140069b24  mov     ecx, 0C06D007Eh; dwExceptionCode
0x140069b29  lea     r8d, [rdx+1]; nNumberOfArguments
0x140069b2d  call    cs:__imp_RaiseException
0x140069b33  mov     rax, [rbp+var_18]
0x140069b37  jmp     loc_140069C6B
0x140069b3c  mov     rax, rdi
0x140069b3f  xchg    rax, [r15]
0x140069b42  cmp     rax, rdi
0x140069b45  jnz     short loc_140069B50
0x140069b47  mov     rcx, rdi; hLibModule
0x140069b4a  call    cs:__imp_FreeLibrary
0x140069b50  mov     rax, cs:__pfnDliNotifyHook2
0x140069b57  mov     [rbp+var_20], rdi
0x140069b5b  test    rax, rax
0x140069b5e  jz      short loc_140069B72
0x140069b60  lea     rdx, [rbp+var_50]
0x140069b64  mov     ecx, 2
0x140069b69  call    cs:__guard_dispatch_icall_fptr
0x140069b6f  mov     rbx, rax
0x140069b72  test    rbx, rbx
0x140069b75  jnz     loc_140069C1A
0x140069b7b  cmp     [r14+14h], ebx
0x140069b7f  jz      short loc_140069BB0
0x140069b81  cmp     [r14+1Ch], ebx
0x140069b85  jz      short loc_140069BB0
0x140069b87  movsxd  rax, dword ptr [rdi+3Ch]
0x140069b8b  cmp     dword ptr [rax+rdi], 4550h
0x140069b92  jnz     short loc_140069BB0
0x140069b94  mov     ecx, dword ptr [rbp+Arguments]
0x140069b97  cmp     [rax+rdi+8], ecx
0x140069b9b  jnz     short loc_140069BB0
0x140069b9d  cmp     rdi, [rax+rdi+30h]
0x140069ba2  jnz     short loc_140069BB0
0x140069ba4  mov     eax, esi
0x140069ba6  mov     rbx, [r13+rax*8+0]
0x140069bab  test    rbx, rbx
0x140069bae  jnz     short loc_140069C1A
0x140069bb0  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x140069bb4  mov     rcx, rdi; hModule
0x140069bb7  call    cs:__imp_GetProcAddress
0x140069bbd  mov     rbx, rax
0x140069bc0  test    rax, rax
0x140069bc3  jnz     short loc_140069C1A
0x140069bc5  call    cs:__imp_GetLastError
0x140069bcb  mov     [rbp+var_10], eax
0x140069bce  mov     rax, cs:__pfnDliFailureHook2
0x140069bd5  test    rax, rax
0x140069bd8  jz      short loc_140069BEF
0x140069bda  lea     rdx, [rbp+var_50]
0x140069bde  lea     ecx, [rbx+4]
0x140069be1  call    cs:__guard_dispatch_icall_fptr
0x140069be7  mov     rbx, rax
0x140069bea  test    rax, rax
0x140069bed  jnz     short loc_140069C1A
0x140069bef  lea     rax, [rbp+var_50]
0x140069bf3  mov     [rbp+Arguments], rax
0x140069bf7  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140069bfc  xor     edx, edx; dwExceptionFlags
0x140069bfe  lea     r9, [rbp+Arguments]; lpArguments
0x140069c02  mov     ecx, 0C06D007Fh; dwExceptionCode
0x140069c07  lea     r8d, [rdx+1]; nNumberOfArguments
0x140069c0b  call    cs:__imp_RaiseException
0x140069c11  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x140069c16  mov     rbx, [rbp+var_18]
0x140069c1a  mov     qword ptr [rbp+var_60], r12
0x140069c1e  lea     r8, [rbp+var_60]
0x140069c22  mov     qword ptr [rbp+var_60+8], rbx
0x140069c26  mov     edx, 8; dwSize
0x140069c2b  movaps  xmm0, [rbp+var_60]
0x140069c2f  mov     rcx, r12; lpAddress
0x140069c32  movdqa  [rbp+var_60], xmm0
0x140069c37  call    GuardedWrite__lambda_7ce9785d57ad9101eca44ba76fd23ffb___; GuardedWrite__lambda_7ce9785d57ad9101eca44ba76fd23ffb_
0x140069c3c  mov     rax, cs:__pfnDliNotifyHook2
0x140069c43  test    rax, rax
0x140069c46  jz      short loc_140069C63
0x140069c48  and     [rbp+var_10], 0
0x140069c4c  lea     rdx, [rbp+var_50]
0x140069c50  mov     ecx, 5
0x140069c55  mov     [rbp+var_20], rdi
0x140069c59  mov     [rbp+var_18], rbx
0x140069c5d  call    cs:__guard_dispatch_icall_fptr
0x140069c63  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140069c68  mov     rax, rbx
0x140069c6b  lea     r11, [rsp+80h+var_s0]
0x140069c73  mov     rbx, [r11+38h]
0x140069c77  mov     rsi, [r11+40h]
0x140069c7b  mov     rdi, [r11+48h]
0x140069c7f  mov     rsp, r11
0x140069c82  pop     r15
0x140069c84  pop     r14
0x140069c86  pop     r13
0x140069c88  pop     r12
0x140069c8a  pop     rbp
0x140069c8b  retn
```
