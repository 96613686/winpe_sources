# PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)

- ea: `0x180010430`
- end: `0x180010f21`
- name: `?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z`
- size: `2801`
- prototype: `int(unsigned int, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8 *, unsigned int *, unsigned int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800093a8`

## callees

- `0x180001210`
- `0x1800012dc`
- `0x1800013ac`
- `0x180001450`
- `0x180003b40`
- `0x180005da0`
- `0x1800069b0`
- `0x180007740`
- `0x180008050`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000abc4`
- `0x18000c774`
- `0x1800102c0`
- `0x180010430`
- `0x180010f28`
- `0x180011180`
- `0x1800117f0`
- `0x18001e431`

## import_xrefs

- `ntdll!NtReadFile` at `0x180010da2`
- `ntdll!NtReadFile` at `0x180010da2`
- `ntdll!NtQueryInformationFile` at `0x180010cb1`
- `ntdll!NtQueryInformationFile` at `0x180010cb1`
- `ntdll!NtOpenFile` at `0x180010c4f`
- `ntdll!NtOpenFile` at `0x180010c4f`
- `ntdll!NtSetInformationFile` at `0x180010a31`
- `ntdll!NtSetInformationFile` at `0x180010a31`
- `ntdll!NtFlushBuffersFile` at `0x180010929`
- `ntdll!NtFlushBuffersFile` at `0x180010929`
- `ntdll!NtWriteFile` at `0x1800108a4`
- `ntdll!NtWriteFile` at `0x1800108a4`
- `ntdll!NtCreateFile` at `0x1800107f0`
- `ntdll!NtCreateFile` at `0x1800107f0`
- `ntdll!RtlInitUnicodeString` at `0x180010724`
- `ntdll!RtlInitUnicodeString` at `0x180010bfa`
- `ntdll!RtlInitUnicodeString` at `0x180010724`
- `ntdll!RtlInitUnicodeString` at `0x180010bfa`
- `ntdll!NtClose` at `0x180010ef2`
- `ntdll!NtClose` at `0x180010ef2`

## pseudocode

```c
__int64 __fastcall PerfGetNames(
        int a1,
        const struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int16 *a7)
{
  int v8; // r8d
  int v9; // r14d
  unsigned int v11; // eax
  unsigned __int16 *v12; // r15
  __int64 v13; // rdx
  WCHAR *v14; // rbx
  __int64 i; // rcx
  unsigned __int16 v16; // ax
  unsigned __int16 *v17; // rax
  unsigned int v18; // r14d
  WCHAR *v19; // rbx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  NTSTATUS v26; // esi
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  int LowPart; // ebx
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  HANDLE v38; // rcx
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  void *v50; // rcx
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  int v54; // eax
  int v55; // eax
  __int64 Information_low; // rsi
  unsigned int LangIdFromSzLang; // eax
  unsigned int v58; // r15d
  NTSTATUS File; // eax
  _QWORD *v60; // rcx
  ULONG ShareAccess; // [rsp+30h] [rbp-D0h]
  int v62; // [rsp+60h] [rbp-A0h] BYREF
  bool v63; // [rsp+64h] [rbp-9Ch]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  union _LARGE_INTEGER ByteOffset[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD FileInformation[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E4h] [rbp-1Ch]
  _BYTE v73[26]; // [rsp+E8h] [rbp-18h] BYREF
  int v74; // [rsp+102h] [rbp+2h]
  __int16 v75; // [rsp+106h] [rbp+6h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  __int64 v77; // [rsp+118h] [rbp+18h]
  int v78; // [rsp+120h] [rbp+20h] BYREF
  __int64 v79; // [rsp+124h] [rbp+24h]
  int v80; // [rsp+12Ch] [rbp+2Ch]
  __int64 v81; // [rsp+130h] [rbp+30h]
  wchar_t v82; // [rsp+138h] [rbp+38h]

  v8 = a1 & 0x10000;
  v9 = 104;
  LODWORD(FileHandle) = a1 & 0x10000;
  v63 = (unsigned __int16)(a1 - 7) <= 1u;
  if ( (((_WORD)a1 - 5) & 0xFFFD) == 0 )
    v9 = 99;
  v62 = v9;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dZ(*((_QWORD *)WPP_GLOBAL_Control + 2), a1, v8, (unsigned __int16)a1, (__int64)a3);
    v8 = (int)FileHandle;
  }
  if ( a7 )
  {
    v11 = GetLangIdFromSzLang(a7) & 0x3FF;
    if ( v11 == 4 || v11 == 22 || (v12 = (unsigned __int16 *)PerflibCheckPerfFile(a7)) == 0 )
      v12 = a7;
  }
  else
  {
    v13 = v8 != 0 ? 11 : 7;
    v14 = &a3->Buffer[v13];
    for ( i = v8 != 0 ? 14 : 10; a3->Length >= (unsigned __int64)(2 * i); i = (unsigned int)(v13 + 3) )
    {
      if ( (unsigned __int16)(*v14 - 48) <= 9u )
        goto LABEL_16;
      ++v14;
      LODWORD(v13) = v13 + 1;
    }
    v14 = (WCHAR *)L"009";
LABEL_16:
    Perflib004Update(v14);
    v12 = (unsigned __int16 *)PerflibCheckPerfFile(v14);
    if ( !v12 )
      v12 = v14;
  }
  v82 = a01234567Dat[12];
  v81 = *(_QWORD *)L".dat";
  v78 = 3211312;
  v79 = 0x35003400330032LL;
  v80 = 3604534;
  if ( (unsigned __int16)(v12[3] - 48) > 9u )
  {
    v78 = 6619248;
    LODWORD(v79) = 6684786;
    WORD2(v79) = v9;
    HIWORD(v79) = *v12;
    LOWORD(v80) = v12[1];
    v16 = v12[2];
  }
  else
  {
    v78 = 7471216;
    LOWORD(v79) = 102;
    WORD1(v79) = v9;
    HIDWORD(v79) = *(_DWORD *)v12;
    LOWORD(v80) = v12[2];
    v16 = v12[3];
  }
  HIWORD(v80) = v16;
  v17 = (unsigned __int16 *)operator new(68);
  v18 = 0;
  v19 = v17;
  if ( v17 )
  {
    if ( !v63 )
    {
      v55 = StringCbPrintfW(v17, 0x44u, L"%.*ls\\%ls");
      if ( v55 < 0 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
            (unsigned int)&v78,
            v55);
        goto LABEL_83;
      }
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, v19);
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      Handle = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      *(_OWORD *)&ByteOffset[0].LowPart = 0;
      v26 = NtOpenFile(&Handle, 0x80100000, &ObjectAttributes, (PIO_STATUS_BLOCK)ByteOffset, 7u, 0x60u);
      operator delete(v19);
      if ( v26 < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          return (unsigned int)v26;
        v31 = 19;
LABEL_44:
        WPP_SF_d(v30[2], v31, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, (unsigned int)v26);
        return (unsigned int)v26;
      }
      v77 = 0;
      IoStatusBlock = 0;
      LowPart = NtQueryInformationFile(
                  Handle,
                  (PIO_STATUS_BLOCK)ByteOffset,
                  &IoStatusBlock,
                  0x18u,
                  FileStandardInformation);
      if ( LowPart >= 0 && SHIDWORD(IoStatusBlock.Information) > 0 )
        LowPart = -2147483643;
      Information_low = (unsigned int)(LODWORD(IoStatusBlock.Information) - 2);
      if ( LODWORD(IoStatusBlock.Information) < 2 )
        Information_low = LODWORD(IoStatusBlock.Information);
      if ( LowPart >= 0 )
      {
        Src = 0;
        if ( !(_DWORD)FileHandle )
        {
          LODWORD(FileHandle) = 0;
          LangIdFromSzLang = GetLangIdFromSzLang(v12);
          if ( PerflibciEnsurePerflibV2StringTable(
                 LangIdFromSzLang,
                 v62,
                 (unsigned __int8 **)&Src,
                 (unsigned int *)&FileHandle) )
          {
            LowPart = -1073741811;
          }
          else
          {
            v18 = (unsigned int)FileHandle;
            LowPart = 0;
          }
        }
        if ( a4 && a5 && (v58 = v18 + Information_low + 2, *a5 >= v58) )
        {
          File = NtReadFile(Handle, 0, 0, 0, (PIO_STATUS_BLOCK)ByteOffset, a4, Information_low, 0, 0);
          LowPart = File;
          if ( File < 0 )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                23,
                WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
                (unsigned int)File);
          }
          else
          {
            LowPart = ByteOffset[0].LowPart;
            if ( (ByteOffset[0].LowPart & 0x80000000) == 0 )
            {
              if ( ByteOffset[1].QuadPart == (unsigned int)Information_low )
              {
                if ( Src && v18 )
                  memcpy_0(&a4[Information_low], Src, v18);
                *(_WORD *)&a4[v18 + Information_low] = 0;
                *a5 = v58;
                if ( a6 )
                  *a6 = v58;
              }
              else
              {
                LowPart = -1073741807;
              }
            }
          }
        }
        else
        {
          v60 = WPP_GLOBAL_Control;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
              (unsigned int)LowPart);
            v60 = WPP_GLOBAL_Control;
          }
          if ( a6 )
          {
            *a6 = 0;
            v60 = WPP_GLOBAL_Control;
          }
          if ( a4 )
          {
            if ( (*((_DWORD *)v60 + 7) & 0x200) != 0 && *((_BYTE *)v60 + 25) >= 3u )
              WPP_SF_d(v60[2], 22, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, (unsigned int)LowPart);
            if ( a5 && a6 )
            {
              *a5 = v18 + Information_low + 2;
              *a6 = 0;
            }
            LowPart = -2147483643;
          }
          else
          {
            if ( a5 )
              *a5 = v18 + Information_low + 2;
            LowPart = 0;
          }
        }
        operator delete(Src);
      }
      else if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
          (unsigned int)LowPart);
      }
      v38 = Handle;
