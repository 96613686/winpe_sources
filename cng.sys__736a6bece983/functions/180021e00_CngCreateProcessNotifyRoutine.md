# CngCreateProcessNotifyRoutine

- ea: `0x180021e00`
- end: `0x180021e8c`
- name: `CngCreateProcessNotifyRoutine`
- size: `140`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180021e00`
- `0x180021ea0`
- `0x180021f8c`
- `0x18005dc98`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180021e4f`
- `ntoskrnl!ObfDereferenceObject` at `0x180021e4f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x180021e1e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x180021e1e`

## pseudocode

```c
void __fastcall CngCreateProcessNotifyRoutine(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)
{
  NTSTATUS v3; // eax
  __int64 v4; // r8
  struct _CNG_CONFIG_CONTEXT *ConfigContext; // rax
  PEPROCESS Process; // [rsp+48h] [rbp+20h] BYREF

  if ( !Create )
  {
    Process = 0;
    v3 = PsLookupProcessByProcessId(ProcessId, &Process);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, v4, (unsigned int)v3);
    }
    else
    {
      ConfigContext = CfgGetConfigContext();
      CcnCancelSubscriptionProcess(*((PERESOURCE *)ConfigContext + 33));
      ObfDereferenceObject(Process);
    }
  }
}

```

## disassembly

```asm
0x180021e00  test    r8b, r8b
0x180021e03  jnz     short locret_180021E60
0x180021e05  push    rbx
0x180021e06  sub     rsp, 20h
0x180021e0a  mov     rax, rdx
0x180021e0d  mov     [rsp+28h+Process], 0
0x180021e16  mov     rcx, rax; ProcessId
0x180021e19  lea     rdx, [rsp+28h+Process]; Process
0x180021e1e  call    cs:__imp_PsLookupProcessByProcessId
0x180021e25  nop     dword ptr [rax+rax+00h]
0x180021e2a  mov     r9d, eax
0x180021e2d  test    eax, eax
0x180021e2f  js      short loc_180021E62
0x180021e31  mov     rbx, [rsp+28h+Process]
0x180021e36  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x180021e3b  mov     rdx, rbx
0x180021e3e  mov     rcx, [rax+108h]; Resource
0x180021e45  call    CcnCancelSubscriptionProcess
0x180021e4a  mov     rcx, [rsp+28h+Process]; Object
0x180021e4f  call    cs:__imp_ObfDereferenceObject
0x180021e56  nop     dword ptr [rax+rax+00h]
0x180021e5b  add     rsp, 20h
0x180021e5f  pop     rbx
0x180021e60  retn
0x180021e62  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e69  lea     rax, WPP_GLOBAL_Control
0x180021e70  cmp     rcx, rax
0x180021e73  jz      short loc_180021E5B
0x180021e75  mov     eax, [rcx+2Ch]
0x180021e78  test    al, 2
0x180021e7a  jz      short loc_180021E5B
0x180021e7c  mov     rcx, [rcx+18h]
0x180021e80  mov     edx, 0Bh
0x180021e85  call    WPP_SF_D
0x180021e8a  jmp     short loc_180021E5B
```
