# HHUrlSecurityManager::CheckAndSetSafeMode(char const *,HWND__ *)

- ea: `0x180065760`
- end: `0x180065b83`
- name: `?CheckAndSetSafeMode@HHUrlSecurityManager@@QEAAXPEBDPEAUHWND__@@@Z`
- size: `1059`
- prototype: `void(HHUrlSecurityManager *__hidden this, const char *, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f30c`

## callees

- `0x180065760`
- `0x180068a30`
- `0x180068f80`
- `0x180075c90`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180065b42`
- `ADVAPI32!EventWriteTransfer` at `0x180065b42`
- `ADVAPI32!EventSetInformation` at `0x18006581d`
- `ADVAPI32!EventSetInformation` at `0x180065921`
- `ADVAPI32!EventSetInformation` at `0x180065a67`
- `ADVAPI32!EventSetInformation` at `0x18006581d`
- `ADVAPI32!EventSetInformation` at `0x180065921`
- `ADVAPI32!EventSetInformation` at `0x180065a67`
- `ADVAPI32!EventRegister` at `0x1800657fc`
- `ADVAPI32!EventRegister` at `0x180065900`
- `ADVAPI32!EventRegister` at `0x180065a46`
- `ADVAPI32!EventRegister` at `0x1800657fc`
- `ADVAPI32!EventRegister` at `0x180065900`
- `ADVAPI32!EventRegister` at `0x180065a46`
- `ADVAPI32!EventUnregister` at `0x180065b5c`
- `ADVAPI32!EventUnregister` at `0x180065b5c`
- `SHLWAPI!StrCmpNIA` at `0x1800659ed`
- `SHLWAPI!StrCmpNIA` at `0x1800659ed`

## pseudocode

```c
void __fastcall HHUrlSecurityManager::CheckAndSetSafeMode(HHUrlSecurityManager *this, const char *a2, HWND a3)
{
  __int16 *v5; // rax
  REGHANDLE v6; // rcx
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  GUID ProviderId; // [rsp+40h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp+17h] BYREF
  __int16 *v10; // [rsp+60h] [rbp+27h]
  int v11; // [rsp+68h] [rbp+2Fh]
  int v12; // [rsp+6Ch] [rbp+33h]
  __int64 *v13; // [rsp+70h] [rbp+37h]
  __int64 v14; // [rsp+78h] [rbp+3Fh]

  if ( g_fShortcutsAllowedInProcess )
  {
    if ( *(_DWORD *)&dword_18008C2CC )
    {
      if ( *(_DWORD *)&dword_18008C2CC == 1 )
      {
        g_fShortcutsAllowedInProcess = 0;
        ProviderId = *(GUID *)&(*off_18008B2D8)[-8];
        if ( RegHandle )
          __fastfail(5u);
        xmmword_18008B2F8 = 0;
        if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18008B2D0, &RegHandle) )
          EventSetInformation(RegHandle, 2, (__int16 *)off_18008B2D8, *(unsigned __int16 *)off_18008B2D8);
        if ( (unsigned int)dword_18008B2D0 <= 5
          || (qword_18008B2E0 & 0x400000000000LL) == 0
          || (qword_18008B2E8 & 0x400000000000LL) != qword_18008B2E8 )
        {
          goto LABEL_35;
        }
        v7 = 0x2000000;
        v13 = &v7;
        *(_DWORD *)&ProviderId.Data2 = 5;
        UserData.Ptr = (ULONGLONG)off_18008B2D8;
        v14 = 8;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18008B2D8;
        v5 = (__int16 *)&unk_180080D18;
        v11 = 41;
        goto LABEL_34;
      }
      if ( *(_DWORD *)&dword_18008C2CC == 2 )
      {
        ProviderId = *(GUID *)&(*off_18008B2D8)[-8];
        if ( RegHandle )
          __fastfail(5u);
        xmmword_18008B2F8 = 0;
        if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18008B2D0, &RegHandle) )
          EventSetInformation(RegHandle, 2, (__int16 *)off_18008B2D8, *(unsigned __int16 *)off_18008B2D8);
        if ( (unsigned int)dword_18008B2D0 <= 5
          || (qword_18008B2E0 & 0x400000000000LL) == 0
          || (qword_18008B2E8 & 0x400000000000LL) != qword_18008B2E8 )
        {
          goto LABEL_35;
        }
        v7 = 0x2000000;
        v13 = &v7;
        *(_DWORD *)&ProviderId.Data2 = 5;
        UserData.Ptr = (ULONGLONG)off_18008B2D8;
        v14 = 8;
        ProviderId.Data1 = 184549376;
        *(_QWORD *)ProviderId.Data4 = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18008B2D8;
        v5 = (__int16 *)&byte_180080CDF;
        v11 = 45;
