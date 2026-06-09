# InternalGetRegistrySectionName(void)

- ea: `0x18000dde0`
- end: `0x18000e001`
- name: `?InternalGetRegistrySectionName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@XZ`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d890`

## callees

- `0x180003426`
- `0x180004074`
- `0x18000c404`
- `0x18000c810`
- `0x18000c840`
- `0x18000ca5c`
- `0x18000d0e8`
- `0x18000d940`
- `0x18000dde0`
- `0x180017430`
- `0x18002f0ba`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000df18`
- `KERNEL32!CompareStringW` at `0x18000df18`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall InternalGetRegistrySectionName(__int64 a1)
{
  signed int FalconServiceName; // edi
  unsigned int v3; // eax
  _BYTE *v4; // rax
  const wchar_t *v5; // rdx
  __int64 v6; // rax
  unsigned __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // rdx
  __int16 v11; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v12; // [rsp+68h] [rbp-98h] BYREF
  _QWORD pExceptionObject[5]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v14[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v15[40]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v16; // [rsp+D8h] [rbp-28h]
  __int64 *v17; // [rsp+E0h] [rbp-20h]
  _QWORD *v18; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v19; // [rsp+100h] [rbp+0h]
  int *v20; // [rsp+110h] [rbp+10h]
  unsigned __int64 v21; // [rsp+128h] [rbp+28h]
  char v22; // [rsp+130h] [rbp+30h]
  WCHAR String1[304]; // [rsp+1A0h] [rbp+A0h] BYREF

  v12 = a1;
  memset_0(String1, 0, 0x258u);
  FalconServiceName = GetFalconServiceName(String1, 0x12Cu);
  if ( FalconServiceName < 0 )
  {
    v11 = 200;
    LODWORD(v12) = FalconServiceName;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v3 = mqwcslen(L"mqsec/register");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v3 + 1),
        L"mqsec/register",
        2,
        &v11,
        4,
        &v12,
        0,
        0);
    }
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, FalconServiceName);
    pExceptionObject[0] = &bad_win32_error::`vftable';
    throw (bad_string_result *)pExceptionObject;
  }
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>(v14);
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L"MSMQ", -1) == 2 )
  {
    v4 = v15;
    v5 = L"SOFTWARE\\Microsoft\\MSMQ\\Parameters";
  }
  else
  {
    v6 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v15, L"SOFTWARE\\Microsoft\\MSMQ\\Clustered QMs\\");
    v4 = (_BYTE *)std::operator<<<wchar_t,std::char_traits<wchar_t>>(v6, String1);
    v5 = L"\\Parameters";
  }
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v4, v5);
  if ( (v22 & 2) != 0 || !*v19 )
  {
    if ( (v22 & 4) != 0 || !*v18 )
    {
      *(_QWORD *)(a1 + 32) = 7;
      *(_QWORD *)(a1 + 24) = 0;
      *(_WORD *)(a1 + 8) = 0;
      goto LABEL_18;
    }
    v9 = *v16;
    v8 = *v18 + 2LL * *v20 - *v16;
  }
  else
  {
    v7 = v21;
    if ( v21 < *v19 )
      v7 = *v19;
    v8 = v7 - *v17;
    v9 = *v17;
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    a1,
    v9,
    v8 >> 1);
LABEL_18:
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::`vbase destructor'(v14);
  return a1;
}

