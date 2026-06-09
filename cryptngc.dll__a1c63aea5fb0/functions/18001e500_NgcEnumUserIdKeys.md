# NgcEnumUserIdKeys

- ea: `0x18001e500`
- end: `0x18001e809`
- name: `NgcEnumUserIdKeys`
- size: `777`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028d50`
- `0x1800384e0`

## callees

- `0x180006538`
- `0x18001e500`
- `0x18002c944`
- `0x18003a510`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e632`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e743`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e7e7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e632`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e743`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e7e7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e554`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e554`

## string_xrefs

- `0x18001e698`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall NgcEnumUserIdKeys(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, char a6)
{
  int v6; // eax
  unsigned int v7; // ebx
  ULONG UserDataCount; // [rsp+20h] [rbp-79h]
  int v10; // [rsp+34h] [rbp-65h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-61h] BYREF
  __int16 v12; // [rsp+48h] [rbp-51h]
  int v13; // [rsp+50h] [rbp-49h] BYREF
  int v14; // [rsp+58h] [rbp-41h] BYREF
  char v15; // [rsp+5Ch] [rbp-3Dh]
  GUID ActivityId; // [rsp+60h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  __int16 *v18; // [rsp+90h] [rbp-9h]
  __int64 v19; // [rsp+98h] [rbp-1h]
  int *v20; // [rsp+A0h] [rbp+7h]
  __int64 v21; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]
  __int64 v23; // [rsp+F0h] [rbp+57h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+5Fh] BYREF
  __int64 v25; // [rsp+100h] [rbp+67h] BYREF
  __int64 v26; // [rsp+108h] [rbp+6Fh] BYREF

  v26 = a4;
  v25 = a3;
  v24 = a2;
  v23 = a1;
  v10 = 0;
  v14 = 0;
  v15 = 0;
  if ( (unsigned int)dword_18006E000 <= 5 )
    ActivityId = 0;
  else
    EventActivityIdControl(3u, &ActivityId);
  v14 = 1;
  if ( (unsigned int)dword_18006E000 > 5 )
  {
    v13 = v10;
    v21 = 4;
    v20 = &v13;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    v18 = &word_180060E56;
    UserData.Reserved = 2;
    v19 = 0x10000001DLL;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 3u, &UserData);
  }
  v12 = 256;
  *(_QWORD *)&EventDescriptor.Id = &v14;
  EventDescriptor.Keyword = (ULONGLONG)&v10;
  UserData.Ptr = (ULONGLONG)&v23;
  *(_QWORD *)&UserData.Size = &a5;
  v18 = (__int16 *)&a6;
  v19 = (__int64)&v24;
  v20 = (int *)&v25;
  v21 = (__int64)&v26;
  v6 = HResultErrorContract__lambda_0cdd00fcf549bea2ee2c1016e52bb9ee_(&UserData);
  v10 = v6;
  v7 = v6;
  if ( v6 >= 0 )
  {
    wil::details::ScopeExitFnGuard__lambda_1ec4bfaf849e39df46fc8555ad8a761b___::operator()(&EventDescriptor);
    if ( v14 == 1 )
    {
      v14 = 2;
      if ( (unsigned int)dword_18006E000 > 5 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = (ULONGLONG)off_18006E008;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_18006E008;
        v18 = (__int16 *)&unk_180060800;
        UserData.Reserved = 2;
        v19 = 0x100000020LL;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &UserData);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47C,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v6,
      UserDataCount);
    wil::details::ScopeExitFnGuard__lambda_1ec4bfaf849e39df46fc8555ad8a761b___::operator()(&EventDescriptor);
    if ( v14 == 1 )
    {
      v14 = 2;
      if ( (unsigned int)dword_18006E000 > 5 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = (ULONGLONG)off_18006E008;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_18006E008;
        v18 = (__int16 *)&unk_180060800;
        UserData.Reserved = 2;
        v19 = 0x100000020LL;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &UserData);
      }
    }
    return v7;
  }
}

```

## disassembly

