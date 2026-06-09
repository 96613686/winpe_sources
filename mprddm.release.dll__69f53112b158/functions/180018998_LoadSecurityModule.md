# LoadSecurityModule

- ea: `0x180018998`
- end: `0x180018d83`
- name: `LoadSecurityModule`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x18001612c`
- `0x180018998`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180018b80`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180018c0e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180018b80`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180018c0e`
- `KERNEL32!GetProcAddress` at `0x180018cac`
- `KERNEL32!GetProcAddress` at `0x180018cd2`
- `KERNEL32!GetProcAddress` at `0x180018cac`
- `KERNEL32!GetProcAddress` at `0x180018cd2`
- `KERNEL32!LoadLibraryExW` at `0x180018c2e`
- `KERNEL32!LoadLibraryExW` at `0x180018c2e`
- `KERNEL32!HeapAlloc` at `0x180018a9e`
- `KERNEL32!HeapAlloc` at `0x180018bc6`
- `KERNEL32!HeapAlloc` at `0x180018a9e`
- `KERNEL32!HeapAlloc` at `0x180018bc6`
- `KERNEL32!GetLastError` at `0x180018ab2`
- `KERNEL32!GetLastError` at `0x180018b93`
- `KERNEL32!GetLastError` at `0x180018bdb`
- `KERNEL32!GetLastError` at `0x180018c46`
- `KERNEL32!GetLastError` at `0x180018cea`
- `KERNEL32!GetLastError` at `0x180018ab2`
- `KERNEL32!GetLastError` at `0x180018b93`
- `KERNEL32!GetLastError` at `0x180018bdb`
- `KERNEL32!GetLastError` at `0x180018c46`
- `KERNEL32!GetLastError` at `0x180018cea`
- `KERNEL32!HeapFree` at `0x180018d39`
- `KERNEL32!HeapFree` at `0x180018d57`
- `KERNEL32!HeapFree` at `0x180018d39`
- `KERNEL32!HeapFree` at `0x180018d57`
- `ADVAPI32!RegOpenKeyW` at `0x1800189d5`
- `ADVAPI32!RegOpenKeyW` at `0x1800189d5`
- `ADVAPI32!RegQueryValueExW` at `0x180018af5`
- `ADVAPI32!RegQueryValueExW` at `0x180018af5`
- `ADVAPI32!RegCloseKey` at `0x180018d67`
- `ADVAPI32!RegCloseKey` at `0x180018d67`
- `rtutils!RouterLogEventW` at `0x180018a79`
- `rtutils!RouterLogEventW` at `0x180018b31`
- `rtutils!RouterLogEventW` at `0x180018a79`
- `rtutils!RouterLogEventW` at `0x180018b31`
- `rtutils!RouterLogEventStringW` at `0x180018a22`
- `rtutils!RouterLogEventStringW` at `0x180018d21`
- `rtutils!RouterLogEventStringW` at `0x180018a22`
- `rtutils!RouterLogEventStringW` at `0x180018d21`

## string_xrefs

- `0x1800189af`: `Software\Microsoft\RAS\SecurityHost`
- `0x180018aee`: `DllPath`
- `0x180018ca2`: `RasSecurityDialogBegin`
- `0x180018ccb`: `RasSecurityDialogEnd`

## pseudocode

