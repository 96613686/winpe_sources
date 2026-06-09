# CActiveXInstallBroker::RunSetupCommand(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong,void * *)

- ea: `0x140005b10`
- end: `0x140005e90`
- name: `?RunSetupCommand@CActiveXInstallBroker@@QEAAJPEAGPEAUHWND__@@0000KPEAPEAX@Z`
- size: `896`
- prototype: `__int64 __usercall@<rax>(CActiveXInstallBroker *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HWND@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400082d0`

## callees

- `0x140004a18`
- `0x140005b10`
- `0x140008984`
- `0x140008f78`
- `0x14000a0d4`
- `0x14000bb30`
- `0x140011010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140005e26`
- `KERNEL32!CloseHandle` at `0x140005e43`
- `KERNEL32!CloseHandle` at `0x140005e26`
- `KERNEL32!CloseHandle` at `0x140005e43`
- `KERNEL32!GetProcAddress` at `0x140005cd1`
- `KERNEL32!GetProcAddress` at `0x140005cd1`
- `KERNEL32!LoadLibraryExW` at `0x140005c8e`
- `KERNEL32!LoadLibraryExW` at `0x140005c8e`
- `KERNEL32!LeaveCriticalSection` at `0x140005e69`
- `KERNEL32!LeaveCriticalSection` at `0x140005e69`
- `KERNEL32!GetCurrentProcess` at `0x140005da6`
- `KERNEL32!GetCurrentProcess` at `0x140005da6`
- `KERNEL32!EnterCriticalSection` at `0x140005b59`
- `KERNEL32!EnterCriticalSection` at `0x140005b59`
- `KERNEL32!OpenProcess` at `0x140005d89`
- `KERNEL32!OpenProcess` at `0x140005d89`
- `KERNEL32!DuplicateHandle` at `0x140005dd6`
- `KERNEL32!DuplicateHandle` at `0x140005dd6`
- `KERNEL32!GetLastError` at `0x140005ca3`
- `KERNEL32!GetLastError` at `0x140005ca3`
- `ole32!CoTaskMemFree` at `0x140005e08`
- `ole32!CoTaskMemFree` at `0x140005e08`
- `ole32!CoImpersonateClient` at `0x140005d5f`
- `ole32!CoImpersonateClient` at `0x140005d5f`
- `ole32!CoRevertToSelf` at `0x140005e54`
- `ole32!CoRevertToSelf` at `0x140005e54`

## string_xrefs

