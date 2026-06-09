# SettingAnnouncementHandler(ushort *,ushort *)

- ea: `0x14002b7f0`
- end: `0x14002b9d0`
- name: `?SettingAnnouncementHandler@@YAXPEAG0@Z`
- size: `480`
- prototype: `void __fastcall(PCNZWCH lpString1, wchar_t *String)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x14002b7f0`
- `0x140034ce4`
- `0x140037168`
- `0x14003ecf8`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002b831`
- `KERNEL32!CompareStringW` at `0x14002b831`
- `USER32!SendMessageW` at `0x14002b956`
- `USER32!SendMessageW` at `0x14002b9b0`
- `USER32!SendMessageW` at `0x14002b956`
- `USER32!SendMessageW` at `0x14002b9b0`
- `msvcrt!_wtoi` at `0x14002b863`
- `msvcrt!_wtoi` at `0x14002b863`

## string_xrefs

- `0x14002b8a8`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SettingAnnouncementHandler(PCNZWCH lpString1, wchar_t *String)
{
  int v3; // ebx
  signed int SettingFromRegistry; // eax
  unsigned int v5; // r9d
  LPARAM v6; // r9
  WPARAM wParam[2]; // [rsp+30h] [rbp-828h] BYREF
  unsigned __int16 v8[1024]; // [rsp+40h] [rbp-818h] BYREF

  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"CONTACTEXCHANGE", -1) == 2 )
  {
    memset_0(v8, 0, sizeof(v8));
    LODWORD(wParam[0]) = 0;
    v3 = _wtoi(String);
    SettingFromRegistry = CSettingsManager::GetSettingFromRegistry((char *)_AtlModule + 696, 4, wParam);
    if ( SettingFromRegistry < 0 )
    {
      v5 = 5468;
LABEL_4:
      CEventLogger::LogError(
        (CEventLogger *)L"SettingAnnouncementHandler",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        v5,
        L"SettingAnnouncementHandler",
        SettingFromRegistry);
      goto LABEL_17;
    }
    if ( *(_QWORD *)(*((_QWORD *)_AtlModule + 104) + 208LL) )
    {
      SettingFromRegistry = StringCchPrintfW(v8, 0x400u, L"%d", LODWORD(wParam[0]));
      if ( SettingFromRegistry < 0 )
      {
        v5 = 5479;
        goto LABEL_4;
      }
      SettingFromRegistry = CRATicket::SendControlMessage(
                              *((CRATicket **)_AtlModule + 104),
                              7,
                              (__int64)L"CONTACTEXCHANGE",
                              (__int64)v8);
      if ( SettingFromRegistry < 0 )
      {
        v5 = 5484;
        goto LABEL_4;
      }
      if ( !v3 )
      {
        SendMessageW(*((HWND *)_AtlModule + 35), 0x801Bu, LODWORD(wParam[0]), 3);
LABEL_12:
        *((_DWORD *)_AtlModule + 204) &= ~1u;
        return;
      }
    }
    else
    {
      v6 = 1;
      if ( v3 != 1 )
        v6 = 3;
      SendMessageW(*((HWND *)_AtlModule + 10), 0x801Bu, LODWORD(wParam[0]), v6);
    }
LABEL_17:
    if ( v3 == 1 )
    {
      *((_DWORD *)_AtlModule + 204) |= 1u;
      return;
    }
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x14002b7f0  mov     [rsp+arg_10], rbx
0x14002b7f5  push    rsi
0x14002b7f6  sub     rsp, 850h
0x14002b7fd  mov     rax, cs:__security_cookie
0x14002b804  xor     rax, rsp
0x14002b807  mov     [rsp+858h+var_18], rax
0x14002b80f  mov     rbx, rdx
0x14002b812  or      r9d, 0FFFFFFFFh; cchCount1
0x14002b816  mov     [rsp+858h+cchCount2], r9d; cchCount2
0x14002b81b  lea     rsi, aContactexchang; "CONTACTEXCHANGE"
0x14002b822  mov     [rsp+858h+lpString2], rsi; lpString2
0x14002b827  mov     r8, rcx; lpString1
0x14002b82a  lea     edx, [r9+2]; dwCmpFlags
0x14002b82e  lea     ecx, [rdx+7Eh]; Locale
0x14002b831  call    cs:__imp_CompareStringW
0x14002b838  nop     dword ptr [rax+rax+00h]
0x14002b83d  cmp     eax, 2
0x14002b840  jnz     loc_14002B970
0x14002b846  xor     edx, edx; Val
0x14002b848  mov     r8d, 800h; Size
0x14002b84e  lea     rcx, [rsp+858h+var_818]; void *
0x14002b853  call    memset_0
0x14002b858  mov     dword ptr [rsp+858h+wParam], 0
0x14002b860  mov     rcx, rbx; String
0x14002b863  call    cs:__imp__wtoi
0x14002b86a  nop     dword ptr [rax+rax+00h]
0x14002b86f  mov     ebx, eax
0x14002b871  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b878  add     rcx, 2B8h
0x14002b87f  lea     r8, [rsp+858h+wParam]
0x14002b884  mov     edx, 4
0x14002b889  call    ?GetSettingFromRegistry@CSettingsManager@@QEAAJW4_RASettingDWORD@@PEAK@Z; CSettingsManager::GetSettingFromRegistry(_RASettingDWORD,ulong *)
0x14002b88e  test    eax, eax
0x14002b890  jns     short loc_14002B8C0
0x14002b892  mov     r9d, 155Ch; unsigned int
0x14002b898  mov     [rsp+858h+cchCount2], eax; unsigned int
0x14002b89c  lea     rcx, aSettingannounc_0; "SettingAnnouncementHandler"
0x14002b8a3  mov     [rsp+858h+lpString2], rcx; unsigned __int16 *
0x14002b8a8  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002b8af  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002b8b6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002b8bb  jmp     loc_14002B9BC
0x14002b8c0  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b8c7  mov     rax, [rcx+340h]
0x14002b8ce  cmp     qword ptr [rax+0D0h], 0
0x14002b8d6  jz      loc_14002B992
0x14002b8dc  mov     r9d, dword ptr [rsp+858h+wParam]
0x14002b8e1  lea     r8, aD; "%d"
0x14002b8e8  mov     edx, 400h; unsigned __int64
0x14002b8ed  lea     rcx, [rsp+858h+var_818]; unsigned __int16 *
0x14002b8f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002b8f7  test    eax, eax
0x14002b8f9  jns     short loc_14002B903
0x14002b8fb  mov     r9d, 1567h
0x14002b901  jmp     short loc_14002B898
0x14002b903  lea     r9, [rsp+858h+var_818]
0x14002b908  mov     r8, rsi
0x14002b90b  mov     edx, 7
0x14002b910  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b917  mov     rcx, [rcx+340h]
0x14002b91e  call    ?SendControlMessage@CRATicket@@QEAAJW4_RCMESSAGE@@PEAG1@Z; CRATicket::SendControlMessage(_RCMESSAGE,ushort *,ushort *)
0x14002b923  test    eax, eax
0x14002b925  jns     short loc_14002B932
0x14002b927  mov     r9d, 156Ch
0x14002b92d  jmp     loc_14002B898
0x14002b932  test    ebx, ebx
0x14002b934  jnz     loc_14002B9BC
0x14002b93a  mov     r8d, dword ptr [rsp+858h+wParam]; wParam
0x14002b93f  mov     edx, 801Bh; Msg
0x14002b944  lea     r9d, [rbx+3]; lParam
0x14002b948  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b94f  mov     rcx, [rcx+118h]; hWnd
0x14002b956  call    cs:__imp_SendMessageW
0x14002b95d  nop     dword ptr [rax+rax+00h]
0x14002b962  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b969  and     dword ptr [rax+330h], 0FFFFFFFEh
0x14002b970  mov     rcx, [rsp+858h+var_18]
0x14002b978  xor     rcx, rsp; StackCookie
0x14002b97b  call    __security_check_cookie
0x14002b980  mov     rbx, [rsp+858h+arg_10]
0x14002b988  add     rsp, 850h
0x14002b98f  pop     rsi
0x14002b990  retn
0x14002b992  mov     eax, 3
0x14002b997  lea     r9d, [rax-2]
0x14002b99b  cmp     ebx, r9d
0x14002b99e  cmovnz  r9d, eax; lParam
0x14002b9a2  mov     r8d, dword ptr [rsp+858h+wParam]; wParam
0x14002b9a7  mov     edx, 801Bh; Msg
0x14002b9ac  mov     rcx, [rcx+50h]; hWnd
0x14002b9b0  call    cs:__imp_SendMessageW
0x14002b9b7  nop     dword ptr [rax+rax+00h]
0x14002b9bc  cmp     ebx, 1
0x14002b9bf  jnz     short loc_14002B962
0x14002b9c1  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002b9c8  or      [rax+330h], ebx
0x14002b9ce  jmp     short loc_14002B970
```