```

## disassembly

```asm
0x18000dde0  mov     [rsp-8+arg_8], rbx
0x18000dde5  mov     [rsp-8+arg_10], rdi
0x18000ddea  push    rbp
0x18000ddeb  lea     rbp, [rsp-310h]
0x18000ddf3  sub     rsp, 410h
0x18000ddfa  mov     rax, cs:__security_cookie
0x18000de01  xor     rax, rsp
0x18000de04  mov     [rbp+310h+var_10], rax
0x18000de0b  mov     rbx, rcx
0x18000de0e  mov     [rsp+410h+var_3A8], rcx
0x18000de13  xor     edx, edx; Val
0x18000de15  mov     r8d, 258h; Size
0x18000de1b  lea     rcx, [rbp+310h+String1]; void *
0x18000de22  call    memset_0
0x18000de27  mov     edx, 12Ch; unsigned int
0x18000de2c  lea     rcx, [rbp+310h+String1]; wchar_t *
0x18000de33  call    ?GetFalconServiceName@@YAJPEA_WK@Z; GetFalconServiceName(wchar_t *,ulong)
0x18000de38  mov     edi, eax
0x18000de3a  test    eax, eax
0x18000de3c  jns     loc_18000DEEB
0x18000de42  mov     eax, 0C8h
0x18000de47  mov     [rsp+410h+var_3B0], ax
0x18000de4c  mov     dword ptr [rsp+410h+var_3A8], edi
0x18000de50  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000de58  jz      short loc_18000DEC1
0x18000de5a  lea     rbx, aMqsecRegister; "mqsec/register"
0x18000de61  mov     rcx, rbx; wchar_t *
0x18000de64  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000de69  mov     edx, 1
0x18000de6e  lea     r9d, [rdx+rax]
0x18000de72  add     r9, r9
0x18000de75  mov     [rsp+410h+var_3C0], 0
0x18000de7e  mov     [rsp+410h+var_3C8], 0
0x18000de87  lea     rax, [rsp+410h+var_3A8]
0x18000de8c  mov     [rsp+410h+var_3D0], rax
0x18000de91  mov     [rsp+410h+var_3D8], 4
0x18000de9a  lea     rax, [rsp+410h+var_3B0]
0x18000de9f  mov     [rsp+410h+var_3E0], rax
0x18000dea4  mov     qword ptr [rsp+410h+cchCount2], 2
0x18000dead  mov     [rsp+410h+lpString2], rbx
0x18000deb2  mov     r8d, edx
0x18000deb5  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000debc  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000dec1  mov     edx, edi; unsigned int
0x18000dec3  lea     rcx, [rsp+410h+pExceptionObject]; this
0x18000dec8  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18000decd  lea     rax, ??_7bad_win32_error@@6B@; const bad_win32_error::`vftable'
0x18000ded4  mov     [rsp+410h+pExceptionObject], rax
0x18000ded9  lea     rdx, _TI4?AVbad_string_result@@; pThrowInfo
0x18000dee0  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18000dee5  call    _CxxThrowException_0
0x18000deeb  lea     rcx, [rbp+310h+var_370]
0x18000deef  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@@std@@QEAA@H@Z; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>(int)
0x18000def4  nop
0x18000def5  or      r9d, 0FFFFFFFFh; cchCount1
0x18000def9  mov     [rsp+410h+cchCount2], r9d; cchCount2
0x18000defe  lea     rax, SubsystemName; "MSMQ"
0x18000df05  mov     [rsp+410h+lpString2], rax; lpString2
0x18000df0a  lea     r8, [rbp+310h+String1]; lpString1
0x18000df11  lea     edx, [r9+2]; dwCmpFlags
0x18000df15  lea     ecx, [rdx+7Eh]; Locale
0x18000df18  call    cs:__imp_CompareStringW
0x18000df1e  cmp     eax, 2
0x18000df21  jnz     short loc_18000DF30
0x18000df23  lea     rax, [rbp+310h+var_360]
0x18000df27  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSMQ\\Parameters"
0x18000df2e  jmp     short loc_18000DF56
0x18000df30  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\MSMQ\\Clustered QM"...
0x18000df37  lea     rcx, [rbp+310h+var_360]
0x18000df3b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18000df40  mov     rcx, rax
0x18000df43  lea     rdx, [rbp+310h+String1]
0x18000df4a  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18000df4f  lea     rdx, aParameters; "\\Parameters"
0x18000df56  mov     rcx, rax
0x18000df59  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18000df5e  test    [rbp+310h+var_2E0], 2
0x18000df62  jnz     short loc_18000DF90
0x18000df64  mov     rax, [rbp+310h+var_310]
0x18000df68  cmp     qword ptr [rax], 0
0x18000df6c  jz      short loc_18000DF90
0x18000df6e  mov     r8, [rbp+310h+var_2E8]
0x18000df72  cmp     r8, [rax]
0x18000df75  cmovb   r8, [rax]
0x18000df79  mov     rax, [rbp+310h+var_330]
0x18000df7d  sub     r8, [rax]
0x18000df80  mov     rdx, [rax]
0x18000df83  sar     r8, 1
0x18000df86  mov     rcx, rbx
0x18000df89  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *,unsigned __int64)
0x18000df8e  jmp     short loc_18000DFD1
0x18000df90  test    [rbp+310h+var_2E0], 4
0x18000df94  jnz     short loc_18000DFBB
0x18000df96  mov     rax, [rbp+310h+var_318]
0x18000df9a  mov     rcx, [rax]
0x18000df9d  test    rcx, rcx
0x18000dfa0  jz      short loc_18000DFBB
0x18000dfa2  mov     rax, [rbp+310h+var_338]
0x18000dfa6  mov     rdx, [rax]
0x18000dfa9  mov     rax, [rbp+310h+var_300]
0x18000dfad  movsxd  r8, dword ptr [rax]
0x18000dfb0  add     r8, r8
0x18000dfb3  sub     r8, rdx
0x18000dfb6  add     r8, rcx
0x18000dfb9  jmp     short loc_18000DF83
0x18000dfbb  mov     qword ptr [rbx+20h], 7
0x18000dfc3  mov     qword ptr [rbx+18h], 0
0x18000dfcb  xor     ecx, ecx
0x18000dfcd  mov     [rbx+8], cx
0x18000dfd1  lea     rcx, [rbp+310h+var_370]
0x18000dfd5  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>>::`vbase destructor'(void)
0x18000dfda  mov     rax, rbx
0x18000dfdd  mov     rcx, [rbp+310h+var_10]
0x18000dfe4  xor     rcx, rsp; StackCookie
0x18000dfe7  call    __security_check_cookie
0x18000dfec  lea     r11, [rsp+410h+var_s0]
0x18000dff4  mov     rbx, [r11+18h]
0x18000dff8  mov     rdi, [r11+20h]
0x18000dffc  mov     rsp, r11
0x18000dfff  pop     rbp
0x18000e000  retn
```