```c
__int64 LoadSecurityModule()
{
  LSTATUS v0; // eax
  DWORD v1; // ebx
  unsigned int KeyMax; // eax
  DWORD v4; // r8d
  BYTE *v5; // rsi
  LSTATUS v6; // eax
  DWORD v7; // r9d
  DWORD v8; // r8d
  DWORD v9; // eax
  DWORD v10; // r14d
  DWORD v11; // eax
  WCHAR *v12; // rax
  DWORD LastError; // eax
  HMODULE Library; // rax
  DWORD v15; // eax
  LPWSTR *plpszSubStringArray; // [rsp+20h] [rbp-38h]
  DWORD dwErrorCode; // [rsp+28h] [rbp-30h]
  LPCWSTR lpLibFileName; // [rsp+40h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+38h] BYREF
  DWORD Type; // [rsp+98h] [rbp+40h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+50h] BYREF

  phkResult = 0;
  cbData = 0;
  v23 = 0;
  v22 = 0;
  Type = 0;
  lpLibFileName = 0;
  v0 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RAS\\SecurityHost", &phkResult);
  v1 = v0;
  if ( v0 == 2 )
    return 0;
  if ( !v0 )
  {
    KeyMax = GetKeyMax(phkResult, &v23, &v22, &cbData);
    v1 = KeyMax;
    if ( KeyMax )
    {
      if ( !dword_1800CF4E4 )
      {
LABEL_40:
        if ( lpLibFileName )
          HeapFree(hHeap, 0, (LPVOID)lpLibFileName);
        RegCloseKey(phkResult);
        return v1;
      }
      v4 = 20002;
LABEL_9:
      RouterLogEventW(hLogHandle, 1u, v4, 0, 0, KeyMax);
      goto LABEL_40;
    }
    v5 = (BYTE *)HeapAlloc(hHeap, 8u, cbData + 2LL);
    if ( !v5 )
    {
      KeyMax = GetLastError();
      v1 = KeyMax;
      if ( !dword_1800CF4E4 )
        goto LABEL_40;
      v4 = 20104;
      goto LABEL_9;
    }
    v6 = RegQueryValueExW(phkResult, L"DllPath", 0, &Type, v5, &cbData);
    v1 = v6;
    if ( v6 )
    {
      if ( dword_1800CF4E4 )
      {
        v7 = 0;
        dwErrorCode = v6;
        plpszSubStringArray = 0;
        v8 = 20002;
LABEL_16:
        RouterLogEventW(hLogHandle, 1u, v8, v7, plpszSubStringArray, dwErrorCode);
      }
LABEL_39:
      HeapFree(hHeap, 0, v5);
      goto LABEL_40;
    }
    if ( Type - 1 <= 1 )
    {
      v9 = ExpandEnvironmentStringsW((LPCWSTR)v5, 0, 0);
      v10 = v9;
      if ( v9 )
      {
        v12 = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * v9);
        lpLibFileName = v12;
        if ( !v12 )
        {
          LastError = GetLastError();
          v1 = LastError;
          if ( !dword_1800CF4E4 )
            goto LABEL_39;
          dwErrorCode = LastError;
          v8 = 20104;
          goto LABEL_21;
        }
        if ( ExpandEnvironmentStringsW((LPCWSTR)v5, v12, v10) )
        {
          Library = LoadLibraryExW(lpLibFileName, 0, 0x1000u);
          hModule = Library;
          if ( Library )
          {
            qword_1800CF5E0 = (__int64)GetProcAddress(Library, "RasSecurityDialogBegin");
            if ( !qword_1800CF5E0 || (qword_1800CF5E8 = (__int64)GetProcAddress(hModule, "RasSecurityDialogEnd")) == 0 )
            {
              v15 = GetLastError();
              v1 = v15;
              if ( dword_1800CF4E4 )
                RouterLogEventStringW(hLogHandle, 1u, 0x4E7Cu, 0, 0, v15, 0);
            }
            goto LABEL_39;
          }
          v1 = GetLastError();
          if ( v1 - 191 > 2 )
          {
            if ( dword_1800CF4E4 )
              RouterLogEventStringW(hLogHandle, 1u, 0x4E7Cu, 0, 0, v1, 0);
            goto LABEL_39;
          }
          if ( dword_1800CF4E4 )
          {
            dwErrorCode = 0;
            plpszSubStringArray = (LPWSTR *)&lpLibFileName;
            v7 = 1;
            v8 = 20203;
            goto LABEL_16;
          }
          goto LABEL_39;
        }
      }
      v11 = GetLastError();
      v1 = v11;
      if ( !dword_1800CF4E4 )
        goto LABEL_39;
      dwErrorCode = v11;
    }
    else
    {
      v1 = 1015;
      if ( !dword_1800CF4E4 )
        goto LABEL_39;
      dwErrorCode = 1015;
    }
    v8 = 20002;
LABEL_21:
    v7 = 0;
    plpszSubStringArray = 0;
    goto LABEL_16;
  }
  if ( dword_1800CF4E4 )
    RouterLogEventStringW(hLogHandle, 1u, 0x4E7Bu, 0, 0, v0, 0);
  return v1;
}

```

## disassembly

