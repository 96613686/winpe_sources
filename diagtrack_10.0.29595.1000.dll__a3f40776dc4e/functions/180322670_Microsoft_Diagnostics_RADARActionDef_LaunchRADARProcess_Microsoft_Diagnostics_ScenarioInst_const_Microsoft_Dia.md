# Microsoft::Diagnostics::RADARActionDef::LaunchRADARProcess(Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::EscalationWorkItemState &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::optional<unsigned __int64>)

- ea: `0x180322670`
- end: `0x180322a98`
- name: `?LaunchRADARProcess@RADARActionDef@Diagnostics@Microsoft@@SAXAEBVScenarioInst@23@AEAVEscalationWorkItemState@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2V?$optional@_K@7@@Z`
- size: `1064`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18031a910`
- `0x180322530`
- `0x180324ef0`

## callees

- `0x180020150`
- `0x1800202a4`
- `0x18002110c`
- `0x180027c28`
- `0x180027e50`
- `0x180028ba8`
- `0x18002967c`
- `0x18002ac10`
- `0x18002b9c0`
- `0x18002df00`
- `0x18009c8c0`
- `0x1800bc658`
- `0x1800cf7d8`
- `0x1800dce08`
- `0x1800e99a0`
- `0x1800f9fa8`
- `0x180135800`
- `0x180142fcc`
- `0x18016323c`
- `0x1801a9494`
- `0x1801b2084`
- `0x1801dfc6c`
- `0x18020aac0`
- `0x18020bab8`
- `0x180322670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180322a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180322a07`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180322963`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180322963`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180322739`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180322739`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1803227b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1803227b4`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1803227a2`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1803227a2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180322765`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180322765`

## string_xrefs

- `0x1803229e0`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`
- `0x1803229f2`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`
- `0x180322a6e`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`
- `0x180322a86`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::RADARActionDef::LaunchRADARProcess(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        _OWORD *a4,
        __int64 a5)
{
  DWORD v7; // edi
  void *v8; // rbx
  void *v9; // rax
  void *v10; // rax
  HANDLE v11; // rcx
  const char *v12; // r9
  WCHAR *v13; // rcx
  UINT SystemWow64Directory2W; // eax
  UINT v15; // ecx
  __int64 v16; // rdx
  LPWSTR *v17; // rax
  char v18; // al
  void *appended; // rax
  void *v20; // rax
  void *v21; // rax
  void *v22; // rax
  _QWORD *v23; // rax
  int v24; // r8d
  int v25; // r9d
  WCHAR *v26; // rdx
  const char *v27; // r9
  signed int LastError; // eax
  unsigned int v30; // ebx
  int v31; // r8d
  int v32; // r9d
  unsigned int v33; // eax
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  __int16 v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36[6]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v37; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+110h] [rbp+10h] BYREF
  UINT uSize[2]; // [rsp+120h] [rbp+20h]
  unsigned __int64 v42; // [rsp+128h] [rbp+28h]
  _OWORD v43[2]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Src[16]; // [rsp+150h] [rbp+50h] BYREF
  LPWSTR lpCommandLine[6]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  if ( *((_QWORD *)a3 + 1) )
  {
    v37 = *a3;
    Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a1, v43, &v37);
    v7 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v43);
    std::wstring::_Tidy_deallocate(v43);
  }
  else
  {
    v7 = 0;
  }
  v8 = (void *)(a2 + 168);
  v9 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v8);
  Microsoft::Diagnostics::WideStringStream::operator<<(v9);
  if ( *(_BYTE *)(a5 + 8) )
  {
    v10 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v8);
    Microsoft::Diagnostics::WideStringStream::operator<<(v10);
  }
  Microsoft::Diagnostics::WideStringStream::operator<<(v8);
  v11 = OpenProcess(0x400u, 0, v7);
  if ( !v11 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      v12);
  *(_QWORD *)&v37 = v11;
  v35 = 0;
  if ( !(unsigned int)IsWow64Process2(v11, &v35, 0) )
  {
    LastError = GetLastError();
    v30 = LastError;
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 262148) )
    {
      v36[0] = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)word_1804031CA,
        v31,
        v32,
        (__int64)v36);
    }
    v33 = wil::verify_hresult<long>(v30);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      (const char *)v33,
      bInheritHandles);
  }
  std::wstring::wstring(lpBuffer, 260, 0);
  v13 = (WCHAR *)lpBuffer;
  if ( v35 )
  {
    if ( v42 > 7 )
      v13 = lpBuffer[0];
    SystemWow64Directory2W = GetSystemWow64Directory2W(v13, uSize[0]);
  }
  else
  {
    if ( v42 > 7 )
      v13 = lpBuffer[0];
    SystemWow64Directory2W = GetSystemDirectoryW(v13, uSize[0]);
  }
  v15 = SystemWow64Directory2W;
  if ( !SystemWow64Directory2W )
    goto LABEL_21;
  v16 = SystemWow64Directory2W;
  if ( (unsigned __int64)SystemWow64Directory2W >= *(_QWORD *)uSize )
    goto LABEL_21;
  v17 = lpBuffer;
  if ( v42 > 7 )
    v17 = (LPWSTR *)lpBuffer[0];
  if ( *(_WORD *)v17 )
  {
    v18 = 0;
  }
  else
  {
LABEL_21:
    v18 = 1;
    v16 = v15;
  }
  if ( v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      (const char *)0x800700A1LL,
      bInheritHandles);
  std::wstring::resize(lpBuffer, v16);
  std::wstring::wstring(Src, lpBuffer);
  *(_QWORD *)&v43[0] = L"RdrLeakDiag.exe";
  *((_QWORD *)&v43[0] + 1) = 15;
  Microsoft::Diagnostics::Utils::String::AppendPath(Src, v43);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpCommandLine);
  v43[0] = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v36);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
  v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  v21 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v20);
  v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v21);
  v43[0] = *a4;
  Microsoft::Diagnostics::WideStringStream::AppendString(v22);
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 262148) )
  {
    v23 = (_QWORD *)Microsoft::Diagnostics::WideStringStream::str(lpCommandLine, v43);
    if ( v23[3] > 7u )
      v23 = (_QWORD *)*v23;
    *(_QWORD *)v36 = v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_1804543B0,
      (unsigned int)&word_180403196,
      v24,
      v25,
      (__int64)v36);
    std::wstring::_Tidy_deallocate(v43);
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v26 = (WCHAR *)lpCommandLine;
  if ( lpCommandLine[3] > (LPWSTR)7 )
    v26 = lpCommandLine[0];
  if ( !CreateProcessW(0, v26, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      v27);
  *(_QWORD *)&v43[0] = ProcessInformation.hProcess;
  *(_QWORD *)v36 = ProcessInformation.hThread;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v43);
  std::wstring::_Tidy_deallocate(lpCommandLine);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(lpBuffer);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
}

