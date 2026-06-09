# NgcPackAuthBuffer

- ea: `0x18001d500`
- end: `0x18001de3e`
- name: `NgcPackAuthBuffer`
- size: `2366`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a240`
- `0x18001c7e0`
- `0x18001d500`
- `0x18001e930`
- `0x18002cb98`
- `0x180033f3c`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d7dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d960`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001da4c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dbd3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dce3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001de09`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d7dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d960`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001da4c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dbd3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dce3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001de09`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001d5cb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001d5ee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001daf5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001dc05`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001dd2b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001d5cb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001d5ee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001daf5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001dc05`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001dd2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall NgcPackAuthBuffer(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        int a7,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  bool *v11; // rdx
  GUID *v12; // r9
  bool *v13; // rdx
  int v14; // esi
  bool v16; // [rsp+50h] [rbp-198h] BYREF
  _BYTE v17[3]; // [rsp+51h] [rbp-197h] BYREF
  unsigned int v18; // [rsp+54h] [rbp-194h] BYREF
  int IsCertTrustEnabled; // [rsp+58h] [rbp-190h] BYREF
  bool v20; // [rsp+5Ch] [rbp-18Ch] BYREF
  char v21; // [rsp+5Dh] [rbp-18Bh] BYREF
  unsigned int v22; // [rsp+60h] [rbp-188h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-180h] BYREF
  int v24; // [rsp+78h] [rbp-170h] BYREF
  int v25; // [rsp+7Ch] [rbp-16Ch] BYREF
  unsigned int *v26; // [rsp+80h] [rbp-168h]
  unsigned __int16 *v27; // [rsp+88h] [rbp-160h]
  __int64 v28; // [rsp+90h] [rbp-158h] BYREF
  unsigned __int64 v29; // [rsp+98h] [rbp-150h]
  _QWORD v30[5]; // [rsp+A0h] [rbp-148h] BYREF
  __int16 v31; // [rsp+C8h] [rbp-120h]
  int v32; // [rsp+D0h] [rbp-118h] BYREF
  char v33; // [rsp+D4h] [rbp-114h]
  GUID ActivityId; // [rsp+D8h] [rbp-110h] BYREF
  GUID v35; // [rsp+E8h] [rbp-100h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+F8h] [rbp-F0h] BYREF
  __int16 *v37; // [rsp+108h] [rbp-E0h]
  int v38; // [rsp+110h] [rbp-D8h]
  int v39; // [rsp+114h] [rbp-D4h]
  unsigned int *v40; // [rsp+118h] [rbp-D0h]
  __int64 v41; // [rsp+120h] [rbp-C8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+130h] [rbp-B8h] BYREF
  __int16 *v43; // [rsp+140h] [rbp-A8h]
  int v44; // [rsp+148h] [rbp-A0h]
  int v45; // [rsp+14Ch] [rbp-9Ch]
  unsigned int *v46; // [rsp+150h] [rbp-98h]
  __int64 v47; // [rsp+158h] [rbp-90h]
  __int64 *v48; // [rsp+160h] [rbp-88h]
  __int64 v49; // [rsp+168h] [rbp-80h]
  int *v50; // [rsp+170h] [rbp-78h]
  __int64 v51; // [rsp+178h] [rbp-70h]
  char *v52; // [rsp+180h] [rbp-68h]
  __int64 v53; // [rsp+188h] [rbp-60h]
  bool *v54; // [rsp+190h] [rbp-58h]
  __int64 v55; // [rsp+198h] [rbp-50h]

  v29 = a4;
  v27 = a1;
  v26 = a9;
  IsCertTrustEnabled = 0;
  v17[0] = 0;
  v16 = 0;
  v24 = 0;
  NgcGetKeyImplType(a3, &v24);
  v32 = 0;
  v33 = 0;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x400000000000LL) != 0
    && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v35 = ActivityId;
    EventActivityIdControl(4u, &v35);
    v33 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v32 = 1;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x400000000000LL) != 0
    && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
  {
    v20 = v16;
    v21 = v17[0];
    v25 = v24;
    v28 = 16779264;
    v22 = IsCertTrustEnabled;
    if ( v33 && (v35.Data1 || *(_DWORD *)&v35.Data2 || *(_DWORD *)v35.Data4 || *(_DWORD *)&v35.Data4[4]) )
      v12 = &v35;
    else
      v12 = 0;
    v54 = &v20;
    v55 = 1;
    v52 = &v21;
    v53 = 1;
    v50 = &v25;
    v51 = 4;
    v48 = &v28;
    v49 = 8;
    v46 = &v22;
    v47 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    UserData.Reserved = 2;
    v43 = word_18005F312;
    v44 = 87;
    v45 = 1;
    v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, v12, 7u, &UserData);
  }
  v30[0] = &v32;
  v30[1] = &IsCertTrustEnabled;
  v30[2] = &v24;
  v30[3] = v17;
  v30[4] = &v16;
  v31 = 256;
  if ( v27 && a2 && a3 && a5 && a8 && v26 )
  {
    IsCertTrustEnabled = NgcUtils::IsCertTrustEnabled((NgcUtils *)v17, v11);
    if ( IsCertTrustEnabled < 0 )
    {
      if ( (unsigned int)dword_18006E000 > 3 )
      {
        v18 = IsCertTrustEnabled;
        v40 = &v18;
        v41 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 3;
        EventDescriptor.Keyword = 0;
        v36.Ptr = (ULONGLONG)off_18006E008;
        v36.Size = *(unsigned __int16 *)off_18006E008;
        v36.Reserved = 2;
        v37 = &word_18005F2DE;
        v38 = 40;
        v39 = 1;
        v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v36);
      }
      IsCertTrustEnabled = 0;
    }
    IsCertTrustEnabled = NgcUtils::IsCloudTrustEnabled((NgcUtils *)&v16, v13);
    if ( IsCertTrustEnabled < 0 )
    {
      if ( (unsigned int)dword_18006E000 > 3 )
      {
        v18 = IsCertTrustEnabled;
        v40 = &v18;
        v41 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 3;
        EventDescriptor.Keyword = 0;
        v36.Ptr = (ULONGLONG)off_18006E008;
        v36.Size = *(unsigned __int16 *)off_18006E008;
        v36.Reserved = 2;
        v37 = (__int16 *)byte_18005F2A9;
        v38 = 41;
        v39 = 1;
        v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v36);
      }
      IsCertTrustEnabled = 0;
    }
    *a8 = 0;
    v14 = NgcPackAuthBufferInternal(v27, a2, a3, v29, a5, a6, a7, v16, a8, v26);
    IsCertTrustEnabled = v14;
    wil::details::ScopeExitFnGuard__lambda_333315bb9ef65493f2fec098b6afeb7c___::operator()(v30);
    if ( v14 >= 0 )
    {
      if ( v32 == 1 )
      {
        if ( v33 )
          EventActivityIdControl(4u, &v35);
        v32 = 2;
        if ( (unsigned int)dword_18006E000 > 5
          && (qword_18006E010 & 0x400000000000LL) != 0
          && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
        {
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 517;
          EventDescriptor.Keyword = 0x400000000000LL;
          v36.Ptr = (ULONGLONG)off_18006E008;
          v36.Size = *(unsigned __int16 *)off_18006E008;
          v36.Reserved = 2;
          v37 = (__int16 *)&dword_18005E36C;
          v38 = 32;
          v39 = 1;
          v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v36);
        }
      }
      return (unsigned int)v14;
    }
    else
    {
      if ( v32 == 1 )
      {
        if ( v33 )
          EventActivityIdControl(4u, &v35);
        v32 = 2;
        if ( (unsigned int)dword_18006E000 > 5
          && (qword_18006E010 & 0x400000000000LL) != 0
          && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
        {
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 517;
          EventDescriptor.Keyword = 0x400000000000LL;
          v36.Ptr = (ULONGLONG)off_18006E008;
          v36.Size = *(unsigned __int16 *)off_18006E008;
          v36.Reserved = 2;
          v37 = (__int16 *)&dword_18005E36C;
          v38 = 32;
          v39 = 1;
          v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v36);
        }
      }
      return (unsigned int)v14;
    }
  }
  else
  {
    IsCertTrustEnabled = -2147467261;
    wil::details::ScopeExitFnGuard__lambda_333315bb9ef65493f2fec098b6afeb7c___::operator()(v30);
    if ( v32 == 1 )
    {
      if ( v33 )
        EventActivityIdControl(4u, &v35);
      v32 = 2;
      if ( (unsigned int)dword_18006E000 > 5
        && (qword_18006E010 & 0x400000000000LL) != 0
        && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
      {
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 517;
        EventDescriptor.Keyword = 0x400000000000LL;
        v36.Ptr = (ULONGLONG)off_18006E008;
        v36.Size = *(unsigned __int16 *)off_18006E008;
        v36.Reserved = 2;
        v37 = (__int16 *)&dword_18005E36C;
        v38 = 32;
        v39 = 1;
        v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v36);
      }
    }
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18001d500  push    rbx
0x18001d502  push    rsi
0x18001d503  push    rdi
0x18001d504  push    r12
0x18001d506  push    r13
0x18001d508  push    r14
0x18001d50a  push    r15
0x18001d50c  sub     rsp, 1B0h
0x18001d513  mov     rax, cs:__security_cookie
0x18001d51a  xor     rax, rsp
0x18001d51d  mov     [rsp+1E8h+var_48], rax
0x18001d525  mov     [rsp+1E8h+var_150], r9
0x18001d52d  mov     rsi, r8
0x18001d530  mov     r12, rdx
0x18001d533  mov     [rsp+1E8h+var_160], rcx
0x18001d53b  mov     r13, [rsp+1E8h+arg_20]
0x18001d543  mov     r15, [rsp+1E8h+arg_38]
0x18001d54b  mov     rax, [rsp+1E8h+arg_40]
0x18001d553  mov     [rsp+1E8h+var_168], rax
0x18001d55b  xor     edi, edi
0x18001d55d  mov     [rsp+1E8h+var_190], edi
0x18001d561  mov     [rsp+1E8h+var_197], dil
0x18001d566  mov     [rsp+1E8h+var_198], dil
0x18001d56b  mov     [rsp+1E8h+var_170], edi
0x18001d56f  lea     rdx, [rsp+1E8h+var_170]
0x18001d574  mov     rcx, r8
0x18001d577  call    NgcGetKeyImplType
0x18001d57c  mov     [rsp+1E8h+var_118], edi
0x18001d583  mov     [rsp+1E8h+var_114], dil
0x18001d58b  mov     eax, cs:dword_18006E000
0x18001d591  mov     rbx, 400000000000h
0x18001d59b  cmp     eax, 5
0x18001d59e  jbe     short loc_18001D5FE
0x18001d5a0  mov     rcx, cs:qword_18006E018
0x18001d5a7  mov     rax, cs:qword_18006E010
0x18001d5ae  test    rbx, rax
0x18001d5b1  jz      short loc_18001D5FE
0x18001d5b3  mov     rax, rcx
0x18001d5b6  and     rax, rbx
0x18001d5b9  cmp     rax, rcx
0x18001d5bc  jnz     short loc_18001D5FE
0x18001d5be  lea     rdx, [rsp+1E8h+ActivityId]; ActivityId
0x18001d5c6  mov     ecx, 3; ControlCode
0x18001d5cb  call    cs:__imp_EventActivityIdControl
0x18001d5d1  movups  xmm0, xmmword ptr [rsp+1E8h+ActivityId.Data1]
0x18001d5d9  movups  xmmword ptr [rsp+1E8h+var_100.Data1], xmm0
0x18001d5e1  lea     rdx, [rsp+1E8h+var_100]; ActivityId
0x18001d5e9  mov     ecx, 4; ControlCode
0x18001d5ee  call    cs:__imp_EventActivityIdControl
0x18001d5f4  mov     [rsp+1E8h+var_114], 1
0x18001d5fc  jmp     short loc_18001D609
0x18001d5fe  xorps   xmm0, xmm0
0x18001d601  movups  xmmword ptr [rsp+1E8h+ActivityId.Data1], xmm0
0x18001d609  mov     [rsp+1E8h+var_118], 1
0x18001d614  mov     eax, cs:dword_18006E000
0x18001d61a  cmp     eax, 5
0x18001d61d  jbe     loc_18001D7E4
0x18001d623  mov     rcx, cs:qword_18006E018
0x18001d62a  mov     rax, cs:qword_18006E010
0x18001d631  test    rbx, rax
0x18001d634  jz      loc_18001D7E4
0x18001d63a  mov     rax, rcx
0x18001d63d  and     rax, rbx
0x18001d640  cmp     rax, rcx
0x18001d643  jnz     loc_18001D7E4
0x18001d649  movzx   eax, [rsp+1E8h+var_198]
0x18001d64e  mov     [rsp+1E8h+var_18C], al
0x18001d652  movzx   eax, [rsp+1E8h+var_197]
0x18001d657  mov     [rsp+1E8h+var_18B], al
0x18001d65b  mov     eax, [rsp+1E8h+var_170]
0x18001d65f  mov     [rsp+1E8h+var_16C], eax
0x18001d663  mov     [rsp+1E8h+var_158], 1000800h
0x18001d66f  mov     eax, [rsp+1E8h+var_190]
0x18001d673  mov     [rsp+1E8h+var_188], eax
0x18001d677  cmp     [rsp+1E8h+var_114], 0
0x18001d67f  jz      short loc_18001D6B3
0x18001d681  cmp     [rsp+1E8h+var_100.Data1], 0
0x18001d689  jnz     short loc_18001D6A9
0x18001d68b  cmp     dword ptr [rsp+1E8h+var_100.Data2], 0
0x18001d693  jnz     short loc_18001D6A9
0x18001d695  cmp     dword ptr [rsp+1E8h+var_100.Data4], 0
0x18001d69d  jnz     short loc_18001D6A9
0x18001d69f  cmp     dword ptr [rsp+1E8h+var_100.Data4+4], 0
0x18001d6a7  jz      short loc_18001D6B3
0x18001d6a9  lea     r9, [rsp+1E8h+var_100]
0x18001d6b1  jmp     short loc_18001D6B6
0x18001d6b3  mov     r9, rdi; RelatedActivityId
0x18001d6b6  lea     rax, [rsp+1E8h+var_18C]
0x18001d6bb  mov     [rsp+1E8h+var_58], rax
0x18001d6c3  mov     [rsp+1E8h+var_50], 1
0x18001d6cf  lea     rax, [rsp+1E8h+var_18B]
0x18001d6d4  mov     [rsp+1E8h+var_68], rax
0x18001d6dc  mov     [rsp+1E8h+var_60], 1
0x18001d6e8  lea     rax, [rsp+1E8h+var_16C]
0x18001d6ed  mov     [rsp+1E8h+var_78], rax
0x18001d6f5  mov     [rsp+1E8h+var_70], 4
0x18001d701  lea     rax, [rsp+1E8h+var_158]
0x18001d709  mov     [rsp+1E8h+var_88], rax
0x18001d711  mov     [rsp+1E8h+var_80], 8
0x18001d71d  lea     rax, [rsp+1E8h+var_188]
0x18001d722  mov     [rsp+1E8h+var_98], rax
0x18001d72a  mov     [rsp+1E8h+var_90], 4
0x18001d736  mov     dword ptr [rsp+1E8h+EventDescriptor.Id], 0B000000h
0x18001d73e  movzx   eax, cs:word_18005F308
0x18001d745  mov     dword ptr [rsp+1E8h+EventDescriptor.Level], eax
0x18001d749  mov     [rsp+1E8h+EventDescriptor.Keyword], rbx
0x18001d74e  mov     rax, cs:off_18006E008
0x18001d755  mov     [rsp+1E8h+var_B8.Ptr], rax
0x18001d75d  movzx   eax, word ptr [rax]
0x18001d760  mov     [rsp+1E8h+var_B8.Size], eax
0x18001d767  mov     dword ptr [rsp+1E8h+var_B8.0Ch], 2
0x18001d772  lea     rax, word_18005F312
0x18001d779  mov     [rsp+1E8h+var_A8], rax
0x18001d781  mov     [rsp+1E8h+var_A0], 57h ; 'W'
0x18001d78c  mov     [rsp+1E8h+var_9C], 1
0x18001d797  lea     rdi, _TraceLoggingMetadataEnd
0x18001d79e  mov     rax, rdi
0x18001d7a1  lea     r14, _TraceLoggingMetadata
0x18001d7a8  sub     eax, r14d
0x18001d7ab  mov     [rsp+1E8h+var_194], eax
0x18001d7af  mov     eax, [rsp+1E8h+var_194]
0x18001d7b3  lea     rax, [rsp+1E8h+var_B8]
0x18001d7bb  mov     [rsp+1E8h+UserData], rax; UserData
0x18001d7c0  mov     [rsp+1E8h+UserDataCount], 7; UserDataCount
0x18001d7c8  lea     r8, [rsp+1E8h+ActivityId]; ActivityId
0x18001d7d0  lea     rdx, [rsp+1E8h+EventDescriptor]; EventDescriptor
0x18001d7d5  mov     rcx, cs:RegHandle; RegHandle
0x18001d7dc  call    cs:__imp_EventWriteTransfer
0x18001d7e2  jmp     short loc_18001D7F2
0x18001d7e4  lea     rdi, _TraceLoggingMetadataEnd
0x18001d7eb  lea     r14, _TraceLoggingMetadata
0x18001d7f2  lea     rax, [rsp+1E8h+var_118]
0x18001d7fa  mov     [rsp+1E8h+var_148], rax
0x18001d802  lea     rax, [rsp+1E8h+var_190]
0x18001d807  mov     [rsp+1E8h+var_140], rax
0x18001d80f  lea     rax, [rsp+1E8h+var_170]
0x18001d814  mov     [rsp+1E8h+var_138], rax
0x18001d81c  lea     rax, [rsp+1E8h+var_197]
0x18001d821  mov     [rsp+1E8h+var_130], rax
0x18001d829  lea     rax, [rsp+1E8h+var_198]
0x18001d82e  mov     [rsp+1E8h+var_128], rax
0x18001d836  mov     [rsp+1E8h+var_120], 100h
0x18001d840  cmp     [rsp+1E8h+var_160], 0
0x18001d849  jz      loc_18001DCF0
0x18001d84f  test    r12, r12
0x18001d852  jz      loc_18001DCF0
0x18001d858  test    rsi, rsi
0x18001d85b  jz      loc_18001DCF0
0x18001d861  test    r13, r13
0x18001d864  jz      loc_18001DCF0
0x18001d86a  test    r15, r15
0x18001d86d  jz      loc_18001DCF0
0x18001d873  cmp     [rsp+1E8h+var_168], 0
0x18001d87c  jz      loc_18001DCF0
0x18001d882  lea     rcx, [rsp+1E8h+var_197]; this
0x18001d887  call    ?IsCertTrustEnabled@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsCertTrustEnabled(bool *)
0x18001d88c  mov     [rsp+1E8h+var_190], eax
0x18001d890  test    eax, eax
0x18001d892  jns     loc_18001D96E
0x18001d898  mov     eax, cs:dword_18006E000
0x18001d89e  cmp     eax, 3
0x18001d8a1  jbe     loc_18001D966
0x18001d8a7  mov     eax, [rsp+1E8h+var_190]
0x18001d8ab  mov     [rsp+1E8h+var_194], eax
0x18001d8af  lea     rax, [rsp+1E8h+var_194]
0x18001d8b4  mov     [rsp+1E8h+var_D0], rax
0x18001d8bc  mov     [rsp+1E8h+var_C8], 4
0x18001d8c8  xor     ecx, ecx
0x18001d8ca  mov     dword ptr [rsp+1E8h+EventDescriptor.Id], 0B000000h
0x18001d8d2  movzx   eax, cs:word_18005F2D4
0x18001d8d9  mov     dword ptr [rsp+1E8h+EventDescriptor.Level], eax
0x18001d8dd  mov     [rsp+1E8h+EventDescriptor.Keyword], rcx
0x18001d8e2  mov     rax, cs:off_18006E008
0x18001d8e9  mov     [rsp+1E8h+var_F0.Ptr], rax
0x18001d8f1  movzx   eax, word ptr [rax]
0x18001d8f4  mov     [rsp+1E8h+var_F0.Size], eax
0x18001d8fb  mov     dword ptr [rsp+1E8h+var_F0.0Ch], 2
0x18001d906  lea     rax, word_18005F2DE
0x18001d90d  mov     [rsp+1E8h+var_E0], rax
0x18001d915  mov     [rsp+1E8h+var_D8], 28h ; '('
0x18001d920  mov     [rsp+1E8h+var_D4], 1
0x18001d92b  mov     rax, rdi
0x18001d92e  sub     eax, r14d
0x18001d931  mov     [rsp+1E8h+var_188], eax
0x18001d935  mov     eax, [rsp+1E8h+var_188]
0x18001d939  lea     rax, [rsp+1E8h+var_F0]
0x18001d941  mov     [rsp+1E8h+UserData], rax; UserData
0x18001d946  mov     [rsp+1E8h+UserDataCount], 3; UserDataCount
0x18001d94e  xor     r9d, r9d; RelatedActivityId
0x18001d951  xor     r8d, r8d; ActivityId
0x18001d954  lea     rdx, [rsp+1E8h+EventDescriptor]; EventDescriptor
0x18001d959  mov     rcx, cs:RegHandle; RegHandle
0x18001d960  call    cs:__imp_EventWriteTransfer
0x18001d966  mov     [rsp+1E8h+var_190], 0
0x18001d96e  lea     rcx, [rsp+1E8h+var_198]; this
0x18001d973  call    ?IsCloudTrustEnabled@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsCloudTrustEnabled(bool *)
0x18001d978  mov     [rsp+1E8h+var_190], eax
0x18001d97c  test    eax, eax
0x18001d97e  jns     loc_18001DA5A
0x18001d984  mov     eax, cs:dword_18006E000
0x18001d98a  cmp     eax, 3
0x18001d98d  jbe     loc_18001DA52
0x18001d993  mov     eax, [rsp+1E8h+var_190]
0x18001d997  mov     [rsp+1E8h+var_194], eax
0x18001d99b  lea     rax, [rsp+1E8h+var_194]
0x18001d9a0  mov     [rsp+1E8h+var_D0], rax
0x18001d9a8  mov     [rsp+1E8h+var_C8], 4
0x18001d9b4  xor     ecx, ecx
0x18001d9b6  mov     dword ptr [rsp+1E8h+EventDescriptor.Id], 0B000000h
0x18001d9be  movzx   eax, cs:word_18005F29F
0x18001d9c5  mov     dword ptr [rsp+1E8h+EventDescriptor.Level], eax
0x18001d9c9  mov     [rsp+1E8h+EventDescriptor.Keyword], rcx
0x18001d9ce  mov     rax, cs:off_18006E008
0x18001d9d5  mov     [rsp+1E8h+var_F0.Ptr], rax
0x18001d9dd  movzx   eax, word ptr [rax]
0x18001d9e0  mov     [rsp+1E8h+var_F0.Size], eax
0x18001d9e7  mov     dword ptr [rsp+1E8h+var_F0.0Ch], 2
0x18001d9f2  lea     rax, byte_18005F2A9
0x18001d9f9  mov     [rsp+1E8h+var_E0], rax
0x18001da01  mov     [rsp+1E8h+var_D8], 29h ; ')'
0x18001da0c  mov     [rsp+1E8h+var_D4], 1
0x18001da17  mov     rax, rdi
0x18001da1a  sub     eax, r14d
0x18001da1d  mov     [rsp+1E8h+var_188], eax
0x18001da21  mov     eax, [rsp+1E8h+var_188]
0x18001da25  lea     rax, [rsp+1E8h+var_F0]
0x18001da2d  mov     [rsp+1E8h+UserData], rax; UserData
0x18001da32  mov     [rsp+1E8h+UserDataCount], 3; UserDataCount
0x18001da3a  xor     r9d, r9d; RelatedActivityId
0x18001da3d  xor     r8d, r8d; ActivityId
0x18001da40  lea     rdx, [rsp+1E8h+EventDescriptor]; EventDescriptor
0x18001da45  mov     rcx, cs:RegHandle; RegHandle
0x18001da4c  call    cs:__imp_EventWriteTransfer
0x18001da52  mov     [rsp+1E8h+var_190], 0
0x18001da5a  mov     qword ptr [r15], 0
0x18001da61  mov     rax, [rsp+1E8h+var_168]
0x18001da69  mov     [rsp+1E8h+var_1A0], rax; unsigned int *
0x18001da6e  mov     [rsp+1E8h+var_1A8], r15; unsigned __int8 **
0x18001da73  movzx   eax, [rsp+1E8h+var_198]
0x18001da78  mov     [rsp+1E8h+var_1B0], al; bool
0x18001da7c  mov     eax, [rsp+1E8h+arg_30]
0x18001da83  mov     [rsp+1E8h+var_1B8], eax; int
0x18001da87  mov     rax, [rsp+1E8h+arg_28]
0x18001da8f  mov     [rsp+1E8h+UserData], rax; unsigned __int64
0x18001da94  mov     qword ptr [rsp+1E8h+UserDataCount], r13; unsigned __int16 *
0x18001da99  mov     r9, [rsp+1E8h+var_150]; unsigned __int64
0x18001daa1  mov     r8, rsi; unsigned __int16 *
0x18001daa4  mov     rdx, r12; unsigned __int16 *
0x18001daa7  mov     rcx, [rsp+1E8h+var_160]; unsigned __int16 *
0x18001daaf  call    ?NgcPackAuthBufferInternal@@YAJPEBG00_K01H_NPEAPEAEPEAK@Z; NgcPackAuthBufferInternal(ushort const *,ushort const *,ushort const *,unsigned __int64,ushort const *,unsigned __int64,int,bool,uchar * *,ulong *)
0x18001dab4  mov     esi, eax
0x18001dab6  mov     [rsp+1E8h+var_190], eax
0x18001daba  lea     rcx, [rsp+1E8h+var_148]
0x18001dac2  call    wil__details__ScopeExitFnGuard__lambda_333315bb9ef65493f2fec098b6afeb7c_____operator__
0x18001dac7  nop
0x18001dac8  test    esi, esi
0x18001daca  jns     loc_18001DBE0
0x18001dad0  cmp     [rsp+1E8h+var_118], 1
0x18001dad8  jnz     loc_18001DBD9
0x18001dade  cmp     [rsp+1E8h+var_114], 0
0x18001dae6  jz      short loc_18001DAFB
0x18001dae8  lea     rdx, [rsp+1E8h+var_100]; ActivityId
0x18001daf0  mov     ecx, 4; ControlCode
0x18001daf5  call    cs:__imp_EventActivityIdControl
0x18001dafb  mov     [rsp+1E8h+var_118], 2
0x18001db06  mov     eax, cs:dword_18006E000
0x18001db0c  cmp     eax, 5
0x18001db0f  jbe     loc_18001DBD9
0x18001db15  mov     rcx, cs:qword_18006E018
0x18001db1c  mov     rax, cs:qword_18006E010
0x18001db23  test    rbx, rax
0x18001db26  jz      loc_18001DBD9
0x18001db2c  mov     rax, rcx
0x18001db2f  and     rax, rbx
0x18001db32  cmp     rax, rcx
0x18001db35  jnz     loc_18001DBD9
0x18001db3b  mov     dword ptr [rsp+1E8h+EventDescriptor.Id], 0B000000h
0x18001db43  movzx   eax, cs:word_18005E362
0x18001db4a  mov     dword ptr [rsp+1E8h+EventDescriptor.Level], eax
0x18001db4e  mov     [rsp+1E8h+EventDescriptor.Keyword], rbx
0x18001db53  mov     rax, cs:off_18006E008
0x18001db5a  mov     [rsp+1E8h+var_F0.Ptr], rax
0x18001db62  movzx   eax, word ptr [rax]
0x18001db65  mov     [rsp+1E8h+var_F0.Size], eax
0x18001db6c  mov     dword ptr [rsp+1E8h+var_F0.0Ch], 2
0x18001db77  lea     rax, dword_18005E36C
0x18001db7e  mov     [rsp+1E8h+var_E0], rax
0x18001db86  mov     [rsp+1E8h+var_D8], 20h ; ' '
0x18001db91  mov     [rsp+1E8h+var_D4], 1
0x18001db9c  sub     edi, r14d
0x18001db9f  mov     [rsp+1E8h+var_194], edi
0x18001dba3  mov     eax, [rsp+1E8h+var_194]
0x18001dba7  lea     rax, [rsp+1E8h+var_F0]
0x18001dbaf  mov     [rsp+1E8h+UserData], rax; UserData
0x18001dbb4  mov     [rsp+1E8h+UserDataCount], 2; UserDataCount
0x18001dbbc  xor     r9d, r9d; RelatedActivityId
0x18001dbbf  lea     r8, [rsp+1E8h+ActivityId]; ActivityId
0x18001dbc7  lea     rdx, [rsp+1E8h+EventDescriptor]; EventDescriptor
0x18001dbcc  mov     rcx, cs:RegHandle; RegHandle
0x18001dbd3  call    cs:__imp_EventWriteTransfer
  ... truncated ...
```
