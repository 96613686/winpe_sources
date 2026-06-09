# CCDSResultsParser::IsProtocolInfoProtected(Windows::Media::Streaming::Internal::IProtocolInfo *)

- ea: `0x18002cc70`
- end: `0x18002cfae`
- name: `?IsProtocolInfoProtected@CCDSResultsParser@@SA_NPEAUIProtocolInfo@Internal@Streaming@Media@Windows@@@Z`
- size: `830`
- prototype: `bool __fastcall(struct Windows::Media::Streaming::Internal::IProtocolInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002cfb4`

## callees

- `0x1800097c0`
- `0x18000d990`
- `0x180011930`
- `0x18002c28c`
- `0x18002c324`
- `0x18002c370`
- `0x18002cc70`
- `0x18002ed7c`
- `0x18002f144`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cd7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cdbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cf60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cd7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cdbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cf60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cd61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cda1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cf46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cd61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cda1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cf46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002cd4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002cd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002ce83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002ce98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002ceb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002cf31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002cd4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002cd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002ce83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002ce98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002ceb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002cf31`

## pseudocode

```c
bool __fastcall CCDSResultsParser::IsProtocolInfoProtected(
        struct Windows::Media::Streaming::Internal::IProtocolInfo *a1)
{
  __int64 v1; // rax
  bool v3; // si
  int (__fastcall *v4)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, __int64 *); // rbx
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, _QWORD, char *); // rbx
  _QWORD *v7; // rax
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v10; // rax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v12; // rax
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, _QWORD, char *); // rbx
  _QWORD *v15; // rax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rdi
  char v18; // al
  void (__fastcall *v19)(__int64, _QWORD, _BYTE *); // rbx
  _QWORD *v20; // rax
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v24; // rax
  UINT32 StringLen; // eax
  unsigned int v26; // edx
  UINT32 v27; // r8d
  __int64 v28; // rbx
  PCWSTR v29; // rax
  __int64 v30; // rax
  const WCHAR *v31; // rax
  char v33; // [rsp+30h] [rbp-29h] BYREF
  char v34; // [rsp+31h] [rbp-28h] BYREF
  _BYTE v35[6]; // [rsp+32h] [rbp-27h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  __int64 v37; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v38; // [rsp+48h] [rbp-11h] BYREF
  HSTRING v39; // [rsp+50h] [rbp-9h] BYREF
  HSTRING v40; // [rsp+58h] [rbp-1h] BYREF
  HSTRING v41[4]; // [rsp+60h] [rbp+7h] BYREF

  v1 = *(_QWORD *)a1;
  v3 = 0;
  v37 = 0;
  v4 = *(int (__fastcall **)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, __int64 *))(v1 + 120);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v37);
  if ( v4(a1, &v37) >= 0 )
  {
    v5 = v37;
    v33 = 0;
    v6 = *(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v37 + 64LL);
    v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(v41, L"DLNA.ORG_PN");
    v6(v5, *v7, &v33);
    if ( v33 )
    {
      v8 = v37;
      string = 0;
      v9 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v37 + 48LL);
      v10 = (_QWORD *)Windows::Internal::StringReference::StringReference(v41, L"DLNA.ORG_PN");
      if ( v9(v8, *v10, &string) >= 0 )
      {
        if ( WindowsGetStringLen(string) >= 6 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v3 = CompareStringOrdinal(StringRawBuffer, 6, L"WMDRM_", 6, 0) == 2;
        }
        if ( WindowsGetStringLen(string) >= 5 )
        {
          v12 = WindowsGetStringRawBuffer(string, 0);
          if ( CompareStringOrdinal(v12, 5, L"DTCP_", 5, 0) == 2 )
            v3 = 1;
        }
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
    }
    v13 = v37;
    v34 = 0;
    v14 = *(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v37 + 64LL);
    v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(v41, L"upnp.org_DRMInfo");
    v14(v13, *v15, &v34);
    v17 = v37;
    v18 = v3;
    if ( v34 )
      v18 = 1;
    v35[0] = 0;
    v3 = v18;
    v19 = *(void (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v37 + 64LL);
    v20 = (_QWORD *)Windows::Internal::StringReference::StringReference(v41, (const unsigned __int16 (*)[15])v16);
    v19(v17, *v20, v35);
    if ( v35[0] )
    {
      v22 = v37;
      v38 = 0;
      v23 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v37 + 48LL);
      v24 = (_QWORD *)Windows::Internal::StringReference::StringReference(v41, (const unsigned __int16 (*)[15])v21);
      if ( v23(v22, *v24, &v38) >= 0 )
      {
        v39 = 0;
        StringLen = WindowsGetStringLen(v38);
        v27 = 8;
        if ( StringLen <= 8 )
          v27 = WindowsGetStringLen(v38);
        if ( Windows::Internal::String::Substring(
               (Windows::Internal::String *)&v38,
               v26,
               v27,
               (struct Windows::Internal::String *)&v39) >= 0 )
        {
          v28 = WindowsGetStringLen(v39);
          v29 = WindowsGetStringRawBuffer(v39, 0);
          LODWORD(v41[0]) = 0;
          v41[1] = (HSTRING)v29;
          LODWORD(string) = 0;
          v41[2] = (HSTRING)&v29[v28];
          if ( (unsigned int)CStringReaderT<unsigned short>::ReadUInt32(v41, &string, 16) )
          {
            if ( ((unsigned int)string & 0x10000) != 0 )
              v3 = 1;
          }
        }
        Windows::Internal::String::~String((Windows::Internal::String *)&v39);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&v38);
    }
  }
  v30 = *(_QWORD *)a1;
  v40 = 0;
  if ( (*(int (__fastcall **)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, HSTRING *))(v30 + 88))(
         a1,
         &v40) >= 0
    && WindowsGetStringLen(v40) >= 0x13 )
  {
    v31 = WindowsGetStringRawBuffer(v40, 0);
    if ( CompareStringOrdinal(v31, 19, L"application/x-dtcp1", 19, 1) == 2 )
      v3 = 1;
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v37);
  return v3;
}

