# AllocateAndInitializeExtObject(HKEY__ *,HKEY__ *,_UNICODE_STRING *)

- ea: `0x18000e1a8`
- end: `0x18000f639`
- name: `?AllocateAndInitializeExtObject@@YAPEAUEXT_OBJECT@@PEAUHKEY__@@0PEAU_UNICODE_STRING@@@Z`
- size: `5265`
- prototype: `struct EXT_OBJECT *__fastcall(HKEY, HKEY, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f640`

## callees

- `0x180005da0`
- `0x180007740`
- `0x180007fee`
- `0x18000802a`
- `0x180008050`
- `0x180009ef8`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000ab64`
- `0x18000b008`
- `0x18000bef8`
- `0x18000c134`
- `0x18000c2b0`
- `0x18000c774`
- `0x18000e1a8`
- `0x18000fb6c`
- `0x18000fdd0`
- `0x18000fea0`
- `0x180010020`
- `0x180010218`
- `0x18001335c`
- `0x18001e431`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18000f3ac`
- `ntdll!NtOpenThreadToken` at `0x18000f3ac`
- `ntdll!NtClose` at `0x18000f0c4`
- `ntdll!NtClose` at `0x18000f0c4`
- `ntdll!NtSetInformationThread` at `0x18000f3e1`
- `ntdll!NtSetInformationThread` at `0x18000f462`
- `ntdll!NtSetInformationThread` at `0x18000f3e1`
- `ntdll!NtSetInformationThread` at `0x18000f462`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f440`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f588`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f46c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f46c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f47b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f348`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e3b4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e3b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e27c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f012`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e27c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f012`

## string_xrefs

- `0x18000ec35`: `Keep Library Resident`
- `0x18000e6ad`: `Open Timeout`
- `0x18000ee2c`: `\Linkage`

## pseudocode

```c
struct EXT_OBJECT *__fastcall AllocateAndInitializeExtObject(HKEY a1, HKEY a2, struct _UNICODE_STRING *a3)
{
  unsigned __int16 *Buffer; // r12
  int v4; // esi
  HKEY v5; // r14
  LPCWCH *v6; // rbx
  void *v7; // rax
  unsigned int *v8; // r8
  _WORD *v9; // r15
  char *v11; // rdi
  unsigned __int64 v12; // r13
  DWORD LastError; // ebx
  unsigned int *v14; // r8
  __int64 v15; // r12
  unsigned int v16; // ebx
  size_t v17; // rbx
  char *v18; // rsi
  DWORD v19; // eax
  __int64 v20; // rax
  char *v21; // rsi
  _QWORD *v22; // rcx
  char *v23; // r15
  DWORD v24; // eax
  unsigned int v25; // r14d
  __int64 v26; // r14
  char *v27; // rsi
  __int64 v28; // r14
  DWORD v29; // eax
  unsigned int *v30; // r8
  char *v31; // r15
  BOOL v32; // eax
  unsigned __int16 *v33; // r14
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned __int16 *v36; // r15
  __int64 v37; // rdx
  __int64 v38; // rcx
  HKEY v39; // rbx
  __int64 v40; // r14
  unsigned int *v41; // r8
  unsigned int v42; // eax
  unsigned int v43; // ebx
  __int64 v44; // rsi
  __int64 v45; // rdx
  __int64 v46; // rcx
  HKEY v47; // rbx
  unsigned int *v48; // r8
  unsigned int *v49; // r8
  const wchar_t *v50; // r14
  int v51; // eax
  unsigned int *v52; // r8
  __int64 v53; // r15
  bool v54; // zf
  wchar_t v55; // ax
  const wchar_t *v56; // rbx
  wchar_t *v57; // rsi
  __int64 v58; // rax
  unsigned __int16 *v59; // rbx
  unsigned int v60; // r15d
  unsigned int *v61; // r8
  int v62; // esi
  unsigned int *v63; // r8
  unsigned int *v64; // r8
  unsigned int *v65; // r8
  LSTATUS v66; // eax
  unsigned int *v67; // r8
  HKEY v68; // rcx
  int v69; // eax
  unsigned int v70; // esi
  unsigned int *v71; // r8
  unsigned int v72; // edx
  __int64 v73; // rsi
  __int64 v74; // rsi
  char *v75; // rbx
  char *v76; // rax
  char *v77; // r8
  int v78; // ecx
  int v79; // edx
  char *v80; // r14
  char *v81; // rax
  char *v82; // r8
  int v83; // ecx
  int v84; // edx
  unsigned __int8 *v85; // rax
  char *v86; // r8
  int v87; // ecx
  int v88; // edx
  __int64 v89; // rsi
  __int64 v90; // rax
  char *v91; // r8
  int v92; // eax
  char *v93; // r9
  unsigned __int64 v94; // rdx
  char *v95; // rcx
  char *v96; // r9
  unsigned __int64 v97; // rdx
  const char *v98; // r8
  unsigned __int64 v99; // rcx
  char *v100; // rax
  const unsigned __int16 *v101; // r8
  unsigned __int16 *v102; // rcx
  unsigned __int64 v103; // rdx
  unsigned __int16 *v104; // rsi
  unsigned __int64 v105; // r14
  void *v106; // rcx
  int v107; // eax
  unsigned int v108; // esi
  unsigned int v109; // eax
  DWORD CurrentProcessId; // eax
  HANDLE CurrentThread; // rax
  NTSTATUS v112; // eax
  BOOL v113; // ebx
  DWORD v114; // eax
  int SD; // eax
  __int64 *v116; // rax
  char *v117; // rdx
  unsigned int v118; // eax
  const unsigned __int16 *v119; // r8
  unsigned __int16 *v120; // rcx
  unsigned int v121; // [rsp+28h] [rbp-D8h]
  unsigned int v122; // [rsp+28h] [rbp-D8h]
  unsigned int v123; // [rsp+28h] [rbp-D8h]
  unsigned int v124; // [rsp+28h] [rbp-D8h]
  unsigned int v125; // [rsp+28h] [rbp-D8h]
  unsigned int v126; // [rsp+28h] [rbp-D8h]
  unsigned int v127; // [rsp+28h] [rbp-D8h]
  unsigned int v128; // [rsp+28h] [rbp-D8h]
  unsigned int v129; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v130; // [rsp+44h] [rbp-BCh] BYREF
  int v131; // [rsp+48h] [rbp-B8h]
  HKEY KeyHandle; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v133; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v134; // [rsp+60h] [rbp-A0h] BYREF
  int v135; // [rsp+68h] [rbp-98h]
  unsigned int v136; // [rsp+6Ch] [rbp-94h]
  unsigned __int8 v137[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v138[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int8 v139[4]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v140[4]; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v141; // [rsp+80h] [rbp-80h]
  char *v142; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v143[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v144[4]; // [rsp+94h] [rbp-6Ch] BYREF
  char *v145; // [rsp+98h] [rbp-68h]
  void *TokenHandle; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v147; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 v148[8]; // [rsp+B0h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp-48h] BYREF
  char *v150; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING *ThreadInformation; // [rsp+C8h] [rbp-38h] BYREF
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+D0h] [rbp-30h] BYREF
  void *Block; // [rsp+E8h] [rbp-18h]
  LPCWCH *v154; // [rsp+F0h] [rbp-10h]
  LPCWCH lpString2; // [rsp+F8h] [rbp-8h]
  HKEY hKey; // [rsp+100h] [rbp+0h]
  void *v157; // [rsp+108h] [rbp+8h]
  unsigned __int8 v158[16]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD Src[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v160[32]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR Name[576]; // [rsp+260h] [rbp+160h] BYREF

  Buffer = a3->Buffer;
  v4 = 0;
  phkResult = 0;
  *(_DWORD *)v143 = 0;
  v5 = a2;
  *(_DWORD *)v139 = 0;
  *(_DWORD *)v140 = 0;
  *(_DWORD *)v144 = 0;
  *(_OWORD *)v158 = 0;
  *(_QWORD *)v148 = 0;
  *(_DWORD *)v137 = 0;
  *(_DWORD *)v138 = 0;
  v147 = 0;
  v142 = 0;
  v133 = 0;
  v134 = Buffer;
  ThreadInformation = a3;
  KeyHandle = a2;
  hKey = a1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, Buffer);
  v6 = (LPCWCH *)ExtensibleObjects;
  v154 = 0;
  while ( 1 )
  {
    Block = v6;
    if ( !v6 )
      break;
    if ( CompareStringOrdinal(v6[49], -1, Buffer, -1, 1) == 2 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids);
      break;
    }
    v154 = v6;
    v6 = (LPCWCH *)*v6;
  }
  v7 = (void *)operator new(5896);
  v157 = v7;
  v9 = v7;
  if ( !v7 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, 5896);
    return 0;
  }
  v129 = 0;
  *(_QWORD *)v148 = 0;
  *(_DWORD *)v138 = dwExtCtrOpenProcWaitMs;
  *(_DWORD *)v137 = dwExtCtrOpenProcWaitMs;
  v11 = 0;
  v131 = 0;
  v12 = 0;
  *(_OWORD *)v158 = 0;
  *(_DWORD *)v144 = 1000;
  v130 = 1072;
  LastError = PrivateRegQueryValueExT(v5, L"Library", v8, &v129, (unsigned __int8 *)v7, &v130, 1);
  if ( LastError )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, Buffer);
    goto LABEL_262;
  }
  v15 = 528;
  v16 = v130 + 8;
  v9[(unsigned __int64)v130 >> 1] = 0;
  v17 = v16 & 0xFFFFFFF8;
  v18 = (char *)v9 + v17;
  lpString2 = (_WORD *)((char *)v9 + v17);
  if ( v129 != 2 )
  {
    if ( v129 == 1 )
    {
      memcpy_0((char *)v9 + v17, v9, v17);
      v21 = &v18[v17];
      v15 = v17 + 528;
      goto LABEL_21;
    }
    LastError = 1154;
    v22 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, 1154);
      v22 = WPP_GLOBAL_Control;
      v21 = v18 + 8;
      v150 = v21;
      goto LABEL_35;
    }
