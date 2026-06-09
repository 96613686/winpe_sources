# MprConfigInterfaceSetCustomInfoEx

- ea: `0x180024c10`
- end: `0x180024f6c`
- name: `MprConfigInterfaceSetCustomInfoEx`
- size: `860`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180008948`
- `0x180024c10`
- `0x180027d5c`
- `0x18002ed78`
- `0x180030b7c`
- `0x180030c30`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024f54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024cd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024cd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024d38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024d38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180024d5d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180024f17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180024d5d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180024f17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024df1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024e20`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024e4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024e8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024ed0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024df1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024e20`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024e4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024e8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024ed0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024d71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024d82`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024d93`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024da4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024db5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024ea0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024ede`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024d71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024d82`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024d93`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024da4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024db5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024ea0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024ede`

## pseudocode

```c
__int64 __fastcall MprConfigInterfaceSetCustomInfoEx(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // r12d
  unsigned int v6; // ebx
  void *v7; // r15
  HANDLE ProcessHeap; // rax
  const BYTE *lpData; // rcx
  const BYTE *v10; // rcx
  HKEY v11; // rcx

  v5 = 0;
  if ( !a1 || !a2 || !a3 )
    goto LABEL_43;
  v6 = MprConfigServerValidateCb();
  if ( v6 )
    goto LABEL_44;
  v6 = ValidateMprIfCustomInfoExVersion(a3);
  if ( v6 )
    goto LABEL_44;
  v6 = 0;
  if ( (*(_BYTE *)(a3 + 4) & 1) != 0
    && ((unsigned int)(*(_DWORD *)(a3 + 8) - 300) > 0x2A1D3
     || (unsigned int)(*(_DWORD *)(a3 + 56) - 300) > 0x2A1D3
     || *(_DWORD *)(a3 + 12) < 0x400u) )
  {
    v6 = 87;
  }
  if ( v6 )
    goto LABEL_44;
  EnterCriticalSection(&CfgLock);
  v5 = 1;
  if ( *(_DWORD *)(a2 + 56) )
  {
    v6 = 905;
    goto LABEL_44;
  }
  if ( *(_DWORD *)(a2 + 24) != 2 )
    goto LABEL_43;
  if ( (*(_BYTE *)(a3 + 4) & 1) == 0 )
  {
    if ( a2 != -104 )
    {
      FreeCertificateBlob(a2 + 120);
      FreeCertificateBlob(a2 + 144);
      v7 = *(void **)(a2 + 136);
      if ( v7 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v7);
      }
      memset_0((void *)(a2 + 104), 0, 0x58u);
    }
    RegDeleteKeyExW(*(HKEY *)(a2 + 40), L"IKEv2CustomPolicy", 0, 0);
    *(_DWORD *)(a2 + 104) = 0;
    RegDeleteValueW(*(HKEY *)(a2 + 40), L"MachineCertificateName");
    RegDeleteValueW(*(HKEY *)(a2 + 40), L"MachineCertificateHash");
    RegDeleteValueW(*(HKEY *)(a2 + 40), L"SaLifeTime");
    RegDeleteValueW(*(HKEY *)(a2 + 40), L"MmSaLifeTime");
    RegDeleteValueW(*(HKEY *)(a2 + 40), L"SaMaxDataSize");
    *(_DWORD *)(a2 + 100) = 0;
    goto LABEL_44;
  }
  if ( a3 == -8 )
  {
LABEL_43:
    v6 = 87;
    goto LABEL_44;
  }
  v6 = RegSetValueExW(*(HKEY *)(a2 + 40), L"SaLifeTime", 0, 4u, (const BYTE *)(a3 + 8), 4u);
  if ( !v6 )
  {
    v6 = RegSetValueExW(*(HKEY *)(a2 + 40), L"MmSaLifeTime", 0, 4u, (const BYTE *)(a3 + 56), 4u);
    if ( !v6 )
    {
      v6 = RegSetValueExW(*(HKEY *)(a2 + 40), L"SaMaxDataSize", 0, 4u, (const BYTE *)(a3 + 12), 4u);
      if ( !v6 )
      {
        if ( *(_BYTE *)a3 == 2 && (lpData = *(const BYTE **)(a3 + 48)) != 0 )
          RegSetValueExW(*(HKEY *)(a2 + 40), L"MachineCertificateHash", 0, 3u, lpData, *(_DWORD *)(a3 + 40));
        else
          RegDeleteValueW(*(HKEY *)(a2 + 40), L"MachineCertificateHash");
        v10 = *(const BYTE **)(a3 + 24);
        if ( v10 )
        {
          v6 = RegSetValueExW(*(HKEY *)(a2 + 40), L"MachineCertificateName", 0, 3u, v10, *(_DWORD *)(a3 + 16));
        }
        else
        {
          v6 = RegDeleteValueW(*(HKEY *)(a2 + 40), L"MachineCertificateName");
          if ( v6 == 2 )
            v6 = 0;
        }
        if ( !v6 )
        {
          v11 = *(HKEY *)(a2 + 40);
          if ( *(_QWORD *)(a3 + 32) )
          {
            v6 = SetIkev2CustomPolicy(v11);
            if ( v6 )
              goto LABEL_44;
          }
          else
          {
            RegDeleteKeyExW(v11, L"IKEv2CustomPolicy", 0, 0);
          }
          if ( *(_DWORD *)(a3 + 64) || *(_DWORD *)(a3 + 68) )
            v6 = SetIkev2TrafficSelectors(*(HKEY *)(a2 + 40));
          if ( !v6 )
          {
            *(_DWORD *)(a2 + 100) = 0;
            *(_DWORD *)(a2 + 104) = 1;
          }
        }
      }
    }
  }
