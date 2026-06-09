# FwMoneisInboxAppCsUpdateList(void *)

- ea: `0x1800bc43c`
- end: `0x1800bc654`
- name: `?FwMoneisInboxAppCsUpdateList@@YAKPEAX@Z`
- size: `536`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800bc0b0`

## callees

- `0x18000a66c`
- `0x18000a710`
- `0x180058778`
- `0x18006c8ac`
- `0x1800729c0`
- `0x180073488`
- `0x1800bc43c`
- `0x1800c1e2c`

## import_xrefs

- `fwbase!FwRegSetString` at `0x1800bc5ce`
- `fwbase!FwRegSetString` at `0x1800bc5ce`
- `fwbase!FwHResultToWindowsError` at `0x1800bc584`
- `fwbase!FwHResultToWindowsError` at `0x1800bc5dc`
- `fwbase!FwHResultToWindowsError` at `0x1800bc584`
- `fwbase!FwHResultToWindowsError` at `0x1800bc5dc`
- `fwbase!FwFree` at `0x1800bc624`
- `fwbase!FwFree` at `0x1800bc624`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800bc576`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800bc576`

## string_xrefs

- `0x1800bc483`: `ACService`
- `0x1800bc4d9`: `FwMoneisInboxAppCsUpdateList::StringCchPrintf`

## pseudocode

```c
__int64 __fastcall FwMoneisInboxAppCsUpdateList(void *a1)
{
  unsigned int v2; // edi
  int v3; // r9d
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  struct _SID_AND_ATTRIBUTES v9; // [rsp+30h] [rbp-248h] BYREF
  __int64 v10; // [rsp+40h] [rbp-238h] BYREF
  unsigned __int16 v11[264]; // [rsp+50h] [rbp-228h] BYREF

  v2 = 0;
  v10 = 0;
  *(_QWORD *)&v9.Attributes = 0;
  memset_0(v11, 0, 0x208u);
  v9.Sid = a1;
  v3 = StringCchPrintfW(v11, 0x104u, L"%ls\\%ls", *(_QWORD *)gFwIsolationManager, L"ACService");
  if ( v3 >= 0 )
  {
    if ( (unsigned int)FwSidAndAttributesFindSid(&v9, qword_18012FBE0, dword_18012FBD8) )
      goto LABEL_19;
    v2 = FwSidAndAttributesAppend(&v9, &qword_18012FBE0, &dword_18012FBD8);
    if ( v2 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_19;
      v5 = 206;
    }
    else
    {
      v6 = FwSidsToString(dword_18012FBD8, qword_18012FBE0, &v10);
      v2 = FwHResultToWindowsError(v6);
      if ( v2 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_19;
        v5 = 207;
      }
      else
      {
        v7 = FwRegSetString(-2147483646, v11, L"KnownApps", v10);
        v2 = FwHResultToWindowsError(v7);
        if ( !v2 )
          goto LABEL_19;
        v4 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_19;
        v5 = 208;
      }
    }
    WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v2);
    goto LABEL_19;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_Ds(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      205,
      (unsigned int)WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
      v3,
      (__int64)"FwMoneisInboxAppCsUpdateList::StringCchPrintf");
LABEL_19:
  FwFree(v10);
  return v2;
}

