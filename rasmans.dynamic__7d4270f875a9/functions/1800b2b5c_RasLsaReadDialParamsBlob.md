# RasLsaReadDialParamsBlob

- ea: `0x1800b2b5c`
- end: `0x1800b2e47`
- name: `RasLsaReadDialParamsBlob`
- size: `747`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b20e0`
- `0x1800b2264`
- `0x1800b3138`
- `0x1800b3620`

## callees

- `0x1800b1c64`
- `0x1800b2b5c`
- `0x1800e8e7e`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b2bd9`
- `ntdll!RtlNtStatusToDosError` at `0x1800b2d94`
- `ntdll!RtlNtStatusToDosError` at `0x1800b2bd9`
- `ntdll!RtlNtStatusToDosError` at `0x1800b2d94`
- `ntdll!RtlInitUnicodeString` at `0x1800b2c7c`
- `ntdll!RtlInitUnicodeString` at `0x1800b2c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2d77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2c16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2cc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2c16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2dc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2e10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2dc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2e10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800b2d43`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800b2dda`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800b2d43`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800b2dda`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800b2bc7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800b2bc7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800b2c94`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800b2c94`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b2c2e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b2dea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b2c2e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b2dea`

## pseudocode

```c
ULONG __fastcall RasLsaReadDialParamsBlob(__int64 a1, __int64 a2, char **a3, unsigned int *a4, int a5)
{
  char *v5; // rbx
  NTSTATUS v7; // eax
  __int64 v9; // rax
  unsigned int v10; // r15d
  WCHAR *v11; // r14
  int v12; // edi
  unsigned int v13; // esi
  unsigned int v14; // r12d
  NTSTATUS v15; // eax
  unsigned int v16; // ecx
  char *v17; // rax
  __int64 v18; // r15
  char *v19; // rcx
  DWORD LastError; // eax
  __int64 v21; // rax
  char *v22; // rcx
  WCHAR *v23; // rcx
  __int64 i; // rax
  PLSA_UNICODE_STRING PrivateData; // [rsp+38h] [rbp-41h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-39h] BYREF
  char *v27; // [rsp+48h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v30; // [rsp+E0h] [rbp+67h]

  v5 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a3 = 0;
  *a4 = 0;
  PrivateData = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  DestinationString = 0;
  v7 = LsaOpenPolicy(0, &ObjectAttributes, 0x20006u, &PolicyHandle);
  if ( v7 )
    return RtlNtStatusToDosError(v7);
  if ( a1 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a1 + 2 * v9) );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  v10 = v9 + 64;
  v30 = v9 + 64;
  v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v9 + 64));
  if ( v11 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 1;
    if ( !(unsigned int)FormatKey(v11, v10, a1, 0, a5) )
    {
      while ( 1 )
      {
        RtlInitUnicodeString(&DestinationString, v11);
        v15 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v15 )
          break;
        if ( !PrivateData )
          goto LABEL_32;
        v16 = v13 + PrivateData->Length;
        if ( v16 < v13 )
        {
          v12 = 534;
          goto LABEL_26;
        }
        v17 = (char *)LocalAlloc(0x40u, v16);
        v27 = v17;
        if ( !v17 )
        {
          LastError = GetLastError();
          goto LABEL_25;
        }
        if ( v5 )
        {
          v18 = v13;
          memcpy_0(v17, v5, v13);
          v19 = v5;
          if ( v13 )
          {
            do
            {
              *v19++ = 0;
              --v18;
            }
            while ( v18 );
          }
          LocalFree(v5);
          v17 = v27;
          v10 = v30;
        }
        memcpy_0(&v17[v13], PrivateData->Buffer, PrivateData->Length);
        v5 = v27;
        v13 += PrivateData->Length;
        LsaFreeMemory(PrivateData);
        PrivateData = 0;
        if ( (unsigned int)FormatKey(v11, v10, a1, v14, a5) )
          goto LABEL_30;
        ++v14;
      }
      if ( v14 > 1 )
        goto LABEL_30;
      LastError = RtlNtStatusToDosError(v15);
LABEL_25:
      v12 = LastError;
      if ( !LastError )
        goto LABEL_30;
LABEL_26:
      if ( v5 )
      {
        v21 = v13;
        v22 = v5;
        if ( v13 )
        {
          do
          {
            *v22++ = 0;
            --v21;
          }
          while ( v21 );
        }
        LocalFree(v5);
        v5 = 0;
      }
    }
LABEL_30:
    if ( PrivateData )
      LsaFreeMemory(PrivateData);
LABEL_32:
    LsaClose(PolicyHandle);
    v23 = v11;
    for ( i = 2LL * v10; i; --i )
    {
      *(_BYTE *)v23 = 0;
      v23 = (WCHAR *)((char *)v23 + 1);
    }
    LocalFree(v11);
    *a3 = v5;
    *a4 = v13;
    return v12;
  }
  else
  {
    LsaClose(PolicyHandle);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x1800b2b5c  mov     rax, rsp
0x1800b2b5f  mov     [rax+8], rbx
0x1800b2b63  mov     [rax+20h], r9
0x1800b2b67  mov     [rax+18h], r8
0x1800b2b6b  mov     [rax+10h], edx
0x1800b2b6e  push    rbp
0x1800b2b6f  push    rsi
0x1800b2b70  push    rdi
0x1800b2b71  push    r12
0x1800b2b73  push    r13
0x1800b2b75  push    r14
0x1800b2b77  push    r15
0x1800b2b79  lea     rbp, [rax-57h]
0x1800b2b7d  sub     rsp, 90h
0x1800b2b84  xor     ebx, ebx
0x1800b2b86  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800b2b8e  xorps   xmm0, xmm0
0x1800b2b91  mov     [r8], rbx
0x1800b2b94  mov     [r9], ebx
0x1800b2b97  lea     rdx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800b2b9b  mov     r13, rcx
0x1800b2b9e  mov     [rbp+4Fh+PrivateData], rbx
0x1800b2ba2  lea     r9, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800b2ba6  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], rbx
0x1800b2baa  mov     r8d, 20006h; DesiredAccess
0x1800b2bb0  mov     [rbp+4Fh+PolicyHandle], rbx
0x1800b2bb4  xor     ecx, ecx; SystemName
0x1800b2bb6  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rbx
0x1800b2bba  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800b2bbe  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rbx
0x1800b2bc2  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b2bc7  call    cs:__imp_LsaOpenPolicy
0x1800b2bce  nop     dword ptr [rax+rax+00h]
0x1800b2bd3  test    eax, eax
0x1800b2bd5  jz      short loc_1800B2BEA
0x1800b2bd7  mov     ecx, eax; Status
0x1800b2bd9  call    cs:__imp_RtlNtStatusToDosError
0x1800b2be0  nop     dword ptr [rax+rax+00h]
0x1800b2be5  jmp     loc_1800B2E2B
0x1800b2bea  test    r13, r13
0x1800b2bed  jz      short loc_1800B2C00
0x1800b2bef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b2bf3  inc     rax
0x1800b2bf6  cmp     [r13+rax*2+0], bx
0x1800b2bfc  jnz     short loc_1800B2BF3
0x1800b2bfe  jmp     short loc_1800B2C03
0x1800b2c00  mov     rax, rbx
0x1800b2c03  lea     r15d, [rax+40h]
0x1800b2c07  mov     ecx, 40h ; '@'; uFlags
0x1800b2c0c  mov     edx, r15d
0x1800b2c0f  add     rdx, rdx; uBytes
0x1800b2c12  mov     [rbp+4Fh+arg_8], r15d
0x1800b2c16  call    cs:__imp_LocalAlloc
0x1800b2c1d  nop     dword ptr [rax+rax+00h]
0x1800b2c22  mov     r14, rax
0x1800b2c25  test    rax, rax
0x1800b2c28  jnz     short loc_1800B2C4B
0x1800b2c2a  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x1800b2c2e  call    cs:__imp_LsaClose
0x1800b2c35  nop     dword ptr [rax+rax+00h]
0x1800b2c3a  call    cs:__imp_GetLastError
0x1800b2c41  nop     dword ptr [rax+rax+00h]
0x1800b2c46  jmp     loc_1800B2E2B
0x1800b2c4b  mov     eax, [rbp+4Fh+arg_20]
0x1800b2c4e  xor     r9d, r9d
0x1800b2c51  mov     r8, r13
0x1800b2c54  mov     [rsp+20h], eax
0x1800b2c58  mov     edx, r15d
0x1800b2c5b  mov     rcx, r14
0x1800b2c5e  mov     edi, ebx
0x1800b2c60  mov     esi, ebx
0x1800b2c62  mov     r12d, 1
0x1800b2c68  call    FormatKey
0x1800b2c6d  test    eax, eax
0x1800b2c6f  jnz     loc_1800B2DD1
0x1800b2c75  mov     rdx, r14; SourceString
0x1800b2c78  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800b2c7c  call    cs:__imp_RtlInitUnicodeString
0x1800b2c83  nop     dword ptr [rax+rax+00h]
0x1800b2c88  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800b2c8c  lea     r8, [rbp+4Fh+PrivateData]; PrivateData
0x1800b2c90  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800b2c94  call    cs:__imp_LsaRetrievePrivateData
0x1800b2c9b  nop     dword ptr [rax+rax+00h]
0x1800b2ca0  test    eax, eax
0x1800b2ca2  jnz     loc_1800B2D8C
0x1800b2ca8  mov     rcx, [rbp+4Fh+PrivateData]
0x1800b2cac  test    rcx, rcx
0x1800b2caf  jz      loc_1800B2DE6
0x1800b2cb5  movzx   ecx, word ptr [rcx]
0x1800b2cb8  add     ecx, esi
0x1800b2cba  cmp     ecx, esi
0x1800b2cbc  jb      loc_1800B2D85
0x1800b2cc2  mov     edx, ecx; uBytes
0x1800b2cc4  lea     ecx, [rax+40h]; uFlags
0x1800b2cc7  call    cs:__imp_LocalAlloc
0x1800b2cce  nop     dword ptr [rax+rax+00h]
0x1800b2cd3  mov     [rbp+4Fh+var_80], rax
0x1800b2cd7  test    rax, rax
0x1800b2cda  jz      loc_1800B2D77
0x1800b2ce0  test    rbx, rbx
0x1800b2ce3  jz      short loc_1800B2D20
0x1800b2ce5  mov     r8d, esi; Size
0x1800b2ce8  mov     rdx, rbx; Src
0x1800b2ceb  mov     rcx, rax; void *
0x1800b2cee  mov     r15d, esi
0x1800b2cf1  call    memcpy_0
0x1800b2cf6  mov     rcx, rbx
0x1800b2cf9  test    esi, esi
0x1800b2cfb  jz      short loc_1800B2D09
0x1800b2cfd  mov     [rcx], dil
0x1800b2d00  inc     rcx
0x1800b2d03  sub     r15, 1
0x1800b2d07  jnz     short loc_1800B2CFD
0x1800b2d09  mov     rcx, rbx; hMem
0x1800b2d0c  call    cs:__imp_LocalFree
0x1800b2d13  nop     dword ptr [rax+rax+00h]
0x1800b2d18  mov     rax, [rbp+4Fh+var_80]
0x1800b2d1c  mov     r15d, [rbp+4Fh+arg_8]
0x1800b2d20  mov     rdx, [rbp+4Fh+PrivateData]
0x1800b2d24  mov     ecx, esi
0x1800b2d26  add     rcx, rax; void *
0x1800b2d29  movzx   r8d, word ptr [rdx]; Size
0x1800b2d2d  mov     rdx, [rdx+8]; Src
0x1800b2d31  call    memcpy_0
0x1800b2d36  mov     rcx, [rbp+4Fh+PrivateData]; Buffer
0x1800b2d3a  mov     rbx, [rbp+4Fh+var_80]
0x1800b2d3e  movzx   eax, word ptr [rcx]
0x1800b2d41  add     esi, eax
0x1800b2d43  call    cs:__imp_LsaFreeMemory
0x1800b2d4a  nop     dword ptr [rax+rax+00h]
0x1800b2d4f  mov     eax, [rbp+4Fh+arg_20]
0x1800b2d52  mov     r9d, r12d
0x1800b2d55  mov     r8, r13
0x1800b2d58  mov     [rsp+20h], eax
0x1800b2d5c  mov     edx, r15d
0x1800b2d5f  mov     [rbp+4Fh+PrivateData], rdi
0x1800b2d63  mov     rcx, r14
0x1800b2d66  call    FormatKey
0x1800b2d6b  test    eax, eax
0x1800b2d6d  jnz     short loc_1800B2DD1
0x1800b2d6f  inc     r12d
0x1800b2d72  jmp     loc_1800B2C75
0x1800b2d77  call    cs:__imp_GetLastError
0x1800b2d7e  nop     dword ptr [rax+rax+00h]
0x1800b2d83  jmp     short loc_1800B2DA0
0x1800b2d85  mov     edi, 216h
0x1800b2d8a  jmp     short loc_1800B2DA6
0x1800b2d8c  cmp     r12d, 1
0x1800b2d90  ja      short loc_1800B2DD1
0x1800b2d92  mov     ecx, eax; Status
0x1800b2d94  call    cs:__imp_RtlNtStatusToDosError
0x1800b2d9b  nop     dword ptr [rax+rax+00h]
0x1800b2da0  mov     edi, eax
0x1800b2da2  test    eax, eax
0x1800b2da4  jz      short loc_1800B2DD1
0x1800b2da6  test    rbx, rbx
0x1800b2da9  jz      short loc_1800B2DD1
0x1800b2dab  mov     eax, esi
0x1800b2dad  mov     rcx, rbx
0x1800b2db0  test    esi, esi
0x1800b2db2  jz      short loc_1800B2DC0
0x1800b2db4  mov     byte ptr [rcx], 0
0x1800b2db7  inc     rcx
0x1800b2dba  sub     rax, 1
0x1800b2dbe  jnz     short loc_1800B2DB4
0x1800b2dc0  mov     rcx, rbx; hMem
0x1800b2dc3  call    cs:__imp_LocalFree
0x1800b2dca  nop     dword ptr [rax+rax+00h]
0x1800b2dcf  xor     ebx, ebx
0x1800b2dd1  mov     rcx, [rbp+4Fh+PrivateData]; Buffer
0x1800b2dd5  test    rcx, rcx
0x1800b2dd8  jz      short loc_1800B2DE6
0x1800b2dda  call    cs:__imp_LsaFreeMemory
0x1800b2de1  nop     dword ptr [rax+rax+00h]
0x1800b2de6  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x1800b2dea  call    cs:__imp_LsaClose
0x1800b2df1  nop     dword ptr [rax+rax+00h]
0x1800b2df6  mov     eax, r15d
0x1800b2df9  mov     rcx, r14
0x1800b2dfc  add     rax, rax
0x1800b2dff  jz      short loc_1800B2E0D
0x1800b2e01  mov     byte ptr [rcx], 0
0x1800b2e04  inc     rcx
0x1800b2e07  sub     rax, 1
0x1800b2e0b  jnz     short loc_1800B2E01
0x1800b2e0d  mov     rcx, r14; hMem
0x1800b2e10  call    cs:__imp_LocalFree
0x1800b2e17  nop     dword ptr [rax+rax+00h]
0x1800b2e1c  mov     rax, [rbp+4Fh+arg_10]
0x1800b2e20  mov     [rax], rbx
0x1800b2e23  mov     rax, [rbp+4Fh+arg_18]
0x1800b2e27  mov     [rax], esi
0x1800b2e29  mov     eax, edi
0x1800b2e2b  mov     rbx, [rsp+0C0h+arg_0]
0x1800b2e33  add     rsp, 90h
0x1800b2e3a  pop     r15
0x1800b2e3c  pop     r14
0x1800b2e3e  pop     r13
0x1800b2e40  pop     r12
0x1800b2e42  pop     rdi
0x1800b2e43  pop     rsi
0x1800b2e44  pop     rbp
0x1800b2e45  retn
```
