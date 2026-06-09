# StartTraceW

- ea: `0x18000cca0`
- end: `0x18000d5bc`
- name: `StartTraceW`
- size: `2332`
- prototype: `ULONG __stdcall(PTRACEHANDLE TraceHandle, LPCWSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, loader_planting`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001e82`
- `0x180001eb2`
- `0x180001ff0`
- `0x180002014`
- `0x180002020`
- `0x180002ec4`
- `0x180006180`
- `0x180008c58`
- `0x180008e3c`
- `0x180008f30`
- `0x180009228`
- `0x1800097e0`
- `0x1800098ec`
- `0x18000cca0`
- `0x180013138`
- `0x1800131ec`
- `0x1800137e4`
- `0x18001581c`
- `0x180015834`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000d145`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000d145`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d12e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000d12e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d117`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000d117`
- `ntdll!RtlSetLastWin32Error` at `0x18000ce30`
- `ntdll!RtlSetLastWin32Error` at `0x18000cf0c`
- `ntdll!RtlSetLastWin32Error` at `0x18000d066`
- `ntdll!RtlSetLastWin32Error` at `0x18000d54d`
- `ntdll!RtlSetLastWin32Error` at `0x18000d567`
- `ntdll!RtlSetLastWin32Error` at `0x18000ce30`
- `ntdll!RtlSetLastWin32Error` at `0x18000cf0c`
- `ntdll!RtlSetLastWin32Error` at `0x18000d066`
- `ntdll!RtlSetLastWin32Error` at `0x18000d54d`
- `ntdll!RtlSetLastWin32Error` at `0x18000d567`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cd1f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cd1f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000d015`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000d015`

## pseudocode

```c
ULONG __stdcall StartTraceW(PTRACEHANDLE TraceHandle, LPCWSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)
{
  const wchar_t *v3; // rsi
  __int64 v6; // r15
  LPCWSTR v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // eax
  ULONG v11; // ebx
  __int64 v12; // rax
  __int64 v13; // r13
  ULONG v14; // r14d
  bool v15; // zf
  __int64 v16; // rax
  DWORD i; // ebx
  unsigned __int64 v18; // r14
  WCHAR *v19; // rax
  DWORD FullPathNameW; // eax
  DWORD v21; // r14d
  _BOOL8 v22; // rcx
  __int64 v23; // rdx
  char *v24; // rbx
  __int64 v25; // rax
  wchar_t *v26; // rax
  int v27; // edx
  ULONG v28; // r8d
  unsigned int v29; // ecx
  int v30; // eax
  char *v31; // rax
  unsigned int v32; // r14d
  unsigned __int64 v33; // rdx
  __int16 v34; // ax
  int v35; // r11d
  __int16 v36; // ax
  int v37; // r11d
  int v38; // r11d
  unsigned __int16 *v39; // rcx
  unsigned int v40; // r11d
  ULONG v41; // eax
  ULONG LogFileNameOffset; // ecx
  unsigned int v43; // ecx
  __int64 v44; // rax
  __int64 v45; // r8
  unsigned __int64 v46; // rdx
  __int64 v47; // rcx
  _WORD *v48; // rax
  LPCWSTR v49; // r9
  _WORD *v50; // rcx
  __int64 v51; // rcx
  ULONG LoggerNameOffset; // eax
  unsigned int v53; // eax
  unsigned __int64 v54; // rdx
  _WORD *v55; // rax
  _WORD *v56; // rcx
  ULONG LastError; // [rsp+30h] [rbp-D0h] BYREF
  char v58; // [rsp+34h] [rbp-CCh]
  size_t v59; // [rsp+38h] [rbp-C8h] BYREF
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  int v61; // [rsp+48h] [rbp-B8h]
  unsigned int v62; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t *v63; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR lpBuffer; // [rsp+58h] [rbp-A8h]
  PTRACEHANDLE v65; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v66[3]; // [rsp+68h] [rbp-98h] BYREF
  char v67; // [rsp+80h] [rbp-80h]
  unsigned __int64 v68; // [rsp+88h] [rbp-78h]
  __int64 v69; // [rsp+90h] [rbp-70h]
  struct _EVENT_FILTER_DESCRIPTOR *v70; // [rsp+98h] [rbp-68h] BYREF
  int v71; // [rsp+A0h] [rbp-60h] BYREF
  char v72; // [rsp+A4h] [rbp-5Ch]
  GUID ActivityId; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v74[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t **v75; // [rsp+F0h] [rbp-10h]
  __int64 v76; // [rsp+F8h] [rbp-8h]
  LPCWSTR v77; // [rsp+100h] [rbp+0h]
  int v78; // [rsp+108h] [rbp+8h]
  int v79; // [rsp+10Ch] [rbp+Ch]

  v3 = 0;
  v65 = TraceHandle;
  LastError = 0;
  LODWORD(v59) = 0;
  v62 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v6 = -1;
  v71 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    if ( InstanceName )
    {
      v7 = InstanceName;
      v8 = -1;
      do
        ++v8;
      while ( InstanceName[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v7 = (LPCWSTR)&qword_180017B18;
      v9 = 2;
    }
    v76 = v9;
    v75 = (wchar_t **)v7;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)byte_180019295,
      (__int64)&ActivityId,
      0,
      3,
      (__int64)v74);
  }
  v67 = 1;
  v66[0] = &v71;
  v66[1] = &LastError;
  v66[2] = &v65;
  if ( !Properties || !v65 )
  {
    v11 = 87;
    LastError = 87;
LABEL_134:
    RtlSetLastWin32Error(v11);
    if ( v67 )
      lambda_f978de3a668969ac683e101937331384_::operator()(v66);
    if ( v71 != 1 )
      return v11;
    v71 = 2;
    goto LABEL_138;
  }
  if ( !InstanceName )
  {
    LastError = 123;
    RtlSetLastWin32Error(0x7Bu);
    if ( v67 )
      lambda_f978de3a668969ac683e101937331384_::operator()(v66);
    if ( v71 == 1 )
    {
      v71 = 2;
      _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
    }
    return 123;
  }
  LastError = EtwpValidateTraceProperties(Properties, &v62, &v70, (unsigned int *)&v59);
  v11 = LastError;
  if ( LastError )
    goto LABEL_134;
  v12 = -1;
  do
    ++v12;
  while ( InstanceName[v12] );
  v13 = (unsigned int)v59;
  v14 = v59 + 2 + 2 * (unsigned __int16)v12;
  if ( wcsicmp(InstanceName, L"NT Kernel Logger") )
  {
    if ( *(_QWORD *)&Properties->Wnode.Guid.Data1 == *(_QWORD *)&SystemTraceControlGuid.Data1
      && *(_QWORD *)Properties->Wnode.Guid.Data4 == *(_QWORD *)SystemTraceControlGuid.Data4 )
    {
      goto LABEL_32;
    }
  }
  else
  {
    Properties->Wnode.Guid = SystemTraceControlGuid;
  }
  if ( !wcsicmp(InstanceName, L"Circular Kernel Context Logger") )
  {
    Properties->Wnode.Guid = (GUID)CKCLGuid;
    goto LABEL_38;
  }
  if ( *(_OWORD *)&Properties->Wnode.Guid == CKCLGuid )
  {
LABEL_32:
    v11 = 87;
    LastError = 87;
    RtlSetLastWin32Error(0x57u);
    v15 = v67 == 0;
LABEL_33:
    if ( !v15 )
      lambda_f978de3a668969ac683e101937331384_::operator()(v66);
    if ( v71 != 1 )
      return v11;
    v71 = 2;
LABEL_138:
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
    return v11;
  }
LABEL_38:
  v58 = 0;
  lpBuffer = 0;
  if ( !Properties->LogFileNameOffset )
  {
    LOWORD(v6) = 0;
    LODWORD(v22) = 0;
    goto LABEL_61;
  }
  v16 = -1;
  v3 = (const wchar_t *)((char *)Properties + Properties->LogFileNameOffset);
  do
    ++v16;
  while ( v3[v16] );
  v14 += 2 * v16 + 2;
  LODWORD(v59) = v14;
  if ( !wcsncmp_0(v3, L"%SystemRoot%", 0xCu) || !wcsncmp_0(v3, L"%DriverData%", 0xCu) )
  {
    v58 = 1;
    do
LABEL_52:
      ++v6;
    while ( v3[v6] );
    v22 = (_WORD)v6 != 0;
LABEL_61:
    v23 = -1;
    v61 = v22;
    v24 = 0;
    if ( Properties->Wnode.BufferSize < v14 )
    {
      LastError = 24;
      goto LABEL_124;
    }
    v25 = -1;
    do
      ++v25;
    while ( InstanceName[v25] );
    v69 = v25;
    if ( !(_WORD)v25 )
    {
      LastError = 123;
      goto LABEL_124;
    }
    LastError = EtwpValidateLogFileMode(Properties, v22);
    if ( !LastError )
    {
      if ( (Properties->LogFileMode & 8) != 0 )
      {
        v63 = wcschr(v3, 0x25u);
        if ( !v63 || (v26 = wcsrchr(v3, 0x25u), v63 != v26) || !wcsstr(v3, L"%d") )
        {
          LastError = 123;
LABEL_73:
          v23 = -1;
          goto LABEL_124;
        }
      }
      LODWORD(v63) = (unsigned __int16)v6;
      LODWORD(v68) = (unsigned __int16)v69 + 1;
      LODWORD(Size) = 2 * ((unsigned __int16)v6 + 1 + v68) + 176;
      LastError = EtwpCheckFlagExtensions(Properties, (unsigned int *)&Size);
      if ( !LastError )
      {
        v15 = (Properties->LogFileMode & 0x10000) == 0;
        v27 = 0;
        LODWORD(v59) = 0;
        if ( v15 )
        {
          v30 = Size;
        }
        else if ( (Properties->LogFileMode & 0x1000) != 0 )
        {
          v28 = v13;
          if ( (unsigned int)v13 < Properties->LogFileNameOffset )
          {
            do
            {
              v29 = (*(unsigned __int16 *)((char *)&Properties->Wnode.ProviderId + v28) + 7) & 0xFFFFFFF8;
              v27 += v29;
              v28 += v29;
            }
            while ( v28 < Properties->LogFileNameOffset );
            LODWORD(v59) = v27;
          }
          v30 = v27 + Size;
        }
        else
        {
          LODWORD(v59) = *(unsigned __int16 *)((char *)&Properties->Wnode.ProviderId + v13);
          v30 = v59 + ((Size + 7) & 0xFFFFFFF8);
        }
        Size = (v30 + 7) & 0xFFFFFFF8;
        v31 = (char *)operator new(Size, (const struct std::nothrow_t *)&std::nothrow);
        v24 = v31;
        if ( !v31 )
        {
          LastError = 8;
          goto LABEL_73;
        }
        v32 = Size;
        memset_0(v31, 0, Size);
        *v65 = 0;
        EtwpCopyPropertiesToInfo(Properties, (struct _WMI_LOGGER_INFORMATION *)v24);
        v33 = (unsigned int)v68;
        v34 = v68;
        *((_DWORD *)v24 + 26) = Properties->Wnode.ProviderId;
        *((_DWORD *)v24 + 1) = v35;
        *((_WORD *)v24 + 73) = 2 * v34;
        v36 = 2 * v69;
        *((_QWORD *)v24 + 19) = v24 + 176;
        *((_WORD *)v24 + 72) = v36;
        StringCchCopyW((unsigned __int16 *)v24 + 88, v33, InstanceName);
        if ( v61 == v37
          || (v38 = (int)v63,
              v39 = (unsigned __int16 *)&v24[*((unsigned __int16 *)v24 + 73) + 176],
              *((_WORD *)v24 + 64) = 2 * v6,
              *((_QWORD *)v24 + 17) = v39,
              *((_WORD *)v24 + 65) = 2 * (v38 + 1),
              StringCchCopyW(v39, (unsigned int)(v38 + 1), v3),
              v58)
          || (v41 = EtwpCheckForEnoughFreeSpace(
                      *((const unsigned __int16 **)v24 + 17),
                      v40,
                      Properties->MaximumFileSize,
                      Properties->LogFileMode & 4,
                      Properties->LogFileMode & 0x2000)) == 0 )
        {
          *((_DWORD *)v24 + 11) |= 0x20000u;
          *(_DWORD *)v24 = v32;
          LastError = EtwpCopyFlagExtensions(Properties, (struct _WMI_LOGGER_INFORMATION *)v24, v32);
          if ( !LastError )
          {
            if ( (Properties->LogFileMode & 0x10000) != 0 && (_DWORD)v59 )
              memcpy_0(
                &v24[(*((unsigned __int16 *)v24 + 73) + 183LL + *((unsigned __int16 *)v24 + 65)) & 0xFFFFFFF8LL],
                (char *)Properties + v13,
                (unsigned int)v59);
            LastError = EtwpStartLogger((struct _WMI_LOGGER_INFORMATION *)v24, v62, v70);
            if ( !LastError )
            {
              EtwpCopyInfoToProperties((struct _WMI_LOGGER_INFORMATION *)v24, Properties);
              if ( Properties->LoggerNameOffset )
                Properties->LoggerNameOffset = v13;
              else
                LODWORD(v13) = Properties->LoggerNameOffset;
              LogFileNameOffset = Properties->LogFileNameOffset;
              if ( (unsigned int)v13 > LogFileNameOffset )
                LogFileNameOffset = Properties->Wnode.BufferSize;
              v43 = LogFileNameOffset - v13;
              v44 = -1;
              do
                ++v44;
              while ( InstanceName[v44] );
              v45 = 2147483646;
              if ( 2 * (int)v44 + 2 <= v43 )
              {
                v46 = (unsigned __int64)v43 >> 1;
                if ( v46 )
                {
                  v47 = 2147483646;
                  v48 = (_WORD *)((char *)Properties + (unsigned int)v13);
                  v49 = InstanceName;
                  do
                  {
                    if ( !v47 )
                      break;
                    if ( !*v49 )
                      break;
                    *v48++ = *v49++;
                    --v47;
                    --v46;
                  }
                  while ( v46 );
                  v50 = v48 - 1;
                  if ( v46 )
                    v50 = v48;
                  *v50 = 0;
                }
              }
              *v65 = *((_QWORD *)v24 + 1);
              v51 = Properties->LogFileNameOffset;
              LoggerNameOffset = Properties->LoggerNameOffset;
              if ( (unsigned int)v51 > LoggerNameOffset )
                LoggerNameOffset = Properties->Wnode.BufferSize;
              v53 = LoggerNameOffset - v51;
              if ( *((_WORD *)v24 + 64) )
              {
                if ( *((unsigned __int16 *)v24 + 64) <= v53 )
                {
                  v54 = (unsigned __int64)v53 >> 1;
                  if ( v54 )
                  {
                    v55 = (_WORD *)((char *)Properties + v51);
                    do
                    {
                      if ( !v45 )
                        break;
                      if ( !*v3 )
                        break;
                      *v55++ = *v3++;
                      --v45;
                      --v54;
                    }
                    while ( v54 );
                    v56 = v55 - 1;
                    if ( v54 )
                      v56 = v55;
                    *v56 = 0;
                  }
                }
              }
            }
          }
        }
        else
        {
          LastError = v41;
        }
      }
    }
    if ( !LastError )
    {
LABEL_130:
      operator delete(v24);
      operator delete(lpBuffer);
      v11 = LastError;
      if ( LastError )
        RtlSetLastWin32Error(LastError);
      v15 = v67 == 0;
      goto LABEL_33;
    }
    v23 = -1;
LABEL_124:
    if ( (unsigned int)dword_18001D020 > 2 && (qword_18001D030 & 2) != 0 && (qword_18001D038 & 2) == qword_18001D038 )
    {
      LODWORD(v63) = LastError;
      do
        ++v23;
      while ( InstanceName[v23] );
      v77 = InstanceName;
      v78 = 2 * v23 + 2;
      v79 = 0;
      v75 = &v63;
      v76 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_18001D020,
        (unsigned __int8 *)qword_180019260,
        0,
        0,
        4,
        (__int64)v74);
    }
    goto LABEL_130;
  }
  for ( i = 1024; ; i = v21 )
  {
    v18 = 2LL * i;
    if ( !is_mul_ok(i, 2u) )
      v18 = -1;
    v19 = (WCHAR *)operator new(v18, (const struct std::nothrow_t *)&std::nothrow);
    lpBuffer = v19;
    if ( !v19 )
      break;
    memset_0(v19, 0, v18);
    FullPathNameW = GetFullPathNameW(v3, i, lpBuffer, 0);
    v21 = FullPathNameW;
    if ( !FullPathNameW )
      goto LABEL_51;
    if ( FullPathNameW <= i )
    {
      v3 = lpBuffer;
LABEL_51:
      v14 = v59;
      goto LABEL_52;
    }
    operator delete(lpBuffer);
  }
  LastError = 8;
  RtlSetLastWin32Error(8u);
  if ( v67 )
    lambda_f978de3a668969ac683e101937331384_::operator()(v66);
  if ( v71 == 1 )
  {
    v71 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return 8;
}

