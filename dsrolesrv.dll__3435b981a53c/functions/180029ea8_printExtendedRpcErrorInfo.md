# printExtendedRpcErrorInfo

- ea: `0x180029ea8`
- end: `0x18002a268`
- name: `printExtendedRpcErrorInfo`
- size: `960`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029220`
- `0x1800295c0`

## callees

- `0x180029d64`
- `0x180029ea8`
- `0x18002c01e`
- `0x18002c050`
- `0x18002e010`

## import_xrefs

- `RPCRT4!RpcErrorGetNextRecord` at `0x180029fd9`
- `RPCRT4!RpcErrorGetNextRecord` at `0x180029fd9`
- `RPCRT4!I_RpcGetExtendedError` at `0x180029f02`
- `RPCRT4!I_RpcGetExtendedError` at `0x180029f02`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180029f3d`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180029f3d`
- `RPCRT4!RpcErrorEndEnumeration` at `0x18002a23e`
- `RPCRT4!RpcErrorEndEnumeration` at `0x18002a23e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a206`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a206`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a014`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a1f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a014`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a1f8`
- `KERNEL32!FileTimeToSystemTime` at `0x18002a04d`
- `KERNEL32!FileTimeToSystemTime` at `0x18002a04d`

## string_xrefs

- `0x18002a22a`: `DnsRpcError: error %1!d! during error info enumeration`
- `0x18002a008`: `DnsRpcError: ComputerName %1!s!`
- `0x18002a039`: `DnsRpcError: ProcessID is %1!d!`
- `0x18002a0ac`: `DnsRpcError: Generating component is %1!d!`

## pseudocode

```c
void __fastcall printExtendedRpcErrorInfo(unsigned int a1)
{
  unsigned int v1; // esi
  RPC_STATUS ExtendedError; // eax
  unsigned int v3; // ebx
  RPC_STATUS started; // eax
  unsigned int v5; // edi
  unsigned int NextRecord; // eax
  HANDLE ProcessHeap; // rax
  int v8; // edi
  LPSTR AnsiString; // rbx
  HANDLE v10; // rax
  __int64 v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+28h] [rbp-D8h]
  __int64 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+38h] [rbp-C8h]
  RPC_ERROR_ENUM_HANDLE EnumHandle; // [rsp+50h] [rbp-B0h] BYREF
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+110h] [rbp+10h] BYREF

  if ( !a1 )
    return;
  v1 = 0;
  memset(&EnumHandle, 0, 20);
  if ( g_LogFnPtr )
    g_LogFnPtr(L"DnsRpcError: received error %1!d!", a1);
  ExtendedError = I_RpcGetExtendedError();
  v3 = ExtendedError;
  if ( ExtendedError )
  {
    if ( ExtendedError < 0 )
      v1 = dns_MapRpcExtendedHResultToWin32((unsigned int)ExtendedError);
    if ( g_LogFnPtr )
      g_LogFnPtr(L"DnsRpcError: extended error code HResult %1!d! Win32 %2!d!", v3, v1);
  }
  started = RpcErrorStartEnumeration(&EnumHandle);
  v5 = started;
  if ( !started )
  {
    *(&ErrorInfo.Version + 1) = 0;
    memset_0(&ErrorInfo, 0, 0x94u);
    SystemTime = 0;
    while ( 1 )
    {
LABEL_15:
      ErrorInfo.Version = 1;
      ErrorInfo.NumberOfParameters = 4;
      ErrorInfo.Flags = 4;
      NextRecord = RpcErrorGetNextRecord(&EnumHandle, 1, &ErrorInfo);
      if ( NextRecord == 1761 )
        goto LABEL_61;
      if ( NextRecord )
        break;
      if ( ErrorInfo.ComputerName )
      {
        if ( g_LogFnPtr )
          g_LogFnPtr(L"DnsRpcError: ComputerName %1!s!");
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, ErrorInfo.ComputerName);
      }
      if ( g_LogFnPtr )
        g_LogFnPtr(L"DnsRpcError: ProcessID is %1!d!", ErrorInfo.ProcessID);
      FileTimeToSystemTime((const FILETIME *)&ErrorInfo.u, &SystemTime);
      if ( g_LogFnPtr )
      {
        LODWORD(v14) = SystemTime.wMilliseconds;
        LODWORD(v13) = SystemTime.wSecond;
        LODWORD(v12) = SystemTime.wMinute;
        LODWORD(v11) = SystemTime.wHour;
        g_LogFnPtr(
          L"DnsRpcError: system time is: %1!d!/%2!d!/%3!d! %4!d!:%5!d!:%6!d!:%7!d!",
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wYear,
          v11,
          v12,
          v13,
          v14);
      }
      if ( g_LogFnPtr )
        g_LogFnPtr(L"DnsRpcError: Generating component is %1!d!", ErrorInfo.GeneratingComponent);
      if ( g_LogFnPtr )
        g_LogFnPtr(L"DnsRpcError: Status is %1!d!", ErrorInfo.Status);
      if ( g_LogFnPtr )
        g_LogFnPtr(L"DnsRpcError: Detection location is %1!d!", ErrorInfo.DetectionLocation);
      if ( g_LogFnPtr )
        g_LogFnPtr(L"DnsRpcError: Flags is %1!d!", ErrorInfo.Flags);
      if ( g_LogFnPtr )
        g_LogFnPtr(L"DnsRpcError: NumberOfParameters is %1!d!", (unsigned int)ErrorInfo.NumberOfParameters);
      v8 = 0;
      if ( ErrorInfo.NumberOfParameters > 0 )
      {
        while ( 1 )
        {
          if ( ErrorInfo.Parameters[v8].ParameterType == eeptAnsiString )
          {
            if ( g_LogFnPtr )
              g_LogFnPtr(L"DnsRpcError: Ansi string: %1!S!", ErrorInfo.Parameters[v8].u.PVal);
          }
          else
          {
            if ( ErrorInfo.Parameters[v8].ParameterType != eeptUnicodeString )
            {
              switch ( ErrorInfo.Parameters[v8].ParameterType )
              {
                case eeptLongVal:
                  if ( g_LogFnPtr )
                    g_LogFnPtr(L"DnsRpcError: Long val: %1!d!");
                  break;
                case eeptShortVal:
                  if ( g_LogFnPtr )
                    g_LogFnPtr(L"DnsRpcError: Short val: %1!d!");
                  break;
                case eeptPointerVal:
                  if ( g_LogFnPtr )
                    g_LogFnPtr(L"DnsRpcError: Pointer val: %1!d!", ErrorInfo.Parameters[v8].u.PVal);
                  break;
                case eeptNone:
                  if ( g_LogFnPtr )
                    g_LogFnPtr(L"DnsRpcError: Truncated");
                  break;
                default:
                  if ( g_LogFnPtr )
                    g_LogFnPtr(L"DnsRpcError: Invalid type: %1!d!");
                  break;
              }
              goto LABEL_57;
            }
            if ( g_LogFnPtr )
              g_LogFnPtr(L"DnsRpcError: Unicode string: %1!s!", ErrorInfo.Parameters[v8].u.PVal);
          }
          AnsiString = ErrorInfo.Parameters[v8].u.AnsiString;
          v10 = GetProcessHeap();
          HeapFree(v10, 0, AnsiString);
LABEL_57:
          if ( ++v8 >= ErrorInfo.NumberOfParameters )
            goto LABEL_15;
        }
      }
    }
    if ( g_LogFnPtr )
      g_LogFnPtr(L"DnsRpcError: error %1!d! during error info enumeration", NextRecord);
