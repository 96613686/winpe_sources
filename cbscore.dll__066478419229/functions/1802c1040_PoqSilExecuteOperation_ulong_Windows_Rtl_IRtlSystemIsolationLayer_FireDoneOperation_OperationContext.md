# PoqSilExecuteOperation(ulong,Windows::Rtl::IRtlSystemIsolationLayer *,FireDoneOperation *,OperationContext &)

- ea: `0x1802c1040`
- end: `0x1802c1ea3`
- name: `?PoqSilExecuteOperation@@YAJKPEAUIRtlSystemIsolationLayer@Rtl@Windows@@PEAVFireDoneOperation@@AEAUOperationContext@@@Z`
- size: `3683`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::Rtl::IRtlSystemIsolationLayer *, struct FireDoneOperation *, struct OperationContext *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1802bed98`

## callees

- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800eb920`
- `0x1802b99fc`
- `0x1802b9a38`
- `0x1802bdc7c`
- `0x1802be308`
- `0x1802bff74`
- `0x1802c0030`
- `0x1802c00e8`
- `0x1802c02ac`
- `0x1802c0584`
- `0x1802c0748`
- `0x1802c0974`
- `0x1802c0c98`
- `0x1802c0dd4`
- `0x1802c1040`
- `0x1802c1eac`
- `0x1802c2000`
- `0x1802c20c0`
- `0x1802c2174`
- `0x1802c26f0`
- `0x1802c2884`
- `0x1802c2c38`
- `0x1802c2df8`

## string_xrefs

- `0x1802c168c`: `Not-null check failed: Op.Data.DeleteKey`
- `0x1802c114c`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.CreateKey->Path)`
- `0x1802c1104`: `Op.Data.CreateKey != nullptr`
- `0x1802c1c7e`: `Not-null check failed: Op.Data.DeleteKeyValue`
- `0x1802c1db6`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.SetKeyValue->Path)`
- `0x1802c16d4`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.DeleteKey->Path)`
- `0x1802c11ad`: `Not-null check failed: Op.Data.SetFileInformation`
- `0x1802c11df`: `Valid flags check failed: Op.Data.SetFileInformation->Flags`
- `0x1802c12e6`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.CreateDirectoryW->FilePath)`
- `0x1802c127d`: `Not-null check failed: Op.Data.CreateDirectory`
- `0x1802c12af`: `Valid flags check failed: Op.Data.CreateDirectory->Flags`
- `0x1802c1577`: `Not-null check failed: Op.Data.CopyFile`
- `0x1802c15a6`: `Valid flags check failed: Op.Data.CopyFile->Flags`
- `0x1802c13b3`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.CreateFileW->FilePath)`
- `0x1802c134a`: `Not-null check failed: Op.Data.CreateFile`
- `0x1802c137c`: `Valid flags check failed: Op.Data.CreateFile->Flags`
- `0x1802c1216`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.SetFileInformation->FilePath)`
- `0x1802c1c1a`: `Valid flags check failed: Op.Data.SetKeySecurity->Flags`
- `0x1802c1bb7`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.SetKeySecurity->Path)`
- `0x1802c1be7`: `Not-null check failed: Op.Data.SetKeySecurity->SecurityDescriptor`
- `0x1802c1b80`: `Not-null check failed: Op.Data.SetKeySecurity`
- `0x1802c1cb5`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.DeleteKeyValue->Path)`
- `0x1802c1cec`: `RtlpValidateUnicodeString(&Op.Data.DeleteKeyValue->Name)`
- `0x1802c14ca`: `Valid flags check failed: Op.Data.DeleteFile->Flags`
- `0x1802c1460`: `Not-null check failed: Op.Data.DeleteFile`
- `0x1802c1497`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.DeleteFileW->FilePath)`
- `0x1802c17ed`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.SetKeyInfo->Path)`
- `0x1802c18ef`: `Not-null check failed: Op.Data.DecompressFile`
- `0x1802c1a70`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.FlushFileBuffers->Path)`
- `0x1802c15dd`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.CopyFileW->Source)`
- `0x1802c1614`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.CopyFileW->Destination)`
- `0x1802c1851`: `Not-null check failed: Op.Data.WofDecompressFile`
- `0x1802c1888`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.WofDecompressFile->FilePath)`
- `0x1802c1992`: `Op.Data.DecompressFile->FileHash.Length <= 0xffffffff`
- `0x1802c1926`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.DecompressFile->Source)`
- `0x1802c195d`: `RtlpValidateNonEmptyUnicodeString(&Op.Data.DecompressFile->Destination)`

## pseudocode

```c
int __fastcall PoqSilExecuteOperation(
        unsigned int a1,
        struct Windows::Rtl::IRtlSystemIsolationLayer *a2,
        struct FireDoneOperation *a3,
        struct OperationContext *a4)
{
  char *v4; // rbx
  unsigned int v5; // eax
  char v6; // r14
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rax
  const char *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  int Key; // eax
  _DWORD *v23; // rax
  __int64 v24; // rcx
  struct Windows::Rtl::IRtlSystemIsolationLayer *v25; // rdx
  _DWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  _DWORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rcx
  _DWORD *v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rcx
  _DWORD *v38; // r8
  __int64 v39; // r8
  __int64 v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rax
  int result; // eax
  __int64 v44; // rcx
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // r8
  __int64 v60; // rcx
  _DWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rcx
  _DWORD *v64; // r8
  __int64 v65; // r8
  __int64 v66; // r8
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r8
  __int64 v70; // r8
  __int64 v71; // r8
  int v72; // ecx
  __int64 v73; // r8
  __int64 v74; // r8
  __int64 v75; // r8
  __int64 v76; // r9
  const char *v77; // [rsp+30h] [rbp-38h] BYREF
  const char *v78; // [rsp+38h] [rbp-30h]
  __int64 v79; // [rsp+40h] [rbp-28h]
  const char *v80; // [rsp+48h] [rbp-20h]
  int v81; // [rsp+50h] [rbp-18h] BYREF

