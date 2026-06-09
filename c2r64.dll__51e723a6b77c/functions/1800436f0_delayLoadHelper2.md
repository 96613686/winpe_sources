# __delayLoadHelper2

- ea: `0x1800436f0`
- end: `0x1800439ea`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `16`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003aca0`
- `0x18003ad70`
- `0x18003afee`
- `0x18003b0e0`
- `0x18003b29e`
- `0x18003b330`
- `0x18003b3b6`
- `0x18003b448`
- `0x18003b516`
- `0x18003b59c`
- `0x18003b6ca`
- `0x18003b828`
- `0x18003b8c6`
- `0x18003b94c`
- `0x18003b9d2`
- `0x18003ba58`

## callees

- `0x1800431cc`
- `0x1800432b8`
- `0x180043640`
- `0x1800436f0`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004384f`
- `KERNEL32!GetLastError` at `0x180043929`
- `KERNEL32!GetLastError` at `0x18004384f`
- `KERNEL32!GetLastError` at `0x180043929`
- `KERNEL32!GetProcAddress` at `0x18004391b`
- `KERNEL32!GetProcAddress` at `0x18004391b`
- `KERNEL32!FreeLibrary` at `0x1800438b2`
- `KERNEL32!FreeLibrary` at `0x1800438b2`
- `KERNEL32!RaiseException` at `0x18004379f`
- `KERNEL32!RaiseException` at `0x180043895`
- `KERNEL32!RaiseException` at `0x18004396f`
- `KERNEL32!RaiseException` at `0x18004379f`
- `KERNEL32!RaiseException` at `0x180043895`
- `KERNEL32!RaiseException` at `0x18004396f`
- `KERNEL32!LoadLibraryExA` at `0x180043841`
- `KERNEL32!LoadLibraryExA` at `0x180043841`

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
  v4 = (volatile __int64 *)((char *)&_NULL_IMPORT_DESCRIPTOR.unused + a1->rvaHmod);
  v5 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaIAT;
  v6 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaINT;
  v7 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaBoundIAT;
  v16.szDll = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaDLLName;
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
    v16.dlp.szProcName = (char *)&_NULL_IMPORT_DESCRIPTOR.unused + *(unsigned int *)&v6[8 * v11] + 2;
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
  sub_1800431CC(a2, 8u);
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
0x1800436f0  mov     [rsp-28h+arg_8], rbx
0x1800436f5  mov     [rsp-28h+arg_10], rsi
0x1800436fa  mov     [rsp-28h+arg_18], rdi
0x1800436ff  push    rbp
0x180043700  push    r12
0x180043702  push    r13
0x180043704  push    r14
0x180043706  push    r15
0x180043708  mov     rbp, rsp
0x18004370b  sub     rsp, 80h
0x180043712  mov     r15, rdx
0x180043715  mov     rsi, rcx
0x180043718  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18004371d  mov     eax, [rsi+4]
0x180043720  lea     r8, __NULL_IMPORT_DESCRIPTOR
0x180043727  mov     r14d, [rsi+8]
0x18004372b  add     rax, r8
0x18004372e  mov     edx, [rsi+0Ch]
0x180043731  add     r14, r8
0x180043734  mov     ecx, [rsi+10h]
0x180043737  add     rdx, r8
0x18004373a  mov     r13d, [rsi+14h]
0x18004373e  add     rcx, r8
0x180043741  add     r13, r8
0x180043744  mov     [rbp+lpLibFileName], rax
0x180043748  mov     eax, [rsi]
0x18004374a  xorps   xmm0, xmm0
0x18004374d  mov     r8d, [rsi+1Ch]
0x180043751  mov     dword ptr [rbp+Arguments], r8d
0x180043755  mov     [rbp+var_50], 48h ; 'H'
0x18004375c  mov     [rbp+var_48], rsi
0x180043760  mov     [rbp+var_40], r15
0x180043764  mov     [rbp+var_20], 0
0x18004376c  mov     [rbp+var_18], 0
0x180043774  mov     [rbp+var_10], 0
0x18004377b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18004377f  test    al, 1
0x180043781  jnz     short loc_1800437AC
0x180043783  lea     rax, [rbp+var_50]
0x180043787  mov     [rbp+Arguments], rax
0x18004378b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180043790  xor     edx, edx; dwExceptionFlags
0x180043792  lea     r9, [rbp+Arguments]; lpArguments
0x180043796  mov     ecx, 0C06D0057h; dwExceptionCode
0x18004379b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18004379f  call    cs:__imp_RaiseException
0x1800437a5  xor     eax, eax
0x1800437a7  jmp     loc_1800439C9
0x1800437ac  mov     rbx, [r14]
0x1800437af  mov     r12, r15
0x1800437b2  sub     r12, rdx
0x1800437b5  sar     r12, 3
0x1800437b9  mov     r12d, r12d
0x1800437bc  mov     rax, [rcx+r12*8]
0x1800437c0  shr     rax, 3Fh
0x1800437c4  xor     eax, 1
0x1800437c7  mov     dword ptr [rbp+lpProcName], eax
0x1800437ca  jz      short loc_1800437E0
0x1800437cc  mov     eax, [rcx+r12*8]
0x1800437d0  lea     rcx, __NULL_IMPORT_DESCRIPTOR.unused+2
0x1800437d7  add     rax, rcx
0x1800437da  mov     [rbp+lpProcName+8], rax
0x1800437de  jmp     short loc_1800437E8
0x1800437e0  movzx   eax, word ptr [rcx+r12*8]
0x1800437e5  mov     dword ptr [rbp+lpProcName+8], eax
0x1800437e8  mov     rax, cs:__pfnDliNotifyHook2
0x1800437ef  xor     edi, edi
0x1800437f1  test    rax, rax
0x1800437f4  jz      short loc_180043815
0x1800437f6  lea     rdx, [rbp+var_50]
0x1800437fa  xor     ecx, ecx
0x1800437fc  call    cs:__guard_dispatch_icall_fptr
0x180043802  mov     rdi, rax
0x180043805  test    rax, rax
0x180043808  jnz     loc_180043997
0x18004380e  mov     rax, cs:__pfnDliNotifyHook2
0x180043815  test    rbx, rbx
0x180043818  jnz     loc_1800438BF
0x18004381e  test    rax, rax
0x180043821  jz      short loc_180043838
0x180043823  lea     rdx, [rbp+var_50]
0x180043827  lea     ecx, [rbx+1]
0x18004382a  call    cs:__guard_dispatch_icall_fptr
0x180043830  mov     rbx, rax
0x180043833  test    rax, rax
0x180043836  jnz     short loc_1800438A4
0x180043838  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18004383c  xor     r8d, r8d; dwFlags
0x18004383f  xor     edx, edx; hFile
0x180043841  call    cs:__imp_LoadLibraryExA
0x180043847  mov     rbx, rax
0x18004384a  test    rax, rax
0x18004384d  jnz     short loc_1800438A4
0x18004384f  call    cs:__imp_GetLastError
0x180043855  mov     [rbp+var_10], eax
0x180043858  mov     rax, cs:__pfnDliFailureHook2
0x18004385f  test    rax, rax
0x180043862  jz      short loc_180043879
0x180043864  lea     rdx, [rbp+var_50]
0x180043868  lea     ecx, [rbx+3]
0x18004386b  call    cs:__guard_dispatch_icall_fptr
0x180043871  mov     rbx, rax
0x180043874  test    rax, rax
0x180043877  jnz     short loc_1800438A4
0x180043879  lea     rax, [rbp+var_50]
0x18004387d  mov     [rbp+Arguments], rax
0x180043881  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180043886  xor     edx, edx; dwExceptionFlags
0x180043888  lea     r9, [rbp+Arguments]; lpArguments
0x18004388c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180043891  lea     r8d, [rdx+1]; nNumberOfArguments
0x180043895  call    cs:__imp_RaiseException
0x18004389b  mov     rax, [rbp+var_18]
0x18004389f  jmp     loc_1800439C9
0x1800438a4  mov     rax, rbx
0x1800438a7  xchg    rax, [r14]
0x1800438aa  cmp     rax, rbx
0x1800438ad  jnz     short loc_1800438B8
0x1800438af  mov     rcx, rbx; hLibModule
0x1800438b2  call    cs:__imp_FreeLibrary
0x1800438b8  mov     rax, cs:__pfnDliNotifyHook2
0x1800438bf  mov     [rbp+var_20], rbx
0x1800438c3  test    rax, rax
0x1800438c6  jz      short loc_1800438DA
0x1800438c8  lea     rdx, [rbp+var_50]
0x1800438cc  mov     ecx, 2
0x1800438d1  call    cs:__guard_dispatch_icall_fptr
0x1800438d7  mov     rdi, rax
0x1800438da  test    rdi, rdi
0x1800438dd  jnz     loc_18004397E
0x1800438e3  cmp     [rsi+14h], edi
0x1800438e6  jz      short loc_180043914
0x1800438e8  cmp     [rsi+1Ch], edi
0x1800438eb  jz      short loc_180043914
0x1800438ed  movsxd  rax, dword ptr [rbx+3Ch]
0x1800438f1  cmp     dword ptr [rax+rbx], 4550h
0x1800438f8  jnz     short loc_180043914
0x1800438fa  mov     ecx, dword ptr [rbp+Arguments]
0x1800438fd  cmp     [rax+rbx+8], ecx
0x180043901  jnz     short loc_180043914
0x180043903  cmp     rbx, [rax+rbx+30h]
0x180043908  jnz     short loc_180043914
0x18004390a  mov     rdi, [r13+r12*8+0]
0x18004390f  test    rdi, rdi
0x180043912  jnz     short loc_18004397E
0x180043914  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x180043918  mov     rcx, rbx; hModule
0x18004391b  call    cs:__imp_GetProcAddress
0x180043921  mov     rdi, rax
0x180043924  test    rax, rax
0x180043927  jnz     short loc_18004397E
0x180043929  call    cs:__imp_GetLastError
0x18004392f  mov     [rbp+var_10], eax
0x180043932  mov     rax, cs:__pfnDliFailureHook2
0x180043939  test    rax, rax
0x18004393c  jz      short loc_180043953
0x18004393e  lea     rdx, [rbp+var_50]
0x180043942  lea     ecx, [rdi+4]
0x180043945  call    cs:__guard_dispatch_icall_fptr
0x18004394b  mov     rdi, rax
0x18004394e  test    rax, rax
0x180043951  jnz     short loc_18004397E
0x180043953  lea     rax, [rbp+var_50]
0x180043957  mov     [rbp+Arguments], rax
0x18004395b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180043960  xor     edx, edx; dwExceptionFlags
0x180043962  lea     r9, [rbp+Arguments]; lpArguments
0x180043966  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18004396b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18004396f  call    cs:__imp_RaiseException
0x180043975  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18004397a  mov     rdi, [rbp+var_18]
0x18004397e  lea     r8, [rbp+var_60]
0x180043982  mov     [rbp+var_60], r15
0x180043986  mov     edx, 8; dwSize
0x18004398b  mov     [rbp+var_58], rdi
0x18004398f  mov     rcx, r15; lpAddress
0x180043992  call    sub_1800431CC
0x180043997  mov     rax, cs:__pfnDliNotifyHook2
0x18004399e  test    rax, rax
0x1800439a1  jz      short loc_1800439C1
0x1800439a3  lea     rdx, [rbp+var_50]
0x1800439a7  mov     [rbp+var_10], 0
0x1800439ae  mov     ecx, 5
0x1800439b3  mov     [rbp+var_20], rbx
0x1800439b7  mov     [rbp+var_18], rdi
0x1800439bb  call    cs:__guard_dispatch_icall_fptr
0x1800439c1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800439c6  mov     rax, rdi
0x1800439c9  lea     r11, [rsp+80h+var_s0]
0x1800439d1  mov     rbx, [r11+38h]
0x1800439d5  mov     rsi, [r11+40h]
0x1800439d9  mov     rdi, [r11+48h]
0x1800439dd  mov     rsp, r11
0x1800439e0  pop     r15
0x1800439e2  pop     r14
0x1800439e4  pop     r13
0x1800439e6  pop     r12
0x1800439e8  pop     rbp
0x1800439e9  retn
```