LABEL_23:
    v21 = v18 + 8;
    v150 = v21;
LABEL_35:
    v26 = 8;
    if ( (*((_BYTE *)v22 + 28) & 4) != 0 && *((_BYTE *)v22 + 25) >= 2u )
      WPP_SF_S(v22[2], 17, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v134);
    goto LABEL_38;
  }
  v19 = ExpandEnvironmentStringsW(v9, (_WORD *)((char *)v9 + v17), 0x218u);
  if ( v19 - 1 > 0x217 )
  {
    v22 = WPP_GLOBAL_Control;
    LastError = 1154;
    goto LABEL_23;
  }
  v20 = (2 * v19 + 9) & 0xFFFFFFF8;
  v21 = &v18[v20];
  v15 = v20 + 528;
LABEL_21:
  v150 = v21;
  v130 = 536;
  v23 = v21;
  v24 = PrivateRegQueryValueExT(v5, L"Open", v14, &v129, (unsigned __int8 *)v21, &v130, 0);
  LastError = v24;
  if ( v24 )
  {
    v32 = v24 == 2 || v24 == 234;
LABEL_50:
    v33 = v134;
    v131 = v32;
    if ( v134 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
          (_DWORD)v134,
          LastError);
    }
    else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, LastError);
    }
    if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
      McTemplateU0sz_EtwEventWriteTransfer(v35, v34, "Open", v33);
    v26 = 8;
    if ( LastError )
      goto LABEL_38;
    goto LABEL_61;
  }
  if ( !*v21 )
  {
    LastError = 1;
    v32 = 1;
    goto LABEL_50;
  }
  if ( ((unsigned __int8)(v24 + 4) & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= (unsigned __int8)(v24 + 4) )
  {
    WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), v24 + 16, (_DWORD)v14, (_DWORD)v21, (__int64)v134);
  }
  v25 = v130 + 8;
  v21[v130] = 0;
  v26 = v25 & 0xFFFFFFF8;