  v4 = (char *)a3 + 96;
  *((_DWORD *)a4 + 28) = 0;
  v5 = *((_DWORD *)a3 + 24);
  v6 = a1 & 1;
  v81 = 0;
  if ( v5 <= 0xA )
  {
    if ( v5 == 10 )
    {
      v42 = *((_QWORD *)a3 + 13);
      if ( !v42 )
      {
        v79 = 3079;
        v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v78 = "PoqSilExecuteOperation";
        v19 = "Not-null check failed: Op.Data.DeleteKey";
        goto LABEL_65;
      }
      if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v42 + 8) )
      {
        v79 = 3080;
        v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v78 = "PoqSilExecuteOperation";
        v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.DeleteKey->Path)";
        goto LABEL_65;
      }
      CheckForUnexpandedVariables(v4, v44);
      v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
      if ( !*(_BYTE *)(v21 + 48) )
      {
        Key = PoqSilDeleteKey(a2, *((_QWORD *)v4 + 1), a4);
        goto LABEL_136;
      }
    }
    else
    {
      v11 = v5 - 1;
      if ( !v11 )
      {
        v38 = (_DWORD *)*((_QWORD *)a3 + 13);
        if ( !v38 )
        {
          v79 = 3285;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Not-null check failed: Op.Data.CopyFile";
          goto LABEL_65;
        }
        if ( *v38 )
        {
          v79 = 3286;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Valid flags check failed: Op.Data.CopyFile->Flags";
          goto LABEL_65;
        }
        if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v38 + 2) )
        {
          v79 = 3287;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.CopyFileW->Source)";
          goto LABEL_65;
        }
        if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v39 + 24) )
        {
          v79 = 3288;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.CopyFileW->Destination)";
          goto LABEL_65;
        }
        CheckForUnexpandedVariables(v4, v40 + 8);
        CheckForUnexpandedVariables(v4, *((_QWORD *)v4 + 1) + 24LL);
        v25 = a2;
        v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
        if ( !*(_BYTE *)(v21 + 48) )
        {
          LOBYTE(v41) = v6;
          Key = PoqSilCopyFile(v41, a2, *((_QWORD *)v4 + 1), a4);
          goto LABEL_136;
        }
        goto LABEL_134;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        CheckForUnexpandedVariables((char *)a3 + 96, *((_QWORD *)a3 + 13) + 8LL);
        CheckForUnexpandedVariables(v4, *((_QWORD *)v4 + 1) + 24LL);
        v25 = a2;
        v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
        if ( !*(_BYTE *)(v21 + 48) )
        {
          LOBYTE(v37) = v6;
          Key = PoqSilMoveFile(v37, a2, *((_QWORD *)v4 + 1), a4);
          goto LABEL_136;
        }
        goto LABEL_134;
      }
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 )
        {
          CheckForUnexpandedVariables((char *)a3 + 96, *((_QWORD *)a3 + 13) + 8LL);
          CheckForUnexpandedVariables(v4, *((_QWORD *)v4 + 1) + 24LL);
          v25 = a2;
          v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
          if ( !*(_BYTE *)(v21 + 48) )
          {
            LOBYTE(v32) = v6;
            Key = PoqSilHardlinkFile(v32, a2, *((_QWORD *)v4 + 1), a4);
            goto LABEL_136;
          }
          goto LABEL_134;
        }
        v15 = v14 - 2;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 == 1 )
              {
                v18 = *((_QWORD *)a3 + 13);
                if ( !v18 )
                {
                  v79 = 3061;
                  v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
                  v78 = "PoqSilExecuteOperation";
                  v19 = "Op.Data.CreateKey != nullptr";
LABEL_65:
                  v80 = v19;
                  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                           &v81,
                           &v77);
                }
                if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v18 + 8) )
                {
                  v79 = 3062;
                  v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
                  v78 = "PoqSilExecuteOperation";
                  v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.CreateKey->Path)";
                  goto LABEL_65;
                }
                CheckForUnexpandedVariables(v4, v20);
                v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
                if ( !*(_BYTE *)(v21 + 48) )
                {
                  Key = PoqSilCreateKey(a2, *((_QWORD *)v4 + 1), a4);
LABEL_136:
                  v72 = 0;
                  if ( Key < 0 )
                    return Key;
                  return v72;
                }
                goto LABEL_133;
              }