LABEL_34:
        v10 = v5;
        UserData.Reserved = 2;
        v12 = 1;
        EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 3u, &UserData);
LABEL_35:
        v6 = RegHandle;
        dword_18008B2D0 = 0;
        RegHandle = 0;
        EventUnregister(v6);
        return;
      }
    }
    if ( !a2
      || !a3
      || (!(unsigned int)IsCompiledURL(a2) || !(unsigned int)IsHtmlHelpCreatedWindow(a3)) && StrCmpNIA("hcp:", a2, 4) )
    {
      g_fShortcutsAllowedInProcess = 0;
      ProviderId = *(GUID *)&(*off_18008B2D8)[-8];
      if ( RegHandle )
        __fastfail(5u);
      xmmword_18008B2F8 = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18008B2D0, &RegHandle) )
        EventSetInformation(RegHandle, 2, (__int16 *)off_18008B2D8, *(unsigned __int16 *)off_18008B2D8);
      if ( (unsigned int)dword_18008B2D0 <= 5
        || (qword_18008B2E0 & 0x400000000000LL) == 0
        || (qword_18008B2E8 & 0x400000000000LL) != qword_18008B2E8 )
      {
        goto LABEL_35;
      }
      v7 = 0x2000000;
      v13 = &v7;
      *(_DWORD *)&ProviderId.Data2 = 5;
      UserData.Ptr = (ULONGLONG)off_18008B2D8;
      v14 = 8;
      ProviderId.Data1 = 184549376;
      *(_QWORD *)ProviderId.Data4 = 0x400000000000LL;
      UserData.Size = *(unsigned __int16 *)off_18008B2D8;
      v5 = word_180080CB2;
      v11 = 33;
      goto LABEL_34;
    }
  }
}

