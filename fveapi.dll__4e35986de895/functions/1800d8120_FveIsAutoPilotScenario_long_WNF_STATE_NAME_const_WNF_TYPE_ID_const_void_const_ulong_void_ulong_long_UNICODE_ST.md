# FveIsAutoPilotScenario(long (*)(_WNF_STATE_NAME const *,_WNF_TYPE_ID const *,void const *,ulong *,void *,ulong *),long (*)(_UNICODE_STRING *,ulong *,void *,ulong,ulong *),bool *,bool *,unsigned __int64 *)

- ea: `0x1800d8120`
- end: `0x1800d877f`
- name: `?FveIsAutoPilotScenario@@YAJP6AJPEBU_WNF_STATE_NAME@@PEBU_WNF_TYPE_ID@@PEBXPEAKPEAX3@ZP6AJPEAU_UNICODE_STRING@@34K3@ZPEA_N8PEA_K@Z`
- size: `1631`
- prototype: `__int64 __fastcall(int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *), int (*)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *), bool *, bool *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d7284`

## callees

- `0x1800043f4`
- `0x180008d70`
- `0x1800090c0`
- `0x180045ff0`
- `0x1800485f0`
- `0x18004ad74`
- `0x1800d8120`
- `0x180129010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800d8185`
- `ntdll!RtlInitUnicodeString` at `0x1800d8185`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d81fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d81fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d82f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d82f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d8753`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d8753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8304`

## string_xrefs

- `0x1800d81ef`: `autopilot.dll`
- `0x1800d8156`: `WorkstationService-DomainJoinEnabled`

## pseudocode

```c
__int64 __fastcall FveIsAutoPilotScenario(
        int (*a1)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *),
        __int64 (__fastcall *a2)(struct _UNICODE_STRING *, int *, int *, __int64, int *),
        bool *a3,
        bool *a4,
        unsigned __int64 *a5)
{
  char v5; // r13
  int v9; // eax
  __int64 v10; // rdi
  HMODULE Library; // rax
  HMODULE v12; // r15
  signed int LastError; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  FARPROC ProcAddress; // rbx
  signed int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  bool v24; // r14
  int v25; // eax
  __int64 v26; // rax
  bool *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  int v32; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-2Dh] BYREF
  int v34; // [rsp+48h] [rbp-29h] BYREF
  int v35; // [rsp+4Ch] [rbp-25h] BYREF
  int v36; // [rsp+50h] [rbp-21h] BYREF
  int v37; // [rsp+54h] [rbp-1Dh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v39[88]; // [rsp+68h] [rbp-9h] BYREF
  unsigned int v41; // [rsp+D8h] [rbp+67h] BYREF
  int v42; // [rsp+E0h] [rbp+6Fh] BYREF
  bool *v43; // [rsp+E8h] [rbp+77h] BYREF

  v43 = a4;
  v5 = 0;
  v33 = 0;
  v34 = 0;
  v32 = 0;
  v37 = 0;
  v42 = 4;
  v36 = 0;
  DestinationString = 0;
  v35 = 0;
  *a3 = 0;
  *a4 = 0;
  RtlInitUnicodeString(&DestinationString, L"WorkstationService-DomainJoinEnabled");
  v9 = a2(&DestinationString, &v37, &v35, 4, &v36);
  if ( v9 >= 0 )
  {
    v10 = 0;
    if ( (v35 & 2) == 0 )
    {
      v12 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v10 = 0x20000000;
      goto LABEL_87;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v9);
    v10 = 0x10000000;
  }
  Library = LoadLibraryExW(L"autopilot.dll", 0, 0x800u);
  v12 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( v14 == -2147024894 )
    {
      v14 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v15 = 0x40000000;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v14);
      v15 = 0x80000000LL;
    }
LABEL_23:
    v10 |= v15;
    goto LABEL_88;
  }
  ProcAddress = GetProcAddress(Library, "AutoPilotIsLocalProfileAvailable");
  if ( !ProcAddress )
  {
    v17 = GetLastError();
    v14 = v17;
    if ( v17 > 0 )
      v14 = (unsigned __int16)v17 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v14);
    v15 = 0x100000000LL;
    goto LABEL_23;
  }
  LOBYTE(v41) = 0;
  v32 = 0;
  v42 = 4;
  v18 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, int *))a1)(
          &WNF_PROV_AUTOPILOT_PROFILE_AVAILABLE,
          0,
          0,
          &v34,
          &v32,
          &v42);
  if ( v18 >= 0 )
  {
    if ( v42 == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      LOBYTE(v41) = 1;
      v19 = 0x400000000LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v19 = 0x800000000LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v18);
    v19 = 0x200000000LL;
  }
  v20 = v19 | v10;
  v32 = 0;
  v42 = 4;
  v21 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, int *))a1)(
          &WNF_PROV_AUTOPILOT_DEVICE_NOT_MANAGED,
          0,
          0,
          &v34,
          &v32,
          &v42);
  if ( v21 >= 0 )
  {
    if ( v42 == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v5 = 1;
      v22 = 0x2000000000LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v22 = 0x4000000000LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v21);
    v22 = 0x1000000000LL;
  }
  v10 = v22 | v20;
  v23 = ((__int64 (__fastcall *)(unsigned int *))ProcAddress)(&v33);
  v14 = v23;
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v23);
    v15 = 0x8000000000LL;
    goto LABEL_23;
  }
  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v33);
  v32 = 0;
  v42 = 4;
  v25 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, int *))a1)(
          &WNF_PROV_DEVICE_BOOTSTRAP_COMPLETE,
          0,
          0,
          &v34,
          &v32,
          &v42);
  if ( v25 >= 0 )
  {
    if ( v42 == 4 )
    {
      v24 = v32 == 1;
      goto LABEL_79;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
    v26 = 0x20000000000LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v25);
    v26 = 0x10000000000LL;
  }
  v10 |= v26;
LABEL_79:
  if ( v33 )
  {
    v27 = v43;
    *a3 = 1;
    *v27 = v24;
LABEL_87:
    v14 = 0;
    goto LABEL_88;
  }
  v14 = -2147024875;
  if ( v5 )
  {
    *a3 = 0;
    v14 = 0;
  }
  if ( (_BYTE)v41 )
  {
    *a3 = 0;
    v14 = 0;
  }
  if ( v24 )
  {
    *a3 = 0;
    goto LABEL_87;
  }
LABEL_88:
  if ( a5 )
    *a5 |= v10;
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v39,
    &g_hBitLockerDelayProvider,
    &g_bitLockerDelayProviderInitLock,
    &g_bitLockerDelayProviderRefCount);
  if ( (unsigned int)dword_180172550 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180172550, 0x400000000000LL) )
  {
    LODWORD(a5) = v33;
    LOBYTE(v43) = *a3;
    v41 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v28,
      (int)&word_1801602C6,
      v29,
      v30,
      (__int64)&v41,
      (__int64)&v43,
      (__int64)&a5);
  }
  if ( v12 )
    FreeLibrary(v12);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v39);
  return v14;
}

```

