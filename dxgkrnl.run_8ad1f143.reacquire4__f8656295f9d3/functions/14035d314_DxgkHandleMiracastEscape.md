# DxgkHandleMiracastEscape

- ea: `0x14035d314`
- end: `0x14035db00`
- name: `DxgkHandleMiracastEscape`
- size: `2028`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x14035a080`

## callees

- `0x140022264`
- `0x14003ff50`
- `0x1400406a8`
- `0x1400406ec`
- `0x140061768`
- `0x140081a6c`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x1402b2e48`
- `0x1402b2fb0`
- `0x1402b3444`
- `0x14035d314`
- `0x140365a0c`
- `0x1403668f8`
- `0x140367514`
- `0x1403676e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14035d57a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14035d57a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035daaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035daaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035da2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035da46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035da2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14035da46`
- `ntoskrnl!ExAllocatePool2` at `0x14035d444`
- `ntoskrnl!ExAllocatePool2` at `0x14035d49a`
- `ntoskrnl!ExAllocatePool2` at `0x14035d444`
- `ntoskrnl!ExAllocatePool2` at `0x14035d49a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14035d3f5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14035d3f5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14035d5a1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14035d5a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14035daa3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14035daa3`
- `ntoskrnl!DbgPrintEx` at `0x14035d740`
- `ntoskrnl!DbgPrintEx` at `0x14035d740`
- `ntoskrnl!ExEventObjectType` at `0x14035d82b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14035d83a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14035d83a`
- `ntoskrnl!ProbeForRead` at `0x14035d4ea`
- `ntoskrnl!ProbeForRead` at `0x14035d4ea`
- `ntoskrnl!ProbeForWrite` at `0x14035d519`
- `ntoskrnl!ProbeForWrite` at `0x14035d519`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14035d650`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14035d650`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14035da61`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14035da61`
- `watchdog!WdIsDebuggerPresent` at `0x14035d728`
- `watchdog!WdIsDebuggerPresent` at `0x14035d728`
- `watchdog!WdLogSingleEntry2` at `0x14035d8af`
- `watchdog!WdLogSingleEntry2` at `0x14035d8ee`
- `watchdog!WdLogSingleEntry2` at `0x14035d8af`
- `watchdog!WdLogSingleEntry2` at `0x14035d8ee`
- `watchdog!WdLogSingleEntry1` at `0x14035d35c`
- `watchdog!WdLogSingleEntry1` at `0x14035d3a5`
- `watchdog!WdLogSingleEntry1` at `0x14035d415`
- `watchdog!WdLogSingleEntry1` at `0x14035d469`
- `watchdog!WdLogSingleEntry1` at `0x14035d4bc`
- `watchdog!WdLogSingleEntry1` at `0x14035d556`
- `watchdog!WdLogSingleEntry1` at `0x14035d5e5`
- `watchdog!WdLogSingleEntry1` at `0x14035d625`
- `watchdog!WdLogSingleEntry1` at `0x14035d6b0`
- `watchdog!WdLogSingleEntry1` at `0x14035d700`
- `watchdog!WdLogSingleEntry1` at `0x14035d7ed`
- `watchdog!WdLogSingleEntry1` at `0x14035d854`
- `watchdog!WdLogSingleEntry1` at `0x14035d95e`
- `watchdog!WdLogSingleEntry1` at `0x14035d9b0`
- `watchdog!WdLogSingleEntry1` at `0x14035d9f0`
- `watchdog!WdLogSingleEntry1` at `0x14035d35c`
- `watchdog!WdLogSingleEntry1` at `0x14035d3a5`
- `watchdog!WdLogSingleEntry1` at `0x14035d415`
- `watchdog!WdLogSingleEntry1` at `0x14035d469`
- `watchdog!WdLogSingleEntry1` at `0x14035d4bc`
- `watchdog!WdLogSingleEntry1` at `0x14035d556`
- `watchdog!WdLogSingleEntry1` at `0x14035d5e5`
- `watchdog!WdLogSingleEntry1` at `0x14035d625`
- `watchdog!WdLogSingleEntry1` at `0x14035d6b0`
- `watchdog!WdLogSingleEntry1` at `0x14035d700`
- `watchdog!WdLogSingleEntry1` at `0x14035d7ed`
- `watchdog!WdLogSingleEntry1` at `0x14035d854`
- `watchdog!WdLogSingleEntry1` at `0x14035d95e`
- `watchdog!WdLogSingleEntry1` at `0x14035d9b0`
- `watchdog!WdLogSingleEntry1` at `0x14035d9f0`

