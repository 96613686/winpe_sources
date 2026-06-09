# CWwanTranslator::_ProcessDMConfigProfileChange(_GUID const &,WWAN_DMPROFILE_UPDATE_INFO *,uint)

- ea: `0x18003e710`
- end: `0x18003ed24`
- name: `?_ProcessDMConfigProfileChange@CWwanTranslator@@AEAAJAEBU_GUID@@PEAUWWAN_DMPROFILE_UPDATE_INFO@@I@Z`
- size: `1556`
- prototype: `int __fastcall(CWwanTranslator *this, const struct _GUID *, struct WWAN_DMPROFILE_UPDATE_INFO *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x18003812c`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003994c`
- `0x18003e710`
- `0x180043de4`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `WwanPrfl!WwanProfileLoadXml` at `0x18003ec76`
- `WwanPrfl!WwanProfileLoadXml` at `0x18003ec76`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003ecfb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003ecfb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003ecd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003ecd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003e85a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003e85a`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18003ec49`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18003ec49`

## string_xrefs

- `0x18003e9d3`: `DMConfig profile %s deleted`
- `0x18003e7b8`: `CWwanTranslator::_ProcessDMConfigProfileChange`
- `0x18003eaed`: `DMConfig profile %s renamed`
- `0x18003ebb6`: `DMConfig profile %s created/updated`
- `0x18003e912`: `DMConfig unrecognized update!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CWwanTranslator::_ProcessDMConfigProfileChange(
        CWwanTranslator *this,
        const struct _GUID *a2,
        struct WWAN_DMPROFILE_UPDATE_INFO *a3,
        int a4)
{
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  unsigned int v11; // eax
  const struct _tlgProvider_t *v13; // rax
  int v14; // r8d
  int v15; // r9d
  unsigned __int16 **v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  int v18; // r8d
  int v19; // r9d
  _QWORD *v20; // rdx
  const struct _tlgProvider_t *v21; // rax
  int v22; // r8d
  int v23; // r9d
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  unsigned int DMConfigProfile; // eax
  __int64 v28; // rdx
  unsigned int v29[2]; // [rsp+20h] [rbp-E0h]
  unsigned int *v30; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h]
  unsigned int v33[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v34[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  struct WWAN_DMPROFILE_UPDATE_INFO *v36; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v41[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h]
  _QWORD v43[7]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v44; // [rsp+E8h] [rbp-18h]
  _BYTE v45[6320]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+19E8h] [rbp+18E8h]

  v36 = a3;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  std::vector<unsigned short>::resize(v31);
  std::vector<unsigned short>::resize(v41);
  StringCchPrintfW(v31[0], v31[1] - v31[0], L"Enter");
  v29[0] = 3195;
  StringCchPrintfW(v41[0], v41[1] - v41[0], L"%S(%d):%s", "CWwanTranslator::_ProcessDMConfigProfileChange");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(unsigned __int16 **)v33 = v41[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)&byte_1800762DF,
      v8,
      v9,
      (__int64)v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v41);
  std::vector<unsigned short>::~vector<unsigned short>(v31);
  if ( a4 == 536 )
  {
    v38 = 0;
    v39 = 0;
    v11 = WwanOpenHandle(1, 0, &v39, &v38);
    if ( v11 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xC7F,
               (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
               (const char *)v11,
               v29[0]);
    v41[0] = (unsigned __int16 *)&v38;
    LOBYTE(v41[1]) = 1;
    v40 = 0;
    memset_0(v45, 0, sizeof(v45));
    v37 = 0;
    if ( *(_DWORD *)v36 >= 2u )
    {
      if ( *(_DWORD *)v36 == 2 )
      {
        *(_OWORD *)v31 = 0;
        v32 = 0;
        *(_OWORD *)v34 = 0;
        v35 = 0;
        std::vector<unsigned short>::resize(v31);
        std::vector<unsigned short>::resize(v34);
        StringCchPrintfW(v31[0], v31[1] - v31[0], L"DMConfig profile %s renamed", (char *)v36 + 4);
        v29[0] = 3231;
        StringCchPrintfW(
          v34[0],
          v34[1] - v34[0],
          L"%S(%d):%s",
          "CWwanTranslator::_ProcessDMConfigProfileChange",
          *(_QWORD *)v29,
          v31[0]);
        v21 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v21 > 4u )
        {
          *(unsigned __int16 **)v33 = v34[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v21,
            (unsigned int)&byte_1800762BF,
            v22,
            v23,
            (__int64)v33);
        }
        std::vector<unsigned short>::~vector<unsigned short>(v34);
        v16 = v31;
      }
      else
      {
        if ( *(_DWORD *)v36 == 3 )
        {
          *(_OWORD *)v31 = 0;
          v32 = 0;
          *(_OWORD *)v34 = 0;
          v35 = 0;
          std::vector<unsigned short>::resize(v31);
          std::vector<unsigned short>::resize(v34);
          StringCchPrintfW(v31[0], v31[1] - v31[0], L"DMConfig profile %s deleted", (char *)v36 + 4);
          v29[0] = 3208;
          StringCchPrintfW(
            v34[0],
            v34[1] - v34[0],
            L"%S(%d):%s",
            "CWwanTranslator::_ProcessDMConfigProfileChange",
            *(_QWORD *)v29,
            v31[0]);
          v17 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v17 > 4u )
          {
            *(unsigned __int16 **)v33 = v34[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v17,
              (unsigned int)word_180076302,
              v18,
              v19,
              (__int64)v33);
          }
          std::vector<unsigned short>::~vector<unsigned short>(v34);
          std::vector<unsigned short>::~vector<unsigned short>(v31);
          v43[0] = off_18005EB58;
          v43[1] = this;
          v43[2] = a2;
          v43[3] = &v36;
          v44 = v43;
          CWwanTranslator::SafelyNotify(this, v43);
          if ( v44 )
          {
            v20 = v43;
            LOBYTE(v20) = v44 != v43;
            (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v44 + 32LL))(v44, v20);
          }
          goto LABEL_33;
        }
        *(_OWORD *)v34 = 0;
        v35 = 0;
        *(_OWORD *)v31 = 0;
        v32 = 0;
        std::vector<unsigned short>::resize(v34);
        std::vector<unsigned short>::resize(v31);
        StringCchPrintfW(v34[0], v34[1] - v34[0], L"DMConfig unrecognized update!");
        v29[0] = 3235;
        StringCchPrintfW(
          v31[0],
          v31[1] - v31[0],
          L"%S(%d):%s",
          "CWwanTranslator::_ProcessDMConfigProfileChange",
          *(_QWORD *)v29,
          v34[0]);
        v13 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v13 > 2u )
        {
          *(unsigned __int16 **)v33 = v31[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v13,
            (unsigned int)byte_18007625B,
            v14,
            v15,
            (__int64)v33);
        }
        std::vector<unsigned short>::~vector<unsigned short>(v31);
        v16 = v34;
      }
      std::vector<unsigned short>::~vector<unsigned short>(v16);
LABEL_33:
      v10 = 0;
      goto LABEL_34;
    }
    *(_OWORD *)v31 = 0;
    v32 = 0;
    *(_OWORD *)v34 = 0;
    v35 = 0;
    std::vector<unsigned short>::resize(v31);
    std::vector<unsigned short>::resize(v34);
    StringCchPrintfW(v31[0], v31[1] - v31[0], L"DMConfig profile %s created/updated", (char *)v36 + 4);
    LODWORD(v30) = 3216;
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"%S(%d):%s", "CWwanTranslator::_ProcessDMConfigProfileChange");
    v24 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v24 > 4u )
    {
      *(unsigned __int16 **)v33 = v34[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v24,
        (unsigned int)&byte_18007629F,
        v25,
        v26,
        (__int64)v33);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v34);
    std::vector<unsigned short>::~vector<unsigned short>(v31);
    DMConfigProfile = WwanGetDMConfigProfile(v38, a2, (char *)v36 + 4, &v40);
    if ( DMConfigProfile )
    {
      v28 = 3218;
    }
    else
    {
      v30 = &v37;
      DMConfigProfile = WwanProfileLoadXml(v45, v40, 0, 0);
      if ( !DMConfigProfile )
      {
        if ( !v37 )
        {
          if ( v40 )
            WwanFreeMemory();
          LOBYTE(v30) = 1;
          CWwanTranslator::_ProcessWwanProfile(this, a2, 3, v45, v30);
          goto LABEL_33;
        }
        v10 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC95,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
          (const char *)0x80004005LL,
          (int)&v37);
LABEL_34:
        WwanCloseHandle(v38, 0);
        return v10;
      }
      v28 = 3219;
    }
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v28,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)DMConfigProfile,
            (unsigned int)v30);
    goto LABEL_34;
  }
  v10 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC7C,
    (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
    (const char *)0x80070057LL,
    v29[0]);
  return v10;
}

```

