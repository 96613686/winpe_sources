# LogExtendedErrorInformationInternal(bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180024efc`
- end: `0x180025403`
- name: `?LogExtendedErrorInformationInternal@@YAX_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1287`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002222c`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18001406c`
- `0x18001864c`
- `0x18001868c`
- `0x1800186c8`
- `0x18001870c`
- `0x180018748`
- `0x180018784`
- `0x1800187c4`
- `0x180018804`
- `0x180018840`
- `0x18001cad0`
- `0x18001cc2c`
- `0x18001d80c`
- `0x18001ed18`
- `0x180024efc`
- `0x180029538`
- `0x180029578`
- `0x180092d1c`
- `0x1800b5010`

## import_xrefs

- `RPCRT4!RpcErrorStartEnumeration` at `0x180024f88`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180024f88`
- `RPCRT4!RpcErrorGetNextRecord` at `0x180025061`
- `RPCRT4!RpcErrorGetNextRecord` at `0x180025061`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025395`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800253d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025395`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800253d9`

## string_xrefs

- `0x180025122`: `ComputerName is {0}`
- `0x180025149`: `ProcessID is {0}`
- `0x18002518a`: `Generating component is {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LogExtendedErrorInformationInternal(__int64 a1, __int64 a2)
{
  RPC_STATUS started; // eax
  wchar_t *v4; // rdx
  int v5; // eax
  RPC_STATUS NextRecord; // eax
  __int64 result; // rax
  int v8; // r8d
  int v9; // eax
  int i; // ecx
  wchar_t *v11; // rdx
  HANDLE ProcessHeap; // rax
  int j; // edi
  LPSTR AnsiString; // rbx
  HANDLE v15; // rax
  RPC_STATUS v16; // [rsp+20h] [rbp-188h]
  int v17; // [rsp+24h] [rbp-184h]
  int v18; // [rsp+28h] [rbp-180h]
  _QWORD v19[4]; // [rsp+30h] [rbp-178h] BYREF
  RPC_ERROR_ENUM_HANDLE EnumHandle; // [rsp+50h] [rbp-158h] BYREF
  void **v21; // [rsp+68h] [rbp-140h]
  __int64 v22; // [rsp+70h] [rbp-138h]
  char v23[8]; // [rsp+78h] [rbp-130h] BYREF
  RPC_ERROR_ENUM_HANDLE *p_EnumHandle; // [rsp+80h] [rbp-128h]
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+90h] [rbp-118h] BYREF
  _OWORD v26[2]; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v27[32]; // [rsp+150h] [rbp-58h] BYREF

  memset(&EnumHandle, 0, sizeof(EnumHandle));
  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  v26[0] = 0;
  v26[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v26[0]) = 0;
  cxl::StringWriter::StringWriter(v19, v26);
  started = RpcErrorStartEnumeration(&EnumHandle);
  try
  {
    v16 = started;
    if ( started == 1761 )
    {
      v4 = L"Failed RpcErrorStartEnumeration (not found)";
LABEL_6:
      cxl::TextWriter::WriteLine<wchar_t,long,>((struct cxl::TextWriter *)v19, v4);
LABEL_15:
      std::wstring::operator=(a2, v26);
      v19[0] = &cxl::RefCounted::`vftable';
      return std::wstring::_Tidy_deallocate(v26);
    }
    if ( started )
    {
      v4 = L"Failed RpcErrorStartEnumeration: {0}";
      goto LABEL_6;
    }
    v23[0] = 1;
    p_EnumHandle = &EnumHandle;
    v5 = 0;
