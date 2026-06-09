# GetUserIdString

- ea: `0x140014e5c`
- end: `0x1400150bb`
- name: `GetUserIdString`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14002bd70`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002140`
- `0x140002650`
- `0x140002dd0`
- `0x140003ec0`
- `0x140014e5c`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140014ea5`
- `ADVAPI32!OpenProcessToken` at `0x140014ea5`
- `ADVAPI32!GetTokenInformation` at `0x140014ecd`
- `ADVAPI32!GetTokenInformation` at `0x140014f14`
- `ADVAPI32!GetTokenInformation` at `0x140014ecd`
- `ADVAPI32!GetTokenInformation` at `0x140014f14`
- `ADVAPI32!IsValidSid` at `0x140014f44`
- `ADVAPI32!IsValidSid` at `0x140014f44`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140014f59`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140014f59`
- `KERNEL32!LocalFree` at `0x14001507e`
- `KERNEL32!LocalFree` at `0x14001507e`
- `KERNEL32!GetCurrentProcess` at `0x140014e95`
- `KERNEL32!GetCurrentProcess` at `0x140014e95`
- `KERNEL32!CloseHandle` at `0x140014f3b`
- `KERNEL32!CloseHandle` at `0x140014f3b`
- `KERNEL32!HeapFree` at `0x140014f2c`
- `KERNEL32!HeapFree` at `0x140015074`
- `KERNEL32!HeapFree` at `0x140014f2c`
- `KERNEL32!HeapFree` at `0x140015074`
- `KERNEL32!HeapAlloc` at `0x140014ee4`
- `KERNEL32!HeapAlloc` at `0x140014ee4`
- `KERNEL32!GetProcessHeap` at `0x140014ed6`
- `KERNEL32!GetProcessHeap` at `0x140014f1e`
- `KERNEL32!GetProcessHeap` at `0x140015066`
- `KERNEL32!GetProcessHeap` at `0x140014ed6`
- `KERNEL32!GetProcessHeap` at `0x140014f1e`
- `KERNEL32!GetProcessHeap` at `0x140015066`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140015043`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140015043`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140014fdb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140015037`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140014fdb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140015037`

## pseudocode

```c
char __fastcall GetUserIdString(int **a1)
{
  HANDLE CurrentProcess; // rax
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v6; // rsi
  HANDLE v7; // rax
  LPWSTR v8; // r12
  __int64 v9; // rbx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r13
  int *v12; // rcx
  unsigned __int64 v13; // rdi
  char *v14; // rdx
  size_t v15; // r8
  HANDLE v16; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-10h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v4 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v6 = (PSID *)HeapAlloc(ProcessHeap, 0, v4);
  memset_0(v6, 0, TokenInformationLength);
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength)
    || (CloseHandle(TokenHandle), !IsValidSid(*v6))
    || (StringSid = 0, !ConvertSidToStringSidW(*v6, &StringSid)) )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    return 0;
  }
  v8 = StringSid;
  if ( !StringSid )
    goto LABEL_30;
  v9 = -1;
  do
    ++v9;
  while ( StringSid[v9] );
  if ( !(_DWORD)v9 )
  {
LABEL_30:
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
    goto LABEL_31;
  }
  v10 = ((char *)StringSid - (char *)*a1) >> 1;
  v11 = (unsigned int)*(*a1 - 4);
  if ( (int)v9 < 0 )
LABEL_32:
    ATL::AtlThrowImpl(-2147024809);
  if ( (int)((*(*a1 - 3) - v9) | (1 - *(*a1 - 2))) < 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v9);
  }
  v12 = *a1;
  v13 = 2LL * (int)v9;
  if ( v10 > v11 )
  {
    v15 = 2LL * *(v12 - 3);
    if ( !v13 )
      goto LABEL_28;
    if ( v12 )
    {
      if ( v15 >= v13 )
      {
        _mm_lfence();
        memcpy_0(v12, v8, 2LL * (int)v9);
        goto LABEL_28;
      }
      memset_0(v12, 0, v15);
      goto LABEL_26;
    }
  }
  else
  {
    v14 = (char *)v12 + 2 * v10;
    if ( !v13 )
      goto LABEL_28;
    if ( v12 && v14 )
    {
      if ( 2LL * *(v12 - 3) >= v13 )
      {
        _mm_lfence();
        memmove_0(v12, v14, 2LL * (int)v9);
        goto LABEL_28;
      }
LABEL_26:
      *_errno() = 34;
      goto LABEL_27;
    }
  }
  *_errno() = 22;
