# CSyncMLCmdStatus::BatchUpExecution(IConfigManager2 *)

- ea: `0x18000adf0`
- end: `0x18000b550`
- name: `?BatchUpExecution@CSyncMLCmdStatus@@UEAAJPEAUIConfigManager2@@@Z`
- size: `1888`
- prototype: `__int64 __fastcall(CSyncMLCmdStatus *__hidden this, struct IConfigManager2 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001008`
- `0x180003960`
- `0x18000adf0`
- `0x18000fad0`
- `0x180010728`
- `0x180014330`
- `0x180019060`
- `0x1800216c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000b2d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000b3f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000b2d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000b3f9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000af92`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b110`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b1ce`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b53f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000af92`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b110`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b1ce`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b53f`
- `DMCmnUtils!InvStrCmpIW` at `0x18000afde`
- `DMCmnUtils!InvStrCmpIW` at `0x18000afde`
- `DMCmnUtils!CopyString` at `0x18000b4a6`
- `DMCmnUtils!CopyString` at `0x18000b4a6`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdStatus::BatchUpExecution(CSyncMLCmdStatus *this, struct IConfigManager2 *a2)
{
  int appended; // ebx
  struct CSyncMLCmd **v4; // rsi
  struct CSyncMLCmd **i; // rdi
  const enum SyncMLProp near *const *v6; // r8
  int v7; // r9d
  CSyncMLMeta *v8; // rcx
  const unsigned __int16 *Type; // rax
  EVENT_DESCRIPTOR *v10; // rsi
  int v11; // eax
  __int64 v12; // rax
  bool v13; // zf
  const unsigned __int16 *v14; // rdx
  __int16 *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // ecx
  int v18; // eax
  __int64 v19; // rax
  const OLECHAR *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  const wchar_t *v24; // rcx
  unsigned int v25; // edx
  const wchar_t *v26; // rcx
  unsigned int v27; // edx
  __int64 v28; // rcx
  const unsigned __int16 *v29; // rcx
  ULONG UserDataCount; // [rsp+28h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR *p_UserData; // [rsp+30h] [rbp-41h]
  int v32; // [rsp+38h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  __int64 *v35; // [rsp+60h] [rbp-11h]
  int v36; // [rsp+68h] [rbp-9h]
  int v37; // [rsp+6Ch] [rbp-5h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+70h] [rbp-1h]
  __int64 v39; // [rsp+78h] [rbp+7h]
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+80h] [rbp+Fh] BYREF
  __int16 *v41; // [rsp+90h] [rbp+1Fh]
  int v42; // [rsp+98h] [rbp+27h]
  int v43; // [rsp+9Ch] [rbp+2Bh]

  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 40LL) )
  {
    appended = 0;
    if ( *((int *)this + 15) >= 0 )
      *((_DWORD *)this + 15) = -2102722553;
    v4 = (struct CSyncMLCmd **)*((_QWORD *)this + 4);
    for ( i = (struct CSyncMLCmd **)*((_QWORD *)this + 5); v4 != i; ++v4 )
      CSyncMLCmd::SetCmdBypassResult(*v4);
    goto LABEL_39;
  }
  appended = CSyncMLCmd::VerifyDTD(this);
  if ( appended < 0 )
    goto LABEL_37;
  if ( (*((_DWORD *)this + 42) & 2) != 0 )
  {
    v8 = (CSyncMLMeta *)*((_QWORD *)this + 22);
    if ( !v8 )
      goto LABEL_36;
    Type = CSyncMLMeta::GetType(v8);
    v10 = (EVENT_DESCRIPTOR *)Type;
    if ( Type )
    {
      v11 = GenericGetType(Type, 0xFFFFFFFF, (const unsigned __int16 **const)&c_rgszCmdAuthType, 4, (int *)this + 52);
      appended = v11;
      if ( v11 == -2147023728 )
      {
        if ( (unsigned int)dword_18003E048 > 2 )
        {
          v12 = -1;
          do
            v13 = *((_WORD *)&v10->Version + v12++) == 0;
          while ( !v13 );
          p_EventDescriptor = v10;
          v39 = (unsigned int)(2 * v12 + 2);
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_18003E050;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = (unsigned __int16)*off_18003E050;
          v35 = (__int64 *)&dword_180037024;
          UserData.Reserved = 2;
          v36 = 32;
          v37 = 1;
          v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        appended = -2147467263;
        *(_DWORD *)(*((_QWORD *)this + 10) + 244LL) = 200;
        goto LABEL_37;
      }
      if ( v11 < 0 )
        goto LABEL_37;
    }
    if ( *((_DWORD *)this + 53) != 1
      || (v14 = (const unsigned __int16 *)*((_QWORD *)this + 24)) != 0 && InvStrCmpIW(L"0", v14) )
    {
      if ( (unsigned int)dword_18003E048 <= 2 )
        goto LABEL_36;
      v21 = (const OLECHAR *)*((_QWORD *)this + 24);
      if ( v21 )
      {
        v22 = -1;
        do
          v13 = v21[++v22] == 0;
        while ( !v13 );
        v23 = 2 * v22 + 2;
      }
      else
      {
        v21 = &word_180032B28;
        v23 = 2;
      }
      v39 = v23;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      p_EventDescriptor = (EVENT_DESCRIPTOR *)v21;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v35 = qword_180037140;
      UserData.Reserved = 2;
      v36 = 29;
      v37 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      p_UserData = &UserData;
      UserDataCount = 3;
      goto LABEL_35;
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 10) + 424LL) != 4 )
    {
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        *(_DWORD *)&EventDescriptor.Level = 2;
        v40.Ptr = (ULONGLONG)off_18003E050;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        v40.Size = (unsigned __int16)*off_18003E050;
        v15 = word_18003694A;
        v42 = 29;
LABEL_34:
        v41 = v15;
        v40.Reserved = 2;
        v43 = 1;
        v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        p_UserData = &v40;
        UserDataCount = 2;
LABEL_35:
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, UserDataCount, p_UserData);
        goto LABEL_36;
      }
      goto LABEL_36;
    }
    v16 = *((_QWORD *)this + 22);
    v6 = &CSyncMLMeta::rgSupportedProps;
    v17 = 0;
    while ( *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v17) )
    {
      if ( ++v17 >= 0x10 )
      {
        v17 = -1;
        break;
      }
    }
    v18 = *(_DWORD *)(v16 + 128);
    if ( _bittest(&v18, v17) )
      v19 = *(_QWORD *)(v16 + 8LL * v17);
    else
      LODWORD(v19) = 1;
    if ( (_DWORD)v19 != 6 )
    {
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        *(_DWORD *)&EventDescriptor.Level = 2;
        v40.Ptr = (ULONGLONG)off_18003E050;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        v40.Size = (unsigned __int16)*off_18003E050;
        v15 = (__int16 *)&byte_18003723F;
        v42 = 25;
        goto LABEL_34;
      }
