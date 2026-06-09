# GetCommonHttpRequestHeaders(ushort * *,unsigned __int64 *)

- ea: `0x18006d4b8`
- end: `0x18006dacf`
- name: `?GetCommonHttpRequestHeaders@@YAJPEAPEAGPEA_K@Z`
- size: `1559`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007bfb4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`
- `0x18004654c`
- `0x180067c6c`
- `0x18006d4b8`
- `0x18006dad8`
- `0x18006e14c`
- `0x18006e8e0`
- `0x180097e38`

## string_xrefs

- `0x18006d5a9`: `GetCommonHttpRequestHeaders`
- `0x18006d5c3`: `GetCommonHttpRequestHeaders`
- `0x18006d612`: `GetCommonHttpRequestHeaders`
- `0x18006d65c`: `GetCommonHttpRequestHeaders`
- `0x18006d6a9`: `GetCommonHttpRequestHeaders`
- `0x18006d6e1`: `GetCommonHttpRequestHeaders`
- `0x18006d75b`: `GetCommonHttpRequestHeaders`
- `0x18006d77b`: `GetCommonHttpRequestHeaders`
- `0x18006d79e`: `GetCommonHttpRequestHeaders`
- `0x18006d8f3`: `GetCommonHttpRequestHeaders`
- `0x18006d991`: `GetCommonHttpRequestHeaders`
- `0x18006da0c`: `GetCommonHttpRequestHeaders`
- `0x18006da9f`: `GetCommonHttpRequestHeaders`
- `0x18006d655`: `GetDllVersionInfo`
- `0x18006d6a2`: `GetDllVersionInfo`
- `0x18006d782`: `%s: %d disallowed character(s) were removed from target server value.`
- `0x18006d94c`: `User-Agent: Dsreg/%s (Windows %s)\nocp-adrs-client-name: Dsreg\nocp-adrs-client-version: %s\n`

## pseudocode

```c
__int64 __fastcall GetCommonHttpRequestHeaders(unsigned __int16 **a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rax
  int OSVersionInfo; // [rsp+50h] [rbp-3F8h]
  int TargetServer; // [rsp+50h] [rbp-3F8h]
  int v6; // [rsp+54h] [rbp-3F4h] BYREF
  unsigned __int16 *v7; // [rsp+58h] [rbp-3F0h] BYREF
  wchar_t *v8; // [rsp+60h] [rbp-3E8h]
  unsigned __int64 v9; // [rsp+68h] [rbp-3E0h] BYREF
  unsigned __int64 v10; // [rsp+70h] [rbp-3D8h]
  wchar_t *Buffer; // [rsp+78h] [rbp-3D0h] BYREF
  __int64 v12; // [rsp+80h] [rbp-3C8h]
  __int64 v13; // [rsp+88h] [rbp-3C0h]
  __int64 v14; // [rsp+90h] [rbp-3B8h]
  unsigned __int64 v15; // [rsp+98h] [rbp-3B0h] BYREF
  unsigned __int16 *v16; // [rsp+A0h] [rbp-3A8h]
  wchar_t *v17; // [rsp+A8h] [rbp-3A0h]
  unsigned __int16 *v18; // [rsp+B0h] [rbp-398h]
  wchar_t *v19; // [rsp+B8h] [rbp-390h]
  void *Block; // [rsp+C0h] [rbp-388h]
  unsigned __int16 v21[56]; // [rsp+D0h] [rbp-378h] BYREF
  wchar_t v22[56]; // [rsp+140h] [rbp-308h] BYREF
  unsigned __int16 v23[56]; // [rsp+1B0h] [rbp-298h] BYREF
  unsigned __int16 v24[264]; // [rsp+220h] [rbp-228h] BYREF

  memset(v22, 0, 0x64u);
  memset(v23, 0, 0x64u);
  memset(v21, 0, 0x64u);
  memset(v24, 0, 0x20Au);
  v7 = 0;
  v6 = 0;
  v8 = 0;
  Buffer = 0;
  v10 = 0;
  v9 = 0;
  v15 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    OSVersionInfo = GetOSVersionInfo(v22, 0x32u);
    if ( OSVersionInfo >= 0 )
    {
      OSVersionInfo = GetDllVersionInfo(v23, 0x32u, 0);
      if ( OSVersionInfo < 0 || (OSVersionInfo = GetDllVersionInfo(v21, 0x32u, 1), OSVersionInfo < 0) )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"GetCommonHttpRequestHeaders",
          L"GetDllVersionInfo",
          (unsigned int)OSVersionInfo);
      }
      else
      {
        TargetServer = GetTargetServer(&v7);
        if ( TargetServer >= 0 )
        {
          if ( !(unsigned int)IsEmptyString(v7) )
          {
            if ( !(unsigned int)SanitizeHttpHeaderValue(v7, v24, 0x105u, &v15, &v6) )
              Logger::TraceWarning(
                (wchar_t *)L"%s: Target server value is truncated to %zu characters.",
                L"GetCommonHttpRequestHeaders",
                260);
            if ( v6 > 0 )
              Logger::TraceWarning(
                (wchar_t *)L"%s: %d disallowed character(s) were removed from target server value.",
                L"GetCommonHttpRequestHeaders",
                (unsigned int)v6);
            Logger::TraceInformation(
              L"%s: Header value for \"%s\" is \"%s\"",
              L"GetCommonHttpRequestHeaders",
              L"x-ms-target-dc",
              v24);
          }
        }
        else
        {
          Logger::TraceWarning(
            (wchar_t *)L"%s: GetTargetServer failed with error code %08x.",
            L"GetCommonHttpRequestHeaders",
            (unsigned int)TargetServer);
          SafeFree(v7);
          v7 = 0;
        }
        v16 = v23;
        v12 = -1;
        do
          ++v12;
        while ( v16[v12] );
        v17 = v22;
        v13 = -1;
        do
          ++v13;
        while ( v17[v13] );
        v18 = v21;
        v14 = -1;
        do
          ++v14;
        while ( v18[v14] );
        v10 = v14 + v12 + v13 + 93;
        if ( v15 )
          v10 += v15 + 20;
        v2 = 2 * v10;
        if ( !is_mul_ok(v10, 2u) )
          v2 = -1;
        v19 = (wchar_t *)operator new[](v2, (const struct std::nothrow_t *)&std::nothrow);
        v8 = v19;
        if ( v19 )
        {
          v9 = v10;
          Buffer = v8;
          OSVersionInfo = StringCchPrintfExW(
                            v8,
                            v10,
                            &Buffer,
                            &v9,
                            0,
                            L"User-Agent: Dsreg/%s (Windows %s)\r\n"
                             "ocp-adrs-client-name: Dsreg\r\n"
                             "ocp-adrs-client-version: %s\r\n",
                            v23,
                            v22,
                            v21);
          if ( OSVersionInfo < 0
            || v15
            && (OSVersionInfo = StringCchPrintfExW(Buffer, v9, &Buffer, &v9, 0, L"x-ms-target-dc: %s\r\n", v24),
                OSVersionInfo < 0) )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"GetCommonHttpRequestHeaders",
              L"StringCchPrintfExW",
              (unsigned int)OSVersionInfo);
          }
          else
          {
            *a1 = v8;
            v8 = 0;
            if ( a2 )
              *a2 = v10 - v9;
          }
        }
        else
        {
          OSVersionInfo = -2147024882;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetCommonHttpRequestHeaders");
        }
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetCommonHttpRequestHeaders",
        L"GetOSVersionInfo",
        (unsigned int)OSVersionInfo);
    }
  }
  else
  {
    OSVersionInfo = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetCommonHttpRequestHeaders", L"pBuffer");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetCommonHttpRequestHeaders", L"pBuffer");
  }
  SafeFree(v7);
  v7 = 0;
  Block = v8;
  operator delete(v8);
  v8 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"GetCommonHttpRequestHeaders", (unsigned int)OSVersionInfo);
  return (unsigned int)OSVersionInfo;
}

