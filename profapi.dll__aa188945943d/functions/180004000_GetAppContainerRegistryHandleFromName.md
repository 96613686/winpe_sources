# GetAppContainerRegistryHandleFromName

- ea: `0x180004000`
- end: `0x180004222`
- name: `GetAppContainerRegistryHandleFromName`
- size: `546`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, REGSAM, PHKEY)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003fdc`
- `0x180004000`
- `0x180004990`
- `0x180004c10`
- `0x180005b60`
- `0x180005b90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004161`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004153`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004153`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000413b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000413b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004038`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004038`

## string_xrefs

- `0x18000411b`: `minio\profapi\registry.cpp`
- `0x18000416e`: `minio\profapi\registry.cpp`
- `0x180004193`: `minio\profapi\registry.cpp`
- `0x1800041bb`: `minio\profapi\registry.cpp`
- `0x1800041ff`: `minio\profapi\registry.cpp`

## pseudocode

```c
__int64 __fastcall GetAppContainerRegistryHandleFromName(__int64 a1, __int64 a2, __int64 a3, REGSAM a4, PHKEY a5)
{
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  WCHAR *v13; // rdi
  LSTATUS v14; // eax
  HANDLE v15; // rax
  HANDLE ProcessHeap; // rax
  int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-48h]
  LPCWSTR lpSubKey[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY phkResult; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"minio\\profapi\\registry.cpp",
      (const char *)0x80070057LL,
      v19);
    return 2147942487LL;
  }
  phkResult = 0;
  v9 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v9 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x21,
            (unsigned int)"minio\\profapi\\registry.cpp",
            (const char *)v9,
            v19);
LABEL_16:
    if ( phkResult )
      RegCloseKey(phkResult);
    return v11;
  }
  memset(lpSubKey, 0, 24);
  v10 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          lpSubKey,
          L"%s%s",
          L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Storage\\",
          a1);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"minio\\profapi\\registry.cpp",
      (const char *)(unsigned int)v10,
      v19);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    goto LABEL_16;
  }
  if ( a2 )
  {
    v18 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
            lpSubKey,
            L"\\Children\\%s",
            a2);
    v11 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"minio\\profapi\\registry.cpp",
        (const char *)(unsigned int)v18,
        v19);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
      goto LABEL_16;
    }
  }
  if ( a3 )
  {
    v12 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
            lpSubKey,
            L"\\%s",
            a3);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"minio\\profapi\\registry.cpp",
        (const char *)(unsigned int)v12,
        v19);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
      goto LABEL_16;
    }
  }
  v13 = (WCHAR *)lpSubKey[0];
  v14 = RegOpenKeyExW(phkResult, lpSubKey[0], 0, a4, a5);
  v11 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    if ( v13 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
    }
    goto LABEL_16;
  }
  if ( v13 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v13);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180004000  mov     [rsp+arg_10], rbx
