# RasLsaReadDialParamsBlob

- ea: `0x180082884`
- end: `0x180082af4`
- name: `RasLsaReadDialParamsBlob`
- size: `624`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180082174`
- `0x1800822f0`
- `0x180082d58`

## callees

- `0x180002ba6`
- `0x180081d60`
- `0x180082884`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800829e5`
- `KERNEL32!LocalFree` at `0x180082a82`
- `KERNEL32!LocalFree` at `0x180082ac3`
- `KERNEL32!LocalFree` at `0x1800829e5`
- `KERNEL32!LocalFree` at `0x180082a82`
- `KERNEL32!LocalFree` at `0x180082ac3`
- `KERNEL32!GetLastError` at `0x18008292b`
- `KERNEL32!GetLastError` at `0x180082a40`
- `KERNEL32!GetLastError` at `0x18008292b`
- `KERNEL32!GetLastError` at `0x180082a40`
- `KERNEL32!LocalAlloc` at `0x180082913`
- `KERNEL32!LocalAlloc` at `0x1800829a6`
- `KERNEL32!LocalAlloc` at `0x180082913`
- `KERNEL32!LocalAlloc` at `0x1800829a6`
- `ADVAPI32!LsaClose` at `0x180082925`
- `ADVAPI32!LsaClose` at `0x180082aab`
- `ADVAPI32!LsaClose` at `0x180082925`
- `ADVAPI32!LsaClose` at `0x180082aab`
- `ADVAPI32!LsaFreeMemory` at `0x180082a0f`
- `ADVAPI32!LsaFreeMemory` at `0x180082a99`
- `ADVAPI32!LsaFreeMemory` at `0x180082a0f`
- `ADVAPI32!LsaFreeMemory` at `0x180082a99`
- `ADVAPI32!LsaOpenPolicy` at `0x1800828ec`
- `ADVAPI32!LsaOpenPolicy` at `0x1800828ec`
- `ADVAPI32!LsaRetrievePrivateData` at `0x180082977`
- `ADVAPI32!LsaRetrievePrivateData` at `0x180082977`
- `ntdll!RtlNtStatusToDosError` at `0x1800828f8`
- `ntdll!RtlNtStatusToDosError` at `0x180082a57`
- `ntdll!RtlNtStatusToDosError` at `0x1800828f8`
- `ntdll!RtlNtStatusToDosError` at `0x180082a57`
- `ntdll!RtlInitUnicodeString` at `0x180082965`
- `ntdll!RtlInitUnicodeString` at `0x180082965`

## pseudocode

