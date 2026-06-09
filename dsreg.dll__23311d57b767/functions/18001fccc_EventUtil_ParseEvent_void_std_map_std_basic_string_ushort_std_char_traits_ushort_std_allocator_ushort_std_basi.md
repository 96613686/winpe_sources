# EventUtil::ParseEvent(void *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18001fccc`
- end: `0x1800203e1`
- name: `?ParseEvent@EventUtil@@SAJPEAXAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1813`
- prototype: `__int64 __fastcall(EVT_HANDLE Fragment)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800320e8`

## callees

- `0x180009780`
- `0x180012cf0`
- `0x18001378c`
- `0x1800155a4`
- `0x180016190`
- `0x180016ae0`
- `0x180016b90`
- `0x18001fccc`
- `0x1800292ac`
- `0x180029554`
- `0x18002b9b4`
- `0x1800319ac`
- `0x180044300`
- `0x1800a1d54`
- `0x1800b2854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe8e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001ff72`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800201cc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001ff72`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800201cc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18001ff7e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800201d8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180020251`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18001ff7e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800201d8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180020251`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18001fe3b`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18001fe88`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18001fe3b`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18001fe88`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18001fdf8`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18001fdf8`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18002038b`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18002038b`

## string_xrefs

- `0x18001fd08`: `Event/System/TimeCreated/@SystemTime`
- `0x18001fd4e`: `Event/EventData/Data[@Name='EndpointUri']`
- `0x18001ff00`: `Previous Prt Attempt`
- `0x18001ff98`: `Attempt Status`
- `0x18002010e`: `Endpoint URI`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall EventUtil::ParseEvent(EVT_HANDLE Fragment, __int64 a2)
{
  unsigned int v4; // r14d
  EVT_HANDLE RenderContext; // r12
  signed int LastError; // edi
  __int64 *Buffer; // rsi
  DWORD v8; // ebx
  unsigned __int64 i; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  _WORD *v15; // r13
  char **v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 AADCredentialTypeName; // rax
  __int64 v20; // rax
  _WORD *v21; // r13
  char **v22; // rax
  __int64 v23; // r8
  _WORD *v24; // r13
  char **v25; // rax
  __int64 v26; // r8
  _WORD *v27; // r13
  char **v28; // rax
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  _WORD *v34; // r13
  char **v35; // rax
  __int64 v36; // r8
  _WORD *v37; // r13
  char **v38; // rax
  DWORD PropertyCount; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BufferSize; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h]
  _BYTE v43[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v44[232]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v45[8]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v46[232]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v47[8]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v48[232]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v49[8]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v50[232]; // [rsp+328h] [rbp+228h] BYREF
  _OWORD v51[2]; // [rsp+410h] [rbp+310h] BYREF
  int v52; // [rsp+430h] [rbp+330h]
  int v53; // [rsp+434h] [rbp+334h]
  int v54; // [rsp+438h] [rbp+338h]
  _BYTE v55[32]; // [rsp+440h] [rbp+340h] BYREF
  LPCWSTR ValuePaths[12]; // [rsp+460h] [rbp+360h] BYREF

  v4 = 0;
  ValuePaths[0] = L"Event/System/TimeCreated/@SystemTime";
  ValuePaths[1] = L"Event/EventData/Data[@Name='Result']";
  ValuePaths[2] = L"Event/EventData/Data[@Name='UserIdentity']";
  ValuePaths[3] = L"Event/EventData/Data[@Name='CredentialType']";
  ValuePaths[4] = L"Event/EventData/Data[@Name='CorrelationID']";
  ValuePaths[5] = L"Event/EventData/Data[@Name='EndpointUri']";
  ValuePaths[6] = L"Event/EventData/Data[@Name='Method']";
  ValuePaths[7] = L"Event/EventData/Data[@Name='HTTPTransportError']";
  ValuePaths[8] = L"Event/EventData/Data[@Name='HTTPStatus']";
  ValuePaths[9] = L"Event/EventData/Data[@Name='ErrorCode']";
  ValuePaths[10] = L"Event/EventData/Data[@Name='ErrorDescription']";
  v51[0] = _mm_load_si128((const __m128i *)&_xmm);
  v51[1] = _mm_load_si128((const __m128i *)&_xmm);
  v52 = 7;
  v53 = 1;
  v54 = 1;
  BufferSize = 0;
  PropertyCount = 0;
  RenderContext = EvtCreateRenderContext(0xBu, ValuePaths, 0);
  if ( !RenderContext )
  {
    LastError = GetLastError();
    goto LABEL_30;
  }
  Buffer = 0;
  if ( EvtRender(RenderContext, Fragment, 0, 0, 0, &BufferSize, &PropertyCount) )
    goto LABEL_8;
  if ( GetLastError() == 122 )
  {
    v8 = BufferSize;
    Buffer = (__int64 *)SafeAlloc(BufferSize);
    if ( !Buffer )
    {
      LastError = 14;
      goto LABEL_28;
    }
    EvtRender(RenderContext, Fragment, 0, v8, Buffer, &BufferSize, &PropertyCount);
  }
  LastError = GetLastError();
  if ( !LastError )
  {
LABEL_8:
    if ( PropertyCount == 11 )
    {
      for ( i = 0; i < 0xB; ++i )
      {
        if ( *((_DWORD *)v51 + i) != HIDWORD(Buffer[2 * i + 1]) )
          goto LABEL_9;
      }
      LastError = 0;
      v42 = *Buffer;
      v10 = TimeUtils::FileTimeToString(v51, v42);
      std::wstring::wstring((__int64)v55, (__int64)L"Previous Prt Attempt");
      v11 = std::map<std::wstring,std::wstring>::operator[](a2, v55);
      std::wstring::operator=(v11, v10);
      std::wstring::_Tidy_deallocate((__int64)v55);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v49);
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v49, (__int64)L"0x");
      v13 = std::basic_ostream<unsigned short>::operator<<(v12, std::hex);
      std::basic_ostream<unsigned short>::operator<<(v13, *((unsigned int *)Buffer + 4));
      std::basic_stringbuf<unsigned short>::str(v50, v51);
      std::wstring::wstring((__int64)v55, (__int64)L"Attempt Status");
      v14 = std::map<std::wstring,std::wstring>::operator[](a2, v55);
      std::wstring::operator=(v14, (__int64)v51);
      std::wstring::_Tidy_deallocate((__int64)v55);
      std::wstring::_Tidy_deallocate((__int64)v51);
      v15 = (_WORD *)Buffer[4];
      std::wstring::wstring((__int64)v51, (__int64)L"User Identity");
      v16 = (char **)std::map<std::wstring,std::wstring>::operator[](a2, v51);
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( v15[v18] );
      std::wstring::_Assign<unsigned short>(v16, v15, (char *)v18);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v47);
      AADCredentialTypeName = GetAADCredentialTypeName(*((unsigned int *)Buffer + 12));
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v47, AADCredentialTypeName);
      std::basic_stringbuf<unsigned short>::str(v48, v55);
      std::wstring::wstring((__int64)v51, (__int64)L"Credential Type");
      v20 = std::map<std::wstring,std::wstring>::operator[](a2, v51);
      std::wstring::operator=(v20, (__int64)v55);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::wstring::_Tidy_deallocate((__int64)v55);
      v21 = (_WORD *)Buffer[8];
      std::wstring::wstring((__int64)v51, (__int64)L"Correlation ID");
      v22 = (char **)std::map<std::wstring,std::wstring>::operator[](a2, v51);
      v23 = -1;
      do
        ++v23;
      while ( v21[v23] );
      std::wstring::_Assign<unsigned short>(v22, v21, (char *)v23);
      std::wstring::_Tidy_deallocate((__int64)v51);
      v24 = (_WORD *)Buffer[10];
      std::wstring::wstring((__int64)v51, (__int64)L"Endpoint URI");
      v25 = (char **)std::map<std::wstring,std::wstring>::operator[](a2, v51);
      v26 = -1;
      do
        ++v26;
      while ( v24[v26] );
      std::wstring::_Assign<unsigned short>(v25, v24, (char *)v26);
      std::wstring::_Tidy_deallocate((__int64)v51);
      v27 = (_WORD *)Buffer[12];
      std::wstring::wstring((__int64)v51, (__int64)L"HTTP Method");
      v28 = (char **)std::map<std::wstring,std::wstring>::operator[](a2, v51);
      v29 = -1;
      do
        ++v29;
      while ( v27[v29] );
      std::wstring::_Assign<unsigned short>(v28, v27, (char *)v29);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v45);
      v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v45, (__int64)L"0x");
      v31 = std::basic_ostream<unsigned short>::operator<<(v30, std::hex);
      std::basic_ostream<unsigned short>::operator<<(v31, *((unsigned int *)Buffer + 28));
      std::basic_stringbuf<unsigned short>::str(v46, v55);
      std::wstring::wstring((__int64)v51, (__int64)L"HTTP Error");
      v32 = std::map<std::wstring,std::wstring>::operator[](a2, v51);
      std::wstring::operator=(v32, (__int64)v55);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::wstring::_Tidy_deallocate((__int64)v55);
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v43);
      std::basic_ostream<unsigned short>::operator<<(v43, *((unsigned int *)Buffer + 32));
      std::basic_stringbuf<unsigned short>::str(v44, v55);
      std::wstring::wstring((__int64)v51, (__int64)L"HTTP status");
      v33 = std::map<std::wstring,std::wstring>::operator[](a2, v51);
      std::wstring::operator=(v33, (__int64)v55);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::wstring::_Tidy_deallocate((__int64)v55);
      v34 = (_WORD *)Buffer[18];
      std::wstring::wstring((__int64)v51, (__int64)L"Server Error Code");
      v35 = (char **)std::map<std::wstring,std::wstring>::operator[](a2, v51);
      v36 = -1;
      do
        ++v36;
      while ( v34[v36] );
      std::wstring::_Assign<unsigned short>(v35, v34, (char *)v36);
      std::wstring::_Tidy_deallocate((__int64)v51);
      v37 = (_WORD *)Buffer[20];
      std::wstring::wstring((__int64)v51, (__int64)L"Server Error Description");
      v38 = (char **)std::map<std::wstring,std::wstring>::operator[](a2, v51);
      do
        ++v17;
      while ( v37[v17] );
      std::wstring::_Assign<unsigned short>(v38, v37, (char *)v17);
      std::wstring::_Tidy_deallocate((__int64)v51);
      std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v43);
      std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v45);
      std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v47);
      std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v49);
    }
    else
    {
LABEL_9:
      LastError = 13;
    }
  }
LABEL_28:
  EvtClose(RenderContext);
  if ( Buffer )
    SafeFree(Buffer);
LABEL_30:
  if ( LastError )
  {
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    else
      return (unsigned int)LastError;
  }
  return v4;
}

```

