# CWmiProvider::_CreateObjectFromClassName(ushort const *,UstCommon::CWmiObject * *)

- ea: `0x180025de0`
- end: `0x180025ee1`
- name: `?_CreateObjectFromClassName@CWmiProvider@@AEAAJPEBGPEAPEAVCWmiObject@UstCommon@@@Z`
- size: `257`
- prototype: `int(CWmiProvider *__hidden this, const unsigned __int16 *, struct UstCommon::CWmiObject **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025700`

## callees

- `0x180014068`
- `0x1800140c8`
- `0x18002337c`
- `0x180023484`
- `0x180025de0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025e17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025e57`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025e17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025e57`

## string_xrefs

- `0x180025e41`: `Win32_OfflineFilesMachineConfiguration`
- `0x180025dfe`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CWmiProvider::_CreateObjectFromClassName(
        CWmiProvider *this,
        const unsigned __int16 *a2,
        struct UstCommon::CWmiObject **a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx

  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Win32_OfflineFilesUserConfiguration", -1) == 2 )
  {
    v6 = UstCommon::CWmiCreator<COfflineFilesUserConfiguration>::CreateInstance<UstCommon::CWmiObject>(v5, a3);
LABEL_3:
    v7 = v6;
LABEL_9:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Win32_OfflineFilesMachineConfiguration", -1) == 2 )
  {
    v6 = UstCommon::CWmiCreator<COfflineFilesMachineConfiguration>::CreateInstance<UstCommon::CWmiObject>(v8, a3);
    goto LABEL_3;
  }
  v9 = WPP_GLOBAL_Control;
  v7 = -2147217392;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, a2);
    goto LABEL_9;
  }
LABEL_10:
  if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_DWORD *)(v9 + 28) & 0x4000000) != 0 )
    WPP_SF_SD(*(_QWORD *)(v9 + 16), 28, (unsigned int)WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, (_DWORD)a2, v7);
  return v7;
}

```

## disassembly

```asm
0x180025de0  mov     [rsp+arg_0], rbx
0x180025de5  mov     [rsp+arg_8], rbp
0x180025dea  push    rdi
0x180025deb  sub     rsp, 30h
0x180025def  or      r9d, 0FFFFFFFFh; cchCount1
0x180025df3  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180025dfb  mov     rbx, r8
0x180025dfe  lea     rax, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x180025e05  mov     rdi, rdx
0x180025e08  mov     [rsp+38h+lpString2], rax; lpString2
0x180025e0d  mov     r8, rdx; lpString1
0x180025e10  lea     edx, [r9+2]; dwCmpFlags
0x180025e14  lea     ecx, [rdx+7Eh]; Locale
0x180025e17  call    cs:__imp_CompareStringW
0x180025e1d  lea     rbp, WPP_GLOBAL_Control
0x180025e24  cmp     eax, 2
0x180025e27  jnz     short loc_180025E35
0x180025e29  mov     rdx, rbx
0x180025e2c  call    ??$CreateInstance@VCWmiObject@UstCommon@@@?$CWmiCreator@VCOfflineFilesUserConfiguration@@@UstCommon@@SAJPEAXPEAPEAVCWmiObject@1@@Z; UstCommon::CWmiCreator<COfflineFilesUserConfiguration>::CreateInstance<UstCommon::CWmiObject>(void *,UstCommon::CWmiObject * *)
0x180025e31  mov     ebx, eax
0x180025e33  jmp     short loc_180025E9E
0x180025e35  or      r9d, 0FFFFFFFFh; cchCount1
0x180025e39  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180025e41  lea     rax, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x180025e48  mov     r8, rdi; lpString1
0x180025e4b  mov     [rsp+38h+lpString2], rax; lpString2
0x180025e50  lea     edx, [r9+2]; dwCmpFlags
0x180025e54  lea     ecx, [rdx+7Eh]; Locale
0x180025e57  call    cs:__imp_CompareStringW
0x180025e5d  cmp     eax, 2
0x180025e60  jnz     short loc_180025E6C
0x180025e62  mov     rdx, rbx
0x180025e65  call    ??$CreateInstance@VCWmiObject@UstCommon@@@?$CWmiCreator@VCOfflineFilesMachineConfiguration@@@UstCommon@@SAJPEAXPEAPEAVCWmiObject@1@@Z; UstCommon::CWmiCreator<COfflineFilesMachineConfiguration>::CreateInstance<UstCommon::CWmiObject>(void *,UstCommon::CWmiObject * *)
0x180025e6a  jmp     short loc_180025E31
0x180025e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e73  mov     ebx, 80041010h
0x180025e78  cmp     rcx, rbp
0x180025e7b  jz      short loc_180025ECF
0x180025e7d  test    dword ptr [rcx+1Ch], 4000000h
0x180025e84  jz      short loc_180025EA5
0x180025e86  mov     rcx, [rcx+10h]
0x180025e8a  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180025e91  mov     edx, 1Bh
0x180025e96  mov     r9, rdi
0x180025e99  call    WPP_SF_S
0x180025e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ea5  cmp     rcx, rbp
0x180025ea8  jz      short loc_180025ECF
0x180025eaa  test    dword ptr [rcx+1Ch], 4000000h
0x180025eb1  jz      short loc_180025ECF
0x180025eb3  mov     rcx, [rcx+10h]
0x180025eb7  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180025ebe  mov     edx, 1Ch
0x180025ec3  mov     dword ptr [rsp+38h+lpString2], ebx
0x180025ec7  mov     r9, rdi
0x180025eca  call    WPP_SF_SD
0x180025ecf  mov     rbp, [rsp+38h+arg_8]
0x180025ed4  mov     eax, ebx
0x180025ed6  mov     rbx, [rsp+38h+arg_0]
0x180025edb  add     rsp, 30h
0x180025edf  pop     rdi
0x180025ee0  retn
```