```asm
0x18001e500  mov     [rsp-8+arg_18], r9
0x18001e505  mov     [rsp-8+arg_10], r8
0x18001e50a  mov     [rsp-8+arg_8], rdx
0x18001e50f  mov     [rsp-8+arg_0], rcx
0x18001e514  push    rbp
0x18001e515  push    rbx
0x18001e516  push    rsi
0x18001e517  push    rdi
0x18001e518  push    r14
0x18001e51a  lea     rbp, [rsp-27h]
0x18001e51f  sub     rsp, 0C0h
0x18001e526  mov     rax, cs:__security_cookie
0x18001e52d  xor     rax, rsp
0x18001e530  mov     [rbp+47h+var_30], rax
0x18001e534  mov     eax, cs:dword_18006E000
0x18001e53a  xor     esi, esi
0x18001e53c  mov     [rbp+47h+var_AC], esi
0x18001e53f  mov     [rbp+47h+var_88], esi
0x18001e542  mov     [rbp+47h+var_84], sil
0x18001e546  cmp     eax, 5
0x18001e549  jbe     short loc_18001E55C
0x18001e54b  lea     rdx, [rbp+47h+ActivityId]; ActivityId
0x18001e54f  mov     ecx, 3; ControlCode
0x18001e554  call    cs:__imp_EventActivityIdControl
0x18001e55a  jmp     short loc_18001E563
0x18001e55c  xorps   xmm0, xmm0
0x18001e55f  movups  xmmword ptr [rbp+47h+ActivityId.Data1], xmm0
0x18001e563  mov     eax, cs:dword_18006E000
0x18001e569  lea     rdi, _TraceLoggingMetadataEnd
0x18001e570  mov     [rbp+47h+var_88], 1
0x18001e577  lea     r14, _TraceLoggingMetadata
0x18001e57e  cmp     eax, 5
0x18001e581  jbe     loc_18001E638
0x18001e587  mov     eax, [rbp+47h+var_AC]
0x18001e58a  mov     [rbp+47h+var_90], eax
0x18001e58d  cmp     [rbp+47h+var_84], sil
0x18001e591  jz      short loc_18001E5AD
0x18001e593  cmp     [rbp+47h+var_70], esi
0x18001e596  jnz     short loc_18001E5A7
0x18001e598  cmp     [rbp+47h+var_6C], esi
0x18001e59b  jnz     short loc_18001E5A7
0x18001e59d  cmp     [rbp+47h+var_68], esi
0x18001e5a0  jnz     short loc_18001E5A7
0x18001e5a2  cmp     [rbp+47h+var_64], esi
0x18001e5a5  jz      short loc_18001E5AD
0x18001e5a7  lea     r9, [rbp+47h+var_70]
0x18001e5ab  jmp     short loc_18001E5B0
0x18001e5ad  mov     r9, rsi; RelatedActivityId
0x18001e5b0  lea     rax, [rbp+47h+var_90]
0x18001e5b4  mov     [rbp+47h+var_38], 4
0x18001e5bc  mov     [rbp+47h+var_40], rax
0x18001e5c0  lea     r8, [rbp+47h+ActivityId]; ActivityId
0x18001e5c4  movzx   eax, cs:word_180060E4C
0x18001e5cb  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18001e5cf  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18001e5d2  mov     rax, cs:off_18006E008
0x18001e5d9  mov     [rbp+47h+var_60.Ptr], rax
0x18001e5dd  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x18001e5e4  mov     [rbp+47h+EventDescriptor.Keyword], rsi
0x18001e5e8  movzx   eax, word ptr [rax]
0x18001e5eb  mov     [rbp+47h+var_60.Size], eax
0x18001e5ee  lea     rax, word_180060E56
0x18001e5f5  mov     [rbp+47h+var_50], rax
0x18001e5f9  mov     rax, rdi
0x18001e5fc  sub     eax, r14d
0x18001e5ff  mov     dword ptr [rbp+47h+var_60.0Ch], 2
0x18001e606  mov     dword ptr [rbp+47h+var_48], 1Dh
0x18001e60d  mov     dword ptr [rbp+47h+var_48+4], 1
0x18001e614  mov     [rbp+47h+var_B0], eax
0x18001e617  mov     eax, [rbp+47h+var_B0]
0x18001e61a  mov     rcx, cs:RegHandle; RegHandle
0x18001e621  lea     rax, [rbp+47h+var_60]
0x18001e625  mov     [rsp+0E0h+UserData], rax; UserData
0x18001e62a  mov     [rsp+0E0h+UserDataCount], 3; int
0x18001e632  call    cs:__imp_EventWriteTransfer
0x18001e638  lea     rax, [rbp+47h+var_88]
0x18001e63c  mov     [rbp+47h+var_98], 100h
0x18001e642  mov     qword ptr [rbp+47h+EventDescriptor.Id], rax
0x18001e646  lea     rcx, [rbp+47h+var_60]
0x18001e64a  lea     rax, [rbp+47h+var_AC]
0x18001e64e  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x18001e652  lea     rax, [rbp+47h+arg_0]
0x18001e656  mov     [rbp+47h+var_60.Ptr], rax
0x18001e65a  lea     rax, [rbp+47h+arg_20]
0x18001e65e  mov     qword ptr [rbp+47h+var_60.Size], rax
0x18001e662  lea     rax, [rbp+47h+arg_28]
0x18001e666  mov     [rbp+47h+var_50], rax
0x18001e66a  lea     rax, [rbp+47h+arg_8]
0x18001e66e  mov     [rbp+47h+var_48], rax
0x18001e672  lea     rax, [rbp+47h+arg_10]
0x18001e676  mov     [rbp+47h+var_40], rax
0x18001e67a  lea     rax, [rbp+47h+arg_18]
0x18001e67e  mov     [rbp+47h+var_38], rax
0x18001e682  call    HResultErrorContract__lambda_0cdd00fcf549bea2ee2c1016e52bb9ee___; HResultErrorContract__lambda_0cdd00fcf549bea2ee2c1016e52bb9ee_
0x18001e687  mov     [rbp+47h+var_AC], eax
0x18001e68a  mov     ebx, eax
0x18001e68c  test    eax, eax
0x18001e68e  jns     loc_18001E750
0x18001e694  mov     rcx, [rbp+4Fh]; this
0x18001e698  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001e69f  mov     r9d, eax; char *
0x18001e6a2  mov     edx, 47Ch; void *
0x18001e6a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e6ac  lea     rcx, [rbp+47h+EventDescriptor]
0x18001e6b0  call    wil__details__ScopeExitFnGuard__lambda_1ec4bfaf849e39df46fc8555ad8a761b_____operator__
0x18001e6b5  cmp     [rbp+47h+var_88], 1
0x18001e6b9  jnz     loc_18001E749
0x18001e6bf  mov     eax, cs:dword_18006E000
0x18001e6c5  mov     [rbp+47h+var_88], 2
0x18001e6cc  cmp     eax, 5
0x18001e6cf  jbe     short loc_18001E749
0x18001e6d1  movzx   eax, cs:word_1800607F6
0x18001e6d8  lea     r8, [rbp+47h+ActivityId]; ActivityId
0x18001e6dc  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18001e6df  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18001e6e3  mov     rax, cs:off_18006E008
0x18001e6ea  sub     edi, r14d
0x18001e6ed  mov     [rbp+47h+var_60.Ptr], rax
0x18001e6f1  xor     r9d, r9d; RelatedActivityId
0x18001e6f4  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x18001e6fb  mov     [rbp+47h+EventDescriptor.Keyword], rsi
0x18001e6ff  movzx   eax, word ptr [rax]
0x18001e702  mov     [rbp+47h+var_60.Size], eax
0x18001e705  lea     rax, unk_180060800
0x18001e70c  mov     [rbp+47h+var_50], rax
0x18001e710  mov     dword ptr [rbp+47h+var_60.0Ch], 2
0x18001e717  mov     dword ptr [rbp+47h+var_48], 20h ; ' '
0x18001e71e  mov     dword ptr [rbp+47h+var_48+4], 1
0x18001e725  mov     [rbp+47h+var_B0], edi
0x18001e728  mov     eax, [rbp+47h+var_B0]
0x18001e72b  mov     rcx, cs:RegHandle; RegHandle
0x18001e732  lea     rax, [rbp+47h+var_60]
0x18001e736  mov     [rsp+0E0h+UserData], rax; UserData
0x18001e73b  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x18001e743  call    cs:__imp_EventWriteTransfer
0x18001e749  mov     eax, ebx
0x18001e74b  jmp     loc_18001E7EF
0x18001e750  lea     rcx, [rbp+47h+EventDescriptor]
0x18001e754  call    wil__details__ScopeExitFnGuard__lambda_1ec4bfaf849e39df46fc8555ad8a761b_____operator__
0x18001e759  cmp     [rbp+47h+var_88], 1
0x18001e75d  jnz     loc_18001E7ED
0x18001e763  mov     eax, cs:dword_18006E000
0x18001e769  mov     [rbp+47h+var_88], 2
0x18001e770  cmp     eax, 5
0x18001e773  jbe     short loc_18001E7ED
0x18001e775  movzx   eax, cs:word_1800607F6
0x18001e77c  lea     r8, [rbp+47h+ActivityId]; ActivityId
0x18001e780  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18001e783  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18001e787  mov     rax, cs:off_18006E008
0x18001e78e  sub     edi, r14d
0x18001e791  mov     [rbp+47h+var_60.Ptr], rax
0x18001e795  xor     r9d, r9d; RelatedActivityId
0x18001e798  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x18001e79f  mov     [rbp+47h+EventDescriptor.Keyword], rsi
0x18001e7a3  movzx   eax, word ptr [rax]
0x18001e7a6  mov     [rbp+47h+var_60.Size], eax
0x18001e7a9  lea     rax, unk_180060800
0x18001e7b0  mov     [rbp+47h+var_50], rax
0x18001e7b4  mov     dword ptr [rbp+47h+var_60.0Ch], 2
0x18001e7bb  mov     dword ptr [rbp+47h+var_48], 20h ; ' '
0x18001e7c2  mov     dword ptr [rbp+47h+var_48+4], 1
0x18001e7c9  mov     [rbp+47h+var_B0], edi
0x18001e7cc  mov     eax, [rbp+47h+var_B0]
0x18001e7cf  mov     rcx, cs:RegHandle; RegHandle
0x18001e7d6  lea     rax, [rbp+47h+var_60]
0x18001e7da  mov     [rsp+0E0h+UserData], rax; UserData
0x18001e7df  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x18001e7e7  call    cs:__imp_EventWriteTransfer
0x18001e7ed  xor     eax, eax
0x18001e7ef  mov     rcx, [rbp+47h+var_30]
0x18001e7f3  xor     rcx, rsp; StackCookie
0x18001e7f6  call    __security_check_cookie
0x18001e7fb  add     rsp, 0C0h
0x18001e802  pop     r14
0x18001e804  pop     rdi
0x18001e805  pop     rsi
0x18001e806  pop     rbx
0x18001e807  pop     rbp
0x18001e808  retn
```
