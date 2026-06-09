# FwMoneisInboxAppCServicingInitialize(void)

- ea: `0x1800bbbc0`
- end: `0x1800bbfad`
- name: `?FwMoneisInboxAppCServicingInitialize@@YAKXZ`
- size: `1005`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800beee0`

## callees

- `0x180001784`
- `0x18000a66c`
- `0x18000a710`
- `0x180061c90`
- `0x18006c8ac`
- `0x1800729c0`
- `0x180073488`
- `0x1800bbbc0`
- `0x1800bbfc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbc9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbc9a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bbc8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bbc8a`
- `fwbase!FwTriggerRegisterWait` at `0x1800bbe48`
- `fwbase!FwTriggerRegisterWait` at `0x1800bbe48`
- `fwbase!FwHResultToWindowsError` at `0x1800bbc23`
- `fwbase!FwHResultToWindowsError` at `0x1800bbd9c`
- `fwbase!FwHResultToWindowsError` at `0x1800bbed9`
- `fwbase!FwHResultToWindowsError` at `0x1800bbc23`
- `fwbase!FwHResultToWindowsError` at `0x1800bbd9c`
- `fwbase!FwHResultToWindowsError` at `0x1800bbed9`
- `fwbase!FwRegNotifyCreate` at `0x1800bbecb`
- `fwbase!FwRegNotifyCreate` at `0x1800bbecb`
- `fwbase!FwRegQueryString` at `0x1800bbd8e`
- `fwbase!FwRegQueryString` at `0x1800bbd8e`
- `fwbase!FwFree` at `0x1800bbf7a`
- `fwbase!FwFree` at `0x1800bbf7a`
- `fwbase!FwCriticalSectionCreate` at `0x1800bbc15`
- `fwbase!FwCriticalSectionCreate` at `0x1800bbc15`
- `FWPolicyIOMgr!FwStringToSids` at `0x1800bbdf3`
- `FWPolicyIOMgr!FwStringToSids` at `0x1800bbdf3`

## string_xrefs

- `0x1800bbeeb`: `FwRegNotifyCreate`
- `0x1800bbcd7`: `ACService`
- `0x1800bbc83`: `ConvertStringSidToSid`
- `0x1800bbe06`: `FwStringToSids`

## pseudocode

```c
__int64 FwMoneisInboxAppCServicingInitialize(void)
{
  unsigned int v0; // eax
  DWORD LastError; // eax
  DWORD v2; // ebx
  const char *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-A0h] BYREF

  v12 = 0;
  v13 = 0;
  memset_0(v14, 0, 0x208u);
  v0 = FwCriticalSectionCreate(qword_18012FBE8);
  LastError = FwHResultToWindowsError(v0);
  v2 = LastError;
  if ( LastError )
  {
    v3 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v5 = 209;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, LastError);
    }
  }
  else
  {
    v3 = "ConvertStringSidToSid";
    if ( ConvertStringSidToSidW(L"WD", &Sid2) )
    {
      dword_18012FC20 = 0;
      dword_18012FBD8 = 0;
      qword_18012FBE0 = 0;
      v6 = StringCchPrintfW(v14, 0x104u, L"%ls\\%ls", *(_QWORD *)gFwIsolationManager, L"ACService");
      if ( v6 >= 0 )
      {
        v7 = FwRegQueryString(-2147483646, v14, L"KnownApps", &v12, &v13);
        LastError = FwHResultToWindowsError(v7);
        v2 = LastError;
        if ( LastError )
        {
          v3 = "FwRegQueryString";
          v4 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v5 = 212;
            goto LABEL_5;
          }
        }
        else
        {
          LastError = FwStringToSids(v12, &dword_18012FBD8, &qword_18012FBE0);
          v2 = LastError;
          if ( LastError == 14 )
          {
            v3 = "FwStringToSids";
            v4 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v5 = 213;
              goto LABEL_5;
            }
          }
          else
          {
            LastError = FwTriggerRegisterWait(FwMoneisInboxAppCServicingUpdate, 0, Block);
            v2 = LastError;
            if ( LastError )
            {
              v3 = "FwTriggerRegisterWait";
              v4 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v5 = 214;
                goto LABEL_5;
              }
            }
            else
            {
              v8 = FwRegNotifyCreate(
                     -2147483646,
                     v14,
                     1,
                     5,
                     50,
                     FwMoneisInboxAppCServicingRegChange,
                     0,
                     (char *)Block + 8);
              LastError = FwHResultToWindowsError(v8);
              v2 = LastError;
              if ( !LastError )
              {
                FwMoneisInboxAppCServicingRegChange(0, 0);
                v3 = 0;
                goto LABEL_31;
              }
              v3 = "FwRegNotifyCreate";
              v4 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v5 = 215;
                goto LABEL_5;
              }
            }
          }
        }
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          211,
          (unsigned int)WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
          v6,
          (__int64)"FwMoneisInboxAppCServicingInitialize::StringCchPrintf");
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v5 = 210;
        goto LABEL_5;
      }
    }
  }
