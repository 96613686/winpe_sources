# Microsoft::Windows::MDM::OmadmClient::UserInteractionManager::CreateResultsSmsMsg(long,ulong,tagOMADMACCTINFO &)

- ea: `0x140018550`
- end: `0x140018990`
- name: `?CreateResultsSmsMsg@UserInteractionManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJJKAEAUtagOMADMACCTINFO@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::UserInteractionManager *__hidden this, int, unsigned int, struct tagOMADMACCTINFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x140003eb4`
- `0x140005864`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x140018550`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400186c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140018712`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400186c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140018712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400186d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400186d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018834`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140018820`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140018820`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018924`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018924`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140018655`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14001873d`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140018873`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140018655`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14001873d`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140018873`

## string_xrefs

- `0x14001859d`: `CreateResultsSmsMsg`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::UserInteractionManager::CreateResultsSmsMsg(
        Microsoft::Windows::MDM::OmadmClient::UserInteractionManager *this,
        int a2,
        int a3,
        struct tagOMADMACCTINFO *a4)
{
  __int64 v8; // r8
  int ValueFromStruct; // eax
  unsigned int v10; // ebx
  UINT v11; // ebx
  signed int v12; // eax
  unsigned __int16 *v13; // rax
  va_list v14; // r10
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  int v17; // eax
  signed int LastError; // eax
  __int64 v19; // rcx
  WCHAR *v20; // r8
  __int64 v21; // rdx
  WCHAR v22; // ax
  _WORD *v23; // rcx
  __int64 v24; // rcx
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR **v29; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v30[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v32[3]; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+80h] [rbp-80h]
  unsigned int *v34; // [rsp+88h] [rbp-78h]
  WCHAR *v35; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+98h] [rbp-68h] BYREF
  int *v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  WCHAR v39[512]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[512]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  v27 = 0;
  v32[0] = 0;
  v32[1] = "CreateResultsSmsMsg";
  v32[2] = COmaDmLogger::GetLogger();
  v33 = 1;
  v34 = &v27;
  Arguments = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v31 = 20;
    v37 = &v31;
    v38 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v8,
      2u,
      &v36);
  }
  v36.Ptr = (ULONGLONG)&v27;
  *(_QWORD *)&v36.Size = &Arguments;
  LOBYTE(v37) = 1;
  memset_0(v39, 0, sizeof(v39));
  v35 = v39;
  v29 = &v35;
  ValueFromStruct = OmaDmGetValueFromStruct(12, a4, 0xFFFFFFFFLL, &v29, 0);
  v10 = ValueFromStruct;
  v27 = ValueFromStruct;
  if ( ValueFromStruct < 0 )
  {
    LODWORD(v32[0]) = 6014;
LABEL_5:
    HIDWORD(v32[0]) = ValueFromStruct;
    goto LABEL_45;
  }
  if ( a3 )
  {
    v11 = ((a2 >> 31) & 2) + 50005;
  }
  else
  {
    v11 = 26048;
    if ( a2 < 0 )
      v11 = 26065;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( LoadStringW(g_hInstRes, v11, Buffer, 512) && LoadStringW(g_hInstRes, 0x659Bu, v39, 512) )
  {
    if ( *((_QWORD *)a4 + 4) )
    {
      ValueFromStruct = OmaDmGetValueFromStruct(3, a4, 0xFFFFFFFFLL, &v29, 0);
      v10 = ValueFromStruct;
      v27 = ValueFromStruct;
      if ( ValueFromStruct < 0 )
        goto LABEL_17;
    }
    v27 = 0;
    v13 = (unsigned __int16 *)operator new[](0x82u, (const struct std::nothrow_t *)std::nothrow);
    v14 = (va_list)v13;
    Arguments = (va_list)v13;
    if ( !v13 )
    {
      v10 = -2147024882;
      v27 = -2147024882;
      v15 = 428;
LABEL_20:
      v16 = v10;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\userinteractionmanager.cpp",
        (const char *)v16,
        lpBuffer);
      goto LABEL_45;
    }
    v27 = 0;
    if ( a3 )
    {
      if ( a2 >= 0 )
      {
        *v13 = 0;
      }
      else
      {
        v17 = StringCchPrintfW(v13, 0x41u, L"0x%08X", (unsigned int)a2);
        v10 = v17;
        v27 = v17;
        if ( v17 < 0 )
        {
          v16 = (unsigned int)v17;
          v15 = 436;
          goto LABEL_21;
        }
      }
    }
    else
    {
      if ( *((_QWORD *)a4 + 4) )
      {
        ValueFromStruct = OmaDmGetValueFromStruct(3, a4, 0xFFFFFFFFLL, &v29, 0);
        v10 = ValueFromStruct;
        v27 = ValueFromStruct;
        if ( ValueFromStruct < 0 )
        {
LABEL_17:
          LODWORD(v32[0]) = 6023;
          goto LABEL_5;
        }
        v14 = Arguments;
      }
      v19 = 64;
      v20 = *v29;
      v21 = 65;
      do
      {
        if ( !v19 )
          break;
        v22 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *(_WORD *)v14 = v22;
        v14 += 2;
        --v19;
        --v21;
      }
      while ( v21 );
      v10 = v21 == 0 ? 0x8007007A : 0;
      v23 = v14 - 2;
      if ( v21 )
        v23 = v14;
      *v23 = 0;
      v27 = v21 == 0 ? 0x8007007A : 0;
      if ( !v21 )
      {
        v15 = 465;
        goto LABEL_20;
      }
    }
    *(_QWORD *)v30 = 0;
    if ( FormatMessageW(0x2500u, Buffer, 0, 0, v30, 0x100u, &Arguments) )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, _QWORD))(**((_QWORD **)this + 3) + 256LL))(
              *((_QWORD *)this + 3),
              v39,
              *(_QWORD *)v30);
      v27 = v10;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v27 = v10;
    }
    if ( *(_QWORD *)v30 )
      LocalFree(*(HLOCAL *)v30);
  }
  else
  {
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    v27 = v10;
  }
LABEL_45:
  operator delete(Arguments);
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(v24, OmaDmClientFunctionReturnValueEvent, 20, v27);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v32);
  return v10;
}

```