LABEL_36:
      appended = -2102788095;
      goto LABEL_37;
    }
  }
  v24 = (const wchar_t *)*((_QWORD *)this + 25);
  v25 = 0;
  if ( v24 )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    if ( !*v24 || (v25 = wcstoul(v24, (wchar_t **)&EventDescriptor, 10), **(_WORD **)&EventDescriptor.Id) )
    {
      appended = -2147024809;
      goto LABEL_37;
    }
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 232LL) - 1 != v25 )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      v32 = *(_DWORD *)(*((_QWORD *)this + 10) + 232LL) - 1;
      *(_DWORD *)&EventDescriptor.Id = v25;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18003E048,
        (unsigned int)byte_1800371BB,
        (_DWORD)v6,
        v7,
        (__int64)&EventDescriptor,
        (__int64)&v32);
    }
    goto LABEL_36;
  }
  v26 = (const wchar_t *)*((_QWORD *)this + 23);
  if ( !v26 )
  {
    if ( (unsigned int)dword_18003E048 > 5 )
    {
      UserData.Ptr = (ULONGLONG)off_18003E050;
      v40.Ptr = 0x50B000000LL;
      *(_QWORD *)&v40.Size = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v35 = qword_180037050;
      UserData.Reserved = 2;
      v36 = 26;
      v37 = 1;
      *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v40, 0, 0, 2u, &UserData);
    }
    goto LABEL_36;
  }
  *(_QWORD *)&EventDescriptor.Id = 0;
  if ( !*v26 )
  {
    appended = -2147024809;
    goto LABEL_37;
  }
  v27 = wcstoul(v26, (wchar_t **)&EventDescriptor, 10);
  if ( **(_WORD **)&EventDescriptor.Id )
  {
    appended = -2147024809;
    goto LABEL_37;
  }
  appended = 0;
  if ( *((_DWORD *)this + 53) != 1 )
  {
    if ( *((_DWORD *)this + 53) != 27 )
      goto LABEL_39;
    appended = CSyncMLDPU::AppendAlertStatus(*((CSyncMLDPU **)this + 10), *((const unsigned __int16 **)this + 24), v27);
    if ( appended >= 0 )
      goto LABEL_39;
    goto LABEL_37;
  }
  *(_DWORD *)(*((_QWORD *)this + 10) + 244LL) = v27;
  if ( (*((_DWORD *)this + 42) & 2) == 0 )
    goto LABEL_39;
  *(_DWORD *)(*((_QWORD *)this + 10) + 424LL) = *((_DWORD *)this + 52);
  v28 = *((_QWORD *)this + 22);
  if ( (*(_DWORD *)(v28 + 128) & 4) != 0 )
    v29 = *(const unsigned __int16 **)(v28 + 16);
  else
    v29 = 0;
  appended = CopyString(v29, 0xFFFFFFFF, (unsigned __int16 **)(*((_QWORD *)this + 10) + 432LL));
  if ( appended < 0 )
  {
LABEL_37:
    if ( *((int *)this + 15) >= 0 )
      *((_DWORD *)this + 15) = appended;
    goto LABEL_39;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v40.Ptr = 0x50B000000LL;
    *(_QWORD *)&v40.Size = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v35 = (__int64 *)&dword_180036B04;
    UserData.Reserved = 2;
    v36 = 29;
    v37 = 1;
    *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v40, 0, 0, 2u, &UserData);
  }
