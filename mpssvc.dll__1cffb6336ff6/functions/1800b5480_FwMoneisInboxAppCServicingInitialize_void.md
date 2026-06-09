# FwMoneisInboxAppCServicingInitialize(void)

- ea: `0x1800b5480`
- end: `0x1800b57b5`
- name: `?FwMoneisInboxAppCServicingInitialize@@YAKXZ`
- size: `821`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b80c0`

## callees

- `0x18000177c`
- `0x18000ae9c`
- `0x18000af3c`
- `0x18005cf9c`
- `0x180069bb4`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800b5480`
- `0x1800b57c0`
- `0x1800bda40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b54e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b54e2`
- `fwbase!FwTriggerRegisterWait` at `0x1800b5665`
- `fwbase!FwTriggerRegisterWait` at `0x1800b5665`
- `fwbase!FwRegNotifyCreate` at `0x1800b56e6`
- `fwbase!FwRegNotifyCreate` at `0x1800b56e6`
- `fwbase!FwRegQueryString` at `0x1800b55d4`
- `fwbase!FwRegQueryString` at `0x1800b55d4`
- `fwbase!FwHResultToWindowsError` at `0x1800b55dc`
- `fwbase!FwHResultToWindowsError` at `0x1800b56ee`
- `fwbase!FwHResultToWindowsError` at `0x1800b55dc`
- `fwbase!FwHResultToWindowsError` at `0x1800b56ee`
- `fwbase!FwFree` at `0x1800b5789`
- `fwbase!FwFree` at `0x1800b5789`

## string_xrefs

- `0x1800b56fa`: `FwRegNotifyCreate`
- `0x1800b5537`: `ACService`

## pseudocode

```c
__int64 FwMoneisInboxAppCServicingInitialize(void)
{
  const char *v0; // rdi
  DWORD LastError; // ebx
  __int64 v2; // rcx
  __int64 v3; // rdx
  int v4; // r9d
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-A0h] BYREF

  v12 = 0;
  v13 = 0;
  v0 = 0;
  memset_0(v14, 0, 0x208u);
  if ( ConvertStringSidToSidW(L"WD", gSidManager + 1) )
  {
    v4 = StringCchPrintfW(v14, 0x104u, L"%ls\\%ls", *((_QWORD *)gFwIsolationManager + 13), L"ACService");
    if ( v4 >= 0 )
    {
      v0 = "FwRegQueryString";
      v5 = FwRegQueryString(-2147483646, v14, L"KnownApps", &v12, &v13);
      LastError = FwHResultToWindowsError(v5);
      if ( LastError )
      {
        v2 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v3 = 20;
          goto LABEL_5;
        }
      }
      else
      {
        LastError = appIsolation::InboxAppContainerManager::InitializeInboxAppContainerManagement(
                      gInboxAppContainerManager,
                      v12);
        if ( LastError )
        {
          v2 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v3 = 21;
            goto LABEL_5;
          }
        }
        else
        {
          LastError = FwTriggerRegisterWait(FwMoneisInboxAppCServicingUpdate, 0, Block);
          if ( LastError )
          {
            v0 = "FwTriggerRegisterWait";
            v2 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v3 = 22;
              goto LABEL_5;
            }
          }
          else
          {
            v6 = FwRegNotifyCreate(
                   -2147483646,
                   v14,
                   1,
                   5,
                   50,
                   FwMoneisInboxAppCServicingRegChange,
                   0,
                   (char *)Block + 8);
            LastError = FwHResultToWindowsError(v6);
            if ( !LastError )
            {
              FwMoneisInboxAppCServicingRegChange(0, 0);
              v0 = 0;
              goto LABEL_27;
            }
            v0 = "FwRegNotifyCreate";
            v2 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v3 = 23;
              goto LABEL_5;
            }
          }
        }
      }
    }
    else
    {
      LastError = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_Ds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          19,
          (unsigned int)WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
          v4,
          (__int64)"FwMoneisInboxAppCServicingInitialize::StringCchPrintf");
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 18;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, LastError);
    }
  }
LABEL_27:
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(v10) = LastError;
    v11 = (__int64)v0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)&dword_180110B74,
      v7,
      v8,
      (const char **)&v11,
      (__int64)&v10);
  }
  FwFree(v12);
  return LastError;
}

```

## disassembly

