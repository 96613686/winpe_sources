# __delayLoadHelper2

- ea: `0x18003ee20`
- end: `0x18003f0f2`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003e7a9`
- `0x18003e83a`

## callees

- `0x18003ea78`
- `0x18003ed84`
- `0x18003ee20`
- `0x18003f280`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003efd5`
- `KERNEL32!FreeLibrary` at `0x18003efd5`
- `KERNEL32!RaiseException` at `0x18003eec2`
- `KERNEL32!RaiseException` at `0x18003efb8`
- `KERNEL32!RaiseException` at `0x18003f092`
- `KERNEL32!RaiseException` at `0x18003eec2`
- `KERNEL32!RaiseException` at `0x18003efb8`
- `KERNEL32!RaiseException` at `0x18003f092`
- `KERNEL32!LoadLibraryExA` at `0x18003ef64`
- `KERNEL32!LoadLibraryExA` at `0x18003ef64`
- `KERNEL32!GetLastError` at `0x18003ef72`
- `KERNEL32!GetLastError` at `0x18003f04c`
- `KERNEL32!GetLastError` at `0x18003ef72`
- `KERNEL32!GetLastError` at `0x18003f04c`
- `KERNEL32!GetProcAddress` at `0x18003f03e`
- `KERNEL32!GetProcAddress` at `0x18003f03e`

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
0x18003ee20  mov     [rsp-28h+arg_8], rbx
0x18003ee25  mov     [rsp-28h+arg_10], rsi
0x18003ee2a  mov     [rsp-28h+arg_18], rdi
0x18003ee2f  push    rbp
0x18003ee30  push    r12
0x18003ee32  push    r13
0x18003ee34  push    r14
0x18003ee36  push    r15
0x18003ee38  mov     rbp, rsp
0x18003ee3b  sub     rsp, 70h
0x18003ee3f  mov     r12, rdx
0x18003ee42  mov     rsi, rcx
0x18003ee45  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18003ee4a  mov     eax, [rsi+4]
0x18003ee4d  lea     rdx, __ImageBase
0x18003ee54  mov     r14d, [rsi+8]
0x18003ee58  add     rax, rdx
0x18003ee5b  mov     r9d, [rsi+0Ch]
0x18003ee5f  add     r14, rdx
0x18003ee62  mov     ecx, [rsi+10h]
0x18003ee65  add     r9, rdx
0x18003ee68  mov     r13d, [rsi+14h]
0x18003ee6c  add     rcx, rdx
0x18003ee6f  and     [rbp+var_20], 0
0x18003ee74  add     r13, rdx
0x18003ee77  and     [rbp+var_18], 0
0x18003ee7c  xorps   xmm0, xmm0
0x18003ee7f  and     [rbp+var_10], 0
0x18003ee83  mov     edx, [rsi+1Ch]
0x18003ee86  mov     [rbp+lpLibFileName], rax
0x18003ee8a  mov     eax, [rsi]
0x18003ee8c  mov     dword ptr [rbp+Arguments], edx
0x18003ee8f  mov     [rbp+var_50], 48h ; 'H'
0x18003ee96  mov     [rbp+var_48], rsi
0x18003ee9a  mov     [rbp+var_40], r12
0x18003ee9e  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18003eea2  test    al, 1
0x18003eea4  jnz     short loc_18003EECF
0x18003eea6  lea     rax, [rbp+var_50]
0x18003eeaa  mov     [rbp+Arguments], rax
0x18003eeae  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18003eeb3  xor     edx, edx; dwExceptionFlags
0x18003eeb5  lea     r9, [rbp+Arguments]; lpArguments
0x18003eeb9  mov     ecx, 0C06D0057h; dwExceptionCode
0x18003eebe  lea     r8d, [rdx+1]; nNumberOfArguments
0x18003eec2  call    cs:__imp_RaiseException
0x18003eec8  xor     eax, eax
0x18003eeca  jmp     loc_18003F0D4
0x18003eecf  mov     rdi, [r14]
0x18003eed2  mov     r15, r12
0x18003eed5  sub     r15, r9
0x18003eed8  sar     r15, 3
0x18003eedc  mov     r15d, r15d
0x18003eedf  mov     rax, [rcx+r15*8]
0x18003eee3  shr     rax, 3Fh
0x18003eee7  xor     eax, 1
0x18003eeea  mov     dword ptr [rbp+lpProcName], eax
0x18003eeed  jz      short loc_18003EF03
0x18003eeef  mov     eax, [rcx+r15*8]
0x18003eef3  lea     rcx, word_180000002
0x18003eefa  add     rax, rcx
0x18003eefd  mov     [rbp+lpProcName+8], rax
0x18003ef01  jmp     short loc_18003EF0B
0x18003ef03  movzx   eax, word ptr [rcx+r15*8]
0x18003ef08  mov     dword ptr [rbp+lpProcName+8], eax
0x18003ef0b  mov     rax, cs:__pfnDliNotifyHook2
0x18003ef12  xor     ebx, ebx
0x18003ef14  test    rax, rax
0x18003ef17  jz      short loc_18003EF38
0x18003ef19  lea     rdx, [rbp+var_50]
0x18003ef1d  xor     ecx, ecx
0x18003ef1f  call    cs:__guard_dispatch_icall_fptr
0x18003ef25  mov     rbx, rax
0x18003ef28  test    rax, rax
0x18003ef2b  jnz     loc_18003F0A5
0x18003ef31  mov     rax, cs:__pfnDliNotifyHook2
0x18003ef38  test    rdi, rdi
0x18003ef3b  jnz     loc_18003EFE2
0x18003ef41  test    rax, rax
0x18003ef44  jz      short loc_18003EF5B
0x18003ef46  lea     rdx, [rbp+var_50]
0x18003ef4a  lea     ecx, [rdi+1]
0x18003ef4d  call    cs:__guard_dispatch_icall_fptr
0x18003ef53  mov     rdi, rax
0x18003ef56  test    rax, rax
0x18003ef59  jnz     short loc_18003EFC7
0x18003ef5b  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18003ef5f  xor     r8d, r8d; dwFlags
0x18003ef62  xor     edx, edx; hFile
0x18003ef64  call    cs:__imp_LoadLibraryExA
0x18003ef6a  mov     rdi, rax
0x18003ef6d  test    rax, rax
0x18003ef70  jnz     short loc_18003EFC7
0x18003ef72  call    cs:__imp_GetLastError
0x18003ef78  mov     [rbp+var_10], eax
0x18003ef7b  mov     rax, cs:__pfnDliFailureHook2
0x18003ef82  test    rax, rax
0x18003ef85  jz      short loc_18003EF9C
0x18003ef87  lea     rdx, [rbp+var_50]
0x18003ef8b  lea     ecx, [rdi+3]
0x18003ef8e  call    cs:__guard_dispatch_icall_fptr
0x18003ef94  mov     rdi, rax
0x18003ef97  test    rax, rax
0x18003ef9a  jnz     short loc_18003EFC7
0x18003ef9c  lea     rax, [rbp+var_50]
0x18003efa0  mov     [rbp+Arguments], rax
0x18003efa4  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18003efa9  xor     edx, edx; dwExceptionFlags
0x18003efab  lea     r9, [rbp+Arguments]; lpArguments
0x18003efaf  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18003efb4  lea     r8d, [rdx+1]; nNumberOfArguments
0x18003efb8  call    cs:__imp_RaiseException
0x18003efbe  mov     rax, [rbp+var_18]
0x18003efc2  jmp     loc_18003F0D4
0x18003efc7  mov     rax, rdi
0x18003efca  xchg    rax, [r14]
0x18003efcd  cmp     rax, rdi
0x18003efd0  jnz     short loc_18003EFDB
0x18003efd2  mov     rcx, rdi; hLibModule
0x18003efd5  call    cs:__imp_FreeLibrary
0x18003efdb  mov     rax, cs:__pfnDliNotifyHook2
0x18003efe2  mov     [rbp+var_20], rdi
0x18003efe6  test    rax, rax
0x18003efe9  jz      short loc_18003EFFD
0x18003efeb  lea     rdx, [rbp+var_50]
0x18003efef  mov     ecx, 2
0x18003eff4  call    cs:__guard_dispatch_icall_fptr
0x18003effa  mov     rbx, rax
0x18003effd  test    rbx, rbx
0x18003f000  jnz     loc_18003F0A1
0x18003f006  cmp     [rsi+14h], ebx
0x18003f009  jz      short loc_18003F037
0x18003f00b  cmp     [rsi+1Ch], ebx
0x18003f00e  jz      short loc_18003F037
0x18003f010  movsxd  rax, dword ptr [rdi+3Ch]
0x18003f014  cmp     dword ptr [rax+rdi], 4550h
0x18003f01b  jnz     short loc_18003F037
0x18003f01d  mov     ecx, dword ptr [rbp+Arguments]
0x18003f020  cmp     [rax+rdi+8], ecx
0x18003f024  jnz     short loc_18003F037
0x18003f026  cmp     rdi, [rax+rdi+30h]
0x18003f02b  jnz     short loc_18003F037
0x18003f02d  mov     rbx, [r13+r15*8+0]
0x18003f032  test    rbx, rbx
0x18003f035  jnz     short loc_18003F0A1
0x18003f037  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x18003f03b  mov     rcx, rdi; hModule
0x18003f03e  call    cs:__imp_GetProcAddress
0x18003f044  mov     rbx, rax
0x18003f047  test    rax, rax
0x18003f04a  jnz     short loc_18003F0A1
0x18003f04c  call    cs:__imp_GetLastError
0x18003f052  mov     [rbp+var_10], eax
0x18003f055  mov     rax, cs:__pfnDliFailureHook2
0x18003f05c  test    rax, rax
0x18003f05f  jz      short loc_18003F076
0x18003f061  lea     rdx, [rbp+var_50]
0x18003f065  lea     ecx, [rbx+4]
0x18003f068  call    cs:__guard_dispatch_icall_fptr
0x18003f06e  mov     rbx, rax
0x18003f071  test    rax, rax
0x18003f074  jnz     short loc_18003F0A1
0x18003f076  lea     rax, [rbp+var_50]
0x18003f07a  mov     [rbp+Arguments], rax
0x18003f07e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18003f083  xor     edx, edx; dwExceptionFlags
0x18003f085  lea     r9, [rbp+Arguments]; lpArguments
0x18003f089  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18003f08e  lea     r8d, [rdx+1]; nNumberOfArguments
0x18003f092  call    cs:__imp_RaiseException
0x18003f098  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18003f09d  mov     rbx, [rbp+var_18]
0x18003f0a1  mov     [r12], rbx
0x18003f0a5  mov     rax, cs:__pfnDliNotifyHook2
0x18003f0ac  test    rax, rax
0x18003f0af  jz      short loc_18003F0CC
0x18003f0b1  and     [rbp+var_10], 0
0x18003f0b5  lea     rdx, [rbp+var_50]
0x18003f0b9  mov     ecx, 5
0x18003f0be  mov     [rbp+var_20], rdi
0x18003f0c2  mov     [rbp+var_18], rbx
0x18003f0c6  call    cs:__guard_dispatch_icall_fptr
0x18003f0cc  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18003f0d1  mov     rax, rbx
0x18003f0d4  lea     r11, [rsp+70h+var_s0]
0x18003f0d9  mov     rbx, [r11+38h]
0x18003f0dd  mov     rsi, [r11+40h]
0x18003f0e1  mov     rdi, [r11+48h]
0x18003f0e5  mov     rsp, r11
0x18003f0e8  pop     r15
0x18003f0ea  pop     r14
0x18003f0ec  pop     r13
0x18003f0ee  pop     r12
0x18003f0f0  pop     rbp
0x18003f0f1  retn
```
