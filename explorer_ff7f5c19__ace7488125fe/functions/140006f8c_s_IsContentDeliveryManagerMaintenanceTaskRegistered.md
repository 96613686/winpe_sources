# s_IsContentDeliveryManagerMaintenanceTaskRegistered

- ea: `0x140006f8c`
- end: `0x140007145`
- name: `s_IsContentDeliveryManagerMaintenanceTaskRegistered`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1401ab6d0`

## callees

- `0x140006edc`
- `0x140006f8c`
- `0x14000714c`
- `0x1401a21cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140006fe2`
- `ntdll!RtlInitUnicodeString` at `0x140006fe2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400070a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400070a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007108`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryWorkItem` at `0x140007065`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryWorkItem` at `0x140007065`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400070ca`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400070e8`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400070ca`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400070e8`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateWorkItemsForPackageName` at `0x140007010`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateWorkItemsForPackageName` at `0x140007010`

## string_xrefs

- `0x14000709d`: `ContentDeliveryManager.Background.MaintenanceTask`
- `0x140006fbc`: `shell\lib\logontasks\DesktopSpotlightLogonTaskHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall s_IsContentDeliveryManagerMaintenanceTaskRegistered(
        CallerIdentity *a1,
        __int64 a2,
        unsigned __int16 **a3)
{
  char v3; // di
  int SinglePackageFullNameFromPackageFamilyName; // eax
  int v5; // eax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int i; // esi
  int v9; // eax
  unsigned int v10; // r8d
  _DWORD *v11; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-48h]
  _DWORD *v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char v18; // [rsp+70h] [rbp+8h]
  unsigned int v20; // [rsp+78h] [rbp+10h] BYREF
  int v21; // [rsp+80h] [rbp+18h] BYREF
  PCWSTR SourceString; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    v3 = 0;
    v18 = 0;
    SourceString = 0;
    SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                   a1,
                                                   (const unsigned __int16 *)&SourceString,
                                                   a3);
    if ( SinglePackageFullNameFromPackageFamilyName < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"shell\\lib\\logontasks\\DesktopSpotlightLogonTaskHelper.h",
        (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
        bIgnoreCase);
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    v20 = 0;
    v15 = 0;
    v5 = BiPtEnumerateWorkItemsForPackageName(&DestinationString, 0, &v20, &v15);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x8B, v6, (const char *)(unsigned int)v5, bIgnoreCase);
    v21 = 0;
    for ( i = 0; i < v20; ++i )
    {
      v14 = 0;
      v9 = BiPtQueryWorkItem(v15 + 16LL * i, &v21, &v14);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x91, v10, (const char *)(unsigned int)v9, bIgnoreCase);
      v11 = v14;
      if ( !v14[10] )
      {
        if ( CompareStringOrdinal(
               (LPCWCH)((char *)v14 + (unsigned int)v14[18]),
               v14[19] >> 1,
               L"ContentDeliveryManager.Background.MaintenanceTask",
               -1,
               1) == 2 )
          v3 = 1;
        v18 = v3;
        v11 = v14;
      }
      if ( v11 )
        BiPtFreeMemory();
    }
    if ( v15 )
      BiPtFreeMemory();
    if ( SourceString )
      CoTaskMemFree((LPVOID)SourceString);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x9D,
      (unsigned int)"shell\\lib\\logontasks\\DesktopSpotlightLogonTaskHelper.h",
      v7);
    return v18;
  }
  return v3;
}

