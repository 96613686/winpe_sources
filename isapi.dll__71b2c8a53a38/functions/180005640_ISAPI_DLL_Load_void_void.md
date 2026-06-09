# ISAPI_DLL::Load(void *,void *)

- ea: `0x180005640`
- end: `0x1800059cd`
- name: `?Load@ISAPI_DLL@@QEAAJPEAX0@Z`
- size: `909`
- prototype: `__int64 __fastcall(ISAPI_DLL *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005224`

## callees

- `0x1800050fc`
- `0x180005640`
- `0x1800059d4`
- `0x180005a78`
- `0x180012482`
- `0x18001249a`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005695`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005695`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800056c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800056c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000580d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000595b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000580d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000595b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005790`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005790`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000583e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005859`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000583e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005859`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800059ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800059ac`
- `iisutil!PuDbgPrint` at `0x18000572a`
- `iisutil!PuDbgPrint` at `0x1800057fe`
- `iisutil!PuDbgPrint` at `0x180005905`
- `iisutil!PuDbgPrint` at `0x18000572a`
- `iisutil!PuDbgPrint` at `0x1800057fe`
- `iisutil!PuDbgPrint` at `0x180005905`

## string_xrefs

- `0x180005708`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x1800057dc`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x1800058e7`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x18000571e`: `[ISAPI_DLL::Load] SetThreadToken failed for %S. Error %0x08x\n`
- `0x1800056fa`: `ISAPI_DLL::Load`
- `0x1800057d1`: `ISAPI_DLL::Load`
- `0x1800058dc`: `ISAPI_DLL::Load`
- `0x1800057f2`: `[ISAPI_DLL::Load] LoadLibraryEx %S failed. Error %d\n`
- `0x18000581c`: `GetExtensionVersion`
- `0x180005830`: `TerminateExtension`
- `0x18000584b`: `HttpExtensionProc`
- `0x1800058f9`: `ISAPI_DLL::Load() Loaded extension %S,  description "%s"\n`

## pseudocode