LABEL_61:
    RpcErrorEndEnumeration(&EnumHandle);
    return;
  }
  if ( started != 1761 && g_LogFnPtr )
  {
    g_LogFnPtr(L"DnsRpcError: extended error code HResult %1!d! Win32 %2!d!", v3, v1);
    if ( g_LogFnPtr )
      g_LogFnPtr(L"DnsRpcError: error %1!d! retrieving RPC error information", v5);
  }
}

```

## disassembly

```asm
0x180029ea8  test    ecx, ecx
0x180029eaa  jz      locret_18002A267
0x180029eb0  mov     [rsp-8+arg_8], rbx
0x180029eb5  mov     [rsp-8+arg_10], rsi
0x180029eba  push    rbp
0x180029ebb  push    rdi
0x180029ebc  push    r14
0x180029ebe  lea     rbp, [rsp-30h]
0x180029ec3  sub     rsp, 130h
0x180029eca  mov     rax, cs:__security_cookie
0x180029ed1  xor     rax, rsp
0x180029ed4  mov     [rbp+40h+var_20], rax
0x180029ed8  xor     eax, eax
0x180029eda  xor     esi, esi
0x180029edc  mov     dword ptr [rsp+140h+EnumHandle.Head], eax
0x180029ee0  xorps   xmm0, xmm0
0x180029ee3  mov     rax, cs:g_LogFnPtr
0x180029eea  movups  xmmword ptr [rsp+140h+EnumHandle.Signature], xmm0
0x180029eef  test    rax, rax
0x180029ef2  jz      short loc_180029F02
0x180029ef4  mov     edx, ecx
0x180029ef6  lea     rcx, aDnsrpcerrorRec; "DnsRpcError: received error %1!d!"
0x180029efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f02  call    cs:__imp_I_RpcGetExtendedError
0x180029f08  mov     ebx, eax
0x180029f0a  test    eax, eax
0x180029f0c  jz      short loc_180029F38
0x180029f0e  test    eax, eax
0x180029f10  jns     short loc_180029F1B
0x180029f12  mov     ecx, eax
0x180029f14  call    dns_MapRpcExtendedHResultToWin32
0x180029f19  mov     esi, eax
0x180029f1b  mov     rax, cs:g_LogFnPtr
0x180029f22  test    rax, rax
0x180029f25  jz      short loc_180029F38
0x180029f27  mov     r8d, esi
0x180029f2a  lea     rcx, aDnsrpcerrorExt; "DnsRpcError: extended error code HResul"...
0x180029f31  mov     edx, ebx
0x180029f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f38  lea     rcx, [rsp+140h+EnumHandle]; EnumHandle
0x180029f3d  call    cs:__imp_RpcErrorStartEnumeration
0x180029f43  mov     edi, eax
0x180029f45  test    eax, eax
0x180029f47  jz      short loc_180029F98
0x180029f49  cmp     eax, 6E1h
0x180029f4e  jz      loc_18002A244
0x180029f54  mov     rax, cs:g_LogFnPtr
0x180029f5b  test    rax, rax
0x180029f5e  jz      loc_18002A244
0x180029f64  mov     r8d, esi
0x180029f67  lea     rcx, aDnsrpcerrorExt; "DnsRpcError: extended error code HResul"...
0x180029f6e  mov     edx, ebx
0x180029f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f75  mov     rax, cs:g_LogFnPtr
0x180029f7c  test    rax, rax
0x180029f7f  jz      loc_18002A244
0x180029f85  mov     edx, edi
0x180029f87  lea     rcx, aDnsrpcerrorErr; "DnsRpcError: error %1!d! retrieving RPC"...
0x180029f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f93  jmp     loc_18002A244
0x180029f98  xor     eax, eax
0x180029f9a  lea     rcx, [rsp+140h+ErrorInfo]; void *
0x180029f9f  xor     edx, edx; Val
0x180029fa1  mov     dword ptr [rsp+140h+ErrorInfo+4], eax
0x180029fa5  mov     r8d, 94h; Size
0x180029fab  call    memset_0
0x180029fb0  mov     esi, 1
0x180029fb5  xorps   xmm0, xmm0
0x180029fb8  movups  xmmword ptr [rbp+40h+SystemTime.wYear], xmm0
0x180029fbc  lea     r14d, [rsi+3]
0x180029fc0  lea     r8, [rsp+140h+ErrorInfo]; ErrorInfo
0x180029fc5  mov     [rsp+140h+ErrorInfo.Version], esi
0x180029fc9  mov     edx, esi; CopyStrings
0x180029fcb  mov     [rbp+40h+ErrorInfo.NumberOfParameters], r14d
0x180029fcf  lea     rcx, [rsp+140h+EnumHandle]; EnumHandle
0x180029fd4  mov     [rbp+40h+ErrorInfo.Flags], r14w
0x180029fd9  call    cs:__imp_RpcErrorGetNextRecord
0x180029fdf  cmp     eax, 6E1h
0x180029fe4  jz      loc_18002A239
0x180029fea  test    eax, eax
0x180029fec  jnz     loc_18002A21C
0x180029ff2  mov     rdx, [rsp+140h+ErrorInfo.ComputerName]
0x180029ff7  test    rdx, rdx
0x180029ffa  jz      short loc_18002A02A
0x180029ffc  mov     rax, cs:g_LogFnPtr
0x18002a003  test    rax, rax
0x18002a006  jz      short loc_18002A014
0x18002a008  lea     rcx, aDnsrpcerrorCom; "DnsRpcError: ComputerName %1!s!"
0x18002a00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a014  call    cs:__imp_GetProcessHeap
0x18002a01a  mov     r8, [rsp+140h+ErrorInfo.ComputerName]; lpMem
0x18002a01f  xor     edx, edx; dwFlags
0x18002a021  mov     rcx, rax; hHeap
0x18002a024  call    cs:__imp_HeapFree
0x18002a02a  mov     rax, cs:g_LogFnPtr
0x18002a031  test    rax, rax
0x18002a034  jz      short loc_18002A045
0x18002a036  mov     edx, [rbp+40h+ErrorInfo.ProcessID]
0x18002a039  lea     rcx, aDnsrpcerrorPro; "DnsRpcError: ProcessID is %1!d!"
0x18002a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a045  lea     rdx, [rbp+40h+SystemTime]; lpSystemTime
0x18002a049  lea     rcx, [rbp+40h+ErrorInfo.u]; lpFileTime
0x18002a04d  call    cs:__imp_FileTimeToSystemTime
0x18002a053  mov     rax, cs:g_LogFnPtr
0x18002a05a  test    rax, rax
0x18002a05d  jz      short loc_18002A09D
0x18002a05f  movzx   ecx, [rbp+40h+SystemTime.wMilliseconds]
0x18002a063  movzx   r10d, [rbp+40h+SystemTime.wSecond]
0x18002a068  movzx   r11d, [rbp+40h+SystemTime.wMinute]
0x18002a06d  movzx   ebx, [rbp+40h+SystemTime.wHour]
0x18002a071  movzx   r9d, [rbp+40h+SystemTime.wYear]
0x18002a076  movzx   r8d, [rbp+40h+SystemTime.wDay]
0x18002a07b  movzx   edx, [rbp+40h+SystemTime.wMonth]
0x18002a07f  mov     dword ptr [rsp+140h+var_108], ecx
0x18002a083  lea     rcx, aDnsrpcerrorSys; "DnsRpcError: system time is: %1!d!/%2!d"...
0x18002a08a  mov     dword ptr [rsp+140h+var_110], r10d
0x18002a08f  mov     dword ptr [rsp+140h+var_118], r11d
0x18002a094  mov     dword ptr [rsp+140h+var_120], ebx
0x18002a098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a09d  mov     rax, cs:g_LogFnPtr
0x18002a0a4  test    rax, rax
0x18002a0a7  jz      short loc_18002A0B8
0x18002a0a9  mov     edx, [rbp+40h+ErrorInfo.GeneratingComponent]
0x18002a0ac  lea     rcx, aDnsrpcerrorGen; "DnsRpcError: Generating component is %1"...
0x18002a0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0b8  mov     rax, cs:g_LogFnPtr
0x18002a0bf  test    rax, rax
0x18002a0c2  jz      short loc_18002A0D3
0x18002a0c4  mov     edx, [rbp+40h+ErrorInfo.Status]
0x18002a0c7  lea     rcx, aDnsrpcerrorSta; "DnsRpcError: Status is %1!d!"
0x18002a0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0d3  mov     rax, cs:g_LogFnPtr
0x18002a0da  test    rax, rax
0x18002a0dd  jz      short loc_18002A0EF
0x18002a0df  movzx   edx, [rbp+40h+ErrorInfo.DetectionLocation]
0x18002a0e3  lea     rcx, aDnsrpcerrorDet; "DnsRpcError: Detection location is %1!d"...
0x18002a0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0ef  mov     rax, cs:g_LogFnPtr
0x18002a0f6  test    rax, rax
0x18002a0f9  jz      short loc_18002A10B
0x18002a0fb  movzx   edx, [rbp+40h+ErrorInfo.Flags]
0x18002a0ff  lea     rcx, aDnsrpcerrorFla; "DnsRpcError: Flags is %1!d!"
0x18002a106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a10b  mov     rax, cs:g_LogFnPtr
0x18002a112  test    rax, rax
0x18002a115  jz      short loc_18002A126
0x18002a117  mov     edx, [rbp+40h+ErrorInfo.NumberOfParameters]
0x18002a11a  lea     rcx, aDnsrpcerrorNum; "DnsRpcError: NumberOfParameters is %1!d"...
0x18002a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a126  xor     edi, edi
0x18002a128  cmp     [rbp+40h+ErrorInfo.NumberOfParameters], edi
0x18002a12b  jle     loc_180029FC0
0x18002a131  movsxd  rax, edi
0x18002a134  lea     rbx, [rax+rax*2]
0x18002a138  mov     rax, cs:g_LogFnPtr
0x18002a13f  mov     edx, [rbp+rbx*8+40h+ErrorInfo.Parameters.ParameterType]
0x18002a143  mov     ecx, edx
0x18002a145  sub     ecx, esi
0x18002a147  jz      loc_18002A1DD
0x18002a14d  sub     ecx, esi
0x18002a14f  jz      short loc_18002A1CF
0x18002a151  sub     ecx, esi
0x18002a153  jz      short loc_18002A1BD
0x18002a155  sub     ecx, esi
0x18002a157  jz      short loc_18002A1AA
0x18002a159  sub     ecx, esi
0x18002a15b  jz      short loc_18002A192
0x18002a15d  cmp     ecx, esi
0x18002a15f  jz      short loc_18002A17B
0x18002a161  test    rax, rax
0x18002a164  jz      loc_18002A20C
0x18002a16a  lea     rcx, aDnsrpcerrorInv; "DnsRpcError: Invalid type: %1!d!"
0x18002a171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a176  jmp     loc_18002A20C
0x18002a17b  test    rax, rax
0x18002a17e  jz      loc_18002A20C
0x18002a184  lea     rcx, aDnsrpcerrorTru; "DnsRpcError: Truncated"
0x18002a18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a190  jmp     short loc_18002A20C
0x18002a192  test    rax, rax
0x18002a195  jz      short loc_18002A20C
0x18002a197  mov     rdx, qword ptr [rbp+rbx*8+40h+ErrorInfo.Parameters.u]
0x18002a19c  lea     rcx, aDnsrpcerrorPoi; "DnsRpcError: Pointer val: %1!d!"
0x18002a1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1a8  jmp     short loc_18002A20C
0x18002a1aa  test    rax, rax
0x18002a1ad  jz      short loc_18002A20C
0x18002a1af  movsx   edx, word ptr [rbp+rbx*8+40h+ErrorInfo.Parameters.u]
0x18002a1b4  lea     rcx, aDnsrpcerrorSho; "DnsRpcError: Short val: %1!d!"
0x18002a1bb  jmp     short loc_18002A171
0x18002a1bd  test    rax, rax
0x18002a1c0  jz      short loc_18002A20C
0x18002a1c2  mov     edx, dword ptr [rbp+rbx*8+40h+ErrorInfo.Parameters.u]
0x18002a1c6  lea     rcx, aDnsrpcerrorLon; "DnsRpcError: Long val: %1!d!"
0x18002a1cd  jmp     short loc_18002A171
0x18002a1cf  test    rax, rax
0x18002a1d2  jz      short loc_18002A1F3
0x18002a1d4  lea     rcx, aDnsrpcerrorUni; "DnsRpcError: Unicode string: %1!s!"
0x18002a1db  jmp     short loc_18002A1E9
0x18002a1dd  test    rax, rax
0x18002a1e0  jz      short loc_18002A1F3
0x18002a1e2  lea     rcx, aDnsrpcerrorAns; "DnsRpcError: Ansi string: %1!S!"
0x18002a1e9  mov     rdx, qword ptr [rbp+rbx*8+40h+ErrorInfo.Parameters.u]
0x18002a1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1f3  mov     rbx, qword ptr [rbp+rbx*8+40h+ErrorInfo.Parameters.u]
0x18002a1f8  call    cs:__imp_GetProcessHeap
0x18002a1fe  mov     r8, rbx; lpMem
0x18002a201  xor     edx, edx; dwFlags
0x18002a203  mov     rcx, rax; hHeap
0x18002a206  call    cs:__imp_HeapFree
0x18002a20c  add     edi, esi
0x18002a20e  cmp     edi, [rbp+40h+ErrorInfo.NumberOfParameters]
0x18002a211  jl      loc_18002A131
0x18002a217  jmp     loc_180029FC0
0x18002a21c  mov     r8, cs:g_LogFnPtr
0x18002a223  test    r8, r8
0x18002a226  jz      short loc_18002A239
0x18002a228  mov     edx, eax
0x18002a22a  lea     rcx, aDnsrpcerrorErr_0; "DnsRpcError: error %1!d! during error i"...
0x18002a231  mov     rax, r8
0x18002a234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a239  lea     rcx, [rsp+140h+EnumHandle]; EnumHandle
0x18002a23e  call    cs:__imp_RpcErrorEndEnumeration
0x18002a244  mov     rcx, [rbp+40h+var_20]
0x18002a248  xor     rcx, rsp; StackCookie
0x18002a24b  call    __security_check_cookie
0x18002a250  lea     r11, [rsp+140h+var_10]
0x18002a258  mov     rbx, [r11+28h]
0x18002a25c  mov     rsi, [r11+30h]
0x18002a260  mov     rsp, r11
0x18002a263  pop     r14
0x18002a265  pop     rdi
0x18002a266  pop     rbp
0x18002a267  retn
```
