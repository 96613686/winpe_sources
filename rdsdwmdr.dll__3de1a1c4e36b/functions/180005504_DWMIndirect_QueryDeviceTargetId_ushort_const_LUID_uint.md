# DWMIndirect::QueryDeviceTargetId(ushort const *,_LUID *,uint *)

- ea: `0x180005504`
- end: `0x1800058eb`
- name: `?QueryDeviceTargetId@DWMIndirect@@IEAAJPEBGPEAU_LUID@@PEAI@Z`
- size: `999`
- prototype: `__int64 __fastcall(DWMIndirect *__hidden this, const unsigned __int16 *, struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180004cbc`

## callees

- `0x18000160c`
- `0x180001724`
- `0x1800032d4`
- `0x180003314`
- `0x180005504`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `USER32!DisplayConfigGetDeviceInfo` at `0x1800057c4`
- `USER32!DisplayConfigGetDeviceInfo` at `0x1800057c4`
- `USER32!QueryDisplayConfig` at `0x18000573e`
- `USER32!QueryDisplayConfig` at `0x18000573e`
- `USER32!GetDisplayConfigBufferSizes` at `0x180005557`
- `USER32!GetDisplayConfigBufferSizes` at `0x180005557`

## string_xrefs

- `0x1800055a9`: `GetDisplayConfigBufferSizes failed`
- `0x18000562d`: `DISPLAYCONFIG_PATH_INFO`
- `0x1800056e2`: `DISPLAYCONFIG_MODE_INFO`
- `0x180005763`: `QueryDisplayConfig failed.`
- `0x180005831`: `DisplayConfigGetDeviceInfo failed.`

## pseudocode