LABEL_8:
    if ( v16 )
      goto LABEL_14;
    v18 = v5 + 1;
    if ( v5 + 1 > 1 )
    {
      (*(void (__fastcall **)(_QWORD *, const wchar_t *, __int64))(v19[0] + 24LL))(
        v19,
        L"-----------------------------------",
        35);
      cxl::TextWriter::operator<<<cxl::ENDL>(v19);
    }
    cxl::TextWriter::WriteLine<wchar_t,int,>((struct cxl::TextWriter *)v19, L"\nRPC Error Record {0}");
    ErrorInfo.Version = 1;
    ErrorInfo.NumberOfParameters = 4;
    ErrorInfo.Flags = 4;
    NextRecord = RpcErrorGetNextRecord(&EnumHandle, 1, &ErrorInfo);
    v16 = NextRecord;
    if ( NextRecord == 1761 )
    {
LABEL_14:
      cxl::ScopeGuardImpl__lambda_1e54ec72bada8c8e15f400892bf71413___::_ScopeGuardImpl__lambda_1e54ec72bada8c8e15f400892bf71413___(v23);
      goto LABEL_15;
    }
    if ( NextRecord )
    {
      cxl::TextWriter::WriteLine<wchar_t,long,>(
        (struct cxl::TextWriter *)v19,
        L"Failed to enumerate extended error information: {0}");
      goto LABEL_14;
    }
    (*(void (__fastcall **)(_QWORD *, const wchar_t *, __int64))(v19[0] + 24LL))(
      v19,
      L"Extended RPC error information:",
      31);
    cxl::TextWriter::operator<<<cxl::ENDL>(v19);
    if ( ErrorInfo.ComputerName )
    {
      std::wstring::wstring(v27, ErrorInfo.ComputerName);
      cxl::TextWriter::WriteLine<wchar_t,std::wstring,>((struct cxl::TextWriter *)v19, L"ComputerName is {0}");
      std::wstring::_Tidy_deallocate(v27);
    }
    cxl::TextWriter::WriteLine<wchar_t,unsigned long,>((struct cxl::TextWriter *)v19, L"ProcessID is {0}");
    v21 = &cxl::DateTime::`vftable';
    v22 = *(_QWORD *)&ErrorInfo.u.SystemTime.wYear;
    cxl::TextWriter::WriteLine<wchar_t,cxl::DateTime,>((struct cxl::TextWriter *)v19);
    cxl::TextWriter::WriteLine<wchar_t,unsigned long,>((struct cxl::TextWriter *)v19, L"Generating component is {0}");
    cxl::TextWriter::WriteLine<wchar_t,unsigned long,>((struct cxl::TextWriter *)v19, L"Status is {0}");
    cxl::TextWriter::WriteLine<wchar_t,int,>((struct cxl::TextWriter *)v19, L"Detection location is {0}");
    cxl::TextWriter::WriteLine<wchar_t,unsigned short,>((struct cxl::TextWriter *)v19);
    cxl::TextWriter::WriteLine<wchar_t,int,>((struct cxl::TextWriter *)v19, L"NumberOfParameters is {0}");
    v8 = 0;
    v9 = 0;
    for ( i = 0; ; i = v17 + 1 )
    {
      v17 = v8;
      if ( v9 >= ErrorInfo.NumberOfParameters )
      {
        if ( ErrorInfo.ComputerName )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, ErrorInfo.ComputerName);
        }
        for ( j = 0; j < ErrorInfo.NumberOfParameters; ++j )
        {
          if ( ErrorInfo.Parameters[j].ParameterType == eeptAnsiString
            || ErrorInfo.Parameters[j].ParameterType == eeptUnicodeString )
          {
            AnsiString = ErrorInfo.Parameters[j].u.AnsiString;
            v15 = GetProcessHeap();
            HeapFree(v15, 0, AnsiString);
          }
        }
        v5 = v18;
        goto LABEL_8;
      }
      switch ( ErrorInfo.Parameters[i].ParameterType )
      {
        case eeptAnsiString:
          std::string::string(v27, ErrorInfo.Parameters[v8].u.PVal);
          cxl::TextWriter::WriteLine<wchar_t,std::string,>((struct cxl::TextWriter *)v19);
          std::string::_Tidy_deallocate(v27);
          break;
        case eeptUnicodeString:
          std::wstring::wstring(v27, ErrorInfo.Parameters[v8].u.PVal);
          cxl::TextWriter::WriteLine<wchar_t,std::wstring,>((struct cxl::TextWriter *)v19, L"Unicode string: {0}");
          std::wstring::_Tidy_deallocate(v27);
          break;
        case eeptLongVal:
          cxl::TextWriter::WriteLine<wchar_t,long,>((struct cxl::TextWriter *)v19, L"Long val: {0}");
          break;
        default:
          switch ( ErrorInfo.Parameters[i].ParameterType )
          {
            case eeptShortVal:
              v11 = L"Short val: {0}";
              break;
            case eeptPointerVal:
              cxl::TextWriter::WriteLine<wchar_t,unsigned __int64,>((struct cxl::TextWriter *)v19);
              goto LABEL_34;
            case eeptNone:
              v11 = L"(parameter {0} truncated";
              break;
            default:
              cxl::TextWriter::WriteLine<wchar_t,int,int>((struct cxl::TextWriter *)v19);
              goto LABEL_34;
          }
          cxl::TextWriter::WriteLine<wchar_t,int,>((struct cxl::TextWriter *)v19, v11);
          break;
      }
LABEL_34:
      v8 = v17 + 1;
      v9 = v17 + 1;
    }
  }
  catch ( ... )
  {
  }
  return result;
}

```

