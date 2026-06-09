# TokenExtCreateEnvironment

- ea: `0x180019efc`
- end: `0x18001a6ab`
- name: `TokenExtCreateEnvironment`
- size: `1967`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019ef0`

## callees

- `0x180019efc`
- `0x18001a6b4`
- `0x180033604`
- `0x18003364c`
- `0x18008275d`
- `0x18008278d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlCreateEnvironmentEx` at `0x18001a08f`
- `ntdll!RtlCreateEnvironmentEx` at `0x18001a08f`
- `ntdll!RtlDestroyEnvironment` at `0x18001a662`
- `ntdll!RtlDestroyEnvironment` at `0x18001a662`
- `ntdll!NtQueryInformationToken` at `0x180019fcd`
- `ntdll!NtQueryInformationToken` at `0x18001a00c`
- `ntdll!NtQueryInformationToken` at `0x180019fcd`
- `ntdll!NtQueryInformationToken` at `0x18001a00c`
- `ntdll!wcslen` at `0x18001a19d`
- `ntdll!wcslen` at `0x18001a29b`
- `ntdll!wcslen` at `0x18001a2d8`
- `ntdll!wcslen` at `0x18001a30a`
- `ntdll!wcslen` at `0x18001a352`
- `ntdll!wcslen` at `0x18001a36b`
- `ntdll!wcslen` at `0x18001a19d`
- `ntdll!wcslen` at `0x18001a29b`
- `ntdll!wcslen` at `0x18001a2d8`
- `ntdll!wcslen` at `0x18001a30a`
- `ntdll!wcslen` at `0x18001a352`
- `ntdll!wcslen` at `0x18001a36b`
- `ntdll!wcsstr` at `0x18001a27d`
- `ntdll!wcsstr` at `0x18001a2f2`
- `ntdll!wcsstr` at `0x18001a27d`
- `ntdll!wcsstr` at `0x18001a2f2`
- `ntdll!RtlGetAppContainerSidType` at `0x18001a02c`
- `ntdll!RtlGetAppContainerSidType` at `0x18001a0ad`
- `ntdll!RtlGetAppContainerSidType` at `0x18001a02c`
- `ntdll!RtlGetAppContainerSidType` at `0x18001a0ad`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001a483`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001a534`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001a56c`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001a483`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001a534`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001a56c`
- `ntdll!RtlGetAppContainerParent` at `0x18001a240`
- `ntdll!RtlGetAppContainerParent` at `0x18001a240`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001a0e8`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001a16e`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001a0e8`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001a16e`
- `ntdll!RtlInitUnicodeString` at `0x18001a453`
- `ntdll!RtlInitUnicodeString` at `0x18001a46a`
- `ntdll!RtlInitUnicodeString` at `0x18001a502`
- `ntdll!RtlInitUnicodeString` at `0x18001a51a`
- `ntdll!RtlInitUnicodeString` at `0x18001a552`
- `ntdll!RtlInitUnicodeString` at `0x18001a453`
- `ntdll!RtlInitUnicodeString` at `0x18001a46a`
- `ntdll!RtlInitUnicodeString` at `0x18001a502`
- `ntdll!RtlInitUnicodeString` at `0x18001a51a`
- `ntdll!RtlInitUnicodeString` at `0x18001a552`
- `ntdll!RtlFreeHeap` at `0x18001a5b7`
- `ntdll!RtlFreeHeap` at `0x18001a5df`
- `ntdll!RtlFreeHeap` at `0x18001a602`
- `ntdll!RtlFreeHeap` at `0x18001a625`
- `ntdll!RtlFreeHeap` at `0x18001a648`
- `ntdll!RtlFreeHeap` at `0x18001a5b7`
- `ntdll!RtlFreeHeap` at `0x18001a5df`
- `ntdll!RtlFreeHeap` at `0x18001a602`
- `ntdll!RtlFreeHeap` at `0x18001a625`
- `ntdll!RtlFreeHeap` at `0x18001a648`
- `ntdll!RtlAllocateHeap` at `0x18001a118`
- `ntdll!RtlAllocateHeap` at `0x18001a1c6`
- `ntdll!RtlAllocateHeap` at `0x18001a391`
- `ntdll!RtlAllocateHeap` at `0x18001a4af`
- `ntdll!RtlAllocateHeap` at `0x18001a118`
- `ntdll!RtlAllocateHeap` at `0x18001a1c6`
- `ntdll!RtlAllocateHeap` at `0x18001a391`
- `ntdll!RtlAllocateHeap` at `0x18001a4af`
- `KERNELBASE!AppContainerLookupMoniker` at `0x18001a070`
- `KERNELBASE!AppContainerLookupMoniker` at `0x18001a070`
- `KERNELBASE!AppContainerFreeMemory` at `0x18001a594`
- `KERNELBASE!AppContainerFreeMemory` at `0x18001a594`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a04f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a04f`

