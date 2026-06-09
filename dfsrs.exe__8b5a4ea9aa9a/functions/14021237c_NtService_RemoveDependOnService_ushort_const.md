# NtService::RemoveDependOnService(ushort const *)

- ea: `0x14021237c`
- end: `0x140212598`
- name: `?RemoveDependOnService@NtService@@QEAAPEAVFrsStatus@@PEBG@Z`
- size: `540`
- prototype: `struct FrsStatus *__fastcall(NtService *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1401f9e68`
- `0x1401fdf10`
- `0x1401fe65c`

## callees

- `0x14000bbd1`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401b9494`
- `0x14021237c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1402123b2`
- `KERNEL32!GetLastError` at `0x140212431`
- `KERNEL32!GetLastError` at `0x140212552`
- `KERNEL32!GetLastError` at `0x1402123b2`
- `KERNEL32!GetLastError` at `0x140212431`
- `KERNEL32!GetLastError` at `0x140212552`
- `KERNEL32!GetCurrentThreadId` at `0x1402123c5`
- `KERNEL32!GetCurrentThreadId` at `0x140212423`
- `KERNEL32!GetCurrentThreadId` at `0x140212544`
- `KERNEL32!GetCurrentThreadId` at `0x1402123c5`
- `KERNEL32!GetCurrentThreadId` at `0x140212423`
- `KERNEL32!GetCurrentThreadId` at `0x140212544`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14021249c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14021249c`
- `ADVAPI32!QueryServiceConfigW` at `0x1402123a6`
- `ADVAPI32!QueryServiceConfigW` at `0x140212413`
- `ADVAPI32!QueryServiceConfigW` at `0x1402123a6`
- `ADVAPI32!QueryServiceConfigW` at `0x140212413`
- `ADVAPI32!ChangeServiceConfigW` at `0x140212534`
- `ADVAPI32!ChangeServiceConfigW` at `0x140212534`

## string_xrefs

- `0x14021245c`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212450`: `NtService::RemoveDependOnService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall NtService::RemoveDependOnService(SC_HANDLE *this, const unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // rax
  struct _QUERY_SERVICE_CONFIGW *v5; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD v7; // eax
  __int64 v8; // rbx
  LPWSTR i; // rbx
  __int64 v10; // rax
  _WORD *j; // r8
  __int64 v12; // rax
  DWORD v13; // ebx
  int lpdwTagId; // [rsp+30h] [rbp-48h]
  DWORD lpDependenciesa; // [rsp+38h] [rbp-40h]
  DWORD lpDependencies; // [rsp+38h] [rbp-40h]
  struct _QUERY_SERVICE_CONFIGW *v18; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbBufSize; // [rsp+88h] [rbp+10h] BYREF
  int v20; // [rsp+8Ch] [rbp+14h]

  v20 = HIDWORD(a2);
  cbBufSize = 0;
  v18 = 0;
  QueryServiceConfigW(*this, 0, 0, &cbBufSize);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    lpDependenciesa = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           LastError,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           "NtService::RemoveDependOnService",
           471,
           lpDependenciesa,
           0);
LABEL_6:
    v8 = v4;
    goto LABEL_21;
  }
  v5 = (struct _QUERY_SERVICE_CONFIGW *)operator_new(cbBufSize);
  v18 = v5;
  if ( !QueryServiceConfigW(*this, v5, cbBufSize, &cbBufSize) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = GetLastError();
    lpDependencies = CurrentThreadId;
    lpdwTagId = 484;
LABEL_5:
    v4 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           v7,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           "NtService::RemoveDependOnService",
           lpdwTagId,
           lpDependencies,
           0);
    goto LABEL_6;
  }
  for ( i = v5->lpDependencies; i && *i; i += v10 + 1 )
  {
    if ( !(unsigned int)_o__wcsicmp(i, L"NTDS") )
    {
      for ( j = i + 5; *j; j += v12 + 1 )
      {
        v12 = -1;
        do
          ++v12;
        while ( j[v12] );
      }
      memmove_0(i, i + 5, 2 * (j - (i + 5)) + 2);
      if ( !ChangeServiceConfigW(*this, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 0, v5->lpDependencies, 0, 0, 0) )
      {
        v13 = GetCurrentThreadId();
        v7 = GetLastError();
        lpDependencies = v13;
        lpdwTagId = 543;
        goto LABEL_5;
      }
      break;
    }
    v10 = -1;
    do
      ++v10;
    while ( i[v10] );
  }
  v8 = 0;
