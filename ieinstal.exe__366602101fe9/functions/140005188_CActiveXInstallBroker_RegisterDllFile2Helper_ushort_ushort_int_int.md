# CActiveXInstallBroker::RegisterDllFile2Helper(ushort *,ushort *,int,int)

- ea: `0x140005188`
- end: `0x1400055b1`
- name: `?RegisterDllFile2Helper@CActiveXInstallBroker@@AEAAJPEAG0HH@Z`
- size: `1065`
- prototype: `__int64 __usercall@<rax>(CActiveXInstallBroker *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005108`
- `0x1400055c0`

## callees

- `0x140001af3`
- `0x140004a18`
- `0x140005188`
- `0x140006070`
- `0x140008984`
- `0x140008f78`
- `0x14000bb30`
- `0x14000d314`
- `0x14000d36c`
- `0x14000d4f0`
- `0x1400109c0`
- `0x140011010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000546e`
- `ADVAPI32!RegSetValueExW` at `0x14000546e`
- `ADVAPI32!RegCreateKeyExW` at `0x140005371`
- `ADVAPI32!RegCreateKeyExW` at `0x140005371`
- `ADVAPI32!RegCloseKey` at `0x140005513`
- `ADVAPI32!RegCloseKey` at `0x140005513`
- `ADVAPI32!RegQueryValueExW` at `0x1400053e1`
- `ADVAPI32!RegQueryValueExW` at `0x1400053e1`
- `ADVAPI32!RegOverridePredefKey` at `0x140005550`
- `ADVAPI32!RegOverridePredefKey` at `0x140005565`
- `ADVAPI32!RegOverridePredefKey` at `0x140005550`
- `ADVAPI32!RegOverridePredefKey` at `0x140005565`
- `KERNEL32!GetProcAddress` at `0x1400054c4`
- `KERNEL32!GetProcAddress` at `0x1400054c4`
- `KERNEL32!FreeLibrary` at `0x140005527`
- `KERNEL32!FreeLibrary` at `0x140005527`
- `KERNEL32!LoadLibraryExW` at `0x140005491`
- `KERNEL32!LoadLibraryExW` at `0x140005491`
- `KERNEL32!LeaveCriticalSection` at `0x14000557f`
- `KERNEL32!LeaveCriticalSection` at `0x14000557f`
- `KERNEL32!EnterCriticalSection` at `0x1400051dc`
- `KERNEL32!EnterCriticalSection` at `0x1400051dc`
- `KERNEL32!GetLastError` at `0x1400054a5`
- `KERNEL32!GetLastError` at `0x1400054a5`

## string_xrefs

