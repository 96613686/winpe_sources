# TokenExtCreateEnvironment

- ea: `0x18001c2dc`
- end: `0x18001c9a4`
- name: `TokenExtCreateEnvironment`
- size: `1736`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c2d0`

## callees

- `0x18001c2dc`
- `0x18001c9ac`
- `0x1800315e8`
- `0x180031630`
- `0x18007a7dd`
- `0x18007a80d`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlCreateEnvironmentEx` at `0x18001c451`
- `ntdll!RtlCreateEnvironmentEx` at `0x18001c451`
- `ntdll!RtlDestroyEnvironment` at `0x18001c962`
- `ntdll!RtlDestroyEnvironment` at `0x18001c962`
- `ntdll!NtQueryInformationToken` at `0x18001c3ad`
- `ntdll!NtQueryInformationToken` at `0x18001c3e6`
- `ntdll!NtQueryInformationToken` at `0x18001c3ad`
- `ntdll!NtQueryInformationToken` at `0x18001c3e6`
- `ntdll!wcslen` at `0x18001c541`
- `ntdll!wcslen` at `0x18001c627`
- `ntdll!wcslen` at `0x18001c65a`
- `ntdll!wcslen` at `0x18001c680`
- `ntdll!wcslen` at `0x18001c6c2`
- `ntdll!wcslen` at `0x18001c6d5`
- `ntdll!wcslen` at `0x18001c541`
- `ntdll!wcslen` at `0x18001c627`
- `ntdll!wcslen` at `0x18001c65a`
- `ntdll!wcslen` at `0x18001c680`
- `ntdll!wcslen` at `0x18001c6c2`
- `ntdll!wcslen` at `0x18001c6d5`
- `ntdll!wcsstr` at `0x18001c60f`
- `ntdll!wcsstr` at `0x18001c66e`
- `ntdll!wcsstr` at `0x18001c60f`
- `ntdll!wcsstr` at `0x18001c66e`
- `ntdll!RtlGetAppContainerSidType` at `0x18001c400`
- `ntdll!RtlGetAppContainerSidType` at `0x18001c469`
- `ntdll!RtlGetAppContainerSidType` at `0x18001c400`
- `ntdll!RtlGetAppContainerSidType` at `0x18001c469`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001c7d5`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001c86a`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001c896`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001c7d5`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001c86a`
- `ntdll!RtlSetEnvironmentVariable` at `0x18001c896`
- `ntdll!RtlGetAppContainerParent` at `0x18001c5d8`
- `ntdll!RtlGetAppContainerParent` at `0x18001c5d8`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001c49e`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001c518`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001c49e`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001c518`
- `ntdll!RtlInitUnicodeString` at `0x18001c7b1`
- `ntdll!RtlInitUnicodeString` at `0x18001c7c2`
- `ntdll!RtlInitUnicodeString` at `0x18001c844`
- `ntdll!RtlInitUnicodeString` at `0x18001c856`
- `ntdll!RtlInitUnicodeString` at `0x18001c882`
- `ntdll!RtlInitUnicodeString` at `0x18001c7b1`
- `ntdll!RtlInitUnicodeString` at `0x18001c7c2`
- `ntdll!RtlInitUnicodeString` at `0x18001c844`
- `ntdll!RtlInitUnicodeString` at `0x18001c856`
- `ntdll!RtlInitUnicodeString` at `0x18001c882`
- `ntdll!RtlFreeHeap` at `0x18001c8d5`
- `ntdll!RtlFreeHeap` at `0x18001c8f7`
- `ntdll!RtlFreeHeap` at `0x18001c914`
- `ntdll!RtlFreeHeap` at `0x18001c931`
- `ntdll!RtlFreeHeap` at `0x18001c94e`
- `ntdll!RtlFreeHeap` at `0x18001c8d5`
- `ntdll!RtlFreeHeap` at `0x18001c8f7`
- `ntdll!RtlFreeHeap` at `0x18001c914`
- `ntdll!RtlFreeHeap` at `0x18001c931`
- `ntdll!RtlFreeHeap` at `0x18001c94e`
- `ntdll!RtlAllocateHeap` at `0x18001c4c8`
- `ntdll!RtlAllocateHeap` at `0x18001c564`
- `ntdll!RtlAllocateHeap` at `0x18001c6f5`
- `ntdll!RtlAllocateHeap` at `0x18001c7fb`
- `ntdll!RtlAllocateHeap` at `0x18001c4c8`
- `ntdll!RtlAllocateHeap` at `0x18001c564`
- `ntdll!RtlAllocateHeap` at `0x18001c6f5`
- `ntdll!RtlAllocateHeap` at `0x18001c7fb`
- `KERNELBASE!AppContainerLookupMoniker` at `0x18001c438`
- `KERNELBASE!AppContainerLookupMoniker` at `0x18001c438`
- `KERNELBASE!AppContainerFreeMemory` at `0x18001c8b8`
- `KERNELBASE!AppContainerFreeMemory` at `0x18001c8b8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001c41d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001c41d`

## string_xrefs

- `0x18001c825`: `\Temp`

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
0x18001c2dc  mov     [rsp-8+arg_18], rbx
0x18001c2e1  push    rbp
0x18001c2e2  push    rsi
0x18001c2e3  push    rdi
0x18001c2e4  push    r12
0x18001c2e6  push    r13
0x18001c2e8  push    r14
0x18001c2ea  push    r15
0x18001c2ec  lea     rbp, [rsp-20h]
0x18001c2f1  sub     rsp, 120h
0x18001c2f8  mov     rax, cs:__security_cookie
0x18001c2ff  xor     rax, rsp
0x18001c302  mov     [rbp+50h+var_40], rax
0x18001c306  xorps   xmm0, xmm0
0x18001c309  mov     [rbp+50h+var_C8], r8
0x18001c30d  mov     rdi, r8
0x18001c310  mov     [rsp+150h+var_E0], rdx
0x18001c315  mov     rbx, rdx
0x18001c318  mov     [rsp+150h+TokenInformation], 0
0x18001c320  mov     rsi, rcx
0x18001c323  mov     [rsp+150h+String], 0
0x18001c32c  xorps   xmm1, xmm1
0x18001c32f  mov     [rsp+150h+var_110], 0
0x18001c337  mov     r14d, 4Ch ; 'L'
0x18001c33d  mov     [rsp+150h+var_108], 0
0x18001c346  mov     r8d, r14d; Size
0x18001c349  mov     [rsp+150h+Environment], 0
0x18001c352  xor     edx, edx; Val
0x18001c354  lea     rcx, [rbp+50h+pSid1]; void *
0x18001c358  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x18001c35c  movups  xmmword ptr [rbp+50h+Name.Length], xmm0
0x18001c360  movups  xmmword ptr [rbp+50h+Value.Length], xmm0
0x18001c364  movups  xmmword ptr [rsp+150h+var_D8.Length], xmm1
0x18001c369  call    memset_0
0x18001c36e  lea     rax, [rsp+150h+var_110]
0x18001c373  mov     [rsp+150h+var_120], 0
0x18001c37b  xor     r15d, r15d
0x18001c37e  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x18001c383  lea     r9d, [r14-48h]; TokenInformationLength
0x18001c387  mov     [rsp+150h+var_F4], 0
0x18001c38f  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x18001c394  mov     [rsp+150h+P], 0
0x18001c39d  lea     edx, [r14-2Fh]; TokenInformationClass
0x18001c3a1  mov     [rsp+150h+SubStr], r15
0x18001c3a6  lea     rcx, [r14-52h]; TokenHandle
0x18001c3aa  mov     [rdi], r15
0x18001c3ad  call    cs:__imp_NtQueryInformationToken
0x18001c3b3  test    eax, eax
0x18001c3b5  js      loc_18001C97D
0x18001c3bb  xor     edi, edi
0x18001c3bd  xor     r12d, r12d
0x18001c3c0  xor     r13d, r13d
0x18001c3c3  cmp     [rsp+150h+TokenInformation], edi
0x18001c3c7  jz      short loc_18001C430
0x18001c3c9  lea     rax, [rsp+150h+var_110]
0x18001c3ce  mov     [rsp+150h+var_110], r14d
0x18001c3d3  mov     r9d, r14d; TokenInformationLength
0x18001c3d6  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x18001c3db  lea     r8, [rbp+50h+pSid1]; TokenInformation
0x18001c3df  lea     edx, [rdi+1Fh]; TokenInformationClass
0x18001c3e2  lea     rcx, [rdi-6]; TokenHandle
0x18001c3e6  call    cs:__imp_NtQueryInformationToken
0x18001c3ec  test    eax, eax
0x18001c3ee  js      loc_18001C97D
0x18001c3f4  mov     r14, [rbp+50h+pSid1]
0x18001c3f8  lea     rdx, [rsp+150h+var_120]
0x18001c3fd  mov     rcx, r14
0x18001c400  call    cs:__imp_RtlGetAppContainerSidType
0x18001c406  mov     ebx, eax
0x18001c408  test    eax, eax
0x18001c40a  js      loc_18001C8AE
0x18001c410  cmp     [rsp+150h+var_120], 2
0x18001c415  jnz     short loc_18001C42B
0x18001c417  mov     rdx, rsi; pSid2
0x18001c41a  mov     rcx, r14; pSid1
0x18001c41d  call    cs:__imp_EqualSid
0x18001c423  test    eax, eax
0x18001c425  jnz     loc_18001C6AA
0x18001c42b  mov     rbx, [rsp+150h+var_E0]
0x18001c430  lea     rdx, [rsp+150h+String]
0x18001c435  mov     rcx, rsi
0x18001c438  call    cs:__imp_AppContainerLookupMoniker
0x18001c43e  test    eax, eax
0x18001c440  js      loc_18001C96C
0x18001c446  xor     r8d, r8d
0x18001c449  lea     rdx, [rsp+150h+Environment]
0x18001c44e  mov     rcx, rbx
0x18001c451  call    cs:__imp_RtlCreateEnvironmentEx
0x18001c457  mov     ebx, eax
0x18001c459  test    eax, eax
0x18001c45b  js      loc_18001C8AE
0x18001c461  lea     rdx, [rsp+150h+var_F4]
0x18001c466  mov     rcx, rsi
0x18001c469  call    cs:__imp_RtlGetAppContainerSidType
0x18001c46f  mov     ebx, eax
0x18001c471  test    eax, eax
0x18001c473  js      loc_18001C8AE
0x18001c479  mov     rcx, [rsp+150h+Environment]
0x18001c47e  lea     rax, [rsp+150h+var_108]
0x18001c483  xor     r9d, r9d
0x18001c486  mov     [rsp+150h+var_128], rax
0x18001c48b  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x18001c492  mov     [rsp+150h+ReturnLength], rdi
0x18001c497  lea     r14d, [r9+0Ch]
0x18001c49b  mov     r8d, r14d
0x18001c49e  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001c4a4  mov     ebx, eax
0x18001c4a6  cmp     eax, 0C0000023h
0x18001c4ab  jnz     loc_18001C8AE
0x18001c4b1  mov     rcx, gs:60h
0x18001c4ba  xor     edx, edx; Flags
0x18001c4bc  mov     r8, [rsp+150h+var_108]
0x18001c4c1  add     r8, r8; Size
0x18001c4c4  mov     rcx, [rcx+30h]; HeapHandle
0x18001c4c8  call    cs:__imp_RtlAllocateHeap
0x18001c4ce  mov     r12, rax
0x18001c4d1  test    rax, rax
0x18001c4d4  jnz     short loc_18001C4E0
0x18001c4d6  mov     ebx, 0C0000017h
0x18001c4db  jmp     loc_18001C8AE
0x18001c4e0  mov     r8, [rsp+150h+var_108]
0x18001c4e5  xor     edx, edx; Val
0x18001c4e7  add     r8, r8; Size
0x18001c4ea  mov     rcx, r12; void *
0x18001c4ed  call    memset_0
0x18001c4f2  mov     rcx, [rsp+150h+Environment]
0x18001c4f7  lea     rax, [rsp+150h+var_108]
0x18001c4fc  mov     [rsp+150h+var_128], rax
0x18001c501  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x18001c508  mov     rax, [rsp+150h+var_108]
0x18001c50d  mov     r9, r12
0x18001c510  mov     r8, r14
0x18001c513  mov     [rsp+150h+ReturnLength], rax
0x18001c518  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001c51e  mov     ebx, eax
0x18001c520  test    eax, eax
0x18001c522  js      loc_18001C8AE
0x18001c528  cmp     [rsp+150h+var_F4], 2
0x18001c52d  jnz     loc_18001C5D0
0x18001c533  mov     rbx, [rsp+150h+var_108]
0x18001c538  mov     rcx, [rsp+150h+String]; String
0x18001c53d  add     rbx, 0Bh
0x18001c541  call    cs:__imp_wcslen
0x18001c547  mov     rcx, gs:60h
0x18001c550  xor     edx, edx; Flags
0x18001c552  add     rax, rbx
0x18001c555  mov     rcx, [rcx+30h]; HeapHandle
0x18001c559  lea     rsi, ds:0Ah[rax*2]
0x18001c561  mov     r8, rsi; Size
0x18001c564  call    cs:__imp_RtlAllocateHeap
0x18001c56a  mov     rdi, rax
0x18001c56d  test    rax, rax
0x18001c570  jz      loc_18001C4D6
0x18001c576  mov     r8, r12
0x18001c579  mov     rdx, rsi
0x18001c57c  mov     rcx, rax
0x18001c57f  call    RtlStringCbCopyW
0x18001c584  mov     ebx, eax
0x18001c586  test    eax, eax
0x18001c588  js      loc_18001C8AE
0x18001c58e  lea     r8, aPackages; "\\Packages\\"
0x18001c595  mov     rdx, rsi
0x18001c598  mov     rcx, rdi
0x18001c59b  call    RtlStringCbCatW
0x18001c5a0  mov     ebx, eax
0x18001c5a2  test    eax, eax
0x18001c5a4  js      loc_18001C8AE
0x18001c5aa  mov     r8, [rsp+150h+String]
0x18001c5af  mov     rdx, rsi
0x18001c5b2  mov     rcx, rdi
0x18001c5b5  call    RtlStringCbCatW
0x18001c5ba  mov     ebx, eax
0x18001c5bc  test    eax, eax
0x18001c5be  js      loc_18001C8AE
0x18001c5c4  lea     r8, aAc; "\\AC"
0x18001c5cb  jmp     loc_18001C795
0x18001c5d0  lea     rdx, [rsp+150h+P]
0x18001c5d5  mov     rcx, rsi
0x18001c5d8  call    cs:__imp_RtlGetAppContainerParent
0x18001c5de  mov     ebx, eax
0x18001c5e0  test    eax, eax
0x18001c5e2  js      loc_18001C8AE
0x18001c5e8  mov     rdx, [rsp+150h+P]; PSID
0x18001c5ed  lea     r8, [rsp+150h+SubStr]
0x18001c5f2  mov     rcx, rsi; Sid
0x18001c5f5  call    GetParentAppContainerMoniker
0x18001c5fa  mov     r15, [rsp+150h+SubStr]
0x18001c5ff  mov     ebx, eax
0x18001c601  test    eax, eax
0x18001c603  js      loc_18001C8AE
0x18001c609  mov     rdx, r15; SubStr
0x18001c60c  mov     rcx, r12; Str
0x18001c60f  call    cs:__imp_wcsstr
0x18001c615  cmp     [rsp+150h+var_120], 2
0x18001c61a  mov     r14, rax
0x18001c61d  jnz     short loc_18001C64B
0x18001c61f  test    rax, rax
0x18001c622  jz      short loc_18001C641
0x18001c624  mov     rcx, r15; String
0x18001c627  call    cs:__imp_wcslen
0x18001c62d  lea     rdx, aAc; "\\AC"
0x18001c634  lea     rcx, [r14+rax*2]; String1
0x18001c638  call    wcscmp_0
0x18001c63d  test    eax, eax
0x18001c63f  jz      short loc_18001C6B1
0x18001c641  mov     ebx, 0C000000Dh
0x18001c646  jmp     loc_18001C8AE
0x18001c64b  cmp     [rsp+150h+var_120], 1
0x18001c650  jnz     short loc_18001C6B1
0x18001c652  test    r14, r14
0x18001c655  jz      short loc_18001C6B1
0x18001c657  mov     rcx, r15; String
0x18001c65a  call    cs:__imp_wcslen
0x18001c660  lea     rdx, aAc_0; "\\AC\\#!"
0x18001c667  lea     rbx, [r14+rax*2]
0x18001c66b  mov     rcx, rbx; Str
0x18001c66e  call    cs:__imp_wcsstr
0x18001c674  cmp     rbx, rax
0x18001c677  jnz     short loc_18001C6B1
0x18001c679  lea     rcx, aAc_0; "\\AC\\#!"
0x18001c680  call    cs:__imp_wcslen
0x18001c686  mov     r8, [rsp+150h+String]
0x18001c68b  lea     rcx, [rbx+rax*2]
0x18001c68f  sub     r8, rcx
0x18001c692  movzx   eax, word ptr [rcx]
0x18001c695  movzx   edx, word ptr [rcx+r8]
0x18001c69a  sub     eax, edx
0x18001c69c  jnz     short loc_18001C6A6
0x18001c69e  add     rcx, 2
0x18001c6a2  test    edx, edx
0x18001c6a4  jnz     short loc_18001C692
0x18001c6a6  test    eax, eax
0x18001c6a8  jnz     short loc_18001C6B1
0x18001c6aa  xor     eax, eax
0x18001c6ac  jmp     loc_18001C97D
0x18001c6b1  mov     rax, [rsp+150h+var_108]
0x18001c6b6  lea     rbx, [rax+rax]
0x18001c6ba  test    r14, r14
0x18001c6bd  jnz     short loc_18001C6D0
0x18001c6bf  mov     rcx, r15; String
0x18001c6c2  call    cs:__imp_wcslen
0x18001c6c8  lea     rbx, [rbx+rax*2]
0x18001c6cc  add     rbx, 1Eh
0x18001c6d0  mov     rcx, [rsp+150h+String]; String
0x18001c6d5  call    cs:__imp_wcslen
0x18001c6db  mov     rcx, gs:60h
0x18001c6e4  xor     edx, edx; Flags
0x18001c6e6  add     rax, 5
0x18001c6ea  mov     rcx, [rcx+30h]; HeapHandle
0x18001c6ee  lea     rsi, [rbx+rax*2]
0x18001c6f2  mov     r8, rsi; Size
0x18001c6f5  call    cs:__imp_RtlAllocateHeap
0x18001c6fb  mov     rdi, rax
0x18001c6fe  test    rax, rax
0x18001c701  jz      loc_18001C4D6
0x18001c707  mov     r8, r12
0x18001c70a  mov     rdx, rsi
0x18001c70d  mov     rcx, rax
0x18001c710  call    RtlStringCbCopyW
0x18001c715  mov     ebx, eax
0x18001c717  test    eax, eax
0x18001c719  js      loc_18001C8AE
0x18001c71f  test    r14, r14
0x18001c722  jnz     short loc_18001C774
0x18001c724  lea     r8, aPackages; "\\Packages\\"
0x18001c72b  mov     rdx, rsi
0x18001c72e  mov     rcx, rdi
0x18001c731  call    RtlStringCbCatW
0x18001c736  mov     ebx, eax
0x18001c738  test    eax, eax
0x18001c73a  js      loc_18001C8AE
0x18001c740  mov     r8, r15
0x18001c743  mov     rdx, rsi
0x18001c746  mov     rcx, rdi
0x18001c749  call    RtlStringCbCatW
0x18001c74e  mov     ebx, eax
0x18001c750  test    eax, eax
0x18001c752  js      loc_18001C8AE
0x18001c758  lea     r8, aAc; "\\AC"
0x18001c75f  mov     rdx, rsi
0x18001c762  mov     rcx, rdi
0x18001c765  call    RtlStringCbCatW
0x18001c76a  mov     ebx, eax
0x18001c76c  test    eax, eax
0x18001c76e  js      loc_18001C8AE
0x18001c774  lea     r8, asc_18008C950; "\\#!"
0x18001c77b  mov     rdx, rsi
0x18001c77e  mov     rcx, rdi
0x18001c781  call    RtlStringCbCatW
0x18001c786  mov     ebx, eax
0x18001c788  test    eax, eax
0x18001c78a  js      loc_18001C8AE
0x18001c790  mov     r8, [rsp+150h+String]
0x18001c795  mov     rdx, rsi
0x18001c798  mov     rcx, rdi
0x18001c79b  call    RtlStringCbCatW
0x18001c7a0  mov     ebx, eax
0x18001c7a2  test    eax, eax
0x18001c7a4  js      loc_18001C8AE
0x18001c7aa  mov     rdx, rdi; SourceString
  ... truncated ...
```
