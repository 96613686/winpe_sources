# CreateRemoteThreadEx

- ea: `0x1800c6880`
- end: `0x1800c7030`
- name: `CreateRemoteThreadEx`
- size: `1968`
- prototype: `HANDLE __stdcall(HANDLE hProcess, LPSECURITY_ATTRIBUTES lpThreadAttributes, SIZE_T dwStackSize, LPTHREAD_START_ROUTINE lpStartAddress, LPVOID lpParameter, DWORD dwCreationFlags, LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList, LPDWORD lpThreadId)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18017f570`
- `0x18017f5c0`

## callees

- `0x1800134a0`
- `0x1800222a0`
- `0x1800c6880`
- `0x1800c7038`
- `0x1800c8680`
- `0x18012d080`
- `0x18012d119`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlQueryInformationActivationContext` at `0x1800c6a93`
- `ntdll!RtlQueryInformationActivationContext` at `0x1800c6a93`
- `ntdll!RtlReleaseActivationContext` at `0x1800c6d3d`
- `ntdll!RtlReleaseActivationContext` at `0x1800c6fff`
- `ntdll!RtlReleaseActivationContext` at `0x18018b5f9`
- `ntdll!RtlReleaseActivationContext` at `0x18018b63a`
- `ntdll!RtlReleaseActivationContext` at `0x1800c6d3d`
- `ntdll!RtlReleaseActivationContext` at `0x1800c6fff`
- `ntdll!RtlReleaseActivationContext` at `0x18018b5f9`
- `ntdll!RtlReleaseActivationContext` at `0x18018b63a`
- `ntdll!NtClose` at `0x1800c6fd7`
- `ntdll!NtClose` at `0x1800c6fe3`
- `ntdll!NtClose` at `0x1800c7025`
- `ntdll!NtClose` at `0x18018b615`
- `ntdll!NtClose` at `0x18018b66f`
- `ntdll!NtClose` at `0x1800c6fd7`
- `ntdll!NtClose` at `0x1800c6fe3`
- `ntdll!NtClose` at `0x1800c7025`
- `ntdll!NtClose` at `0x18018b615`
- `ntdll!NtClose` at `0x18018b66f`
- `ntdll!NtQueryInformationProcess` at `0x1800c6f02`
- `ntdll!NtQueryInformationProcess` at `0x1800c6f4d`
- `ntdll!NtQueryInformationProcess` at `0x1800c6f02`
- `ntdll!NtQueryInformationProcess` at `0x1800c6f4d`
- `ntdll!NtDuplicateObject` at `0x1800c6ed9`
- `ntdll!NtDuplicateObject` at `0x1800c6ed9`
- `ntdll!NtCreateThreadEx` at `0x1800c6b54`
- `ntdll!NtCreateThreadEx` at `0x1800c6b54`
- `ntdll!RtlAllocateActivationContextStack` at `0x1800c6c7d`
- `ntdll!RtlAllocateActivationContextStack` at `0x1800c6c7d`
- `ntdll!RtlActivateActivationContextEx` at `0x1800c6cc8`
- `ntdll!RtlActivateActivationContextEx` at `0x1800c6cc8`
- `ntdll!NtResumeThread` at `0x1800c6c50`
- `ntdll!NtResumeThread` at `0x1800c6c50`
- `ntdll!RtlFreeActivationContextStack` at `0x1800c700a`
- `ntdll!RtlFreeActivationContextStack` at `0x18018b64d`
- `ntdll!RtlFreeActivationContextStack` at `0x1800c700a`
- `ntdll!RtlFreeActivationContextStack` at `0x18018b64d`
- `ntdll!NtTerminateThread` at `0x1800c7017`
- `ntdll!NtTerminateThread` at `0x18018b662`
- `ntdll!NtTerminateThread` at `0x1800c7017`
- `ntdll!NtTerminateThread` at `0x18018b662`

## string_xrefs

- `0x1800c6b95`: `CreateRemoteThreadEx`
- `0x1800c6cee`: `CreateRemoteThreadEx`
- `0x1800c6d1b`: `CreateRemoteThreadEx`
- `0x1800c6b9c`: `SXS: %s - Failing thread create because RtlQueryInformationActivationContext() failed with status %08lx\n`
- `0x1800c6cf5`: `SXS: %s - Failing thread create because RtlActivateActivationContextEx() failed with status %08lx\n`
- `0x1800c6d22`: `SXS: %s - Failing thread create because RtlAllocateActivationContextStack() failed with status %08lx\n`
- `0x1800c6bf6`: `CsrCreateRemoteThread`

## pseudocode

```c
HANDLE __stdcall CreateRemoteThreadEx(
        HANDLE hProcess,
        LPSECURITY_ATTRIBUTES lpThreadAttributes,
        SIZE_T dwStackSize,
        LPTHREAD_START_ROUTINE lpStartAddress,
        LPVOID lpParameter,
        DWORD dwCreationFlags,
        LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList,
        LPDWORD lpThreadId)
{
  int v10; // edx
  _BYTE *v11; // r12
  __int64 v12; // rax
  char v13; // r14
  char v14; // bl
  NTSTATUS InformationActivationContext; // eax
  NTSTATUS v16; // ebx
  char v17; // si
  int v18; // edx
  SIZE_T v19; // rcx
  SIZE_T v20; // r8
  HMODULE ModuleHandleA; // rax
  FARPROC CsrCreateRemoteThread; // rax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  int v26; // eax
  NTSTATUS InformationProcess; // esi
  __int64 v28; // rcx
  HANDLE ThreadHandle; // [rsp+D8h] [rbp-5D0h] BYREF
  unsigned int v30; // [rsp+E0h] [rbp-5C8h] BYREF
  HANDLE TargetHandle; // [rsp+E8h] [rbp-5C0h] BYREF
  int v32; // [rsp+F0h] [rbp-5B8h] BYREF
  PVOID Context[2]; // [rsp+F8h] [rbp-5B0h] BYREF
  PTEB Teb; // [rsp+108h] [rbp-5A0h] BYREF
  PACTIVATION_CONTEXT_STACK Stack; // [rsp+110h] [rbp-598h] BYREF
  ULONG SuspendCount; // [rsp+118h] [rbp-590h] BYREF
  unsigned __int64 Cookie; // [rsp+120h] [rbp-588h] BYREF
  SIZE_T v38; // [rsp+128h] [rbp-580h]
  LPVOID v39; // [rsp+130h] [rbp-578h]
  LPDWORD v40; // [rsp+138h] [rbp-570h]
  __int128 v41; // [rsp+140h] [rbp-568h] BYREF
  _BYTE v42[48]; // [rsp+150h] [rbp-558h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+180h] [rbp-528h] BYREF
  _BYTE v44[32]; // [rsp+1B0h] [rbp-4F8h] BYREF
  int v45; // [rsp+1D0h] [rbp-4D8h]
  _QWORD v46[142]; // [rsp+1F0h] [rbp-4B8h] BYREF

  Cookie = (unsigned __int64)lpStartAddress;
  v38 = dwStackSize;
  v39 = lpParameter;
  v40 = lpThreadId;
  *(_OWORD *)Context = 0;
  Stack = 0;
  v30 = 0;
  v41 = 0;
  memset_0(v46, 0, 0x468u);
  ThreadHandle = 0;
  TargetHandle = 0;
  memset(v42, 0, 44);
  SuspendCount = 0;
  memset_0(v44, 0, 0x40u);
  memset(ProcessInformation, 0, 44);
  Teb = 0;
  v32 = 0;
  if ( (dwCreationFlags & 0xFFFEFFFB) != 0 )
  {
    v28 = 3221225485LL;
    goto LABEL_74;
  }
  if ( lpThreadAttributes )
  {
    *(_DWORD *)v42 = 48;
    *(_QWORD *)&v42[8] = 0;
    *(_DWORD *)&v42[24] = lpThreadAttributes->bInheritHandle ? 2 : 0;
    *(_QWORD *)&v42[16] = 0;
    *(_OWORD *)&v42[32] = (unsigned __int64)lpThreadAttributes->lpSecurityDescriptor;
    if ( pfnAdjustObjectAttributesForPrivateNamespace )
      pfnAdjustObjectAttributesForPrivateNamespace(v42);
    v11 = v42;
  }
  else
  {
    v11 = 0;
  }
  v46[1] = 65539;
  v46[2] = 16;
  v46[4] = 0;
  v46[3] = &v41;
  v46[5] = 65540;
  v46[6] = 8;
  v46[8] = 0;
  v46[7] = &Teb;
  v12 = 2;
  v30 = 2;
  if ( lpAttributeList )
  {
    LOBYTE(v10) = 1;
    v26 = BasepConvertWin32AttributeList(
            (_DWORD)lpAttributeList,
            v10,
            (unsigned int)&v32,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            (__int64)v46,
            (__int64)&v30);
    if ( v26 < 0 )
    {
      v28 = (unsigned int)v26;
      goto LABEL_74;
    }
    v12 = v30;
  }
  v13 = 0;
  v46[0] = 32 * v12 + 8;
  TargetHandle = 0;
  v14 = 1;
  if ( hProcess != (HANDLE)-1LL )
  {
    if ( NtDuplicateObject(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           hProcess,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &TargetHandle,
           0x402u,
           0,
           0) >= 0 )
      hProcess = TargetHandle;
    InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess < 0
      || *(HANDLE *)&ProcessInformation[2] == NtCurrentTeb()->ClientId.UniqueProcess
      || (v14 = 0,
          InformationProcess = NtQueryInformationProcess(hProcess, ProcessImageInformation, v44, 0x40u, 0),
          InformationProcess < 0)
      || (unsigned int)(v45 - 2) <= 1 )
    {
      if ( InformationProcess >= 0 )
        goto LABEL_6;
    }
    else
    {
      InformationProcess = -1073741823;
    }
    if ( TargetHandle )
      NtClose(TargetHandle);
    v28 = (unsigned int)InformationProcess;
LABEL_74:
    BaseSetLastNTError(v28);
    return 0;
  }
