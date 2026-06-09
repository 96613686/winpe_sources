# PESetInitialState

- ea: `0x18007e848`
- end: `0x18007e9a3`
- name: `PESetInitialState`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e4cb8`

## callees

- `0x18000ec18`
- `0x18002bef0`
- `0x18007e848`
- `0x18007ed28`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x18007e888`
- `ntoskrnl!EtwRegister` at `0x18007e888`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007e8c4`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007e8d7`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007e8c4`
- `ntoskrnl!ExInitializeResourceLite` at `0x18007e8d7`
- `ntoskrnl!EtwWrite` at `0x18007e8b1`
- `ntoskrnl!EtwWrite` at `0x18007e984`
- `ntoskrnl!EtwWrite` at `0x18007e8b1`
- `ntoskrnl!EtwWrite` at `0x18007e984`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007e911`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007e911`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18007e8ec`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18007e8ec`

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
0x18007e848  push    rbp
0x18007e84a  mov     rbp, rsp
0x18007e84d  sub     rsp, 50h
0x18007e851  mov     rax, cs:__security_cookie
0x18007e858  xor     rax, rsp
0x18007e85b  mov     [rbp+var_8], rax
0x18007e85f  mov     [rbp+var_1C], 0
0x18007e866  call    I_PEConfigOptions
0x18007e86b  mov     eax, cs:g_PEAuthConfigOptions
0x18007e871  test    al, 1
0x18007e873  jz      short loc_18007E8BD
0x18007e875  lea     r9, g_PEAuthEtwHandle; RegHandle
0x18007e87c  xor     r8d, r8d; CallbackContext
0x18007e87f  xor     edx, edx; EnableCallback
0x18007e881  lea     rcx, PEAUTH_EVENT_GUID; ProviderId
0x18007e888  call    cs:__imp_EtwRegister
0x18007e88f  nop     dword ptr [rax+rax+00h]
0x18007e894  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18007e89b  lea     rdx, PEAUTH_BEGIN_INITIALIZATION; EventDescriptor
0x18007e8a2  xor     r9d, r9d; UserDataCount
0x18007e8a5  mov     [rsp+50h+UserData], 0; UserData
0x18007e8ae  xor     r8d, r8d; ActivityId
0x18007e8b1  call    cs:__imp_EtwWrite
0x18007e8b8  nop     dword ptr [rax+rax+00h]
0x18007e8bd  lea     rcx, g_GRLContextLock; Resource
0x18007e8c4  call    cs:__imp_ExInitializeResourceLite
0x18007e8cb  nop     dword ptr [rax+rax+00h]
0x18007e8d0  lea     rcx, g_HashCacheLock; Resource
0x18007e8d7  call    cs:__imp_ExInitializeResourceLite
0x18007e8de  nop     dword ptr [rax+rax+00h]
0x18007e8e3  xor     edx, edx; Remove
0x18007e8e5  lea     rcx, I_PEProcessNotify; NotifyRoutine
0x18007e8ec  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x18007e8f3  nop     dword ptr [rax+rax+00h]
0x18007e8f8  xor     eax, eax
0x18007e8fa  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18007e8fe  xor     r9d, r9d; ReturnLength
0x18007e901  mov     [rbp+SystemInformation], ax
0x18007e905  mov     ecx, 95h; SystemInformationClass
0x18007e90a  mov     [rbp+var_1E], al
0x18007e90d  lea     r8d, [rax+3]; SystemInformationLength
0x18007e911  call    cs:__imp_ZwQuerySystemInformation
0x18007e918  nop     dword ptr [rax+rax+00h]
0x18007e91d  test    eax, eax
0x18007e91f  movzx   eax, byte ptr [rbp+SystemInformation]
0x18007e923  jns     short loc_18007E92A
0x18007e925  mov     eax, 1
0x18007e92a  xor     ecx, ecx
0x18007e92c  test    eax, eax
0x18007e92e  setnz   cl
0x18007e931  or      [rbp+var_1C], ecx
0x18007e934  jz      short loc_18007E94A
0x18007e936  xor     edx, edx
0x18007e938  lea     ecx, [rdx+1]
0x18007e93b  call    PEAuthStoreParameter
0x18007e940  mov     cs:g_PEAuthStateVariables, 0
0x18007e94a  mov     eax, cs:g_PEAuthConfigOptions
0x18007e950  test    al, 1
0x18007e952  jz      short loc_18007E990
0x18007e954  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18007e95b  lea     rax, [rbp+var_1C]
0x18007e95f  mov     [rbp+var_18.Ptr], rax
0x18007e963  lea     rdx, PEAUTH_END_INITIALIZATION; EventDescriptor
0x18007e96a  lea     rax, [rbp+var_18]
0x18007e96e  mov     qword ptr [rbp+var_18.Size], 4
0x18007e976  mov     r9d, 1; UserDataCount
0x18007e97c  mov     [rsp+50h+UserData], rax; UserData
0x18007e981  xor     r8d, r8d; ActivityId
0x18007e984  call    cs:__imp_EtwWrite
0x18007e98b  nop     dword ptr [rax+rax+00h]
0x18007e990  mov     rcx, [rbp+var_8]
0x18007e994  xor     rcx, rsp; StackCookie
0x18007e997  call    __security_check_cookie
0x18007e99c  add     rsp, 50h
0x18007e9a0  pop     rbp
0x18007e9a1  retn
```
