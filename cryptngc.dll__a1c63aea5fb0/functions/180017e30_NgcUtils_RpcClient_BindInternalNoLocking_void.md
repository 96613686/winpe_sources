# NgcUtils::RpcClient::BindInternalNoLocking(void)

- ea: `0x180017e30`
- end: `0x180018308`
- name: `?BindInternalNoLocking@RpcClient@NgcUtils@@AEAAJXZ`
- size: `1240`
- prototype: `__int64 __fastcall(NgcUtils::RpcClient *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017df0`
- `0x180043e70`

## callees

- `0x180016508`
- `0x180017e30`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017efe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017fc5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018161`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018295`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017efe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017fc5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018161`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018295`
- `RPCRT4!RpcBindingCreateW` at `0x180018096`
- `RPCRT4!RpcBindingCreateW` at `0x180018096`
- `RPCRT4!RpcBindingBind` at `0x1800181aa`
- `RPCRT4!RpcBindingBind` at `0x1800181aa`

## pseudocode

```c
__int64 __fastcall NgcUtils::RpcClient::BindInternalNoLocking(NgcUtils::RpcClient *this)
{
  RPC_STATUS v3; // eax
  signed int v4; // ebx
  int v5; // esi
  RPC_STATUS v6; // eax
  int v7; // ecx
  unsigned int v8; // [rsp+30h] [rbp-D0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v11[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+60h] [rbp-A0h]
  __int64 v13; // [rsp+68h] [rbp-98h]
  __int64 v14; // [rsp+70h] [rbp-90h]
  __int64 v15; // [rsp+78h] [rbp-88h]
  __int64 v16; // [rsp+80h] [rbp-80h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+88h] [rbp-78h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+B0h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+E8h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F8h] [rbp-8h] BYREF
  __int16 *v21; // [rsp+108h] [rbp+8h]
  int v22; // [rsp+110h] [rbp+10h]
  int v23; // [rsp+114h] [rbp+14h]
  unsigned int *v24; // [rsp+118h] [rbp+18h]
  __int64 v25; // [rsp+120h] [rbp+20h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+128h] [rbp+28h] BYREF
  __int16 *v27; // [rsp+138h] [rbp+38h]
  int v28; // [rsp+140h] [rbp+40h]
  int v29; // [rsp+144h] [rbp+44h]
  __int64 *v30; // [rsp+148h] [rbp+48h]
  __int64 v31; // [rsp+150h] [rbp+50h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( (unsigned int)dword_18006E000 > 3 )
    {
      *(_DWORD *)&EventDescriptor.Level = 3;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v21 = &word_18006396E;
      UserData.Reserved = 2;
      v22 = 25;
      v23 = 1;
      LODWORD(v10) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    }
    return 0;
  }
  else if ( *((int *)this + 12) >= 0 )
  {
    Template.ProtocolSequence = *((_DWORD *)this + 6);
    memset(&Template.ProtocolSequence + 1, 0, 44);
    v11[1] = *((_DWORD *)this + 7);
    v11[2] = *((_DWORD *)this + 8);
    v11[3] = *((_DWORD *)this + 9);
    v14 = *((_QWORD *)this + 7);
    v16 = *((_QWORD *)this + 11);
    Security.SecurityQos = (RPC_SECURITY_QOS *)v11;
    *(_QWORD *)&Template.Version = 1;
    v11[0] = 5;
    v12 = 0;
    v13 = 0;
    v15 = 1;
    *(_QWORD *)&Security.Version = 1;
    Security.ServerPrincName = 0;
    Security.AuthnLevel = 6;
    Security.AuthnSvc = 10;
    Security.AuthIdentity = 0;
    Options.Version = 1;
    Options.Flags = 1;
    *(_QWORD *)&Options.ComTimeout = 5;
    v3 = RpcBindingCreateW(&Template, &Security, &Options, (RPC_BINDING_HANDLE *)this + 2);
    if ( v3 )
    {
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      else
        v4 = v3;
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v8 = v3;
        v24 = &v8;
        *(_DWORD *)&EventDescriptor.Level = 2;
        UserData.Ptr = (ULONGLONG)off_18006E008;
        v25 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_18006E008;
        v21 = (__int16 *)&unk_1800638F8;
        UserData.Reserved = 2;
        v22 = 45;
        v23 = 1;
        LODWORD(v10) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
    }
    else
    {
      v5 = 0;
      *(_QWORD *)&EventDescriptor.Id = this;
      LOWORD(EventDescriptor.Keyword) = 258;
      while ( 1 )
      {
        v6 = RpcBindingBind(0, *((RPC_BINDING_HANDLE *)this + 2), *((RPC_IF_HANDLE *)this + 5));
        v4 = v6;
        if ( v6 > 0 )
          v4 = (unsigned __int16)v6 | 0x80070000;
        if ( v4 >= 0 )
          break;
        if ( (unsigned int)dword_18006E000 > 2
          && (qword_18006E010 & 0x200000000000LL) != 0
          && (qword_18006E018 & 0x200000000000LL) == qword_18006E018 )
        {
          *(_QWORD *)&UserData.Size = 0x200000000000LL;
          v31 = 8;
          UserData.Ptr = 0x20B000000LL;
          v10 = v4;
          v30 = &v10;
          v26.Ptr = (ULONGLONG)off_18006E008;
          v26.Size = *(unsigned __int16 *)off_18006E008;
          v27 = &word_1800638CE;
          v26.Reserved = 2;
          v28 = 30;
          v29 = 1;
          v8 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 3u, &v26);
        }
        if ( (unsigned int)(v4 + 2147023179) > 0xA || (v7 = 1601, !_bittest(&v7, v4 + 2147023179)) )
        {
          *((_DWORD *)this + 12) = v4;
          goto LABEL_29;
        }
        if ( (unsigned int)++v5 >= 0x14 )
          goto LABEL_29;
      }
      BYTE1(EventDescriptor.Keyword) = 0;
LABEL_29:
      wil::details::ScopeExitFnGuard__lambda_22ea034c96aed9483165fa2d3e8cbb87___::operator()(&EventDescriptor);
    }
    return (unsigned int)v4;
  }
  else
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v10) = *((_DWORD *)this + 12);
      v25 = 4;
      v24 = (unsigned int *)&v10;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v21 = (__int16 *)byte_180063931;
      UserData.Reserved = 2;
      v22 = 49;
      v23 = 1;
      v8 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    return *((unsigned int *)this + 12);
  }
}

```