```

## disassembly

```asm
0x140006f8c  mov     rax, rsp
0x140006f8f  push    rsi
0x140006f90  push    rdi
0x140006f91  push    r15
0x140006f93  sub     rsp, 50h
0x140006f97  xor     dil, dil
0x140006f9a  mov     [rsp+68h+arg_0], dil
0x140006f9f  mov     qword ptr [rax+20h], 0
0x140006fa7  lea     rdx, [rax+20h]; unsigned __int16 *
0x140006fab  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x140006fb0  mov     rcx, [rsp+68h]; this
0x140006fb5  test    eax, eax
0x140006fb7  jns     short loc_140006FCD
0x140006fb9  mov     r9d, eax; char *
0x140006fbc  lea     r8, aShellLibLogont; "shell\\lib\\logontasks\\DesktopSpotligh"...
0x140006fc3  mov     edx, 84h; void *
0x140006fc8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140006fcd  xorps   xmm0, xmm0
0x140006fd0  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140006fd5  mov     rdx, [rsp+68h+SourceString]; SourceString
0x140006fdd  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140006fe2  call    cs:__imp_RtlInitUnicodeString
0x140006fe9  nop     dword ptr [rax+rax+00h]
0x140006fee  mov     [rsp+68h+arg_8], 0
0x140006ff6  mov     [rsp+68h+var_30], 0
0x140006fff  lea     r9, [rsp+68h+var_30]
0x140007004  lea     r8, [rsp+68h+arg_8]
0x140007009  xor     edx, edx
0x14000700b  lea     rcx, [rsp+68h+DestinationString]
0x140007010  call    cs:__imp_BiPtEnumerateWorkItemsForPackageName
0x140007017  nop     dword ptr [rax+rax+00h]
0x14000701c  mov     rcx, [rsp+68h]; this
0x140007021  test    eax, eax
0x140007023  js      loc_140007122
0x140007029  mov     [rsp+68h+arg_10], 0
0x140007034  xor     esi, esi
0x140007036  lea     r15d, [rsi+1]
0x14000703a  cmp     esi, [rsp+68h+arg_8]
0x14000703e  jnb     loc_1400070DE
0x140007044  mov     [rsp+68h+var_38], 0
0x14000704d  mov     ecx, esi
0x14000704f  shl     rcx, 4
0x140007053  add     rcx, [rsp+68h+var_30]
0x140007058  lea     r8, [rsp+68h+var_38]
0x14000705d  lea     rdx, [rsp+68h+arg_10]
0x140007065  call    cs:__imp_BiPtQueryWorkItem
0x14000706c  nop     dword ptr [rax+rax+00h]
0x140007071  mov     rcx, [rsp+68h]; this
0x140007076  test    eax, eax
0x140007078  js      loc_140007130
0x14000707e  mov     rcx, [rsp+68h+var_38]
0x140007083  cmp     dword ptr [rcx+28h], 0
0x140007087  jnz     short loc_1400070C5
0x140007089  mov     edx, [rcx+4Ch]
0x14000708c  shr     edx, 1; cchCount1
0x14000708e  mov     eax, [rcx+48h]
0x140007091  add     rcx, rax; lpString1
0x140007094  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x140007099  or      r9d, 0FFFFFFFFh; cchCount2
0x14000709d  lea     r8, ?c_ContentDeliveryManagerMaintenanceTask@Shared@CreativeFramework@@3QBGB; "ContentDeliveryManager.Background.Maint"...
0x1400070a4  call    cs:__imp_CompareStringOrdinal
0x1400070ab  nop     dword ptr [rax+rax+00h]
0x1400070b0  movzx   edi, dil
0x1400070b4  cmp     eax, 2
0x1400070b7  cmovz   edi, r15d
0x1400070bb  mov     [rsp+68h+arg_0], dil
0x1400070c0  mov     rcx, [rsp+68h+var_38]
0x1400070c5  test    rcx, rcx
0x1400070c8  jz      short loc_1400070D6
0x1400070ca  call    cs:__imp_BiPtFreeMemory
0x1400070d1  nop     dword ptr [rax+rax+00h]
0x1400070d6  add     esi, r15d
0x1400070d9  jmp     loc_14000703A
0x1400070de  mov     rcx, [rsp+68h+var_30]
0x1400070e3  test    rcx, rcx
0x1400070e6  jz      short loc_1400070F5
0x1400070e8  call    cs:__imp_BiPtFreeMemory
0x1400070ef  nop     dword ptr [rax+rax+00h]
0x1400070f4  nop
0x1400070f5  cmp     [rsp+68h+SourceString], 0
0x1400070fe  jz      short loc_140007115
0x140007100  mov     rcx, [rsp+68h+SourceString]; pv
0x140007108  call    cs:__imp_CoTaskMemFree
0x14000710f  nop     dword ptr [rax+rax+00h]
0x140007114  nop
0x140007115  mov     al, dil
0x140007118  add     rsp, 50h
0x14000711c  pop     r15
0x14000711e  pop     rdi
0x14000711f  pop     rsi
0x140007120  retn
0x140007122  mov     r9d, eax; char *
0x140007125  mov     edx, 8Bh; void *
0x14000712a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140007130  mov     r9d, eax; char *
0x140007133  mov     edx, 91h; void *
0x140007138  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14000713e  mov     dil, [rsp+68h+arg_0]
0x140007143  jmp     short loc_140007115
```
