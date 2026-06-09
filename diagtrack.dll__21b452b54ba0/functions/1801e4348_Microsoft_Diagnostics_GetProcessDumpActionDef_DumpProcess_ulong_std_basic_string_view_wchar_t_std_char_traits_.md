# Microsoft::Diagnostics::GetProcessDumpActionDef::DumpProcess(ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &)

- ea: `0x1801e4348`
- end: `0x1801e47c7`
- name: `?DumpProcess@GetProcessDumpActionDef@Diagnostics@Microsoft@@AEBAJKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@@Z`
- size: `1151`
- prototype: `__int64 __fastcall(__int64, DWORD, __int128 *, _QWORD *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801e6638`
- `0x18032a3e0`

## callees

- `0x18001d9a0`
- `0x18001dbb0`
- `0x180027c28`
- `0x18002967c`
- `0x18006019c`
- `0x180060500`
- `0x180064e8c`
- `0x18008a4ec`
- `0x18009c8c0`
- `0x1800bc658`
- `0x1800c4b14`
- `0x1800cce78`
- `0x1800f7f64`
- `0x180106460`
- `0x1801251ac`
- `0x180125500`
- `0x1801dc728`
- `0x1801e24d4`
- `0x1801e4348`
- `0x18026dbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e43fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e4708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e43fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e4708`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801e4371`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801e43e4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801e4371`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801e43e4`

## string_xrefs

- `0x1801e44e9`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1801e458b`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1801e4621`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1801e4686`: `commandline`
- `0x1801e4718`: `Failed to open process (PplQuery): 0x`
- `0x1801e4407`: `Failed to open process (Non-Ppl): 0x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetProcessDumpActionDef::DumpProcess(
        __int64 a1,
        DWORD a2,
        __int128 *a3,
        _QWORD *a4)
{
  char *v8; // rax
  bool IsProcessPpl; // al
  void *v10; // rcx
  void *v11; // rax
  void *v12; // rax
  __int64 v13; // rax
  void *v14; // rax
  __int64 v15; // rax
  const char *v16; // r9
  __int64 result; // rax
  int v18; // eax
  unsigned int v19; // r15d
  void *v20; // rax
  void *v21; // rax
  int v22; // eax
  unsigned int v23; // esi
  int CommandLineForPids; // eax
  __int64 v25; // rbx
  int v26; // r8d
  __int64 v27; // rax
  void *v28; // rax
  __int64 v29; // rax
  int v30; // [rsp+20h] [rbp-C8h]
  __int128 v31; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-A8h] BYREF
  char *v33; // [rsp+50h] [rbp-98h] BYREF
  _QWORD v34[2]; // [rsp+58h] [rbp-90h] BYREF
  __int128 v35; // [rsp+68h] [rbp-80h] BYREF
  __int64 v36; // [rsp+78h] [rbp-70h]
  _QWORD v37[3]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v38[80]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v8 = (char *)OpenProcess(0x1000u, 0, a2);
  try
  {
    v33 = v8;
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      GetLastError();
      v27 = Microsoft::Diagnostics::WideStringStream::operator<<(a4 + 21);
      WORD1(v32[0]) = 0;
      LOBYTE(v31) = 1;
      *(_WORD *)((char *)&v31 + 1) = BYTE1(v32[0]);
      BYTE3(v31) = 0;
      DWORD1(v31) = 2097153;
      *((_QWORD *)&v31 + 1) = 0;
      v28 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v27, &v31);
      v29 = Microsoft::Diagnostics::WideStringStream::operator<<(v28);
      WORD1(v32[0]) = 0;
      LOBYTE(v31) = 1;
      *(_WORD *)((char *)&v31 + 1) = BYTE1(v32[0]);
      BYTE3(v31) = 0;
      DWORD1(v31) = 0x200000;
      *((_QWORD *)&v31 + 1) = 0;
      Microsoft::Diagnostics::WideStringStream::operator<<(v29, &v31);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
      result = 1;
    }
    else
    {
      IsProcessPpl = Microsoft::Diagnostics::Utils::Os::IsProcessPpl(v8);
      v10 = a4 + 21;
      if ( IsProcessPpl )
      {
        v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v10);
        v21 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v20);
        Microsoft::Diagnostics::WideStringStream::operator<<(v21);
        v31 = *a3;
        v22 = Microsoft::Diagnostics::Utils::Os::DumpPplProcess(
                a2,
                (unsigned int)&v33,
                *(_DWORD *)(a1 + 200),
                (unsigned int)&v31,
                a4[1]);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v22,
            v30);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
          return v23;
        }
      }
      else
      {
        v11 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v10);
        v12 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v11);
        Microsoft::Diagnostics::WideStringStream::operator<<(v12);
        v34[0] = OpenProcess(16 * (*(_DWORD *)(a1 + 200) & 4 | 0x41u), 1, a2);
        if ( ((v34[0] + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          GetLastError();
          v13 = Microsoft::Diagnostics::WideStringStream::operator<<(a4 + 21);
          WORD1(v32[0]) = 0;
          LOBYTE(v31) = 1;
          *(_WORD *)((char *)&v31 + 1) = BYTE1(v32[0]);
          BYTE3(v31) = 0;
          DWORD1(v31) = 2097153;
          *((_QWORD *)&v31 + 1) = 0;
          v14 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v13, &v31);
          v15 = Microsoft::Diagnostics::WideStringStream::operator<<(v14);
          WORD1(v32[0]) = 0;
          LOBYTE(v31) = 1;
          *(_WORD *)((char *)&v31 + 1) = BYTE1(v32[0]);
          BYTE3(v31) = 0;
          DWORD1(v31) = 0x200000;
          *((_QWORD *)&v31 + 1) = 0;
          Microsoft::Diagnostics::WideStringStream::operator<<(v15, &v31);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v34);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
          return 1;
        }
        v31 = *a3;
        v18 = Microsoft::Diagnostics::Utils::Os::DumpProcess(
                a2,
                (unsigned int)v34,
                *(_DWORD *)(a1 + 200),
                (unsigned int)&v31,
                a4[1]);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v18,
            v30);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v34);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
          return v19;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v34);
      }
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(v37);
      LODWORD(v34[0]) = a2;
      v35 = 0;
      v36 = 0;
      v32[0] = (char *)v34 + 4;
      *(_QWORD *)&v31 = v34;
      std::vector<unsigned long>::_Construct_n<unsigned long const *,unsigned long const *>(&v35, 1, &v31, v32);
      CommandLineForPids = Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(&v35, v37);
      if ( CommandLineForPids < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)CommandLineForPids,
          v30);
      std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v35);
      if ( v37[0] != v37[1] )
      {
        v25 = a4[8];
        Microsoft::Diagnostics::EscalationWorkItemState::AddNewActionInfoToBuilder(a4, v34);
        v31 = *(_OWORD *)std::wstring::operator std::wstring_view(v37[0], v38);
        v32[0] = L"commandline";
        v32[1] = 11;
        JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
          (unsigned int)&v35,
          v25,
          v26,
          (unsigned int)v34,
          (__int64)v32,
          (__int64)&v31);
        Microsoft::Diagnostics::EscalationWorkItemState::AddDynamicInfoForCurrentActionToBuilder((Microsoft::Diagnostics::EscalationWorkItemState *)a4);
      }
      v31 = *a3;
      Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a4, &v31);
      std::vector<std::pair<std::wstring,unsigned long>>::_Tidy(v37);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x190,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1801e4348  push    rbx
0x1801e434a  push    rsi
0x1801e434b  push    rdi
0x1801e434c  push    r12
0x1801e434e  push    r13
0x1801e4350  push    r14
0x1801e4352  push    r15
0x1801e4354  sub     rsp, 0B0h
0x1801e435b  mov     rdi, r9
0x1801e435e  mov     r12, r8
0x1801e4361  mov     r14d, edx
0x1801e4364  mov     r13, rcx
0x1801e4367  mov     r8d, edx; dwProcessId
0x1801e436a  xor     edx, edx; bInheritHandle
0x1801e436c  mov     ecx, 1000h; dwDesiredAccess
0x1801e4371  call    cs:__imp_OpenProcess
0x1801e4377  mov     [rsp+0E8h+var_98], rax
0x1801e437c  lea     rcx, [rax-1]
0x1801e4380  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801e4384  ja      loc_1801E4708
0x1801e438a  lea     r15, [rdi+0A8h]
0x1801e4391  mov     rcx, rax; void *
0x1801e4394  call    ?IsProcessPpl@Os@Utils@Diagnostics@Microsoft@@SA_NPEAX@Z; Microsoft::Diagnostics::Utils::Os::IsProcessPpl(void *)
0x1801e4399  xor     ebx, ebx
0x1801e439b  mov     rcx, r15; Src
0x1801e439e  test    al, al
0x1801e43a0  jnz     loc_1801E4527
0x1801e43a6  lea     rdx, aDumpingNonPplP; "Dumping non-PPL process: "
0x1801e43ad  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e43b2  mov     edx, r14d
0x1801e43b5  mov     rcx, rax; Src
0x1801e43b8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1801e43bd  lea     rdx, asc_1803A0C7C; "\r\n"
0x1801e43c4  mov     rcx, rax; Src
0x1801e43c7  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e43cc  mov     ecx, [r13+0C8h]
0x1801e43d3  and     ecx, 4
0x1801e43d6  or      ecx, 41h
0x1801e43d9  shl     ecx, 4; dwDesiredAccess
0x1801e43dc  mov     r8d, r14d; dwProcessId
0x1801e43df  lea     esi, [rbx+1]
0x1801e43e2  mov     edx, esi; bInheritHandle
0x1801e43e4  call    cs:__imp_OpenProcess
0x1801e43ea  mov     [rsp+0E8h+var_90], rax
0x1801e43ef  inc     rax
0x1801e43f2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e43f8  jnz     loc_1801E44AA
0x1801e43fe  call    cs:__imp_GetLastError
0x1801e4404  mov     r14d, eax
0x1801e4407  lea     rdx, aFailedToOpenPr; "Failed to open process (Non-Ppl): 0x"
0x1801e440e  mov     rcx, r15; Src
0x1801e4411  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e4416  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1801e441b  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1801e4420  movzx   ecx, word ptr [rsp+41h]
0x1801e4425  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1801e442a  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1801e442e  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1801e4432  mov     dword ptr [rsp+0E8h+var_B8+4], 200001h
0x1801e443a  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1801e443f  lea     rdx, [rsp+0E8h+var_B8]
0x1801e4444  mov     rcx, rax
0x1801e4447  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1801e444c  mov     edx, r14d
0x1801e444f  mov     rcx, rax; Src
0x1801e4452  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1801e4457  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1801e445c  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1801e4461  movzx   ecx, word ptr [rsp+41h]
0x1801e4466  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1801e446b  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1801e446f  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1801e4473  mov     dword ptr [rsp+0E8h+var_B8+4], 200000h
0x1801e447b  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1801e4480  lea     rdx, [rsp+0E8h+var_B8]
0x1801e4485  mov     rcx, rax
0x1801e4488  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1801e448d  nop
0x1801e448e  lea     rcx, [rsp+0E8h+var_90]
0x1801e4493  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e4498  nop
0x1801e4499  lea     rcx, [rsp+0E8h+var_98]
0x1801e449e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e44a3  mov     eax, esi
0x1801e44a5  jmp     loc_1801E47B3
0x1801e44aa  movaps  xmm0, xmmword ptr [r12]
0x1801e44af  movdqa  [rsp+0E8h+var_B8], xmm0
0x1801e44b5  mov     rax, [rdi+8]
0x1801e44b9  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1801e44be  lea     r9, [rsp+0E8h+var_B8]
0x1801e44c3  mov     r8d, [r13+0C8h]
0x1801e44ca  lea     rdx, [rsp+0E8h+var_90]
0x1801e44cf  mov     ecx, r14d
0x1801e44d2  call    ?DumpProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z; Microsoft::Diagnostics::Utils::Os::DumpProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::wstring_view,unsigned __int64)
0x1801e44d7  mov     r15d, eax
0x1801e44da  test    eax, eax
0x1801e44dc  jns     short loc_1801E4518
0x1801e44de  mov     rcx, [rsp+0E8h]; this
0x1801e44e6  mov     r9d, eax; char *
0x1801e44e9  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1801e44f0  mov     edx, 176h; void *
0x1801e44f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e44fa  nop
0x1801e44fb  lea     rcx, [rsp+0E8h+var_90]
0x1801e4500  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e4505  nop
0x1801e4506  lea     rcx, [rsp+0E8h+var_98]
0x1801e450b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e4510  mov     eax, r15d
0x1801e4513  jmp     loc_1801E47B3
0x1801e4518  lea     rcx, [rsp+0E8h+var_90]
0x1801e451d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e4522  jmp     loc_1801E45B3
0x1801e4527  lea     rdx, aDumpingPplProc; "Dumping PPL process: "
0x1801e452e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e4533  mov     edx, r14d
0x1801e4536  mov     rcx, rax; Src
0x1801e4539  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1801e453e  lea     rdx, asc_1803A0C7C; "\r\n"
0x1801e4545  mov     rcx, rax; Src
0x1801e4548  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e454d  movaps  xmm0, xmmword ptr [r12]
0x1801e4552  movdqa  [rsp+0E8h+var_B8], xmm0
0x1801e4558  mov     rax, [rdi+8]
0x1801e455c  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1801e4561  lea     r9, [rsp+0E8h+var_B8]
0x1801e4566  mov     r8d, [r13+0C8h]
0x1801e456d  lea     rdx, [rsp+0E8h+var_98]
0x1801e4572  mov     ecx, r14d
0x1801e4575  call    ?DumpPplProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z; Microsoft::Diagnostics::Utils::Os::DumpPplProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::wstring_view,unsigned __int64)
0x1801e457a  mov     esi, eax
0x1801e457c  test    eax, eax
0x1801e457e  jns     short loc_1801E45AE
0x1801e4580  mov     rcx, [rsp+0E8h]; this
0x1801e4588  mov     r9d, eax; char *
0x1801e458b  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1801e4592  mov     edx, 17Ch; void *
0x1801e4597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e459c  nop
0x1801e459d  lea     rcx, [rsp+0E8h+var_98]
0x1801e45a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e45a7  mov     eax, esi
0x1801e45a9  jmp     loc_1801E47B3
0x1801e45ae  mov     esi, 1
0x1801e45b3  lea     rcx, [rsp+0E8h+var_68]; void *
0x1801e45bb  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1801e45c0  nop
0x1801e45c1  mov     dword ptr [rsp+0E8h+var_90], r14d
0x1801e45c6  xorps   xmm0, xmm0
0x1801e45c9  movdqu  [rsp+0E8h+var_80], xmm0
0x1801e45cf  mov     [rsp+0E8h+var_70], rbx
0x1801e45d4  lea     rax, [rsp+0E8h+var_90+4]
0x1801e45d9  mov     [rsp+40h], rax
0x1801e45de  lea     rax, [rsp+0E8h+var_90]
0x1801e45e3  mov     qword ptr [rsp+0E8h+var_B8], rax
0x1801e45e8  lea     r9, [rsp+0E8h+var_A8]
0x1801e45ed  lea     r8, [rsp+0E8h+var_B8]
0x1801e45f2  mov     rdx, rsi
0x1801e45f5  lea     rcx, [rsp+0E8h+var_80]
0x1801e45fa  call    ??$_Construct_n@PEBKPEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAX_K$$QEAPEBK1@Z; std::vector<ulong>::_Construct_n<ulong const *,ulong const *>(unsigned __int64,ulong const * &&,ulong const * &&)
0x1801e45ff  nop
0x1801e4600  lea     rdx, [rsp+0E8h+var_68]
0x1801e4608  lea     rcx, [rsp+0E8h+var_80]
0x1801e460d  call    ?GetCommandLineForPids@Os@Utils@Diagnostics@Microsoft@@SAJAEBV?$vector@KV?$allocator@K@std@@@std@@AEAV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@6@@Z; Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(std::vector<ulong> const &,std::vector<std::pair<std::wstring,ulong>> &)
0x1801e4612  mov     rcx, [rsp+0E8h]; this
0x1801e461a  test    eax, eax
0x1801e461c  jns     short loc_1801E4633
0x1801e461e  mov     r9d, eax; char *
0x1801e4621  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1801e4628  mov     edx, 181h; void *
0x1801e462d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801e4632  nop
0x1801e4633  lea     rcx, [rsp+0E8h+var_80]
0x1801e4638  call    ??1?$vector@W4_TDH_IN_TYPE@@V?$allocator@W4_TDH_IN_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_TDH_IN_TYPE>::~vector<_TDH_IN_TYPE>(void)
0x1801e463d  mov     rax, [rsp+0E8h+var_60]
0x1801e4645  cmp     [rsp+0E8h+var_68], rax
0x1801e464d  jz      short loc_1801E46C9
0x1801e464f  mov     rbx, [rdi+40h]
0x1801e4653  lea     rdx, [rsp+0E8h+var_90]
0x1801e4658  mov     rcx, rdi
0x1801e465b  call    ?AddNewActionInfoToBuilder@EscalationWorkItemState@Diagnostics@Microsoft@@QEAA?AVJsonIterator@@XZ; Microsoft::Diagnostics::EscalationWorkItemState::AddNewActionInfoToBuilder(void)
0x1801e4660  lea     rdx, [rsp+0E8h+var_50]
0x1801e4668  mov     rcx, [rsp+0E8h+var_68]
0x1801e4670  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e4675  mov     rcx, [rax]
0x1801e4678  mov     qword ptr [rsp+0E8h+var_B8], rcx
0x1801e467d  mov     rax, [rax+8]
0x1801e4681  mov     qword ptr [rsp+0E8h+var_B8+8], rax
0x1801e4686  lea     rax, aCommandline_2; "commandline"
0x1801e468d  mov     [rsp+0E8h+var_A8], rax
0x1801e4692  mov     [rsp+0E8h+var_A0], 0Bh
0x1801e469b  lea     rax, [rsp+0E8h+var_B8]
0x1801e46a0  mov     [rsp+0E8h+var_C0], rax
0x1801e46a5  lea     rax, [rsp+0E8h+var_A8]
0x1801e46aa  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1801e46af  lea     r9, [rsp+0E8h+var_90]
0x1801e46b4  mov     rdx, rbx
0x1801e46b7  lea     rcx, [rsp+0E8h+var_80]
0x1801e46bc  call    ?AddValue@?$JsonImplementType@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@SA?AVJsonIterator@@AEAVJsonBuilder@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@3@Z; JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1801e46c1  mov     rcx, rdi; this
0x1801e46c4  call    ?AddDynamicInfoForCurrentActionToBuilder@EscalationWorkItemState@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::EscalationWorkItemState::AddDynamicInfoForCurrentActionToBuilder(void)
0x1801e46c9  mov     r8d, 3
0x1801e46cf  movaps  xmm0, xmmword ptr [r12]
0x1801e46d4  movdqa  [rsp+0E8h+var_B8], xmm0
0x1801e46da  lea     rdx, [rsp+0E8h+var_B8]
0x1801e46df  mov     rcx, rdi
0x1801e46e2  call    ?AddCollectedFileToBuilder@EscalationWorkItemState@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@VCollectedFileType@EnumDetails@23@@Z; Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(std::wstring_view,Microsoft::Diagnostics::EnumDetails::CollectedFileType)
0x1801e46e7  nop
0x1801e46e8  lea     rcx, [rsp+0E8h+var_68]
0x1801e46f0  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,ulong>>::_Tidy(void)
0x1801e46f5  nop
0x1801e46f6  lea     rcx, [rsp+0E8h+var_98]
0x1801e46fb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e4700  nop
0x1801e4701  xor     eax, eax
0x1801e4703  jmp     loc_1801E47B3
0x1801e4708  call    cs:__imp_GetLastError
0x1801e470e  mov     r14d, eax
0x1801e4711  lea     rcx, [rdi+0A8h]; Src
0x1801e4718  lea     rdx, aFailedToOpenPr_0; "Failed to open process (PplQuery): 0x"
0x1801e471f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e4724  xor     ebx, ebx
0x1801e4726  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1801e472b  lea     esi, [rbx+1]
0x1801e472e  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1801e4733  movzx   ecx, word ptr [rsp+0E8h+var_A8+1]
0x1801e4738  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1801e473d  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1801e4741  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1801e4745  mov     dword ptr [rsp+0E8h+var_B8+4], 200001h
0x1801e474d  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1801e4752  lea     rdx, [rsp+0E8h+var_B8]
0x1801e4757  mov     rcx, rax
0x1801e475a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1801e475f  mov     edx, r14d
0x1801e4762  mov     rcx, rax; Src
0x1801e4765  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1801e476a  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1801e476f  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1801e4774  movzx   ecx, word ptr [rsp+0E8h+var_A8+1]
0x1801e4779  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1801e477e  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1801e4782  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1801e4786  mov     dword ptr [rsp+0E8h+var_B8+4], 200000h
0x1801e478e  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1801e4793  lea     rdx, [rsp+0E8h+var_B8]
0x1801e4798  mov     rcx, rax
0x1801e479b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1801e47a0  nop
0x1801e47a1  lea     rcx, [rsp+0E8h+var_98]
0x1801e47a6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e47ab  mov     eax, esi
0x1801e47ad  jmp     short loc_1801E47B3
0x1801e47af  mov     eax, dword ptr [rsp+0E8h+var_90]
0x1801e47b3  add     rsp, 0B0h
0x1801e47ba  pop     r15
0x1801e47bc  pop     r14
0x1801e47be  pop     r13
0x1801e47c0  pop     r12
0x1801e47c2  pop     rdi
0x1801e47c3  pop     rsi
0x1801e47c4  pop     rbx
0x1801e47c5  retn
```