LABEL_78:
              v79 = 3056;
              v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
              v80 = 0;
              v78 = "PoqSilExecuteOperation";
              return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                       &v81,
                       &v77,
                       3221225485LL);
            }
            v23 = (_DWORD *)*((_QWORD *)a3 + 13);
            if ( !v23 )
            {
              v79 = 3236;
              v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
              v78 = "PoqSilExecuteOperation";
              v19 = "Not-null check failed: Op.Data.SetFileInformation";
              goto LABEL_65;
            }
            if ( (*v23 & 0xFFFFFE80) != 0 )
            {
              v79 = 3245;
              v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
              v78 = "PoqSilExecuteOperation";
              v19 = "Valid flags check failed: Op.Data.SetFileInformation->Flags";
              goto LABEL_65;
            }
            if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v23 + 4) )
            {
              v79 = 3247;
              v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
              v78 = "PoqSilExecuteOperation";
              v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.SetFileInformation->FilePath)";
              goto LABEL_65;
            }
            CheckForUnexpandedVariables(v4, v24);
            v25 = a2;
            v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
            if ( !*(_BYTE *)(v21 + 48) )
            {
              Key = PoqSilSetFileInformation(v6, (__int64 *)a2, *((_QWORD *)v4 + 1), (__int64)a4);
              goto LABEL_136;
            }
LABEL_134:
            Key = AddIoOverlappedWork(a1, v25, a3, *(void **)v21, a4);
            goto LABEL_136;
          }
          v26 = (_DWORD *)*((_QWORD *)a3 + 13);
          if ( !v26 )
          {
            v79 = 3215;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Not-null check failed: Op.Data.CreateDirectory";
            goto LABEL_65;
          }
          if ( (*v26 & 0xFFFFFFFC) != 0 )
          {
            v79 = 3218;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Valid flags check failed: Op.Data.CreateDirectory->Flags";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v26 + 2) )
          {
            v79 = 3220;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.CreateDirectoryW->FilePath)";
            goto LABEL_65;
          }
          CheckForUnexpandedVariables(v4, v27);
          v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
          if ( !*(_BYTE *)(v21 + 48) )
          {
            LOBYTE(v28) = v6;
            Key = PoqSilCreateDirectory(v28, *((_QWORD *)v4 + 1), a4);
            goto LABEL_136;
          }
        }
        else
        {
          v29 = (_DWORD *)*((_QWORD *)a3 + 13);
          if ( !v29 )
          {
            v79 = 3264;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Not-null check failed: Op.Data.CreateFile";
            goto LABEL_65;
          }
          if ( (*v29 & 0xFFFFFFFC) != 0 )
          {
            v79 = 3267;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Valid flags check failed: Op.Data.CreateFile->Flags";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v29 + 2) )
          {
            v79 = 3269;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.CreateFileW->FilePath)";
            goto LABEL_65;
          }
          CheckForUnexpandedVariables(v4, v30);
          v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
          if ( !*(_BYTE *)(v21 + 48) )
          {
            LOBYTE(v31) = v6;
            Key = PoqSilCreateFile(v31, *((_QWORD *)v4 + 1), a4);
            goto LABEL_136;
          }
        }
      }
      else
      {
        v33 = *((_QWORD *)a3 + 13);
        if ( !v33 )
        {
          v79 = 3165;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Not-null check failed: Op.Data.DeleteFile";
          goto LABEL_65;
        }
        if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v33 + 8) )
        {
          v79 = 3166;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.DeleteFileW->FilePath)";
          goto LABEL_65;
        }
        if ( (*v35 & 0xFFFFFFFC) != 0 )
        {
          v79 = 3169;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Valid flags check failed: Op.Data.DeleteFile->Flags";
          goto LABEL_65;
        }
        CheckForUnexpandedVariables(v4, v34);
        v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
        if ( !*(_BYTE *)(v21 + 48) )
        {
          LOBYTE(v36) = v6;
          Key = PoqSilDeleteFile(v36, *((_QWORD *)v4 + 1), a4);
          goto LABEL_136;
        }
      }
    }