```

## disassembly

```asm
0x180322670  push    rbp
0x180322672  push    rbx
0x180322673  push    rsi
0x180322674  push    rdi
0x180322675  push    r14
0x180322677  push    r15
0x180322679  lea     rbp, [rsp-0B8h]
0x180322681  sub     rsp, 1B8h
0x180322688  mov     rax, cs:__security_cookie
0x18032268f  xor     rax, rsp
0x180322692  mov     [rbp+0E0h+var_40], rax
0x180322699  mov     r14, r9
0x18032269c  mov     rbx, rdx
0x18032269f  mov     rsi, [rbp+0E0h+arg_20]
0x1803226a6  xor     r15d, r15d
0x1803226a9  cmp     [r8+8], r15
0x1803226ad  jnz     short loc_1803226B4
0x1803226af  mov     edi, r15d
0x1803226b2  jmp     short loc_1803226E0
0x1803226b4  movups  xmm0, xmmword ptr [r8]
0x1803226b8  movdqu  [rsp+1E0h+var_170], xmm0
0x1803226be  lea     r8, [rsp+1E0h+var_170]
0x1803226c3  lea     rdx, [rbp+0E0h+var_B0]
0x1803226c7  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x1803226cc  lea     rcx, [rbp+0E0h+var_B0]
0x1803226d0  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1803226d5  mov     edi, eax
0x1803226d7  lea     rcx, [rbp+0E0h+var_B0]
0x1803226db  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803226e0  add     rbx, 0A8h
0x1803226e7  lea     rdx, aPid_4; "PID: "
0x1803226ee  mov     rcx, rbx; Src
0x1803226f1  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1803226f6  mov     edx, edi
0x1803226f8  mov     rcx, rax; Src
0x1803226fb  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180322700  cmp     [rsi+8], r15b
0x180322704  jz      short loc_180322720
0x180322706  lea     rdx, aWaitTimeMin; "; Wait Time (min): "
0x18032270d  mov     rcx, rbx; Src
0x180322710  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180322715  mov     rdx, [rsi]
0x180322718  mov     rcx, rax; Src
0x18032271b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x180322720  lea     rdx, asc_1803A0CBC; "\r\n"
0x180322727  mov     rcx, rbx; Src
0x18032272a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032272f  mov     r8d, edi; dwProcessId
0x180322732  xor     edx, edx; bInheritHandle
0x180322734  mov     ecx, 400h; dwDesiredAccess
0x180322739  call    cs:__imp_OpenProcess
0x18032273f  mov     rcx, rax
0x180322742  mov     rax, [rbp+0E8h]
0x180322749  test    rcx, rcx
0x18032274c  jz      loc_1803229F2
0x180322752  mov     qword ptr [rsp+1E0h+var_170], rcx
0x180322757  mov     [rsp+1E0h+var_190], r15w
0x18032275d  xor     r8d, r8d
0x180322760  lea     rdx, [rsp+1E0h+var_190]
0x180322765  call    cs:__imp_IsWow64Process2
0x18032276b  test    eax, eax
0x18032276d  jz      loc_180322A07
0x180322773  xor     r8d, r8d
0x180322776  mov     edx, 104h
0x18032277b  lea     rcx, [rbp+0E0h+lpBuffer]
0x18032277f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180322784  nop
0x180322785  movzx   r8d, [rsp+1E0h+var_190]
0x18032278b  lea     rcx, [rbp+0E0h+lpBuffer]
0x18032278f  mov     edx, [rbp+0E0h+uSize]; uSize
0x180322792  test    r8w, r8w
0x180322796  jz      short loc_1803227AA
0x180322798  cmp     [rbp+0E0h+var_B8], 7
0x18032279d  cmova   rcx, [rbp+0E0h+lpBuffer]
0x1803227a2  call    cs:__imp_GetSystemWow64Directory2W
0x1803227a8  jmp     short loc_1803227BA
0x1803227aa  cmp     [rbp+0E0h+var_B8], 7
0x1803227af  cmova   rcx, [rbp+0E0h+lpBuffer]; lpBuffer
0x1803227b4  call    cs:__imp_GetSystemDirectoryW
0x1803227ba  mov     ecx, eax
0x1803227bc  test    eax, eax
0x1803227be  jz      short loc_1803227E1
0x1803227c0  mov     edx, eax
0x1803227c2  cmp     rdx, qword ptr [rbp+0E0h+uSize]
0x1803227c6  jnb     short loc_1803227E1
0x1803227c8  lea     rax, [rbp+0E0h+lpBuffer]
0x1803227cc  cmp     [rbp+0E0h+var_B8], 7
0x1803227d1  cmova   rax, [rbp+0E0h+lpBuffer]
0x1803227d6  cmp     [rax], r15w
0x1803227da  jz      short loc_1803227E1
0x1803227dc  mov     al, r15b
0x1803227df  jmp     short loc_1803227E5
0x1803227e1  mov     al, 1
0x1803227e3  mov     edx, ecx
0x1803227e5  mov     rcx, [rbp+0E8h]; this
0x1803227ec  test    al, al
0x1803227ee  jnz     loc_180322A80
0x1803227f4  lea     rcx, [rbp+0E0h+lpBuffer]
0x1803227f8  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1803227fd  lea     rdx, [rbp+0E0h+lpBuffer]
0x180322801  lea     rcx, [rbp+0E0h+Src]
0x180322805  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18032280a  nop
0x18032280b  lea     rax, aRdrleakdiagExe; "RdrLeakDiag.exe"
0x180322812  mov     qword ptr [rbp+0E0h+var_B0], rax
0x180322816  mov     qword ptr [rbp+0E0h+var_B0+8], 0Fh
0x18032281e  lea     rdx, [rbp+0E0h+var_B0]
0x180322822  lea     rcx, [rbp+0E0h+Src]
0x180322826  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18032282b  xor     r8d, r8d
0x18032282e  mov     dl, 1
0x180322830  lea     rcx, [rbp+0E0h+Src]; lpSrc
0x180322834  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180322839  lea     rcx, [rbp+0E0h+lpCommandLine]; this
0x18032283d  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x180322842  nop
0x180322843  lea     rdx, [rsp+1E0h+var_188]
0x180322848  lea     rcx, [rbp+0E0h+Src]
0x18032284c  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180322851  movups  xmm0, xmmword ptr [rax]
0x180322854  movdqu  [rbp+0E0h+var_B0], xmm0
0x180322859  lea     rdx, [rbp+0E0h+var_B0]
0x18032285d  lea     rcx, [rbp+0E0h+lpCommandLine]; Src
0x180322861  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x180322866  lea     rdx, aP; " -p "
0x18032286d  mov     rcx, rax; Src
0x180322870  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180322875  mov     edx, edi
0x180322877  mov     rcx, rax; Src
0x18032287a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032287f  lea     rdx, asc_1803933B4; " "
0x180322886  mov     rcx, rax; Src
0x180322889  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032288e  movups  xmm0, xmmword ptr [r14]
0x180322892  movdqu  [rbp+0E0h+var_B0], xmm0
0x180322897  lea     rdx, [rbp+0E0h+var_B0]
0x18032289b  mov     rcx, rax; Src
0x18032289e  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1803228a3  mov     eax, cs:dword_1804543B0
0x1803228a9  cmp     eax, 4
0x1803228ac  jbe     short loc_180322905
0x1803228ae  mov     edx, 40004h
0x1803228b3  lea     rcx, dword_1804543B0
0x1803228ba  call    _tlgKeywordOn
0x1803228bf  test    al, al
0x1803228c1  jz      short loc_180322905
0x1803228c3  lea     rdx, [rbp+0E0h+var_B0]
0x1803228c7  lea     rcx, [rbp+0E0h+lpCommandLine]
0x1803228cb  call    ?str@WideStringStream@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::WideStringStream::str(void)
0x1803228d0  cmp     qword ptr [rax+18h], 7
0x1803228d5  jbe     short loc_1803228DA
0x1803228d7  mov     rax, [rax]
0x1803228da  mov     qword ptr [rsp+1E0h+var_188], rax
0x1803228df  lea     rax, [rsp+1E0h+var_188]
0x1803228e4  mov     qword ptr [rsp+1E0h+bInheritHandles], rax
0x1803228e9  lea     rdx, word_180403196
0x1803228f0  lea     rcx, dword_1804543B0
0x1803228f7  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1803228fc  lea     rcx, [rbp+0E0h+var_B0]
0x180322900  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180322905  xor     edx, edx; Val
0x180322907  lea     r8d, [rdx+68h]; Size
0x18032290b  lea     rcx, [rbp+0E0h+StartupInfo]; void *
0x18032290f  call    memset_0
0x180322914  xorps   xmm0, xmm0
0x180322917  xor     eax, eax
0x180322919  movups  xmmword ptr [rbp+0E0h+ProcessInformation.hProcess], xmm0
0x18032291d  mov     qword ptr [rbp+0E0h+ProcessInformation.dwProcessId], rax
0x180322921  lea     rdx, [rbp+0E0h+lpCommandLine]
0x180322925  cmp     [rbp+0E0h+var_58], 7
0x18032292d  cmova   rdx, [rbp+0E0h+lpCommandLine]; lpCommandLine
0x180322932  lea     rax, [rbp+0E0h+ProcessInformation]
0x180322936  mov     [rsp+1E0h+lpProcessInformation], rax; lpProcessInformation
0x18032293b  lea     rax, [rbp+0E0h+StartupInfo]
0x18032293f  mov     [rsp+1E0h+lpStartupInfo], rax; lpStartupInfo
0x180322944  mov     [rsp+1E0h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180322949  mov     [rsp+1E0h+lpEnvironment], r15; lpEnvironment
0x18032294e  mov     [rsp+1E0h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x180322956  mov     [rsp+1E0h+bInheritHandles], r15d; bInheritHandles
0x18032295b  xor     r9d, r9d; lpThreadAttributes
0x18032295e  xor     r8d, r8d; lpProcessAttributes
0x180322961  xor     ecx, ecx; lpApplicationName
0x180322963  call    cs:__imp_CreateProcessW
0x180322969  mov     rcx, [rbp+0E8h]; this
0x180322970  test    eax, eax
0x180322972  jz      short loc_1803229E0
0x180322974  mov     rax, [rbp+0E0h+ProcessInformation.hProcess]
0x180322978  mov     qword ptr [rbp+0E0h+var_B0], rax
0x18032297c  mov     rax, [rbp+0E0h+ProcessInformation.hThread]
0x180322980  mov     qword ptr [rsp+1E0h+var_188], rax
0x180322985  lea     rcx, [rsp+1E0h+var_188]
0x18032298a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18032298f  lea     rcx, [rbp+0E0h+var_B0]
0x180322993  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180322998  nop
0x180322999  lea     rcx, [rbp+0E0h+lpCommandLine]
0x18032299d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803229a2  nop
0x1803229a3  lea     rcx, [rbp+0E0h+Src]
0x1803229a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803229ac  nop
0x1803229ad  lea     rcx, [rbp+0E0h+lpBuffer]
0x1803229b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803229b6  nop
0x1803229b7  lea     rcx, [rsp+1E0h+var_170]
0x1803229bc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1803229c1  mov     rcx, [rbp+0E0h+var_40]
0x1803229c8  xor     rcx, rsp; StackCookie
0x1803229cb  call    __security_check_cookie
0x1803229d0  add     rsp, 1B8h
0x1803229d7  pop     r15
0x1803229d9  pop     r14
0x1803229db  pop     rdi
0x1803229dc  pop     rsi
0x1803229dd  pop     rbx
0x1803229de  pop     rbp
0x1803229df  retn
0x1803229e0  lea     r8, aOnecoreBaseTel_270; "onecore\\base\\telemetry\\utc\\service"...
0x1803229e7  mov     edx, 13Ah; void *
0x1803229ec  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1803229f2  lea     r8, aOnecoreBaseTel_270; "onecore\\base\\telemetry\\utc\\service"...
0x1803229f9  mov     edx, 0FCh; void *
0x1803229fe  mov     rcx, rax; this
0x180322a01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180322a07  call    cs:__imp_GetLastError
0x180322a0d  mov     ebx, eax
0x180322a0f  test    eax, eax
0x180322a11  jle     short loc_180322A1C
0x180322a13  movzx   ebx, ax
0x180322a16  or      ebx, 80070000h
0x180322a1c  mov     eax, cs:dword_1804543B0
0x180322a22  cmp     eax, 2
0x180322a25  jbe     short loc_180322A5D
0x180322a27  mov     edx, 40004h
0x180322a2c  lea     rcx, dword_1804543B0
0x180322a33  call    _tlgKeywordOn
0x180322a38  test    al, al
0x180322a3a  jz      short loc_180322A5D
0x180322a3c  mov     [rsp+1E0h+var_188], ebx
0x180322a40  lea     rax, [rsp+1E0h+var_188]
0x180322a45  mov     qword ptr [rsp+1E0h+bInheritHandles], rax; int
0x180322a4a  lea     rdx, word_1804031CA
0x180322a51  lea     rcx, dword_1804543B0
0x180322a58  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180322a5d  mov     ecx, ebx
0x180322a5f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180322a64  mov     r9d, eax; char *
0x180322a67  mov     rcx, [rbp+0E8h]; this
0x180322a6e  lea     r8, aOnecoreBaseTel_270; "onecore\\base\\telemetry\\utc\\service"...
0x180322a75  mov     edx, 10Fh; void *
0x180322a7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180322a80  mov     r9d, 800700A1h; char *
0x180322a86  lea     r8, aOnecoreBaseTel_270; "onecore\\base\\telemetry\\utc\\service"...
0x180322a8d  mov     edx, 11Eh; void *
0x180322a92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