- `0x14000540f`: `rundll32.exe IEAdvpack.dll,RegisterOCX %s`
- `0x1400054ba`: `DllRegisterServer`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::RegisterDllFile2Helper(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        int a5)
{
  HMODULE v5; // r15
  int v10; // r12d
  signed int IsAuthorized; // ebx
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rcx
  WCHAR *v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // edi
  WCHAR *v19; // rcx
  WCHAR v20; // ax
  WCHAR *v21; // rcx
  int v22; // r8d
  int LastError; // eax
  bool v24; // cc
  __int64 v25; // rax
  HMODULE Library; // rax
  __int64 (*ProcAddress)(void); // rbx
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR LibFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v34[526]; // [rsp+282h] [rbp+182h] BYREF
  unsigned __int16 Data[520]; // [rsp+490h] [rbp+390h] BYREF

  v5 = 0;
  v10 = -2147467259;
  phkResult = 0;
  if ( !*(_DWORD *)this )
  {
    IsAuthorized = -2147024882;
    goto LABEL_60;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 12) >= 6 )
  {
    if ( a2 && a3 )
    {
      v12 = *((_QWORD *)this + 8) - (_QWORD)a2;
      do
      {
        v13 = *(unsigned __int16 *)((char *)a2 + v12);
        v14 = *a2 - v13;
        if ( v14 )
          break;
        ++a2;
      }
      while ( v13 );
      if ( v14 )
      {
LABEL_10:
        IsAuthorized = -2147024891;
        goto LABEL_54;
      }
      v15 = 2147483646;
      v16 = LibFileName;
      v17 = 260;
      do
      {
        if ( !v15 )
          break;
        if ( !*a3 )
          break;
        *v16++ = *a3++;
        --v15;
        --v17;
      }
      while ( v17 );
      v18 = 0;
      v19 = v16 - 1;
      if ( v17 )
        v19 = v16;
      *v19 = 0;
      if ( v17 )
      {
        v20 = LibFileName[0];
        if ( LibFileName[0] )
        {
          v21 = LibFileName;
          do
          {
            if ( v20 == 47 )
              *v21 = 92;
            v20 = *++v21;
          }
          while ( *v21 );
        }
        if ( (int)AxiPreScanPathW(LibFileName) >= 0 && (int)VerifyFileHasExtensionW(LibFileName) >= 0 )
        {
          IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, LibFileName, v22);
          if ( IsAuthorized < 0 )
            goto LABEL_54;
          if ( *((_DWORD *)this + 35) || (unsigned int)ContainingPathIsTamperProof(LibFileName) )
          {
            if ( a5 )
            {
              ValueName = 0;
              memset_0(v34, 0, 0x206u);
              dwDisposition = 0;
              hKey = 0;
              IsAuthorized = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
              if ( IsAuthorized )
                goto LABEL_54;
              LastError = RegCreateKeyExW(
                            hKey,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
                            0,
                            0,
                            0,
                            0x20006u,
                            0,
                            &phkResult,
                            &dwDisposition);
              IsAuthorized = LastError;
              v24 = LastError <= 0;
              if ( !LastError )
              {
                while ( 1 )
                {
                  IsAuthorized = StringCchPrintfW(&ValueName, 0x104u, L"ICDRegOCX%u", v18);
                  if ( IsAuthorized < 0 )
                    goto LABEL_54;
                  ++v18;
                  if ( RegQueryValueExW(phkResult, &ValueName, 0, 0, 0, &dwDisposition) )
                  {
                    if ( !v18 )
                    {
LABEL_38:
                      IsAuthorized = -2147023883;
                      goto LABEL_54;
                    }
                    IsAuthorized = StringCchPrintfW(
                                     Data,
                                     0x207u,
                                     L"rundll32.exe IEAdvpack.dll,RegisterOCX %s",
                                     LibFileName);
                    if ( IsAuthorized < 0 )
                      goto LABEL_54;
                    v25 = -1;
                    do
                      ++v25;
                    while ( Data[v25] );
                    LastError = RegSetValueExW(phkResult, &ValueName, 0, 1u, (const BYTE *)Data, 2 * v25 + 2);
                    if ( !LastError )
                      goto LABEL_52;
                    if ( LastError > 0 )
                      goto LABEL_32;
                    goto LABEL_50;
                  }
                  if ( !v18 )
                    goto LABEL_38;
                }
              }
            }
            else
            {
              Library = LoadLibraryExW(LibFileName, 0, 8u);
              v5 = Library;
              if ( Library )
              {
                ProcAddress = GetProcAddress(Library, "DllRegisterServer");
                if ( ProcAddress )
                {
                  if ( a4 && (LastError = EnableRedirectToHKCU(), (v10 = LastError) != 0) )
                  {
LABEL_50:
                    IsAuthorized = LastError;
                  }
                  else
                  {
                    IsAuthorized = ProcAddress();
                    if ( IsAuthorized >= 0 )
LABEL_52:
                      *((_DWORD *)this + 12) = 8;
                  }
                  goto LABEL_54;
                }
              }
              LastError = GetLastError();
              IsAuthorized = LastError;
              v24 = LastError <= 0;
            }
            if ( !v24 )
LABEL_32:
              IsAuthorized = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_54;
          }
          goto LABEL_10;
        }
      }
    }
    IsAuthorized = -2147024809;
    goto LABEL_54;
  }
  IsAuthorized = -2147019873;
LABEL_54:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    FreeLibrary(v5);
LABEL_60:
  if ( a4 && !v10 )
  {
    RegOverridePredefKey(HKEY_CLASSES_ROOT, 0);
    RegOverridePredefKey(HKEY_LOCAL_MACHINE, 0);
    DestroyDetoursRedirectToHKCU();
  }
  if ( *(_DWORD *)this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)IsAuthorized;
}

