# AppendType

- ea: `0x18003f72c`
- end: `0x18003faf7`
- name: `AppendType`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180038cb0`

## callees

- `0x180012dbc`
- `0x180034148`
- `0x18003f72c`
- `0x18004b630`
- `0x180082084`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f8b4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f8f1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f8b4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f8f1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f888`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003fa98`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f888`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003fa98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fac2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fac2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f82c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f82c`
- `WS2_32!GetAddrInfoW` at `0x18003f922`
- `WS2_32!GetAddrInfoW` at `0x18003f946`
- `WS2_32!GetAddrInfoW` at `0x18003f922`
- `WS2_32!GetAddrInfoW` at `0x18003f946`
- `WS2_32!FreeAddrInfoW` at `0x18003fa2e`
- `WS2_32!FreeAddrInfoW` at `0x18003fa3f`
- `WS2_32!FreeAddrInfoW` at `0x18003fa2e`
- `WS2_32!FreeAddrInfoW` at `0x18003fa3f`

## pseudocode

```c
LSTATUS __fastcall AppendType(__int64 a1, HKEY a2, int a3)
{
  const WCHAR *v5; // rdx
  LSTATUS result; // eax
  int v7; // r14d
  wchar_t *v8; // rax
  WCHAR *v9; // rdi
  bool v10; // zf
  WCHAR *v11; // rbx
  wchar_t *v12; // rax
  const WCHAR *v13; // rax
  struct addrinfoW *v14; // rcx
  struct sockaddr *ai_addr; // rcx
  const IN6_ADDR *v16; // rcx
  __int64 v17; // rbx
  __int64 *v18; // rax
  PADDRINFOW v19; // rdx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  PADDRINFOW ppResult; // [rsp+50h] [rbp-B0h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  ADDRINFOW v27; // [rsp+70h] [rbp-90h] BYREF
  ADDRINFOW pHints; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[256]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Data[256]; // [rsp+2D0h] [rbp+1D0h] BYREF

  pAddrInfo = 0;
  ppResult = 0;
  memset(&v27, 0, sizeof(v27));
  cchValueName = 0;
  Type = 0;
  cbData = 0;
  memset(&pHints, 0, sizeof(pHints));
  v27.ai_family = PpTypeInfo[2 * a3];
  v5 = (const WCHAR *)PpTypeInfo[2 * a3 + 1];
  pHints.ai_family = HIDWORD(PpTypeInfo[2 * a3]);
  hKey = 0;
  phkResult = 0;
  v27.ai_socktype = 1;
  v27.ai_flags = 1;
  pHints.ai_socktype = 1;
  result = RegOpenKeyExW(a2, v5, 0, 1u, &hKey);
  if ( !result )
  {
    if ( !RegOpenKeyExW(hKey, L"tcp", 0, 1u, &phkResult) )
    {
      cchValueName = 256;
      cbData = 512;
      v7 = 0;
      if ( !RegEnumValueW(phkResult, 0, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
      {
        while ( 1 )
        {
          if ( Type != 1 )
            goto LABEL_28;
          v8 = wcschr(ValueName, 0x2Fu);
          if ( v8 )
          {
            v9 = ValueName;
            v10 = ValueName[0] == 42;
            *v8 = 0;
            if ( v10 )
              v9 = 0;
            v11 = v8 + 1;
          }
          else
          {
            v9 = 0;
            v11 = ValueName;
          }
          v12 = wcschr(Data, 0x2Fu);
          if ( v12 )
          {
            *v12 = 0;
            v13 = v12 + 1;
          }
          else
          {
            v13 = v11;
          }
          if ( GetAddrInfoW(Data, v13, &pHints, &ppResult) )
            goto LABEL_28;
          if ( !GetAddrInfoW(v9, v11, &v27, &pAddrInfo) )
            break;
          v14 = ppResult;
LABEL_27:
          FreeAddrInfoW(v14);
LABEL_28:
          cchValueName = 256;
          cbData = 512;
          if ( RegEnumValueW(phkResult, ++v7, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
            goto LABEL_29;
        }
        ai_addr = ppResult->ai_addr;
        if ( ai_addr->sa_family == 23 )
        {
          v16 = (const IN6_ADDR *)&ai_addr->sa_data[6];
          if ( v16->u.Byte[0] == 0xFF || IN6_IS_ADDR_UNSPECIFIED(v16) )
          {
LABEL_26:
            FreeAddrInfoW(ppResult);
            v14 = pAddrInfo;
            goto LABEL_27;
          }
        }
        else if ( ai_addr->sa_family != 2
               || (ai_addr->sa_data[2] & 0xF0) == 0xE0
               || (unsigned int)(*(_DWORD *)&ai_addr->sa_data[2] - 1) > 0xFFFFFFFD )
        {
          goto LABEL_26;
        }
        v17 = MALLOC(0x200u);
        if ( v17 )
        {
          v18 = *(__int64 **)(a1 + 8);
          if ( *v18 != a1 )
            __fastfail(3u);
          *(_QWORD *)v17 = a1;
          *(_QWORD *)(v17 + 8) = v18;
          *v18 = v17;
          v19 = ppResult;
          *(_QWORD *)(a1 + 8) = v17;
          memcpy_0((void *)(v17 + 320), v19->ai_addr, v19->ai_addrlen);
          *(_DWORD *)(v17 + 448) = ppResult->ai_addrlen;
          memcpy_0((void *)(v17 + 184), pAddrInfo->ai_addr, pAddrInfo->ai_addrlen);
          *(_DWORD *)(v17 + 312) = pAddrInfo->ai_addrlen;
        }
        goto LABEL_26;
      }
LABEL_29:
      RegCloseKey(phkResult);
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18003f72c  push    rbp
0x18003f72e  push    rbx
0x18003f72f  push    rsi
0x18003f730  push    rdi
0x18003f731  push    r12
0x18003f733  push    r13
0x18003f735  push    r14
0x18003f737  lea     rbp, [rsp-3E0h]
0x18003f73f  sub     rsp, 4E0h
0x18003f746  mov     rax, cs:__security_cookie
0x18003f74d  xor     rax, rsp
0x18003f750  mov     [rbp+410h+var_40], rax
0x18003f757  xorps   xmm0, xmm0
0x18003f75a  mov     [rsp+510h+pAddrInfo], 0
0x18003f763  mov     r10, rdx
0x18003f766  mov     [rsp+510h+ppResult], 0
0x18003f76f  movups  xmmword ptr [rsp+510h+var_4A0.ai_flags], xmm0
0x18003f774  mov     r13d, 1
0x18003f77a  movsxd  rdx, r8d
0x18003f77d  add     rdx, rdx
0x18003f780  mov     [rsp+510h+cchValueName], 0
0x18003f788  mov     rsi, rcx
0x18003f78b  mov     [rsp+510h+Type], 0
0x18003f793  lea     rcx, PpTypeInfo
0x18003f79a  mov     [rsp+510h+cbData], 0
0x18003f7a2  movups  xmmword ptr [rbp+410h+pHints.ai_flags], xmm0
0x18003f7a6  mov     eax, [rcx+rdx*8]
0x18003f7a9  mov     r9d, r13d; samDesired
0x18003f7ac  mov     [rsp+510h+var_4A0.ai_family], eax
0x18003f7b0  xor     r8d, r8d; ulOptions
0x18003f7b3  mov     eax, [rcx+rdx*8+4]
0x18003f7b7  mov     rdx, [rcx+rdx*8+8]; lpSubKey
0x18003f7bc  mov     rcx, r10; hKey
0x18003f7bf  mov     [rbp+410h+pHints.ai_family], eax
0x18003f7c2  lea     rax, [rsp+510h+hKey]
0x18003f7c7  mov     [rsp+510h+phkResult], rax; phkResult
0x18003f7cc  mov     [rsp+510h+hKey], 0
0x18003f7d5  mov     [rsp+510h+var_4B0], 0
0x18003f7de  movups  xmmword ptr [rbp+410h+var_4A0.ai_addrlen], xmm0
0x18003f7e2  mov     [rsp+510h+var_4A0.ai_socktype], r13d
0x18003f7e7  movups  xmmword ptr [rbp+410h+var_4A0.ai_addr], xmm0
0x18003f7eb  mov     [rsp+510h+var_4A0.ai_flags], r13d
0x18003f7f0  movups  xmmword ptr [rbp+410h+pHints.ai_addrlen], xmm0
0x18003f7f4  mov     [rbp+410h+pHints.ai_socktype], r13d
0x18003f7f8  movups  xmmword ptr [rbp+410h+pHints.ai_addr], xmm0
0x18003f7fc  call    cs:__imp_RegOpenKeyExW
0x18003f803  nop     dword ptr [rax+rax+00h]
0x18003f808  test    eax, eax
0x18003f80a  jnz     loc_18003FACE
0x18003f810  mov     rcx, [rsp+510h+hKey]; hKey
0x18003f815  lea     rax, [rsp+510h+var_4B0]
0x18003f81a  mov     r9d, r13d; samDesired
0x18003f81d  mov     [rsp+510h+phkResult], rax; phkResult
0x18003f822  xor     r8d, r8d; ulOptions
0x18003f825  lea     rdx, aTcp; "tcp"
0x18003f82c  call    cs:__imp_RegOpenKeyExW
0x18003f833  nop     dword ptr [rax+rax+00h]
0x18003f838  test    eax, eax
0x18003f83a  jnz     loc_18003FABD
0x18003f840  mov     rcx, [rsp+510h+var_4B0]; hKey
0x18003f845  lea     rax, [rsp+510h+cbData]
0x18003f84a  mov     [rsp+510h+lpcbData], rax; lpcbData
0x18003f84f  lea     r9, [rsp+510h+cchValueName]; lpcchValueName
0x18003f854  lea     rax, [rbp+410h+Data]
0x18003f85b  mov     [rsp+510h+cchValueName], 100h
0x18003f863  mov     [rsp+510h+lpData], rax; lpData
0x18003f868  lea     r8, [rbp+410h+ValueName]; lpValueName
0x18003f86c  lea     rax, [rsp+510h+Type]
0x18003f871  mov     [rsp+510h+cbData], 200h
0x18003f879  mov     [rsp+510h+lpType], rax; lpType
0x18003f87e  xor     r14d, r14d
0x18003f881  xor     edx, edx; dwIndex
0x18003f883  mov     [rsp+510h+phkResult], r14; lpReserved
0x18003f888  call    cs:__imp_RegEnumValueW
0x18003f88f  nop     dword ptr [rax+rax+00h]
0x18003f894  test    eax, eax
0x18003f896  jnz     loc_18003FAAC
0x18003f89c  lea     r12d, [r13+1]
0x18003f8a0  cmp     [rsp+510h+Type], r13d
0x18003f8a5  jnz     loc_18003FA4B
0x18003f8ab  mov     edx, 2Fh ; '/'; Ch
0x18003f8b0  lea     rcx, [rbp+410h+ValueName]; Str
0x18003f8b4  call    cs:__imp_wcschr
0x18003f8bb  nop     dword ptr [rax+rax+00h]
0x18003f8c0  mov     rbx, rax
0x18003f8c3  test    rax, rax
0x18003f8c6  jz      short loc_18003F8DF
0x18003f8c8  xor     ecx, ecx
0x18003f8ca  lea     rdi, [rbp+410h+ValueName]
0x18003f8ce  cmp     [rbp+410h+ValueName], 2Ah ; '*'
0x18003f8d3  mov     [rax], cx
0x18003f8d6  cmovz   rdi, rcx
0x18003f8da  add     rbx, r12
0x18003f8dd  jmp     short loc_18003F8E5
0x18003f8df  xor     edi, edi
0x18003f8e1  lea     rbx, [rbp+410h+ValueName]
0x18003f8e5  mov     edx, 2Fh ; '/'; Ch
0x18003f8ea  lea     rcx, [rbp+410h+Data]; Str
0x18003f8f1  call    cs:__imp_wcschr
0x18003f8f8  nop     dword ptr [rax+rax+00h]
0x18003f8fd  test    rax, rax
0x18003f900  jz      short loc_18003F90C
0x18003f902  xor     ecx, ecx
0x18003f904  mov     [rax], cx
0x18003f907  add     rax, r12
0x18003f90a  jmp     short loc_18003F90F
0x18003f90c  mov     rax, rbx
0x18003f90f  lea     r9, [rsp+510h+ppResult]; ppResult
0x18003f914  mov     rdx, rax; pServiceName
0x18003f917  lea     r8, [rbp+410h+pHints]; pHints
0x18003f91b  lea     rcx, [rbp+410h+Data]; pNodeName
0x18003f922  call    cs:__imp_GetAddrInfoW
0x18003f929  nop     dword ptr [rax+rax+00h]
0x18003f92e  test    eax, eax
0x18003f930  jnz     loc_18003FA4B
0x18003f936  lea     r9, [rsp+510h+pAddrInfo]; ppResult
0x18003f93b  mov     rdx, rbx; pServiceName
0x18003f93e  lea     r8, [rsp+510h+var_4A0]; pHints
0x18003f943  mov     rcx, rdi; pNodeName
0x18003f946  call    cs:__imp_GetAddrInfoW
0x18003f94d  nop     dword ptr [rax+rax+00h]
0x18003f952  test    eax, eax
0x18003f954  jz      short loc_18003F960
0x18003f956  mov     rcx, [rsp+510h+ppResult]
0x18003f95b  jmp     loc_18003FA3F
0x18003f960  mov     rax, [rsp+510h+ppResult]
0x18003f965  mov     rcx, [rax+20h]
0x18003f969  cmp     word ptr [rcx], 17h
0x18003f96d  jnz     short loc_18003F98A
0x18003f96f  add     rcx, 8; a
0x18003f973  cmp     byte ptr [rcx], 0FFh
0x18003f976  jz      loc_18003FA29
0x18003f97c  call    IN6_IS_ADDR_UNSPECIFIED
0x18003f981  test    al, al
0x18003f983  jz      short loc_18003F9AE
0x18003f985  jmp     loc_18003FA29
0x18003f98a  cmp     [rcx], r12w
0x18003f98e  jnz     loc_18003FA29
0x18003f994  mov     edx, [rcx+4]
0x18003f997  mov     eax, edx
0x18003f999  and     eax, 0F0h
0x18003f99e  cmp     al, 0E0h
0x18003f9a0  jz      loc_18003FA29
0x18003f9a6  lea     eax, [rdx-1]
0x18003f9a9  cmp     eax, 0FFFFFFFDh
0x18003f9ac  ja      short loc_18003FA29
0x18003f9ae  mov     ecx, 200h; dwBytes
0x18003f9b3  call    MALLOC
0x18003f9b8  mov     rbx, rax
0x18003f9bb  test    rax, rax
0x18003f9be  jz      short loc_18003FA29
0x18003f9c0  mov     rax, [rsi+8]
0x18003f9c4  cmp     [rax], rsi
0x18003f9c7  jnz     loc_18003FAF0
0x18003f9cd  mov     [rbx], rsi
0x18003f9d0  lea     rcx, [rbx+140h]; void *
0x18003f9d7  mov     [rbx+8], rax
0x18003f9db  mov     [rax], rbx
0x18003f9de  mov     rdx, [rsp+510h+ppResult]
0x18003f9e3  mov     [rsi+8], rbx
0x18003f9e7  mov     r8, [rdx+10h]; Size
0x18003f9eb  mov     rdx, [rdx+20h]; Src
0x18003f9ef  call    memcpy_0
0x18003f9f4  mov     rax, [rsp+510h+ppResult]
0x18003f9f9  mov     ecx, [rax+10h]
0x18003f9fc  mov     [rbx+1C0h], ecx
0x18003fa02  lea     rcx, [rbx+0B8h]; void *
0x18003fa09  mov     rdx, [rsp+510h+pAddrInfo]
0x18003fa0e  mov     r8, [rdx+10h]; Size
0x18003fa12  mov     rdx, [rdx+20h]; Src
0x18003fa16  call    memcpy_0
0x18003fa1b  mov     rax, [rsp+510h+pAddrInfo]
0x18003fa20  mov     ecx, [rax+10h]
0x18003fa23  mov     [rbx+138h], ecx
0x18003fa29  mov     rcx, [rsp+510h+ppResult]; pAddrInfo
0x18003fa2e  call    cs:__imp_FreeAddrInfoW
0x18003fa35  nop     dword ptr [rax+rax+00h]
0x18003fa3a  mov     rcx, [rsp+510h+pAddrInfo]; pAddrInfo
0x18003fa3f  call    cs:__imp_FreeAddrInfoW
0x18003fa46  nop     dword ptr [rax+rax+00h]
0x18003fa4b  mov     rcx, [rsp+510h+var_4B0]; hKey
0x18003fa50  lea     rax, [rsp+510h+cbData]
0x18003fa55  mov     [rsp+510h+lpcbData], rax; lpcbData
0x18003fa5a  lea     r9, [rsp+510h+cchValueName]; lpcchValueName
0x18003fa5f  lea     rax, [rbp+410h+Data]
0x18003fa66  mov     [rsp+510h+cchValueName], 100h
0x18003fa6e  mov     [rsp+510h+lpData], rax; lpData
0x18003fa73  lea     r8, [rbp+410h+ValueName]; lpValueName
0x18003fa77  lea     rax, [rsp+510h+Type]
0x18003fa7c  mov     [rsp+510h+cbData], 200h
0x18003fa84  mov     [rsp+510h+lpType], rax; lpType
0x18003fa89  add     r14d, r13d
0x18003fa8c  mov     edx, r14d; dwIndex
0x18003fa8f  mov     [rsp+510h+phkResult], 0; lpReserved
0x18003fa98  call    cs:__imp_RegEnumValueW
0x18003fa9f  nop     dword ptr [rax+rax+00h]
0x18003faa4  test    eax, eax
0x18003faa6  jz      loc_18003F8A0
0x18003faac  mov     rcx, [rsp+510h+var_4B0]; hKey
0x18003fab1  call    cs:__imp_RegCloseKey
0x18003fab8  nop     dword ptr [rax+rax+00h]
0x18003fabd  mov     rcx, [rsp+510h+hKey]; hKey
0x18003fac2  call    cs:__imp_RegCloseKey
0x18003fac9  nop     dword ptr [rax+rax+00h]
0x18003face  mov     rcx, [rbp+410h+var_40]
0x18003fad5  xor     rcx, rsp; StackCookie
0x18003fad8  call    __security_check_cookie
0x18003fadd  add     rsp, 4E0h
0x18003fae4  pop     r14
0x18003fae6  pop     r13
0x18003fae8  pop     r12
0x18003faea  pop     rdi
0x18003faeb  pop     rsi
0x18003faec  pop     rbx
0x18003faed  pop     rbp
0x18003faee  retn
0x18003faf0  mov     ecx, 3
0x18003faf5  int     29h; Win8: RtlFailFast(ecx)
```
