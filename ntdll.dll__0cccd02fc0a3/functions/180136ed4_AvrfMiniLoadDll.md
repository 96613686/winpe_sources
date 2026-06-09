# AvrfMiniLoadDll

- ea: `0x180136ed4`
- end: `0x18013790b`
- name: `AvrfMiniLoadDll`
- size: `2615`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180112488`

## callees

- `0x18001a080`
- `0x18001e820`
- `0x18001f070`
- `0x180029b70`
- `0x18002ad90`
- `0x180050d08`
- `0x180065ab0`
- `0x180066020`
- `0x1800661e0`
- `0x180066d14`
- `0x180067210`
- `0x180069678`
- `0x180069d44`
- `0x1800c0420`
- `0x1800c3810`
- `0x1800ea628`
- `0x180136ed4`
- `0x18015e4b0`
- `0x18015e7d0`
- `0x18015e810`
- `0x18015e930`
- `0x18015ea70`
- `0x18015ec10`
- `0x18015ecd0`
- `0x18015ecf0`
- `0x18015edd0`
- `0x1801609c0`
- `0x180161020`
- `0x180161cc0`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x180136fcd`: `\KnownDlls`
- `0x180137023`: `KnownDllPath`
- `0x180137469`: `AVRF: Verifier .dlls must not have thread locals\n`

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
              appended = NtCreateSection(&Handle, 13, 0);
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
0x180136ed4  mov     [rsp-8+arg_0], rbx
0x180136ed9  push    rbp
0x180136eda  push    rsi
0x180136edb  push    rdi
0x180136edc  push    r12
0x180136ede  push    r13
0x180136ee0  push    r14
0x180136ee2  push    r15
0x180136ee4  lea     rbp, [rsp-560h]
0x180136eec  sub     rsp, 660h
0x180136ef3  mov     rax, cs:__security_cookie
0x180136efa  xor     rax, rsp
0x180136efd  mov     [rbp+590h+var_40], rax
0x180136f04  mov     r14, [rbp+590h+arg_20]
0x180136f0b  lea     rcx, [rbp+590h+var_3C0]; void *
0x180136f12  xorps   xmm0, xmm0
0x180136f15  mov     [rbp+590h+var_580], r8
0x180136f19  xor     ebx, ebx
0x180136f1b  mov     [rbp+590h+var_588], rdx
0x180136f1f  xorps   xmm1, xmm1
0x180136f22  mov     [rbp+590h+var_600], r9
0x180136f26  xor     eax, eax
0x180136f28  mov     [rbp+590h+var_5E8], rbx
0x180136f2c  movups  xmmword ptr [rbp+590h+ObjectAttributes.ObjectName], xmm0
0x180136f30  xor     edx, edx; Val
0x180136f32  mov     [rbp+590h+var_5E0], rbx
0x180136f36  mov     r8d, 138h; Size
0x180136f3c  mov     [rbp+590h+var_260], rax
0x180136f43  movups  xmmword ptr [rbp+590h+ObjectAttributes+1Ch], xmm0
0x180136f47  mov     [rsp+690h+Handle], rbx
0x180136f4c  movups  xmmword ptr [rbp+590h+ObjectAttributes.Length], xmm0
0x180136f50  mov     [rbp+590h+FileHandle], rbx
0x180136f54  movups  [rbp+590h+var_280], xmm0
0x180136f5b  mov     [rsp+690h+var_628], rbx
0x180136f60  movups  [rbp+590h+var_270], xmm0
0x180136f67  mov     [rbp+590h+var_590], rbx
0x180136f6b  movups  xmmword ptr [rsp+690h+var_618.Length], xmm0
0x180136f70  movups  xmmword ptr [rbp+590h+DestinationString.Length], xmm1
0x180136f74  movups  xmmword ptr [rbp+590h+var_568.Length], xmm0
0x180136f78  movups  [rsp+690h+var_640], xmm1
0x180136f7d  movups  xmmword ptr [rbp+590h+IoStatusBlock.___u0], xmm0
0x180136f84  call    memset$thunk$772440563353939046
0x180136f89  xor     edx, edx; Val
0x180136f8b  mov     [rbp+590h+var_5A0], rbx
0x180136f8f  mov     r8d, 0D0h; Size
0x180136f95  mov     [rbp+590h+var_5F8], rbx
0x180136f99  lea     rcx, [rbp+590h+var_490]; void *
0x180136fa0  mov     [rsp+690h+var_630], ebx
0x180136fa4  mov     [rbp+590h+var_598], rbx
0x180136fa8  call    memset$thunk$772440563353939046
0x180136fad  xorps   xmm0, xmm0
0x180136fb0  mov     [rbp+590h+var_608], ebx
0x180136fb3  xor     eax, eax
0x180136fb5  lea     rcx, [rbp+590h+var_540]; void *
0x180136fb9  xor     edx, edx; Val
0x180136fbb  mov     [rbp+590h+var_53C], eax
0x180136fbe  mov     r8d, 94h; Size
0x180136fc4  movups  [rbp+590h+var_550], xmm0
0x180136fc8  call    memset$thunk$772440563353939046
0x180136fcd  lea     rdx, aKnowndlls; "\\KnownDlls"
0x180136fd4  mov     [rbp+590h+var_5A8], rbx
0x180136fd8  lea     rcx, [rbp+590h+DestinationString]; DestinationString
0x180136fdc  mov     [rsp+690h+var_630], ebx
0x180136fe0  call    RtlInitUnicodeString
0x180136fe5  lea     rax, [rbp+590h+DestinationString]
0x180136fe9  mov     [rbp+590h+ObjectAttributes.RootDirectory], rbx
0x180136fed  xorps   xmm0, xmm0
0x180136ff0  mov     [rbp+590h+ObjectAttributes.ObjectName], rax
0x180136ff4  lea     r12d, [rbx+30h]
0x180136ff8  lea     r13d, [rbx+40h]
0x180136ffc  mov     [rbp+590h+ObjectAttributes.Length], r12d
0x180137000  lea     r8, [rbp+590h+ObjectAttributes]
0x180137004  mov     [rbp+590h+ObjectAttributes.Attributes], r13d
0x180137008  lea     edx, [rbx+3]
0x18013700b  lea     rcx, [rbp+590h+var_5E8]
0x18013700f  movdqu  xmmword ptr [rbp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180137014  call    ZwOpenDirectoryObject
0x180137019  mov     esi, eax
0x18013701b  test    eax, eax
0x18013701d  js      loc_180137583
0x180137023  lea     rdx, aKnowndllpath; "KnownDllPath"
0x18013702a  lea     rcx, [rbp+590h+var_568]; DestinationString
0x18013702e  call    RtlInitUnicodeString
0x180137033  mov     rax, [rbp+590h+var_5E8]
0x180137037  lea     r15d, [rbx+1]
0x18013703b  mov     [rbp+590h+ObjectAttributes.RootDirectory], rax
0x18013703f  lea     r8, [rbp+590h+ObjectAttributes]
0x180137043  lea     rax, [rbp+590h+var_568]
0x180137047  mov     [rbp+590h+ObjectAttributes.Length], r12d
0x18013704b  xorps   xmm0, xmm0
0x18013704e  mov     [rbp+590h+ObjectAttributes.ObjectName], rax
0x180137052  mov     edx, r15d
0x180137055  mov     [rbp+590h+ObjectAttributes.Attributes], r13d
0x180137059  lea     rcx, [rbp+590h+var_5E0]
0x18013705d  movdqu  xmmword ptr [rbp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180137062  call    ZwOpenSymbolicLinkObject
0x180137067  mov     esi, eax
0x180137069  test    eax, eax
0x18013706b  js      loc_180137583
0x180137071  mov     rcx, [rbp+590h+var_5E0]
0x180137075  lea     rax, [rbp+590h+var_248]
0x18013707c  xor     r8d, r8d
0x18013707f  mov     qword ptr [rsp+690h+var_640+8], rax
0x180137084  lea     rdx, [rsp+690h+var_640]
0x180137089  mov     [rbp+590h+var_250], 3F005Ch
0x180137093  mov     [rbp+590h+var_24C], 5C003Fh
0x18013709d  mov     dword ptr [rsp+690h+var_640], 2000000h
0x1801370a5  call    NtQuerySymbolicLinkObject
0x1801370aa  mov     esi, eax
0x1801370ac  test    eax, eax
0x1801370ae  js      loc_180137583
0x1801370b4  lea     rax, [rbp+590h+var_250]
0x1801370bb  mov     qword ptr [rsp+690h+var_640+8], rax
0x1801370c0  lea     rdx, asc_180177BA4; "\\"
0x1801370c7  lea     eax, [rbx+8]
0x1801370ca  add     word ptr [rsp+690h+var_640], ax
0x1801370cf  lea     rcx, [rsp+690h+var_618]; DestinationString
0x1801370d4  add     word ptr [rsp+690h+var_640+2], ax
0x1801370d9  call    RtlInitUnicodeString
0x1801370de  lea     rdx, [rsp+690h+var_618]
0x1801370e3  lea     rcx, [rsp+690h+var_640]
0x1801370e8  call    RtlAppendUnicodeStringToString
0x1801370ed  mov     esi, eax
0x1801370ef  test    eax, eax
0x1801370f1  js      loc_180137583
0x1801370f7  lea     rdx, VerifierDllString
0x1801370fe  lea     rcx, [rsp+690h+var_640]
0x180137103  call    RtlAppendUnicodeStringToString
0x180137108  mov     esi, eax
0x18013710a  test    eax, eax
0x18013710c  js      loc_180137583
0x180137112  mov     rax, gs:60h
0x18013711b  lea     edi, [rbx+10h]
0x18013711e  test    dword ptr [rax+0BCh], 40000h
0x180137128  jz      short loc_18013714F
0x18013712a  movaps  xmm0, [rsp+690h+var_640]
0x18013712f  lea     rdx, [rbp+590h+var_550]
0x180137133  mov     qword ptr [rsp+690h+OpenOptions], rbx
0x180137138  lea     ecx, [rbx+26h]
0x18013713b  xor     r9d, r9d
0x18013713e  movdqa  [rbp+590h+var_550], xmm0
0x180137143  mov     r8d, edi
0x180137146  mov     [rsp+690h+ShareAccess], ebx
0x18013714a  call    ZwSystemDebugControl
0x18013714f  lea     rax, [rsp+690h+var_640]
0x180137154  mov     [rbp+590h+ObjectAttributes.Length], r12d
0x180137158  xorps   xmm0, xmm0
0x18013715b  mov     [rbp+590h+ObjectAttributes.ObjectName], rax
0x18013715f  lea     rdx, [rbp+590h+var_280]
0x180137166  mov     [rbp+590h+ObjectAttributes.RootDirectory], rbx
0x18013716a  lea     rcx, [rbp+590h+ObjectAttributes]
0x18013716e  mov     [rbp+590h+ObjectAttributes.Attributes], r13d
0x180137172  movdqu  xmmword ptr [rbp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180137177  call    ZwQueryAttributesFile
0x18013717c  test    eax, eax
0x18013717e  jns     short loc_180137198
0x180137180  cmp     eax, 0C0000043h
0x180137185  jz      short loc_180137198
0x180137187  cmp     eax, 0C0000022h
0x18013718c  jz      short loc_180137198
0x18013718e  mov     esi, 0C0000135h
0x180137193  jmp     loc_180137583
0x180137198  mov     [rsp+690h+OpenOptions], 60h ; '`'; OpenOptions
0x1801371a0  lea     r9, [rbp+590h+IoStatusBlock]; IoStatusBlock
0x1801371a7  lea     r8, [rbp+590h+ObjectAttributes]; ObjectAttributes
0x1801371ab  mov     [rsp+690h+ShareAccess], 5; ShareAccess
0x1801371b3  mov     edx, 100020h; DesiredAccess
0x1801371b8  lea     rcx, [rbp+590h+FileHandle]; FileHandle
0x1801371bc  call    NtOpenFile
0x1801371c1  mov     esi, eax
0x1801371c3  test    eax, eax
0x1801371c5  jns     short loc_1801371D4
0x1801371c7  cmp     eax, 0C0000034h
0x1801371cc  jnz     loc_180137583
0x1801371d2  jmp     short loc_18013718E
0x1801371d4  mov     rax, [rbp+590h+FileHandle]
0x1801371d8  lea     rcx, [rsp+690h+Handle]
0x1801371dd  mov     [rsp+690h+var_660], rax
0x1801371e2  xor     r9d, r9d
0x1801371e5  mov     [rsp+690h+OpenOptions], 1000000h
0x1801371ed  xor     r8d, r8d
0x1801371f0  mov     [rsp+690h+ShareAccess], edi
0x1801371f4  lea     edx, [r9+0Dh]
0x1801371f8  call    NtCreateSection
0x1801371fd  mov     esi, eax
0x1801371ff  test    eax, eax
0x180137201  js      loc_180137583
0x180137207  lea     rax, [r14+198h]
0x18013720e  mov     word ptr [r14+18Ah], 208h
0x180137218  mov     [r14+190h], rax
0x18013721f  lea     r12, [r14+188h]
0x180137226  lea     rax, [rbp+590h+var_248]
0x18013722d  mov     [r12], bx
0x180137232  mov     qword ptr [rsp+690h+var_640+8], rax
0x180137237  lea     rdx, [rsp+690h+var_640]
0x18013723c  mov     eax, 0FFF8h
0x180137241  mov     rcx, r12
0x180137244  add     word ptr [rsp+690h+var_640], ax
0x180137249  add     word ptr [rsp+690h+var_640+2], ax
0x18013724e  call    RtlCopyUnicodeString
0x180137253  mov     rdi, gs:30h
0x18013725c  lea     r8, [rsp+690h+var_628]
0x180137261  mov     rax, qword ptr [rsp+690h+var_640+8]
0x180137266  xor     r9d, r9d
0x180137269  mov     [rsp+690h+var_648], 2
0x180137271  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180137275  mov     [rsp+690h+var_650], 800000h
0x18013727d  mov     rbx, [rdi+28h]
0x180137281  mov     [rdi+28h], rax
0x180137285  lea     rax, [rbp+590h+var_590]
0x180137289  mov     rcx, [rsp+690h+Handle]
0x18013728e  mov     [rsp+690h+var_658], r15d
0x180137293  mov     [rsp+690h+var_660], rax
0x180137298  mov     qword ptr [rsp+690h+OpenOptions], 0
0x1801372a1  mov     qword ptr [rsp+690h+ShareAccess], 0
0x1801372aa  call    ZwMapViewOfSection
0x1801372af  mov     [rdi+28h], rbx
0x1801372b3  mov     esi, eax
0x1801372b5  xor     ebx, ebx
0x1801372b7  test    eax, eax
0x1801372b9  js      loc_180137583
0x1801372bf  mov     rdx, [rsp+690h+var_628]
0x1801372c4  lea     r9, [rsp+690h+var_618]
0x1801372c9  xor     r8d, r8d
0x1801372cc  mov     qword ptr [rsp+690h+var_618.Length], rbx
0x1801372d1  mov     ecx, r15d
0x1801372d4  call    RtlImageNtHeaderEx
0x1801372d9  mov     r15, qword ptr [rsp+690h+var_618.Length]
0x1801372de  test    r15, r15
0x1801372e1  jnz     short loc_1801372ED
0x1801372e3  mov     esi, 0C000007Bh
0x1801372e8  jmp     loc_180137583
0x1801372ed  mov     rax, [rsp+690h+var_628]
0x1801372f2  lea     r13, [r14+138h]
0x1801372f9  mov     [r14+30h], rax
0x1801372fd  mov     eax, [r15+50h]
0x180137301  mov     [r14+40h], eax
0x180137305  mov     eax, [r15+8]
0x180137309  mov     [r14+80h], eax
0x180137310  mov     eax, 5Ch ; '\'
0x180137315  mov     [r14+90h], rbx
0x18013731c  movups  xmm0, xmmword ptr [r12]
0x180137321  mov     [r14+68h], ebx
0x180137325  movdqu  xmmword ptr [r14+48h], xmm0
0x18013732b  movzx   r9d, word ptr [r14+48h]
0x180137330  mov     r8, [r14+50h]
0x180137334  mov     edx, r9d
0x180137337  shr     rdx, 1
0x18013733a  dec     rdx
0x18013733d  lea     rdx, [r8+rdx*2]
0x180137341  cmp     rdx, r8
0x180137344  jbe     short loc_180137351
0x180137346  cmp     ax, [rdx]
0x180137349  jz      short loc_180137356
0x18013734b  sub     rdx, 2
0x18013734f  jmp     short loc_180137341
0x180137351  cmp     ax, [rdx]
0x180137354  jnz     short loc_180137382
0x180137356  movzx   eax, word ptr [r14+4Ah]
0x18013735b  add     rdx, 2
0x18013735f  mov     rcx, rdx
0x180137362  mov     [r14+60h], rdx
0x180137366  sub     rcx, r8
0x180137369  sar     rcx, 1
0x18013736c  add     cx, cx
0x18013736f  sub     r9w, cx
0x180137373  sub     ax, cx
0x180137376  mov     [r14+58h], r9w
0x18013737b  mov     [r14+5Ah], ax
0x180137380  jmp     short loc_180137388
0x180137382  movdqu  xmmword ptr [r14+58h], xmm0
0x180137388  cmp     [r15+28h], ebx
0x18013738c  jnz     short loc_180137393
0x18013738e  mov     rax, rbx
0x180137391  jmp     short loc_18013739B
0x180137393  mov     eax, [r15+28h]
0x180137397  add     rax, [r14+30h]
0x18013739b  xor     edx, edx; Val
0x18013739d  mov     [r14+38h], rax
0x1801373a1  mov     rax, [r15+30h]
0x1801373a5  mov     rcx, r13; void *
0x1801373a8  mov     [r14+0F8h], rax
0x1801373af  mov     [r14+98h], r13
0x1801373b6  lea     r8d, [rdx+50h]; Size
0x1801373ba  call    memset$thunk$772440563353939046
0x1801373bf  lea     rax, [r14+0A0h]
0x1801373c6  mov     qword ptr [rsp+690h+ShareAccess], rbx
0x1801373cb  mov     [rax], r13
0x1801373ce  lea     r8, [rbp+590h+var_5A8]
0x1801373d2  mov     [rax+8], r13
0x1801373d6  mov     r9d, 8
0x1801373dc  mov     [r13+0], rax
0x1801373e0  mov     [r13+8], rax
0x1801373e4  mov     dword ptr [r14+114h], 2
0x1801373ef  mov     dword ptr [r13+18h], 0FFFFFFFFh
0x1801373f7  lea     edx, [r9-6]
0x1801373fb  mov     rax, [r13+0]
0x1801373ff  mov     word ptr [rax-34h], 0FFFFh
0x180137405  mov     rcx, [rsp+690h+Handle]
0x18013740a  call    NtQuerySection
  ... truncated ...
```