## disassembly

```asm
0x1800d8120  mov     [rsp-8+arg_18], r9
0x1800d8125  mov     [rsp-8+arg_0], rcx
0x1800d812a  push    rbp
0x1800d812b  push    rbx
0x1800d812c  push    rsi
0x1800d812d  push    rdi
0x1800d812e  push    r12
0x1800d8130  push    r13
0x1800d8132  push    r14
0x1800d8134  push    r15
0x1800d8136  lea     rbp, [rsp-17h]
0x1800d813b  sub     rsp, 88h
0x1800d8142  xor     r13d, r13d
0x1800d8145  mov     rbx, rdx
0x1800d8148  mov     r14, rcx
0x1800d814b  mov     [rbp+4Fh+var_7C], r13d
0x1800d814f  xorps   xmm0, xmm0
0x1800d8152  mov     [rbp+4Fh+var_78], r13d
0x1800d8156  lea     rdx, aWorkstationser; "WorkstationService-DomainJoinEnabled"
0x1800d815d  mov     [rbp+4Fh+var_80], r13d
0x1800d8161  lea     edi, [r13+4]
0x1800d8165  mov     [rbp+4Fh+var_6C], r13d
0x1800d8169  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800d816d  mov     [rbp+4Fh+arg_10], edi
0x1800d8170  mov     r12, r8
0x1800d8173  mov     [rbp+4Fh+var_70], r13d
0x1800d8177  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800d817b  mov     [rbp+4Fh+var_74], r13d
0x1800d817f  mov     [r8], r13b
0x1800d8182  mov     [r9], r13b
0x1800d8185  call    cs:__imp_RtlInitUnicodeString
0x1800d818c  nop     dword ptr [rax+rax+00h]
0x1800d8191  lea     rax, [rbp+4Fh+var_70]
0x1800d8195  mov     r9d, edi
0x1800d8198  mov     [rsp+0C0h+var_A0], rax
0x1800d819d  lea     r8, [rbp+4Fh+var_74]
0x1800d81a1  mov     rax, rbx
0x1800d81a4  lea     rdx, [rbp+4Fh+var_6C]
0x1800d81a8  lea     rcx, [rbp+4Fh+DestinationString]
0x1800d81ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d81b1  lea     rsi, WPP_GLOBAL_Control
0x1800d81b8  test    eax, eax
0x1800d81ba  jns     loc_1800D826B
0x1800d81c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d81c7  cmp     rcx, rsi
0x1800d81ca  jz      short loc_1800D81E8
0x1800d81cc  test    [rcx+1Ch], dil
0x1800d81d0  jz      short loc_1800D81E8
0x1800d81d2  mov     rcx, [rcx+10h]
0x1800d81d6  lea     edx, [rdi+6]
0x1800d81d9  mov     r9d, eax
0x1800d81dc  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d81e3  call    WPP_SF_d
0x1800d81e8  mov     edi, 10000000h
0x1800d81ed  xor     edx, edx; hFile
0x1800d81ef  lea     rcx, aAutopilotDll; "autopilot.dll"
0x1800d81f6  mov     r8d, 800h; dwFlags
0x1800d81fc  call    cs:__imp_LoadLibraryExW
0x1800d8203  nop     dword ptr [rax+rax+00h]
0x1800d8208  mov     r15, rax
0x1800d820b  test    rax, rax
0x1800d820e  jnz     loc_1800D82E6
0x1800d8214  call    cs:__imp_GetLastError
0x1800d821b  nop     dword ptr [rax+rax+00h]
0x1800d8220  mov     ebx, eax
0x1800d8222  test    eax, eax
0x1800d8224  jle     short loc_1800D822F
0x1800d8226  movzx   ebx, ax
0x1800d8229  or      ebx, 80070000h
0x1800d822f  cmp     ebx, 80070002h
0x1800d8235  jnz     short loc_1800D82AF
0x1800d8237  mov     ebx, r13d
0x1800d823a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8241  cmp     rcx, rsi
0x1800d8244  jz      short loc_1800D8264
0x1800d8246  mov     sil, 8
0x1800d8249  test    [rcx+1Ch], sil
0x1800d824d  jz      short loc_1800D8264
0x1800d824f  mov     rcx, [rcx+10h]
0x1800d8253  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d825a  mov     edx, 0Ch
0x1800d825f  call    WPP_SF_
0x1800d8264  mov     eax, 40000000h
0x1800d8269  jmp     short loc_1800D82DE
0x1800d826b  test    byte ptr [rbp+4Fh+var_74], 2
0x1800d826f  mov     rdi, r13
0x1800d8272  jnz     loc_1800D81ED
0x1800d8278  mov     r15, r13
0x1800d827b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8282  cmp     rcx, rsi
0x1800d8285  jz      short loc_1800D82A5
0x1800d8287  mov     sil, 8
0x1800d828a  test    [rcx+1Ch], sil
0x1800d828e  jz      short loc_1800D82A5
0x1800d8290  mov     rcx, [rcx+10h]
0x1800d8294  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d829b  mov     edx, 0Bh
0x1800d82a0  call    WPP_SF_
0x1800d82a5  mov     edi, 20000000h
0x1800d82aa  jmp     loc_1800D86C2
0x1800d82af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d82b6  cmp     rcx, rsi
0x1800d82b9  jz      short loc_1800D82D9
0x1800d82bb  test    byte ptr [rcx+1Ch], 2
0x1800d82bf  jz      short loc_1800D82D9
0x1800d82c1  mov     rcx, [rcx+10h]
0x1800d82c5  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d82cc  mov     edx, 0Dh
0x1800d82d1  mov     r9d, ebx
0x1800d82d4  call    WPP_SF_d
0x1800d82d9  mov     eax, 80000000h
0x1800d82de  or      rdi, rax
0x1800d82e1  jmp     loc_1800D86C5
0x1800d82e6  lea     rdx, aAutopilotisloc; "AutoPilotIsLocalProfileAvailable"
0x1800d82ed  mov     rcx, rax; hModule
0x1800d82f0  call    cs:__imp_GetProcAddress
0x1800d82f7  nop     dword ptr [rax+rax+00h]
0x1800d82fc  mov     rbx, rax
0x1800d82ff  test    rax, rax
0x1800d8302  jnz     short loc_1800D8355
0x1800d8304  call    cs:__imp_GetLastError
0x1800d830b  nop     dword ptr [rax+rax+00h]
0x1800d8310  mov     ebx, eax
0x1800d8312  test    eax, eax
0x1800d8314  jle     short loc_1800D831F
0x1800d8316  movzx   ebx, ax
0x1800d8319  or      ebx, 80070000h
0x1800d831f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8326  cmp     rcx, rsi
0x1800d8329  jz      short loc_1800D8349
0x1800d832b  test    byte ptr [rcx+1Ch], 2
0x1800d832f  jz      short loc_1800D8349
0x1800d8331  mov     rcx, [rcx+10h]
0x1800d8335  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d833c  mov     edx, 0Eh
0x1800d8341  mov     r9d, ebx
0x1800d8344  call    WPP_SF_d
0x1800d8349  mov     rax, 100000000h
0x1800d8353  jmp     short loc_1800D82DE
0x1800d8355  lea     rax, [rbp+4Fh+arg_10]
0x1800d8359  mov     byte ptr [rbp+4Fh+arg_8], r13b
0x1800d835d  mov     [rsp+0C0h+var_98], rax
0x1800d8362  lea     r9, [rbp+4Fh+var_78]
0x1800d8366  lea     rax, [rbp+4Fh+var_80]
0x1800d836a  mov     [rbp+4Fh+var_80], r13d
0x1800d836e  mov     [rsp+0C0h+var_A0], rax
0x1800d8373  lea     rcx, WNF_PROV_AUTOPILOT_PROFILE_AVAILABLE
0x1800d837a  mov     rax, r14
0x1800d837d  mov     [rbp+4Fh+arg_10], 4
0x1800d8384  xor     r8d, r8d
0x1800d8387  xor     edx, edx
0x1800d8389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d838e  mov     sil, 8
0x1800d8391  test    eax, eax
0x1800d8393  jns     short loc_1800D83D2
0x1800d8395  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d839c  lea     rdx, WPP_GLOBAL_Control
0x1800d83a3  cmp     rcx, rdx
0x1800d83a6  jz      short loc_1800D83C6
0x1800d83a8  test    byte ptr [rcx+1Ch], 2
0x1800d83ac  jz      short loc_1800D83C6
0x1800d83ae  mov     rcx, [rcx+10h]
0x1800d83b2  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d83b9  mov     edx, 0Fh
0x1800d83be  mov     r9d, eax
0x1800d83c1  call    WPP_SF_d
0x1800d83c6  mov     rax, 200000000h
0x1800d83d0  jmp     short loc_1800D844E
0x1800d83d2  cmp     [rbp+4Fh+arg_10], 4
0x1800d83d6  jnz     short loc_1800D8416
0x1800d83d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d83df  lea     rdx, WPP_GLOBAL_Control
0x1800d83e6  cmp     rcx, rdx
0x1800d83e9  jz      short loc_1800D8406
0x1800d83eb  test    [rcx+1Ch], sil
0x1800d83ef  jz      short loc_1800D8406
0x1800d83f1  mov     rcx, [rcx+10h]
0x1800d83f5  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d83fc  mov     edx, 10h
0x1800d8401  call    WPP_SF_
0x1800d8406  mov     byte ptr [rbp+4Fh+arg_8], 1
0x1800d840a  mov     rax, 400000000h
0x1800d8414  jmp     short loc_1800D844E
0x1800d8416  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d841d  lea     rdx, WPP_GLOBAL_Control
0x1800d8424  cmp     rcx, rdx
0x1800d8427  jz      short loc_1800D8444
0x1800d8429  test    [rcx+1Ch], sil
0x1800d842d  jz      short loc_1800D8444
0x1800d842f  mov     rcx, [rcx+10h]
0x1800d8433  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d843a  mov     edx, 11h
0x1800d843f  call    WPP_SF_
0x1800d8444  mov     rax, 800000000h
0x1800d844e  or      rdi, rax
0x1800d8451  mov     [rbp+4Fh+var_80], r13d
0x1800d8455  lea     rax, [rbp+4Fh+arg_10]
0x1800d8459  mov     [rbp+4Fh+arg_10], 4
0x1800d8460  mov     [rsp+0C0h+var_98], rax
0x1800d8465  lea     r9, [rbp+4Fh+var_78]
0x1800d8469  lea     rax, [rbp+4Fh+var_80]
0x1800d846d  xor     r8d, r8d
0x1800d8470  mov     [rsp+0C0h+var_A0], rax
0x1800d8475  lea     rcx, WNF_PROV_AUTOPILOT_DEVICE_NOT_MANAGED
0x1800d847c  mov     rax, r14
0x1800d847f  xor     edx, edx
0x1800d8481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8486  test    eax, eax
0x1800d8488  jns     short loc_1800D84C7
0x1800d848a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8491  lea     r14, WPP_GLOBAL_Control
0x1800d8498  cmp     rcx, r14
0x1800d849b  jz      short loc_1800D84BB
0x1800d849d  test    byte ptr [rcx+1Ch], 2
0x1800d84a1  jz      short loc_1800D84BB
0x1800d84a3  mov     rcx, [rcx+10h]
0x1800d84a7  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d84ae  mov     edx, 12h
0x1800d84b3  mov     r9d, eax
0x1800d84b6  call    WPP_SF_d
0x1800d84bb  mov     rax, 1000000000h
0x1800d84c5  jmp     short loc_1800D8542
0x1800d84c7  cmp     [rbp+4Fh+arg_10], 4
0x1800d84cb  jnz     short loc_1800D850A
0x1800d84cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d84d4  lea     r14, WPP_GLOBAL_Control
0x1800d84db  cmp     rcx, r14
0x1800d84de  jz      short loc_1800D84FB
0x1800d84e0  test    [rcx+1Ch], sil
0x1800d84e4  jz      short loc_1800D84FB
0x1800d84e6  mov     rcx, [rcx+10h]
0x1800d84ea  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d84f1  mov     edx, 13h
0x1800d84f6  call    WPP_SF_
0x1800d84fb  mov     r13b, 1
0x1800d84fe  mov     rax, 2000000000h
0x1800d8508  jmp     short loc_1800D8542
0x1800d850a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8511  lea     r14, WPP_GLOBAL_Control
0x1800d8518  cmp     rcx, r14
0x1800d851b  jz      short loc_1800D8538
0x1800d851d  test    [rcx+1Ch], sil
0x1800d8521  jz      short loc_1800D8538
0x1800d8523  mov     rcx, [rcx+10h]
0x1800d8527  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d852e  mov     edx, 14h
0x1800d8533  call    WPP_SF_
0x1800d8538  mov     rax, 4000000000h
0x1800d8542  or      rdi, rax
0x1800d8545  lea     rcx, [rbp+4Fh+var_7C]
0x1800d8549  mov     rax, rbx
0x1800d854c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8551  mov     ebx, eax
0x1800d8553  test    eax, eax
0x1800d8555  jns     short loc_1800D8590
0x1800d8557  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d855e  cmp     rcx, r14
0x1800d8561  jz      short loc_1800D8581
0x1800d8563  test    byte ptr [rcx+1Ch], 2
0x1800d8567  jz      short loc_1800D8581
0x1800d8569  mov     rcx, [rcx+10h]
0x1800d856d  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d8574  mov     edx, 15h
0x1800d8579  mov     r9d, eax
0x1800d857c  call    WPP_SF_d
0x1800d8581  mov     rax, 8000000000h
0x1800d858b  jmp     loc_1800D82DE
0x1800d8590  xor     r14b, r14b
0x1800d8593  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d859a  lea     rbx, WPP_GLOBAL_Control
0x1800d85a1  cmp     rcx, rbx
0x1800d85a4  jz      short loc_1800D85C5
0x1800d85a6  test    [rcx+1Ch], sil
0x1800d85aa  jz      short loc_1800D85C5
0x1800d85ac  mov     r9d, [rbp+4Fh+var_7C]
0x1800d85b0  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d85b7  mov     rcx, [rcx+10h]
0x1800d85bb  mov     edx, 16h
0x1800d85c0  call    WPP_SF_d
0x1800d85c5  lea     rax, [rbp+4Fh+arg_10]
0x1800d85c9  mov     [rbp+4Fh+var_80], 0
0x1800d85d0  mov     [rsp+0C0h+var_98], rax
0x1800d85d5  lea     r9, [rbp+4Fh+var_78]
0x1800d85d9  lea     rax, [rbp+4Fh+var_80]
0x1800d85dd  mov     [rbp+4Fh+arg_10], 4
0x1800d85e4  mov     [rsp+0C0h+var_A0], rax
0x1800d85e9  lea     rcx, WNF_PROV_DEVICE_BOOTSTRAP_COMPLETE
0x1800d85f0  mov     rax, [rbp+4Fh+arg_0]
0x1800d85f4  xor     r8d, r8d
0x1800d85f7  xor     edx, edx
0x1800d85f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d85fe  test    eax, eax
0x1800d8600  jns     short loc_1800D8638
0x1800d8602  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8609  cmp     rcx, rbx
0x1800d860c  jz      short loc_1800D862C
0x1800d860e  test    byte ptr [rcx+1Ch], 2
0x1800d8612  jz      short loc_1800D862C
0x1800d8614  mov     rcx, [rcx+10h]
0x1800d8618  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
  ... truncated ...
```
