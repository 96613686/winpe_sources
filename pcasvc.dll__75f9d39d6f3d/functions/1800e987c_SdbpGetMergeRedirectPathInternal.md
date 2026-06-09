# SdbpGetMergeRedirectPathInternal

- ea: `0x1800e987c`
- end: `0x1800e9fe0`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1892`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e280`

## callees

- `0x18000a57c`
- `0x180012920`
- `0x180019c84`
- `0x18001b804`
- `0x18001bd38`
- `0x18001c870`
- `0x18001cbac`
- `0x18001cffc`
- `0x180025b40`
- `0x180031370`
- `0x180049e10`
- `0x1800e987c`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800e9ace`
- `msvcrt!_wcsnicmp` at `0x1800e9ace`
- `msvcrt!_wcsicmp` at `0x1800e9cf7`
- `msvcrt!_wcsicmp` at `0x1800e9d15`
- `msvcrt!_wcsicmp` at `0x1800e9cf7`
- `msvcrt!_wcsicmp` at `0x1800e9d15`
- `ntdll!ZwClose` at `0x1800e9cc8`
- `ntdll!ZwClose` at `0x1800e9cc8`
- `ntdll!RtlAllocateHeap` at `0x1800e9a11`
- `ntdll!RtlAllocateHeap` at `0x1800e9a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e99a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e99b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e99bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e99a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e99b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e99bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a56`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800e999b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800e9a38`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800e999b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800e9a38`

## string_xrefs

- `0x1800e9c76`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1800e9f3e`: `Failed to get manifested stub [%x]`
- `0x1800e9a67`: `Failed to get full path [%x]`
- `0x1800e9c90`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x1800e9c14`: `StagedDelete_`
- `0x1800e99d8`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9a73`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9be6`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9c3b`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9ca1`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9ddc`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9e2b`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9ea5`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9ef3`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e9f77`: `SdbpGetMergeRedirectPathInternal`
- `0x1800e99cc`: `Failed to get full path size [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, unsigned __int64 a4)
{
  __int64 v6; // rsi
  signed int LastError; // ebx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r12
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  __int64 v16; // r14
  __int64 FileNamePart; // rax
  const wchar_t *v18; // r15
  const wchar_t *i; // rsi
  unsigned __int64 v20; // r12
  const wchar_t *v21; // rsi
  int Key; // eax
  const char *v23; // r9
  int v24; // r8d
  wchar_t *v25; // rbx
  int UInt32; // eax
  unsigned int v27; // esi
  int FileTimestamp; // eax
  int v29; // r8d
  const char *v30; // r9
  int ManifestedMergeStubAlloc; // eax
  __int64 v32; // [rsp+30h] [rbp-79h] BYREF
  __int64 v33; // [rsp+38h] [rbp-71h]
  unsigned int v34; // [rsp+40h] [rbp-69h] BYREF
  int v35; // [rsp+44h] [rbp-65h]
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v37; // [rsp+50h] [rbp-59h] BYREF
  WCHAR *v38; // [rsp+58h] [rbp-51h]
  wchar_t *String1; // [rsp+60h] [rbp-49h] BYREF
  __int64 v40; // [rsp+68h] [rbp-41h] BYREF
  __int64 v41; // [rsp+70h] [rbp-39h] BYREF
  const wchar_t *v42; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v43; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v44; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v45; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v46; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v47; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD *v48; // [rsp+A8h] [rbp-1h]
  wchar_t String2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v35 = a3;
  v48 = a1;
  v6 = 0;
  v34 = 0;
  Handle = 0;
  String1 = 0;
  v44 = 0;
  v43 = 0;
  v37 = 0;
  v33 = 0;
  v40 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v32 = 0;
  v41 = 0;
  v42 = 0;
  wcscpy(String2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a4 + 2 * v9) );
    v10 = 0;
    if ( v9 <= 3 )
    {
      if ( v9 <= 1 )
      {
LABEL_16:
        FullPathNameW = GetFullPathNameW((LPCWSTR)a4, 0, 0, 0);
        v14 = FullPathNameW;
        if ( !FullPathNameW )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1816,
            (unsigned int)"Failed to get full path size [%x]");
          return (unsigned int)LastError;
        }
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * FullPathNameW);
        v38 = Heap;
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        if ( !GetFullPathNameW((LPCWSTR)a4, v14, Heap, 0) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1830,
            (unsigned int)"Failed to get full path [%x]");
          v16 = v32;
          goto LABEL_43;
        }
        a4 = (unsigned __int64)v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v18 = (const wchar_t *)FileNamePart;
        if ( FileNamePart == a4 )
        {
LABEL_41:
          v16 = v32;
          goto LABEL_42;
        }
        for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
        {
          if ( (unsigned __int64)i < a4 )
            goto LABEL_40;
          if ( (*i == 92 || *i == 47) && !_wcsnicmp(i, String2, 0xAu) )
            break;
        }
        LastError = RtlStringCchLengthW(v18, 0x7FFFFFFF, &v43);
        if ( LastError < 0 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1866,
            (unsigned int)"RtlStringCchLengthW failed [%x]");
LABEL_40:
          v6 = v33;
          goto LABEL_41;
        }
        v20 = v43;
        if ( v35 )
        {
          LastError = SdbpSafeAllocAndConcatW((unsigned int)&v42, (unsigned int)L"StagedDelete_", 13, (_DWORD)v18, v43);
          if ( LastError < 0 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"SdbpGetMergeRedirectPathInternal",
              1878,
              (unsigned int)"Failed to alloc and cat file to prefix [%x]");
            v6 = v33;
            v12 = v38;
            goto LABEL_41;
          }
          v21 = v42;
        }
        else
        {
          v21 = v18;
        }
        Key = AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                2147483904LL,
                1,
                0);
        LastError = Key;
        if ( Key < 0 )
        {
          if ( Key == -1073741772 )
          {
LABEL_66:
            v6 = v33;
LABEL_67:
            v16 = v32;
LABEL_68:
            if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              ZwClose(Handle);
            v12 = v38;
LABEL_42:
            if ( !v12 )
            {
LABEL_44:
              if ( String1 )
                AslFree(NtCurrentPeb()->ProcessHeap, String1);
              if ( v6 )
                AslFree(NtCurrentPeb()->ProcessHeap, v6);
              if ( v16 )
                AslFree(NtCurrentPeb()->ProcessHeap, v16);
              if ( v41 )
                AslFree(NtCurrentPeb()->ProcessHeap, v41);
              if ( v42 )
                AslFree(NtCurrentPeb()->ProcessHeap, v42);
              return (unsigned int)LastError;
            }
LABEL_43:
            AslFree(NtCurrentPeb()->ProcessHeap, v12);
            goto LABEL_44;
          }
          v23 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
          v24 = 1895;
LABEL_65:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v24, (_DWORD)v23);
          goto LABEL_66;
        }
        LastError = AslRegistryGetString(&String1, Handle, v21);
        if ( LastError < 0 )
          goto LABEL_66;
        v25 = String1;
        if ( !_wcsicmp(String1, v18) )
        {
          LastError = -1073741772;
          goto LABEL_66;
        }
        if ( v35 && !_wcsicmp(v25, L"__NotRedirected__") && a2 )
        {
          *a2 = 1;
          LastError = 0;
          goto LABEL_66;
        }
        LastError = SdbpSafeAllocAndConcatW((unsigned int)&v41, (unsigned int)L"MergeVer_", 9, (_DWORD)v21, 0);
        if ( LastError < 0 )
        {
          v23 = "Failed to alloc and cat file to prefix [%x]";
          v24 = 1929;
          goto LABEL_65;
        }
        UInt32 = AslRegistryGetUInt32(&v37, Handle, v41);
        LastError = UInt32;
        if ( UInt32 == -1073741772 )
        {
          v27 = 0;
        }
        else
        {
          if ( UInt32 < 0 )
          {
            v23 = "Failed to query reg value. [%x]";
            v24 = 1938;
            goto LABEL_65;
          }
          v27 = v37;
        }
        LastError = AslRegistryGetUInt32(&v34, Handle, L"MergeVer");
        if ( LastError < 0 )
        {
          v23 = "Failed to query reg value. [%x]";
          v24 = 1944;
          goto LABEL_65;
        }
        if ( v34 < v27 )
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1953,
            (unsigned int)"Merge target is too high of a version, this code might not handle it correctly.");
        LastError = AslRegistryGetUInt32(&v34, Handle, L"MinMergeVer");
        if ( LastError < 0 )
        {
          v23 = "Failed to query reg value. [%x]";
          v24 = 1959;
          goto LABEL_65;
        }
        if ( v27 < v34 )
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1968,
            (unsigned int)"Merge target is too low of a version, it might not be possible to handle correctly.");
        LastError = RtlStringCchLengthW(a4, 0x7FFFFFFF, &v44);
        if ( LastError < 0 )
        {
          v23 = "RtlStringCchLengthW failed [%x]";
          v24 = 1975;
          goto LABEL_65;
        }
        if ( v44 < v20 )
        {
          LastError = -1073741675;
          v23 = "RtlSizeTSub failed [%x]";
          v24 = 1982;
          goto LABEL_65;
        }
        LastError = SdbpSafeAllocAndConcatW((unsigned int)&v40, a4, (int)v44 - (int)v20, (_DWORD)String1, 0);
        if ( LastError < 0 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1992,
            (unsigned int)"Failed to alloc and cat file to prefix [%x]");
          v6 = v40;
          goto LABEL_67;
        }
        v6 = v40;
        FileTimestamp = SdbpGetFileTimestamp(&v45, v40, 1);
        LastError = FileTimestamp;
        if ( FileTimestamp >= 0 )
        {
          LastError = SdbpGetFileTimestamp(&v46, a4, 0);
          if ( LastError >= 0 )
          {
            ManifestedMergeStubAlloc = SdbpGetManifestedMergeStubAlloc(&v32, v18);
            LastError = ManifestedMergeStubAlloc;
            if ( ManifestedMergeStubAlloc == -1073741772 )
            {
              v16 = v32;
            }
            else
            {
              if ( ManifestedMergeStubAlloc < 0 )
              {
                v30 = "Failed to get manifested stub [%x]";
                v29 = 2028;
                goto LABEL_102;
              }
              v16 = v32;
              LastError = SdbpGetFileTimestamp(&v47, v32, 0);
              if ( LastError < 0 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"SdbpGetMergeRedirectPathInternal",
                  2038,
                  (unsigned int)"Failed to check timestamp [%x]");
                goto LABEL_68;
              }
            }
            if ( v45 < v46 || v45 < v47 )
            {
              LastError = -1073741772;
            }
            else
            {
              *v48 = v6;
              if ( a2 && v35 )
                *a2 = 1;
              v6 = 0;
              LastError = 0;
            }
            goto LABEL_68;
          }
          v29 = 2014;
        }
        else
        {
          if ( FileTimestamp == -1073741772 )
            goto LABEL_67;
          v29 = 2003;
        }
        v30 = "Failed to check timestamp [%x]";
LABEL_102:
        AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v29, (_DWORD)v30);
        goto LABEL_67;
      }
    }
    else if ( *(_WORD *)(a4 + 2) == 58 )
    {
      v10 = *(_WORD *)(a4 + 4) == 92;
    }
    v11 = *(_WORD *)a4 == 92;
    v12 = 0;
    v38 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x1800e987c  mov     [rsp-8+arg_10], rbx
0x1800e9881  push    rbp
0x1800e9882  push    rsi
0x1800e9883  push    rdi
0x1800e9884  push    r12
0x1800e9886  push    r13
0x1800e9888  push    r14
0x1800e988a  push    r15
0x1800e988c  lea     rbp, [rsp-27h]
0x1800e9891  sub     rsp, 0D0h
0x1800e9898  mov     rax, cs:__security_cookie
0x1800e989f  xor     rax, rsp
0x1800e98a2  mov     [rbp+57h+var_38], rax
0x1800e98a6  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x1800e98ad  xor     edi, edi
0x1800e98af  mov     eax, r8d
0x1800e98b2  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x1800e98ba  mov     r14, r9
0x1800e98bd  mov     [rbp+57h+var_BC], eax
0x1800e98c0  mov     r13, rdx
0x1800e98c3  mov     [rbp+57h+var_58], rcx
0x1800e98c7  mov     esi, edi
0x1800e98c9  mov     [rbp+57h+var_C0], edi
0x1800e98cc  mov     [rbp+57h+Handle], rdi
0x1800e98d0  mov     [rbp+57h+String1], rdi
0x1800e98d4  mov     [rbp+57h+var_78], rdi
0x1800e98d8  mov     [rbp+57h+var_80], rdi
0x1800e98dc  mov     [rbp+57h+var_B0], edi
0x1800e98df  mov     [rbp+57h+var_C8], rdi
0x1800e98e3  mov     [rbp+57h+var_98], rdi
0x1800e98e7  mov     [rbp+57h+var_70], rdi
0x1800e98eb  mov     [rbp+57h+var_68], rdi
0x1800e98ef  mov     [rbp+57h+var_60], rdi
0x1800e98f3  mov     [rbp+57h+var_D0], rdi
0x1800e98f7  mov     [rbp+57h+var_90], rdi
0x1800e98fb  mov     [rbp+57h+var_88], rdi
0x1800e98ff  movups  xmmword ptr [rbp+57h+String2], xmm0
0x1800e9903  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x1800e9908  test    rcx, rcx
0x1800e990b  jnz     short loc_1800E9917
0x1800e990d  mov     eax, 0C00000EFh
0x1800e9912  jmp     loc_1800E9B97
0x1800e9917  mov     [rcx], rdi
0x1800e991a  test    r13, r13
0x1800e991d  jz      short loc_1800E9925
0x1800e991f  test    eax, eax
0x1800e9921  jz      short loc_1800E9925
0x1800e9923  mov     [rdx], edi
0x1800e9925  call    SdbpGetMergeSdbsSupported
0x1800e992a  test    eax, eax
0x1800e992c  jnz     short loc_1800E9938
0x1800e992e  mov     ebx, 0C0000034h
0x1800e9933  jmp     loc_1800E9B95
0x1800e9938  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e993c  inc     rax
0x1800e993f  cmp     [r14+rax*2], di
0x1800e9944  jnz     short loc_1800E993C
0x1800e9946  mov     r15d, 1
0x1800e994c  mov     ecx, edi
0x1800e994e  cmp     rax, 3
0x1800e9952  jbe     short loc_1800E9969
0x1800e9954  cmp     word ptr [r14+2], 3Ah ; ':'
0x1800e995a  jnz     short loc_1800E996E
0x1800e995c  cmp     word ptr [r14+4], 5Ch ; '\'
0x1800e9962  jnz     short loc_1800E996E
0x1800e9964  mov     ecx, r15d
0x1800e9967  jmp     short loc_1800E996E
0x1800e9969  cmp     rax, r15
0x1800e996c  jbe     short loc_1800E9990
0x1800e996e  cmp     word ptr [r14], 5Ch ; '\'
0x1800e9973  mov     eax, edi
0x1800e9975  mov     r12, rdi
0x1800e9978  mov     [rbp+57h+var_A8], rdi
0x1800e997c  cmovz   eax, r15d
0x1800e9980  test    ecx, ecx
0x1800e9982  jnz     loc_1800E9A98
0x1800e9988  test    eax, eax
0x1800e998a  jnz     loc_1800E9A98
0x1800e9990  xor     r9d, r9d; lpFilePart
0x1800e9993  xor     r8d, r8d; lpBuffer
0x1800e9996  xor     edx, edx; nBufferLength
0x1800e9998  mov     rcx, r14; lpFileName
0x1800e999b  call    cs:__imp_GetFullPathNameW
0x1800e99a1  mov     ebx, eax
0x1800e99a3  test    eax, eax
0x1800e99a5  jnz     short loc_1800E99F9
0x1800e99a7  call    cs:__imp_GetLastError
0x1800e99ad  test    eax, eax
0x1800e99af  jg      short loc_1800E99BB
0x1800e99b1  call    cs:__imp_GetLastError
0x1800e99b7  mov     ebx, eax
0x1800e99b9  jmp     short loc_1800E99CA
0x1800e99bb  call    cs:__imp_GetLastError
0x1800e99c1  movzx   ebx, ax
0x1800e99c4  or      ebx, 0C0070000h
0x1800e99ca  test    ebx, ebx
0x1800e99cc  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x1800e99d3  mov     eax, 0C00000E5h
0x1800e99d8  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800e99df  cmovns  ebx, eax
0x1800e99e2  mov     r8d, 718h
0x1800e99e8  mov     ecx, r15d
0x1800e99eb  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800e99ef  call    AslLogCallPrintf
0x1800e99f4  jmp     loc_1800E9B95
0x1800e99f9  mov     rcx, gs:60h
0x1800e9a02  mov     r8, rbx
0x1800e9a05  add     r8, r8; Size
0x1800e9a08  mov     edx, 8; Flags
0x1800e9a0d  mov     rcx, [rcx+30h]; HeapHandle
0x1800e9a11  call    cs:__imp_RtlAllocateHeap
0x1800e9a17  mov     [rbp+57h+var_A8], rax
0x1800e9a1b  mov     r12, rax
0x1800e9a1e  test    rax, rax
0x1800e9a21  jnz     short loc_1800E9A2D
0x1800e9a23  mov     ebx, 0C0000017h
0x1800e9a28  jmp     loc_1800E9B95
0x1800e9a2d  xor     r9d, r9d; lpFilePart
0x1800e9a30  mov     r8, r12; lpBuffer
0x1800e9a33  mov     edx, ebx; nBufferLength
0x1800e9a35  mov     rcx, r14; lpFileName
0x1800e9a38  call    cs:__imp_GetFullPathNameW
0x1800e9a3e  test    eax, eax
0x1800e9a40  jnz     short loc_1800E9A95
0x1800e9a42  call    cs:__imp_GetLastError
0x1800e9a48  test    eax, eax
0x1800e9a4a  jg      short loc_1800E9A56
0x1800e9a4c  call    cs:__imp_GetLastError
0x1800e9a52  mov     ebx, eax
0x1800e9a54  jmp     short loc_1800E9A65
0x1800e9a56  call    cs:__imp_GetLastError
0x1800e9a5c  movzx   ebx, ax
0x1800e9a5f  or      ebx, 0C0070000h
0x1800e9a65  test    ebx, ebx
0x1800e9a67  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x1800e9a6e  mov     eax, 0C00000E5h
0x1800e9a73  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800e9a7a  cmovns  ebx, eax
0x1800e9a7d  mov     r8d, 726h
0x1800e9a83  mov     ecx, r15d
0x1800e9a86  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800e9a8a  call    AslLogCallPrintf
0x1800e9a8f  mov     r14, [rbp+57h+var_D0]
0x1800e9a93  jmp     short loc_1800E9AF2
0x1800e9a95  mov     r14, r12
0x1800e9a98  mov     edi, 0C0000034h
0x1800e9a9d  mov     rcx, r14
0x1800e9aa0  mov     ebx, edi
0x1800e9aa2  call    AslPathGetFileNamePart
0x1800e9aa7  mov     r15, rax
0x1800e9aaa  cmp     rax, r14
0x1800e9aad  jz      short loc_1800E9AE9
0x1800e9aaf  lea     rsi, [rax-4]
0x1800e9ab3  jmp     short loc_1800E9AE0
0x1800e9ab5  cmp     word ptr [rsi], 5Ch ; '\'
0x1800e9ab9  jz      short loc_1800E9AC1
0x1800e9abb  cmp     word ptr [rsi], 2Fh ; '/'
0x1800e9abf  jnz     short loc_1800E9ADC
0x1800e9ac1  mov     r8d, 0Ah; MaxCount
0x1800e9ac7  lea     rdx, [rbp+57h+String2]; String2
0x1800e9acb  mov     rcx, rsi; String1
0x1800e9ace  call    cs:__imp__wcsnicmp
0x1800e9ad4  test    eax, eax
0x1800e9ad6  jz      loc_1800E9BBE
0x1800e9adc  sub     rsi, 2
0x1800e9ae0  cmp     rsi, r14
0x1800e9ae3  jnb     short loc_1800E9AB5
0x1800e9ae5  mov     rsi, [rbp+57h+var_C8]
0x1800e9ae9  mov     r14, [rbp+57h+var_D0]
0x1800e9aed  test    r12, r12
0x1800e9af0  jz      short loc_1800E9B07
0x1800e9af2  mov     rcx, gs:60h
0x1800e9afb  mov     rdx, r12
0x1800e9afe  mov     rcx, [rcx+30h]
0x1800e9b02  call    AslFree
0x1800e9b07  mov     rax, [rbp+57h+String1]
0x1800e9b0b  test    rax, rax
0x1800e9b0e  jz      short loc_1800E9B25
0x1800e9b10  mov     rcx, gs:60h
0x1800e9b19  mov     rdx, rax
0x1800e9b1c  mov     rcx, [rcx+30h]
0x1800e9b20  call    AslFree
0x1800e9b25  test    rsi, rsi
0x1800e9b28  jz      short loc_1800E9B3F
0x1800e9b2a  mov     rcx, gs:60h
0x1800e9b33  mov     rdx, rsi
0x1800e9b36  mov     rcx, [rcx+30h]
0x1800e9b3a  call    AslFree
0x1800e9b3f  test    r14, r14
0x1800e9b42  jz      short loc_1800E9B59
0x1800e9b44  mov     rcx, gs:60h
0x1800e9b4d  mov     rdx, r14
0x1800e9b50  mov     rcx, [rcx+30h]
0x1800e9b54  call    AslFree
0x1800e9b59  mov     rax, [rbp+57h+var_90]
0x1800e9b5d  test    rax, rax
0x1800e9b60  jz      short loc_1800E9B77
0x1800e9b62  mov     rcx, gs:60h
0x1800e9b6b  mov     rdx, rax
0x1800e9b6e  mov     rcx, [rcx+30h]
0x1800e9b72  call    AslFree
0x1800e9b77  mov     rax, [rbp+57h+var_88]
0x1800e9b7b  test    rax, rax
0x1800e9b7e  jz      short loc_1800E9B95
0x1800e9b80  mov     rcx, gs:60h
0x1800e9b89  mov     rdx, rax
0x1800e9b8c  mov     rcx, [rcx+30h]
0x1800e9b90  call    AslFree
0x1800e9b95  mov     eax, ebx
0x1800e9b97  mov     rcx, [rbp+57h+var_38]
0x1800e9b9b  xor     rcx, rsp; StackCookie
0x1800e9b9e  call    __security_check_cookie
0x1800e9ba3  mov     rbx, [rsp+100h+arg_10]
0x1800e9bab  add     rsp, 0D0h
0x1800e9bb2  pop     r15
0x1800e9bb4  pop     r14
0x1800e9bb6  pop     r13
0x1800e9bb8  pop     r12
0x1800e9bba  pop     rdi
0x1800e9bbb  pop     rsi
0x1800e9bbc  pop     rbp
0x1800e9bbd  retn
0x1800e9bbe  lea     r8, [rbp+57h+var_80]
0x1800e9bc2  mov     edx, 7FFFFFFFh
0x1800e9bc7  mov     rcx, r15
0x1800e9bca  call    RtlStringCchLengthW
0x1800e9bcf  mov     ebx, eax
0x1800e9bd1  test    eax, eax
0x1800e9bd3  jns     short loc_1800E9BFC
0x1800e9bd5  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x1800e9bdc  mov     dword ptr [rsp+100h+var_E0], eax
0x1800e9be0  mov     r8d, 74Ah
0x1800e9be6  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800e9bed  mov     ecx, 1
0x1800e9bf2  call    AslLogCallPrintf
0x1800e9bf7  jmp     loc_1800E9AE5
0x1800e9bfc  cmp     [rbp+57h+var_BC], 0
0x1800e9c00  mov     r12, [rbp+57h+var_80]
0x1800e9c04  jz      short loc_1800E9C5F
0x1800e9c06  mov     r9, r15
0x1800e9c09  mov     [rsp+100h+var_E0], r12
0x1800e9c0e  mov     r8d, 0Dh
0x1800e9c14  lea     rdx, aStageddelete; "StagedDelete_"
0x1800e9c1b  lea     rcx, [rbp+57h+var_88]
0x1800e9c1f  call    SdbpSafeAllocAndConcatW
0x1800e9c24  mov     ebx, eax
0x1800e9c26  test    eax, eax
0x1800e9c28  jns     short loc_1800E9C59
0x1800e9c2a  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x1800e9c31  mov     dword ptr [rsp+100h+var_E0], eax
0x1800e9c35  mov     r8d, 756h
0x1800e9c3b  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800e9c42  mov     ecx, 1
0x1800e9c47  call    AslLogCallPrintf
0x1800e9c4c  mov     rsi, [rbp+57h+var_C8]
0x1800e9c50  mov     r12, [rbp+57h+var_A8]
0x1800e9c54  jmp     loc_1800E9AE9
0x1800e9c59  mov     rsi, [rbp+57h+var_88]
0x1800e9c5d  jmp     short loc_1800E9C62
0x1800e9c5f  mov     rsi, r15
0x1800e9c62  mov     r9d, 1
0x1800e9c68  mov     dword ptr [rsp+100h+var_E0], 0
0x1800e9c70  mov     r8d, 80000100h
0x1800e9c76  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800e9c7d  lea     rcx, [rbp+57h+Handle]
0x1800e9c81  call    AslRegistryGetKey
0x1800e9c86  mov     ebx, eax
0x1800e9c88  test    eax, eax
0x1800e9c8a  jns     short loc_1800E9CD7
0x1800e9c8c  cmp     eax, edi
0x1800e9c8e  jz      short loc_1800E9CB2
0x1800e9c90  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1800e9c97  mov     r8d, 767h
0x1800e9c9d  mov     dword ptr [rsp+100h+var_E0], eax
0x1800e9ca1  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800e9ca8  mov     ecx, 1
0x1800e9cad  call    AslLogCallPrintf
0x1800e9cb2  mov     rsi, [rbp+57h+var_C8]
0x1800e9cb6  mov     r14, [rbp+57h+var_D0]
0x1800e9cba  mov     rcx, [rbp+57h+Handle]; Handle
0x1800e9cbe  lea     rax, [rcx-1]
0x1800e9cc2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e9cc6  ja      short loc_1800E9CCE
0x1800e9cc8  call    cs:__imp_ZwClose
0x1800e9cce  mov     r12, [rbp+57h+var_A8]
0x1800e9cd2  jmp     loc_1800E9AED
0x1800e9cd7  mov     rdx, [rbp+57h+Handle]
0x1800e9cdb  lea     rcx, [rbp+57h+String1]
0x1800e9cdf  mov     r8, rsi
0x1800e9ce2  call    AslRegistryGetString
0x1800e9ce7  mov     ebx, eax
0x1800e9ce9  test    eax, eax
0x1800e9ceb  js      short loc_1800E9CB2
0x1800e9ced  mov     rbx, [rbp+57h+String1]
0x1800e9cf1  mov     rdx, r15; String2
0x1800e9cf4  mov     rcx, rbx; String1
0x1800e9cf7  call    cs:__imp__wcsicmp
0x1800e9cfd  test    eax, eax
0x1800e9cff  jnz     short loc_1800E9D05
0x1800e9d01  mov     ebx, edi
  ... truncated ...
```