```c
ULONG __fastcall RasLsaReadDialParamsBlob(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4, int a5)
{
  NTSTATUS v5; // eax
  __int64 v7; // r15
  WCHAR *v8; // rsi
  __int64 v9; // r8
  int v10; // edi
  unsigned int v11; // r14d
  _BYTE *v12; // rbx
  unsigned int v13; // r12d
  NTSTATUS v14; // eax
  unsigned int v15; // ecx
  _BYTE *v16; // rax
  _BYTE *v17; // r13
  __int64 v18; // r15
  _BYTE *v19; // rcx
  __int64 v20; // r8
  ULONG LastError; // eax
  __int64 v22; // rax
  _BYTE *v23; // rcx
  WCHAR *v24; // rax
  PVOID PolicyHandle; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  PLSA_UNICODE_STRING PrivateData; // [rsp+C0h] [rbp+40h] BYREF
  _QWORD *v29; // [rsp+D0h] [rbp+50h]
  unsigned int *v30; // [rsp+D8h] [rbp+58h]

  v30 = a4;
  v29 = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a3 = 0;
  *a4 = 0;
  PrivateData = 0;
  PolicyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v5 = LsaOpenPolicy(0, &ObjectAttributes, 0x20006u, &PolicyHandle);
  if ( v5 )
    return RtlNtStatusToDosError(v5);
  v7 = 128;
  v8 = (WCHAR *)LocalAlloc(0x40u, 0x80u);
  if ( v8 )
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
    v13 = 1;
    if ( (unsigned int)FormatKey(v8, 64, v9, 0, a5) )
    {
LABEL_26:
      if ( PrivateData )
        LsaFreeMemory(PrivateData);
    }
    else
    {
      while ( 1 )
      {
        RtlInitUnicodeString(&DestinationString, v8);
        v14 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v14 )
        {
          if ( v13 <= 1 )
          {
            LastError = RtlNtStatusToDosError(v14);
LABEL_20:
            v10 = LastError;
            if ( LastError )
            {
LABEL_21:
              if ( v12 )
              {
                v22 = v11;
                v23 = v12;
                if ( v11 )
                {
                  do
                  {
                    *v23++ = 0;
                    --v22;
                  }
                  while ( v22 );
                }
                LocalFree(v12);
                v12 = 0;
              }
            }
          }
LABEL_25:
          v7 = 128;
          goto LABEL_26;
        }
        if ( !PrivateData )
          break;
        v15 = v11 + PrivateData->Length;
        if ( v15 < v11 )
        {
          v10 = 534;
          goto LABEL_21;
        }
        v16 = LocalAlloc(0x40u, v15);
        v17 = v16;
        if ( !v16 )
        {
          LastError = GetLastError();
          goto LABEL_20;
        }
        if ( v12 )
        {
          v18 = v11;
          memcpy_0(v16, v12, v11);
          v19 = v12;
          if ( v11 )
          {
            do
            {
              *v19++ = 0;
              --v18;
            }
            while ( v18 );
          }
          LocalFree(v12);
        }
        memcpy_0(&v17[v11], PrivateData->Buffer, PrivateData->Length);
        v12 = v17;
        v11 += PrivateData->Length;
        LsaFreeMemory(PrivateData);
        PrivateData = 0;
        if ( (unsigned int)FormatKey(v8, 64, v20, v13, a5) )
          goto LABEL_25;
        ++v13;
      }
      v7 = 128;
    }
    LsaClose(PolicyHandle);
    v24 = v8;
    do
    {
      *(_BYTE *)v24 = 0;
      v24 = (WCHAR *)((char *)v24 + 1);
      --v7;
    }
    while ( v7 );
    LocalFree(v8);
    *v29 = v12;
    *v30 = v11;
    return v10;
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
0x180082884  mov     rax, rsp
0x180082887  mov     [rax+10h], rbx
0x18008288b  mov     [rax+20h], r9
0x18008288f  mov     [rax+18h], r8
0x180082893  mov     [rax+8], rcx
0x180082897  push    rbp
0x180082898  push    rsi
0x180082899  push    rdi
0x18008289a  push    r12
0x18008289c  push    r13
0x18008289e  push    r14
0x1800828a0  push    r15
0x1800828a2  mov     rbp, rsp
0x1800828a5  sub     rsp, 80h
0x1800828ac  xor     edx, edx
0x1800828ae  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800828b6  mov     [r8], rdx
0x1800828b9  xorps   xmm0, xmm0
0x1800828bc  mov     [r9], edx
0x1800828bf  xor     ecx, ecx; SystemName
0x1800828c1  mov     [rbp+PrivateData], rdx
0x1800828c5  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800828c9  mov     qword ptr [rbp+ObjectAttributes.Attributes], rdx
0x1800828cd  mov     r8d, 20006h; DesiredAccess
0x1800828d3  mov     [rbp+PolicyHandle], rdx
0x1800828d7  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800828db  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800828df  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1800828e3  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1800828e7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800828ec  call    cs:__imp_LsaOpenPolicy
0x1800828f2  test    eax, eax
0x1800828f4  jz      short loc_180082903
0x1800828f6  mov     ecx, eax; Status
0x1800828f8  call    cs:__imp_RtlNtStatusToDosError
0x1800828fe  jmp     loc_180082AD9
0x180082903  mov     r15d, 80h
0x180082909  mov     edx, r15d; uBytes
0x18008290c  lea     r13d, [r15-40h]
0x180082910  mov     ecx, r13d; uFlags
0x180082913  call    cs:__imp_LocalAlloc
0x180082919  mov     rsi, rax
0x18008291c  test    rax, rax
0x18008291f  jnz     short loc_180082936
0x180082921  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180082925  call    cs:__imp_LsaClose
0x18008292b  call    cs:__imp_GetLastError
0x180082931  jmp     loc_180082AD9
0x180082936  mov     eax, [rbp+arg_20]
0x180082939  xor     edi, edi
0x18008293b  xor     r9d, r9d
0x18008293e  mov     [rsp+80h+var_60], eax
0x180082942  mov     edx, r13d
0x180082945  mov     rcx, rsi
0x180082948  xor     r14d, r14d
0x18008294b  xor     ebx, ebx
0x18008294d  lea     r12d, [rdi+1]
0x180082951  call    FormatKey
0x180082956  test    eax, eax
0x180082958  jnz     loc_180082A90
0x18008295e  mov     rdx, rsi; SourceString
0x180082961  lea     rcx, [rbp+DestinationString]; DestinationString
0x180082965  call    cs:__imp_RtlInitUnicodeString
0x18008296b  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18008296f  lea     r8, [rbp+PrivateData]; PrivateData
0x180082973  lea     rdx, [rbp+DestinationString]; KeyName
0x180082977  call    cs:__imp_LsaRetrievePrivateData
0x18008297d  test    eax, eax
0x18008297f  jnz     loc_180082A4F
0x180082985  mov     rcx, [rbp+PrivateData]
0x180082989  test    rcx, rcx
0x18008298c  jz      loc_180082AA1
0x180082992  movzx   ecx, word ptr [rcx]
0x180082995  add     ecx, r14d
0x180082998  cmp     ecx, r14d
0x18008299b  jb      loc_180082A48
0x1800829a1  mov     edx, ecx; uBytes
0x1800829a3  mov     ecx, r13d; uFlags
0x1800829a6  call    cs:__imp_LocalAlloc
0x1800829ac  mov     r13, rax
0x1800829af  test    rax, rax
0x1800829b2  jz      loc_180082A40
0x1800829b8  test    rbx, rbx
0x1800829bb  jz      short loc_1800829EB
0x1800829bd  mov     r8d, r14d; Size
0x1800829c0  mov     rdx, rbx; Src
0x1800829c3  mov     rcx, rax; void *
0x1800829c6  mov     r15d, r14d
0x1800829c9  call    memcpy_0
0x1800829ce  mov     rcx, rbx
0x1800829d1  test    r14d, r14d
0x1800829d4  jz      short loc_1800829E2
0x1800829d6  mov     [rcx], dil
0x1800829d9  inc     rcx
0x1800829dc  sub     r15, 1
0x1800829e0  jnz     short loc_1800829D6
0x1800829e2  mov     rcx, rbx; hMem
0x1800829e5  call    cs:__imp_LocalFree
0x1800829eb  mov     rdx, [rbp+PrivateData]
0x1800829ef  mov     ecx, r14d
0x1800829f2  add     rcx, r13; void *
0x1800829f5  movzx   r8d, word ptr [rdx]; Size
0x1800829f9  mov     rdx, [rdx+8]; Src
0x1800829fd  call    memcpy_0
0x180082a02  mov     rcx, [rbp+PrivateData]; Buffer
0x180082a06  mov     rbx, r13
0x180082a09  movzx   eax, word ptr [rcx]
0x180082a0c  add     r14d, eax
0x180082a0f  call    cs:__imp_LsaFreeMemory
0x180082a15  mov     eax, [rbp+arg_20]
0x180082a18  mov     r13d, 40h ; '@'
0x180082a1e  mov     edx, r13d
0x180082a21  mov     [rbp+PrivateData], rdi
0x180082a25  mov     r9d, r12d
0x180082a28  mov     [rsp+80h+var_60], eax
0x180082a2c  mov     rcx, rsi
0x180082a2f  call    FormatKey
0x180082a34  test    eax, eax
0x180082a36  jnz     short loc_180082A8A
0x180082a38  inc     r12d
0x180082a3b  jmp     loc_18008295E
0x180082a40  call    cs:__imp_GetLastError
0x180082a46  jmp     short loc_180082A5D
0x180082a48  mov     edi, 216h
0x180082a4d  jmp     short loc_180082A63
0x180082a4f  cmp     r12d, 1
0x180082a53  ja      short loc_180082A8A
0x180082a55  mov     ecx, eax; Status
0x180082a57  call    cs:__imp_RtlNtStatusToDosError
0x180082a5d  mov     edi, eax
0x180082a5f  test    eax, eax
0x180082a61  jz      short loc_180082A8A
0x180082a63  test    rbx, rbx
0x180082a66  jz      short loc_180082A8A
0x180082a68  mov     eax, r14d
0x180082a6b  mov     rcx, rbx
0x180082a6e  test    r14d, r14d
0x180082a71  jz      short loc_180082A7F
0x180082a73  mov     byte ptr [rcx], 0
0x180082a76  inc     rcx
0x180082a79  sub     rax, 1
0x180082a7d  jnz     short loc_180082A73
0x180082a7f  mov     rcx, rbx; hMem
0x180082a82  call    cs:__imp_LocalFree
0x180082a88  xor     ebx, ebx
0x180082a8a  mov     r15d, 80h
0x180082a90  mov     rcx, [rbp+PrivateData]; Buffer
0x180082a94  test    rcx, rcx
0x180082a97  jz      short loc_180082AA7
0x180082a99  call    cs:__imp_LsaFreeMemory
0x180082a9f  jmp     short loc_180082AA7
0x180082aa1  mov     r15d, 80h
0x180082aa7  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180082aab  call    cs:__imp_LsaClose
0x180082ab1  mov     rax, rsi
0x180082ab4  mov     byte ptr [rax], 0
0x180082ab7  inc     rax
0x180082aba  sub     r15, 1
0x180082abe  jnz     short loc_180082AB4
0x180082ac0  mov     rcx, rsi; hMem
0x180082ac3  call    cs:__imp_LocalFree
0x180082ac9  mov     rax, [rbp+arg_10]
0x180082acd  mov     [rax], rbx
0x180082ad0  mov     rax, [rbp+arg_18]
0x180082ad4  mov     [rax], r14d
0x180082ad7  mov     eax, edi
0x180082ad9  mov     rbx, [rsp+80h+arg_8]
0x180082ae1  add     rsp, 80h
0x180082ae8  pop     r15
0x180082aea  pop     r14
0x180082aec  pop     r13
0x180082aee  pop     r12
0x180082af0  pop     rdi
0x180082af1  pop     rsi
0x180082af2  pop     rbp
0x180082af3  retn
```
