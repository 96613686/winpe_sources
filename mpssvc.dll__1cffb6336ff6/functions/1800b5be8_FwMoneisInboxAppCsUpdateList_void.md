# FwMoneisInboxAppCsUpdateList(void *)

- ea: `0x1800b5be8`
- end: `0x1800b5da9`
- name: `?FwMoneisInboxAppCsUpdateList@@YAKPEAX@Z`
- size: `449`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b5890`

## callees

- `0x18000ae9c`
- `0x18000af3c`
- `0x180069bb4`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800b5be8`
- `0x1800bd870`

## import_xrefs

- `fwbase!FwRegSetString` at `0x1800b5d3e`
- `fwbase!FwRegSetString` at `0x1800b5d3e`
- `fwbase!FwHResultToWindowsError` at `0x1800b5cfa`
- `fwbase!FwHResultToWindowsError` at `0x1800b5d46`
- `fwbase!FwHResultToWindowsError` at `0x1800b5cfa`
- `fwbase!FwHResultToWindowsError` at `0x1800b5d46`
- `fwbase!FwFree` at `0x1800b5d88`
- `fwbase!FwFree` at `0x1800b5d88`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800b5cf2`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800b5cf2`

## string_xrefs

- `0x1800b5c28`: `ACService`
- `0x1800b5c79`: `FwMoneisInboxAppCsUpdateList::StringCchPrintf`

## pseudocode

```c
__int64 __fastcall FwMoneisInboxAppCsUpdateList(void *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned int updated; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-228h] BYREF

  v10 = 0;
  memset_0(v11, 0, 0x208u);
  v2 = StringCchPrintfW(v11, 0x104u, L"%ls\\%ls", *((_QWORD *)gFwIsolationManager + 13), L"ACService");
  if ( v2 >= 0 )
  {
    updated = appIsolation::InboxAppContainerManager::InboxAppCsUpdateList(gInboxAppContainerManager, a1);
    v3 = updated;
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_18;
      v6 = 201;
    }
    else
    {
      v7 = FwSidsToString(
             *((unsigned int *)gInboxAppContainerManager + 14),
             *((_QWORD *)gInboxAppContainerManager + 6),
             &v10);
      updated = FwHResultToWindowsError(v7);
      v3 = updated;
      if ( updated )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_18;
        v6 = 202;
      }
      else
      {
        v8 = FwRegSetString(-2147483646, v11, L"KnownApps", v10);
        updated = FwHResultToWindowsError(v8);
        v3 = updated;
        if ( !updated )
          goto LABEL_18;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_18;
        v6 = 203;
      }
    }
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, updated);
    goto LABEL_18;
  }
  v3 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_Ds(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      200,
      (unsigned int)WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
      v2,
      (__int64)"FwMoneisInboxAppCsUpdateList::StringCchPrintf");
LABEL_18:
  FwFree(v10);
  return v3;
}

```

## disassembly