## disassembly

```asm
0x180024efc  push    rbx
0x180024efe  push    rsi
0x180024eff  push    rdi
0x180024f00  push    r12
0x180024f02  sub     rsp, 188h
0x180024f09  mov     rax, cs:__security_cookie
0x180024f10  xor     rax, rsp
0x180024f13  mov     [rsp+1A8h+var_38], rax
0x180024f1b  mov     rsi, rdx
0x180024f1e  mov     [rsp+1A8h+var_188], 0
0x180024f26  xorps   xmm0, xmm0
0x180024f29  xor     eax, eax
0x180024f2b  movups  xmmword ptr [rsp+1A8h+EnumHandle.Signature], xmm0
0x180024f30  mov     [rsp+1A8h+EnumHandle.Head], rax
0x180024f35  xor     edx, edx; Val
0x180024f37  mov     r8d, 98h; Size
0x180024f3d  lea     rcx, [rsp+1A8h+ErrorInfo]; void *
0x180024f45  call    memset_0
0x180024f4a  xorps   xmm0, xmm0
0x180024f4d  movups  [rsp+1A8h+var_78], xmm0
0x180024f55  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180024f5d  movdqu  [rsp+1A8h+var_68], xmm1
0x180024f66  xor     eax, eax
0x180024f68  mov     word ptr [rsp+1A8h+var_78], ax
0x180024f70  lea     rdx, [rsp+1A8h+var_78]
0x180024f78  lea     rcx, [rsp+1A8h+var_178]
0x180024f7d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180024f82  nop
0x180024f83  lea     rcx, [rsp+1A8h+EnumHandle]; EnumHandle
0x180024f88  call    cs:__imp_RpcErrorStartEnumeration
0x180024f8e  mov     [rsp+1A8h+var_188], eax
0x180024f92  cmp     eax, 6E1h
0x180024f97  jnz     short loc_180024FA2
0x180024f99  lea     rdx, aFailedRpcerror_0; "Failed RpcErrorStartEnumeration (not fo"...
0x180024fa0  jmp     short loc_180024FAD
0x180024fa2  test    eax, eax
0x180024fa4  jz      short loc_180024FC1
0x180024fa6  lea     rdx, aFailedRpcerror; "Failed RpcErrorStartEnumeration: {0}"
0x180024fad  lea     r8, [rsp+1A8h+var_188]
0x180024fb2  lea     rcx, [rsp+1A8h+var_178]
0x180024fb7  call    ??$WriteLine@_WJ$$V@TextWriter@cxl@@QEAAXPEB_WAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,long,>(wchar_t const *,long const &)
0x180024fbc  jmp     loc_180025097
0x180024fc1  mov     [rsp+1A8h+var_130], 1
0x180024fc6  lea     rax, [rsp+1A8h+EnumHandle]
0x180024fcb  mov     [rsp+1A8h+var_128], rax
0x180024fd3  xor     eax, eax
0x180024fd5  mov     [rsp+1A8h+var_180], eax
0x180024fd9  lea     r12d, [rax+4]
0x180024fdd  cmp     [rsp+1A8h+var_188], 0
0x180024fe2  jnz     loc_18002508D
0x180024fe8  inc     eax
0x180024fea  mov     [rsp+1A8h+var_180], eax
0x180024fee  cmp     eax, 1
0x180024ff1  jle     short loc_18002501D
0x180024ff3  mov     rax, [rsp+1A8h+var_178]
0x180024ff8  mov     r8d, 23h ; '#'
0x180024ffe  lea     rdx, asc_1800C5250; "-----------------------------------"
0x180025005  lea     rcx, [rsp+1A8h+var_178]
0x18002500a  mov     rax, [rax+18h]
0x18002500e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025013  lea     rcx, [rsp+1A8h+var_178]
0x180025018  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18002501d  lea     r8, [rsp+1A8h+var_180]
0x180025022  lea     rdx, aRpcErrorRecord; "\nRPC Error Record {0}"
0x180025029  lea     rcx, [rsp+1A8h+var_178]
0x18002502e  call    ??$WriteLine@_WH$$V@TextWriter@cxl@@QEAAXPEB_WAEBH@Z; cxl::TextWriter::WriteLine<wchar_t,int,>(wchar_t const *,int const &)
0x180025033  mov     [rsp+1A8h+ErrorInfo.Version], 1
0x18002503e  mov     [rsp+1A8h+ErrorInfo.NumberOfParameters], r12d
0x180025046  mov     [rsp+1A8h+ErrorInfo.Flags], r12w
0x18002504f  lea     r8, [rsp+1A8h+ErrorInfo]; ErrorInfo
0x180025057  mov     edx, 1; CopyStrings
0x18002505c  lea     rcx, [rsp+1A8h+EnumHandle]; EnumHandle
0x180025061  call    cs:__imp_RpcErrorGetNextRecord
0x180025067  mov     [rsp+1A8h+var_188], eax
0x18002506b  cmp     eax, 6E1h
0x180025070  jz      short loc_18002508D
0x180025072  lea     rcx, [rsp+1A8h+var_178]
0x180025077  test    eax, eax
0x180025079  jz      short loc_1800250DF
0x18002507b  lea     r8, [rsp+1A8h+var_188]
0x180025080  lea     rdx, aFailedToEnumer_0; "Failed to enumerate extended error info"...
0x180025087  call    ??$WriteLine@_WJ$$V@TextWriter@cxl@@QEAAXPEB_WAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,long,>(wchar_t const *,long const &)
0x18002508c  nop
0x18002508d  lea     rcx, [rsp+1A8h+var_130]
0x180025092  call    cxl__ScopeGuardImpl__lambda_1e54ec72bada8c8e15f400892bf71413______ScopeGuardImpl__lambda_1e54ec72bada8c8e15f400892bf71413___
0x180025097  lea     rdx, [rsp+1A8h+var_78]
0x18002509f  mov     rcx, rsi
0x1800250a2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800250a7  nop
0x1800250a8  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x1800250af  mov     [rsp+1A8h+var_178], rax
0x1800250b4  lea     rcx, [rsp+1A8h+var_78]
0x1800250bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800250c1  nop
0x1800250c2  mov     rcx, [rsp+1A8h+var_38]
0x1800250ca  xor     rcx, rsp; StackCookie
0x1800250cd  call    __security_check_cookie
0x1800250d2  add     rsp, 188h
0x1800250d9  pop     r12
0x1800250db  pop     rdi
0x1800250dc  pop     rsi
0x1800250dd  pop     rbx
0x1800250de  retn
0x1800250df  mov     rax, [rsp+1A8h+var_178]
0x1800250e4  mov     r8d, 1Fh
0x1800250ea  lea     rdx, aExtendedRpcErr; "Extended RPC error information:"
0x1800250f1  mov     rax, [rax+18h]
0x1800250f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250fa  lea     rcx, [rsp+1A8h+var_178]
0x1800250ff  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180025104  mov     rdx, [rsp+1A8h+ErrorInfo.ComputerName]
0x18002510c  test    rdx, rdx
0x18002510f  jz      short loc_180025141
0x180025111  lea     rcx, [rsp+1A8h+var_58]
0x180025119  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002511e  nop
0x18002511f  mov     r8, rax
0x180025122  lea     rdx, aComputernameIs; "ComputerName is {0}"
0x180025129  lea     rcx, [rsp+1A8h+var_178]
0x18002512e  call    ??$WriteLine@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x180025133  nop
0x180025134  lea     rcx, [rsp+1A8h+var_58]
0x18002513c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025141  lea     r8, [rsp+1A8h+ErrorInfo.ProcessID]
0x180025149  lea     rdx, aProcessidIs0; "ProcessID is {0}"
0x180025150  lea     rcx, [rsp+1A8h+var_178]
0x180025155  call    ??$WriteLine@_WK$$V@TextWriter@cxl@@QEAAXPEB_WAEBK@Z; cxl::TextWriter::WriteLine<wchar_t,ulong,>(wchar_t const *,ulong const &)
0x18002515a  lea     rax, ??_7DateTime@cxl@@6B@; const cxl::DateTime::`vftable'
0x180025161  mov     [rsp+1A8h+var_140], rax
0x180025166  mov     rax, qword ptr [rsp+1A8h+ErrorInfo.u]
0x18002516e  mov     [rsp+1A8h+var_138], rax
0x180025173  lea     r8, [rsp+1A8h+var_140]
0x180025178  lea     rcx, [rsp+1A8h+var_178]
0x18002517d  call    ??$WriteLine@_WUDateTime@cxl@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBUDateTime@1@@Z; cxl::TextWriter::WriteLine<wchar_t,cxl::DateTime,>(wchar_t const *,cxl::DateTime const &)
0x180025182  lea     r8, [rsp+1A8h+ErrorInfo.GeneratingComponent]
0x18002518a  lea     rdx, aGeneratingComp; "Generating component is {0}"
0x180025191  lea     rcx, [rsp+1A8h+var_178]
0x180025196  call    ??$WriteLine@_WK$$V@TextWriter@cxl@@QEAAXPEB_WAEBK@Z; cxl::TextWriter::WriteLine<wchar_t,ulong,>(wchar_t const *,ulong const &)
0x18002519b  lea     r8, [rsp+1A8h+ErrorInfo.Status]
0x1800251a3  lea     rdx, aStatusIs0; "Status is {0}"
0x1800251aa  lea     rcx, [rsp+1A8h+var_178]
0x1800251af  call    ??$WriteLine@_WK$$V@TextWriter@cxl@@QEAAXPEB_WAEBK@Z; cxl::TextWriter::WriteLine<wchar_t,ulong,>(wchar_t const *,ulong const &)
0x1800251b4  movzx   eax, [rsp+1A8h+ErrorInfo.DetectionLocation]
0x1800251bc  mov     [rsp+1A8h+var_184], eax
0x1800251c0  lea     r8, [rsp+1A8h+var_184]
0x1800251c5  lea     rdx, aDetectionLocat; "Detection location is {0}"
0x1800251cc  lea     rcx, [rsp+1A8h+var_178]
0x1800251d1  call    ??$WriteLine@_WH$$V@TextWriter@cxl@@QEAAXPEB_WAEBH@Z; cxl::TextWriter::WriteLine<wchar_t,int,>(wchar_t const *,int const &)
0x1800251d6  lea     r8, [rsp+1A8h+ErrorInfo.Flags]
0x1800251de  lea     rcx, [rsp+1A8h+var_178]
0x1800251e3  call    ??$WriteLine@_WG$$V@TextWriter@cxl@@QEAAXPEB_WAEBG@Z; cxl::TextWriter::WriteLine<wchar_t,ushort,>(wchar_t const *,ushort const &)
0x1800251e8  lea     r8, [rsp+1A8h+ErrorInfo.NumberOfParameters]
0x1800251f0  lea     rdx, aNumberofparame; "NumberOfParameters is {0}"
0x1800251f7  lea     rcx, [rsp+1A8h+var_178]
0x1800251fc  call    ??$WriteLine@_WH$$V@TextWriter@cxl@@QEAAXPEB_WAEBH@Z; cxl::TextWriter::WriteLine<wchar_t,int,>(wchar_t const *,int const &)
0x180025201  xor     r8d, r8d
0x180025204  xor     eax, eax
0x180025206  xor     ecx, ecx
0x180025208  mov     [rsp+1A8h+var_184], r8d
0x18002520d  cmp     eax, [rsp+1A8h+ErrorInfo.NumberOfParameters]
0x180025214  jge     loc_18002538A
0x18002521a  movsxd  rax, ecx
0x18002521d  lea     rcx, [rax+rax*2]
0x180025221  mov     edx, [rsp+rcx*8+1A8h+ErrorInfo.Parameters.ParameterType]
0x180025228  sub     edx, 1
0x18002522b  jz      loc_18002533F
0x180025231  sub     edx, 1
0x180025234  jz      loc_1800252FE
0x18002523a  sub     edx, 1
0x18002523d  jz      loc_1800252D5
0x180025243  sub     edx, 1
0x180025246  jz      short loc_1800252AA
0x180025248  sub     edx, 1
0x18002524b  jz      short loc_18002528B
0x18002524d  cmp     edx, 1
0x180025250  jz      short loc_18002527D
0x180025252  movsxd  rax, r8d
0x180025255  lea     rcx, [rax+rax*2]
0x180025259  mov     eax, [rsp+rcx*8+1A8h+ErrorInfo.Parameters.ParameterType]
0x180025260  mov     [rsp+1A8h+var_17C], eax
0x180025264  lea     r9, [rsp+1A8h+var_17C]
0x180025269  lea     r8, [rsp+1A8h+var_184]
0x18002526e  lea     rcx, [rsp+1A8h+var_178]
0x180025273  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x180025278  jmp     loc_180025377
0x18002527d  lea     r8, [rsp+1A8h+var_184]
0x180025282  lea     rdx, aParameter0Trun; "(parameter {0} truncated"
0x180025289  jmp     short loc_1800252C9
0x18002528b  movsxd  rax, r8d
0x18002528e  lea     rcx, [rax+rax*2]
0x180025292  lea     r8, [rsp+1A8h+ErrorInfo.Parameters.u]
0x18002529a  lea     r8, [r8+rcx*8]
0x18002529e  lea     rcx, [rsp+1A8h+var_178]
0x1800252a3  call    ??$WriteLine@_W_K$$V@TextWriter@cxl@@QEAAXPEB_WAEB_K@Z; cxl::TextWriter::WriteLine<wchar_t,unsigned __int64,>(wchar_t const *,unsigned __int64 const &)
0x1800252a8  jmp     short loc_180025278
0x1800252aa  movsxd  rax, r8d
0x1800252ad  lea     rcx, [rax+rax*2]
0x1800252b1  movsx   eax, word ptr [rsp+rcx*8+1A8h+ErrorInfo.Parameters.u]
0x1800252b9  mov     [rsp+1A8h+var_17C], eax
0x1800252bd  lea     r8, [rsp+1A8h+var_17C]
0x1800252c2  lea     rdx, aShortVal0; "Short val: {0}"
0x1800252c9  lea     rcx, [rsp+1A8h+var_178]
0x1800252ce  call    ??$WriteLine@_WH$$V@TextWriter@cxl@@QEAAXPEB_WAEBH@Z; cxl::TextWriter::WriteLine<wchar_t,int,>(wchar_t const *,int const &)
0x1800252d3  jmp     short loc_180025278
0x1800252d5  movsxd  rax, r8d
0x1800252d8  lea     rcx, [rax+rax*2]
0x1800252dc  lea     r8, [rsp+1A8h+ErrorInfo.Parameters.u]
0x1800252e4  lea     r8, [r8+rcx*8]
0x1800252e8  lea     rdx, aLongVal0; "Long val: {0}"
0x1800252ef  lea     rcx, [rsp+1A8h+var_178]
0x1800252f4  call    ??$WriteLine@_WJ$$V@TextWriter@cxl@@QEAAXPEB_WAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,long,>(wchar_t const *,long const &)
0x1800252f9  jmp     loc_180025278
0x1800252fe  movsxd  rax, r8d
0x180025301  lea     rdx, [rax+rax*2]
0x180025305  mov     rdx, qword ptr [rsp+rdx*8+1A8h+ErrorInfo.Parameters.u]
0x18002530d  lea     rcx, [rsp+1A8h+var_58]
0x180025315  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002531a  nop
0x18002531b  mov     r8, rax
0x18002531e  lea     rdx, aUnicodeString0; "Unicode string: {0}"
0x180025325  lea     rcx, [rsp+1A8h+var_178]
0x18002532a  call    ??$WriteLine@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x18002532f  nop
0x180025330  lea     rcx, [rsp+1A8h+var_58]
0x180025338  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002533d  jmp     short loc_180025377
0x18002533f  movsxd  rax, r8d
0x180025342  lea     rdx, [rax+rax*2]
0x180025346  mov     rdx, qword ptr [rsp+rdx*8+1A8h+ErrorInfo.Parameters.u]
0x18002534e  lea     rcx, [rsp+1A8h+var_58]
0x180025356  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002535b  nop
0x18002535c  mov     r8, rax
0x18002535f  lea     rcx, [rsp+1A8h+var_178]
0x180025364  call    ??$WriteLine@_WV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,std::string,>(wchar_t const *,std::string const &)
0x180025369  nop
0x18002536a  lea     rcx, [rsp+1A8h+var_58]
0x180025372  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180025377  mov     r8d, [rsp+1A8h+var_184]
0x18002537c  inc     r8d
0x18002537f  mov     eax, r8d
0x180025382  mov     ecx, r8d
0x180025385  jmp     loc_180025208
0x18002538a  cmp     [rsp+1A8h+ErrorInfo.ComputerName], 0
0x180025393  jz      short loc_1800253AE
0x180025395  call    cs:__imp_GetProcessHeap
0x18002539b  mov     rcx, rax; hHeap
0x18002539e  mov     r8, [rsp+1A8h+ErrorInfo.ComputerName]; lpMem
0x1800253a6  xor     edx, edx; dwFlags
0x1800253a8  call    cs:__imp_HeapFree
0x1800253ae  xor     edi, edi
0x1800253b0  cmp     [rsp+1A8h+ErrorInfo.NumberOfParameters], edi
0x1800253b7  jle     short loc_1800253F8
0x1800253b9  movsxd  rax, edi
0x1800253bc  lea     rbx, [rax+rax*2]
0x1800253c0  mov     ecx, [rsp+rbx*8+1A8h+ErrorInfo.Parameters.ParameterType]
0x1800253c7  sub     ecx, 1
0x1800253ca  jz      short loc_1800253D1
0x1800253cc  cmp     ecx, 1
0x1800253cf  jnz     short loc_1800253ED
0x1800253d1  mov     rbx, qword ptr [rsp+rbx*8+1A8h+ErrorInfo.Parameters.u]
0x1800253d9  call    cs:__imp_GetProcessHeap
0x1800253df  mov     r8, rbx; lpMem
0x1800253e2  xor     edx, edx; dwFlags
0x1800253e4  mov     rcx, rax; hHeap
0x1800253e7  call    cs:__imp_HeapFree
0x1800253ed  inc     edi
0x1800253ef  cmp     edi, [rsp+1A8h+ErrorInfo.NumberOfParameters]
0x1800253f6  jl      short loc_1800253B9
0x1800253f8  mov     eax, [rsp+1A8h+var_180]
0x1800253fc  jmp     loc_180024FDD
```
