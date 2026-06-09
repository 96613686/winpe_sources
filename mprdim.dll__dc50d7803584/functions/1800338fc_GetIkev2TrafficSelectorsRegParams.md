# GetIkev2TrafficSelectorsRegParams

- ea: `0x1800338fc`
- end: `0x180033e1b`
- name: `GetIkev2TrafficSelectorsRegParams`
- size: `1311`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800336dc`

## callees

- `0x1800338fc`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!wcsstr` at `0x180033c5b`
- `msvcrt!wcsstr` at `0x180033d34`
- `msvcrt!wcsstr` at `0x180033c5b`
- `msvcrt!wcsstr` at `0x180033d34`
- `ntdll!RtlIpv6StringToAddressW` at `0x180033c9f`
- `ntdll!RtlIpv6StringToAddressW` at `0x180033d7b`
- `ntdll!RtlIpv6StringToAddressW` at `0x180033c9f`
- `ntdll!RtlIpv6StringToAddressW` at `0x180033d7b`
- `ntdll!RtlIpv4StringToAddressW` at `0x180033c76`
- `ntdll!RtlIpv4StringToAddressW` at `0x180033d4f`
- `ntdll!RtlIpv4StringToAddressW` at `0x180033c76`
- `ntdll!RtlIpv4StringToAddressW` at `0x180033d4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033dd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033de2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033dd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033de2`
- `KERNEL32!RegGetValueW` at `0x180033acb`
- `KERNEL32!RegGetValueW` at `0x180033b26`
- `KERNEL32!RegGetValueW` at `0x180033b7a`
- `KERNEL32!RegGetValueW` at `0x180033bcc`
- `KERNEL32!RegGetValueW` at `0x180033c35`
- `KERNEL32!RegGetValueW` at `0x180033d0e`
- `KERNEL32!RegGetValueW` at `0x180033acb`
- `KERNEL32!RegGetValueW` at `0x180033b26`
- `KERNEL32!RegGetValueW` at `0x180033b7a`
- `KERNEL32!RegGetValueW` at `0x180033bcc`
- `KERNEL32!RegGetValueW` at `0x180033c35`
- `KERNEL32!RegGetValueW` at `0x180033d0e`
- `ADVAPI32!RegEnumKeyExW` at `0x180033a8c`
- `ADVAPI32!RegEnumKeyExW` at `0x180033a8c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800339d9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800339d9`

## string_xrefs

- `0x180033b4f`: `Protocol`

## pseudocode

