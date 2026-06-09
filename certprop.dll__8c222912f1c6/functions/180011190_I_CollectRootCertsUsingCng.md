# I_CollectRootCertsUsingCng

- ea: `0x180011190`
- end: `0x1800115b6`
- name: `I_CollectRootCertsUsingCng`
- size: `1062`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180012690`

## callees

- `0x180004600`
- `0x180006010`
- `0x180011190`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001121b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001122a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001152b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001121b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001122a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001152b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800112be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001151c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800112be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001151c`
- `CRYPT32!CertCloseStore` at `0x18001133a`
- `CRYPT32!CertCloseStore` at `0x180011459`
- `CRYPT32!CertCloseStore` at `0x18001133a`
- `CRYPT32!CertCloseStore` at `0x180011459`
- `ncrypt!NCryptFreeObject` at `0x180011438`
- `ncrypt!NCryptFreeObject` at `0x180011438`
- `ncrypt!NCryptGetProperty` at `0x18001136e`
- `ncrypt!NCryptGetProperty` at `0x1800113db`
- `ncrypt!NCryptGetProperty` at `0x18001136e`
- `ncrypt!NCryptGetProperty` at `0x1800113db`

## pseudocode

```c
__int64 __fastcall I_CollectRootCertsUsingCng(__int64 a1, unsigned int *a2)
{
  unsigned int Property; // ebx
  __int64 v5; // rcx
  unsigned int v6; // r15d
  NCRYPT_HANDLE *v7; // rsi
  HCERTSTORE *v8; // rdi
  void *v9; // rcx
  __int64 v10; // rcx
  STRSAFE_LPSTR v11; // rcx
  int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-79h] BYREF
  DWORD pcbResult; // [rsp+34h] [rbp-75h] BYREF
  _DWORD v18[2]; // [rsp+38h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-69h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-59h] BYREF
  GUID v21; // [rsp+60h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-39h] BYREF
  int *v23; // [rsp+80h] [rbp-29h]
  int v24; // [rsp+88h] [rbp-21h]
  int v25; // [rsp+8Ch] [rbp-1Dh]
  unsigned int *v26; // [rsp+90h] [rbp-19h]
  __int64 v27; // [rsp+98h] [rbp-11h]
  _DWORD *v28; // [rsp+A0h] [rbp-9h]
  __int64 v29; // [rsp+A8h] [rbp-1h]

  Property = 0;
  pcbResult = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v21 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v21);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v23 = (int *)byte_180029E45;
    UserData.Reserved = 2;
    v24 = 36;
    v25 = 1;
    v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v21, &ActivityId, 2u, &UserData);
  }
  v6 = I_SetupNCryptStorageProvider(a1);
  if ( !v6 )
  {
    v8 = (HCERTSTORE *)(a1 + 176);
    v9 = *(void **)(a1 + 176);
    if ( v9 )
    {
      CertCloseStore(v9, 0);
      *v8 = 0;
    }
    v7 = (NCRYPT_HANDLE *)(a1 + 136);
    Property = NCryptGetProperty(
                 *(_QWORD *)(a1 + 136),
                 L"SmartcardRootCertStore",
                 (PBYTE)(a1 + 176),
                 8u,
                 &pcbResult,
                 0x40u);
    if ( Property )
    {
      WppTraceIndent(v10, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_26;
      }
      v12 = 162;
    }
    else
    {
      Property = NCryptGetProperty(*v7, L"SmartCardGuid", (PBYTE)(a1 + 24), 0x10u, &pcbResult, 0x40u);
      if ( !Property )
        goto LABEL_26;
      WppTraceIndent(v13, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_26;
      }
      v12 = 163;
    }
    WPP_SF_sD(
      *((_QWORD *)v11 + 2),
      v12,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      Property);
    goto LABEL_26;
  }
  WppTraceIndent(v5, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      161,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
  }
  v7 = (NCRYPT_HANDLE *)(a1 + 136);
  v8 = (HCERTSTORE *)(a1 + 176);
LABEL_26:
  if ( *v7 )
  {
    NCryptFreeObject(*v7);
    *v7 = 0;
  }
  if ( !Property )
    Property = v6;
  if ( Property && *v8 )
  {
    CertCloseStore(*v8, 0);
    *v8 = 0;
  }
  if ( (unsigned int)dword_180031008 > 5 )
  {
    v16 = *a2;
    EventDescriptor.Keyword = 0;
    v26 = &v16;
    v27 = 4;
    v28 = v18;
    *(_DWORD *)&EventDescriptor.Level = 517;
    UserData.Ptr = (ULONGLONG)off_180031010;
    v18[0] = Property;
    v29 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v23 = &dword_18002AB34;
    UserData.Reserved = 2;
    v24 = 64;
    v25 = 1;
    v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v21, &ActivityId, 4u, &UserData);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( !Property )
  {
    *(_DWORD *)(a1 + 220) = *a2;
    *(_DWORD *)(a1 + 228) = 3;
  }
  WppTraceIndent(v14, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      164,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      Property);
  }
  return Property;
}

```