LABEL_21:
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v18);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x14021237c  mov     rax, rsp
0x14021237f  mov     [rax+18h], rbx
0x140212383  mov     [rax+10h], rdx
0x140212387  push    rbp
0x140212388  push    rsi
0x140212389  push    rdi
0x14021238a  sub     rsp, 60h
0x14021238e  mov     rsi, rcx
0x140212391  xor     ebp, ebp
0x140212393  mov     [rax+10h], ebp
0x140212396  mov     [rax+8], rbp
0x14021239a  lea     r9, [rax+10h]; pcbBytesNeeded
0x14021239e  xor     r8d, r8d; cbBufSize
0x1402123a1  xor     edx, edx; lpServiceConfig
0x1402123a3  mov     rcx, [rcx]; hService
0x1402123a6  call    cs:__imp_QueryServiceConfigW
0x1402123ad  nop     dword ptr [rax+rax+00h]
0x1402123b2  call    cs:__imp_GetLastError
0x1402123b9  nop     dword ptr [rax+rax+00h]
0x1402123be  mov     ebx, eax
0x1402123c0  cmp     eax, 7Ah ; 'z'
0x1402123c3  jz      short loc_1402123E6
0x1402123c5  call    cs:__imp_GetCurrentThreadId
0x1402123cc  nop     dword ptr [rax+rax+00h]
0x1402123d1  mov     [rsp+78h+lpServiceStartName], rbp
0x1402123d6  mov     dword ptr [rsp+78h+lpDependencies], eax
0x1402123da  mov     dword ptr [rsp+78h+lpdwTagId], 1D7h
0x1402123e2  mov     edx, ebx
0x1402123e4  jmp     short loc_140212450
0x1402123e6  mov     ecx, [rsp+78h+cbBufSize]; unsigned __int64
0x1402123ed  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1402123f2  mov     rdi, rax
0x1402123f5  mov     [rsp+78h+arg_0], rax
0x1402123fd  lea     r9, [rsp+78h+cbBufSize]; pcbBytesNeeded
0x140212405  mov     r8d, [rsp+78h+cbBufSize]; cbBufSize
0x14021240d  mov     rdx, rax; lpServiceConfig
0x140212410  mov     rcx, [rsi]; hService
0x140212413  call    cs:__imp_QueryServiceConfigW
0x14021241a  nop     dword ptr [rax+rax+00h]
0x14021241f  test    eax, eax
0x140212421  jnz     short loc_14021247C
0x140212423  call    cs:__imp_GetCurrentThreadId
0x14021242a  nop     dword ptr [rax+rax+00h]
0x14021242f  mov     ebx, eax
0x140212431  call    cs:__imp_GetLastError
0x140212438  nop     dword ptr [rax+rax+00h]
0x14021243d  mov     [rsp+78h+lpServiceStartName], rbp
0x140212442  mov     dword ptr [rsp+78h+lpDependencies], ebx
0x140212446  mov     dword ptr [rsp+78h+lpdwTagId], 1E4h
0x14021244e  mov     edx, eax
0x140212450  lea     rcx, aNtserviceRemov; "NtService::RemoveDependOnService"
0x140212457  mov     [rsp+78h+lpLoadOrderGroup], rcx
0x14021245c  lea     rcx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212463  xor     r8d, r8d
0x140212466  lea     r9d, [r8+1]
0x14021246a  mov     [rsp+78h+lpBinaryPathName], rcx
0x14021246f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212474  mov     rbx, rax
0x140212477  jmp     loc_140212577
0x14021247c  mov     rbx, [rdi+28h]
0x140212480  test    rbx, rbx
0x140212483  jz      loc_140212574
0x140212489  cmp     [rbx], bp
0x14021248c  jz      loc_140212574
0x140212492  lea     rdx, aNtds; "NTDS"
0x140212499  mov     rcx, rbx
0x14021249c  call    cs:__imp__o__wcsicmp
0x1402124a3  nop     dword ptr [rax+rax+00h]
0x1402124a8  test    eax, eax
0x1402124aa  jz      short loc_1402124C3
0x1402124ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1402124b0  inc     rax
0x1402124b3  cmp     [rbx+rax*2], bp
0x1402124b7  jnz     short loc_1402124B0
0x1402124b9  lea     rbx, [rbx+rax*2]
0x1402124bd  add     rbx, 2
0x1402124c1  jmp     short loc_140212480
0x1402124c3  lea     rdx, [rbx+0Ah]; Src
0x1402124c7  mov     r8, rdx
0x1402124ca  cmp     [rdx], bp
0x1402124cd  jz      short loc_1402124EB
0x1402124cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1402124d3  inc     rax
0x1402124d6  cmp     [r8+rax*2], bp
0x1402124db  jnz     short loc_1402124D3
0x1402124dd  lea     r8, [r8+rax*2]
0x1402124e1  add     r8, 2
0x1402124e5  cmp     [r8], bp
0x1402124e9  jnz     short loc_1402124CF
0x1402124eb  sub     r8, rdx
0x1402124ee  sar     r8, 1
0x1402124f1  lea     r8, ds:2[r8*2]; Size
0x1402124f9  mov     rcx, rbx; void *
0x1402124fc  call    memmove_0
0x140212501  mov     rax, [rdi+28h]
0x140212505  mov     [rsp+78h+lpDisplayName], rbp; lpDisplayName
0x14021250a  mov     [rsp+78h+lpPassword], rbp; lpPassword
0x14021250f  mov     [rsp+78h+lpServiceStartName], rbp; lpServiceStartName
0x140212514  mov     [rsp+78h+lpDependencies], rax; lpDependencies
0x140212519  mov     [rsp+78h+lpdwTagId], rbp; lpdwTagId
0x14021251e  mov     [rsp+78h+lpLoadOrderGroup], rbp; lpLoadOrderGroup
0x140212523  mov     [rsp+78h+lpBinaryPathName], rbp; lpBinaryPathName
0x140212528  or      edx, 0FFFFFFFFh; dwServiceType
0x14021252b  mov     r9d, edx; dwErrorControl
0x14021252e  mov     r8d, edx; dwStartType
0x140212531  mov     rcx, [rsi]; hService
0x140212534  call    cs:__imp_ChangeServiceConfigW
0x14021253b  nop     dword ptr [rax+rax+00h]
0x140212540  test    eax, eax
0x140212542  jnz     short loc_140212574
0x140212544  call    cs:__imp_GetCurrentThreadId
0x14021254b  nop     dword ptr [rax+rax+00h]
0x140212550  mov     ebx, eax
0x140212552  call    cs:__imp_GetLastError
0x140212559  nop     dword ptr [rax+rax+00h]
0x14021255e  mov     [rsp+78h+lpServiceStartName], rbp
0x140212563  mov     dword ptr [rsp+78h+lpDependencies], ebx
0x140212567  mov     dword ptr [rsp+78h+lpdwTagId], 21Fh
0x14021256f  jmp     loc_14021244E
0x140212574  mov     rbx, rbp
0x140212577  lea     rcx, [rsp+78h+arg_0]
0x14021257f  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x140212584  mov     rax, rbx
0x140212587  mov     rbx, [rsp+78h+arg_10]
0x14021258f  add     rsp, 60h
0x140212593  pop     rdi
0x140212594  pop     rsi
0x140212595  pop     rbp
0x140212596  retn
```
