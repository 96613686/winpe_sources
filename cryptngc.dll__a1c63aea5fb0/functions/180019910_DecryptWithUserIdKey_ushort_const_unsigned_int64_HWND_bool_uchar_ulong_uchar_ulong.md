# DecryptWithUserIdKey(ushort const *,unsigned __int64,HWND__ *,bool,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180019910`
- end: `0x180019d39`
- name: `?DecryptWithUserIdKey@@YAJPEBG_KPEAUHWND__@@_NPEAEKPEAPEAEPEAK@Z`
- size: `1065`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, HWND, bool, unsigned __int8 *, char, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800198d0`
- `0x18003c8b0`

## callees

- `0x18000323c`
- `0x180006538`
- `0x180019910`
- `0x18003c6cc`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019ac9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019c31`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019d17`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019ac9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019c31`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019d17`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001998c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800199a3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019b7b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019c61`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001998c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800199a3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019b7b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019c61`

## string_xrefs

- `0x180019b44`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`

## pseudocode

```c
__int64 __fastcall DecryptWithUserIdKey(
        const unsigned __int16 *a1,
        __int64 a2,
        HWND a3,
        char a4,
        unsigned __int8 *a5,
        char a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  GUID *v8; // r9
  int v9; // eax
  unsigned int v10; // ebx
  ULONG UserDataCount; // [rsp+20h] [rbp-A9h]
  int v13; // [rsp+34h] [rbp-95h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-91h] BYREF
  __int16 v15; // [rsp+48h] [rbp-81h]
  int v16; // [rsp+50h] [rbp-79h] BYREF
  __int64 v17; // [rsp+58h] [rbp-71h] BYREF
  int v18; // [rsp+60h] [rbp-69h] BYREF
  char v19; // [rsp+64h] [rbp-65h]
  GUID ActivityId; // [rsp+68h] [rbp-61h] BYREF
  GUID v21; // [rsp+78h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-39h] BYREF
  char *v23; // [rsp+A0h] [rbp-29h]
  __int64 v24; // [rsp+A8h] [rbp-21h]
  unsigned int **v25; // [rsp+B0h] [rbp-19h]
  __int64 v26; // [rsp+B8h] [rbp-11h]
  HWND *v27; // [rsp+C0h] [rbp-9h]
  __int64 v28; // [rsp+C8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+3Fh]
  const unsigned __int16 *v30; // [rsp+110h] [rbp+47h] BYREF
  __int64 v31; // [rsp+118h] [rbp+4Fh] BYREF
  HWND v32; // [rsp+120h] [rbp+57h] BYREF
  char v33; // [rsp+128h] [rbp+5Fh] BYREF

  v33 = a4;
  v32 = a3;
  v31 = a2;
  v30 = a1;
  v13 = 0;
  v18 = 0;
  v19 = 0;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x200000000000LL) != 0
    && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v21 = ActivityId;
    EventActivityIdControl(4u, &v21);
    v19 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v18 = 1;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x200000000000LL) != 0
    && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
  {
    v16 = v13;
    v17 = 0x1000000;
    if ( v19 && (v21.Data1 || *(_DWORD *)&v21.Data2 || *(_DWORD *)v21.Data4 || *(_DWORD *)&v21.Data4[4]) )
      v8 = &v21;
    else
      v8 = 0;
    v28 = 8;
    v27 = (HWND *)&v17;
    v26 = 4;
    v25 = (unsigned int **)&v16;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x200000000000LL;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    v23 = (char *)&unk_1800612B0;
    UserData.Reserved = 2;
    v24 = 0x100000039LL;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, v8, 4u, &UserData);
  }
  v15 = 256;
  *(_QWORD *)&EventDescriptor.Id = &v18;
  EventDescriptor.Keyword = (ULONGLONG)&v13;
  UserData.Ptr = (ULONGLONG)&v30;
  *(_QWORD *)&UserData.Size = &a5;
  v23 = &a6;
  v24 = (__int64)&a7;
  v25 = &a8;
  v26 = (__int64)&v31;
  v27 = &v32;
  v28 = (__int64)&v33;
  v9 = HResultErrorContract__lambda_41da0fdb9f953cc094cad49c7e4dbc37_(&UserData);
  v13 = v9;
  v10 = v9;
  if ( v9 >= 0 )
  {
    wil::details::ScopeExitFnGuard__lambda_93c817616f72b5eb0a2ebc800f1b3c45___::operator()(&EventDescriptor);
    if ( v18 == 1 )
    {
      if ( v19 )
        EventActivityIdControl(4u, &v21);
      v18 = 2;
      if ( (unsigned int)dword_18006E000 > 5
        && (qword_18006E010 & 0x200000000000LL) != 0
        && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = (ULONGLONG)off_18006E008;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x200000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18006E008;
        v23 = &byte_18005F607;
        UserData.Reserved = 2;
        v24 = 0x100000020LL;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &UserData);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)v9,
      UserDataCount);
    wil::details::ScopeExitFnGuard__lambda_93c817616f72b5eb0a2ebc800f1b3c45___::operator()(&EventDescriptor);
    if ( v18 == 1 )
    {
      if ( v19 )
        EventActivityIdControl(4u, &v21);
      v18 = 2;
      if ( (unsigned int)dword_18006E000 > 5
        && (qword_18006E010 & 0x200000000000LL) != 0
        && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = (ULONGLONG)off_18006E008;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x200000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18006E008;
        v23 = &byte_18005F607;
        UserData.Reserved = 2;
        v24 = 0x100000020LL;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &UserData);
      }
    }
    return v10;
  }
}

```