- `0x140005c81`: `IEAdvpack.Dll`
- `0x140005cc7`: `RunSetupCommandW`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::RunSetupCommand(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        HWND a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        void **lpTargetHandle)
{
  __int64 v9; // r12
  unsigned __int16 *v13; // rsi
  int v14; // r13d
  int ExecutablePathFromCommandLine; // edi
  __int64 v16; // rdx
  int v17; // eax
  int v18; // ecx
  __int16 *v19; // rax
  __int16 i; // cx
  int v21; // r8d
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  HANDLE v25; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE hSourceHandle; // [rsp+50h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-40h] BYREF
  int v30; // [rsp+A0h] [rbp+8h]

  v9 = -1;
  v13 = 0;
  v14 = 0;
  pv = 0;
  hSourceHandle = 0;
  v30 = 0;
  if ( !*(_DWORD *)this )
  {
    ExecutablePathFromCommandLine = -2147024882;
LABEL_52:
    CloseHandle((HANDLE)v9);
    goto LABEL_53;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 12) < 2 )
  {
    ExecutablePathFromCommandLine = -2147019873;
    goto LABEL_47;
  }
  if ( !a2 || !a4 || !a5 || !a6 || !a7 )
    goto LABEL_43;
  v16 = *((_QWORD *)this + 8) - (_QWORD)a2;
  do
  {
    v17 = *(unsigned __int16 *)((char *)a2 + v16);
    v18 = *a2 - v17;
    if ( v18 )
      break;
    ++a2;
  }
  while ( v17 );
  if ( v18 )
  {
    ExecutablePathFromCommandLine = -2147024891;
    v14 = 0;
    goto LABEL_47;
  }
  ExecutablePathFromCommandLine = GetExecutablePathFromCommandLine(a4, (unsigned __int16 **)&pv);
  v13 = (unsigned __int16 *)pv;
  if ( ExecutablePathFromCommandLine < 0 )
    goto LABEL_44;
  v19 = (__int16 *)pv;
  if ( pv )
  {
    for ( i = *(_WORD *)pv; i; i = *v19 )
    {
      if ( i == 47 )
        *v19 = 92;
      ++v19;
    }
  }
  if ( (int)AxiPreScanPathW(v13) < 0 || (int)VerifyFileHasExtensionW(v13) < 0 )
  {
LABEL_43:
    ExecutablePathFromCommandLine = -2147024809;
    goto LABEL_44;
  }
  ExecutablePathFromCommandLine = CActiveXInstallBroker::FileIsAuthorized(this, v13, v21);
  if ( ExecutablePathFromCommandLine >= 0 )
  {
    if ( !*((_DWORD *)this + 35) && !(unsigned int)ContainingPathIsTamperProof(v13) )
    {
      ExecutablePathFromCommandLine = -2147024891;
      goto LABEL_44;
    }
    Library = (HMODULE)*((_QWORD *)this + 14);
    if ( Library || (Library = LoadLibraryExW(L"IEAdvpack.Dll", 0, 0x800u), (*((_QWORD *)this + 14) = Library) != 0) )
    {
      ProcAddress = GetProcAddress(Library, "RunSetupCommandW");
      if ( ProcAddress )
      {
        ExecutablePathFromCommandLine = ((__int64 (__fastcall *)(HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, HANDLE *, unsigned int, _QWORD))ProcAddress)(
                                          a3,
                                          a4,
                                          a5,
                                          a6,
                                          a7,
                                          &hSourceHandle,
                                          a8,
                                          0);
        if ( ExecutablePathFromCommandLine < 0 )
          goto LABEL_44;
        if ( lpTargetHandle )
        {
          if ( (char *)hSourceHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            *lpTargetHandle = (void *)-1LL;
          }
          else
          {
            if ( !g_fRunningAsSystem )
            {
              ExecutablePathFromCommandLine = CoImpersonateClient();
              if ( ExecutablePathFromCommandLine < 0 )
                goto LABEL_44;
              v30 = 1;
            }
            v9 = (__int64)OpenProcess(0x40u, 0, *((_DWORD *)this + 30));
            if ( !v9 )
              goto LABEL_29;
            v25 = hSourceHandle;
            CurrentProcess = GetCurrentProcess();
            if ( !DuplicateHandle(CurrentProcess, v25, (HANDLE)v9, lpTargetHandle, 0x20000100u, 0, 0) )
              goto LABEL_29;
          }
        }
        *((_DWORD *)this + 12) = 6;
        goto LABEL_44;
      }
    }
LABEL_29:
    LastError = GetLastError();
    ExecutablePathFromCommandLine = LastError;
    if ( LastError > 0 )
      ExecutablePathFromCommandLine = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_44:
  if ( v13 )
    CoTaskMemFree(v13);
  v14 = v30;
LABEL_47:
  if ( hSourceHandle )
    CloseHandle(hSourceHandle);
  if ( v9 )
    goto LABEL_52;
LABEL_53:
  if ( v14 )
    CoRevertToSelf();
  if ( *(_DWORD *)this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)ExecutablePathFromCommandLine;
}

