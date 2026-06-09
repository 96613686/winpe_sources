# DxgkHandleMiracastEscape

- ea: `0x14035d7c4`
- end: `0x14035dfb0`
- name: `DxgkHandleMiracastEscape`
- size: `2028`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x14035a530`

## callees

- `0x140022434`
- `0x1400401b0`
- `0x140040908`
- `0x14004094c`
- `0x140061b18`
- `0x14008243c`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x1402b97f8`
- `0x1402b9960`
- `0x1402b9df4`
- `0x14035d7c4`
- `0x140365a4c`
- `0x140366938`
- `0x140367554`
- `0x140367720`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14035da2a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14035da2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035df5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035df5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035dedb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035def6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035dedb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035def6`
- `ntoskrnl!ExAllocatePool2` at `0x14035d8f4`
- `ntoskrnl!ExAllocatePool2` at `0x14035d94a`
- `ntoskrnl!ExAllocatePool2` at `0x14035d8f4`
- `ntoskrnl!ExAllocatePool2` at `0x14035d94a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14035d8a5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14035d8a5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14035da51`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14035da51`
- `ntoskrnl!ExReleaseResourceLite` at `0x14035df53`
- `ntoskrnl!ExReleaseResourceLite` at `0x14035df53`
- `ntoskrnl!DbgPrintEx` at `0x14035dbf0`
- `ntoskrnl!DbgPrintEx` at `0x14035dbf0`
- `ntoskrnl!ExEventObjectType` at `0x14035dcdb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14035dcea`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14035dcea`
- `ntoskrnl!ProbeForRead` at `0x14035d99a`
- `ntoskrnl!ProbeForRead` at `0x14035d99a`
- `ntoskrnl!ProbeForWrite` at `0x14035d9c9`
- `ntoskrnl!ProbeForWrite` at `0x14035d9c9`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14035db00`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14035db00`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14035df11`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14035df11`
- `watchdog!WdIsDebuggerPresent` at `0x14035dbd8`
- `watchdog!WdIsDebuggerPresent` at `0x14035dbd8`
- `watchdog!WdLogSingleEntry2` at `0x14035dd5f`
- `watchdog!WdLogSingleEntry2` at `0x14035dd9e`
- `watchdog!WdLogSingleEntry2` at `0x14035dd5f`
- `watchdog!WdLogSingleEntry2` at `0x14035dd9e`
- `watchdog!WdLogSingleEntry1` at `0x14035d80c`
- `watchdog!WdLogSingleEntry1` at `0x14035d855`
- `watchdog!WdLogSingleEntry1` at `0x14035d8c5`
- `watchdog!WdLogSingleEntry1` at `0x14035d919`
- `watchdog!WdLogSingleEntry1` at `0x14035d96c`
- `watchdog!WdLogSingleEntry1` at `0x14035da06`
- `watchdog!WdLogSingleEntry1` at `0x14035da95`
- `watchdog!WdLogSingleEntry1` at `0x14035dad5`
- `watchdog!WdLogSingleEntry1` at `0x14035db60`
- `watchdog!WdLogSingleEntry1` at `0x14035dbb0`
- `watchdog!WdLogSingleEntry1` at `0x14035dc9d`
- `watchdog!WdLogSingleEntry1` at `0x14035dd04`
- `watchdog!WdLogSingleEntry1` at `0x14035de0e`
- `watchdog!WdLogSingleEntry1` at `0x14035de60`
- `watchdog!WdLogSingleEntry1` at `0x14035dea0`
- `watchdog!WdLogSingleEntry1` at `0x14035d80c`
- `watchdog!WdLogSingleEntry1` at `0x14035d855`
- `watchdog!WdLogSingleEntry1` at `0x14035d8c5`
- `watchdog!WdLogSingleEntry1` at `0x14035d919`
- `watchdog!WdLogSingleEntry1` at `0x14035d96c`
- `watchdog!WdLogSingleEntry1` at `0x14035da06`
- `watchdog!WdLogSingleEntry1` at `0x14035da95`
- `watchdog!WdLogSingleEntry1` at `0x14035dad5`
- `watchdog!WdLogSingleEntry1` at `0x14035db60`
- `watchdog!WdLogSingleEntry1` at `0x14035dbb0`
- `watchdog!WdLogSingleEntry1` at `0x14035dc9d`
- `watchdog!WdLogSingleEntry1` at `0x14035dd04`
- `watchdog!WdLogSingleEntry1` at `0x14035de0e`
- `watchdog!WdLogSingleEntry1` at `0x14035de60`
- `watchdog!WdLogSingleEntry1` at `0x14035dea0`

## pseudocode

```c
__int64 __fastcall DxgkHandleMiracastEscape(unsigned int a1, __int64 a2)
{
  int v3; // ebx
  __int64 DeviceContextFromLuid; // rax
  __int64 v5; // r14
  __int64 v7; // r13
  _DWORD *Pool2; // r15
  char v9; // r12
  __int64 v10; // rbx
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  void *v22; // rcx
  NTSTATUS v23; // eax
  char v24; // [rsp+40h] [rbp-B8h]
  char v25; // [rsp+42h] [rbp-B6h]
  char v26; // [rsp+43h] [rbp-B5h]
  PVOID Object; // [rsp+48h] [rbp-B0h] BYREF
  void *Src; // [rsp+50h] [rbp-A8h]
  __int64 v29; // [rsp+58h] [rbp-A0h]
  _DWORD *v30; // [rsp+60h] [rbp-98h]
  _DWORD *v31; // [rsp+68h] [rbp-90h]
  __int64 v32; // [rsp+70h] [rbp-88h]
  __int64 v33; // [rsp+78h] [rbp-80h]
  _OWORD v34[4]; // [rsp+80h] [rbp-78h] BYREF

  v33 = a2;
  if ( a1 >= 0x38 )
  {
    v31 = (_DWORD *)(a2 + 48);
    *(_DWORD *)(a2 + 48) = 0;
    DeviceContextFromLuid = DpiMiracastGetDeviceContextFromLuid(*(_QWORD *)a2, 0);
    v5 = DeviceContextFromLuid;
    v32 = DeviceContextFromLuid;
    if ( !DeviceContextFromLuid )
    {
      WdLogSingleEntry1(2, -1073741811);
      WdLogGlobalForLineNumber = 4212;
      return 3221225485LL;
    }
    v7 = 0;
    v29 = 0;
    Pool2 = 0;
    v30 = 0;
    Src = 0;
    v9 = 0;
    v24 = 0;
    v26 = 0;
    v25 = 0;
    v10 = *(_QWORD *)(DeviceContextFromLuid + 104);
    if ( PsGetCurrentProcess() == v10 )
    {
      v12 = *(_DWORD *)(a2 + 16);
      if ( !v12 || (Pool2 = (_DWORD *)ExAllocatePool2(257, v12, 1953656900), (v30 = Pool2) != 0) )
      {
        v3 = 0;
        v13 = *(_DWORD *)(a2 + 32);
        if ( !v13 || (Src = (void *)ExAllocatePool2(257, v13, 1953656900)) != 0 )
        {
          v14 = *(_DWORD *)(a2 + 16);
          if ( v14 )
          {
            ProbeForRead(*(volatile void **)(a2 + 24), v14, 1u);
            memmove(Pool2, *(const void **)(a2 + 24), *(unsigned int *)(a2 + 16));
          }
          v15 = *(_DWORD *)(a2 + 32);
          if ( v15 )
            ProbeForWrite(*(volatile void **)(a2 + 40), v15, 1u);
          if ( (*(_DWORD *)(a2 + 8) & 6) != 0 )
          {
            AcquireMiniportListMutex();
            v9 = 1;
            v16 = *(_QWORD *)(v5 + 432);
            if ( !v16 )
            {
              v3 = -1073741275;
              WdLogSingleEntry1(2, -1073741275);
              WdLogGlobalForLineNumber = 4332;
              goto LABEL_58;
            }
            v29 = *(_QWORD *)(v16 + 64);
            v7 = v29;
            KeEnterCriticalRegion();
            if ( *(_BYTE *)(v29 + 484) )
              DpiCheckForOutstandingD3Requests(v29);
            ExAcquireResourceSharedLite(*(PERESOURCE *)(v29 + 168), 1u);
            v24 = 1;
            v18 = *(_DWORD *)(v29 + 236);
            if ( v18 != 2 && (*(_DWORD *)(v29 + 240) != 2 || ((v18 - 3) & 0xFFFFFFFC) != 0 || v18 == 4) )
            {
              v3 = -1073741130;
              WdLogSingleEntry1(2, -1073741130);
              WdLogGlobalForLineNumber = 4366;
              goto LABEL_58;
            }
            if ( (*(_DWORD *)(a2 + 8) & 4) != 0 )
            {
              LOBYTE(v17) = *(_BYTE *)(a2 + 12);
              v19 = DpiAcquireCoreSyncAccessSafe(*(_QWORD *)(v5 + 432), v17);
              v3 = v19;
              if ( v19 < 0 )
              {
                WdLogSingleEntry1(2, v19);
                WdLogGlobalForLineNumber = 4390;
                goto LABEL_58;
              }
              v26 = 1;
            }
          }
          if ( (*(_DWORD *)(a2 + 8) & 1) != 0 )
          {
            ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v5 + 32);
            *(_QWORD *)(v5 + 88) = KeGetCurrentThread();
            v25 = 1;
          }
          v20 = *(_DWORD *)(a2 + 8);
          switch ( v20 )
          {
            case 4:
              v3 = DpiMiracastDdiMiracastIoControl(
                     v7,
                     *(_QWORD *)(v5 + 448),
                     *(_DWORD *)(a2 + 16),
                     (_DWORD)Pool2,
                     *(_DWORD *)(a2 + 32),
                     (__int64)Src,
                     (__int64)v31);
              break;
            case 8:
              if ( *(_DWORD *)(a2 + 16) >= 0x350u )
              {
                DpiMiracastHandleStartSessionDone((PVOID)v5);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry2(2, 8, -1073741811);
                WdLogGlobalForLineNumber = 4442;
              }
              break;
            case 16:
              if ( *(_DWORD *)(a2 + 16) >= 0x350u )
              {
                DpiMiracastHandleStopSessionDone((PVOID)v5);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry2(2, 16, -1073741811);
                WdLogGlobalForLineNumber = 4468;
              }
              break;
            case 24:
              if ( *(_DWORD *)(a2 + 16) >= 0x18u )
              {
                v22 = (void *)*((_QWORD *)Pool2 + 1);
                if ( v22 )
                {
                  Object = 0;
                  v23 = ObReferenceObjectByHandle(v22, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
                  v3 = v23;
                  if ( v23 < 0 )
                  {
                    WdLogSingleEntry1(2, v23);
                    WdLogGlobalForLineNumber = 4530;
                  }
                }
                DpiMiracastStopMiracastSessionSync((PVOID)v5, Pool2[4], *Pool2);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry1(2, -1073741811);
                WdLogGlobalForLineNumber = 4497;
              }
              break;
            case 32:
              memset(v34, 0, sizeof(v34));
              *(_BYTE *)(v5 + 591) = 1;
              if ( *(_DWORD *)(a2 + 16) >= 0x404u )
              {
                *((_BYTE *)Pool2 + 1023) = 0;
                LODWORD(Object) = 0;
                LOBYTE(v21) = 1;
                if ( (unsigned __int8)WdIsDebuggerPresent(v21) )
                {
                  DbgPrintEx(0x65u, 0, (PCSTR)Pool2);
                  __debugbreak();
                  LODWORD(Object) = 1;
                }
                v34[0] = 0x4000000006uLL;
                memset(&v34[1], 0, 28);
                LODWORD(v34[3]) = 74;
                DWORD1(v34[3]) = Pool2[256];
                *((_QWORD *)&v34[3] + 1) = (unsigned int)Object;
                DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v34, 0x200000000uLL);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry1(2, -1073741811);
                WdLogGlobalForLineNumber = 4578;
              }
              break;
            default:
              v3 = -1073741637;
              WdLogSingleEntry1(2, -1073741637);
              WdLogGlobalForLineNumber = 4629;
              break;
          }
          v24 = v9;
          goto LABEL_58;
        }
        v3 = -1073741801;
        WdLogSingleEntry1(6, -1073741801);
        WdLogGlobalForLineNumber = 4270;
      }
      else
      {
        v3 = -1073741801;
        WdLogSingleEntry1(6, -1073741801);
        WdLogGlobalForLineNumber = 4252;
      }
    }
    else
    {
      v3 = -1073741790;
      WdLogSingleEntry1(2, -1073741790);
      WdLogGlobalForLineNumber = 4231;
    }
LABEL_58:
    if ( v3 >= 0 )
    {
      if ( *(_DWORD *)(a2 + 32) >= *v31 )
      {
        if ( *v31 )
          memmove(*(void **)(a2 + 40), Src, (unsigned int)*v31);
      }
      else
      {
        v3 = -1073741811;
        WdLogSingleEntry1(2, -1073741811);
        WdLogGlobalForLineNumber = 4652;
      }
    }
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    if ( Src )
      ExFreePoolWithTag(Src, 0);
    if ( v25 )
    {
      *(_QWORD *)(v5 + 88) = 0;
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion();
    }
    if ( v26 )
    {
      LOBYTE(v11) = *(_BYTE *)(a2 + 12);
      DpiReleaseCoreSyncAccessSafe(*(_QWORD *)(v5 + 432), v11);
    }
    if ( v24 )
    {
      if ( *(_BYTE *)(v7 + 484) )
        DpiEnableD3Requests(*(_QWORD *)(v7 + 24));
      ExReleaseResourceLite(*(PERESOURCE *)(v7 + 168));
      KeLeaveCriticalRegion();
    }
    if ( v9 )
      ReleaseMiniportListMutex();
    DpiMiracastReleaseMiracastDeviceContext((PVOID)v5);
    return (unsigned int)v3;
  }
  v3 = -1073741789;
  WdLogSingleEntry1(2, -1073741789);
  WdLogGlobalForLineNumber = 4183;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14035d7c4  mov     [rsp+arg_0], rbx