0x180004005  push    rbp
0x180004006  push    rsi
0x180004007  push    rdi
0x180004008  sub     rsp, 50h
0x18000400c  mov     ebp, r9d
0x18000400f  mov     rdi, r8
0x180004012  mov     rsi, rdx
0x180004015  mov     rbx, rcx
0x180004018  test    rcx, rcx
0x18000401b  jz      loc_1800041B6
0x180004021  mov     [rsp+68h+arg_8], r14
0x180004026  lea     rdx, [rsp+68h+phkResult]; phkResult
0x18000402b  xor     r14d, r14d
0x18000402e  mov     ecx, 20019h; samDesired
0x180004033  mov     [rsp+68h+phkResult], r14
0x180004038  call    cs:__imp_RegOpenCurrentUser
0x18000403e  test    eax, eax
0x180004040  jnz     loc_180004116
0x180004046  mov     r9, rbx
0x180004049  mov     [rsp+68h+lpSubKey], r14
0x18000404e  lea     r8, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x180004055  mov     [rsp+68h+var_30], r14
0x18000405a  lea     rdx, aSS; "%s%s"
0x180004061  mov     [rsp+68h+var_28], r14
0x180004066  lea     rcx, [rsp+68h+lpSubKey]
0x18000406b  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180004070  mov     ebx, eax
0x180004072  test    eax, eax
0x180004074  js      loc_18000418E
0x18000407a  test    rsi, rsi
0x18000407d  jnz     loc_1800041DC
0x180004083  test    rdi, rdi
0x180004086  jz      short loc_1800040A6
0x180004088  mov     r8, rdi
0x18000408b  lea     rdx, aS_0; "\\%s"
0x180004092  lea     rcx, [rsp+68h+lpSubKey]
0x180004097  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18000409c  mov     ebx, eax
0x18000409e  test    eax, eax
0x1800040a0  js      loc_180004169
0x1800040a6  mov     rax, [rsp+68h+arg_20]
0x1800040ae  mov     r9d, ebp; samDesired
0x1800040b1  mov     rdi, [rsp+68h+lpSubKey]
0x1800040b6  xor     r8d, r8d; ulOptions
0x1800040b9  mov     rcx, [rsp+68h+phkResult]; hKey
0x1800040be  mov     rdx, rdi; lpSubKey
0x1800040c1  mov     qword ptr [rsp+68h+var_48], rax; phkResult
0x1800040c6  call    cs:__imp_RegOpenKeyExW
0x1800040cc  mov     ebx, eax
0x1800040ce  test    eax, eax
0x1800040d0  jnz     short loc_180004143
0x1800040d2  test    rdi, rdi
0x1800040d5  jz      short loc_1800040EB
0x1800040d7  call    cs:__imp_GetProcessHeap
0x1800040dd  mov     r8, rdi; lpMem
0x1800040e0  xor     edx, edx; dwFlags
0x1800040e2  mov     rcx, rax; hHeap
0x1800040e5  call    cs:__imp_HeapFree
0x1800040eb  mov     rcx, [rsp+68h+phkResult]; hKey
0x1800040f0  test    rcx, rcx
0x1800040f3  jz      short loc_1800040FB
0x1800040f5  call    cs:__imp_RegCloseKey
0x1800040fb  xor     eax, eax
0x1800040fd  jmp     short loc_180004101
0x1800040ff  mov     eax, ebx
0x180004101  mov     r14, [rsp+68h+arg_8]
0x180004106  mov     rbx, [rsp+68h+arg_10]
0x18000410e  add     rsp, 50h
0x180004112  pop     rdi
0x180004113  pop     rsi
0x180004114  pop     rbp
0x180004115  retn
0x180004116  mov     rcx, [rsp+68h]; this
0x18000411b  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180004122  mov     r9d, eax; char *
0x180004125  mov     edx, 21h ; '!'; void *
0x18000412a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000412f  mov     ebx, eax
0x180004131  mov     rcx, [rsp+68h+phkResult]; hKey
0x180004136  test    rcx, rcx
0x180004139  jz      short loc_1800040FF
0x18000413b  call    cs:__imp_RegCloseKey
0x180004141  jmp     short loc_1800040FF
0x180004143  jle     short loc_18000414E
0x180004145  movzx   ebx, ax
0x180004148  or      ebx, 80070000h
0x18000414e  test    rdi, rdi
0x180004151  jz      short loc_180004131
0x180004153  call    cs:__imp_GetProcessHeap
0x180004159  mov     r8, rdi; lpMem
0x18000415c  xor     edx, edx; dwFlags
0x18000415e  mov     rcx, rax; hHeap
0x180004161  call    cs:__imp_HeapFree
0x180004167  jmp     short loc_180004131
0x180004169  mov     rcx, [rsp+68h]; this
0x18000416e  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180004175  mov     r9d, ebx; char *
0x180004178  mov     edx, 2Dh ; '-'; void *
0x18000417d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004182  lea     rcx, [rsp+68h+lpSubKey]
0x180004187  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000418c  jmp     short loc_180004131
0x18000418e  mov     rcx, [rsp+68h]; this
0x180004193  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x18000419a  mov     r9d, ebx; char *
0x18000419d  mov     edx, 24h ; '$'; void *
0x1800041a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041a7  lea     rcx, [rsp+68h+lpSubKey]
0x1800041ac  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800041b1  jmp     loc_180004131
0x1800041b6  mov     rcx, [rsp+68h]; this
0x1800041bb  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x1800041c2  mov     r9d, 80070057h; char *
0x1800041c8  mov     edx, 1Eh; void *
0x1800041cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041d2  mov     eax, 80070057h
0x1800041d7  jmp     loc_180004106
0x1800041dc  mov     r8, rsi
0x1800041df  lea     rdx, aChildrenS; "\\Children\\%s"
0x1800041e6  lea     rcx, [rsp+68h+lpSubKey]
0x1800041eb  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800041f0  mov     ebx, eax
0x1800041f2  test    eax, eax
0x1800041f4  jns     loc_180004083
0x1800041fa  mov     rcx, [rsp+68h]; this
0x1800041ff  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180004206  mov     r9d, eax; char *
0x180004209  mov     edx, 28h ; '('; void *
0x18000420e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004213  lea     rcx, [rsp+68h+lpSubKey]
0x180004218  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000421d  jmp     loc_180004131
```