```c
__int64 __fastcall DWMIndirect::QueryDeviceTargetId(
        DWMIndirect *this,
        const char *a2,
        struct _LUID *a3,
        unsigned int *a4)
{
  LONG DisplayConfigBufferSizes; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  DISPLAYCONFIG_PATH_INFO *v11; // rdi
  __int64 v12; // r8
  __int64 v13; // r9
  DISPLAYCONFIG_MODE_INFO *modeInfoArray; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  DISPLAYCONFIG_MODE_INFO *v17; // r14
  __int64 v18; // rcx
  __int16 *v19; // rdx
  const char *v20; // rax
  LONG v21; // eax
  const char *v22; // rax
  __int64 v23; // rsi
  LONG DeviceInfo; // eax
  const char *v25; // rax
  int v26; // ecx
  int v27; // edx
  int v29; // [rsp+50h] [rbp-89h] BYREF
  int v30; // [rsp+54h] [rbp-85h] BYREF
  UINT32 numPathArrayElements; // [rsp+58h] [rbp-81h] BYREF
  const char *v32; // [rsp+60h] [rbp-79h] BYREF
  const char *v33; // [rsp+68h] [rbp-71h] BYREF
  const char *v34; // [rsp+70h] [rbp-69h] BYREF
  const char *v35; // [rsp+78h] [rbp-61h] BYREF
  UINT32 numModeInfoArrayElements[4]; // [rsp+80h] [rbp-59h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v38[76]; // [rsp+A4h] [rbp-35h] BYREF

  v35 = a2;
  numPathArrayElements = 0;
  numModeInfoArrayElements[0] = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, numModeInfoArrayElements);
  v10 = DisplayConfigBufferSizes;
  if ( DisplayConfigBufferSizes )
  {
    if ( DisplayConfigBufferSizes > 0 )
      v10 = (unsigned __int16)DisplayConfigBufferSizes | 0x80070000;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v29 = 757;
      v32 = "QueryDeviceTargetId";
      v30 = v10;
      v33 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
      v34 = "GetDisplayConfigBufferSizes failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (__int64)&dword_18003772C,
        v8,
        v9,
        (const unsigned __int16 **)&v34,
        (__int64)&v30,
        (const unsigned __int16 **)&v33,
        (__int64)&v29,
        (const unsigned __int16 **)&v32);
    }
    return v10;
  }
  v11 = (DISPLAYCONFIG_PATH_INFO *)operator new(saturated_mul(numPathArrayElements, 0x48u));
  if ( !v11 )
  {
    v10 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v30 = 762;
      v34 = "DISPLAYCONFIG_PATH_INFO";
      v29 = -2147467261;
      v33 = "QueryDeviceTargetId";
      v32 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
      v35 = "Unexpected NULL object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        2147500035LL,
        (__int64)byte_1800376E1,
        v12,
        v13,
        (const unsigned __int16 **)&v35,
        (__int64)&v29,
        (const unsigned __int16 **)&v32,
        (__int64)&v30,
        (const unsigned __int16 **)&v33,
        (const unsigned __int16 **)&v34);
    }
    return v10;
  }
  modeInfoArray = (DISPLAYCONFIG_MODE_INFO *)operator new(saturated_mul(numModeInfoArrayElements[0], 0x40u));
  v17 = modeInfoArray;
  if ( modeInfoArray )
  {
    v21 = QueryDisplayConfig(2u, &numPathArrayElements, v11, numModeInfoArrayElements, modeInfoArray, 0);
    v10 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v10 = (unsigned __int16)v21 | 0x80070000;
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_33;
      v22 = "QueryDisplayConfig failed.";
      v30 = 773;
      v19 = (__int16 *)byte_180037649;
    }
    else
    {
      v23 = 0;
      v10 = -2147467263;
      if ( !numPathArrayElements )
        goto LABEL_33;
      while ( 1 )
      {
        requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_SOURCE_NAME;
        requestPacket.adapterId = v11[v23].sourceInfo.adapterId;
        requestPacket.id = v11[v23].sourceInfo.id;
        requestPacket.size = 84;
        memset_0(v38, 0, 0x40u);
        DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
        if ( DeviceInfo )
          break;
        v25 = v35;
        do
        {
          v26 = *(unsigned __int16 *)&v25[v38 - v35];
          v27 = *(unsigned __int16 *)v25 - v26;
          if ( v27 )
            break;
          v25 += 2;
        }
        while ( v26 );
        if ( !v27 )
        {
          v10 = 0;
          *a3 = v11[v23].targetInfo.adapterId;
          *a4 = v11[v23].targetInfo.id;
          goto LABEL_33;
        }
        v23 = (unsigned int)(v23 + 1);
        if ( (unsigned int)v23 >= numPathArrayElements )
          goto LABEL_33;
      }
      v10 = DeviceInfo > 0 ? (unsigned __int16)DeviceInfo | 0x80070000 : DeviceInfo;
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_33;
      v22 = "DisplayConfigGetDeviceInfo failed.";
      v30 = 785;
      v19 = (__int16 *)&dword_1800375FC;
    }
    v35 = v22;
    v34 = "QueryDeviceTargetId";
    v33 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    v20 = "Error condition failed";
    v29 = v10;
  }
  else
  {
    v18 = 2147500035LL;
    v10 = -2147467261;
    if ( (unsigned int)dword_180044008 <= 2 )
      goto LABEL_33;
    v30 = 765;
    v35 = "DISPLAYCONFIG_MODE_INFO";
    v19 = &word_180037696;
    v29 = -2147467261;
    v34 = "QueryDeviceTargetId";
    v33 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    v20 = "Unexpected NULL object";
  }
  v32 = v20;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
    v18,
    (__int64)v19,
    v15,
    v16,
    (const unsigned __int16 **)&v32,
    (__int64)&v29,
    (const unsigned __int16 **)&v33,
    (__int64)&v30,
    (const unsigned __int16 **)&v34,
    (const unsigned __int16 **)&v35);
LABEL_33:
  operator delete(v11);
  if ( v17 )
    operator delete(v17);
  return v10;
}

```

## disassembly