## disassembly

```asm
0x18001fccc  mov     [rsp-8+arg_10], rbx
0x18001fcd1  push    rbp
0x18001fcd2  push    rsi
0x18001fcd3  push    rdi
0x18001fcd4  push    r12
0x18001fcd6  push    r13
0x18001fcd8  push    r14
0x18001fcda  push    r15
0x18001fcdc  lea     rbp, [rsp-3D0h]
0x18001fce4  sub     rsp, 4D0h
0x18001fceb  mov     rax, cs:__security_cookie
0x18001fcf2  xor     rax, rsp
0x18001fcf5  mov     [rbp+400h+var_40], rax
0x18001fcfc  mov     r15, rdx
0x18001fcff  mov     rdi, rcx
0x18001fd02  xor     r13d, r13d
0x18001fd05  mov     r14d, r13d
0x18001fd08  lea     rax, aEventSystemTim; "Event/System/TimeCreated/@SystemTime"
0x18001fd0f  mov     [rbp+400h+ValuePaths], rax
0x18001fd16  lea     rax, aEventEventdata_3; "Event/EventData/Data[@Name='Result']"
0x18001fd1d  mov     [rbp+400h+var_98], rax
0x18001fd24  lea     rax, aEventEventdata_4; "Event/EventData/Data[@Name='UserIdentit"...
0x18001fd2b  mov     [rbp+400h+var_90], rax
0x18001fd32  lea     rax, aEventEventdata_5; "Event/EventData/Data[@Name='CredentialT"...
0x18001fd39  mov     [rbp+400h+var_88], rax
0x18001fd40  lea     rax, aEventEventdata; "Event/EventData/Data[@Name='Correlation"...
0x18001fd47  mov     [rbp+400h+var_80], rax
0x18001fd4e  lea     rax, aEventEventdata_0; "Event/EventData/Data[@Name='EndpointUri"...
0x18001fd55  mov     [rbp+400h+var_78], rax
0x18001fd5c  lea     rax, aEventEventdata_6; "Event/EventData/Data[@Name='Method']"
0x18001fd63  mov     [rbp+400h+var_70], rax
0x18001fd6a  lea     rax, aEventEventdata_7; "Event/EventData/Data[@Name='HTTPTranspo"...
0x18001fd71  mov     [rbp+400h+var_68], rax
0x18001fd78  lea     rax, aEventEventdata_1; "Event/EventData/Data[@Name='HTTPStatus'"...
0x18001fd7f  mov     [rbp+400h+var_60], rax
0x18001fd86  lea     rax, aEventEventdata_8; "Event/EventData/Data[@Name='ErrorCode']"
0x18001fd8d  mov     [rbp+400h+var_58], rax
0x18001fd94  lea     rax, aEventEventdata_2; "Event/EventData/Data[@Name='ErrorDescri"...
0x18001fd9b  mov     [rbp+400h+var_50], rax
0x18001fda2  movdqa  xmm0, cs:__xmm@00000007000000010000000800000011
0x18001fdaa  movdqu  [rbp+400h+var_F0], xmm0
0x18001fdb2  movdqa  xmm1, cs:__xmm@00000007000000010000000100000001
0x18001fdba  movdqu  [rbp+400h+var_E0], xmm1
0x18001fdc2  mov     [rbp+400h+var_D0], 7
0x18001fdcc  mov     [rbp+400h+var_CC], 1
0x18001fdd6  mov     [rbp+400h+var_C8], 1
0x18001fde0  mov     [rsp+500h+BufferSize], r13d
0x18001fde5  mov     [rsp+500h+var_4C0], r13d
0x18001fdea  xor     r8d, r8d; Flags
0x18001fded  lea     rdx, [rbp+400h+ValuePaths]; ValuePaths
0x18001fdf4  lea     ecx, [r13+0Bh]; ValuePathsCount
0x18001fdf8  call    cs:__imp_EvtCreateRenderContext
0x18001fdfe  mov     r12, rax
0x18001fe01  test    rax, rax
0x18001fe04  jnz     short loc_18001FE13
0x18001fe06  call    cs:__imp_GetLastError
0x18001fe0c  mov     edi, eax
0x18001fe0e  jmp     loc_18002039E
0x18001fe13  mov     rsi, r13
0x18001fe16  lea     rax, [rsp+500h+var_4C0]
0x18001fe1b  mov     [rsp+500h+PropertyCount], rax; PropertyCount
0x18001fe20  lea     rax, [rsp+500h+BufferSize]
0x18001fe25  mov     [rsp+500h+BufferUsed], rax; BufferUsed
0x18001fe2a  mov     [rsp+500h+Buffer], r13; Buffer
0x18001fe2f  xor     r9d, r9d; BufferSize
0x18001fe32  xor     r8d, r8d; Flags
0x18001fe35  mov     rdx, rdi; Fragment
0x18001fe38  mov     rcx, r12; Context
0x18001fe3b  call    cs:__imp_EvtRender
0x18001fe41  test    eax, eax
0x18001fe43  jnz     short loc_18001FE9E
0x18001fe45  call    cs:__imp_GetLastError
0x18001fe4b  cmp     eax, 7Ah ; 'z'
0x18001fe4e  jnz     short loc_18001FE8E
0x18001fe50  mov     ebx, [rsp+500h+BufferSize]
0x18001fe54  mov     ecx, ebx; unsigned __int64
0x18001fe56  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18001fe5b  mov     rsi, rax
0x18001fe5e  test    rax, rax
0x18001fe61  jz      short loc_18001FEAF
0x18001fe63  lea     rax, [rsp+500h+var_4C0]
0x18001fe68  mov     [rsp+500h+PropertyCount], rax; PropertyCount
0x18001fe6d  lea     rax, [rsp+500h+BufferSize]
0x18001fe72  mov     [rsp+500h+BufferUsed], rax; BufferUsed
0x18001fe77  mov     [rsp+500h+Buffer], rsi; Buffer
0x18001fe7c  mov     r9d, ebx; BufferSize
0x18001fe7f  xor     r8d, r8d; Flags
0x18001fe82  mov     rdx, rdi; Fragment
0x18001fe85  mov     rcx, r12; Context
0x18001fe88  call    cs:__imp_EvtRender
0x18001fe8e  call    cs:__imp_GetLastError
0x18001fe94  mov     edi, eax
0x18001fe96  test    eax, eax
0x18001fe98  jnz     loc_180020388
0x18001fe9e  cmp     [rsp+500h+var_4C0], 0Bh
0x18001fea3  jz      short loc_18001FEB9
0x18001fea5  mov     edi, 0Dh
0x18001feaa  jmp     loc_180020388
0x18001feaf  mov     edi, 0Eh
0x18001feb4  jmp     loc_180020388
0x18001feb9  mov     rcx, r13
0x18001febc  cmp     rcx, 0Bh
0x18001fec0  jnb     short loc_18001FEDA
0x18001fec2  mov     rax, rcx
0x18001fec5  add     rax, rax
0x18001fec8  mov     eax, [rsi+rax*8+0Ch]
0x18001fecc  cmp     dword ptr [rbp+rcx*4+400h+var_F0], eax
0x18001fed3  jnz     short loc_18001FEA5
0x18001fed5  inc     rcx
0x18001fed8  jmp     short loc_18001FEBC
0x18001feda  mov     edi, r13d
0x18001fedd  mov     rax, [rsi]
0x18001fee0  mov     dword ptr [rsp+500h+var_4B8], eax
0x18001fee4  shr     rax, 20h
0x18001fee8  mov     dword ptr [rsp+500h+var_4B8+4], eax
0x18001feec  mov     rdx, [rsp+500h+var_4B8]
0x18001fef1  lea     rcx, [rbp+400h+var_F0]
0x18001fef8  call    ?FileTimeToString@TimeUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@Z; TimeUtils::FileTimeToString(_FILETIME)
0x18001fefd  mov     rbx, rax
0x18001ff00  lea     rdx, aPreviousPrtAtt; "Previous Prt Attempt"
0x18001ff07  lea     rcx, [rbp+400h+var_C0]
0x18001ff0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ff13  nop
0x18001ff14  lea     rdx, [rbp+400h+var_C0]
0x18001ff1b  mov     rcx, r15
0x18001ff1e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18001ff23  mov     rcx, rax
0x18001ff26  mov     rdx, rbx
0x18001ff29  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ff2e  nop
0x18001ff2f  lea     rcx, [rbp+400h+var_C0]
0x18001ff36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ff3b  nop
0x18001ff3c  lea     rcx, [rbp+400h+var_F0]
0x18001ff43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ff48  lea     rcx, [rbp+400h+var_1E0]
0x18001ff4f  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18001ff54  nop
0x18001ff55  lea     rdx, a0x; "0x"
0x18001ff5c  lea     rcx, [rbp+400h+var_1E0]
0x18001ff63  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18001ff68  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001ff6f  mov     rcx, rax
0x18001ff72  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001ff78  mov     edx, [rsi+10h]
0x18001ff7b  mov     rcx, rax
0x18001ff7e  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18001ff84  lea     rdx, [rbp+400h+var_F0]
0x18001ff8b  lea     rcx, [rbp+400h+var_1D8]
0x18001ff92  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18001ff97  nop
0x18001ff98  lea     rdx, aAttemptStatus; "Attempt Status"
0x18001ff9f  lea     rcx, [rbp+400h+var_C0]
0x18001ffa6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ffab  nop
0x18001ffac  lea     rdx, [rbp+400h+var_C0]
0x18001ffb3  mov     rcx, r15
0x18001ffb6  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18001ffbb  mov     rcx, rax
0x18001ffbe  lea     rdx, [rbp+400h+var_F0]
0x18001ffc5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ffca  nop
0x18001ffcb  lea     rcx, [rbp+400h+var_C0]
0x18001ffd2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ffd7  nop
0x18001ffd8  lea     rcx, [rbp+400h+var_F0]
0x18001ffdf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ffe4  mov     r13, [rsi+20h]
0x18001ffe8  lea     rdx, aUserIdentity; "User Identity"
0x18001ffef  lea     rcx, [rbp+400h+var_F0]
0x18001fff6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001fffb  nop
0x18001fffc  lea     rdx, [rbp+400h+var_F0]
0x180020003  mov     rcx, r15
0x180020006  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18002000b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002000f  mov     r8, rbx
0x180020012  xor     ecx, ecx
0x180020014  inc     r8
0x180020017  cmp     [r13+r8*2+0], cx
0x18002001d  jnz     short loc_180020014
0x18002001f  mov     rdx, r13
0x180020022  mov     rcx, rax
0x180020025  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002002a  nop
0x18002002b  lea     rcx, [rbp+400h+var_F0]
0x180020032  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020037  lea     rcx, [rbp+400h+var_2D0]
0x18002003e  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180020043  nop
0x180020044  mov     ecx, [rsi+30h]
0x180020047  call    GetAADCredentialTypeName
0x18002004c  mov     rdx, rax
0x18002004f  lea     rcx, [rbp+400h+var_2D0]
0x180020056  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002005b  lea     rdx, [rbp+400h+var_C0]
0x180020062  lea     rcx, [rbp+400h+var_2C8]
0x180020069  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002006e  nop
0x18002006f  lea     rdx, aCredentialType; "Credential Type"
0x180020076  lea     rcx, [rbp+400h+var_F0]
0x18002007d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020082  nop
0x180020083  lea     rdx, [rbp+400h+var_F0]
0x18002008a  mov     rcx, r15
0x18002008d  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180020092  mov     rcx, rax
0x180020095  lea     rdx, [rbp+400h+var_C0]
0x18002009c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800200a1  nop
0x1800200a2  lea     rcx, [rbp+400h+var_F0]
0x1800200a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800200ae  nop
0x1800200af  lea     rcx, [rbp+400h+var_C0]
0x1800200b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800200bb  mov     r13, [rsi+40h]
0x1800200bf  lea     rdx, aCorrelationId_1; "Correlation ID"
0x1800200c6  lea     rcx, [rbp+400h+var_F0]
0x1800200cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800200d2  nop
0x1800200d3  lea     rdx, [rbp+400h+var_F0]
0x1800200da  mov     rcx, r15
0x1800200dd  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800200e2  mov     r8, rbx
0x1800200e5  xor     ecx, ecx
0x1800200e7  inc     r8
0x1800200ea  cmp     [r13+r8*2+0], cx
0x1800200f0  jnz     short loc_1800200E7
0x1800200f2  mov     rdx, r13
0x1800200f5  mov     rcx, rax
0x1800200f8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800200fd  nop
0x1800200fe  lea     rcx, [rbp+400h+var_F0]
0x180020105  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002010a  mov     r13, [rsi+50h]
0x18002010e  lea     rdx, aEndpointUri; "Endpoint URI"
0x180020115  lea     rcx, [rbp+400h+var_F0]
0x18002011c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020121  nop
0x180020122  lea     rdx, [rbp+400h+var_F0]
0x180020129  mov     rcx, r15
0x18002012c  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180020131  mov     r8, rbx
0x180020134  xor     ecx, ecx
0x180020136  inc     r8
0x180020139  cmp     [r13+r8*2+0], cx
0x18002013f  jnz     short loc_180020136
0x180020141  mov     rdx, r13
0x180020144  mov     rcx, rax
0x180020147  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002014c  nop
0x18002014d  lea     rcx, [rbp+400h+var_F0]
0x180020154  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020159  mov     r13, [rsi+60h]
0x18002015d  lea     rdx, aHttpMethod; "HTTP Method"
0x180020164  lea     rcx, [rbp+400h+var_F0]
0x18002016b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020170  nop
0x180020171  lea     rdx, [rbp+400h+var_F0]
0x180020178  mov     rcx, r15
0x18002017b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180020180  mov     r8, rbx
0x180020183  xor     ecx, ecx
0x180020185  inc     r8
0x180020188  cmp     [r13+r8*2+0], cx
0x18002018e  jnz     short loc_180020185
0x180020190  mov     rdx, r13
0x180020193  mov     rcx, rax
0x180020196  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002019b  nop
0x18002019c  lea     rcx, [rbp+400h+var_F0]
0x1800201a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800201a8  lea     rcx, [rbp+400h+var_3C0]
0x1800201ac  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800201b1  nop
0x1800201b2  lea     rdx, a0x; "0x"
0x1800201b9  lea     rcx, [rbp+400h+var_3C0]
0x1800201bd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800201c2  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x1800201c9  mov     rcx, rax
0x1800201cc  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800201d2  mov     edx, [rsi+70h]
0x1800201d5  mov     rcx, rax
0x1800201d8  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x1800201de  lea     rdx, [rbp+400h+var_C0]
0x1800201e5  lea     rcx, [rbp+400h+var_3B8]
0x1800201e9  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800201ee  nop
0x1800201ef  lea     rdx, aHttpError; "HTTP Error"
0x1800201f6  lea     rcx, [rbp+400h+var_F0]
0x1800201fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020202  nop
0x180020203  lea     rdx, [rbp+400h+var_F0]
0x18002020a  mov     rcx, r15
0x18002020d  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180020212  mov     rcx, rax
0x180020215  lea     rdx, [rbp+400h+var_C0]
0x18002021c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020221  nop
0x180020222  lea     rcx, [rbp+400h+var_F0]
  ... truncated ...
```
