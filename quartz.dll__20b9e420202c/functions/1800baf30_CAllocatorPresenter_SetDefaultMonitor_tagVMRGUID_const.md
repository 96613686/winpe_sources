# CAllocatorPresenter::SetDefaultMonitor(tagVMRGUID const *)

- ea: `0x1800baf30`
- end: `0x1800bb094`
- name: `?SetDefaultMonitor@CAllocatorPresenter@@UEAAJPEBUtagVMRGUID@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CAllocatorPresenter *__hidden this, const struct tagVMRGUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800ba8c0`
- `0x1800baf30`
- `0x1800bb1a4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800bb01c`
- `KERNEL32!LeaveCriticalSection` at `0x1800bb078`
- `KERNEL32!LeaveCriticalSection` at `0x1800bb01c`
- `KERNEL32!LeaveCriticalSection` at `0x1800bb078`
- `KERNEL32!EnterCriticalSection` at `0x1800baf49`
- `KERNEL32!EnterCriticalSection` at `0x1800baf49`
- `ADVAPI32!RegDeleteValueW` at `0x1800baff2`
- `ADVAPI32!RegDeleteValueW` at `0x1800baff2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800bafcf`
- `ADVAPI32!RegOpenKeyExW` at `0x1800bafcf`
- `ADVAPI32!RegCloseKey` at `0x1800bb009`
- `ADVAPI32!RegCloseKey` at `0x1800bb009`
- `ole32!StringFromCLSID` at `0x1800bb046`
- `ole32!StringFromCLSID` at `0x1800bb046`
- `ole32!CoTaskMemFree` at `0x1800bb069`
- `ole32!CoTaskMemFree` at `0x1800bb069`

## pseudocode

```c
__int64 __fastcall CAllocatorPresenter::SetDefaultMonitor(CAllocatorPresenter *this, const struct tagVMRGUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HRESULT v5; // ebx
  GUID *pGUID; // rbx
  __int64 v7; // rax
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  LSTATUS v10; // eax
  const unsigned __int16 *v11; // rdx
  HKEY v12; // rcx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp+10h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !a2 )
  {
    v5 = -2147467261;
LABEL_19:
    LeaveCriticalSection(v2);
    return (unsigned int)v5;
  }
  pGUID = a2->pGUID;
  if ( a2->pGUID )
  {
    v7 = *(_QWORD *)&a2->GUID.Data1 - *(_QWORD *)&pGUID->Data1;
    if ( !v7 )
      v7 = *(_QWORD *)a2->GUID.Data4 - *(_QWORD *)pGUID->Data4;
    if ( v7 )
      goto LABEL_8;
  }
  if ( (unsigned int)CMonitorArray::MatchGUID(
                       (CAllocatorPresenter *)((char *)this + 48),
                       a2->pGUID,
                       (unsigned int *)&hKey) == 1 )
  {
LABEL_8:
    v5 = -2147024809;
    goto LABEL_19;
  }
  if ( pGUID )
  {
    lpsz = 0;
    v5 = StringFromCLSID(&a2->GUID, &lpsz);
    if ( v5 >= 0 )
    {
      v5 = SetRegistryString(v12, v11, lpsz);
      CoTaskMemFree(lpsz);
    }
    goto LABEL_19;
  }
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Multimedia\\ActiveMovie Filters\\Video Mixing Renderer",
         0,
         2u,
         &hKey);
  v9 = v8;
  if ( v8 == 2 )
    goto LABEL_16;
  if ( !v8 )
  {
    v10 = RegDeleteValueW(hKey, L"DDraw Connection Device GUID");
    if ( v10 != 2 )
      v9 = v10;
    RegCloseKey(hKey);
    if ( !v9 )
    {
LABEL_16:
      v5 = 0;
      goto LABEL_19;
    }
  }
  LeaveCriticalSection(v2);
  return v9 | 0x80070000;
}

```

## disassembly

