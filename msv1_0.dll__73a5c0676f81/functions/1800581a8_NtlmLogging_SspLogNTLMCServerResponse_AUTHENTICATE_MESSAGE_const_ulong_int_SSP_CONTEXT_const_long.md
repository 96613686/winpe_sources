# NtlmLogging::SspLogNTLMCServerResponse(_AUTHENTICATE_MESSAGE const *,ulong,int,_SSP_CONTEXT const *,long)

- ea: `0x1800581a8`
- end: `0x1800587bf`
- name: `?SspLogNTLMCServerResponse@NtlmLogging@@YAXPEBU_AUTHENTICATE_MESSAGE@@KHPEBU_SSP_CONTEXT@@J@Z`
- size: `1559`
- prototype: `void __usercall(NtlmLogging *__hidden this@<rcx>, const struct _AUTHENTICATE_MESSAGE *@<rdx>, unsigned int@<r8d>, int@<r9d>, const struct _SSP_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800157b0`

## callees

- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x180021acc`
- `0x18002e3e8`
- `0x18002e7a8`
- `0x18002f03c`
- `0x18002fb50`
- `0x18004c874`
- `0x180057bb8`
- `0x180057c9c`
- `0x180057ccc`
- `0x180057d1c`
- `0x180057d80`
- `0x180057de8`
- `0x180057e48`
- `0x180057ecc`
- `0x180057f84`
- `0x180058068`
- `0x1800581a8`
- `0x18005a2f0`
- `0x18005a318`
- `0x1800692ac`
- `0x1800693f8`
- `0x1800696dc`
- `0x1800698e0`
- `0x180069de4`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180058207`
- `ntdll!EtwEventEnabled` at `0x18005821f`
- `ntdll!EtwEventEnabled` at `0x1800586dd`
- `ntdll!EtwEventEnabled` at `0x180058702`
- `ntdll!EtwEventEnabled` at `0x180058207`
- `ntdll!EtwEventEnabled` at `0x18005821f`
- `ntdll!EtwEventEnabled` at `0x1800586dd`
- `ntdll!EtwEventEnabled` at `0x180058702`
- `ntdll!EtwEventWrite` at `0x18005872b`
- `ntdll!EtwEventWrite` at `0x18005872b`
- `LSASRV!LsaIFreeHeap` at `0x180058751`
- `LSASRV!LsaIFreeHeap` at `0x18005875c`
- `LSASRV!LsaIFreeHeap` at `0x180058751`
- `LSASRV!LsaIFreeHeap` at `0x18005875c`
- `LSASRV!LsaIGetNetworkInfo` at `0x180058430`
- `LSASRV!LsaIGetNetworkInfo` at `0x180058430`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NtlmLogging::SspLogNTLMCServerResponse(
        NtlmLogging *this,
        const struct _AUTHENTICATE_MESSAGE *a2,
        __int64 a3,
        __int64 a4,
        const struct _SSP_CONTEXT *a5)
{
  unsigned int v6; // esi
  __int64 v8; // r8
  __int64 v9; // rbx
  int v10; // ebx
  __int64 v11; // rax
  bool v12; // al
  __int64 SessionKeyStatus; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v17[3]; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v18; // [rsp+48h] [rbp-B8h] BYREF
  _WORD *v19; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v20; // [rsp+60h] [rbp-A0h]
  _WORD v21[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v22[2]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v23[8]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v24[2]; // [rsp+98h] [rbp-68h] BYREF
  _WORD v25[8]; // [rsp+A8h] [rbp-58h] BYREF
  int v26; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v27; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v29[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v30[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v31[32]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v32[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v33[4]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v34[32]; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v35; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v36[120]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v37[32]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v38[8]; // [rsp+250h] [rbp+150h] BYREF
  unsigned int v39[6]; // [rsp+258h] [rbp+158h] BYREF
  _WORD v40[788]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v41[8]; // [rsp+898h] [rbp+798h] BYREF

  v6 = (unsigned int)a2;
  if ( NtlmDoEnhancedAuditing
    && (int)SspInitEtwLogHandle() >= 0
    && ((unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedServerLogsInfo)
     || (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedServerLogsWarning))
    && (*(_DWORD *)(a4 + 48) & 0x4000) == 0 )
  {
    NtlmHelper::AuthenticateMessage::AuthenticateMessage((NtlmHelper::AuthenticateMessage *)v32, this, v6);
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v38, LsaFunctions);
    SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v38, &v16);
    NtlmLogging::EventDataHelper::EventDataHelper((NtlmLogging::EventDataHelper *)v17, 0x12u);
    v19 = v21;
    v20 = v21;
    v21[0] = 0;
    v8 = -1;
    do
      ++v8;
    while ( v40[v8] );
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      &v19,
      v40,
      v8);
    if ( v19 == v20 && v39[0] == 4 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        &v19,
        L"SYSTEM",
        6);
    }
    else
    {
      v9 = v16;
      if ( v16 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v19,
          L" (",
          2);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v19,
          v9);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          &v19,
          L")",
          1);
      }
    }
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, &v19)
      || !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)v17, v39) )
    {
      goto LABEL_64;
    }
    if ( v32[0] == v32[1] && v33[0] == v33[1] )
    {
      if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"ANONYMOUS LOGON", 0x20u)
        || !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"ANONYMOUS LOGON", 0x20u) )
      {
        goto LABEL_64;
      }
      v10 = 1;
    }
    else
    {
      if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v32)
        || !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v33) )
      {
        goto LABEL_64;
      }
      v10 = 0;
    }
    if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v34) )
    {
LABEL_64:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v19);
      utl::vector<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>,utl::allocator<utl::basic_string_view<unsigned short,utl::char_traits<unsigned short>>>>::_Uninit(v17);
      wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v16);
      wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v41);
      NtlmHelper::AuthenticateMessage::~AuthenticateMessage((NtlmHelper::AuthenticateMessage *)v32);
      return;
    }
    v15 = 0;
    v22[0] = v23;
    v22[1] = v23;
    v23[0] = 0;
    v18 = 0;
    if ( (int)LsaIGetNetworkInfo(&v15, &v18) < 0 )
    {
      if ( !NtlmLogging::EventDataHelper::AddNullString((NtlmLogging::EventDataHelper *)v17) )
        goto LABEL_63;
      v12 = NtlmLogging::EventDataHelper::AddNullString((NtlmLogging::EventDataHelper *)v17);
    }
    else
    {
      v11 = NtlmLogging::IpToString(v37, v15);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v22,
        v11);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v37);
      if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v22) )
        goto LABEL_63;
      v12 = NtlmLogging::EventDataHelper::AddUnicodeString((NtlmLogging::EventDataHelper *)v17, &v18);
    }
    if ( v12 )
    {
      v24[0] = v25;
      v24[1] = v25;
      v25[0] = 0;
      NtlmHelper::AvPairHelper::GetTargetInfo(v36, v29);
      NtlmHelper::AvPairHelper::GetFlags(v36, &v27);
      if ( NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)v17, &v35) )
      {
        if ( v36[104] )
        {
          if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"NTLMv2", 0xEu) )
            goto LABEL_62;
        }
        else
        {
          if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"NTLMv1", 0xEu) )
            goto LABEL_62;
          v10 = 1;
        }
        SessionKeyStatus = NtlmHelper::AuthenticateMessage::GetSessionKeyStatus(v32, v37);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
          v24,
          SessionKeyStatus);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v37);
        if ( (unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v24) )
        {
          v26 = 10;
          if ( (_BYTE *)utl::_Tree<enum MSV1_0_AVID,utl::pair<enum MSV1_0_AVID const,utl::vector<unsigned char,utl::allocator<unsigned char>>>,utl::less<enum MSV1_0_AVID>,utl::allocator<utl::pair<enum MSV1_0_AVID const,utl::vector<unsigned char,utl::allocator<unsigned char>>>>,0>::_FindImpl<enum MSV1_0_AVID>(
                          v36,
                          &v26) == v36 )
          {
            if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"Not Supported", 0x1Cu) )
              goto LABEL_62;
            v10 = 1;
          }
          else if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"Supported", 0x14u) )
          {
            goto LABEL_62;
          }
          if ( !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v29)
            || !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v30)
            || !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v31) )
          {
            goto LABEL_62;
          }
          if ( NtlmHelper::AvPairHelper::SupportsMic((NtlmHelper::AvPairHelper *)v36) )
          {
            if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"Protected", 0x14u) )
              goto LABEL_62;
          }
          else
          {
            if ( !NtlmLogging::EventDataHelper::AddBuffer((NtlmLogging::EventDataHelper *)v17, L"Unprotected", 0x18u) )
              goto LABEL_62;
            v10 = 1;
          }
          if ( !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)v17, &v27)
            || !(unsigned __int8)NtlmLogging::EventDataHelper::AddUtlString(v17, v28) )
          {
            goto LABEL_62;
          }
          if ( (v27 & 4) != 0 )
            v10 = 1;
          if ( !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)v17, (const unsigned int *)&a5)
            || !NtlmLogging::EventDataHelper::AddULong((NtlmLogging::EventDataHelper *)v17, (const unsigned int *)&a5) )
          {
            goto LABEL_62;
          }
          if ( v10 )
          {
            if ( (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedServerLogsWarning) )
            {
              v14 = NTLMLessEnhancedServerLogsWarning;
              goto LABEL_61;
            }
          }
          else if ( (unsigned __int8)EtwEventEnabled(MsvEtwLogHandle, NTLMLessEnhancedServerLogsInfo) )
          {
            v14 = NTLMLessEnhancedServerLogsInfo;
LABEL_61:
            EtwEventWrite(MsvEtwLogHandle, v14, (__int64)(v17[1] - v17[0]) >> 4);
          }
        }
      }
