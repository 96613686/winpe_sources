# AvrfMiniLoadDll

- ea: `0x1801379c4`
- end: `0x1801383fb`
- name: `AvrfMiniLoadDll`
- size: `2615`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180113878`

## callees

- `0x18001a080`
- `0x18001e820`
- `0x18001f070`
- `0x180029a60`
- `0x180036fa0`
- `0x18006d6e8`
- `0x180082490`
- `0x180082a00`
- `0x180082bc0`
- `0x1800836f4`
- `0x180083bf0`
- `0x18008612c`
- `0x1800867f8`
- `0x1800c4700`
- `0x1800c7ac0`
- `0x1800eac88`
- `0x1801379c4`
- `0x18015ecc0`
- `0x18015efe0`
- `0x18015f020`
- `0x18015f140`
- `0x18015f280`
- `0x18015f420`
- `0x18015f4e0`
- `0x18015f500`
- `0x18015f5e0`
- `0x1801611d0`
- `0x180161830`
- `0x1801624d0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x180137abd`: `\KnownDlls`
- `0x180137b13`: `KnownDllPath`
- `0x180137f59`: `AVRF: Verifier .dlls must not have thread locals\n`

## pseudocode

```c
__int64 __fastcall AvrfMiniLoadDll(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int appended; // esi
  int v6; // eax
  NTSTATUS v7; // eax
  struct _TEB *v8; // rdi
  void *ArbitraryUserPointer; // rbx
  int v10; // eax
  __int64 v11; // r15
  __int64 v12; // r13
  __int128 v13; // xmm0
  unsigned __int16 v14; // r9
  unsigned __int64 v15; // r8
  _WORD *i; // rdx
  __int16 v17; // ax
  _WORD *v18; // rdx
  __int16 v19; // cx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned int *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int *v27; // rdi
  __int64 v28; // r12
  _QWORD *v29; // rbx
  __int64 v30; // r13
  __int64 v31; // rsi
  __int64 v33; // rdi
  __int64 v34; // r12
  __int64 v35; // rcx
  int v36; // eax
  int v37; // r9d
  __int64 v38; // rdx
  __int64 v39; // rcx
  _DWORD *v40; // rcx
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int64 v51; // rcx
  __int128 v52; // [rsp+50h] [rbp-B0h] BYREF
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  UNICODE_STRING v56; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+88h] [rbp-78h] BYREF
  __int64 v58; // [rsp+90h] [rbp-70h]
  _DWORD *v59; // [rsp+98h] [rbp-68h] BYREF
  HANDLE FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE v61; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v62; // [rsp+B0h] [rbp-50h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v64; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE *v65; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v66; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v67; // [rsp+100h] [rbp+0h] BYREF
  __int64 v68; // [rsp+108h] [rbp+8h]
  __int64 v69; // [rsp+110h] [rbp+10h]
  UNICODE_STRING DestinationString; // [rsp+118h] [rbp+18h] BYREF
  UNICODE_STRING v71; // [rsp+128h] [rbp+28h] BYREF
  __int128 v72; // [rsp+140h] [rbp+40h] BYREF
  _DWORD v73[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 (__fastcall *v74)(); // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v75)(); // [rsp+160h] [rbp+60h]
  __int64 (__fastcall *v76)(); // [rsp+168h] [rbp+68h]
  __int64 v77; // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v78)(); // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v79)(); // [rsp+180h] [rbp+80h]
  __int64 (__fastcall *v80)(int, int, int, int, int, __int64); // [rsp+188h] [rbp+88h]
  __int128 v81; // [rsp+190h] [rbp+90h]
  _DWORD *v82; // [rsp+1A0h] [rbp+A0h]
  __int64 v83; // [rsp+1A8h] [rbp+A8h]
  __int64 v84; // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v85)(); // [rsp+1B8h] [rbp+B8h]
  __int64 (__fastcall *v86)(); // [rsp+1C0h] [rbp+C0h]
  __int64 (__fastcall *v87)(); // [rsp+1C8h] [rbp+C8h]
  __int64 (__fastcall *v88)(); // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v89)(); // [rsp+1D8h] [rbp+D8h]
  __int64 (__fastcall *v90)(); // [rsp+1E0h] [rbp+E0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v92[56]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v93; // [rsp+238h] [rbp+138h]
  _QWORD *v94; // [rsp+258h] [rbp+158h]
  int v95; // [rsp+268h] [rbp+168h]
  __int64 v96; // [rsp+270h] [rbp+170h] BYREF
  char v97[16]; // [rsp+278h] [rbp+178h] BYREF
  unsigned int *v98; // [rsp+288h] [rbp+188h]
  unsigned int v99; // [rsp+290h] [rbp+190h]
  _BYTE v100[48]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v101; // [rsp+300h] [rbp+200h]
  int v102; // [rsp+310h] [rbp+210h]
  int v103; // [rsp+338h] [rbp+238h]
  _OWORD v104[2]; // [rsp+410h] [rbp+310h] BYREF
  __int64 v105; // [rsp+430h] [rbp+330h]
  _DWORD v106[2]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v107[520]; // [rsp+448h] [rbp+348h] BYREF

  v69 = a3;
  v68 = a2;
  v58 = a4;
  v61 = 0;
  v62 = 0;
  v105 = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  Handle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  FileHandle = 0;
  memset(v104, 0, sizeof(v104));
  v54 = 0;
  v67 = 0;
  v56 = 0;
  DestinationString = 0;
  v71 = 0;
  v52 = 0;
  IoStatusBlock = 0;
  memset_thunk_772440563353939046(v100, 0, 0x138u);
  v65 = 0;
  v59 = 0;
  v66 = 0;
  memset_thunk_772440563353939046(v92, 0, 0xD0u);
  v57 = 0;
  v73[1] = 0;
  v72 = 0;
  memset_thunk_772440563353939046(v73, 0, 0x94u);
  v64 = 0;
  v53 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\KnownDlls");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  appended = ZwOpenDirectoryObject(&v61, 3, &ObjectAttributes);
  if ( appended >= 0 )
  {
    RtlInitUnicodeString(&v71, L"KnownDllPath");
    ObjectAttributes.RootDirectory = v61;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v71;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    appended = ZwOpenSymbolicLinkObject(&v62, 1, &ObjectAttributes);
    if ( appended >= 0 )
    {
      *((_QWORD *)&v52 + 1) = v107;
      v106[0] = 4128860;
      v106[1] = 6029375;
      LODWORD(v52) = 0x2000000;
      appended = NtQuerySymbolicLinkObject(v62, &v52, 0);
      if ( appended >= 0 )
      {
        *((_QWORD *)&v52 + 1) = v106;
        LOWORD(v52) = v52 + 8;
        WORD1(v52) += 8;
        RtlInitUnicodeString(&v56, L"\\");
        appended = RtlAppendUnicodeStringToString(&v52, &v56);
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&v52, VerifierDllString);
          if ( appended >= 0 )
          {
            if ( (NtCurrentPeb()->NtGlobalFlag & 0x40000) != 0 )
            {
              v72 = v52;
              ZwSystemDebugControl(38, &v72, 16, 0, 0, 0);
            }
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)&v52;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v6 = ZwQueryAttributesFile(&ObjectAttributes, v104);
            if ( v6 < 0 && v6 != -1073741757 && v6 != -1073741790 )
              goto LABEL_11;
            v7 = NtOpenFile(&FileHandle, 0x100020u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
            appended = v7;
            if ( v7 >= 0 )
            {
              appended = NtCreateSection(&Handle, 13, 0, 0, 16, 0x1000000, FileHandle);
              if ( appended >= 0 )
              {
                *(_WORD *)(a5 + 394) = 520;
                *(_QWORD *)(a5 + 400) = a5 + 408;
                *(_WORD *)(a5 + 392) = 0;
                *((_QWORD *)&v52 + 1) = v107;
                LOWORD(v52) = v52 - 8;
                WORD1(v52) -= 8;
                RtlCopyUnicodeString(a5 + 392, &v52);
                v8 = NtCurrentTeb();
                ArbitraryUserPointer = v8->NtTib.ArbitraryUserPointer;
                v8->NtTib.ArbitraryUserPointer = (void *)*((_QWORD *)&v52 + 1);
                v10 = ZwMapViewOfSection(Handle, -1, &v54, 0, 0, 0, &v67, 1, 0x800000, 2);
                v8->NtTib.ArbitraryUserPointer = ArbitraryUserPointer;
                appended = v10;
                if ( v10 >= 0 )
                {
                  *(_QWORD *)&v56.Length = 0;
                  RtlImageNtHeaderEx(1, v54, 0, &v56);
                  v11 = *(_QWORD *)&v56.Length;
                  if ( !*(_QWORD *)&v56.Length )
                    goto LABEL_18;
                  v12 = a5 + 312;
                  *(_QWORD *)(a5 + 48) = v54;
                  *(_DWORD *)(a5 + 64) = *(_DWORD *)(v11 + 80);
                  *(_DWORD *)(a5 + 128) = *(_DWORD *)(v11 + 8);
                  *(_QWORD *)(a5 + 144) = 0;
                  v13 = *(_OWORD *)(a5 + 392);
                  *(_DWORD *)(a5 + 104) = 0;
                  *(_OWORD *)(a5 + 72) = v13;
                  v14 = *(_WORD *)(a5 + 72);
                  v15 = *(_QWORD *)(a5 + 80);
                  for ( i = (_WORD *)(v15 + 2 * (((unsigned __int64)v14 >> 1) - 1)); (unsigned __int64)i > v15; --i )
                  {
                    if ( *i == 92 )
                      goto LABEL_24;
                  }
                  if ( *i == 92 )
                  {
LABEL_24:
                    v17 = *(_WORD *)(a5 + 74);
                    v18 = i + 1;
                    *(_QWORD *)(a5 + 96) = v18;
                    v19 = 2 * ((__int64)((__int64)v18 - v15) >> 1);
                    *(_WORD *)(a5 + 88) = v14 - v19;
                    *(_WORD *)(a5 + 90) = v17 - v19;
                    goto LABEL_26;
                  }
                  *(_OWORD *)(a5 + 88) = v13;
LABEL_26:
                  if ( *(_DWORD *)(v11 + 40) )
                    v20 = *(_QWORD *)(a5 + 48) + *(unsigned int *)(v11 + 40);
                  else
                    v20 = 0;
                  *(_QWORD *)(a5 + 56) = v20;
                  *(_QWORD *)(a5 + 248) = *(_QWORD *)(v11 + 48);
                  *(_QWORD *)(a5 + 152) = v12;
                  memset_thunk_772440563353939046((void *)(a5 + 312), 0, 0x50u);
                  *(_QWORD *)(a5 + 160) = v12;
                  *(_QWORD *)(a5 + 168) = v12;
                  *(_QWORD *)v12 = a5 + 160;
                  *(_QWORD *)(a5 + 320) = a5 + 160;
                  *(_DWORD *)(a5 + 276) = 2;
                  *(_DWORD *)(a5 + 336) = -1;
                  *(_WORD *)(*(_QWORD *)v12 - 52LL) = -1;
                  v21 = NtQuerySection(Handle, 2, &v64);
                  if ( v21 < 0 )
                  {
                    appended = v21;
                    goto LABEL_45;
                  }
                  if ( v64 )
                    *(_QWORD *)(a5 + 248) -= v64;
                  if ( (*(_WORD *)(v11 + 22) & 0x2000) != 0 )
                    *(_DWORD *)(a5 + 104) |= 4u;
                  if ( (*(_BYTE *)(a5 + 104) & 4) == 0 )
                    *(_QWORD *)(a5 + 56) = 0;
                  LOBYTE(v22) = 1;
                  if ( RtlImageDirectoryEntryToData(*(_QWORD *)(a5 + 48), v22, 9, &v53) && v53 )
                  {
                    DbgPrintEx(93, 0, "AVRF: Verifier .dlls must not have thread locals\n");
                    __debugbreak();
                  }
                  LOBYTE(v23) = 1;
                  v24 = (unsigned int *)RtlImageDirectoryEntryToData(*(_QWORD *)(a5 + 48), v23, 1, &v53);
                  v27 = v24;
                  if ( !v24 )
                  {
LABEL_18:
                    appended = -1073741701;
                    goto LABEL_45;
                  }
                  v28 = *(_QWORD *)(a5 + 48);
                  v29 = (_QWORD *)(v28 + *v24);
                  if ( *v29 )
                  {
                    v30 = v24[4];
                    memset_thunk_772440563353939046(v92, 0, 0xD0u);
                    v93 = a5;
                    *(_QWORD *)(a5 + 176) = v92;
                    memset_thunk_772440563353939046(v100, 0, 0x138u);
                    v31 = v58;
                    v65 = v100;
                    *(_QWORD *)&v56.Length = 0;
                    RtlImageNtHeaderEx(1, v58, 0, &v56);
                    v103 = 33554436;
                    v101 = v31;
                    v102 = *(_DWORD *)(*(_QWORD *)&v56.Length + 80LL);
                    v94 = &v65;
                    v98 = v27;
                    v95 = 1;
                    appended = LdrpPrepareImportAddressTableForSnap(v92);
                    if ( appended >= 0 )
                    {
                      if ( v96 )
                      {
                        v33 = v28 + v30;
                        v34 = v58;
                        while ( 1 )
                        {
                          appended = LdrpGetProcedureAddress(
                                       v34,
                                       *(unsigned int *)v29 + *(_QWORD *)(a5 + 48) + 2LL,
                                       0,
                                       v33);
                          if ( appended < 0 )
                            break;
                          if ( !*++v29 )
                          {
                            ZwProtectVirtualMemory(-1, &v96, v97, v99, &v57);
                            if ( !(unsigned int)LdrControlFlowGuardEnforcedWithExportSuppression()
                              || (appended = LdrpUnsuppressAddressTakenIat(*(_QWORD *)(v93 + 48), 0, 0), appended >= 0) )
                            {
                              v12 = a5 + 312;
                              goto LABEL_64;
                            }
                            break;
                          }
                          v33 += 8;
                        }
                      }
                      else
                      {
                        appended = -1073741701;
                      }
                    }
                  }
                  else
                  {
                    v34 = v58;
LABEL_64:
                    v35 = *(unsigned int *)(a5 + 104);
                    if ( (*(_DWORD *)(a5 + 104) & 0x2004) == 4 )
                    {
                      v36 = LdrpGenRandom(v35, v25, v26, (unsigned int)dword_1801E34F8);
                      LdrInitSecurityCookie(*(_QWORD *)(a5 + 48), *(_DWORD *)(a5 + 64), 0, v36 ^ v37, (__int64)&v66);
                      appended = LdrpCfgProcessLoadConfig(a5, v11, v66);
                      if ( appended < 0 )
                        goto LABEL_45;
                      *(_DWORD *)(a5 + 104) |= 0x2000u;
                      LODWORD(v35) = *(_DWORD *)(a5 + 104);
                    }
                    if ( (v35 & 0x200) == 0 )
                    {
                      RtlInsertInvertedFunctionTable(v54, *(unsigned int *)(a5 + 64));
                      *(_DWORD *)(a5 + 104) |= 0x200u;
                    }
                    v38 = *(_QWORD *)(a5 + 48);
                    v39 = *(_QWORD *)(a5 + 56);
                    v74 = RtlpGetStackTraceAddress;
                    v73[0] = 152;
                    v85 = RtlpGetStackTraceAddressEx;
                    v84 = v34;
                    v75 = AVrfInternalHeapFreeNotification;
                    v76 = RtlLogStackTrace;
                    v86 = RtlReleaseStackTrace;
                    v87 = RtlStdInitializeStackDatabase;
                    v88 = RtlStdDeleteStackDatabase;
                    v89 = RtlStdLogStackTrace;
                    v90 = RtlStdReleaseStackTrace;
                    v77 = v68;
                    v83 = v69;
                    v78 = RtlCommitDebugInfo;
                    v79 = RtlSetProcessDebugInformation;
                    v80 = RtlQueryImageFileExecutionOptions;
                    v59 = v73;
                    v81 = 0;
                    v82 = 0;
                    if ( (unsigned __int8)LdrpCallInitRoutine(v39, v38, 5, &v59)
                      && v59 == v73
                      && (v40 = v82) != 0
                      && *v82 == 80
                      && *((_QWORD *)&v81 + 1)
                      && **((_DWORD **)&v81 + 1) == 176 )
                    {
                      v41 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 16LL);
                      xmmword_1801C4598 = **((_OWORD **)&v81 + 1);
                      v42 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 32LL);
                      xmmword_1801C45A8 = v41;
                      v43 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 48LL);
                      xmmword_1801C45B8 = v42;
                      v44 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 64LL);
                      *(_OWORD *)&qword_1801C45C8 = v43;
                      v45 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 80LL);
                      xmmword_1801C45D8 = v44;
                      v46 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 96LL);
                      xmmword_1801C45E8 = v45;
                      v47 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 112LL);
                      xmmword_1801C45F8 = v46;
                      v48 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 128LL);
                      xmmword_1801C4608 = v47;
                      v49 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 144LL);
                      *(_OWORD *)&qword_1801C4618 = v48;
                      v50 = *(_OWORD *)(*((_QWORD *)&v81 + 1) + 160LL);
                      RtlpDebugPageHeapTable = (char (*)[4])v81;
                      v82[10] = AVrfpVerifierFlags;
                      v40[11] = AVrfpDebug;
                      v51 = *(_QWORD *)(a5 + 48);
                      xmmword_1801C4628 = v49;
                      v54 = 0;
                      xmmword_1801C4638 = v50;
                      LdrpLogDllState(v51, a5 + 72, 5294);
                      *(_DWORD *)(v12 + 56) = 9;
                      *(_QWORD *)(a5 + 176) = 0;
                    }
                    else
                    {
                      appended = -1073741502;
                    }
                  }
                }
              }
            }
            else if ( v7 == -1073741772 )
            {
LABEL_11:
              appended = -1073741515;
            }
          }
        }
      }
    }
  }