LABEL_27:
  _invalid_parameter_noinfo();
LABEL_28:
  if ( (int)v9 > *(*a1 - 3) )
    goto LABEL_32;
  *(*a1 - 4) = v9;
  *(_WORD *)((char *)*a1 + v13) = 0;
LABEL_31:
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v6);
  LocalFree(StringSid);
  return 1;
}

```

## disassembly

```asm
0x140014e5c  mov     [rsp-28h+arg_8], rbx
0x140014e61  mov     [rsp-28h+arg_10], rsi
0x140014e66  mov     [rsp-28h+arg_18], rdi
0x140014e6b  push    rbp
0x140014e6c  push    r12
0x140014e6e  push    r13
0x140014e70  push    r14
0x140014e72  push    r15
0x140014e74  mov     rbp, rsp
0x140014e77  sub     rsp, 50h
0x140014e7b  mov     rax, cs:__security_cookie
0x140014e82  xor     rax, rsp
0x140014e85  mov     [rbp+var_8], rax
0x140014e89  xor     edi, edi
0x140014e8b  mov     r15, rcx
0x140014e8e  mov     [rbp+TokenHandle], rdi
0x140014e92  mov     [rbp+TokenInformationLength], edi
0x140014e95  call    cs:__imp_GetCurrentProcess
0x140014e9b  mov     rcx, rax; ProcessHandle
0x140014e9e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140014ea2  lea     edx, [rdi+8]; DesiredAccess
0x140014ea5  call    cs:__imp_OpenProcessToken
0x140014eab  test    eax, eax
0x140014ead  jnz     short loc_140014EB6
0x140014eaf  xor     al, al
0x140014eb1  jmp     loc_140015086
0x140014eb6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140014eba  lea     rax, [rbp+TokenInformationLength]
0x140014ebe  xor     r9d, r9d; TokenInformationLength
0x140014ec1  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x140014ec6  xor     r8d, r8d; TokenInformation
0x140014ec9  lea     edx, [r9+1]; TokenInformationClass
0x140014ecd  call    cs:__imp_GetTokenInformation
0x140014ed3  mov     ebx, [rbp+TokenInformationLength]
0x140014ed6  call    cs:__imp_GetProcessHeap
0x140014edc  mov     r8d, ebx; dwBytes
0x140014edf  xor     edx, edx; dwFlags
0x140014ee1  mov     rcx, rax; hHeap
0x140014ee4  call    cs:__imp_HeapAlloc
0x140014eea  mov     r8d, [rbp+TokenInformationLength]; Size
0x140014eee  xor     edx, edx; Val
0x140014ef0  mov     rcx, rax; void *
0x140014ef3  mov     rsi, rax
0x140014ef6  call    memset_0
0x140014efb  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140014eff  lea     rax, [rbp+TokenInformationLength]
0x140014f03  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140014f07  mov     r8, rsi; TokenInformation
0x140014f0a  mov     edx, 1; TokenInformationClass
0x140014f0f  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x140014f14  call    cs:__imp_GetTokenInformation
0x140014f1a  test    eax, eax
0x140014f1c  jnz     short loc_140014F37
0x140014f1e  call    cs:__imp_GetProcessHeap
0x140014f24  mov     r8, rsi; lpMem
0x140014f27  xor     edx, edx; dwFlags
0x140014f29  mov     rcx, rax; hHeap
0x140014f2c  call    cs:__imp_HeapFree
0x140014f32  jmp     loc_140014EAF
0x140014f37  mov     rcx, [rbp+TokenHandle]; hObject
0x140014f3b  call    cs:__imp_CloseHandle
0x140014f41  mov     rcx, [rsi]; pSid
0x140014f44  call    cs:__imp_IsValidSid
0x140014f4a  test    eax, eax
0x140014f4c  jz      short loc_140014F1E
0x140014f4e  mov     [rbp+StringSid], rdi
0x140014f52  lea     rdx, [rbp+StringSid]; StringSid
0x140014f56  mov     rcx, [rsi]; Sid
0x140014f59  call    cs:__imp_ConvertSidToStringSidW
0x140014f5f  test    eax, eax
0x140014f61  jz      short loc_140014F1E
0x140014f63  mov     r12, [rbp+StringSid]
0x140014f67  test    r12, r12
0x140014f6a  jz      loc_14001505E
0x140014f70  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140014f74  inc     rbx
0x140014f77  cmp     [r12+rbx*2], di
0x140014f7c  jnz     short loc_140014F74
0x140014f7e  test    ebx, ebx
0x140014f80  jz      loc_14001505E
0x140014f86  mov     rax, [r15]
0x140014f89  mov     r14, r12
0x140014f8c  sub     r14, rax
0x140014f8f  sar     r14, 1
0x140014f92  mov     r13d, [rax-10h]
0x140014f96  test    ebx, ebx
0x140014f98  js      loc_1400150B0
0x140014f9e  mov     ecx, 1
0x140014fa3  sub     ecx, [rax-8]
0x140014fa6  mov     eax, [rax-0Ch]
0x140014fa9  sub     eax, ebx
0x140014fab  or      ecx, eax
0x140014fad  jge     short loc_140014FBC
0x140014faf  lfence
0x140014fb2  mov     edx, ebx
0x140014fb4  mov     rcx, r15
0x140014fb7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z
0x140014fbc  mov     rcx, [r15]; void *
0x140014fbf  movsxd  rdi, ebx
0x140014fc2  add     rdi, rdi
0x140014fc5  cmp     r14, r13
0x140014fc8  ja      short loc_140015007
0x140014fca  lea     rdx, [rcx+r14*2]; Src
0x140014fce  xor     r14d, r14d
0x140014fd1  test    rdi, rdi
0x140014fd4  jz      short loc_140015049
0x140014fd6  test    rcx, rcx
0x140014fd9  jnz     short loc_140014FE9
0x140014fdb  call    cs:__imp__errno
0x140014fe1  mov     dword ptr [rax], 16h
0x140014fe7  jmp     short loc_140015043
0x140014fe9  test    rdx, rdx
0x140014fec  jz      short loc_140014FDB
0x140014fee  movsxd  rax, dword ptr [rcx-0Ch]
0x140014ff2  add     rax, rax
0x140014ff5  cmp     rax, rdi
0x140014ff8  jb      short loc_140015037
0x140014ffa  lfence
0x140014ffd  mov     r8, rdi; Size
0x140015000  call    memmove_0
0x140015005  jmp     short loc_140015049
0x140015007  movsxd  r8, dword ptr [rcx-0Ch]
0x14001500b  xor     r14d, r14d
0x14001500e  add     r8, r8; Size
0x140015011  test    rdi, rdi
0x140015014  jz      short loc_140015049
0x140015016  test    rcx, rcx
0x140015019  jz      short loc_140014FDB
0x14001501b  cmp     r8, rdi
0x14001501e  jb      short loc_140015030
0x140015020  lfence
0x140015023  mov     r8, rdi; Size
0x140015026  mov     rdx, r12; Src
0x140015029  call    memcpy_0
0x14001502e  jmp     short loc_140015049
0x140015030  xor     edx, edx; Val
0x140015032  call    memset_0
0x140015037  call    cs:__imp__errno
0x14001503d  mov     dword ptr [rax], 22h ; '"'
0x140015043  call    cs:__imp__invalid_parameter_noinfo
0x140015049  mov     rax, [r15]
0x14001504c  cmp     ebx, [rax-0Ch]
0x14001504f  jg      short loc_1400150B0
0x140015051  mov     [rax-10h], ebx
0x140015054  mov     rax, [r15]
0x140015057  mov     [rdi+rax], r14w
0x14001505c  jmp     short loc_140015066
0x14001505e  mov     rcx, r15
0x140015061  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ
0x140015066  call    cs:__imp_GetProcessHeap
0x14001506c  mov     r8, rsi; lpMem
0x14001506f  xor     edx, edx; dwFlags
0x140015071  mov     rcx, rax; hHeap
0x140015074  call    cs:__imp_HeapFree
0x14001507a  mov     rcx, [rbp+StringSid]; hMem
0x14001507e  call    cs:__imp_LocalFree
0x140015084  mov     al, 1
0x140015086  mov     rcx, [rbp+var_8]
0x14001508a  xor     rcx, rsp; StackCookie
0x14001508d  call    __security_check_cookie
0x140015092  lea     r11, [rsp+50h+var_s0]
0x140015097  mov     rbx, [r11+38h]
0x14001509b  mov     rsi, [r11+40h]
0x14001509f  mov     rdi, [r11+48h]
0x1400150a3  mov     rsp, r11
0x1400150a6  pop     r15
0x1400150a8  pop     r14
0x1400150aa  pop     r13
0x1400150ac  pop     r12
0x1400150ae  pop     rbp
0x1400150af  retn
0x1400150b0  mov     ecx, 80070057h; int
0x1400150b5  call    ?AtlThrowImpl@ATL@@YAXJ@Z
```