LABEL_6:
  if ( v14 )
  {
    InformationActivationContext = RtlQueryInformationActivationContext(1u, 0, 0, 1u, Context, 0x10u, 0);
    v16 = InformationActivationContext;
    if ( InformationActivationContext < 0 )
    {
      DbgPrint_0(
        "SXS: %s - Failing thread create because RtlQueryInformationActivationContext() failed with status %08lx\n",
        "CreateRemoteThreadEx",
        InformationActivationContext);
      goto LABEL_41;
    }
    if ( byte_1803A2DC4 || NtCurrentTeb()->SubProcessTag || Context[0] && ((__int64)Context[1] & 1) == 0 )
    {
      v17 = 1;
      goto LABEL_14;
    }
  }
  v17 = 0;
  if ( (dwCreationFlags & 4) != 0 )
  {
LABEL_14:
    v18 = 1;
    goto LABEL_15;
  }
  v18 = 0;
LABEL_15:
  v32 = v18;
  v19 = 0;
  v20 = v38;
  if ( (dwCreationFlags & 0x10000) != 0 )
  {
    v19 = v38;
    v20 = 0;
  }
  v16 = NtCreateThreadEx(&ThreadHandle, 0x1FFFFF, v11, hProcess, Cookie, v39, v18, 0, v20, v19, v46);
  if ( v16 < 0 )
    goto LABEL_41;
  if ( !v17 )
    goto LABEL_19;
  if ( NtCurrentTeb()->SubProcessTag )
    Teb->SubProcessTag = NtCurrentTeb()->SubProcessTag;
  if ( Context[0] && ((__int64)Context[1] & 1) == 0 )
  {
    Cookie = 0;
    v23 = RtlAllocateActivationContextStack(&Stack);
    v16 = v23;
    if ( v23 < 0 )
    {
      DbgPrint_0(
        "SXS: %s - Failing thread create because RtlAllocateActivationContextStack() failed with status %08lx\n",
        "CreateRemoteThreadEx",
        v23);
      goto LABEL_41;
    }
    Teb->ActivationContextStackPointer = Stack;
    v24 = RtlActivateActivationContextEx(1u, Teb, Context[0], &Cookie);
    v16 = v24;
    if ( v24 < 0 )
    {
      DbgPrint_0(
        "SXS: %s - Failing thread create because RtlActivateActivationContextEx() failed with status %08lx\n",
        "CreateRemoteThreadEx",
        v24);
      goto LABEL_41;
    }
    v13 = 1;
  }
  if ( !byte_1803A2DC4
    || (ModuleHandleA = GetModuleHandleA("csrsrv"),
        (CsrCreateRemoteThread = GetProcAddress(ModuleHandleA, "CsrCreateRemoteThread")) == 0)
    || (v16 = ((__int64 (__fastcall *)(HANDLE, __int128 *))CsrCreateRemoteThread)(ThreadHandle, &v41), v16 >= 0) )
  {
LABEL_19:
    if ( v40 )
      *v40 = DWORD2(v41);
    if ( v17 && (dwCreationFlags & 4) == 0 )
      NtResumeThread(ThreadHandle, &SuspendCount);
  }