LABEL_45:
  if ( v54 )
  {
    NtUnmapViewOfSection(-1);
    *(_QWORD *)(a5 + 48) = 0;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v61 )
    NtClose(v61);
  if ( v62 )
    NtClose(v62);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1801379c4  mov     [rsp-8+arg_0], rbx
0x1801379c9  push    rbp
0x1801379ca  push    rsi
0x1801379cb  push    rdi
0x1801379cc  push    r12
0x1801379ce  push    r13
0x1801379d0  push    r14
0x1801379d2  push    r15
0x1801379d4  lea     rbp, [rsp-560h]
0x1801379dc  sub     rsp, 660h
0x1801379e3  mov     rax, cs:__security_cookie
0x1801379ea  xor     rax, rsp
0x1801379ed  mov     [rbp+590h+var_40], rax
0x1801379f4  mov     r14, [rbp+590h+arg_20]
0x1801379fb  lea     rcx, [rbp+590h+var_3C0]; void *
0x180137a02  xorps   xmm0, xmm0
0x180137a05  mov     [rbp+590h+var_580], r8
0x180137a09  xor     ebx, ebx
0x180137a0b  mov     [rbp+590h+var_588], rdx
0x180137a0f  xorps   xmm1, xmm1
0x180137a12  mov     [rbp+590h+var_600], r9
0x180137a16  xor     eax, eax
0x180137a18  mov     [rbp+590h+var_5E8], rbx
0x180137a1c  movups  xmmword ptr [rbp+590h+ObjectAttributes.ObjectName], xmm0
0x180137a20  xor     edx, edx; Val
0x180137a22  mov     [rbp+590h+var_5E0], rbx
0x180137a26  mov     r8d, 138h; Size
0x180137a2c  mov     [rbp+590h+var_260], rax
0x180137a33  movups  xmmword ptr [rbp+590h+ObjectAttributes+1Ch], xmm0
0x180137a37  mov     [rsp+690h+Handle], rbx
0x180137a3c  movups  xmmword ptr [rbp+590h+ObjectAttributes.Length], xmm0
0x180137a40  mov     [rbp+590h+FileHandle], rbx
0x180137a44  movups  [rbp+590h+var_280], xmm0
0x180137a4b  mov     [rsp+690h+var_628], rbx
0x180137a50  movups  [rbp+590h+var_270], xmm0
0x180137a57  mov     [rbp+590h+var_590], rbx
0x180137a5b  movups  xmmword ptr [rsp+690h+var_618.Length], xmm0
0x180137a60  movups  xmmword ptr [rbp+590h+DestinationString.Length], xmm1
0x180137a64  movups  xmmword ptr [rbp+590h+var_568.Length], xmm0
0x180137a68  movups  [rsp+690h+var_640], xmm1
0x180137a6d  movups  xmmword ptr [rbp+590h+IoStatusBlock.___u0], xmm0
0x180137a74  call    memset$thunk$772440563353939046
0x180137a79  xor     edx, edx; Val
0x180137a7b  mov     [rbp+590h+var_5A0], rbx
0x180137a7f  mov     r8d, 0D0h; Size
0x180137a85  mov     [rbp+590h+var_5F8], rbx
0x180137a89  lea     rcx, [rbp+590h+var_490]; void *
0x180137a90  mov     [rsp+690h+var_630], ebx
0x180137a94  mov     [rbp+590h+var_598], rbx
0x180137a98  call    memset$thunk$772440563353939046
0x180137a9d  xorps   xmm0, xmm0
0x180137aa0  mov     [rbp+590h+var_608], ebx
0x180137aa3  xor     eax, eax
0x180137aa5  lea     rcx, [rbp+590h+var_540]; void *
0x180137aa9  xor     edx, edx; Val
0x180137aab  mov     [rbp+590h+var_53C], eax
0x180137aae  mov     r8d, 94h; Size
0x180137ab4  movups  [rbp+590h+var_550], xmm0
0x180137ab8  call    memset$thunk$772440563353939046
0x180137abd  lea     rdx, aKnowndlls; "\\KnownDlls"
0x180137ac4  mov     [rbp+590h+var_5A8], rbx
0x180137ac8  lea     rcx, [rbp+590h+DestinationString]; DestinationString
0x180137acc  mov     [rsp+690h+var_630], ebx
0x180137ad0  call    RtlInitUnicodeString
0x180137ad5  lea     rax, [rbp+590h+DestinationString]
0x180137ad9  mov     [rbp+590h+ObjectAttributes.RootDirectory], rbx
0x180137add  xorps   xmm0, xmm0
0x180137ae0  mov     [rbp+590h+ObjectAttributes.ObjectName], rax
0x180137ae4  lea     r12d, [rbx+30h]
0x180137ae8  lea     r13d, [rbx+40h]
0x180137aec  mov     [rbp+590h+ObjectAttributes.Length], r12d
0x180137af0  lea     r8, [rbp+590h+ObjectAttributes]
0x180137af4  mov     [rbp+590h+ObjectAttributes.Attributes], r13d
0x180137af8  lea     edx, [rbx+3]
0x180137afb  lea     rcx, [rbp+590h+var_5E8]
0x180137aff  movdqu  xmmword ptr [rbp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180137b04  call    ZwOpenDirectoryObject
0x180137b09  mov     esi, eax
0x180137b0b  test    eax, eax
0x180137b0d  js      loc_180138073
0x180137b13  lea     rdx, aKnowndllpath; "KnownDllPath"
0x180137b1a  lea     rcx, [rbp+590h+var_568]; DestinationString
0x180137b1e  call    RtlInitUnicodeString
0x180137b23  mov     rax, [rbp+590h+var_5E8]
0x180137b27  lea     r15d, [rbx+1]
0x180137b2b  mov     [rbp+590h+ObjectAttributes.RootDirectory], rax
0x180137b2f  lea     r8, [rbp+590h+ObjectAttributes]
0x180137b33  lea     rax, [rbp+590h+var_568]
0x180137b37  mov     [rbp+590h+ObjectAttributes.Length], r12d
0x180137b3b  xorps   xmm0, xmm0
0x180137b3e  mov     [rbp+590h+ObjectAttributes.ObjectName], rax
0x180137b42  mov     edx, r15d
0x180137b45  mov     [rbp+590h+ObjectAttributes.Attributes], r13d
0x180137b49  lea     rcx, [rbp+590h+var_5E0]
0x180137b4d  movdqu  xmmword ptr [rbp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180137b52  call    ZwOpenSymbolicLinkObject
0x180137b57  mov     esi, eax
0x180137b59  test    eax, eax
0x180137b5b  js      loc_180138073
0x180137b61  mov     rcx, [rbp+590h+var_5E0]
0x180137b65  lea     rax, [rbp+590h+var_248]
0x180137b6c  xor     r8d, r8d
0x180137b6f  mov     qword ptr [rsp+690h+var_640+8], rax
0x180137b74  lea     rdx, [rsp+690h+var_640]
0x180137b79  mov     [rbp+590h+var_250], 3F005Ch
0x180137b83  mov     [rbp+590h+var_24C], 5C003Fh
0x180137b8d  mov     dword ptr [rsp+690h+var_640], 2000000h
0x180137b95  call    NtQuerySymbolicLinkObject
0x180137b9a  mov     esi, eax
0x180137b9c  test    eax, eax
0x180137b9e  js      loc_180138073
0x180137ba4  lea     rax, [rbp+590h+var_250]
0x180137bab  mov     qword ptr [rsp+690h+var_640+8], rax
0x180137bb0  lea     rdx, asc_180178554; "\\"
0x180137bb7  lea     eax, [rbx+8]
0x180137bba  add     word ptr [rsp+690h+var_640], ax
0x180137bbf  lea     rcx, [rsp+690h+var_618]; DestinationString
0x180137bc4  add     word ptr [rsp+690h+var_640+2], ax
0x180137bc9  call    RtlInitUnicodeString
0x180137bce  lea     rdx, [rsp+690h+var_618]
0x180137bd3  lea     rcx, [rsp+690h+var_640]
0x180137bd8  call    RtlAppendUnicodeStringToString
0x180137bdd  mov     esi, eax
0x180137bdf  test    eax, eax
0x180137be1  js      loc_180138073
0x180137be7  lea     rdx, VerifierDllString
0x180137bee  lea     rcx, [rsp+690h+var_640]
0x180137bf3  call    RtlAppendUnicodeStringToString
0x180137bf8  mov     esi, eax
0x180137bfa  test    eax, eax
0x180137bfc  js      loc_180138073
0x180137c02  mov     rax, gs:60h
0x180137c0b  lea     edi, [rbx+10h]
0x180137c0e  test    dword ptr [rax+0BCh], 40000h
0x180137c18  jz      short loc_180137C3F
0x180137c1a  movaps  xmm0, [rsp+690h+var_640]
0x180137c1f  lea     rdx, [rbp+590h+var_550]
0x180137c23  mov     qword ptr [rsp+690h+OpenOptions], rbx
0x180137c28  lea     ecx, [rbx+26h]
0x180137c2b  xor     r9d, r9d
0x180137c2e  movdqa  [rbp+590h+var_550], xmm0
0x180137c33  mov     r8d, edi
0x180137c36  mov     [rsp+690h+ShareAccess], ebx
0x180137c3a  call    ZwSystemDebugControl
0x180137c3f  lea     rax, [rsp+690h+var_640]
0x180137c44  mov     [rbp+590h+ObjectAttributes.Length], r12d
0x180137c48  xorps   xmm0, xmm0
0x180137c4b  mov     [rbp+590h+ObjectAttributes.ObjectName], rax
0x180137c4f  lea     rdx, [rbp+590h+var_280]
0x180137c56  mov     [rbp+590h+ObjectAttributes.RootDirectory], rbx
0x180137c5a  lea     rcx, [rbp+590h+ObjectAttributes]
0x180137c5e  mov     [rbp+590h+ObjectAttributes.Attributes], r13d
0x180137c62  movdqu  xmmword ptr [rbp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180137c67  call    ZwQueryAttributesFile
0x180137c6c  test    eax, eax
0x180137c6e  jns     short loc_180137C88
0x180137c70  cmp     eax, 0C0000043h
0x180137c75  jz      short loc_180137C88
0x180137c77  cmp     eax, 0C0000022h
0x180137c7c  jz      short loc_180137C88
0x180137c7e  mov     esi, 0C0000135h
0x180137c83  jmp     loc_180138073
0x180137c88  mov     [rsp+690h+OpenOptions], 60h ; '`'; OpenOptions
0x180137c90  lea     r9, [rbp+590h+IoStatusBlock]; IoStatusBlock
0x180137c97  lea     r8, [rbp+590h+ObjectAttributes]; ObjectAttributes
0x180137c9b  mov     [rsp+690h+ShareAccess], 5; ShareAccess
0x180137ca3  mov     edx, 100020h; DesiredAccess
0x180137ca8  lea     rcx, [rbp+590h+FileHandle]; FileHandle
0x180137cac  call    NtOpenFile
0x180137cb1  mov     esi, eax
0x180137cb3  test    eax, eax
0x180137cb5  jns     short loc_180137CC4
0x180137cb7  cmp     eax, 0C0000034h
0x180137cbc  jnz     loc_180138073
0x180137cc2  jmp     short loc_180137C7E
0x180137cc4  mov     rax, [rbp+590h+FileHandle]
0x180137cc8  lea     rcx, [rsp+690h+Handle]
0x180137ccd  mov     [rsp+690h+var_660], rax
0x180137cd2  xor     r9d, r9d
0x180137cd5  mov     [rsp+690h+OpenOptions], 1000000h
0x180137cdd  xor     r8d, r8d
0x180137ce0  mov     [rsp+690h+ShareAccess], edi
0x180137ce4  lea     edx, [r9+0Dh]
0x180137ce8  call    NtCreateSection
0x180137ced  mov     esi, eax
0x180137cef  test    eax, eax
0x180137cf1  js      loc_180138073
0x180137cf7  lea     rax, [r14+198h]
0x180137cfe  mov     word ptr [r14+18Ah], 208h
0x180137d08  mov     [r14+190h], rax
0x180137d0f  lea     r12, [r14+188h]
0x180137d16  lea     rax, [rbp+590h+var_248]
0x180137d1d  mov     [r12], bx
0x180137d22  mov     qword ptr [rsp+690h+var_640+8], rax
0x180137d27  lea     rdx, [rsp+690h+var_640]
0x180137d2c  mov     eax, 0FFF8h
0x180137d31  mov     rcx, r12
0x180137d34  add     word ptr [rsp+690h+var_640], ax
0x180137d39  add     word ptr [rsp+690h+var_640+2], ax
0x180137d3e  call    RtlCopyUnicodeString
0x180137d43  mov     rdi, gs:30h
0x180137d4c  lea     r8, [rsp+690h+var_628]
0x180137d51  mov     rax, qword ptr [rsp+690h+var_640+8]
0x180137d56  xor     r9d, r9d
0x180137d59  mov     [rsp+690h+var_648], 2
0x180137d61  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180137d65  mov     [rsp+690h+var_650], 800000h
0x180137d6d  mov     rbx, [rdi+28h]
0x180137d71  mov     [rdi+28h], rax
0x180137d75  lea     rax, [rbp+590h+var_590]
0x180137d79  mov     rcx, [rsp+690h+Handle]
0x180137d7e  mov     [rsp+690h+var_658], r15d
0x180137d83  mov     [rsp+690h+var_660], rax
0x180137d88  mov     qword ptr [rsp+690h+OpenOptions], 0
0x180137d91  mov     qword ptr [rsp+690h+ShareAccess], 0
0x180137d9a  call    ZwMapViewOfSection
0x180137d9f  mov     [rdi+28h], rbx
0x180137da3  mov     esi, eax
0x180137da5  xor     ebx, ebx
0x180137da7  test    eax, eax
0x180137da9  js      loc_180138073
0x180137daf  mov     rdx, [rsp+690h+var_628]
0x180137db4  lea     r9, [rsp+690h+var_618]
0x180137db9  xor     r8d, r8d
0x180137dbc  mov     qword ptr [rsp+690h+var_618.Length], rbx
0x180137dc1  mov     ecx, r15d
0x180137dc4  call    RtlImageNtHeaderEx
0x180137dc9  mov     r15, qword ptr [rsp+690h+var_618.Length]
0x180137dce  test    r15, r15
0x180137dd1  jnz     short loc_180137DDD
0x180137dd3  mov     esi, 0C000007Bh
0x180137dd8  jmp     loc_180138073
0x180137ddd  mov     rax, [rsp+690h+var_628]
0x180137de2  lea     r13, [r14+138h]
0x180137de9  mov     [r14+30h], rax
0x180137ded  mov     eax, [r15+50h]
0x180137df1  mov     [r14+40h], eax
0x180137df5  mov     eax, [r15+8]
0x180137df9  mov     [r14+80h], eax
0x180137e00  mov     eax, 5Ch ; '\'
0x180137e05  mov     [r14+90h], rbx
0x180137e0c  movups  xmm0, xmmword ptr [r12]
0x180137e11  mov     [r14+68h], ebx
0x180137e15  movdqu  xmmword ptr [r14+48h], xmm0
0x180137e1b  movzx   r9d, word ptr [r14+48h]
0x180137e20  mov     r8, [r14+50h]
0x180137e24  mov     edx, r9d
0x180137e27  shr     rdx, 1
0x180137e2a  dec     rdx
0x180137e2d  lea     rdx, [r8+rdx*2]
0x180137e31  cmp     rdx, r8
0x180137e34  jbe     short loc_180137E41
0x180137e36  cmp     ax, [rdx]
0x180137e39  jz      short loc_180137E46
0x180137e3b  sub     rdx, 2
0x180137e3f  jmp     short loc_180137E31
0x180137e41  cmp     ax, [rdx]
0x180137e44  jnz     short loc_180137E72
0x180137e46  movzx   eax, word ptr [r14+4Ah]
0x180137e4b  add     rdx, 2
0x180137e4f  mov     rcx, rdx
0x180137e52  mov     [r14+60h], rdx
0x180137e56  sub     rcx, r8
0x180137e59  sar     rcx, 1
0x180137e5c  add     cx, cx
0x180137e5f  sub     r9w, cx
0x180137e63  sub     ax, cx
0x180137e66  mov     [r14+58h], r9w
0x180137e6b  mov     [r14+5Ah], ax
0x180137e70  jmp     short loc_180137E78
0x180137e72  movdqu  xmmword ptr [r14+58h], xmm0
0x180137e78  cmp     [r15+28h], ebx
0x180137e7c  jnz     short loc_180137E83
0x180137e7e  mov     rax, rbx
0x180137e81  jmp     short loc_180137E8B
0x180137e83  mov     eax, [r15+28h]
0x180137e87  add     rax, [r14+30h]
0x180137e8b  xor     edx, edx; Val
0x180137e8d  mov     [r14+38h], rax
0x180137e91  mov     rax, [r15+30h]
0x180137e95  mov     rcx, r13; void *
0x180137e98  mov     [r14+0F8h], rax
0x180137e9f  mov     [r14+98h], r13
0x180137ea6  lea     r8d, [rdx+50h]; Size
0x180137eaa  call    memset$thunk$772440563353939046
0x180137eaf  lea     rax, [r14+0A0h]
0x180137eb6  mov     qword ptr [rsp+690h+ShareAccess], rbx
0x180137ebb  mov     [rax], r13
0x180137ebe  lea     r8, [rbp+590h+var_5A8]
0x180137ec2  mov     [rax+8], r13
0x180137ec6  mov     r9d, 8
0x180137ecc  mov     [r13+0], rax
0x180137ed0  mov     [r13+8], rax
0x180137ed4  mov     dword ptr [r14+114h], 2
0x180137edf  mov     dword ptr [r13+18h], 0FFFFFFFFh
0x180137ee7  lea     edx, [r9-6]
0x180137eeb  mov     rax, [r13+0]
0x180137eef  mov     word ptr [rax-34h], 0FFFFh
0x180137ef5  mov     rcx, [rsp+690h+Handle]
0x180137efa  call    NtQuerySection
  ... truncated ...
```