```c
__int64 __fastcall ISAPI_DLL::Load(ISAPI_DLL *this, void *a2, void *a3)
{
  BOOL v6; // esi
  signed int v7; // eax
  signed int Acl; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  DWORD v11; // eax
  FARPROC ProcAddress; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  FARPROC v16; // rax
  unsigned int (__fastcall *v17)(_BYTE *); // rdx
  signed int v18; // eax
  HMODULE v20; // rcx
  _BYTE v21[4]; // [rsp+40h] [rbp-148h] BYREF
  char v22[268]; // [rsp+44h] [rbp-144h] BYREF

  memset_0(v21, 0, 0x104u);
  if ( *((_DWORD *)this + 40) )
    return 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  if ( *((_DWORD *)this + 40) )
  {
LABEL_32:
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
    return 0;
  }
  v6 = 0;
  if ( wcsncmp_0(*((const wchar_t **)this + 5), L"\\\\", 2u) || (v6 = SetThreadToken(0, a2)) )
  {
    Acl = ISAPI_DLL::LoadAcl(this, (ISAPI_DLL *)((char *)this + 64));
    if ( Acl < 0 )
      goto LABEL_35;
    if ( a2 && !ISAPI_DLL::AccessCheck(this, a2, a3) )
    {
      Acl = -2147024891;
      goto LABEL_35;
    }
    if ( !a3 || (Acl = ISAPI_DLL::SetFastSid(this, a3), Acl >= 0) )
    {
      Library = LoadLibraryExW(*((LPCWSTR *)this + 12), 0, 8u);
      *((_QWORD *)this + 24) = Library;
      if ( !Library )
      {
        LastError = GetLastError();
        Acl = LastError;
        if ( LastError > 0 )
          Acl = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v11 = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
            324,
            "ISAPI_DLL::Load",
            "[ISAPI_DLL::Load] LoadLibraryEx %S failed. Error %d\n",
            *((const wchar_t **)this + 5),
            v11);
        }
        goto LABEL_35;
      }
      if ( v6 )
      {
        RevertToSelf();
        v6 = 0;
      }
      ProcAddress = GetProcAddress(*((HMODULE *)this + 24), "GetExtensionVersion");
      v13 = (HMODULE)*((_QWORD *)this + 24);
      *((_QWORD *)this + 21) = ProcAddress;
      v14 = GetProcAddress(v13, "TerminateExtension");
      v15 = (HMODULE)*((_QWORD *)this + 24);
      *((_QWORD *)this + 22) = v14;
      v16 = GetProcAddress(v15, "HttpExtensionProc");
      v17 = (unsigned int (__fastcall *)(_BYTE *))*((_QWORD *)this + 21);
      *((_QWORD *)this + 23) = v16;
      if ( v17 && v16 )
      {
        if ( !v17(v21) )
        {
          if ( GetLastError() )
          {
            v18 = GetLastError();
            Acl = v18;
            if ( v18 > 0 )
              Acl = (unsigned __int16)v18 | 0x80070000;
          }
          else
          {
            Acl = -2147467259;
          }
          goto LABEL_35;
        }
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
            390,
            "ISAPI_DLL::Load",
            "ISAPI_DLL::Load() Loaded extension %S,  description \"%s\"\n",
            *((const wchar_t **)this + 5),
            v22);
        *((_DWORD *)this + 40) = 1;
        goto LABEL_32;
      }
      Acl = -2147024769;
      *((_QWORD *)this + 22) = 0;
    }
LABEL_35:
    if ( v6 )
      RevertToSelf();
    goto LABEL_37;
  }
  v7 = GetLastError();
  Acl = v7;
  if ( v7 > 0 )
    Acl = (unsigned __int16)v7 | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
      275,
      "ISAPI_DLL::Load",
      "[ISAPI_DLL::Load] SetThreadToken failed for %S. Error %0x08x\n",
      *((const wchar_t **)this + 5),
      Acl);
LABEL_37:
  if ( *((_QWORD *)this + 23) )
    *((_QWORD *)this + 23) = 0;
  if ( *((_QWORD *)this + 21) )
    *((_QWORD *)this + 21) = 0;
  if ( *((_QWORD *)this + 22) )
    *((_QWORD *)this + 22) = 0;
  v20 = (HMODULE)*((_QWORD *)this + 24);
  if ( v20 )
  {
    FreeLibrary(v20);
    *((_QWORD *)this + 24) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x180005640  mov     [rsp+arg_18], rbx
0x180005645  push    rbp
0x180005646  push    rsi
0x180005647  push    rdi
0x180005648  push    r14
0x18000564a  push    r15
0x18000564c  sub     rsp, 160h
0x180005653  mov     rax, cs:__security_cookie
0x18000565a  xor     rax, rsp
0x18000565d  mov     [rsp+188h+var_38], rax
0x180005665  mov     r14, r8
0x180005668  mov     rbp, rdx
0x18000566b  mov     rdi, rcx
0x18000566e  xor     edx, edx; Val
0x180005670  mov     r8d, 104h; Size
0x180005676  lea     rcx, [rsp+188h+var_148]; void *
0x18000567b  call    memset_0
0x180005680  mov     eax, [rdi+0A0h]
0x180005686  test    eax, eax
0x180005688  jnz     loc_18000591E
0x18000568e  lea     r15, [rdi+78h]
0x180005692  mov     rcx, r15; lpCriticalSection
0x180005695  call    cs:__imp_EnterCriticalSection
0x18000569b  mov     eax, [rdi+0A0h]
0x1800056a1  test    eax, eax
0x1800056a3  jnz     loc_180005915
0x1800056a9  mov     rcx, [rdi+28h]; String1
0x1800056ad  lea     r8d, [rax+2]; MaxCount
0x1800056b1  lea     rdx, asc_180016DCC; "\\\\"
0x1800056b8  xor     esi, esi
0x1800056ba  call    wcsncmp_0
0x1800056bf  test    eax, eax
0x1800056c1  jnz     short loc_180005735
0x1800056c3  mov     rdx, rbp; Token
0x1800056c6  xor     ecx, ecx; Thread
0x1800056c8  call    cs:__imp_SetThreadToken
0x1800056ce  mov     esi, eax
0x1800056d0  test    eax, eax
0x1800056d2  jnz     short loc_180005735
0x1800056d4  call    cs:__imp_GetLastError
0x1800056da  mov     ebx, eax
0x1800056dc  test    eax, eax
0x1800056de  jle     short loc_1800056E9
0x1800056e0  movzx   ebx, ax
0x1800056e3  or      ebx, 80070000h
0x1800056e9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800056f0  jz      loc_180005961
0x1800056f6  mov     rax, [rdi+28h]
0x1800056fa  lea     r9, aIsapiDllLoad; "ISAPI_DLL::Load"
0x180005701  mov     rcx, cs:g_pDebug
0x180005708  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000570f  mov     dword ptr [rsp+188h+var_158], ebx
0x180005713  mov     r8d, 113h
0x180005719  mov     [rsp+188h+var_160], rax
0x18000571e  lea     rax, aIsapiDllLoadSe; "[ISAPI_DLL::Load] SetThreadToken failed"...
0x180005725  mov     [rsp+188h+var_168], rax
0x18000572a  call    cs:__imp_PuDbgPrint
0x180005730  jmp     loc_180005961
0x180005735  lea     rdx, [rdi+40h]; struct STRU *
0x180005739  mov     rcx, rdi; this
0x18000573c  call    ?LoadAcl@ISAPI_DLL@@AEAAJAEAVSTRU@@@Z; ISAPI_DLL::LoadAcl(STRU &)
0x180005741  mov     ebx, eax
0x180005743  test    eax, eax
0x180005745  js      loc_180005957
0x18000574b  test    rbp, rbp
0x18000574e  jz      short loc_18000576C
0x180005750  mov     r8, r14; void *
0x180005753  mov     rdx, rbp; void *
0x180005756  mov     rcx, rdi; this
0x180005759  call    ?AccessCheck@ISAPI_DLL@@QEAAHPEAX0@Z; ISAPI_DLL::AccessCheck(void *,void *)
0x18000575e  test    eax, eax
0x180005760  jnz     short loc_18000576C
0x180005762  mov     ebx, 80070005h
0x180005767  jmp     loc_180005957
0x18000576c  test    r14, r14
0x18000576f  jz      short loc_180005786
0x180005771  mov     rdx, r14; void *
0x180005774  mov     rcx, rdi; this
0x180005777  call    ?SetFastSid@ISAPI_DLL@@QEAAJPEAX@Z; ISAPI_DLL::SetFastSid(void *)
0x18000577c  mov     ebx, eax
0x18000577e  test    eax, eax
0x180005780  js      loc_180005957
0x180005786  mov     rcx, [rdi+60h]; lpLibFileName
0x18000578a  xor     edx, edx; hFile
0x18000578c  lea     r8d, [rdx+8]; dwFlags
0x180005790  call    cs:__imp_LoadLibraryExW
0x180005796  mov     [rdi+0C0h], rax
0x18000579d  test    rax, rax
0x1800057a0  jnz     short loc_180005809
0x1800057a2  call    cs:__imp_GetLastError
0x1800057a8  mov     ebx, eax
0x1800057aa  test    eax, eax
0x1800057ac  jle     short loc_1800057B7
0x1800057ae  movzx   ebx, ax
0x1800057b1  or      ebx, 80070000h
0x1800057b7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800057be  jz      loc_180005957
0x1800057c4  call    cs:__imp_GetLastError
0x1800057ca  mov     rcx, cs:g_pDebug
0x1800057d1  lea     r9, aIsapiDllLoad; "ISAPI_DLL::Load"
0x1800057d8  mov     dword ptr [rsp+188h+var_158], eax
0x1800057dc  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800057e3  mov     rax, [rdi+28h]
0x1800057e7  mov     r8d, 144h
0x1800057ed  mov     [rsp+188h+var_160], rax
0x1800057f2  lea     rax, aIsapiDllLoadLo; "[ISAPI_DLL::Load] LoadLibraryEx %S fail"...
0x1800057f9  mov     [rsp+188h+var_168], rax
0x1800057fe  call    cs:__imp_PuDbgPrint
0x180005804  jmp     loc_180005957
0x180005809  test    esi, esi
0x18000580b  jz      short loc_180005815
0x18000580d  call    cs:__imp_RevertToSelf
0x180005813  xor     esi, esi
0x180005815  mov     rcx, [rdi+0C0h]; hModule
0x18000581c  lea     rdx, ProcName; "GetExtensionVersion"
0x180005823  call    cs:__imp_GetProcAddress
0x180005829  mov     rcx, [rdi+0C0h]; hModule
0x180005830  lea     rdx, aTerminateexten; "TerminateExtension"
0x180005837  mov     [rdi+0A8h], rax
0x18000583e  call    cs:__imp_GetProcAddress
0x180005844  mov     rcx, [rdi+0C0h]; hModule
0x18000584b  lea     rdx, aHttpextensionp_1; "HttpExtensionProc"
0x180005852  mov     [rdi+0B0h], rax
0x180005859  call    cs:__imp_GetProcAddress
0x18000585f  mov     rdx, [rdi+0A8h]
0x180005866  mov     [rdi+0B8h], rax
0x18000586d  test    rdx, rdx
0x180005870  jz      loc_180005947
0x180005876  test    rax, rax
0x180005879  jz      loc_180005947
0x18000587f  lea     rcx, [rsp+188h+var_148]
0x180005884  mov     rax, rdx
0x180005887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588c  test    eax, eax
0x18000588e  jnz     short loc_1800058C2
0x180005890  call    cs:__imp_GetLastError
0x180005896  test    eax, eax
0x180005898  jnz     short loc_1800058A4
0x18000589a  mov     ebx, 80004005h
0x18000589f  jmp     loc_180005957
0x1800058a4  call    cs:__imp_GetLastError
0x1800058aa  mov     ebx, eax
0x1800058ac  test    eax, eax
0x1800058ae  jle     loc_180005957
0x1800058b4  movzx   ebx, ax
0x1800058b7  or      ebx, 80070000h
0x1800058bd  jmp     loc_180005957
0x1800058c2  test    byte ptr cs:g_dwDebugFlags, 3
0x1800058c9  jz      short loc_18000590B
0x1800058cb  mov     rcx, cs:g_pDebug
0x1800058d2  lea     rax, [rsp+188h+var_144]
0x1800058d7  mov     [rsp+188h+var_158], rax
0x1800058dc  lea     r9, aIsapiDllLoad; "ISAPI_DLL::Load"
0x1800058e3  mov     rax, [rdi+28h]
0x1800058e7  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800058ee  mov     [rsp+188h+var_160], rax
0x1800058f3  mov     r8d, 186h
0x1800058f9  lea     rax, aIsapiDllLoadLo_0; "ISAPI_DLL::Load() Loaded extension %S, "...
0x180005900  mov     [rsp+188h+var_168], rax
0x180005905  call    cs:__imp_PuDbgPrint
0x18000590b  mov     dword ptr [rdi+0A0h], 1
0x180005915  mov     rcx, r15; lpCriticalSection
0x180005918  call    cs:__imp_LeaveCriticalSection
0x18000591e  xor     eax, eax
0x180005920  mov     rcx, [rsp+188h+var_38]
0x180005928  xor     rcx, rsp; StackCookie
0x18000592b  call    __security_check_cookie
0x180005930  mov     rbx, [rsp+188h+arg_18]
0x180005938  add     rsp, 160h
0x18000593f  pop     r15
0x180005941  pop     r14
0x180005943  pop     rdi
0x180005944  pop     rsi
0x180005945  pop     rbp
0x180005946  retn
0x180005947  mov     ebx, 8007007Fh
0x18000594c  mov     qword ptr [rdi+0B0h], 0
0x180005957  test    esi, esi
0x180005959  jz      short loc_180005961
0x18000595b  call    cs:__imp_RevertToSelf
0x180005961  cmp     qword ptr [rdi+0B8h], 0
0x180005969  jz      short loc_180005976
0x18000596b  mov     qword ptr [rdi+0B8h], 0
0x180005976  cmp     qword ptr [rdi+0A8h], 0
0x18000597e  jz      short loc_18000598B
0x180005980  mov     qword ptr [rdi+0A8h], 0
0x18000598b  cmp     qword ptr [rdi+0B0h], 0
0x180005993  jz      short loc_1800059A0
0x180005995  mov     qword ptr [rdi+0B0h], 0
0x1800059a0  mov     rcx, [rdi+0C0h]; hLibModule
0x1800059a7  test    rcx, rcx
0x1800059aa  jz      short loc_1800059BD
0x1800059ac  call    cs:__imp_FreeLibrary
0x1800059b2  mov     qword ptr [rdi+0C0h], 0
0x1800059bd  mov     rcx, r15; lpCriticalSection
0x1800059c0  call    cs:__imp_LeaveCriticalSection
0x1800059c6  mov     eax, ebx
0x1800059c8  jmp     loc_180005920
```
