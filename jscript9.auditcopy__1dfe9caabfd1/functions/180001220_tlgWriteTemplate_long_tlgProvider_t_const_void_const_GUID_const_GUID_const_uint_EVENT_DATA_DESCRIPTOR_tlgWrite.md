# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001220`
- end: `0x18000142d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `525`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180221d84`

## callees

- `0x180001220`
- `0x1803466d4`
- `0x1803481f0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!EventWriteEx` at `0x1800013ff`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventWriteEx` at `0x1800013ff`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1800013a7`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1800013a7`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180001397`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180001397`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180001386`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180001386`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000131d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180001358`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180001372`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000131d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180001358`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180001372`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180001345`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180001345`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  ULONG v7; // edi
  int v8; // eax
  int DWORD; // ebx
  __int64 v10; // rdx
  bool *v11; // rcx
  __int64 v12; // r8
  const char *v13; // r9
  BOOL v14; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int8 *v18; // [rsp+70h] [rbp-68h]
  int v19; // [rsp+78h] [rbp-60h]
  int v20; // [rsp+7Ch] [rbp-5Ch]
  __int64 v21; // [rsp+80h] [rbp-58h]
  __int64 v22; // [rsp+88h] [rbp-50h]
  __int64 v23; // [rsp+90h] [rbp-48h]
  __int64 v24; // [rsp+98h] [rbp-40h]
  __int64 v25; // [rsp+A0h] [rbp-38h]
  __int64 v26; // [rsp+A8h] [rbp-30h]

  v25 = a7;
  v23 = a6;
  v7 = 0;
  v21 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1804300F0;
  v26 = 4;
  v24 = 4;
  v22 = 8;
  UserData.Size = *(unsigned __int16 *)off_1804300F0;
  v8 = *(unsigned __int16 *)(a2 + 11);
  UserData.Reserved = 2;
  v18 = a2 + 11;
  v19 = v8;
  v20 = 1;
  if ( *(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 35LL) )
    return EventWriteEx(RegHandle, &EventDescriptor, 0, v7, 0, 0, 5u, &UserData);
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
    goto LABEL_14;
  if ( dword_18043E620 != 2 )
  {
    if ( dword_18043E620 != 1 )
      return EventWriteEx(RegHandle, &EventDescriptor, 0, v7, 0, 0, 5u, &UserData);
    goto LABEL_14;
  }
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) && DWORD == 2 )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435512) )
      GetInPrivateFromBrowserSession(v11, v10, v12, v13);
    LOBYTE(v14) = LCIEIsCurrentProcessUsingInPrivateComponents();
    goto LABEL_11;
  }
  if ( !LCIEIsCurrentProcessInPrivateOverrideSet() )
  {
LABEL_14:
    v7 = 2;
    return EventWriteEx(RegHandle, &EventDescriptor, 0, v7, 0, 0, 5u, &UserData);
  }
  v14 = LCIEIsCurrentProcessInPrivate();
  if ( DWORD != 3 )
    dword_18043E620 = v14;
LABEL_11:
  if ( v14 )
    goto LABEL_14;
  return EventWriteEx(RegHandle, &EventDescriptor, 0, v7, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x180001220  mov     r11, rsp
0x180001223  mov     [r11+20h], r9
0x180001227  mov     [r11+18h], r8
0x18000122b  mov     [r11+10h], rdx
0x18000122f  mov     [r11+8], rcx
0x180001233  push    rbx
0x180001234  push    rsi
0x180001235  push    rdi
0x180001236  sub     rsp, 0C0h
0x18000123d  mov     rax, cs:__security_cookie
0x180001244  xor     rax, rsp
0x180001247  mov     [rsp+0D8h+var_28], rax
0x18000124f  mov     rax, [rsp+0D8h+arg_30]
0x180001257  mov     rcx, rdx
0x18000125a  mov     [r11-38h], rax
0x18000125e  add     rcx, 0Bh
0x180001262  mov     rax, [rsp+0D8h+arg_28]
0x18000126a  xor     esi, esi
0x18000126c  mov     [r11-48h], rax
0x180001270  mov     edi, esi
0x180001272  mov     rax, [rsp+0D8h+arg_20]
0x18000127a  mov     [r11-58h], rax
0x18000127e  movzx   eax, byte ptr [rdx]
0x180001281  shl     eax, 18h
0x180001284  mov     dword ptr [rsp+0D8h+EventDescriptor.Id], eax
0x180001288  movzx   eax, word ptr [rdx+1]
0x18000128c  mov     dword ptr [rsp+0D8h+EventDescriptor.Level], eax
0x180001290  mov     rax, [rdx+3]
0x180001294  mov     [rsp+0D8h+EventDescriptor.Keyword], rax
0x180001299  mov     rax, cs:off_1804300F0
0x1800012a0  mov     [r11-78h], rax
0x1800012a4  mov     qword ptr [r11-30h], 4
0x1800012ac  mov     qword ptr [r11-40h], 4
0x1800012b4  mov     qword ptr [r11-50h], 8
0x1800012bc  movzx   eax, word ptr [rax]
0x1800012bf  mov     [rsp+0D8h+var_78.Size], eax
0x1800012c3  movzx   eax, word ptr [rcx]
0x1800012c6  mov     dword ptr [rsp+0D8h+var_78.0Ch], 2
0x1800012ce  mov     [r11-68h], rcx
0x1800012d2  lea     rcx, _TraceLoggingMetadata
0x1800012d9  mov     [rsp+0D8h+var_60], eax
0x1800012dd  lea     rax, _TraceLoggingMetadataEnd
0x1800012e4  sub     eax, ecx
0x1800012e6  mov     [rsp+0D8h+var_5C], 1
0x1800012ee  mov     ecx, cs:_tls_index
0x1800012f4  mov     [rsp+0D8h+var_98], eax
0x1800012f8  mov     eax, [rsp+0D8h+var_98]
0x1800012fc  mov     rax, gs:58h
0x180001305  mov     edx, 23h ; '#'
0x18000130a  mov     rax, [rax+rcx*8]
0x18000130e  cmp     [rdx+rax], sil
0x180001312  jnz     loc_1800013D1
0x180001318  mov     ecx, 20000019h
0x18000131d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180001324  nop     dword ptr [rax+rax+00h]
0x180001329  test    al, al
0x18000132b  jz      loc_1800013CC
0x180001331  mov     eax, cs:dword_18043E620
0x180001337  cmp     eax, 2
0x18000133a  jnz     loc_1800013C7
0x180001340  mov     ecx, 1000002Dh
0x180001345  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18000134c  nop     dword ptr [rax+rax+00h]
0x180001351  mov     ecx, 20000002h
0x180001356  mov     ebx, eax
0x180001358  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18000135f  nop     dword ptr [rax+rax+00h]
0x180001364  test    al, al
0x180001366  jnz     short loc_180001397
0x180001368  cmp     ebx, 2
0x18000136b  jnz     short loc_180001397
0x18000136d  mov     ecx, 10000038h
0x180001372  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180001379  nop     dword ptr [rax+rax+00h]
0x18000137e  test    al, al
0x180001380  jz      loc_180001427
0x180001386  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x18000138d  nop     dword ptr [rax+rax+00h]
0x180001392  movzx   ecx, al
0x180001395  jmp     short loc_1800013C1
0x180001397  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18000139e  nop     dword ptr [rax+rax+00h]
0x1800013a3  test    al, al
0x1800013a5  jz      short loc_1800013CC
0x1800013a7  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1800013ae  nop     dword ptr [rax+rax+00h]
0x1800013b3  movzx   ecx, al
0x1800013b6  cmp     ebx, 3
0x1800013b9  jz      short loc_1800013C1
0x1800013bb  mov     cs:dword_18043E620, ecx
0x1800013c1  test    cl, cl
0x1800013c3  jz      short loc_1800013D1
0x1800013c5  jmp     short loc_1800013CC
0x1800013c7  cmp     eax, 1
0x1800013ca  jnz     short loc_1800013D1
0x1800013cc  mov     edi, 2
0x1800013d1  mov     rcx, cs:RegHandle; RegHandle
0x1800013d8  lea     rax, [rsp+0D8h+var_78]
0x1800013dd  mov     [rsp+0D8h+UserData], rax; UserData
0x1800013e2  lea     rdx, [rsp+0D8h+EventDescriptor]; EventDescriptor
0x1800013e7  mov     [rsp+0D8h+UserDataCount], 5; UserDataCount
0x1800013ef  mov     r9d, edi; Flags
0x1800013f2  mov     [rsp+0D8h+RelatedActivityId], rsi; RelatedActivityId
0x1800013f7  xor     r8d, r8d; Filter
0x1800013fa  mov     [rsp+0D8h+ActivityId], rsi; ActivityId
0x1800013ff  call    cs:__imp_EventWriteEx
0x180001406  nop     dword ptr [rax+rax+00h]
0x18000140b  mov     rcx, [rsp+0D8h+var_28]
0x180001413  xor     rcx, rsp; StackCookie
0x180001416  call    __security_check_cookie
0x18000141b  add     rsp, 0C0h
0x180001422  pop     rdi
0x180001423  pop     rsi
0x180001424  pop     rbx
0x180001425  retn
0x180001427  call    ?GetInPrivateFromBrowserSession@@YAJPEA_N@Z; GetInPrivateFromBrowserSession(bool *)
```