```

## disassembly

```asm
0x140005b10  mov     rax, rsp
0x140005b13  mov     [rax+10h], rbx
0x140005b17  mov     [rax+18h], r8
0x140005b1b  push    rbp
0x140005b1c  push    rsi
0x140005b1d  push    rdi
0x140005b1e  push    r12
0x140005b20  push    r13
0x140005b22  push    r14
0x140005b24  push    r15
0x140005b26  sub     rsp, 60h
0x140005b2a  xor     edi, edi
0x140005b2c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140005b30  mov     r14, r9
0x140005b33  mov     rbx, rdx
0x140005b36  mov     rbp, rcx
0x140005b39  mov     esi, edi
0x140005b3b  mov     r13d, edi
0x140005b3e  mov     [rax-40h], rdi
0x140005b42  mov     [rax-48h], rdi
0x140005b46  mov     [rsp+98h+arg_0], edi
0x140005b4d  cmp     [rcx], edi
0x140005b4f  jz      loc_140005E39
0x140005b55  add     rcx, 8; lpCriticalSection
0x140005b59  call    cs:__imp_EnterCriticalSection
0x140005b60  nop     dword ptr [rax+rax+00h]
0x140005b65  cmp     dword ptr [rbp+30h], 2
0x140005b69  jge     short loc_140005B77
0x140005b6b  mov     edi, 8007139Fh
0x140005b70  xor     ebx, ebx
0x140005b72  jmp     loc_140005E1C
0x140005b77  test    rbx, rbx
0x140005b7a  jz      loc_140005DF9
0x140005b80  test    r14, r14
0x140005b83  jz      loc_140005DF9
0x140005b89  mov     r13, [rsp+98h+arg_20]
0x140005b91  test    r13, r13
0x140005b94  jz      loc_140005DF9
0x140005b9a  cmp     [rsp+98h+arg_28], rdi
0x140005ba2  jz      loc_140005DF9
0x140005ba8  cmp     [rsp+98h+arg_30], rdi
0x140005bb0  jz      loc_140005DF9
0x140005bb6  mov     rdx, [rbp+40h]
0x140005bba  sub     rdx, rbx
0x140005bbd  movzx   ecx, word ptr [rbx]
0x140005bc0  movzx   eax, word ptr [rbx+rdx]
0x140005bc4  sub     ecx, eax
0x140005bc6  jnz     short loc_140005BD0
0x140005bc8  add     rbx, 2
0x140005bcc  test    eax, eax
0x140005bce  jnz     short loc_140005BBD
0x140005bd0  xor     ebx, ebx
0x140005bd2  test    ecx, ecx
0x140005bd4  jz      short loc_140005BE3
0x140005bd6  mov     edi, 80070005h
0x140005bdb  mov     r13d, ebx
0x140005bde  jmp     loc_140005E1C
0x140005be3  lea     rdx, [rsp+98h+pv]; unsigned __int16 **
0x140005be8  mov     rcx, r14; Str
0x140005beb  call    ?GetExecutablePathFromCommandLine@@YAJPEBGPEAPEAG@Z; GetExecutablePathFromCommandLine(ushort const *,ushort * *)
0x140005bf0  mov     edi, eax
0x140005bf2  mov     rsi, [rsp+98h+pv]
0x140005bf7  test    eax, eax
0x140005bf9  js      loc_140005E00
0x140005bff  mov     rax, rsi
0x140005c02  test    rsi, rsi
0x140005c05  jz      short loc_140005C23
0x140005c07  movzx   ecx, word ptr [rsi]
0x140005c0a  jmp     short loc_140005C1E
0x140005c0c  cmp     cx, 2Fh ; '/'
0x140005c10  jnz     short loc_140005C17
0x140005c12  mov     word ptr [rax], 5Ch ; '\'
0x140005c17  add     rax, 2
0x140005c1b  movzx   ecx, word ptr [rax]
0x140005c1e  test    cx, cx
0x140005c21  jnz     short loc_140005C0C
0x140005c23  mov     rcx, rsi; unsigned __int16 *
0x140005c26  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x140005c2b  test    eax, eax
0x140005c2d  js      loc_140005DFB
0x140005c33  mov     rcx, rsi; lpFileName
0x140005c36  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x140005c3b  test    eax, eax
0x140005c3d  js      loc_140005DFB
0x140005c43  mov     rdx, rsi; unsigned __int16 *
0x140005c46  mov     rcx, rbp; this
0x140005c49  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x140005c4e  mov     edi, eax
0x140005c50  test    eax, eax
0x140005c52  js      loc_140005E00
0x140005c58  cmp     [rbp+8Ch], ebx
0x140005c5e  jnz     short loc_140005C76
0x140005c60  mov     rcx, rsi; unsigned __int16 *
0x140005c63  call    ?ContainingPathIsTamperProof@@YAHPEBG@Z; ContainingPathIsTamperProof(ushort const *)
0x140005c68  test    eax, eax
0x140005c6a  jnz     short loc_140005C76
0x140005c6c  mov     edi, 80070005h
0x140005c71  jmp     loc_140005E00
0x140005c76  mov     rax, [rbp+70h]
0x140005c7a  test    rax, rax
0x140005c7d  jnz     short loc_140005CC7
0x140005c7f  xor     edx, edx; hFile
0x140005c81  lea     rcx, LibFileName; "IEAdvpack.Dll"
0x140005c88  mov     r8d, 800h; dwFlags
0x140005c8e  call    cs:__imp_LoadLibraryExW
0x140005c95  nop     dword ptr [rax+rax+00h]
0x140005c9a  mov     [rbp+70h], rax
0x140005c9e  test    rax, rax
0x140005ca1  jnz     short loc_140005CC7
0x140005ca3  call    cs:__imp_GetLastError
0x140005caa  nop     dword ptr [rax+rax+00h]
0x140005caf  mov     edi, eax
0x140005cb1  test    eax, eax
0x140005cb3  jle     loc_140005E00
0x140005cb9  movzx   edi, ax
0x140005cbc  or      edi, 80070000h
0x140005cc2  jmp     loc_140005E00
0x140005cc7  lea     rdx, aRunsetupcomman; "RunSetupCommandW"
0x140005cce  mov     rcx, rax; hModule
0x140005cd1  call    cs:__imp_GetProcAddress
0x140005cd8  nop     dword ptr [rax+rax+00h]
0x140005cdd  mov     r10, rax
0x140005ce0  test    rax, rax
0x140005ce3  jz      short loc_140005CA3
0x140005ce5  mov     eax, [rsp+98h+arg_38]
0x140005cec  mov     r8, r13
0x140005cef  mov     r9, [rsp+98h+arg_28]
0x140005cf7  mov     rdx, r14
0x140005cfa  mov     rcx, [rsp+98h+arg_10]
0x140005d02  mov     [rsp+98h+var_60], rbx
0x140005d07  mov     [rsp+98h+dwOptions], eax
0x140005d0b  lea     rax, [rsp+98h+hSourceHandle]
0x140005d10  mov     qword ptr [rsp+98h+bInheritHandle], rax
0x140005d15  mov     rax, [rsp+98h+arg_30]
0x140005d1d  mov     qword ptr [rsp+98h+dwDesiredAccess], rax
0x140005d22  mov     rax, r10
0x140005d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d2a  mov     edi, eax
0x140005d2c  test    eax, eax
0x140005d2e  js      loc_140005E00
0x140005d34  mov     r14, [rsp+98h+lpTargetHandle]
0x140005d3c  test    r14, r14
0x140005d3f  jz      loc_140005DF0
0x140005d45  mov     rax, [rsp+98h+hSourceHandle]
0x140005d4a  dec     rax
0x140005d4d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005d51  ja      loc_140005DED
0x140005d57  cmp     cs:?g_fRunningAsSystem@@3HA, ebx; int g_fRunningAsSystem
0x140005d5d  jnz     short loc_140005D80
0x140005d5f  call    cs:__imp_CoImpersonateClient
0x140005d66  nop     dword ptr [rax+rax+00h]
0x140005d6b  mov     edi, eax
0x140005d6d  test    eax, eax
0x140005d6f  js      loc_140005E00
0x140005d75  mov     [rsp+98h+arg_0], 1
0x140005d80  mov     r8d, [rbp+78h]; dwProcessId
0x140005d84  xor     edx, edx; bInheritHandle
0x140005d86  lea     ecx, [rdx+40h]; dwDesiredAccess
0x140005d89  call    cs:__imp_OpenProcess
0x140005d90  nop     dword ptr [rax+rax+00h]
0x140005d95  mov     r12, rax
0x140005d98  test    rax, rax
0x140005d9b  jz      loc_140005CA3
0x140005da1  mov     rbx, [rsp+98h+hSourceHandle]
0x140005da6  call    cs:__imp_GetCurrentProcess
0x140005dad  nop     dword ptr [rax+rax+00h]
0x140005db2  mov     [rsp+98h+dwOptions], 0; dwOptions
0x140005dba  mov     r9, r14; lpTargetHandle
0x140005dbd  mov     rcx, rax; hSourceProcessHandle
0x140005dc0  mov     [rsp+98h+bInheritHandle], 0; bInheritHandle
0x140005dc8  mov     r8, r12; hTargetProcessHandle
0x140005dcb  mov     [rsp+98h+dwDesiredAccess], 20000100h; dwDesiredAccess
0x140005dd3  mov     rdx, rbx; hSourceHandle
0x140005dd6  call    cs:__imp_DuplicateHandle
0x140005ddd  nop     dword ptr [rax+rax+00h]
0x140005de2  xor     ebx, ebx
0x140005de4  test    eax, eax
0x140005de6  jnz     short loc_140005DF0
0x140005de8  jmp     loc_140005CA3
0x140005ded  mov     [r14], r12
0x140005df0  mov     dword ptr [rbp+30h], 6
0x140005df7  jmp     short loc_140005E00
0x140005df9  xor     ebx, ebx
0x140005dfb  mov     edi, 80070057h
0x140005e00  test    rsi, rsi
0x140005e03  jz      short loc_140005E14
0x140005e05  mov     rcx, rsi; pv
0x140005e08  call    cs:__imp_CoTaskMemFree
0x140005e0f  nop     dword ptr [rax+rax+00h]
0x140005e14  mov     r13d, [rsp+98h+arg_0]
0x140005e1c  mov     rcx, [rsp+98h+hSourceHandle]; hObject
0x140005e21  test    rcx, rcx
0x140005e24  jz      short loc_140005E32
0x140005e26  call    cs:__imp_CloseHandle
0x140005e2d  nop     dword ptr [rax+rax+00h]
0x140005e32  test    r12, r12
0x140005e35  jnz     short loc_140005E40
0x140005e37  jmp     short loc_140005E4F
0x140005e39  mov     edi, 8007000Eh
0x140005e3e  xor     ebx, ebx
0x140005e40  mov     rcx, r12; hObject
0x140005e43  call    cs:__imp_CloseHandle
0x140005e4a  nop     dword ptr [rax+rax+00h]
0x140005e4f  test    r13d, r13d
0x140005e52  jz      short loc_140005E60
0x140005e54  call    cs:__imp_CoRevertToSelf
0x140005e5b  nop     dword ptr [rax+rax+00h]
0x140005e60  cmp     [rbp+0], ebx
0x140005e63  jz      short loc_140005E75
0x140005e65  lea     rcx, [rbp+8]; lpCriticalSection
0x140005e69  call    cs:__imp_LeaveCriticalSection
0x140005e70  nop     dword ptr [rax+rax+00h]
0x140005e75  mov     rbx, [rsp+98h+arg_8]
0x140005e7d  mov     eax, edi
0x140005e7f  add     rsp, 60h
0x140005e83  pop     r15
0x140005e85  pop     r14
0x140005e87  pop     r13
0x140005e89  pop     r12
0x140005e8b  pop     rdi
0x140005e8c  pop     rsi
0x140005e8d  pop     rbp
0x140005e8e  retn
```