```

## disassembly

```asm
0x18006d4b8  mov     [rsp+arg_8], rdx
0x18006d4bd  mov     [rsp+arg_0], rcx
0x18006d4c2  push    rdi
0x18006d4c3  sub     rsp, 440h
0x18006d4ca  mov     rax, cs:__security_cookie
0x18006d4d1  xor     rax, rsp
0x18006d4d4  mov     [rsp+448h+var_18], rax
0x18006d4dc  mov     [rsp+448h+var_3F8], 0
0x18006d4e4  lea     rax, [rsp+448h+var_308]
0x18006d4ec  mov     rdi, rax
0x18006d4ef  xor     eax, eax
0x18006d4f1  mov     ecx, 64h ; 'd'
0x18006d4f6  rep stosb
0x18006d4f8  lea     rax, [rsp+448h+var_298]
0x18006d500  mov     rdi, rax
0x18006d503  xor     eax, eax
0x18006d505  mov     ecx, 64h ; 'd'
0x18006d50a  rep stosb
0x18006d50c  lea     rax, [rsp+448h+var_378]
0x18006d514  mov     rdi, rax
0x18006d517  xor     eax, eax
0x18006d519  mov     ecx, 64h ; 'd'
0x18006d51e  rep stosb
0x18006d520  lea     rax, [rsp+448h+var_228]
0x18006d528  mov     rdi, rax
0x18006d52b  xor     eax, eax
0x18006d52d  mov     ecx, 20Ah
0x18006d532  rep stosb
0x18006d534  mov     [rsp+448h+var_3F0], 0
0x18006d53d  mov     [rsp+448h+var_3F4], 0
0x18006d545  mov     [rsp+448h+var_3E8], 0
0x18006d54e  mov     [rsp+448h+Buffer], 0
0x18006d557  mov     [rsp+448h+var_3D8], 0
0x18006d560  mov     [rsp+448h+var_3E0], 0
0x18006d569  mov     [rsp+448h+var_3B0], 0
0x18006d575  cmp     [rsp+448h+arg_8], 0
0x18006d57e  jz      short loc_18006D58F
0x18006d580  mov     rax, [rsp+448h+arg_8]
0x18006d588  mov     qword ptr [rax], 0
0x18006d58f  cmp     [rsp+448h+arg_0], 0
0x18006d598  jnz     short loc_18006D5DA
0x18006d59a  mov     [rsp+448h+var_3F8], 80070057h
0x18006d5a2  lea     r8, aPbuffer; "pBuffer"
0x18006d5a9  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d5b0  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18006d5b7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d5bc  lea     rdx, aPbuffer; "pBuffer"
0x18006d5c3  lea     rcx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d5ca  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18006d5cf  nop
0x18006d5d0  jmp     loc_18006DA63
0x18006d5d5  jmp     loc_18006DA63
0x18006d5da  mov     rax, [rsp+448h+arg_0]
0x18006d5e2  mov     qword ptr [rax], 0
0x18006d5e9  mov     edx, 32h ; '2'; BufferCount
0x18006d5ee  lea     rcx, [rsp+448h+var_308]; Buffer
0x18006d5f6  call    ?GetOSVersionInfo@@YAJPEAG_K@Z; GetOSVersionInfo(ushort *,unsigned __int64)
0x18006d5fb  mov     [rsp+448h+var_3F8], eax
0x18006d5ff  cmp     [rsp+448h+var_3F8], 0
0x18006d604  jge     short loc_18006D630
0x18006d606  mov     r9d, [rsp+448h+var_3F8]
0x18006d60b  lea     r8, aGetosversionin; "GetOSVersionInfo"
0x18006d612  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d619  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d620  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d625  nop
0x18006d626  jmp     loc_18006DA63
0x18006d62b  jmp     loc_18006DA63
0x18006d630  xor     r8d, r8d; int
0x18006d633  mov     edx, 32h ; '2'; unsigned __int64
0x18006d638  lea     rcx, [rsp+448h+var_298]; unsigned __int16 *
0x18006d640  call    ?GetDllVersionInfo@@YAJPEAG_KH@Z; GetDllVersionInfo(ushort *,unsigned __int64,int)
0x18006d645  mov     [rsp+448h+var_3F8], eax
0x18006d649  cmp     [rsp+448h+var_3F8], 0
0x18006d64e  jge     short loc_18006D67A
0x18006d650  mov     r9d, [rsp+448h+var_3F8]
0x18006d655  lea     r8, aGetdllversioni; "GetDllVersionInfo"
0x18006d65c  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d663  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d66a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d66f  nop
0x18006d670  jmp     loc_18006DA63
0x18006d675  jmp     loc_18006DA63
0x18006d67a  mov     r8d, 1; int
0x18006d680  mov     edx, 32h ; '2'; unsigned __int64
0x18006d685  lea     rcx, [rsp+448h+var_378]; unsigned __int16 *
0x18006d68d  call    ?GetDllVersionInfo@@YAJPEAG_KH@Z; GetDllVersionInfo(ushort *,unsigned __int64,int)
0x18006d692  mov     [rsp+448h+var_3F8], eax
0x18006d696  cmp     [rsp+448h+var_3F8], 0
0x18006d69b  jge     short loc_18006D6C7
0x18006d69d  mov     r9d, [rsp+448h+var_3F8]
0x18006d6a2  lea     r8, aGetdllversioni; "GetDllVersionInfo"
0x18006d6a9  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d6b0  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d6b7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d6bc  nop
0x18006d6bd  jmp     loc_18006DA63
0x18006d6c2  jmp     loc_18006DA63
0x18006d6c7  lea     rcx, [rsp+448h+var_3F0]; unsigned __int16 **
0x18006d6cc  call    ?GetTargetServer@@YAJPEAPEAG@Z; GetTargetServer(ushort * *)
0x18006d6d1  mov     [rsp+448h+var_3F8], eax
0x18006d6d5  cmp     [rsp+448h+var_3F8], 0
0x18006d6da  jge     short loc_18006D715
0x18006d6dc  mov     r8d, [rsp+448h+var_3F8]
0x18006d6e1  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d6e8  lea     rcx, aSGettargetserv; "%s: GetTargetServer failed with error c"...
0x18006d6ef  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006d6f4  nop
0x18006d6f5  mov     rcx, [rsp+448h+var_3F0]; lpMem
0x18006d6fa  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18006d6ff  mov     [rsp+448h+var_3F0], 0
0x18006d708  mov     [rsp+448h+var_3F8], 0
0x18006d710  jmp     loc_18006D7B2
0x18006d715  mov     rcx, [rsp+448h+var_3F0]; unsigned __int16 *
0x18006d71a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18006d71f  test    eax, eax
0x18006d721  jnz     loc_18006D7B2
0x18006d727  lea     rax, [rsp+448h+var_3F4]
0x18006d72c  mov     [rsp+448h+var_428], rax; int *
0x18006d731  lea     r9, [rsp+448h+var_3B0]; unsigned __int64 *
0x18006d739  mov     r8d, 105h; unsigned __int64
0x18006d73f  lea     rdx, [rsp+448h+var_228]; unsigned __int16 *
0x18006d747  mov     rcx, [rsp+448h+var_3F0]; unsigned __int16 *
0x18006d74c  call    ?SanitizeHttpHeaderValue@@YAHPEBGPEAG_KPEA_KPEAH@Z; SanitizeHttpHeaderValue(ushort const *,ushort *,unsigned __int64,unsigned __int64 *,int *)
0x18006d751  test    eax, eax
0x18006d753  jnz     short loc_18006D76F
0x18006d755  mov     r8d, 104h
0x18006d75b  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d762  lea     rcx, aSTargetServerV; "%s: Target server value is truncated to"...
0x18006d769  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006d76e  nop
0x18006d76f  cmp     [rsp+448h+var_3F4], 0
0x18006d774  jle     short loc_18006D78F
0x18006d776  mov     r8d, [rsp+448h+var_3F4]
0x18006d77b  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d782  lea     rcx, aSDDisallowedCh; "%s: %d disallowed character(s) were rem"...
0x18006d789  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006d78e  nop
0x18006d78f  lea     r9, [rsp+448h+var_228]
0x18006d797  lea     r8, aXMsTargetDc; "x-ms-target-dc"
0x18006d79e  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d7a5  lea     rcx, aSHeaderValueFo; "%s: Header value for \"%s\" is \"%s\""
0x18006d7ac  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18006d7b1  nop
0x18006d7b2  lea     rax, [rsp+448h+var_298]
0x18006d7ba  mov     [rsp+448h+var_3A8], rax
0x18006d7c2  mov     [rsp+448h+var_3C8], 0FFFFFFFFFFFFFFFFh
0x18006d7ce  inc     [rsp+448h+var_3C8]
0x18006d7d6  mov     rax, [rsp+448h+var_3A8]
0x18006d7de  mov     rcx, [rsp+448h+var_3C8]
0x18006d7e6  cmp     word ptr [rax+rcx*2], 0
0x18006d7eb  jnz     short loc_18006D7CE
0x18006d7ed  mov     rax, [rsp+448h+var_3C8]
0x18006d7f5  lea     rcx, [rsp+448h+var_308]
0x18006d7fd  mov     [rsp+448h+var_3A0], rcx
0x18006d805  mov     [rsp+448h+var_3C0], 0FFFFFFFFFFFFFFFFh
0x18006d811  inc     [rsp+448h+var_3C0]
0x18006d819  mov     rcx, [rsp+448h+var_3A0]
0x18006d821  mov     rdx, [rsp+448h+var_3C0]
0x18006d829  cmp     word ptr [rcx+rdx*2], 0
0x18006d82e  jnz     short loc_18006D811
0x18006d830  mov     rcx, [rsp+448h+var_3C0]
0x18006d838  lea     rax, [rax+rcx+5Dh]
0x18006d83d  lea     rcx, [rsp+448h+var_378]
0x18006d845  mov     [rsp+448h+var_398], rcx
0x18006d84d  mov     [rsp+448h+var_3B8], 0FFFFFFFFFFFFFFFFh
0x18006d859  inc     [rsp+448h+var_3B8]
0x18006d861  mov     rcx, [rsp+448h+var_398]
0x18006d869  mov     rdx, [rsp+448h+var_3B8]
0x18006d871  cmp     word ptr [rcx+rdx*2], 0
0x18006d876  jnz     short loc_18006D859
0x18006d878  mov     rcx, [rsp+448h+var_3B8]
0x18006d880  add     rax, rcx
0x18006d883  mov     [rsp+448h+var_3D8], rax
0x18006d888  cmp     [rsp+448h+var_3B0], 0
0x18006d891  jbe     short loc_18006D8AA
0x18006d893  mov     rax, [rsp+448h+var_3D8]
0x18006d898  mov     rcx, [rsp+448h+var_3B0]
0x18006d8a0  lea     rax, [rax+rcx+14h]
0x18006d8a5  mov     [rsp+448h+var_3D8], rax
0x18006d8aa  mov     eax, 2
0x18006d8af  mul     [rsp+448h+var_3D8]
0x18006d8b4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006d8bb  cmovb   rax, rcx
0x18006d8bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006d8c6  mov     rcx, rax; unsigned __int64
0x18006d8c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006d8ce  mov     [rsp+448h+var_390], rax
0x18006d8d6  mov     rax, [rsp+448h+var_390]
0x18006d8de  mov     [rsp+448h+var_3E8], rax
0x18006d8e3  cmp     [rsp+448h+var_3E8], 0
0x18006d8e9  jnz     short loc_18006D911
0x18006d8eb  mov     [rsp+448h+var_3F8], 8007000Eh
0x18006d8f3  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d8fa  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18006d901  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18006d906  nop
0x18006d907  jmp     loc_18006DA63
0x18006d90c  jmp     loc_18006DA63
0x18006d911  mov     rax, [rsp+448h+var_3D8]
0x18006d916  mov     [rsp+448h+var_3E0], rax
0x18006d91b  mov     rax, [rsp+448h+var_3E8]
0x18006d920  mov     [rsp+448h+Buffer], rax
0x18006d925  lea     rax, [rsp+448h+var_378]
0x18006d92d  mov     [rsp+448h+var_408], rax
0x18006d932  lea     rax, [rsp+448h+var_308]
0x18006d93a  mov     [rsp+448h+var_410], rax
0x18006d93f  lea     rax, [rsp+448h+var_298]
0x18006d947  mov     [rsp+448h+var_418], rax
0x18006d94c  lea     rax, aUserAgentDsreg; "User-Agent: Dsreg/%s (Windows %s)\r\noc"...
0x18006d953  mov     [rsp+448h+var_420], rax; unsigned __int16 *
0x18006d958  mov     [rsp+448h+var_428], 0; unsigned int
0x18006d961  lea     r9, [rsp+448h+var_3E0]; unsigned __int64 *
0x18006d966  lea     r8, [rsp+448h+Buffer]; unsigned __int16 **
0x18006d96b  mov     rdx, [rsp+448h+var_3E0]; unsigned __int64
0x18006d970  mov     rcx, [rsp+448h+Buffer]; Buffer
0x18006d975  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18006d97a  mov     [rsp+448h+var_3F8], eax
0x18006d97e  cmp     [rsp+448h+var_3F8], 0
0x18006d983  jge     short loc_18006D9AF
0x18006d985  mov     r9d, [rsp+448h+var_3F8]
0x18006d98a  lea     r8, aStringcchprint_0; "StringCchPrintfExW"
0x18006d991  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006d998  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d99f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d9a4  nop
0x18006d9a5  jmp     loc_18006DA63
0x18006d9aa  jmp     loc_18006DA63
0x18006d9af  cmp     [rsp+448h+var_3B0], 0
0x18006d9b8  jbe     short loc_18006DA24
0x18006d9ba  lea     rax, [rsp+448h+var_228]
0x18006d9c2  mov     [rsp+448h+var_418], rax
0x18006d9c7  lea     rax, aXMsTargetDcS; "x-ms-target-dc: %s\r\n"
0x18006d9ce  mov     [rsp+448h+var_420], rax; unsigned __int16 *
0x18006d9d3  mov     [rsp+448h+var_428], 0; unsigned int
0x18006d9dc  lea     r9, [rsp+448h+var_3E0]; unsigned __int64 *
0x18006d9e1  lea     r8, [rsp+448h+Buffer]; unsigned __int16 **
0x18006d9e6  mov     rdx, [rsp+448h+var_3E0]; unsigned __int64
0x18006d9eb  mov     rcx, [rsp+448h+Buffer]; Buffer
0x18006d9f0  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18006d9f5  mov     [rsp+448h+var_3F8], eax
0x18006d9f9  cmp     [rsp+448h+var_3F8], 0
0x18006d9fe  jge     short loc_18006DA24
0x18006da00  mov     r9d, [rsp+448h+var_3F8]
0x18006da05  lea     r8, aStringcchprint_0; "StringCchPrintfExW"
0x18006da0c  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006da13  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006da1a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006da1f  nop
0x18006da20  jmp     short loc_18006DA63
0x18006da22  jmp     short loc_18006DA63
0x18006da24  mov     rax, [rsp+448h+arg_0]
0x18006da2c  mov     rcx, [rsp+448h+var_3E8]
0x18006da31  mov     [rax], rcx
0x18006da34  mov     [rsp+448h+var_3E8], 0
0x18006da3d  cmp     [rsp+448h+arg_8], 0
0x18006da46  jz      short loc_18006DA63
0x18006da48  mov     rax, [rsp+448h+var_3E0]
0x18006da4d  mov     rcx, [rsp+448h+var_3D8]
0x18006da52  sub     rcx, rax
0x18006da55  mov     rax, rcx
0x18006da58  mov     rcx, [rsp+448h+arg_8]
0x18006da60  mov     [rcx], rax
0x18006da63  mov     rcx, [rsp+448h+var_3F0]; lpMem
0x18006da68  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18006da6d  mov     [rsp+448h+var_3F0], 0
0x18006da76  mov     rax, [rsp+448h+var_3E8]
0x18006da7b  mov     [rsp+448h+Block], rax
0x18006da83  mov     rcx, [rsp+448h+Block]; Block
0x18006da8b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006da90  nop
0x18006da91  mov     [rsp+448h+var_3E8], 0
0x18006da9a  mov     r8d, [rsp+448h+var_3F8]
0x18006da9f  lea     rdx, aGetcommonhttpr; "GetCommonHttpRequestHeaders"
0x18006daa6  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18006daad  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006dab2  mov     eax, [rsp+448h+var_3F8]
0x18006dab6  mov     rcx, [rsp+448h+var_18]
0x18006dabe  xor     rcx, rsp; StackCookie
0x18006dac1  call    __security_check_cookie
0x18006dac6  add     rsp, 440h
0x18006dacd  pop     rdi
0x18006dace  retn
```