LABEL_41:
  if ( Context[0] )
    RtlReleaseActivationContext(Context[0]);
  if ( TargetHandle )
    NtClose(TargetHandle);
  if ( v16 >= 0 )
    return ThreadHandle;
  if ( v13 && Context[0] )
    RtlReleaseActivationContext(Context[0]);
  if ( Stack )
    RtlFreeActivationContextStack(Stack);
  if ( ThreadHandle )
  {
    NtTerminateThread(ThreadHandle, v16);
    NtClose(ThreadHandle);
  }
  BaseSetLastNTError((unsigned int)v16);
  return 0;
}

```

## disassembly

```asm
0x1800c6880  push    rbx
0x1800c6882  push    rsi
0x1800c6883  push    rdi
0x1800c6884  push    r12
0x1800c6886  push    r13
0x1800c6888  push    r14
0x1800c688a  push    r15
0x1800c688c  sub     rsp, 670h
0x1800c6893  mov     rax, cs:__security_cookie
0x1800c689a  xor     rax, rsp
0x1800c689d  mov     [rsp+6A8h+var_48], rax
0x1800c68a5  mov     [rsp+6A8h+Cookie], r9
0x1800c68ad  mov     [rsp+6A8h+var_580], r8
0x1800c68b5  mov     rbx, rdx
0x1800c68b8  mov     r13, rcx
0x1800c68bb  mov     rax, [rsp+6A8h+lpParameter]
0x1800c68c3  mov     [rsp+6A8h+var_578], rax
0x1800c68cb  mov     rdi, [rsp+6A8h+lpAttributeList]
0x1800c68d3  mov     rax, [rsp+6A8h+lpThreadId]
0x1800c68db  mov     [rsp+6A8h+var_570], rax
0x1800c68e3  xorps   xmm0, xmm0
0x1800c68e6  movups  xmmword ptr [rsp+6A8h+Context], xmm0
0x1800c68ee  xor     esi, esi
0x1800c68f0  mov     [rsp+6A8h+Stack], rsi
0x1800c68f8  mov     [rsp+6A8h+var_5C8], esi
0x1800c68ff  movups  [rsp+6A8h+var_568], xmm0
0x1800c6907  xor     edx, edx; Val
0x1800c6909  mov     r8d, 468h; Size
0x1800c690f  lea     rcx, [rsp+6A8h+var_4B8]; void *
0x1800c6917  call    memset_0
0x1800c691c  mov     [rsp+6A8h+ThreadHandle], rsi
0x1800c6924  mov     [rsp+6A8h+TargetHandle], rsi
0x1800c692c  xor     eax, eax
0x1800c692e  xorps   xmm0, xmm0
0x1800c6931  movups  [rsp+6A8h+var_558], xmm0
0x1800c6939  movups  [rsp+6A8h+var_548], xmm0
0x1800c6941  movups  [rsp+6A8h+var_548+0Ch], xmm0
0x1800c6949  mov     [rsp+6A8h+SuspendCount], esi
0x1800c6950  xor     edx, edx; Val
0x1800c6952  mov     r8d, 40h ; '@'; Size
0x1800c6958  lea     rcx, [rsp+6A8h+var_4F8]; void *
0x1800c6960  call    memset_0
0x1800c6965  xor     eax, eax
0x1800c6967  xorps   xmm0, xmm0
0x1800c696a  movups  [rsp+6A8h+ProcessInformation], xmm0
0x1800c6972  movups  [rsp+6A8h+var_518], xmm0
0x1800c697a  movups  [rsp+6A8h+var_518+0Ch], xmm0
0x1800c6982  mov     [rsp+6A8h+Teb], rsi
0x1800c698a  mov     [rsp+6A8h+var_5B8], esi
0x1800c6991  mov     r15d, [rsp+6A8h+dwCreationFlags]
0x1800c6999  test    r15d, 0FFFEFFFBh
0x1800c69a0  jnz     loc_1800C6FA1
0x1800c69a6  test    rbx, rbx
0x1800c69a9  jnz     loc_1800C6D87
0x1800c69af  mov     r12d, esi
0x1800c69b2  mov     [rsp+6A8h+var_5D4], esi
0x1800c69b9  mov     [rsp+6A8h+var_4B0], 10003h
0x1800c69c5  mov     [rsp+6A8h+var_4A8], 10h
0x1800c69d1  mov     [rsp+6A8h+var_498], rsi
0x1800c69d9  lea     rax, [rsp+6A8h+var_568]
0x1800c69e1  mov     [rsp+6A8h+var_4A0], rax
0x1800c69e9  mov     [rsp+6A8h+var_490], 10004h
0x1800c69f5  mov     [rsp+6A8h+var_488], 8
0x1800c6a01  mov     [rsp+6A8h+var_478], rsi
0x1800c6a09  lea     rax, [rsp+6A8h+Teb]
0x1800c6a11  mov     [rsp+6A8h+var_480], rax
0x1800c6a19  mov     eax, 2
0x1800c6a1e  mov     [rsp+6A8h+var_5C8], eax
0x1800c6a25  test    rdi, rdi
0x1800c6a28  jnz     loc_1800C6DED
0x1800c6a2e  xor     r14b, r14b
0x1800c6a31  mov     [rsp+6A8h+var_5D8], r14b
0x1800c6a39  shl     rax, 5
0x1800c6a3d  add     rax, 8
0x1800c6a41  mov     [rsp+6A8h+var_4B8], rax
0x1800c6a49  mov     edi, r15d
0x1800c6a4c  and     edi, 10000h
0x1800c6a52  mov     [rsp+6A8h+TargetHandle], rsi
0x1800c6a5a  mov     bl, 1
0x1800c6a5c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800c6a60  jnz     loc_1800C6EB4
0x1800c6a66  test    bl, bl
0x1800c6a68  jz      short loc_1800C6ACF
0x1800c6a6a  mov     [rsp+6A8h+pcbWrittenOrRequired], rsi; pcbWrittenOrRequired
0x1800c6a6f  mov     [rsp+6A8h+cbBuffer], 10h; cbBuffer
0x1800c6a78  lea     rax, [rsp+6A8h+Context]
0x1800c6a80  mov     [rsp+6A8h+pvBuffer], rax; pvBuffer
0x1800c6a85  mov     r9d, 1; ulInfoClass
0x1800c6a8b  xor     r8d, r8d; pvSubInstance
0x1800c6a8e  xor     edx, edx; Context
0x1800c6a90  mov     ecx, r9d; dwFlags
0x1800c6a93  call    cs:__imp_RtlQueryInformationActivationContext
0x1800c6a99  mov     ebx, eax
0x1800c6a9b  mov     [rsp+6A8h+var_5D4], eax
0x1800c6aa2  test    eax, eax
0x1800c6aa4  js      loc_1800C6B92
0x1800c6aaa  cmp     cs:byte_1803A2DC4, 0
0x1800c6ab1  jnz     short loc_1800C6ADC
0x1800c6ab3  mov     rax, gs:1720h
0x1800c6abc  test    rax, rax
0x1800c6abf  jnz     short loc_1800C6ADC
0x1800c6ac1  cmp     [rsp+6A8h+Context], rax
0x1800c6ac9  jnz     loc_1800C6D05
0x1800c6acf  xor     sil, sil
0x1800c6ad2  test    r15b, 4
0x1800c6ad6  jnz     short loc_1800C6ADF
0x1800c6ad8  xor     edx, edx
0x1800c6ada  jmp     short loc_1800C6AE4
0x1800c6adc  mov     sil, 1
0x1800c6adf  mov     edx, 1
0x1800c6ae4  mov     [rsp+6A8h+var_5B8], edx
0x1800c6aeb  xor     ecx, ecx
0x1800c6aed  test    edi, edi
0x1800c6aef  mov     r8, [rsp+6A8h+var_580]
0x1800c6af7  cmovnz  rcx, r8
0x1800c6afb  xor     eax, eax
0x1800c6afd  test    edi, edi
0x1800c6aff  cmovnz  r8, rax
0x1800c6b03  lea     rax, [rsp+6A8h+var_4B8]
0x1800c6b0b  mov     [rsp+6A8h+var_658], rax
0x1800c6b10  mov     [rsp+6A8h+var_660], rcx
0x1800c6b15  mov     [rsp+6A8h+var_668], r8
0x1800c6b1a  mov     [rsp+6A8h+var_670], 0
0x1800c6b23  mov     dword ptr [rsp+6A8h+pcbWrittenOrRequired], edx
0x1800c6b27  mov     rax, [rsp+6A8h+var_578]
0x1800c6b2f  mov     [rsp+6A8h+cbBuffer], rax
0x1800c6b34  mov     rax, [rsp+6A8h+Cookie]
0x1800c6b3c  mov     [rsp+6A8h+pvBuffer], rax
0x1800c6b41  mov     r9, r13
0x1800c6b44  mov     r8, r12
0x1800c6b47  mov     edx, 1FFFFFh
0x1800c6b4c  lea     rcx, [rsp+6A8h+ThreadHandle]
0x1800c6b54  call    cs:__imp_NtCreateThreadEx
0x1800c6b5a  mov     ebx, eax
0x1800c6b5c  mov     [rsp+6A8h+var_5D4], eax
0x1800c6b63  test    eax, eax
0x1800c6b65  js      short loc_1800C6B8B
0x1800c6b67  test    sil, sil
0x1800c6b6a  jnz     short loc_1800C6BAD
0x1800c6b6c  mov     rcx, [rsp+6A8h+var_570]
0x1800c6b74  test    rcx, rcx
0x1800c6b77  jz      short loc_1800C6B82
0x1800c6b79  mov     eax, dword ptr [rsp+6A8h+var_568+8]
0x1800c6b80  mov     [rcx], eax
0x1800c6b82  test    sil, sil
0x1800c6b85  jnz     loc_1800C6C36
0x1800c6b8b  xor     esi, esi
0x1800c6b8d  jmp     loc_1800C6D30
0x1800c6b92  mov     r8d, eax
0x1800c6b95  lea     rdx, aCreateremoteth_1; "CreateRemoteThreadEx"
0x1800c6b9c  lea     rcx, aSxsSFailingThr_1; "SXS: %s - Failing thread create because"...
0x1800c6ba3  call    DbgPrint_0
0x1800c6ba8  jmp     loc_1800C6D30
0x1800c6bad  mov     rax, gs:1720h
0x1800c6bb6  test    rax, rax
0x1800c6bb9  jz      short loc_1800C6BD3
0x1800c6bbb  mov     rcx, gs:1720h
0x1800c6bc4  mov     rax, [rsp+6A8h+Teb]
0x1800c6bcc  mov     [rax+1720h], rcx
0x1800c6bd3  cmp     [rsp+6A8h+Context], 0
0x1800c6bdc  jnz     short loc_1800C6C5B
0x1800c6bde  cmp     cs:byte_1803A2DC4, 0
0x1800c6be5  jz      short loc_1800C6B6C
0x1800c6be7  lea     rcx, aCsrsrv; "csrsrv"
0x1800c6bee  call    GetModuleHandleA
0x1800c6bf3  mov     rcx, rax; hModule
0x1800c6bf6  lea     rdx, aCsrcreateremot; "CsrCreateRemoteThread"
0x1800c6bfd  call    GetProcAddress
0x1800c6c02  test    rax, rax
0x1800c6c05  jz      loc_1800C6B6C
0x1800c6c0b  lea     rdx, [rsp+6A8h+var_568]
0x1800c6c13  mov     rcx, [rsp+6A8h+ThreadHandle]
0x1800c6c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c20  mov     ebx, eax
0x1800c6c22  mov     [rsp+6A8h+var_5D4], eax
0x1800c6c29  test    eax, eax
0x1800c6c2b  js      loc_1800C6B8B
0x1800c6c31  jmp     loc_1800C6B6C
0x1800c6c36  test    r15b, 4
0x1800c6c3a  jnz     loc_1800C6B8B
0x1800c6c40  lea     rdx, [rsp+6A8h+SuspendCount]; SuspendCount
0x1800c6c48  mov     rcx, [rsp+6A8h+ThreadHandle]; ThreadHandle
0x1800c6c50  call    cs:__imp_NtResumeThread
0x1800c6c56  jmp     loc_1800C6B8B
0x1800c6c5b  test    byte ptr [rsp+6A8h+Context+8], 1
0x1800c6c63  jnz     loc_1800C6BDE
0x1800c6c69  mov     [rsp+6A8h+Cookie], 0
0x1800c6c75  lea     rcx, [rsp+6A8h+Stack]; Stack
0x1800c6c7d  call    cs:__imp_RtlAllocateActivationContextStack
0x1800c6c83  mov     ebx, eax
0x1800c6c85  mov     [rsp+6A8h+var_5D4], eax
0x1800c6c8c  test    eax, eax
0x1800c6c8e  js      loc_1800C6D18
0x1800c6c94  mov     rcx, [rsp+6A8h+Stack]
0x1800c6c9c  mov     rax, [rsp+6A8h+Teb]
0x1800c6ca4  mov     [rax+2C8h], rcx
0x1800c6cab  lea     r9, [rsp+6A8h+Cookie]; Cookie
0x1800c6cb3  mov     r8, [rsp+6A8h+Context]; Context
0x1800c6cbb  mov     rdx, [rsp+6A8h+Teb]; Teb
0x1800c6cc3  mov     ecx, 1; Flags
0x1800c6cc8  call    cs:__imp_RtlActivateActivationContextEx
0x1800c6cce  mov     ebx, eax
0x1800c6cd0  mov     [rsp+6A8h+var_5D4], eax
0x1800c6cd7  test    eax, eax
0x1800c6cd9  js      short loc_1800C6CEB
0x1800c6cdb  mov     r14b, 1
0x1800c6cde  mov     [rsp+6A8h+var_5D8], r14b
0x1800c6ce6  jmp     loc_1800C6BDE
0x1800c6ceb  mov     r8d, eax
0x1800c6cee  lea     rdx, aCreateremoteth_1; "CreateRemoteThreadEx"
0x1800c6cf5  lea     rcx, aSxsSFailingThr; "SXS: %s - Failing thread create because"...
0x1800c6cfc  call    DbgPrint_0
0x1800c6d01  xor     esi, esi
0x1800c6d03  jmp     short loc_1800C6D30
0x1800c6d05  test    byte ptr [rsp+6A8h+Context+8], 1
0x1800c6d0d  jnz     loc_1800C6ACF
0x1800c6d13  jmp     loc_1800C6ADC
0x1800c6d18  mov     r8d, eax
0x1800c6d1b  lea     rdx, aCreateremoteth_1; "CreateRemoteThreadEx"
0x1800c6d22  lea     rcx, aSxsSFailingThr_0; "SXS: %s - Failing thread create because"...
0x1800c6d29  call    DbgPrint_0
0x1800c6d2e  xor     esi, esi
0x1800c6d30  mov     rcx, [rsp+6A8h+Context]; handle
0x1800c6d38  test    rcx, rcx
0x1800c6d3b  jz      short loc_1800C6D43
0x1800c6d3d  call    cs:__imp_RtlReleaseActivationContext
0x1800c6d43  mov     rcx, [rsp+6A8h+TargetHandle]; Handle
0x1800c6d4b  test    rcx, rcx
0x1800c6d4e  jnz     loc_1800C6FE3
0x1800c6d54  test    ebx, ebx
0x1800c6d56  js      loc_1800C6F6B
0x1800c6d5c  mov     rax, [rsp+6A8h+ThreadHandle]
0x1800c6d64  mov     rcx, [rsp+6A8h+var_48]
0x1800c6d6c  xor     rcx, rsp; StackCookie
0x1800c6d6f  call    __security_check_cookie
0x1800c6d74  add     rsp, 670h
0x1800c6d7b  pop     r15
0x1800c6d7d  pop     r14
0x1800c6d7f  pop     r13
0x1800c6d81  pop     r12
0x1800c6d83  pop     rdi
0x1800c6d84  pop     rsi
0x1800c6d85  pop     rbx
0x1800c6d86  retn
0x1800c6d87  mov     dword ptr [rsp+6A8h+var_558], 30h ; '0'
0x1800c6d92  mov     qword ptr [rsp+6A8h+var_558+8], rsi
0x1800c6d9a  mov     eax, [rbx+10h]
0x1800c6d9d  neg     eax
0x1800c6d9f  sbb     ecx, ecx
0x1800c6da1  and     ecx, 2
0x1800c6da4  mov     dword ptr [rsp+6A8h+var_548+8], ecx
0x1800c6dab  mov     qword ptr [rsp+6A8h+var_548], rsi
0x1800c6db3  mov     rax, [rbx+8]
0x1800c6db7  mov     [rsp+6A8h+var_538], rax
0x1800c6dbf  mov     [rsp+6A8h+var_530], rsi
0x1800c6dc7  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x1800c6dce  test    rax, rax
0x1800c6dd1  jz      short loc_1800C6DE0
0x1800c6dd3  lea     rcx, [rsp+6A8h+var_558]
0x1800c6ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6de0  lea     r12, [rsp+6A8h+var_558]
0x1800c6de8  jmp     loc_1800C69B2
0x1800c6ded  mov     [rsp+6A8h+var_5E8], 23h ; '#'
0x1800c6df8  lea     rax, [rsp+6A8h+var_5C8]
0x1800c6e00  mov     [rsp+6A8h+var_5F0], rax
0x1800c6e08  lea     rax, [rsp+6A8h+var_4B8]
0x1800c6e10  mov     [rsp+6A8h+var_5F8], rax
0x1800c6e18  mov     [rsp+6A8h+var_600], rsi
0x1800c6e20  mov     [rsp+6A8h+var_608], rsi
0x1800c6e28  mov     [rsp+6A8h+var_610], rsi
0x1800c6e30  mov     [rsp+6A8h+var_618], rsi
0x1800c6e38  mov     [rsp+6A8h+var_620], rsi
0x1800c6e40  mov     [rsp+6A8h+var_628], rsi
0x1800c6e48  mov     [rsp+6A8h+var_630], rsi
0x1800c6e4d  mov     [rsp+6A8h+var_638], rsi
0x1800c6e52  mov     [rsp+6A8h+var_640], rsi
0x1800c6e57  mov     [rsp+6A8h+var_648], rsi
0x1800c6e5c  mov     [rsp+6A8h+var_650], rsi
0x1800c6e61  mov     [rsp+6A8h+var_658], rsi
0x1800c6e66  mov     [rsp+6A8h+var_660], rsi
0x1800c6e6b  mov     [rsp+6A8h+var_668], rsi
0x1800c6e70  mov     [rsp+6A8h+var_670], rsi
0x1800c6e75  mov     [rsp+6A8h+pcbWrittenOrRequired], rsi
0x1800c6e7a  mov     [rsp+6A8h+cbBuffer], rsi
0x1800c6e7f  mov     [rsp+6A8h+pvBuffer], rsi
0x1800c6e84  xor     r9d, r9d
0x1800c6e87  lea     r8, [rsp+6A8h+var_5B8]
0x1800c6e8f  mov     dl, 1
0x1800c6e91  mov     rcx, rdi
0x1800c6e94  call    BasepConvertWin32AttributeList
0x1800c6e99  mov     [rsp+6A8h+var_5D4], eax
0x1800c6ea0  test    eax, eax
0x1800c6ea2  js      loc_1800C6FAB
0x1800c6ea8  mov     eax, [rsp+6A8h+var_5C8]
0x1800c6eaf  jmp     loc_1800C6A2E
0x1800c6eb4  mov     dword ptr [rsp+6A8h+pcbWrittenOrRequired], esi; Options
0x1800c6eb8  mov     dword ptr [rsp+6A8h+cbBuffer], esi; HandleAttributes
0x1800c6ebc  mov     dword ptr [rsp+6A8h+pvBuffer], 402h; DesiredAccess
0x1800c6ec4  lea     r9, [rsp+6A8h+TargetHandle]; TargetHandle
0x1800c6ecc  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
  ... truncated ...
```
