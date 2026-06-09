# BootAnimationRelayThreadStartup(CDDPDEV *)

- ea: `0x14002a344`
- end: `0x14002a6a4`
- name: `?BootAnimationRelayThreadStartup@@YAJPEAUCDDPDEV@@@Z`
- size: `864`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140021d5c`

## callees

- `0x14002a1cc`
- `0x14002a344`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14002a422`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002a422`
- `ntoskrnl!PsCreateSystemThread` at `0x14002a5c6`
- `ntoskrnl!PsCreateSystemThread` at `0x14002a5c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a5f0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a5f0`
- `ntoskrnl!ZwClose` at `0x14002a588`
- `ntoskrnl!ZwClose` at `0x14002a588`
- `ntoskrnl!KeInitializeEvent` at `0x14002a56f`
- `ntoskrnl!KeInitializeEvent` at `0x14002a56f`
- `ntoskrnl!ExAllocatePool2` at `0x14002a4e9`
- `ntoskrnl!ExAllocatePool2` at `0x14002a4e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a359`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a359`
- `watchdog!WdLogSingleEntry5` at `0x14002a45f`
- `watchdog!WdLogSingleEntry5` at `0x14002a645`
- `watchdog!WdLogSingleEntry5` at `0x14002a45f`
- `watchdog!WdLogSingleEntry5` at `0x14002a645`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002a525`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002a525`
- `watchdog!WdLogSingleEntry2` at `0x14002a50e`
- `watchdog!WdLogSingleEntry2` at `0x14002a50e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002a476`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002a65c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002a476`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002a65c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002a388`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002a388`
- `watchdog!WdLogSingleEntry0` at `0x14002a372`
- `watchdog!WdLogSingleEntry0` at `0x14002a372`

## pseudocode

```c
__int64 __fastcall BootAnimationRelayThreadStartup(unsigned int *StartContext)
{
  NTSTATUS v2; // edi
  _QWORD *v3; // rax
  void *v4; // rcx
  NTSTATUS v5; // eax
  _QWORD *v6; // rax
  struct _KEVENT *Pool2; // rax
  _QWORD *v9; // rax
  HANDLE v10; // rdi
  _QWORD *v11; // rax
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  HANDLE ThreadHandle; // [rsp+90h] [rbp+20h] BYREF
  HANDLE ProcessHandle; // [rsp+98h] [rbp+28h] BYREF

  v2 = 0;
  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4741;
    v3 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 4741;
  }
  if ( !(*((unsigned __int8 (__fastcall **)(_QWORD, _QWORD))StartContext + 67))(
          *((_QWORD *)StartContext + 311),
          StartContext[196])
    || !(*((unsigned __int8 (__fastcall **)(__int64))StartContext + 64))(2) )
  {
    return (unsigned int)v2;
  }
  v4 = (void *)*((_QWORD *)StartContext + 94);
  ProcessHandle = 0;
  v5 = ObOpenObjectByPointer(v4, 0x200u, 0, 2u, 0, 0, &ProcessHandle);
  if ( v5 < 0 )
  {
    WdLogSingleEntry5(2, StartContext, v5, StartContext[196], StartContext[199], StartContext[200]);
    WdLogGlobalForLineNumber = 4762;
    v6 = (_QWORD *)WdLogNewEntry5_WdError();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 4762;
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ProcessHandle);
    return 3221225473LL;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1684300612);
  *((_QWORD *)StartContext + 331) = Pool2;
  if ( Pool2 )
  {
    ThreadHandle = 0;
    KeInitializeEvent(Pool2, SynchronizationEvent, 0);
    v10 = ProcessHandle;
    if ( ThreadHandle )
      ZwClose(ThreadHandle);
    ThreadHandle = 0;
    v2 = PsCreateSystemThread(
           &ThreadHandle,
           0x1FFFFFu,
           &ObjectAttributes,
           v10,
           0,
           BootGraphicsUpdateThread,
           StartContext);
    if ( v2 >= 0 )
      KeWaitForSingleObject(*((PVOID *)StartContext + 331), Executive, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ThreadHandle);
    if ( v2 >= 0 )
      goto LABEL_15;
  }
  else
  {
    WdLogSingleEntry2(6, StartContext, StartContext[196]);
    WdLogGlobalForLineNumber = 4780;
    v9 = (_QWORD *)WdLogNewEntry5_WdLowResource();
    v9[3] = gCddImageInfo;
    v9[4] = (unsigned int)dword_14003E570;
    v9[5] = 215857758;
    WdLogGlobalForLineNumber = 4780;
    v2 = -1073741801;
  }
  (*((void (__fastcall **)(_QWORD, _QWORD))StartContext + 65))(0, StartContext[630]);
  WdLogSingleEntry5(2, StartContext, v2, StartContext[196], StartContext[199], StartContext[200]);
  WdLogGlobalForLineNumber = 4805;
  v11 = (_QWORD *)WdLogNewEntry5_WdError();
  v11[3] = gCddImageInfo;
  v11[4] = (unsigned int)dword_14003E570;
  v11[5] = 215857758;
  WdLogGlobalForLineNumber = 4805;
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ProcessHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002a344  mov     [rsp-18h+arg_10], rbx
0x14002a349  push    rbp
0x14002a34a  push    rdi
0x14002a34b  push    r15
0x14002a34d  mov     rbp, rsp
0x14002a350  sub     rsp, 70h
0x14002a354  mov     rbx, rcx
0x14002a357  xor     edi, edi
0x14002a359  call    cs:__imp_KeGetCurrentIrql
0x14002a360  nop     dword ptr [rax+rax+00h]
0x14002a365  mov     r15d, 0CDDBA5Eh
0x14002a36b  test    al, al
0x14002a36d  jz      short loc_14002A3BA
0x14002a36f  lea     ecx, [rdi+1]
0x14002a372  call    cs:__imp_WdLogSingleEntry0
0x14002a379  nop     dword ptr [rax+rax+00h]
0x14002a37e  mov     cs:WdLogGlobalForLineNumber, 1285h
0x14002a388  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002a38f  nop     dword ptr [rax+rax+00h]
0x14002a394  mov     rcx, rax
0x14002a397  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a39e  mov     [rcx+18h], rax
0x14002a3a2  mov     eax, cs:dword_14003E570
0x14002a3a8  mov     [rcx+20h], rax
0x14002a3ac  mov     [rcx+28h], r15
0x14002a3b0  mov     cs:WdLogGlobalForLineNumber, 1285h
0x14002a3ba  mov     rax, [rbx+218h]
0x14002a3c1  mov     edx, [rbx+310h]
0x14002a3c7  mov     rcx, [rbx+9B8h]
0x14002a3ce  call    _guard_dispatch_icall
0x14002a3d3  test    al, al
0x14002a3d5  jz      loc_14002A690
0x14002a3db  mov     rax, [rbx+200h]
0x14002a3e2  mov     ecx, 2
0x14002a3e7  call    _guard_dispatch_icall
0x14002a3ec  test    al, al
0x14002a3ee  jz      loc_14002A690
0x14002a3f4  mov     rcx, [rbx+2F0h]; Object
0x14002a3fb  lea     rax, [rbp+ProcessHandle]
0x14002a3ff  mov     [rsp+70h+Handle], rax; Handle
0x14002a404  mov     r9d, 2; DesiredAccess
0x14002a40a  mov     [rsp+70h+AccessMode], dil; AccessMode
0x14002a40f  xor     r8d, r8d; PassedAccessState
0x14002a412  mov     [rbp+ProcessHandle], rdi
0x14002a416  mov     [rsp+70h+ObjectType], rdi; ObjectType
0x14002a41b  mov     edi, 200h
0x14002a420  mov     edx, edi; HandleAttributes
0x14002a422  call    cs:__imp_ObOpenObjectByPointer
0x14002a429  nop     dword ptr [rax+rax+00h]
0x14002a42e  test    eax, eax
0x14002a430  jns     loc_14002A4B7
0x14002a436  mov     edx, [rbx+320h]
0x14002a43c  mov     ecx, 2
0x14002a441  mov     r10d, [rbx+31Ch]
0x14002a448  mov     r9d, [rbx+310h]
0x14002a44f  mov     qword ptr [rsp+70h+AccessMode], rdx
0x14002a454  mov     rdx, rbx
0x14002a457  movsxd  r8, eax
0x14002a45a  mov     [rsp+70h+ObjectType], r10
0x14002a45f  call    cs:__imp_WdLogSingleEntry5
0x14002a466  nop     dword ptr [rax+rax+00h]
0x14002a46b  mov     ebx, 129Ah
0x14002a470  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a476  call    cs:__imp_WdLogNewEntry5_WdError
0x14002a47d  nop     dword ptr [rax+rax+00h]
0x14002a482  mov     rcx, rax
0x14002a485  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a48c  mov     [rcx+18h], rax
0x14002a490  mov     eax, cs:dword_14003E570
0x14002a496  mov     [rcx+20h], rax
0x14002a49a  mov     [rcx+28h], r15
0x14002a49e  lea     rcx, [rbp+ProcessHandle]
0x14002a4a2  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a4a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14002a4ad  mov     eax, 0C0000001h
0x14002a4b2  jmp     loc_14002A692
0x14002a4b7  mov     edx, 18h
0x14002a4bc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002a4c4  xorps   xmm0, xmm0
0x14002a4c7  mov     qword ptr [rbp+ObjectAttributes.Attributes], rdi
0x14002a4cb  mov     r8d, 64646344h
0x14002a4d1  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002a4d9  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14002a4e1  lea     ecx, [rdx+28h]
0x14002a4e4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a4e9  call    cs:__imp_ExAllocatePool2
0x14002a4f0  nop     dword ptr [rax+rax+00h]
0x14002a4f5  mov     [rbx+0A58h], rax
0x14002a4fc  test    rax, rax
0x14002a4ff  jnz     short loc_14002A55D
0x14002a501  mov     r8d, [rbx+310h]
0x14002a508  lea     ecx, [rax+6]
0x14002a50b  mov     rdx, rbx
0x14002a50e  call    cs:__imp_WdLogSingleEntry2
0x14002a515  nop     dword ptr [rax+rax+00h]
0x14002a51a  mov     edi, 12ACh
0x14002a51f  mov     cs:WdLogGlobalForLineNumber, edi
0x14002a525  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002a52c  nop     dword ptr [rax+rax+00h]
0x14002a531  mov     rcx, rax
0x14002a534  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a53b  mov     [rcx+18h], rax
0x14002a53f  mov     eax, cs:dword_14003E570
0x14002a545  mov     [rcx+20h], rax
0x14002a549  mov     [rcx+28h], r15
0x14002a54d  mov     cs:WdLogGlobalForLineNumber, edi
0x14002a553  mov     edi, 0C0000017h
0x14002a558  jmp     loc_14002A609
0x14002a55d  xor     r8d, r8d; State
0x14002a560  mov     [rbp+ThreadHandle], 0
0x14002a568  mov     rcx, rax; Event
0x14002a56b  lea     edx, [r8+1]; Type
0x14002a56f  call    cs:__imp_KeInitializeEvent
0x14002a576  nop     dword ptr [rax+rax+00h]
0x14002a57b  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002a57f  mov     rdi, [rbp+ProcessHandle]
0x14002a583  test    rcx, rcx
0x14002a586  jz      short loc_14002A594
0x14002a588  call    cs:__imp_ZwClose
0x14002a58f  nop     dword ptr [rax+rax+00h]
0x14002a594  lea     rax, ?BootGraphicsUpdateThread@@YAXPEAUCDDPDEV@@@Z; BootGraphicsUpdateThread(CDDPDEV *)
0x14002a59b  mov     [rsp+70h+Handle], rbx; StartContext
0x14002a5a0  mov     qword ptr [rsp+70h+AccessMode], rax; StartRoutine
0x14002a5a5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002a5a9  mov     r9, rdi; ProcessHandle
0x14002a5ac  mov     [rsp+70h+ObjectType], 0; ClientId
0x14002a5b5  mov     edx, 1FFFFFh; DesiredAccess
0x14002a5ba  mov     [rbp+ThreadHandle], 0
0x14002a5c2  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14002a5c6  call    cs:__imp_PsCreateSystemThread
0x14002a5cd  nop     dword ptr [rax+rax+00h]
0x14002a5d2  mov     edi, eax
0x14002a5d4  test    eax, eax
0x14002a5d6  js      short loc_14002A5FC
0x14002a5d8  mov     rcx, [rbx+0A58h]; Object
0x14002a5df  xor     r9d, r9d; Alertable
0x14002a5e2  xor     r8d, r8d; WaitMode
0x14002a5e5  mov     [rsp+70h+ObjectType], 0; Timeout
0x14002a5ee  xor     edx, edx; WaitReason
0x14002a5f0  call    cs:__imp_KeWaitForSingleObject
0x14002a5f7  nop     dword ptr [rax+rax+00h]
0x14002a5fc  lea     rcx, [rbp+ThreadHandle]
0x14002a600  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14002a605  test    edi, edi
0x14002a607  jns     short loc_14002A687
0x14002a609  mov     rax, [rbx+208h]
0x14002a610  xor     ecx, ecx
0x14002a612  mov     edx, [rbx+9D8h]
0x14002a618  call    _guard_dispatch_icall
0x14002a61d  mov     ecx, [rbx+31Ch]
0x14002a623  mov     rdx, rbx
0x14002a626  mov     eax, [rbx+320h]
0x14002a62c  mov     r9d, [rbx+310h]
0x14002a633  mov     qword ptr [rsp+70h+AccessMode], rax
0x14002a638  mov     [rsp+70h+ObjectType], rcx
0x14002a63d  mov     ecx, 2
0x14002a642  movsxd  r8, edi
0x14002a645  call    cs:__imp_WdLogSingleEntry5
0x14002a64c  nop     dword ptr [rax+rax+00h]
0x14002a651  mov     ebx, 12C5h
0x14002a656  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a65c  call    cs:__imp_WdLogNewEntry5_WdError
0x14002a663  nop     dword ptr [rax+rax+00h]
0x14002a668  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a66f  mov     [rax+18h], rcx
0x14002a673  mov     ecx, cs:dword_14003E570
0x14002a679  mov     [rax+20h], rcx
0x14002a67d  mov     [rax+28h], r15
0x14002a681  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a687  lea     rcx, [rbp+ProcessHandle]
0x14002a68b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14002a690  mov     eax, edi
0x14002a692  mov     rbx, [rsp+70h+arg_10]
0x14002a69a  add     rsp, 70h
0x14002a69e  pop     r15
0x14002a6a0  pop     rdi
0x14002a6a1  pop     rbp
0x14002a6a2  retn
```