```

## disassembly

```asm
0x18002cc70  mov     [rsp-8+arg_8], rbx
0x18002cc75  mov     [rsp-8+arg_10], rsi
0x18002cc7a  push    rbp
0x18002cc7b  push    rdi
0x18002cc7c  push    r12
0x18002cc7e  push    r14
0x18002cc80  push    r15
0x18002cc82  lea     rbp, [rsp-37h]
0x18002cc87  sub     rsp, 90h
0x18002cc8e  mov     rax, cs:__security_cookie
0x18002cc95  xor     rax, rsp
0x18002cc98  mov     [rbp+57h+var_30], rax
0x18002cc9c  mov     rax, [rcx]
0x18002cc9f  mov     r14, rcx
0x18002cca2  xor     r15d, r15d
0x18002cca5  lea     rcx, [rbp+57h+var_70]
0x18002cca9  movzx   esi, r15b
0x18002ccad  mov     [rbp+57h+var_70], r15
0x18002ccb1  mov     rbx, [rax+78h]
0x18002ccb5  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002ccba  lea     rdx, [rbp+57h+var_70]
0x18002ccbe  mov     rcx, r14
0x18002ccc1  mov     rax, rbx
0x18002ccc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccc9  lea     r12d, [r15+1]
0x18002cccd  test    eax, eax
0x18002cccf  js      loc_18002CF12
0x18002ccd5  mov     rdi, [rbp+57h+var_70]
0x18002ccd9  lea     rdx, aDlnaOrgPn; "DLNA.ORG_PN"
0x18002cce0  mov     [rbp+57h+var_80], r15b
0x18002cce4  lea     rcx, [rbp+57h+var_50]; string
0x18002cce8  mov     rax, [rdi]
0x18002cceb  mov     rbx, [rax+40h]
0x18002ccef  call    ??$?0$0M@@StringReference@Internal@Windows@@QEAA@AEAY0M@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[12])
0x18002ccf4  lea     r8, [rbp+57h+var_80]
0x18002ccf8  mov     rcx, rdi
0x18002ccfb  mov     rdx, [rax]
0x18002ccfe  mov     rax, rbx
0x18002cd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd06  cmp     [rbp+57h+var_80], r15b
0x18002cd0a  jz      loc_18002CDD5
0x18002cd10  mov     rdi, [rbp+57h+var_70]
0x18002cd14  lea     rdx, aDlnaOrgPn; "DLNA.ORG_PN"
0x18002cd1b  mov     [rbp+57h+string], r15
0x18002cd1f  lea     rcx, [rbp+57h+var_50]; string
0x18002cd23  mov     rax, [rdi]
0x18002cd26  mov     rbx, [rax+30h]
0x18002cd2a  call    ??$?0$0M@@StringReference@Internal@Windows@@QEAA@AEAY0M@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[12])
0x18002cd2f  lea     r8, [rbp+57h+string]
0x18002cd33  mov     rcx, rdi
0x18002cd36  mov     rdx, [rax]
0x18002cd39  mov     rax, rbx
0x18002cd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd41  test    eax, eax
0x18002cd43  js      loc_18002CDCC
0x18002cd49  mov     rcx, [rbp+57h+string]; string
0x18002cd4d  call    cs:__imp_WindowsGetStringLen
0x18002cd53  lea     ebx, [r15+6]
0x18002cd57  cmp     eax, ebx
0x18002cd59  jb      short loc_18002CD88
0x18002cd5b  mov     rcx, [rbp+57h+string]; string
0x18002cd5f  xor     edx, edx; length
0x18002cd61  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cd67  mov     r9d, ebx; cchCount2
0x18002cd6a  mov     [rsp+0B0h+bIgnoreCase], r15d; bIgnoreCase
0x18002cd6f  mov     rcx, rax; lpString1
0x18002cd72  lea     r8, aWmdrm; "WMDRM_"
0x18002cd79  mov     edx, ebx; cchCount1
0x18002cd7b  call    cs:__imp_CompareStringOrdinal
0x18002cd81  cmp     eax, 2
0x18002cd84  cmovz   esi, r12d
0x18002cd88  mov     rcx, [rbp+57h+string]; string
0x18002cd8c  call    cs:__imp_WindowsGetStringLen
0x18002cd92  mov     ebx, 5
0x18002cd97  cmp     eax, ebx
0x18002cd99  jb      short loc_18002CDCC
0x18002cd9b  mov     rcx, [rbp+57h+string]; string
0x18002cd9f  xor     edx, edx; length
0x18002cda1  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cda7  mov     r9d, ebx; cchCount2
0x18002cdaa  mov     [rsp+0B0h+bIgnoreCase], r15d; bIgnoreCase
0x18002cdaf  mov     rcx, rax; lpString1
0x18002cdb2  lea     r8, aDtcp; "DTCP_"
0x18002cdb9  mov     edx, ebx; cchCount1
0x18002cdbb  call    cs:__imp_CompareStringOrdinal
0x18002cdc1  cmp     eax, 2
0x18002cdc4  movzx   esi, sil
0x18002cdc8  cmovz   esi, r12d
0x18002cdcc  lea     rcx, [rbp+57h+string]; this
0x18002cdd0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002cdd5  mov     rdi, [rbp+57h+var_70]
0x18002cdd9  lea     rdx, aUpnpOrgDrminfo; "upnp.org_DRMInfo"
0x18002cde0  mov     [rbp+57h+var_7F], r15b
0x18002cde4  lea     rcx, [rbp+57h+var_50]; string
0x18002cde8  mov     rax, [rdi]
0x18002cdeb  mov     rbx, [rax+40h]
0x18002cdef  call    ??$?0$0BB@@StringReference@Internal@Windows@@QEAA@AEAY0BB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[17])
0x18002cdf4  lea     r8, [rbp+57h+var_7F]
0x18002cdf8  mov     rcx, rdi
0x18002cdfb  mov     rdx, [rax]
0x18002cdfe  mov     rax, rbx
0x18002ce01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce06  cmp     [rbp+57h+var_7F], r15b
0x18002ce0a  lea     rcx, [rbp+57h+var_50]; string
0x18002ce0e  mov     rdi, [rbp+57h+var_70]
0x18002ce12  movzx   eax, sil
0x18002ce16  cmovnz  eax, r12d
0x18002ce1a  mov     [rbp+57h+var_7E], r15b
0x18002ce1e  movzx   esi, al
0x18002ce21  mov     rax, [rdi]
0x18002ce24  mov     rbx, [rax+40h]
0x18002ce28  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x18002ce2d  lea     r8, [rbp+57h+var_7E]
0x18002ce31  mov     rcx, rdi
0x18002ce34  mov     rdx, [rax]
0x18002ce37  mov     rax, rbx
0x18002ce3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce3f  cmp     [rbp+57h+var_7E], r15b
0x18002ce43  jz      loc_18002CF12
0x18002ce49  mov     rdi, [rbp+57h+var_70]
0x18002ce4d  lea     rcx, [rbp+57h+var_50]; string
0x18002ce51  mov     [rbp+57h+var_68], r15
0x18002ce55  mov     rax, [rdi]
0x18002ce58  mov     rbx, [rax+30h]
0x18002ce5c  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x18002ce61  lea     r8, [rbp+57h+var_68]
0x18002ce65  mov     rcx, rdi
0x18002ce68  mov     rdx, [rax]
0x18002ce6b  mov     rax, rbx
0x18002ce6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce73  test    eax, eax
0x18002ce75  js      loc_18002CF09
0x18002ce7b  mov     rcx, [rbp+57h+var_68]; string
0x18002ce7f  mov     [rbp+57h+var_60], r15
0x18002ce83  call    cs:__imp_WindowsGetStringLen
0x18002ce89  mov     r8d, 8
0x18002ce8f  cmp     eax, r8d
0x18002ce92  ja      short loc_18002CEA1
0x18002ce94  mov     rcx, [rbp+57h+var_68]; string
0x18002ce98  call    cs:__imp_WindowsGetStringLen
0x18002ce9e  mov     r8d, eax; unsigned int
0x18002cea1  lea     r9, [rbp+57h+var_60]; struct Windows::Internal::String *
0x18002cea5  lea     rcx, [rbp+57h+var_68]; this
0x18002cea9  call    ?Substring@String@Internal@Windows@@QEBAJIIPEAV123@@Z; Windows::Internal::String::Substring(uint,uint,Windows::Internal::String *)
0x18002ceae  test    eax, eax
0x18002ceb0  js      short loc_18002CF00
0x18002ceb2  mov     rcx, [rbp+57h+var_60]; string
0x18002ceb6  call    cs:__imp_WindowsGetStringLen
0x18002cebc  mov     rcx, [rbp+57h+var_60]; string
0x18002cec0  xor     edx, edx; length
0x18002cec2  mov     ebx, eax
0x18002cec4  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ceca  mov     r8d, 10h
0x18002ced0  mov     dword ptr [rbp+57h+var_50], r15d
0x18002ced4  mov     [rbp+57h+var_48], rax
0x18002ced8  lea     rdx, [rbp+57h+string]
0x18002cedc  lea     rcx, [rbp+57h+var_50]
0x18002cee0  mov     dword ptr [rbp+57h+string], r15d
0x18002cee4  lea     rax, [rax+rbx*2]
0x18002cee8  mov     [rbp+57h+var_40], rax
0x18002ceec  call    ?ReadUInt32@?$CStringReaderT@G@@QEAAHPEAII@Z; CStringReaderT<ushort>::ReadUInt32(uint *,uint)
0x18002cef1  test    eax, eax
0x18002cef3  jz      short loc_18002CF00
0x18002cef5  test    dword ptr [rbp+57h+string], 10000h
0x18002cefc  cmovnz  esi, r12d
0x18002cf00  lea     rcx, [rbp+57h+var_60]; this
0x18002cf04  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002cf09  lea     rcx, [rbp+57h+var_68]; this
0x18002cf0d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002cf12  mov     rax, [r14]
0x18002cf15  lea     rdx, [rbp+57h+var_58]
0x18002cf19  mov     rcx, r14
0x18002cf1c  mov     [rbp+57h+var_58], r15
0x18002cf20  mov     rax, [rax+58h]
0x18002cf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf29  test    eax, eax
0x18002cf2b  js      short loc_18002CF71
0x18002cf2d  mov     rcx, [rbp+57h+var_58]; string
0x18002cf31  call    cs:__imp_WindowsGetStringLen
0x18002cf37  mov     ebx, 13h
0x18002cf3c  cmp     eax, ebx
0x18002cf3e  jb      short loc_18002CF71
0x18002cf40  mov     rcx, [rbp+57h+var_58]; string
0x18002cf44  xor     edx, edx; length
0x18002cf46  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cf4c  mov     r9d, ebx; cchCount2
0x18002cf4f  mov     [rsp+0B0h+bIgnoreCase], r12d; bIgnoreCase
0x18002cf54  mov     rcx, rax; lpString1
0x18002cf57  lea     r8, aApplicationXDt; "application/x-dtcp1"
0x18002cf5e  mov     edx, ebx; cchCount1
0x18002cf60  call    cs:__imp_CompareStringOrdinal
0x18002cf66  cmp     eax, 2
0x18002cf69  movzx   esi, sil
0x18002cf6d  cmovz   esi, r12d
0x18002cf71  lea     rcx, [rbp+57h+var_58]; this
0x18002cf75  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002cf7a  lea     rcx, [rbp+57h+var_70]
0x18002cf7e  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002cf83  mov     al, sil
0x18002cf86  mov     rcx, [rbp+57h+var_30]
0x18002cf8a  xor     rcx, rsp; StackCookie
0x18002cf8d  call    __security_check_cookie
0x18002cf92  lea     r11, [rsp+0B0h+var_20]
0x18002cf9a  mov     rbx, [r11+38h]
0x18002cf9e  mov     rsi, [r11+40h]
0x18002cfa2  mov     rsp, r11
0x18002cfa5  pop     r15
0x18002cfa7  pop     r14
0x18002cfa9  pop     r12
0x18002cfab  pop     rdi
0x18002cfac  pop     rbp
0x18002cfad  retn
```