```

## disassembly

```asm
0x18000cca0  mov     [rsp-8+arg_18], rbx
0x18000cca5  push    rbp
0x18000cca6  push    rsi
0x18000cca7  push    rdi
0x18000cca8  push    r12
0x18000ccaa  push    r13
0x18000ccac  push    r14
0x18000ccae  push    r15
0x18000ccb0  lea     rbp, [rsp-20h]
0x18000ccb5  sub     rsp, 120h
0x18000ccbc  mov     rax, cs:__security_cookie
0x18000ccc3  xor     rax, rsp
0x18000ccc6  mov     [rbp+50h+var_40], rax
0x18000ccca  mov     eax, cs:dword_18001D020
0x18000ccd0  xor     esi, esi
0x18000ccd2  mov     [rsp+150h+var_F0], rcx
0x18000ccd7  mov     rdi, r8
0x18000ccda  mov     [rsp+150h+LastError], esi
0x18000ccde  mov     r12, rdx
0x18000cce1  mov     dword ptr [rsp+150h+var_118], esi
0x18000cce5  mov     [rsp+150h+var_104], esi
0x18000cce9  lea     ebx, [rsi+3]
0x18000ccec  mov     [rbp+50h+var_B8], rsi
0x18000ccf0  mov     [rbp+50h+var_B0], esi
0x18000ccf3  mov     [rbp+50h+var_AC], sil
0x18000ccf7  cmp     eax, 5
0x18000ccfa  jbe     short loc_18000CD27
0x18000ccfc  mov     rcx, cs:qword_18001D038
0x18000cd03  mov     rax, cs:qword_18001D030
0x18000cd0a  test    al, 10h
0x18000cd0c  jz      short loc_18000CD27
0x18000cd0e  mov     rax, rcx
0x18000cd11  and     eax, 10h
0x18000cd14  cmp     rax, rcx
0x18000cd17  jnz     short loc_18000CD27
0x18000cd19  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x18000cd1d  mov     ecx, ebx; ControlCode
0x18000cd1f  call    cs:__imp_EventActivityIdControl
0x18000cd25  jmp     short loc_18000CD2E
0x18000cd27  xorps   xmm0, xmm0
0x18000cd2a  movups  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x18000cd2e  mov     eax, cs:dword_18001D020
0x18000cd34  lea     r13, dword_18001D020
0x18000cd3b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000cd3f  mov     [rbp+50h+var_B0], 1
0x18000cd46  lea     r14d, [r15+3]
0x18000cd4a  cmp     eax, 5
0x18000cd4d  jbe     loc_18000CDE9
0x18000cd53  mov     rcx, cs:qword_18001D038
0x18000cd5a  mov     rax, cs:qword_18001D030
0x18000cd61  test    al, 10h
0x18000cd63  jz      loc_18000CDE9
0x18000cd69  mov     rax, rcx
0x18000cd6c  and     eax, 10h
0x18000cd6f  cmp     rax, rcx
0x18000cd72  jnz     short loc_18000CDE9
0x18000cd74  cmp     [rbp+50h+var_AC], sil
0x18000cd78  jz      short loc_18000CD94
0x18000cd7a  cmp     [rbp+50h+var_98], esi
0x18000cd7d  jnz     short loc_18000CD8E
0x18000cd7f  cmp     [rbp+50h+var_94], esi
0x18000cd82  jnz     short loc_18000CD8E
0x18000cd84  cmp     [rbp+50h+var_90], esi
0x18000cd87  jnz     short loc_18000CD8E
0x18000cd89  cmp     [rbp+50h+var_8C], esi
0x18000cd8c  jz      short loc_18000CD94
0x18000cd8e  lea     r9, [rbp+50h+var_98]
0x18000cd92  jmp     short loc_18000CD97
0x18000cd94  mov     r9, rsi
0x18000cd97  test    r12, r12
0x18000cd9a  jz      short loc_18000CDB5
0x18000cd9c  mov     rcx, r12
0x18000cd9f  mov     rax, r15
0x18000cda2  inc     rax
0x18000cda5  cmp     [r12+rax*2], si
0x18000cdaa  jnz     short loc_18000CDA2
0x18000cdac  lea     eax, ds:2[rax*2]
0x18000cdb3  jmp     short loc_18000CDBF
0x18000cdb5  lea     rcx, qword_180017B18
0x18000cdbc  mov     eax, r14d
0x18000cdbf  mov     dword ptr [rbp+50h+var_58], eax
0x18000cdc2  lea     r8, [rbp+50h+ActivityId]
0x18000cdc6  lea     rax, [rbp+50h+var_80]
0x18000cdca  mov     [rbp+50h+var_60], rcx
0x18000cdce  mov     [rsp+150h+var_128], rax
0x18000cdd3  lea     rdx, byte_180019295
0x18000cdda  mov     rcx, r13
0x18000cddd  mov     [rsp+150h+var_130], ebx
0x18000cde1  mov     dword ptr [rbp+50h+var_58+4], esi
0x18000cde4  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000cde9  mov     [rbp+50h+var_D0], 1
0x18000cded  lea     rax, [rbp+50h+var_B0]
0x18000cdf1  mov     [rsp+150h+var_E8], rax
0x18000cdf6  lea     rax, [rsp+150h+LastError]
0x18000cdfb  mov     [rsp+150h+var_E0], rax
0x18000ce00  lea     rax, [rsp+150h+var_F0]
0x18000ce05  mov     [rsp+150h+var_D8], rax
0x18000ce0a  test    rdi, rdi
0x18000ce0d  jz      loc_18000D55C
0x18000ce13  cmp     [rsp+150h+var_F0], rsi
0x18000ce18  jz      loc_18000D55C
0x18000ce1e  test    r12, r12
0x18000ce21  jnz     short loc_18000CE66
0x18000ce23  lea     ecx, [r12+7Bh]; LastError
0x18000ce28  mov     [rsp+150h+LastError], 7Bh ; '{'
0x18000ce30  call    cs:__imp_RtlSetLastWin32Error
0x18000ce36  cmp     [rbp+50h+var_D0], sil
0x18000ce3a  jz      short loc_18000CE46
0x18000ce3c  lea     rcx, [rsp+150h+var_E8]
0x18000ce41  call    _lambda_f978de3a668969ac683e101937331384___operator__
0x18000ce46  cmp     [rbp+50h+var_B0], 1
0x18000ce4a  jnz     short loc_18000CE5C
0x18000ce4c  lea     rdx, [rbp+50h+ActivityId]
0x18000ce50  mov     [rbp+50h+var_B0], r14d
0x18000ce54  mov     rcx, r13
0x18000ce57  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000ce5c  mov     eax, 7Bh ; '{'
0x18000ce61  jmp     loc_18000D595
0x18000ce66  lea     r9, [rsp+150h+var_118]; unsigned int *
0x18000ce6b  mov     rcx, rdi; struct _EVENT_TRACE_PROPERTIES *
0x18000ce6e  lea     r8, [rbp+50h+var_B8]; struct _EVENT_FILTER_DESCRIPTOR **
0x18000ce72  lea     rdx, [rsp+150h+var_104]; unsigned int *
0x18000ce77  call    ?EtwpValidateTraceProperties@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAKPEAPEAU_EVENT_FILTER_DESCRIPTOR@@1@Z; EtwpValidateTraceProperties(_EVENT_TRACE_PROPERTIES *,ulong *,_EVENT_FILTER_DESCRIPTOR * *,ulong *)
0x18000ce7c  mov     [rsp+150h+LastError], eax
0x18000ce80  mov     ebx, eax
0x18000ce82  test    eax, eax
0x18000ce84  jnz     loc_18000D565
0x18000ce8a  mov     rax, r15
0x18000ce8d  inc     rax
0x18000ce90  cmp     [r12+rax*2], si
0x18000ce95  jnz     short loc_18000CE8D
0x18000ce97  mov     r13d, dword ptr [rsp+150h+var_118]
0x18000ce9c  lea     rdx, aNtKernelLogger_0; "NT Kernel Logger"
0x18000cea3  movzx   eax, ax
0x18000cea6  mov     rcx, r12; String1
0x18000cea9  lea     r14d, [r13+2]
0x18000cead  lea     r14d, [r14+rax*2]
0x18000ceb1  call    _wcsicmp
0x18000ceb6  test    eax, eax
0x18000ceb8  jnz     short loc_18000CEE7
0x18000ceba  movups  xmm0, xmmword ptr cs:SystemTraceControlGuid.Data1
0x18000cec1  movdqu  xmmword ptr [rdi+18h], xmm0
0x18000cec6  lea     rdx, aCircularKernel_0; "Circular Kernel Context Logger"
0x18000cecd  mov     rcx, r12; String1
0x18000ced0  call    _wcsicmp
0x18000ced5  test    eax, eax
0x18000ced7  jnz     short loc_18000CF3F
0x18000ced9  movups  xmm0, cs:CKCLGuid
0x18000cee0  movdqu  xmmword ptr [rdi+18h], xmm0
0x18000cee5  jmp     short loc_18000CF59
0x18000cee7  mov     rax, [rdi+18h]
0x18000ceeb  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x18000cef2  jnz     short loc_18000CEC6
0x18000cef4  mov     rax, [rdi+20h]
0x18000cef8  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x18000ceff  jnz     short loc_18000CEC6
0x18000cf01  mov     ebx, 57h ; 'W'
0x18000cf06  mov     ecx, ebx; LastError
0x18000cf08  mov     [rsp+150h+LastError], ebx
0x18000cf0c  call    cs:__imp_RtlSetLastWin32Error
0x18000cf12  cmp     [rbp+50h+var_D0], sil
0x18000cf16  jz      short loc_18000CF22
0x18000cf18  lea     rcx, [rsp+150h+var_E8]
0x18000cf1d  call    _lambda_f978de3a668969ac683e101937331384___operator__
0x18000cf22  cmp     [rbp+50h+var_B0], 1
0x18000cf26  jnz     loc_18000D593
0x18000cf2c  mov     [rbp+50h+var_B0], 2
0x18000cf33  lea     rcx, dword_18001D020
0x18000cf3a  jmp     loc_18000D58A
0x18000cf3f  mov     rax, [rdi+18h]
0x18000cf43  cmp     rax, qword ptr cs:CKCLGuid
0x18000cf4a  jnz     short loc_18000CF59
0x18000cf4c  mov     rax, [rdi+20h]
0x18000cf50  cmp     rax, qword ptr cs:CKCLGuid+8
0x18000cf57  jz      short loc_18000CF01
0x18000cf59  mov     [rsp+150h+var_11C], sil
0x18000cf5e  mov     [rsp+150h+lpBuffer], rsi
0x18000cf63  cmp     [rdi+70h], esi
0x18000cf66  jbe     loc_18000D0A8
0x18000cf6c  mov     esi, [rdi+70h]
0x18000cf6f  mov     rax, r15
0x18000cf72  add     rsi, rdi
0x18000cf75  xor     ecx, ecx
0x18000cf77  inc     rax
0x18000cf7a  cmp     [rsi+rax*2], cx
0x18000cf7e  jnz     short loc_18000CF77
0x18000cf80  lea     r14d, [r14+rax*2]
0x18000cf84  mov     ebx, 0Ch
0x18000cf89  add     r14d, 2
0x18000cf8d  lea     rdx, aSystemroot; "%SystemRoot%"
0x18000cf94  mov     r8d, ebx; MaxCount
0x18000cf97  mov     dword ptr [rsp+150h+var_118], r14d
0x18000cf9c  mov     rcx, rsi; String1
0x18000cf9f  call    wcsncmp_0
0x18000cfa4  xor     r8d, r8d
0x18000cfa7  test    eax, eax
0x18000cfa9  jz      loc_18000D0A1
0x18000cfaf  mov     r8d, ebx; MaxCount
0x18000cfb2  lea     rdx, aDriverdata_0; "%DriverData%"
0x18000cfb9  mov     rcx, rsi; String1
0x18000cfbc  call    wcsncmp_0
0x18000cfc1  xor     r8d, r8d
0x18000cfc4  test    eax, eax
0x18000cfc6  jz      loc_18000D0A1
0x18000cfcc  mov     ebx, 400h
0x18000cfd1  mov     ecx, ebx
0x18000cfd3  mov     eax, 2
0x18000cfd8  mul     rcx
0x18000cfdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cfe2  mov     r14, rax
0x18000cfe5  cmovb   r14, r15
0x18000cfe9  mov     rcx, r14; unsigned __int64
0x18000cfec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cff1  mov     [rsp+150h+lpBuffer], rax
0x18000cff6  test    rax, rax
0x18000cff9  jz      short loc_18000D058
0x18000cffb  mov     r8, r14; Size
0x18000cffe  xor     edx, edx; Val
0x18000d000  mov     rcx, rax; void *
0x18000d003  call    memset_0
0x18000d008  mov     r8, [rsp+150h+lpBuffer]; lpBuffer
0x18000d00d  xor     r9d, r9d; lpFilePart
0x18000d010  mov     edx, ebx; nBufferLength
0x18000d012  mov     rcx, rsi; lpFileName
0x18000d015  call    cs:__imp_GetFullPathNameW
0x18000d01b  xor     r8d, r8d
0x18000d01e  mov     r14d, eax
0x18000d021  test    eax, eax
0x18000d023  jz      short loc_18000D03D
0x18000d025  cmp     eax, ebx
0x18000d027  jbe     short loc_18000D038
0x18000d029  mov     rcx, [rsp+150h+lpBuffer]; Block
0x18000d02e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d033  mov     ebx, r14d
0x18000d036  jmp     short loc_18000CFD1
0x18000d038  mov     rsi, [rsp+150h+lpBuffer]
0x18000d03d  mov     r14d, dword ptr [rsp+150h+var_118]
0x18000d042  inc     r15
0x18000d045  cmp     [rsi+r15*2], r8w
0x18000d04a  jnz     short loc_18000D042
0x18000d04c  test    r15w, r15w
0x18000d050  mov     ecx, r8d
0x18000d053  setnz   cl
0x18000d056  jmp     short loc_18000D0B1
0x18000d058  mov     r14d, 8
0x18000d05e  mov     ecx, r14d; LastError
0x18000d061  mov     [rsp+150h+LastError], r14d
0x18000d066  call    cs:__imp_RtlSetLastWin32Error
0x18000d06c  cmp     [rbp+50h+var_D0], 0
0x18000d070  jz      short loc_18000D07C
0x18000d072  lea     rcx, [rsp+150h+var_E8]
0x18000d077  call    _lambda_f978de3a668969ac683e101937331384___operator__
0x18000d07c  cmp     [rbp+50h+var_B0], 1
0x18000d080  jnz     short loc_18000D099
0x18000d082  lea     rdx, [rbp+50h+ActivityId]
0x18000d086  mov     [rbp+50h+var_B0], 2
0x18000d08d  lea     rcx, dword_18001D020
0x18000d094  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000d099  mov     eax, r14d
0x18000d09c  jmp     loc_18000D595
0x18000d0a1  mov     [rsp+150h+var_11C], 1
0x18000d0a6  jmp     short loc_18000D042
0x18000d0a8  xor     r8d, r8d
0x18000d0ab  mov     r15d, esi
0x18000d0ae  mov     ecx, r8d
0x18000d0b1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000d0b5  mov     [rsp+150h+var_108], ecx
0x18000d0b9  mov     rbx, r8
0x18000d0bc  cmp     [rdi], r14d
0x18000d0bf  jnb     short loc_18000D0D1
0x18000d0c1  mov     [rsp+150h+LastError], 18h
0x18000d0c9  xor     r15d, r15d
0x18000d0cc  jmp     loc_18000D4AA
0x18000d0d1  mov     rax, rdx
0x18000d0d4  inc     rax
0x18000d0d7  cmp     [r12+rax*2], r8w
0x18000d0dc  jnz     short loc_18000D0D4
0x18000d0de  mov     [rbp+50h+var_C0], rax
0x18000d0e2  test    ax, ax
0x18000d0e5  jnz     short loc_18000D0F1
0x18000d0e7  mov     [rsp+150h+LastError], 7Bh ; '{'
0x18000d0ef  jmp     short loc_18000D0C9
0x18000d0f1  mov     edx, ecx; unsigned int
0x18000d0f3  mov     rcx, rdi; struct _EVENT_TRACE_PROPERTIES *
0x18000d0f6  call    ?EtwpValidateLogFileMode@@YAKPEAU_EVENT_TRACE_PROPERTIES@@K@Z; EtwpValidateLogFileMode(_EVENT_TRACE_PROPERTIES *,ulong)
0x18000d0fb  mov     [rsp+150h+LastError], eax
0x18000d0ff  test    eax, eax
0x18000d101  jnz     loc_18000D498
0x18000d107  lea     r14d, [rax+8]
0x18000d10b  test    [rdi+40h], r14b
0x18000d10f  jz      short loc_18000D161
0x18000d111  lea     edx, [rax+25h]; Ch
0x18000d114  mov     rcx, rsi; Str
0x18000d117  call    cs:__imp_wcschr
0x18000d11d  mov     [rsp+150h+var_100], rax
0x18000d122  test    rax, rax
0x18000d125  jz      short loc_18000D150
0x18000d127  lea     edx, [r14+1Dh]; Ch
0x18000d12b  mov     rcx, rsi; Str
0x18000d12e  call    cs:__imp_wcsrchr
  ... truncated ...
```
