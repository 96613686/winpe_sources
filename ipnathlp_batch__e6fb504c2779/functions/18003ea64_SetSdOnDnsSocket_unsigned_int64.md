# SetSdOnDnsSocket(unsigned __int64)

- ea: `0x18003ea64`
- end: `0x18003ec70`
- name: `?SetSdOnDnsSocket@@YAK_K@Z`
- size: `524`
- prototype: `unsigned int __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f120`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003ea64`
- `0x18003ec78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ec40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ec40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ec56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ec56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebcd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003ea91`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003ea91`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18003ebbd`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18003ebbd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003eb60`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003eb60`

## pseudocode

```c
__int64 __fastcall SetSdOnDnsSocket(HANDLE Handle)
{
  unsigned int LastError; // ebx
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
0x18003ea64  mov     r11, rsp
0x18003ea67  mov     [r11+8], rbx
0x18003ea6b  push    rsi
0x18003ea6c  sub     rsp, 50h
0x18003ea70  xor     eax, eax
0x18003ea72  xorps   xmm0, xmm0
0x18003ea75  mov     rsi, rcx
0x18003ea78  mov     [r11+10h], rax
0x18003ea7c  movups  [rsp+58h+pSecurityDescriptor], xmm0
0x18003ea81  lea     rcx, [r11-38h]; pSecurityDescriptor
0x18003ea85  movups  [rsp+58h+var_28], xmm0
0x18003ea8a  lea     edx, [rax+1]; dwRevision
0x18003ea8d  mov     [r11-18h], rax
0x18003ea91  call    cs:__imp_InitializeSecurityDescriptor
0x18003ea98  nop     dword ptr [rax+rax+00h]
0x18003ea9d  test    eax, eax
0x18003ea9f  jnz     short loc_18003EAF7
0x18003eaa1  call    cs:__imp_GetLastError
0x18003eaa8  nop     dword ptr [rax+rax+00h]
0x18003eaad  mov     ebx, eax
0x18003eaaf  mov     rax, cs:WPP_GLOBAL_Control
0x18003eab6  lea     rcx, WPP_GLOBAL_Control
0x18003eabd  cmp     rax, rcx
0x18003eac0  jz      loc_18003EC62
0x18003eac6  test    byte ptr [rax+1Ch], 8
0x18003eaca  jz      loc_18003EC62
0x18003ead0  cmp     byte ptr [rax+19h], 4
0x18003ead4  jb      loc_18003EC62
0x18003eada  mov     rcx, [rax+10h]
0x18003eade  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003eae5  mov     edx, 1Ah
0x18003eaea  mov     r9d, ebx
0x18003eaed  call    WPP_SF_d
0x18003eaf2  jmp     loc_18003EC62
0x18003eaf7  lea     rcx, [rsp+58h+pDacl]; struct _ACL **
0x18003eafc  call    ?SetAclPerms@@YAKPEAPEAU_ACL@@@Z; SetAclPerms(_ACL * *)
0x18003eb01  mov     ebx, eax
0x18003eb03  test    eax, eax
0x18003eb05  jz      short loc_18003EB4F
0x18003eb07  mov     rax, cs:WPP_GLOBAL_Control
0x18003eb0e  lea     rcx, WPP_GLOBAL_Control
0x18003eb15  cmp     rax, rcx
0x18003eb18  jz      loc_18003EC38
0x18003eb1e  test    byte ptr [rax+1Ch], 8
0x18003eb22  jz      loc_18003EC38
0x18003eb28  cmp     byte ptr [rax+19h], 4
0x18003eb2c  jb      loc_18003EC38
0x18003eb32  mov     edx, 1Bh
0x18003eb37  mov     rcx, [rax+10h]
0x18003eb3b  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003eb42  mov     r9d, ebx
0x18003eb45  call    WPP_SF_d
0x18003eb4a  jmp     loc_18003EC38
0x18003eb4f  mov     r8, [rsp+58h+pDacl]; pDacl
0x18003eb54  lea     rcx, [rsp+58h+pSecurityDescriptor]; pSecurityDescriptor
0x18003eb59  xor     r9d, r9d; bDaclDefaulted
0x18003eb5c  lea     edx, [r9+1]; bDaclPresent
0x18003eb60  call    cs:__imp_SetSecurityDescriptorDacl
0x18003eb67  nop     dword ptr [rax+rax+00h]
0x18003eb6c  test    eax, eax
0x18003eb6e  jnz     short loc_18003EBB0
0x18003eb70  call    cs:__imp_GetLastError
0x18003eb77  nop     dword ptr [rax+rax+00h]
0x18003eb7c  mov     ebx, eax
0x18003eb7e  mov     rax, cs:WPP_GLOBAL_Control
0x18003eb85  lea     rcx, WPP_GLOBAL_Control
0x18003eb8c  cmp     rax, rcx
0x18003eb8f  jz      loc_18003EC38
0x18003eb95  test    byte ptr [rax+1Ch], 8
0x18003eb99  jz      loc_18003EC38
0x18003eb9f  cmp     byte ptr [rax+19h], 4
0x18003eba3  jb      loc_18003EC38
0x18003eba9  mov     edx, 1Ch
0x18003ebae  jmp     short loc_18003EB37
0x18003ebb0  lea     r8, [rsp+58h+pSecurityDescriptor]; SecurityDescriptor
0x18003ebb5  mov     edx, 4; SecurityInformation
0x18003ebba  mov     rcx, rsi; Handle
0x18003ebbd  call    cs:__imp_SetKernelObjectSecurity
0x18003ebc4  nop     dword ptr [rax+rax+00h]
0x18003ebc9  test    eax, eax
0x18003ebcb  jnz     short loc_18003EC04
0x18003ebcd  call    cs:__imp_GetLastError
0x18003ebd4  nop     dword ptr [rax+rax+00h]
0x18003ebd9  mov     ebx, eax
0x18003ebdb  mov     rax, cs:WPP_GLOBAL_Control
0x18003ebe2  lea     rcx, WPP_GLOBAL_Control
0x18003ebe9  cmp     rax, rcx
0x18003ebec  jz      short loc_18003EC38
0x18003ebee  test    byte ptr [rax+1Ch], 8
0x18003ebf2  jz      short loc_18003EC38
0x18003ebf4  cmp     byte ptr [rax+19h], 4
0x18003ebf8  jb      short loc_18003EC38
0x18003ebfa  mov     edx, 1Dh
0x18003ebff  jmp     loc_18003EB37
0x18003ec04  mov     rax, cs:WPP_GLOBAL_Control
0x18003ec0b  lea     rcx, WPP_GLOBAL_Control
0x18003ec12  cmp     rax, rcx
0x18003ec15  jz      short loc_18003EC38
0x18003ec17  test    byte ptr [rax+1Ch], 8
0x18003ec1b  jz      short loc_18003EC38
0x18003ec1d  cmp     byte ptr [rax+19h], 4
0x18003ec21  jb      short loc_18003EC38
0x18003ec23  mov     rcx, [rax+10h]
0x18003ec27  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003ec2e  mov     edx, 1Eh
0x18003ec33  call    WPP_SF_
0x18003ec38  cmp     [rsp+58h+pDacl], 0
0x18003ec3e  jz      short loc_18003EC62
0x18003ec40  call    cs:__imp_GetProcessHeap
0x18003ec47  nop     dword ptr [rax+rax+00h]
0x18003ec4c  mov     r8, [rsp+58h+pDacl]; lpMem
0x18003ec51  xor     edx, edx; dwFlags
0x18003ec53  mov     rcx, rax; hHeap
0x18003ec56  call    cs:__imp_HeapFree
0x18003ec5d  nop     dword ptr [rax+rax+00h]
0x18003ec62  mov     eax, ebx
0x18003ec64  mov     rbx, [rsp+58h+arg_0]
0x18003ec69  add     rsp, 50h
0x18003ec6d  pop     rsi
0x18003ec6e  retn
```
