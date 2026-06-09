# ProcessVolumesForThisDevice(CommandLineArgs const *,_iobuf *)

- ea: `0x140007c84`
- end: `0x1400082ca`
- name: `?ProcessVolumesForThisDevice@@YAJPEBUCommandLineArgs@@PEAU_iobuf@@@Z`
- size: `1606`
- prototype: `__int64 __fastcall(const struct CommandLineArgs *, struct _iobuf *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140009ee0`

## callees

- `0x1400011bc`
- `0x140001c50`
- `0x140001c74`
- `0x1400027d2`
- `0x140005444`
- `0x140005684`
- `0x1400057fc`
- `0x1400059b4`
- `0x140006b20`
- `0x140007534`
- `0x140007c84`
- `0x1400089ac`
- `0x140009dac`
- `0x14000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x140007f2d`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x140007f2d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140007ef5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140007ef5`
- `ntdll!RtlGetVersion` at `0x140008155`
- `ntdll!RtlGetVersion` at `0x140008155`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140008186`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400081a3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400081bc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140008186`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400081a3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400081bc`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1400080e9`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1400080e9`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000802c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000802c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140007d4e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140007d74`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140007fd7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140008062`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140007d4e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140007d74`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140007fd7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140008062`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140007d30`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140007d30`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140007d0d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140007d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080f3`

## pseudocode

```c
__int64 __fastcall ProcessVolumesForThisDevice(const struct CommandLineArgs *a1, struct _iobuf *a2)
{
  GUID *v4; // r9
  int v5; // r14d
  void *v6; // rax
  gsl::details *v7; // rcx
  gsl::details *v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // r15
  int v11; // ebx
  REGHANDLE v12; // rcx
  signed int LastError; // eax
  int v15; // edi
  int v16; // eax
  NTSTATUS Version; // eax
  GUID *v18; // rbx
  int v19; // eax
  GUID *v20; // rbx
  int v21; // eax
  gsl::details *v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  char *v23; // [rsp+60h] [rbp-A0h]
  gsl::details *v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v26)(); // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v27)(); // [rsp+80h] [rbp-80h]
  __int128 v28; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A0h] [rbp-60h]
  char v31; // [rsp+A4h] [rbp-5Ch]
  GUID ActivityId; // [rsp+A8h] [rbp-58h] BYREF
  GUID v33; // [rsp+B8h] [rbp-48h] BYREF
  GUID ProviderId; // [rsp+D0h] [rbp-30h] BYREF
  struct _OSVERSIONINFOW String; // [rsp+F0h] [rbp-10h] BYREF
  int v36; // [rsp+20Ch] [rbp+10Ch]
  WCHAR Buffer[264]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v38[264]; // [rsp+510h] [rbp+410h] BYREF

  v30 = 0;
  v31 = 0;
  ProviderId = (GUID)*((_OWORD *)off_140014008 - 1);
  if ( RegHandle )
    __fastfail(5u);
  qword_140014028 = 0;
  qword_140014030 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_140014000, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_140014008, *(unsigned __int16 *)off_140014008);
  if ( (unsigned int)dword_140014000 <= 5 )
  {
    ActivityId = 0;
  }
  else
  {
    EventActivityIdControl(3u, &ActivityId);
    v33 = ActivityId;
    EventActivityIdControl(4u, &v33);
    v31 = 1;
  }
  v30 = 1;
  if ( (unsigned int)dword_140014000 > 5 )
  {
    if ( v31 && (v33.Data1 || *(_DWORD *)&v33.Data2 || *(_DWORD *)v33.Data4 || *(_DWORD *)&v33.Data4[4]) )
      v4 = &v33;
    else
      v4 = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_140014000, byte_140010D9B, &ActivityId, v4, 2, &ProviderId);
  }
  if ( *((_DWORD *)a1 + 5)
    || (v5 = 0, dword_140014000)
    && (qword_140014010 & 0xFFFFFF000LL) != 0
    && (qword_140014018 & 0xFFFFFF000LL) == qword_140014018 )
  {
    v5 = 1;
  }
  v28 = 0;
  v29 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v6 = operator new(0x2027u);
  if ( !v6 )
    __fastfail(5u);
  v7 = (gsl::details *)(((unsigned __int64)v6 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v7 - 1) = v6;
  v22[0] = v7;
  v8 = (gsl::details *)((char *)v7 + 0x2000);
  v23 = (char *)v7 + 0x2000;
  memset_0(v7, 0, 0x2000u);
  v22[1] = v8;
  *(_QWORD *)&ProviderId.Data1 = 0;
  std::_Tidy_guard<std::vector<enum gsl::byte>>::~_Tidy_guard<std::vector<enum gsl::byte>>(&ProviderId);
  v24 = v22[0];
  v25 = 0;
  v26 = LogSingleRuleSummaryEvent;
  v27 = LogBatchedRuleSummaryEvent;
  if ( *((_QWORD *)a1 + 5) )
  {
    memset_0(Buffer, 0, 0x208u);
    memset_0(v38, 0, 0x208u);
    memset_0(&String, 0, 0x208u);
    v9 = wcsstr(*((const wchar_t **)a1 + 5), L"\\");
    v10 = v9;
    if ( v9 )
    {
      v11 = StringCchPrintfW((unsigned __int16 *)&String, 0x104u, L".%s", v9);
      if ( v11 < 0 )
        goto LABEL_32;
      if ( _wcslwr_s((wchar_t *)&String, 0x104u) )
      {
        v11 = -2147467259;
        goto LABEL_32;
      }
      *v10 = 0;
    }
    v11 = StringCchPrintfW(Buffer, 0x104u, L"\\\\.\\%s", *((_QWORD *)a1 + 5));
    if ( v11 < 0 )
      goto LABEL_32;
    v11 = StringCchPrintfW(v38, 0x104u, L"%s\\", *((_QWORD *)a1 + 5));
    if ( v11 < 0 )
      goto LABEL_32;
    v11 = ProcessVolume(a1, Buffer, v38, (__int64)&String, 9u, a2, v5, (__int64)&v28, (__int64)v22);
    if ( v11 < 0 )
      goto LABEL_32;
LABEL_65:
    if ( v5 )
    {
      if ( v24 - v22[0] == -1 || !v22[0] && v24 )
        gsl::details::terminate(v22[0]);
      *(_QWORD *)&ProviderId.Data1 = v24 - v22[0];
      *(gsl::details **)ProviderId.Data4 = v22[0];
      ((void (__fastcall *)(GUID *, __int64))v27)(&ProviderId, v25);
      v24 = v22[0];
      v25 = 0;
    }
    goto LABEL_32;
  }
  memset_0(&String, 0, 0x124u);
  memset_0(Buffer, 0, 0x208u);
  if ( !GetEnvironmentVariableW(L"SystemDrive", Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_32;
  }
  v15 = 0;
  *(_QWORD *)&ProviderId.Data1 = 0;
  *(_QWORD *)ProviderId.Data4 = Buffer;
  v16 = ProcessLetterVolume((_DWORD)a1, (unsigned int)&ProviderId, (_DWORD)a2, v5, (__int64)&v28, (__int64)v22);
  if ( v16 < 0 )
    v15 = v16;
  wcscpy((wchar_t *)&String, L"Ĥ");
  Version = RtlGetVersion(&String);
  v11 = Version | 0x10000000;
  if ( Version >= 0 )
  {
    if ( (v36 & 0x10000) != 0
      || (ProviderId.Data1 = 0, RtlGetDeviceFamilyInfoEnum(0, &ProviderId, 0), ProviderId.Data1 == 10) )
    {
      v20 = (GUID *)&qword_14000E0A0;
      do
      {
        ProviderId = *v20;
        v21 = ProcessLetterVolume((_DWORD)a1, (unsigned int)&ProviderId, (_DWORD)a2, v5, (__int64)&v28, (__int64)v22);
        if ( v21 < 0 && !v15 )
          v15 = v21;
        ++v20;
      }
      while ( v20 != (GUID *)&load_config_used );
    }
    else
    {
      ProviderId.Data1 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &ProviderId, 0);
      if ( ProviderId.Data1 == 14
        || (ProviderId.Data1 = 0, RtlGetDeviceFamilyInfoEnum(0, &ProviderId, 0), ProviderId.Data1 == 16) )
      {
        v18 = (GUID *)&qword_14000E060;
        do
        {
          ProviderId = *v18;
          v19 = ProcessLetterVolume((_DWORD)a1, (unsigned int)&ProviderId, (_DWORD)a2, v5, (__int64)&v28, (__int64)v22);
          if ( v19 < 0 && !v15 )
            v15 = v19;
          ++v18;
        }
        while ( v18 != (GUID *)&qword_14000E0A0 );
      }
    }
    v11 = 0;
    if ( v15 < 0 )
      v11 = v15;
    goto LABEL_65;
  }
LABEL_32:
  if ( v31 )
    EventActivityIdControl(4u, &v33);
  v30 = 2;
  if ( (unsigned int)dword_140014000 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_140014000, qword_140010640, &ActivityId, 0, 2, &ProviderId);
  v12 = RegHandle;
  dword_140014000 = 0;
  RegHandle = 0;
  EventUnregister(v12);
  CleanupRules();
  std::vector<enum gsl::byte>::~vector<enum gsl::byte>(v22);
  std::vector<enum gsl::byte>::~vector<enum gsl::byte>(&v28);
  if ( v30 == 1 )
  {
    if ( v31 )
      EventActivityIdControl(4u, &v33);
    v30 = 2;
    _tlgWriteActivityAutoStop<0,5>(&dword_140014000, &ActivityId);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140007c84  mov     [rsp-8+arg_10], rbx
0x140007c89  push    rbp
0x140007c8a  push    rsi
0x140007c8b  push    rdi
0x140007c8c  push    r12
0x140007c8e  push    r13
0x140007c90  push    r14
0x140007c92  push    r15
0x140007c94  lea     rbp, [rsp-630h]
0x140007c9c  sub     rsp, 730h
0x140007ca3  mov     rax, cs:__security_cookie
0x140007caa  xor     rax, rsp
0x140007cad  mov     [rbp+660h+var_40], rax
0x140007cb4  mov     r12, rdx
0x140007cb7  mov     rsi, rcx
0x140007cba  xor     r13d, r13d
0x140007cbd  mov     [rbp+660h+var_6C0], r13d
0x140007cc1  mov     [rbp+660h+var_6BC], r13b
0x140007cc5  mov     rax, cs:off_140014008
0x140007ccc  movups  xmm0, xmmword ptr [rax-10h]
0x140007cd0  movdqu  xmmword ptr [rbp+660h+ProviderId.Data1], xmm0
0x140007cd5  lea     ebx, [r13+5]
0x140007cd9  cmp     cs:RegHandle, r13
0x140007ce0  jz      short loc_140007CE6
0x140007ce2  mov     ecx, ebx
0x140007ce4  int     29h; Win8: RtlFailFast(ecx)
0x140007ce6  mov     cs:qword_140014028, r13
0x140007ced  mov     cs:qword_140014030, r13
0x140007cf4  lea     r9, RegHandle; RegHandle
0x140007cfb  lea     r8, dword_140014000; CallbackContext
0x140007d02  lea     rdx, _tlgEnableCallback; EnableCallback
0x140007d09  lea     rcx, [rbp+660h+ProviderId]; ProviderId
0x140007d0d  call    cs:__imp_EventRegister
0x140007d13  mov     edi, 2
0x140007d18  test    eax, eax
0x140007d1a  jnz     short loc_140007D36
0x140007d1c  mov     r8, cs:off_140014008
0x140007d23  movzx   r9d, word ptr [r8]
0x140007d27  mov     edx, edi
0x140007d29  mov     rcx, cs:RegHandle
0x140007d30  call    cs:__imp_EventSetInformation
0x140007d36  mov     eax, cs:dword_140014000
0x140007d3c  mov     r15d, 1
0x140007d42  cmp     eax, ebx
0x140007d44  jbe     short loc_140007D80
0x140007d46  lea     rdx, [rbp+660h+ActivityId]; ActivityId
0x140007d4a  lea     ecx, [r15+2]; ControlCode
0x140007d4e  call    cs:__imp_EventActivityIdControl
0x140007d54  mov     eax, [rbp+660h+ActivityId.Data1]
0x140007d57  mov     [rbp+660h+var_6A8.Data1], eax
0x140007d5a  mov     eax, dword ptr [rbp+660h+ActivityId.Data2]
0x140007d5d  mov     dword ptr [rbp+660h+var_6A8.Data2], eax
0x140007d60  mov     eax, dword ptr [rbp+660h+ActivityId.Data4]
0x140007d63  mov     dword ptr [rbp+660h+var_6A8.Data4], eax
0x140007d66  mov     eax, dword ptr [rbp+660h+ActivityId.Data4+4]
0x140007d69  mov     dword ptr [rbp+660h+var_6A8.Data4+4], eax
0x140007d6c  lea     rdx, [rbp+660h+var_6A8]; ActivityId
0x140007d70  lea     ecx, [r15+3]; ControlCode
0x140007d74  call    cs:__imp_EventActivityIdControl
0x140007d7a  mov     [rbp+660h+var_6BC], r15b
0x140007d7e  jmp     short loc_140007D87
0x140007d80  xorps   xmm0, xmm0
0x140007d83  movups  xmmword ptr [rbp+660h+ActivityId.Data1], xmm0
0x140007d87  mov     [rbp+660h+var_6C0], r15d
0x140007d8b  mov     eax, cs:dword_140014000
0x140007d91  cmp     eax, ebx
0x140007d93  jbe     short loc_140007DE0
0x140007d95  cmp     [rbp+660h+var_6BC], r13b
0x140007d99  jz      short loc_140007DB9
0x140007d9b  cmp     [rbp+660h+var_6A8.Data1], r13d
0x140007d9f  jnz     short loc_140007DB3
0x140007da1  cmp     dword ptr [rbp+660h+var_6A8.Data2], r13d
0x140007da5  jnz     short loc_140007DB3
0x140007da7  cmp     dword ptr [rbp+660h+var_6A8.Data4], r13d
0x140007dab  jnz     short loc_140007DB3
0x140007dad  cmp     dword ptr [rbp+660h+var_6A8.Data4+4], r13d
0x140007db1  jz      short loc_140007DB9
0x140007db3  lea     r9, [rbp+660h+var_6A8]
0x140007db7  jmp     short loc_140007DBC
0x140007db9  mov     r9, r13
0x140007dbc  lea     rax, [rbp+660h+ProviderId]
0x140007dc0  mov     [rsp+760h+var_738], rax
0x140007dc5  mov     dword ptr [rsp+760h+var_740], edi
0x140007dc9  lea     r8, [rbp+660h+ActivityId]
0x140007dcd  lea     rdx, byte_140010D9B
0x140007dd4  lea     rcx, dword_140014000
0x140007ddb  call    _tlgWriteTransfer_EventWriteTransfer
0x140007de0  cmp     [rsi+14h], r13d
0x140007de4  jnz     short loc_140007E1B
0x140007de6  mov     r14d, r13d
0x140007de9  mov     eax, cs:dword_140014000
0x140007def  test    eax, eax
0x140007df1  jz      short loc_140007E1E
0x140007df3  mov     rcx, cs:qword_140014018
0x140007dfa  mov     rax, cs:qword_140014010
0x140007e01  mov     rdx, 0FFFFFF000h
0x140007e0b  test    rdx, rax
0x140007e0e  jz      short loc_140007E1E
0x140007e10  mov     rax, rcx
0x140007e13  and     rax, rdx
0x140007e16  cmp     rax, rcx
0x140007e19  jnz     short loc_140007E1E
0x140007e1b  mov     r14d, r15d
0x140007e1e  xorps   xmm0, xmm0
0x140007e21  movdqu  [rbp+660h+var_6D8], xmm0
0x140007e26  mov     [rbp+660h+var_6C8], r13
0x140007e2a  movdqu  xmmword ptr [rsp+760h+var_710], xmm0
0x140007e30  mov     [rsp+760h+var_700], r13
0x140007e35  mov     ecx, 2027h; Size
0x140007e3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007e3f  test    rax, rax
0x140007e42  jnz     short loc_140007E49
0x140007e44  mov     rcx, rbx
0x140007e47  int     29h; Win8: RtlFailFast(ecx)
0x140007e49  lea     rcx, [rax+27h]
0x140007e4d  and     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x140007e51  mov     [rcx-8], rax
0x140007e55  mov     [rsp+760h+var_710], rcx
0x140007e5a  lea     rbx, [rcx+2000h]
0x140007e61  mov     [rsp+760h+var_700], rbx
0x140007e66  xor     edx, edx; Val
0x140007e68  mov     r8d, 2000h; Size
0x140007e6e  call    memset_0
0x140007e73  mov     [rsp+760h+var_710+8], rbx
0x140007e78  mov     qword ptr [rbp+660h+ProviderId.Data1], r13
0x140007e7c  lea     rcx, [rbp+660h+ProviderId]
0x140007e80  call    ??1?$_Tidy_guard@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<gsl::byte>>::~_Tidy_guard<std::vector<gsl::byte>>(void)
0x140007e85  mov     rax, [rsp+760h+var_710]
0x140007e8a  mov     [rsp+760h+var_6F8], rax
0x140007e8f  mov     [rsp+760h+var_6F0], r13
0x140007e94  lea     rax, ?LogSingleRuleSummaryEvent@@YAXV?$span@W4byte@gsl@@$0?0@gsl@@@Z; LogSingleRuleSummaryEvent(gsl::span<gsl::byte,-1>)
0x140007e9b  mov     [rsp+760h+var_6E8], rax
0x140007ea0  lea     rax, ?LogBatchedRuleSummaryEvent@@YAXV?$span@W4byte@gsl@@$0?0@gsl@@_K@Z; LogBatchedRuleSummaryEvent(gsl::span<gsl::byte,-1>,unsigned __int64)
0x140007ea7  mov     [rbp+660h+var_6E0], rax
0x140007eab  xor     edx, edx; Val
0x140007ead  cmp     [rsi+28h], r13
0x140007eb1  jz      loc_1400080B1
0x140007eb7  mov     ebx, 208h
0x140007ebc  mov     r8d, ebx; Size
0x140007ebf  lea     rcx, [rbp+660h+Buffer]; void *
0x140007ec6  call    memset_0
0x140007ecb  mov     r8d, ebx; Size
0x140007ece  xor     edx, edx; Val
0x140007ed0  lea     rcx, [rbp+660h+var_250]; void *
0x140007ed7  call    memset_0
0x140007edc  mov     r8d, ebx; Size
0x140007edf  xor     edx, edx; Val
0x140007ee1  lea     rcx, [rbp+660h+String]; void *
0x140007ee5  call    memset_0
0x140007eea  lea     rdx, SubStr; "\\"
0x140007ef1  mov     rcx, [rsi+28h]; Str
0x140007ef5  call    cs:__imp_wcsstr
0x140007efb  mov     r15, rax
0x140007efe  mov     edi, 104h
0x140007f03  test    rax, rax
0x140007f06  jz      short loc_140007F3F
0x140007f08  mov     r9, rax
0x140007f0b  lea     r8, aS_0; ".%s"
0x140007f12  mov     edx, edi; unsigned __int64
0x140007f14  lea     rcx, [rbp+660h+String]; unsigned __int16 *
0x140007f18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007f1d  mov     ebx, eax
0x140007f1f  test    eax, eax
0x140007f21  js      loc_140007FC8
0x140007f27  mov     edx, edi; SizeInWords
0x140007f29  lea     rcx, [rbp+660h+String]; String
0x140007f2d  call    cs:__imp__wcslwr_s
0x140007f33  test    eax, eax
0x140007f35  jnz     loc_1400080A7
0x140007f3b  mov     [r15], r13w
0x140007f3f  mov     r9, [rsi+28h]
0x140007f43  lea     r8, aS_1; "\\\\.\\%s"
0x140007f4a  mov     rdx, rdi; unsigned __int64
0x140007f4d  lea     rcx, [rbp+660h+Buffer]; unsigned __int16 *
0x140007f54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007f59  mov     ebx, eax
0x140007f5b  test    eax, eax
0x140007f5d  js      short loc_140007FC8
0x140007f5f  mov     r9, [rsi+28h]
0x140007f63  lea     r8, aS_2; "%s\\"
0x140007f6a  mov     rdx, rdi; unsigned __int64
0x140007f6d  lea     rcx, [rbp+660h+var_250]; unsigned __int16 *
0x140007f74  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007f79  mov     ebx, eax
0x140007f7b  test    eax, eax
0x140007f7d  js      short loc_140007FC8
0x140007f7f  lea     rax, [rsp+760h+var_710]
0x140007f84  mov     [rsp+760h+var_720], rax
0x140007f89  lea     rax, [rbp+660h+var_6D8]
0x140007f8d  mov     [rsp+760h+var_728], rax
0x140007f92  mov     [rsp+760h+var_730], r14d
0x140007f97  mov     [rsp+760h+var_738], r12
0x140007f9c  mov     dword ptr [rsp+760h+var_740], 9
0x140007fa4  lea     r9, [rbp+660h+String]
0x140007fa8  lea     r8, [rbp+660h+var_250]
0x140007faf  lea     rdx, [rbp+660h+Buffer]
0x140007fb6  mov     rcx, rsi
0x140007fb9  call    ProcessVolume
0x140007fbe  mov     ebx, eax
0x140007fc0  test    eax, eax
0x140007fc2  jns     loc_140008270
0x140007fc8  cmp     [rbp+660h+var_6BC], r13b
0x140007fcc  jz      short loc_140007FDD
0x140007fce  lea     rdx, [rbp+660h+var_6A8]; ActivityId
0x140007fd2  mov     ecx, 4; ControlCode
0x140007fd7  call    cs:__imp_EventActivityIdControl
0x140007fdd  mov     edi, 2
0x140007fe2  mov     [rbp+660h+var_6C0], edi
0x140007fe5  mov     eax, cs:dword_140014000
0x140007feb  cmp     eax, 5
0x140007fee  jbe     short loc_140008017
0x140007ff0  lea     rax, [rbp+660h+ProviderId]
0x140007ff4  mov     [rsp+760h+var_738], rax
0x140007ff9  mov     dword ptr [rsp+760h+var_740], edi
0x140007ffd  xor     r9d, r9d
0x140008000  lea     r8, [rbp+660h+ActivityId]
0x140008004  lea     rdx, qword_140010640
0x14000800b  lea     rcx, dword_140014000
0x140008012  call    _tlgWriteTransfer_EventWriteTransfer
0x140008017  mov     rcx, cs:RegHandle; RegHandle
0x14000801e  mov     cs:dword_140014000, r13d
0x140008025  mov     cs:RegHandle, r13
0x14000802c  call    cs:__imp_EventUnregister
0x140008032  call    CleanupRules
0x140008037  nop
0x140008038  lea     rcx, [rsp+760h+var_710]
0x14000803d  call    ??1?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::vector<gsl::byte>::~vector<gsl::byte>(void)
0x140008042  nop
0x140008043  lea     rcx, [rbp+660h+var_6D8]
0x140008047  call    ??1?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::vector<gsl::byte>::~vector<gsl::byte>(void)
0x14000804c  nop
0x14000804d  cmp     [rbp+660h+var_6C0], 1
0x140008051  jnz     short loc_14000807B
0x140008053  cmp     [rbp+660h+var_6BC], r13b
0x140008057  jz      short loc_140008068
0x140008059  lea     rdx, [rbp+660h+var_6A8]; ActivityId
0x14000805d  mov     ecx, 4; ControlCode
0x140008062  call    cs:__imp_EventActivityIdControl
0x140008068  mov     [rbp+660h+var_6C0], edi
0x14000806b  lea     rdx, [rbp+660h+ActivityId]
0x14000806f  lea     rcx, dword_140014000
0x140008076  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x14000807b  mov     eax, ebx
0x14000807d  mov     rcx, [rbp+660h+var_40]
0x140008084  xor     rcx, rsp; StackCookie
0x140008087  call    __security_check_cookie
0x14000808c  mov     rbx, [rsp+760h+arg_10]
0x140008094  add     rsp, 730h
0x14000809b  pop     r15
0x14000809d  pop     r14
0x14000809f  pop     r13
0x1400080a1  pop     r12
0x1400080a3  pop     rdi
0x1400080a4  pop     rsi
0x1400080a5  pop     rbp
0x1400080a6  retn
0x1400080a7  mov     ebx, 80004005h
0x1400080ac  jmp     loc_140007FC8
0x1400080b1  mov     r15d, 124h
0x1400080b7  mov     r8d, r15d; Size
0x1400080ba  lea     rcx, [rbp+660h+String]; void *
0x1400080be  call    memset_0
0x1400080c3  xor     edx, edx; Val
0x1400080c5  mov     r8d, 208h; Size
0x1400080cb  lea     rcx, [rbp+660h+Buffer]; void *
0x1400080d2  call    memset_0
0x1400080d7  lea     r8d, [r15-20h]; nSize
0x1400080db  lea     rdx, [rbp+660h+Buffer]; lpBuffer
0x1400080e2  lea     rcx, Name; "SystemDrive"
0x1400080e9  call    cs:__imp_GetEnvironmentVariableW
0x1400080ef  test    eax, eax
0x1400080f1  jnz     short loc_140008111
0x1400080f3  call    cs:__imp_GetLastError
0x1400080f9  mov     ebx, eax
0x1400080fb  test    eax, eax
0x1400080fd  jle     loc_140007FC8
0x140008103  movzx   ebx, ax
0x140008106  or      ebx, 80070000h
0x14000810c  jmp     loc_140007FC8
0x140008111  mov     edi, r13d
0x140008114  mov     qword ptr [rbp+660h+ProviderId.Data1], r13
0x140008118  lea     rax, [rbp+660h+Buffer]
0x14000811f  mov     qword ptr [rbp+660h+ProviderId.Data4], rax
0x140008123  lea     rax, [rsp+760h+var_710]
0x140008128  mov     [rsp+760h+var_738], rax
0x14000812d  lea     rax, [rbp+660h+var_6D8]
0x140008131  mov     [rsp+760h+var_740], rax
0x140008136  mov     r9d, r14d
0x140008139  mov     r8, r12
0x14000813c  lea     rdx, [rbp+660h+ProviderId]
0x140008140  mov     rcx, rsi
0x140008143  call    ProcessLetterVolume
0x140008148  test    eax, eax
0x14000814a  cmovs   edi, eax
0x14000814d  mov     [rbp+660h+String.dwOSVersionInfoSize], r15d
0x140008151  lea     rcx, [rbp+660h+String]; lpVersionInformation
0x140008155  call    cs:__imp_RtlGetVersion
0x14000815b  mov     ebx, eax
0x14000815d  or      ebx, 10000000h
0x140008163  jl      loc_140007FC8
  ... truncated ...
```
