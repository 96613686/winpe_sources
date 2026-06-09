# RasLsaWriteDialParamsBlob

- ea: `0x180082b60`
- end: `0x180082d50`
- name: `RasLsaWriteDialParamsBlob`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180082d58`

## callees

- `0x180081d60`
- `0x1800827d0`
- `0x180082b60`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180082c18`
- `KERNEL32!LocalFree` at `0x180082d22`
- `KERNEL32!LocalFree` at `0x180082c18`
- `KERNEL32!LocalFree` at `0x180082d22`
- `KERNEL32!GetLastError` at `0x180082bc4`
- `KERNEL32!GetLastError` at `0x180082bc4`
- `KERNEL32!LocalAlloc` at `0x180082bb6`
- `KERNEL32!LocalAlloc` at `0x180082bb6`
- `ADVAPI32!LsaClose` at `0x180082d2c`
- `ADVAPI32!LsaClose` at `0x180082d2c`
- `ADVAPI32!LsaStorePrivateData` at `0x180082c9f`
- `ADVAPI32!LsaStorePrivateData` at `0x180082ce7`
- `ADVAPI32!LsaStorePrivateData` at `0x180082c9f`
- `ADVAPI32!LsaStorePrivateData` at `0x180082ce7`
- `ADVAPI32!LsaOpenPolicy` at `0x180082bfa`
- `ADVAPI32!LsaOpenPolicy` at `0x180082bfa`
- `ntdll!RtlNtStatusToDosError` at `0x180082c20`
- `ntdll!RtlNtStatusToDosError` at `0x180082cc4`
- `ntdll!RtlNtStatusToDosError` at `0x180082c20`
- `ntdll!RtlNtStatusToDosError` at `0x180082cc4`
- `ntdll!RtlInitUnicodeString` at `0x180082c70`
- `ntdll!RtlInitUnicodeString` at `0x180082cd6`
- `ntdll!RtlInitUnicodeString` at `0x180082c70`
- `ntdll!RtlInitUnicodeString` at `0x180082cd6`

## pseudocode

```c
ULONG __fastcall RasLsaWriteDialParamsBlob(__int64 a1, ULONG a2, WCHAR *a3, unsigned int a4, int a5)
{
  __int64 v5; // rsi
  _BYTE *v8; // rbx
  NTSTATUS v10; // edi
  __int64 v11; // r8
  _BYTE *v12; // rcx
  ULONG v13; // r15d
  unsigned int v14; // edi
  int v15; // r13d
  unsigned int v16; // r15d
  NTSTATUS v17; // eax
  __int64 v18; // r9
  _BYTE *v19; // rax
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+C0h] [rbp+40h] BYREF
  ULONG v24; // [rsp+C8h] [rbp+48h]

  v24 = a2;
  v5 = 128;
  PolicyHandle = 0;
  DestinationString = 0;
  PrivateData = 0;
  memset(&ObjectAttributes, 0, 44);
  v8 = LocalAlloc(0x40u, 0x80u);
  if ( !v8 )
    return GetLastError();
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = LsaOpenPolicy(0, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v10 )
  {
    v12 = v8;
    do
    {
      *v12++ = 0;
      --v5;
    }
    while ( v5 );
    LocalFree(v8);
    return RtlNtStatusToDosError(v10);
  }
  else
  {
    v24 = 0;
    v13 = 0;
    v14 = 0;
    v15 = a5;
    if ( a3 && !(unsigned int)RasLsaIsPasswordSavingDisabled() && a4 )
    {
      while ( !(unsigned int)FormatKey(v8, 64, v11, v14, v15) )
      {
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v8);
        PrivateData.Buffer = a3;
        v16 = a4;
        if ( a4 > 0xFFFF )
          v16 = 0xFFFF;
        PrivateData.MaximumLength = v16;
        PrivateData.Length = v16;
        v17 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v17 )
        {
          v13 = RtlNtStatusToDosError(v17);
          goto LABEL_22;
        }
        ++v14;
        a3 = (WCHAR *)((char *)a3 + v16);
        a4 -= v16;
        if ( !a4 )
        {
          v13 = v24;
          goto LABEL_19;
        }
      }
      v13 = v24;
    }
    else
    {
      do
      {
LABEL_19:
        v18 = v14++;
        if ( (unsigned int)FormatKey(v8, 64, v11, v18, v15) )
          break;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v8);
      }
      while ( !LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, 0) );
    }
LABEL_22:
    v19 = v8;
    do
    {
      *v19++ = 0;
      --v5;
    }
    while ( v5 );
    LocalFree(v8);
    LsaClose(PolicyHandle);
    return v13;
  }
}

```

