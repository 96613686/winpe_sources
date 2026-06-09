# GetShimDllPathName

- ea: `0x180004660`
- end: `0x180004d41`
- name: `GetShimDllPathName`
- size: `1761`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002a90`
- `0x180005300`

## callees

- `0x180003070`
- `0x180003740`
- `0x180003840`
- `0x180004660`
- `0x180004d50`
- `0x180008624`
- `0x18000c1a8`
- `0x18000d264`
- `0x18000d614`
- `0x18000d8f0`
- `0x180041ac0`
- `0x180041ec0`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18000486b`
- `KERNEL32!GetFullPathNameW` at `0x1800048bf`
- `KERNEL32!GetFullPathNameW` at `0x18000496e`
- `KERNEL32!GetFullPathNameW` at `0x180004c7c`
- `KERNEL32!GetFullPathNameW` at `0x18000486b`
- `KERNEL32!GetFullPathNameW` at `0x1800048bf`
- `KERNEL32!GetFullPathNameW` at `0x18000496e`
- `KERNEL32!GetFullPathNameW` at `0x180004c7c`
- `KERNEL32!GetLastError` at `0x180004737`
- `KERNEL32!GetLastError` at `0x1800047ef`
- `KERNEL32!GetLastError` at `0x18000487c`
- `KERNEL32!GetLastError` at `0x180004a73`
- `KERNEL32!GetLastError` at `0x180004b6a`
- `KERNEL32!GetLastError` at `0x180004b86`
- `KERNEL32!GetLastError` at `0x180004737`
- `KERNEL32!GetLastError` at `0x1800047ef`
- `KERNEL32!GetLastError` at `0x18000487c`
- `KERNEL32!GetLastError` at `0x180004a73`
- `KERNEL32!GetLastError` at `0x180004b6a`
- `KERNEL32!GetLastError` at `0x180004b86`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004723`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004cf6`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004723`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004cf6`
- `KERNEL32!GetModuleFileNameW` at `0x180004aa4`
- `KERNEL32!GetModuleFileNameW` at `0x180004b12`
- `KERNEL32!GetModuleFileNameW` at `0x180004c54`
- `KERNEL32!GetModuleFileNameW` at `0x180004aa4`
- `KERNEL32!GetModuleFileNameW` at `0x180004b12`
- `KERNEL32!GetModuleFileNameW` at `0x180004c54`
- `KERNEL32!GetFileAttributesW` at `0x180004ad2`
- `KERNEL32!GetFileAttributesW` at `0x180004b40`
- `KERNEL32!GetFileAttributesW` at `0x180004ad2`
- `KERNEL32!GetFileAttributesW` at `0x180004b40`
- `KERNEL32!SetLastError` at `0x180004a85`
- `KERNEL32!SetLastError` at `0x180004b7b`
- `KERNEL32!SetLastError` at `0x180004b97`
- `KERNEL32!SetLastError` at `0x180004a85`
- `KERNEL32!SetLastError` at `0x180004b7b`
- `KERNEL32!SetLastError` at `0x180004b97`
- `ADVAPI32!RegOpenKeyExW` at `0x180004792`
- `ADVAPI32!RegOpenKeyExW` at `0x180004792`
- `ADVAPI32!RegQueryValueExW` at `0x1800047c3`
- `ADVAPI32!RegQueryValueExW` at `0x180004834`
- `ADVAPI32!RegQueryValueExW` at `0x1800047c3`
- `ADVAPI32!RegQueryValueExW` at `0x180004834`
- `ADVAPI32!RegCloseKey` at `0x180004844`
- `ADVAPI32!RegCloseKey` at `0x180004844`

## string_xrefs

- `0x180004703`: `InstallRoot`
- `0x1800047bc`: `InstallRoot`
- `0x180004822`: `InstallRoot`
- `0x1800046de`: `COMPlus_`

## pseudocode