```c
__int64 __fastcall GetIkev2TrafficSelectorsRegParams(HKEY hkey, __int64 a2, __int64 a3, DWORD *a4, _QWORD *a5)
{
  DWORD v5; // r14d
  unsigned int ValueW; // ebx
  unsigned __int64 v9; // rdi
  DWORD v10; // esi
  WCHAR *v11; // r15
  _BYTE *v12; // rdi
  __int64 v13; // rsi
  __int16 v14; // cx
  int v15; // eax
  __int16 v16; // ax
  DWORD pdwType; // [rsp+60h] [rbp-A0h] BYREF
  int pvData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  in_addr Addr; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-8Ch] BYREF
  LPCWSTR Terminator; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  DWORD v26; // [rsp+84h] [rbp-7Ch]
  _QWORD *v27; // [rsp+88h] [rbp-78h]
  in6_addr v28; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Str[136]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = 0;
  v27 = a5;
  cbMaxSubKeyLen = 0;
  cSubKeys = 0;
  pdwType = 0;
  ValueW = 0;
  pcbData = 4;
  memset_0(Str, 0, 0x102u);
  Terminator = 0;
  Addr = 0;
  pvData = 0;
  v28 = 0;
  if ( hkey )
  {
    if ( a5 )
    {
      if ( a4 )
      {
        ValueW = RegQueryInfoKeyW(hkey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( !ValueW )
        {
          v9 = 52LL * cSubKeys;
          if ( v9 > 0xFFFFFFFF )
          {
            return 87;
          }
          else
          {
            ++cbMaxSubKeyLen;
            v10 = 2 * cbMaxSubKeyLen;
            v26 = 2 * cbMaxSubKeyLen;
            v11 = (WCHAR *)HeapAlloc(hHeap, 8u, 2 * cbMaxSubKeyLen);
            if ( v11 )
            {
              v12 = HeapAlloc(hHeap, 8u, (unsigned int)v9);
              if ( v12 )
              {
                if ( cSubKeys )
                {
                  while ( 1 )
                  {
                    cchName = v10;
                    ValueW = RegEnumKeyExW(hkey, v5, v11, &cchName, 0, 0, 0, 0);
                    if ( ValueW )
                      break;
                    ValueW = RegGetValueW(hkey, v11, L"StartPort", 0x10u, &pdwType, &pvData, &pcbData);
                    if ( ValueW )
                      break;
                    if ( pdwType != 4 )
                      break;
                    v13 = 52LL * v5;
                    *(_WORD *)&v12[v13 + 6] = pvData;
                    ValueW = RegGetValueW(hkey, v11, L"EndPort", 0x10u, &pdwType, &pvData, &pcbData);
                    if ( ValueW )
                      break;
                    if ( pdwType != 4 )
                      break;
                    *(_WORD *)&v12[v13 + 8] = pvData;
                    ValueW = RegGetValueW(hkey, v11, L"Protocol", 0x10u, &pdwType, &pvData, &pcbData);
                    if ( ValueW )
                      break;
                    if ( pdwType != 4 )
                      break;
                    v12[v13 + 4] = pvData;
                    ValueW = RegGetValueW(hkey, v11, L"TsPayloadId", 0x10u, &pdwType, &pvData, &pcbData);
                    if ( ValueW )
                      break;
                    if ( pdwType != 4 )
                      break;
                    *(_WORD *)&v12[v13 + 10] = pvData;
                    pcbData = 258;
                    memset_0(Str, 0, 0x102u);
                    ValueW = RegGetValueW(hkey, v11, L"StartIP", 2u, &pdwType, Str, &pcbData);
                    if ( ValueW || pdwType != 1 )
                      break;
                    if ( wcsstr(Str, L":") )
                    {
                      ValueW = RtlIpv6StringToAddressW(Str, &Terminator, &v28);
                      if ( ValueW )
                        break;
                      v14 = 23;
                      v15 = 8;
                      *(in6_addr *)&v12[v13 + 16] = v28;
                    }
                    else
                    {
                      ValueW = RtlIpv4StringToAddressW(Str, 1u, &Terminator, &Addr);
                      if ( ValueW )
                        break;
                      v14 = 2;
                      *(in_addr *)&v12[v13 + 16] = Addr;
                      v15 = 7;
                    }
                    *(_DWORD *)&v12[v13] = v15;
                    *(_WORD *)&v12[v13 + 12] = v14;
                    pcbData = 258;
                    memset_0(Str, 0, 0x102u);
                    ValueW = RegGetValueW(hkey, v11, L"EndIP", 2u, &pdwType, Str, &pcbData);
                    if ( ValueW || pdwType != 1 )
                      break;
                    if ( wcsstr(Str, L":") )
                    {
                      RtlIpv6StringToAddressW(Str, &Terminator, &v28);
                      v16 = 23;
                      if ( *(_WORD *)&v12[v13 + 12] != 23 )
                        break;
                      *(in6_addr *)&v12[v13 + 36] = v28;
                    }
                    else
                    {
                      ValueW = RtlIpv4StringToAddressW(Str, 1u, &Terminator, &Addr);
                      if ( ValueW || *(_WORD *)&v12[v13 + 12] != 2 )
                        break;
                      *(in_addr *)&v12[v13 + 36] = Addr;
                      v16 = 2;
                    }
                    *(_WORD *)&v12[v13 + 32] = v16;
                    ++v5;
                    v10 = v26;
                    if ( v5 >= cSubKeys )
                    {
                      if ( !v5 )
                        goto LABEL_36;
                      *v27 = v12;
                      *a4 = v5;
                      goto LABEL_38;
                    }
                  }
                }
                else
                {
LABEL_36:
                  ValueW = 1168;
                }
                HeapFree(hHeap, 0, v12);
              }
LABEL_38:
              HeapFree(hHeap, 0, v11);
            }
          }
        }
      }
    }
  }
  return ValueW;
}

```

## disassembly