```

## disassembly

```asm
0x180065760  mov     [rsp-8+arg_0], rbx
0x180065765  mov     [rsp-8+arg_18], rdi
0x18006576a  push    rbp
0x18006576b  lea     rbp, [rsp-57h]
0x180065770  sub     rsp, 90h
0x180065777  mov     rax, cs:__security_cookie
0x18006577e  xor     rax, rsp
0x180065781  mov     [rbp+57h+var_10], rax
0x180065785  cmp     cs:?g_fShortcutsAllowedInProcess@@3HA, 0; int g_fShortcutsAllowedInProcess
0x18006578c  mov     rdi, r8
0x18006578f  mov     rbx, rdx
0x180065792  jz      loc_180065B62
0x180065798  mov     eax, cs:dword_18008C2CC
0x18006579e  test    eax, eax
0x1800657a0  jz      loc_1800659B7
0x1800657a6  sub     eax, 1
0x1800657a9  jz      loc_1800658B5
0x1800657af  cmp     eax, 1
0x1800657b2  jnz     loc_1800659B7
0x1800657b8  cmp     cs:RegHandle, 0
0x1800657c0  mov     rax, cs:off_18008B2D8
0x1800657c7  movups  xmm0, xmmword ptr [rax-10h]
0x1800657cb  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x1800657cf  jz      short loc_1800657D8
0x1800657d1  mov     ecx, 5
0x1800657d6  int     29h; Win8: RtlFailFast(ecx)
0x1800657d8  xorps   xmm0, xmm0
0x1800657db  lea     r9, RegHandle; RegHandle
0x1800657e2  lea     r8, dword_18008B2D0; CallbackContext
0x1800657e9  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800657f0  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x1800657f4  movdqu  cs:xmmword_18008B2F8, xmm0
0x1800657fc  call    cs:__imp_EventRegister
0x180065802  test    eax, eax
0x180065804  jnz     short loc_180065823
0x180065806  mov     r8, cs:off_18008B2D8
0x18006580d  mov     edx, 2
0x180065812  mov     rcx, cs:RegHandle
0x180065819  movzx   r9d, word ptr [r8]
0x18006581d  call    cs:__imp_EventSetInformation
0x180065823  mov     eax, cs:dword_18008B2D0
0x180065829  xor     ebx, ebx
0x18006582b  cmp     eax, 5
0x18006582e  jbe     loc_180065B48
0x180065834  mov     rdx, cs:qword_18008B2E8
0x18006583b  mov     rcx, 400000000000h
0x180065845  mov     rax, cs:qword_18008B2E0
0x18006584c  test    rcx, rax
0x18006584f  jz      loc_180065B48
0x180065855  mov     rax, rdx
0x180065858  and     rax, rcx
0x18006585b  cmp     rax, rdx
0x18006585e  jnz     loc_180065B48
0x180065864  lea     rax, [rbp+57h+var_58]
0x180065868  mov     [rbp+57h+var_58], 2000000h
0x180065870  mov     [rbp+57h+var_20], rax
0x180065874  movzx   eax, cs:word_180080CD5
0x18006587b  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18006587e  mov     rax, cs:off_18008B2D8
0x180065885  mov     [rbp+57h+var_40.Ptr], rax
0x180065889  mov     [rbp+57h+var_18], 8
0x180065891  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x180065898  mov     qword ptr [rbp+57h+ProviderId.Data4], rcx
0x18006589c  movzx   eax, word ptr [rax]
0x18006589f  mov     [rbp+57h+var_40.Size], eax
0x1800658a2  lea     rax, byte_180080CDF
0x1800658a9  mov     [rbp+57h+var_28], 2Dh ; '-'
0x1800658b0  jmp     loc_180065AF8
0x1800658b5  mov     rax, cs:off_18008B2D8
0x1800658bc  xor     ebx, ebx
0x1800658be  cmp     cs:RegHandle, rbx
0x1800658c5  mov     cs:?g_fShortcutsAllowedInProcess@@3HA, ebx; int g_fShortcutsAllowedInProcess
0x1800658cb  movups  xmm0, xmmword ptr [rax-10h]
0x1800658cf  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x1800658d3  jz      short loc_1800658DC
0x1800658d5  mov     ecx, 5
0x1800658da  int     29h; Win8: RtlFailFast(ecx)
0x1800658dc  xorps   xmm0, xmm0
0x1800658df  lea     r9, RegHandle; RegHandle
0x1800658e6  lea     r8, dword_18008B2D0; CallbackContext
0x1800658ed  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800658f4  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x1800658f8  movdqu  cs:xmmword_18008B2F8, xmm0
0x180065900  call    cs:__imp_EventRegister
0x180065906  test    eax, eax
0x180065908  jnz     short loc_180065927
0x18006590a  mov     r8, cs:off_18008B2D8
0x180065911  mov     edx, 2
0x180065916  mov     rcx, cs:RegHandle
0x18006591d  movzx   r9d, word ptr [r8]
0x180065921  call    cs:__imp_EventSetInformation
0x180065927  mov     eax, cs:dword_18008B2D0
0x18006592d  cmp     eax, 5
0x180065930  jbe     loc_180065B48
0x180065936  mov     rdx, cs:qword_18008B2E8
0x18006593d  mov     rcx, 400000000000h
0x180065947  mov     rax, cs:qword_18008B2E0
0x18006594e  test    rcx, rax
0x180065951  jz      loc_180065B48
0x180065957  mov     rax, rdx
0x18006595a  and     rax, rcx
0x18006595d  cmp     rax, rdx
0x180065960  jnz     loc_180065B48
0x180065966  lea     rax, [rbp+57h+var_58]
0x18006596a  mov     [rbp+57h+var_58], 2000000h
0x180065972  mov     [rbp+57h+var_20], rax
0x180065976  movzx   eax, cs:word_180080D0E
0x18006597d  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x180065980  mov     rax, cs:off_18008B2D8
0x180065987  mov     [rbp+57h+var_40.Ptr], rax
0x18006598b  mov     [rbp+57h+var_18], 8
0x180065993  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18006599a  mov     qword ptr [rbp+57h+ProviderId.Data4], rcx
0x18006599e  movzx   eax, word ptr [rax]
0x1800659a1  mov     [rbp+57h+var_40.Size], eax
0x1800659a4  lea     rax, unk_180080D18
0x1800659ab  mov     [rbp+57h+var_28], 29h ; ')'
0x1800659b2  jmp     loc_180065AF8
0x1800659b7  test    rbx, rbx
0x1800659ba  jz      short loc_1800659FB
0x1800659bc  test    rdi, rdi
0x1800659bf  jz      short loc_1800659FB
0x1800659c1  mov     rcx, rbx; char *
0x1800659c4  call    ?IsCompiledURL@@YAHPEBD@Z; IsCompiledURL(char const *)
0x1800659c9  test    eax, eax
0x1800659cb  jz      short loc_1800659DD
0x1800659cd  mov     rcx, rdi; HWND
0x1800659d0  call    ?IsHtmlHelpCreatedWindow@@YAHPEAUHWND__@@@Z; IsHtmlHelpCreatedWindow(HWND__ *)
0x1800659d5  test    eax, eax
0x1800659d7  jnz     loc_180065B62
0x1800659dd  mov     r8d, 4; nChar
0x1800659e3  lea     rcx, psz1; "hcp:"
0x1800659ea  mov     rdx, rbx; psz2
0x1800659ed  call    cs:__imp_StrCmpNIA
0x1800659f3  test    eax, eax
0x1800659f5  jz      loc_180065B62
0x1800659fb  mov     rax, cs:off_18008B2D8
0x180065a02  xor     ebx, ebx
0x180065a04  cmp     cs:RegHandle, rbx
0x180065a0b  mov     cs:?g_fShortcutsAllowedInProcess@@3HA, ebx; int g_fShortcutsAllowedInProcess
0x180065a11  movups  xmm0, xmmword ptr [rax-10h]
0x180065a15  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180065a19  jz      short loc_180065A22
0x180065a1b  mov     ecx, 5
0x180065a20  int     29h; Win8: RtlFailFast(ecx)
0x180065a22  xorps   xmm0, xmm0
0x180065a25  lea     r9, RegHandle; RegHandle
0x180065a2c  lea     r8, dword_18008B2D0; CallbackContext
0x180065a33  lea     rdx, _tlgEnableCallback; EnableCallback
0x180065a3a  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180065a3e  movdqu  cs:xmmword_18008B2F8, xmm0
0x180065a46  call    cs:__imp_EventRegister
0x180065a4c  test    eax, eax
0x180065a4e  jnz     short loc_180065A6D
0x180065a50  mov     r8, cs:off_18008B2D8
0x180065a57  mov     edx, 2
0x180065a5c  mov     rcx, cs:RegHandle
0x180065a63  movzx   r9d, word ptr [r8]
0x180065a67  call    cs:__imp_EventSetInformation
0x180065a6d  mov     eax, cs:dword_18008B2D0
0x180065a73  cmp     eax, 5
0x180065a76  jbe     loc_180065B48
0x180065a7c  mov     rdx, cs:qword_18008B2E8
0x180065a83  mov     rcx, 400000000000h
0x180065a8d  mov     rax, cs:qword_18008B2E0
0x180065a94  test    rcx, rax
0x180065a97  jz      loc_180065B48
0x180065a9d  mov     rax, rdx
0x180065aa0  and     rax, rcx
0x180065aa3  cmp     rax, rdx
0x180065aa6  jnz     loc_180065B48
0x180065aac  lea     rax, [rbp+57h+var_58]
0x180065ab0  mov     [rbp+57h+var_58], 2000000h
0x180065ab8  mov     [rbp+57h+var_20], rax
0x180065abc  movzx   eax, cs:word_180080CA8
0x180065ac3  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x180065ac6  mov     rax, cs:off_18008B2D8
0x180065acd  mov     [rbp+57h+var_40.Ptr], rax
0x180065ad1  mov     [rbp+57h+var_18], 8
0x180065ad9  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x180065ae0  mov     qword ptr [rbp+57h+ProviderId.Data4], rcx
0x180065ae4  movzx   eax, word ptr [rax]
0x180065ae7  mov     [rbp+57h+var_40.Size], eax
0x180065aea  lea     rax, word_180080CB2
0x180065af1  mov     [rbp+57h+var_28], 21h ; '!'
0x180065af8  mov     [rbp+57h+var_30], rax
0x180065afc  lea     rcx, _TraceLoggingMetadata
0x180065b03  lea     rax, _TraceLoggingMetadataEnd
0x180065b0a  mov     dword ptr [rbp+57h+var_40.0Ch], 2
0x180065b11  sub     eax, ecx
0x180065b13  mov     [rbp+57h+var_24], 1
0x180065b1a  mov     [rbp+57h+var_60], eax
0x180065b1d  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x180065b21  mov     eax, [rbp+57h+var_60]
0x180065b24  xor     r9d, r9d; RelatedActivityId
0x180065b27  mov     rcx, cs:RegHandle; RegHandle
0x180065b2e  lea     rax, [rbp+57h+var_40]
0x180065b32  mov     [rsp+90h+UserData], rax; UserData
0x180065b37  xor     r8d, r8d; ActivityId
0x180065b3a  mov     [rsp+90h+UserDataCount], 3; UserDataCount
0x180065b42  call    cs:__imp_EventWriteTransfer
0x180065b48  mov     rcx, cs:RegHandle; RegHandle
0x180065b4f  mov     cs:dword_18008B2D0, ebx
0x180065b55  mov     cs:RegHandle, rbx
0x180065b5c  call    cs:__imp_EventUnregister
0x180065b62  mov     rcx, [rbp+57h+var_10]
0x180065b66  xor     rcx, rsp; StackCookie
0x180065b69  call    __security_check_cookie
0x180065b6e  lea     r11, [rsp+90h+var_s0]
0x180065b76  mov     rbx, [r11+10h]
0x180065b7a  mov     rdi, [r11+28h]
0x180065b7e  mov     rsp, r11
0x180065b81  pop     rbp
0x180065b82  retn
```
