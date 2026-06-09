# NtService::AppendDependOnService(ushort const *)

- ea: `0x140211e54`
- end: `0x1402120b8`
- name: `?AppendDependOnService@NtService@@QEAAPEAVFrsStatus@@PEBG@Z`
- size: `612`
- prototype: `struct FrsStatus *__fastcall(NtService *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1401fdadc`

## callees

- `0x14000bbc5`
- `0x1400173c0`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401b9494`
- `0x140211e54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140211e90`
- `KERNEL32!GetLastError` at `0x140211eff`
- `KERNEL32!GetLastError` at `0x14021203d`
- `KERNEL32!GetLastError` at `0x140211e90`
- `KERNEL32!GetLastError` at `0x140211eff`
- `KERNEL32!GetLastError` at `0x14021203d`
- `KERNEL32!GetCurrentThreadId` at `0x140211ea3`
- `KERNEL32!GetCurrentThreadId` at `0x140211ef1`
- `KERNEL32!GetCurrentThreadId` at `0x14021202f`
- `KERNEL32!GetCurrentThreadId` at `0x140211ea3`
- `KERNEL32!GetCurrentThreadId` at `0x140211ef1`
- `KERNEL32!GetCurrentThreadId` at `0x14021202f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140211f67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140211f67`
- `ADVAPI32!QueryServiceConfigW` at `0x140211e84`
- `ADVAPI32!QueryServiceConfigW` at `0x140211ee1`
- `ADVAPI32!QueryServiceConfigW` at `0x140211e84`
- `ADVAPI32!QueryServiceConfigW` at `0x140211ee1`
- `ADVAPI32!ChangeServiceConfigW` at `0x14021201f`
- `ADVAPI32!ChangeServiceConfigW` at `0x14021201f`

## string_xrefs

- `0x140211f2a`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212066`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140211f1e`: `NtService::AppendDependOnService`
- `0x14021205a`: `NtService::AppendDependOnService`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall NtService::AppendDependOnService(SC_HANDLE *this, const unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // rax
  struct _QUERY_SERVICE_CONFIGW *v5; // rsi
  DWORD CurrentThreadId; // ebx
  __int64 v7; // rdx
  __int64 v8; // rbx
  LPWSTR i; // rdi
  __int64 v10; // rax
  __int64 v11; // rdi
  WCHAR *v12; // rax
  const WCHAR *v13; // r14
  size_t v14; // rbx
  unsigned __int16 *v15; // rbx
  DWORD v16; // ebx
  DWORD v17; // eax
  DWORD lpDependencies; // [rsp+38h] [rbp-28h]
  WCHAR *v20; // [rsp+A0h] [rbp+40h] BYREF
  DWORD pcbBytesNeeded; // [rsp+A8h] [rbp+48h] BYREF
  int v22; // [rsp+ACh] [rbp+4Ch]
  struct _QUERY_SERVICE_CONFIGW *v23; // [rsp+B0h] [rbp+50h] BYREF

  v22 = HIDWORD(a2);
  pcbBytesNeeded = 0;
  v23 = 0;
  QueryServiceConfigW(*this, 0, 0, &pcbBytesNeeded);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    lpDependencies = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           LastError,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           "NtService::AppendDependOnService",
           348,
           lpDependencies,
           0);
LABEL_5:
    v8 = v4;
    goto LABEL_19;
  }
  v5 = (struct _QUERY_SERVICE_CONFIGW *)operator_new(pcbBytesNeeded);
  v23 = v5;
  if ( !QueryServiceConfigW(*this, v5, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = GetLastError();
    v4 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           v7,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           "NtService::AppendDependOnService",
           361,
           CurrentThreadId,
           0);
    goto LABEL_5;
  }
  for ( i = v5->lpDependencies; i && *i; i += v10 + 1 )
  {
    if ( !(unsigned int)_o__wcsicmp(i, L"NTDS") )
      goto LABEL_18;
    v10 = -1;
    do
      ++v10;
    while ( i[v10] );
  }
  v11 = i - v5->lpDependencies;
  v20 = 0;
  v12 = (WCHAR *)operator_new(saturated_mul((unsigned int)v11 + 6LL, 2u));
  v13 = v12;
  v20 = v12;
  v14 = (unsigned int)v11;
  if ( (_DWORD)v11 )
    memcpy_0(v12, v5->lpDependencies, v14 * 2);
  v15 = (unsigned __int16 *)&v13[v14];
  StringCchCopyW(v15, 5u, L"NTDS");
  v15[5] = 0;
  if ( !ChangeServiceConfigW(*this, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 0, v13, 0, 0, 0) )
  {
    v16 = GetCurrentThreadId();
    v17 = GetLastError();
    v8 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           v17,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
           "NtService::AppendDependOnService",
           435,
           v16,
           0);
    scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v20);
    goto LABEL_19;
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v20);
LABEL_18:
  v8 = 0;
LABEL_19:
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v23);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x140211e54  mov     qword ptr [rsp-38h+pcbBytesNeeded], rdx
0x140211e59  push    rbp
0x140211e5a  push    rbx
0x140211e5b  push    rsi
0x140211e5c  push    rdi
0x140211e5d  push    r12
0x140211e5f  push    r14
0x140211e61  push    r15
0x140211e63  mov     rbp, rsp
0x140211e66  sub     rsp, 60h
0x140211e6a  mov     r15, rcx
0x140211e6d  xor     r12d, r12d
0x140211e70  mov     [rbp+pcbBytesNeeded], r12d
0x140211e74  mov     [rbp+arg_10], r12
0x140211e78  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x140211e7c  xor     r8d, r8d; cbBufSize
0x140211e7f  xor     edx, edx; lpServiceConfig
0x140211e81  mov     rcx, [rcx]; hService
0x140211e84  call    cs:__imp_QueryServiceConfigW
0x140211e8b  nop     dword ptr [rax+rax+00h]
0x140211e90  call    cs:__imp_GetLastError
0x140211e97  nop     dword ptr [rax+rax+00h]
0x140211e9c  mov     ebx, eax
0x140211e9e  cmp     eax, 7Ah ; 'z'
0x140211ea1  jz      short loc_140211EC4
0x140211ea3  call    cs:__imp_GetCurrentThreadId
0x140211eaa  nop     dword ptr [rax+rax+00h]
0x140211eaf  mov     [rsp+60h+lpServiceStartName], r12
0x140211eb4  mov     dword ptr [rsp+60h+lpDependencies], eax
0x140211eb8  mov     dword ptr [rsp+60h+lpdwTagId], 15Ch
0x140211ec0  mov     edx, ebx
0x140211ec2  jmp     short loc_140211F1E
0x140211ec4  mov     ecx, [rbp+pcbBytesNeeded]; unsigned __int64
0x140211ec7  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x140211ecc  mov     rsi, rax
0x140211ecf  mov     [rbp+arg_10], rax
0x140211ed3  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x140211ed7  mov     r8d, [rbp+pcbBytesNeeded]; cbBufSize
0x140211edb  mov     rdx, rax; lpServiceConfig
0x140211ede  mov     rcx, [r15]; hService
0x140211ee1  call    cs:__imp_QueryServiceConfigW
0x140211ee8  nop     dword ptr [rax+rax+00h]
0x140211eed  test    eax, eax
0x140211eef  jnz     short loc_140211F4A
0x140211ef1  call    cs:__imp_GetCurrentThreadId
0x140211ef8  nop     dword ptr [rax+rax+00h]
0x140211efd  mov     ebx, eax
0x140211eff  call    cs:__imp_GetLastError
0x140211f06  nop     dword ptr [rax+rax+00h]
0x140211f0b  mov     [rsp+60h+lpServiceStartName], r12
0x140211f10  mov     dword ptr [rsp+60h+lpDependencies], ebx
0x140211f14  mov     dword ptr [rsp+60h+lpdwTagId], 169h
0x140211f1c  mov     edx, eax
0x140211f1e  lea     rcx, aNtserviceAppen; "NtService::AppendDependOnService"
0x140211f25  mov     [rsp+60h+lpLoadOrderGroup], rcx
0x140211f2a  lea     rcx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140211f31  xor     r8d, r8d
0x140211f34  lea     r9d, [r8+1]
0x140211f38  mov     [rsp+60h+lpBinaryPathName], rcx
0x140211f3d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140211f42  mov     rbx, rax
0x140211f45  jmp     loc_14021209C
0x140211f4a  mov     rdi, [rsi+28h]
0x140211f4e  or      r14, 0FFFFFFFFFFFFFFFFh
0x140211f52  test    rdi, rdi
0x140211f55  jz      short loc_140211F92
0x140211f57  cmp     [rdi], r12w
0x140211f5b  jz      short loc_140211F92
0x140211f5d  lea     rdx, aNtds; "NTDS"
0x140211f64  mov     rcx, rdi
0x140211f67  call    cs:__imp__o__wcsicmp
0x140211f6e  nop     dword ptr [rax+rax+00h]
0x140211f73  test    eax, eax
0x140211f75  jz      loc_140212099
0x140211f7b  mov     rax, r14
0x140211f7e  inc     rax
0x140211f81  cmp     [rdi+rax*2], r12w
0x140211f86  jnz     short loc_140211F7E
0x140211f88  lea     rdi, [rdi+rax*2]
0x140211f8c  add     rdi, 2
0x140211f90  jmp     short loc_140211F52
0x140211f92  sub     rdi, [rsi+28h]
0x140211f96  sar     rdi, 1
0x140211f99  mov     [rbp+arg_0], r12
0x140211f9d  mov     ebx, edi
0x140211f9f  lea     rcx, [rbx+6]
0x140211fa3  mov     eax, 2
0x140211fa8  mul     rcx
0x140211fab  cmovo   rax, r14
0x140211faf  mov     rcx, rax; unsigned __int64
0x140211fb2  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x140211fb7  mov     r14, rax
0x140211fba  mov     [rbp+arg_0], rax
0x140211fbe  add     rbx, rbx
0x140211fc1  test    edi, edi
0x140211fc3  jz      short loc_140211FD4
0x140211fc5  mov     r8, rbx; Size
0x140211fc8  mov     rdx, [rsi+28h]; Src
0x140211fcc  mov     rcx, rax; void *
0x140211fcf  call    memcpy_0
0x140211fd4  add     rbx, r14
0x140211fd7  lea     r8, aNtds; "NTDS"
0x140211fde  mov     edx, 5; unsigned __int64
0x140211fe3  mov     rcx, rbx; unsigned __int16 *
0x140211fe6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140211feb  mov     [rbx+0Ah], r12w
0x140211ff0  mov     [rsp+60h+lpDisplayName], r12; lpDisplayName
0x140211ff5  mov     [rsp+60h+lpPassword], r12; lpPassword
0x140211ffa  mov     [rsp+60h+lpServiceStartName], r12; lpServiceStartName
0x140211fff  mov     [rsp+60h+lpDependencies], r14; lpDependencies
0x140212004  mov     [rsp+60h+lpdwTagId], r12; lpdwTagId
0x140212009  mov     [rsp+60h+lpLoadOrderGroup], r12; lpLoadOrderGroup
0x14021200e  mov     [rsp+60h+lpBinaryPathName], r12; lpBinaryPathName
0x140212013  or      edx, 0FFFFFFFFh; dwServiceType
0x140212016  mov     r9d, edx; dwErrorControl
0x140212019  mov     r8d, edx; dwStartType
0x14021201c  mov     rcx, [r15]; hService
0x14021201f  call    cs:__imp_ChangeServiceConfigW
0x140212026  nop     dword ptr [rax+rax+00h]
0x14021202b  test    eax, eax
0x14021202d  jnz     short loc_140212090
0x14021202f  call    cs:__imp_GetCurrentThreadId
0x140212036  nop     dword ptr [rax+rax+00h]
0x14021203b  mov     ebx, eax
0x14021203d  call    cs:__imp_GetLastError
0x140212044  nop     dword ptr [rax+rax+00h]
0x140212049  mov     [rsp+60h+lpServiceStartName], r12
0x14021204e  mov     dword ptr [rsp+60h+lpDependencies], ebx
0x140212052  mov     dword ptr [rsp+60h+lpdwTagId], 1B3h
0x14021205a  lea     rcx, aNtserviceAppen; "NtService::AppendDependOnService"
0x140212061  mov     [rsp+60h+lpLoadOrderGroup], rcx
0x140212066  lea     rcx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x14021206d  mov     [rsp+60h+lpBinaryPathName], rcx
0x140212072  mov     r9d, 1
0x140212078  xor     r8d, r8d
0x14021207b  mov     edx, eax
0x14021207d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212082  mov     rbx, rax
0x140212085  lea     rcx, [rbp+arg_0]
0x140212089  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x14021208e  jmp     short loc_14021209C
0x140212090  lea     rcx, [rbp+arg_0]
0x140212094  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x140212099  mov     rbx, r12
0x14021209c  lea     rcx, [rbp+arg_10]
0x1402120a0  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1402120a5  mov     rax, rbx
0x1402120a8  add     rsp, 60h
0x1402120ac  pop     r15
0x1402120ae  pop     r14
0x1402120b0  pop     r12
0x1402120b2  pop     rdi
0x1402120b3  pop     rsi
0x1402120b4  pop     rbx
0x1402120b5  pop     rbp
0x1402120b6  retn
```