```asm
0x180018998  push    rbp
0x18001899a  push    rbx
0x18001899b  push    rsi
0x18001899c  push    rdi
0x18001899d  push    r14
0x18001899f  push    r15
0x1800189a1  mov     rbp, rsp
0x1800189a4  sub     rsp, 58h
0x1800189a8  xor     r15d, r15d
0x1800189ab  lea     r8, [rbp+phkResult]; phkResult
0x1800189af  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS\\SecurityHost"
0x1800189b6  mov     [rbp+phkResult], r15
0x1800189ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800189c1  mov     [rbp+cbData], r15d
0x1800189c5  mov     [rbp+arg_18], r15d
0x1800189c9  mov     [rbp+arg_10], r15d
0x1800189cd  mov     [rbp+Type], r15d
0x1800189d1  mov     [rbp+lpLibFileName], r15
0x1800189d5  call    cs:__imp_RegOpenKeyW
0x1800189dc  nop     dword ptr [rax+rax+00h]
0x1800189e1  mov     ebx, eax
0x1800189e3  cmp     eax, 2
0x1800189e6  jnz     short loc_1800189EF
0x1800189e8  xor     eax, eax
0x1800189ea  jmp     loc_180018D75
0x1800189ef  test    ebx, ebx
0x1800189f1  jz      short loc_180018A33
0x1800189f3  cmp     cs:dword_1800CF4E4, r15d
0x1800189fa  jbe     loc_180018D73
0x180018a00  mov     rcx, cs:hLogHandle; hLogHandle
0x180018a07  xor     r9d, r9d; dwSubStringCount
0x180018a0a  mov     [rsp+58h+dwErrorIndex], r15d; dwErrorIndex
0x180018a0f  mov     r8d, 4E7Bh; dwMessageId
0x180018a15  mov     [rsp+58h+dwErrorCode], ebx; dwErrorCode
0x180018a19  mov     [rsp+58h+plpszSubStringArray], r15; plpszSubStringArray
0x180018a1e  lea     edx, [r9+1]; dwEventType
0x180018a22  call    cs:__imp_RouterLogEventStringW
0x180018a29  nop     dword ptr [rax+rax+00h]
0x180018a2e  jmp     loc_180018D73
0x180018a33  mov     rcx, [rbp+phkResult]; HKEY
0x180018a37  lea     r9, [rbp+cbData]; unsigned int *
0x180018a3b  lea     r8, [rbp+arg_10]; unsigned int *
0x180018a3f  lea     rdx, [rbp+arg_18]; unsigned int *
0x180018a43  call    ?GetKeyMax@@YAKPEAUHKEY__@@PEAK11@Z; GetKeyMax(HKEY__ *,ulong *,ulong *,ulong *)
0x180018a48  mov     ebx, eax
0x180018a4a  test    eax, eax
0x180018a4c  jz      short loc_180018A8A
0x180018a4e  cmp     cs:dword_1800CF4E4, r15d
0x180018a55  jbe     loc_180018D45
0x180018a5b  mov     r8d, 4E22h; dwMessageId
0x180018a61  mov     rcx, cs:hLogHandle; hLogHandle
0x180018a68  mov     edx, 1; dwEventType
0x180018a6d  mov     [rsp+58h+dwErrorCode], eax; dwErrorCode
0x180018a71  xor     r9d, r9d; dwSubStringCount
0x180018a74  mov     [rsp+58h+plpszSubStringArray], r15; plpszSubStringArray
0x180018a79  call    cs:__imp_RouterLogEventW
0x180018a80  nop     dword ptr [rax+rax+00h]
0x180018a85  jmp     loc_180018D45
0x180018a8a  mov     r8d, [rbp+cbData]
0x180018a8e  mov     edx, 8; dwFlags
0x180018a93  mov     rcx, cs:hHeap; hHeap
0x180018a9a  add     r8, 2; dwBytes
0x180018a9e  call    cs:__imp_HeapAlloc
0x180018aa5  nop     dword ptr [rax+rax+00h]
0x180018aaa  mov     rsi, rax
0x180018aad  test    rax, rax
0x180018ab0  jnz     short loc_180018AD5
0x180018ab2  call    cs:__imp_GetLastError
0x180018ab9  nop     dword ptr [rax+rax+00h]
0x180018abe  cmp     cs:dword_1800CF4E4, r15d
0x180018ac5  mov     ebx, eax
0x180018ac7  jbe     loc_180018D45
0x180018acd  mov     r8d, 4E88h
0x180018ad3  jmp     short loc_180018A61
0x180018ad5  mov     rcx, [rbp+phkResult]; hKey
0x180018ad9  lea     rax, [rbp+cbData]
0x180018add  mov     qword ptr [rsp+58h+dwErrorCode], rax; lpcbData
0x180018ae2  lea     r9, [rbp+Type]; lpType
0x180018ae6  xor     r8d, r8d; lpReserved
0x180018ae9  mov     [rsp+58h+plpszSubStringArray], rsi; lpData
0x180018aee  lea     rdx, aDllpath; "DllPath"
0x180018af5  call    cs:__imp_RegQueryValueExW
0x180018afc  nop     dword ptr [rax+rax+00h]
0x180018b01  mov     ebx, eax
0x180018b03  test    eax, eax
0x180018b05  jz      short loc_180018B42
0x180018b07  cmp     cs:dword_1800CF4E4, r15d
0x180018b0e  jbe     loc_180018D2D
0x180018b14  xor     r9d, r9d; dwSubStringCount
0x180018b17  mov     [rsp+58h+dwErrorCode], eax; dwErrorCode
0x180018b1b  mov     [rsp+58h+plpszSubStringArray], r15; plpszSubStringArray
0x180018b20  mov     r8d, 4E22h; dwMessageId
0x180018b26  lea     edx, [r9+1]; dwEventType
0x180018b2a  mov     rcx, cs:hLogHandle; hLogHandle
0x180018b31  call    cs:__imp_RouterLogEventW
0x180018b38  nop     dword ptr [rax+rax+00h]
0x180018b3d  jmp     loc_180018D2D
0x180018b42  mov     eax, [rbp+Type]
0x180018b45  mov     edi, 1
0x180018b4a  dec     eax
0x180018b4c  cmp     eax, edi
0x180018b4e  jbe     short loc_180018B78
0x180018b50  cmp     cs:dword_1800CF4E4, r15d
0x180018b57  mov     ebx, 3F7h
0x180018b5c  jbe     loc_180018D2D
0x180018b62  mov     [rsp+58h+dwErrorCode], ebx
0x180018b66  mov     r8d, 4E22h
0x180018b6c  xor     r9d, r9d
0x180018b6f  mov     [rsp+58h+plpszSubStringArray], r15
0x180018b74  mov     edx, edi
0x180018b76  jmp     short loc_180018B2A
0x180018b78  xor     r8d, r8d; nSize
0x180018b7b  xor     edx, edx; lpDst
0x180018b7d  mov     rcx, rsi; lpSrc
0x180018b80  call    cs:__imp_ExpandEnvironmentStringsW
0x180018b87  nop     dword ptr [rax+rax+00h]
0x180018b8c  mov     r14d, eax
0x180018b8f  test    eax, eax
0x180018b91  jnz     short loc_180018BB4
0x180018b93  call    cs:__imp_GetLastError
0x180018b9a  nop     dword ptr [rax+rax+00h]
0x180018b9f  cmp     cs:dword_1800CF4E4, r15d
0x180018ba6  mov     ebx, eax
0x180018ba8  jbe     loc_180018D2D
0x180018bae  mov     [rsp+58h+dwErrorCode], eax
0x180018bb2  jmp     short loc_180018B66
0x180018bb4  mov     rcx, cs:hHeap; hHeap
0x180018bbb  mov     r8, r14
0x180018bbe  add     r8, r8; dwBytes
0x180018bc1  mov     edx, 8; dwFlags
0x180018bc6  call    cs:__imp_HeapAlloc
0x180018bcd  nop     dword ptr [rax+rax+00h]
0x180018bd2  mov     [rbp+lpLibFileName], rax
0x180018bd6  test    rax, rax
0x180018bd9  jnz     short loc_180018C05
0x180018bdb  call    cs:__imp_GetLastError
0x180018be2  nop     dword ptr [rax+rax+00h]
0x180018be7  cmp     cs:dword_1800CF4E4, r15d
0x180018bee  mov     ebx, eax
0x180018bf0  jbe     loc_180018D2D
0x180018bf6  mov     [rsp+58h+dwErrorCode], eax
0x180018bfa  mov     r8d, 4E88h
0x180018c00  jmp     loc_180018B6C
0x180018c05  mov     r8d, r14d; nSize
0x180018c08  mov     rdx, rax; lpDst
0x180018c0b  mov     rcx, rsi; lpSrc
0x180018c0e  call    cs:__imp_ExpandEnvironmentStringsW
0x180018c15  nop     dword ptr [rax+rax+00h]
0x180018c1a  test    eax, eax
0x180018c1c  jz      loc_180018B93
0x180018c22  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180018c26  xor     edx, edx; hFile
0x180018c28  mov     r8d, 1000h; dwFlags
0x180018c2e  call    cs:__imp_LoadLibraryExW
0x180018c35  nop     dword ptr [rax+rax+00h]
0x180018c3a  mov     cs:hModule, rax
0x180018c41  test    rax, rax
0x180018c44  jnz     short loc_180018CA2
0x180018c46  call    cs:__imp_GetLastError
0x180018c4d  nop     dword ptr [rax+rax+00h]
0x180018c52  mov     ebx, eax
0x180018c54  add     eax, 0FFFFFF41h
0x180018c59  cmp     eax, 2
0x180018c5c  jbe     short loc_180018C79
0x180018c5e  cmp     cs:dword_1800CF4E4, r15d
0x180018c65  jbe     loc_180018D2D
0x180018c6b  mov     [rsp+58h+dwErrorIndex], r15d
0x180018c70  mov     [rsp+58h+dwErrorCode], ebx
0x180018c74  jmp     loc_180018D0A
0x180018c79  cmp     cs:dword_1800CF4E4, r15d
0x180018c80  jbe     loc_180018D2D
0x180018c86  lea     rax, [rbp+lpLibFileName]
0x180018c8a  mov     [rsp+58h+dwErrorCode], r15d
0x180018c8f  mov     [rsp+58h+plpszSubStringArray], rax
0x180018c94  mov     r9d, edi
0x180018c97  mov     r8d, 4EEBh
0x180018c9d  jmp     loc_180018B74
0x180018ca2  lea     rdx, aRassecuritydia_0; "RasSecurityDialogBegin"
0x180018ca9  mov     rcx, rax; hModule
0x180018cac  call    cs:__imp_GetProcAddress
0x180018cb3  nop     dword ptr [rax+rax+00h]
0x180018cb8  mov     cs:qword_1800CF5E0, rax
0x180018cbf  test    rax, rax
0x180018cc2  jz      short loc_180018CEA
0x180018cc4  mov     rcx, cs:hModule; hModule
0x180018ccb  lea     rdx, aRassecuritydia; "RasSecurityDialogEnd"
0x180018cd2  call    cs:__imp_GetProcAddress
0x180018cd9  nop     dword ptr [rax+rax+00h]
0x180018cde  mov     cs:qword_1800CF5E8, rax
0x180018ce5  test    rax, rax
0x180018ce8  jnz     short loc_180018D2D
0x180018cea  call    cs:__imp_GetLastError
0x180018cf1  nop     dword ptr [rax+rax+00h]
0x180018cf6  cmp     cs:dword_1800CF4E4, r15d
0x180018cfd  mov     ebx, eax
0x180018cff  jbe     short loc_180018D2D
0x180018d01  mov     [rsp+58h+dwErrorIndex], r15d; dwErrorIndex
0x180018d06  mov     [rsp+58h+dwErrorCode], eax; dwErrorCode
0x180018d0a  mov     rcx, cs:hLogHandle; hLogHandle
0x180018d11  xor     r9d, r9d; dwSubStringCount
0x180018d14  mov     r8d, 4E7Ch; dwMessageId
0x180018d1a  mov     [rsp+58h+plpszSubStringArray], r15; plpszSubStringArray
0x180018d1f  mov     edx, edi; dwEventType
0x180018d21  call    cs:__imp_RouterLogEventStringW
0x180018d28  nop     dword ptr [rax+rax+00h]
0x180018d2d  mov     rcx, cs:hHeap; hHeap
0x180018d34  mov     r8, rsi; lpMem
0x180018d37  xor     edx, edx; dwFlags
0x180018d39  call    cs:__imp_HeapFree
0x180018d40  nop     dword ptr [rax+rax+00h]
0x180018d45  mov     r8, [rbp+lpLibFileName]; lpMem
0x180018d49  test    r8, r8
0x180018d4c  jz      short loc_180018D63
0x180018d4e  mov     rcx, cs:hHeap; hHeap
0x180018d55  xor     edx, edx; dwFlags
0x180018d57  call    cs:__imp_HeapFree
0x180018d5e  nop     dword ptr [rax+rax+00h]
0x180018d63  mov     rcx, [rbp+phkResult]; hKey
0x180018d67  call    cs:__imp_RegCloseKey
0x180018d6e  nop     dword ptr [rax+rax+00h]
0x180018d73  mov     eax, ebx
0x180018d75  add     rsp, 58h
0x180018d79  pop     r15
0x180018d7b  pop     r14
0x180018d7d  pop     rdi
0x180018d7e  pop     rsi
0x180018d7f  pop     rbx
0x180018d80  pop     rbp
0x180018d81  retn
```