```

## disassembly

```asm
0x140005188  push    rbp
0x14000518a  push    rbx
0x14000518b  push    rsi
0x14000518c  push    rdi
0x14000518d  push    r12
0x14000518f  push    r13
0x140005191  push    r14
0x140005193  push    r15
0x140005195  lea     rbp, [rsp-7B8h]
0x14000519d  sub     rsp, 8B8h
0x1400051a4  mov     rax, cs:__security_cookie
0x1400051ab  xor     rax, rsp
0x1400051ae  mov     [rbp+7F0h+var_50], rax
0x1400051b5  xor     r15d, r15d
0x1400051b8  mov     r13d, r9d
0x1400051bb  mov     rdi, r8
0x1400051be  mov     rbx, rdx
0x1400051c1  mov     rsi, rcx
0x1400051c4  mov     r12d, 80004005h
0x1400051ca  mov     [rsp+8F0h+var_898], r15
0x1400051cf  cmp     [rcx], r15d
0x1400051d2  jz      loc_140005538
0x1400051d8  add     rcx, 8; lpCriticalSection
0x1400051dc  call    cs:__imp_EnterCriticalSection
0x1400051e3  nop     dword ptr [rax+rax+00h]
0x1400051e8  cmp     dword ptr [rsi+30h], 6
0x1400051ec  jge     short loc_1400051F8
0x1400051ee  mov     ebx, 8007139Fh
0x1400051f3  jmp     loc_140005509
0x1400051f8  test    rbx, rbx
0x1400051fb  jz      loc_140005504
0x140005201  test    rdi, rdi
0x140005204  jz      loc_140005504
0x14000520a  mov     rdx, [rsi+40h]
0x14000520e  sub     rdx, rbx
0x140005211  movzx   eax, word ptr [rbx]
0x140005214  movzx   ecx, word ptr [rbx+rdx]
0x140005218  sub     eax, ecx
0x14000521a  jnz     short loc_140005224
0x14000521c  add     rbx, 2
0x140005220  test    ecx, ecx
0x140005222  jnz     short loc_140005211
0x140005224  test    eax, eax
0x140005226  jz      short loc_140005232
0x140005228  mov     ebx, 80070005h
0x14000522d  jmp     loc_140005509
0x140005232  mov     ecx, 7FFFFFFEh
0x140005237  lea     rax, [rsp+8F0h+LibFileName]
0x14000523c  mov     edx, 104h
0x140005241  test    rcx, rcx
0x140005244  jz      short loc_140005265
0x140005246  movzx   r8d, word ptr [rdi]
0x14000524a  test    r8w, r8w
0x14000524e  jz      short loc_140005265
0x140005250  mov     [rax], r8w
0x140005254  add     rdi, 2
0x140005258  add     rax, 2
0x14000525c  dec     rcx
0x14000525f  sub     rdx, 1
0x140005263  jnz     short loc_140005241
0x140005265  xor     edi, edi
0x140005267  lea     rcx, [rax-2]
0x14000526b  test    rdx, rdx
0x14000526e  cmovnz  rcx, rax
0x140005272  mov     [rcx], di
0x140005275  jz      loc_140005504
0x14000527b  movzx   eax, [rsp+8F0h+LibFileName]
0x140005280  test    ax, ax
0x140005283  jz      short loc_1400052A1
0x140005285  lea     rcx, [rsp+8F0h+LibFileName]
0x14000528a  cmp     ax, 2Fh ; '/'
0x14000528e  jnz     short loc_140005295
0x140005290  mov     word ptr [rcx], 5Ch ; '\'
0x140005295  add     rcx, 2
0x140005299  movzx   eax, word ptr [rcx]
0x14000529c  test    ax, ax
0x14000529f  jnz     short loc_14000528A
0x1400052a1  lea     rcx, [rsp+8F0h+LibFileName]; unsigned __int16 *
0x1400052a6  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x1400052ab  test    eax, eax
0x1400052ad  js      loc_140005504
0x1400052b3  lea     rcx, [rsp+8F0h+LibFileName]; lpFileName
0x1400052b8  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x1400052bd  test    eax, eax
0x1400052bf  js      loc_140005504
0x1400052c5  lea     rdx, [rsp+8F0h+LibFileName]; unsigned __int16 *
0x1400052ca  mov     rcx, rsi; this
0x1400052cd  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x1400052d2  mov     ebx, eax
0x1400052d4  test    eax, eax
0x1400052d6  js      loc_140005509
0x1400052dc  cmp     [rsi+8Ch], edi
0x1400052e2  jnz     short loc_1400052F6
0x1400052e4  lea     rcx, [rsp+8F0h+LibFileName]; unsigned __int16 *
0x1400052e9  call    ?ContainingPathIsTamperProof@@YAHPEBG@Z; ContainingPathIsTamperProof(ushort const *)
0x1400052ee  test    eax, eax
0x1400052f0  jz      loc_140005228
0x1400052f6  cmp     [rbp+7F0h+arg_20], edi
0x1400052fc  jz      loc_140005486
0x140005302  xor     edx, edx; Val
0x140005304  mov     [rbp+7F0h+ValueName], di
0x14000530b  mov     r8d, 206h; Size
0x140005311  lea     rcx, [rbp+7F0h+var_66E]; void *
0x140005318  call    memset_0
0x14000531d  lea     rcx, [rsp+8F0h+hKey]; HKEY *
0x140005322  mov     [rsp+8F0h+dwDisposition], edi
0x140005326  mov     [rsp+8F0h+hKey], rdi
0x14000532b  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YAJPEAPEAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x140005330  mov     ebx, eax
0x140005332  test    eax, eax
0x140005334  jnz     loc_140005509
0x14000533a  mov     rcx, [rsp+8F0h+hKey]; hKey
0x14000533f  lea     rax, [rsp+8F0h+dwDisposition]
0x140005344  mov     [rsp+8F0h+lpdwDisposition], rax; lpdwDisposition
0x140005349  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140005350  lea     rax, [rsp+8F0h+var_898]
0x140005355  xor     r9d, r9d; lpClass
0x140005358  mov     [rsp+8F0h+phkResult], rax; phkResult
0x14000535d  xor     r8d, r8d; Reserved
0x140005360  mov     [rsp+8F0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140005365  mov     [rsp+8F0h+samDesired], 20006h; samDesired
0x14000536d  mov     [rsp+8F0h+dwOptions], edi; dwOptions
0x140005371  call    cs:__imp_RegCreateKeyExW
0x140005378  nop     dword ptr [rax+rax+00h]
0x14000537d  mov     ebx, eax
0x14000537f  test    eax, eax
0x140005381  jz      short loc_140005397
0x140005383  jle     loc_140005509
0x140005389  movzx   ebx, ax
0x14000538c  or      ebx, 80070000h
0x140005392  jmp     loc_140005509
0x140005397  mov     r9d, edi
0x14000539a  lea     r8, aIcdregocxU; "ICDRegOCX%u"
0x1400053a1  mov     edx, 104h; unsigned __int64
0x1400053a6  lea     rcx, [rbp+7F0h+ValueName]; unsigned __int16 *
0x1400053ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400053b2  xor     ecx, ecx
0x1400053b4  mov     ebx, eax
0x1400053b6  test    eax, eax
0x1400053b8  js      loc_140005509
0x1400053be  lea     rax, [rsp+8F0h+dwDisposition]
0x1400053c3  xor     r9d, r9d; lpType
0x1400053c6  mov     qword ptr [rsp+8F0h+samDesired], rax; lpcbData
0x1400053cb  lea     rdx, [rbp+7F0h+ValueName]; lpValueName
0x1400053d2  mov     qword ptr [rsp+8F0h+dwOptions], rcx; lpData
0x1400053d7  xor     r8d, r8d; lpReserved
0x1400053da  mov     rcx, [rsp+8F0h+var_898]; hKey
0x1400053df  inc     edi
0x1400053e1  call    cs:__imp_RegQueryValueExW
0x1400053e8  nop     dword ptr [rax+rax+00h]
0x1400053ed  test    eax, eax
0x1400053ef  jnz     short loc_1400053F7
0x1400053f1  test    edi, edi
0x1400053f3  jnz     short loc_140005397
0x1400053f5  jmp     short loc_1400053FB
0x1400053f7  test    edi, edi
0x1400053f9  jnz     short loc_140005405
0x1400053fb  mov     ebx, 800703F5h
0x140005400  jmp     loc_140005509
0x140005405  lea     r9, [rsp+8F0h+LibFileName]
0x14000540a  mov     edx, 207h; unsigned __int64
0x14000540f  lea     r8, aRundll32ExeIea; "rundll32.exe IEAdvpack.dll,RegisterOCX "...
0x140005416  lea     rcx, [rbp+7F0h+Data]; unsigned __int16 *
0x14000541d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005422  xor     edi, edi
0x140005424  mov     ebx, eax
0x140005426  test    eax, eax
0x140005428  js      loc_140005509
0x14000542e  lea     rcx, [rbp+7F0h+Data]
0x140005435  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005439  inc     rax
0x14000543c  cmp     [rcx+rax*2], di
0x140005440  jnz     short loc_140005439
0x140005442  mov     rcx, [rsp+8F0h+var_898]; hKey
0x140005447  lea     eax, ds:2[rax*2]
0x14000544e  mov     [rsp+8F0h+samDesired], eax; cbData
0x140005452  lea     rdx, [rbp+7F0h+ValueName]; lpValueName
0x140005459  lea     rax, [rbp+7F0h+Data]
0x140005460  mov     r9d, 1; dwType
0x140005466  xor     r8d, r8d; Reserved
0x140005469  mov     qword ptr [rsp+8F0h+dwOptions], rax; lpData
0x14000546e  call    cs:__imp_RegSetValueExW
0x140005475  nop     dword ptr [rax+rax+00h]
0x14000547a  test    eax, eax
0x14000547c  jz      short loc_1400054FB
0x14000547e  jg      loc_140005389
0x140005484  jmp     short loc_1400054E9
0x140005486  xor     edx, edx; hFile
0x140005488  lea     rcx, [rsp+8F0h+LibFileName]; lpLibFileName
0x14000548d  lea     r8d, [rdx+8]; dwFlags
0x140005491  call    cs:__imp_LoadLibraryExW
0x140005498  nop     dword ptr [rax+rax+00h]
0x14000549d  mov     r15, rax
0x1400054a0  test    rax, rax
0x1400054a3  jnz     short loc_1400054BA
0x1400054a5  call    cs:__imp_GetLastError
0x1400054ac  nop     dword ptr [rax+rax+00h]
0x1400054b1  mov     ebx, eax
0x1400054b3  test    eax, eax
0x1400054b5  jmp     loc_140005383
0x1400054ba  lea     rdx, aDllregisterser; "DllRegisterServer"
0x1400054c1  mov     rcx, rax; hModule
0x1400054c4  call    cs:__imp_GetProcAddress
0x1400054cb  nop     dword ptr [rax+rax+00h]
0x1400054d0  mov     rbx, rax
0x1400054d3  test    rax, rax
0x1400054d6  jz      short loc_1400054A5
0x1400054d8  test    r13d, r13d
0x1400054db  jz      short loc_1400054ED
0x1400054dd  call    EnableRedirectToHKCU
0x1400054e2  mov     r12d, eax
0x1400054e5  test    eax, eax
0x1400054e7  jz      short loc_1400054ED
0x1400054e9  mov     ebx, eax
0x1400054eb  jmp     short loc_140005509
0x1400054ed  mov     rax, rbx
0x1400054f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054f5  mov     ebx, eax
0x1400054f7  test    eax, eax
0x1400054f9  js      short loc_140005509
0x1400054fb  mov     dword ptr [rsi+30h], 8
0x140005502  jmp     short loc_140005509
0x140005504  mov     ebx, 80070057h
0x140005509  mov     rcx, [rsp+8F0h+var_898]; hKey
0x14000550e  test    rcx, rcx
0x140005511  jz      short loc_14000551F
0x140005513  call    cs:__imp_RegCloseKey
0x14000551a  nop     dword ptr [rax+rax+00h]
0x14000551f  test    r15, r15
0x140005522  jz      short loc_140005533
0x140005524  mov     rcx, r15; hLibModule
0x140005527  call    cs:__imp_FreeLibrary
0x14000552e  nop     dword ptr [rax+rax+00h]
0x140005533  xor     r15d, r15d
0x140005536  jmp     short loc_14000553D
0x140005538  mov     ebx, 8007000Eh
0x14000553d  test    r13d, r13d
0x140005540  jz      short loc_140005576
0x140005542  test    r12d, r12d
0x140005545  jnz     short loc_140005576
0x140005547  xor     edx, edx; hNewHKey
0x140005549  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140005550  call    cs:__imp_RegOverridePredefKey
0x140005557  nop     dword ptr [rax+rax+00h]
0x14000555c  xor     edx, edx; hNewHKey
0x14000555e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005565  call    cs:__imp_RegOverridePredefKey
0x14000556c  nop     dword ptr [rax+rax+00h]
0x140005571  call    ?DestroyDetoursRedirectToHKCU@@YAJXZ; DestroyDetoursRedirectToHKCU(void)
0x140005576  cmp     [rsi], r15d
0x140005579  jz      short loc_14000558B
0x14000557b  lea     rcx, [rsi+8]; lpCriticalSection
0x14000557f  call    cs:__imp_LeaveCriticalSection
0x140005586  nop     dword ptr [rax+rax+00h]
0x14000558b  mov     eax, ebx
0x14000558d  mov     rcx, [rbp+7F0h+var_50]
0x140005594  xor     rcx, rsp; StackCookie
0x140005597  call    __security_check_cookie
0x14000559c  add     rsp, 8B8h
0x1400055a3  pop     r15
0x1400055a5  pop     r14
0x1400055a7  pop     r13
0x1400055a9  pop     r12
0x1400055ab  pop     rdi
0x1400055ac  pop     rsi
0x1400055ad  pop     rbx
0x1400055ae  pop     rbp
0x1400055af  retn
```