## disassembly

```asm
0x180082b60  mov     [rsp-38h+arg_10], rbx
0x180082b65  mov     [rsp-38h+arg_8], edx
0x180082b69  mov     [rsp-38h+PolicyHandle], rcx
0x180082b6e  push    rbp
0x180082b6f  push    rsi
0x180082b70  push    rdi
0x180082b71  push    r12
0x180082b73  push    r13
0x180082b75  push    r14
0x180082b77  push    r15
0x180082b79  mov     rbp, rsp
0x180082b7c  sub     rsp, 80h
0x180082b83  xorps   xmm0, xmm0
0x180082b86  xor     eax, eax
0x180082b88  xorps   xmm1, xmm1
0x180082b8b  mov     esi, 80h
0x180082b90  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180082b94  xor     r13d, r13d
0x180082b97  mov     edx, esi; uBytes
0x180082b99  lea     ecx, [rax+40h]; uFlags
0x180082b9c  mov     [rbp+PolicyHandle], r13
0x180082ba0  mov     r14d, r9d
0x180082ba3  mov     r12, r8
0x180082ba6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180082baa  movups  xmmword ptr [rbp+PrivateData.Length], xmm1
0x180082bae  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180082bb2  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180082bb6  call    cs:__imp_LocalAlloc
0x180082bbc  mov     rbx, rax
0x180082bbf  test    rax, rax
0x180082bc2  jnz     short loc_180082BCF
0x180082bc4  call    cs:__imp_GetLastError
0x180082bca  jmp     loc_180082D35
0x180082bcf  xorps   xmm0, xmm0
0x180082bd2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180082bd9  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180082bdd  mov     [rbp+ObjectAttributes.RootDirectory], r13
0x180082be1  mov     r8d, 207F8h; DesiredAccess
0x180082be7  mov     [rbp+ObjectAttributes.Attributes], r13d
0x180082beb  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180082bef  mov     [rbp+ObjectAttributes.ObjectName], r13
0x180082bf3  xor     ecx, ecx; SystemName
0x180082bf5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180082bfa  call    cs:__imp_LsaOpenPolicy
0x180082c00  mov     edi, eax
0x180082c02  test    eax, eax
0x180082c04  jz      short loc_180082C2B
0x180082c06  mov     rcx, rbx
0x180082c09  mov     [rcx], r13b
0x180082c0c  inc     rcx
0x180082c0f  sub     rsi, 1
0x180082c13  jnz     short loc_180082C09
0x180082c15  mov     rcx, rbx; hMem
0x180082c18  call    cs:__imp_LocalFree
0x180082c1e  mov     ecx, edi; Status
0x180082c20  call    cs:__imp_RtlNtStatusToDosError
0x180082c26  jmp     loc_180082D35
0x180082c2b  mov     [rbp+arg_8], r13d
0x180082c2f  mov     r15d, r13d
0x180082c32  mov     edi, r13d
0x180082c35  mov     r13d, [rbp+arg_20]
0x180082c39  test    r12, r12
0x180082c3c  jz      short loc_180082CBA
0x180082c3e  call    RasLsaIsPasswordSavingDisabled
0x180082c43  test    eax, eax
0x180082c45  jnz     short loc_180082CBA
0x180082c47  test    r14d, r14d
0x180082c4a  jz      short loc_180082CBA
0x180082c4c  mov     r9d, edi
0x180082c4f  mov     [rsp+80h+var_60], r13d
0x180082c54  mov     edx, 40h ; '@'
0x180082c59  mov     rcx, rbx
0x180082c5c  call    FormatKey
0x180082c61  test    eax, eax
0x180082c63  jnz     loc_180082D0C
0x180082c69  mov     rdx, rbx; SourceString
0x180082c6c  lea     rcx, [rbp+DestinationString]; DestinationString
0x180082c70  call    cs:__imp_RtlInitUnicodeString
0x180082c76  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180082c7a  lea     r8, [rbp+PrivateData]; PrivateData
0x180082c7e  mov     eax, 0FFFFh
0x180082c83  mov     [rbp+PrivateData.Buffer], r12
0x180082c87  cmp     r14d, eax
0x180082c8a  lea     rdx, [rbp+DestinationString]; KeyName
0x180082c8e  mov     r15d, r14d
0x180082c91  cmova   r15d, eax
0x180082c95  mov     [rbp+PrivateData.MaximumLength], r15w
0x180082c9a  mov     [rbp+PrivateData.Length], r15w
0x180082c9f  call    cs:__imp_LsaStorePrivateData
0x180082ca5  test    eax, eax
0x180082ca7  jnz     short loc_180082CC2
0x180082ca9  mov     eax, r15d
0x180082cac  inc     edi
0x180082cae  add     r12, rax
0x180082cb1  sub     r14d, r15d
0x180082cb4  jnz     short loc_180082C4C
0x180082cb6  mov     r15d, [rbp+arg_8]
0x180082cba  mov     r14d, 40h ; '@'
0x180082cc0  jmp     short loc_180082CF1
0x180082cc2  mov     ecx, eax; Status
0x180082cc4  call    cs:__imp_RtlNtStatusToDosError
0x180082cca  mov     r15d, eax
0x180082ccd  jmp     short loc_180082D10
0x180082ccf  mov     rdx, rbx; SourceString
0x180082cd2  lea     rcx, [rbp+DestinationString]; DestinationString
0x180082cd6  call    cs:__imp_RtlInitUnicodeString
0x180082cdc  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180082ce0  lea     rdx, [rbp+DestinationString]; KeyName
0x180082ce4  xor     r8d, r8d; PrivateData
0x180082ce7  call    cs:__imp_LsaStorePrivateData
0x180082ced  test    eax, eax
0x180082cef  jnz     short loc_180082D10
0x180082cf1  mov     r9d, edi
0x180082cf4  mov     [rsp+80h+var_60], r13d
0x180082cf9  mov     edx, r14d
0x180082cfc  mov     rcx, rbx
0x180082cff  inc     edi
0x180082d01  call    FormatKey
0x180082d06  test    eax, eax
0x180082d08  jz      short loc_180082CCF
0x180082d0a  jmp     short loc_180082D10
0x180082d0c  mov     r15d, [rbp+arg_8]
0x180082d10  mov     rax, rbx
0x180082d13  mov     byte ptr [rax], 0
0x180082d16  inc     rax
0x180082d19  sub     rsi, 1
0x180082d1d  jnz     short loc_180082D13
0x180082d1f  mov     rcx, rbx; hMem
0x180082d22  call    cs:__imp_LocalFree
0x180082d28  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180082d2c  call    cs:__imp_LsaClose
0x180082d32  mov     eax, r15d
0x180082d35  mov     rbx, [rsp+80h+arg_10]
0x180082d3d  add     rsp, 80h
0x180082d44  pop     r15
0x180082d46  pop     r14
0x180082d48  pop     r13
0x180082d4a  pop     r12
0x180082d4c  pop     rdi
0x180082d4d  pop     rsi
0x180082d4e  pop     rbp
0x180082d4f  retn
```