```c
__int64 __fastcall GetShimDllPathName(wchar_t *Source, wchar_t *a2, wchar_t *a3)
{
  int v6; // eax
  signed int EnvironmentVariableW; // eax
  unsigned __int64 v8; // r14
  __int64 v9; // rdi
  DWORD LastError; // r13d
  unsigned __int64 v11; // rax
  WCHAR *v12; // rbx
  unsigned __int64 v13; // rbx
  DWORD v14; // r14d
  DWORD FullPathNameW; // eax
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // rax
  wchar_t *v18; // r14
  __int64 v19; // rbx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned int DirectoryLocation; // ebx
  __int64 v23; // rax
  bool v24; // zf
  unsigned __int64 v25; // r15
  __int64 v27; // r15
  DWORD Type[2]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  int v30; // [rsp+48h] [rbp-C0h]
  wchar_t Destination[64]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 Src[264]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR Buffer[264]; // [rsp+2E8h] [rbp+1E0h] BYREF
  WCHAR Filename[272]; // [rsp+4F8h] [rbp+3F0h] BYREF

  if ( Source )
  {
    v6 = g_UseLocalRuntime;
    if ( g_UseLocalRuntime != -1 )
      goto LABEL_3;
    if ( GetModuleFileNameW(g_hShimMod, Filename, 0x104u) - 1 <= 0x102 )
    {
      wcscat_s(Filename, 0x10Bu, L".local");
      if ( GetFileAttributesW(Filename) != -1 )
      {
        g_UseLocalRuntime = 1;
        goto LABEL_63;
      }
    }
    v6 = g_UseLocalRuntime;
    if ( g_UseLocalRuntime == -1 )
    {
      g_UseLocalRuntime = 0;
    }
    else
    {
LABEL_3:
      if ( v6 )
        goto LABEL_63;
    }
    if ( a2 )
    {
      hKey = 0;
      Type[0] = 0;
      Type[1] = 0;
      wcscpy_s(Destination, 0x40u, L"COMPlus_");
      wcscat_s(Destination, 0x40u, L"InstallRoot");
      EnvironmentVariableW = GetEnvironmentVariableW(Destination, 0, 0);
      v8 = EnvironmentVariableW;
      v9 = -1;
      if ( EnvironmentVariableW )
      {
        LastError = GetLastError();
        v11 = 2 * v8;
        if ( !is_mul_ok(v8, 2u) )
          v11 = -1;
        v12 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v11);
        if ( LastError && !GetLastError() )
          SetLastError(LastError);
        if ( v12 )
        {
          GetEnvironmentVariableW(Destination, v12, v8);
          if ( *v12 )
          {
            hKey = (HKEY)v12;
LABEL_22:
            v30 = 1;
            FullPathNameW = GetFullPathNameW(v12, 0, 0, 0);
            v16 = FullPathNameW;
            if ( FullPathNameW )
            {
              Type[0] = GetLastError();
              v17 = 2 * v16;
              if ( !is_mul_ok(v16, 2u) )
                v17 = -1;
              v18 = (wchar_t *)ClrAllocInProcessHeapBootstrap(0, v17);
              if ( Type[0] && !GetLastError() )
                SetLastError(Type[0]);
              if ( v18 )
              {
                if ( (unsigned int)v16 >= GetFullPathNameW(v12, v16, v18, 0) )
                {
                  operator delete(v12);
                  hKey = 0;
                  v19 = -1;
                  do
                    ++v19;
                  while ( v18[v19] );
                  v20 = -1;
                  do
                    ++v20;
                  while ( a2[v20] );
                  if ( ~v19 < v20 || ~(v20 + v19) < 2 || v20 + v19 + 2 > 0x104 )
                    goto LABEL_68;
                  wcscpy_s(a3, 0x104u, v18);
                  if ( a3[v19 - 1] != 92 )
                    wcscat_s(a3, 0x104u, L"\\");
                  wcscat_s(a3, 0x104u, a2);
                  if ( GetFullPathNameW(a3, 0x104u, Buffer, (LPWSTR *)&hKey) - 1 > 0x102 )
                    goto LABEL_68;
                  if ( wcsicmp(Buffer, a3) )
                    goto LABEL_68;
                  v21 = -1;
                  do
                    ++v21;
                  while ( a3[v21] );
                  if ( v21 > 0xFFFFFFFFFFFFFFFDuLL || v21 + 2 >= 0x104 )
                  {
LABEL_68:
                    DirectoryLocation = -2147024735;
                    operator delete(v18);
                    return DirectoryLocation;
                  }
                  DirectoryLocation = 0;
                  wcscat_s(a3, 0x104u, L"\\");
                  v23 = -1;
                  do
                    v24 = a3[++v23] == 0;
                  while ( !v24 );
                  v25 = v23 + 1;
                  operator delete(v18);
                  goto LABEL_46;
                }
                operator delete(v18);
              }
              operator delete(v12);
            }
            else
            {
              Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&hKey);
            }
            return (unsigned int)-2147024735;
          }
          operator delete(v12);
        }
      }
      v12 = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &hKey)
        && !RegQueryValueExW(hKey, L"InstallRoot", 0, Type, 0, &Type[1])
        && Type[0] == 1
        && Type[1] > 1 )
      {
        v13 = 2LL * (Type[1] + 1);
        if ( !is_mul_ok(Type[1] + 1, 2u) )
          v13 = -1;
        v14 = GetLastError();
        v12 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v13);
        if ( v14 && !GetLastError() )
          SetLastError(v14);
        if ( v12 )
          RegQueryValueExW(hKey, L"InstallRoot", 0, 0, (LPBYTE)v12, &Type[1]);
      }
      if ( hKey )
        RegCloseKey(hKey);
      hKey = (HKEY)v12;
      if ( !v12 )
        return (unsigned int)-2147024735;
      goto LABEL_22;
    }
LABEL_63:
    DirectoryLocation = GetDirectoryLocation(Source, Src, (unsigned int)a3);
    if ( (DirectoryLocation & 0x80000000) != 0 )
      return DirectoryLocation;
    v9 = -1;
    v27 = -1;
    do
      ++v27;
    while ( Src[v27] );
    v25 = v27 + 1;
    if ( v25 < 0x104 )
    {
      memmove(a3, Src, 2 * v25);
      do
LABEL_46:
        v24 = Source[++v9] == 0;
      while ( !v24 );
      if ( v9 + v25 < 0x104 )
      {
        wcscat_s(a3, 0x104u, Source);
        return DirectoryLocation;
      }
    }
    return (unsigned int)-2147024735;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180004660  mov     r11, rsp
0x180004663  push    rbp
0x180004664  push    rsi
0x180004665  push    r12
0x180004667  push    r15
0x180004669  lea     rbp, [r11-878h]
0x180004670  sub     rsp, 958h
0x180004677  mov     rax, cs:__security_cookie
0x18000467e  xor     rax, rsp
0x180004681  mov     [rbp+870h+var_40], rax
0x180004688  mov     rsi, r8
0x18000468b  mov     r15, rdx
0x18000468e  mov     r12, rcx
0x180004691  test    rcx, rcx
0x180004694  jz      loc_180004C26
0x18000469a  mov     eax, cs:?g_UseLocalRuntime@@3HA; int g_UseLocalRuntime
0x1800046a0  mov     [r11+20h], rbx
0x1800046a4  mov     [r11-28h], rdi
0x1800046a8  mov     [r11-30h], r13
0x1800046ac  xor     r13d, r13d
0x1800046af  mov     [r11-38h], r14
0x1800046b3  cmp     eax, 0FFFFFFFFh
0x1800046b6  jz      loc_180004A90
0x1800046bc  test    eax, eax
0x1800046be  jnz     loc_180004BAD
0x1800046c4  test    r15, r15
0x1800046c7  jz      loc_180004BAD
0x1800046cd  cmp     eax, 0FFFFFFFFh
0x1800046d0  jz      loc_180004AFE
0x1800046d6  test    eax, eax
0x1800046d8  jnz     loc_180004C3B
0x1800046de  lea     r8, aComplus; "COMPlus_"
0x1800046e5  mov     [rsp+970h+hKey], r13
0x1800046ea  mov     edx, 40h ; '@'; SizeInWords
0x1800046ef  mov     [rsp+970h+Type], r13d
0x1800046f4  lea     rcx, [rsp+970h+Destination]; Destination
0x1800046f9  mov     [rsp+970h+Type+4], r13d
0x1800046fe  call    wcscpy_s
0x180004703  lea     r8, aInstallroot; "InstallRoot"
0x18000470a  mov     edx, 40h ; '@'; SizeInWords
0x18000470f  lea     rcx, [rsp+970h+Destination]; Destination
0x180004714  call    wcscat_s
0x180004719  xor     r8d, r8d; nSize
0x18000471c  lea     rcx, [rsp+970h+Destination]; lpName
0x180004721  xor     edx, edx; lpBuffer
0x180004723  call    cs:__imp_GetEnvironmentVariableW
0x180004729  movsxd  r14, eax
0x18000472c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180004733  test    eax, eax
0x180004735  jz      short loc_18000476E
0x180004737  call    cs:__imp_GetLastError
0x18000473d  mov     r13d, eax
0x180004740  mov     eax, 2
0x180004745  mul     r14
0x180004748  cmovb   rax, rdi
0x18000474c  xor     ecx, ecx; unsigned int
0x18000474e  mov     rdx, rax; unsigned __int64
0x180004751  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180004756  mov     rbx, rax
0x180004759  test    r13d, r13d
0x18000475c  jnz     loc_180004B6A
0x180004762  test    rbx, rbx
0x180004765  jnz     loc_180004CEB
0x18000476b  xor     r13d, r13d
0x18000476e  lea     rax, [rsp+970h+hKey]
0x180004773  mov     r9d, 20019h; samDesired
0x180004779  xor     r8d, r8d; ulOptions
0x18000477c  mov     [rsp+970h+phkResult], rax; phkResult
0x180004781  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x180004788  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000478f  mov     rbx, r13
0x180004792  call    cs:__imp_RegOpenKeyExW
0x180004798  test    eax, eax
0x18000479a  jnz     loc_18000483A
0x1800047a0  mov     rcx, [rsp+970h+hKey]; hKey
0x1800047a5  lea     rax, [rsp+970h+Type+4]
0x1800047aa  mov     [rsp+970h+lpcbData], rax; lpcbData
0x1800047af  lea     r9, [rsp+970h+Type]; lpType
0x1800047b4  xor     r8d, r8d; lpReserved
0x1800047b7  mov     [rsp+970h+phkResult], r13; lpData
0x1800047bc  lea     rdx, aInstallroot; "InstallRoot"
0x1800047c3  call    cs:__imp_RegQueryValueExW
0x1800047c9  test    eax, eax
0x1800047cb  jnz     short loc_18000483A
0x1800047cd  cmp     [rsp+970h+Type], 1
0x1800047d2  jnz     short loc_18000483A
0x1800047d4  mov     eax, [rsp+970h+Type+4]
0x1800047d8  cmp     eax, 1
0x1800047db  jbe     short loc_18000483A
0x1800047dd  lea     ecx, [rax+1]
0x1800047e0  mov     eax, 2
0x1800047e5  mul     rcx
0x1800047e8  mov     rbx, rax
0x1800047eb  cmovb   rbx, rdi
0x1800047ef  call    cs:__imp_GetLastError
0x1800047f5  mov     rdx, rbx; unsigned __int64
0x1800047f8  xor     ecx, ecx; unsigned int
0x1800047fa  mov     r14d, eax
0x1800047fd  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180004802  mov     rbx, rax
0x180004805  test    r14d, r14d
0x180004808  jnz     loc_180004B86
0x18000480e  test    rbx, rbx
0x180004811  jz      short loc_18000483A
0x180004813  mov     rcx, [rsp+970h+hKey]; hKey
0x180004818  lea     rax, [rsp+970h+Type+4]
0x18000481d  mov     [rsp+970h+lpcbData], rax; lpcbData
0x180004822  lea     rdx, aInstallroot; "InstallRoot"
0x180004829  xor     r9d, r9d; lpType
0x18000482c  mov     [rsp+970h+phkResult], rbx; lpData
0x180004831  xor     r8d, r8d; lpReserved
0x180004834  call    cs:__imp_RegQueryValueExW
0x18000483a  mov     rcx, [rsp+970h+hKey]; hKey
0x18000483f  test    rcx, rcx
0x180004842  jz      short loc_18000484A
0x180004844  call    cs:__imp_RegCloseKey
0x18000484a  mov     [rsp+970h+hKey], rbx
0x18000484f  test    rbx, rbx
0x180004852  jz      loc_180004A1D
0x180004858  xor     r9d, r9d; lpFilePart
0x18000485b  mov     [rsp+970h+var_930], 1
0x180004863  xor     r8d, r8d; lpBuffer
0x180004866  xor     edx, edx; nBufferLength
0x180004868  mov     rcx, rbx; lpFileName
0x18000486b  call    cs:__imp_GetFullPathNameW
0x180004871  mov     r13d, eax
0x180004874  test    eax, eax
0x180004876  jz      loc_180004D19
0x18000487c  call    cs:__imp_GetLastError
0x180004882  mov     [rsp+970h+Type], eax
0x180004886  mov     eax, 2
0x18000488b  mul     r13
0x18000488e  cmovb   rax, rdi
0x180004892  xor     ecx, ecx; unsigned int
0x180004894  mov     rdx, rax; unsigned __int64
0x180004897  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x18000489c  cmp     [rsp+970h+Type], 0
0x1800048a1  mov     r14, rax
0x1800048a4  jnz     loc_180004A73
0x1800048aa  test    r14, r14
0x1800048ad  jz      loc_180004A69
0x1800048b3  xor     r9d, r9d; lpFilePart
0x1800048b6  mov     r8, r14; lpBuffer
0x1800048b9  mov     edx, r13d; nBufferLength
0x1800048bc  mov     rcx, rbx; lpFileName
0x1800048bf  call    cs:__imp_GetFullPathNameW
0x1800048c5  cmp     r13d, eax
0x1800048c8  jb      loc_180004A61
0x1800048ce  mov     rcx, rbx; void *
0x1800048d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800048d6  xor     r13d, r13d
0x1800048d9  mov     [rsp+970h+hKey], r13
0x1800048de  mov     rbx, rdi
0x1800048e1  inc     rbx
0x1800048e4  cmp     word ptr [r14+rbx*2], 0
0x1800048ea  jnz     short loc_1800048E1
0x1800048ec  mov     rcx, rdi
0x1800048ef  nop
0x1800048f0  inc     rcx
0x1800048f3  cmp     word ptr [r15+rcx*2], 0
0x1800048f9  jnz     short loc_1800048F0
0x1800048fb  mov     rax, rbx
0x1800048fe  not     rax
0x180004901  cmp     rax, rcx
0x180004904  jb      loc_180004BFF
0x18000490a  lea     rdx, [rcx+rbx]
0x18000490e  mov     rax, rdx
0x180004911  not     rax
0x180004914  cmp     rax, 2
0x180004918  jb      loc_180004BFF
0x18000491e  lea     rax, [rdx+2]
0x180004922  cmp     rax, 104h
0x180004928  ja      loc_180004BFF
0x18000492e  mov     r8, r14; Source
0x180004931  mov     edx, 104h; SizeInWords
0x180004936  mov     rcx, rsi; Destination
0x180004939  call    wcscpy_s
0x18000493e  cmp     word ptr [rsi+rbx*2-2], 5Ch ; '\'
0x180004944  jnz     loc_180004D28
0x18000494a  mov     r8, r15; Source
0x18000494d  mov     edx, 104h; SizeInWords
0x180004952  mov     rcx, rsi; Destination
0x180004955  call    wcscat_s
0x18000495a  lea     r9, [rsp+970h+hKey]; lpFilePart
0x18000495f  mov     edx, 104h; nBufferLength
0x180004964  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x18000496b  mov     rcx, rsi; lpFileName
0x18000496e  call    cs:__imp_GetFullPathNameW
0x180004974  dec     eax
0x180004976  cmp     eax, 102h
0x18000497b  ja      loc_180004BFF
0x180004981  mov     rdx, rsi; String2
0x180004984  lea     rcx, [rbp+870h+Buffer]; String1
0x18000498b  call    _wcsicmp
0x180004990  test    eax, eax
0x180004992  jnz     loc_180004BFF
0x180004998  mov     rax, rdi
0x18000499b  nop     dword ptr [rax+rax+00h]
0x1800049a0  inc     rax
0x1800049a3  cmp     word ptr [rsi+rax*2], 0
0x1800049a8  jnz     short loc_1800049A0
0x1800049aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800049ae  ja      loc_180004BFF
0x1800049b4  add     rax, 2
0x1800049b8  cmp     rax, 104h
0x1800049be  jnb     loc_180004BFF
0x1800049c4  lea     r8, asc_18004C8C0; "\\"
0x1800049cb  mov     edx, 104h; SizeInWords
0x1800049d0  mov     rcx, rsi; Destination
0x1800049d3  mov     ebx, r13d
0x1800049d6  call    wcscat_s
0x1800049db  mov     rax, rdi
0x1800049de  xchg    ax, ax
0x1800049e0  cmp     word ptr [rsi+rax*2+2], 0
0x1800049e6  lea     rax, [rax+1]
0x1800049ea  jnz     short loc_1800049E0
0x1800049ec  mov     rcx, r14; void *
0x1800049ef  lea     r15, [rax+1]
0x1800049f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800049f8  nop     dword ptr [rax+rax+00000000h]
0x180004a00  cmp     word ptr [r12+rdi*2+2], 0
0x180004a07  lea     rdi, [rdi+1]
0x180004a0b  jnz     short loc_180004A00
0x180004a0d  lea     rax, [rdi+r15]
0x180004a11  cmp     rax, 104h
0x180004a17  jb      loc_180004C11
0x180004a1d  mov     ebx, 800700A1h
0x180004a22  mov     r14, [rsp+970h+var_30]
0x180004a2a  mov     eax, ebx
0x180004a2c  mov     rbx, [rsp+970h+arg_18]
0x180004a34  mov     r13, [rsp+970h+var_28]
0x180004a3c  mov     rdi, [rsp+950h]
0x180004a44  mov     rcx, [rbp+870h+var_40]
0x180004a4b  xor     rcx, rsp; StackCookie
0x180004a4e  call    __security_check_cookie
0x180004a53  add     rsp, 958h
0x180004a5a  pop     r15
0x180004a5c  pop     r12
0x180004a5e  pop     rsi
0x180004a5f  pop     rbp
0x180004a60  retn
0x180004a61  mov     rcx, r14; void *
0x180004a64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004a69  mov     rcx, rbx; void *
0x180004a6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004a71  jmp     short loc_180004A1D
0x180004a73  call    cs:__imp_GetLastError
0x180004a79  test    eax, eax
0x180004a7b  jnz     loc_1800048AA
0x180004a81  mov     ecx, [rsp+970h+Type]; dwErrCode
0x180004a85  call    cs:__imp_SetLastError
0x180004a8b  jmp     loc_1800048AA
0x180004a90  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; hModule
0x180004a97  lea     rdx, [rbp+870h+Filename]; lpFilename
0x180004a9e  mov     r8d, 104h; nSize
0x180004aa4  call    cs:__imp_GetModuleFileNameW
0x180004aaa  dec     eax
0x180004aac  cmp     eax, 102h
0x180004ab1  ja      short loc_180004AE1
0x180004ab3  lea     r8, aLocal; ".local"
0x180004aba  mov     edx, 10Bh; SizeInWords
0x180004abf  lea     rcx, [rbp+870h+Filename]; Destination
0x180004ac6  call    wcscat_s
0x180004acb  lea     rcx, [rbp+870h+Filename]; lpFileName
0x180004ad2  call    cs:__imp_GetFileAttributesW
0x180004ad8  cmp     eax, 0FFFFFFFFh
0x180004adb  jnz     loc_180004BA2
0x180004ae1  mov     eax, cs:?g_UseLocalRuntime@@3HA; int g_UseLocalRuntime
0x180004ae7  cmp     eax, 0FFFFFFFFh
0x180004aea  jnz     loc_1800046BC
0x180004af0  mov     eax, r13d
0x180004af3  mov     cs:?g_UseLocalRuntime@@3HA, eax; int g_UseLocalRuntime
0x180004af9  jmp     loc_1800046C4
0x180004afe  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; hModule
0x180004b05  lea     rdx, [rbp+870h+FileName]; lpFilename
0x180004b0c  mov     r8d, 104h; nSize
0x180004b12  call    cs:__imp_GetModuleFileNameW
0x180004b18  dec     eax
0x180004b1a  cmp     eax, 102h
0x180004b1f  ja      short loc_180004B4F
0x180004b21  lea     r8, aLocal; ".local"
0x180004b28  mov     edx, 10Bh; SizeInWords
0x180004b2d  lea     rcx, [rbp+870h+FileName]; Destination
0x180004b34  call    wcscat_s
0x180004b39  lea     rcx, [rbp+870h+FileName]; lpFileName
0x180004b40  call    cs:__imp_GetFileAttributesW
0x180004b46  cmp     eax, 0FFFFFFFFh
0x180004b49  jnz     loc_180004C30
0x180004b4f  mov     eax, cs:?g_UseLocalRuntime@@3HA; int g_UseLocalRuntime
0x180004b55  cmp     eax, 0FFFFFFFFh
0x180004b58  jnz     loc_1800046D6
0x180004b5e  mov     cs:?g_UseLocalRuntime@@3HA, r13d; int g_UseLocalRuntime
0x180004b65  jmp     loc_1800046DE
0x180004b6a  call    cs:__imp_GetLastError
0x180004b70  test    eax, eax
0x180004b72  jnz     loc_180004762
0x180004b78  mov     ecx, r13d; dwErrCode
0x180004b7b  call    cs:__imp_SetLastError
0x180004b81  jmp     loc_180004762
0x180004b86  call    cs:__imp_GetLastError
  ... truncated ...
```