## string_xrefs

- `0x18001a4df`: `\Temp`

## pseudocode

```c
NTSTATUS __fastcall TokenExtCreateEnvironment(PSID Sid, __int64 a2, PWSTR *a3)
{
  __int64 v4; // rbx
  wchar_t *v6; // r15
  NTSTATUS result; // eax
  WCHAR *v8; // rdi
  wchar_t *v9; // r12
  WCHAR *v10; // r13
  PSID v11; // r14
  NTSTATUS AppContainerSidType; // ebx
  int v13; // eax
  wchar_t *Heap; // rax
  __int64 v15; // rbx
  SIZE_T v16; // rsi
  WCHAR *v17; // rax
  wchar_t *v18; // r8
  int ParentAppContainerMoniker; // eax
  wchar_t *v20; // rax
  wchar_t *v21; // r14
  size_t v22; // rax
  wchar_t *v23; // rbx
  wchar_t *v24; // rcx
  char *v25; // r8
  int v26; // edx
  int v27; // eax
  __int64 v28; // rbx
  WCHAR *v29; // rax
  SIZE_T v30; // rsi
  WCHAR *v31; // rax
  int v32; // ecx
  int v33; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR Environment; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h]
  wchar_t *String; // [rsp+50h] [rbp-B0h] BYREF
  int TokenInformation; // [rsp+58h] [rbp-A8h] BYREF
  int v39; // [rsp+5Ch] [rbp-A4h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *SubStr; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING v43; // [rsp+78h] [rbp-88h] BYREF
  PWSTR *v44; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING Value; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING Name; // [rsp+B0h] [rbp-50h] BYREF
  PSID pSid1[10]; // [rsp+C0h] [rbp-40h] BYREF

  v44 = a3;
  v42 = a2;
  v4 = a2;
  TokenInformation = 0;
  String = 0;
  ReturnLength = 0;
  v36 = 0;
  Environment = 0;
  DestinationString = 0;
  Name = 0;
  Value = 0;
  v43 = 0;
  memset_0(pSid1, 0, 0x4Cu);
  v33 = 0;
  v6 = 0;
  v39 = 0;
  P = 0;
  SubStr = 0;
  *a3 = 0;
  result = NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFALL,
             TokenIsAppContainer,
             &TokenInformation,
             4u,
             &ReturnLength);
  if ( result < 0 )
    return result;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( TokenInformation )
  {
    ReturnLength = 76;
    result = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenAppContainerSid, pSid1, 0x4Cu, &ReturnLength);
    if ( result < 0 )
      return result;
    v11 = pSid1[0];
    AppContainerSidType = RtlGetAppContainerSidType(pSid1[0], &v33);
    if ( AppContainerSidType < 0 )
      goto LABEL_53;
    if ( v33 == 2 && EqualSid(v11, Sid) )
      return 0;
    v4 = v42;
  }
  v13 = AppContainerLookupMoniker(Sid, &String);
  if ( v13 >= 0 )
  {
    AppContainerSidType = RtlCreateEnvironmentEx(v4, &Environment, 0);
    if ( AppContainerSidType < 0 )
      goto LABEL_53;
    AppContainerSidType = RtlGetAppContainerSidType(Sid, &v39);
    if ( AppContainerSidType < 0 )
      goto LABEL_53;
    AppContainerSidType = RtlQueryEnvironmentVariable(Environment, L"LOCALAPPDATA", 12);
    if ( AppContainerSidType != -1073741789 )
      goto LABEL_53;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v36);
    v9 = Heap;
    if ( !Heap )
      goto LABEL_13;
    memset_0(Heap, 0, 2 * v36);
    AppContainerSidType = RtlQueryEnvironmentVariable(Environment, L"LOCALAPPDATA", 12);
    if ( AppContainerSidType < 0 )
      goto LABEL_53;
    if ( v39 == 2 )
    {
      v15 = v36 + 11;
      v16 = 2 * (v15 + wcslen(String)) + 10;
      v17 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      v8 = v17;
      if ( v17 )
      {
        AppContainerSidType = RtlStringCbCopyW(v17, v16, v9);
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        AppContainerSidType = RtlStringCbCatW(v8, v16, L"\\Packages\\");
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        AppContainerSidType = RtlStringCbCatW(v8, v16, String);
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        v18 = (wchar_t *)L"\\AC";
        goto LABEL_45;
      }
      goto LABEL_13;
    }
    AppContainerSidType = RtlGetAppContainerParent(Sid, &P);
    if ( AppContainerSidType < 0 )
      goto LABEL_53;
    ParentAppContainerMoniker = GetParentAppContainerMoniker(Sid, P);
    v6 = SubStr;
    AppContainerSidType = ParentAppContainerMoniker;
    if ( ParentAppContainerMoniker < 0 )
      goto LABEL_53;
    v20 = wcsstr(v9, SubStr);
    v21 = v20;
    if ( v33 == 2 )
    {
      if ( !v20 || (v22 = wcslen(v6), wcscmp_0(&v21[v22], L"\\AC")) )
      {
        AppContainerSidType = -1073741811;
        goto LABEL_53;
      }
LABEL_35:
      v28 = 2 * v36;
      if ( !v21 )
        v28 += 2 * wcslen(v6) + 30;
      v16 = v28 + 2 * (wcslen(String) + 5);
      v29 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      v8 = v29;
      if ( v29 )
      {
        AppContainerSidType = RtlStringCbCopyW(v29, v16, v9);
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        if ( !v21 )
        {
          AppContainerSidType = RtlStringCbCatW(v8, v16, L"\\Packages\\");
          if ( AppContainerSidType < 0 )
            goto LABEL_53;
          AppContainerSidType = RtlStringCbCatW(v8, v16, v6);
          if ( AppContainerSidType < 0 )
            goto LABEL_53;
          AppContainerSidType = RtlStringCbCatW(v8, v16, L"\\AC");
          if ( AppContainerSidType < 0 )
            goto LABEL_53;
        }
        AppContainerSidType = RtlStringCbCatW(v8, v16, L"\\#!");
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        v18 = String;
LABEL_45:
        AppContainerSidType = RtlStringCbCatW(v8, v16, v18);
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        RtlInitUnicodeString(&DestinationString, v8);
        RtlInitUnicodeString(&Name, L"LOCALAPPDATA");
        AppContainerSidType = RtlSetEnvironmentVariable(&Environment, &Name, &DestinationString);
        if ( AppContainerSidType < 0 )
          goto LABEL_53;
        v30 = v16 + 14;
        v31 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
        v10 = v31;
        if ( v31 )
        {
          AppContainerSidType = RtlStringCbCopyW(v31, v30, v8);
          if ( AppContainerSidType >= 0 )
          {
            AppContainerSidType = RtlStringCbCatW(v10, v30, L"\\Temp");
            if ( AppContainerSidType >= 0 )
            {
              RtlInitUnicodeString(&Value, v10);
              RtlInitUnicodeString(&v43, L"TEMP");
              AppContainerSidType = RtlSetEnvironmentVariable(&Environment, &v43, &Value);
              if ( AppContainerSidType >= 0 )
              {
                RtlInitUnicodeString(&v43, L"TMP");
                AppContainerSidType = RtlSetEnvironmentVariable(&Environment, &v43, &Value);
                if ( AppContainerSidType >= 0 )
                  *v44 = Environment;
              }
            }
          }
          goto LABEL_53;
        }
      }
LABEL_13:
      AppContainerSidType = -1073741801;
LABEL_53:
      if ( String )
        AppContainerFreeMemory();
      if ( v9 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      if ( v8 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
      if ( v10 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      if ( AppContainerSidType < 0 )
      {
        if ( Environment )
          RtlDestroyEnvironment(Environment);
      }
      return AppContainerSidType;
    }
    if ( v33 != 1 )
      goto LABEL_35;
    if ( !v20 )
      goto LABEL_35;
    v23 = &v20[wcslen(v6)];
    if ( v23 != wcsstr(v23, L"\\AC\\#!") )
      goto LABEL_35;
    v24 = &v23[wcslen(L"\\AC\\#!")];
    v25 = (char *)((char *)String - (char *)v24);
    do
    {
      v26 = *(unsigned __int16 *)&v25[(_QWORD)v24];
      v27 = *v24 - v26;
      if ( v27 )
        break;
      ++v24;
    }
    while ( v26 );
    if ( v27 )
      goto LABEL_35;
    return 0;
  }
  v32 = (unsigned __int16)v13;
  result = -1073741823;
  if ( v32 == 2 )
    return -1073741809;
  return result;
}

```

