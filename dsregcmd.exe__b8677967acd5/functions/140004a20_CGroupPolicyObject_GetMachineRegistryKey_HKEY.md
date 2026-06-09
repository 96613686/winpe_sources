# CGroupPolicyObject::GetMachineRegistryKey(HKEY__ * *)

- ea: `0x140004a20`
- end: `0x140004b0e`
- name: `?GetMachineRegistryKey@CGroupPolicyObject@@UEAAJPEAPEAUHKEY__@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CGroupPolicyObject *__hidden this, HKEY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x140004a20`
- `0x140004f90`
- `0x140005004`
- `0x14000507c`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004add`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004add`

## string_xrefs

- `0x140004a32`: `CGroupPolicyObject::GetRegistryKey`
- `0x140004abf`: `IGroupPolicyObject::GetRegistryKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGroupPolicyObject::GetMachineRegistryKey(CGroupPolicyObject *this, HKEY *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int v6; // eax

  Logger::TraceVerbose(L"%s started", L"CGroupPolicyObject::GetRegistryKey");
  if ( a2 )
  {
    *a2 = 0;
    v5 = *((_QWORD *)this + 1);
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v5 + 120LL))(v5, 2, a2);
      v4 = v6;
      if ( v6 >= 0 )
        goto LABEL_9;
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"CGroupPolicyObject::GetRegistryKey",
        L"IGroupPolicyObject::GetRegistryKey",
        (unsigned int)v6);
    }
    else
    {
      Logger::TraceError(L"%s: Group policy object is not initialized.", L"CGroupPolicyObject::GetRegistryKey");
      v4 = -2147024890;
    }
    if ( *a2 )
    {
      RegCloseKey(*a2);
      *a2 = 0;
    }
  }
  else
  {
    v4 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CGroupPolicyObject::GetRegistryKey", L"phKey");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CGroupPolicyObject::GetRegistryKey", L"phKey");
  }
LABEL_9:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"CGroupPolicyObject::GetRegistryKey", v4);
  return v4;
}

```

## disassembly

```asm
0x140004a20  mov     [rsp+arg_0], rbx
0x140004a25  mov     [rsp+arg_8], rsi
0x140004a2a  push    rdi
0x140004a2b  sub     rsp, 20h
0x140004a2f  mov     rdi, rdx
0x140004a32  lea     rsi, aCgrouppolicyob_1; "CGroupPolicyObject::GetRegistryKey"
0x140004a39  mov     rbx, rcx
0x140004a3c  mov     rdx, rsi
0x140004a3f  lea     rcx, aSStarted; "%s started"
0x140004a46  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x140004a4b  test    rdi, rdi
0x140004a4e  jnz     short loc_140004A7C
0x140004a50  lea     r8, aPhkey; "phKey"
0x140004a57  mov     rdx, rsi
0x140004a5a  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x140004a61  mov     ebx, 80070057h
0x140004a66  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x140004a6b  lea     rdx, aPhkey; "phKey"
0x140004a72  mov     rcx, rsi; unsigned __int16 *
0x140004a75  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x140004a7a  jmp     short loc_140004AEA
0x140004a7c  mov     qword ptr [rdi], 0
0x140004a83  mov     rcx, [rbx+8]
0x140004a87  test    rcx, rcx
0x140004a8a  jnz     short loc_140004AA2
0x140004a8c  mov     rdx, rsi
0x140004a8f  lea     rcx, aSGroupPolicyOb; "%s: Group policy object is not initiali"...
0x140004a96  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x140004a9b  mov     ebx, 80070006h
0x140004aa0  jmp     short loc_140004AD5
0x140004aa2  mov     rax, [rcx]
0x140004aa5  mov     r8, rdi
0x140004aa8  mov     edx, 2
0x140004aad  mov     rax, [rax+78h]
0x140004ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ab6  mov     ebx, eax
0x140004ab8  test    eax, eax
0x140004aba  jns     short loc_140004AEA
0x140004abc  mov     r9d, eax
0x140004abf  lea     r8, aIgrouppolicyob; "IGroupPolicyObject::GetRegistryKey"
0x140004ac6  mov     rdx, rsi
0x140004ac9  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x."
0x140004ad0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x140004ad5  mov     rcx, [rdi]; hKey
0x140004ad8  test    rcx, rcx
0x140004adb  jz      short loc_140004AEA
0x140004add  call    cs:__imp_RegCloseKey
0x140004ae3  mov     qword ptr [rdi], 0
0x140004aea  mov     r8d, ebx
0x140004aed  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x140004af4  mov     rdx, rsi
0x140004af7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x140004afc  mov     rsi, [rsp+28h+arg_8]
0x140004b01  mov     eax, ebx
0x140004b03  mov     rbx, [rsp+28h+arg_0]
0x140004b08  add     rsp, 20h
0x140004b0c  pop     rdi
0x140004b0d  retn
```