LABEL_61:
  v129 = 0;
  v15 += v26;
  v130 = 4;
  LastError = PrivateRegQueryValueExT(KeyHandle, L"Open Timeout", v14, &v129, v137, &v130, 1);
  if ( LastError || v129 != 4 )
  {
    v27 = &v21[v26];
    TokenHandle = &v23[v26];
    v28 = 8;
    *(_DWORD *)v137 = dwExtCtrOpenProcWaitMs;
    goto LABEL_39;
  }
LABEL_38:
  v27 = &v21[v26];
  v28 = 8;
  TokenHandle = v27;
  if ( LastError )
    goto LABEL_259;
LABEL_39:
  v130 = 536;
  v29 = PrivateRegQueryValueExT(KeyHandle, L"Close", v14, &v129, (unsigned __int8 *)v27, &v130, 0);
  LastError = v29;
  if ( v29 )
  {
    if ( v29 == 2 || v29 == 234 )
      v131 = 1;
LABEL_68:
    v36 = v134;
    if ( v134 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
          (_DWORD)v134,
          LastError);
    }
    else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, LastError);
    }
    if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
      McTemplateU0sz_EtwEventWriteTransfer(v38, v37, "Close", v36);
    if ( !LastError )
    {
      v31 = v27 + 8;
      goto LABEL_80;
    }
LABEL_259:
    Buffer = v134;
LABEL_260:
    v5 = KeyHandle;
    goto LABEL_261;
  }
  if ( !*v27 )
  {
    LastError = 1;
    v131 = 1;
    goto LABEL_68;
  }
  if ( ((unsigned __int8)(v29 + 4) & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= (unsigned __int8)(v29 + 4) )
  {
    WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), v29 + 20, (_DWORD)v30, (_DWORD)v27, (__int64)v134);
  }
  v28 = (v130 + 8) & 0xFFFFFFF8;
  v31 = &v27[v28];
LABEL_80:
  v39 = KeyHandle;
  v145 = v31;
  v40 = v15 + v28;
  v135 = 0;
  v136 = 0;
  v141 = v40;
  v130 = 536;
  if ( (unsigned int)PrivateRegQueryValueExT(KeyHandle, L"Query", v30, &v129, (unsigned __int8 *)v31, &v130, 0)
    && (v130 = 536,
        v42 = PrivateRegQueryValueExT(v39, L"Collect", v41, &v129, (unsigned __int8 *)v31, &v130, 0),
        (v43 = v42) != 0) )
  {
    v44 = 8;
    if ( v42 == 2 || v42 == 234 )
      v131 = 1;
  }
  else
  {
    v44 = (v130 + 8) & 0xFFFFFFF8;
    v141 = v44 + v40;
    if ( *v31 )
    {
      Buffer = v134;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, (_DWORD)v41, (_DWORD)v31, (__int64)v134);
      goto LABEL_101;
    }
    v43 = 1;
    v131 = 1;
  }
  Buffer = v134;
  if ( v134 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
        (_DWORD)v134,
        v43);
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v43);
  }
  if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
    McTemplateU0sz_EtwEventWriteTransfer(v46, v45, "Collect", Buffer);
  if ( v43 )
  {
    v47 = KeyHandle;
    goto LABEL_105;
  }
LABEL_101:
  v130 = 4;
  v47 = KeyHandle;
  v129 = 0;
  if ( (unsigned int)PrivateRegQueryValueExT(KeyHandle, L"Collect Timeout", v41, &v129, v138, &v130, 1) || v129 != 4 )
    *(_DWORD *)v138 = dwExtCtrOpenProcWaitMs;
LABEL_105:
  v129 = 0;
  v130 = 4;
  if ( (unsigned int)PrivateRegQueryValueExT(v47, L"First Counter", v41, &v129, v139, &v130, 1) || v129 != 4 )
    *(_DWORD *)v139 = 0;
  v129 = 0;
  v130 = 4;
  if ( (unsigned int)PrivateRegQueryValueExT(v47, L"Last Counter", v48, &v129, v140, &v130, 1) || v129 != 4 )
    *(_DWORD *)v140 = 0;
  v50 = (const wchar_t *)&v31[v44];
  v129 = 0;
  v130 = 1072;
  v51 = PrivateRegQueryValueExT(v47, L"Object List", v49, &v129, (unsigned __int8 *)&v31[v44], &v130, 1);
  v52 = 0;
  if ( v51 )
  {
    *v50 = 0;
    v53 = 8;
    goto LABEL_141;
  }
  v53 = (v130 + 8) & 0xFFFFFFF8;
  v54 = v129 == 1;
  v50[(unsigned __int64)v130 >> 1] = 0;
  if ( !v54 )
  {
    if ( v129 != 7 )
      goto LABEL_141;
    v56 = v50;
    v136 = 0;
    if ( !*v50 )
      goto LABEL_134;
    do
    {
      if ( (unsigned int)v12 >= 0x40 )
        break;
      Src[v12] = o_wcstoul_0(v56, 0, 10);
      v12 = (unsigned int)(v12 + 1);
      v58 = -1;
      v52 = 0;
      do
        ++v58;
      while ( v56[v58] );
      v56 += v58 + 1;
    }
    while ( *v56 );
    Buffer = v134;
LABEL_133:
    v136 = v12;
LABEL_134:
    if ( !v56 )
      goto LABEL_141;
    goto LABEL_135;
  }
  v55 = *v50;
  if ( *v50 )
  {
    v56 = 0;
    v57 = (wchar_t *)v50;
    do
    {
      if ( v55 == 32 )
      {
        if ( v56 && (unsigned int)v12 < 0x40 )
        {
          *v57 = 0;
          Src[v12] = o_wcstoul_0(v56, 0, 10);
          v12 = (unsigned int)(v12 + 1);
          *v57 = 32;
          v52 = 0;
          v56 = 0;
        }
      }
      else if ( !v56 )
      {
        v56 = v57;
      }
      v55 = *++v57;
    }
    while ( *v57 );
    v136 = v12;
    if ( v56 )
    {
      if ( (unsigned int)v12 >= 0x40 || v56 == v57 )
      {
LABEL_135:
        if ( *v56 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids);
          PerfpThrottleError(0xBBAu, 0, &PerfpErrorLog);
        }
        goto LABEL_141;
      }
      Src[v12] = o_wcstoul_0(v56, 0, 10);
      LODWORD(v12) = v12 + 1;
      v52 = 0;
      v56 = 0;
      goto LABEL_133;
    }
  }