```asm
0x1800b5480  mov     [rsp-8+arg_0], rbx
0x1800b5485  mov     [rsp-8+arg_8], rdi
0x1800b548a  push    rbp
0x1800b548b  lea     rbp, [rsp-180h]
0x1800b5493  sub     rsp, 280h
0x1800b549a  mov     rax, cs:__security_cookie
0x1800b54a1  xor     rax, rsp
0x1800b54a4  mov     [rbp+180h+var_10], rax
0x1800b54ab  xor     edx, edx; Val
0x1800b54ad  mov     [rsp+280h+var_230], 0
0x1800b54b6  mov     r8d, 208h; Size
0x1800b54bc  mov     [rsp+280h+var_228], 0
0x1800b54c4  lea     rcx, [rsp+280h+var_220]; void *
0x1800b54c9  xor     edi, edi
0x1800b54cb  call    memset_0
0x1800b54d0  mov     rdx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b54d7  lea     rcx, aWd; "WD"
0x1800b54de  add     rdx, 8; Sid
0x1800b54e2  call    cs:__imp_ConvertStringSidToSidW
0x1800b54e8  test    eax, eax
0x1800b54ea  jnz     short loc_1800B5530
0x1800b54ec  call    cs:__imp_GetLastError
0x1800b54f2  mov     ebx, eax
0x1800b54f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b54fb  lea     rax, WPP_GLOBAL_Control
0x1800b5502  cmp     rcx, rax
0x1800b5505  jz      loc_1800B572F
0x1800b550b  test    byte ptr [rcx+1Ch], 1
0x1800b550f  jz      loc_1800B572F
0x1800b5515  lea     edx, [rdi+12h]
0x1800b5518  mov     rcx, [rcx+10h]
0x1800b551c  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b5523  mov     r9d, ebx
0x1800b5526  call    WPP_SF_d
0x1800b552b  jmp     loc_1800B572F
0x1800b5530  mov     r9, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b5537  lea     rax, aAcservice; "ACService"
0x1800b553e  lea     r8, aLsLs; "%ls\\%ls"
0x1800b5545  mov     [rsp+280h+var_260], rax
0x1800b554a  mov     edx, 104h; unsigned __int64
0x1800b554f  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x1800b5554  mov     r9, [r9+68h]
0x1800b5558  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b555d  mov     r9d, eax
0x1800b5560  test    eax, eax
0x1800b5562  jns     short loc_1800B55AB
0x1800b5564  xor     ebx, ebx
0x1800b5566  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b556d  lea     rax, WPP_GLOBAL_Control
0x1800b5574  cmp     rcx, rax
0x1800b5577  jz      loc_1800B572F
0x1800b557d  test    byte ptr [rcx+1Ch], 1
0x1800b5581  jz      loc_1800B572F
0x1800b5587  mov     rcx, [rcx+10h]
0x1800b558b  lea     rax, aFwmoneisinboxa_0; "FwMoneisInboxAppCServicingInitialize::S"...
0x1800b5592  lea     edx, [rbx+13h]
0x1800b5595  mov     [rsp+280h+var_260], rax
0x1800b559a  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b55a1  call    WPP_SF_Ds
0x1800b55a6  jmp     loc_1800B572F
0x1800b55ab  lea     rax, [rsp+280h+var_228]
0x1800b55b0  mov     rcx, 0FFFFFFFF80000002h
0x1800b55b7  lea     r9, [rsp+280h+var_230]
0x1800b55bc  mov     [rsp+280h+var_260], rax
0x1800b55c1  lea     r8, aKnownapps; "KnownApps"
0x1800b55c8  lea     rdx, [rsp+280h+var_220]
0x1800b55cd  lea     rdi, aFwregquerystri_0; "FwRegQueryString"
0x1800b55d4  call    cs:__imp_FwRegQueryString
0x1800b55da  mov     ecx, eax
0x1800b55dc  call    cs:__imp_FwHResultToWindowsError
0x1800b55e2  mov     ebx, eax
0x1800b55e4  test    eax, eax
0x1800b55e6  jz      short loc_1800B5613
0x1800b55e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b55ef  lea     rax, WPP_GLOBAL_Control
0x1800b55f6  cmp     rcx, rax
0x1800b55f9  jz      loc_1800B572F
0x1800b55ff  test    byte ptr [rcx+1Ch], 1
0x1800b5603  jz      loc_1800B572F
0x1800b5609  mov     edx, 14h
0x1800b560e  jmp     loc_1800B5518
0x1800b5613  mov     rdx, [rsp+280h+var_230]; unsigned __int16 *
0x1800b5618  mov     rcx, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; this
0x1800b561f  call    ?InitializeInboxAppContainerManagement@InboxAppContainerManager@appIsolation@@QEAAKPEAG@Z; appIsolation::InboxAppContainerManager::InitializeInboxAppContainerManagement(ushort *)
0x1800b5624  mov     ebx, eax
0x1800b5626  test    eax, eax
0x1800b5628  jz      short loc_1800B5655
0x1800b562a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5631  lea     rax, WPP_GLOBAL_Control
0x1800b5638  cmp     rcx, rax
0x1800b563b  jz      loc_1800B572F
0x1800b5641  test    byte ptr [rcx+1Ch], 1
0x1800b5645  jz      loc_1800B572F
0x1800b564b  mov     edx, 15h
0x1800b5650  jmp     loc_1800B5518
0x1800b5655  mov     r8, cs:Block
0x1800b565c  lea     rcx, ?FwMoneisInboxAppCServicingUpdate@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; FwMoneisInboxAppCServicingUpdate(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x1800b5663  xor     edx, edx
0x1800b5665  call    cs:__imp_FwTriggerRegisterWait
0x1800b566b  mov     ebx, eax
0x1800b566d  test    eax, eax
0x1800b566f  jz      short loc_1800B56A3
0x1800b5671  lea     rdi, aFwtriggerregis_0; "FwTriggerRegisterWait"
0x1800b5678  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b567f  lea     rax, WPP_GLOBAL_Control
0x1800b5686  cmp     rcx, rax
0x1800b5689  jz      loc_1800B572F
0x1800b568f  test    byte ptr [rcx+1Ch], 1
0x1800b5693  jz      loc_1800B572F
0x1800b5699  mov     edx, 16h
0x1800b569e  jmp     loc_1800B5518
0x1800b56a3  mov     rax, cs:Block
0x1800b56aa  lea     rdx, [rsp+280h+var_220]
0x1800b56af  add     rax, 8
0x1800b56b3  mov     r9d, 5
0x1800b56b9  mov     [rsp+280h+var_248], rax
0x1800b56be  mov     rcx, 0FFFFFFFF80000002h
0x1800b56c5  lea     rax, ?FwMoneisInboxAppCServicingRegChange@@YAXPEAXJ@Z; FwMoneisInboxAppCServicingRegChange(void *,long)
0x1800b56cc  mov     [rsp+280h+var_250], 0
0x1800b56d5  mov     [rsp+280h+var_258], rax
0x1800b56da  lea     r8d, [r9-4]
0x1800b56de  mov     dword ptr [rsp+280h+var_260], 32h ; '2'
0x1800b56e6  call    cs:__imp_FwRegNotifyCreate
0x1800b56ec  mov     ecx, eax
0x1800b56ee  call    cs:__imp_FwHResultToWindowsError
0x1800b56f4  mov     ebx, eax
0x1800b56f6  test    eax, eax
0x1800b56f8  jz      short loc_1800B5724
0x1800b56fa  lea     rdi, aFwregnotifycre_0; "FwRegNotifyCreate"
0x1800b5701  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5708  lea     rax, WPP_GLOBAL_Control
0x1800b570f  cmp     rcx, rax
0x1800b5712  jz      short loc_1800B572F
0x1800b5714  test    byte ptr [rcx+1Ch], 1
0x1800b5718  jz      short loc_1800B572F
0x1800b571a  mov     edx, 17h
0x1800b571f  jmp     loc_1800B5518
0x1800b5724  xor     edx, edx; int
0x1800b5726  xor     ecx, ecx; void *
0x1800b5728  call    ?FwMoneisInboxAppCServicingRegChange@@YAXPEAXJ@Z; FwMoneisInboxAppCServicingRegChange(void *,long)
0x1800b572d  xor     edi, edi
0x1800b572f  mov     eax, cs:dword_1801263B0
0x1800b5735  cmp     eax, 4
0x1800b5738  jbe     short loc_1800B5784
0x1800b573a  mov     rdx, 4000000000000h
0x1800b5744  lea     rcx, dword_1801263B0
0x1800b574b  call    _tlgKeywordOn
0x1800b5750  test    al, al
0x1800b5752  jz      short loc_1800B5784
0x1800b5754  lea     rax, [rsp+280h+var_240]
0x1800b5759  mov     dword ptr [rsp+280h+var_240], ebx
0x1800b575d  mov     [rsp+280h+var_258], rax; __int64
0x1800b5762  lea     rdx, dword_180110B74
0x1800b5769  lea     rax, [rsp+280h+var_238]
0x1800b576e  mov     [rsp+280h+var_238], rdi
0x1800b5773  lea     rcx, dword_1801263B0; int
0x1800b577a  mov     [rsp+280h+var_260], rax; __int64
0x1800b577f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b5784  mov     rcx, [rsp+280h+var_230]
0x1800b5789  call    cs:__imp_FwFree
0x1800b578f  mov     eax, ebx
0x1800b5791  mov     rcx, [rbp+180h+var_10]
0x1800b5798  xor     rcx, rsp; StackCookie
0x1800b579b  call    __security_check_cookie
0x1800b57a0  lea     r11, [rsp+280h+var_s0]
0x1800b57a8  mov     rbx, [r11+10h]
0x1800b57ac  mov     rdi, [r11+18h]
0x1800b57b0  mov     rsp, r11
0x1800b57b3  pop     rbp
0x1800b57b4  retn
```
