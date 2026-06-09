# CActiveXInstallBroker::RegisterExeFile(ushort *,ushort *,int,_PROCESS_INFORMATION *)

- ea: `0x140005630`
- end: `0x14000591d`
- name: `?RegisterExeFile@CActiveXInstallBroker@@QEAAJPEAG0HPEAU_PROCESS_INFORMATION@@@Z`
- size: `749`
- prototype: `__int64 __usercall@<rax>(CActiveXInstallBroker *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008200`

## callees

- `0x140001af3`
- `0x140004314`
- `0x1400045a0`
- `0x140004a18`
- `0x140005630`
- `0x140008984`
- `0x140008f78`
- `0x14000bb30`
- `0x14000d094`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400058c0`
- `KERNEL32!CloseHandle` at `0x1400058d6`
- `KERNEL32!CloseHandle` at `0x1400058c0`
- `KERNEL32!CloseHandle` at `0x1400058d6`
- `KERNEL32!CreateProcessW` at `0x14000585e`
- `KERNEL32!CreateProcessW` at `0x14000585e`
- `KERNEL32!LeaveCriticalSection` at `0x1400058eb`
- `KERNEL32!LeaveCriticalSection` at `0x1400058eb`
- `KERNEL32!EnterCriticalSection` at `0x1400056bb`
- `KERNEL32!EnterCriticalSection` at `0x1400056bb`
- `KERNEL32!GetLastError` at `0x14000586e`
- `KERNEL32!GetLastError` at `0x14000586e`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::RegisterExeFile(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        struct _PROCESS_INFORMATION *a5)
{
  signed int IsAuthorized; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // eax
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  WCHAR v17; // ax
  WCHAR *v18; // rcx
  int v19; // r8d
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v26[542]; // [rsp+2F2h] [rbp+1F2h] BYREF

  CommandLine = 0;
  memset_0(v26, 0, 0x212u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( *(_DWORD *)this )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 12) < 6 )
    {
      IsAuthorized = -2147019873;
      goto LABEL_39;
    }
    if ( !a2 || !a3 || !a5 )
      goto LABEL_37;
    v10 = *((_QWORD *)this + 8) - (_QWORD)a2;
    do
    {
      v11 = *(unsigned __int16 *)((char *)a2 + v10);
      v12 = *a2 - v11;
      if ( v12 )
        break;
      ++a2;
    }
    while ( v11 );
    if ( v12 )
      goto LABEL_11;
    v13 = 2147483646;
    v14 = FileName;
    v15 = 260;
    do
    {
      if ( !v13 )
        break;
      if ( !*a3 )
        break;
      *v14++ = *a3++;
      --v13;
      --v15;
    }
    while ( v15 );
    v16 = v14 - 1;
    if ( v15 )
      v16 = v14;
    *v16 = 0;
    if ( !v15 )
      goto LABEL_37;
    v17 = FileName[0];
    if ( FileName[0] )
    {
      v18 = FileName;
      do
      {
        if ( v17 == 47 )
          *v18 = 92;
        v17 = *++v18;
      }
      while ( *v18 );
    }
    if ( (int)AxiPreScanPathW(FileName) >= 0 && (int)VerifyFileHasExtensionW(FileName) >= 0 )
    {
      IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, FileName, v19);
      if ( IsAuthorized >= 0 )
      {
        if ( !*((_DWORD *)this + 35) && !(unsigned int)ContainingPathIsTamperProof(FileName) )
        {
LABEL_11:
          IsAuthorized = -2147024891;
          goto LABEL_39;
        }
        IsAuthorized = QuotePath(FileName, 0x10Au, &CommandLine);
        if ( IsAuthorized >= 0 )
        {
          if ( !a4 || (IsAuthorized = StringCchCatW(&CommandLine, 0x10Au, L" /RegServer"), IsAuthorized >= 0) )
          {
            StartupInfo.cb = 104;
            if ( CreateProcessW(0, &CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
            {
              IsAuthorized = CActiveXInstallBroker::DuplicateProcessInformation(this, &ProcessInformation, a5);
              if ( IsAuthorized >= 0 )
                *((_DWORD *)this + 12) = 8;
            }
            else
            {
              LastError = GetLastError();
              IsAuthorized = LastError;
              if ( LastError > 0 )
                IsAuthorized = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
    else
    {
LABEL_37:
      IsAuthorized = -2147024809;
    }
  }
  else
  {
    IsAuthorized = -2147024882;
  }
LABEL_39:
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( *(_DWORD *)this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)IsAuthorized;
}

```

## disassembly