LABEL_141:
  v59 = (unsigned __int16 *)((char *)v50 + v53);
  v130 = 4;
  v5 = KeyHandle;
  v60 = 0;
  v129 = 0;
  *(_DWORD *)v143 = 0;
  v62 = 0;
  if ( !(unsigned int)PrivateRegQueryValueExT(KeyHandle, L"Keep Library Resident", v52, &v129, v143, &v130, 1)
    && v129 == 4 )
  {
    if ( *(_DWORD *)v143 == 1 )
      v62 = 4;
    v135 = v62;
  }
  v130 = 4;
  v129 = 0;
  LODWORD(v134) = 0;
  if ( !(unsigned int)PrivateRegQueryValueExT(
                        v5,
                        L"Collect Supports Metadata",
                        v61,
                        &v129,
                        (unsigned __int8 *)&v134,
                        &v130,
                        1)
    && v129 == 4
    && (_DWORD)v134 == 1 )
  {
    v135 = v62 | 0x80;
  }
  v130 = 4;
  PrivateRegQueryValueExT(v5, L"Error Count Limit", v63, &v129, v144, &v130, 1);
  v129 = 0;
  v130 = 16;
  if ( (unsigned int)PrivateRegQueryValueExT(v5, L"Library Validation Code", v64, &v129, v158, &v130, 1)
    || v129 != 3
    || v130 != 16 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, Buffer);
    *(_OWORD *)v158 = 0;
  }
  v129 = 0;
  v130 = 8;
  *(_QWORD *)v148 = 0;
  if ( (unsigned int)PrivateRegQueryValueExT(v5, L"Successful File Date", v65, &v129, v148, &v130, 1)
    || v129 != 3
    || v130 != 8 )
  {
    *(_QWORD *)v148 = -1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids);
  }
  v66 = StringCchCopyExW(v59, 0x218u, Buffer, &v147, &v133, v121);
  if ( v66 >= 0 )
    v66 = StringCchCopyW(v147, v133, L"\\Linkage");
  v68 = 0;
  phkResult = 0;
  if ( v66 < 0 )
  {
    v66 = (unsigned __int16)v66;
  }
  else
  {
    v66 = RegOpenKeyExW(hKey, v59, 0, 0x20019u, &phkResult);
    v68 = phkResult;
  }
  if ( v66 || !v68 )
  {
    v74 = v141;
    v12 = 0;
    goto LABEL_188;
  }
  v130 = 0;
  v129 = 0;
  v69 = PrivateRegQueryValueExT(v68, L"Export", v67, &v129, 0, &v130, 1);
  if ( (!v69 || v69 == 234) && (v129 == 1 || v129 == 7) )
  {
    v70 = v130;
    v12 = operator new(saturated_mul(((unsigned __int64)(v130 + 1) >> 1) + 1, 2u));
    if ( v12 )
    {
      v129 = 0;
      LastError = PrivateRegQueryValueExT(phkResult, L"Export", v71, &v129, (unsigned __int8 *)v12, &v130, 1);
      if ( !LastError && (v129 == 1 || v129 == 7) )
      {
        v72 = v130;
        v73 = v141;
        *(_WORD *)(v12 + 2 * ((unsigned __int64)v130 >> 1)) = 0;
        v60 = v72 + 2;
        v74 = ((v72 + 9) & 0xFFFFFFF8) + v73;
        goto LABEL_185;
      }
      operator delete((void *)v12);
      LastError = 0;
      v12 = 0;
    }
    else
    {
      LastError = 14;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v70);
    }
  }
  else
  {
    v12 = 0;
    LastError = 0;
  }
  v74 = v141;
LABEL_185:
  RegCloseKey(phkResult);
  if ( LastError )
    goto LABEL_261;
