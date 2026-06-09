# RasLsaWriteDialParamsBlob

- ea: `0x1800b2ec4`
- end: `0x1800b312f`
- name: `RasLsaWriteDialParamsBlob`
- size: `619`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b3138`
- `0x1800b3620`

## callees

- `0x1800b1c64`
- `0x1800b2a98`
- `0x1800b2ec4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b2fbd`
- `ntdll!RtlNtStatusToDosError` at `0x1800b311f`
- `ntdll!RtlNtStatusToDosError` at `0x1800b2fbd`
- `ntdll!RtlNtStatusToDosError` at `0x1800b311f`
- `ntdll!RtlInitUnicodeString` at `0x1800b301d`
- `ntdll!RtlInitUnicodeString` at `0x1800b30a2`
- `ntdll!RtlInitUnicodeString` at `0x1800b301d`
- `ntdll!RtlInitUnicodeString` at `0x1800b30a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2f4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2f37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2faf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b30e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2faf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b30e3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800b2f86`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800b2f86`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800b3052`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800b30b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800b3052`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800b30b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b30f3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b30f3`

## pseudocode

```c
ULONG __fastcall RasLsaWriteDialParamsBlob(__int64 a1, __int64 a2, WCHAR *a3, unsigned int a4, int a5)
{
  __int64 v5; // rax
  unsigned int v9; // r12d
  SIZE_T v10; // rbx
  _BYTE *v11; // rdi
  NTSTATUS v13; // esi
  _BYTE *i; // rcx
  unsigned int v15; // esi
  unsigned int v16; // r12d
  NTSTATUS v17; // eax
  __int64 v18; // r9
  ULONG v19; // esi
  _BYTE *j; // rax
  PVOID PolicyHandle; // [rsp+30h] [rbp-41h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+38h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-29h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-19h] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+5Fh]

  LODWORD(v5) = 0;
  PolicyHandle = 0;
  DestinationString = 0;
  PrivateData = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(a1 + 2 * v5) );
  }
  v9 = v5 + 64;
  v10 = 2LL * (unsigned int)(v5 + 64);
  v25 = v5 + 64;
  v11 = LocalAlloc(0x40u, v10);
  if ( !v11 )
    return GetLastError();
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = LsaOpenPolicy(0, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v13 )
  {
    for ( i = v11; v10; --v10 )
      *i++ = 0;
    LocalFree(v11);
    return RtlNtStatusToDosError(v13);
  }
  else
  {
    v15 = 0;
    if ( a3 && !(unsigned int)RasLsaIsPasswordSavingDisabled() && a4 )
    {
      while ( !(unsigned int)FormatKey(v11, v9, a1, v15, a5) )
      {
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v11);
        PrivateData.Buffer = a3;
        v16 = a4;
        if ( a4 > 0xFFFF )
          v16 = 0xFFFF;
        PrivateData.MaximumLength = v16;
        PrivateData.Length = v16;
        v17 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v17 )
        {
          v19 = RtlNtStatusToDosError(v17);
          goto LABEL_21;
        }
        ++v15;
        a3 = (WCHAR *)((char *)a3 + v16);
        a4 -= v16;
        v9 = v25;
        if ( !a4 )
          goto LABEL_18;
      }
    }
    else
    {
      do
      {
LABEL_18:
        v18 = v15++;
        if ( (unsigned int)FormatKey(v11, v9, a1, v18, a5) )
          break;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v11);
      }
      while ( !LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, 0) );
    }
    v19 = 0;
LABEL_21:
    for ( j = v11; v10; --v10 )
      *j++ = 0;
    LocalFree(v11);
    LsaClose(PolicyHandle);
    return v19;
  }
}