## pseudocode

```c
__int64 __fastcall DxgkHandleMiracastEscape(unsigned int a1, __int64 a2)
{
  NTSTATUS v3; // ebx
  __int64 DeviceContextFromLuid; // rax
  __int64 v5; // rcx
  __int64 v6; // r14
  __int64 v8; // r13
  _DWORD *Pool2; // r15
  char v10; // r12
  __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // eax
  __int64 v21; // rcx
  void *v22; // rcx
  char v23; // [rsp+40h] [rbp-B8h]
  char v24; // [rsp+42h] [rbp-B6h]
  char v25; // [rsp+43h] [rbp-B5h]
  PVOID Object; // [rsp+48h] [rbp-B0h] BYREF
  void *Src; // [rsp+50h] [rbp-A8h]
  __int64 v28; // [rsp+58h] [rbp-A0h]
  _DWORD *v29; // [rsp+60h] [rbp-98h]
  _DWORD *v30; // [rsp+68h] [rbp-90h]
  __int64 v31; // [rsp+70h] [rbp-88h]
  __int64 v32; // [rsp+78h] [rbp-80h]
  _OWORD v33[4]; // [rsp+80h] [rbp-78h] BYREF

  v32 = a2;
  if ( a1 >= 0x38 )
  {
    v30 = (_DWORD *)(a2 + 48);
    *(_DWORD *)(a2 + 48) = 0;
    DeviceContextFromLuid = DpiMiracastGetDeviceContextFromLuid(*(_QWORD *)a2, 0);
    v6 = DeviceContextFromLuid;
    v31 = DeviceContextFromLuid;
    if ( !DeviceContextFromLuid )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 4212;
      return 3221225485LL;
    }
    v8 = 0;
    v28 = 0;
    Pool2 = 0;
    v29 = 0;
    Src = 0;
    v10 = 0;
    v23 = 0;
    v25 = 0;
    v24 = 0;
    v11 = *(_QWORD *)(DeviceContextFromLuid + 104);
    if ( PsGetCurrentProcess(v5) == v11 )
    {
      v13 = *(_DWORD *)(a2 + 16);
      if ( !v13 || (Pool2 = (_DWORD *)ExAllocatePool2(257, v13, 1953656900), (v29 = Pool2) != 0) )
      {
        v3 = 0;
        v14 = *(_DWORD *)(a2 + 32);
        if ( !v14 || (Src = (void *)ExAllocatePool2(257, v14, 1953656900)) != 0 )
        {
          v15 = *(_DWORD *)(a2 + 16);
          if ( v15 )
          {
            ProbeForRead(*(volatile void **)(a2 + 24), v15, 1u);
            memmove(Pool2, *(const void **)(a2 + 24), *(unsigned int *)(a2 + 16));
          }
          v16 = *(_DWORD *)(a2 + 32);
          if ( v16 )
            ProbeForWrite(*(volatile void **)(a2 + 40), v16, 1u);
          if ( (*(_DWORD *)(a2 + 8) & 6) != 0 )
          {
            AcquireMiniportListMutex();
            v10 = 1;
            v17 = *(_QWORD *)(v6 + 432);
            if ( !v17 )
            {
              v3 = -1073741275;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 4332;
              goto LABEL_58;
            }
            v28 = *(_QWORD *)(v17 + 64);
            v8 = v28;
            KeEnterCriticalRegion();
            if ( *(_BYTE *)(v28 + 484) )
              DpiCheckForOutstandingD3Requests(v28);
            ExAcquireResourceSharedLite(*(PERESOURCE *)(v28 + 168), 1u);
            v23 = 1;
            v19 = *(_DWORD *)(v28 + 236);
            if ( v19 != 2 && (*(_DWORD *)(v28 + 240) != 2 || ((v19 - 3) & 0xFFFFFFFC) != 0 || v19 == 4) )
            {
              v3 = -1073741130;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 4366;
              goto LABEL_58;
            }
            if ( (*(_DWORD *)(a2 + 8) & 4) != 0 )
            {
              LOBYTE(v18) = *(_BYTE *)(a2 + 12);
              v3 = DpiAcquireCoreSyncAccessSafe(*(_QWORD *)(v6 + 432), v18);
              if ( v3 < 0 )
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4390;
                goto LABEL_58;
              }
              v25 = 1;
            }
          }
          if ( (*(_DWORD *)(a2 + 8) & 1) != 0 )
          {
            ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v6 + 32);
            *(_QWORD *)(v6 + 88) = KeGetCurrentThread();
            v24 = 1;
          }
          v20 = *(_DWORD *)(a2 + 8);
          switch ( v20 )
          {
            case 4:
              v3 = DpiMiracastDdiMiracastIoControl(
                     v8,
                     *(_QWORD *)(v6 + 448),
                     *(_DWORD *)(a2 + 16),
                     (_DWORD)Pool2,
                     *(_DWORD *)(a2 + 32),
                     (__int64)Src,
                     (__int64)v30);
              break;
            case 8:
              if ( *(_DWORD *)(a2 + 16) >= 0x350u )
              {
                DpiMiracastHandleStartSessionDone((PVOID)v6);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry2(2, 8);
                WdLogGlobalForLineNumber = 4442;
              }
              break;
            case 16:
              if ( *(_DWORD *)(a2 + 16) >= 0x350u )
              {
                DpiMiracastHandleStopSessionDone((PVOID)v6);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry2(2, 16);
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
                  v3 = ObReferenceObjectByHandle(v22, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
                  if ( v3 < 0 )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 4530;
                  }
                }
                DpiMiracastStopMiracastSessionSync((PVOID)v6, Pool2[4], *Pool2);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4497;
              }
              break;
            case 32:
              memset(v33, 0, sizeof(v33));
              *(_BYTE *)(v6 + 591) = 1;
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
                v33[0] = 0x4000000006uLL;
                memset(&v33[1], 0, 28);
                LODWORD(v33[3]) = 74;
                DWORD1(v33[3]) = Pool2[256];
                *((_QWORD *)&v33[3] + 1) = (unsigned int)Object;
                DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v33, 0x200000000uLL);
              }
              else
              {
                v3 = -1073741811;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4578;
              }
              break;
            default:
              v3 = -1073741637;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 4629;
              break;
          }
          v23 = v10;
          goto LABEL_58;
        }
        v3 = -1073741801;
        WdLogSingleEntry1(6);
        WdLogGlobalForLineNumber = 4270;
      }
      else
      {
        v3 = -1073741801;
        WdLogSingleEntry1(6);
        WdLogGlobalForLineNumber = 4252;
      }
    }
    else
    {
      v3 = -1073741790;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 4231;
    }
LABEL_58:
    if ( v3 >= 0 )
    {
      if ( *(_DWORD *)(a2 + 32) >= *v30 )
      {
        if ( *v30 )
          memmove(*(void **)(a2 + 40), Src, (unsigned int)*v30);
      }
      else
      {
        v3 = -1073741811;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4652;
      }
    }
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    if ( Src )
      ExFreePoolWithTag(Src, 0);
    if ( v24 )
    {
      *(_QWORD *)(v6 + 88) = 0;
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v6 + 32);
    }
    if ( v25 )
    {
      LOBYTE(v12) = *(_BYTE *)(a2 + 12);
      DpiReleaseCoreSyncAccessSafe(*(_QWORD *)(v6 + 432), v12);
    }
    if ( v23 )
    {
      if ( *(_BYTE *)(v8 + 484) )
        DpiEnableD3Requests(*(_QWORD *)(v8 + 24));
      ExReleaseResourceLite(*(PERESOURCE *)(v8 + 168));
      KeLeaveCriticalRegion();
    }
    if ( v10 )
      ReleaseMiniportListMutex();
    DpiMiracastReleaseMiracastDeviceContext((PVOID)v6);
    return (unsigned int)v3;
  }
  v3 = -1073741789;
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 4183;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14035d314  mov     [rsp+arg_0], rbx
0x14035d319  mov     [rsp+arg_10], rsi
0x14035d31e  push    rdi
0x14035d31f  push    r12
0x14035d321  push    r13
0x14035d323  push    r14
0x14035d325  push    r15
0x14035d327  sub     rsp, 0D0h
0x14035d32e  mov     rax, cs:__security_cookie
0x14035d335  xor     rax, rsp
0x14035d338  mov     [rsp+0F8h+var_38], rax
0x14035d340  mov     rsi, rdx
0x14035d343  mov     [rsp+0F8h+var_80], rdx
0x14035d348  cmp     ecx, 38h ; '8'
0x14035d34b  jnb     short loc_14035D377
0x14035d34d  mov     rbx, 0FFFFFFFFC0000023h
0x14035d354  mov     rdx, rbx
0x14035d357  mov     ecx, 2
0x14035d35c  call    cs:__imp_WdLogSingleEntry1
0x14035d363  nop     dword ptr [rax+rax+00h]
0x14035d368  mov     cs:WdLogGlobalForLineNumber, 1057h
0x14035d372  jmp     loc_14035DAD0
0x14035d377  lea     rax, [rdx+30h]
0x14035d37b  mov     [rsp+0F8h+var_90], rax
0x14035d380  xor     edi, edi
0x14035d382  mov     [rax], edi
0x14035d384  xor     edx, edx
0x14035d386  mov     rcx, [rsi]
0x14035d389  call    DpiMiracastGetDeviceContextFromLuid
0x14035d38e  mov     r14, rax
0x14035d391  mov     [rsp+0F8h+var_88], rax
0x14035d396  test    rax, rax
0x14035d399  jnz     short loc_14035D3C5
0x14035d39b  mov     rdx, 0FFFFFFFFC000000Dh
0x14035d3a2  lea     ecx, [rdi+2]
0x14035d3a5  call    cs:__imp_WdLogSingleEntry1
0x14035d3ac  nop     dword ptr [rax+rax+00h]
0x14035d3b1  mov     cs:WdLogGlobalForLineNumber, 1074h
0x14035d3bb  mov     eax, 0C000000Dh
0x14035d3c0  jmp     loc_14035DAD2
0x14035d3c5  mov     r13, rdi
0x14035d3c8  mov     [rsp+0F8h+var_A0], rdi
0x14035d3cd  mov     r15, rdi
0x14035d3d0  mov     [rsp+0F8h+var_98], rdi
0x14035d3d5  mov     [rsp+0F8h+Src], rdi
0x14035d3da  mov     r12b, dil
0x14035d3dd  mov     [rsp+0F8h+var_B7], dil
0x14035d3e2  mov     [rsp+0F8h+var_B8], dil
0x14035d3e7  mov     [rsp+0F8h+var_B5], dil
0x14035d3ec  mov     [rsp+0F8h+var_B6], dil
0x14035d3f1  mov     rbx, [rax+68h]
0x14035d3f5  call    cs:__imp_PsGetCurrentProcess
0x14035d3fc  nop     dword ptr [rax+rax+00h]
0x14035d401  cmp     rax, rbx
0x14035d404  jz      short loc_14035D430
0x14035d406  mov     rbx, 0FFFFFFFFC0000022h
0x14035d40d  mov     rdx, rbx
0x14035d410  mov     ecx, 2
0x14035d415  call    cs:__imp_WdLogSingleEntry1
0x14035d41c  nop     dword ptr [rax+rax+00h]
0x14035d421  mov     cs:WdLogGlobalForLineNumber, 1087h
0x14035d42b  jmp     loc_14035D98B
0x14035d430  mov     eax, [rsi+10h]
0x14035d433  test    eax, eax
0x14035d435  jz      short loc_14035D484
0x14035d437  mov     edx, eax
0x14035d439  mov     ecx, 101h
0x14035d43e  mov     r8d, 74727044h
0x14035d444  call    cs:__imp_ExAllocatePool2
0x14035d44b  nop     dword ptr [rax+rax+00h]
0x14035d450  mov     r15, rax
0x14035d453  mov     [rsp+0F8h+var_98], rax
0x14035d458  test    rax, rax
0x14035d45b  jnz     short loc_14035D484
0x14035d45d  mov     rdx, 0FFFFFFFFC0000017h
0x14035d464  mov     ebx, edx
0x14035d466  lea     ecx, [rax+6]
0x14035d469  call    cs:__imp_WdLogSingleEntry1
0x14035d470  nop     dword ptr [rax+rax+00h]
0x14035d475  mov     cs:WdLogGlobalForLineNumber, 109Ch
0x14035d47f  jmp     loc_14035D98B
0x14035d484  mov     ebx, edi
0x14035d486  mov     eax, [rsi+20h]
0x14035d489  test    eax, eax
0x14035d48b  jz      short loc_14035D4D7
0x14035d48d  mov     edx, eax
0x14035d48f  mov     ecx, 101h
0x14035d494  mov     r8d, 74727044h
0x14035d49a  call    cs:__imp_ExAllocatePool2
0x14035d4a1  nop     dword ptr [rax+rax+00h]
0x14035d4a6  mov     [rsp+0F8h+Src], rax
0x14035d4ab  test    rax, rax
0x14035d4ae  jnz     short loc_14035D4D7
0x14035d4b0  mov     rdx, 0FFFFFFFFC0000017h
0x14035d4b7  mov     ebx, edx
0x14035d4b9  lea     ecx, [rax+6]
0x14035d4bc  call    cs:__imp_WdLogSingleEntry1
0x14035d4c3  nop     dword ptr [rax+rax+00h]
0x14035d4c8  mov     cs:WdLogGlobalForLineNumber, 10AEh
0x14035d4d2  jmp     loc_14035D98B
0x14035d4d7  mov     eax, [rsi+10h]
0x14035d4da  test    eax, eax
0x14035d4dc  jz      short loc_14035D506
0x14035d4de  mov     edx, eax; Length
0x14035d4e0  mov     r8d, 1; Alignment
0x14035d4e6  mov     rcx, [rsi+18h]; Address
0x14035d4ea  call    cs:__imp_ProbeForRead
0x14035d4f1  nop     dword ptr [rax+rax+00h]
0x14035d4f6  mov     r8d, [rsi+10h]; Size
0x14035d4fa  mov     rdx, [rsi+18h]; Src
0x14035d4fe  mov     rcx, r15; void *
0x14035d501  call    memmove
0x14035d506  mov     eax, [rsi+20h]
0x14035d509  test    eax, eax
0x14035d50b  jz      short loc_14035D526
0x14035d50d  mov     edx, eax; Length
0x14035d50f  mov     r8d, 1; Alignment
0x14035d515  mov     rcx, [rsi+28h]; Address
0x14035d519  call    cs:__imp_ProbeForWrite
0x14035d520  nop     dword ptr [rax+rax+00h]
0x14035d525  nop
0x14035d526  mov     eax, [rsi+8]
0x14035d529  test    al, 6
0x14035d52b  jz      loc_14035D645
0x14035d531  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x14035d536  mov     r12b, 1
0x14035d539  mov     [rsp+0F8h+var_B7], r12b
0x14035d53e  mov     rax, [r14+1B0h]
0x14035d545  test    rax, rax
0x14035d548  jnz     short loc_14035D571
0x14035d54a  mov     rdx, 0FFFFFFFFC0000225h
0x14035d551  mov     ebx, edx
0x14035d553  lea     ecx, [rax+2]
0x14035d556  call    cs:__imp_WdLogSingleEntry1
0x14035d55d  nop     dword ptr [rax+rax+00h]
0x14035d562  mov     cs:WdLogGlobalForLineNumber, 10ECh
0x14035d56c  jmp     loc_14035D98B
0x14035d571  mov     r13, [rax+40h]
0x14035d575  mov     [rsp+0F8h+var_A0], r13
0x14035d57a  call    cs:__imp_KeEnterCriticalRegion
0x14035d581  nop     dword ptr [rax+rax+00h]
0x14035d586  cmp     [r13+1E4h], dil
0x14035d58d  jz      short loc_14035D597
0x14035d58f  mov     rcx, r13
0x14035d592  call    DpiCheckForOutstandingD3Requests
0x14035d597  mov     dl, r12b; Wait
0x14035d59a  mov     rcx, [r13+0A8h]; Resource
0x14035d5a1  call    cs:__imp_ExAcquireResourceSharedLite
0x14035d5a8  nop     dword ptr [rax+rax+00h]
0x14035d5ad  mov     [rsp+0F8h+var_B8], r12b
0x14035d5b2  mov     ecx, [r13+0ECh]
0x14035d5b9  cmp     ecx, 2
0x14035d5bc  jz      short loc_14035D600
0x14035d5be  cmp     dword ptr [r13+0F0h], 2
0x14035d5c6  jnz     short loc_14035D5D7
0x14035d5c8  lea     eax, [rcx-3]
0x14035d5cb  test    eax, 0FFFFFFFCh
0x14035d5d0  jnz     short loc_14035D5D7
0x14035d5d2  cmp     ecx, 4
0x14035d5d5  jnz     short loc_14035D600
0x14035d5d7  mov     rdx, 0FFFFFFFFC00002B6h
0x14035d5de  mov     ebx, edx
0x14035d5e0  mov     ecx, 2
0x14035d5e5  call    cs:__imp_WdLogSingleEntry1
0x14035d5ec  nop     dword ptr [rax+rax+00h]
0x14035d5f1  mov     cs:WdLogGlobalForLineNumber, 110Eh
0x14035d5fb  jmp     loc_14035D98B
0x14035d600  mov     eax, [rsi+8]
0x14035d603  test    al, 4
0x14035d605  jz      short loc_14035D645
0x14035d607  mov     dl, [rsi+0Ch]
0x14035d60a  mov     rcx, [r14+1B0h]
0x14035d611  call    DpiAcquireCoreSyncAccessSafe
0x14035d616  movsxd  rbx, eax
0x14035d619  test    eax, eax
0x14035d61b  jns     short loc_14035D640
0x14035d61d  mov     rdx, rbx
0x14035d620  mov     ecx, 2
0x14035d625  call    cs:__imp_WdLogSingleEntry1
0x14035d62c  nop     dword ptr [rax+rax+00h]
0x14035d631  mov     cs:WdLogGlobalForLineNumber, 1126h
0x14035d63b  jmp     loc_14035D98B
0x14035d640  mov     [rsp+0F8h+var_B5], r12b
0x14035d645  mov     eax, [rsi+8]
0x14035d648  test    al, 1
0x14035d64a  jz      short loc_14035D66E
0x14035d64c  lea     rcx, [r14+20h]
0x14035d650  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14035d657  nop     dword ptr [rax+rax+00h]
0x14035d65c  mov     rax, gs:188h
0x14035d665  mov     [r14+58h], rax
0x14035d669  mov     [rsp+0F8h+var_B6], 1
0x14035d66e  mov     eax, [rsi+8]
0x14035d671  cmp     eax, 4
0x14035d674  jz      loc_14035D913
0x14035d67a  mov     edx, 8
0x14035d67f  cmp     eax, edx
0x14035d681  jz      loc_14035D8D4
0x14035d687  mov     edx, 10h
0x14035d68c  cmp     eax, edx
0x14035d68e  jz      loc_14035D895
0x14035d694  cmp     eax, 18h
0x14035d697  jz      loc_14035D7D6
0x14035d69d  cmp     eax, 20h ; ' '
0x14035d6a0  jz      short loc_14035D6CB
0x14035d6a2  mov     rdx, 0FFFFFFFFC00000BBh
0x14035d6a9  mov     ebx, edx
0x14035d6ab  mov     ecx, 2
0x14035d6b0  call    cs:__imp_WdLogSingleEntry1
0x14035d6b7  nop     dword ptr [rax+rax+00h]
0x14035d6bc  mov     cs:WdLogGlobalForLineNumber, 1215h
0x14035d6c6  jmp     loc_14035D946
0x14035d6cb  xor     edx, edx; Val
0x14035d6cd  lea     r8d, [rdx+40h]; Size
0x14035d6d1  lea     rcx, [rsp+0F8h+var_78]; void *
0x14035d6d9  call    memset
0x14035d6de  mov     byte ptr [r14+24Fh], 1
0x14035d6e6  cmp     dword ptr [rsi+10h], 404h
0x14035d6ed  jnb     short loc_14035D71B
0x14035d6ef  mov     ebx, 0C000000Dh
0x14035d6f4  mov     rdx, 0FFFFFFFFC000000Dh
0x14035d6fb  mov     ecx, 2
0x14035d700  call    cs:__imp_WdLogSingleEntry1
0x14035d707  nop     dword ptr [rax+rax+00h]
0x14035d70c  mov     cs:WdLogGlobalForLineNumber, 11E2h
0x14035d716  jmp     loc_14035D946
0x14035d71b  mov     [r15+3FFh], dil
0x14035d722  mov     dword ptr [rsp+0F8h+var_B0], edi
0x14035d726  mov     cl, 1
0x14035d728  call    cs:__imp_WdIsDebuggerPresent
0x14035d72f  nop     dword ptr [rax+rax+00h]
0x14035d734  test    al, al
0x14035d736  jz      short loc_14035D755
0x14035d738  mov     r8, r15; Format
0x14035d73b  xor     edx, edx; Level
0x14035d73d  lea     ecx, [rdx+65h]; ComponentId
0x14035d740  call    cs:__imp_DbgPrintEx
0x14035d747  nop     dword ptr [rax+rax+00h]
0x14035d74c  int     3; Trap to Debugger
0x14035d74d  mov     dword ptr [rsp+0F8h+var_B0], 1
0x14035d755  mov     [rsp+0F8h+var_78], 6
0x14035d760  mov     [rsp+0F8h+var_74], 40h ; '@'
0x14035d76b  mov     [rsp+0F8h+var_50], edi
0x14035d772  mov     [rsp+0F8h+var_58], rdi
0x14035d77a  xor     eax, eax
0x14035d77c  mov     [rsp+0F8h+var_70], rax
0x14035d784  xorps   xmm0, xmm0
0x14035d787  movups  [rsp+0F8h+var_68], xmm0
0x14035d78f  mov     [rsp+0F8h+var_48], 4Ah ; 'J'
0x14035d79a  mov     eax, [r15+400h]
0x14035d7a1  mov     [rsp+0F8h+var_44], eax
0x14035d7a8  mov     eax, dword ptr [rsp+0F8h+var_B0]
0x14035d7ac  mov     [rsp+0F8h+var_40], eax
0x14035d7b3  mov     [rsp+0F8h+var_3C], edi
0x14035d7ba  mov     rdx, 200000000h; unsigned __int64
0x14035d7c4  lea     rcx, [rsp+0F8h+var_78]; struct _DXGK_DIAG_HEADER *
0x14035d7cc  call    ?DxgkWriteDiagEntry@@YAJPEAU_DXGK_DIAG_HEADER@@_K@Z; DxgkWriteDiagEntry(_DXGK_DIAG_HEADER *,unsigned __int64)
0x14035d7d1  jmp     loc_14035D946
0x14035d7d6  cmp     dword ptr [rsi+10h], 18h
0x14035d7da  jnb     short loc_14035D808
0x14035d7dc  mov     ebx, 0C000000Dh
0x14035d7e1  mov     rdx, 0FFFFFFFFC000000Dh
0x14035d7e8  mov     ecx, 2
0x14035d7ed  call    cs:__imp_WdLogSingleEntry1
0x14035d7f4  nop     dword ptr [rax+rax+00h]
0x14035d7f9  mov     cs:WdLogGlobalForLineNumber, 1191h
0x14035d803  jmp     loc_14035D946
0x14035d808  mov     r9, rdi
0x14035d80b  mov     rcx, [r15+8]; Handle
0x14035d80f  test    rcx, rcx
0x14035d812  jz      short loc_14035D874
0x14035d814  mov     [rsp+0F8h+var_B0], rdi
0x14035d819  mov     [rsp+0F8h+HandleInformation], rdi; HandleInformation
0x14035d81e  lea     rax, [rsp+0F8h+var_B0]
0x14035d823  mov     [rsp+0F8h+Object], rax; Object
0x14035d828  mov     r9b, 1; AccessMode
0x14035d82b  mov     r8, cs:ExEventObjectType
0x14035d832  mov     r8, [r8]; ObjectType
0x14035d835  mov     edx, 1F0003h; DesiredAccess
0x14035d83a  call    cs:__imp_ObReferenceObjectByHandle
0x14035d841  nop     dword ptr [rax+rax+00h]
0x14035d846  mov     ebx, eax
0x14035d848  test    eax, eax
0x14035d84a  jns     short loc_14035D86F
0x14035d84c  movsxd  rdx, eax
0x14035d84f  mov     ecx, 2
0x14035d854  call    cs:__imp_WdLogSingleEntry1
0x14035d85b  nop     dword ptr [rax+rax+00h]
0x14035d860  mov     cs:WdLogGlobalForLineNumber, 11B2h
0x14035d86a  mov     r9, rdi
0x14035d86d  jmp     short loc_14035D874
0x14035d86f  mov     r9, [rsp+0F8h+var_B0]
0x14035d874  mov     eax, [r15]
0x14035d877  mov     dword ptr [rsp+0F8h+HandleInformation], eax; int
0x14035d87b  mov     eax, [r15+10h]
0x14035d87f  mov     dword ptr [rsp+0F8h+Object], eax; int
0x14035d883  xor     r8d, r8d
0x14035d886  xor     edx, edx
0x14035d888  mov     rcx, r14; P
0x14035d88b  call    DpiMiracastStopMiracastSessionSync
  ... truncated ...
```
