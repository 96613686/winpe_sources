# AppendType

- ea: `0x18003f6ec`
- end: `0x18003fab7`
- name: `AppendType`
- size: `971`
- prototype: `LSTATUS __fastcall(__int64, HKEY, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180038cc0`

## callees

- `0x180012dcc`
- `0x180034158`
- `0x18003f6ec`
- `0x18004b5f0`
- `0x180082274`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f874`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f8b1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f874`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003f8b1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f848`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003fa58`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f848`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003fa58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fa71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fa82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fa71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fa82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f7ec`
- `WS2_32!GetAddrInfoW` at `0x18003f8e2`
- `WS2_32!GetAddrInfoW` at `0x18003f906`
- `WS2_32!GetAddrInfoW` at `0x18003f8e2`
- `WS2_32!GetAddrInfoW` at `0x18003f906`
- `WS2_32!FreeAddrInfoW` at `0x18003f9ee`
- `WS2_32!FreeAddrInfoW` at `0x18003f9ff`
- `WS2_32!FreeAddrInfoW` at `0x18003f9ee`
- `WS2_32!FreeAddrInfoW` at `0x18003f9ff`

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
0x18003f6ec  push    rbp
0x18003f6ee  push    rbx
0x18003f6ef  push    rsi
0x18003f6f0  push    rdi
0x18003f6f1  push    r12
0x18003f6f3  push    r13
0x18003f6f5  push    r14
0x18003f6f7  lea     rbp, [rsp-3E0h]
0x18003f6ff  sub     rsp, 4E0h
0x18003f706  mov     rax, cs:__security_cookie
0x18003f70d  xor     rax, rsp
0x18003f710  mov     [rbp+410h+var_40], rax
0x18003f717  xorps   xmm0, xmm0
0x18003f71a  mov     [rsp+510h+pAddrInfo], 0
0x18003f723  mov     r10, rdx
0x18003f726  mov     [rsp+510h+ppResult], 0
0x18003f72f  movups  xmmword ptr [rsp+510h+var_4A0.ai_flags], xmm0
0x18003f734  mov     r13d, 1
0x18003f73a  movsxd  rdx, r8d
0x18003f73d  add     rdx, rdx
0x18003f740  mov     [rsp+510h+cchValueName], 0
0x18003f748  mov     rsi, rcx
0x18003f74b  mov     [rsp+510h+Type], 0
0x18003f753  lea     rcx, PpTypeInfo
0x18003f75a  mov     [rsp+510h+cbData], 0
0x18003f762  movups  xmmword ptr [rbp+410h+pHints.ai_flags], xmm0
0x18003f766  mov     eax, [rcx+rdx*8]
0x18003f769  mov     r9d, r13d; samDesired
0x18003f76c  mov     [rsp+510h+var_4A0.ai_family], eax
0x18003f770  xor     r8d, r8d; ulOptions
0x18003f773  mov     eax, [rcx+rdx*8+4]
0x18003f777  mov     rdx, [rcx+rdx*8+8]; lpSubKey
0x18003f77c  mov     rcx, r10; hKey
0x18003f77f  mov     [rbp+410h+pHints.ai_family], eax
0x18003f782  lea     rax, [rsp+510h+hKey]
0x18003f787  mov     [rsp+510h+phkResult], rax; phkResult
0x18003f78c  mov     [rsp+510h+hKey], 0
0x18003f795  mov     [rsp+510h+var_4B0], 0
0x18003f79e  movups  xmmword ptr [rbp+410h+var_4A0.ai_addrlen], xmm0
0x18003f7a2  mov     [rsp+510h+var_4A0.ai_socktype], r13d
0x18003f7a7  movups  xmmword ptr [rbp+410h+var_4A0.ai_addr], xmm0
0x18003f7ab  mov     [rsp+510h+var_4A0.ai_flags], r13d
0x18003f7b0  movups  xmmword ptr [rbp+410h+pHints.ai_addrlen], xmm0
0x18003f7b4  mov     [rbp+410h+pHints.ai_socktype], r13d
0x18003f7b8  movups  xmmword ptr [rbp+410h+pHints.ai_addr], xmm0
0x18003f7bc  call    cs:__imp_RegOpenKeyExW
0x18003f7c3  nop     dword ptr [rax+rax+00h]
0x18003f7c8  test    eax, eax
0x18003f7ca  jnz     loc_18003FA8E
0x18003f7d0  mov     rcx, [rsp+510h+hKey]; hKey
0x18003f7d5  lea     rax, [rsp+510h+var_4B0]
0x18003f7da  mov     r9d, r13d; samDesired
0x18003f7dd  mov     [rsp+510h+phkResult], rax; phkResult
0x18003f7e2  xor     r8d, r8d; ulOptions
0x18003f7e5  lea     rdx, aTcp; "tcp"
0x18003f7ec  call    cs:__imp_RegOpenKeyExW
0x18003f7f3  nop     dword ptr [rax+rax+00h]
0x18003f7f8  test    eax, eax
0x18003f7fa  jnz     loc_18003FA7D
0x18003f800  mov     rcx, [rsp+510h+var_4B0]; hKey
0x18003f805  lea     rax, [rsp+510h+cbData]
0x18003f80a  mov     [rsp+510h+lpcbData], rax; lpcbData
0x18003f80f  lea     r9, [rsp+510h+cchValueName]; lpcchValueName
0x18003f814  lea     rax, [rbp+410h+Data]
0x18003f81b  mov     [rsp+510h+cchValueName], 100h
0x18003f823  mov     [rsp+510h+lpData], rax; lpData
0x18003f828  lea     r8, [rbp+410h+ValueName]; lpValueName
0x18003f82c  lea     rax, [rsp+510h+Type]
0x18003f831  mov     [rsp+510h+cbData], 200h
0x18003f839  mov     [rsp+510h+lpType], rax; lpType
0x18003f83e  xor     r14d, r14d
0x18003f841  xor     edx, edx; dwIndex
0x18003f843  mov     [rsp+510h+phkResult], r14; lpReserved
0x18003f848  call    cs:__imp_RegEnumValueW
0x18003f84f  nop     dword ptr [rax+rax+00h]
0x18003f854  test    eax, eax
0x18003f856  jnz     loc_18003FA6C
0x18003f85c  lea     r12d, [r13+1]
0x18003f860  cmp     [rsp+510h+Type], r13d
0x18003f865  jnz     loc_18003FA0B
0x18003f86b  mov     edx, 2Fh ; '/'; Ch
0x18003f870  lea     rcx, [rbp+410h+ValueName]; Str
0x18003f874  call    cs:__imp_wcschr
0x18003f87b  nop     dword ptr [rax+rax+00h]
0x18003f880  mov     rbx, rax
0x18003f883  test    rax, rax
0x18003f886  jz      short loc_18003F89F
0x18003f888  xor     ecx, ecx
0x18003f88a  lea     rdi, [rbp+410h+ValueName]
0x18003f88e  cmp     [rbp+410h+ValueName], 2Ah ; '*'
0x18003f893  mov     [rax], cx
0x18003f896  cmovz   rdi, rcx
0x18003f89a  add     rbx, r12
0x18003f89d  jmp     short loc_18003F8A5
0x18003f89f  xor     edi, edi
0x18003f8a1  lea     rbx, [rbp+410h+ValueName]
0x18003f8a5  mov     edx, 2Fh ; '/'; Ch
0x18003f8aa  lea     rcx, [rbp+410h+Data]; Str
0x18003f8b1  call    cs:__imp_wcschr
0x18003f8b8  nop     dword ptr [rax+rax+00h]
0x18003f8bd  test    rax, rax
0x18003f8c0  jz      short loc_18003F8CC
0x18003f8c2  xor     ecx, ecx
0x18003f8c4  mov     [rax], cx
0x18003f8c7  add     rax, r12
0x18003f8ca  jmp     short loc_18003F8CF
0x18003f8cc  mov     rax, rbx
0x18003f8cf  lea     r9, [rsp+510h+ppResult]; ppResult
0x18003f8d4  mov     rdx, rax; pServiceName
0x18003f8d7  lea     r8, [rbp+410h+pHints]; pHints
0x18003f8db  lea     rcx, [rbp+410h+Data]; pNodeName
0x18003f8e2  call    cs:__imp_GetAddrInfoW
0x18003f8e9  nop     dword ptr [rax+rax+00h]
0x18003f8ee  test    eax, eax
0x18003f8f0  jnz     loc_18003FA0B
0x18003f8f6  lea     r9, [rsp+510h+pAddrInfo]; ppResult
0x18003f8fb  mov     rdx, rbx; pServiceName
0x18003f8fe  lea     r8, [rsp+510h+var_4A0]; pHints
0x18003f903  mov     rcx, rdi; pNodeName
0x18003f906  call    cs:__imp_GetAddrInfoW
0x18003f90d  nop     dword ptr [rax+rax+00h]
0x18003f912  test    eax, eax
0x18003f914  jz      short loc_18003F920
0x18003f916  mov     rcx, [rsp+510h+ppResult]
0x18003f91b  jmp     loc_18003F9FF
0x18003f920  mov     rax, [rsp+510h+ppResult]
0x18003f925  mov     rcx, [rax+20h]
0x18003f929  cmp     word ptr [rcx], 17h
0x18003f92d  jnz     short loc_18003F94A
0x18003f92f  add     rcx, 8; a
0x18003f933  cmp     byte ptr [rcx], 0FFh
0x18003f936  jz      loc_18003F9E9
0x18003f93c  call    IN6_IS_ADDR_UNSPECIFIED
0x18003f941  test    al, al
0x18003f943  jz      short loc_18003F96E
0x18003f945  jmp     loc_18003F9E9
0x18003f94a  cmp     [rcx], r12w
0x18003f94e  jnz     loc_18003F9E9
0x18003f954  mov     edx, [rcx+4]
0x18003f957  mov     eax, edx
0x18003f959  and     eax, 0F0h
0x18003f95e  cmp     al, 0E0h
0x18003f960  jz      loc_18003F9E9
0x18003f966  lea     eax, [rdx-1]
0x18003f969  cmp     eax, 0FFFFFFFDh
0x18003f96c  ja      short loc_18003F9E9
0x18003f96e  mov     ecx, 200h; dwBytes
0x18003f973  call    MALLOC
0x18003f978  mov     rbx, rax
0x18003f97b  test    rax, rax
0x18003f97e  jz      short loc_18003F9E9
0x18003f980  mov     rax, [rsi+8]
0x18003f984  cmp     [rax], rsi
0x18003f987  jnz     loc_18003FAB0
0x18003f98d  mov     [rbx], rsi
0x18003f990  lea     rcx, [rbx+140h]; void *
0x18003f997  mov     [rbx+8], rax
0x18003f99b  mov     [rax], rbx
0x18003f99e  mov     rdx, [rsp+510h+ppResult]
0x18003f9a3  mov     [rsi+8], rbx
0x18003f9a7  mov     r8, [rdx+10h]; Size
0x18003f9ab  mov     rdx, [rdx+20h]; Src
0x18003f9af  call    memcpy_0
0x18003f9b4  mov     rax, [rsp+510h+ppResult]
0x18003f9b9  mov     ecx, [rax+10h]
0x18003f9bc  mov     [rbx+1C0h], ecx
0x18003f9c2  lea     rcx, [rbx+0B8h]; void *
0x18003f9c9  mov     rdx, [rsp+510h+pAddrInfo]
0x18003f9ce  mov     r8, [rdx+10h]; Size
0x18003f9d2  mov     rdx, [rdx+20h]; Src
0x18003f9d6  call    memcpy_0
0x18003f9db  mov     rax, [rsp+510h+pAddrInfo]
0x18003f9e0  mov     ecx, [rax+10h]
0x18003f9e3  mov     [rbx+138h], ecx
0x18003f9e9  mov     rcx, [rsp+510h+ppResult]; pAddrInfo
0x18003f9ee  call    cs:__imp_FreeAddrInfoW
0x18003f9f5  nop     dword ptr [rax+rax+00h]
0x18003f9fa  mov     rcx, [rsp+510h+pAddrInfo]; pAddrInfo
0x18003f9ff  call    cs:__imp_FreeAddrInfoW
0x18003fa06  nop     dword ptr [rax+rax+00h]
0x18003fa0b  mov     rcx, [rsp+510h+var_4B0]; hKey
0x18003fa10  lea     rax, [rsp+510h+cbData]
0x18003fa15  mov     [rsp+510h+lpcbData], rax; lpcbData
0x18003fa1a  lea     r9, [rsp+510h+cchValueName]; lpcchValueName
0x18003fa1f  lea     rax, [rbp+410h+Data]
0x18003fa26  mov     [rsp+510h+cchValueName], 100h
0x18003fa2e  mov     [rsp+510h+lpData], rax; lpData
0x18003fa33  lea     r8, [rbp+410h+ValueName]; lpValueName
0x18003fa37  lea     rax, [rsp+510h+Type]
0x18003fa3c  mov     [rsp+510h+cbData], 200h
0x18003fa44  mov     [rsp+510h+lpType], rax; lpType
0x18003fa49  add     r14d, r13d
0x18003fa4c  mov     edx, r14d; dwIndex
0x18003fa4f  mov     [rsp+510h+phkResult], 0; lpReserved
0x18003fa58  call    cs:__imp_RegEnumValueW
0x18003fa5f  nop     dword ptr [rax+rax+00h]
0x18003fa64  test    eax, eax
0x18003fa66  jz      loc_18003F860
0x18003fa6c  mov     rcx, [rsp+510h+var_4B0]; hKey
0x18003fa71  call    cs:__imp_RegCloseKey
0x18003fa78  nop     dword ptr [rax+rax+00h]
0x18003fa7d  mov     rcx, [rsp+510h+hKey]; hKey
0x18003fa82  call    cs:__imp_RegCloseKey
0x18003fa89  nop     dword ptr [rax+rax+00h]
0x18003fa8e  mov     rcx, [rbp+410h+var_40]
0x18003fa95  xor     rcx, rsp; StackCookie
0x18003fa98  call    __security_check_cookie
0x18003fa9d  add     rsp, 4E0h
0x18003faa4  pop     r14
0x18003faa6  pop     r13
0x18003faa8  pop     r12
0x18003faaa  pop     rdi
0x18003faab  pop     rsi
0x18003faac  pop     rbx
0x18003faad  pop     rbp
0x18003faae  retn
0x18003fab0  mov     ecx, 3
0x18003fab5  int     29h; Win8: RtlFailFast(ecx)
```
