# myGetTargetMachineDomainDnsName(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x18000eac0`
- end: `0x18000ed7b`
- name: `?myGetTargetMachineDomainDnsName@@YAJPEBGPEAPEAG11@Z`
- size: `699`
- prototype: `__int64 __fastcall(WCHAR *lpString, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800062d0`
- `0x18002a290`
- `0x18002fa68`

## callees

- `0x180008610`
- `0x18000eac0`
- `0x180013a86`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ec3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ec93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ecee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ec3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ec93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ecee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000eb47`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000eb47`
- `ntdll!RtlNtStatusToDosError` at `0x18000eb8e`
- `ntdll!RtlNtStatusToDosError` at `0x18000ebe1`
- `ntdll!RtlNtStatusToDosError` at `0x18000eb8e`
- `ntdll!RtlNtStatusToDosError` at `0x18000ebe1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000ed55`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000ed55`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000eb6e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000eb6e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000ed46`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000ed46`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000ebc1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000ebc1`

## pseudocode

```c
__int64 __fastcall myGetTargetMachineDomainDnsName(
        WCHAR *lpString,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  struct _LSA_UNICODE_STRING *p_SystemName; // rcx
  __int16 v9; // ax
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  signed int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // edx
  const unsigned __int16 *v15; // rcx
  NTSTATUS v16; // eax
  NTSTATUS v17; // ebx
  signed int v18; // eax
  __int64 v19; // rdx
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  unsigned __int16 *v24; // rax
  PVOID Buffer; // [rsp+20h] [rbp-49h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-41h] BYREF
  struct _LSA_UNICODE_STRING SystemName; // [rsp+30h] [rbp-39h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v30[4]; // [rsp+70h] [rbp+7h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  Buffer = 0;
  v30[2] = 1;
  v30[0] = 12;
  v30[1] = 2;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  p_SystemName = 0;
  ObjectAttributes.SecurityQualityOfService = v30;
  SystemName = 0;
  if ( lpString )
  {
    SystemName.Buffer = lpString;
    v9 = lstrlenW(lpString);
    p_SystemName = &SystemName;
    SystemName.Length = 2 * v9;
    SystemName.MaximumLength = 2 * v9 + 2;
  }
  v10 = LsaOpenPolicy(p_SystemName, &ObjectAttributes, 1u, &PolicyHandle);
  v11 = v10;
  if ( v10 )
    CSPrintErrorLineFileData2(0, 0x1B10326u, v10, 0);
  v12 = RtlNtStatusToDosError(v11);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( !v13 )
  {
    v16 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    v17 = v16;
    if ( v16 )
      CSPrintErrorLineFileData2(0, 0x1B90326u, v16, 0);
    v18 = RtlNtStatusToDosError(v17);
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
    if ( v13 )
    {
      v14 = 29033254;
      v15 = lpString;
      goto LABEL_40;
    }
    if ( !Buffer )
    {
      v14 = 29360934;
LABEL_38:
      v13 = -2147023545;
      goto LABEL_39;
    }
    if ( a2 )
    {
      v19 = *(unsigned __int16 *)Buffer;
      if ( !(_WORD)v19 || !*((_QWORD *)Buffer + 1) )
      {
        v14 = 29950758;
        goto LABEL_38;
      }
      v20 = (unsigned __int16 *)LocalAlloc(0x40u, v19 + 2);
      *a2 = v20;
      if ( !v20 )
      {
        v13 = -2147024882;
        v14 = 30409510;
LABEL_39:
        v15 = 0;
        goto LABEL_40;
      }
      memcpy_0(v20, *((const void **)Buffer + 1), *(unsigned __int16 *)Buffer);
    }
    if ( a3 )
    {
      v21 = *((unsigned __int16 *)Buffer + 8);
      if ( !(_WORD)v21 || !*((_QWORD *)Buffer + 3) )
      {
        v14 = 31130406;
        goto LABEL_38;
      }
      v22 = (unsigned __int16 *)LocalAlloc(0x40u, v21 + 2);
      *a3 = v22;
      if ( !v22 )
      {
        v13 = -2147024882;
        v14 = 31654694;
        goto LABEL_39;
      }
      memcpy_0(v22, *((const void **)Buffer + 3), *((unsigned __int16 *)Buffer + 8));
    }
    if ( !a4 )
      goto LABEL_41;
    v23 = *((unsigned __int16 *)Buffer + 16);
    if ( (_WORD)v23 && *((_QWORD *)Buffer + 5) )
    {
      v24 = (unsigned __int16 *)LocalAlloc(0x40u, v23 + 2);
      *a4 = v24;
      if ( v24 )
      {
        memcpy_0(v24, *((const void **)Buffer + 5), *((unsigned __int16 *)Buffer + 16));
        goto LABEL_41;
      }
      v13 = -2147024882;
      v14 = 32834342;
      goto LABEL_39;
    }
    v14 = 32375590;
    goto LABEL_38;
  }
  v14 = 28508966;
  v15 = lpString;
LABEL_40:
  CSPrintErrorLineFileData2(v15, v14, v13, 0);
LABEL_41:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v13;
}

```

