# Microsoft::Diagnostics::Utils::Os::GetRunningPidsWithModuleRegex(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::set<ulong,std::less<ulong>,std::allocator<ulong>> &,Microsoft::Diagnostics::EscalationWorkItemState *)

- ea: `0x18032b2b8`
- end: `0x18032b932`
- name: `?GetRunningPidsWithModuleRegex@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$set@KU?$less@K@std@@V?$allocator@K@2@@6@PEAVEscalationWorkItemState@34@@Z`
- size: `1658`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18032a8e0`

## callees

- `0x180027c28`
- `0x18002967c`
- `0x18006b958`
- `0x18008abf4`
- `0x1800d5488`
- `0x1800f7f64`
- `0x18019b4b0`
- `0x1801dcaf8`
- `0x18020aac0`
- `0x18020bab8`
- `0x18031b284`
- `0x18032b2b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b5ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b82d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b5ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18032b82d`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18032b331`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18032b331`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18032b2f8`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18032b45b`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18032b2f8`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18032b45b`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18032b531`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18032b531`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18032b49e`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18032b49e`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18032b69e`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18032b69e`

## string_xrefs

- `0x18032b429`: `), path(`
- `0x18032b847`: `Failed to create process snapshot: 0x`
- `0x18032b604`: `Failed to create module snapshot: 0x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetRunningPidsWithModuleRegex(_QWORD *a1, __int64 a2, __int64 a3)
{
  char *Toolhelp32Snapshot; // rdi
  unsigned int v6; // esi
  DWORD LastError; // ebx
  __int64 v8; // rax
  void *v9; // rax
  __int64 v10; // rax
  void *v11; // rax
  __int64 v12; // rdx
  void *v13; // rax
  void *v14; // rax
  void *v15; // rax
  void *v16; // rax
  char *v17; // rbx
  __int64 v18; // rdi
  void *v19; // rax
  void *v20; // rax
  __int64 v21; // rax
  void *v22; // rax
  __int64 v23; // rax
  void *v24; // rax
  __int64 v25; // rax
  void *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  void *v29; // rax
  __int64 v30; // rax
  void *v31; // rax
  DWORD v32; // ebx
  __int64 v33; // rax
  void *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  void *v37; // rax
  __int64 v38; // rax
  void *v39; // rax
  unsigned int v41; // [rsp+20h] [rbp-E0h] BYREF
  int v42; // [rsp+24h] [rbp-DCh]
  __int64 v43; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v44; // [rsp+31h] [rbp-CFh]
  __int16 v45; // [rsp+32h] [rbp-CEh]
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h]
  _QWORD v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v49; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v50; // [rsp+61h] [rbp-9Fh]
  char v51; // [rsp+63h] [rbp-9Dh]
  int v52; // [rsp+64h] [rbp-9Ch]
  __int64 v53; // [rsp+68h] [rbp-98h]
  char v54; // [rsp+70h] [rbp-90h] BYREF
  __int16 v55; // [rsp+71h] [rbp-8Fh]
  char v56; // [rsp+73h] [rbp-8Dh]
  int v57; // [rsp+74h] [rbp-8Ch]
  __int64 v58; // [rsp+78h] [rbp-88h]
  char v59; // [rsp+80h] [rbp-80h] BYREF
  __int16 v60; // [rsp+81h] [rbp-7Fh]
  char v61; // [rsp+83h] [rbp-7Dh]
  int v62; // [rsp+84h] [rbp-7Ch]
  __int64 v63; // [rsp+88h] [rbp-78h]
  HANDLE hSnapshot; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v65; // [rsp+99h] [rbp-67h]
  __int16 v66; // [rsp+9Ah] [rbp-66h]
  unsigned __int8 v67; // [rsp+A9h] [rbp-57h]
  __int16 v68; // [rsp+AAh] [rbp-56h]
  unsigned __int8 v69; // [rsp+B9h] [rbp-47h]
  __int16 v70; // [rsp+BAh] [rbp-46h]
  _BYTE v71[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v72[16]; // [rsp+F0h] [rbp-10h] BYREF
  PROCESSENTRY32W pe; // [rsp+100h] [rbp+0h] BYREF
  MODULEENTRY32W me; // [rsp+340h] [rbp+240h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7C8h] [rbp+6C8h]

  v46 = a2;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  hSnapshot = Toolhelp32Snapshot;
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset_0(&pe.cntUsage, 0, 0x234u);
    pe.dwSize = 568;
    v6 = 0;
    if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
    {
      LastError = GetLastError();
      if ( a3 )
      {
        v8 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        LOBYTE(v46) = 1;
        *(_WORD *)((char *)&v46 + 1) = BYTE1(v41);
        BYTE3(v46) = 0;
        HIDWORD(v46) = 2097153;
        v47 = 0;
        v9 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v8, &v46);
        v10 = Microsoft::Diagnostics::WideStringStream::operator<<(v9);
        HIWORD(v41) = 0;
        LOBYTE(v46) = 1;
        *(_WORD *)((char *)&v46 + 1) = BYTE1(v41);
        BYTE3(v46) = 0;
        HIDWORD(v46) = 0x200000;
        v47 = 0;
        v11 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v10, &v46);
        Microsoft::Diagnostics::WideStringStream::operator<<(v11);
      }
      if ( !LastError )
        goto LABEL_37;
      v12 = 1618;
LABEL_36:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
             (const char *)LastError,
             v41);
      goto LABEL_37;
    }
    while ( 1 )
    {
      if ( a3 )
      {
        v13 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        v14 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v13);
        v15 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v14);
        v16 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v15);
        Microsoft::Diagnostics::WideStringStream::operator<<(v16);
      }
      v17 = (char *)CreateToolhelp32Snapshot(8u, pe.th32ProcessID);
      v48[0] = v17;
      if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        GetLastError();
        if ( a3 )
        {
          v25 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
          v70 = 0;
          v59 = 1;
          v60 = v69;
          v61 = 0;
          v62 = 2097153;
          v63 = 0;
          v26 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v25, &v59);
          v27 = Microsoft::Diagnostics::WideStringStream::operator<<(v26);
          v45 = 0;
          LOBYTE(v41) = 1;
          *(_WORD *)((char *)&v41 + 1) = v44;
          HIBYTE(v41) = 0;
          v42 = 0x200000;
          v43 = 0;
          v24 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v27, &v41);
          goto LABEL_22;
        }
      }
      else
      {
        memset_0(&me.th32ModuleID, 0, 0x434u);
        me.dwSize = 1080;
        if ( !Module32FirstW(v17, &me) )
        {
          v32 = GetLastError();
          if ( a3 )
          {
            v33 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
            v45 = 0;
            LOBYTE(v41) = 1;
            *(_WORD *)((char *)&v41 + 1) = v44;
            HIBYTE(v41) = 0;
            v42 = 2097153;
            v43 = 0;
            v34 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v33, &v41);
            v35 = Microsoft::Diagnostics::WideStringStream::operator<<(v34);
            v45 = 0;
            LOBYTE(v41) = 1;
            *(_WORD *)((char *)&v41 + 1) = v44;
            HIBYTE(v41) = 0;
            v42 = 0x200000;
            v43 = 0;
            Microsoft::Diagnostics::WideStringStream::operator<<(v35, &v41);
          }
          if ( v32 )
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x671,
                   (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                   (const char *)v32,
                   v41);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(v48);
          goto LABEL_37;
        }
        v18 = v46;
        do
        {
          std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(
            v71,
            *a1,
            a1[1]);
          if ( (unsigned __int8)std::regex_search<wchar_t,std::regex_traits<wchar_t>>(me.szModule, v71) )
          {
            if ( a3 )
            {
              v19 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
              v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v19);
              Microsoft::Diagnostics::WideStringStream::operator<<(v20);
            }
            std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::emplace<unsigned long &>(
              v18,
              v72,
              &pe.th32ProcessID);
          }
          std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v71);
        }
        while ( Module32NextW(v17, &me) );
        Toolhelp32Snapshot = (char *)hSnapshot;
        if ( GetLastError() != 18 && a3 )
        {
          v21 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
          v66 = 0;
          v49 = 1;
          v50 = v65;
          v51 = 0;
          v52 = 2097153;
          v53 = 0;
          v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v21, &v49);
          v23 = Microsoft::Diagnostics::WideStringStream::operator<<(v22);
          v68 = 0;
          v54 = 1;
          v55 = v67;
          v56 = 0;
          v57 = 0x200000;
          v58 = 0;
          v24 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v23, &v54);