```asm
0x1800338fc  mov     [rsp-8+arg_8], rbx
0x180033901  push    rbp
0x180033902  push    rsi
0x180033903  push    rdi
0x180033904  push    r12
0x180033906  push    r13
0x180033908  push    r14
0x18003390a  push    r15
0x18003390c  lea     rbp, [rsp-0C0h]
0x180033914  sub     rsp, 1C0h
0x18003391b  mov     rax, cs:__security_cookie
0x180033922  xor     rax, rsp
0x180033925  mov     [rbp+0F0h+var_40], rax
0x18003392c  mov     rdi, [rbp+0F0h+arg_20]
0x180033933  xor     r14d, r14d
0x180033936  mov     r12, rcx
0x180033939  mov     [rbp+0F0h+var_168], rdi
0x18003393d  lea     rcx, [rbp+0F0h+Str]; void *
0x180033941  mov     [rsp+1F0h+cbMaxSubKeyLen], r14d
0x180033946  xor     edx, edx; Val
0x180033948  mov     [rsp+1F0h+cSubKeys], r14d
0x18003394d  mov     r8d, 102h; Size
0x180033953  mov     [rsp+1F0h+pdwType], r14d
0x180033958  mov     ebx, r14d
0x18003395b  mov     [rsp+1F0h+pcbData], 4
0x180033963  mov     r13, r9
0x180033966  call    memset_0
0x18003396b  mov     [rsp+1F0h+Terminator], r14
0x180033970  xorps   xmm0, xmm0
0x180033973  mov     dword ptr [rsp+1F0h+Addr.S_un], r14d
0x180033978  mov     [rsp+1F0h+pvData], r14d
0x18003397d  movups  xmmword ptr [rbp+0F0h+var_160.u], xmm0
0x180033981  test    r12, r12
0x180033984  jz      loc_180033DEF
0x18003398a  test    rdi, rdi
0x18003398d  jz      loc_180033DEF
0x180033993  test    r13, r13
0x180033996  jz      loc_180033DEF
0x18003399c  mov     [rsp+1F0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800339a1  lea     rax, [rsp+1F0h+cbMaxSubKeyLen]
0x1800339a6  mov     [rsp+1F0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800339ab  xor     r9d, r9d; lpReserved
0x1800339ae  mov     [rsp+1F0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800339b3  xor     r8d, r8d; lpcchClass
0x1800339b6  mov     [rsp+1F0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800339bb  xor     edx, edx; lpClass
0x1800339bd  mov     [rsp+1F0h+lpcValues], r14; lpcValues
0x1800339c2  mov     rcx, r12; hKey
0x1800339c5  mov     [rsp+1F0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800339ca  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800339cf  lea     rax, [rsp+1F0h+cSubKeys]
0x1800339d4  mov     [rsp+1F0h+lpcSubKeys], rax; lpcSubKeys
0x1800339d9  call    cs:__imp_RegQueryInfoKeyW
0x1800339df  mov     ebx, eax
0x1800339e1  test    eax, eax
0x1800339e3  jnz     loc_180033DEF
0x1800339e9  mov     ecx, [rsp+1F0h+cSubKeys]
0x1800339ed  mov     eax, 0FFFFFFFFh
0x1800339f2  imul    rdi, rcx, 34h ; '4'
0x1800339f6  cmp     rdi, rax
0x1800339f9  ja      loc_180033DEA
0x1800339ff  mov     ecx, [rsp+1F0h+cbMaxSubKeyLen]
0x180033a03  lea     edx, [rbx+8]; dwFlags
0x180033a06  inc     ecx
0x180033a08  mov     [rsp+1F0h+cbMaxSubKeyLen], ecx
0x180033a0c  lea     esi, [rcx+rcx]
0x180033a0f  mov     rcx, cs:hHeap; hHeap
0x180033a16  mov     r8d, esi; dwBytes
0x180033a19  mov     [rbp+0F0h+var_16C], esi
0x180033a1c  call    cs:__imp_HeapAlloc
0x180033a22  mov     r15, rax
0x180033a25  test    rax, rax
0x180033a28  jz      loc_180033DEF
0x180033a2e  mov     rcx, cs:hHeap; hHeap
0x180033a35  lea     edx, [rbx+8]; dwFlags
0x180033a38  mov     r8d, edi; dwBytes
0x180033a3b  call    cs:__imp_HeapAlloc
0x180033a41  mov     rdi, rax
0x180033a44  test    rax, rax
0x180033a47  jz      loc_180033DD6
0x180033a4d  cmp     [rsp+1F0h+cSubKeys], r14d
0x180033a52  jbe     loc_180033DBF
0x180033a58  mov     [rsp+1F0h+lpcValues], 0; lpftLastWriteTime
0x180033a61  lea     r9, [rbp+0F0h+cchName]; lpcchName
0x180033a65  mov     [rsp+1F0h+lpcbMaxClassLen], 0; lpcchClass
0x180033a6e  mov     r8, r15; lpName
0x180033a71  mov     [rsp+1F0h+lpcbMaxSubKeyLen], 0; lpClass
0x180033a7a  mov     edx, r14d; dwIndex
0x180033a7d  mov     rcx, r12; hKey
0x180033a80  mov     [rsp+1F0h+lpcSubKeys], 0; lpReserved
0x180033a89  mov     [rbp+0F0h+cchName], esi
0x180033a8c  call    cs:__imp_RegEnumKeyExW
0x180033a92  mov     ebx, eax
0x180033a94  test    eax, eax
0x180033a96  jnz     loc_180033DC4
0x180033a9c  lea     rax, [rsp+1F0h+pcbData]
0x180033aa1  mov     rdx, r15; lpSubKey
0x180033aa4  mov     [rsp+1F0h+lpcbMaxClassLen], rax; pcbData
0x180033aa9  lea     r9d, [rbx+10h]; dwFlags
0x180033aad  lea     rax, [rsp+1F0h+pvData]
0x180033ab2  mov     rcx, r12; hkey
0x180033ab5  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; pvData
0x180033aba  lea     r8, aStartport; "StartPort"
0x180033ac1  lea     rax, [rsp+1F0h+pdwType]
0x180033ac6  mov     [rsp+1F0h+lpcSubKeys], rax; pdwType
0x180033acb  call    cs:__imp_RegGetValueW
0x180033ad1  mov     ebx, eax
0x180033ad3  test    eax, eax
0x180033ad5  jnz     loc_180033DC4
0x180033adb  cmp     [rsp+1F0h+pdwType], 4
0x180033ae0  jnz     loc_180033DC4
0x180033ae6  mov     eax, r14d
0x180033ae9  lea     r9d, [rbx+10h]; dwFlags
0x180033aed  imul    rsi, rax, 34h ; '4'
0x180033af1  movzx   eax, word ptr [rsp+1F0h+pvData]
0x180033af6  lea     r8, aEndport; "EndPort"
0x180033afd  mov     rdx, r15; lpSubKey
0x180033b00  mov     rcx, r12; hkey
0x180033b03  mov     [rsi+rdi+6], ax
0x180033b08  lea     rax, [rsp+1F0h+pcbData]
0x180033b0d  mov     [rsp+1F0h+lpcbMaxClassLen], rax; pcbData
0x180033b12  lea     rax, [rsp+1F0h+pvData]
0x180033b17  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; pvData
0x180033b1c  lea     rax, [rsp+1F0h+pdwType]
0x180033b21  mov     [rsp+1F0h+lpcSubKeys], rax; pdwType
0x180033b26  call    cs:__imp_RegGetValueW
0x180033b2c  mov     ebx, eax
0x180033b2e  test    eax, eax
0x180033b30  jnz     loc_180033DC4
0x180033b36  cmp     [rsp+1F0h+pdwType], 4
0x180033b3b  jnz     loc_180033DC4
0x180033b41  movzx   eax, word ptr [rsp+1F0h+pvData]
0x180033b46  lea     r9d, [rbx+10h]; dwFlags
0x180033b4a  mov     [rsi+rdi+8], ax
0x180033b4f  lea     r8, aProtocol; "Protocol"
0x180033b56  lea     rax, [rsp+1F0h+pcbData]
0x180033b5b  mov     rdx, r15; lpSubKey
0x180033b5e  mov     [rsp+1F0h+lpcbMaxClassLen], rax; pcbData
0x180033b63  mov     rcx, r12; hkey
0x180033b66  lea     rax, [rsp+1F0h+pvData]
0x180033b6b  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; pvData
0x180033b70  lea     rax, [rsp+1F0h+pdwType]
0x180033b75  mov     [rsp+1F0h+lpcSubKeys], rax; pdwType
0x180033b7a  call    cs:__imp_RegGetValueW
0x180033b80  mov     ebx, eax
0x180033b82  test    eax, eax
0x180033b84  jnz     loc_180033DC4
0x180033b8a  cmp     [rsp+1F0h+pdwType], 4
0x180033b8f  jnz     loc_180033DC4
0x180033b95  mov     al, byte ptr [rsp+1F0h+pvData]
0x180033b99  lea     r9d, [rbx+10h]; dwFlags
0x180033b9d  mov     [rsi+rdi+4], al
0x180033ba1  lea     r8, aTspayloadid; "TsPayloadId"
0x180033ba8  lea     rax, [rsp+1F0h+pcbData]
0x180033bad  mov     rdx, r15; lpSubKey
0x180033bb0  mov     [rsp+1F0h+lpcbMaxClassLen], rax; pcbData
0x180033bb5  mov     rcx, r12; hkey
0x180033bb8  lea     rax, [rsp+1F0h+pvData]
0x180033bbd  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; pvData
0x180033bc2  lea     rax, [rsp+1F0h+pdwType]
0x180033bc7  mov     [rsp+1F0h+lpcSubKeys], rax; pdwType
0x180033bcc  call    cs:__imp_RegGetValueW
0x180033bd2  mov     ebx, eax
0x180033bd4  test    eax, eax
0x180033bd6  jnz     loc_180033DC4
0x180033bdc  cmp     [rsp+1F0h+pdwType], 4
0x180033be1  jnz     loc_180033DC4
0x180033be7  movzx   eax, word ptr [rsp+1F0h+pvData]
0x180033bec  lea     rcx, [rbp+0F0h+Str]; void *
0x180033bf0  mov     r8d, 102h; Size
0x180033bf6  mov     [rsi+rdi+0Ah], ax
0x180033bfb  xor     edx, edx; Val
0x180033bfd  mov     [rsp+1F0h+pcbData], r8d
0x180033c02  call    memset_0
0x180033c07  lea     rax, [rsp+1F0h+pcbData]
0x180033c0c  mov     rdx, r15; lpSubKey
0x180033c0f  mov     [rsp+1F0h+lpcbMaxClassLen], rax; pcbData
0x180033c14  lea     r9d, [rbx+2]; dwFlags
0x180033c18  lea     rax, [rbp+0F0h+Str]
0x180033c1c  mov     rcx, r12; hkey
0x180033c1f  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; pvData
0x180033c24  lea     r8, aStartip; "StartIP"
0x180033c2b  lea     rax, [rsp+1F0h+pdwType]
0x180033c30  mov     [rsp+1F0h+lpcSubKeys], rax; pdwType
0x180033c35  call    cs:__imp_RegGetValueW
0x180033c3b  mov     ebx, eax
0x180033c3d  test    eax, eax
0x180033c3f  jnz     loc_180033DC4
0x180033c45  cmp     [rsp+1F0h+pdwType], 1
0x180033c4a  jnz     loc_180033DC4
0x180033c50  lea     rdx, SubStr; ":"
0x180033c57  lea     rcx, [rbp+0F0h+Str]; Str
0x180033c5b  call    cs:__imp_wcsstr
0x180033c61  lea     rcx, [rbp+0F0h+Str]; S
0x180033c65  test    rax, rax
0x180033c68  jnz     short loc_180033C96
0x180033c6a  lea     r9, [rsp+1F0h+Addr]; Addr
0x180033c6f  mov     dl, 1; Strict
0x180033c71  lea     r8, [rsp+1F0h+Terminator]; Terminator
0x180033c76  call    cs:__imp_RtlIpv4StringToAddressW
0x180033c7c  mov     ebx, eax
0x180033c7e  test    eax, eax
0x180033c80  jnz     loc_180033DC4
0x180033c86  mov     eax, dword ptr [rsp+1F0h+Addr.S_un]
0x180033c8a  lea     ecx, [rbx+2]
0x180033c8d  mov     [rsi+rdi+10h], eax
0x180033c91  lea     eax, [rbx+7]
0x180033c94  jmp     short loc_180033CBF
0x180033c96  lea     r8, [rbp+0F0h+var_160]; Addr
0x180033c9a  lea     rdx, [rsp+1F0h+Terminator]; Terminator
0x180033c9f  call    cs:__imp_RtlIpv6StringToAddressW
0x180033ca5  mov     ebx, eax
0x180033ca7  test    eax, eax
0x180033ca9  jnz     loc_180033DC4
0x180033caf  movups  xmm0, xmmword ptr [rbp+0F0h+var_160.u]
0x180033cb3  lea     ecx, [rax+17h]
0x180033cb6  lea     eax, [rbx+8]
0x180033cb9  movdqu  xmmword ptr [rsi+rdi+10h], xmm0
0x180033cbf  mov     [rsi+rdi], eax
0x180033cc2  xor     edx, edx; Val
0x180033cc4  mov     eax, 102h
0x180033cc9  mov     [rsi+rdi+0Ch], cx
0x180033cce  mov     r8d, eax; Size
0x180033cd1  mov     [rsp+1F0h+pcbData], eax
0x180033cd5  lea     rcx, [rbp+0F0h+Str]; void *
0x180033cd9  call    memset_0
0x180033cde  lea     rax, [rsp+1F0h+pcbData]
0x180033ce3  mov     r9d, 2; dwFlags
0x180033ce9  mov     [rsp+1F0h+lpcbMaxClassLen], rax; pcbData
0x180033cee  lea     r8, aEndip; "EndIP"
0x180033cf5  lea     rax, [rbp+0F0h+Str]
0x180033cf9  mov     rdx, r15; lpSubKey
0x180033cfc  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; pvData
0x180033d01  mov     rcx, r12; hkey
0x180033d04  lea     rax, [rsp+1F0h+pdwType]
0x180033d09  mov     [rsp+1F0h+lpcSubKeys], rax; pdwType
0x180033d0e  call    cs:__imp_RegGetValueW
0x180033d14  mov     ebx, eax
0x180033d16  test    eax, eax
0x180033d18  jnz     loc_180033DC4
0x180033d1e  cmp     [rsp+1F0h+pdwType], 1
0x180033d23  jnz     loc_180033DC4
0x180033d29  lea     rdx, SubStr; ":"
0x180033d30  lea     rcx, [rbp+0F0h+Str]; Str
0x180033d34  call    cs:__imp_wcsstr
0x180033d3a  lea     rcx, [rbp+0F0h+Str]; S
0x180033d3e  test    rax, rax
0x180033d41  jnz     short loc_180033D72
0x180033d43  lea     r9, [rsp+1F0h+Addr]; Addr
0x180033d48  mov     dl, 1; Strict
0x180033d4a  lea     r8, [rsp+1F0h+Terminator]; Terminator
0x180033d4f  call    cs:__imp_RtlIpv4StringToAddressW
0x180033d55  mov     ebx, eax
0x180033d57  test    eax, eax
0x180033d59  jnz     short loc_180033DC4
0x180033d5b  lea     ecx, [rax+2]
0x180033d5e  cmp     [rsi+rdi+0Ch], cx
0x180033d63  jnz     short loc_180033DC4
0x180033d65  mov     eax, dword ptr [rsp+1F0h+Addr.S_un]
0x180033d69  mov     [rsi+rdi+24h], eax
0x180033d6d  movzx   eax, cx
0x180033d70  jmp     short loc_180033D97
0x180033d72  lea     r8, [rbp+0F0h+var_160]; Addr
0x180033d76  lea     rdx, [rsp+1F0h+Terminator]; Terminator
0x180033d7b  call    cs:__imp_RtlIpv6StringToAddressW
0x180033d81  mov     eax, 17h
0x180033d86  cmp     [rsi+rdi+0Ch], ax
0x180033d8b  jnz     short loc_180033DC4
0x180033d8d  movups  xmm0, xmmword ptr [rbp+0F0h+var_160.u]
0x180033d91  movdqu  xmmword ptr [rsi+rdi+24h], xmm0
0x180033d97  mov     [rsi+rdi+20h], ax
0x180033d9c  inc     r14d
0x180033d9f  mov     esi, [rbp+0F0h+var_16C]
0x180033da2  cmp     r14d, [rsp+1F0h+cSubKeys]
0x180033da7  jb      loc_180033A58
0x180033dad  test    r14d, r14d
0x180033db0  jz      short loc_180033DBF
0x180033db2  mov     rax, [rbp+0F0h+var_168]
0x180033db6  mov     [rax], rdi
0x180033db9  mov     [r13+0], r14d
0x180033dbd  jmp     short loc_180033DD6
0x180033dbf  mov     ebx, 490h
0x180033dc4  mov     rcx, cs:hHeap; hHeap
0x180033dcb  mov     r8, rdi; lpMem
0x180033dce  xor     edx, edx; dwFlags
0x180033dd0  call    cs:__imp_HeapFree
0x180033dd6  mov     rcx, cs:hHeap; hHeap
0x180033ddd  mov     r8, r15; lpMem
0x180033de0  xor     edx, edx; dwFlags
0x180033de2  call    cs:__imp_HeapFree
0x180033de8  jmp     short loc_180033DEF
0x180033dea  mov     ebx, 57h ; 'W'
0x180033def  mov     eax, ebx
0x180033df1  mov     rcx, [rbp+0F0h+var_40]
0x180033df8  xor     rcx, rsp; StackCookie
0x180033dfb  call    __security_check_cookie
0x180033e00  mov     rbx, [rsp+1F0h+arg_8]
0x180033e08  add     rsp, 1C0h
0x180033e0f  pop     r15
0x180033e11  pop     r14
  ... truncated ...
```