## disassembly

```asm
0x18000eac0  push    rbp
0x18000eac2  push    rbx
0x18000eac3  push    rsi
0x18000eac4  push    rdi
0x18000eac5  push    r12
0x18000eac7  push    r14
0x18000eac9  push    r15
0x18000eacb  lea     rbp, [rsp-27h]
0x18000ead0  sub     rsp, 90h
0x18000ead7  mov     rax, cs:__security_cookie
0x18000eade  xor     rax, rsp
0x18000eae1  mov     [rbp+57h+var_40], rax
0x18000eae5  xor     r12d, r12d
0x18000eae8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000eaf0  mov     rdi, rcx
0x18000eaf3  mov     [rbp+57h+PolicyHandle], r12
0x18000eaf7  mov     [rbp+57h+Buffer], r12
0x18000eafb  xorps   xmm0, xmm0
0x18000eafe  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r12
0x18000eb02  lea     rax, [rbp+57h+var_50]
0x18000eb06  mov     [rbp+57h+var_48], 1
0x18000eb0d  mov     r15, r9
0x18000eb10  mov     [rbp+57h+var_50], 0Ch
0x18000eb17  mov     r14, r8
0x18000eb1a  mov     [rbp+57h+var_4C], 2
0x18000eb21  mov     rsi, rdx
0x18000eb24  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18000eb28  mov     ecx, r12d
0x18000eb2b  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x18000eb2f  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x18000eb33  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18000eb37  movups  xmmword ptr [rbp+57h+SystemName.Length], xmm0
0x18000eb3b  test    rdi, rdi
0x18000eb3e  jz      short loc_18000EB60
0x18000eb40  mov     rcx, rdi; lpString
0x18000eb43  mov     [rbp+57h+SystemName.Buffer], rdi
0x18000eb47  call    cs:__imp_lstrlenW
0x18000eb4d  add     ax, ax
0x18000eb50  lea     rcx, [rbp+57h+SystemName]; SystemName
0x18000eb54  mov     [rbp+57h+SystemName.Length], ax
0x18000eb58  add     ax, 2
0x18000eb5c  mov     [rbp+57h+SystemName.MaximumLength], ax
0x18000eb60  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000eb64  mov     r8d, 1; DesiredAccess
0x18000eb6a  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000eb6e  call    cs:__imp_LsaOpenPolicy
0x18000eb74  mov     ebx, eax
0x18000eb76  test    eax, eax
0x18000eb78  jz      short loc_18000EB8C
0x18000eb7a  xor     r9d, r9d; int
0x18000eb7d  mov     r8d, eax; int
0x18000eb80  mov     edx, 1B10326h; unsigned int
0x18000eb85  xor     ecx, ecx; unsigned __int16 *
0x18000eb87  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000eb8c  mov     ecx, ebx; Status
0x18000eb8e  call    cs:__imp_RtlNtStatusToDosError
0x18000eb94  mov     ebx, eax
0x18000eb96  test    eax, eax
0x18000eb98  jle     short loc_18000EBA3
0x18000eb9a  movzx   ebx, ax
0x18000eb9d  or      ebx, 80070000h
0x18000eba3  test    ebx, ebx
0x18000eba5  jz      short loc_18000EBB4
0x18000eba7  mov     edx, 1B30326h
0x18000ebac  mov     rcx, rdi
0x18000ebaf  jmp     loc_18000ED32
0x18000ebb4  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000ebb8  lea     r8, [rbp+57h+Buffer]; Buffer
0x18000ebbc  mov     edx, 0Ch; InformationClass
0x18000ebc1  call    cs:__imp_LsaQueryInformationPolicy
0x18000ebc7  mov     ebx, eax
0x18000ebc9  test    eax, eax
0x18000ebcb  jz      short loc_18000EBDF
0x18000ebcd  xor     r9d, r9d; int
0x18000ebd0  mov     r8d, eax; int
0x18000ebd3  mov     edx, 1B90326h; unsigned int
0x18000ebd8  xor     ecx, ecx; unsigned __int16 *
0x18000ebda  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000ebdf  mov     ecx, ebx; Status
0x18000ebe1  call    cs:__imp_RtlNtStatusToDosError
0x18000ebe7  mov     ebx, eax
0x18000ebe9  test    eax, eax
0x18000ebeb  jle     short loc_18000EBF6
0x18000ebed  movzx   ebx, ax
0x18000ebf0  or      ebx, 80070000h
0x18000ebf6  test    ebx, ebx
0x18000ebf8  jz      short loc_18000EC07
0x18000ebfa  mov     edx, 1BB0326h
0x18000ebff  mov     rcx, rdi
0x18000ec02  jmp     loc_18000ED32
0x18000ec07  cmp     [rbp+57h+Buffer], r12
0x18000ec0b  jnz     short loc_18000EC17
0x18000ec0d  mov     edx, 1C00326h
0x18000ec12  jmp     loc_18000ED2B
0x18000ec17  test    rsi, rsi
0x18000ec1a  jz      short loc_18000EC6D
0x18000ec1c  mov     rcx, [rbp+57h+Buffer]
0x18000ec20  movzx   edx, word ptr [rcx]
0x18000ec23  cmp     r12w, dx
0x18000ec27  jnb     loc_18000ECB0
0x18000ec2d  cmp     [rcx+8], r12
0x18000ec31  jz      short loc_18000ECB0
0x18000ec33  add     rdx, 2; uBytes
0x18000ec37  mov     ecx, 40h ; '@'; uFlags
0x18000ec3c  call    cs:__imp_LocalAlloc
0x18000ec42  mov     [rsi], rax
0x18000ec45  test    rax, rax
0x18000ec48  jnz     short loc_18000EC59
0x18000ec4a  mov     ebx, 8007000Eh
0x18000ec4f  mov     edx, 1D00326h
0x18000ec54  jmp     loc_18000ED30
0x18000ec59  mov     rdx, [rbp+57h+Buffer]
0x18000ec5d  mov     rcx, rax; void *
0x18000ec60  movzx   r8d, word ptr [rdx]; Size
0x18000ec64  mov     rdx, [rdx+8]; Src
0x18000ec68  call    memcpy_0
0x18000ec6d  test    r14, r14
0x18000ec70  jz      short loc_18000ECCC
0x18000ec72  mov     rcx, [rbp+57h+Buffer]
0x18000ec76  movzx   edx, word ptr [rcx+10h]
0x18000ec7a  cmp     r12w, dx
0x18000ec7e  jnb     loc_18000ED08
0x18000ec84  cmp     [rcx+18h], r12
0x18000ec88  jz      short loc_18000ED08
0x18000ec8a  add     rdx, 2; uBytes
0x18000ec8e  mov     ecx, 40h ; '@'; uFlags
0x18000ec93  call    cs:__imp_LocalAlloc
0x18000ec99  mov     [r14], rax
0x18000ec9c  test    rax, rax
0x18000ec9f  jnz     short loc_18000ECB7
0x18000eca1  mov     ebx, 8007000Eh
0x18000eca6  mov     edx, 1E30326h
0x18000ecab  jmp     loc_18000ED30
0x18000ecb0  mov     edx, 1C90326h
0x18000ecb5  jmp     short loc_18000ED2B
0x18000ecb7  mov     rdx, [rbp+57h+Buffer]
0x18000ecbb  mov     rcx, rax; void *
0x18000ecbe  movzx   r8d, word ptr [rdx+10h]; Size
0x18000ecc3  mov     rdx, [rdx+18h]; Src
0x18000ecc7  call    memcpy_0
0x18000eccc  test    r15, r15
0x18000eccf  jz      short loc_18000ED3D
0x18000ecd1  mov     rcx, [rbp+57h+Buffer]
0x18000ecd5  movzx   edx, word ptr [rcx+20h]
0x18000ecd9  cmp     r12w, dx
0x18000ecdd  jnb     short loc_18000ED26
0x18000ecdf  cmp     [rcx+28h], r12
0x18000ece3  jz      short loc_18000ED26
0x18000ece5  add     rdx, 2; uBytes
0x18000ece9  mov     ecx, 40h ; '@'; uFlags
0x18000ecee  call    cs:__imp_LocalAlloc
0x18000ecf4  mov     [r15], rax
0x18000ecf7  test    rax, rax
0x18000ecfa  jnz     short loc_18000ED0F
0x18000ecfc  mov     ebx, 8007000Eh
0x18000ed01  mov     edx, 1F50326h
0x18000ed06  jmp     short loc_18000ED30
0x18000ed08  mov     edx, 1DB0326h
0x18000ed0d  jmp     short loc_18000ED2B
0x18000ed0f  mov     rdx, [rbp+57h+Buffer]
0x18000ed13  mov     rcx, rax; void *
0x18000ed16  movzx   r8d, word ptr [rdx+20h]; Size
0x18000ed1b  mov     rdx, [rdx+28h]; Src
0x18000ed1f  call    memcpy_0
0x18000ed24  jmp     short loc_18000ED3D
0x18000ed26  mov     edx, 1EE0326h; unsigned int
0x18000ed2b  mov     ebx, 80070547h
0x18000ed30  xor     ecx, ecx; unsigned __int16 *
0x18000ed32  xor     r9d, r9d; int
0x18000ed35  mov     r8d, ebx; int
0x18000ed38  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000ed3d  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000ed41  test    rcx, rcx
0x18000ed44  jz      short loc_18000ED4C
0x18000ed46  call    cs:__imp_LsaFreeMemory
0x18000ed4c  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18000ed50  test    rcx, rcx
0x18000ed53  jz      short loc_18000ED5B
0x18000ed55  call    cs:__imp_LsaClose
0x18000ed5b  mov     eax, ebx
0x18000ed5d  mov     rcx, [rbp+57h+var_40]
0x18000ed61  xor     rcx, rsp; StackCookie
0x18000ed64  call    __security_check_cookie
0x18000ed69  add     rsp, 90h
0x18000ed70  pop     r15
0x18000ed72  pop     r14
0x18000ed74  pop     r12
0x18000ed76  pop     rdi
0x18000ed77  pop     rsi
0x18000ed78  pop     rbx
0x18000ed79  pop     rbp
0x18000ed7a  retn
```
