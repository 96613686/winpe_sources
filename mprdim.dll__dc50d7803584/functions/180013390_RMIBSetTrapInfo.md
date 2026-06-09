# RMIBSetTrapInfo

- ea: `0x180013390`
- end: `0x18001357a`
- name: `RMIBSetTrapInfo`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180013390`
- `0x180019950`
- `0x18002f09c`
- `0x180036430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013454`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013454`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001347f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001347f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001348c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001355e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001348c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001355e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180013431`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180013431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001343f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001343f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800134e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800134e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013554`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013554`
- `RPCRT4!RpcRevertToSelf` at `0x180013447`
- `RPCRT4!RpcRevertToSelf` at `0x18001349a`
- `RPCRT4!RpcRevertToSelf` at `0x180013447`
- `RPCRT4!RpcRevertToSelf` at `0x18001349a`
- `RPCRT4!RpcImpersonateClient` at `0x180013418`
- `RPCRT4!RpcImpersonateClient` at `0x180013418`

## pseudocode

```c
RPC_STATUS __fastcall RMIBSetTrapInfo(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        void *a4,
        DWORD dwProcessId,
        __int64 a6)
{
  RPC_STATUS result; // eax
  HANDLE v10; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  CDimRouterManager *v13; // rcx
  unsigned int v14; // edi
  HLOCAL v15; // rax
  CDimRouterManager *v16; // rcx
  void *v17; // rdi
  unsigned int v18; // esi
  SIZE_T uBytes; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-20h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-18h] BYREF

  AccessStatus = 0;
  uBytes = 0;
  TargetHandle = 0;
  result = IsMultiTenancyEnabled((int *)&uBytes + 1);
  if ( !result )
  {
    if ( HIDWORD(uBytes) )
      return 50;
    if ( DimSecObjAccessCheck(1u, &AccessStatus) || AccessStatus )
    {
      return 5;
    }
    else
    {
      if ( !a6 )
        return 87;
      result = RpcImpersonateClient(0);
      if ( !result )
      {
        v10 = OpenProcess(0xFFFFFu, 0, dwProcessId);
        if ( !v10 )
        {
LABEL_10:
          LastError = GetLastError();
          RpcRevertToSelf();
          return LastError;
        }
        CurrentProcess = GetCurrentProcess();
        if ( !DuplicateHandle(v10, a4, CurrentProcess, &TargetHandle, 0, 0, 2u) )
        {
          CloseHandle(v10);
          goto LABEL_10;
        }
        CloseHandle(v10);
        result = RpcRevertToSelf();
        if ( !result )
        {
          v14 = CDimRouterManager::MIBSetTrapInfo(
                  v13,
                  a2,
                  a3,
                  TargetHandle,
                  *(_DWORD *)a6,
                  *(void **)(a6 + 8),
                  (unsigned int *)&uBytes,
                  0);
          if ( v14 != 122 )
          {
LABEL_17:
            CloseHandle(TargetHandle);
            return v14;
          }
          v15 = LocalAlloc(0x40u, (unsigned int)uBytes);
          v17 = v15;
          if ( !v15 )
          {
            v14 = 8;
            goto LABEL_17;
          }
          v18 = CDimRouterManager::MIBSetTrapInfo(
                  v16,
                  a2,
                  a3,
                  TargetHandle,
                  *(_DWORD *)a6,
                  *(void **)(a6 + 8),
                  (unsigned int *)&uBytes,
                  v15);
          if ( v18 )
          {
            *(_DWORD *)(a6 + 16) = 0;
            *(_QWORD *)(a6 + 24) = 0;
            LocalFree(v17);
            CloseHandle(TargetHandle);
          }
          else
          {
            *(_DWORD *)(a6 + 16) = uBytes;
            *(_QWORD *)(a6 + 24) = v17;
          }
          return v18;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013390  push    rbp
0x180013392  push    rbx
0x180013393  push    rsi
0x180013394  push    rdi
0x180013395  push    r14
0x180013397  push    r15
0x180013399  mov     rbp, rsp
0x18001339c  sub     rsp, 68h
0x1800133a0  lea     rcx, [rbp+uBytes+4]; int *
0x1800133a4  mov     [rbp+AccessStatus], 0
0x1800133ab  mov     r15, r9
0x1800133ae  mov     dword ptr [rbp+uBytes], 0
0x1800133b5  mov     esi, r8d
0x1800133b8  mov     [rbp+TargetHandle], 0
0x1800133c0  mov     r14d, edx
0x1800133c3  mov     dword ptr [rbp+uBytes+4], 0
0x1800133ca  call    IsMultiTenancyEnabled
0x1800133cf  test    eax, eax
0x1800133d1  jnz     loc_18001356D
0x1800133d7  cmp     dword ptr [rbp+uBytes+4], eax
0x1800133da  jz      short loc_1800133E6
0x1800133dc  mov     eax, 32h ; '2'
0x1800133e1  jmp     loc_18001356D
0x1800133e6  lea     rdx, [rbp+AccessStatus]; AccessStatus
0x1800133ea  mov     ecx, 1; DesiredAccess
0x1800133ef  call    ?DimSecObjAccessCheck@@YAKKPEAK@Z; DimSecObjAccessCheck(ulong,ulong *)
0x1800133f4  test    eax, eax
0x1800133f6  jnz     loc_180013568
0x1800133fc  cmp     [rbp+AccessStatus], eax
0x1800133ff  jnz     loc_180013568
0x180013405  mov     rbx, [rbp+arg_28]
0x180013409  test    rbx, rbx
0x18001340c  jnz     short loc_180013416
0x18001340e  lea     eax, [rbx+57h]
0x180013411  jmp     loc_18001356D
0x180013416  xor     ecx, ecx; BindingHandle
0x180013418  call    cs:__imp_RpcImpersonateClient
0x18001341e  test    eax, eax
0x180013420  jnz     loc_18001356D
0x180013426  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18001342a  xor     edx, edx; bInheritHandle
0x18001342c  mov     ecx, 0FFFFFh; dwDesiredAccess
0x180013431  call    cs:__imp_OpenProcess
0x180013437  mov     rdi, rax
0x18001343a  test    rax, rax
0x18001343d  jnz     short loc_180013454
0x18001343f  call    cs:__imp_GetLastError
0x180013445  mov     ebx, eax
0x180013447  call    cs:__imp_RpcRevertToSelf
0x18001344d  mov     eax, ebx
0x18001344f  jmp     loc_18001356D
0x180013454  call    cs:__imp_GetCurrentProcess
0x18001345a  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180013462  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x180013466  mov     r8, rax; hTargetProcessHandle
0x180013469  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180013471  mov     rdx, r15; hSourceHandle
0x180013474  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18001347c  mov     rcx, rdi; hSourceProcessHandle
0x18001347f  call    cs:__imp_DuplicateHandle
0x180013485  mov     rcx, rdi; hObject
0x180013488  test    eax, eax
0x18001348a  jnz     short loc_180013494
0x18001348c  call    cs:__imp_CloseHandle
0x180013492  jmp     short loc_18001343F
0x180013494  call    cs:__imp_CloseHandle
0x18001349a  call    cs:__imp_RpcRevertToSelf
0x1800134a0  test    eax, eax
0x1800134a2  jnz     loc_18001356D
0x1800134a8  mov     r9, [rbp+TargetHandle]; void *
0x1800134ac  lea     rax, [rbp+uBytes]
0x1800134b0  mov     [rsp+68h+var_30], 0; void *
0x1800134b9  mov     r8d, esi; unsigned int
0x1800134bc  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int *
0x1800134c1  mov     edx, r14d; unsigned int
0x1800134c4  mov     rax, [rbx+8]
0x1800134c8  mov     qword ptr [rsp+68h+bInheritHandle], rax; void *
0x1800134cd  mov     eax, [rbx]
0x1800134cf  mov     [rsp+68h+dwDesiredAccess], eax; unsigned int
0x1800134d3  call    ?MIBSetTrapInfo@CDimRouterManager@@QEAAKKKPEAXK0PEAK0@Z; CDimRouterManager::MIBSetTrapInfo(ulong,ulong,void *,ulong,void *,ulong *,void *)
0x1800134d8  mov     edi, eax
0x1800134da  cmp     eax, 7Ah ; 'z'
0x1800134dd  jnz     short loc_1800134F6
0x1800134df  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x1800134e2  lea     ecx, [rax-3Ah]; uFlags
0x1800134e5  call    cs:__imp_LocalAlloc
0x1800134eb  mov     rdi, rax
0x1800134ee  test    rax, rax
0x1800134f1  jnz     short loc_180013504
0x1800134f3  lea     edi, [rax+8]
0x1800134f6  mov     rcx, [rbp+TargetHandle]; hObject
0x1800134fa  call    cs:__imp_CloseHandle
0x180013500  mov     eax, edi
0x180013502  jmp     short loc_18001356D
0x180013504  mov     r9, [rbp+TargetHandle]; void *
0x180013508  lea     rax, [rbp+uBytes]
0x18001350c  mov     [rsp+68h+var_30], rdi; void *
0x180013511  mov     r8d, esi; unsigned int
0x180013514  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int *
0x180013519  mov     edx, r14d; unsigned int
0x18001351c  mov     rax, [rbx+8]
0x180013520  mov     qword ptr [rsp+68h+bInheritHandle], rax; void *
0x180013525  mov     eax, [rbx]
0x180013527  mov     [rsp+68h+dwDesiredAccess], eax; unsigned int
0x18001352b  call    ?MIBSetTrapInfo@CDimRouterManager@@QEAAKKKPEAXK0PEAK0@Z; CDimRouterManager::MIBSetTrapInfo(ulong,ulong,void *,ulong,void *,ulong *,void *)
0x180013530  mov     esi, eax
0x180013532  test    eax, eax
0x180013534  jnz     short loc_180013542
0x180013536  mov     ecx, dword ptr [rbp+uBytes]
0x180013539  mov     [rbx+10h], ecx
0x18001353c  mov     [rbx+18h], rdi
0x180013540  jmp     short loc_180013564
0x180013542  mov     rcx, rdi; hMem
0x180013545  mov     dword ptr [rbx+10h], 0
0x18001354c  mov     qword ptr [rbx+18h], 0
0x180013554  call    cs:__imp_LocalFree
0x18001355a  mov     rcx, [rbp+TargetHandle]; hObject
0x18001355e  call    cs:__imp_CloseHandle
0x180013564  mov     eax, esi
0x180013566  jmp     short loc_18001356D
0x180013568  mov     eax, 5
0x18001356d  add     rsp, 68h
0x180013571  pop     r15
0x180013573  pop     r14
0x180013575  pop     rdi
0x180013576  pop     rsi
0x180013577  pop     rbx
0x180013578  pop     rbp
0x180013579  retn
```