LABEL_31:
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(v10) = v2;
    v11 = (__int64)v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_18012C3B0,
      (__int64)&v11,
      (__int64)&v10);
  }
  FwFree(v12);
  return v2;
}

```

## disassembly

```asm
0x1800bbbc0  mov     [rsp-8+arg_0], rbx
0x1800bbbc5  mov     [rsp-8+arg_8], rdi
0x1800bbbca  push    rbp
0x1800bbbcb  lea     rbp, [rsp-180h]
0x1800bbbd3  sub     rsp, 280h
0x1800bbbda  mov     rax, cs:__security_cookie
0x1800bbbe1  xor     rax, rsp
0x1800bbbe4  mov     [rbp+180h+var_10], rax
0x1800bbbeb  xor     edx, edx; Val
0x1800bbbed  mov     [rsp+280h+var_230], 0
0x1800bbbf6  mov     r8d, 208h; Size
0x1800bbbfc  mov     [rsp+280h+var_228], 0
0x1800bbc04  lea     rcx, [rsp+280h+var_220]; void *
0x1800bbc09  call    memset_0
0x1800bbc0e  lea     rcx, qword_18012FBE8
0x1800bbc15  call    cs:__imp_FwCriticalSectionCreate
0x1800bbc1c  nop     dword ptr [rax+rax+00h]
0x1800bbc21  mov     ecx, eax
0x1800bbc23  call    cs:__imp_FwHResultToWindowsError
0x1800bbc2a  nop     dword ptr [rax+rax+00h]
0x1800bbc2f  mov     ebx, eax
0x1800bbc31  test    eax, eax
0x1800bbc33  jz      short loc_1800BBC75
0x1800bbc35  xor     edi, edi
0x1800bbc37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbc3e  lea     rdx, WPP_GLOBAL_Control
0x1800bbc45  cmp     rcx, rdx
0x1800bbc48  jz      loc_1800BBF20
0x1800bbc4e  test    byte ptr [rcx+1Ch], 1
0x1800bbc52  jz      loc_1800BBF20
0x1800bbc58  mov     edx, 0D1h
0x1800bbc5d  mov     rcx, [rcx+10h]
0x1800bbc61  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bbc68  mov     r9d, eax
0x1800bbc6b  call    WPP_SF_d
0x1800bbc70  jmp     loc_1800BBF20
0x1800bbc75  lea     rdx, Sid2; Sid
0x1800bbc7c  lea     rcx, aWd; "WD"
0x1800bbc83  lea     rdi, aConvertstrings_1; "ConvertStringSidToSid"
0x1800bbc8a  call    cs:__imp_ConvertStringSidToSidW
0x1800bbc91  nop     dword ptr [rax+rax+00h]
0x1800bbc96  test    eax, eax
0x1800bbc98  jnz     short loc_1800BBCD0
0x1800bbc9a  call    cs:__imp_GetLastError
0x1800bbca1  nop     dword ptr [rax+rax+00h]
0x1800bbca6  mov     ebx, eax
0x1800bbca8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbcaf  lea     rdx, WPP_GLOBAL_Control
0x1800bbcb6  cmp     rcx, rdx
0x1800bbcb9  jz      loc_1800BBF20
0x1800bbcbf  test    byte ptr [rcx+1Ch], 1
0x1800bbcc3  jz      loc_1800BBF20
0x1800bbcc9  mov     edx, 0D2h
0x1800bbcce  jmp     short loc_1800BBC5D
0x1800bbcd0  mov     r9, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bbcd7  lea     rax, aAcservice; "ACService"
0x1800bbcde  mov     cs:dword_18012FC20, 0
0x1800bbce8  lea     r8, aLsLs; "%ls\\%ls"
0x1800bbcef  mov     cs:dword_18012FBD8, 0
0x1800bbcf9  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x1800bbcfe  mov     cs:qword_18012FBE0, 0
0x1800bbd09  mov     edx, 104h; unsigned __int64
0x1800bbd0e  mov     r9, [r9]
0x1800bbd11  mov     [rsp+280h+var_260], rax
0x1800bbd16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bbd1b  test    eax, eax
0x1800bbd1d  jns     short loc_1800BBD69
0x1800bbd1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbd26  lea     rdx, WPP_GLOBAL_Control
0x1800bbd2d  cmp     rcx, rdx
0x1800bbd30  jz      loc_1800BBF20
0x1800bbd36  test    byte ptr [rcx+1Ch], 1
0x1800bbd3a  jz      loc_1800BBF20
0x1800bbd40  mov     rcx, [rcx+10h]
0x1800bbd44  lea     r8, aFwmoneisinboxa_0; "FwMoneisInboxAppCServicingInitialize::S"...
0x1800bbd4b  mov     [rsp+280h+var_260], r8
0x1800bbd50  mov     edx, 0D3h
0x1800bbd55  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bbd5c  mov     r9d, eax
0x1800bbd5f  call    WPP_SF_Ds
0x1800bbd64  jmp     loc_1800BBF20
0x1800bbd69  lea     rax, [rsp+280h+var_228]
0x1800bbd6e  mov     rdi, 0FFFFFFFF80000002h
0x1800bbd75  mov     rcx, rdi
0x1800bbd78  mov     [rsp+280h+var_260], rax
0x1800bbd7d  lea     r9, [rsp+280h+var_230]
0x1800bbd82  lea     r8, aKnownapps; "KnownApps"
0x1800bbd89  lea     rdx, [rsp+280h+var_220]
0x1800bbd8e  call    cs:__imp_FwRegQueryString
0x1800bbd95  nop     dword ptr [rax+rax+00h]
0x1800bbd9a  mov     ecx, eax
0x1800bbd9c  call    cs:__imp_FwHResultToWindowsError
0x1800bbda3  nop     dword ptr [rax+rax+00h]
0x1800bbda8  mov     ebx, eax
0x1800bbdaa  test    eax, eax
0x1800bbdac  jz      short loc_1800BBDE0
0x1800bbdae  lea     rdi, aFwregquerystri_0; "FwRegQueryString"
0x1800bbdb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbdbc  lea     rdx, WPP_GLOBAL_Control
0x1800bbdc3  cmp     rcx, rdx
0x1800bbdc6  jz      loc_1800BBF20
0x1800bbdcc  test    byte ptr [rcx+1Ch], 1
0x1800bbdd0  jz      loc_1800BBF20
0x1800bbdd6  mov     edx, 0D4h
0x1800bbddb  jmp     loc_1800BBC5D
0x1800bbde0  mov     rcx, [rsp+280h+var_230]
0x1800bbde5  lea     r8, qword_18012FBE0
0x1800bbdec  lea     rdx, dword_18012FBD8
0x1800bbdf3  call    cs:__imp_FwStringToSids
0x1800bbdfa  nop     dword ptr [rax+rax+00h]
0x1800bbdff  mov     ebx, eax
0x1800bbe01  cmp     eax, 0Eh
0x1800bbe04  jnz     short loc_1800BBE38
0x1800bbe06  lea     rdi, aFwstringtosids_0; "FwStringToSids"
0x1800bbe0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbe14  lea     rdx, WPP_GLOBAL_Control
0x1800bbe1b  cmp     rcx, rdx
0x1800bbe1e  jz      loc_1800BBF20
0x1800bbe24  test    byte ptr [rcx+1Ch], 1
0x1800bbe28  jz      loc_1800BBF20
0x1800bbe2e  mov     edx, 0D5h
0x1800bbe33  jmp     loc_1800BBC5D
0x1800bbe38  mov     r8, cs:Block
0x1800bbe3f  lea     rcx, ?FwMoneisInboxAppCServicingUpdate@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; FwMoneisInboxAppCServicingUpdate(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x1800bbe46  xor     edx, edx
0x1800bbe48  call    cs:__imp_FwTriggerRegisterWait
0x1800bbe4f  nop     dword ptr [rax+rax+00h]
0x1800bbe54  mov     ebx, eax
0x1800bbe56  test    eax, eax
0x1800bbe58  jz      short loc_1800BBE8C
0x1800bbe5a  lea     rdi, aFwtriggerregis_0; "FwTriggerRegisterWait"
0x1800bbe61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbe68  lea     rdx, WPP_GLOBAL_Control
0x1800bbe6f  cmp     rcx, rdx
0x1800bbe72  jz      loc_1800BBF20
0x1800bbe78  test    byte ptr [rcx+1Ch], 1
0x1800bbe7c  jz      loc_1800BBF20
0x1800bbe82  mov     edx, 0D6h
0x1800bbe87  jmp     loc_1800BBC5D
0x1800bbe8c  mov     rax, cs:Block
0x1800bbe93  lea     rdx, [rsp+280h+var_220]
0x1800bbe98  add     rax, 8
0x1800bbe9c  mov     r9d, 5
0x1800bbea2  mov     [rsp+280h+var_248], rax
0x1800bbea7  mov     rcx, rdi
0x1800bbeaa  lea     rax, ?FwMoneisInboxAppCServicingRegChange@@YAXPEAXJ@Z; FwMoneisInboxAppCServicingRegChange(void *,long)
0x1800bbeb1  mov     [rsp+280h+var_250], 0
0x1800bbeba  mov     [rsp+280h+var_258], rax
0x1800bbebf  lea     r8d, [r9-4]
0x1800bbec3  mov     dword ptr [rsp+280h+var_260], 32h ; '2'
0x1800bbecb  call    cs:__imp_FwRegNotifyCreate
0x1800bbed2  nop     dword ptr [rax+rax+00h]
0x1800bbed7  mov     ecx, eax
0x1800bbed9  call    cs:__imp_FwHResultToWindowsError
0x1800bbee0  nop     dword ptr [rax+rax+00h]
0x1800bbee5  mov     ebx, eax
0x1800bbee7  test    eax, eax
0x1800bbee9  jz      short loc_1800BBF15
0x1800bbeeb  lea     rdi, aFwregnotifycre_0; "FwRegNotifyCreate"
0x1800bbef2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbef9  lea     rdx, WPP_GLOBAL_Control
0x1800bbf00  cmp     rcx, rdx
0x1800bbf03  jz      short loc_1800BBF20
0x1800bbf05  test    byte ptr [rcx+1Ch], 1
0x1800bbf09  jz      short loc_1800BBF20
0x1800bbf0b  mov     edx, 0D7h
0x1800bbf10  jmp     loc_1800BBC5D
0x1800bbf15  xor     edx, edx; int
0x1800bbf17  xor     ecx, ecx; void *
0x1800bbf19  call    ?FwMoneisInboxAppCServicingRegChange@@YAXPEAXJ@Z; FwMoneisInboxAppCServicingRegChange(void *,long)
0x1800bbf1e  xor     edi, edi
0x1800bbf20  mov     eax, cs:dword_18012C3B0
0x1800bbf26  cmp     eax, 4
0x1800bbf29  jbe     short loc_1800BBF75
0x1800bbf2b  mov     rdx, 4000000000000h
0x1800bbf35  lea     rcx, dword_18012C3B0
0x1800bbf3c  call    _tlgKeywordOn
0x1800bbf41  test    al, al
0x1800bbf43  jz      short loc_1800BBF75
0x1800bbf45  lea     rax, [rsp+280h+var_240]
0x1800bbf4a  mov     dword ptr [rsp+280h+var_240], ebx
0x1800bbf4e  mov     [rsp+280h+var_258], rax; __int64
0x1800bbf53  lea     rdx, byte_1801169AD
0x1800bbf5a  lea     rax, [rsp+280h+var_238]
0x1800bbf5f  mov     [rsp+280h+var_238], rdi
0x1800bbf64  lea     rcx, dword_18012C3B0; int
0x1800bbf6b  mov     [rsp+280h+var_260], rax; __int64
0x1800bbf70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bbf75  mov     rcx, [rsp+280h+var_230]
0x1800bbf7a  call    cs:__imp_FwFree
0x1800bbf81  nop     dword ptr [rax+rax+00h]
0x1800bbf86  mov     eax, ebx
0x1800bbf88  mov     rcx, [rbp+180h+var_10]
0x1800bbf8f  xor     rcx, rsp; StackCookie
0x1800bbf92  call    __security_check_cookie
0x1800bbf97  lea     r11, [rsp+280h+var_s0]
0x1800bbf9f  mov     rbx, [r11+10h]
0x1800bbfa3  mov     rdi, [r11+18h]
0x1800bbfa7  mov     rsp, r11
0x1800bbfaa  pop     rbp
0x1800bbfab  retn
```