LABEL_62:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v28);
      NtlmHelper::AuthenticateHeader::~AuthenticateHeader((NtlmHelper::AuthenticateHeader *)v29);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v24);
    }
LABEL_63:
    LsaIFreeHeap(v15);
    LsaIFreeHeap(v18.Buffer);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
    goto LABEL_64;
  }
}

```

## disassembly

```asm
0x1800581a8  push    rbp
0x1800581aa  push    rbx
0x1800581ab  push    rsi
0x1800581ac  push    rdi
0x1800581ad  push    r14
0x1800581af  push    r15
0x1800581b1  lea     rbp, [rsp-7B8h]
0x1800581b9  sub     rsp, 8B8h
0x1800581c0  mov     rax, cs:__security_cookie
0x1800581c7  xor     rax, rsp
0x1800581ca  mov     [rbp+7E0h+var_40], rax
0x1800581d1  mov     rbx, r9
0x1800581d4  mov     edi, r8d
0x1800581d7  mov     esi, edx
0x1800581d9  mov     r14, rcx
0x1800581dc  xor     r15d, r15d
0x1800581df  cmp     cs:NtlmDoEnhancedAuditing, r15b
0x1800581e6  jz      loc_1800587A0
0x1800581ec  call    SspInitEtwLogHandle
0x1800581f1  test    eax, eax
0x1800581f3  js      loc_1800587A0
0x1800581f9  lea     rdx, NTLMLessEnhancedServerLogsInfo
0x180058200  mov     rcx, cs:MsvEtwLogHandle
0x180058207  call    cs:__imp_EtwEventEnabled
0x18005820d  test    al, al
0x18005820f  jnz     short loc_18005822D
0x180058211  lea     rdx, NTLMLessEnhancedServerLogsWarning
0x180058218  mov     rcx, cs:MsvEtwLogHandle
0x18005821f  call    cs:__imp_EtwEventEnabled
0x180058225  test    al, al
0x180058227  jz      loc_1800587A0
0x18005822d  test    dword ptr [rbx+30h], 4000h
0x180058234  jnz     loc_1800587A0
0x18005823a  test    edi, edi
0x18005823c  setnz   r9b; bool
0x180058240  mov     r8d, esi; unsigned int
0x180058243  mov     rdx, r14; struct _AUTHENTICATE_MESSAGE *
0x180058246  lea     rcx, [rbp+7E0h+var_790]; this
0x18005824a  call    ??0AuthenticateMessage@NtlmHelper@@QEAA@PEBU_AUTHENTICATE_MESSAGE@@K_N@Z; NtlmHelper::AuthenticateMessage::AuthenticateMessage(_AUTHENTICATE_MESSAGE const *,ulong,bool)
0x18005824f  nop
0x180058250  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x180058257  lea     rcx, [rbp+7E0h+var_690]; this
0x18005825e  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180058263  lea     rdx, [rsp+8E0h+var_8B8]
0x180058268  lea     rcx, [rbp+7E0h+var_690]
0x18005826f  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x180058274  mov     edx, 12h; unsigned int
0x180058279  lea     rcx, [rsp+8E0h+var_8B0]; this
0x18005827e  call    ??0EventDataHelper@NtlmLogging@@QEAA@I@Z; NtlmLogging::EventDataHelper::EventDataHelper(uint)
0x180058283  lea     rax, [rsp+8E0h+var_878]
0x180058288  mov     [rsp+8E0h+var_888], rax
0x18005828d  lea     rax, [rsp+8E0h+var_878]
0x180058292  mov     [rsp+8E0h+var_880], rax
0x180058297  mov     [rsp+8E0h+var_878], r15w
0x18005829d  lea     rax, [rbp+7E0h+var_670]
0x1800582a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800582a8  inc     r8
0x1800582ab  cmp     [rax+r8*2], r15w
0x1800582b0  jnz     short loc_1800582A8
0x1800582b2  lea     rdx, [rbp+7E0h+var_670]
0x1800582b9  lea     rcx, [rsp+8E0h+var_888]
0x1800582be  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800582c3  mov     edi, 1
0x1800582c8  mov     rax, [rsp+8E0h+var_880]
0x1800582cd  cmp     [rsp+8E0h+var_888], rax
0x1800582d2  jnz     short loc_1800582F4
0x1800582d4  cmp     [rbp+7E0h+var_688], 4
0x1800582db  jnz     short loc_1800582F4
0x1800582dd  lea     r8d, [rdi+5]
0x1800582e1  lea     rdx, aSystem; "SYSTEM"
0x1800582e8  lea     rcx, [rsp+8E0h+var_888]
0x1800582ed  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800582f2  jmp     short loc_180058336
0x1800582f4  mov     rbx, [rsp+8E0h+var_8B8]
0x1800582f9  test    rbx, rbx
0x1800582fc  jz      short loc_180058336
0x1800582fe  mov     r8d, 2
0x180058304  lea     rdx, asc_18007659C; " ("
0x18005830b  lea     rcx, [rsp+8E0h+var_888]
0x180058310  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180058315  mov     rdx, rbx
0x180058318  lea     rcx, [rsp+8E0h+var_888]
0x18005831d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180058322  mov     r8, rdi
0x180058325  lea     rdx, asc_180076728; ")"
0x18005832c  lea     rcx, [rsp+8E0h+var_888]
0x180058331  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180058336  lea     rdx, [rsp+8E0h+var_888]
0x18005833b  lea     rcx, [rsp+8E0h+var_8B0]
0x180058340  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058345  test    al, al
0x180058347  jz      loc_18005876C
0x18005834d  lea     rdx, [rbp+7E0h+var_688]; unsigned int *
0x180058354  lea     rcx, [rsp+8E0h+var_8B0]; this
0x180058359  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x18005835e  test    al, al
0x180058360  jz      loc_18005876C
0x180058366  mov     rax, [rbp+7E0h+var_788]
0x18005836a  cmp     [rbp+7E0h+var_790], rax
0x18005836e  jnz     short loc_1800583BB
0x180058370  mov     rax, [rbp+7E0h+var_768]
0x180058374  cmp     [rbp+7E0h+var_770], rax
0x180058378  jnz     short loc_1800583BB
0x18005837a  mov     ebx, 20h ; ' '
0x18005837f  mov     r8d, ebx; unsigned __int64
0x180058382  lea     rdx, aAnonymousLogon; "ANONYMOUS LOGON"
0x180058389  lea     rcx, [rsp+8E0h+var_8B0]; this
0x18005838e  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x180058393  test    al, al
0x180058395  jz      loc_18005876C
0x18005839b  mov     r8d, ebx; unsigned __int64
0x18005839e  lea     rdx, aAnonymousLogon; "ANONYMOUS LOGON"
0x1800583a5  lea     rcx, [rsp+8E0h+var_8B0]; this
0x1800583aa  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x1800583af  test    al, al
0x1800583b1  jz      loc_18005876C
0x1800583b7  mov     ebx, edi
0x1800583b9  jmp     short loc_1800583EA
0x1800583bb  lea     rdx, [rbp+7E0h+var_790]
0x1800583bf  lea     rcx, [rsp+8E0h+var_8B0]
0x1800583c4  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800583c9  test    al, al
0x1800583cb  jz      loc_18005876C
0x1800583d1  lea     rdx, [rbp+7E0h+var_770]
0x1800583d5  lea     rcx, [rsp+8E0h+var_8B0]
0x1800583da  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800583df  test    al, al
0x1800583e1  jz      loc_18005876C
0x1800583e7  mov     ebx, r15d
0x1800583ea  lea     rdx, [rbp+7E0h+var_750]
0x1800583f1  lea     rcx, [rsp+8E0h+var_8B0]
0x1800583f6  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800583fb  test    al, al
0x1800583fd  jz      loc_18005876C
0x180058403  mov     [rsp+8E0h+var_8C0], r15
0x180058408  lea     rax, [rbp+7E0h+var_858]
0x18005840c  mov     [rsp+8E0h+var_868], rax
0x180058411  lea     rax, [rbp+7E0h+var_858]
0x180058415  mov     [rbp+7E0h+var_860], rax
0x180058419  mov     [rbp+7E0h+var_858], r15w
0x18005841e  xorps   xmm0, xmm0
0x180058421  movups  xmmword ptr [rsp+8E0h+var_898.Length], xmm0
0x180058426  lea     rdx, [rsp+8E0h+var_898]
0x18005842b  lea     rcx, [rsp+8E0h+var_8C0]
0x180058430  call    cs:__imp_LsaIGetNetworkInfo
0x180058436  test    eax, eax
0x180058438  js      loc_18005850D
0x18005843e  mov     rdx, [rsp+8E0h+var_8C0]
0x180058443  lea     rcx, [rbp+7E0h+var_6B0]
0x18005844a  call    ?IpToString@NtlmLogging@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAE@Z; NtlmLogging::IpToString(uchar * const)
0x18005844f  mov     rdx, rax
0x180058452  lea     rcx, [rsp+8E0h+var_868]
0x180058457  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18005845c  lea     rcx, [rbp+7E0h+var_6B0]
0x180058463  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180058468  lea     rdx, [rsp+8E0h+var_868]
0x18005846d  lea     rcx, [rsp+8E0h+var_8B0]
0x180058472  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058477  test    al, al
0x180058479  jz      loc_18005874C
0x18005847f  lea     rdx, [rsp+8E0h+var_898]; struct _UNICODE_STRING *
0x180058484  lea     rcx, [rsp+8E0h+var_8B0]; this
0x180058489  call    ?AddUnicodeString@EventDataHelper@NtlmLogging@@QEAA_NPEBU_UNICODE_STRING@@@Z; NtlmLogging::EventDataHelper::AddUnicodeString(_UNICODE_STRING const *)
0x18005848e  test    al, al
0x180058490  jz      loc_18005874C
0x180058496  lea     rax, [rbp+7E0h+var_838]
0x18005849a  mov     [rbp+7E0h+var_848], rax
0x18005849e  lea     rax, [rbp+7E0h+var_838]
0x1800584a2  mov     [rbp+7E0h+var_840], rax
0x1800584a6  mov     [rbp+7E0h+var_838], r15w
0x1800584ab  lea     rdx, [rbp+7E0h+var_7F0]
0x1800584af  lea     rcx, [rbp+7E0h+var_728]
0x1800584b6  call    ?GetTargetInfo@AvPairHelper@NtlmHelper@@QEBA?AUNtlmTargetInfo@2@XZ; NtlmHelper::AvPairHelper::GetTargetInfo(void)
0x1800584bb  lea     rdx, [rbp+7E0h+var_820]
0x1800584bf  lea     rcx, [rbp+7E0h+var_728]
0x1800584c6  call    ?GetFlags@AvPairHelper@NtlmHelper@@QEBA?AUAvFlags@2@XZ; NtlmHelper::AvPairHelper::GetFlags(void)
0x1800584cb  lea     rdx, [rbp+7E0h+var_730]; unsigned int *
0x1800584d2  lea     rcx, [rsp+8E0h+var_8B0]; this
0x1800584d7  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x1800584dc  test    al, al
0x1800584de  jz      loc_180058731
0x1800584e4  mov     r8d, 0Eh; unsigned __int64
0x1800584ea  lea     rcx, [rsp+8E0h+var_8B0]; this
0x1800584ef  cmp     [rbp+7E0h+var_6C0], r15b
0x1800584f6  jz      short loc_18005852E
0x1800584f8  lea     rdx, aNtlmv2; "NTLMv2"
0x1800584ff  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x180058504  test    al, al
0x180058506  jnz     short loc_180058544
0x180058508  jmp     loc_180058731
0x18005850d  lea     rcx, [rsp+8E0h+var_8B0]; this
0x180058512  call    ?AddNullString@EventDataHelper@NtlmLogging@@QEAA_NXZ; NtlmLogging::EventDataHelper::AddNullString(void)
0x180058517  test    al, al
0x180058519  jz      loc_18005874C
0x18005851f  lea     rcx, [rsp+8E0h+var_8B0]; this
0x180058524  call    ?AddNullString@EventDataHelper@NtlmLogging@@QEAA_NXZ; NtlmLogging::EventDataHelper::AddNullString(void)
0x180058529  jmp     loc_18005848E
0x18005852e  lea     rdx, aNtlmv1; "NTLMv1"
0x180058535  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x18005853a  test    al, al
0x18005853c  jz      loc_180058731
0x180058542  mov     ebx, edi
0x180058544  lea     rdx, [rbp+7E0h+var_6B0]
0x18005854b  lea     rcx, [rbp+7E0h+var_790]
0x18005854f  call    ?GetSessionKeyStatus@AuthenticateMessage@NtlmHelper@@QEBA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; NtlmHelper::AuthenticateMessage::GetSessionKeyStatus(void)
0x180058554  mov     rdx, rax
0x180058557  lea     rcx, [rbp+7E0h+var_848]
0x18005855b  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180058560  lea     rcx, [rbp+7E0h+var_6B0]
0x180058567  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18005856c  lea     rdx, [rbp+7E0h+var_848]
0x180058570  lea     rcx, [rsp+8E0h+var_8B0]
0x180058575  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18005857a  test    al, al
0x18005857c  jz      loc_180058731
0x180058582  mov     [rbp+7E0h+var_828], 0Ah
0x180058589  lea     rdx, [rbp+7E0h+var_828]
0x18005858d  lea     rcx, [rbp+7E0h+var_728]
0x180058594  call    ??$_FindImpl@W4MSV1_0_AVID@@@?$_Tree@W4MSV1_0_AVID@@U?$pair@$$CBW4MSV1_0_AVID@@V?$vector@EV?$allocator@E@utl@@@utl@@@utl@@U?$less@W4MSV1_0_AVID@@@3@V?$allocator@U?$pair@$$CBW4MSV1_0_AVID@@V?$vector@EV?$allocator@E@utl@@@utl@@@utl@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBW4MSV1_0_AVID@@V?$vector@EV?$allocator@E@utl@@@utl@@@utl@@@1@AEBW4MSV1_0_AVID@@@Z; utl::_Tree<MSV1_0_AVID,utl::pair<MSV1_0_AVID const,utl::vector<uchar,utl::allocator<uchar>>>,utl::less<MSV1_0_AVID>,utl::allocator<utl::pair<MSV1_0_AVID const,utl::vector<uchar,utl::allocator<uchar>>>>,0>::_FindImpl<MSV1_0_AVID>(MSV1_0_AVID const &)
0x180058599  lea     rcx, [rbp+7E0h+var_728]
0x1800585a0  mov     esi, 14h
0x1800585a5  cmp     rax, rcx
0x1800585a8  lea     rcx, [rsp+8E0h+var_8B0]; this
0x1800585ad  jz      short loc_1800585C7
0x1800585af  mov     r8d, esi; unsigned __int64
0x1800585b2  lea     rdx, aSupported; "Supported"
0x1800585b9  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x1800585be  test    al, al
0x1800585c0  jnz     short loc_1800585E3
0x1800585c2  jmp     loc_180058731
0x1800585c7  mov     r8d, 1Ch; unsigned __int64
0x1800585cd  lea     rdx, aNotSupported; "Not Supported"
0x1800585d4  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x1800585d9  test    al, al
0x1800585db  jz      loc_180058731
0x1800585e1  mov     ebx, edi
0x1800585e3  lea     rdx, [rbp+7E0h+var_7F0]
0x1800585e7  lea     rcx, [rsp+8E0h+var_8B0]
0x1800585ec  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800585f1  test    al, al
0x1800585f3  jz      loc_180058731
0x1800585f9  lea     rdx, [rbp+7E0h+var_7D0]
0x1800585fd  lea     rcx, [rsp+8E0h+var_8B0]
0x180058602  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058607  test    al, al
0x180058609  jz      loc_180058731
0x18005860f  lea     rdx, [rbp+7E0h+var_7B0]
0x180058613  lea     rcx, [rsp+8E0h+var_8B0]
0x180058618  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18005861d  test    al, al
0x18005861f  jz      loc_180058731
0x180058625  lea     rcx, [rbp+7E0h+var_728]; this
0x18005862c  call    ?SupportsMic@AvPairHelper@NtlmHelper@@QEBA_NXZ; NtlmHelper::AvPairHelper::SupportsMic(void)
0x180058631  lea     rcx, [rsp+8E0h+var_8B0]; this
0x180058636  test    al, al
0x180058638  jz      short loc_180058652
0x18005863a  mov     r8, rsi; unsigned __int64
0x18005863d  lea     rdx, aProtected; "Protected"
0x180058644  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x180058649  test    al, al
0x18005864b  jnz     short loc_18005866E
0x18005864d  jmp     loc_180058731
0x180058652  mov     r8d, 18h; unsigned __int64
0x180058658  lea     rdx, aUnprotected; "Unprotected"
0x18005865f  call    ?AddBuffer@EventDataHelper@NtlmLogging@@QEAA_NPEBX_K@Z; NtlmLogging::EventDataHelper::AddBuffer(void const *,unsigned __int64)
0x180058664  test    al, al
0x180058666  jz      loc_180058731
0x18005866c  mov     ebx, edi
0x18005866e  lea     rdx, [rbp+7E0h+var_820]; unsigned int *
0x180058672  lea     rcx, [rsp+8E0h+var_8B0]; this
0x180058677  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x18005867c  test    al, al
0x18005867e  jz      loc_180058731
0x180058684  lea     rdx, [rbp+7E0h+var_818]
0x180058688  lea     rcx, [rsp+8E0h+var_8B0]
0x18005868d  call    ?AddUtlString@EventDataHelper@NtlmLogging@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; NtlmLogging::EventDataHelper::AddUtlString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180058692  test    al, al
0x180058694  jz      loc_180058731
0x18005869a  test    byte ptr [rbp+7E0h+var_820], 4
0x18005869e  cmovnz  ebx, edi
0x1800586a1  lea     rdx, [rbp+7E0h+arg_20]; unsigned int *
0x1800586a8  lea     rcx, [rsp+8E0h+var_8B0]; this
0x1800586ad  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x1800586b2  test    al, al
0x1800586b4  jz      short loc_180058731
0x1800586b6  lea     rdx, [rbp+7E0h+arg_20]; unsigned int *
0x1800586bd  lea     rcx, [rsp+8E0h+var_8B0]; this
0x1800586c2  call    ?AddULong@EventDataHelper@NtlmLogging@@QEAA_NPEBK@Z; NtlmLogging::EventDataHelper::AddULong(ulong const *)
0x1800586c7  test    al, al
0x1800586c9  jz      short loc_180058731
0x1800586cb  test    ebx, ebx
0x1800586cd  jnz     short loc_1800586F0
0x1800586cf  lea     rdx, NTLMLessEnhancedServerLogsInfo
0x1800586d6  mov     rcx, cs:MsvEtwLogHandle
0x1800586dd  call    cs:__imp_EtwEventEnabled
0x1800586e3  test    al, al
0x1800586e5  jz      short loc_180058731
0x1800586e7  lea     rdx, NTLMLessEnhancedServerLogsInfo
0x1800586ee  jmp     short loc_180058713
0x1800586f0  cmp     ebx, edi
  ... truncated ...
```