LABEL_44:
  if ( v5 )
    LeaveCriticalSection(&CfgLock);
  return v6;
}

```

## disassembly

```asm
0x180024c10  mov     [rsp+arg_10], r8
0x180024c15  mov     [rsp+arg_8], rdx
0x180024c1a  push    rbx
0x180024c1b  push    rsi
0x180024c1c  push    rdi
0x180024c1d  push    r12
0x180024c1f  push    r13
0x180024c21  push    r14
0x180024c23  push    r15
0x180024c25  sub     rsp, 40h
0x180024c29  mov     r14, r8
0x180024c2c  mov     rsi, rdx
0x180024c2f  xor     edi, edi
0x180024c31  mov     r12d, edi
0x180024c34  test    rcx, rcx
0x180024c37  jz      loc_180024F43
0x180024c3d  test    rdx, rdx
0x180024c40  jz      loc_180024F43
0x180024c46  test    r8, r8
0x180024c49  jz      loc_180024F43
0x180024c4f  call    MprConfigServerValidateCb
0x180024c54  mov     ebx, eax
0x180024c56  test    eax, eax
0x180024c58  jnz     loc_180024F48
0x180024c5e  mov     rcx, r14
0x180024c61  call    ValidateMprIfCustomInfoExVersion
0x180024c66  mov     ebx, eax
0x180024c68  mov     [rsp+78h+var_48], eax
0x180024c6c  jmp     short loc_180024C8C
0x180024c6e  mov     ebx, 57h ; 'W'
0x180024c73  mov     [rsp+78h+var_48], ebx
0x180024c77  xor     edi, edi
0x180024c79  mov     r14, [rsp+78h+arg_10]
0x180024c81  mov     rsi, [rsp+78h+arg_8]
0x180024c89  mov     r12d, edi
0x180024c8c  test    ebx, ebx
0x180024c8e  jnz     loc_180024F48
0x180024c94  mov     ebx, edi
0x180024c96  test    byte ptr [r14+4], 1
0x180024c9b  jz      short loc_180024CCA
0x180024c9d  mov     eax, [r14+8]
0x180024ca1  mov     ecx, 12Ch
0x180024ca6  sub     eax, ecx
0x180024ca8  mov     edx, 2A1D3h
0x180024cad  cmp     eax, edx
0x180024caf  ja      short loc_180024CC5
0x180024cb1  mov     eax, [r14+38h]
0x180024cb5  sub     eax, ecx
0x180024cb7  cmp     eax, edx
0x180024cb9  ja      short loc_180024CC5
0x180024cbb  cmp     dword ptr [r14+0Ch], 400h
0x180024cc3  jnb     short loc_180024CCA
0x180024cc5  mov     ebx, 57h ; 'W'
0x180024cca  test    ebx, ebx
0x180024ccc  jnz     loc_180024F48
0x180024cd2  lea     rcx, CfgLock; lpCriticalSection
0x180024cd9  call    cs:__imp_EnterCriticalSection
0x180024cdf  lea     r12d, [rbx+1]
0x180024ce3  cmp     [rsi+38h], edi
0x180024ce6  jz      short loc_180024CF2
0x180024ce8  mov     ebx, 389h
0x180024ced  jmp     loc_180024F48
0x180024cf2  cmp     dword ptr [rsi+18h], 2
0x180024cf6  jnz     loc_180024F43
0x180024cfc  test    [r14+4], r12b
0x180024d00  jnz     loc_180024DC3
0x180024d06  lea     r14, [rsi+68h]
0x180024d0a  test    r14, r14
0x180024d0d  jz      short loc_180024D4C
0x180024d0f  lea     rcx, [r14+10h]
0x180024d13  call    FreeCertificateBlob
0x180024d18  lea     rcx, [r14+28h]
0x180024d1c  call    FreeCertificateBlob
0x180024d21  mov     r15, [r14+20h]
0x180024d25  test    r15, r15
0x180024d28  jz      short loc_180024D3E
0x180024d2a  call    cs:__imp_GetProcessHeap
0x180024d30  mov     rcx, rax; hHeap
0x180024d33  mov     r8, r15; lpMem
0x180024d36  xor     edx, edx; dwFlags
0x180024d38  call    cs:__imp_HeapFree
0x180024d3e  xor     edx, edx; Val
0x180024d40  lea     r8d, [rdx+58h]; Size
0x180024d44  mov     rcx, r14; void *
0x180024d47  call    memset_0
0x180024d4c  xor     r9d, r9d; Reserved
0x180024d4f  xor     r8d, r8d; samDesired
0x180024d52  lea     rdx, c_KEYNAME_IKEv2_CUSTOM_POLICY; "IKEv2CustomPolicy"
0x180024d59  mov     rcx, [rsi+28h]; hKey
0x180024d5d  call    cs:__imp_RegDeleteKeyExW
0x180024d63  mov     [r14], edi
0x180024d66  lea     rdx, c_VALNAME_MC_CERTIFICATE_NAME; "MachineCertificateName"
0x180024d6d  mov     rcx, [rsi+28h]; hKey
0x180024d71  call    cs:__imp_RegDeleteValueW
0x180024d77  lea     rdx, c_VALNAME_MC_CERTIFICATE_HASH; "MachineCertificateHash"
0x180024d7e  mov     rcx, [rsi+28h]; hKey
0x180024d82  call    cs:__imp_RegDeleteValueW
0x180024d88  lea     rdx, c_VALNAME_SALIFETIME; "SaLifeTime"
0x180024d8f  mov     rcx, [rsi+28h]; hKey
0x180024d93  call    cs:__imp_RegDeleteValueW
0x180024d99  lea     rdx, c_VALNAME_MMSALIFETIME; "MmSaLifeTime"
0x180024da0  mov     rcx, [rsi+28h]; hKey
0x180024da4  call    cs:__imp_RegDeleteValueW
0x180024daa  lea     rdx, c_VALNAME_SAMAXDATASIZE; "SaMaxDataSize"
0x180024db1  mov     rcx, [rsi+28h]; hKey
0x180024db5  call    cs:__imp_RegDeleteValueW
0x180024dbb  mov     [rsi+64h], edi
0x180024dbe  jmp     loc_180024F48
0x180024dc3  lea     r15, [r14+8]
0x180024dc7  test    r15, r15
0x180024dca  jz      loc_180024F43
0x180024dd0  mov     r13d, 4
0x180024dd6  mov     [rsp+78h+cbData], r13d; cbData
0x180024ddb  mov     [rsp+78h+lpData], r15; lpData
0x180024de0  mov     r9d, r13d; dwType
0x180024de3  xor     r8d, r8d; Reserved
0x180024de6  lea     rdx, c_VALNAME_SALIFETIME; "SaLifeTime"
0x180024ded  mov     rcx, [rsi+28h]; hKey
0x180024df1  call    cs:__imp_RegSetValueExW
0x180024df7  mov     ebx, eax
0x180024df9  test    eax, eax
0x180024dfb  jnz     loc_180024F48
0x180024e01  lea     rax, [r15+30h]
0x180024e05  mov     [rsp+78h+cbData], r13d; cbData
0x180024e0a  mov     [rsp+78h+lpData], rax; lpData
0x180024e0f  mov     r9d, r13d; dwType
0x180024e12  xor     r8d, r8d; Reserved
0x180024e15  lea     rdx, c_VALNAME_MMSALIFETIME; "MmSaLifeTime"
0x180024e1c  mov     rcx, [rsi+28h]; hKey
0x180024e20  call    cs:__imp_RegSetValueExW
0x180024e26  mov     ebx, eax
0x180024e28  test    eax, eax
0x180024e2a  jnz     loc_180024F48
0x180024e30  lea     rax, [r15+4]
0x180024e34  mov     [rsp+78h+cbData], r13d; cbData
0x180024e39  mov     [rsp+78h+lpData], rax; lpData
0x180024e3e  mov     r9d, r13d; dwType
0x180024e41  xor     r8d, r8d; Reserved
0x180024e44  lea     rdx, c_VALNAME_SAMAXDATASIZE; "SaMaxDataSize"
0x180024e4b  mov     rcx, [rsi+28h]; hKey
0x180024e4f  call    cs:__imp_RegSetValueExW
0x180024e55  mov     ebx, eax
0x180024e57  test    eax, eax
0x180024e59  jnz     loc_180024F48
0x180024e5f  cmp     byte ptr [r14], 2
0x180024e63  jnz     short loc_180024E95
0x180024e65  mov     rcx, [r15+28h]
0x180024e69  test    rcx, rcx
0x180024e6c  jz      short loc_180024E95
0x180024e6e  mov     eax, [r15+20h]
0x180024e72  mov     [rsp+78h+cbData], eax; cbData
0x180024e76  mov     [rsp+78h+lpData], rcx; lpData
0x180024e7b  lea     r9d, [r13-1]; dwType
0x180024e7f  xor     r8d, r8d; Reserved
0x180024e82  lea     rdx, c_VALNAME_MC_CERTIFICATE_HASH; "MachineCertificateHash"
0x180024e89  mov     rcx, [rsi+28h]; hKey
0x180024e8d  call    cs:__imp_RegSetValueExW
0x180024e93  jmp     short loc_180024EA6
0x180024e95  lea     rdx, c_VALNAME_MC_CERTIFICATE_HASH; "MachineCertificateHash"
0x180024e9c  mov     rcx, [rsi+28h]; hKey
0x180024ea0  call    cs:__imp_RegDeleteValueW
0x180024ea6  mov     rcx, [r15+10h]
0x180024eaa  lea     rdx, c_VALNAME_MC_CERTIFICATE_NAME; "MachineCertificateName"
0x180024eb1  test    rcx, rcx
0x180024eb4  jz      short loc_180024EDA
0x180024eb6  mov     eax, [r15+8]
0x180024eba  mov     [rsp+78h+cbData], eax; cbData
0x180024ebe  mov     [rsp+78h+lpData], rcx; lpData
0x180024ec3  mov     r9d, 3; dwType
0x180024ec9  xor     r8d, r8d; Reserved
0x180024ecc  mov     rcx, [rsi+28h]; hKey
0x180024ed0  call    cs:__imp_RegSetValueExW
0x180024ed6  mov     ebx, eax
0x180024ed8  jmp     short loc_180024EEC
0x180024eda  mov     rcx, [rsi+28h]; hKey
0x180024ede  call    cs:__imp_RegDeleteValueW
0x180024ee4  mov     ebx, eax
0x180024ee6  cmp     eax, 2
0x180024ee9  cmovz   ebx, edi
0x180024eec  test    ebx, ebx
0x180024eee  jnz     short loc_180024F48
0x180024ef0  mov     rdx, [r15+18h]
0x180024ef4  mov     rcx, [rsi+28h]; hKey
0x180024ef8  test    rdx, rdx
0x180024efb  jz      short loc_180024F0A
0x180024efd  call    SetIkev2CustomPolicy
0x180024f02  mov     ebx, eax
0x180024f04  test    eax, eax
0x180024f06  jnz     short loc_180024F48
0x180024f08  jmp     short loc_180024F1D
0x180024f0a  xor     r9d, r9d; Reserved
0x180024f0d  xor     r8d, r8d; samDesired
0x180024f10  lea     rdx, c_KEYNAME_IKEv2_CUSTOM_POLICY; "IKEv2CustomPolicy"
0x180024f17  call    cs:__imp_RegDeleteKeyExW
0x180024f1d  lea     rdx, [r15+38h]
0x180024f21  cmp     [rdx], edi
0x180024f23  jnz     short loc_180024F2B
0x180024f25  cmp     [r15+3Ch], edi
0x180024f29  jz      short loc_180024F36
0x180024f2b  mov     rcx, [rsi+28h]; hKey
0x180024f2f  call    SetIkev2TrafficSelectors
0x180024f34  mov     ebx, eax
0x180024f36  test    ebx, ebx
0x180024f38  jnz     short loc_180024F48
0x180024f3a  mov     [rsi+64h], edi
0x180024f3d  mov     [rsi+68h], r12d
0x180024f41  jmp     short loc_180024F48
0x180024f43  mov     ebx, 57h ; 'W'
0x180024f48  test    r12d, r12d
0x180024f4b  jz      short loc_180024F5A
0x180024f4d  lea     rcx, CfgLock; lpCriticalSection
0x180024f54  call    cs:__imp_LeaveCriticalSection
0x180024f5a  mov     eax, ebx
0x180024f5c  add     rsp, 40h
0x180024f60  pop     r15
0x180024f62  pop     r14
0x180024f64  pop     r13
0x180024f66  pop     r12
0x180024f68  pop     rdi
0x180024f69  pop     rsi
0x180024f6a  pop     rbx
0x180024f6b  retn
```