LABEL_39:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Id = appended;
    p_EventDescriptor = &EventDescriptor;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v39 = 4;
    v40.Ptr = 0x50B000000LL;
    *(_QWORD *)&v40.Size = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v35 = (__int64 *)byte_180037313;
    UserData.Reserved = 2;
    v36 = 29;
    v37 = 1;
    v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v40, 0, 0, 3u, &UserData);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000adf0  mov     r11, rsp
0x18000adf3  push    rbp
0x18000adf4  push    rbx
0x18000adf5  push    r12
0x18000adf7  push    r14
0x18000adf9  push    r15
0x18000adfb  lea     rbp, [r11-5Fh]
0x18000adff  sub     rsp, 0A0h
0x18000ae06  mov     rax, cs:__security_cookie
0x18000ae0d  xor     rax, rsp
0x18000ae10  mov     [rbp+57h+var_28], rax
0x18000ae14  mov     rax, [rcx+50h]
0x18000ae18  lea     r15, _TraceLoggingMetadataEnd
0x18000ae1f  mov     [r11+10h], rsi
0x18000ae23  lea     r12, _TraceLoggingMetadata
0x18000ae2a  mov     [r11+18h], rdi
0x18000ae2e  mov     rdi, rcx
0x18000ae31  cmp     dword ptr [rax+28h], 0
0x18000ae35  jz      short loc_18000AE76
0x18000ae37  xor     r14d, r14d
0x18000ae3a  mov     ebx, r14d
0x18000ae3d  cmp     [rcx+3Ch], r14d
0x18000ae41  jl      short loc_18000AE4A
0x18000ae43  mov     dword ptr [rcx+3Ch], 82AB0007h
0x18000ae4a  mov     rsi, [rcx+20h]
0x18000ae4e  mov     rdi, [rcx+28h]
0x18000ae52  cmp     rsi, rdi
0x18000ae55  jz      loc_18000B12A
0x18000ae5b  nop     dword ptr [rax+rax+00h]
0x18000ae60  mov     rcx, [rsi]; struct CSyncMLCmd *
0x18000ae63  call    ?SetCmdBypassResult@CSyncMLCmd@@SAXPEAV1@@Z; CSyncMLCmd::SetCmdBypassResult(CSyncMLCmd *)
0x18000ae68  add     rsi, 8
0x18000ae6c  cmp     rsi, rdi
0x18000ae6f  jnz     short loc_18000AE60
0x18000ae71  jmp     loc_18000B12A
0x18000ae76  call    ?VerifyDTD@CSyncMLCmd@@IEBAJXZ; CSyncMLCmd::VerifyDTD(void)
0x18000ae7b  xor     r14d, r14d
0x18000ae7e  mov     ebx, eax
0x18000ae80  test    eax, eax
0x18000ae82  js      loc_18000B121
0x18000ae88  mov     eax, [rdi+0A8h]
0x18000ae8e  test    al, 2
0x18000ae90  jz      loc_18000B2B4
0x18000ae96  mov     rcx, [rdi+0B0h]; this
0x18000ae9d  test    rcx, rcx
0x18000aea0  jz      loc_18000B11C
0x18000aea6  call    ?GetType@CSyncMLMeta@@QEBAPEBGXZ; CSyncMLMeta::GetType(void)
0x18000aeab  mov     rsi, rax
0x18000aeae  test    rax, rax
0x18000aeb1  jz      loc_18000AFBE
0x18000aeb7  lea     rcx, [rdi+0D0h]
0x18000aebe  mov     r9d, 4; int
0x18000aec4  mov     qword ptr [rsp+0C0h+UserDataCount], rcx; int *
0x18000aec9  lea     r8, ?c_rgszCmdAuthType@@3PAPEBGA; unsigned __int16 **
0x18000aed0  mov     rcx, rax; unsigned __int16 *
0x18000aed3  mov     edx, 0FFFFFFFFh; unsigned int
0x18000aed8  call    ?GenericGetType@@YAJPEBGKQEAPEBGHPEAH@Z; GenericGetType(ushort const *,ulong,ushort const * * const,int,int *)
0x18000aedd  mov     ebx, eax
0x18000aedf  cmp     eax, 80070490h
0x18000aee4  jnz     loc_18000AFB6
0x18000aeea  mov     eax, cs:dword_18003E048
0x18000aef0  cmp     eax, 2
0x18000aef3  jbe     loc_18000AF9E
0x18000aef9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000af00  cmp     [rsi+rax*2+2], r14w
0x18000af06  lea     rax, [rax+1]
0x18000af0a  jnz     short loc_18000AF00
0x18000af0c  lea     eax, ds:2[rax*2]
0x18000af13  mov     [rbp+57h+var_58], rsi
0x18000af17  mov     dword ptr [rbp+57h+var_50], eax
0x18000af1a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000af1e  movzx   eax, cs:word_18003701A
0x18000af25  xor     r9d, r9d; RelatedActivityId
0x18000af28  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000af2b  xor     r8d, r8d; ActivityId
0x18000af2e  mov     rax, cs:off_18003E050
0x18000af35  mov     [rbp+57h+UserData.Ptr], rax
0x18000af39  mov     dword ptr [rbp+57h+var_50+4], r14d
0x18000af3d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000af44  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000af48  movzx   eax, word ptr [rax]
0x18000af4b  mov     [rbp+57h+UserData.Size], eax
0x18000af4e  lea     rax, dword_180037024
0x18000af55  mov     [rbp+57h+var_68], rax
0x18000af59  mov     rax, r15
0x18000af5c  sub     eax, r12d
0x18000af5f  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x18000af66  mov     [rbp+57h+var_60], 20h ; ' '
0x18000af6d  mov     [rbp+57h+var_5C], 1
0x18000af74  mov     [rbp+57h+var_90], eax
0x18000af77  mov     eax, [rbp+57h+var_90]
0x18000af7a  mov     rcx, cs:RegHandle; RegHandle
0x18000af81  lea     rax, [rbp+57h+UserData]
0x18000af85  mov     [rsp+28h], rax; UserData
0x18000af8a  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x18000af92  call    cs:__imp_EventWriteTransfer
0x18000af99  nop     dword ptr [rax+rax+00h]
0x18000af9e  mov     rax, [rdi+50h]
0x18000afa2  mov     ebx, 80004001h
0x18000afa7  mov     dword ptr [rax+0F4h], 0C8h
0x18000afb1  jmp     loc_18000B121
0x18000afb6  test    eax, eax
0x18000afb8  js      loc_18000B121
0x18000afbe  cmp     dword ptr [rdi+0D4h], 1
0x18000afc5  jnz     loc_18000B1F9
0x18000afcb  mov     rdx, [rdi+0C0h]
0x18000afd2  test    rdx, rdx
0x18000afd5  jz      short loc_18000AFF2
0x18000afd7  lea     rcx, a0; "0"
0x18000afde  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18000afe5  nop     dword ptr [rax+rax+00h]
0x18000afea  test    eax, eax
0x18000afec  jnz     loc_18000B1F9
0x18000aff2  mov     rax, [rdi+50h]
0x18000aff6  cmp     dword ptr [rax+1A8h], 4
0x18000affd  jz      short loc_18000B047
0x18000afff  mov     eax, cs:dword_18003E048
0x18000b005  cmp     eax, 2
0x18000b008  jbe     loc_18000B11C
0x18000b00e  movzx   eax, cs:word_180036940
0x18000b015  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000b018  mov     rax, cs:off_18003E050
0x18000b01f  mov     [rbp+57h+var_48.Ptr], rax
0x18000b023  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000b02a  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000b02e  movzx   eax, word ptr [rax]
0x18000b031  mov     [rbp+57h+var_48.Size], eax
0x18000b034  lea     rax, word_18003694A
0x18000b03b  mov     [rbp+57h+var_30], 1Dh
0x18000b042  jmp     loc_18000B0D0
0x18000b047  mov     rdx, [rdi+0B0h]
0x18000b04e  lea     r8, ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps
0x18000b055  mov     ecx, r14d
0x18000b058  mov     eax, ecx
0x18000b05a  cmp     [r8+rax*4], r14d
0x18000b05e  jz      short loc_18000B06C
0x18000b060  inc     ecx
0x18000b062  cmp     ecx, 10h
0x18000b065  jb      short loc_18000B058
0x18000b067  mov     ecx, 0FFFFFFFFh
0x18000b06c  mov     eax, [rdx+80h]
0x18000b072  bt      eax, ecx
0x18000b075  jb      short loc_18000B07E
0x18000b077  mov     eax, 1
0x18000b07c  jmp     short loc_18000B084
0x18000b07e  mov     eax, ecx
0x18000b080  mov     rax, [rdx+rax*8]
0x18000b084  cmp     eax, 6
0x18000b087  jz      loc_18000B2B4
0x18000b08d  mov     eax, cs:dword_18003E048
0x18000b093  cmp     eax, 2
0x18000b096  jbe     loc_18000B11C
0x18000b09c  movzx   eax, cs:word_180037235
0x18000b0a3  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000b0a6  mov     rax, cs:off_18003E050
0x18000b0ad  mov     [rbp+57h+var_48.Ptr], rax
0x18000b0b1  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000b0b8  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000b0bc  movzx   eax, word ptr [rax]
0x18000b0bf  mov     [rbp+57h+var_48.Size], eax
0x18000b0c2  lea     rax, byte_18003723F
0x18000b0c9  mov     [rbp+57h+var_30], 19h
0x18000b0d0  mov     [rbp+57h+var_38], rax
0x18000b0d4  mov     rax, r15
0x18000b0d7  sub     eax, r12d
0x18000b0da  mov     dword ptr [rbp+57h+var_48.0Ch], 2
0x18000b0e1  mov     [rbp+57h+var_2C], 1
0x18000b0e8  mov     [rbp+57h+var_90], eax
0x18000b0eb  mov     eax, [rbp+57h+var_90]
0x18000b0ee  lea     rax, [rbp+57h+var_48]
0x18000b0f2  mov     [rsp+28h], rax; UserData
0x18000b0f7  mov     [rsp+0C0h+UserDataCount], 2; UserDataCount
0x18000b0ff  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000b103  mov     rcx, cs:RegHandle; RegHandle
0x18000b10a  xor     r9d, r9d; RelatedActivityId
0x18000b10d  xor     r8d, r8d; ActivityId
0x18000b110  call    cs:__imp_EventWriteTransfer
0x18000b117  nop     dword ptr [rax+rax+00h]
0x18000b11c  mov     ebx, 82AA0001h
0x18000b121  cmp     [rdi+3Ch], r14d
0x18000b125  jl      short loc_18000B12A
0x18000b127  mov     [rdi+3Ch], ebx
0x18000b12a  mov     eax, cs:dword_18003E048
0x18000b130  mov     rdi, [rsp+0C0h+arg_10]
0x18000b138  mov     rsi, [rsp+0C0h+arg_8]
0x18000b140  cmp     eax, 5
0x18000b143  jbe     loc_18000B1DA
0x18000b149  lea     rax, [rbp+57h+EventDescriptor]
0x18000b14d  mov     dword ptr [rbp+57h+EventDescriptor.Id], ebx
0x18000b150  mov     [rbp+57h+var_58], rax
0x18000b154  lea     rdx, [rbp+57h+var_48]; EventDescriptor
0x18000b158  movzx   eax, cs:word_180037309
0x18000b15f  sub     r15d, r12d
0x18000b162  mov     dword ptr [rbp+57h+var_48.Ptr+4], eax
0x18000b165  xor     r9d, r9d; RelatedActivityId
0x18000b168  mov     rax, cs:off_18003E050
0x18000b16f  xor     r8d, r8d; ActivityId
0x18000b172  mov     [rbp+57h+UserData.Ptr], rax
0x18000b176  mov     [rbp+57h+var_50], 4
0x18000b17e  mov     dword ptr [rbp+57h+var_48.Ptr], 0B000000h
0x18000b185  mov     qword ptr [rbp+57h+var_48.Size], r14
0x18000b189  movzx   eax, word ptr [rax]
0x18000b18c  mov     [rbp+57h+UserData.Size], eax
0x18000b18f  lea     rax, byte_180037313
0x18000b196  mov     [rbp+57h+var_68], rax
0x18000b19a  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x18000b1a1  mov     [rbp+57h+var_60], 1Dh
0x18000b1a8  mov     [rbp+57h+var_5C], 1
0x18000b1af  mov     [rbp+57h+var_90], r15d
0x18000b1b3  mov     eax, [rbp+57h+var_90]
0x18000b1b6  mov     rcx, cs:RegHandle; RegHandle
0x18000b1bd  lea     rax, [rbp+57h+UserData]
0x18000b1c1  mov     [rsp+28h], rax; UserData
0x18000b1c6  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x18000b1ce  call    cs:__imp_EventWriteTransfer
0x18000b1d5  nop     dword ptr [rax+rax+00h]
0x18000b1da  mov     eax, ebx
0x18000b1dc  mov     rcx, [rbp+57h+var_28]
0x18000b1e0  xor     rcx, rsp; StackCookie
0x18000b1e3  call    __security_check_cookie
0x18000b1e8  add     rsp, 0A0h
0x18000b1ef  pop     r15
0x18000b1f1  pop     r14
0x18000b1f3  pop     r12
0x18000b1f5  pop     rbx
0x18000b1f6  pop     rbp
0x18000b1f7  retn
0x18000b1f9  mov     eax, cs:dword_18003E048
0x18000b1ff  cmp     eax, 2
0x18000b202  jbe     loc_18000B11C
0x18000b208  mov     rcx, [rdi+0C0h]
0x18000b20f  test    rcx, rcx
0x18000b212  jz      short loc_18000B235
0x18000b214  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b21b  nop     dword ptr [rax+rax+00h]
0x18000b220  cmp     [rcx+rax*2+2], r14w
0x18000b226  lea     rax, [rax+1]
0x18000b22a  jnz     short loc_18000B220
0x18000b22c  lea     eax, ds:2[rax*2]
0x18000b233  jmp     short loc_18000B241
0x18000b235  lea     rcx, word_180032B28
0x18000b23c  mov     eax, 2
0x18000b241  mov     dword ptr [rbp+57h+var_50], eax
0x18000b244  movzx   eax, cs:word_180037136
0x18000b24b  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000b24e  mov     rax, cs:off_18003E050
0x18000b255  mov     [rbp+57h+UserData.Ptr], rax
0x18000b259  mov     [rbp+57h+var_58], rcx
0x18000b25d  mov     dword ptr [rbp+57h+var_50+4], r14d
0x18000b261  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000b268  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000b26c  movzx   eax, word ptr [rax]
0x18000b26f  mov     [rbp+57h+UserData.Size], eax
0x18000b272  lea     rax, qword_180037140
0x18000b279  mov     [rbp+57h+var_68], rax
0x18000b27d  mov     rax, r15
0x18000b280  sub     eax, r12d
0x18000b283  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x18000b28a  mov     [rbp+57h+var_60], 1Dh
0x18000b291  mov     [rbp+57h+var_5C], 1
0x18000b298  mov     [rbp+57h+var_90], eax
0x18000b29b  mov     eax, [rbp+57h+var_90]
0x18000b29e  lea     rax, [rbp+57h+UserData]
0x18000b2a2  mov     [rsp+28h], rax
0x18000b2a7  mov     [rsp+0C0h+UserDataCount], 3
0x18000b2af  jmp     loc_18000B0FF
0x18000b2b4  mov     rcx, [rdi+0C8h]; String
0x18000b2bb  mov     edx, r14d
0x18000b2be  test    rcx, rcx
0x18000b2c1  jz      short loc_18000B2F9
0x18000b2c3  mov     qword ptr [rbp+57h+EventDescriptor.Id], r14
0x18000b2c7  cmp     r14w, [rcx]
0x18000b2cb  jz      short loc_18000B2EF
0x18000b2cd  mov     r8d, 0Ah; Radix
0x18000b2d3  lea     rdx, [rbp+57h+EventDescriptor]; EndPtr
0x18000b2d7  call    cs:__imp_wcstoul
0x18000b2de  nop     dword ptr [rax+rax+00h]
0x18000b2e3  mov     rcx, qword ptr [rbp+57h+EventDescriptor.Id]
0x18000b2e7  mov     edx, eax
0x18000b2e9  cmp     r14w, [rcx]
0x18000b2ed  jz      short loc_18000B2F9
0x18000b2ef  mov     ebx, 80070057h
0x18000b2f4  jmp     loc_18000B121
0x18000b2f9  mov     rax, [rdi+50h]
0x18000b2fd  mov     ecx, [rax+0E8h]
0x18000b303  dec     ecx
0x18000b305  cmp     ecx, edx
0x18000b307  jz      short loc_18000B354
0x18000b309  mov     eax, cs:dword_18003E048
0x18000b30f  cmp     eax, 2
0x18000b312  jbe     loc_18000B11C
0x18000b318  mov     rax, [rdi+50h]
0x18000b31c  mov     ecx, [rax+0E8h]
0x18000b322  lea     rax, [rbp+57h+var_90]
0x18000b326  dec     ecx
0x18000b328  mov     [rsp+28h], rax
0x18000b32d  mov     [rbp+57h+var_90], ecx
0x18000b330  lea     rax, [rbp+57h+EventDescriptor]
0x18000b334  mov     dword ptr [rbp+57h+EventDescriptor.Id], edx
0x18000b337  lea     rcx, dword_18003E048
  ... truncated ...
```