0x14035d7c9  mov     [rsp+arg_10], rsi
0x14035d7ce  push    rdi
0x14035d7cf  push    r12
0x14035d7d1  push    r13
0x14035d7d3  push    r14
0x14035d7d5  push    r15
0x14035d7d7  sub     rsp, 0D0h
0x14035d7de  mov     rax, cs:__security_cookie
0x14035d7e5  xor     rax, rsp
0x14035d7e8  mov     [rsp+0F8h+var_38], rax
0x14035d7f0  mov     rsi, rdx
0x14035d7f3  mov     [rsp+0F8h+var_80], rdx
0x14035d7f8  cmp     ecx, 38h ; '8'
0x14035d7fb  jnb     short loc_14035D827
0x14035d7fd  mov     rbx, 0FFFFFFFFC0000023h
0x14035d804  mov     rdx, rbx
0x14035d807  mov     ecx, 2
0x14035d80c  call    cs:__imp_WdLogSingleEntry1
0x14035d813  nop     dword ptr [rax+rax+00h]
0x14035d818  mov     cs:WdLogGlobalForLineNumber, 1057h
0x14035d822  jmp     loc_14035DF80
0x14035d827  lea     rax, [rdx+30h]
0x14035d82b  mov     [rsp+0F8h+var_90], rax
0x14035d830  xor     edi, edi
0x14035d832  mov     [rax], edi
0x14035d834  xor     edx, edx
0x14035d836  mov     rcx, [rsi]
0x14035d839  call    DpiMiracastGetDeviceContextFromLuid
0x14035d83e  mov     r14, rax
0x14035d841  mov     [rsp+0F8h+var_88], rax
0x14035d846  test    rax, rax
0x14035d849  jnz     short loc_14035D875
0x14035d84b  mov     rdx, 0FFFFFFFFC000000Dh
0x14035d852  lea     ecx, [rdi+2]
0x14035d855  call    cs:__imp_WdLogSingleEntry1
0x14035d85c  nop     dword ptr [rax+rax+00h]
0x14035d861  mov     cs:WdLogGlobalForLineNumber, 1074h
0x14035d86b  mov     eax, 0C000000Dh
0x14035d870  jmp     loc_14035DF82
0x14035d875  mov     r13, rdi
0x14035d878  mov     [rsp+0F8h+var_A0], rdi
0x14035d87d  mov     r15, rdi
0x14035d880  mov     [rsp+0F8h+var_98], rdi
0x14035d885  mov     [rsp+0F8h+Src], rdi
0x14035d88a  mov     r12b, dil
0x14035d88d  mov     [rsp+0F8h+var_B7], dil
0x14035d892  mov     [rsp+0F8h+var_B8], dil
0x14035d897  mov     [rsp+0F8h+var_B5], dil
0x14035d89c  mov     [rsp+0F8h+var_B6], dil
0x14035d8a1  mov     rbx, [rax+68h]
0x14035d8a5  call    cs:__imp_PsGetCurrentProcess
0x14035d8ac  nop     dword ptr [rax+rax+00h]
0x14035d8b1  cmp     rax, rbx
0x14035d8b4  jz      short loc_14035D8E0
0x14035d8b6  mov     rbx, 0FFFFFFFFC0000022h
0x14035d8bd  mov     rdx, rbx
0x14035d8c0  mov     ecx, 2
0x14035d8c5  call    cs:__imp_WdLogSingleEntry1
0x14035d8cc  nop     dword ptr [rax+rax+00h]
0x14035d8d1  mov     cs:WdLogGlobalForLineNumber, 1087h
0x14035d8db  jmp     loc_14035DE3B
0x14035d8e0  mov     eax, [rsi+10h]
0x14035d8e3  test    eax, eax
0x14035d8e5  jz      short loc_14035D934
0x14035d8e7  mov     edx, eax
0x14035d8e9  mov     ecx, 101h
0x14035d8ee  mov     r8d, 74727044h
0x14035d8f4  call    cs:__imp_ExAllocatePool2
0x14035d8fb  nop     dword ptr [rax+rax+00h]
0x14035d900  mov     r15, rax
0x14035d903  mov     [rsp+0F8h+var_98], rax
0x14035d908  test    rax, rax
0x14035d90b  jnz     short loc_14035D934
0x14035d90d  mov     rdx, 0FFFFFFFFC0000017h
0x14035d914  mov     ebx, edx
0x14035d916  lea     ecx, [rax+6]
0x14035d919  call    cs:__imp_WdLogSingleEntry1
0x14035d920  nop     dword ptr [rax+rax+00h]
0x14035d925  mov     cs:WdLogGlobalForLineNumber, 109Ch
0x14035d92f  jmp     loc_14035DE3B
0x14035d934  mov     ebx, edi
0x14035d936  mov     eax, [rsi+20h]
0x14035d939  test    eax, eax
0x14035d93b  jz      short loc_14035D987
0x14035d93d  mov     edx, eax
0x14035d93f  mov     ecx, 101h
0x14035d944  mov     r8d, 74727044h
0x14035d94a  call    cs:__imp_ExAllocatePool2
0x14035d951  nop     dword ptr [rax+rax+00h]
0x14035d956  mov     [rsp+0F8h+Src], rax
0x14035d95b  test    rax, rax
0x14035d95e  jnz     short loc_14035D987
0x14035d960  mov     rdx, 0FFFFFFFFC0000017h
0x14035d967  mov     ebx, edx
0x14035d969  lea     ecx, [rax+6]
0x14035d96c  call    cs:__imp_WdLogSingleEntry1
0x14035d973  nop     dword ptr [rax+rax+00h]
0x14035d978  mov     cs:WdLogGlobalForLineNumber, 10AEh
0x14035d982  jmp     loc_14035DE3B
0x14035d987  mov     eax, [rsi+10h]
0x14035d98a  test    eax, eax
0x14035d98c  jz      short loc_14035D9B6
0x14035d98e  mov     edx, eax; Length
0x14035d990  mov     r8d, 1; Alignment
0x14035d996  mov     rcx, [rsi+18h]; Address
0x14035d99a  call    cs:__imp_ProbeForRead
0x14035d9a1  nop     dword ptr [rax+rax+00h]
0x14035d9a6  mov     r8d, [rsi+10h]; Size
0x14035d9aa  mov     rdx, [rsi+18h]; Src
0x14035d9ae  mov     rcx, r15; void *
0x14035d9b1  call    memmove
0x14035d9b6  mov     eax, [rsi+20h]
0x14035d9b9  test    eax, eax
0x14035d9bb  jz      short loc_14035D9D6
0x14035d9bd  mov     edx, eax; Length
0x14035d9bf  mov     r8d, 1; Alignment
0x14035d9c5  mov     rcx, [rsi+28h]; Address
0x14035d9c9  call    cs:__imp_ProbeForWrite
0x14035d9d0  nop     dword ptr [rax+rax+00h]
0x14035d9d5  nop
0x14035d9d6  mov     eax, [rsi+8]
0x14035d9d9  test    al, 6
0x14035d9db  jz      loc_14035DAF5
0x14035d9e1  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x14035d9e6  mov     r12b, 1
0x14035d9e9  mov     [rsp+0F8h+var_B7], r12b
0x14035d9ee  mov     rax, [r14+1B0h]
0x14035d9f5  test    rax, rax
0x14035d9f8  jnz     short loc_14035DA21
0x14035d9fa  mov     rdx, 0FFFFFFFFC0000225h
0x14035da01  mov     ebx, edx
0x14035da03  lea     ecx, [rax+2]
0x14035da06  call    cs:__imp_WdLogSingleEntry1
0x14035da0d  nop     dword ptr [rax+rax+00h]
0x14035da12  mov     cs:WdLogGlobalForLineNumber, 10ECh
0x14035da1c  jmp     loc_14035DE3B
0x14035da21  mov     r13, [rax+40h]
0x14035da25  mov     [rsp+0F8h+var_A0], r13
0x14035da2a  call    cs:__imp_KeEnterCriticalRegion
0x14035da31  nop     dword ptr [rax+rax+00h]
0x14035da36  cmp     [r13+1E4h], dil
0x14035da3d  jz      short loc_14035DA47
0x14035da3f  mov     rcx, r13
0x14035da42  call    DpiCheckForOutstandingD3Requests
0x14035da47  mov     dl, r12b; Wait
0x14035da4a  mov     rcx, [r13+0A8h]; Resource
0x14035da51  call    cs:__imp_ExAcquireResourceSharedLite
0x14035da58  nop     dword ptr [rax+rax+00h]
0x14035da5d  mov     [rsp+0F8h+var_B8], r12b
0x14035da62  mov     ecx, [r13+0ECh]
0x14035da69  cmp     ecx, 2
0x14035da6c  jz      short loc_14035DAB0
0x14035da6e  cmp     dword ptr [r13+0F0h], 2
0x14035da76  jnz     short loc_14035DA87
0x14035da78  lea     eax, [rcx-3]
0x14035da7b  test    eax, 0FFFFFFFCh
0x14035da80  jnz     short loc_14035DA87
0x14035da82  cmp     ecx, 4
0x14035da85  jnz     short loc_14035DAB0
0x14035da87  mov     rdx, 0FFFFFFFFC00002B6h
0x14035da8e  mov     ebx, edx
0x14035da90  mov     ecx, 2
0x14035da95  call    cs:__imp_WdLogSingleEntry1
0x14035da9c  nop     dword ptr [rax+rax+00h]
0x14035daa1  mov     cs:WdLogGlobalForLineNumber, 110Eh
0x14035daab  jmp     loc_14035DE3B
0x14035dab0  mov     eax, [rsi+8]
0x14035dab3  test    al, 4
0x14035dab5  jz      short loc_14035DAF5
0x14035dab7  mov     dl, [rsi+0Ch]
0x14035daba  mov     rcx, [r14+1B0h]
0x14035dac1  call    DpiAcquireCoreSyncAccessSafe
0x14035dac6  movsxd  rbx, eax
0x14035dac9  test    eax, eax
0x14035dacb  jns     short loc_14035DAF0
0x14035dacd  mov     rdx, rbx
0x14035dad0  mov     ecx, 2
0x14035dad5  call    cs:__imp_WdLogSingleEntry1
0x14035dadc  nop     dword ptr [rax+rax+00h]
0x14035dae1  mov     cs:WdLogGlobalForLineNumber, 1126h
0x14035daeb  jmp     loc_14035DE3B
0x14035daf0  mov     [rsp+0F8h+var_B5], r12b
0x14035daf5  mov     eax, [rsi+8]
0x14035daf8  test    al, 1
0x14035dafa  jz      short loc_14035DB1E
0x14035dafc  lea     rcx, [r14+20h]
0x14035db00  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14035db07  nop     dword ptr [rax+rax+00h]
0x14035db0c  mov     rax, gs:188h
0x14035db15  mov     [r14+58h], rax
0x14035db19  mov     [rsp+0F8h+var_B6], 1
0x14035db1e  mov     eax, [rsi+8]
0x14035db21  cmp     eax, 4
0x14035db24  jz      loc_14035DDC3
0x14035db2a  mov     edx, 8
0x14035db2f  cmp     eax, edx
0x14035db31  jz      loc_14035DD84
0x14035db37  mov     edx, 10h
0x14035db3c  cmp     eax, edx
0x14035db3e  jz      loc_14035DD45
0x14035db44  cmp     eax, 18h
0x14035db47  jz      loc_14035DC86
0x14035db4d  cmp     eax, 20h ; ' '
0x14035db50  jz      short loc_14035DB7B
0x14035db52  mov     rdx, 0FFFFFFFFC00000BBh
0x14035db59  mov     ebx, edx
0x14035db5b  mov     ecx, 2
0x14035db60  call    cs:__imp_WdLogSingleEntry1
0x14035db67  nop     dword ptr [rax+rax+00h]
0x14035db6c  mov     cs:WdLogGlobalForLineNumber, 1215h
0x14035db76  jmp     loc_14035DDF6
0x14035db7b  xor     edx, edx; Val
0x14035db7d  lea     r8d, [rdx+40h]; Size
0x14035db81  lea     rcx, [rsp+0F8h+var_78]; void *
0x14035db89  call    memset
0x14035db8e  mov     byte ptr [r14+24Fh], 1
0x14035db96  cmp     dword ptr [rsi+10h], 404h
0x14035db9d  jnb     short loc_14035DBCB
0x14035db9f  mov     ebx, 0C000000Dh
0x14035dba4  mov     rdx, 0FFFFFFFFC000000Dh
0x14035dbab  mov     ecx, 2
0x14035dbb0  call    cs:__imp_WdLogSingleEntry1
0x14035dbb7  nop     dword ptr [rax+rax+00h]
0x14035dbbc  mov     cs:WdLogGlobalForLineNumber, 11E2h
0x14035dbc6  jmp     loc_14035DDF6
0x14035dbcb  mov     [r15+3FFh], dil
0x14035dbd2  mov     dword ptr [rsp+0F8h+var_B0], edi
0x14035dbd6  mov     cl, 1
0x14035dbd8  call    cs:__imp_WdIsDebuggerPresent
0x14035dbdf  nop     dword ptr [rax+rax+00h]
0x14035dbe4  test    al, al
0x14035dbe6  jz      short loc_14035DC05
0x14035dbe8  mov     r8, r15; Format
0x14035dbeb  xor     edx, edx; Level
0x14035dbed  lea     ecx, [rdx+65h]; ComponentId
0x14035dbf0  call    cs:__imp_DbgPrintEx
0x14035dbf7  nop     dword ptr [rax+rax+00h]
0x14035dbfc  int     3; Trap to Debugger
0x14035dbfd  mov     dword ptr [rsp+0F8h+var_B0], 1
0x14035dc05  mov     [rsp+0F8h+var_78], 6
0x14035dc10  mov     [rsp+0F8h+var_74], 40h ; '@'
0x14035dc1b  mov     [rsp+0F8h+var_50], edi
0x14035dc22  mov     [rsp+0F8h+var_58], rdi
0x14035dc2a  xor     eax, eax
0x14035dc2c  mov     [rsp+0F8h+var_70], rax
0x14035dc34  xorps   xmm0, xmm0
0x14035dc37  movups  [rsp+0F8h+var_68], xmm0
0x14035dc3f  mov     [rsp+0F8h+var_48], 4Ah ; 'J'
0x14035dc4a  mov     eax, [r15+400h]
0x14035dc51  mov     [rsp+0F8h+var_44], eax
0x14035dc58  mov     eax, dword ptr [rsp+0F8h+var_B0]
0x14035dc5c  mov     [rsp+0F8h+var_40], eax
0x14035dc63  mov     [rsp+0F8h+var_3C], edi
0x14035dc6a  mov     rdx, 200000000h; unsigned __int64
0x14035dc74  lea     rcx, [rsp+0F8h+var_78]; struct _DXGK_DIAG_HEADER *
0x14035dc7c  call    ?DxgkWriteDiagEntry@@YAJPEAU_DXGK_DIAG_HEADER@@_K@Z; DxgkWriteDiagEntry(_DXGK_DIAG_HEADER *,unsigned __int64)
0x14035dc81  jmp     loc_14035DDF6
0x14035dc86  cmp     dword ptr [rsi+10h], 18h
0x14035dc8a  jnb     short loc_14035DCB8
0x14035dc8c  mov     ebx, 0C000000Dh
0x14035dc91  mov     rdx, 0FFFFFFFFC000000Dh
0x14035dc98  mov     ecx, 2
0x14035dc9d  call    cs:__imp_WdLogSingleEntry1
0x14035dca4  nop     dword ptr [rax+rax+00h]
0x14035dca9  mov     cs:WdLogGlobalForLineNumber, 1191h
0x14035dcb3  jmp     loc_14035DDF6
0x14035dcb8  mov     r9, rdi
0x14035dcbb  mov     rcx, [r15+8]; Handle
0x14035dcbf  test    rcx, rcx
0x14035dcc2  jz      short loc_14035DD24
0x14035dcc4  mov     [rsp+0F8h+var_B0], rdi
0x14035dcc9  mov     [rsp+0F8h+HandleInformation], rdi; HandleInformation
0x14035dcce  lea     rax, [rsp+0F8h+var_B0]
0x14035dcd3  mov     [rsp+0F8h+Object], rax; Object
0x14035dcd8  mov     r9b, 1; AccessMode
0x14035dcdb  mov     r8, cs:ExEventObjectType
0x14035dce2  mov     r8, [r8]; ObjectType
0x14035dce5  mov     edx, 1F0003h; DesiredAccess
0x14035dcea  call    cs:__imp_ObReferenceObjectByHandle
0x14035dcf1  nop     dword ptr [rax+rax+00h]
0x14035dcf6  mov     ebx, eax
0x14035dcf8  test    eax, eax
0x14035dcfa  jns     short loc_14035DD1F
0x14035dcfc  movsxd  rdx, eax
0x14035dcff  mov     ecx, 2
0x14035dd04  call    cs:__imp_WdLogSingleEntry1
0x14035dd0b  nop     dword ptr [rax+rax+00h]
0x14035dd10  mov     cs:WdLogGlobalForLineNumber, 11B2h
0x14035dd1a  mov     r9, rdi
0x14035dd1d  jmp     short loc_14035DD24
0x14035dd1f  mov     r9, [rsp+0F8h+var_B0]
0x14035dd24  mov     eax, [r15]
0x14035dd27  mov     dword ptr [rsp+0F8h+HandleInformation], eax; int
0x14035dd2b  mov     eax, [r15+10h]
0x14035dd2f  mov     dword ptr [rsp+0F8h+Object], eax; int
0x14035dd33  xor     r8d, r8d
0x14035dd36  xor     edx, edx
0x14035dd38  mov     rcx, r14; P
0x14035dd3b  call    DpiMiracastStopMiracastSessionSync
  ... truncated ...
```