LABEL_138:
      NtClose(v38);
      return (unsigned int)LowPart;
    }
    if ( !a4 || !a5 || !*a5 )
    {
      v50 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, a3);
      if ( (unsigned int)dword_18002B048 > 2 && (unsigned __int8)tlgKeywordOn(v50, 0x4000000000000000LL) )
      {
        Src = a4;
        if ( a5 )
          v54 = *a5;
        else
          v54 = -1;
        v62 = v54;
        Handle = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v51,
          (unsigned int)byte_180026403,
          v52,
          v53,
          (__int64)&Handle,
          (__int64)&v62,
          (__int64)&Src);
      }
      goto LABEL_83;
    }
    v21 = StringCbPrintfW(v17, 0x44u, L"%.*ls\\%ls");
    if ( v21 < 0 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_19eda5448c57313a885eafc13b9604e0_Traceguids,
          (unsigned int)v21);
LABEL_83:
      operator delete(v19);
      return 3221225485LL;
    }
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v19);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( (unsigned int)dword_18002B048 > 5 && (unsigned __int8)tlgKeywordOn(v22, 0x4000000000000000LL) )
    {
      v62 = *a5;
      Src = v19;
      Handle = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v23,
        (unsigned int)&byte_1800263C7,
        v24,
        v25,
        (__int64)&Handle,
        (__int64)&v62,
        (__int64)&Src);
    }
    FileHandle = 0;
    IoStatusBlock = 0;
    v26 = NtCreateFile(&FileHandle, 0x40110000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 0, 0x20u, 0, 0);
    operator delete(v19);
    if ( v26 < 0 )
    {
      if ( (unsigned int)dword_18002B048 > 2
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B048, 0x4000000000000000LL) )
      {
        v62 = v26;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v27,
          (unsigned int)byte_18002638D,
          v28,
          v29,
          (__int64)&v62);
      }
      v30 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        return (unsigned int)v26;
      v31 = 14;
      goto LABEL_44;
    }
    ShareAccess = *a5;
    ByteOffset[0].QuadPart = 0;
    LowPart = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, a4, ShareAccess, ByteOffset, 0);
    if ( LowPart >= 0 )
    {
      LowPart = NtFlushBuffersFile(FileHandle, &IoStatusBlock);
      if ( LowPart >= 0 )
      {
        FileInformation[0] = 3;
        v74 = 0;
        memset(v73, 0, sizeof(v73));
        v75 = 0;
        v42 = -1;
        FileInformation[1] = 0;
        do
          ++v42;
        while ( *((_WORD *)&v78 + v42) );
        *(_QWORD *)&v73[12] = v81;
        v71 = 2 * v42;
        v72 = v78;
        *(_QWORD *)v73 = v79;
        *(_DWORD *)&v73[8] = v80;
        *(_WORD *)&v73[20] = v82;
        LowPart = NtSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x38u, (FILE_INFORMATION_CLASS)65);
        if ( LowPart >= 0 )
        {
          if ( (unsigned int)dword_18002B048 > 5 && (unsigned __int8)tlgKeywordOn(v43, 0x4000000000000000LL) )
          {
            v62 = LowPart;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v47,
              (unsigned int)word_1800262B2,
              v48,
              v49,
              (__int64)&v62);
          }
          goto LABEL_54;
        }
        if ( (unsigned int)dword_18002B048 > 2
          && (unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B048, 0x4000000000000000LL) )
        {
          v62 = LowPart;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v44,
            (unsigned int)byte_1800262E1,
            v45,
            v46,
            (__int64)&v62);
        }
        v36 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_54:
          v38 = FileHandle;
          goto LABEL_138;
        }
        v37 = 17;
      }
      else
      {
        if ( (unsigned int)dword_18002B048 > 2
          && (unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B048, 0x4000000000000000LL) )
        {
          v62 = LowPart;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v39,
            (unsigned int)byte_18002631B,
            v40,
            v41,
            (__int64)&v62);
        }
        v36 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_54;
        v37 = 16;
      }
    }
    else
    {
      if ( (unsigned int)dword_18002B048 > 2
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B048, 0x4000000000000000LL) )
      {
        v62 = LowPart;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)&dword_180026354,
          v34,
          v35,
          (__int64)&v62);
      }
      v36 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_54;
      v37 = 15;
    }
    WPP_SF_d(v36[2], v37, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids, (unsigned int)LowPart);
    goto LABEL_54;
  }
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180010430  mov     [rsp-8+arg_8], rbx
0x180010435  push    rbp
0x180010436  push    rsi
0x180010437  push    rdi
0x180010438  push    r12
0x18001043a  push    r13
0x18001043c  push    r14
0x18001043e  push    r15
0x180010440  lea     rbp, [rsp-60h]
0x180010445  sub     rsp, 160h
0x18001044c  mov     rax, cs:__security_cookie
0x180010453  xor     rax, rsp
0x180010456  mov     [rbp+90h+var_40], rax
0x18001045a  mov     rdi, [rbp+90h+arg_20]
0x180010461  mov     r11d, 7
0x180010467  mov     r13, [rbp+90h+arg_28]
0x18001046e  movzx   eax, cx
0x180010471  mov     rbx, [rbp+90h+arg_30]
0x180010478  sub     ax, r11w
0x18001047c  mov     rsi, r8
0x18001047f  mov     edx, ecx
0x180010481  mov     r8d, ecx
0x180010484  lea     r10d, [r11-6]
0x180010488  and     r8d, 10000h
0x18001048f  lea     r14d, [r11+61h]
0x180010493  cmp     ax, r10w
0x180010497  mov     dword ptr [rsp+190h+FileHandle], r8d
0x18001049c  lea     eax, [rcx-5]
0x18001049f  mov     r12, r9
0x1800104a2  mov     ecx, 0FFFDh
0x1800104a7  setbe   [rsp+190h+var_12C]
0x1800104ac  test    cx, ax
0x1800104af  jnz     short loc_1800104B5
0x1800104b1  lea     r14d, [r11+5Ch]
0x1800104b5  mov     [rsp+190h+var_130], r14d
0x1800104ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104c1  test    dword ptr [rcx+1Ch], 200h
0x1800104c8  jz      short loc_1800104F1
0x1800104ca  cmp     byte ptr [rcx+19h], 4
0x1800104ce  jb      short loc_1800104F1
0x1800104d0  mov     rcx, [rcx+10h]
0x1800104d4  movzx   r9d, dx
0x1800104d8  mov     [rsp+190h+AllocationSize], rsi
0x1800104dd  call    WPP_SF_dZ
0x1800104e2  mov     r8d, dword ptr [rsp+190h+FileHandle]
0x1800104e7  mov     r10d, 1
0x1800104ed  lea     r11d, [r10+6]
0x1800104f1  mov     r9d, 30h ; '0'
0x1800104f7  test    rbx, rbx
0x1800104fa  jz      short loc_18001052C
0x1800104fc  mov     rcx, rbx; unsigned __int16 *
0x1800104ff  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180010504  and     eax, 3FFh
0x180010509  cmp     eax, 4
0x18001050c  jz      short loc_180010527
0x18001050e  cmp     eax, 16h
0x180010511  jz      short loc_180010527
0x180010513  lea     rdx, [rbp+90h+var_50]
0x180010517  mov     rcx, rbx; unsigned __int16 *
0x18001051a  call    PerflibCheckPerfFile
0x18001051f  mov     r15, rax
0x180010522  test    rax, rax
0x180010525  jnz     short loc_180010590
0x180010527  mov     r15, rbx
0x18001052a  jmp     short loc_180010590
0x18001052c  mov     eax, r8d
0x18001052f  movzx   r8d, word ptr [rsi]
0x180010533  neg     eax
0x180010535  mov     rax, [rsi+8]
0x180010539  sbb     ecx, ecx
0x18001053b  and     ecx, 4
0x18001053e  add     ecx, r11d
0x180010541  mov     edx, ecx
0x180010543  lea     rbx, [rax+rcx*2]
0x180010547  add     ecx, 3
0x18001054a  jmp     short loc_180010563
0x18001054c  movzx   eax, word ptr [rbx]
0x18001054f  sub     ax, r9w
0x180010553  cmp     ax, 9
0x180010557  jbe     short loc_180010572
0x180010559  add     rbx, 2
0x18001055d  add     edx, r10d
0x180010560  lea     ecx, [rdx+3]
0x180010563  add     rcx, rcx
0x180010566  cmp     r8, rcx
0x180010569  jnb     short loc_18001054C
0x18001056b  lea     rbx, ?DefaultLangId@@3QBGB; "009"
0x180010572  mov     rcx, rbx
0x180010575  call    Perflib004Update
0x18001057a  lea     rdx, [rbp+90h+var_50]
0x18001057e  mov     rcx, rbx; unsigned __int16 *
0x180010581  call    PerflibCheckPerfFile
0x180010586  test    rax, rax
0x180010589  mov     r15, rax
0x18001058c  cmovz   r15, rbx
0x180010590  movzx   eax, word ptr cs:a01234567Dat+18h; ""
0x180010597  mov     ecx, 30h ; '0'
0x18001059c  movsd   xmm0, qword ptr cs:a01234567Dat+10h; ".dat"
0x1800105a4  mov     [rbp+90h+var_58], ax
0x1800105a8  movsd   [rbp+90h+var_60], xmm0
0x1800105ad  mov     [rbp+90h+var_70], 310030h
0x1800105b4  mov     dword ptr [rbp+90h+var_6C], 330032h
0x1800105bb  mov     dword ptr [rbp+90h+var_6C+4], 350034h
0x1800105c2  mov     [rbp+90h+var_64], 370036h
0x1800105c9  movzx   eax, word ptr [r15+6]
0x1800105ce  sub     ax, cx
0x1800105d1  cmp     ax, 9
0x1800105d5  ja      short loc_18001060B
0x1800105d7  mov     [rbp+90h+var_70], 720070h
0x1800105de  lea     eax, [rcx+36h]
0x1800105e1  mov     word ptr [rbp+90h+var_6C], ax
0x1800105e5  mov     word ptr [rbp+90h+var_6C+2], r14w
0x1800105ea  movzx   eax, word ptr [r15]
0x1800105ee  mov     word ptr [rbp+90h+var_6C+4], ax
0x1800105f2  movzx   eax, word ptr [r15+2]
0x1800105f7  mov     word ptr [rbp+90h+var_6C+6], ax
0x1800105fb  movzx   eax, word ptr [r15+4]
0x180010600  mov     word ptr [rbp+90h+var_64], ax
0x180010604  movzx   eax, word ptr [r15+6]
0x180010609  jmp     short loc_180010634
0x18001060b  mov     [rbp+90h+var_70], 650070h
0x180010612  mov     dword ptr [rbp+90h+var_6C], 660072h
0x180010619  mov     word ptr [rbp+90h+var_6C+4], r14w
0x18001061e  movzx   eax, word ptr [r15]
0x180010622  mov     word ptr [rbp+90h+var_6C+6], ax
0x180010626  movzx   eax, word ptr [r15+2]
0x18001062b  mov     word ptr [rbp+90h+var_64], ax
0x18001062f  movzx   eax, word ptr [r15+4]
0x180010634  mov     ecx, 44h ; 'D'
0x180010639  mov     word ptr [rbp+90h+var_64+2], ax
0x18001063d  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180010642  xor     r14d, r14d
0x180010645  mov     rbx, rax
0x180010648  test    rax, rax
0x18001064b  jnz     short loc_180010680
0x18001064d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010654  test    dword ptr [rcx+1Ch], 200h
0x18001065b  jz      short loc_180010676
0x18001065d  cmp     byte ptr [rcx+19h], 2
0x180010661  jb      short loc_180010676
0x180010663  mov     rcx, [rcx+10h]
0x180010667  lea     edx, [rax+0Bh]
0x18001066a  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x180010671  call    WPP_SF_
0x180010676  mov     eax, 0C0000017h
0x18001067b  jmp     loc_180010EFA
0x180010680  cmp     [rsp+190h+var_12C], r14b
0x180010685  jz      loc_180010B85
0x18001068b  test    r12, r12
0x18001068e  jz      loc_180010AE2
0x180010694  test    rdi, rdi
0x180010697  jz      loc_180010AE2
0x18001069d  cmp     [rdi], r14d
0x1800106a0  jz      loc_180010AE2
0x1800106a6  mov     r9d, 14h
0x1800106ac  lea     rax, aPerftmpDat; "perfTMP.dat"
0x1800106b3  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1800106b8  lea     r8, aLsLs; "%.*ls\\%ls"
0x1800106bf  mov     rax, cs:stru_1800206B8.Buffer
0x1800106c6  mov     rcx, rbx; unsigned __int16 *
0x1800106c9  mov     [rsp+190h+AllocationSize], rax
0x1800106ce  lea     edx, [r9+30h]; unsigned __int64
0x1800106d2  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800106d7  test    eax, eax
0x1800106d9  jns     short loc_180010716
0x1800106db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106e2  test    dword ptr [rcx+1Ch], 200h
0x1800106e9  jz      loc_180010B73
0x1800106ef  cmp     byte ptr [rcx+19h], 2
0x1800106f3  jb      loc_180010B73
0x1800106f9  mov     rcx, [rcx+10h]
0x1800106fd  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x180010704  mov     edx, 0Dh
0x180010709  mov     r9d, eax
0x18001070c  call    WPP_SF_d
0x180010711  jmp     loc_180010B73
0x180010716  xorps   xmm0, xmm0
0x180010719  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18001071d  mov     rdx, rbx; SourceString
0x180010720  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x180010724  call    cs:__imp_RtlInitUnicodeString
0x18001072a  lea     rax, [rbp+90h+DestinationString]
0x18001072e  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x180010736  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x18001073a  xorps   xmm0, xmm0
0x18001073d  mov     eax, cs:dword_18002B048
0x180010743  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 40h ; '@'
0x18001074b  mov     [rbp+90h+ObjectAttributes.RootDirectory], r14
0x18001074f  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010754  cmp     eax, 5
0x180010757  jbe     short loc_1800107A6
0x180010759  mov     rdx, 4000000000000000h
0x180010763  call    _tlgKeywordOn
0x180010768  test    al, al
0x18001076a  jz      short loc_1800107A6
0x18001076c  mov     eax, [rdi]
0x18001076e  lea     rdx, byte_1800263C7
0x180010775  mov     [rsp+190h+var_130], eax
0x180010779  lea     rax, [rsp+190h+Src]
0x18001077e  mov     qword ptr [rsp+190h+ShareAccess], rax
0x180010783  lea     rax, [rsp+190h+var_130]
0x180010788  mov     qword ptr [rsp+190h+FileAttributes], rax
0x18001078d  lea     rax, [rsp+190h+Handle]
0x180010792  mov     [rsp+190h+AllocationSize], rax
0x180010797  mov     [rsp+190h+Src], rbx
0x18001079c  mov     [rsp+190h+Handle], rsi
0x1800107a1  call    ??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800107a6  mov     [rsp+190h+EaLength], r14d; EaLength
0x1800107ab  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1800107af  mov     [rsp+190h+EaBuffer], r14; EaBuffer
0x1800107b4  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1800107b8  mov     [rsp+190h+CreateOptions], 20h ; ' '; CreateOptions
0x1800107c0  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x1800107c5  mov     [rsp+190h+CreateDisposition], r14d; CreateDisposition
0x1800107ca  xorps   xmm0, xmm0
0x1800107cd  mov     [rsp+190h+ShareAccess], 1; ShareAccess
0x1800107d5  mov     edx, 40110000h; DesiredAccess
0x1800107da  mov     [rsp+190h+FileAttributes], 80h; FileAttributes
0x1800107e2  mov     [rsp+190h+AllocationSize], r14; AllocationSize
0x1800107e7  mov     [rsp+190h+FileHandle], r14
0x1800107ec  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x1800107f0  call    cs:__imp_NtCreateFile
0x1800107f6  mov     rcx, rbx; Block
0x1800107f9  mov     esi, eax
0x1800107fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010800  test    esi, esi
0x180010802  jns     short loc_180010871
0x180010804  mov     ecx, cs:dword_18002B048
0x18001080a  cmp     ecx, 2
0x18001080d  jbe     short loc_18001083C
0x18001080f  mov     rdx, 4000000000000000h
0x180010819  call    _tlgKeywordOn
0x18001081e  test    al, al
0x180010820  jz      short loc_18001083C
0x180010822  lea     rax, [rsp+190h+var_130]
0x180010827  mov     [rsp+190h+var_130], esi
0x18001082b  lea     rdx, byte_18002638D
0x180010832  mov     [rsp+190h+AllocationSize], rax
0x180010837  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001083c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010843  test    dword ptr [rcx+1Ch], 200h
0x18001084a  jz      short loc_18001086A
0x18001084c  cmp     byte ptr [rcx+19h], 2
0x180010850  jb      short loc_18001086A
0x180010852  mov     edx, 0Eh
0x180010857  mov     rcx, [rcx+10h]
0x18001085b  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x180010862  mov     r9d, esi
0x180010865  call    WPP_SF_d
0x18001086a  mov     eax, esi
0x18001086c  jmp     loc_180010EFA
0x180010871  mov     rcx, [rsp+190h+FileHandle]; FileHandle
0x180010876  lea     rax, [rbp+90h+ByteOffset]
0x18001087a  mov     qword ptr [rsp+190h+CreateOptions], r14; Key
0x18001087f  xor     r9d, r9d; ApcContext
0x180010882  mov     qword ptr [rsp+190h+CreateDisposition], rax; ByteOffset
0x180010887  xor     r8d, r8d; ApcRoutine
0x18001088a  mov     eax, [rdi]
0x18001088c  xor     edx, edx; Event
0x18001088e  mov     [rsp+190h+ShareAccess], eax; Length
0x180010892  lea     rax, [rbp+90h+IoStatusBlock]
0x180010896  mov     qword ptr [rsp+190h+FileAttributes], r12; Buffer
0x18001089b  mov     [rsp+190h+AllocationSize], rax; IoStatusBlock
0x1800108a0  mov     qword ptr [rbp+90h+ByteOffset], r14
0x1800108a4  call    cs:__imp_NtWriteFile
0x1800108aa  mov     ebx, eax
0x1800108ac  test    eax, eax
0x1800108ae  jns     short loc_180010920
0x1800108b0  mov     ecx, cs:dword_18002B048
0x1800108b6  cmp     ecx, 2
0x1800108b9  jbe     short loc_1800108E8
0x1800108bb  mov     rdx, 4000000000000000h
0x1800108c5  call    _tlgKeywordOn
0x1800108ca  test    al, al
0x1800108cc  jz      short loc_1800108E8
0x1800108ce  lea     rax, [rsp+190h+var_130]
0x1800108d3  mov     [rsp+190h+var_130], ebx
0x1800108d7  lea     rdx, dword_180026354
0x1800108de  mov     [rsp+190h+AllocationSize], rax
0x1800108e3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800108e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108ef  test    dword ptr [rcx+1Ch], 200h
0x1800108f6  jz      short loc_180010916
0x1800108f8  cmp     byte ptr [rcx+19h], 2
0x1800108fc  jb      short loc_180010916
0x1800108fe  mov     edx, 0Fh
0x180010903  mov     rcx, [rcx+10h]
0x180010907  lea     r8, WPP_19eda5448c57313a885eafc13b9604e0_Traceguids
0x18001090e  mov     r9d, ebx
0x180010911  call    WPP_SF_d
0x180010916  mov     rcx, [rsp+190h+FileHandle]
0x18001091b  jmp     loc_180010EF2
0x180010920  mov     rcx, [rsp+190h+FileHandle]; FileHandle
0x180010925  lea     rdx, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x180010929  call    cs:__imp_NtFlushBuffersFile
0x18001092f  mov     ebx, eax
0x180010931  test    eax, eax
0x180010933  jns     short loc_18001098D
0x180010935  mov     ecx, cs:dword_18002B048
0x18001093b  cmp     ecx, 2
  ... truncated ...
```