```

## disassembly

```asm
0x1800b2ec4  mov     [rsp-8+arg_10], rbx
0x1800b2ec9  mov     [rsp-8+arg_8], edx
0x1800b2ecd  push    rbp
0x1800b2ece  push    rsi
0x1800b2ecf  push    rdi
0x1800b2ed0  push    r12
0x1800b2ed2  push    r13
0x1800b2ed4  push    r14
0x1800b2ed6  push    r15
0x1800b2ed8  lea     rbp, [rsp-1Fh]
0x1800b2edd  sub     rsp, 90h
0x1800b2ee4  xorps   xmm0, xmm0
0x1800b2ee7  xor     esi, esi
0x1800b2ee9  xor     eax, eax
0x1800b2eeb  mov     [rbp+4Fh+PolicyHandle], rsi
0x1800b2eef  xorps   xmm1, xmm1
0x1800b2ef2  mov     r15d, r9d
0x1800b2ef5  mov     r13, r8
0x1800b2ef8  mov     r14, rcx
0x1800b2efb  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800b2eff  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800b2f03  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800b2f07  movups  xmmword ptr [rbp+4Fh+PrivateData.Length], xmm1
0x1800b2f0b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800b2f0f  test    rcx, rcx
0x1800b2f12  jz      short loc_1800B2F21
0x1800b2f14  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b2f18  inc     rax
0x1800b2f1b  cmp     [rcx+rax*2], si
0x1800b2f1f  jnz     short loc_1800B2F18
0x1800b2f21  lea     r12d, [rax+40h]
0x1800b2f25  mov     ecx, 40h ; '@'; uFlags
0x1800b2f2a  mov     ebx, r12d
0x1800b2f2d  add     rbx, rbx
0x1800b2f30  mov     [rbp+4Fh+arg_0], r12d
0x1800b2f34  mov     rdx, rbx; uBytes
0x1800b2f37  call    cs:__imp_LocalAlloc
0x1800b2f3e  nop     dword ptr [rax+rax+00h]
0x1800b2f43  mov     rdi, rax
0x1800b2f46  test    rax, rax
0x1800b2f49  jnz     short loc_1800B2F5C
0x1800b2f4b  call    cs:__imp_GetLastError
0x1800b2f52  nop     dword ptr [rax+rax+00h]
0x1800b2f57  jmp     loc_1800B3101
0x1800b2f5c  xorps   xmm0, xmm0
0x1800b2f5f  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800b2f66  lea     r9, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800b2f6a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x1800b2f6e  mov     r8d, 207F8h; DesiredAccess
0x1800b2f74  mov     [rbp+4Fh+ObjectAttributes.Attributes], esi
0x1800b2f77  lea     rdx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800b2f7b  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rsi
0x1800b2f7f  xor     ecx, ecx; SystemName
0x1800b2f81  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b2f86  call    cs:__imp_LsaOpenPolicy
0x1800b2f8d  nop     dword ptr [rax+rax+00h]
0x1800b2f92  mov     esi, eax
0x1800b2f94  test    eax, eax
0x1800b2f96  jz      short loc_1800B2FCE
0x1800b2f98  mov     rcx, rdi
0x1800b2f9b  test    rbx, rbx
0x1800b2f9e  jz      short loc_1800B2FAC
0x1800b2fa0  mov     byte ptr [rcx], 0
0x1800b2fa3  inc     rcx
0x1800b2fa6  sub     rbx, 1
0x1800b2faa  jnz     short loc_1800B2FA0
0x1800b2fac  mov     rcx, rdi; hMem
0x1800b2faf  call    cs:__imp_LocalFree
0x1800b2fb6  nop     dword ptr [rax+rax+00h]
0x1800b2fbb  mov     ecx, esi; Status
0x1800b2fbd  call    cs:__imp_RtlNtStatusToDosError
0x1800b2fc4  nop     dword ptr [rax+rax+00h]
0x1800b2fc9  jmp     loc_1800B3101
0x1800b2fce  xor     esi, esi
0x1800b2fd0  mov     [rbp+4Fh+arg_8], 0
0x1800b2fd7  test    r13, r13
0x1800b2fda  jz      loc_1800B307B
0x1800b2fe0  call    RasLsaIsPasswordSavingDisabled
0x1800b2fe5  test    eax, eax
0x1800b2fe7  jnz     loc_1800B307B
0x1800b2fed  test    r15d, r15d
0x1800b2ff0  jz      loc_1800B307B
0x1800b2ff6  mov     eax, [rbp+4Fh+arg_20]
0x1800b2ff9  mov     r9d, esi
0x1800b2ffc  mov     r8, r14
0x1800b2fff  mov     [rsp+0C0h+var_A0], eax
0x1800b3003  mov     edx, r12d
0x1800b3006  mov     rcx, rdi
0x1800b3009  call    FormatKey
0x1800b300e  test    eax, eax
0x1800b3010  jnz     loc_1800B30C9
0x1800b3016  mov     rdx, rdi; SourceString
0x1800b3019  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800b301d  call    cs:__imp_RtlInitUnicodeString
0x1800b3024  nop     dword ptr [rax+rax+00h]
0x1800b3029  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800b302d  lea     r8, [rbp+4Fh+PrivateData]; PrivateData
0x1800b3031  mov     eax, 0FFFFh
0x1800b3036  mov     [rbp+4Fh+PrivateData.Buffer], r13
0x1800b303a  cmp     r15d, eax
0x1800b303d  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800b3041  mov     r12d, r15d
0x1800b3044  cmova   r12d, eax
0x1800b3048  mov     [rbp+4Fh+PrivateData.MaximumLength], r12w
0x1800b304d  mov     [rbp+4Fh+PrivateData.Length], r12w
0x1800b3052  call    cs:__imp_LsaStorePrivateData
0x1800b3059  nop     dword ptr [rax+rax+00h]
0x1800b305e  test    eax, eax
0x1800b3060  jnz     loc_1800B311D
0x1800b3066  mov     eax, r12d
0x1800b3069  inc     esi
0x1800b306b  add     r13, rax
0x1800b306e  sub     r15d, r12d
0x1800b3071  mov     r12d, [rbp+4Fh+arg_0]
0x1800b3075  jnz     loc_1800B2FF6
0x1800b307b  mov     r15d, [rbp+4Fh+arg_20]
0x1800b307f  mov     r9d, esi
0x1800b3082  mov     [rsp+0C0h+var_A0], r15d
0x1800b3087  mov     r8, r14
0x1800b308a  mov     edx, r12d
0x1800b308d  mov     rcx, rdi
0x1800b3090  inc     esi
0x1800b3092  call    FormatKey
0x1800b3097  test    eax, eax
0x1800b3099  jnz     short loc_1800B30C9
0x1800b309b  mov     rdx, rdi; SourceString
0x1800b309e  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800b30a2  call    cs:__imp_RtlInitUnicodeString
0x1800b30a9  nop     dword ptr [rax+rax+00h]
0x1800b30ae  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800b30b2  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800b30b6  xor     r8d, r8d; PrivateData
0x1800b30b9  call    cs:__imp_LsaStorePrivateData
0x1800b30c0  nop     dword ptr [rax+rax+00h]
0x1800b30c5  test    eax, eax
0x1800b30c7  jz      short loc_1800B307F
0x1800b30c9  mov     esi, [rbp+4Fh+arg_8]
0x1800b30cc  mov     rax, rdi
0x1800b30cf  test    rbx, rbx
0x1800b30d2  jz      short loc_1800B30E0
0x1800b30d4  mov     byte ptr [rax], 0
0x1800b30d7  inc     rax
0x1800b30da  sub     rbx, 1
0x1800b30de  jnz     short loc_1800B30D4
0x1800b30e0  mov     rcx, rdi; hMem
0x1800b30e3  call    cs:__imp_LocalFree
0x1800b30ea  nop     dword ptr [rax+rax+00h]
0x1800b30ef  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x1800b30f3  call    cs:__imp_LsaClose
0x1800b30fa  nop     dword ptr [rax+rax+00h]
0x1800b30ff  mov     eax, esi
0x1800b3101  mov     rbx, [rsp+0C0h+arg_10]
0x1800b3109  add     rsp, 90h
0x1800b3110  pop     r15
0x1800b3112  pop     r14
0x1800b3114  pop     r13
0x1800b3116  pop     r12
0x1800b3118  pop     rdi
0x1800b3119  pop     rsi
0x1800b311a  pop     rbp
0x1800b311b  retn
0x1800b311d  mov     ecx, eax; Status
0x1800b311f  call    cs:__imp_RtlNtStatusToDosError
0x1800b3126  nop     dword ptr [rax+rax+00h]
0x1800b312b  mov     esi, eax
0x1800b312d  jmp     short loc_1800B30CC
```