## disassembly

```asm
0x180011190  push    rbp
0x180011192  push    rbx
0x180011193  push    rsi
0x180011194  push    rdi
0x180011195  push    r12
0x180011197  push    r13
0x180011199  push    r14
0x18001119b  push    r15
0x18001119d  lea     rbp, [rsp-1Fh]
0x1800111a2  sub     rsp, 0C8h
0x1800111a9  mov     rax, cs:__security_cookie
0x1800111b0  xor     rax, rsp
0x1800111b3  mov     [rbp+57h+var_50], rax
0x1800111b7  mov     r12, rdx
0x1800111ba  xor     ebx, ebx
0x1800111bc  xor     edx, edx
0x1800111be  mov     [rbp+57h+pcbResult], ebx
0x1800111c1  mov     r14, rcx
0x1800111c4  call    WppTraceIndent
0x1800111c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111d0  lea     rdi, WPP_GLOBAL_Control
0x1800111d7  cmp     rcx, rdi
0x1800111da  jz      short loc_180011204
0x1800111dc  test    byte ptr [rcx+1Ch], 2
0x1800111e0  jz      short loc_180011204
0x1800111e2  cmp     byte ptr [rcx+19h], 5
0x1800111e6  jb      short loc_180011204
0x1800111e8  mov     r9, cs:WPP_pszIndent
0x1800111ef  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800111f6  mov     rcx, [rcx+10h]
0x1800111fa  mov     edx, 0A0h
0x1800111ff  call    WPP_SF_s
0x180011204  xorps   xmm0, xmm0
0x180011207  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18001120b  xorps   xmm1, xmm1
0x18001120e  mov     ecx, 5; ControlCode
0x180011213  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180011217  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm1
0x18001121b  call    cs:__imp_EventActivityIdControl
0x180011221  lea     rdx, [rbp+57h+var_A0]; ActivityId
0x180011225  mov     ecx, 1; ControlCode
0x18001122a  call    cs:__imp_EventActivityIdControl
0x180011230  mov     eax, cs:dword_180031008
0x180011236  lea     r13, _TraceLoggingMetadataEnd
0x18001123d  lea     rcx, _TraceLoggingMetadata
0x180011244  cmp     eax, 5
0x180011247  jbe     short loc_1800112C4
0x180011249  movzx   eax, cs:word_180029E3B
0x180011250  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x180011254  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180011257  lea     r8, [rbp+57h+var_A0]; ActivityId
0x18001125b  mov     rax, cs:off_180031010
0x180011262  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180011266  mov     [rbp+57h+var_90.Ptr], rax
0x18001126a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180011271  mov     [rbp+57h+EventDescriptor.Keyword], rbx
0x180011275  movzx   eax, word ptr [rax]
0x180011278  mov     [rbp+57h+var_90.Size], eax
0x18001127b  lea     rax, byte_180029E45
0x180011282  mov     [rbp+57h+var_80], rax
0x180011286  mov     rax, r13
0x180011289  sub     eax, ecx
0x18001128b  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180011292  mov     [rbp+57h+var_78], 24h ; '$'
0x180011299  mov     [rbp+57h+var_74], 1
0x1800112a0  mov     [rbp+57h+var_D0], eax
0x1800112a3  mov     eax, [rbp+57h+var_D0]
0x1800112a6  mov     rcx, cs:RegHandle; RegHandle
0x1800112ad  lea     rax, [rbp+57h+var_90]
0x1800112b1  mov     [rsp+100h+UserData], rax; UserData
0x1800112b6  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x1800112be  call    cs:__imp_EventWriteTransfer
0x1800112c4  mov     rcx, r14
0x1800112c7  call    I_SetupNCryptStorageProvider
0x1800112cc  mov     r15d, eax
0x1800112cf  test    eax, eax
0x1800112d1  jz      short loc_180011329
0x1800112d3  mov     edx, 2
0x1800112d8  call    WppTraceIndent
0x1800112dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112e4  cmp     rcx, rdi
0x1800112e7  jz      short loc_180011316
0x1800112e9  test    byte ptr [rcx+1Ch], 1
0x1800112ed  jz      short loc_180011316
0x1800112ef  cmp     byte ptr [rcx+19h], 2
0x1800112f3  jb      short loc_180011316
0x1800112f5  mov     r9, cs:WPP_pszIndent
0x1800112fc  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180011303  mov     rcx, [rcx+10h]
0x180011307  mov     edx, 0A1h
0x18001130c  mov     [rsp+100h+UserDataCount], r15d
0x180011311  call    WPP_SF_sD
0x180011316  lea     rsi, [r14+88h]
0x18001131d  lea     rdi, [r14+0B0h]
0x180011324  jmp     loc_180011430
0x180011329  lea     rdi, [r14+0B0h]
0x180011330  mov     rcx, [rdi]; hCertStore
0x180011333  test    rcx, rcx
0x180011336  jz      short loc_180011343
0x180011338  xor     edx, edx; dwFlags
0x18001133a  call    cs:__imp_CertCloseStore
0x180011340  mov     [rdi], rbx
0x180011343  lea     rax, [rbp+57h+pcbResult]
0x180011347  mov     dword ptr [rsp+100h+UserData], 40h ; '@'; dwFlags
0x18001134f  lea     rsi, [r14+88h]
0x180011356  mov     qword ptr [rsp+100h+UserDataCount], rax; pcbResult
0x18001135b  mov     rcx, [rsi]; hObject
0x18001135e  lea     rdx, aSmartcardrootc; "SmartcardRootCertStore"
0x180011365  mov     r9d, 8; cbOutput
0x18001136b  mov     r8, rdi; pbOutput
0x18001136e  call    cs:__imp_NCryptGetProperty
0x180011374  mov     ebx, eax
0x180011376  test    eax, eax
0x180011378  jz      short loc_1800113B6
0x18001137a  mov     edx, 2
0x18001137f  call    WppTraceIndent
0x180011384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001138b  lea     rax, WPP_GLOBAL_Control
0x180011392  cmp     rcx, rax
0x180011395  jz      loc_180011430
0x18001139b  test    byte ptr [rcx+1Ch], 1
0x18001139f  jz      loc_180011430
0x1800113a5  cmp     byte ptr [rcx+19h], 2
0x1800113a9  jb      loc_180011430
0x1800113af  mov     edx, 0A2h
0x1800113b4  jmp     short loc_180011415
0x1800113b6  mov     rcx, [rsi]; hObject
0x1800113b9  lea     rax, [rbp+57h+pcbResult]
0x1800113bd  lea     r8, [r14+18h]; pbOutput
0x1800113c1  mov     dword ptr [rsp+100h+UserData], 40h ; '@'; dwFlags
0x1800113c9  mov     r9d, 10h; cbOutput
0x1800113cf  mov     qword ptr [rsp+100h+UserDataCount], rax; pcbResult
0x1800113d4  lea     rdx, aSmartcardguid; "SmartCardGuid"
0x1800113db  call    cs:__imp_NCryptGetProperty
0x1800113e1  mov     ebx, eax
0x1800113e3  test    eax, eax
0x1800113e5  jz      short loc_180011430
0x1800113e7  mov     edx, 2
0x1800113ec  call    WppTraceIndent
0x1800113f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113f8  lea     rax, WPP_GLOBAL_Control
0x1800113ff  cmp     rcx, rax
0x180011402  jz      short loc_180011430
0x180011404  test    byte ptr [rcx+1Ch], 1
0x180011408  jz      short loc_180011430
0x18001140a  cmp     byte ptr [rcx+19h], 2
0x18001140e  jb      short loc_180011430
0x180011410  mov     edx, 0A3h
0x180011415  mov     r9, cs:WPP_pszIndent
0x18001141c  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180011423  mov     rcx, [rcx+10h]
0x180011427  mov     [rsp+100h+UserDataCount], ebx
0x18001142b  call    WPP_SF_sD
0x180011430  mov     rcx, [rsi]; hObject
0x180011433  test    rcx, rcx
0x180011436  jz      short loc_180011445
0x180011438  call    cs:__imp_NCryptFreeObject
0x18001143e  mov     qword ptr [rsi], 0
0x180011445  test    ebx, ebx
0x180011447  cmovz   ebx, r15d
0x18001144b  test    ebx, ebx
0x18001144d  jz      short loc_180011466
0x18001144f  mov     rcx, [rdi]; hCertStore
0x180011452  test    rcx, rcx
0x180011455  jz      short loc_180011466
0x180011457  xor     edx, edx; dwFlags
0x180011459  call    cs:__imp_CertCloseStore
0x18001145f  xor     ecx, ecx
0x180011461  mov     [rdi], rcx
0x180011464  jmp     short loc_180011468
0x180011466  xor     ecx, ecx
0x180011468  mov     eax, cs:dword_180031008
0x18001146e  cmp     eax, 5
0x180011471  jbe     loc_180011522
0x180011477  mov     eax, [r12]
0x18001147b  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x18001147f  mov     [rbp+57h+var_D0], eax
0x180011482  lea     r8, [rbp+57h+var_A0]; ActivityId
0x180011486  mov     [rbp+57h+EventDescriptor.Keyword], rcx
0x18001148a  lea     rax, [rbp+57h+var_D0]
0x18001148e  mov     [rbp+57h+var_70], rax
0x180011492  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180011496  lea     rax, [rbp+57h+var_C8]
0x18001149a  mov     [rbp+57h+var_68], 4
0x1800114a2  mov     [rbp+57h+var_60], rax
0x1800114a6  movzx   eax, cs:word_18002AB2A
0x1800114ad  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800114b0  mov     rax, cs:off_180031010
0x1800114b7  mov     [rbp+57h+var_90.Ptr], rax
0x1800114bb  mov     [rbp+57h+var_C8], ebx
0x1800114be  mov     [rbp+57h+var_58], 4
0x1800114c6  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800114cd  movzx   eax, word ptr [rax]
0x1800114d0  mov     [rbp+57h+var_90.Size], eax
0x1800114d3  lea     rax, dword_18002AB34
0x1800114da  mov     [rbp+57h+var_80], rax
0x1800114de  lea     rax, _TraceLoggingMetadata
0x1800114e5  sub     r13d, eax
0x1800114e8  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x1800114ef  mov     [rbp+57h+var_78], 40h ; '@'
0x1800114f6  mov     [rbp+57h+var_74], 1
0x1800114fd  mov     [rbp+57h+var_C4], r13d
0x180011501  mov     eax, [rbp+57h+var_C4]
0x180011504  mov     rcx, cs:RegHandle; RegHandle
0x18001150b  lea     rax, [rbp+57h+var_90]
0x18001150f  mov     [rsp+100h+UserData], rax; UserData
0x180011514  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x18001151c  call    cs:__imp_EventWriteTransfer
0x180011522  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180011526  mov     ecx, 2; ControlCode
0x18001152b  call    cs:__imp_EventActivityIdControl
0x180011531  test    ebx, ebx
0x180011533  jnz     short loc_18001154B
0x180011535  mov     eax, [r12]
0x180011539  mov     [r14+0DCh], eax
0x180011540  mov     dword ptr [r14+0E4h], 3
0x18001154b  mov     edx, 1
0x180011550  call    WppTraceIndent
0x180011555  mov     rcx, cs:WPP_GLOBAL_Control
0x18001155c  lea     rax, WPP_GLOBAL_Control
0x180011563  cmp     rcx, rax
0x180011566  jz      short loc_180011594
0x180011568  test    byte ptr [rcx+1Ch], 2
0x18001156c  jz      short loc_180011594
0x18001156e  cmp     byte ptr [rcx+19h], 5
0x180011572  jb      short loc_180011594
0x180011574  mov     r9, cs:WPP_pszIndent
0x18001157b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180011582  mov     rcx, [rcx+10h]
0x180011586  mov     edx, 0A4h
0x18001158b  mov     [rsp+100h+UserDataCount], ebx
0x18001158f  call    WPP_SF_sD
0x180011594  mov     eax, ebx
0x180011596  mov     rcx, [rbp+57h+var_50]
0x18001159a  xor     rcx, rsp; StackCookie
0x18001159d  call    __security_check_cookie
0x1800115a2  add     rsp, 0C8h
0x1800115a9  pop     r15
0x1800115ab  pop     r14
0x1800115ad  pop     r13
0x1800115af  pop     r12
0x1800115b1  pop     rdi
0x1800115b2  pop     rsi
0x1800115b3  pop     rbx
0x1800115b4  pop     rbp
0x1800115b5  retn
```
