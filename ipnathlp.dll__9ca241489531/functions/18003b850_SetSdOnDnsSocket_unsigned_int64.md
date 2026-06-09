# SetSdOnDnsSocket(unsigned __int64)

- ea: `0x18003b850`
- end: `0x18003ba2b`
- name: `?SetSdOnDnsSocket@@YAK_K@Z`
- size: `475`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002aaa0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18003b850`
- `0x18003ba34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ba18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ba18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b99b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b99b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003b87d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003b87d`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18003b991`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18003b991`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003b940`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003b940`

## pseudocode

```c
__int64 __fastcall SetSdOnDnsSocket(HANDLE Handle)
{
  DWORD LastError; // ebx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  HANDLE ProcessHeap; // rax
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]
  PACL pDacl; // [rsp+68h] [rbp+10h] BYREF

  pDacl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v8 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
    }
    return LastError;
  }
  LastError = SetAclPerms(&pDacl);
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v4 = 27;
LABEL_11:
      WPP_SF_d(v3[2], v4, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
    }
  }
  else if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
  {
    if ( SetKernelObjectSecurity(Handle, 4u, pSecurityDescriptor) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
      }
      goto LABEL_26;
    }
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v4 = 29;
      goto LABEL_11;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v4 = 28;
      goto LABEL_11;
    }
  }
LABEL_26:
  if ( pDacl )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, pDacl);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003b850  mov     r11, rsp
