# pSetupGetPolicyListStrings

- ea: `0x180003cf8`
- end: `0x1800040d0`
- name: `pSetupGetPolicyListStrings`
- size: `984`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, const WCHAR *, wchar_t **)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800086bc`
- `0x1800087c4`
- `0x18000892c`
- `0x180008bc0`

## callees

- `0x180003820`
- `0x180003b40`
- `0x180003cf8`
- `0x1800040d8`
- `0x18000a1a0`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeString` at `0x180003f64`
- `ntdll!RtlUpcaseUnicodeString` at `0x180003f64`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003f2c`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003f2c`
- `ntdll!NtQueryKey` at `0x180003e1f`
- `ntdll!NtQueryKey` at `0x180003e1f`
- `ntdll!NtClose` at `0x180004080`
- `ntdll!NtClose` at `0x180004091`
- `ntdll!NtClose` at `0x1800040a2`
- `ntdll!NtClose` at `0x180004080`
- `ntdll!NtClose` at `0x180004091`
- `ntdll!NtClose` at `0x1800040a2`
- `ntdll!RtlNtStatusToDosError` at `0x180003e2b`
- `ntdll!RtlNtStatusToDosError` at `0x180003ff6`
- `ntdll!RtlNtStatusToDosError` at `0x180003e2b`
- `ntdll!RtlNtStatusToDosError` at `0x180003ff6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180003ef0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180003fde`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180003ef0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180003fde`
- `KERNEL32!HeapFree` at `0x180004068`
- `KERNEL32!HeapFree` at `0x180004068`
- `KERNEL32!HeapReAlloc` at `0x180003e8e`
- `KERNEL32!HeapReAlloc` at `0x180003e8e`
- `KERNEL32!HeapAlloc` at `0x180003e83`
- `KERNEL32!HeapAlloc` at `0x180003e83`

## pseudocode

```c
__int64 __fastcall pSetupGetPolicyListStrings(__int64 a1, const WCHAR *a2, __int64 a3, const WCHAR *a4, wchar_t **a5)
{
  __int64 v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  wchar_t *v16; // rdi
  wchar_t *v17; // r14
  wchar_t *v18; // rax
  unsigned int v19; // esi
  unsigned int v20; // r14d
  LSTATUS v21; // eax
  int inited; // eax
  __int64 v23; // r15
  STRSAFE_LPWSTR *v24; // r9
  wchar_t **v25; // rax
  size_t *ResultLength; // [rsp+20h] [rbp-E0h]
  unsigned int cchDest; // [rsp+40h] [rbp-C0h]
  DWORD cchDest_4; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwIndex; // [rsp+4Ch] [rbp-B4h]
  HANDLE KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v35; // [rsp+68h] [rbp-98h] BYREF
  ULONG v36; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  wchar_t **v39; // [rsp+90h] [rbp-70h]
  __int128 KeyInformation; // [rsp+98h] [rbp-68h] BYREF
  __int128 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B8h] [rbp-48h]
  WCHAR ValueName[16]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Data[259]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v45; // [rsp+2E6h] [rbp+1E6h]

  v39 = a5;
  v35 = 0;
  Handle = 0;
  KeyHandle = 0;
  cchDest_4 = 0;
  cchValueName = 0;
  Type = 0;
  DestinationString = 0;
  *a5 = 0;
  if ( (unsigned int)pSetupGetPolicyValue(a1, a2, a3, a4, 0, 1) )
  {
    v8 = pSetupOpenKey((void *)0xFFFFFFFF80000002LL, a2, v7, 1u, &v35);
    if ( !v8 )
    {
      v8 = pSetupOpenKey(v35, L"Restrictions", v9, 1u, &Handle);
      if ( !v8 )
      {
        v8 = pSetupOpenKey(Handle, a4, v10, 1u, &KeyHandle);
        if ( v8 )
          goto LABEL_39;
        v36 = 0;
        v42 = 0;
        KeyInformation = 0;
        v41 = 0;
        v11 = NtQueryKey((HANDLE)(unsigned int)KeyHandle, KeyCachedInformation, &KeyInformation, 0x28u, &v36);
        if ( v11 >= 0 )
        {
          v13 = DWORD1(v41);
          v12 = HIDWORD(v41);
        }
        else
        {
          v8 = RtlNtStatusToDosError(v11);
          if ( v8 )
            goto LABEL_39;
          v12 = 0;
          v13 = 0;
        }
        v14 = v12 * v13;
        if ( v14 > 0xFFFFFFFF || (LODWORD(v15) = v14 + 2, (int)v14 + 2 < (unsigned int)v14) )
        {
          v8 = 13;
          goto LABEL_39;
        }
        v16 = 0;
        v8 = 0;
LABEL_13:
        v17 = v16;
        if ( v16 )
          v18 = (wchar_t *)HeapReAlloc(hHeap, 0, v16, (unsigned int)v15);
        else
          v18 = (wchar_t *)HeapAlloc(hHeap, 0, (unsigned int)v15);
        v16 = v18;
        if ( v18 )
        {
          pszDest = v18;
          v19 = (unsigned int)v15 >> 1;
          cchDest = v19;
          v20 = 0;
          cchValueName = 11;
          cchDest_4 = 520;
          v21 = RegEnumValueW((HKEY)KeyHandle, 0, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cchDest_4);
          dwIndex = 1;
          if ( v21 == 259 )
          {
LABEL_34:
            v8 = 2;
            goto LABEL_37;
          }
          while ( 1 )
          {
            if ( v21 != 234 )
            {
              if ( v21 )
              {
                v8 = v21;
                goto LABEL_37;
              }
              v45 = 0;
              inited = RtlInitUnicodeStringEx(&DestinationString, Data);
              if ( inited < 0 )
              {
                v8 = RtlNtStatusToDosError(inited);
                if ( v8 )
                  goto LABEL_37;
LABEL_27:
                if ( !v20 )
                  goto LABEL_34;
                if ( v19 >= v20 + 1 )
                {
                  v25 = v39;
                  v16[v20] = 0;
                  *v25 = v16;
                }
                else
                {
                  v15 = 2LL * (v20 + 1);
                  if ( v15 <= 0xFFFFFFFF )
                    goto LABEL_13;
                  v8 = 13;
LABEL_37:
                  HeapFree(hHeap, 0, v16);
                }
                goto LABEL_39;
              }
              v23 = DestinationString.MaximumLength >> 1;
              if ( (unsigned int)v23 + v20 < v20 )
              {
                v8 = 13;
                goto LABEL_37;
              }
              v20 += v23;
              if ( cchDest > (unsigned int)v23 )
              {
                RtlUpcaseUnicodeString(&DestinationString, &DestinationString, 0);
                StringCchCopyExW(pszDest, cchDest, Data, v24, ResultLength, 0x900u);
                cchDest -= v23;
                pszDest += v23;
              }
            }
            cchValueName = 11;
            cchDest_4 = 520;
            v21 = RegEnumValueW((HKEY)KeyHandle, dwIndex, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cchDest_4);
            if ( v21 == 259 )
              goto LABEL_27;
            ++dwIndex;
          }
        }
        v8 = 8;
        if ( v17 )
        {
          v16 = v17;
          goto LABEL_37;
        }
LABEL_39:
        if ( KeyHandle )
          NtClose((HANDLE)(unsigned int)KeyHandle);
      }
      if ( Handle )
        NtClose((HANDLE)(unsigned int)Handle);
    }
    if ( v35 )
      NtClose((HANDLE)(unsigned int)v35);
  }
  else
  {
    return 2;
  }
  return v8;
}

