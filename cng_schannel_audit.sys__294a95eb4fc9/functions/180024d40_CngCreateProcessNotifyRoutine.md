# CngCreateProcessNotifyRoutine

- ea: `0x180024d40`
- end: `0x180024dcc`
- name: `CngCreateProcessNotifyRoutine`
- size: `140`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180024d40`
- `0x180024de0`
- `0x180024ecc`
- `0x18005d3a8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180024d8f`
- `ntoskrnl!ObfDereferenceObject` at `0x180024d8f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x180024d5e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x180024d5e`

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
0x180024d40  test    r8b, r8b
0x180024d43  jnz     short locret_180024DA0
0x180024d45  push    rbx
0x180024d46  sub     rsp, 20h
0x180024d4a  mov     rax, rdx
0x180024d4d  mov     [rsp+28h+Process], 0
0x180024d56  mov     rcx, rax; ProcessId
0x180024d59  lea     rdx, [rsp+28h+Process]; Process
0x180024d5e  call    cs:__imp_PsLookupProcessByProcessId
0x180024d65  nop     dword ptr [rax+rax+00h]
0x180024d6a  mov     r9d, eax
0x180024d6d  test    eax, eax
0x180024d6f  js      short loc_180024DA2
0x180024d71  mov     rbx, [rsp+28h+Process]
0x180024d76  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x180024d7b  mov     rdx, rbx
0x180024d7e  mov     rcx, [rax+108h]; Resource
0x180024d85  call    CcnCancelSubscriptionProcess
0x180024d8a  mov     rcx, [rsp+28h+Process]; Object
0x180024d8f  call    cs:__imp_ObfDereferenceObject
0x180024d96  nop     dword ptr [rax+rax+00h]
0x180024d9b  add     rsp, 20h
0x180024d9f  pop     rbx
0x180024da0  retn
0x180024da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180024da9  lea     rax, WPP_GLOBAL_Control
0x180024db0  cmp     rcx, rax
0x180024db3  jz      short loc_180024D9B
0x180024db5  mov     eax, [rcx+2Ch]
0x180024db8  test    al, 2
0x180024dba  jz      short loc_180024D9B
0x180024dbc  mov     rcx, [rcx+18h]
0x180024dc0  mov     edx, 0Bh
0x180024dc5  call    WPP_SF_D
0x180024dca  jmp     short loc_180024D9B
```
