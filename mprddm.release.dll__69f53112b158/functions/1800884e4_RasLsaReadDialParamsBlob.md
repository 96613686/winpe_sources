# RasLsaReadDialParamsBlob

- ea: `0x1800884e4`
- end: `0x18008879b`
- name: `RasLsaReadDialParamsBlob`
- size: `695`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180087d80`
- `0x180087eec`
- `0x180088a3c`

## callees

- `0x180002be6`
- `0x180087970`
- `0x1800884e4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18008866b`
- `KERNEL32!LocalFree` at `0x180088720`
- `KERNEL32!LocalFree` at `0x18008876d`
- `KERNEL32!LocalFree` at `0x18008866b`
- `KERNEL32!LocalFree` at `0x180088720`
- `KERNEL32!LocalFree` at `0x18008876d`
- `KERNEL32!GetLastError` at `0x1800885a9`
- `KERNEL32!GetLastError` at `0x1800886d6`
- `KERNEL32!GetLastError` at `0x1800885a9`
- `KERNEL32!GetLastError` at `0x1800886d6`
- `KERNEL32!LocalAlloc` at `0x180088585`
- `KERNEL32!LocalAlloc` at `0x180088633`
- `KERNEL32!LocalAlloc` at `0x180088585`
- `KERNEL32!LocalAlloc` at `0x180088633`
- `ADVAPI32!LsaClose` at `0x18008859d`
- `ADVAPI32!LsaClose` at `0x180088752`
- `ADVAPI32!LsaClose` at `0x18008859d`
- `ADVAPI32!LsaClose` at `0x180088752`
- `ADVAPI32!LsaFreeMemory` at `0x18008869e`
- `ADVAPI32!LsaFreeMemory` at `0x18008873c`
- `ADVAPI32!LsaFreeMemory` at `0x18008869e`
- `ADVAPI32!LsaFreeMemory` at `0x18008873c`
- `ADVAPI32!LsaOpenPolicy` at `0x18008855a`
- `ADVAPI32!LsaOpenPolicy` at `0x18008855a`
- `ADVAPI32!LsaRetrievePrivateData` at `0x1800885fe`
- `ADVAPI32!LsaRetrievePrivateData` at `0x1800885fe`
- `ntdll!RtlNtStatusToDosError` at `0x18008856c`
- `ntdll!RtlNtStatusToDosError` at `0x1800886fb`
- `ntdll!RtlNtStatusToDosError` at `0x18008856c`
- `ntdll!RtlNtStatusToDosError` at `0x1800886fb`
- `ntdll!RtlInitUnicodeString` at `0x1800885e6`
- `ntdll!RtlInitUnicodeString` at `0x1800885e6`

## pseudocode

```c
ULONG __fastcall RasLsaReadDialParamsBlob(__int64 a1, int a2, _QWORD *a3, unsigned int *a4, int a5)
{
  unsigned int *v5; // rbx
  int v6; // r14d
  unsigned int v7; // r12d
  void *v8; // rsi
  NTSTATUS v9; // eax
  __int64 v11; // r8
  WCHAR *v12; // r15
  unsigned int v13; // edi
  NTSTATUS v14; // eax
  unsigned int v15; // ecx
  char *v16; // rax
  char *v17; // r13
  __int64 v18; // r9
  __int64 v19; // r8
  ULONG LastError; // eax
  _QWORD *v21; // rax
  PVOID PolicyHandle; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-39h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-29h] BYREF
  PLSA_UNICODE_STRING PrivateData; // [rsp+D8h] [rbp+5Fh] BYREF
  int v26; // [rsp+E0h] [rbp+67h]
  _QWORD *v27; // [rsp+E8h] [rbp+6Fh]
  unsigned int *v28; // [rsp+F0h] [rbp+77h]

  v28 = a4;
  v27 = a3;
  v26 = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a3 = 0;
  *a4 = 0;
  v5 = a4;
  PrivateData = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  DestinationString = 0;
  v9 = LsaOpenPolicy(0, &ObjectAttributes, 0x20006u, &PolicyHandle);
  if ( v9 )
    return RtlNtStatusToDosError(v9);
  v12 = (WCHAR *)LocalAlloc(0x40u, 0x80u);
  if ( v12 )
  {
    v13 = 1;
    v26 = 1;
    if ( (unsigned int)FormatKey(v12, 64, v11, 0, a5) )
    {
LABEL_23:
      if ( PrivateData )
        LsaFreeMemory(PrivateData);
    }
    else
    {
      while ( 1 )
      {
        RtlInitUnicodeString(&DestinationString, v12);
        v14 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v14 )
        {
          if ( v13 <= 1 )
          {
            LastError = RtlNtStatusToDosError(v14);
LABEL_19:
            v6 = LastError;
            if ( LastError )
            {
LABEL_20:
              if ( v8 )
              {
                memset(v8, 0, v7);
                LocalFree(v8);
                v8 = 0;
              }
            }
          }
          else
          {
            v6 = 0;
          }
LABEL_22:
          v5 = v28;
          goto LABEL_23;
        }
        if ( !PrivateData )
          break;
        v15 = v7 + PrivateData->Length;
        if ( v15 < v7 )
        {
          v6 = 534;
          goto LABEL_20;
        }
        v16 = (char *)LocalAlloc(0x40u, v15);
        v17 = v16;
        if ( !v16 )
        {
          LastError = GetLastError();
          goto LABEL_19;
        }
        if ( v8 )
        {
          memcpy_0(v16, v8, v7);
          memset(v8, 0, v7);
          LocalFree(v8);
          v13 = v26;
        }
        memcpy_0(&v17[v7], PrivateData->Buffer, PrivateData->Length);
        v8 = v17;
        v7 += PrivateData->Length;
        LsaFreeMemory(PrivateData);
        v18 = v13;
        PrivateData = 0;
        v26 = ++v13;
        if ( (unsigned int)FormatKey(v12, 64, v19, v18, a5) )
          goto LABEL_22;
      }
      v5 = v28;
    }
    LsaClose(PolicyHandle);
    memset(v12, 0, 0x80u);
    LocalFree(v12);
    v21 = v27;
    *v5 = v7;
    *v21 = v8;
    return v6;
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
0x1800884e4  mov     rax, rsp
0x1800884e7  mov     [rax+20h], r9
0x1800884eb  mov     [rax+18h], r8
0x1800884ef  mov     [rax+10h], edx
0x1800884f2  mov     [rax+8], rcx
0x1800884f6  push    rbp
0x1800884f7  push    rbx
0x1800884f8  push    rsi
0x1800884f9  push    rdi
0x1800884fa  push    r12
0x1800884fc  push    r13
0x1800884fe  push    r14
0x180088500  push    r15
0x180088502  lea     rbp, [rax-57h]
0x180088506  sub     rsp, 88h
0x18008850d  xor     r13d, r13d
0x180088510  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180088518  xorps   xmm0, xmm0
0x18008851b  mov     [r8], r13
0x18008851e  mov     [r9], r13d
0x180088521  lea     rdx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180088525  mov     rbx, r9
0x180088528  mov     [rbp+4Fh+PrivateData], r13
0x18008852c  lea     r9, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x180088530  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], r13
0x180088534  mov     r8d, 20006h; DesiredAccess
0x18008853a  mov     [rbp+4Fh+PolicyHandle], r13
0x18008853e  xor     ecx, ecx; SystemName
0x180088540  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r13
0x180088544  mov     r14d, r13d
0x180088547  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r13
0x18008854b  mov     r12d, r13d
0x18008854e  mov     esi, r13d
0x180088551  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180088555  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18008855a  call    cs:__imp_LsaOpenPolicy
0x180088561  nop     dword ptr [rax+rax+00h]
0x180088566  test    eax, eax
0x180088568  jz      short loc_18008857D
0x18008856a  mov     ecx, eax; Status
0x18008856c  call    cs:__imp_RtlNtStatusToDosError
0x180088573  nop     dword ptr [rax+rax+00h]
0x180088578  jmp     loc_180088786
0x18008857d  mov     edx, 80h; uBytes
0x180088582  lea     ecx, [rdx-40h]; uFlags
0x180088585  call    cs:__imp_LocalAlloc
0x18008858c  nop     dword ptr [rax+rax+00h]
0x180088591  mov     r15, rax
0x180088594  test    rax, rax
0x180088597  jnz     short loc_1800885BA
0x180088599  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x18008859d  call    cs:__imp_LsaClose
0x1800885a4  nop     dword ptr [rax+rax+00h]
0x1800885a9  call    cs:__imp_GetLastError
0x1800885b0  nop     dword ptr [rax+rax+00h]
0x1800885b5  jmp     loc_180088786
0x1800885ba  mov     eax, [rbp+4Fh+arg_20]
0x1800885bd  mov     edi, 1
0x1800885c2  xor     r9d, r9d
0x1800885c5  mov     [rbp+4Fh+arg_8], edi
0x1800885c8  mov     rcx, r15
0x1800885cb  mov     [rsp+20h], eax
0x1800885cf  lea     edx, [rdi+3Fh]
0x1800885d2  call    FormatKey
0x1800885d7  test    eax, eax
0x1800885d9  jnz     loc_180088733
0x1800885df  mov     rdx, r15; SourceString
0x1800885e2  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800885e6  call    cs:__imp_RtlInitUnicodeString
0x1800885ed  nop     dword ptr [rax+rax+00h]
0x1800885f2  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800885f6  lea     r8, [rbp+4Fh+PrivateData]; PrivateData
0x1800885fa  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800885fe  call    cs:__imp_LsaRetrievePrivateData
0x180088605  nop     dword ptr [rax+rax+00h]
0x18008860a  test    eax, eax
0x18008860c  jnz     loc_1800886EF
0x180088612  mov     rcx, [rbp+4Fh+PrivateData]
0x180088616  test    rcx, rcx
0x180088619  jz      loc_18008874A
0x18008861f  movzx   ecx, word ptr [rcx]
0x180088622  add     ecx, r12d
0x180088625  cmp     ecx, r12d
0x180088628  jb      loc_1800886E7
0x18008862e  mov     edx, ecx; uBytes
0x180088630  lea     ecx, [rax+40h]; uFlags
0x180088633  call    cs:__imp_LocalAlloc
0x18008863a  nop     dword ptr [rax+rax+00h]
0x18008863f  mov     r13, rax
0x180088642  test    rax, rax
0x180088645  jz      loc_1800886D6
0x18008864b  test    rsi, rsi
0x18008864e  jz      short loc_18008867A
0x180088650  mov     r8d, r12d; Size
0x180088653  mov     rdx, rsi; Src
0x180088656  mov     rcx, rax; void *
0x180088659  call    memcpy_0
0x18008865e  xor     eax, eax
0x180088660  mov     ecx, r12d
0x180088663  mov     rdi, rsi
0x180088666  rep stosb
0x180088668  mov     rcx, rsi; hMem
0x18008866b  call    cs:__imp_LocalFree
0x180088672  nop     dword ptr [rax+rax+00h]
0x180088677  mov     edi, [rbp+4Fh+arg_8]
0x18008867a  mov     rdx, [rbp+4Fh+PrivateData]
0x18008867e  mov     ecx, r12d
0x180088681  add     rcx, r13; void *
0x180088684  movzx   r8d, word ptr [rdx]; Size
0x180088688  mov     rdx, [rdx+8]; Src
0x18008868c  call    memcpy_0
0x180088691  mov     rcx, [rbp+4Fh+PrivateData]; Buffer
0x180088695  mov     rsi, r13
0x180088698  movzx   eax, word ptr [rcx]
0x18008869b  add     r12d, eax
0x18008869e  call    cs:__imp_LsaFreeMemory
0x1800886a5  nop     dword ptr [rax+rax+00h]
0x1800886aa  mov     eax, [rbp+4Fh+arg_20]
0x1800886ad  xor     r13d, r13d
0x1800886b0  mov     r9d, edi
0x1800886b3  mov     [rbp+4Fh+PrivateData], r13
0x1800886b7  inc     edi
0x1800886b9  mov     [rsp+20h], eax
0x1800886bd  mov     rcx, r15
0x1800886c0  mov     [rbp+4Fh+arg_8], edi
0x1800886c3  lea     edx, [r13+40h]
0x1800886c7  call    FormatKey
0x1800886cc  test    eax, eax
0x1800886ce  jz      loc_1800885DF
0x1800886d4  jmp     short loc_18008872F
0x1800886d6  call    cs:__imp_GetLastError
0x1800886dd  nop     dword ptr [rax+rax+00h]
0x1800886e2  xor     r13d, r13d
0x1800886e5  jmp     short loc_180088707
0x1800886e7  mov     r14d, 216h
0x1800886ed  jmp     short loc_18008870E
0x1800886ef  cmp     edi, 1
0x1800886f2  jbe     short loc_1800886F9
0x1800886f4  mov     r14d, r13d
0x1800886f7  jmp     short loc_18008872F
0x1800886f9  mov     ecx, eax; Status
0x1800886fb  call    cs:__imp_RtlNtStatusToDosError
0x180088702  nop     dword ptr [rax+rax+00h]
0x180088707  mov     r14d, eax
0x18008870a  test    eax, eax
0x18008870c  jz      short loc_18008872F
0x18008870e  test    rsi, rsi
0x180088711  jz      short loc_18008872F
0x180088713  xor     eax, eax
0x180088715  mov     ecx, r12d
0x180088718  mov     rdi, rsi
0x18008871b  rep stosb
0x18008871d  mov     rcx, rsi; hMem
0x180088720  call    cs:__imp_LocalFree
0x180088727  nop     dword ptr [rax+rax+00h]
0x18008872c  mov     rsi, r13
0x18008872f  mov     rbx, [rbp+4Fh+arg_18]
0x180088733  mov     rcx, [rbp+4Fh+PrivateData]; Buffer
0x180088737  test    rcx, rcx
0x18008873a  jz      short loc_18008874E
0x18008873c  call    cs:__imp_LsaFreeMemory
0x180088743  nop     dword ptr [rax+rax+00h]
0x180088748  jmp     short loc_18008874E
0x18008874a  mov     rbx, [rbp+4Fh+arg_18]
0x18008874e  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x180088752  call    cs:__imp_LsaClose
0x180088759  nop     dword ptr [rax+rax+00h]
0x18008875e  xor     eax, eax
0x180088760  mov     ecx, 80h
0x180088765  mov     rdi, r15
0x180088768  rep stosb
0x18008876a  mov     rcx, r15; hMem
0x18008876d  call    cs:__imp_LocalFree
0x180088774  nop     dword ptr [rax+rax+00h]
0x180088779  mov     rax, [rbp+4Fh+arg_10]
0x18008877d  mov     [rbx], r12d
0x180088780  mov     [rax], rsi
0x180088783  mov     eax, r14d
0x180088786  add     rsp, 88h
0x18008878d  pop     r15
0x18008878f  pop     r14
0x180088791  pop     r13
0x180088793  pop     r12
0x180088795  pop     rdi
0x180088796  pop     rsi
0x180088797  pop     rbx
0x180088798  pop     rbp
0x180088799  retn
```
