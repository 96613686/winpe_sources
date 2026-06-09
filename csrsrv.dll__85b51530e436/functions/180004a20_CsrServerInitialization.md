# CsrServerInitialization

- ea: `0x180004a20`
- end: `0x180004f50`
- name: `CsrServerInitialization`
- size: `1328`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001140`
- `0x1800035c0`
- `0x180004a20`
- `0x180004f60`
- `0x1800050c0`
- `0x180005180`
- `0x180008540`
- `0x180008780`
- `0x180008f00`
- `0x18000b010`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x180004a46`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180004a46`
- `ntdll!RtlWakeAddressAll` at `0x180004f37`
- `ntdll!RtlWakeAddressAll` at `0x180004f37`
- `ntdll!RtlAllocateHeap` at `0x180004c3e`
- `ntdll!RtlAllocateHeap` at `0x180004c3e`
- `ntdll!NtQuerySystemInformation` at `0x180004ac9`
- `ntdll!NtQuerySystemInformation` at `0x180004ac9`
- `ntdll!NtClose` at `0x180004ece`
- `ntdll!NtClose` at `0x180004ece`
- `ntdll!RtlCreateTagHeap` at `0x180004b22`
- `ntdll!RtlCreateTagHeap` at `0x180004b22`
- `ntdll!EtwEventRegister` at `0x180004a72`
- `ntdll!EtwEventRegister` at `0x180004a72`
- `ntdll!NtWaitForSingleObject` at `0x180004ebb`
- `ntdll!NtWaitForSingleObject` at `0x180004ebb`
- `ntdll!NtResumeThread` at `0x180004e74`
- `ntdll!NtResumeThread` at `0x180004e74`
- `ntdll!RtlInitializeCriticalSection` at `0x180004b7e`
- `ntdll!RtlInitializeCriticalSection` at `0x180004b7e`
- `ntdll!RtlConnectToSm` at `0x180004e35`
- `ntdll!RtlConnectToSm` at `0x180004e35`

## pseudocode

```c
__int64 __fastcall CsrServerInitialization(unsigned int a1, __int64 a2)
{
  NTSTATUS SystemInformation; // ebx
  unsigned __int64 Heap; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int i; // ebx
  __int64 v14; // rcx
  void (__fastcall *v15)(_QWORD); // rax
  NTSTATUS v16; // ebx
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  HANDLE v18; // [rsp+40h] [rbp-38h]
  HANDLE ThreadHandle; // [rsp+90h] [rbp+18h] BYREF

  ThreadHandle = 0;
  LODWORD(v18) = 0;
  v17 = 0;
  ServiceSessionId = RtlGetCurrentServiceSessionId();
  CsrApiPort = 0;
  if ( (unsigned int)EtwEventRegister(CsrEventProvider, 0, 0, &CsrTraceHandle) )
    CsrTraceHandle = 0;
  SystemInformation = CsrRemoveUnneededPrivileges();
  if ( SystemInformation >= 0 )
  {
    SystemInformation = NtQuerySystemInformation(SystemBasicInformation, &CsrNtSysInfo, 0x40u, 0);
    if ( SystemInformation >= 0 )
    {
      CsrHeap = *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL);
      CsrBaseTag = RtlCreateTagHeap(CsrHeap, 0, (PWSTR)L"CSRSS!", (PWSTR)L"TMP");
      SystemInformation = CsrSetProcessSecurity();
      if ( SystemInformation >= 0 )
      {
        qword_1800102B8 = (__int64)&CsrNtSessionList;
        CsrNtSessionList = (__int64)&CsrNtSessionList;
        SystemInformation = RtlInitializeCriticalSection(&CsrNtSessionLock);
        if ( SystemInformation >= 0 )
        {
          SystemInformation = CsrInitializeProcessStructure();
          if ( SystemInformation >= 0 )
          {
            SystemInformation = CsrParseServerCommandLine(a1, a2, &v17, &ThreadHandle);
            if ( SystemInformation >= 0 )
            {
              Heap = (unsigned __int64)RtlAllocateHeap(
                                         CsrHeap,
                                         (CsrBaseTag + 786432) | 8,
                                         (unsigned int)CsrTotalPerProcessDataLength);
              if ( !Heap )
              {
                CsrInitFailReason = 8;
                CsrpLogModuleFailureInt(
                  "CsrServerInitialization",
                  408,
                  (const char *)&qword_18000C660,
                  CsrTotalPerProcessDataLength);
                return 3221225495LL;
              }
              _mm_lfence();
              v7 = CsrLoadedServerDll[0];
              if ( CsrLoadedServerDll[0] && *(_DWORD *)(CsrLoadedServerDll[0] + 64) )
              {
                v8 = (_QWORD *)CsrRootProcess;
                *(_QWORD *)(CsrRootProcess + 136) = Heap;
                Heap = (*(unsigned int *)(v7 + 64) + 7LL + Heap) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else
              {
                v8 = (_QWORD *)CsrRootProcess;
                *(_QWORD *)(CsrRootProcess + 136) = 0;
              }
              v9 = qword_180010368;
              if ( qword_180010368 && *(_DWORD *)(qword_180010368 + 64) )
              {
                v8[18] = Heap;
                Heap = (*(unsigned int *)(v9 + 64) + 7LL + Heap) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else
              {
                v8[18] = 0;
              }
              v10 = qword_180010370;
              if ( qword_180010370 && *(_DWORD *)(qword_180010370 + 64) )
              {
                v8[19] = Heap;
                Heap = (*(unsigned int *)(v10 + 64) + 7LL + Heap) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else
              {
                v8[19] = 0;
              }
              v11 = qword_180010378;
              if ( qword_180010378 && *(_DWORD *)(qword_180010378 + 64) )
              {
                v8[20] = Heap;
                Heap = (*(unsigned int *)(v11 + 64) + 7LL + Heap) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else
              {
                v8[20] = 0;
              }
              v12 = qword_180010380;
              if ( qword_180010380 && *(_DWORD *)(qword_180010380 + 64) )
              {
                v8[21] = Heap;
                Heap = (*(unsigned int *)(v12 + 64) + 7LL + Heap) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else
              {
                v8[21] = 0;
              }
              if ( qword_180010388 && *(_DWORD *)(qword_180010388 + 64) )
                v8[22] = Heap;
              else
                v8[22] = 0;
              for ( i = 0; i < 6; ++i )
              {
                v14 = CsrLoadedServerDll[i];
                if ( v14 )
                {
                  v15 = *(void (__fastcall **)(_QWORD))(v14 + 104);
                  if ( v15 )
                    v15(0);
                }
              }
              SystemInformation = CsrSbApiPortInitialize();
              if ( SystemInformation >= 0 )
              {
                SystemInformation = RtlConnectToSm(
                                      &CsrSbApiPortName,
                                      CsrSbApiPort,
                                      (unsigned int)SessionFirstProcessImageType,
                                      &CsrSmApiPort);
                if ( SystemInformation >= 0 )
                {
                  v16 = NtResumeThread(ThreadHandle, 0);
                  if ( v16 < 0 )
                  {
                    CsrInitFailReason = 13;
                    CsrpLogFailure("CsrServerInitialization");
                    return (unsigned int)v16;
                  }
                  SystemInformation = NtWaitForSingleObject(v18, 0, 0);
                  NtClose(v18);
                  if ( SystemInformation >= 0 )
                  {
                    SystemInformation = v17;
                    if ( (int)v17 >= 0 )
                    {
                      CsrInitFailReason = 1;
                      RtlWakeAddressAll(&CsrInitFailReason);
                    }
                    else
                    {
                      CsrInitFailReason = 15;
                      CsrpLogFailure("CsrServerInitialization");
                    }
                  }
                  else
                  {
                    CsrInitFailReason = 14;
                    CsrpLogFailure("CsrServerInitialization");
                  }
                }
                else
                {
                  CsrInitFailReason = 12;
                  CsrpLogFailure("CsrServerInitialization");
                }
              }
              else
              {
                CsrInitFailReason = 11;
                CsrpLogFailure("CsrServerInitialization");
              }
            }
            else
            {
              CsrInitFailReason = 7;
              CsrpLogFailure("CsrServerInitialization");
            }
          }
          else
          {
            CsrInitFailReason = 6;
            CsrpLogFailure("CsrServerInitialization");
          }
        }
        else
        {
          CsrInitFailReason = 5;
          CsrpLogFailure("CsrServerInitialization");
        }
      }
      else
      {
        CsrInitFailReason = 4;
        CsrpLogFailure("CsrServerInitialization");
      }
    }
    else
    {
      CsrInitFailReason = 3;
      CsrpLogFailure("CsrServerInitialization");
    }
  }
  else
  {
    CsrInitFailReason = 2;
    CsrpLogFailure("CsrServerInitialization");
  }
  return (unsigned int)SystemInformation;
}

```

## disassembly

```asm
0x180004a20  push    rbx
0x180004a22  push    rsi
0x180004a23  push    rdi
0x180004a24  push    r14
0x180004a26  sub     rsp, 58h
0x180004a2a  mov     rdi, rdx
0x180004a2d  mov     esi, ecx
0x180004a2f  xor     r14d, r14d
0x180004a32  mov     [rsp+78h+ThreadHandle], r14
0x180004a3a  xor     eax, eax
0x180004a3c  mov     [rsp+78h+var_40+4], rax
0x180004a41  mov     [rsp+78h+var_40], rax
0x180004a46  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180004a4d  nop     dword ptr [rax+rax+00h]
0x180004a52  mov     cs:ServiceSessionId, eax
0x180004a58  mov     cs:CsrApiPort, r14
0x180004a5f  lea     r9, CsrTraceHandle
0x180004a66  xor     r8d, r8d
0x180004a69  xor     edx, edx
0x180004a6b  lea     rcx, CsrEventProvider
0x180004a72  call    cs:__imp_EtwEventRegister
0x180004a79  nop     dword ptr [rax+rax+00h]
0x180004a7e  test    eax, eax
0x180004a80  jz      short loc_180004A89
0x180004a82  mov     cs:CsrTraceHandle, r14
0x180004a89  call    CsrRemoveUnneededPrivileges
0x180004a8e  mov     ebx, eax
0x180004a90  test    eax, eax
0x180004a92  jns     short loc_180004AB7
0x180004a94  mov     cs:CsrInitFailReason, 2
0x180004a9e  mov     r8d, eax
0x180004aa1  mov     edx, 12Fh
0x180004aa6  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004aad  call    CsrpLogFailure
0x180004ab2  jmp     loc_180004F43
0x180004ab7  xor     r9d, r9d; ReturnLength
0x180004aba  mov     r8d, 40h ; '@'; SystemInformationLength
0x180004ac0  lea     rdx, CsrNtSysInfo; SystemInformation
0x180004ac7  xor     ecx, ecx; SystemInformationClass
0x180004ac9  call    cs:__imp_NtQuerySystemInformation
0x180004ad0  nop     dword ptr [rax+rax+00h]
0x180004ad5  mov     ebx, eax
0x180004ad7  test    eax, eax
0x180004ad9  jns     short loc_180004AFE
0x180004adb  mov     cs:CsrInitFailReason, 3
0x180004ae5  mov     r8d, eax
0x180004ae8  mov     edx, 140h
0x180004aed  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004af4  call    CsrpLogFailure
0x180004af9  jmp     loc_180004F43
0x180004afe  mov     rax, gs:60h
0x180004b07  mov     rcx, [rax+30h]; HeapHandle
0x180004b0b  mov     cs:CsrHeap, rcx
0x180004b12  lea     r9, TagSubName; "TMP"
0x180004b19  lea     r8, TagName; "CSRSS!"
0x180004b20  xor     edx, edx; Flags
0x180004b22  call    cs:__imp_RtlCreateTagHeap
0x180004b29  nop     dword ptr [rax+rax+00h]
0x180004b2e  mov     cs:CsrBaseTag, eax
0x180004b34  call    CsrSetProcessSecurity
0x180004b39  mov     ebx, eax
0x180004b3b  test    eax, eax
0x180004b3d  jns     short loc_180004B62
0x180004b3f  mov     cs:CsrInitFailReason, 4
0x180004b49  mov     r8d, eax
0x180004b4c  mov     edx, 15Fh
0x180004b51  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004b58  call    CsrpLogFailure
0x180004b5d  jmp     loc_180004F43
0x180004b62  lea     rax, CsrNtSessionList
0x180004b69  mov     cs:qword_1800102B8, rax
0x180004b70  mov     cs:CsrNtSessionList, rax
0x180004b77  lea     rcx, CsrNtSessionLock; CriticalSection
0x180004b7e  call    cs:__imp_RtlInitializeCriticalSection
0x180004b85  nop     dword ptr [rax+rax+00h]
0x180004b8a  mov     ebx, eax
0x180004b8c  test    eax, eax
0x180004b8e  jns     short loc_180004BB3
0x180004b90  mov     cs:CsrInitFailReason, 5
0x180004b9a  mov     r8d, eax
0x180004b9d  mov     edx, 16Dh
0x180004ba2  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004ba9  call    CsrpLogFailure
0x180004bae  jmp     loc_180004F43
0x180004bb3  call    CsrInitializeProcessStructure
0x180004bb8  mov     ebx, eax
0x180004bba  test    eax, eax
0x180004bbc  jns     short loc_180004BE1
0x180004bbe  mov     cs:CsrInitFailReason, 6
0x180004bc8  mov     r8d, eax
0x180004bcb  mov     edx, 17Bh
0x180004bd0  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004bd7  call    CsrpLogFailure
0x180004bdc  jmp     loc_180004F43
0x180004be1  lea     r9, [rsp+78h+ThreadHandle]
0x180004be9  lea     r8, [rsp+78h+var_40]
0x180004bee  mov     rdx, rdi
0x180004bf1  mov     ecx, esi
0x180004bf3  call    CsrParseServerCommandLine
0x180004bf8  mov     ebx, eax
0x180004bfa  test    eax, eax
0x180004bfc  jns     short loc_180004C21
0x180004bfe  mov     cs:CsrInitFailReason, 7
0x180004c08  mov     r8d, eax
0x180004c0b  mov     edx, 189h
0x180004c10  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004c17  call    CsrpLogFailure
0x180004c1c  jmp     loc_180004F43
0x180004c21  mov     r8d, cs:CsrTotalPerProcessDataLength; Size
0x180004c28  mov     edx, cs:CsrBaseTag
0x180004c2e  add     edx, 0C0000h
0x180004c34  or      edx, 8; Flags
0x180004c37  mov     rcx, cs:CsrHeap; HeapHandle
0x180004c3e  call    cs:__imp_RtlAllocateHeap
0x180004c45  nop     dword ptr [rax+rax+00h]
0x180004c4a  mov     rcx, rax
0x180004c4d  test    rax, rax
0x180004c50  jnz     short loc_180004C8D
0x180004c52  mov     cs:CsrInitFailReason, 8
0x180004c5c  mov     [rsp+78h+var_58], 0C0000017h; int
0x180004c64  mov     r9d, cs:CsrTotalPerProcessDataLength
0x180004c6b  lea     r8, qword_18000C660
0x180004c72  mov     edx, 198h
0x180004c77  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004c7e  call    CsrpLogModuleFailureInt
0x180004c83  mov     eax, 0C0000017h
0x180004c88  jmp     loc_180004F45
0x180004c8d  lfence
0x180004c90  mov     rax, cs:CsrLoadedServerDll
0x180004c97  test    rax, rax
0x180004c9a  jz      short loc_180004CC0
0x180004c9c  cmp     [rax+40h], r14d
0x180004ca0  jz      short loc_180004CC0
0x180004ca2  mov     rdx, cs:CsrRootProcess
0x180004ca9  mov     [rdx+88h], rcx
0x180004cb0  mov     eax, [rax+40h]
0x180004cb3  add     rax, 7
0x180004cb7  add     rcx, rax
0x180004cba  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004cbe  jmp     short loc_180004CCE
0x180004cc0  mov     rdx, cs:CsrRootProcess
0x180004cc7  mov     [rdx+88h], r14
0x180004cce  mov     rax, cs:qword_180010368
0x180004cd5  test    rax, rax
0x180004cd8  jz      short loc_180004CF7
0x180004cda  cmp     [rax+40h], r14d
0x180004cde  jz      short loc_180004CF7
0x180004ce0  mov     [rdx+90h], rcx
0x180004ce7  mov     eax, [rax+40h]
0x180004cea  add     rax, 7
0x180004cee  add     rcx, rax
0x180004cf1  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004cf5  jmp     short loc_180004CFE
0x180004cf7  mov     [rdx+90h], r14
0x180004cfe  mov     rax, cs:qword_180010370
0x180004d05  test    rax, rax
0x180004d08  jz      short loc_180004D27
0x180004d0a  cmp     [rax+40h], r14d
0x180004d0e  jz      short loc_180004D27
0x180004d10  mov     [rdx+98h], rcx
0x180004d17  mov     eax, [rax+40h]
0x180004d1a  add     rax, 7
0x180004d1e  add     rcx, rax
0x180004d21  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004d25  jmp     short loc_180004D2E
0x180004d27  mov     [rdx+98h], r14
0x180004d2e  mov     rax, cs:qword_180010378
0x180004d35  test    rax, rax
0x180004d38  jz      short loc_180004D57
0x180004d3a  cmp     [rax+40h], r14d
0x180004d3e  jz      short loc_180004D57
0x180004d40  mov     [rdx+0A0h], rcx
0x180004d47  mov     eax, [rax+40h]
0x180004d4a  add     rax, 7
0x180004d4e  add     rcx, rax
0x180004d51  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004d55  jmp     short loc_180004D5E
0x180004d57  mov     [rdx+0A0h], r14
0x180004d5e  mov     rax, cs:qword_180010380
0x180004d65  test    rax, rax
0x180004d68  jz      short loc_180004D87
0x180004d6a  cmp     [rax+40h], r14d
0x180004d6e  jz      short loc_180004D87
0x180004d70  mov     [rdx+0A8h], rcx
0x180004d77  mov     eax, [rax+40h]
0x180004d7a  add     rax, 7
0x180004d7e  add     rcx, rax
0x180004d81  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004d85  jmp     short loc_180004D8E
0x180004d87  mov     [rdx+0A8h], r14
0x180004d8e  mov     rax, cs:qword_180010388
0x180004d95  test    rax, rax
0x180004d98  jz      short loc_180004DA9
0x180004d9a  cmp     [rax+40h], r14d
0x180004d9e  jz      short loc_180004DA9
0x180004da0  mov     [rdx+0B0h], rcx
0x180004da7  jmp     short loc_180004DB0
0x180004da9  mov     [rdx+0B0h], r14
0x180004db0  mov     ebx, r14d
0x180004db3  lea     rdi, CsrLoadedServerDll
0x180004dba  mov     [rsp+78h+var_48], ebx
0x180004dbe  cmp     ebx, 6
0x180004dc1  jnb     short loc_180004DE9
0x180004dc3  mov     eax, ebx
0x180004dc5  mov     rcx, [rdi+rax*8]
0x180004dc9  test    rcx, rcx
0x180004dcc  jz      short loc_180004DE5
0x180004dce  mov     rax, [rcx+68h]
0x180004dd2  test    rax, rax
0x180004dd5  jz      short loc_180004DE5
0x180004dd7  xor     ecx, ecx
0x180004dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dde  mov     rdx, cs:CsrRootProcess
0x180004de5  inc     ebx
0x180004de7  jmp     short loc_180004DBA
0x180004de9  jmp     short $+2
0x180004deb  call    CsrSbApiPortInitialize
0x180004df0  mov     ebx, eax
0x180004df2  test    eax, eax
0x180004df4  jns     short loc_180004E19
0x180004df6  mov     cs:CsrInitFailReason, 0Bh
0x180004e00  mov     r8d, eax
0x180004e03  mov     edx, 1C7h
0x180004e08  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004e0f  call    CsrpLogFailure
0x180004e14  jmp     loc_180004F43
0x180004e19  lea     r9, CsrSmApiPort
0x180004e20  mov     r8d, cs:SessionFirstProcessImageType
0x180004e27  mov     rdx, cs:CsrSbApiPort
0x180004e2e  lea     rcx, CsrSbApiPortName
0x180004e35  call    cs:__imp_RtlConnectToSm
0x180004e3c  nop     dword ptr [rax+rax+00h]
0x180004e41  mov     ebx, eax
0x180004e43  test    eax, eax
0x180004e45  jns     short loc_180004E6A
0x180004e47  mov     cs:CsrInitFailReason, 0Ch
0x180004e51  mov     r8d, eax
0x180004e54  mov     edx, 1D9h
0x180004e59  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004e60  call    CsrpLogFailure
0x180004e65  jmp     loc_180004F43
0x180004e6a  xor     edx, edx; SuspendCount
0x180004e6c  mov     rcx, [rsp+78h+ThreadHandle]; ThreadHandle
0x180004e74  call    cs:__imp_NtResumeThread
0x180004e7b  nop     dword ptr [rax+rax+00h]
0x180004e80  mov     ebx, eax
0x180004e82  test    eax, eax
0x180004e84  jns     short loc_180004EB1
0x180004e86  mov     cs:CsrInitFailReason, 0Dh
0x180004e90  mov     r8d, eax
0x180004e93  mov     edx, 1E7h
0x180004e98  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004e9f  call    CsrpLogFailure
0x180004ea4  mov     eax, ebx
0x180004ea6  add     rsp, 58h
0x180004eaa  pop     r14
0x180004eac  pop     rdi
0x180004ead  pop     rsi
0x180004eae  pop     rbx
0x180004eaf  retn
0x180004eb1  xor     r8d, r8d; Timeout
0x180004eb4  xor     edx, edx; Alertable
0x180004eb6  mov     rcx, [rsp+78h+var_38]; Object
0x180004ebb  call    cs:__imp_NtWaitForSingleObject
0x180004ec2  nop     dword ptr [rax+rax+00h]
0x180004ec7  mov     ebx, eax
0x180004ec9  mov     rcx, [rsp+78h+var_38]; Handle
0x180004ece  call    cs:__imp_NtClose
0x180004ed5  nop     dword ptr [rax+rax+00h]
0x180004eda  test    ebx, ebx
0x180004edc  jns     short loc_180004EFE
0x180004ede  mov     cs:CsrInitFailReason, 0Eh
0x180004ee8  mov     r8d, ebx
0x180004eeb  mov     edx, 1F9h
0x180004ef0  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004ef7  call    CsrpLogFailure
0x180004efc  jmp     short loc_180004F43
0x180004efe  mov     ebx, dword ptr [rsp+78h+var_40]
0x180004f02  test    ebx, ebx
0x180004f04  jns     short loc_180004F26
0x180004f06  mov     cs:CsrInitFailReason, 0Fh
0x180004f10  mov     r8d, ebx
0x180004f13  mov     edx, 200h
0x180004f18  lea     rcx, aCsrserveriniti_0; "CsrServerInitialization"
0x180004f1f  call    CsrpLogFailure
0x180004f24  jmp     short loc_180004F43
0x180004f26  mov     cs:CsrInitFailReason, 1
0x180004f30  lea     rcx, CsrInitFailReason
0x180004f37  call    cs:__imp_RtlWakeAddressAll
0x180004f3e  nop     dword ptr [rax+rax+00h]
0x180004f43  mov     eax, ebx
0x180004f45  add     rsp, 58h
0x180004f49  pop     r14
0x180004f4b  pop     rdi
0x180004f4c  pop     rsi
0x180004f4d  pop     rbx
0x180004f4e  retn
0x18000ac70  push    rbp
0x18000ac72  sub     rsp, 30h
0x18000ac76  mov     rbp, rdx
  ... truncated ...
```