LABEL_133:
    v25 = a2;
    goto LABEL_134;
  }
  v45 = v5 - 11;
  if ( v45 )
  {
    v46 = v45 - 1;
    if ( v46 )
    {
      v47 = v46 - 1;
      if ( v47 )
      {
        v48 = v47 - 1;
        if ( !v48 )
        {
          v64 = (_DWORD *)*((_QWORD *)a3 + 13);
          if ( !v64 )
          {
            v79 = 3157;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Not-null check failed: Op.Data.BeginTransaction";
            goto LABEL_65;
          }
          if ( *v64 )
          {
            v79 = 3158;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Valid flags check failed: Op.Data.BeginTransaction->Flags";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateUnicodeString(v64 + 2) )
          {
            v79 = 3159;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateUnicodeString(&Op.Data.BeginTransaction->TransactionId)";
            goto LABEL_65;
          }
          Key = PoqSilBeginTransaction(a2, v65);
          goto LABEL_136;
        }
        v49 = v48 - 1;
        if ( !v49 )
        {
          v61 = (_DWORD *)*((_QWORD *)a3 + 13);
          if ( !v61 )
          {
            v79 = 3305;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Not-null check failed: Op.Data.FlushFileBuffers";
            goto LABEL_65;
          }
          if ( *v61 )
          {
            v79 = 3306;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Valid flags check failed: Op.Data.FlushFileBuffers->Flags";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v61 + 2) )
          {
            v79 = 3307;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.FlushFileBuffers->Path)";
            goto LABEL_65;
          }
          CheckForUnexpandedVariables(v4, v62);
          v25 = a2;
          v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
          if ( !*(_BYTE *)(v21 + 48) )
          {
            LOBYTE(v63) = v6;
            Key = PoqSilFlushFileBuffers(v63, a2, *((_QWORD *)v4 + 1), a4);
            goto LABEL_136;
          }
          goto LABEL_134;
        }
        v50 = v49 - 2;
        if ( !v50 )
        {
          v57 = *((_QWORD *)a3 + 13);
          if ( !v57 )
          {
            v79 = 3323;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Not-null check failed: Op.Data.DecompressFile";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v57 + 8) )
          {
            v79 = 3324;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.DecompressFile->Source)";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v58 + 24) )
          {
            v79 = 3325;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.DecompressFile->Destination)";
            goto LABEL_65;
          }
          if ( *(_QWORD *)(v59 + 48) > 0xFFFFFFFF )
          {
            v79 = 3326;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Op.Data.DecompressFile->FileHash.Length <= 0xffffffff";
            goto LABEL_65;
          }
          CheckForUnexpandedVariables(v4, v59 + 8);
          CheckForUnexpandedVariables(v4, *((_QWORD *)v4 + 1) + 24LL);
          v25 = a2;
          v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
          if ( !*(_BYTE *)(v21 + 48) )
          {
            LOBYTE(v60) = v6;
            Key = PoqSilDecompressFile(v60, a2, *((_QWORD *)v4 + 1), a4);
            goto LABEL_136;
          }
          goto LABEL_134;
        }
        v51 = v50 - 1;
        if ( !v51 )
        {
          v54 = *((_QWORD *)a3 + 13);
          if ( !v54 )
          {
            v79 = 3343;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "Not-null check failed: Op.Data.WofDecompressFile";
            goto LABEL_65;
          }
          if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v54 + 8) )
          {
            v79 = 3344;
            v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
            v78 = "PoqSilExecuteOperation";
            v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.WofDecompressFile->FilePath)";
            goto LABEL_65;
          }
          CheckForUnexpandedVariables(v4, v55);
          v25 = a2;
          v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
          if ( !*(_BYTE *)(v21 + 48) )
          {
            LOBYTE(v56) = v6;
            Key = PoqSilWofDecompressFile(v56, a2, *((_QWORD *)v4 + 1), a4);
            goto LABEL_136;
          }
          goto LABEL_134;
        }
        if ( v51 != 1 )
          goto LABEL_78;
        v52 = *((_QWORD *)a3 + 13);
        if ( !v52 )
        {
          v79 = 3361;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Op.Data.SetKeyInfo != nullptr";
          goto LABEL_65;
        }
        if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v52 + 8) )
        {
          v79 = 3362;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.SetKeyInfo->Path)";
          goto LABEL_65;
        }
        CheckForUnexpandedVariables(v4, v53);
        v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
        if ( !*(_BYTE *)(v21 + 48) )
        {
          Key = PoqSilSetKeyInfo(a2, *((_QWORD *)v4 + 1), a4);
          goto LABEL_136;
        }
      }
      else
      {
        v66 = *((_QWORD *)a3 + 13);
        if ( !v66 )
        {
          v79 = 3138;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Not-null check failed: Op.Data.SetKeySecurity";
          goto LABEL_65;
        }
        if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v66 + 8) )
        {
          v79 = 3139;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.SetKeySecurity->Path)";
          goto LABEL_65;
        }
        if ( !*(_QWORD *)(v68 + 24) )
        {
          v79 = 3140;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Not-null check failed: Op.Data.SetKeySecurity->SecurityDescriptor";
          goto LABEL_65;
        }
        if ( (*(_DWORD *)v68 & 0xFFFFFFFE) != 0 )
        {
          v79 = 3142;
          v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v78 = "PoqSilExecuteOperation";
          v19 = "Valid flags check failed: Op.Data.SetKeySecurity->Flags";
          goto LABEL_65;
        }
        CheckForUnexpandedVariables(v4, v67);
        v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
        if ( !*(_BYTE *)(v21 + 48) )
        {
          Key = PoqSilSetKeySecurity((__int64)a2, *((_QWORD *)v4 + 1), (__int64)a4);
          goto LABEL_136;
        }
      }
    }
    else
    {
      v69 = *((_QWORD *)a3 + 13);
      if ( !v69 )
      {
        v79 = 3118;
        v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v78 = "PoqSilExecuteOperation";
        v19 = "Not-null check failed: Op.Data.DeleteKeyValue";
        goto LABEL_65;
      }
      if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v69 + 8) )
      {
        v79 = 3119;
        v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v78 = "PoqSilExecuteOperation";
        v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.DeleteKeyValue->Path)";
        goto LABEL_65;
      }
      if ( !(unsigned __int8)RtlpValidateUnicodeString(v70 + 24) )
      {
        v79 = 3120;
        v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v78 = "PoqSilExecuteOperation";
        v19 = "RtlpValidateUnicodeString(&Op.Data.DeleteKeyValue->Name)";
        goto LABEL_65;
      }
      CheckForUnexpandedVariables(v4, v71 + 8);
      CheckForUnexpandedVariables(v4, *((_QWORD *)v4 + 1) + 24LL);
      v21 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
      if ( !*(_BYTE *)(v21 + 48) )
      {
        Key = PoqSilDeleteKeyValue(a2, *((_QWORD *)v4 + 1), a4);
        goto LABEL_136;
      }
    }
    goto LABEL_133;
  }
  v73 = *((_QWORD *)a3 + 13);
  if ( !v73 )
  {
    v79 = 3097;
    v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v78 = "PoqSilExecuteOperation";
    v19 = "Not-null check failed: Op.Data.SetKeyValue";
    goto LABEL_65;
  }
  if ( !(unsigned __int8)RtlpValidateNonEmptyUnicodeString(v73 + 8) )
  {
    v79 = 3098;
    v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v78 = "PoqSilExecuteOperation";
    v19 = "RtlpValidateNonEmptyUnicodeString(&Op.Data.SetKeyValue->Path)";
    goto LABEL_65;
  }
  if ( !(unsigned __int8)RtlpValidateUnicodeString(v74 + 24) )
  {
    v79 = 3099;
    v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v78 = "PoqSilExecuteOperation";
    v19 = "RtlpValidateUnicodeString(&Op.Data.SetKeyValue->Name)";
    goto LABEL_65;
  }
  if ( *(_QWORD *)(v75 + 48) > 0xFFFFFFFF )
  {
    v79 = 3100;
    v77 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v78 = "PoqSilExecuteOperation";
    v19 = "Op.Data.SetKeyValue->Value.Length <= 0xffffffff";
    goto LABEL_65;
  }
  CheckForUnexpandedVariables(v4, v75 + 8);
  CheckForUnexpandedVariables(v4, *((_QWORD *)v4 + 1) + 24LL);
  v76 = *(_QWORD *)(*((_QWORD *)a4 + 13) + 40LL);
  if ( *(_BYTE *)(v76 + 48) )
    result = AddIoOverlappedWork(a1, a2, a3, *(void **)v76, a4);
  else
    result = PoqSilSetKeyValue(a2, *((_QWORD *)v4 + 1), a4);
  if ( result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1802c1040  push    rbp
0x1802c1042  push    rbx
0x1802c1043  push    rsi
0x1802c1044  push    rdi
0x1802c1045  push    r12
0x1802c1047  push    r13
0x1802c1049  push    r14
0x1802c104b  push    r15
0x1802c104d  mov     rbp, rsp
0x1802c1050  sub     rsp, 68h
0x1802c1054  mov     rax, cs:__security_cookie
0x1802c105b  xor     rax, rsp
0x1802c105e  mov     [rbp+var_10], rax
0x1802c1062  xor     r12d, r12d
0x1802c1065  lea     rbx, [r8+60h]
0x1802c1069  mov     r14b, cl
0x1802c106c  mov     [r9+70h], r12d
0x1802c1070  mov     eax, [rbx]
0x1802c1072  and     r14b, 1
0x1802c1076  mov     [rbp+var_18], r12d
0x1802c107a  mov     rdi, r9
0x1802c107d  mov     r13, r8
0x1802c1080  mov     rsi, rdx
0x1802c1083  mov     r15d, ecx
0x1802c1086  cmp     eax, 0Ah
0x1802c1089  ja      loc_1802C1711
0x1802c108f  jz      loc_1802C1665
0x1802c1095  sub     eax, 1
0x1802c1098  jz      loc_1802C1550
0x1802c109e  sub     eax, 1
0x1802c10a1  jz      loc_1802C1507
0x1802c10a7  sub     eax, 1
0x1802c10aa  jz      loc_1802C1439
0x1802c10b0  sub     eax, 1
0x1802c10b3  jz      loc_1802C13F0
0x1802c10b9  sub     eax, 2
0x1802c10bc  jz      loc_1802C1323
0x1802c10c2  sub     eax, 1
0x1802c10c5  jz      loc_1802C1256
0x1802c10cb  sub     eax, 1
0x1802c10ce  jz      loc_1802C1186
0x1802c10d4  cmp     eax, 1
0x1802c10d7  jnz     loc_1802C1755
0x1802c10dd  mov     rax, [rbx+8]
0x1802c10e1  test    rax, rax
0x1802c10e4  jnz     short loc_1802C1121
0x1802c10e6  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c10ed  mov     [rbp+var_28], 0BF5h
0x1802c10f5  mov     [rbp+var_38], rax
0x1802c10f9  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1100  mov     [rbp+var_30], rax
0x1802c1104  lea     rax, aOpDataCreateke; "Op.Data.CreateKey != nullptr"
0x1802c110b  lea     rdx, [rbp+var_38]
0x1802c110f  mov     [rbp+var_20], rax
0x1802c1113  lea     rcx, [rbp+var_18]
0x1802c1117  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802c111c  jmp     loc_1802C1E74
0x1802c1121  lea     rcx, [rax+8]
0x1802c1125  call    RtlpValidateNonEmptyUnicodeString
0x1802c112a  test    al, al
0x1802c112c  jnz     short loc_1802C1155
0x1802c112e  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1135  mov     [rbp+var_28], 0BF6h
0x1802c113d  mov     [rbp+var_38], rax
0x1802c1141  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1148  mov     [rbp+var_30], rax
0x1802c114c  lea     rax, aRtlpvalidateno_8; "RtlpValidateNonEmptyUnicodeString(&Op.D"...
0x1802c1153  jmp     short loc_1802C110B
0x1802c1155  mov     rdx, rcx
0x1802c1158  mov     rcx, rbx
0x1802c115b  call    CheckForUnexpandedVariables
0x1802c1160  mov     rax, [rdi+68h]
0x1802c1164  mov     r9, [rax+28h]
0x1802c1168  cmp     [r9+30h], r12b
0x1802c116c  jnz     loc_1802C1D22
0x1802c1172  mov     rdx, [rbx+8]
0x1802c1176  mov     r8, rdi
0x1802c1179  mov     rcx, rsi
0x1802c117c  call    PoqSilCreateKey
0x1802c1181  jmp     loc_1802C1D49
0x1802c1186  mov     rax, [rbx+8]
0x1802c118a  test    rax, rax
0x1802c118d  jnz     short loc_1802C11B9
0x1802c118f  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1196  mov     [rbp+var_28], 0CA4h
0x1802c119e  mov     [rbp+var_38], rax
0x1802c11a2  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c11a9  mov     [rbp+var_30], rax
0x1802c11ad  lea     rax, aNotNullCheckFa_36; "Not-null check failed: Op.Data.SetFileI"...
0x1802c11b4  jmp     loc_1802C1693
0x1802c11b9  test    dword ptr [rax], 0FFFFFE80h
0x1802c11bf  jz      short loc_1802C11EB
0x1802c11c1  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c11c8  mov     [rbp+var_28], 0CADh
0x1802c11d0  mov     [rbp+var_38], rax
0x1802c11d4  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c11db  mov     [rbp+var_30], rax
0x1802c11df  lea     rax, aValidFlagsChec_7; "Valid flags check failed: Op.Data.SetFi"...
0x1802c11e6  jmp     loc_1802C110B
0x1802c11eb  lea     rcx, [rax+10h]
0x1802c11ef  call    RtlpValidateNonEmptyUnicodeString
0x1802c11f4  test    al, al
0x1802c11f6  jnz     short loc_1802C1222
0x1802c11f8  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c11ff  mov     [rbp+var_28], 0CAFh
0x1802c1207  mov     [rbp+var_38], rax
0x1802c120b  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1212  mov     [rbp+var_30], rax
0x1802c1216  lea     rax, aRtlpvalidateno_12; "RtlpValidateNonEmptyUnicodeString(&Op.D"...
0x1802c121d  jmp     loc_1802C110B
0x1802c1222  mov     rdx, rcx
0x1802c1225  mov     rcx, rbx
0x1802c1228  call    CheckForUnexpandedVariables
0x1802c122d  mov     rax, [rdi+68h]
0x1802c1231  mov     rdx, rsi
0x1802c1234  mov     r9, [rax+28h]
0x1802c1238  cmp     [r9+30h], r12b
0x1802c123c  jnz     loc_1802C1D25
0x1802c1242  mov     r8, [rbx+8]
0x1802c1246  mov     r9, rdi
0x1802c1249  mov     cl, r14b
0x1802c124c  call    PoqSilSetFileInformation
0x1802c1251  jmp     loc_1802C1D49
0x1802c1256  mov     rax, [rbx+8]
0x1802c125a  test    rax, rax
0x1802c125d  jnz     short loc_1802C1289
0x1802c125f  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1266  mov     [rbp+var_28], 0C8Fh
0x1802c126e  mov     [rbp+var_38], rax
0x1802c1272  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1279  mov     [rbp+var_30], rax
0x1802c127d  lea     rax, aNotNullCheckFa_58; "Not-null check failed: Op.Data.CreateDi"...
0x1802c1284  jmp     loc_1802C1693
0x1802c1289  test    dword ptr [rax], 0FFFFFFFCh
0x1802c128f  jz      short loc_1802C12BB
0x1802c1291  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1298  mov     [rbp+var_28], 0C92h
0x1802c12a0  mov     [rbp+var_38], rax
0x1802c12a4  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c12ab  mov     [rbp+var_30], rax
0x1802c12af  lea     rax, aValidFlagsChec_12; "Valid flags check failed: Op.Data.Creat"...
0x1802c12b6  jmp     loc_1802C110B
0x1802c12bb  lea     rcx, [rax+8]
0x1802c12bf  call    RtlpValidateNonEmptyUnicodeString
0x1802c12c4  test    al, al
0x1802c12c6  jnz     short loc_1802C12F2
0x1802c12c8  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c12cf  mov     [rbp+var_28], 0C94h
0x1802c12d7  mov     [rbp+var_38], rax
0x1802c12db  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c12e2  mov     [rbp+var_30], rax
0x1802c12e6  lea     rax, aRtlpvalidateno_9; "RtlpValidateNonEmptyUnicodeString(&Op.D"...
0x1802c12ed  jmp     loc_1802C110B
0x1802c12f2  mov     rdx, rcx
0x1802c12f5  mov     rcx, rbx
0x1802c12f8  call    CheckForUnexpandedVariables
0x1802c12fd  mov     rax, [rdi+68h]
0x1802c1301  mov     r9, [rax+28h]
0x1802c1305  cmp     [r9+30h], r12b
0x1802c1309  jnz     loc_1802C1D22
0x1802c130f  mov     rdx, [rbx+8]
0x1802c1313  mov     r8, rdi
0x1802c1316  mov     cl, r14b
0x1802c1319  call    PoqSilCreateDirectory
0x1802c131e  jmp     loc_1802C1D49
0x1802c1323  mov     rax, [rbx+8]
0x1802c1327  test    rax, rax
0x1802c132a  jnz     short loc_1802C1356
0x1802c132c  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1333  mov     [rbp+var_28], 0CC0h
0x1802c133b  mov     [rbp+var_38], rax
0x1802c133f  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1346  mov     [rbp+var_30], rax
0x1802c134a  lea     rax, aNotNullCheckFa_98; "Not-null check failed: Op.Data.CreateFi"...
0x1802c1351  jmp     loc_1802C1693
0x1802c1356  test    dword ptr [rax], 0FFFFFFFCh
0x1802c135c  jz      short loc_1802C1388
0x1802c135e  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1365  mov     [rbp+var_28], 0CC3h
0x1802c136d  mov     [rbp+var_38], rax
0x1802c1371  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1378  mov     [rbp+var_30], rax
0x1802c137c  lea     rax, aValidFlagsChec_10; "Valid flags check failed: Op.Data.Creat"...
0x1802c1383  jmp     loc_1802C110B
0x1802c1388  lea     rcx, [rax+8]
0x1802c138c  call    RtlpValidateNonEmptyUnicodeString
0x1802c1391  test    al, al
0x1802c1393  jnz     short loc_1802C13BF
0x1802c1395  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c139c  mov     [rbp+var_28], 0CC5h
0x1802c13a4  mov     [rbp+var_38], rax
0x1802c13a8  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c13af  mov     [rbp+var_30], rax
0x1802c13b3  lea     rax, aRtlpvalidateno_6; "RtlpValidateNonEmptyUnicodeString(&Op.D"...
0x1802c13ba  jmp     loc_1802C110B
0x1802c13bf  mov     rdx, rcx
0x1802c13c2  mov     rcx, rbx
0x1802c13c5  call    CheckForUnexpandedVariables
0x1802c13ca  mov     rax, [rdi+68h]
0x1802c13ce  mov     r9, [rax+28h]
0x1802c13d2  cmp     [r9+30h], r12b
0x1802c13d6  jnz     loc_1802C1D22
0x1802c13dc  mov     rdx, [rbx+8]
0x1802c13e0  mov     r8, rdi
0x1802c13e3  mov     cl, r14b
0x1802c13e6  call    PoqSilCreateFile
0x1802c13eb  jmp     loc_1802C1D49
0x1802c13f0  mov     rdx, [rbx+8]
0x1802c13f4  mov     rcx, rbx
0x1802c13f7  add     rdx, 8
0x1802c13fb  call    CheckForUnexpandedVariables
0x1802c1400  mov     rdx, [rbx+8]
0x1802c1404  mov     rcx, rbx
0x1802c1407  add     rdx, 18h
0x1802c140b  call    CheckForUnexpandedVariables
0x1802c1410  mov     rax, [rdi+68h]
0x1802c1414  mov     rdx, rsi
0x1802c1417  mov     r9, [rax+28h]
0x1802c141b  cmp     [r9+30h], r12b
0x1802c141f  jnz     loc_1802C1D25
0x1802c1425  mov     r8, [rbx+8]
0x1802c1429  mov     r9, rdi
0x1802c142c  mov     cl, r14b
0x1802c142f  call    PoqSilHardlinkFile
0x1802c1434  jmp     loc_1802C1D49
0x1802c1439  mov     r8, [rbx+8]
0x1802c143d  test    r8, r8
0x1802c1440  jnz     short loc_1802C146C
0x1802c1442  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1449  mov     [rbp+var_28], 0C5Dh
0x1802c1451  mov     [rbp+var_38], rax
0x1802c1455  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c145c  mov     [rbp+var_30], rax
0x1802c1460  lea     rax, aNotNullCheckFa_79; "Not-null check failed: Op.Data.DeleteFi"...
0x1802c1467  jmp     loc_1802C1693
0x1802c146c  lea     rcx, [r8+8]
0x1802c1470  call    RtlpValidateNonEmptyUnicodeString
0x1802c1475  test    al, al
0x1802c1477  jnz     short loc_1802C14A3
0x1802c1479  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1480  mov     [rbp+var_28], 0C5Eh
0x1802c1488  mov     [rbp+var_38], rax
0x1802c148c  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1493  mov     [rbp+var_30], rax
0x1802c1497  lea     rax, aRtlpvalidateno_10; "RtlpValidateNonEmptyUnicodeString(&Op.D"...
0x1802c149e  jmp     loc_1802C110B
0x1802c14a3  test    dword ptr [r8], 0FFFFFFFCh
0x1802c14aa  jz      short loc_1802C14D6
0x1802c14ac  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c14b3  mov     [rbp+var_28], 0C61h
0x1802c14bb  mov     [rbp+var_38], rax
0x1802c14bf  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c14c6  mov     [rbp+var_30], rax
0x1802c14ca  lea     rax, aValidFlagsChec_8; "Valid flags check failed: Op.Data.Delet"...
0x1802c14d1  jmp     loc_1802C110B
0x1802c14d6  mov     rdx, rcx
0x1802c14d9  mov     rcx, rbx
0x1802c14dc  call    CheckForUnexpandedVariables
0x1802c14e1  mov     rax, [rdi+68h]
0x1802c14e5  mov     r9, [rax+28h]
0x1802c14e9  cmp     [r9+30h], r12b
0x1802c14ed  jnz     loc_1802C1D22
0x1802c14f3  mov     rdx, [rbx+8]
0x1802c14f7  mov     r8, rdi
0x1802c14fa  mov     cl, r14b
0x1802c14fd  call    PoqSilDeleteFile
0x1802c1502  jmp     loc_1802C1D49
0x1802c1507  mov     rdx, [rbx+8]
0x1802c150b  mov     rcx, rbx
0x1802c150e  add     rdx, 8
0x1802c1512  call    CheckForUnexpandedVariables
0x1802c1517  mov     rdx, [rbx+8]
0x1802c151b  mov     rcx, rbx
0x1802c151e  add     rdx, 18h
0x1802c1522  call    CheckForUnexpandedVariables
0x1802c1527  mov     rax, [rdi+68h]
0x1802c152b  mov     rdx, rsi
0x1802c152e  mov     r9, [rax+28h]
0x1802c1532  cmp     [r9+30h], r12b
0x1802c1536  jnz     loc_1802C1D25
0x1802c153c  mov     r8, [rbx+8]
0x1802c1540  mov     r9, rdi
0x1802c1543  mov     cl, r14b
0x1802c1546  call    PoqSilMoveFile
0x1802c154b  jmp     loc_1802C1D49
0x1802c1550  mov     r8, [rbx+8]
0x1802c1554  test    r8, r8
0x1802c1557  jnz     short loc_1802C1583
0x1802c1559  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c1560  mov     [rbp+var_28], 0CD5h
0x1802c1568  mov     [rbp+var_38], rax
0x1802c156c  lea     rax, aPoqsilexecuteo; "PoqSilExecuteOperation"
0x1802c1573  mov     [rbp+var_30], rax
0x1802c1577  lea     rax, aNotNullCheckFa_92; "Not-null check failed: Op.Data.CopyFile"
0x1802c157e  jmp     loc_1802C1693
0x1802c1583  cmp     [r8], r12d
0x1802c1586  jz      short loc_1802C15B2
0x1802c1588  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c158f  mov     [rbp+var_28], 0CD6h
0x1802c1597  mov     [rbp+var_38], rax
  ... truncated ...
```
