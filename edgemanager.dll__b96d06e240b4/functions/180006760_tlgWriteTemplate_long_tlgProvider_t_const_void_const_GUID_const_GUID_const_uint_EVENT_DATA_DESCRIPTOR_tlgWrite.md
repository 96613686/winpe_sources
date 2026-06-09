# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180006760`
- end: `0x180006994`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4444@Z`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003cc0`
- `0x180035cf0`

## callees

- `0x180006760`
- `0x18002b530`
- `0x180085010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18000690c`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18000690c`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180006902`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180006902`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800068cb`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800068f7`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800068cb`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800068f7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006871`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800068ad`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800068c1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006871`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800068ad`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800068c1`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800068a0`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800068a0`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800068d6`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800068d6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18000696d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18000696d`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  ULONG v10; // ebx
  __int64 v11; // rcx
  int DWORD; // edi
  BOOL v13; // ecx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  char v16[4]; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-85h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int8 *v20; // [rsp+70h] [rbp-59h]
  int v21; // [rsp+78h] [rbp-51h]
  int v22; // [rsp+7Ch] [rbp-4Dh]
  __int64 v23; // [rsp+80h] [rbp-49h]
  __int64 v24; // [rsp+88h] [rbp-41h]
  __int64 v25; // [rsp+90h] [rbp-39h]
  __int64 v26; // [rsp+98h] [rbp-31h]
  __int64 v27; // [rsp+A0h] [rbp-29h]
  __int64 v28; // [rsp+A8h] [rbp-21h]
  __int64 v29; // [rsp+B0h] [rbp-19h]
  __int64 v30; // [rsp+B8h] [rbp-11h]
  __int64 v31; // [rsp+C0h] [rbp-9h]
  __int64 v32; // [rsp+C8h] [rbp-1h]
  __int64 v33; // [rsp+D0h] [rbp+7h]
  __int64 v34; // [rsp+D8h] [rbp+Fh]

  v33 = a10;
  v10 = 0;
  v31 = a9;
  v29 = a8;
  v27 = a7;
  v25 = a6;
  v34 = 4;
  v32 = 4;
  v30 = 4;
  v11 = *a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1800B60E0;
  v23 = v11;
  v28 = 4;
  v26 = 4;
  v24 = 16;
  UserData.Size = *(unsigned __int16 *)off_1800B60E0;
  v21 = *(unsigned __int16 *)(a2 + 11);
  v20 = a2 + 11;
  UserData.Reserved = 2;
  v22 = 1;
  v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( *(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) )
    return EventWriteEx(RegHandle, &EventDescriptor, 0, v10, 0, 0, 8u, &UserData);
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
  {
LABEL_16:
    v10 = 2;
    return EventWriteEx(RegHandle, &EventDescriptor, 0, v10, 0, 0, 8u, &UserData);
  }
  v16[0] = 1;
  if ( dword_1800B6770 == 2 )
  {
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) && DWORD == 2 )
    {
      if ( (unsigned __int8)IEConfiguration_GetBool(268435512) )
      {
        LOBYTE(v13) = LCIEIsCurrentProcessUsingInPrivateComponents();
        goto LABEL_15;
      }
      EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment();
      if ( (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment + 120LL))(
             EdgeBrowsingEnvironment,
             v16) < 0 )
      {
        LOBYTE(v13) = LCIEIsCurrentProcessUsingInPrivateComponents();
        goto LABEL_15;
      }
      goto LABEL_13;
    }
    if ( !LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
LABEL_13:
      LOBYTE(v13) = v16[0];
      goto LABEL_15;
    }
    v13 = LCIEIsCurrentProcessInPrivate();
    if ( DWORD != 3 )
      dword_1800B6770 = v13;
  }
  else
  {
    LOBYTE(v13) = dword_1800B6770 == 1;
  }
LABEL_15:
  if ( v13 )
    goto LABEL_16;
  return EventWriteEx(RegHandle, &EventDescriptor, 0, v10, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x180006760  mov     [rsp-8+arg_8], rbx
0x180006765  mov     [rsp-8+arg_10], rsi
0x18000676a  push    rbp
0x18000676b  lea     rbp, [rsp-27h]
0x180006770  sub     rsp, 0F0h
0x180006777  mov     rax, cs:__security_cookie
0x18000677e  xor     rax, rsp
0x180006781  mov     [rbp+27h+var_10], rax
0x180006785  mov     rax, [rbp+27h+arg_48]
0x180006789  xor     esi, esi
0x18000678b  mov     [rbp+27h+var_20], rax
0x18000678f  mov     ebx, esi
0x180006791  mov     rax, [rbp+27h+arg_40]
0x180006795  mov     [rbp+27h+var_30], rax
0x180006799  mov     rax, [rbp+27h+arg_38]
0x18000679d  mov     [rbp+27h+var_40], rax
0x1800067a1  mov     rax, [rbp+27h+arg_30]
0x1800067a5  mov     [rbp+27h+var_50], rax
0x1800067a9  mov     rax, [rbp+27h+arg_28]
0x1800067ad  mov     [rbp+27h+var_60], rax
0x1800067b1  mov     rax, [rbp+27h+arg_20]
0x1800067b5  mov     [rbp+27h+var_18], 4
0x1800067bd  mov     [rbp+27h+var_28], 4
0x1800067c5  mov     [rbp+27h+var_38], 4
0x1800067cd  mov     rcx, [rax]
0x1800067d0  movzx   eax, byte ptr [rdx]
0x1800067d3  shl     eax, 18h
0x1800067d6  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x1800067da  movzx   eax, word ptr [rdx+1]
0x1800067de  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x1800067e1  mov     rax, [rdx+3]
0x1800067e5  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x1800067e9  mov     rax, cs:off_1800B60E0
0x1800067f0  mov     [rbp+27h+var_90.Ptr], rax
0x1800067f4  mov     [rbp+27h+var_70], rcx
0x1800067f8  lea     rcx, [rdx+0Bh]
0x1800067fc  mov     [rbp+27h+var_48], 4
0x180006804  mov     [rbp+27h+var_58], 4
0x18000680c  mov     [rbp+27h+var_68], 10h
0x180006814  movzx   eax, word ptr [rax]
0x180006817  mov     [rbp+27h+var_90.Size], eax
0x18000681a  movzx   eax, word ptr [rcx]
0x18000681d  mov     [rbp+27h+var_78], eax
0x180006820  lea     rax, _TraceLoggingMetadataEnd
0x180006827  mov     [rbp+27h+var_80], rcx
0x18000682b  lea     rcx, _TraceLoggingMetadata
0x180006832  sub     eax, ecx
0x180006834  mov     dword ptr [rbp+27h+var_90.0Ch], 2
0x18000683b  mov     ecx, cs:_tls_index
0x180006841  mov     [rbp+27h+var_74], 1
0x180006848  mov     [rsp+0F0h+var_AC], eax
0x18000684c  mov     eax, [rsp+0F0h+var_AC]
0x180006850  mov     rax, gs:58h
0x180006859  mov     edx, 10h
0x18000685e  mov     rax, [rax+rcx*8]
0x180006862  cmp     [rdx+rax], sil
0x180006866  jnz     loc_180006940
0x18000686c  mov     ecx, 20000019h
0x180006871  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180006877  test    al, al
0x180006879  jz      loc_18000693B
0x18000687f  mov     eax, cs:dword_1800B6770
0x180006885  mov     [rsp+0F0h+arg_0], rdi
0x18000688d  mov     [rsp+0F0h+var_B0], 1
0x180006892  cmp     eax, 2
0x180006895  jnz     loc_180006929
0x18000689b  mov     ecx, 1000002Dh
0x1800068a0  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1800068a6  mov     ecx, 20000002h
0x1800068ab  mov     edi, eax
0x1800068ad  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800068b3  test    al, al
0x1800068b5  jnz     short loc_180006902
0x1800068b7  cmp     edi, 2
0x1800068ba  jnz     short loc_180006902
0x1800068bc  mov     ecx, 10000038h
0x1800068c1  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800068c7  test    al, al
0x1800068c9  jz      short loc_1800068D6
0x1800068cb  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800068d1  movzx   ecx, al
0x1800068d4  jmp     short loc_18000692F
0x1800068d6  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x1800068dc  mov     r8, rax
0x1800068df  lea     rdx, [rsp+0F0h+var_B0]
0x1800068e4  mov     rcx, [rax]
0x1800068e7  mov     rax, [rcx+78h]
0x1800068eb  mov     rcx, r8
0x1800068ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f3  test    eax, eax
0x1800068f5  jns     short loc_180006922
0x1800068f7  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800068fd  movzx   ecx, al
0x180006900  jmp     short loc_18000692F
0x180006902  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180006908  test    al, al
0x18000690a  jz      short loc_180006922
0x18000690c  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180006912  movzx   ecx, al
0x180006915  cmp     edi, 3
0x180006918  jz      short loc_18000692F
0x18000691a  mov     cs:dword_1800B6770, ecx
0x180006920  jmp     short loc_18000692F
0x180006922  movzx   ecx, [rsp+0F0h+var_B0]
0x180006927  jmp     short loc_18000692F
0x180006929  cmp     eax, 1
0x18000692c  setz    cl
0x18000692f  mov     rdi, [rsp+0F0h+arg_0]
0x180006937  test    cl, cl
0x180006939  jz      short loc_180006940
0x18000693b  mov     ebx, 2
0x180006940  mov     rcx, cs:RegHandle; RegHandle
0x180006947  lea     rax, [rbp+27h+var_90]
0x18000694b  mov     [rsp+0F0h+UserData], rax; UserData
0x180006950  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x180006955  mov     [rsp+0F0h+UserDataCount], 8; UserDataCount
0x18000695d  mov     r9d, ebx; Flags
0x180006960  mov     [rsp+0F0h+RelatedActivityId], rsi; RelatedActivityId
0x180006965  xor     r8d, r8d; Filter
0x180006968  mov     [rsp+0F0h+ActivityId], rsi; ActivityId
0x18000696d  call    cs:__imp_EventWriteEx
0x180006973  mov     rcx, [rbp+27h+var_10]
0x180006977  xor     rcx, rsp; StackCookie
0x18000697a  call    __security_check_cookie
0x18000697f  lea     r11, [rsp+0F0h+var_s0]
0x180006987  mov     rbx, [r11+18h]
0x18000698b  mov     rsi, [r11+20h]
0x18000698f  mov     rsp, r11
0x180006992  pop     rbp
0x180006993  retn
```
