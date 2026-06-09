# PESetInitialState

- ea: `0x180080888`
- end: `0x1800809e3`
- name: `PESetInitialState`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e5228`

## callees

- `0x18000ec28`
- `0x18002c0d0`
- `0x180080888`
- `0x180080d68`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x1800808c8`
- `ntoskrnl!EtwRegister` at `0x1800808c8`
- `ntoskrnl!ExInitializeResourceLite` at `0x180080904`
- `ntoskrnl!ExInitializeResourceLite` at `0x180080917`
- `ntoskrnl!ExInitializeResourceLite` at `0x180080904`
- `ntoskrnl!ExInitializeResourceLite` at `0x180080917`
- `ntoskrnl!EtwWrite` at `0x1800808f1`
- `ntoskrnl!EtwWrite` at `0x1800809c4`
- `ntoskrnl!EtwWrite` at `0x1800808f1`
- `ntoskrnl!EtwWrite` at `0x1800809c4`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080951`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080951`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18008092c`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18008092c`

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
0x180080888  push    rbp
0x18008088a  mov     rbp, rsp
0x18008088d  sub     rsp, 50h
0x180080891  mov     rax, cs:__security_cookie
0x180080898  xor     rax, rsp
0x18008089b  mov     [rbp+var_8], rax
0x18008089f  mov     [rbp+var_1C], 0
0x1800808a6  call    I_PEConfigOptions
0x1800808ab  mov     eax, cs:g_PEAuthConfigOptions
0x1800808b1  test    al, 1
0x1800808b3  jz      short loc_1800808FD
0x1800808b5  lea     r9, g_PEAuthEtwHandle; RegHandle
0x1800808bc  xor     r8d, r8d; CallbackContext
0x1800808bf  xor     edx, edx; EnableCallback
0x1800808c1  lea     rcx, PEAUTH_EVENT_GUID; ProviderId
0x1800808c8  call    cs:__imp_EtwRegister
0x1800808cf  nop     dword ptr [rax+rax+00h]
0x1800808d4  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800808db  lea     rdx, PEAUTH_BEGIN_INITIALIZATION; EventDescriptor
0x1800808e2  xor     r9d, r9d; UserDataCount
0x1800808e5  mov     [rsp+50h+UserData], 0; UserData
0x1800808ee  xor     r8d, r8d; ActivityId
0x1800808f1  call    cs:__imp_EtwWrite
0x1800808f8  nop     dword ptr [rax+rax+00h]
0x1800808fd  lea     rcx, g_GRLContextLock; Resource
0x180080904  call    cs:__imp_ExInitializeResourceLite
0x18008090b  nop     dword ptr [rax+rax+00h]
0x180080910  lea     rcx, g_HashCacheLock; Resource
0x180080917  call    cs:__imp_ExInitializeResourceLite
0x18008091e  nop     dword ptr [rax+rax+00h]
0x180080923  xor     edx, edx; Remove
0x180080925  lea     rcx, I_PEProcessNotify; NotifyRoutine
0x18008092c  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x180080933  nop     dword ptr [rax+rax+00h]
0x180080938  xor     eax, eax
0x18008093a  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18008093e  xor     r9d, r9d; ReturnLength
0x180080941  mov     [rbp+SystemInformation], ax
0x180080945  mov     ecx, 95h; SystemInformationClass
0x18008094a  mov     [rbp+var_1E], al
0x18008094d  lea     r8d, [rax+3]; SystemInformationLength
0x180080951  call    cs:__imp_ZwQuerySystemInformation
0x180080958  nop     dword ptr [rax+rax+00h]
0x18008095d  test    eax, eax
0x18008095f  movzx   eax, byte ptr [rbp+SystemInformation]
0x180080963  jns     short loc_18008096A
0x180080965  mov     eax, 1
0x18008096a  xor     ecx, ecx
0x18008096c  test    eax, eax
0x18008096e  setnz   cl
0x180080971  or      [rbp+var_1C], ecx
0x180080974  jz      short loc_18008098A
0x180080976  xor     edx, edx
0x180080978  lea     ecx, [rdx+1]
0x18008097b  call    PEAuthStoreParameter
0x180080980  mov     cs:g_PEAuthStateVariables, 0
0x18008098a  mov     eax, cs:g_PEAuthConfigOptions
0x180080990  test    al, 1
0x180080992  jz      short loc_1800809D0
0x180080994  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18008099b  lea     rax, [rbp+var_1C]
0x18008099f  mov     [rbp+var_18.Ptr], rax
0x1800809a3  lea     rdx, PEAUTH_END_INITIALIZATION; EventDescriptor
0x1800809aa  lea     rax, [rbp+var_18]
0x1800809ae  mov     qword ptr [rbp+var_18.Size], 4
0x1800809b6  mov     r9d, 1; UserDataCount
0x1800809bc  mov     [rsp+50h+UserData], rax; UserData
0x1800809c1  xor     r8d, r8d; ActivityId
0x1800809c4  call    cs:__imp_EtwWrite
0x1800809cb  nop     dword ptr [rax+rax+00h]
0x1800809d0  mov     rcx, [rbp+var_8]
0x1800809d4  xor     rcx, rsp; StackCookie
0x1800809d7  call    __security_check_cookie
0x1800809dc  add     rsp, 50h
0x1800809e0  pop     rbp
0x1800809e1  retn
```