0x18003b853  mov     [r11+8], rbx
0x18003b857  push    rsi
0x18003b858  sub     rsp, 50h
0x18003b85c  xor     eax, eax
0x18003b85e  xorps   xmm0, xmm0
0x18003b861  mov     rsi, rcx
0x18003b864  mov     [r11+10h], rax
0x18003b868  movups  [rsp+58h+pSecurityDescriptor], xmm0
0x18003b86d  lea     rcx, [r11-38h]; pSecurityDescriptor
0x18003b871  movups  [rsp+58h+var_28], xmm0
0x18003b876  lea     edx, [rax+1]; dwRevision
0x18003b879  mov     [r11-18h], rax
0x18003b87d  call    cs:__imp_InitializeSecurityDescriptor
0x18003b883  test    eax, eax
0x18003b885  jnz     short loc_18003B8D7
0x18003b887  call    cs:__imp_GetLastError
0x18003b88d  mov     ebx, eax
0x18003b88f  mov     rax, cs:WPP_GLOBAL_Control
0x18003b896  lea     rcx, WPP_GLOBAL_Control
0x18003b89d  cmp     rax, rcx
0x18003b8a0  jz      loc_18003BA1E
0x18003b8a6  test    byte ptr [rax+1Ch], 8
0x18003b8aa  jz      loc_18003BA1E
0x18003b8b0  cmp     byte ptr [rax+19h], 4
0x18003b8b4  jb      loc_18003BA1E
0x18003b8ba  mov     rcx, [rax+10h]
0x18003b8be  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003b8c5  mov     edx, 1Ah
0x18003b8ca  mov     r9d, ebx
0x18003b8cd  call    WPP_SF_d
0x18003b8d2  jmp     loc_18003BA1E
0x18003b8d7  lea     rcx, [rsp+58h+pDacl]; struct _ACL **
0x18003b8dc  call    ?SetAclPerms@@YAKPEAPEAU_ACL@@@Z; SetAclPerms(_ACL * *)
0x18003b8e1  mov     ebx, eax
0x18003b8e3  test    eax, eax
0x18003b8e5  jz      short loc_18003B92F
0x18003b8e7  mov     rax, cs:WPP_GLOBAL_Control
0x18003b8ee  lea     rcx, WPP_GLOBAL_Control
0x18003b8f5  cmp     rax, rcx
0x18003b8f8  jz      loc_18003BA00
0x18003b8fe  test    byte ptr [rax+1Ch], 8
0x18003b902  jz      loc_18003BA00
0x18003b908  cmp     byte ptr [rax+19h], 4
0x18003b90c  jb      loc_18003BA00
0x18003b912  mov     edx, 1Bh
0x18003b917  mov     rcx, [rax+10h]
0x18003b91b  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003b922  mov     r9d, ebx
0x18003b925  call    WPP_SF_d
0x18003b92a  jmp     loc_18003BA00
0x18003b92f  mov     r8, [rsp+58h+pDacl]; pDacl
0x18003b934  lea     rcx, [rsp+58h+pSecurityDescriptor]; pSecurityDescriptor
0x18003b939  xor     r9d, r9d; bDaclDefaulted
0x18003b93c  lea     edx, [r9+1]; bDaclPresent
0x18003b940  call    cs:__imp_SetSecurityDescriptorDacl
0x18003b946  test    eax, eax
0x18003b948  jnz     short loc_18003B984
0x18003b94a  call    cs:__imp_GetLastError
0x18003b950  mov     ebx, eax
0x18003b952  mov     rax, cs:WPP_GLOBAL_Control
0x18003b959  lea     rcx, WPP_GLOBAL_Control
0x18003b960  cmp     rax, rcx
0x18003b963  jz      loc_18003BA00
0x18003b969  test    byte ptr [rax+1Ch], 8
0x18003b96d  jz      loc_18003BA00
0x18003b973  cmp     byte ptr [rax+19h], 4
0x18003b977  jb      loc_18003BA00
0x18003b97d  mov     edx, 1Ch
0x18003b982  jmp     short loc_18003B917
0x18003b984  lea     r8, [rsp+58h+pSecurityDescriptor]; SecurityDescriptor
0x18003b989  mov     edx, 4; SecurityInformation
0x18003b98e  mov     rcx, rsi; Handle
0x18003b991  call    cs:__imp_SetKernelObjectSecurity
0x18003b997  test    eax, eax
0x18003b999  jnz     short loc_18003B9CC
0x18003b99b  call    cs:__imp_GetLastError
0x18003b9a1  mov     ebx, eax
0x18003b9a3  mov     rax, cs:WPP_GLOBAL_Control
0x18003b9aa  lea     rcx, WPP_GLOBAL_Control
0x18003b9b1  cmp     rax, rcx
0x18003b9b4  jz      short loc_18003BA00
0x18003b9b6  test    byte ptr [rax+1Ch], 8
0x18003b9ba  jz      short loc_18003BA00
0x18003b9bc  cmp     byte ptr [rax+19h], 4
0x18003b9c0  jb      short loc_18003BA00
0x18003b9c2  mov     edx, 1Dh
0x18003b9c7  jmp     loc_18003B917
0x18003b9cc  mov     rax, cs:WPP_GLOBAL_Control
0x18003b9d3  lea     rcx, WPP_GLOBAL_Control
0x18003b9da  cmp     rax, rcx
0x18003b9dd  jz      short loc_18003BA00
0x18003b9df  test    byte ptr [rax+1Ch], 8
0x18003b9e3  jz      short loc_18003BA00
0x18003b9e5  cmp     byte ptr [rax+19h], 4
0x18003b9e9  jb      short loc_18003BA00
0x18003b9eb  mov     rcx, [rax+10h]
0x18003b9ef  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003b9f6  mov     edx, 1Eh
0x18003b9fb  call    WPP_SF_
0x18003ba00  cmp     [rsp+58h+pDacl], 0
0x18003ba06  jz      short loc_18003BA1E
0x18003ba08  call    cs:__imp_GetProcessHeap
0x18003ba0e  mov     r8, [rsp+58h+pDacl]; lpMem
0x18003ba13  xor     edx, edx; dwFlags
0x18003ba15  mov     rcx, rax; hHeap
0x18003ba18  call    cs:__imp_HeapFree
0x18003ba1e  mov     eax, ebx
0x18003ba20  mov     rbx, [rsp+58h+arg_0]
0x18003ba25  add     rsp, 50h
0x18003ba29  pop     rsi
0x18003ba2a  retn
```