```asm
0x1800b5be8  push    rbx
0x1800b5bea  sub     rsp, 260h
0x1800b5bf1  mov     rax, cs:__security_cookie
0x1800b5bf8  xor     rax, rsp
0x1800b5bfb  mov     [rsp+268h+var_18], rax
0x1800b5c03  mov     rbx, rcx
0x1800b5c06  mov     [rsp+268h+var_238], 0
0x1800b5c0f  lea     rcx, [rsp+268h+var_228]; void *
0x1800b5c14  xor     edx, edx; Val
0x1800b5c16  mov     r8d, 208h; Size
0x1800b5c1c  call    memset_0
0x1800b5c21  mov     r9, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b5c28  lea     rax, aAcservice; "ACService"
0x1800b5c2f  lea     r8, aLsLs; "%ls\\%ls"
0x1800b5c36  mov     [rsp+268h+var_248], rax
0x1800b5c3b  mov     edx, 104h; unsigned __int64
0x1800b5c40  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800b5c45  mov     r9, [r9+68h]
0x1800b5c49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b5c4e  test    eax, eax
0x1800b5c50  jns     short loc_1800B5C9E
0x1800b5c52  xor     ebx, ebx
0x1800b5c54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5c5b  lea     rdx, WPP_GLOBAL_Control
0x1800b5c62  cmp     rcx, rdx
0x1800b5c65  jz      loc_1800B5D83
0x1800b5c6b  test    byte ptr [rcx+1Ch], 1
0x1800b5c6f  jz      loc_1800B5D83
0x1800b5c75  mov     rcx, [rcx+10h]
0x1800b5c79  lea     r8, aFwmoneisinboxa_1; "FwMoneisInboxAppCsUpdateList::StringCch"...
0x1800b5c80  mov     [rsp+268h+var_248], r8
0x1800b5c85  mov     edx, 0C8h
0x1800b5c8a  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b5c91  mov     r9d, eax
0x1800b5c94  call    WPP_SF_Ds
0x1800b5c99  jmp     loc_1800B5D83
0x1800b5c9e  mov     rcx, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; this
0x1800b5ca5  mov     rdx, rbx; void *
0x1800b5ca8  call    ?InboxAppCsUpdateList@InboxAppContainerManager@appIsolation@@QEAAKPEAX@Z; appIsolation::InboxAppContainerManager::InboxAppCsUpdateList(void *)
0x1800b5cad  mov     ebx, eax
0x1800b5caf  test    eax, eax
0x1800b5cb1  jz      short loc_1800B5CDE
0x1800b5cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5cba  lea     rdx, WPP_GLOBAL_Control
0x1800b5cc1  cmp     rcx, rdx
0x1800b5cc4  jz      loc_1800B5D83
0x1800b5cca  test    byte ptr [rcx+1Ch], 1
0x1800b5cce  jz      loc_1800B5D83
0x1800b5cd4  mov     edx, 0C9h
0x1800b5cd9  jmp     loc_1800B5D70
0x1800b5cde  mov     rax, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::InboxAppContainerManager,wistd::default_delete<appIsolation::InboxAppContainerManager>> gInboxAppContainerManager
0x1800b5ce5  lea     r8, [rsp+268h+var_238]
0x1800b5cea  mov     rdx, [rax+30h]
0x1800b5cee  mov     ecx, [rax+38h]
0x1800b5cf1  nop
0x1800b5cf2  call    cs:__imp_FwSidsToString
0x1800b5cf8  mov     ecx, eax
0x1800b5cfa  call    cs:__imp_FwHResultToWindowsError
0x1800b5d00  mov     ebx, eax
0x1800b5d02  test    eax, eax
0x1800b5d04  jz      short loc_1800B5D26
0x1800b5d06  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5d0d  lea     rdx, WPP_GLOBAL_Control
0x1800b5d14  cmp     rcx, rdx
0x1800b5d17  jz      short loc_1800B5D83
0x1800b5d19  test    byte ptr [rcx+1Ch], 1
0x1800b5d1d  jz      short loc_1800B5D83
0x1800b5d1f  mov     edx, 0CAh
0x1800b5d24  jmp     short loc_1800B5D70
0x1800b5d26  mov     r9, [rsp+268h+var_238]
0x1800b5d2b  lea     r8, aKnownapps; "KnownApps"
0x1800b5d32  lea     rdx, [rsp+268h+var_228]
0x1800b5d37  mov     rcx, 0FFFFFFFF80000002h
0x1800b5d3e  call    cs:__imp_FwRegSetString
0x1800b5d44  mov     ecx, eax
0x1800b5d46  call    cs:__imp_FwHResultToWindowsError
0x1800b5d4c  mov     ebx, eax
0x1800b5d4e  test    eax, eax
0x1800b5d50  jz      short loc_1800B5D83
0x1800b5d52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5d59  lea     rdx, WPP_GLOBAL_Control
0x1800b5d60  cmp     rcx, rdx
0x1800b5d63  jz      short loc_1800B5D83
0x1800b5d65  test    byte ptr [rcx+1Ch], 1
0x1800b5d69  jz      short loc_1800B5D83
0x1800b5d6b  mov     edx, 0CBh
0x1800b5d70  mov     rcx, [rcx+10h]
0x1800b5d74  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b5d7b  mov     r9d, eax
0x1800b5d7e  call    WPP_SF_d
0x1800b5d83  mov     rcx, [rsp+268h+var_238]
0x1800b5d88  call    cs:__imp_FwFree
0x1800b5d8e  mov     eax, ebx
0x1800b5d90  mov     rcx, [rsp+268h+var_18]
0x1800b5d98  xor     rcx, rsp; StackCookie
0x1800b5d9b  call    __security_check_cookie
0x1800b5da0  add     rsp, 260h
0x1800b5da7  pop     rbx
0x1800b5da8  retn
```