```

## disassembly

```asm
0x1800bc43c  mov     [rsp+arg_8], rbx
0x1800bc441  push    rdi
0x1800bc442  sub     rsp, 270h
0x1800bc449  mov     rax, cs:__security_cookie
0x1800bc450  xor     rax, rsp
0x1800bc453  mov     [rsp+278h+var_18], rax
0x1800bc45b  mov     rbx, rcx
0x1800bc45e  xor     edi, edi
0x1800bc460  lea     rcx, [rsp+278h+var_228]; void *
0x1800bc465  mov     [rsp+278h+var_238], rdi
0x1800bc46a  xor     edx, edx; Val
0x1800bc46c  mov     qword ptr [rsp+278h+var_248.Attributes], rdi
0x1800bc471  mov     r8d, 208h; Size
0x1800bc477  call    memset_0
0x1800bc47c  mov     r9, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bc483  lea     rax, aAcservice; "ACService"
0x1800bc48a  lea     r8, aLsLs; "%ls\\%ls"
0x1800bc491  mov     [rsp+278h+var_248.Sid], rbx
0x1800bc496  mov     edx, 104h; unsigned __int64
0x1800bc49b  mov     [rsp+278h+var_258], rax
0x1800bc4a0  lea     rcx, [rsp+278h+var_228]; unsigned __int16 *
0x1800bc4a5  mov     r9, [r9]
0x1800bc4a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bc4ad  mov     r9d, eax
0x1800bc4b0  test    eax, eax
0x1800bc4b2  jns     short loc_1800BC4FB
0x1800bc4b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc4bb  lea     rax, WPP_GLOBAL_Control
0x1800bc4c2  cmp     rcx, rax
0x1800bc4c5  jz      loc_1800BC61F
0x1800bc4cb  test    byte ptr [rcx+1Ch], 1
0x1800bc4cf  jz      loc_1800BC61F
0x1800bc4d5  mov     rcx, [rcx+10h]
0x1800bc4d9  lea     rax, aFwmoneisinboxa_1; "FwMoneisInboxAppCsUpdateList::StringCch"...
0x1800bc4e0  mov     edx, 0CDh
0x1800bc4e5  mov     [rsp+278h+var_258], rax
0x1800bc4ea  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bc4f1  call    WPP_SF_Ds
0x1800bc4f6  jmp     loc_1800BC61F
0x1800bc4fb  mov     r8d, cs:dword_18012FBD8; unsigned int
0x1800bc502  lea     rcx, [rsp+278h+var_248]; struct _SID_AND_ATTRIBUTES *
0x1800bc507  mov     rdx, cs:qword_18012FBE0; struct _SID_AND_ATTRIBUTES *
0x1800bc50e  call    ?FwSidAndAttributesFindSid@@YAHPEAU_SID_AND_ATTRIBUTES@@0K@Z; FwSidAndAttributesFindSid(_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,ulong)
0x1800bc513  test    eax, eax
0x1800bc515  jnz     loc_1800BC61F
0x1800bc51b  lea     r8, dword_18012FBD8; unsigned int *
0x1800bc522  lea     rdx, qword_18012FBE0; struct _SID_AND_ATTRIBUTES **
0x1800bc529  lea     rcx, [rsp+278h+var_248]; struct _SID_AND_ATTRIBUTES *
0x1800bc52e  call    ?FwSidAndAttributesAppend@@YAKPEAU_SID_AND_ATTRIBUTES@@PEAPEAU1@PEAK@Z; FwSidAndAttributesAppend(_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES * *,ulong *)
0x1800bc533  mov     edi, eax
0x1800bc535  test    eax, eax
0x1800bc537  jz      short loc_1800BC564
0x1800bc539  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc540  lea     rax, WPP_GLOBAL_Control
0x1800bc547  cmp     rcx, rax
0x1800bc54a  jz      loc_1800BC61F
0x1800bc550  test    byte ptr [rcx+1Ch], 1
0x1800bc554  jz      loc_1800BC61F
0x1800bc55a  mov     edx, 0CEh
0x1800bc55f  jmp     loc_1800BC60C
0x1800bc564  mov     rdx, cs:qword_18012FBE0
0x1800bc56b  lea     r8, [rsp+278h+var_238]
0x1800bc570  mov     ecx, cs:dword_18012FBD8
0x1800bc576  call    cs:__imp_FwSidsToString
0x1800bc57d  nop     dword ptr [rax+rax+00h]
0x1800bc582  mov     ecx, eax
0x1800bc584  call    cs:__imp_FwHResultToWindowsError
0x1800bc58b  nop     dword ptr [rax+rax+00h]
0x1800bc590  mov     edi, eax
0x1800bc592  test    eax, eax
0x1800bc594  jz      short loc_1800BC5B6
0x1800bc596  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc59d  lea     rax, WPP_GLOBAL_Control
0x1800bc5a4  cmp     rcx, rax
0x1800bc5a7  jz      short loc_1800BC61F
0x1800bc5a9  test    byte ptr [rcx+1Ch], 1
0x1800bc5ad  jz      short loc_1800BC61F
0x1800bc5af  mov     edx, 0CFh
0x1800bc5b4  jmp     short loc_1800BC60C
0x1800bc5b6  mov     r9, [rsp+278h+var_238]
0x1800bc5bb  lea     r8, aKnownapps; "KnownApps"
0x1800bc5c2  lea     rdx, [rsp+278h+var_228]
0x1800bc5c7  mov     rcx, 0FFFFFFFF80000002h
0x1800bc5ce  call    cs:__imp_FwRegSetString
0x1800bc5d5  nop     dword ptr [rax+rax+00h]
0x1800bc5da  mov     ecx, eax
0x1800bc5dc  call    cs:__imp_FwHResultToWindowsError
0x1800bc5e3  nop     dword ptr [rax+rax+00h]
0x1800bc5e8  mov     edi, eax
0x1800bc5ea  test    eax, eax
0x1800bc5ec  jz      short loc_1800BC61F
0x1800bc5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc5f5  lea     rax, WPP_GLOBAL_Control
0x1800bc5fc  cmp     rcx, rax
0x1800bc5ff  jz      short loc_1800BC61F
0x1800bc601  test    byte ptr [rcx+1Ch], 1
0x1800bc605  jz      short loc_1800BC61F
0x1800bc607  mov     edx, 0D0h
0x1800bc60c  mov     rcx, [rcx+10h]
0x1800bc610  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bc617  mov     r9d, edi
0x1800bc61a  call    WPP_SF_d
0x1800bc61f  mov     rcx, [rsp+278h+var_238]
0x1800bc624  call    cs:__imp_FwFree
0x1800bc62b  nop     dword ptr [rax+rax+00h]
0x1800bc630  mov     eax, edi
0x1800bc632  mov     rcx, [rsp+278h+var_18]
0x1800bc63a  xor     rcx, rsp; StackCookie
0x1800bc63d  call    __security_check_cookie
0x1800bc642  mov     rbx, [rsp+278h+arg_8]
0x1800bc64a  add     rsp, 270h
0x1800bc651  pop     rdi
0x1800bc652  retn
```