LABEL_188:
  v75 = (char *)Block;
  if ( Block )
  {
    if ( *((_DWORD *)Block + 93) == *(_DWORD *)v139
      && *((_DWORD *)Block + 94) == *(_DWORD *)v140
      && CompareStringOrdinal(*((LPCWCH *)Block + 12), -1, lpString2, -1, 1) == 2 )
    {
      v76 = (char *)*((_QWORD *)v75 + 3);
      v77 = (char *)(v150 - v76);
      do
      {
        v78 = (unsigned __int8)v77[(_QWORD)v76];
        v79 = (unsigned __int8)*v76 - v78;
        if ( v79 )
          break;
        ++v76;
      }
      while ( v78 );
      v80 = v145;
      if ( !v79 )
      {
        v81 = (char *)*((_QWORD *)v75 + 6);
        v82 = (char *)(v145 - v81);
        do
        {
          v83 = (unsigned __int8)v82[(_QWORD)v81];
          v84 = (unsigned __int8)*v81 - v83;
          if ( v84 )
            break;
          ++v81;
        }
        while ( v83 );
        if ( !v84 )
        {
          v85 = (unsigned __int8 *)*((_QWORD *)v75 + 9);
          v86 = (char *)((_BYTE *)TokenHandle - v85);
          do
          {
            v87 = (unsigned __int8)v86[(_QWORD)v85];
            v88 = *v85 - v87;
            if ( v88 )
              break;
            ++v85;
          }
          while ( v87 );
          if ( !v88 )
          {
            v11 = v75;
            v75[524] = 0;
            goto LABEL_249;
          }
        }
      }
    }
    else
    {
      v80 = v145;
    }
    if ( v154 )
      *v154 = *(LPCWCH *)v75;
    else
      ExtensibleObjects = *(struct EXT_OBJECT **)v75;
    CloseExtObjectLibrary((struct EXT_OBJECT *)v75, 1);
    NtClose(*((HANDLE *)v75 + 13));
    --NumExtensibleObjects;
    operator delete(v75);
  }
  else
  {
    v80 = v145;
  }
  v89 = ((ThreadInformation->MaximumLength + 7LL) & 0xFFFFFFF8LL) + v74;
  v90 = operator new(v89);
  v11 = (char *)v90;
  if ( !v90 )
  {
    LastError = 14;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
        (unsigned int)v89);
    goto LABEL_260;
  }
  v91 = v150;
  *(_QWORD *)(v90 + 24) = v90 + 528;
  v92 = StringCbCopyExA((char *)(v90 + 528), v89 - 528, v91, &v142, &v133, v122);
  if ( v92 < 0 )
    goto LABEL_213;
  v93 = v142;
  v94 = v133;
  *((_DWORD *)v11 + 15) = *(_DWORD *)v137;
  v95 = (char *)((unsigned __int64)(v93 + 8) & 0xFFFFFFFFFFFFFFF8uLL);
  *((_QWORD *)v11 + 6) = v95;
  v92 = StringCbCopyExA(v95, (unsigned __int64)&v93[v94 - (_QWORD)v95], v80, &v142, &v133, v123);
  if ( v92 < 0 )
    goto LABEL_213;
  v96 = v142;
  v97 = v133;
  v98 = (const char *)TokenHandle;
  v99 = (unsigned __int64)(v142 + 8);
  *((_DWORD *)v11 + 14) = *(_DWORD *)v138;
  v99 &= 0xFFFFFFFFFFFFFFF8uLL;
  *((_QWORD *)v11 + 9) = v99;
  v92 = StringCbCopyExA((char *)v99, (unsigned __int64)&v96[v97 - v99], v98, &v142, &v133, v124);
  if ( v92 < 0
    || (v100 = v142,
        v101 = lpString2,
        v102 = (unsigned __int16 *)((unsigned __int64)(v142 + 8) & 0xFFFFFFFFFFFFFFF8uLL),
        v103 = v133 - (_QWORD)v102,
        *((_QWORD *)v11 + 12) = v102,
        v92 = StringCchCopyExW(v102, (unsigned __int64)&v100[v103] >> 1, v101, (unsigned __int16 **)&v142, &v133, v125),
        v92 < 0) )
  {
LABEL_213:
    v5 = KeyHandle;
    LastError = (unsigned __int16)v92;
    goto LABEL_248;
  }
  v104 = (unsigned __int16 *)((unsigned __int64)(v142 + 23) & 0xFFFFFFFFFFFFFFF8uLL);
  v105 = (unsigned __int64)&v142[2 * v133 - (_QWORD)v104];
  if ( v12 )
  {
    v106 = (void *)((unsigned __int64)(v142 + 23) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)v11 + 4) = v104;
    memcpy_0(v106, (const void *)v12, v60);
    v104 = (unsigned __int16 *)(((unsigned __int64)&v104[((unsigned __int64)v60 >> 1) + 3] + 1) & 0xFFFFFFFFFFFFFFF8uLL);
    operator delete((void *)v12);
    v12 = 0;
    v105 -= (v60 + 7) & 0xFFFFFFF8;
  }
  *((_QWORD *)v11 + 49) = v104;
  v107 = StringCchCopyExW(v104, v105 >> 1, Buffer, (unsigned __int16 **)&v142, &v133, v126);
  v5 = KeyHandle;
  v108 = 0;
  if ( v107 < 0 )
  {
    LastError = (unsigned __int16)v107;
    goto LABEL_248;
  }
  *((_DWORD *)v11 + 95) = v135;
  *((_QWORD *)v11 + 13) = v5;
  *(_OWORD *)(v11 + 408) = *(_OWORD *)v158;
  *((_QWORD *)v11 + 53) = *(_QWORD *)v148;
  *((_DWORD *)v11 + 96) = 1;
  *((_DWORD *)v11 + 93) = *(_DWORD *)v139;
  *((_DWORD *)v11 + 94) = *(_DWORD *)v140;
  v109 = v136;
  if ( v136 )
  {
    *((_DWORD *)v11 + 28) = v136;
    memcpy_0(v11 + 116, Src, 4LL * v109);
  }
  *((_QWORD *)v11 + 50) = 0;
  if ( (int)StringCchCopyExW(Name, 0x218u, Buffer, &v147, &v133, v127) >= 0 )
    StringCchCopyExW(v147, v133, L"_Perf_Library_Lock_PID_", &v147, &v133, v128);
  CurrentProcessId = GetCurrentProcessId();
  o__ultow_s_0(CurrentProcessId, v160, 32);
  if ( (int)StringCchCopyW(v147, v133, v160) < 0 )
    v160[0] = 0;
  TokenHandle = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  CurrentThread = GetCurrentThread();
  v112 = NtOpenThreadToken(CurrentThread, 4u, 1u, &TokenHandle);
  if ( v112 >= 0 )
  {
    ThreadInformation = 0;
    v113 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0;
  }
  else
  {
    v113 = 0;
    v108 = PerfpDosError(v112);
  }
  v114 = g_SizeSD;
  if ( g_SizeSD )
  {
    MutexAttributes.bInheritHandle = 0;
    goto LABEL_235;
  }
  SD = PerflibCreateSD(v108);
  MutexAttributes.bInheritHandle = 0;
  if ( SD )
  {
    v114 = g_SizeSD;
LABEL_235:
    MutexAttributes.nLength = v114;
    v116 = (__int64 *)&g_RuntimeSD;
    goto LABEL_236;
  }
  MutexAttributes.nLength = 92;
  v116 = qword_180023FF0;
LABEL_236:
  MutexAttributes.lpSecurityDescriptor = v116;
  *((_QWORD *)v11 + 1) = CreateMutexW(&MutexAttributes, 0, Name);
  if ( v113 && NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u) < 0 )
    GetLastError();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  *((_DWORD *)v11 + 120) = *(_DWORD *)v144;
  v11[524] = 1;
  if ( *((_QWORD *)v11 + 1) && GetLastError() == 183 )
    LastError = 0;
  else
    LastError = GetLastError();
  if ( !*((_QWORD *)v11 + 1) )
  {
    if ( LastError )
      goto LABEL_261;
    LastError = 14;
  }
