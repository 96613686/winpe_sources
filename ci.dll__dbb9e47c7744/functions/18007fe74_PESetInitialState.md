# PESetInitialState

- ea: `0x18007fe74`
- end: `0x18007ffcf`
- name: `PESetInitialState`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e4ca8`

## callees

- `0x18000ec18`
- `0x18002bf20`
- `0x18007fe74`
- `0x180080354`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x18007feb4`
- `ntoskrnl!EtwRegister` at `0x18007feb4`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007fef0`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007ff03`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007fef0`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007ff03`
- `ntoskrnl!EtwWrite` at `0x18007fedd`
- `ntoskrnl!EtwWrite` at `0x18007ffb0`
- `ntoskrnl!EtwWrite` at `0x18007fedd`
- `ntoskrnl!EtwWrite` at `0x18007ffb0`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007ff3d`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007ff3d`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18007ff18`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18007ff18`

## pseudocode

```c
NTSTATUS PESetInitialState()
{
  bool v0; // sf
  int v1; // eax
  NTSTATUS result; // eax
  __int16 SystemInformation; // [rsp+30h] [rbp-20h] BYREF
  char v4; // [rsp+32h] [rbp-1Eh]
  int v5; // [rsp+34h] [rbp-1Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-18h] BYREF

  v5 = 0;
  I_PEConfigOptions();
  if ( (g_PEAuthConfigOptions & 1) != 0 )
  {
    EtwRegister(&PEAUTH_EVENT_GUID, 0, 0, &g_PEAuthEtwHandle);
    EtwWrite(g_PEAuthEtwHandle, &PEAUTH_BEGIN_INITIALIZATION, 0, 0, 0);
  }
  ExInitializeResourceLite(&g_GRLContextLock);
  ExInitializeResourceLite(&g_HashCacheLock);
  PsSetCreateProcessNotifyRoutine(I_PEProcessNotify, 0);
  SystemInformation = 0;
  v4 = 0;
  v0 = ZwQuerySystemInformation(SystemFileCacheInformation|0x80, &SystemInformation, 3u, 0) < 0;
  v1 = (unsigned __int8)SystemInformation;
  if ( v0 )
    v1 = 1;
  v5 |= v1 != 0;
  if ( v5 )
  {
    PEAuthStoreParameter(1, 0);
    g_PEAuthStateVariables = 0;
  }
  result = g_PEAuthConfigOptions;
  if ( (g_PEAuthConfigOptions & 1) != 0 )
  {
    UserData.Ptr = (ULONGLONG)&v5;
    *(_QWORD *)&UserData.Size = 4;
    return EtwWrite(g_PEAuthEtwHandle, &PEAUTH_END_INITIALIZATION, 0, 1u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18007fe74  push    rbp
0x18007fe76  mov     rbp, rsp
0x18007fe79  sub     rsp, 50h
0x18007fe7d  mov     rax, cs:__security_cookie
0x18007fe84  xor     rax, rsp
0x18007fe87  mov     [rbp+var_8], rax
0x18007fe8b  mov     [rbp+var_1C], 0
0x18007fe92  call    I_PEConfigOptions
0x18007fe97  mov     eax, cs:g_PEAuthConfigOptions
0x18007fe9d  test    al, 1
0x18007fe9f  jz      short loc_18007FEE9
0x18007fea1  lea     r9, g_PEAuthEtwHandle; RegHandle
0x18007fea8  xor     r8d, r8d; CallbackContext
0x18007feab  xor     edx, edx; EnableCallback
0x18007fead  lea     rcx, PEAUTH_EVENT_GUID; ProviderId
0x18007feb4  call    cs:__imp_EtwRegister
0x18007febb  nop     dword ptr [rax+rax+00h]
0x18007fec0  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18007fec7  lea     rdx, PEAUTH_BEGIN_INITIALIZATION; EventDescriptor
0x18007fece  xor     r9d, r9d; UserDataCount
0x18007fed1  mov     [rsp+50h+UserData], 0; UserData
0x18007feda  xor     r8d, r8d; ActivityId
0x18007fedd  call    cs:__imp_EtwWrite
0x18007fee4  nop     dword ptr [rax+rax+00h]
0x18007fee9  lea     rcx, g_GRLContextLock; Resource
0x18007fef0  call    cs:__imp_ExInitializeResourceLite
0x18007fef7  nop     dword ptr [rax+rax+00h]
0x18007fefc  lea     rcx, g_HashCacheLock; Resource
0x18007ff03  call    cs:__imp_ExInitializeResourceLite
0x18007ff0a  nop     dword ptr [rax+rax+00h]
0x18007ff0f  xor     edx, edx; Remove
0x18007ff11  lea     rcx, I_PEProcessNotify; NotifyRoutine
0x18007ff18  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x18007ff1f  nop     dword ptr [rax+rax+00h]
0x18007ff24  xor     eax, eax
0x18007ff26  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18007ff2a  xor     r9d, r9d; ReturnLength
0x18007ff2d  mov     [rbp+SystemInformation], ax
0x18007ff31  mov     ecx, 95h; SystemInformationClass
0x18007ff36  mov     [rbp+var_1E], al
0x18007ff39  lea     r8d, [rax+3]; SystemInformationLength
0x18007ff3d  call    cs:__imp_ZwQuerySystemInformation
0x18007ff44  nop     dword ptr [rax+rax+00h]
0x18007ff49  test    eax, eax
0x18007ff4b  movzx   eax, byte ptr [rbp+SystemInformation]
0x18007ff4f  jns     short loc_18007FF56
0x18007ff51  mov     eax, 1
0x18007ff56  xor     ecx, ecx
0x18007ff58  test    eax, eax
0x18007ff5a  setnz   cl
0x18007ff5d  or      [rbp+var_1C], ecx
0x18007ff60  jz      short loc_18007FF76
0x18007ff62  xor     edx, edx
0x18007ff64  lea     ecx, [rdx+1]
0x18007ff67  call    PEAuthStoreParameter
0x18007ff6c  mov     cs:g_PEAuthStateVariables, 0
0x18007ff76  mov     eax, cs:g_PEAuthConfigOptions
0x18007ff7c  test    al, 1
0x18007ff7e  jz      short loc_18007FFBC
0x18007ff80  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18007ff87  lea     rax, [rbp+var_1C]
0x18007ff8b  mov     [rbp+var_18.Ptr], rax
0x18007ff8f  lea     rdx, PEAUTH_END_INITIALIZATION; EventDescriptor
0x18007ff96  lea     rax, [rbp+var_18]
0x18007ff9a  mov     qword ptr [rbp+var_18.Size], 4
0x18007ffa2  mov     r9d, 1; UserDataCount
0x18007ffa8  mov     [rsp+50h+UserData], rax; UserData
0x18007ffad  xor     r8d, r8d; ActivityId
0x18007ffb0  call    cs:__imp_EtwWrite
0x18007ffb7  nop     dword ptr [rax+rax+00h]
0x18007ffbc  mov     rcx, [rbp+var_8]
0x18007ffc0  xor     rcx, rsp; StackCookie
0x18007ffc3  call    __security_check_cookie
0x18007ffc8  add     rsp, 50h
0x18007ffcc  pop     rbp
0x18007ffcd  retn
```
