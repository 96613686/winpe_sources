# SetEnvvar(void * *,ushort const *,ushort const *,int)

- ea: `0x180007470`
- end: `0x1800075d1`
- name: `?SetEnvvar@@YAJPEAPEAXPEBG1H@Z`
- size: `353`
- prototype: `int __fastcall(void **, const unsigned __int16 *, WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006de0`

## callees

- `0x180007470`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074f2`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180007578`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180007578`
- `ntdll!RtlSetEnvironmentVar` at `0x18000752b`
- `ntdll!RtlSetEnvironmentVar` at `0x1800075b9`
- `ntdll!RtlSetEnvironmentVar` at `0x18000752b`
- `ntdll!RtlSetEnvironmentVar` at `0x1800075b9`
- `ntdll!RtlNtStatusToDosError` at `0x180007533`
- `ntdll!RtlNtStatusToDosError` at `0x1800075c1`
- `ntdll!RtlNtStatusToDosError` at `0x180007533`
- `ntdll!RtlNtStatusToDosError` at `0x1800075c1`

## pseudocode

```c
int __fastcall SetEnvvar(void **a1, const unsigned __int16 *a2, WCHAR *a3)
{
  WCHAR *v3; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  NTSTATUS v8; // eax
  int result; // eax
  __int64 v10; // rbx
  NTSTATUS v11; // eax
  WCHAR szShortPath[264]; // [rsp+30h] [rbp-238h] BYREF

  v3 = a3;
  if ( !a3 || !*a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = RtlSetEnvironmentVar(a1, a2, v10, 0, 0);
    result = RtlNtStatusToDosError(v11);
    if ( result <= 0 )
      return result;
    return (unsigned __int16)result | 0x80070000;
  }
  v6 = -1;
  if ( (CompareStringOrdinal(a2, -1, L"TEMP", -1, 1) == 2 || CompareStringOrdinal(a2, -1, L"TMP", -1, 1) == 2)
    && GetShortPathNameW(v3, szShortPath, 0x104u) - 1 <= 0x102 )
  {
    v3 = szShortPath;
  }
  v7 = -1;
  do
    ++v7;
  while ( v3[v7] );
  do
    ++v6;
  while ( a2[v6] );
  v8 = RtlSetEnvironmentVar(a1, a2, v6, v3, v7);
  result = RtlNtStatusToDosError(v8);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007470  mov     [rsp+arg_18], rbx
0x180007475  push    rbp
0x180007476  push    rsi
0x180007477  push    rdi
0x180007478  sub     rsp, 250h
0x18000747f  mov     rax, cs:__security_cookie
0x180007486  xor     rax, rsp
0x180007489  mov     [rsp+268h+var_28], rax
0x180007491  mov     rdi, r8
0x180007494  mov     rsi, rdx
0x180007497  mov     rbp, rcx
0x18000749a  test    r8, r8
0x18000749d  jz      loc_180007595
0x1800074a3  cmp     word ptr [r8], 0
0x1800074a8  jz      loc_180007595
0x1800074ae  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800074b5  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x1800074bd  mov     r9d, ebx; cchCount2
0x1800074c0  lea     r8, String2; "TEMP"
0x1800074c7  mov     edx, ebx; cchCount1
0x1800074c9  mov     rcx, rsi; lpString1
0x1800074cc  call    cs:__imp_CompareStringOrdinal
0x1800074d2  cmp     eax, 2
0x1800074d5  jz      loc_18000756A
0x1800074db  mov     r9d, ebx; cchCount2
0x1800074de  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x1800074e6  lea     r8, aTmp; "TMP"
0x1800074ed  mov     edx, ebx; cchCount1
0x1800074ef  mov     rcx, rsi; lpString1
0x1800074f2  call    cs:__imp_CompareStringOrdinal
0x1800074f8  cmp     eax, 2
0x1800074fb  jz      short loc_18000756A
0x1800074fd  mov     rax, rbx
0x180007500  inc     rax
0x180007503  cmp     word ptr [rdi+rax*2], 0
0x180007508  jnz     short loc_180007500
0x18000750a  nop     word ptr [rax+rax+00h]
0x180007510  inc     rbx
0x180007513  cmp     word ptr [rsi+rbx*2], 0
0x180007518  jnz     short loc_180007510
0x18000751a  mov     r9, rdi
0x18000751d  mov     qword ptr [rsp+268h+bIgnoreCase], rax
0x180007522  mov     r8, rbx
0x180007525  mov     rdx, rsi
0x180007528  mov     rcx, rbp
0x18000752b  call    cs:__imp_RtlSetEnvironmentVar
0x180007531  mov     ecx, eax; Status
0x180007533  call    cs:__imp_RtlNtStatusToDosError
0x180007539  test    eax, eax
0x18000753b  jg      short loc_180007560
0x18000753d  mov     rcx, [rsp+268h+var_28]
0x180007545  xor     rcx, rsp; StackCookie
0x180007548  call    __security_check_cookie
0x18000754d  mov     rbx, [rsp+268h+arg_18]
0x180007555  add     rsp, 250h
0x18000755c  pop     rdi
0x18000755d  pop     rsi
0x18000755e  pop     rbp
0x18000755f  retn
0x180007560  movzx   eax, ax
0x180007563  or      eax, 80070000h
0x180007568  jmp     short loc_18000753D
0x18000756a  mov     r8d, 104h; cchBuffer
0x180007570  lea     rdx, [rsp+268h+szShortPath]; lpszShortPath
0x180007575  mov     rcx, rdi; lpszLongPath
0x180007578  call    cs:__imp_GetShortPathNameW
0x18000757e  dec     eax
0x180007580  cmp     eax, 102h
0x180007585  ja      loc_1800074FD
0x18000758b  lea     rdi, [rsp+268h+szShortPath]
0x180007590  jmp     loc_1800074FD
0x180007595  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000759c  nop     dword ptr [rax+00h]
0x1800075a0  inc     rbx
0x1800075a3  cmp     word ptr [rdx+rbx*2], 0
0x1800075a8  jnz     short loc_1800075A0
0x1800075aa  xor     r9d, r9d
0x1800075ad  mov     qword ptr [rsp+268h+bIgnoreCase], 0
0x1800075b6  mov     r8, rbx
0x1800075b9  call    cs:__imp_RtlSetEnvironmentVar
0x1800075bf  mov     ecx, eax; Status
0x1800075c1  call    cs:__imp_RtlNtStatusToDosError
0x1800075c7  test    eax, eax
0x1800075c9  jle     loc_18000753D
0x1800075cf  jmp     short loc_180007560
```