LABEL_248:
  if ( !LastError )
  {
LABEL_249:
    v117 = (char *)lpPerflibSectionAddr;
    if ( lpPerflibSectionAddr )
    {
      if ( *(_DWORD *)lpPerflibSectionAddr >= *((_DWORD *)lpPerflibSectionAddr + 1) )
      {
        ++*((_DWORD *)lpPerflibSectionAddr + 2);
        *((_QWORD *)v11 + 54) = 0;
      }
      else
      {
        v118 = *(_DWORD *)lpPerflibSectionAddr + 1;
        *(_DWORD *)lpPerflibSectionAddr = v118;
        v119 = (const unsigned __int16 *)*((_QWORD *)v11 + 49);
        v120 = (unsigned __int16 *)&v117[128 * (unsigned __int64)v118];
        *((_QWORD *)v11 + 54) = v120;
        StringCchCopyW(v120, 0x20u, v119);
      }
    }
    goto LABEL_269;
  }
LABEL_261:
  v4 = v131;
LABEL_262:
  SetLastError(LastError);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
      (_DWORD)Buffer,
      v4);
  if ( v4 )
    DisableLibrary(v5, Buffer, 1u);
  if ( v11 )
  {
    operator delete(v11);
    v11 = 0;
  }
LABEL_269:
  if ( v12 )
    operator delete((void *)v12);
  if ( v11 )
  {
    *((_QWORD *)v11 + 62) = v11 + 488;
    *((_QWORD *)v11 + 61) = v11 + 488;
  }
  operator delete(v157);
  return (struct EXT_OBJECT *)v11;
}