LABEL_22:
          Microsoft::Diagnostics::WideStringStream::operator<<(v24);
        }
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(v48);
      if ( !Process32NextW(Toolhelp32Snapshot, &pe) )
      {
        if ( GetLastError() != 18 && a3 )
        {
          v28 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
          v45 = 0;
          LOBYTE(v41) = 1;
          *(_WORD *)((char *)&v41 + 1) = v44;
          HIBYTE(v41) = 0;
          v42 = 2097153;
          v43 = 0;
          v29 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v28, &v41);
          v30 = Microsoft::Diagnostics::WideStringStream::operator<<(v29);
          v45 = 0;
          LOBYTE(v41) = 1;
          *(_WORD *)((char *)&v41 + 1) = v44;
          HIBYTE(v41) = 0;
          v42 = 0x200000;
          v43 = 0;
          v31 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v30, &v41);
          Microsoft::Diagnostics::WideStringStream::operator<<(v31);
        }
        goto LABEL_37;
      }
    }
  }
  LastError = GetLastError();
  v6 = 0;
  if ( a3 )
  {
    v36 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    v45 = 0;
    LOBYTE(v41) = 1;
    *(_WORD *)((char *)&v41 + 1) = v44;
    HIBYTE(v41) = 0;
    v42 = 2097153;
    v43 = 0;
    v37 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v36, &v41);
    v38 = Microsoft::Diagnostics::WideStringStream::operator<<(v37);
    v45 = 0;
    LOBYTE(v41) = 1;
    *(_WORD *)((char *)&v41 + 1) = v44;
    HIBYTE(v41) = 0;
    v42 = 0x200000;
    v43 = 0;
    v39 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v38, &v41);
    Microsoft::Diagnostics::WideStringStream::operator<<(v39);
  }
  if ( LastError )
  {
    v12 = 1606;
    goto LABEL_36;
  }