```

## disassembly

```asm
0x180003cf8  mov     [rsp-8+arg_0], rbx
0x180003cfd  push    rbp
0x180003cfe  push    rsi
0x180003cff  push    rdi
0x180003d00  push    r14
0x180003d02  push    r15
0x180003d04  lea     rbp, [rsp-200h]
0x180003d0c  sub     rsp, 300h
0x180003d13  mov     rax, cs:__security_cookie
0x180003d1a  xor     rax, rsp
0x180003d1d  mov     [rbp+220h+var_30], rax
0x180003d24  mov     rax, [rbp+220h+arg_20]
0x180003d2b  xor     r15d, r15d
0x180003d2e  xorps   xmm0, xmm0
0x180003d31  mov     [rbp+220h+var_290], rax
0x180003d35  mov     rdi, r9
0x180003d38  mov     [rsp+320h+var_2B8], r15
0x180003d3d  mov     rbx, rdx
0x180003d40  mov     [rsp+320h+Handle], r15
0x180003d45  lea     esi, [r15+1]
0x180003d49  mov     [rsp+320h+KeyHandle], r15
0x180003d4e  mov     dword ptr [rsp+320h+lpType], esi
0x180003d52  mov     dword ptr [rsp+320h+ResultLength], r15d
0x180003d57  mov     dword ptr [rsp+320h+cchDest+4], r15d
0x180003d5c  mov     [rsp+320h+cchValueName], r15d
0x180003d61  mov     [rsp+320h+Type], r15d
0x180003d66  movups  xmmword ptr [rbp+220h+DestinationString.Length], xmm0
0x180003d6a  mov     [rax], r15
0x180003d6d  call    pSetupGetPolicyValue
0x180003d72  test    eax, eax
0x180003d74  jnz     short loc_180003D7E
0x180003d76  lea     ebx, [rsi+1]
0x180003d79  jmp     loc_1800040A8
0x180003d7e  lea     rax, [rsp+320h+var_2B8]
0x180003d83  mov     r9d, esi
0x180003d86  mov     rdx, rbx
0x180003d89  mov     [rsp+320h+ResultLength], rax
0x180003d8e  mov     rcx, 0FFFFFFFF80000002h
0x180003d95  call    pSetupOpenKey
0x180003d9a  mov     ebx, eax
0x180003d9c  test    eax, eax
0x180003d9e  jnz     loc_180004097
0x180003da4  mov     rcx, [rsp+320h+var_2B8]
0x180003da9  lea     rax, [rsp+320h+Handle]
0x180003dae  mov     r9d, esi
0x180003db1  mov     [rsp+320h+ResultLength], rax
0x180003db6  lea     rdx, aRestrictions; "Restrictions"
0x180003dbd  call    pSetupOpenKey
0x180003dc2  mov     ebx, eax
0x180003dc4  test    eax, eax
0x180003dc6  jnz     loc_180004086
0x180003dcc  mov     rcx, [rsp+320h+Handle]
0x180003dd1  lea     rax, [rsp+320h+KeyHandle]
0x180003dd6  mov     r9d, esi
0x180003dd9  mov     [rsp+320h+ResultLength], rax
0x180003dde  mov     rdx, rdi
0x180003de1  call    pSetupOpenKey
0x180003de6  mov     ebx, eax
0x180003de8  test    eax, eax
0x180003dea  jnz     loc_180004075
0x180003df0  mov     ecx, dword ptr [rsp+320h+KeyHandle]; KeyHandle
0x180003df4  lea     r9d, [rbx+28h]; Length
0x180003df8  xor     eax, eax
0x180003dfa  mov     [rsp+320h+var_2B0], r15d
0x180003dff  xorps   xmm0, xmm0
0x180003e02  mov     [rbp+220h+var_268], rax
0x180003e06  lea     rax, [rsp+320h+var_2B0]
0x180003e0b  lea     r8, [rbp+220h+KeyInformation]; KeyInformation
0x180003e0f  mov     [rsp+320h+ResultLength], rax; ResultLength
0x180003e14  lea     edx, [rbx+4]; KeyInformationClass
0x180003e17  movups  [rbp+220h+KeyInformation], xmm0
0x180003e1b  movups  [rbp+220h+var_278], xmm0
0x180003e1f  call    cs:__imp_NtQueryKey
0x180003e25  test    eax, eax
0x180003e27  jns     short loc_180003E43
0x180003e29  mov     ecx, eax; Status
0x180003e2b  call    cs:__imp_RtlNtStatusToDosError
0x180003e31  mov     ebx, eax
0x180003e33  test    eax, eax
0x180003e35  jnz     loc_180004075
0x180003e3b  mov     eax, r15d
0x180003e3e  mov     ecx, r15d
0x180003e41  jmp     short loc_180003E49
0x180003e43  mov     ecx, dword ptr [rbp+220h+var_278+4]
0x180003e46  mov     eax, dword ptr [rbp+220h+var_278+0Ch]
0x180003e49  imul    rcx, rax
0x180003e4d  mov     eax, 0FFFFFFFFh
0x180003e52  cmp     rcx, rax
0x180003e55  ja      loc_180004070
0x180003e5b  lea     esi, [rcx+2]
0x180003e5e  cmp     esi, ecx
0x180003e60  jb      loc_180004070
0x180003e66  mov     rdi, r15
0x180003e69  mov     ebx, r15d
0x180003e6c  mov     rcx, cs:hHeap; hHeap
0x180003e73  xor     edx, edx; dwFlags
0x180003e75  mov     r9d, esi; dwBytes
0x180003e78  mov     r14, rdi
0x180003e7b  test    rdi, rdi
0x180003e7e  jnz     short loc_180003E8B
0x180003e80  mov     r8d, r9d; dwBytes
0x180003e83  call    cs:__imp_HeapAlloc
0x180003e89  jmp     short loc_180003E94
0x180003e8b  mov     r8, rdi; lpMem
0x180003e8e  call    cs:__imp_HeapReAlloc
0x180003e94  mov     rdi, rax
0x180003e97  test    rax, rax
0x180003e9a  jz      loc_18000404F
0x180003ea0  mov     rcx, [rsp+320h+KeyHandle]; hKey
0x180003ea5  lea     r9, [rsp+320h+cchValueName]; lpcchValueName
0x180003eaa  mov     [rsp+320h+pszDest], rax
0x180003eaf  lea     r8, [rbp+220h+ValueName]; lpValueName
0x180003eb3  lea     rax, [rsp+320h+cchDest+4]
0x180003eb8  shr     esi, 1
0x180003eba  mov     [rsp+320h+lpcbData], rax; lpcbData
0x180003ebf  xor     edx, edx; dwIndex
0x180003ec1  lea     rax, [rbp+220h+Data]
0x180003ec5  mov     dword ptr [rsp+320h+cchDest], esi
0x180003ec9  mov     [rsp+320h+lpData], rax; lpData
0x180003ece  mov     r14d, r15d
0x180003ed1  lea     rax, [rsp+320h+Type]
0x180003ed6  mov     [rsp+320h+cchValueName], 0Bh
0x180003ede  mov     [rsp+320h+lpType], rax; lpType
0x180003ee3  mov     [rsp+320h+ResultLength], r15; pcchRemaining
0x180003ee8  mov     dword ptr [rsp+320h+cchDest+4], 208h
0x180003ef0  call    cs:__imp_RegEnumValueW
0x180003ef6  mov     [rsp+320h+dwIndex], 1
0x180003efe  cmp     eax, 103h
0x180003f03  jz      loc_180004048
0x180003f09  cmp     eax, 0EAh
0x180003f0e  jz      loc_180003F9A
0x180003f14  test    eax, eax
0x180003f16  jnz     loc_180004033
0x180003f1c  lea     rdx, [rbp+220h+Data]; SourceString
0x180003f20  mov     [rbp+220h+var_3A], r15w
0x180003f28  lea     rcx, [rbp+220h+DestinationString]; DestinationString
0x180003f2c  call    cs:__imp_RtlInitUnicodeStringEx
0x180003f32  test    eax, eax
0x180003f34  js      loc_180003FF4
0x180003f3a  movzx   r15d, [rbp+220h+DestinationString.MaximumLength]
0x180003f3f  shr     r15d, 1
0x180003f42  lea     eax, [r15+r14]
0x180003f46  cmp     eax, r14d
0x180003f49  jb      loc_180004029
0x180003f4f  mov     r14d, eax
0x180003f52  cmp     dword ptr [rsp+320h+cchDest], r15d
0x180003f57  jbe     short loc_180003F97
0x180003f59  xor     r8d, r8d; AllocateDestinationString
0x180003f5c  lea     rdx, [rbp+220h+DestinationString]; SourceString
0x180003f60  lea     rcx, [rbp+220h+DestinationString]; DestinationString
0x180003f64  call    cs:__imp_RtlUpcaseUnicodeString
0x180003f6a  mov     edx, dword ptr [rsp+320h+cchDest]; cchDest
0x180003f6e  lea     r8, [rbp+220h+Data]; pszSrc
0x180003f72  mov     rcx, [rsp+320h+pszDest]; pszDest
0x180003f77  mov     dword ptr [rsp+320h+lpType], 900h; dwFlags
0x180003f7f  call    StringCchCopyExW
0x180003f84  mov     rcx, [rsp+320h+pszDest]
0x180003f89  sub     dword ptr [rsp+320h+cchDest], r15d
0x180003f8e  lea     rcx, [rcx+r15*2]
0x180003f92  mov     [rsp+320h+pszDest], rcx
0x180003f97  xor     r15d, r15d
0x180003f9a  mov     edx, [rsp+320h+dwIndex]; dwIndex
0x180003f9e  lea     rax, [rsp+320h+cchDest+4]
0x180003fa3  mov     rcx, [rsp+320h+KeyHandle]; hKey
0x180003fa8  lea     r9, [rsp+320h+cchValueName]; lpcchValueName
0x180003fad  mov     [rsp+320h+lpcbData], rax; lpcbData
0x180003fb2  lea     r8, [rbp+220h+ValueName]; lpValueName
0x180003fb6  lea     rax, [rbp+220h+Data]
0x180003fba  mov     [rsp+320h+cchValueName], 0Bh
0x180003fc2  mov     [rsp+320h+lpData], rax; lpData
0x180003fc7  lea     rax, [rsp+320h+Type]
0x180003fcc  mov     [rsp+320h+lpType], rax; lpType
0x180003fd1  mov     [rsp+320h+ResultLength], r15; lpReserved
0x180003fd6  mov     dword ptr [rsp+320h+cchDest+4], 208h
0x180003fde  call    cs:__imp_RegEnumValueW
0x180003fe4  cmp     eax, 103h
0x180003fe9  jz      short loc_180004002
0x180003feb  inc     [rsp+320h+dwIndex]
0x180003fef  jmp     loc_180003F09
0x180003ff4  mov     ecx, eax; Status
0x180003ff6  call    cs:__imp_RtlNtStatusToDosError
0x180003ffc  mov     ebx, eax
0x180003ffe  test    eax, eax
0x180004000  jnz     short loc_18000405C
0x180004002  test    r14d, r14d
0x180004005  jz      short loc_180004048
0x180004007  lea     eax, [r14+1]
0x18000400b  cmp     esi, eax
0x18000400d  jnb     short loc_180004037
0x18000400f  mov     esi, eax
0x180004011  mov     eax, 0FFFFFFFFh
0x180004016  add     rsi, rsi
0x180004019  cmp     rsi, rax
0x18000401c  jbe     loc_180003E6C
0x180004022  mov     ebx, 0Dh
0x180004027  jmp     short loc_18000405C
0x180004029  mov     ebx, 0Dh
0x18000402e  xor     r15d, r15d
0x180004031  jmp     short loc_18000405C
0x180004033  mov     ebx, eax
0x180004035  jmp     short loc_18000405C
0x180004037  mov     rax, [rbp+220h+var_290]
0x18000403b  mov     ecx, r14d
0x18000403e  mov     [rdi+rcx*2], r15w
0x180004043  mov     [rax], rdi
0x180004046  jmp     short loc_180004075
0x180004048  mov     ebx, 2
0x18000404d  jmp     short loc_18000405C
0x18000404f  mov     ebx, 8
0x180004054  test    r14, r14
0x180004057  jz      short loc_180004075
0x180004059  mov     rdi, r14
0x18000405c  mov     rcx, cs:hHeap; hHeap
0x180004063  mov     r8, rdi; lpMem
0x180004066  xor     edx, edx; dwFlags
0x180004068  call    cs:__imp_HeapFree
0x18000406e  jmp     short loc_180004075
0x180004070  mov     ebx, 0Dh
0x180004075  cmp     [rsp+320h+KeyHandle], r15
0x18000407a  jz      short loc_180004086
0x18000407c  mov     ecx, dword ptr [rsp+320h+KeyHandle]; Handle
0x180004080  call    cs:__imp_NtClose
0x180004086  cmp     [rsp+320h+Handle], r15
0x18000408b  jz      short loc_180004097
0x18000408d  mov     ecx, dword ptr [rsp+320h+Handle]; Handle
0x180004091  call    cs:__imp_NtClose
0x180004097  cmp     [rsp+320h+var_2B8], r15
0x18000409c  jz      short loc_1800040A8
0x18000409e  mov     ecx, dword ptr [rsp+320h+var_2B8]; Handle
0x1800040a2  call    cs:__imp_NtClose
0x1800040a8  mov     eax, ebx
0x1800040aa  mov     rcx, [rbp+220h+var_30]
0x1800040b1  xor     rcx, rsp; StackCookie
0x1800040b4  call    __security_check_cookie
0x1800040b9  mov     rbx, [rsp+320h+arg_0]
0x1800040c1  add     rsp, 300h
0x1800040c8  pop     r15
0x1800040ca  pop     r14
0x1800040cc  pop     rdi
0x1800040cd  pop     rsi
0x1800040ce  pop     rbp
0x1800040cf  retn
```