```

## disassembly

```asm
0x18000e1a8  mov     [rsp-8+arg_18], rbx
0x18000e1ad  push    rbp
0x18000e1ae  push    rsi
0x18000e1af  push    rdi
0x18000e1b0  push    r12
0x18000e1b2  push    r13
0x18000e1b4  push    r14
0x18000e1b6  push    r15
0x18000e1b8  lea     rbp, [rsp-5F0h]
0x18000e1c0  sub     rsp, 6F0h
0x18000e1c7  mov     rax, cs:__security_cookie
0x18000e1ce  xor     rax, rsp
0x18000e1d1  mov     [rbp+620h+var_40], rax
0x18000e1d8  mov     r12, [r8+8]
0x18000e1dc  xor     esi, esi
0x18000e1de  xorps   xmm0, xmm0
0x18000e1e1  mov     [rbp+620h+phkResult], rsi
0x18000e1e5  mov     dword ptr [rbp+620h+var_690], esi
0x18000e1e8  mov     r14, rdx
0x18000e1eb  mov     dword ptr [rsp+720h+var_6A8], esi
0x18000e1ef  mov     dword ptr [rsp+720h+var_6A4], esi
0x18000e1f3  mov     dword ptr [rbp+620h+var_68C], esi
0x18000e1f6  movups  xmmword ptr [rbp+620h+var_610], xmm0
0x18000e1fa  mov     qword ptr [rbp+620h+var_670], rsi
0x18000e1fe  mov     dword ptr [rsp+720h+var_6B0], esi
0x18000e202  mov     dword ptr [rsp+720h+var_6AC], esi
0x18000e206  mov     [rbp+620h+var_678], rsi
0x18000e20a  mov     [rbp+620h+var_698], rsi
0x18000e20e  mov     [rsp+720h+var_6C8], rsi
0x18000e213  mov     [rsp+720h+var_6C0], r12
0x18000e218  mov     [rbp+620h+ThreadInformation], r8
0x18000e21c  mov     [rsp+720h+KeyHandle], rdx
0x18000e221  mov     [rbp+620h+hKey], rcx
0x18000e225  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e22c  lea     edi, [rsi+4]
0x18000e22f  lea     r13, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18000e236  test    [rcx+1Ch], dil
0x18000e23a  jz      short loc_18000E254
0x18000e23c  cmp     [rcx+19h], dil
0x18000e240  jb      short loc_18000E254
0x18000e242  mov     rcx, [rcx+10h]
0x18000e246  lea     edx, [rsi+0Ah]
0x18000e249  mov     r9, r12
0x18000e24c  mov     r8, r13
0x18000e24f  call    WPP_SF_S
0x18000e254  mov     rbx, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18000e25b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e25f  mov     [rbp+620h+var_630], rsi
0x18000e263  jmp     short loc_18000E295
0x18000e265  mov     rcx, [rbx+188h]; lpString1
0x18000e26c  mov     r9d, eax; cchCount2
0x18000e26f  mov     r8, r12; lpString2
0x18000e272  mov     [rsp+720h+bIgnoreCase], 1; bIgnoreCase
0x18000e27a  mov     edx, eax; cchCount1
0x18000e27c  call    cs:__imp_CompareStringOrdinal
0x18000e282  cmp     eax, 2
0x18000e285  jz      short loc_18000E2A0
0x18000e287  mov     [rbp+620h+var_630], rbx
0x18000e28b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e292  mov     rbx, [rbx]
0x18000e295  mov     [rbp+620h+Block], rbx
0x18000e299  test    rbx, rbx
0x18000e29c  jnz     short loc_18000E265
0x18000e29e  jmp     short loc_18000E2C4
0x18000e2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2a7  test    [rcx+1Ch], dil
0x18000e2ab  jz      short loc_18000E2C4
0x18000e2ad  cmp     [rcx+19h], dil
0x18000e2b1  jb      short loc_18000E2C4
0x18000e2b3  mov     rcx, [rcx+10h]
0x18000e2b7  mov     edx, 0Bh
0x18000e2bc  mov     r8, r13
0x18000e2bf  call    WPP_SF_
0x18000e2c4  mov     ebx, 1708h
0x18000e2c9  mov     ecx, ebx
0x18000e2cb  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000e2d0  mov     [rbp+620h+var_618], rax
0x18000e2d4  mov     r15, rax
0x18000e2d7  test    rax, rax
0x18000e2da  jnz     short loc_18000E308
0x18000e2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2e3  test    [rcx+1Ch], dil
0x18000e2e7  jz      short loc_18000E301
0x18000e2e9  cmp     byte ptr [rcx+19h], 2
0x18000e2ed  jb      short loc_18000E301
0x18000e2ef  mov     rcx, [rcx+10h]
0x18000e2f3  lea     edx, [rax+0Ch]
0x18000e2f6  mov     r9d, ebx
0x18000e2f9  mov     r8, r13
0x18000e2fc  call    WPP_SF_d
0x18000e301  xor     eax, eax
0x18000e303  jmp     loc_18000F60F
0x18000e308  xor     eax, eax
0x18000e30a  mov     [rsp+720h+var_6F0], 1; int
0x18000e312  mov     [rsp+720h+var_6E0], eax
0x18000e316  lea     r9, [rsp+720h+var_6E0]; unsigned int *
0x18000e31b  mov     qword ptr [rbp+620h+var_670], rax
0x18000e31f  lea     rdx, ?DLLValue@@3QBGB; "Library"
0x18000e326  mov     eax, cs:?dwExtCtrOpenProcWaitMs@@3KA; ulong dwExtCtrOpenProcWaitMs
0x18000e32c  xorps   xmm0, xmm0
0x18000e32f  mov     dword ptr [rsp+720h+var_6AC], eax
0x18000e333  mov     rcx, r14; KeyHandle
0x18000e336  mov     dword ptr [rsp+720h+var_6B0], eax
0x18000e33a  mov     rdi, rsi
0x18000e33d  lea     rax, [rsp+720h+var_6DC]
0x18000e342  mov     [rsp+720h+var_6D8], esi
0x18000e346  mov     [rsp+720h+var_6F8], rax; unsigned int *
0x18000e34b  mov     r13, rsi
0x18000e34e  mov     qword ptr [rsp+720h+bIgnoreCase], r15; unsigned __int8 *
0x18000e353  movups  xmmword ptr [rbp+620h+var_610], xmm0
0x18000e357  mov     dword ptr [rbp+620h+var_68C], 3E8h
0x18000e35e  mov     [rsp+720h+var_6DC], 430h
0x18000e366  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18000e36b  mov     ebx, eax
0x18000e36d  xor     eax, eax
0x18000e36f  test    ebx, ebx
0x18000e371  jnz     loc_18000F54B
0x18000e377  mov     edx, [rsp+720h+var_6DC]
0x18000e37b  mov     r12d, 210h
0x18000e381  mov     ecx, edx
0x18000e383  shr     rcx, 1
0x18000e386  lea     ebx, [rdx+8]
0x18000e389  mov     [r15+rcx*2], ax
0x18000e38e  mov     eax, 0FFFFFFF8h
0x18000e393  and     rbx, rax
0x18000e396  cmp     [rsp+720h+var_6E0], 2
0x18000e39b  lea     rsi, [rbx+r15]
0x18000e39f  mov     [rbp+620h+lpString2], rsi
0x18000e3a3  jnz     loc_18000E490
0x18000e3a9  lea     r8d, [r12+8]; nSize
0x18000e3ae  mov     rdx, rsi; lpDst
0x18000e3b1  mov     rcx, r15; lpSrc
0x18000e3b4  call    cs:__imp_ExpandEnvironmentStringsW
0x18000e3ba  lea     ecx, [rax-1]
0x18000e3bd  cmp     ecx, 217h
0x18000e3c3  ja      short loc_18000E3E4
0x18000e3c5  lea     eax, ds:9[rax*2]
0x18000e3cc  mov     ecx, 0FFFFFFF8h
0x18000e3d1  and     rax, rcx
0x18000e3d4  add     rsi, rax
0x18000e3d7  lea     r12, [rax+210h]
0x18000e3de  mov     [rbp+620h+var_660], rsi
0x18000e3e2  jmp     short loc_18000E404
0x18000e3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3eb  mov     ebx, 482h
0x18000e3f0  mov     eax, 8
0x18000e3f5  add     rsi, rax
0x18000e3f8  mov     [rbp+620h+var_660], rsi
0x18000e3fc  test    ebx, ebx
0x18000e3fe  jnz     loc_18000E500
0x18000e404  lea     rax, [rsp+720h+var_6DC]
0x18000e409  mov     [rsp+720h+var_6F0], edi; int
0x18000e40d  mov     [rsp+720h+var_6F8], rax; unsigned int *
0x18000e412  lea     r9, [rsp+720h+var_6E0]; unsigned int *
0x18000e417  lea     rdx, ?OpenValue@@3QBGB; "Open"
0x18000e41e  mov     qword ptr [rsp+720h+bIgnoreCase], rsi; unsigned __int8 *
0x18000e423  mov     rcx, r14; KeyHandle
0x18000e426  mov     [rsp+720h+var_6DC], 218h
0x18000e42e  mov     r15, rsi
0x18000e431  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18000e436  xor     ecx, ecx
0x18000e438  mov     ebx, eax
0x18000e43a  test    eax, eax
0x18000e43c  jnz     loc_18000E5D5
0x18000e442  cmp     [rsi], cl
0x18000e444  jz      loc_18000E5CC
0x18000e44a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e451  lea     eax, [rbx+4]
0x18000e454  test    [rcx+1Ch], al
0x18000e457  jz      short loc_18000E477
0x18000e459  cmp     [rcx+19h], al
0x18000e45c  jb      short loc_18000E477
0x18000e45e  mov     r9, [rsp+720h+var_6C0]
0x18000e463  lea     edx, [rbx+10h]
0x18000e466  mov     rcx, [rcx+10h]
0x18000e46a  mov     qword ptr [rsp+720h+bIgnoreCase], r9
0x18000e46f  mov     r9, rsi
0x18000e472  call    WPP_SF_sS
0x18000e477  mov     eax, [rsp+720h+var_6DC]
0x18000e47b  mov     ecx, 0FFFFFFF8h
0x18000e480  lea     r14d, [rax+8]
0x18000e484  mov     [rax+rsi], dil
0x18000e488  and     r14, rcx
0x18000e48b  jmp     loc_18000E691
0x18000e490  cmp     [rsp+720h+var_6E0], 1
0x18000e495  jnz     short loc_18000E4B4
0x18000e497  mov     r8, rbx; Size
0x18000e49a  mov     rdx, r15; Src
0x18000e49d  mov     rcx, rsi; void *
0x18000e4a0  call    memcpy_0
0x18000e4a5  add     rsi, rbx
0x18000e4a8  lea     r12, [rbx+210h]
0x18000e4af  jmp     loc_18000E3DE
0x18000e4b4  mov     ebx, 482h
0x18000e4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4c0  test    byte ptr [rcx+1Ch], 4
0x18000e4c4  jz      loc_18000E3F0
0x18000e4ca  cmp     byte ptr [rcx+19h], 2
0x18000e4ce  jb      loc_18000E3F0
0x18000e4d4  mov     rcx, [rcx+10h]
0x18000e4d8  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18000e4df  mov     edx, 0Dh
0x18000e4e4  mov     r9d, ebx
0x18000e4e7  call    WPP_SF_d
0x18000e4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4f3  add     rsi, 8
0x18000e4f7  mov     [rbp+620h+var_660], rsi
0x18000e4fb  mov     eax, 8
0x18000e500  test    byte ptr [rcx+1Ch], 4
0x18000e504  mov     r14, rax
0x18000e507  jz      short loc_18000E529
0x18000e509  cmp     byte ptr [rcx+19h], 2
0x18000e50d  jb      short loc_18000E529
0x18000e50f  mov     r9, [rsp+720h+var_6C0]
0x18000e514  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18000e51b  mov     rcx, [rcx+10h]
0x18000e51f  mov     edx, 11h
0x18000e524  call    WPP_SF_S
0x18000e529  add     rsi, r14
0x18000e52c  mov     r14d, 8
0x18000e532  mov     [rbp+620h+TokenHandle], rsi
0x18000e536  test    ebx, ebx
0x18000e538  jnz     loc_18000F578
0x18000e53e  mov     rcx, [rsp+720h+KeyHandle]; KeyHandle
0x18000e543  lea     rax, [rsp+720h+var_6DC]
0x18000e548  mov     [rsp+720h+var_6F0], edi; int
0x18000e54c  lea     r9, [rsp+720h+var_6E0]; unsigned int *
0x18000e551  mov     [rsp+720h+var_6F8], rax; unsigned int *
0x18000e556  lea     rdx, ?CloseValue@@3QBGB; "Close"
0x18000e55d  mov     qword ptr [rsp+720h+bIgnoreCase], rsi; unsigned __int8 *
0x18000e562  mov     r15, rsi
0x18000e565  mov     [rsp+720h+var_6DC], 218h
0x18000e56d  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18000e572  xor     ecx, ecx
0x18000e574  mov     ebx, eax
0x18000e576  test    eax, eax
0x18000e578  jnz     loc_18000E70B
0x18000e57e  cmp     [rsi], cl
0x18000e580  jz      loc_18000E700
0x18000e586  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e58d  lea     eax, [rbx+4]
0x18000e590  test    [rcx+1Ch], al
0x18000e593  jz      short loc_18000E5B3
0x18000e595  cmp     [rcx+19h], al
0x18000e598  jb      short loc_18000E5B3
0x18000e59a  mov     rax, [rsp+720h+var_6C0]
0x18000e59f  lea     edx, [rbx+14h]
0x18000e5a2  mov     rcx, [rcx+10h]
0x18000e5a6  mov     r9, rsi
0x18000e5a9  mov     qword ptr [rsp+720h+bIgnoreCase], rax
0x18000e5ae  call    WPP_SF_sS
0x18000e5b3  mov     r14d, [rsp+720h+var_6DC]
0x18000e5b8  mov     eax, 0FFFFFFF8h
0x18000e5bd  add     r14d, 8
0x18000e5c1  and     r14, rax
0x18000e5c4  add     r15, r14
0x18000e5c7  jmp     loc_18000E7C0
0x18000e5cc  mov     ebx, 1
0x18000e5d1  mov     eax, ebx
0x18000e5d3  jmp     short loc_18000E5EA
0x18000e5d5  cmp     eax, 2
0x18000e5d8  jz      short loc_18000E5E1
0x18000e5da  cmp     eax, 0EAh
0x18000e5df  jnz     short loc_18000E5E8
0x18000e5e1  mov     eax, 1
0x18000e5e6  jmp     short loc_18000E5EA
0x18000e5e8  mov     eax, ecx
0x18000e5ea  mov     r14, [rsp+720h+var_6C0]
0x18000e5ef  mov     [rsp+720h+var_6D8], eax
0x18000e5f3  test    r14, r14
0x18000e5f6  jz      short loc_18000E629
0x18000e5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5ff  test    byte ptr [rcx+1Ch], 4
0x18000e603  jz      short loc_18000E654
0x18000e605  cmp     byte ptr [rcx+19h], 2
0x18000e609  jb      short loc_18000E654
0x18000e60b  mov     rcx, [rcx+10h]
0x18000e60f  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18000e616  mov     edx, 0Eh
0x18000e61b  mov     [rsp+720h+bIgnoreCase], ebx
0x18000e61f  mov     r9, r14
0x18000e622  call    WPP_SF_Sd
0x18000e627  jmp     short loc_18000E654
0x18000e629  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e630  test    byte ptr [rcx+1Ch], 4
0x18000e634  jz      short loc_18000E654
0x18000e636  cmp     byte ptr [rcx+19h], 2
0x18000e63a  jb      short loc_18000E654
0x18000e63c  mov     rcx, [rcx+10h]
0x18000e640  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18000e647  mov     edx, 0Fh
0x18000e64c  mov     r9d, ebx
0x18000e64f  call    WPP_SF_d
0x18000e654  lea     r8, ?PerfpErrorLog@@3UERROR_LOG@@A; struct ERROR_LOG *
0x18000e65b  xor     edx, edx; HKEY
0x18000e65d  mov     ecx, 0BBBh; unsigned int
0x18000e662  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18000e667  test    eax, eax
0x18000e669  jz      short loc_18000E683
0x18000e66b  test    cs:Microsoft_Windows_PerflibEnableBits, 2
  ... truncated ...
```