LABEL_37:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&hSnapshot);
  return v6;
}

```

## disassembly

```asm
0x18032b2b8  mov     [rsp-8+arg_18], rbx
0x18032b2bd  push    rbp
0x18032b2be  push    rsi
0x18032b2bf  push    rdi
0x18032b2c0  push    r12
0x18032b2c2  push    r13
0x18032b2c4  push    r14
0x18032b2c6  push    r15
0x18032b2c8  lea     rbp, [rsp-690h]
0x18032b2d0  sub     rsp, 790h
0x18032b2d7  mov     rax, cs:__security_cookie
0x18032b2de  xor     rax, rsp
0x18032b2e1  mov     [rbp+6C0h+var_40], rax
0x18032b2e8  mov     r14, r8
0x18032b2eb  mov     [rsp+7C0h+var_780], rdx
0x18032b2f0  mov     r13, rcx
0x18032b2f3  xor     edx, edx; th32ProcessID
0x18032b2f5  lea     ecx, [rdx+2]; dwFlags
0x18032b2f8  call    cs:__imp_CreateToolhelp32Snapshot
0x18032b2fe  mov     rdi, rax
0x18032b301  mov     [rbp+6C0h+hSnapshot], rax
0x18032b305  dec     rax
0x18032b308  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18032b30c  ja      loc_18032B82D
0x18032b312  xor     edx, edx; Val
0x18032b314  mov     r8d, 234h; Size
0x18032b31a  lea     rcx, [rbp+6C0h+pe.cntUsage]; void *
0x18032b31e  call    memset_0
0x18032b323  mov     [rbp+6C0h+pe.dwSize], 238h
0x18032b32a  lea     rdx, [rbp+6C0h+pe]; lppe
0x18032b32e  mov     rcx, rdi; hSnapshot
0x18032b331  call    cs:__imp_Process32FirstW
0x18032b337  xor     esi, esi
0x18032b339  test    eax, eax
0x18032b33b  jnz     loc_18032B400
0x18032b341  call    cs:__imp_GetLastError
0x18032b347  mov     ebx, eax
0x18032b349  test    r14, r14
0x18032b34c  jz      loc_18032B3EE
0x18032b352  lea     rcx, [r14+0A8h]; Src
0x18032b359  lea     rdx, aFailedToEnumer_0; "Failed to enumerate processes (1): 0x"
0x18032b360  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b365  mov     word ptr [rsp+7C0h+var_7A0+2], si
0x18032b36a  lea     r15d, [rsi+1]
0x18032b36e  mov     byte ptr [rsp+7C0h+var_780], r15b
0x18032b373  movzx   ecx, word ptr [rsp+21h]
0x18032b378  mov     word ptr [rsp+7C0h+var_780+1], cx
0x18032b37d  mov     cl, byte ptr [rsp+7C0h+var_7A0+3]
0x18032b381  mov     byte ptr [rsp+7C0h+var_780+3], cl
0x18032b385  mov     dword ptr [rsp+7C0h+var_780+4], 200001h
0x18032b38d  mov     [rsp+7C0h+var_778], rsi
0x18032b392  lea     rdx, [rsp+7C0h+var_780]
0x18032b397  mov     rcx, rax
0x18032b39a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b39f  mov     edx, ebx
0x18032b3a1  mov     rcx, rax; Src
0x18032b3a4  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032b3a9  mov     word ptr [rsp+7C0h+var_7A0+2], si
0x18032b3ae  mov     byte ptr [rsp+7C0h+var_780], r15b
0x18032b3b3  movzx   ecx, word ptr [rsp+21h]
0x18032b3b8  mov     word ptr [rsp+7C0h+var_780+1], cx
0x18032b3bd  mov     cl, byte ptr [rsp+7C0h+var_7A0+3]
0x18032b3c1  mov     byte ptr [rsp+7C0h+var_780+3], cl
0x18032b3c5  mov     dword ptr [rsp+7C0h+var_780+4], 200000h
0x18032b3cd  mov     [rsp+7C0h+var_778], rsi
0x18032b3d2  lea     rdx, [rsp+7C0h+var_780]
0x18032b3d7  mov     rcx, rax
0x18032b3da  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b3df  lea     rdx, asc_1803A0CBC; "\r\n"
0x18032b3e6  mov     rcx, rax; Src
0x18032b3e9  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b3ee  test    ebx, ebx
0x18032b3f0  jz      loc_18032B8FD
0x18032b3f6  mov     edx, 652h
0x18032b3fb  jmp     loc_18032B8E5
0x18032b400  mov     r15d, 1
0x18032b406  test    r14, r14
0x18032b409  jz      short loc_18032B453
0x18032b40b  lea     rcx, [r14+0A8h]; Src
0x18032b412  lea     rdx, aEnumeratingMod; "Enumerating modules for pid("
0x18032b419  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b41e  mov     edx, [rbp+6C0h+pe.th32ProcessID]
0x18032b421  mov     rcx, rax; Src
0x18032b424  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032b429  lea     rdx, aPath_1; "), path("
0x18032b430  mov     rcx, rax; Src
0x18032b433  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b438  lea     rdx, [rbp+6C0h+pe.szExeFile]
0x18032b43c  mov     rcx, rax; Src
0x18032b43f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b444  lea     rdx, asc_1803D9880; ")\r\n"
0x18032b44b  mov     rcx, rax; Src
0x18032b44e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b453  mov     edx, [rbp+6C0h+pe.th32ProcessID]; th32ProcessID
0x18032b456  mov     ecx, 8; dwFlags
0x18032b45b  call    cs:__imp_CreateToolhelp32Snapshot
0x18032b461  mov     rbx, rax
0x18032b464  mov     [rsp+7C0h+var_770], rax
0x18032b469  dec     rax
0x18032b46c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18032b470  ja      loc_18032B5EC
0x18032b476  xor     edx, edx; Val
0x18032b478  mov     r8d, 434h; Size
0x18032b47e  lea     rcx, [rbp+6C0h+me.th32ModuleID]; void *
0x18032b485  call    memset_0
0x18032b48a  mov     [rbp+6C0h+me.dwSize], 438h
0x18032b494  lea     rdx, [rbp+6C0h+me]; lpme
0x18032b49b  mov     rcx, rbx; hSnapshot
0x18032b49e  call    cs:__imp_Module32FirstW
0x18032b4a4  test    eax, eax
0x18032b4a6  jz      loc_18032B763
0x18032b4ac  mov     rdi, [rsp+7C0h+var_780]
0x18032b4b1  mov     r8, [r13+8]
0x18032b4b5  mov     rdx, [r13+0]
0x18032b4b9  lea     rcx, [rbp+6C0h+var_6F8]
0x18032b4bd  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_W_KW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,unsigned __int64,std::regex_constants::syntax_option_type)
0x18032b4c2  nop
0x18032b4c3  lea     rdx, [rbp+6C0h+var_6F8]
0x18032b4c7  lea     rcx, [rbp+6C0h+me.szModule]
0x18032b4ce  call    ??$regex_search@_WV?$regex_traits@_W@std@@@std@@YA_NPEB_WAEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x18032b4d3  test    al, al
0x18032b4d5  jz      short loc_18032B51E
0x18032b4d7  test    r14, r14
0x18032b4da  jz      short loc_18032B50D
0x18032b4dc  lea     rcx, [r14+0A8h]; Src
0x18032b4e3  lea     rdx, aFoundMatchingM; "Found matching module "
0x18032b4ea  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b4ef  lea     rdx, [rbp+6C0h+me.szModule]
0x18032b4f6  mov     rcx, rax; Src
0x18032b4f9  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b4fe  lea     rdx, asc_1803A0CBC; "\r\n"
0x18032b505  mov     rcx, rax; Src
0x18032b508  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b50d  lea     r8, [rbp+6C0h+pe.th32ProcessID]
0x18032b511  lea     rdx, [rbp+6C0h+var_6D0]
0x18032b515  mov     rcx, rdi
0x18032b518  call    ??$emplace@AEAK@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@AEAK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::emplace<ulong &>(ulong &)
0x18032b51d  nop
0x18032b51e  lea     rcx, [rbp+6C0h+var_6F8]
0x18032b522  call    ??1?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@XZ; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(void)
0x18032b527  lea     rdx, [rbp+6C0h+me]; lpme
0x18032b52e  mov     rcx, rbx; hSnapshot
0x18032b531  call    cs:__imp_Module32NextW
0x18032b537  test    eax, eax
0x18032b539  jnz     loc_18032B4B1
0x18032b53f  mov     rdi, [rbp+6C0h+hSnapshot]
0x18032b543  call    cs:__imp_GetLastError
0x18032b549  mov     ebx, eax
0x18032b54b  cmp     eax, 12h
0x18032b54e  jz      loc_18032B68D
0x18032b554  test    r14, r14
0x18032b557  jz      loc_18032B68D
0x18032b55d  lea     rcx, [r14+0A8h]; Src
0x18032b564  lea     rdx, aFailedToEnumer_2; "Failed to enumerate modules (2): 0x"
0x18032b56b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b570  mov     [rbp+6C0h+var_726], si
0x18032b574  mov     [rsp+7C0h+var_760], r15b
0x18032b579  movzx   ecx, word ptr [rbp-67h]
0x18032b57d  mov     [rsp+7C0h+var_75F], cx
0x18032b582  mov     cl, byte ptr [rbp+6C0h+var_726+1]
0x18032b585  mov     [rsp+7C0h+var_75D], cl
0x18032b589  mov     [rsp+7C0h+var_75C], 200001h
0x18032b591  mov     [rsp+7C0h+var_758], rsi
0x18032b596  lea     rdx, [rsp+7C0h+var_760]
0x18032b59b  mov     rcx, rax
0x18032b59e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b5a3  mov     edx, ebx
0x18032b5a5  mov     rcx, rax; Src
0x18032b5a8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032b5ad  mov     [rbp+6C0h+var_716], si
0x18032b5b1  mov     [rsp+7C0h+var_750], r15b
0x18032b5b6  movzx   ecx, word ptr [rbp-57h]
0x18032b5ba  mov     [rsp+7C0h+var_74F], cx
0x18032b5bf  mov     cl, byte ptr [rbp+6C0h+var_716+1]
0x18032b5c2  mov     [rsp+7C0h+var_74D], cl
0x18032b5c6  mov     [rsp+7C0h+var_74C], 200000h
0x18032b5ce  mov     [rsp+7C0h+var_748], rsi
0x18032b5d3  lea     rdx, [rsp+7C0h+var_750]
0x18032b5d8  mov     rcx, rax
0x18032b5db  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b5e0  lea     rdx, aNonFatal_1; ". Non-fatal...\r\n"
0x18032b5e7  jmp     loc_18032B684
0x18032b5ec  call    cs:__imp_GetLastError
0x18032b5f2  mov     ebx, eax
0x18032b5f4  test    r14, r14
0x18032b5f7  jz      loc_18032B68D
0x18032b5fd  lea     rcx, [r14+0A8h]; Src
0x18032b604  lea     rdx, aFailedToCreate; "Failed to create module snapshot: 0x"
0x18032b60b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b610  mov     [rbp+6C0h+var_706], si
0x18032b614  mov     [rbp+6C0h+var_740], r15b
0x18032b618  movzx   ecx, word ptr [rbp-47h]
0x18032b61c  mov     [rbp+6C0h+var_73F], cx
0x18032b620  mov     cl, byte ptr [rbp+6C0h+var_706+1]
0x18032b623  mov     [rbp+6C0h+var_73D], cl
0x18032b626  mov     [rbp+6C0h+var_73C], 200001h
0x18032b62d  mov     [rbp+6C0h+var_738], rsi
0x18032b631  lea     rdx, [rbp+6C0h+var_740]
0x18032b635  mov     rcx, rax
0x18032b638  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b63d  mov     edx, ebx
0x18032b63f  mov     rcx, rax; Src
0x18032b642  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032b647  mov     [rsp+7C0h+var_78E], si
0x18032b64c  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x18032b651  movzx   ecx, word ptr [rsp+31h]
0x18032b656  mov     [rsp+21h], cx
0x18032b65b  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x18032b65f  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x18032b663  mov     [rsp+7C0h+var_79C], 200000h
0x18032b66b  mov     [rsp+7C0h+var_798], rsi
0x18032b670  lea     rdx, [rsp+7C0h+var_7A0]
0x18032b675  mov     rcx, rax
0x18032b678  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b67d  lea     rdx, aSkipping; ". Skipping...\r\n"
0x18032b684  mov     rcx, rax; Src
0x18032b687  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b68c  nop
0x18032b68d  lea     rcx, [rsp+7C0h+var_770]
0x18032b692  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@$$A6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>(void)
0x18032b697  lea     rdx, [rbp+6C0h+pe]; lppe
0x18032b69b  mov     rcx, rdi; hSnapshot
0x18032b69e  call    cs:__imp_Process32NextW
0x18032b6a4  test    eax, eax
0x18032b6a6  jnz     loc_18032B406
0x18032b6ac  call    cs:__imp_GetLastError
0x18032b6b2  mov     ebx, eax
0x18032b6b4  cmp     eax, 12h
0x18032b6b7  jz      loc_18032B8FD
0x18032b6bd  test    r14, r14
0x18032b6c0  jz      loc_18032B8FD
0x18032b6c6  lea     rcx, [r14+0A8h]; Src
0x18032b6cd  lea     rdx, aFailedToEnumer_1; "Failed to enumerate processes (2): 0x"
0x18032b6d4  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b6d9  mov     [rsp+7C0h+var_78E], si
0x18032b6de  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x18032b6e3  movzx   ecx, word ptr [rsp+31h]
0x18032b6e8  mov     [rsp+21h], cx
0x18032b6ed  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x18032b6f1  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x18032b6f5  mov     [rsp+7C0h+var_79C], 200001h
0x18032b6fd  mov     [rsp+7C0h+var_798], rsi
0x18032b702  lea     rdx, [rsp+7C0h+var_7A0]
0x18032b707  mov     rcx, rax
0x18032b70a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b70f  mov     edx, ebx
0x18032b711  mov     rcx, rax; Src
0x18032b714  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032b719  mov     [rsp+7C0h+var_78E], si
0x18032b71e  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x18032b723  movzx   ecx, word ptr [rsp+31h]
0x18032b728  mov     [rsp+21h], cx
0x18032b72d  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x18032b731  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x18032b735  mov     [rsp+7C0h+var_79C], 200000h
0x18032b73d  mov     [rsp+7C0h+var_798], rsi
0x18032b742  lea     rdx, [rsp+7C0h+var_7A0]
0x18032b747  mov     rcx, rax
0x18032b74a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b74f  lea     rdx, aNonFatal_1; ". Non-fatal...\r\n"
0x18032b756  mov     rcx, rax; Src
0x18032b759  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b75e  jmp     loc_18032B8FD
0x18032b763  call    cs:__imp_GetLastError
0x18032b769  mov     ebx, eax
0x18032b76b  test    r14, r14
0x18032b76e  jz      loc_18032B7FD
0x18032b774  lea     rcx, [r14+0A8h]; Src
0x18032b77b  lea     rdx, aFailedToEnumer; "Failed to enumerate modules (1): 0x"
0x18032b782  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032b787  mov     [rsp+7C0h+var_78E], si
0x18032b78c  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x18032b791  movzx   ecx, word ptr [rsp+31h]
0x18032b796  mov     [rsp+21h], cx
0x18032b79b  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x18032b79f  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x18032b7a3  mov     [rsp+7C0h+var_79C], 200001h
0x18032b7ab  mov     [rsp+7C0h+var_798], rsi
0x18032b7b0  lea     rdx, [rsp+7C0h+var_7A0]
0x18032b7b5  mov     rcx, rax
0x18032b7b8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b7bd  mov     edx, ebx
0x18032b7bf  mov     rcx, rax; Src
0x18032b7c2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18032b7c7  mov     [rsp+7C0h+var_78E], si
0x18032b7cc  mov     byte ptr [rsp+7C0h+var_7A0], r15b; unsigned int
0x18032b7d1  movzx   ecx, word ptr [rsp+31h]
0x18032b7d6  mov     [rsp+21h], cx
0x18032b7db  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x18032b7df  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x18032b7e3  mov     [rsp+7C0h+var_79C], 200000h
0x18032b7eb  mov     [rsp+7C0h+var_798], rsi
0x18032b7f0  lea     rdx, [rsp+7C0h+var_7A0]
0x18032b7f5  mov     rcx, rax
0x18032b7f8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18032b7fd  test    ebx, ebx
0x18032b7ff  jz      short loc_18032B81E
0x18032b801  mov     rcx, [rbp+6C8h]; this
0x18032b808  mov     r9d, ebx; char *
0x18032b80b  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
  ... truncated ...
```