## disassembly

```asm
0x18003e710  push    rbp
0x18003e712  push    rbx
0x18003e713  push    rsi
0x18003e714  push    rdi
0x18003e715  push    r12
0x18003e717  push    r14
0x18003e719  push    r15
0x18003e71b  lea     rbp, [rsp-18B0h]
0x18003e723  mov     eax, 19B0h
0x18003e728  call    _alloca_probe
0x18003e72d  sub     rsp, rax
0x18003e730  mov     rax, cs:__security_cookie
0x18003e737  xor     rax, rsp
0x18003e73a  mov     [rbp+18E0h+var_40], rax
0x18003e741  mov     esi, r9d
0x18003e744  mov     rdi, rdx
0x18003e747  mov     rbx, rcx
0x18003e74a  mov     [rsp+19E0h+var_1978], r8
0x18003e74f  xorps   xmm0, xmm0
0x18003e752  movdqu  xmmword ptr [rsp+19E0h+var_19B0], xmm0
0x18003e758  xor     r14d, r14d
0x18003e75b  mov     [rsp+19E0h+var_19A0], r14
0x18003e760  movdqu  xmmword ptr [rbp+18E0h+var_1950], xmm0
0x18003e765  mov     [rbp+18E0h+var_1940], r14
0x18003e769  lea     rcx, [rsp+19E0h+var_19B0]
0x18003e76e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e773  lea     rcx, [rbp+18E0h+var_1950]
0x18003e777  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e77c  mov     rdx, [rsp+19E0h+var_19B0+8]
0x18003e781  mov     rcx, [rsp+19E0h+var_19B0]; unsigned __int16 *
0x18003e786  sub     rdx, rcx
0x18003e789  sar     rdx, 1; unsigned __int64
0x18003e78c  lea     r8, aEnter; "Enter"
0x18003e793  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e798  mov     rdx, [rbp+18E0h+var_1950+8]
0x18003e79c  mov     rcx, [rbp+18E0h+var_1950]; unsigned __int16 *
0x18003e7a0  sub     rdx, rcx
0x18003e7a3  sar     rdx, 1; unsigned __int64
0x18003e7a6  mov     rax, [rsp+19E0h+var_19B0]
0x18003e7ab  mov     [rsp+19E0h+var_19B8], rax
0x18003e7b0  mov     [rsp+19E0h+var_19C0], 0C7Bh
0x18003e7b8  lea     r15, aCwwantranslato_1; "CWwanTranslator::_ProcessDMConfigProfil"...
0x18003e7bf  mov     r9, r15
0x18003e7c2  lea     r12, aSDS; "%S(%d):%s"
0x18003e7c9  mov     r8, r12; unsigned __int16 *
0x18003e7cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e7d1  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003e7d6  mov     ecx, [rax]
0x18003e7d8  cmp     ecx, 5
0x18003e7db  jbe     short loc_18003E800
0x18003e7dd  mov     rcx, [rbp+18E0h+var_1950]
0x18003e7e1  mov     qword ptr [rsp+19E0h+var_1998], rcx
0x18003e7e6  lea     rcx, [rsp+19E0h+var_1998]
0x18003e7eb  mov     qword ptr [rsp+19E0h+var_19C0], rcx; unsigned int
0x18003e7f0  lea     rdx, byte_1800762DF
0x18003e7f7  mov     rcx, rax
0x18003e7fa  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003e7ff  nop
0x18003e800  lea     rcx, [rbp+18E0h+var_1950]
0x18003e804  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e809  nop
0x18003e80a  lea     rcx, [rsp+19E0h+var_19B0]
0x18003e80f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e814  cmp     esi, 218h
0x18003e81a  jz      short loc_18003E841
0x18003e81c  mov     rcx, [rbp+18E8h]; this
0x18003e823  mov     ebx, 80070057h
0x18003e828  mov     r9d, ebx; char *
0x18003e82b  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003e832  mov     edx, 0C7Ch; void *
0x18003e837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e83c  jmp     loc_18003ED01
0x18003e841  mov     [rsp+19E0h+var_1968], r14
0x18003e846  mov     [rbp+18E0h+var_1960], r14d
0x18003e84a  lea     r9, [rsp+19E0h+var_1968]
0x18003e84f  lea     r8, [rbp+18E0h+var_1960]
0x18003e853  xor     edx, edx
0x18003e855  lea     esi, [rdx+1]
0x18003e858  mov     ecx, esi
0x18003e85a  call    cs:__imp_WwanOpenHandle
0x18003e860  test    eax, eax
0x18003e862  jz      short loc_18003E884
0x18003e864  mov     rcx, [rbp+18E8h]; this
0x18003e86b  mov     r9d, eax; char *
0x18003e86e  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003e875  mov     edx, 0C7Fh; void *
0x18003e87a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e87f  jmp     loc_18003ED03
0x18003e884  lea     rax, [rsp+19E0h+var_1968]
0x18003e889  mov     [rbp+18E0h+var_1950], rax
0x18003e88d  mov     byte ptr [rbp+18E0h+var_1950+8], sil
0x18003e891  mov     [rbp+18E0h+var_1958], r14
0x18003e895  xor     edx, edx; Val
0x18003e897  mov     r8d, 18B0h; Size
0x18003e89d  lea     rcx, [rbp+18E0h+var_18F0]; void *
0x18003e8a1  call    memset_0
0x18003e8a6  mov     [rsp+19E0h+var_1970], r14d
0x18003e8ab  mov     rcx, [rsp+19E0h+var_1978]
0x18003e8b0  mov     edx, [rcx]
0x18003e8b2  test    edx, edx
0x18003e8b4  jz      loc_18003EB70
0x18003e8ba  sub     edx, 1
0x18003e8bd  jz      loc_18003EB70
0x18003e8c3  sub     edx, 1
0x18003e8c6  xorps   xmm0, xmm0
0x18003e8c9  jz      loc_18003EAAA
0x18003e8cf  cmp     edx, 1
0x18003e8d2  jz      loc_18003E990
0x18003e8d8  movdqu  xmmword ptr [rsp+19E0h+var_1990], xmm0
0x18003e8de  mov     [rsp+19E0h+var_1980], r14
0x18003e8e3  movdqu  xmmword ptr [rsp+19E0h+var_19B0], xmm0
0x18003e8e9  mov     [rsp+19E0h+var_19A0], r14
0x18003e8ee  lea     rcx, [rsp+19E0h+var_1990]
0x18003e8f3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e8f8  lea     rcx, [rsp+19E0h+var_19B0]
0x18003e8fd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e902  mov     rdx, [rsp+19E0h+var_1990+8]
0x18003e907  mov     rcx, [rsp+19E0h+var_1990]; unsigned __int16 *
0x18003e90c  sub     rdx, rcx
0x18003e90f  sar     rdx, 1; unsigned __int64
0x18003e912  lea     r8, aDmconfigUnreco; "DMConfig unrecognized update!"
0x18003e919  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e91e  mov     rdx, [rsp+19E0h+var_19B0+8]
0x18003e923  mov     rcx, [rsp+19E0h+var_19B0]; unsigned __int16 *
0x18003e928  sub     rdx, rcx
0x18003e92b  sar     rdx, 1; unsigned __int64
0x18003e92e  mov     rax, [rsp+19E0h+var_1990]
0x18003e933  mov     [rsp+19E0h+var_19B8], rax
0x18003e938  mov     [rsp+19E0h+var_19C0], 0CA3h
0x18003e940  mov     r9, r15
0x18003e943  mov     r8, r12; unsigned __int16 *
0x18003e946  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e94b  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003e950  mov     ecx, [rax]
0x18003e952  cmp     ecx, 2
0x18003e955  jbe     short loc_18003E97B
0x18003e957  mov     rcx, [rsp+19E0h+var_19B0]
0x18003e95c  mov     qword ptr [rsp+19E0h+var_1998], rcx
0x18003e961  lea     rcx, [rsp+19E0h+var_1998]
0x18003e966  mov     qword ptr [rsp+19E0h+var_19C0], rcx
0x18003e96b  lea     rdx, byte_18007625B
0x18003e972  mov     rcx, rax
0x18003e975  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003e97a  nop
0x18003e97b  lea     rcx, [rsp+19E0h+var_19B0]
0x18003e980  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e985  nop
0x18003e986  lea     rcx, [rsp+19E0h+var_1990]
0x18003e98b  jmp     loc_18003EB66
0x18003e990  movdqu  xmmword ptr [rsp+19E0h+var_19B0], xmm0
0x18003e996  mov     [rsp+19E0h+var_19A0], r14
0x18003e99b  movdqu  xmmword ptr [rsp+19E0h+var_1990], xmm0
0x18003e9a1  mov     [rsp+19E0h+var_1980], r14
0x18003e9a6  lea     rcx, [rsp+19E0h+var_19B0]
0x18003e9ab  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e9b0  lea     rcx, [rsp+19E0h+var_1990]
0x18003e9b5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e9ba  mov     r9, [rsp+19E0h+var_1978]
0x18003e9bf  add     r9, 4
0x18003e9c3  mov     rdx, [rsp+19E0h+var_19B0+8]
0x18003e9c8  mov     rcx, [rsp+19E0h+var_19B0]; unsigned __int16 *
0x18003e9cd  sub     rdx, rcx
0x18003e9d0  sar     rdx, 1; unsigned __int64
0x18003e9d3  lea     r8, aDmconfigProfil_0; "DMConfig profile %s deleted"
0x18003e9da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e9df  mov     rdx, [rsp+19E0h+var_1990+8]
0x18003e9e4  mov     rcx, [rsp+19E0h+var_1990]; unsigned __int16 *
0x18003e9e9  sub     rdx, rcx
0x18003e9ec  sar     rdx, 1; unsigned __int64
0x18003e9ef  mov     rax, [rsp+19E0h+var_19B0]
0x18003e9f4  mov     [rsp+19E0h+var_19B8], rax
0x18003e9f9  mov     [rsp+19E0h+var_19C0], 0C88h
0x18003ea01  mov     r9, r15
0x18003ea04  mov     r8, r12; unsigned __int16 *
0x18003ea07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ea0c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003ea11  mov     ecx, [rax]
0x18003ea13  cmp     ecx, 4
0x18003ea16  jbe     short loc_18003EA3C
0x18003ea18  mov     rcx, [rsp+19E0h+var_1990]
0x18003ea1d  mov     qword ptr [rsp+19E0h+var_1998], rcx
0x18003ea22  lea     rcx, [rsp+19E0h+var_1998]
0x18003ea27  mov     qword ptr [rsp+19E0h+var_19C0], rcx
0x18003ea2c  lea     rdx, word_180076302
0x18003ea33  mov     rcx, rax
0x18003ea36  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003ea3b  nop
0x18003ea3c  lea     rcx, [rsp+19E0h+var_1990]
0x18003ea41  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003ea46  nop
0x18003ea47  lea     rcx, [rsp+19E0h+var_19B0]
0x18003ea4c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003ea51  lea     rax, off_18005EB58
0x18003ea58  mov     [rbp+18E0h+var_1930], rax
0x18003ea5c  mov     [rbp+18E0h+var_1928], rbx
0x18003ea60  mov     [rbp+18E0h+var_1920], rdi
0x18003ea64  lea     rax, [rsp+19E0h+var_1978]
0x18003ea69  mov     [rbp+18E0h+var_1918], rax
0x18003ea6d  lea     rax, [rbp+18E0h+var_1930]
0x18003ea71  mov     [rbp+18E0h+var_18F8], rax
0x18003ea75  lea     rdx, [rbp+18E0h+var_1930]
0x18003ea79  mov     rcx, rbx
0x18003ea7c  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x18003ea81  nop
0x18003ea82  mov     rcx, [rbp+18E0h+var_18F8]
0x18003ea86  test    rcx, rcx
0x18003ea89  jz      loc_18003ECF1
0x18003ea8f  mov     rax, [rcx]
0x18003ea92  lea     rdx, [rbp+18E0h+var_1930]
0x18003ea96  cmp     rcx, rdx
0x18003ea99  setnz   dl
0x18003ea9c  mov     rax, [rax+20h]
0x18003eaa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaa5  jmp     loc_18003ECF1
0x18003eaaa  movdqu  xmmword ptr [rsp+19E0h+var_19B0], xmm0
0x18003eab0  mov     [rsp+19E0h+var_19A0], r14
0x18003eab5  movdqu  xmmword ptr [rsp+19E0h+var_1990], xmm0
0x18003eabb  mov     [rsp+19E0h+var_1980], r14
0x18003eac0  lea     rcx, [rsp+19E0h+var_19B0]
0x18003eac5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003eaca  lea     rcx, [rsp+19E0h+var_1990]
0x18003eacf  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003ead4  mov     r9, [rsp+19E0h+var_1978]
0x18003ead9  add     r9, 4
0x18003eadd  mov     rdx, [rsp+19E0h+var_19B0+8]
0x18003eae2  mov     rcx, [rsp+19E0h+var_19B0]; unsigned __int16 *
0x18003eae7  sub     rdx, rcx
0x18003eaea  sar     rdx, 1; unsigned __int64
0x18003eaed  lea     r8, aDmconfigProfil_1; "DMConfig profile %s renamed"
0x18003eaf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003eaf9  mov     rdx, [rsp+19E0h+var_1990+8]
0x18003eafe  mov     rcx, [rsp+19E0h+var_1990]; unsigned __int16 *
0x18003eb03  sub     rdx, rcx
0x18003eb06  sar     rdx, 1; unsigned __int64
0x18003eb09  mov     rax, [rsp+19E0h+var_19B0]
0x18003eb0e  mov     [rsp+19E0h+var_19B8], rax
0x18003eb13  mov     [rsp+19E0h+var_19C0], 0C9Fh
0x18003eb1b  mov     r9, r15
0x18003eb1e  mov     r8, r12; unsigned __int16 *
0x18003eb21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003eb26  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003eb2b  mov     ecx, [rax]
0x18003eb2d  cmp     ecx, 4
0x18003eb30  jbe     short loc_18003EB56
0x18003eb32  mov     rcx, [rsp+19E0h+var_1990]
0x18003eb37  mov     qword ptr [rsp+19E0h+var_1998], rcx
0x18003eb3c  lea     rcx, [rsp+19E0h+var_1998]
0x18003eb41  mov     qword ptr [rsp+19E0h+var_19C0], rcx
0x18003eb46  lea     rdx, byte_1800762BF
0x18003eb4d  mov     rcx, rax
0x18003eb50  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003eb55  nop
0x18003eb56  lea     rcx, [rsp+19E0h+var_1990]
0x18003eb5b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003eb60  nop
0x18003eb61  lea     rcx, [rsp+19E0h+var_19B0]
0x18003eb66  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003eb6b  jmp     loc_18003ECF1
0x18003eb70  xorps   xmm0, xmm0
0x18003eb73  movdqu  xmmword ptr [rsp+19E0h+var_19B0], xmm0
0x18003eb79  mov     [rsp+19E0h+var_19A0], r14
0x18003eb7e  movdqu  xmmword ptr [rsp+19E0h+var_1990], xmm0
0x18003eb84  mov     [rsp+19E0h+var_1980], r14
0x18003eb89  lea     rcx, [rsp+19E0h+var_19B0]
0x18003eb8e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003eb93  lea     rcx, [rsp+19E0h+var_1990]
0x18003eb98  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003eb9d  mov     r9, [rsp+19E0h+var_1978]
0x18003eba2  add     r9, 4
0x18003eba6  mov     rdx, [rsp+19E0h+var_19B0+8]
0x18003ebab  mov     rcx, [rsp+19E0h+var_19B0]; unsigned __int16 *
0x18003ebb0  sub     rdx, rcx
0x18003ebb3  sar     rdx, 1; unsigned __int64
0x18003ebb6  lea     r8, aDmconfigProfil; "DMConfig profile %s created/updated"
0x18003ebbd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ebc2  mov     rdx, [rsp+19E0h+var_1990+8]
0x18003ebc7  mov     rcx, [rsp+19E0h+var_1990]; unsigned __int16 *
0x18003ebcc  sub     rdx, rcx
0x18003ebcf  sar     rdx, 1; unsigned __int64
0x18003ebd2  mov     rax, [rsp+19E0h+var_19B0]
0x18003ebd7  mov     [rsp+19E0h+var_19B8], rax
0x18003ebdc  mov     [rsp+19E0h+var_19C0], 0C90h
0x18003ebe4  mov     r9, r15
0x18003ebe7  mov     r8, r12; unsigned __int16 *
0x18003ebea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ebef  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003ebf4  mov     ecx, [rax]
0x18003ebf6  cmp     ecx, 4
0x18003ebf9  jbe     short loc_18003EC1F
0x18003ebfb  mov     rcx, [rsp+19E0h+var_1990]
0x18003ec00  mov     qword ptr [rsp+19E0h+var_1998], rcx
0x18003ec05  lea     rcx, [rsp+19E0h+var_1998]
0x18003ec0a  mov     qword ptr [rsp+19E0h+var_19C0], rcx
0x18003ec0f  lea     rdx, byte_18007629F
0x18003ec16  mov     rcx, rax
0x18003ec19  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003ec1e  nop
0x18003ec1f  lea     rcx, [rsp+19E0h+var_1990]
0x18003ec24  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003ec29  nop
  ... truncated ...
```