## disassembly

```asm
0x140018550  mov     [rsp-8+arg_10], rbx
0x140018555  push    rbp
0x140018556  push    rsi
0x140018557  push    rdi
0x140018558  push    r12
0x14001855a  push    r13
0x14001855c  push    r14
0x14001855e  push    r15
0x140018560  lea     rbp, [rsp-7D0h]
0x140018568  sub     rsp, 8D0h
0x14001856f  mov     rax, cs:__security_cookie
0x140018576  xor     rax, rsp
0x140018579  mov     [rbp+800h+var_40], rax
0x140018580  mov     rdi, r9
0x140018583  mov     r14d, r8d
0x140018586  mov     esi, edx
0x140018588  mov     r15, rcx
0x14001858b  xor     r12d, r12d
0x14001858e  mov     [rsp+900h+var_8C0], r12d
0x140018593  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140018598  mov     [rsp+900h+var_898], r12
0x14001859d  lea     rcx, aCreateresultss; "CreateResultsSmsMsg"
0x1400185a4  mov     [rsp+900h+var_890], rcx
0x1400185a9  mov     [rsp+900h+var_888], rax
0x1400185ae  mov     [rbp+800h+var_880], 1
0x1400185b5  lea     rax, [rsp+900h+var_8C0]
0x1400185ba  mov     [rbp+800h+var_878], rax
0x1400185be  mov     [rsp+900h+var_8B8], r12
0x1400185c3  lea     r13d, [r12+14h]
0x1400185c8  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x1400185cf  jz      short loc_140018608
0x1400185d1  mov     [rsp+900h+var_8A0], r13d
0x1400185d6  lea     rax, [rsp+900h+var_8A0]
0x1400185db  mov     [rbp+800h+var_858], rax
0x1400185df  mov     [rbp+800h+var_850], 4
0x1400185e7  lea     rax, [rbp+800h+var_868]
0x1400185eb  mov     [rsp+900h+lpBuffer], rax
0x1400185f0  lea     r9d, [r12+2]
0x1400185f5  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x1400185fc  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140018603  call    McGenEventWrite_EventWriteTransfer
0x140018608  lea     rax, [rsp+900h+var_8C0]
0x14001860d  mov     [rbp+800h+var_868], rax
0x140018611  lea     rax, [rsp+900h+var_8B8]
0x140018616  mov     [rbp+800h+var_860], rax
0x14001861a  mov     byte ptr [rbp+800h+var_858], 1
0x14001861e  xor     edx, edx; Val
0x140018620  mov     r8d, 400h; Size
0x140018626  lea     rcx, [rbp+800h+var_840]; void *
0x14001862a  call    memset_0
0x14001862f  lea     rax, [rbp+800h+var_840]
0x140018633  mov     [rbp+800h+var_870], rax
0x140018637  lea     rax, [rbp+800h+var_870]
0x14001863b  mov     [rsp+900h+var_8B0], rax
0x140018640  mov     [rsp+900h+lpBuffer], r12; int
0x140018645  lea     r9, [rsp+900h+var_8B0]
0x14001864a  or      r8d, 0FFFFFFFFh
0x14001864e  mov     rdx, rdi
0x140018651  lea     ecx, [r8+0Dh]
0x140018655  call    cs:__imp_OmaDmGetValueFromStruct
0x14001865c  nop     dword ptr [rax+rax+00h]
0x140018661  mov     ebx, eax
0x140018663  mov     [rsp+900h+var_8C0], eax
0x140018667  test    eax, eax
0x140018669  jns     short loc_14001867C
0x14001866b  mov     dword ptr [rsp+900h+var_898], 177Eh
0x140018673  mov     dword ptr [rsp+900h+var_898+4], eax
0x140018677  jmp     loc_140018931
0x14001867c  test    r14d, r14d
0x14001867f  jz      short loc_140018691
0x140018681  mov     ebx, esi
0x140018683  sar     ebx, 1Fh
0x140018686  and     ebx, 2
0x140018689  add     ebx, 0C355h
0x14001868f  jmp     short loc_14001869E
0x140018691  mov     ebx, 65C0h
0x140018696  lea     eax, [rbx+11h]
0x140018699  test    esi, esi
0x14001869b  cmovs   ebx, eax
0x14001869e  xor     edx, edx; Val
0x1400186a0  mov     r8d, 400h; Size
0x1400186a6  lea     rcx, [rbp+800h+Buffer]; void *
0x1400186ad  call    memset_0
0x1400186b2  mov     r9d, 200h; cchBufferMax
0x1400186b8  lea     r8, [rbp+800h+Buffer]; lpBuffer
0x1400186bf  mov     edx, ebx; uID
0x1400186c1  mov     rcx, cs:?g_hInstRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1400186c8  call    cs:__imp_LoadStringW
0x1400186cf  nop     dword ptr [rax+rax+00h]
0x1400186d4  test    eax, eax
0x1400186d6  jnz     short loc_1400186FC
0x1400186d8  call    cs:__imp_GetLastError
0x1400186df  nop     dword ptr [rax+rax+00h]
0x1400186e4  mov     ebx, eax
0x1400186e6  test    eax, eax
0x1400186e8  jle     short loc_1400186F3
0x1400186ea  movzx   ebx, ax
0x1400186ed  or      ebx, 80070000h
0x1400186f3  mov     [rsp+900h+var_8C0], ebx
0x1400186f7  jmp     loc_140018931
0x1400186fc  mov     r9d, 200h; cchBufferMax
0x140018702  lea     r8, [rbp+800h+var_840]; lpBuffer
0x140018706  mov     edx, 659Bh; uID
0x14001870b  mov     rcx, cs:?g_hInstRes@@3PEAUHINSTANCE__@@EA; hInstance
0x140018712  call    cs:__imp_LoadStringW
0x140018719  nop     dword ptr [rax+rax+00h]
0x14001871e  test    eax, eax
0x140018720  jz      short loc_1400186D8
0x140018722  cmp     [rdi+20h], r12
0x140018726  jz      short loc_140018760
0x140018728  mov     [rsp+900h+lpBuffer], r12
0x14001872d  lea     r9, [rsp+900h+var_8B0]
0x140018732  or      r8d, 0FFFFFFFFh
0x140018736  mov     rdx, rdi
0x140018739  lea     ecx, [r8+4]
0x14001873d  call    cs:__imp_OmaDmGetValueFromStruct
0x140018744  nop     dword ptr [rax+rax+00h]
0x140018749  mov     ebx, eax
0x14001874b  mov     [rsp+900h+var_8C0], eax
0x14001874f  test    eax, eax
0x140018751  jns     short loc_140018760
0x140018753  mov     dword ptr [rsp+900h+var_898], 1787h
0x14001875b  jmp     loc_140018673
0x140018760  mov     [rsp+900h+var_8C0], r12d
0x140018765  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001876c  mov     ecx, 82h; unsigned __int64
0x140018771  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140018776  mov     r10, rax
0x140018779  mov     [rsp+900h+var_8B8], rax
0x14001877e  test    rax, rax
0x140018781  jnz     short loc_1400187AC
0x140018783  mov     ebx, 8007000Eh
0x140018788  mov     [rsp+900h+var_8C0], ebx
0x14001878c  mov     edx, 1ACh; void *
0x140018791  mov     r9d, ebx; char *
0x140018794  mov     rcx, [rbp+808h]; this
0x14001879b  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400187a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400187a7  jmp     loc_140018931
0x1400187ac  mov     [rsp+900h+var_8C0], r12d
0x1400187b1  test    r14d, r14d
0x1400187b4  jz      loc_140018858
0x1400187ba  test    esi, esi
0x1400187bc  jns     short loc_1400187E9
0x1400187be  mov     r9d, esi
0x1400187c1  lea     r8, a0x08x; "0x%08X"
0x1400187c8  mov     edx, 41h ; 'A'; unsigned __int64
0x1400187cd  mov     rcx, rax; unsigned __int16 *
0x1400187d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400187d5  mov     ebx, eax
0x1400187d7  mov     [rsp+900h+var_8C0], eax
0x1400187db  test    eax, eax
0x1400187dd  jns     short loc_1400187ED
0x1400187df  mov     r9d, eax
0x1400187e2  mov     edx, 1B4h
0x1400187e7  jmp     short loc_140018794
0x1400187e9  mov     [rax], r12w
0x1400187ed  mov     qword ptr [rsp+900h+var_8A8], r12
0x1400187f2  lea     rax, [rsp+900h+var_8B8]
0x1400187f7  mov     [rsp+900h+Arguments], rax; Arguments
0x1400187fc  mov     [rsp+900h+nSize], 100h; nSize
0x140018804  lea     rax, [rsp+900h+var_8A8]
0x140018809  mov     [rsp+900h+lpBuffer], rax; lpBuffer
0x14001880e  xor     r9d, r9d; dwLanguageId
0x140018811  xor     r8d, r8d; dwMessageId
0x140018814  lea     rdx, [rbp+800h+Buffer]; lpSource
0x14001881b  mov     ecx, 2500h; dwFlags
0x140018820  call    cs:__imp_FormatMessageW
0x140018827  nop     dword ptr [rax+rax+00h]
0x14001882c  test    eax, eax
0x14001882e  jnz     loc_1400188F8
0x140018834  call    cs:__imp_GetLastError
0x14001883b  nop     dword ptr [rax+rax+00h]
0x140018840  mov     ebx, eax
0x140018842  test    eax, eax
0x140018844  jle     short loc_14001884F
0x140018846  movzx   ebx, ax
0x140018849  or      ebx, 80070000h
0x14001884f  mov     [rsp+900h+var_8C0], ebx
0x140018853  jmp     loc_14001891A
0x140018858  cmp     [rdi+20h], r12
0x14001885c  jz      short loc_140018892
0x14001885e  mov     [rsp+900h+lpBuffer], r12
0x140018863  lea     r9, [rsp+900h+var_8B0]
0x140018868  or      r8d, 0FFFFFFFFh
0x14001886c  mov     rdx, rdi
0x14001886f  lea     ecx, [r8+4]
0x140018873  call    cs:__imp_OmaDmGetValueFromStruct
0x14001887a  nop     dword ptr [rax+rax+00h]
0x14001887f  mov     ebx, eax
0x140018881  mov     [rsp+900h+var_8C0], eax
0x140018885  test    eax, eax
0x140018887  js      loc_140018753
0x14001888d  mov     r10, [rsp+900h+var_8B8]
0x140018892  mov     ecx, 40h ; '@'
0x140018897  mov     rax, [rsp+900h+var_8B0]
0x14001889c  mov     r8, [rax]
0x14001889f  lea     edx, [rcx+1]
0x1400188a2  test    rcx, rcx
0x1400188a5  jz      short loc_1400188C5
0x1400188a7  movzx   eax, word ptr [r8]
0x1400188ab  test    ax, ax
0x1400188ae  jz      short loc_1400188C5
0x1400188b0  add     r8, 2
0x1400188b4  mov     [r10], ax
0x1400188b8  add     r10, 2
0x1400188bc  dec     rcx
0x1400188bf  sub     rdx, 1
0x1400188c3  jnz     short loc_1400188A2
0x1400188c5  mov     rax, rdx
0x1400188c8  neg     rax
0x1400188cb  sbb     ebx, ebx
0x1400188cd  not     ebx
0x1400188cf  and     ebx, 8007007Ah
0x1400188d5  lea     rcx, [r10-2]
0x1400188d9  test    rdx, rdx
0x1400188dc  cmovnz  rcx, r10
0x1400188e0  mov     [rcx], r12w
0x1400188e4  mov     [rsp+900h+var_8C0], ebx
0x1400188e8  jnz     loc_1400187ED
0x1400188ee  mov     edx, 1D1h
0x1400188f3  jmp     loc_140018791
0x1400188f8  mov     rcx, [r15+18h]
0x1400188fc  mov     rax, [rcx]
0x1400188ff  mov     r8, qword ptr [rsp+900h+var_8A8]
0x140018904  lea     rdx, [rbp+800h+var_840]
0x140018908  mov     rax, [rax+100h]
0x14001890f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018914  mov     ebx, eax
0x140018916  mov     [rsp+900h+var_8C0], eax
0x14001891a  mov     rcx, qword ptr [rsp+900h+var_8A8]; hMem
0x14001891f  test    rcx, rcx
0x140018922  jz      short loc_140018931
0x140018924  call    cs:__imp_LocalFree
0x14001892b  nop     dword ptr [rax+rax+00h]
0x140018930  nop
0x140018931  mov     rcx, [rsp+900h+var_8B8]; Block
0x140018936  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001893b  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x140018942  jz      short loc_140018959
0x140018944  mov     r9d, [rsp+900h+var_8C0]
0x140018949  mov     r8d, r13d
0x14001894c  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x140018953  call    McTemplateU0qq_EventWriteTransfer
0x140018958  nop
0x140018959  lea     rcx, [rsp+900h+var_898]; this
0x14001895e  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140018963  mov     eax, ebx
0x140018965  mov     rcx, [rbp+800h+var_40]
0x14001896c  xor     rcx, rsp; StackCookie
0x14001896f  call    __security_check_cookie
0x140018974  mov     rbx, [rsp+900h+arg_10]
0x14001897c  add     rsp, 8D0h
0x140018983  pop     r15
0x140018985  pop     r14
0x140018987  pop     r13
0x140018989  pop     r12
0x14001898b  pop     rdi
0x14001898c  pop     rsi
0x14001898d  pop     rbp
0x14001898e  retn
```