```asm
0x180005504  mov     [rsp-8+arg_0], rbx
0x180005509  push    rbp
0x18000550a  push    rsi
0x18000550b  push    rdi
0x18000550c  push    r12
0x18000550e  push    r13
0x180005510  push    r14
0x180005512  push    r15
0x180005514  lea     rbp, [rsp-27h]
0x180005519  sub     rsp, 100h
0x180005520  mov     rax, cs:__security_cookie
0x180005527  xor     rax, rsp
0x18000552a  mov     [rbp+57h+var_40], rax
0x18000552e  mov     r12, r8
0x180005531  mov     [rbp+57h+var_B8], rdx
0x180005535  mov     esi, 2
0x18000553a  mov     [rsp+130h+numPathArrayElements], 0
0x180005542  mov     ecx, esi; flags
0x180005544  mov     [rbp+57h+numModeInfoArrayElements], 0
0x18000554b  lea     r8, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18000554f  mov     r13, r9
0x180005552  lea     rdx, [rsp+130h+numPathArrayElements]; numPathArrayElements
0x180005557  call    cs:__imp_GetDisplayConfigBufferSizes
0x18000555d  mov     ebx, eax
0x18000555f  test    eax, eax
0x180005561  jz      loc_1800055ED
0x180005567  jle     short loc_180005572
0x180005569  movzx   ebx, ax
0x18000556c  or      ebx, 80070000h
0x180005572  mov     eax, cs:dword_180044008
0x180005578  cmp     eax, esi
0x18000557a  jbe     loc_1800058C2
0x180005580  lea     rax, aQuerydevicetar; "QueryDeviceTargetId"
0x180005587  mov     [rsp+130h+var_E0], 2F5h
0x18000558f  mov     [rbp+57h+var_D0], rax
0x180005593  lea     rdx, dword_18003772C
0x18000559a  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800055a1  mov     [rsp+130h+var_DC], ebx
0x1800055a5  mov     [rbp+57h+var_C8], rax
0x1800055a9  lea     rax, aGetdisplayconf; "GetDisplayConfigBufferSizes failed"
0x1800055b0  mov     [rbp+57h+var_C0], rax
0x1800055b4  lea     rax, [rbp+57h+var_D0]
0x1800055b8  mov     [rsp+130h+var_F0], rax
0x1800055bd  lea     rax, [rsp+130h+var_E0]
0x1800055c2  mov     [rsp+130h+var_F8], rax
0x1800055c7  lea     rax, [rbp+57h+var_C8]
0x1800055cb  mov     [rsp+130h+var_100], rax
0x1800055d0  lea     rax, [rsp+130h+var_DC]
0x1800055d5  mov     [rsp+130h+currentTopologyId], rax
0x1800055da  lea     rax, [rbp+57h+var_C0]
0x1800055de  mov     [rsp+130h+modeInfoArray], rax
0x1800055e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800055e8  jmp     loc_1800058C2
0x1800055ed  mov     ecx, [rsp+130h+numPathArrayElements]
0x1800055f1  mov     eax, 48h ; 'H'
0x1800055f6  mul     rcx
0x1800055f9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005600  cmovb   rax, rbx
0x180005604  mov     rcx, rax; Size
0x180005607  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000560c  mov     rdi, rax
0x18000560f  test    rax, rax
0x180005612  jnz     loc_1800056AE
0x180005618  mov     eax, cs:dword_180044008
0x18000561e  mov     ecx, 80004003h
0x180005623  mov     ebx, ecx
0x180005625  cmp     eax, esi
0x180005627  jbe     loc_1800058C2
0x18000562d  lea     rax, aDisplayconfigP; "DISPLAYCONFIG_PATH_INFO"
0x180005634  mov     [rsp+130h+var_DC], 2FAh
0x18000563c  mov     [rbp+57h+var_C0], rax
0x180005640  lea     rdx, byte_1800376E1
0x180005647  lea     rax, aQuerydevicetar; "QueryDeviceTargetId"
0x18000564e  mov     [rsp+130h+var_E0], ecx
0x180005652  mov     [rbp+57h+var_C8], rax
0x180005656  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000565d  mov     [rbp+57h+var_D0], rax
0x180005661  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180005668  mov     [rbp+57h+var_B8], rax
0x18000566c  lea     rax, [rbp+57h+var_C0]
0x180005670  mov     [rsp+130h+var_E8], rax
0x180005675  lea     rax, [rbp+57h+var_C8]
0x180005679  mov     [rsp+130h+var_F0], rax
0x18000567e  lea     rax, [rsp+130h+var_DC]
0x180005683  mov     [rsp+130h+var_F8], rax
0x180005688  lea     rax, [rbp+57h+var_D0]
0x18000568c  mov     [rsp+130h+var_100], rax
0x180005691  lea     rax, [rsp+130h+var_E0]
0x180005696  mov     [rsp+130h+currentTopologyId], rax
0x18000569b  lea     rax, [rbp+57h+var_B8]
0x18000569f  mov     [rsp+130h+modeInfoArray], rax
0x1800056a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800056a9  jmp     loc_1800058C2
0x1800056ae  mov     ecx, [rbp+57h+numModeInfoArrayElements]
0x1800056b1  mov     eax, 40h ; '@'
0x1800056b6  mul     rcx
0x1800056b9  cmovb   rax, rbx
0x1800056bd  mov     rcx, rax; Size
0x1800056c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800056c5  mov     r14, rax
0x1800056c8  test    rax, rax
0x1800056cb  jnz     short loc_180005722
0x1800056cd  mov     eax, cs:dword_180044008
0x1800056d3  mov     ecx, 80004003h
0x1800056d8  mov     ebx, ecx
0x1800056da  cmp     eax, esi
0x1800056dc  jbe     loc_1800058AD
0x1800056e2  lea     rax, aDisplayconfigM; "DISPLAYCONFIG_MODE_INFO"
0x1800056e9  mov     [rsp+130h+var_DC], 2FDh
0x1800056f1  mov     [rbp+57h+var_B8], rax
0x1800056f5  lea     rdx, word_180037696
0x1800056fc  lea     rax, aQuerydevicetar; "QueryDeviceTargetId"
0x180005703  mov     [rsp+130h+var_E0], ecx
0x180005707  mov     [rbp+57h+var_C0], rax
0x18000570b  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005712  mov     [rbp+57h+var_C8], rax
0x180005716  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x18000571d  jmp     loc_18000586C
0x180005722  mov     [rsp+130h+currentTopologyId], 0; currentTopologyId
0x18000572b  lea     r9, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18000572f  mov     r8, rdi; pathArray
0x180005732  mov     [rsp+130h+modeInfoArray], r14; modeInfoArray
0x180005737  lea     rdx, [rsp+130h+numPathArrayElements]; numPathArrayElements
0x18000573c  mov     ecx, esi; flags
0x18000573e  call    cs:__imp_QueryDisplayConfig
0x180005744  mov     ebx, eax
0x180005746  test    eax, eax
0x180005748  jz      short loc_18000577E
0x18000574a  jle     short loc_180005755
0x18000574c  movzx   ebx, ax
0x18000574f  or      ebx, 80070000h
0x180005755  mov     eax, cs:dword_180044008
0x18000575b  cmp     eax, esi
0x18000575d  jbe     loc_1800058AD
0x180005763  lea     rax, aQuerydisplayco; "QueryDisplayConfig failed."
0x18000576a  mov     [rsp+130h+var_DC], 305h
0x180005772  lea     rdx, byte_180037649
0x180005779  jmp     loc_180005847
0x18000577e  xor     esi, esi
0x180005780  mov     ebx, 80004001h
0x180005785  cmp     [rsp+130h+numPathArrayElements], esi
0x180005789  jbe     loc_1800058AD
0x18000578f  lea     r15, [rsi+rsi*8]
0x180005793  mov     [rbp+57h+requestPacket.type], 1
0x18000579a  mov     rax, [rdi+r15*8]
0x18000579e  lea     rcx, [rbp+57h+var_8C]; void *
0x1800057a2  xor     edx, edx; Val
0x1800057a4  mov     qword ptr [rbp+57h+requestPacket.adapterId.LowPart], rax
0x1800057a8  mov     eax, [rdi+r15*8+8]
0x1800057ad  mov     [rbp+57h+requestPacket.id], eax
0x1800057b0  mov     [rbp+57h+requestPacket.size], 54h ; 'T'
0x1800057b7  lea     r8d, [rdx+40h]; Size
0x1800057bb  call    memset_0
0x1800057c0  lea     rcx, [rbp+57h+requestPacket]; requestPacket
0x1800057c4  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800057ca  test    eax, eax
0x1800057cc  jnz     short loc_180005817
0x1800057ce  mov     rax, [rbp+57h+var_B8]
0x1800057d2  lea     r8, [rbp+57h+var_8C]
0x1800057d6  sub     r8, rax
0x1800057d9  movzx   edx, word ptr [rax]
0x1800057dc  movzx   ecx, word ptr [rax+r8]
0x1800057e1  sub     edx, ecx
0x1800057e3  jnz     short loc_1800057ED
0x1800057e5  add     rax, 2
0x1800057e9  test    ecx, ecx
0x1800057eb  jnz     short loc_1800057D9
0x1800057ed  test    edx, edx
0x1800057ef  jz      short loc_1800057FE
0x1800057f1  inc     esi
0x1800057f3  cmp     esi, [rsp+130h+numPathArrayElements]
0x1800057f7  jb      short loc_18000578F
0x1800057f9  jmp     loc_1800058AD
0x1800057fe  mov     rax, [rdi+r15*8+14h]
0x180005803  xor     ebx, ebx
0x180005805  mov     [r12], rax
0x180005809  mov     eax, [rdi+r15*8+1Ch]
0x18000580e  mov     [r13+0], eax
0x180005812  jmp     loc_1800058AD
0x180005817  jg      short loc_18000581D
0x180005819  mov     ebx, eax
0x18000581b  jmp     short loc_180005826
0x18000581d  movzx   ebx, ax
0x180005820  or      ebx, 80070000h
0x180005826  mov     eax, cs:dword_180044008
0x18000582c  cmp     eax, 2
0x18000582f  jbe     short loc_1800058AD
0x180005831  lea     rax, aDisplayconfigg; "DisplayConfigGetDeviceInfo failed."
0x180005838  mov     [rsp+130h+var_DC], 311h
0x180005840  lea     rdx, dword_1800375FC
0x180005847  mov     [rbp+57h+var_B8], rax
0x18000584b  lea     rax, aQuerydevicetar; "QueryDeviceTargetId"
0x180005852  mov     [rbp+57h+var_C0], rax
0x180005856  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000585d  mov     [rbp+57h+var_C8], rax
0x180005861  lea     rax, aErrorCondition; "Error condition failed"
0x180005868  mov     [rsp+130h+var_E0], ebx
0x18000586c  mov     [rbp+57h+var_D0], rax
0x180005870  lea     rax, [rbp+57h+var_B8]
0x180005874  mov     [rsp+130h+var_E8], rax
0x180005879  lea     rax, [rbp+57h+var_C0]
0x18000587d  mov     [rsp+130h+var_F0], rax
0x180005882  lea     rax, [rsp+130h+var_DC]
0x180005887  mov     [rsp+130h+var_F8], rax
0x18000588c  lea     rax, [rbp+57h+var_C8]
0x180005890  mov     [rsp+130h+var_100], rax
0x180005895  lea     rax, [rsp+130h+var_E0]
0x18000589a  mov     [rsp+130h+currentTopologyId], rax
0x18000589f  lea     rax, [rbp+57h+var_D0]
0x1800058a3  mov     [rsp+130h+modeInfoArray], rax
0x1800058a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800058ad  mov     rcx, rdi; Block
0x1800058b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800058b5  test    r14, r14
0x1800058b8  jz      short loc_1800058C2
0x1800058ba  mov     rcx, r14; Block
0x1800058bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800058c2  mov     eax, ebx
0x1800058c4  mov     rcx, [rbp+57h+var_40]
0x1800058c8  xor     rcx, rsp; StackCookie
0x1800058cb  call    __security_check_cookie
0x1800058d0  mov     rbx, [rsp+130h+arg_0]
0x1800058d8  add     rsp, 100h
0x1800058df  pop     r15
0x1800058e1  pop     r14
0x1800058e3  pop     r13
0x1800058e5  pop     r12
0x1800058e7  pop     rdi
0x1800058e8  pop     rsi
0x1800058e9  pop     rbp
0x1800058ea  retn
```
