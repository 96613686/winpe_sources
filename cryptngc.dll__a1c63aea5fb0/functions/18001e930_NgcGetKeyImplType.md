# NgcGetKeyImplType

- ea: `0x18001e930`
- end: `0x18001ed49`
- name: `NgcGetKeyImplType`
- size: `1049`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d500`
- `0x180039c18`

## callees

- `0x180006538`
- `0x18000820c`
- `0x18001e930`
- `0x18003a60c`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001eafe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ec3a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ed1d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001eafe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ec3a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ed1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e9aa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e9c1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001eb86`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ec69`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e9aa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e9c1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001eb86`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ec69`

## string_xrefs

- `0x18001eb50`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall NgcGetKeyImplType(__int64 a1, int *a2)
{
  int v2; // ecx
  GUID *v3; // r9
  int v4; // eax
  unsigned int v5; // ebx
  ULONG UserDataCount; // [rsp+20h] [rbp-99h]
  int v8; // [rsp+34h] [rbp-85h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  int v10; // [rsp+48h] [rbp-71h] BYREF
  int v11; // [rsp+4Ch] [rbp-6Dh] BYREF
  __int64 v12; // [rsp+50h] [rbp-69h] BYREF
  int v13; // [rsp+58h] [rbp-61h] BYREF
  char v14; // [rsp+5Ch] [rbp-5Dh]
  GUID ActivityId; // [rsp+60h] [rbp-59h] BYREF
  GUID v16; // [rsp+70h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+80h] [rbp-39h] BYREF
  char *v18; // [rsp+90h] [rbp-29h]
  int v19; // [rsp+98h] [rbp-21h]
  int v20; // [rsp+9Ch] [rbp-1Dh]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-19h] BYREF
  int *v22; // [rsp+B0h] [rbp-9h]
  int v23; // [rsp+B8h] [rbp-1h]
  int v24; // [rsp+BCh] [rbp+3h]
  int *v25; // [rsp+C0h] [rbp+7h]
  __int64 v26; // [rsp+C8h] [rbp+Fh]
  __int64 *v27; // [rsp+D0h] [rbp+17h]
  __int64 v28; // [rsp+D8h] [rbp+1Fh]
  int *v29; // [rsp+E0h] [rbp+27h]
  __int64 v30; // [rsp+E8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  __int64 v32; // [rsp+120h] [rbp+67h] BYREF
  int *v33; // [rsp+128h] [rbp+6Fh] BYREF

  v33 = a2;
  v32 = a1;
  v8 = 0;
  v13 = 0;
  v14 = 0;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x200000000000LL) != 0
    && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v16 = ActivityId;
    EventActivityIdControl(4u, &v16);
    v14 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v13 = 1;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x200000000000LL) != 0
    && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
  {
    v2 = *v33;
    v11 = v8;
    v10 = v2;
    v12 = 16779264;
    if ( v14 && (v16.Data1 || *(_DWORD *)&v16.Data2 || *(_DWORD *)v16.Data4 || *(_DWORD *)&v16.Data4[4]) )
      v3 = &v16;
    else
      v3 = 0;
    v30 = 4;
    v29 = &v10;
    v28 = 8;
    v27 = &v12;
    v26 = 4;
    v25 = &v11;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x200000000000LL;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    v22 = &dword_1800609FC;
    UserData.Reserved = 2;
    v23 = 58;
    v24 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, v3, 5u, &UserData);
  }
  LOWORD(v19) = 256;
  v17.Ptr = (ULONGLONG)&v13;
  *(_QWORD *)&v17.Size = &v8;
  v18 = (char *)&v33;
  *(_QWORD *)&EventDescriptor.Id = &v32;
  EventDescriptor.Keyword = (ULONGLONG)&v33;
  v4 = HResultErrorContract__lambda_3af9af96f55fc1e235ca6cd5835f12ee_(&EventDescriptor);
  v8 = v4;
  v5 = v4;
  if ( v4 >= 0 )
  {
    wil::details::ScopeExitFnGuard__lambda_80610b06a0ba33b6db65fcc020d65aa4___::operator()(&v17);
    if ( v13 == 1 )
    {
      if ( v14 )
        EventActivityIdControl(4u, &v16);
      v13 = 2;
      if ( (unsigned int)dword_18006E000 > 5
        && (qword_18006E010 & 0x200000000000LL) != 0
        && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        v17.Ptr = (ULONGLONG)off_18006E008;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x200000000000LL;
        v17.Size = *(unsigned __int16 *)off_18006E008;
        v18 = &byte_18005F607;
        v17.Reserved = 2;
        v19 = 32;
        v20 = 1;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v17);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x668,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v4,
      UserDataCount);
    wil::details::ScopeExitFnGuard__lambda_80610b06a0ba33b6db65fcc020d65aa4___::operator()(&v17);
    if ( v13 == 1 )
    {
      if ( v14 )
        EventActivityIdControl(4u, &v16);
      v13 = 2;
      if ( (unsigned int)dword_18006E000 > 5
        && (qword_18006E010 & 0x200000000000LL) != 0
        && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        v17.Ptr = (ULONGLONG)off_18006E008;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x200000000000LL;
        v17.Size = *(unsigned __int16 *)off_18006E008;
        v18 = &byte_18005F607;
        v17.Reserved = 2;
        v19 = 32;
        v20 = 1;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v17);
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x18001e930  mov     [rsp-8+arg_10], rbx
0x18001e935  mov     [rsp-8+arg_18], rsi
0x18001e93a  mov     [rsp-8+arg_8], rdx
0x18001e93f  mov     [rsp-8+arg_0], rcx
0x18001e944  push    rbp
0x18001e945  push    rdi
0x18001e946  push    r14
0x18001e948  lea     rbp, [rsp-47h]
0x18001e94d  sub     rsp, 100h
0x18001e954  mov     rax, cs:__security_cookie
0x18001e95b  xor     rax, rsp
0x18001e95e  mov     [rbp+57h+var_20], rax
0x18001e962  mov     eax, cs:dword_18006E000
0x18001e968  xor     ebx, ebx
0x18001e96a  mov     [rsp+110h+var_DC], ebx
0x18001e96e  mov     rsi, 200000000000h
0x18001e978  mov     [rbp+57h+var_B8], ebx
0x18001e97b  mov     [rbp+57h+var_B4], bl
0x18001e97e  cmp     eax, 5
0x18001e981  jbe     short loc_18001E9CD
0x18001e983  mov     rcx, cs:qword_18006E018
0x18001e98a  mov     rax, cs:qword_18006E010
0x18001e991  test    rsi, rax
0x18001e994  jz      short loc_18001E9CD
0x18001e996  mov     rax, rcx
0x18001e999  and     rax, rsi
0x18001e99c  cmp     rax, rcx
0x18001e99f  jnz     short loc_18001E9CD
0x18001e9a1  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18001e9a5  mov     ecx, 3; ControlCode
0x18001e9aa  call    cs:__imp_EventActivityIdControl
0x18001e9b0  movups  xmm0, xmmword ptr [rbp+57h+ActivityId.Data1]
0x18001e9b4  lea     rdx, [rbp+57h+var_A0]; ActivityId
0x18001e9b8  mov     ecx, 4; ControlCode
0x18001e9bd  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x18001e9c1  call    cs:__imp_EventActivityIdControl
0x18001e9c7  mov     [rbp+57h+var_B4], 1
0x18001e9cb  jmp     short loc_18001E9D4
0x18001e9cd  xorps   xmm0, xmm0
0x18001e9d0  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18001e9d4  mov     eax, cs:dword_18006E000
0x18001e9da  lea     rdi, _TraceLoggingMetadataEnd
0x18001e9e1  mov     [rbp+57h+var_B8], 1
0x18001e9e8  lea     r14, _TraceLoggingMetadata
0x18001e9ef  cmp     eax, 5
0x18001e9f2  jbe     loc_18001EB04
0x18001e9f8  mov     rcx, cs:qword_18006E018
0x18001e9ff  mov     rax, cs:qword_18006E010
0x18001ea06  test    rsi, rax
0x18001ea09  jz      loc_18001EB04
0x18001ea0f  mov     rax, rcx
0x18001ea12  and     rax, rsi
0x18001ea15  cmp     rax, rcx
0x18001ea18  jnz     loc_18001EB04
0x18001ea1e  mov     rax, [rbp+57h+arg_8]
0x18001ea22  mov     ecx, [rax]
0x18001ea24  mov     eax, [rsp+110h+var_DC]
0x18001ea28  mov     [rbp+57h+var_C4], eax
0x18001ea2b  mov     [rbp+57h+var_C8], ecx
0x18001ea2e  mov     [rbp+57h+var_C0], 1000800h
0x18001ea36  cmp     [rbp+57h+var_B4], bl
0x18001ea39  jz      short loc_18001EA55
0x18001ea3b  cmp     [rbp+57h+var_A0.Data1], ebx
0x18001ea3e  jnz     short loc_18001EA4F
0x18001ea40  cmp     dword ptr [rbp+57h+var_A0.Data2], ebx
0x18001ea43  jnz     short loc_18001EA4F
0x18001ea45  cmp     dword ptr [rbp+57h+var_A0.Data4], ebx
0x18001ea48  jnz     short loc_18001EA4F
0x18001ea4a  cmp     dword ptr [rbp+57h+var_A0.Data4+4], ebx
0x18001ea4d  jz      short loc_18001EA55
0x18001ea4f  lea     r9, [rbp+57h+var_A0]
0x18001ea53  jmp     short loc_18001EA58
0x18001ea55  mov     r9, rbx; RelatedActivityId
0x18001ea58  mov     [rbp+57h+var_28], 4
0x18001ea60  lea     rax, [rbp+57h+var_C8]
0x18001ea64  mov     [rbp+57h+var_30], rax
0x18001ea68  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x18001ea6c  mov     [rbp+57h+var_38], 8
0x18001ea74  lea     rax, [rbp+57h+var_C0]
0x18001ea78  mov     [rbp+57h+var_40], rax
0x18001ea7c  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x18001ea81  lea     rax, [rbp+57h+var_C4]
0x18001ea85  mov     [rbp+57h+var_48], 4
0x18001ea8d  mov     [rbp+57h+var_50], rax
0x18001ea91  movzx   eax, cs:word_1800609F2
0x18001ea98  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001ea9b  mov     rax, cs:off_18006E008
0x18001eaa2  mov     [rbp+57h+var_70.Ptr], rax
0x18001eaa6  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18001eaae  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18001eab2  movzx   eax, word ptr [rax]
0x18001eab5  mov     [rbp+57h+var_70.Size], eax
0x18001eab8  lea     rax, dword_1800609FC
0x18001eabf  mov     [rbp+57h+var_60], rax
0x18001eac3  mov     rax, rdi
0x18001eac6  sub     eax, r14d
0x18001eac9  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18001ead0  mov     [rbp+57h+var_58], 3Ah ; ':'
0x18001ead7  mov     [rbp+57h+var_54], 1
0x18001eade  mov     [rsp+110h+var_E0], eax
0x18001eae2  mov     eax, [rsp+110h+var_E0]
0x18001eae6  mov     rcx, cs:RegHandle; RegHandle
0x18001eaed  lea     rax, [rbp+57h+var_70]
0x18001eaf1  mov     [rsp+110h+UserData], rax; UserData
0x18001eaf6  mov     [rsp+110h+UserDataCount], 5; int
0x18001eafe  call    cs:__imp_EventWriteTransfer
0x18001eb04  lea     rax, [rbp+57h+var_B8]
0x18001eb08  mov     word ptr [rbp+57h+var_78], 100h
0x18001eb0e  mov     [rbp+57h+var_90.Ptr], rax
0x18001eb12  lea     rcx, [rsp+110h+EventDescriptor]
0x18001eb17  lea     rax, [rsp+110h+var_DC]
0x18001eb1c  mov     qword ptr [rbp+57h+var_90.Size], rax
0x18001eb20  lea     rax, [rbp+57h+arg_8]
0x18001eb24  mov     [rbp+57h+var_80], rax
0x18001eb28  lea     rax, [rbp+57h+arg_0]
0x18001eb2c  mov     qword ptr [rsp+110h+EventDescriptor.Id], rax
0x18001eb31  lea     rax, [rbp+57h+arg_8]
0x18001eb35  mov     [rbp+57h+EventDescriptor.Keyword], rax
0x18001eb39  call    HResultErrorContract__lambda_3af9af96f55fc1e235ca6cd5835f12ee___; HResultErrorContract__lambda_3af9af96f55fc1e235ca6cd5835f12ee_
0x18001eb3e  mov     [rsp+110h+var_DC], eax
0x18001eb42  mov     ebx, eax
0x18001eb44  test    eax, eax
0x18001eb46  jns     loc_18001EC47
0x18001eb4c  mov     rcx, [rbp+5Fh]; this
0x18001eb50  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001eb57  mov     r9d, eax; char *
0x18001eb5a  mov     edx, 668h; void *
0x18001eb5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb64  lea     rcx, [rbp+57h+var_90]
0x18001eb68  call    wil__details__ScopeExitFnGuard__lambda_80610b06a0ba33b6db65fcc020d65aa4_____operator__
0x18001eb6d  cmp     [rbp+57h+var_B8], 1
0x18001eb71  jnz     loc_18001EC40
0x18001eb77  cmp     [rbp+57h+var_B4], 0
0x18001eb7b  jz      short loc_18001EB8C
0x18001eb7d  lea     rdx, [rbp+57h+var_A0]; ActivityId
0x18001eb81  mov     ecx, 4; ControlCode
0x18001eb86  call    cs:__imp_EventActivityIdControl
0x18001eb8c  mov     eax, cs:dword_18006E000
0x18001eb92  mov     [rbp+57h+var_B8], 2
0x18001eb99  cmp     eax, 5
0x18001eb9c  jbe     loc_18001EC40
0x18001eba2  mov     rcx, cs:qword_18006E018
0x18001eba9  mov     rax, cs:qword_18006E010
0x18001ebb0  test    rsi, rax
0x18001ebb3  jz      loc_18001EC40
0x18001ebb9  mov     rax, rcx
0x18001ebbc  and     rax, rsi
0x18001ebbf  cmp     rax, rcx
0x18001ebc2  jnz     short loc_18001EC40
0x18001ebc4  movzx   eax, cs:word_18005F5FD
0x18001ebcb  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x18001ebcf  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001ebd2  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x18001ebd7  mov     rax, cs:off_18006E008
0x18001ebde  sub     edi, r14d
0x18001ebe1  mov     [rbp+57h+var_90.Ptr], rax
0x18001ebe5  xor     r9d, r9d; RelatedActivityId
0x18001ebe8  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18001ebf0  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18001ebf4  movzx   eax, word ptr [rax]
0x18001ebf7  mov     [rbp+57h+var_90.Size], eax
0x18001ebfa  lea     rax, byte_18005F607
0x18001ec01  mov     [rbp+57h+var_80], rax
0x18001ec05  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18001ec0c  mov     [rbp+57h+var_78], 20h ; ' '
0x18001ec13  mov     [rbp+57h+var_74], 1
0x18001ec1a  mov     [rsp+110h+var_E0], edi
0x18001ec1e  mov     eax, [rsp+110h+var_E0]
0x18001ec22  mov     rcx, cs:RegHandle; RegHandle
0x18001ec29  lea     rax, [rbp+57h+var_90]
0x18001ec2d  mov     [rsp+110h+UserData], rax; UserData
0x18001ec32  mov     [rsp+110h+UserDataCount], 2; UserDataCount
0x18001ec3a  call    cs:__imp_EventWriteTransfer
0x18001ec40  mov     eax, ebx
0x18001ec42  jmp     loc_18001ED25
0x18001ec47  lea     rcx, [rbp+57h+var_90]
0x18001ec4b  call    wil__details__ScopeExitFnGuard__lambda_80610b06a0ba33b6db65fcc020d65aa4_____operator__
0x18001ec50  cmp     [rbp+57h+var_B8], 1
0x18001ec54  jnz     loc_18001ED23
0x18001ec5a  cmp     [rbp+57h+var_B4], 0
0x18001ec5e  jz      short loc_18001EC6F
0x18001ec60  lea     rdx, [rbp+57h+var_A0]; ActivityId
0x18001ec64  mov     ecx, 4; ControlCode
0x18001ec69  call    cs:__imp_EventActivityIdControl
0x18001ec6f  mov     eax, cs:dword_18006E000
0x18001ec75  mov     [rbp+57h+var_B8], 2
0x18001ec7c  cmp     eax, 5
0x18001ec7f  jbe     loc_18001ED23
0x18001ec85  mov     rcx, cs:qword_18006E018
0x18001ec8c  mov     rax, cs:qword_18006E010
0x18001ec93  test    rsi, rax
0x18001ec96  jz      loc_18001ED23
0x18001ec9c  mov     rax, rcx
0x18001ec9f  and     rax, rsi
0x18001eca2  cmp     rax, rcx
0x18001eca5  jnz     short loc_18001ED23
0x18001eca7  movzx   eax, cs:word_18005F5FD
0x18001ecae  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x18001ecb2  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001ecb5  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x18001ecba  mov     rax, cs:off_18006E008
0x18001ecc1  sub     edi, r14d
0x18001ecc4  mov     [rbp+57h+var_90.Ptr], rax
0x18001ecc8  xor     r9d, r9d; RelatedActivityId
0x18001eccb  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18001ecd3  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18001ecd7  movzx   eax, word ptr [rax]
0x18001ecda  mov     [rbp+57h+var_90.Size], eax
0x18001ecdd  lea     rax, byte_18005F607
0x18001ece4  mov     [rbp+57h+var_80], rax
0x18001ece8  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18001ecef  mov     [rbp+57h+var_78], 20h ; ' '
0x18001ecf6  mov     [rbp+57h+var_74], 1
0x18001ecfd  mov     [rsp+110h+var_E0], edi
0x18001ed01  mov     eax, [rsp+110h+var_E0]
0x18001ed05  mov     rcx, cs:RegHandle; RegHandle
0x18001ed0c  lea     rax, [rbp+57h+var_90]
0x18001ed10  mov     [rsp+110h+UserData], rax; UserData
0x18001ed15  mov     [rsp+110h+UserDataCount], 2; UserDataCount
0x18001ed1d  call    cs:__imp_EventWriteTransfer
0x18001ed23  xor     eax, eax
0x18001ed25  mov     rcx, [rbp+57h+var_20]
0x18001ed29  xor     rcx, rsp; StackCookie
0x18001ed2c  call    __security_check_cookie
0x18001ed31  lea     r11, [rsp+110h+var_10]
0x18001ed39  mov     rbx, [r11+30h]
0x18001ed3d  mov     rsi, [r11+38h]
0x18001ed41  mov     rsp, r11
0x18001ed44  pop     r14
0x18001ed46  pop     rdi
0x18001ed47  pop     rbp
0x18001ed48  retn
```