## disassembly

```asm
0x180017e30  mov     [rsp-8+arg_18], rdi
0x180017e35  push    rbp
0x180017e36  push    r12
0x180017e38  push    r13
0x180017e3a  push    r14
0x180017e3c  push    r15
0x180017e3e  lea     rbp, [rsp-60h]
0x180017e43  sub     rsp, 160h
0x180017e4a  mov     rax, cs:__security_cookie
0x180017e51  xor     rax, rsp
0x180017e54  mov     [rbp+80h+var_28], rax
0x180017e58  cmp     qword ptr [rcx+10h], 0
0x180017e5d  mov     rdi, rcx
0x180017e60  jz      loc_180017F0B
0x180017e66  mov     eax, cs:dword_18006E000
0x180017e6c  cmp     eax, 3
0x180017e6f  jbe     loc_180017F04
0x180017e75  movzx   eax, cs:word_180063964
0x180017e7c  lea     r15, _TraceLoggingMetadataEnd
0x180017e83  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180017e87  lea     r13, _TraceLoggingMetadata
0x180017e8e  mov     rax, cs:off_18006E008
0x180017e95  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x180017e9a  mov     [rbp+80h+var_88.Ptr], rax
0x180017e9e  xor     r14d, r14d
0x180017ea1  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180017ea9  sub     r15d, r13d
0x180017eac  mov     [rsp+180h+EventDescriptor.Keyword], r14
0x180017eb1  xor     r9d, r9d; RelatedActivityId
0x180017eb4  movzx   eax, word ptr [rax]
0x180017eb7  xor     r8d, r8d; ActivityId
0x180017eba  mov     [rbp+80h+var_88.Size], eax
0x180017ebd  lea     rax, word_18006396E
0x180017ec4  mov     [rbp+80h+var_78], rax
0x180017ec8  mov     dword ptr [rbp+80h+var_88.0Ch], 2
0x180017ecf  mov     [rbp+80h+var_70], 19h
0x180017ed6  mov     [rbp+80h+var_6C], 1
0x180017edd  mov     dword ptr [rsp+180h+var_138], r15d
0x180017ee2  mov     eax, dword ptr [rsp+180h+var_138]
0x180017ee6  mov     rcx, cs:RegHandle; RegHandle
0x180017eed  lea     rax, [rbp+80h+var_88]
0x180017ef1  mov     [rsp+180h+UserData], rax; UserData
0x180017ef6  mov     [rsp+180h+UserDataCount], 2; UserDataCount
0x180017efe  call    cs:__imp_EventWriteTransfer
0x180017f04  xor     eax, eax
0x180017f06  jmp     loc_1800182E3
0x180017f0b  cmp     dword ptr [rcx+30h], 0
0x180017f0f  jge     loc_180017FD3
0x180017f15  mov     eax, cs:dword_18006E000
0x180017f1b  cmp     eax, 2
0x180017f1e  jbe     loc_180017FCB
0x180017f24  mov     eax, [rcx+30h]
0x180017f27  lea     r15, _TraceLoggingMetadataEnd
0x180017f2e  mov     dword ptr [rsp+180h+var_138], eax
0x180017f32  lea     r13, _TraceLoggingMetadata
0x180017f39  lea     rax, [rsp+180h+var_138]
0x180017f3e  mov     [rbp+80h+var_60], 4
0x180017f46  mov     [rbp+80h+var_68], rax
0x180017f4a  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x180017f4f  movzx   eax, cs:word_180063927
0x180017f56  xor     r14d, r14d
0x180017f59  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180017f5d  sub     r15d, r13d
0x180017f60  mov     rax, cs:off_18006E008
0x180017f67  xor     r9d, r9d; RelatedActivityId
0x180017f6a  mov     [rbp+80h+var_88.Ptr], rax
0x180017f6e  xor     r8d, r8d; ActivityId
0x180017f71  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180017f79  mov     [rsp+180h+EventDescriptor.Keyword], r14
0x180017f7e  movzx   eax, word ptr [rax]
0x180017f81  mov     [rbp+80h+var_88.Size], eax
0x180017f84  lea     rax, byte_180063931
0x180017f8b  mov     [rbp+80h+var_78], rax
0x180017f8f  mov     dword ptr [rbp+80h+var_88.0Ch], 2
0x180017f96  mov     [rbp+80h+var_70], 31h ; '1'
0x180017f9d  mov     [rbp+80h+var_6C], 1
0x180017fa4  mov     [rsp+180h+var_150], r15d
0x180017fa9  mov     eax, [rsp+180h+var_150]
0x180017fad  mov     rcx, cs:RegHandle; RegHandle
0x180017fb4  lea     rax, [rbp+80h+var_88]
0x180017fb8  mov     [rsp+180h+UserData], rax; UserData
0x180017fbd  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x180017fc5  call    cs:__imp_EventWriteTransfer
0x180017fcb  mov     eax, [rdi+30h]
0x180017fce  jmp     loc_1800182E3
0x180017fd3  mov     eax, [rcx+18h]
0x180017fd6  lea     r9, [rcx+10h]; Binding
0x180017fda  mov     [rbp+80h+Template.ProtocolSequence], eax
0x180017fdd  lea     r8, [rbp+80h+Options]; Options
0x180017fe1  xor     eax, eax
0x180017fe3  mov     [rsp+180h+arg_8], rbx
0x180017feb  mov     dword ptr [rbp+80h+Template+0Ch], eax
0x180017fee  lea     rdx, [rbp+80h+Security]; Security
0x180017ff2  mov     qword ptr [rbp+80h+Template.ObjectUuid.Data2], rax
0x180017ff6  xor     r14d, r14d
0x180017ff9  mov     dword ptr [rbp+80h+Template.ObjectUuid.Data4+4], eax
0x180017ffc  xorps   xmm0, xmm0
0x180017fff  mov     eax, [rcx+1Ch]
0x180018002  mov     [rsp+180h+var_12C], eax
0x180018006  mov     eax, [rcx+20h]
0x180018009  mov     [rsp+180h+var_128], eax
0x18001800d  mov     eax, [rcx+24h]
0x180018010  mov     [rsp+180h+var_124], eax
0x180018014  mov     rax, [rcx+38h]
0x180018018  mov     [rsp+180h+var_110], rax
0x18001801d  mov     rax, [rcx+58h]
0x180018021  lea     rcx, [rbp+80h+Template]; Template
0x180018025  mov     [rbp+80h+var_100], rax
0x180018029  lea     rax, [rsp+180h+var_130]
0x18001802e  mov     [rbp+80h+Security.SecurityQos], rax
0x180018032  mov     qword ptr [rbp+80h+Template.Version], 1
0x18001803a  movdqu  xmmword ptr [rbp+80h+Template.NetworkAddress], xmm0
0x18001803f  mov     qword ptr [rbp+80h+Template.u1], r14
0x180018043  mov     [rbp+80h+Template.ObjectUuid.Data1], r14d
0x180018047  mov     [rsp+180h+var_130], 5
0x18001804f  mov     [rsp+180h+var_120], r14
0x180018054  mov     [rsp+180h+var_118], r14
0x180018059  mov     [rsp+180h+var_108], 1
0x180018062  mov     qword ptr [rbp+80h+Security.Version], 1
0x18001806a  mov     [rbp+80h+Security.ServerPrincName], r14
0x18001806e  mov     [rbp+80h+Security.AuthnLevel], 6
0x180018075  mov     [rbp+80h+Security.AuthnSvc], 0Ah
0x18001807c  mov     [rbp+80h+Security.AuthIdentity], r14
0x180018080  mov     [rbp+80h+Options.Version], 1
0x180018087  mov     [rbp+80h+Options.Flags], 1
0x18001808e  mov     qword ptr [rbp+80h+Options.ComTimeout], 5
0x180018096  call    cs:__imp_RpcBindingCreateW
0x18001809c  mov     ecx, eax
0x18001809e  test    eax, eax
0x1800180a0  jz      loc_18001816C
0x1800180a6  test    eax, eax
0x1800180a8  jg      short loc_1800180AE
0x1800180aa  mov     ebx, eax
0x1800180ac  jmp     short loc_1800180B7
0x1800180ae  movzx   ebx, cx
0x1800180b1  or      ebx, 80070000h
0x1800180b7  mov     eax, cs:dword_18006E000
0x1800180bd  cmp     eax, 2
0x1800180c0  jbe     loc_1800182D9
0x1800180c6  mov     [rsp+180h+var_150], ecx
0x1800180ca  lea     rax, [rsp+180h+var_150]
0x1800180cf  mov     [rbp+80h+var_68], rax
0x1800180d3  lea     r15, _TraceLoggingMetadataEnd
0x1800180da  movzx   eax, cs:word_1800638EE
0x1800180e1  lea     r13, _TraceLoggingMetadata
0x1800180e8  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x1800180ec  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x1800180f1  mov     rax, cs:off_18006E008
0x1800180f8  sub     r15d, r13d
0x1800180fb  mov     [rbp+80h+var_88.Ptr], rax
0x1800180ff  xor     r9d, r9d; RelatedActivityId
0x180018102  mov     [rbp+80h+var_60], 4
0x18001810a  xor     r8d, r8d; ActivityId
0x18001810d  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180018115  mov     [rsp+180h+EventDescriptor.Keyword], r14
0x18001811a  movzx   eax, word ptr [rax]
0x18001811d  mov     [rbp+80h+var_88.Size], eax
0x180018120  lea     rax, unk_1800638F8
0x180018127  mov     [rbp+80h+var_78], rax
0x18001812b  lea     rax, [rbp+80h+var_88]
0x18001812f  mov     dword ptr [rbp+80h+var_88.0Ch], 2
0x180018136  mov     [rbp+80h+var_70], 2Dh ; '-'
0x18001813d  mov     [rbp+80h+var_6C], 1
0x180018144  mov     [rsp+180h+UserData], rax; UserData
0x180018149  mov     dword ptr [rsp+180h+var_138], r15d
0x18001814e  mov     ecx, dword ptr [rsp+180h+var_138]
0x180018152  mov     rcx, cs:RegHandle; RegHandle
0x180018159  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x180018161  call    cs:__imp_EventWriteTransfer
0x180018167  jmp     loc_1800182D9
0x18001816c  mov     [rsp+180h+arg_10], rsi
0x180018174  lea     r15, _TraceLoggingMetadataEnd
0x18001817b  mov     esi, r14d
0x18001817e  mov     qword ptr [rsp+180h+EventDescriptor.Id], rdi
0x180018183  mov     word ptr [rsp+180h+EventDescriptor.Keyword], 102h
0x18001818a  lea     r13, _TraceLoggingMetadata
0x180018191  nop     dword ptr [rax+00h]
0x180018195  nop     word ptr [rax+rax+00000000h]
0x1800181a0  mov     r8, [rdi+28h]; IfSpec
0x1800181a4  xor     ecx, ecx; pAsync
0x1800181a6  mov     rdx, [rdi+10h]; Binding
0x1800181aa  call    cs:__imp_RpcBindingBind
0x1800181b0  mov     ebx, eax
0x1800181b2  test    eax, eax
0x1800181b4  jle     short loc_1800181BF
0x1800181b6  movzx   ebx, ax
0x1800181b9  or      ebx, 80070000h
0x1800181bf  test    ebx, ebx
0x1800181c1  jns     loc_1800182C2
0x1800181c7  mov     eax, cs:dword_18006E000
0x1800181cd  cmp     eax, 2
0x1800181d0  jbe     loc_18001829B
0x1800181d6  mov     rcx, cs:qword_18006E018
0x1800181dd  mov     rdx, 200000000000h
0x1800181e7  mov     rax, cs:qword_18006E010
0x1800181ee  test    rdx, rax
0x1800181f1  jz      loc_18001829B
0x1800181f7  mov     rax, rcx
0x1800181fa  and     rax, rdx
0x1800181fd  cmp     rax, rcx
0x180018200  jnz     loc_18001829B
0x180018206  mov     qword ptr [rbp+80h+var_88.Size], rdx
0x18001820a  xor     r9d, r9d; RelatedActivityId
0x18001820d  mov     [rbp+80h+var_30], 8
0x180018215  lea     rdx, [rbp+80h+var_88]; EventDescriptor
0x180018219  mov     dword ptr [rbp+80h+var_88.Ptr], 0B000000h
0x180018220  xor     r8d, r8d; ActivityId
0x180018223  movsxd  rax, ebx
0x180018226  mov     [rsp+180h+var_138], rax
0x18001822b  lea     rax, [rsp+180h+var_138]
0x180018230  mov     [rbp+80h+var_38], rax
0x180018234  movzx   eax, cs:word_1800638C4
0x18001823b  mov     dword ptr [rbp+80h+var_88.Ptr+4], eax
0x18001823e  mov     rax, cs:off_18006E008
0x180018245  mov     [rbp+80h+var_58.Ptr], rax
0x180018249  movzx   eax, word ptr [rax]
0x18001824c  mov     [rbp+80h+var_58.Size], eax
0x18001824f  lea     rax, word_1800638CE
0x180018256  mov     [rbp+80h+var_48], rax
0x18001825a  mov     rax, r15
0x18001825d  sub     eax, r13d
0x180018260  mov     dword ptr [rbp+80h+var_58.0Ch], 2
0x180018267  mov     [rbp+80h+var_40], 1Eh
0x18001826e  mov     [rbp+80h+var_3C], 1
0x180018275  mov     [rsp+180h+var_150], eax
0x180018279  mov     eax, [rsp+180h+var_150]
0x18001827d  mov     rcx, cs:RegHandle; RegHandle
0x180018284  lea     rax, [rbp+80h+var_58]
0x180018288  mov     [rsp+180h+UserData], rax; UserData
0x18001828d  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x180018295  call    cs:__imp_EventWriteTransfer
0x18001829b  lea     eax, [rbx+7FF8F94Bh]
0x1800182a1  cmp     eax, 0Ah
0x1800182a4  ja      short loc_1800182BD
0x1800182a6  mov     ecx, 641h
0x1800182ab  bt      ecx, eax
0x1800182ae  jnb     short loc_1800182BD
0x1800182b0  inc     esi
0x1800182b2  cmp     esi, 14h
0x1800182b5  jb      loc_1800181A0
0x1800182bb  jmp     short loc_1800182C7
0x1800182bd  mov     [rdi+30h], ebx
0x1800182c0  jmp     short loc_1800182C7
0x1800182c2  mov     byte ptr [rsp+180h+EventDescriptor.Keyword+1], r14b
0x1800182c7  lea     rcx, [rsp+180h+EventDescriptor]
0x1800182cc  call    wil__details__ScopeExitFnGuard__lambda_22ea034c96aed9483165fa2d3e8cbb87_____operator__
0x1800182d1  mov     rsi, [rsp+180h+arg_10]
0x1800182d9  mov     eax, ebx
0x1800182db  mov     rbx, [rsp+180h+arg_8]
0x1800182e3  mov     rcx, [rbp+80h+var_28]
0x1800182e7  xor     rcx, rsp; StackCookie
0x1800182ea  call    __security_check_cookie
0x1800182ef  mov     rdi, [rsp+180h+arg_18]
0x1800182f7  add     rsp, 160h
0x1800182fe  pop     r15
0x180018300  pop     r14
0x180018302  pop     r13
0x180018304  pop     r12
0x180018306  pop     rbp
0x180018307  retn
```
