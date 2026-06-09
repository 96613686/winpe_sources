# CreateRemoteThreadEx

- ea: `0x1800ccdd0`
- end: `0x1800cd5e3`
- name: `CreateRemoteThreadEx`
- size: `2067`
- prototype: `HANDLE __stdcall(HANDLE hProcess, LPSECURITY_ATTRIBUTES lpThreadAttributes, SIZE_T dwStackSize, LPTHREAD_START_ROUTINE lpStartAddress, LPVOID lpParameter, DWORD dwCreationFlags, LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList, LPDWORD lpThreadId)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018ac30`
- `0x18018ac80`

## callees

- `0x1800393f0`
- `0x18004b9d0`
- `0x1800ccdd0`
- `0x1800cd5ec`
- `0x1800cedf0`
- `0x180136930`
- `0x1801369c9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlQueryInformationActivationContext` at `0x1800ccfe3`
- `ntdll!RtlQueryInformationActivationContext` at `0x1800ccfe3`
- `ntdll!RtlReleaseActivationContext` at `0x1800cd2af`
- `ntdll!RtlReleaseActivationContext` at `0x1800cd59a`
- `ntdll!RtlReleaseActivationContext` at `0x180197799`
- `ntdll!RtlReleaseActivationContext` at `0x1801977e6`
- `ntdll!RtlReleaseActivationContext` at `0x1800cd2af`
- `ntdll!RtlReleaseActivationContext` at `0x1800cd59a`
- `ntdll!RtlReleaseActivationContext` at `0x180197799`
- `ntdll!RtlReleaseActivationContext` at `0x1801977e6`
- `ntdll!NtClose` at `0x1800cd566`
- `ntdll!NtClose` at `0x1800cd578`
- `ntdll!NtClose` at `0x1800cd5d2`
- `ntdll!NtClose` at `0x1801977bb`
- `ntdll!NtClose` at `0x18019782d`
- `ntdll!NtClose` at `0x1800cd566`
- `ntdll!NtClose` at `0x1800cd578`
- `ntdll!NtClose` at `0x1800cd5d2`
- `ntdll!NtClose` at `0x1801977bb`
- `ntdll!NtClose` at `0x18019782d`
- `ntdll!NtQueryInformationProcess` at `0x1800cd481`
- `ntdll!NtQueryInformationProcess` at `0x1800cd4d2`
- `ntdll!NtQueryInformationProcess` at `0x1800cd481`
- `ntdll!NtQueryInformationProcess` at `0x1800cd4d2`
- `ntdll!NtDuplicateObject` at `0x1800cd452`
- `ntdll!NtDuplicateObject` at `0x1800cd452`
- `ntdll!NtCreateThreadEx` at `0x1800cd0aa`
- `ntdll!NtCreateThreadEx` at `0x1800cd0aa`
- `ntdll!RtlAllocateActivationContextStack` at `0x1800cd1e3`
- `ntdll!RtlAllocateActivationContextStack` at `0x1800cd1e3`
- `ntdll!RtlActivateActivationContextEx` at `0x1800cd234`
- `ntdll!RtlActivateActivationContextEx` at `0x1800cd234`
- `ntdll!NtResumeThread` at `0x1800cd1b0`
- `ntdll!NtResumeThread` at `0x1800cd1b0`
- `ntdll!RtlFreeActivationContextStack` at `0x1800cd5ab`
- `ntdll!RtlFreeActivationContextStack` at `0x1801977ff`
- `ntdll!RtlFreeActivationContextStack` at `0x1800cd5ab`
- `ntdll!RtlFreeActivationContextStack` at `0x1801977ff`
- `ntdll!NtTerminateThread` at `0x1800cd5be`
- `ntdll!NtTerminateThread` at `0x18019781a`
- `ntdll!NtTerminateThread` at `0x1800cd5be`
- `ntdll!NtTerminateThread` at `0x18019781a`

## string_xrefs

