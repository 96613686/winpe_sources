# OmaDmAbortSession_Impl

- ea: `0x180014a60`
- end: `0x180014b15`
- name: `OmaDmAbortSession_Impl`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800148f0`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x18000c974`
- `0x180014a60`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180014abe`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180014abe`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180014aef`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180014aef`

## pseudocode

```c
__int64 __fastcall OmaDmAbortSession_Impl(__int64 a1)
{
  __int64 v2; // rcx
  int AccountRootKeyByInitiationId; // ebx
  __int64 v4; // rcx
  const unsigned __int16 *v5; // r8
  unsigned int v6; // r9d
  const unsigned __int16 *v7; // rdx
  char IsStateSeparationEnabled; // al
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  hObject = 0;
  AccountRootKeyByInitiationId = AcquireOmaDmMutex(&hObject);
  if ( AccountRootKeyByInitiationId >= 0 )
  {
    if ( !a1 )
    {
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v2);
      v7 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
      if ( !IsStateSeparationEnabled )
        v7 = L"Software\\Microsoft\\Provisioning\\OMADM";
      v5 = L"SessionModelessUIActive";
      v6 = 0;
      v4 = -2147483646;
      goto LABEL_8;
    }
    v10 = 0;
    AccountRootKeyByInitiationId = GetAccountRootKeyByInitiationId(a1, (__int64)&v10);
    if ( AccountRootKeyByInitiationId >= 0 )
    {
      v4 = v10;
      v5 = L"SessionAbort";
      v6 = 1;
      v7 = (const unsigned __int16 *)a1;
LABEL_8:
      AccountRootKeyByInitiationId = OmaDmRegistrySetDWORD((HKEY)v4, v7, v5, v6);
    }
  }
  ReleaseOmaDmMutex(hObject);
  return (unsigned int)AccountRootKeyByInitiationId;
}

```

## disassembly

```asm
0x180014a60  mov     [rsp+arg_0], rbx
0x180014a65  push    rdi
0x180014a66  sub     rsp, 20h
0x180014a6a  mov     rdi, rcx
0x180014a6d  mov     [rsp+28h+hObject], 0
0x180014a76  lea     rcx, [rsp+28h+hObject]; void **
0x180014a7b  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x180014a80  mov     ebx, eax
0x180014a82  test    eax, eax
0x180014a84  js      short loc_180014AFD
0x180014a86  test    rdi, rdi
0x180014a89  jz      short loc_180014ABE
0x180014a8b  lea     rdx, [rsp+28h+arg_8]
0x180014a90  mov     [rsp+28h+arg_8], 0
0x180014a99  mov     rcx, rdi
0x180014a9c  call    GetAccountRootKeyByInitiationId
0x180014aa1  mov     ebx, eax
0x180014aa3  test    eax, eax
0x180014aa5  js      short loc_180014AFD
0x180014aa7  mov     rcx, [rsp+28h+arg_8]
0x180014aac  lea     r8, aSessionabort; "SessionAbort"
0x180014ab3  mov     r9d, 1
0x180014ab9  mov     rdx, rdi
0x180014abc  jmp     short loc_180014AEF
0x180014abe  call    cs:__imp_RtlIsStateSeparationEnabled
0x180014ac5  nop     dword ptr [rax+rax+00h]
0x180014aca  test    al, al
0x180014acc  lea     rcx, aSoftwareMicros_6; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180014ad3  lea     rdx, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\Provisioni"...
0x180014ada  cmovz   rdx, rcx
0x180014ade  lea     r8, aSessionmodeles; "SessionModelessUIActive"
0x180014ae5  xor     r9d, r9d
0x180014ae8  mov     rcx, 0FFFFFFFF80000002h
0x180014aef  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180014af6  nop     dword ptr [rax+rax+00h]
0x180014afb  mov     ebx, eax
0x180014afd  mov     rcx, [rsp+28h+hObject]; hObject
0x180014b02  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x180014b07  mov     eax, ebx
0x180014b09  mov     rbx, [rsp+28h+arg_0]
0x180014b0e  add     rsp, 20h
0x180014b12  pop     rdi
0x180014b13  retn
```
