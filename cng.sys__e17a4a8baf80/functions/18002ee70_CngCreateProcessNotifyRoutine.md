# CngCreateProcessNotifyRoutine

- ea: `0x18002ee70`
- end: `0x18002eefc`
- name: `CngCreateProcessNotifyRoutine`
- size: `140`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18002ee70`
- `0x18002ef10`
- `0x18002effc`
- `0x180067578`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18002eebf`
- `ntoskrnl!ObfDereferenceObject` at `0x18002eebf`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x18002ee8e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x18002ee8e`

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
0x18002ee70  test    r8b, r8b
0x18002ee73  jnz     short locret_18002EED0
0x18002ee75  push    rbx
0x18002ee76  sub     rsp, 20h
0x18002ee7a  mov     rax, rdx
0x18002ee7d  mov     [rsp+28h+Process], 0
0x18002ee86  mov     rcx, rax; ProcessId
0x18002ee89  lea     rdx, [rsp+28h+Process]; Process
0x18002ee8e  call    cs:__imp_PsLookupProcessByProcessId
0x18002ee95  nop     dword ptr [rax+rax+00h]
0x18002ee9a  mov     r9d, eax
0x18002ee9d  test    eax, eax
0x18002ee9f  js      short loc_18002EED2
0x18002eea1  mov     rbx, [rsp+28h+Process]
0x18002eea6  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x18002eeab  mov     rdx, rbx
0x18002eeae  mov     rcx, [rax+108h]; Resource
0x18002eeb5  call    CcnCancelSubscriptionProcess
0x18002eeba  mov     rcx, [rsp+28h+Process]; Object
0x18002eebf  call    cs:__imp_ObfDereferenceObject
0x18002eec6  nop     dword ptr [rax+rax+00h]
0x18002eecb  add     rsp, 20h
0x18002eecf  pop     rbx
0x18002eed0  retn
0x18002eed2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eed9  lea     rax, WPP_GLOBAL_Control
0x18002eee0  cmp     rcx, rax
0x18002eee3  jz      short loc_18002EECB
0x18002eee5  mov     eax, [rcx+2Ch]
0x18002eee8  test    al, 2
0x18002eeea  jz      short loc_18002EECB
0x18002eeec  mov     rcx, [rcx+18h]
0x18002eef0  mov     edx, 0Bh
0x18002eef5  call    WPP_SF_D
0x18002eefa  jmp     short loc_18002EECB
```