- `0x1800cd0f1`: `CreateRemoteThreadEx`
- `0x1800cd260`: `CreateRemoteThreadEx`
- `0x1800cd28d`: `CreateRemoteThreadEx`
- `0x1800cd0f8`: `SXS: %s - Failing thread create because RtlQueryInformationActivationContext() failed with status %08lx\n`
- `0x1800cd267`: `SXS: %s - Failing thread create because RtlActivateActivationContextEx() failed with status %08lx\n`
- `0x1800cd294`: `SXS: %s - Failing thread create because RtlAllocateActivationContextStack() failed with status %08lx\n`
- `0x1800cd156`: `CsrCreateRemoteThread`

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
  HANDLE ThreadHandle; // [rsp+D8h] [rbp-5B0h] BYREF
  unsigned int v30; // [rsp+E0h] [rbp-5A8h] BYREF
  HANDLE TargetHandle; // [rsp+E8h] [rbp-5A0h] BYREF
  int v32; // [rsp+F0h] [rbp-598h] BYREF
  PVOID Context[2]; // [rsp+F8h] [rbp-590h] BYREF
  PTEB Teb; // [rsp+108h] [rbp-580h] BYREF
  PACTIVATION_CONTEXT_STACK Stack; // [rsp+110h] [rbp-578h] BYREF
  ULONG SuspendCount; // [rsp+118h] [rbp-570h] BYREF
  unsigned __int64 Cookie; // [rsp+120h] [rbp-568h] BYREF
  SIZE_T v38; // [rsp+128h] [rbp-560h]
  LPVOID v39; // [rsp+130h] [rbp-558h]
  LPDWORD v40; // [rsp+138h] [rbp-550h]
  __int128 v41; // [rsp+140h] [rbp-548h] BYREF
  _BYTE v42[48]; // [rsp+150h] [rbp-538h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+180h] [rbp-508h] BYREF
  _BYTE v44[32]; // [rsp+1B0h] [rbp-4D8h] BYREF
  int v45; // [rsp+1D0h] [rbp-4B8h]
  _QWORD v46[138]; // [rsp+1F0h] [rbp-498h] BYREF

  Cookie = (unsigned __int64)lpStartAddress;
  v38 = dwStackSize;
  v39 = lpParameter;
  v40 = lpThreadId;
  *(_OWORD *)Context = 0;
  Stack = 0;
  v30 = 0;
  v41 = 0;
  memset_0(v46, 0, 0x448u);
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
    if ( byte_1803AAD44 || NtCurrentTeb()->SubProcessTag || Context[0] && ((__int64)Context[1] & 1) == 0 )
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
  if ( !byte_1803AAD44
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
0x1800ccdd0  push    rbx
0x1800ccdd2  push    rsi
0x1800ccdd3  push    rdi
0x1800ccdd4  push    r12
0x1800ccdd6  push    r13
0x1800ccdd8  push    r14
0x1800ccdda  push    r15
0x1800ccddc  sub     rsp, 650h
0x1800ccde3  mov     rax, cs:__security_cookie
0x1800ccdea  xor     rax, rsp
0x1800ccded  mov     [rsp+688h+var_48], rax
0x1800ccdf5  mov     [rsp+688h+Cookie], r9
0x1800ccdfd  mov     [rsp+688h+var_560], r8
0x1800cce05  mov     rbx, rdx
0x1800cce08  mov     r13, rcx
0x1800cce0b  mov     rax, [rsp+688h+lpParameter]
0x1800cce13  mov     [rsp+688h+var_558], rax
0x1800cce1b  mov     rdi, [rsp+688h+lpAttributeList]
0x1800cce23  mov     rax, [rsp+688h+lpThreadId]
0x1800cce2b  mov     [rsp+688h+var_550], rax
0x1800cce33  xorps   xmm0, xmm0
0x1800cce36  movups  xmmword ptr [rsp+688h+Context], xmm0
0x1800cce3e  xor     esi, esi
0x1800cce40  mov     [rsp+688h+Stack], rsi
0x1800cce48  mov     [rsp+688h+var_5A8], esi
0x1800cce4f  movups  [rsp+688h+var_548], xmm0
0x1800cce57  xor     edx, edx; Val
0x1800cce59  mov     r8d, 448h; Size
0x1800cce5f  lea     rcx, [rsp+688h+var_498]; void *
0x1800cce67  call    memset_0
0x1800cce6c  mov     [rsp+688h+ThreadHandle], rsi
0x1800cce74  mov     [rsp+688h+TargetHandle], rsi
0x1800cce7c  xor     eax, eax
0x1800cce7e  xorps   xmm0, xmm0
0x1800cce81  movups  [rsp+688h+var_538], xmm0
0x1800cce89  movups  [rsp+688h+var_528], xmm0
0x1800cce91  movups  [rsp+688h+var_528+0Ch], xmm0
0x1800cce99  mov     [rsp+688h+SuspendCount], esi
0x1800ccea0  xor     edx, edx; Val
0x1800ccea2  mov     r8d, 40h ; '@'; Size
0x1800ccea8  lea     rcx, [rsp+688h+var_4D8]; void *
0x1800cceb0  call    memset_0
0x1800cceb5  xor     eax, eax
0x1800cceb7  xorps   xmm0, xmm0
0x1800cceba  movups  [rsp+688h+ProcessInformation], xmm0
0x1800ccec2  movups  [rsp+688h+var_4F8], xmm0
0x1800cceca  movups  [rsp+688h+var_4F8+0Ch], xmm0
0x1800cced2  mov     [rsp+688h+Teb], rsi
0x1800cceda  mov     [rsp+688h+var_598], esi
0x1800ccee1  mov     r15d, [rsp+688h+dwCreationFlags]
0x1800ccee9  test    r15d, 0FFFEFFFBh
0x1800ccef0  jnz     loc_1800CD530
0x1800ccef6  test    rbx, rbx
0x1800ccef9  jnz     loc_1800CD300
0x1800cceff  mov     r12d, esi
0x1800ccf02  mov     [rsp+688h+var_5B4], esi
0x1800ccf09  mov     [rsp+688h+var_490], 10003h
0x1800ccf15  mov     [rsp+688h+var_488], 10h
0x1800ccf21  mov     [rsp+688h+var_478], rsi
0x1800ccf29  lea     rax, [rsp+688h+var_548]
0x1800ccf31  mov     [rsp+688h+var_480], rax
0x1800ccf39  mov     [rsp+688h+var_470], 10004h
0x1800ccf45  mov     [rsp+688h+var_468], 8
0x1800ccf51  mov     [rsp+688h+var_458], rsi
0x1800ccf59  lea     rax, [rsp+688h+Teb]
0x1800ccf61  mov     [rsp+688h+var_460], rax
0x1800ccf69  mov     eax, 2
0x1800ccf6e  mov     [rsp+688h+var_5A8], eax
0x1800ccf75  test    rdi, rdi
0x1800ccf78  jnz     loc_1800CD366
0x1800ccf7e  xor     r14b, r14b
0x1800ccf81  mov     [rsp+688h+var_5B8], r14b
0x1800ccf89  shl     rax, 5
0x1800ccf8d  add     rax, 8
0x1800ccf91  mov     [rsp+688h+var_498], rax
0x1800ccf99  mov     edi, r15d
0x1800ccf9c  and     edi, 10000h
0x1800ccfa2  mov     [rsp+688h+TargetHandle], rsi
0x1800ccfaa  mov     bl, 1
0x1800ccfac  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800ccfb0  jnz     loc_1800CD42D
0x1800ccfb6  test    bl, bl
0x1800ccfb8  jz      short loc_1800CD025
0x1800ccfba  mov     [rsp+688h+pcbWrittenOrRequired], rsi; pcbWrittenOrRequired
0x1800ccfbf  mov     [rsp+688h+cbBuffer], 10h; cbBuffer
0x1800ccfc8  lea     rax, [rsp+688h+Context]
0x1800ccfd0  mov     [rsp+688h+pvBuffer], rax; pvBuffer
0x1800ccfd5  mov     r9d, 1; ulInfoClass
0x1800ccfdb  xor     r8d, r8d; pvSubInstance
0x1800ccfde  xor     edx, edx; Context
0x1800ccfe0  mov     ecx, r9d; dwFlags
0x1800ccfe3  call    cs:__imp_RtlQueryInformationActivationContext
0x1800ccfea  nop     dword ptr [rax+rax+00h]
0x1800ccfef  mov     ebx, eax
0x1800ccff1  mov     [rsp+688h+var_5B4], eax
0x1800ccff8  test    eax, eax
0x1800ccffa  js      loc_1800CD0EE
0x1800cd000  cmp     cs:byte_1803AAD44, 0
0x1800cd007  jnz     short loc_1800CD032
0x1800cd009  mov     rax, gs:1720h
0x1800cd012  test    rax, rax
0x1800cd015  jnz     short loc_1800CD032
0x1800cd017  cmp     [rsp+688h+Context], rax
0x1800cd01f  jnz     loc_1800CD277
0x1800cd025  xor     sil, sil
0x1800cd028  test    r15b, 4
0x1800cd02c  jnz     short loc_1800CD035
0x1800cd02e  xor     edx, edx
0x1800cd030  jmp     short loc_1800CD03A
0x1800cd032  mov     sil, 1
0x1800cd035  mov     edx, 1
0x1800cd03a  mov     [rsp+688h+var_598], edx
0x1800cd041  xor     ecx, ecx
0x1800cd043  test    edi, edi
0x1800cd045  mov     r8, [rsp+688h+var_560]
0x1800cd04d  cmovnz  rcx, r8
0x1800cd051  xor     eax, eax
0x1800cd053  test    edi, edi
0x1800cd055  cmovnz  r8, rax
0x1800cd059  lea     rax, [rsp+688h+var_498]
0x1800cd061  mov     [rsp+688h+var_638], rax
0x1800cd066  mov     [rsp+688h+var_640], rcx
0x1800cd06b  mov     [rsp+688h+var_648], r8
0x1800cd070  mov     [rsp+688h+var_650], 0
0x1800cd079  mov     dword ptr [rsp+688h+pcbWrittenOrRequired], edx
0x1800cd07d  mov     rax, [rsp+688h+var_558]
0x1800cd085  mov     [rsp+688h+cbBuffer], rax
0x1800cd08a  mov     rax, [rsp+688h+Cookie]
0x1800cd092  mov     [rsp+688h+pvBuffer], rax
0x1800cd097  mov     r9, r13
0x1800cd09a  mov     r8, r12
0x1800cd09d  mov     edx, 1FFFFFh
0x1800cd0a2  lea     rcx, [rsp+688h+ThreadHandle]
0x1800cd0aa  call    cs:__imp_NtCreateThreadEx
0x1800cd0b1  nop     dword ptr [rax+rax+00h]
0x1800cd0b6  mov     ebx, eax
0x1800cd0b8  mov     [rsp+688h+var_5B4], eax
0x1800cd0bf  test    eax, eax
0x1800cd0c1  js      short loc_1800CD0E7
0x1800cd0c3  test    sil, sil
0x1800cd0c6  jnz     short loc_1800CD109
0x1800cd0c8  mov     rcx, [rsp+688h+var_550]
0x1800cd0d0  test    rcx, rcx
0x1800cd0d3  jz      short loc_1800CD0DE
0x1800cd0d5  mov     eax, dword ptr [rsp+688h+var_548+8]
0x1800cd0dc  mov     [rcx], eax
0x1800cd0de  test    sil, sil
0x1800cd0e1  jnz     loc_1800CD196
0x1800cd0e7  xor     esi, esi
0x1800cd0e9  jmp     loc_1800CD2A2
0x1800cd0ee  mov     r8d, eax
0x1800cd0f1  lea     rdx, aCreateremoteth_1; "CreateRemoteThreadEx"
0x1800cd0f8  lea     rcx, aSxsSFailingThr_1; "SXS: %s - Failing thread create because"...
0x1800cd0ff  call    DbgPrint_0
0x1800cd104  jmp     loc_1800CD2A2
0x1800cd109  mov     rax, gs:1720h
0x1800cd112  test    rax, rax
0x1800cd115  jz      short loc_1800CD12F
0x1800cd117  mov     rcx, gs:1720h
0x1800cd120  mov     rax, [rsp+688h+Teb]
0x1800cd128  mov     [rax+1720h], rcx
0x1800cd12f  cmp     [rsp+688h+Context], 0
0x1800cd138  jnz     loc_1800CD1C1
0x1800cd13e  cmp     cs:byte_1803AAD44, 0
0x1800cd145  jz      short loc_1800CD0C8
0x1800cd147  lea     rcx, aCsrsrv; "csrsrv"
0x1800cd14e  call    GetModuleHandleA
0x1800cd153  mov     rcx, rax; hModule
0x1800cd156  lea     rdx, aCsrcreateremot; "CsrCreateRemoteThread"
0x1800cd15d  call    GetProcAddress
0x1800cd162  test    rax, rax
0x1800cd165  jz      loc_1800CD0C8
0x1800cd16b  lea     rdx, [rsp+688h+var_548]
0x1800cd173  mov     rcx, [rsp+688h+ThreadHandle]
0x1800cd17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd180  mov     ebx, eax
0x1800cd182  mov     [rsp+688h+var_5B4], eax
0x1800cd189  test    eax, eax
0x1800cd18b  js      loc_1800CD0E7
0x1800cd191  jmp     loc_1800CD0C8
0x1800cd196  test    r15b, 4
0x1800cd19a  jnz     loc_1800CD0E7
0x1800cd1a0  lea     rdx, [rsp+688h+SuspendCount]; SuspendCount
0x1800cd1a8  mov     rcx, [rsp+688h+ThreadHandle]; ThreadHandle
0x1800cd1b0  call    cs:__imp_NtResumeThread
0x1800cd1b7  nop     dword ptr [rax+rax+00h]
0x1800cd1bc  jmp     loc_1800CD0E7
0x1800cd1c1  test    byte ptr [rsp+688h+Context+8], 1
0x1800cd1c9  jnz     loc_1800CD13E
0x1800cd1cf  mov     [rsp+688h+Cookie], 0
0x1800cd1db  lea     rcx, [rsp+688h+Stack]; Stack
0x1800cd1e3  call    cs:__imp_RtlAllocateActivationContextStack
0x1800cd1ea  nop     dword ptr [rax+rax+00h]
0x1800cd1ef  mov     ebx, eax
0x1800cd1f1  mov     [rsp+688h+var_5B4], eax
0x1800cd1f8  test    eax, eax
0x1800cd1fa  js      loc_1800CD28A
0x1800cd200  mov     rcx, [rsp+688h+Stack]
0x1800cd208  mov     rax, [rsp+688h+Teb]
0x1800cd210  mov     [rax+2C8h], rcx
0x1800cd217  lea     r9, [rsp+688h+Cookie]; Cookie
0x1800cd21f  mov     r8, [rsp+688h+Context]; Context
0x1800cd227  mov     rdx, [rsp+688h+Teb]; Teb
0x1800cd22f  mov     ecx, 1; Flags
0x1800cd234  call    cs:__imp_RtlActivateActivationContextEx
0x1800cd23b  nop     dword ptr [rax+rax+00h]
0x1800cd240  mov     ebx, eax
0x1800cd242  mov     [rsp+688h+var_5B4], eax
0x1800cd249  test    eax, eax
0x1800cd24b  js      short loc_1800CD25D
0x1800cd24d  mov     r14b, 1
0x1800cd250  mov     [rsp+688h+var_5B8], r14b
0x1800cd258  jmp     loc_1800CD13E
0x1800cd25d  mov     r8d, eax
0x1800cd260  lea     rdx, aCreateremoteth_1; "CreateRemoteThreadEx"
0x1800cd267  lea     rcx, aSxsSFailingThr; "SXS: %s - Failing thread create because"...
0x1800cd26e  call    DbgPrint_0
0x1800cd273  xor     esi, esi
0x1800cd275  jmp     short loc_1800CD2A2
0x1800cd277  test    byte ptr [rsp+688h+Context+8], 1
0x1800cd27f  jnz     loc_1800CD025
0x1800cd285  jmp     loc_1800CD032
0x1800cd28a  mov     r8d, eax
0x1800cd28d  lea     rdx, aCreateremoteth_1; "CreateRemoteThreadEx"
0x1800cd294  lea     rcx, aSxsSFailingThr_0; "SXS: %s - Failing thread create because"...
0x1800cd29b  call    DbgPrint_0
0x1800cd2a0  xor     esi, esi
0x1800cd2a2  mov     rcx, [rsp+688h+Context]; handle
0x1800cd2aa  test    rcx, rcx
0x1800cd2ad  jz      short loc_1800CD2BB
0x1800cd2af  call    cs:__imp_RtlReleaseActivationContext
0x1800cd2b6  nop     dword ptr [rax+rax+00h]
0x1800cd2bb  mov     rcx, [rsp+688h+TargetHandle]; Handle
0x1800cd2c3  test    rcx, rcx
0x1800cd2c6  jnz     loc_1800CD578
0x1800cd2cc  test    ebx, ebx
0x1800cd2ce  js      loc_1800CD4F6
0x1800cd2d4  mov     rax, [rsp+688h+ThreadHandle]
0x1800cd2dc  mov     rcx, [rsp+688h+var_48]
0x1800cd2e4  xor     rcx, rsp; StackCookie
0x1800cd2e7  call    __security_check_cookie
0x1800cd2ec  add     rsp, 650h
0x1800cd2f3  pop     r15
0x1800cd2f5  pop     r14
0x1800cd2f7  pop     r13
0x1800cd2f9  pop     r12
0x1800cd2fb  pop     rdi
0x1800cd2fc  pop     rsi
0x1800cd2fd  pop     rbx
0x1800cd2fe  retn
0x1800cd300  mov     dword ptr [rsp+688h+var_538], 30h ; '0'
0x1800cd30b  mov     qword ptr [rsp+688h+var_538+8], rsi
0x1800cd313  mov     eax, [rbx+10h]
0x1800cd316  neg     eax
0x1800cd318  sbb     ecx, ecx
0x1800cd31a  and     ecx, 2
0x1800cd31d  mov     dword ptr [rsp+688h+var_528+8], ecx
0x1800cd324  mov     qword ptr [rsp+688h+var_528], rsi
0x1800cd32c  mov     rax, [rbx+8]
0x1800cd330  mov     [rsp+688h+var_518], rax
0x1800cd338  mov     [rsp+688h+var_510], rsi
0x1800cd340  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x1800cd347  test    rax, rax
0x1800cd34a  jz      short loc_1800CD359
0x1800cd34c  lea     rcx, [rsp+688h+var_538]
0x1800cd354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd359  lea     r12, [rsp+688h+var_538]
0x1800cd361  jmp     loc_1800CCF02
0x1800cd366  mov     [rsp+688h+var_5C8], 22h ; '"'
0x1800cd371  lea     rax, [rsp+688h+var_5A8]
0x1800cd379  mov     [rsp+688h+var_5D0], rax
0x1800cd381  lea     rax, [rsp+688h+var_498]
0x1800cd389  mov     [rsp+688h+var_5D8], rax
0x1800cd391  mov     [rsp+688h+var_5E0], rsi
0x1800cd399  mov     [rsp+688h+var_5E8], rsi
0x1800cd3a1  mov     [rsp+688h+var_5F0], rsi
0x1800cd3a9  mov     [rsp+688h+var_5F8], rsi
0x1800cd3b1  mov     [rsp+688h+var_600], rsi
0x1800cd3b9  mov     [rsp+688h+var_608], rsi
0x1800cd3c1  mov     [rsp+688h+var_610], rsi
0x1800cd3c6  mov     [rsp+688h+var_618], rsi
0x1800cd3cb  mov     [rsp+688h+var_620], rsi
0x1800cd3d0  mov     [rsp+688h+var_628], rsi
0x1800cd3d5  mov     [rsp+688h+var_630], rsi
0x1800cd3da  mov     [rsp+688h+var_638], rsi
0x1800cd3df  mov     [rsp+688h+var_640], rsi
0x1800cd3e4  mov     [rsp+688h+var_648], rsi
0x1800cd3e9  mov     [rsp+688h+var_650], rsi
0x1800cd3ee  mov     [rsp+688h+pcbWrittenOrRequired], rsi
0x1800cd3f3  mov     [rsp+688h+cbBuffer], rsi
0x1800cd3f8  mov     [rsp+688h+pvBuffer], rsi
0x1800cd3fd  xor     r9d, r9d
0x1800cd400  lea     r8, [rsp+688h+var_598]
0x1800cd408  mov     dl, 1
0x1800cd40a  mov     rcx, rdi
0x1800cd40d  call    BasepConvertWin32AttributeList
0x1800cd412  mov     [rsp+688h+var_5B4], eax
0x1800cd419  test    eax, eax
0x1800cd41b  js      loc_1800CD53A
0x1800cd421  mov     eax, [rsp+688h+var_5A8]
  ... truncated ...
```