## disassembly

```asm
0x180019efc  mov     [rsp-8+arg_18], rbx
0x180019f01  push    rbp
0x180019f02  push    rsi
0x180019f03  push    rdi
0x180019f04  push    r12
0x180019f06  push    r13
0x180019f08  push    r14
0x180019f0a  push    r15
0x180019f0c  lea     rbp, [rsp-20h]
0x180019f11  sub     rsp, 120h
0x180019f18  mov     rax, cs:__security_cookie
0x180019f1f  xor     rax, rsp
0x180019f22  mov     [rbp+50h+var_40], rax
0x180019f26  xorps   xmm0, xmm0
0x180019f29  mov     [rbp+50h+var_C8], r8
0x180019f2d  mov     rdi, r8
0x180019f30  mov     [rsp+150h+var_E0], rdx
0x180019f35  mov     rbx, rdx
0x180019f38  mov     [rsp+150h+TokenInformation], 0
0x180019f40  mov     rsi, rcx
0x180019f43  mov     [rsp+150h+String], 0
0x180019f4c  xorps   xmm1, xmm1
0x180019f4f  mov     [rsp+150h+var_110], 0
0x180019f57  mov     r14d, 4Ch ; 'L'
0x180019f5d  mov     [rsp+150h+var_108], 0
0x180019f66  mov     r8d, r14d; Size
0x180019f69  mov     [rsp+150h+Environment], 0
0x180019f72  xor     edx, edx; Val
0x180019f74  lea     rcx, [rbp+50h+pSid1]; void *
0x180019f78  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x180019f7c  movups  xmmword ptr [rbp+50h+Name.Length], xmm0
0x180019f80  movups  xmmword ptr [rbp+50h+Value.Length], xmm0
0x180019f84  movups  xmmword ptr [rsp+150h+var_D8.Length], xmm1
0x180019f89  call    memset_0
0x180019f8e  lea     rax, [rsp+150h+var_110]
0x180019f93  mov     [rsp+150h+var_120], 0
0x180019f9b  xor     r15d, r15d
0x180019f9e  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x180019fa3  lea     r9d, [r14-48h]; TokenInformationLength
0x180019fa7  mov     [rsp+150h+var_F4], 0
0x180019faf  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x180019fb4  mov     [rsp+150h+P], 0
0x180019fbd  lea     edx, [r14-2Fh]; TokenInformationClass
0x180019fc1  mov     [rsp+150h+SubStr], r15
0x180019fc6  lea     rcx, [r14-52h]; TokenHandle
0x180019fca  mov     [rdi], r15
0x180019fcd  call    cs:__imp_NtQueryInformationToken
0x180019fd4  nop     dword ptr [rax+rax+00h]
0x180019fd9  test    eax, eax
0x180019fdb  js      loc_18001A683
0x180019fe1  xor     edi, edi
0x180019fe3  xor     r12d, r12d
0x180019fe6  xor     r13d, r13d
0x180019fe9  cmp     [rsp+150h+TokenInformation], edi
0x180019fed  jz      short loc_18001A068
0x180019fef  lea     rax, [rsp+150h+var_110]
0x180019ff4  mov     [rsp+150h+var_110], r14d
0x180019ff9  mov     r9d, r14d; TokenInformationLength
0x180019ffc  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x18001a001  lea     r8, [rbp+50h+pSid1]; TokenInformation
0x18001a005  lea     edx, [rdi+1Fh]; TokenInformationClass
0x18001a008  lea     rcx, [rdi-6]; TokenHandle
0x18001a00c  call    cs:__imp_NtQueryInformationToken
0x18001a013  nop     dword ptr [rax+rax+00h]
0x18001a018  test    eax, eax
0x18001a01a  js      loc_18001A683
0x18001a020  mov     r14, [rbp+50h+pSid1]
0x18001a024  lea     rdx, [rsp+150h+var_120]
0x18001a029  mov     rcx, r14
0x18001a02c  call    cs:__imp_RtlGetAppContainerSidType
0x18001a033  nop     dword ptr [rax+rax+00h]
0x18001a038  mov     ebx, eax
0x18001a03a  test    eax, eax
0x18001a03c  js      loc_18001A58A
0x18001a042  cmp     [rsp+150h+var_120], 2
0x18001a047  jnz     short loc_18001A063
0x18001a049  mov     rdx, rsi; pSid2
0x18001a04c  mov     rcx, r14; pSid1
0x18001a04f  call    cs:__imp_EqualSid
0x18001a056  nop     dword ptr [rax+rax+00h]
0x18001a05b  test    eax, eax
0x18001a05d  jnz     loc_18001A33A
0x18001a063  mov     rbx, [rsp+150h+var_E0]
0x18001a068  lea     rdx, [rsp+150h+String]
0x18001a06d  mov     rcx, rsi
0x18001a070  call    cs:__imp_AppContainerLookupMoniker
0x18001a077  nop     dword ptr [rax+rax+00h]
0x18001a07c  test    eax, eax
0x18001a07e  js      loc_18001A672
0x18001a084  xor     r8d, r8d
0x18001a087  lea     rdx, [rsp+150h+Environment]
0x18001a08c  mov     rcx, rbx
0x18001a08f  call    cs:__imp_RtlCreateEnvironmentEx
0x18001a096  nop     dword ptr [rax+rax+00h]
0x18001a09b  mov     ebx, eax
0x18001a09d  test    eax, eax
0x18001a09f  js      loc_18001A58A
0x18001a0a5  lea     rdx, [rsp+150h+var_F4]
0x18001a0aa  mov     rcx, rsi
0x18001a0ad  call    cs:__imp_RtlGetAppContainerSidType
0x18001a0b4  nop     dword ptr [rax+rax+00h]
0x18001a0b9  mov     ebx, eax
0x18001a0bb  test    eax, eax
0x18001a0bd  js      loc_18001A58A
0x18001a0c3  mov     rcx, [rsp+150h+Environment]
0x18001a0c8  lea     rax, [rsp+150h+var_108]
0x18001a0cd  xor     r9d, r9d
0x18001a0d0  mov     [rsp+150h+var_128], rax
0x18001a0d5  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x18001a0dc  mov     [rsp+150h+ReturnLength], rdi
0x18001a0e1  lea     r14d, [r9+0Ch]
0x18001a0e5  mov     r8d, r14d
0x18001a0e8  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001a0ef  nop     dword ptr [rax+rax+00h]
0x18001a0f4  mov     ebx, eax
0x18001a0f6  cmp     eax, 0C0000023h
0x18001a0fb  jnz     loc_18001A58A
0x18001a101  mov     rcx, gs:60h
0x18001a10a  xor     edx, edx; Flags
0x18001a10c  mov     r8, [rsp+150h+var_108]
0x18001a111  add     r8, r8; Size
0x18001a114  mov     rcx, [rcx+30h]; HeapHandle
0x18001a118  call    cs:__imp_RtlAllocateHeap
0x18001a11f  nop     dword ptr [rax+rax+00h]
0x18001a124  mov     r12, rax
0x18001a127  test    rax, rax
0x18001a12a  jnz     short loc_18001A136
0x18001a12c  mov     ebx, 0C0000017h
0x18001a131  jmp     loc_18001A58A
0x18001a136  mov     r8, [rsp+150h+var_108]
0x18001a13b  xor     edx, edx; Val
0x18001a13d  add     r8, r8; Size
0x18001a140  mov     rcx, r12; void *
0x18001a143  call    memset_0
0x18001a148  mov     rcx, [rsp+150h+Environment]
0x18001a14d  lea     rax, [rsp+150h+var_108]
0x18001a152  mov     [rsp+150h+var_128], rax
0x18001a157  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x18001a15e  mov     rax, [rsp+150h+var_108]
0x18001a163  mov     r9, r12
0x18001a166  mov     r8, r14
0x18001a169  mov     [rsp+150h+ReturnLength], rax
0x18001a16e  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001a175  nop     dword ptr [rax+rax+00h]
0x18001a17a  mov     ebx, eax
0x18001a17c  test    eax, eax
0x18001a17e  js      loc_18001A58A
0x18001a184  cmp     [rsp+150h+var_F4], 2
0x18001a189  jnz     loc_18001A238
0x18001a18f  mov     rbx, [rsp+150h+var_108]
0x18001a194  mov     rcx, [rsp+150h+String]; String
0x18001a199  add     rbx, 0Bh
0x18001a19d  call    cs:__imp_wcslen
0x18001a1a4  nop     dword ptr [rax+rax+00h]
0x18001a1a9  mov     rcx, gs:60h
0x18001a1b2  xor     edx, edx; Flags
0x18001a1b4  add     rax, rbx
0x18001a1b7  mov     rcx, [rcx+30h]; HeapHandle
0x18001a1bb  lea     rsi, ds:0Ah[rax*2]
0x18001a1c3  mov     r8, rsi; Size
0x18001a1c6  call    cs:__imp_RtlAllocateHeap
0x18001a1cd  nop     dword ptr [rax+rax+00h]
0x18001a1d2  mov     rdi, rax
0x18001a1d5  test    rax, rax
0x18001a1d8  jz      loc_18001A12C
0x18001a1de  mov     r8, r12
0x18001a1e1  mov     rdx, rsi
0x18001a1e4  mov     rcx, rax
0x18001a1e7  call    RtlStringCbCopyW
0x18001a1ec  mov     ebx, eax
0x18001a1ee  test    eax, eax
0x18001a1f0  js      loc_18001A58A
0x18001a1f6  lea     r8, aPackages; "\\Packages\\"
0x18001a1fd  mov     rdx, rsi
0x18001a200  mov     rcx, rdi
0x18001a203  call    RtlStringCbCatW
0x18001a208  mov     ebx, eax
0x18001a20a  test    eax, eax
0x18001a20c  js      loc_18001A58A
0x18001a212  mov     r8, [rsp+150h+String]
0x18001a217  mov     rdx, rsi
0x18001a21a  mov     rcx, rdi
0x18001a21d  call    RtlStringCbCatW
0x18001a222  mov     ebx, eax
0x18001a224  test    eax, eax
0x18001a226  js      loc_18001A58A
0x18001a22c  lea     r8, aAc; "\\AC"
0x18001a233  jmp     loc_18001A437
0x18001a238  lea     rdx, [rsp+150h+P]
0x18001a23d  mov     rcx, rsi
0x18001a240  call    cs:__imp_RtlGetAppContainerParent
0x18001a247  nop     dword ptr [rax+rax+00h]
0x18001a24c  mov     ebx, eax
0x18001a24e  test    eax, eax
0x18001a250  js      loc_18001A58A
0x18001a256  mov     rdx, [rsp+150h+P]; PSID
0x18001a25b  lea     r8, [rsp+150h+SubStr]
0x18001a260  mov     rcx, rsi; Sid
0x18001a263  call    GetParentAppContainerMoniker
0x18001a268  mov     r15, [rsp+150h+SubStr]
0x18001a26d  mov     ebx, eax
0x18001a26f  test    eax, eax
0x18001a271  js      loc_18001A58A
0x18001a277  mov     rdx, r15; SubStr
0x18001a27a  mov     rcx, r12; Str
0x18001a27d  call    cs:__imp_wcsstr
0x18001a284  nop     dword ptr [rax+rax+00h]
0x18001a289  cmp     [rsp+150h+var_120], 2
0x18001a28e  mov     r14, rax
0x18001a291  jnz     short loc_18001A2C9
0x18001a293  test    rax, rax
0x18001a296  jz      short loc_18001A2BF
0x18001a298  mov     rcx, r15; String
0x18001a29b  call    cs:__imp_wcslen
0x18001a2a2  nop     dword ptr [rax+rax+00h]
0x18001a2a7  lea     rdx, aAc; "\\AC"
0x18001a2ae  lea     rcx, [r14+rax*2]; String1
0x18001a2b2  call    wcscmp_0
0x18001a2b7  test    eax, eax
0x18001a2b9  jz      loc_18001A341
0x18001a2bf  mov     ebx, 0C000000Dh
0x18001a2c4  jmp     loc_18001A58A
0x18001a2c9  cmp     [rsp+150h+var_120], 1
0x18001a2ce  jnz     short loc_18001A341
0x18001a2d0  test    r14, r14
0x18001a2d3  jz      short loc_18001A341
0x18001a2d5  mov     rcx, r15; String
0x18001a2d8  call    cs:__imp_wcslen
0x18001a2df  nop     dword ptr [rax+rax+00h]
0x18001a2e4  lea     rdx, aAc_0; "\\AC\\#!"
0x18001a2eb  lea     rbx, [r14+rax*2]
0x18001a2ef  mov     rcx, rbx; Str
0x18001a2f2  call    cs:__imp_wcsstr
0x18001a2f9  nop     dword ptr [rax+rax+00h]
0x18001a2fe  cmp     rbx, rax
0x18001a301  jnz     short loc_18001A341
0x18001a303  lea     rcx, aAc_0; "\\AC\\#!"
0x18001a30a  call    cs:__imp_wcslen
0x18001a311  nop     dword ptr [rax+rax+00h]
0x18001a316  mov     r8, [rsp+150h+String]
0x18001a31b  lea     rcx, [rbx+rax*2]
0x18001a31f  sub     r8, rcx
0x18001a322  movzx   eax, word ptr [rcx]
0x18001a325  movzx   edx, word ptr [rcx+r8]
0x18001a32a  sub     eax, edx
0x18001a32c  jnz     short loc_18001A336
0x18001a32e  add     rcx, 2
0x18001a332  test    edx, edx
0x18001a334  jnz     short loc_18001A322
0x18001a336  test    eax, eax
0x18001a338  jnz     short loc_18001A341
0x18001a33a  xor     eax, eax
0x18001a33c  jmp     loc_18001A683
0x18001a341  mov     rax, [rsp+150h+var_108]
0x18001a346  lea     rbx, [rax+rax]
0x18001a34a  test    r14, r14
0x18001a34d  jnz     short loc_18001A366
0x18001a34f  mov     rcx, r15; String
0x18001a352  call    cs:__imp_wcslen
0x18001a359  nop     dword ptr [rax+rax+00h]
0x18001a35e  lea     rbx, [rbx+rax*2]
0x18001a362  add     rbx, 1Eh
0x18001a366  mov     rcx, [rsp+150h+String]; String
0x18001a36b  call    cs:__imp_wcslen
0x18001a372  nop     dword ptr [rax+rax+00h]
0x18001a377  mov     rcx, gs:60h
0x18001a380  xor     edx, edx; Flags
0x18001a382  add     rax, 5
0x18001a386  mov     rcx, [rcx+30h]; HeapHandle
0x18001a38a  lea     rsi, [rbx+rax*2]
0x18001a38e  mov     r8, rsi; Size
0x18001a391  call    cs:__imp_RtlAllocateHeap
0x18001a398  nop     dword ptr [rax+rax+00h]
0x18001a39d  mov     rdi, rax
0x18001a3a0  test    rax, rax
0x18001a3a3  jz      loc_18001A12C
0x18001a3a9  mov     r8, r12
0x18001a3ac  mov     rdx, rsi
0x18001a3af  mov     rcx, rax
0x18001a3b2  call    RtlStringCbCopyW
0x18001a3b7  mov     ebx, eax
0x18001a3b9  test    eax, eax
0x18001a3bb  js      loc_18001A58A
0x18001a3c1  test    r14, r14
0x18001a3c4  jnz     short loc_18001A416
0x18001a3c6  lea     r8, aPackages; "\\Packages\\"
0x18001a3cd  mov     rdx, rsi
0x18001a3d0  mov     rcx, rdi
0x18001a3d3  call    RtlStringCbCatW
0x18001a3d8  mov     ebx, eax
0x18001a3da  test    eax, eax
0x18001a3dc  js      loc_18001A58A
0x18001a3e2  mov     r8, r15
0x18001a3e5  mov     rdx, rsi
0x18001a3e8  mov     rcx, rdi
0x18001a3eb  call    RtlStringCbCatW
0x18001a3f0  mov     ebx, eax
0x18001a3f2  test    eax, eax
0x18001a3f4  js      loc_18001A58A
0x18001a3fa  lea     r8, aAc; "\\AC"
  ... truncated ...
```
