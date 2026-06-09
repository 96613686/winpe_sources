# s_IsContentDeliveryManagerMaintenanceTaskRegistered

- ea: `0x1400193bc`
- end: `0x14001954a`
- name: `s_IsContentDeliveryManagerMaintenanceTaskRegistered`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1401ab400`

## callees

- `0x140019308`
- `0x1400193bc`
- `0x140019550`
- `0x14019ffd4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140019412`
- `ntdll!RtlInitUnicodeString` at `0x140019412`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400194c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400194c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019514`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryWorkItem` at `0x140019489`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryWorkItem` at `0x140019489`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateWorkItemsForPackageName` at `0x14001943a`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateWorkItemsForPackageName` at `0x14001943a`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400194e2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400194fa`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400194e2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1400194fa`

## string_xrefs

- `0x1400194bb`: `ContentDeliveryManager.Background.MaintenanceTask`
- `0x1400193ec`: `shell\lib\logontasks\DesktopSpotlightLogonTaskHelper.h`

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
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
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
0x1400193bc  mov     rax, rsp
0x1400193bf  push    rsi
0x1400193c0  push    rdi
0x1400193c1  push    r15
0x1400193c3  sub     rsp, 50h
0x1400193c7  xor     dil, dil
0x1400193ca  mov     [rsp+68h+arg_0], dil
0x1400193cf  mov     qword ptr [rax+20h], 0
0x1400193d7  lea     rdx, [rax+20h]; unsigned __int16 *
0x1400193db  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x1400193e0  mov     rcx, [rsp+68h]; this
0x1400193e5  test    eax, eax
0x1400193e7  jns     short loc_1400193FD
0x1400193e9  mov     r9d, eax; char *
0x1400193ec  lea     r8, aShellLibLogont; "shell\\lib\\logontasks\\DesktopSpotligh"...
0x1400193f3  mov     edx, 84h; void *
0x1400193f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400193fd  xorps   xmm0, xmm0
0x140019400  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140019405  mov     rdx, [rsp+68h+SourceString]; SourceString
0x14001940d  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140019412  call    cs:__imp_RtlInitUnicodeString
0x140019418  mov     [rsp+68h+arg_8], 0
0x140019420  mov     [rsp+68h+var_30], 0
0x140019429  lea     r9, [rsp+68h+var_30]
0x14001942e  lea     r8, [rsp+68h+arg_8]
0x140019433  xor     edx, edx
0x140019435  lea     rcx, [rsp+68h+DestinationString]
0x14001943a  call    cs:__imp_BiPtEnumerateWorkItemsForPackageName
0x140019440  mov     rcx, [rsp+68h]; this
0x140019445  test    eax, eax
0x140019447  js      loc_140019527
0x14001944d  mov     [rsp+68h+arg_10], 0
0x140019458  xor     esi, esi
0x14001945a  lea     r15d, [rsi+1]
0x14001945e  cmp     esi, [rsp+68h+arg_8]
0x140019462  jnb     loc_1400194F0
0x140019468  mov     [rsp+68h+var_38], 0
0x140019471  mov     ecx, esi
0x140019473  shl     rcx, 4
0x140019477  add     rcx, [rsp+68h+var_30]
0x14001947c  lea     r8, [rsp+68h+var_38]
0x140019481  lea     rdx, [rsp+68h+arg_10]
0x140019489  call    cs:__imp_BiPtQueryWorkItem
0x14001948f  mov     rcx, [rsp+68h]; this
0x140019494  test    eax, eax
0x140019496  js      loc_140019535
0x14001949c  mov     rcx, [rsp+68h+var_38]
0x1400194a1  cmp     dword ptr [rcx+28h], 0
0x1400194a5  jnz     short loc_1400194DD
0x1400194a7  mov     edx, [rcx+4Ch]
0x1400194aa  shr     edx, 1; cchCount1
0x1400194ac  mov     eax, [rcx+48h]
0x1400194af  add     rcx, rax; lpString1
0x1400194b2  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1400194b7  or      r9d, 0FFFFFFFFh; cchCount2
0x1400194bb  lea     r8, ?c_ContentDeliveryManagerMaintenanceTask@Shared@CreativeFramework@@3QBGB; "ContentDeliveryManager.Background.Maint"...
0x1400194c2  call    cs:__imp_CompareStringOrdinal
0x1400194c8  movzx   edi, dil
0x1400194cc  cmp     eax, 2
0x1400194cf  cmovz   edi, r15d
0x1400194d3  mov     [rsp+68h+arg_0], dil
0x1400194d8  mov     rcx, [rsp+68h+var_38]
0x1400194dd  test    rcx, rcx
0x1400194e0  jz      short loc_1400194E8
0x1400194e2  call    cs:__imp_BiPtFreeMemory
0x1400194e8  add     esi, r15d
0x1400194eb  jmp     loc_14001945E
0x1400194f0  mov     rcx, [rsp+68h+var_30]
0x1400194f5  test    rcx, rcx
0x1400194f8  jz      short loc_140019501
0x1400194fa  call    cs:__imp_BiPtFreeMemory
0x140019500  nop
0x140019501  cmp     [rsp+68h+SourceString], 0
0x14001950a  jz      short loc_14001951B
0x14001950c  mov     rcx, [rsp+68h+SourceString]; pv
0x140019514  call    cs:__imp_CoTaskMemFree
0x14001951a  nop
0x14001951b  mov     al, dil
0x14001951e  add     rsp, 50h
0x140019522  pop     r15
0x140019524  pop     rdi
0x140019525  pop     rsi
0x140019526  retn
0x140019527  mov     r9d, eax; char *
0x14001952a  mov     edx, 8Bh; void *
0x14001952f  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140019535  mov     r9d, eax; char *
0x140019538  mov     edx, 91h; void *
0x14001953d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140019543  mov     dil, [rsp+68h+arg_0]
0x140019548  jmp     short loc_14001951B
```