```asm
0x1800baf30  mov     [rsp+arg_10], rbx
0x1800baf35  push    rbp
0x1800baf36  push    rsi
0x1800baf37  push    rdi
0x1800baf38  sub     rsp, 30h
0x1800baf3c  lea     rdi, [rcx+8]
0x1800baf40  mov     rbp, rcx
0x1800baf43  mov     rcx, rdi; lpCriticalSection
0x1800baf46  mov     rsi, rdx
0x1800baf49  call    cs:__imp_EnterCriticalSection
0x1800baf50  nop     dword ptr [rax+rax+00h]
0x1800baf55  test    rsi, rsi
0x1800baf58  jnz     short loc_1800BAF64
0x1800baf5a  mov     ebx, 80004003h
0x1800baf5f  jmp     loc_1800BB075
0x1800baf64  mov     rbx, [rsi]
0x1800baf67  test    rbx, rbx
0x1800baf6a  jz      short loc_1800BAF82
0x1800baf6c  mov     rax, [rsi+8]
0x1800baf70  sub     rax, [rbx]
0x1800baf73  jnz     short loc_1800BAF7D
0x1800baf75  mov     rax, [rsi+10h]
0x1800baf79  sub     rax, [rbx+8]
0x1800baf7d  test    rax, rax
0x1800baf80  jnz     short loc_1800BAF98
0x1800baf82  lea     rcx, [rbp+30h]; this
0x1800baf86  mov     rdx, rbx; struct _GUID *
0x1800baf89  lea     r8, [rsp+48h+hKey]; unsigned int *
0x1800baf8e  call    ?MatchGUID@CMonitorArray@@QEAAJPEBU_GUID@@PEAK@Z; CMonitorArray::MatchGUID(_GUID const *,ulong *)
0x1800baf93  cmp     eax, 1
0x1800baf96  jnz     short loc_1800BAFA2
0x1800baf98  mov     ebx, 80070057h
0x1800baf9d  jmp     loc_1800BB075
0x1800bafa2  test    rbx, rbx
0x1800bafa5  jnz     loc_1800BB034
0x1800bafab  lea     rax, [rsp+48h+hKey]
0x1800bafb0  mov     [rsp+48h+hKey], rbx
0x1800bafb5  lea     r9d, [rbx+2]; samDesired
0x1800bafb9  mov     [rsp+48h+phkResult], rax; phkResult
0x1800bafbe  xor     r8d, r8d; ulOptions
0x1800bafc1  lea     rdx, chRegistryKey; "Software\\Microsoft\\Multimedia\\Active"...
0x1800bafc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bafcf  call    cs:__imp_RegOpenKeyExW
0x1800bafd6  nop     dword ptr [rax+rax+00h]
0x1800bafdb  mov     ebx, eax
0x1800bafdd  cmp     eax, 2
0x1800bafe0  jz      short loc_1800BB030
0x1800bafe2  test    eax, eax
0x1800bafe4  jnz     short loc_1800BB019
0x1800bafe6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800bafeb  lea     rdx, aDdrawConnectio; "DDraw Connection Device GUID"
0x1800baff2  call    cs:__imp_RegDeleteValueW
0x1800baff9  nop     dword ptr [rax+rax+00h]
0x1800baffe  mov     rcx, [rsp+48h+hKey]; hKey
0x1800bb003  cmp     eax, 2
0x1800bb006  cmovnz  ebx, eax
0x1800bb009  call    cs:__imp_RegCloseKey
0x1800bb010  nop     dword ptr [rax+rax+00h]
0x1800bb015  test    ebx, ebx
0x1800bb017  jz      short loc_1800BB030
0x1800bb019  mov     rcx, rdi; lpCriticalSection
0x1800bb01c  call    cs:__imp_LeaveCriticalSection
0x1800bb023  nop     dword ptr [rax+rax+00h]
0x1800bb028  or      ebx, 80070000h
0x1800bb02e  jmp     short loc_1800BB084
0x1800bb030  xor     ebx, ebx
0x1800bb032  jmp     short loc_1800BB075
0x1800bb034  lea     rdx, [rsp+48h+lpsz]; lplpsz
0x1800bb039  mov     [rsp+48h+lpsz], 0
0x1800bb042  lea     rcx, [rsi+8]; rclsid
0x1800bb046  call    cs:__imp_StringFromCLSID
0x1800bb04d  nop     dword ptr [rax+rax+00h]
0x1800bb052  mov     ebx, eax
0x1800bb054  test    eax, eax
0x1800bb056  js      short loc_1800BB075
0x1800bb058  mov     r8, [rsp+48h+lpsz]; unsigned __int16 *
0x1800bb05d  call    ?SetRegistryString@@YAJPEAUHKEY__@@PEBG1@Z; SetRegistryString(HKEY__ *,ushort const *,ushort const *)
0x1800bb062  mov     rcx, [rsp+48h+lpsz]; pv
0x1800bb067  mov     ebx, eax
0x1800bb069  call    cs:__imp_CoTaskMemFree
0x1800bb070  nop     dword ptr [rax+rax+00h]
0x1800bb075  mov     rcx, rdi; lpCriticalSection
0x1800bb078  call    cs:__imp_LeaveCriticalSection
0x1800bb07f  nop     dword ptr [rax+rax+00h]
0x1800bb084  mov     eax, ebx
0x1800bb086  mov     rbx, [rsp+48h+arg_10]
0x1800bb08b  add     rsp, 30h
0x1800bb08f  pop     rdi
0x1800bb090  pop     rsi
0x1800bb091  pop     rbp
0x1800bb092  retn
```