## disassembly

```asm
0x180019910  mov     [rsp-8+arg_18], r9b
0x180019915  mov     [rsp-8+arg_10], r8
0x18001991a  mov     [rsp-8+arg_8], rdx
0x18001991f  mov     [rsp-8+arg_0], rcx
0x180019924  push    rbp
0x180019925  push    rbx
0x180019926  push    rsi
0x180019927  push    rdi
0x180019928  push    r14
0x18001992a  lea     rbp, [rsp-17h]
0x18001992f  sub     rsp, 0E0h
0x180019936  mov     rax, cs:__security_cookie
0x18001993d  xor     rax, rsp
0x180019940  mov     [rbp+37h+var_30], rax
0x180019944  mov     eax, cs:dword_18006E000
0x18001994a  xor     ebx, ebx
0x18001994c  mov     [rsp+100h+var_CC], ebx
0x180019950  mov     rsi, 200000000000h
0x18001995a  mov     [rbp+37h+var_A0], ebx
0x18001995d  mov     [rbp+37h+var_9C], bl
0x180019960  cmp     eax, 5
0x180019963  jbe     short loc_1800199AF
0x180019965  mov     rcx, cs:qword_18006E018
0x18001996c  mov     rax, cs:qword_18006E010
0x180019973  test    rsi, rax
0x180019976  jz      short loc_1800199AF
0x180019978  mov     rax, rcx
0x18001997b  and     rax, rsi
0x18001997e  cmp     rax, rcx
0x180019981  jnz     short loc_1800199AF
0x180019983  lea     rdx, [rbp+37h+ActivityId]; ActivityId
0x180019987  mov     ecx, 3; ControlCode
0x18001998c  call    cs:__imp_EventActivityIdControl
0x180019992  movups  xmm0, xmmword ptr [rbp+37h+ActivityId.Data1]
0x180019996  lea     rdx, [rbp+37h+var_88]; ActivityId
0x18001999a  mov     ecx, 4; ControlCode
0x18001999f  movups  xmmword ptr [rbp+37h+var_88.Data1], xmm0
0x1800199a3  call    cs:__imp_EventActivityIdControl
0x1800199a9  mov     [rbp+37h+var_9C], 1
0x1800199ad  jmp     short loc_1800199B6
0x1800199af  xorps   xmm0, xmm0
0x1800199b2  movups  xmmword ptr [rbp+37h+ActivityId.Data1], xmm0
0x1800199b6  mov     eax, cs:dword_18006E000
0x1800199bc  lea     rdi, _TraceLoggingMetadataEnd
0x1800199c3  mov     [rbp+37h+var_A0], 1
0x1800199ca  lea     r14, _TraceLoggingMetadata
0x1800199d1  cmp     eax, 5
0x1800199d4  jbe     loc_180019ACF
0x1800199da  mov     rcx, cs:qword_18006E018
0x1800199e1  mov     rax, cs:qword_18006E010
0x1800199e8  test    rsi, rax
0x1800199eb  jz      loc_180019ACF
0x1800199f1  mov     rax, rcx
0x1800199f4  and     rax, rsi
0x1800199f7  cmp     rax, rcx
0x1800199fa  jnz     loc_180019ACF
0x180019a00  mov     eax, [rsp+100h+var_CC]
0x180019a04  mov     [rbp+37h+var_B0], eax
0x180019a07  mov     [rbp+37h+var_A8], 1000000h
0x180019a0f  cmp     [rbp+37h+var_9C], bl
0x180019a12  jz      short loc_180019A2E
0x180019a14  cmp     [rbp+37h+var_88.Data1], ebx
0x180019a17  jnz     short loc_180019A28
0x180019a19  cmp     dword ptr [rbp+37h+var_88.Data2], ebx
0x180019a1c  jnz     short loc_180019A28
0x180019a1e  cmp     dword ptr [rbp+37h+var_88.Data4], ebx
0x180019a21  jnz     short loc_180019A28
0x180019a23  cmp     dword ptr [rbp+37h+var_88.Data4+4], ebx
0x180019a26  jz      short loc_180019A2E
0x180019a28  lea     r9, [rbp+37h+var_88]
0x180019a2c  jmp     short loc_180019A31
0x180019a2e  mov     r9, rbx; RelatedActivityId
0x180019a31  mov     [rbp+37h+var_38], 8
0x180019a39  lea     rax, [rbp+37h+var_A8]
0x180019a3d  mov     [rbp+37h+var_40], rax
0x180019a41  lea     r8, [rbp+37h+ActivityId]; ActivityId
0x180019a45  lea     rax, [rbp+37h+var_B0]
0x180019a49  mov     [rbp+37h+var_48], 4
0x180019a51  mov     [rbp+37h+var_50], rax
0x180019a55  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x180019a5a  movzx   eax, cs:word_1800612A6
0x180019a61  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x180019a65  mov     rax, cs:off_18006E008
0x180019a6c  mov     [rbp+37h+var_70.Ptr], rax
0x180019a70  mov     dword ptr [rsp+100h+EventDescriptor.Id], 0B000000h
0x180019a78  mov     [rsp+100h+EventDescriptor.Keyword], rsi
0x180019a7d  movzx   eax, word ptr [rax]
0x180019a80  mov     [rbp+37h+var_70.Size], eax
0x180019a83  lea     rax, unk_1800612B0
0x180019a8a  mov     [rbp+37h+var_60], rax
0x180019a8e  mov     rax, rdi
0x180019a91  sub     eax, r14d
0x180019a94  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x180019a9b  mov     dword ptr [rbp+37h+var_58], 39h ; '9'
0x180019aa2  mov     dword ptr [rbp+37h+var_58+4], 1
0x180019aa9  mov     [rsp+100h+var_D0], eax
0x180019aad  mov     eax, [rsp+100h+var_D0]
0x180019ab1  mov     rcx, cs:RegHandle; RegHandle
0x180019ab8  lea     rax, [rbp+37h+var_70]
0x180019abc  mov     [rsp+100h+UserData], rax; UserData
0x180019ac1  mov     [rsp+100h+UserDataCount], 4; int
0x180019ac9  call    cs:__imp_EventWriteTransfer
0x180019acf  lea     rax, [rbp+37h+var_A0]
0x180019ad3  mov     [rsp+100h+var_B8], 100h
0x180019ada  mov     qword ptr [rsp+100h+EventDescriptor.Id], rax
0x180019adf  lea     rcx, [rbp+37h+var_70]
0x180019ae3  lea     rax, [rsp+100h+var_CC]
0x180019ae8  mov     [rsp+100h+EventDescriptor.Keyword], rax
0x180019aed  lea     rax, [rbp+37h+arg_0]
0x180019af1  mov     [rbp+37h+var_70.Ptr], rax
0x180019af5  lea     rax, [rbp+37h+arg_20]
0x180019af9  mov     qword ptr [rbp+37h+var_70.Size], rax
0x180019afd  lea     rax, [rbp+37h+arg_28]
0x180019b01  mov     [rbp+37h+var_60], rax
0x180019b05  lea     rax, [rbp+37h+arg_30]
0x180019b09  mov     [rbp+37h+var_58], rax
0x180019b0d  lea     rax, [rbp+37h+arg_38]
0x180019b11  mov     [rbp+37h+var_50], rax
0x180019b15  lea     rax, [rbp+37h+arg_8]
0x180019b19  mov     [rbp+37h+var_48], rax
0x180019b1d  lea     rax, [rbp+37h+arg_10]
0x180019b21  mov     [rbp+37h+var_40], rax
0x180019b25  lea     rax, [rbp+37h+arg_18]
0x180019b29  mov     [rbp+37h+var_38], rax
0x180019b2d  call    HResultErrorContract__lambda_41da0fdb9f953cc094cad49c7e4dbc37___; HResultErrorContract__lambda_41da0fdb9f953cc094cad49c7e4dbc37_
0x180019b32  mov     [rsp+100h+var_CC], eax
0x180019b36  mov     ebx, eax
0x180019b38  test    eax, eax
0x180019b3a  jns     loc_180019C3E
0x180019b40  mov     rcx, [rbp+3Fh]; this
0x180019b44  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180019b4b  mov     r9d, eax; char *
0x180019b4e  mov     edx, 1DEh; void *
0x180019b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b58  lea     rcx, [rsp+100h+EventDescriptor]
0x180019b5d  call    wil__details__ScopeExitFnGuard__lambda_93c817616f72b5eb0a2ebc800f1b3c45_____operator__
0x180019b62  cmp     [rbp+37h+var_A0], 1
0x180019b66  jnz     loc_180019C37
0x180019b6c  cmp     [rbp+37h+var_9C], 0
0x180019b70  jz      short loc_180019B81
0x180019b72  lea     rdx, [rbp+37h+var_88]; ActivityId
0x180019b76  mov     ecx, 4; ControlCode
0x180019b7b  call    cs:__imp_EventActivityIdControl
0x180019b81  mov     eax, cs:dword_18006E000
0x180019b87  mov     [rbp+37h+var_A0], 2
0x180019b8e  cmp     eax, 5
0x180019b91  jbe     loc_180019C37
0x180019b97  mov     rcx, cs:qword_18006E018
0x180019b9e  mov     rax, cs:qword_18006E010
0x180019ba5  test    rsi, rax
0x180019ba8  jz      loc_180019C37
0x180019bae  mov     rax, rcx
0x180019bb1  and     rax, rsi
0x180019bb4  cmp     rax, rcx
0x180019bb7  jnz     short loc_180019C37
0x180019bb9  movzx   eax, cs:word_18005F5FD
0x180019bc0  lea     r8, [rbp+37h+ActivityId]; ActivityId
0x180019bc4  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x180019bc8  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x180019bcd  mov     rax, cs:off_18006E008
0x180019bd4  sub     edi, r14d
0x180019bd7  mov     [rbp+37h+var_70.Ptr], rax
0x180019bdb  xor     r9d, r9d; RelatedActivityId
0x180019bde  mov     dword ptr [rsp+100h+EventDescriptor.Id], 0B000000h
0x180019be6  mov     [rsp+100h+EventDescriptor.Keyword], rsi
0x180019beb  movzx   eax, word ptr [rax]
0x180019bee  mov     [rbp+37h+var_70.Size], eax
0x180019bf1  lea     rax, byte_18005F607
0x180019bf8  mov     [rbp+37h+var_60], rax
0x180019bfc  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x180019c03  mov     dword ptr [rbp+37h+var_58], 20h ; ' '
0x180019c0a  mov     dword ptr [rbp+37h+var_58+4], 1
0x180019c11  mov     [rsp+100h+var_D0], edi
0x180019c15  mov     eax, [rsp+100h+var_D0]
0x180019c19  mov     rcx, cs:RegHandle; RegHandle
0x180019c20  lea     rax, [rbp+37h+var_70]
0x180019c24  mov     [rsp+100h+UserData], rax; UserData
0x180019c29  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180019c31  call    cs:__imp_EventWriteTransfer
0x180019c37  mov     eax, ebx
0x180019c39  jmp     loc_180019D1F
0x180019c3e  lea     rcx, [rsp+100h+EventDescriptor]
0x180019c43  call    wil__details__ScopeExitFnGuard__lambda_93c817616f72b5eb0a2ebc800f1b3c45_____operator__
0x180019c48  cmp     [rbp+37h+var_A0], 1
0x180019c4c  jnz     loc_180019D1D
0x180019c52  cmp     [rbp+37h+var_9C], 0
0x180019c56  jz      short loc_180019C67
0x180019c58  lea     rdx, [rbp+37h+var_88]; ActivityId
0x180019c5c  mov     ecx, 4; ControlCode
0x180019c61  call    cs:__imp_EventActivityIdControl
0x180019c67  mov     eax, cs:dword_18006E000
0x180019c6d  mov     [rbp+37h+var_A0], 2
0x180019c74  cmp     eax, 5
0x180019c77  jbe     loc_180019D1D
0x180019c7d  mov     rcx, cs:qword_18006E018
0x180019c84  mov     rax, cs:qword_18006E010
0x180019c8b  test    rsi, rax
0x180019c8e  jz      loc_180019D1D
0x180019c94  mov     rax, rcx
0x180019c97  and     rax, rsi
0x180019c9a  cmp     rax, rcx
0x180019c9d  jnz     short loc_180019D1D
0x180019c9f  movzx   eax, cs:word_18005F5FD
0x180019ca6  lea     r8, [rbp+37h+ActivityId]; ActivityId
0x180019caa  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x180019cae  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x180019cb3  mov     rax, cs:off_18006E008
0x180019cba  sub     edi, r14d
0x180019cbd  mov     [rbp+37h+var_70.Ptr], rax
0x180019cc1  xor     r9d, r9d; RelatedActivityId
0x180019cc4  mov     dword ptr [rsp+100h+EventDescriptor.Id], 0B000000h
0x180019ccc  mov     [rsp+100h+EventDescriptor.Keyword], rsi
0x180019cd1  movzx   eax, word ptr [rax]
0x180019cd4  mov     [rbp+37h+var_70.Size], eax
0x180019cd7  lea     rax, byte_18005F607
0x180019cde  mov     [rbp+37h+var_60], rax
0x180019ce2  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x180019ce9  mov     dword ptr [rbp+37h+var_58], 20h ; ' '
0x180019cf0  mov     dword ptr [rbp+37h+var_58+4], 1
0x180019cf7  mov     [rsp+100h+var_D0], edi
0x180019cfb  mov     eax, [rsp+100h+var_D0]
0x180019cff  mov     rcx, cs:RegHandle; RegHandle
0x180019d06  lea     rax, [rbp+37h+var_70]
0x180019d0a  mov     [rsp+100h+UserData], rax; UserData
0x180019d0f  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180019d17  call    cs:__imp_EventWriteTransfer
0x180019d1d  xor     eax, eax
0x180019d1f  mov     rcx, [rbp+37h+var_30]
0x180019d23  xor     rcx, rsp; StackCookie
0x180019d26  call    __security_check_cookie
0x180019d2b  add     rsp, 0E0h
0x180019d32  pop     r14
0x180019d34  pop     rdi
0x180019d35  pop     rsi
0x180019d36  pop     rbx
0x180019d37  pop     rbp
0x180019d38  retn
```