```asm
0x140005630  push    rbp
0x140005632  push    rbx
0x140005633  push    rsi
0x140005634  push    rdi
0x140005635  push    r12
0x140005637  push    r13
0x140005639  push    r14
0x14000563b  push    r15
0x14000563d  lea     rbp, [rsp-428h]
0x140005645  sub     rsp, 528h
0x14000564c  mov     rax, cs:__security_cookie
0x140005653  xor     rax, rsp
0x140005656  mov     [rbp+460h+var_50], rax
0x14000565d  mov     r15, [rbp+460h+arg_20]
0x140005664  mov     r14, r8
0x140005667  mov     rbx, rdx
0x14000566a  mov     rsi, rcx
0x14000566d  xor     r13d, r13d
0x140005670  lea     rcx, [rbp+460h+var_26E]; void *
0x140005677  xor     edx, edx; Val
0x140005679  mov     [rbp+460h+CommandLine], r13w
0x140005681  mov     r8d, 212h; Size
0x140005687  mov     r12d, r9d
0x14000568a  call    memset_0
0x14000568f  xor     edx, edx; Val
0x140005691  lea     r8d, [r13+68h]; Size
0x140005695  lea     rcx, [rsp+560h+StartupInfo]; void *
0x14000569a  call    memset_0
0x14000569f  xor     eax, eax
0x1400056a1  xorps   xmm0, xmm0
0x1400056a4  movups  xmmword ptr [rsp+560h+ProcessInformation.hProcess], xmm0
0x1400056a9  mov     qword ptr [rsp+560h+ProcessInformation.dwProcessId], rax
0x1400056ae  cmp     [rsi], r13d
0x1400056b1  jz      loc_1400058B1
0x1400056b7  lea     rcx, [rsi+8]; lpCriticalSection
0x1400056bb  call    cs:__imp_EnterCriticalSection
0x1400056c2  nop     dword ptr [rax+rax+00h]
0x1400056c7  cmp     dword ptr [rsi+30h], 6
0x1400056cb  jge     short loc_1400056D7
0x1400056cd  mov     ebx, 8007139Fh
0x1400056d2  jmp     loc_1400058B6
0x1400056d7  test    rbx, rbx
0x1400056da  jz      loc_1400058AA
0x1400056e0  test    r14, r14
0x1400056e3  jz      loc_1400058AA
0x1400056e9  test    r15, r15
0x1400056ec  jz      loc_1400058AA
0x1400056f2  mov     rdx, [rsi+40h]
0x1400056f6  sub     rdx, rbx
0x1400056f9  movzx   eax, word ptr [rbx]
0x1400056fc  movzx   ecx, word ptr [rbx+rdx]
0x140005700  sub     eax, ecx
0x140005702  jnz     short loc_14000570C
0x140005704  add     rbx, 2
0x140005708  test    ecx, ecx
0x14000570a  jnz     short loc_1400056F9
0x14000570c  test    eax, eax
0x14000570e  jz      short loc_14000571A
0x140005710  mov     ebx, 80070005h
0x140005715  jmp     loc_1400058B6
0x14000571a  mov     ecx, 7FFFFFFEh
0x14000571f  lea     rax, [rbp+460h+FileName]
0x140005723  mov     edx, 104h
0x140005728  test    rcx, rcx
0x14000572b  jz      short loc_14000574C
0x14000572d  movzx   r8d, word ptr [r14]
0x140005731  test    r8w, r8w
0x140005735  jz      short loc_14000574C
0x140005737  mov     [rax], r8w
0x14000573b  add     r14, 2
0x14000573f  add     rax, 2
0x140005743  dec     rcx
0x140005746  sub     rdx, 1
0x14000574a  jnz     short loc_140005728
0x14000574c  test    rdx, rdx
0x14000574f  lea     rcx, [rax-2]
0x140005753  cmovnz  rcx, rax
0x140005757  mov     [rcx], r13w
0x14000575b  jz      loc_1400058AA
0x140005761  movzx   eax, [rbp+460h+FileName]
0x140005765  test    ax, ax
0x140005768  jz      short loc_140005785
0x14000576a  lea     rcx, [rbp+460h+FileName]
0x14000576e  cmp     ax, 2Fh ; '/'
0x140005772  jnz     short loc_140005779
0x140005774  mov     word ptr [rcx], 5Ch ; '\'
0x140005779  add     rcx, 2
0x14000577d  movzx   eax, word ptr [rcx]
0x140005780  test    ax, ax
0x140005783  jnz     short loc_14000576E
0x140005785  lea     rcx, [rbp+460h+FileName]; unsigned __int16 *
0x140005789  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x14000578e  test    eax, eax
0x140005790  js      loc_1400058AA
0x140005796  lea     rcx, [rbp+460h+FileName]; lpFileName
0x14000579a  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x14000579f  test    eax, eax
0x1400057a1  js      loc_1400058AA
0x1400057a7  lea     rdx, [rbp+460h+FileName]; unsigned __int16 *
0x1400057ab  mov     rcx, rsi; this
0x1400057ae  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x1400057b3  mov     ebx, eax
0x1400057b5  test    eax, eax
0x1400057b7  js      loc_1400058B6
0x1400057bd  cmp     [rsi+8Ch], r13d
0x1400057c4  jnz     short loc_1400057D7
0x1400057c6  lea     rcx, [rbp+460h+FileName]; unsigned __int16 *
0x1400057ca  call    ?ContainingPathIsTamperProof@@YAHPEBG@Z; ContainingPathIsTamperProof(ushort const *)
0x1400057cf  test    eax, eax
0x1400057d1  jz      loc_140005710
0x1400057d7  mov     r14d, 10Ah
0x1400057dd  lea     r8, [rbp+460h+CommandLine]; unsigned __int16 *
0x1400057e4  mov     edx, r14d; unsigned int
0x1400057e7  lea     rcx, [rbp+460h+FileName]; unsigned __int16 *
0x1400057eb  call    ?QuotePath@@YAJPEBGKPEAG@Z; QuotePath(ushort const *,ulong,ushort *)
0x1400057f0  mov     ebx, eax
0x1400057f2  test    eax, eax
0x1400057f4  js      loc_1400058B6
0x1400057fa  test    r12d, r12d
0x1400057fd  jz      short loc_14000581F
0x1400057ff  lea     r8, aRegserver_0; " /RegServer"
0x140005806  mov     edx, r14d; unsigned __int64
0x140005809  lea     rcx, [rbp+460h+CommandLine]; unsigned __int16 *
0x140005810  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005815  mov     ebx, eax
0x140005817  test    eax, eax
0x140005819  js      loc_1400058B6
0x14000581f  lea     rax, [rsp+560h+ProcessInformation]
0x140005824  mov     [rsp+560h+StartupInfo.cb], 68h ; 'h'
0x14000582c  mov     [rsp+560h+lpProcessInformation], rax; lpProcessInformation
0x140005831  lea     rdx, [rbp+460h+CommandLine]; lpCommandLine
0x140005838  lea     rax, [rsp+560h+StartupInfo]
0x14000583d  xor     r9d, r9d; lpThreadAttributes
0x140005840  mov     [rsp+560h+lpStartupInfo], rax; lpStartupInfo
0x140005845  xor     r8d, r8d; lpProcessAttributes
0x140005848  mov     [rsp+560h+lpCurrentDirectory], r13; lpCurrentDirectory
0x14000584d  xor     ecx, ecx; lpApplicationName
0x14000584f  mov     [rsp+560h+lpEnvironment], r13; lpEnvironment
0x140005854  mov     [rsp+560h+dwCreationFlags], r13d; dwCreationFlags
0x140005859  mov     [rsp+560h+bInheritHandles], r13d; bInheritHandles
0x14000585e  call    cs:__imp_CreateProcessW
0x140005865  nop     dword ptr [rax+rax+00h]
0x14000586a  test    eax, eax
0x14000586c  jnz     short loc_14000588B
0x14000586e  call    cs:__imp_GetLastError
0x140005875  nop     dword ptr [rax+rax+00h]
0x14000587a  mov     ebx, eax
0x14000587c  test    eax, eax
0x14000587e  jle     short loc_1400058B6
0x140005880  movzx   ebx, ax
0x140005883  or      ebx, 80070000h
0x140005889  jmp     short loc_1400058B6
0x14000588b  mov     r8, r15; struct _PROCESS_INFORMATION *
0x14000588e  lea     rdx, [rsp+560h+ProcessInformation]; struct _PROCESS_INFORMATION *
0x140005893  mov     rcx, rsi; this
0x140005896  call    ?DuplicateProcessInformation@CActiveXInstallBroker@@AEAAJPEAU_PROCESS_INFORMATION@@0@Z; CActiveXInstallBroker::DuplicateProcessInformation(_PROCESS_INFORMATION *,_PROCESS_INFORMATION *)
0x14000589b  mov     ebx, eax
0x14000589d  test    eax, eax
0x14000589f  js      short loc_1400058B6
0x1400058a1  mov     dword ptr [rsi+30h], 8
0x1400058a8  jmp     short loc_1400058B6
0x1400058aa  mov     ebx, 80070057h
0x1400058af  jmp     short loc_1400058B6
0x1400058b1  mov     ebx, 8007000Eh
0x1400058b6  mov     rcx, [rsp+560h+ProcessInformation.hThread]; hObject
0x1400058bb  test    rcx, rcx
0x1400058be  jz      short loc_1400058CC
0x1400058c0  call    cs:__imp_CloseHandle
0x1400058c7  nop     dword ptr [rax+rax+00h]
0x1400058cc  mov     rcx, [rsp+560h+ProcessInformation.hProcess]; hObject
0x1400058d1  test    rcx, rcx
0x1400058d4  jz      short loc_1400058E2
0x1400058d6  call    cs:__imp_CloseHandle
0x1400058dd  nop     dword ptr [rax+rax+00h]
0x1400058e2  cmp     [rsi], r13d
0x1400058e5  jz      short loc_1400058F7
0x1400058e7  lea     rcx, [rsi+8]; lpCriticalSection
0x1400058eb  call    cs:__imp_LeaveCriticalSection
0x1400058f2  nop     dword ptr [rax+rax+00h]
0x1400058f7  mov     eax, ebx
0x1400058f9  mov     rcx, [rbp+460h+var_50]
0x140005900  xor     rcx, rsp; StackCookie
0x140005903  call    __security_check_cookie
0x140005908  add     rsp, 528h
0x14000590f  pop     r15
0x140005911  pop     r14
0x140005913  pop     r13
0x140005915  pop     r12
0x140005917  pop     rdi
0x140005918  pop     rsi
0x140005919  pop     rbx
0x14000591a  pop     rbp
0x14000591b  retn
```
