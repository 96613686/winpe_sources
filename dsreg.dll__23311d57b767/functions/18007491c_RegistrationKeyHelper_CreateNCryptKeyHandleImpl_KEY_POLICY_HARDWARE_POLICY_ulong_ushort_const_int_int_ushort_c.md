# RegistrationKeyHelper::CreateNCryptKeyHandleImpl(_KEY_POLICY,_HARDWARE_POLICY,ulong,ushort const *,int,int,ushort const *,ushort const *,unsigned __int64 *,ushort * *,int *)

- ea: `0x18007491c`
- end: `0x180074c52`
- name: `?CreateNCryptKeyHandleImpl@RegistrationKeyHelper@@CAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@KPEBGHH22PEA_KPEAPEAGPEAH@Z`
- size: `822`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x1800747bc`

## callees

- `0x1800012a4`
- `0x180001e6c`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x1800204f0`
- `0x180043ef8`
- `0x180044300`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x18007491c`
- `0x1800750c0`
- `0x180076ad8`
- `0x180076b8c`
- `0x180076e10`
- `0x18008b8a4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180074aea`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180074aea`
- `ncrypt!NCryptFreeObject` at `0x180074bb0`
- `ncrypt!NCryptFreeObject` at `0x180074bc2`
- `ncrypt!NCryptFreeObject` at `0x180074bb0`
- `ncrypt!NCryptFreeObject` at `0x180074bc2`

## string_xrefs

- `0x1800749da`: `RegistrationKeyHelper::TryNCryptOpenStorageProvider`
- `0x180074996`: `RegistrationKeyHelper::CreateNCryptKeyHandleImpl`
- `0x1800749e1`: `RegistrationKeyHelper::CreateNCryptKeyHandleImpl`
- `0x180074a1d`: `RegistrationKeyHelper::CreateNCryptKeyHandleImpl`
- `0x180074be4`: `RegistrationKeyHelper::CreateNCryptKeyHandleImpl`
- `0x180074c16`: `RegistrationKeyHelper::CreateNCryptKeyHandleImpl`
- `0x180074b88`: `CreateNewKey`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::CreateNCryptKeyHandleImpl(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int64 *a9,
        const WCHAR **a10,
        _DWORD *a11)
{
  BOOL v11; // r15d
  unsigned int v12; // ebx
  int v13; // eax
  int NewKey; // ebx
  WCHAR *v15; // rdi
  int IsTpmProvider; // eax
  __int64 v17; // r9
  const wchar_t *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r9
  const WCHAR *v21; // rax
  void *Block; // [rsp+40h] [rbp-69h] BYREF
  int v24; // [rsp+48h] [rbp-61h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-51h]
  unsigned __int16 *v27; // [rsp+60h] [rbp-49h]
  unsigned __int16 *v28; // [rsp+68h] [rbp-41h]
  const WCHAR *v29; // [rsp+70h] [rbp-39h] BYREF
  __int64 v30; // [rsp+78h] [rbp-31h] BYREF
  int v31; // [rsp+80h] [rbp-29h] BYREF
  char v32; // [rsp+84h] [rbp-25h]
  _BYTE v33[16]; // [rsp+88h] [rbp-21h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-11h] BYREF

  v11 = a1 != 2;
  v27 = a7;
  v12 = a1;
  v28 = a4;
  v26 = a8;
  hObject = 0;
  if ( a11 )
    *a11 = 0;
  if ( RegistrationKeyHelper::GetTpmVersion() == 1 && v12 == 1 )
  {
    v12 = 3;
    Logger::TraceInformation(
      L"%s: TPM 1.2 hardware is present. Changing key policy to software key.",
      L"RegistrationKeyHelper::CreateNCryptKeyHandleImpl");
  }
  while ( 1 )
  {
    *a10 = 0;
    *a9 = 0;
    Block = 0;
    v24 = 0;
    hObject = 0;
    v13 = RegistrationKeyHelper::TryNCryptOpenStorageProvider(v12, &hObject, &Block);
    NewKey = v13;
    if ( v13 >= 0 )
    {
      v15 = (WCHAR *)Block;
      IsTpmProvider = RegistrationKeyHelper::IsTpmProvider((const unsigned __int16 *)Block, &v24);
      NewKey = IsTpmProvider;
      if ( IsTpmProvider >= 0 )
      {
        v31 = 0;
        v32 = 0;
        _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v31);
        if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
        {
          Block = (void *)0x1000000;
          if ( v32 )
            _tlgGuidIsZero(&ActivityId);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            (__int64)&dword_18013D150,
            (__int64)word_18012A37A);
        }
        NewKey = RegistrationKeyHelper::CreateNewKey(hObject, v19, v28, a5, a6, v27, v26, a9);
        if ( v32 )
          EventActivityIdControl(4u, &ActivityId);
        v31 = 2;
        if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
        {
          if ( v15 )
          {
            v21 = v15;
          }
          else
          {
            v21 = &cchOriginalDestLength;
            if ( *a10 )
              v21 = *a10;
          }
          v29 = v21;
          LODWORD(Block) = NewKey;
          v30 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (__int64)&dword_18013D150,
            (__int64)word_18012A2C2,
            (__int64)v33,
            v20,
            (__int64)&v30,
            (__int64)&Block,
            &v29);
        }
        _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v31);
        if ( NewKey >= 0 )
        {
          *a10 = v15;
          v15 = 0;
          goto LABEL_28;
        }
        v17 = (unsigned int)NewKey;
        v18 = L"CreateNewKey";
      }
      else
      {
        v17 = (unsigned int)IsTpmProvider;
        v18 = L"RegistrationKeyHelper::IsTpmProvider";
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationKeyHelper::CreateNCryptKeyHandleImpl",
        v18,
        v17);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationKeyHelper::CreateNCryptKeyHandleImpl",
        L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
        (unsigned int)v13);
      v15 = (WCHAR *)Block;
    }
LABEL_28:
    operator delete(v15);
    if ( NewKey < 0 && *a9 )
    {
      NCryptFreeObject(*a9);
      *a9 = 0;
    }
    if ( hObject )
    {
      NCryptFreeObject(hObject);
      hObject = 0;
    }
    if ( !v11 || !v24 || !(unsigned int)IsTpmError(NewKey) )
      break;
    Logger::TraceWarning(
      (wchar_t *)L"%s: Error 0x%08X is detected as TPM-related. Falling back to software key provider",
      L"RegistrationKeyHelper::CreateNCryptKeyHandleImpl",
      (unsigned int)NewKey);
    v12 = 3;
    v11 = 0;
    if ( a11 )
      *a11 = 1;
  }
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationKeyHelper::CreateNCryptKeyHandleImpl",
    (unsigned int)NewKey);
  return (unsigned int)NewKey;
}

```

## disassembly

```asm
0x18007491c  mov     [rsp-8+arg_8], rbx
0x180074921  push    rbp
0x180074922  push    rsi
0x180074923  push    rdi
0x180074924  push    r12
0x180074926  push    r13
0x180074928  push    r14
0x18007492a  push    r15
0x18007492c  lea     rbp, [rsp-7]
0x180074931  sub     rsp, 0B0h
0x180074938  mov     rax, cs:__security_cookie
0x18007493f  xor     rax, rsp
0x180074942  mov     [rbp+37h+var_38], rax
0x180074946  mov     rax, [rbp+37h+arg_30]
0x18007494a  xor     edi, edi
0x18007494c  mov     rsi, [rbp+37h+arg_50]
0x180074953  cmp     ecx, 2
0x180074956  mov     r14, [rbp+37h+arg_40]
0x18007495d  mov     r15d, edi
0x180074960  mov     r12, [rbp+37h+arg_48]
0x180074967  setnz   r15b
0x18007496b  mov     [rbp+37h+var_80], rax
0x18007496f  mov     ebx, ecx
0x180074971  mov     rax, [rbp+37h+arg_38]
0x180074975  mov     [rbp+37h+var_78], r9
0x180074979  mov     [rbp+37h+var_88], rax
0x18007497d  mov     [rbp+37h+hObject], rdi
0x180074981  test    rsi, rsi
0x180074984  jz      short loc_180074988
0x180074986  mov     [rsi], edi
0x180074988  call    ?GetTpmVersion@RegistrationKeyHelper@@SAIXZ; RegistrationKeyHelper::GetTpmVersion(void)
0x18007498d  cmp     eax, 1
0x180074990  jnz     short loc_1800749AC
0x180074992  cmp     ebx, eax
0x180074994  jnz     short loc_1800749AC
0x180074996  lea     rdx, aRegistrationke_13; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x18007499d  lea     rcx, aSTpm12Hardware; "%s: TPM 1.2 hardware is present. Changi"...
0x1800749a4  lea     ebx, [rax+2]
0x1800749a7  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800749ac  mov     r13d, [rbp+37h+arg_28]
0x1800749b0  mov     [r12], rdi
0x1800749b4  lea     r8, [rbp+37h+Block]
0x1800749b8  lea     rdx, [rbp+37h+hObject]
0x1800749bc  mov     [r14], rdi
0x1800749bf  mov     ecx, ebx
0x1800749c1  mov     [rbp+37h+Block], rdi
0x1800749c5  mov     [rbp+37h+var_98], edi
0x1800749c8  mov     [rbp+37h+hObject], rdi
0x1800749cc  call    ?TryNCryptOpenStorageProvider@RegistrationKeyHelper@@CAJW4_KEY_POLICY@@PEA_KPEAPEAG@Z; RegistrationKeyHelper::TryNCryptOpenStorageProvider(_KEY_POLICY,unsigned __int64 *,ushort * *)
0x1800749d1  mov     ebx, eax
0x1800749d3  test    eax, eax
0x1800749d5  jns     short loc_1800749FD
0x1800749d7  mov     r9d, eax
0x1800749da  lea     r8, aRegistrationke; "RegistrationKeyHelper::TryNCryptOpenSto"...
0x1800749e1  lea     rdx, aRegistrationke_13; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x1800749e8  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800749ef  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800749f4  mov     rdi, [rbp+37h+Block]
0x1800749f8  jmp     loc_180074B9A
0x1800749fd  mov     rdi, [rbp+37h+Block]
0x180074a01  lea     rdx, [rbp+37h+var_98]; int *
0x180074a05  mov     rcx, rdi; unsigned __int16 *
0x180074a08  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x180074a0d  mov     ebx, eax
0x180074a0f  test    eax, eax
0x180074a11  jns     short loc_180074A35
0x180074a13  mov     r9d, eax
0x180074a16  lea     r8, aRegistrationke_3; "RegistrationKeyHelper::IsTpmProvider"
0x180074a1d  lea     rdx, aRegistrationke_13; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074a24  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180074a2b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074a30  jmp     loc_180074B9A
0x180074a35  xor     ebx, ebx
0x180074a37  lea     rcx, [rbp+37h+var_60]
0x180074a3b  mov     [rbp+37h+var_60], ebx
0x180074a3e  mov     [rbp+37h+var_5C], bl
0x180074a41  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180074a46  mov     eax, cs:dword_18013D150
0x180074a4c  cmp     eax, 5
0x180074a4f  jbe     short loc_180074AAC
0x180074a51  mov     rdx, 400000000000h
0x180074a5b  lea     rcx, dword_18013D150
0x180074a62  call    _tlgKeywordOn
0x180074a67  test    al, al
0x180074a69  jz      short loc_180074AAC
0x180074a6b  mov     [rbp+37h+Block], 1000000h
0x180074a73  cmp     [rbp+37h+var_5C], bl
0x180074a76  jz      short loc_180074A89
0x180074a78  lea     rcx, [rbp+37h+ActivityId]; struct _GUID *
0x180074a7c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180074a81  lea     r9, [rbp+37h+ActivityId]
0x180074a85  test    al, al
0x180074a87  jz      short loc_180074A8C
0x180074a89  mov     r9, rbx
0x180074a8c  lea     rax, [rbp+37h+Block]
0x180074a90  lea     r8, [rbp+37h+var_58]
0x180074a94  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180074a99  lea     rdx, word_18012A37A
0x180074aa0  lea     rcx, dword_18013D150
0x180074aa7  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180074aac  mov     rax, [rbp+37h+var_88]
0x180074ab0  mov     r9d, [rbp+37h+arg_20]; int
0x180074ab4  mov     r8, [rbp+37h+var_78]; unsigned __int16 *
0x180074ab8  mov     rcx, [rbp+37h+hObject]; unsigned __int64
0x180074abc  mov     [rsp+0E0h+var_A8], r14; unsigned __int64 *
0x180074ac1  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 *
0x180074ac6  mov     rax, [rbp+37h+var_80]
0x180074aca  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180074acf  mov     [rsp+0E0h+var_C0], r13d; int
0x180074ad4  call    ?CreateNewKey@RegistrationKeyHelper@@CAJ_KKPEBGHH11PEA_K@Z; RegistrationKeyHelper::CreateNewKey(unsigned __int64,ulong,ushort const *,int,int,ushort const *,ushort const *,unsigned __int64 *)
0x180074ad9  cmp     [rbp+37h+var_5C], 0
0x180074add  mov     ebx, eax
0x180074adf  jz      short loc_180074AF0
0x180074ae1  lea     rdx, [rbp+37h+ActivityId]; ActivityId
0x180074ae5  mov     ecx, 4; ControlCode
0x180074aea  call    cs:__imp_EventActivityIdControl
0x180074af0  mov     eax, cs:dword_18013D150
0x180074af6  mov     [rbp+37h+var_60], 2
0x180074afd  cmp     eax, 5
0x180074b00  jbe     short loc_180074B78
0x180074b02  mov     rdx, 400000000000h
0x180074b0c  lea     rcx, dword_18013D150
0x180074b13  call    _tlgKeywordOn
0x180074b18  test    al, al
0x180074b1a  jz      short loc_180074B78
0x180074b1c  test    rdi, rdi
0x180074b1f  jz      short loc_180074B26
0x180074b21  mov     rax, rdi
0x180074b24  jmp     short loc_180074B37
0x180074b26  cmp     qword ptr [r12], 0
0x180074b2b  lea     rax, cchOriginalDestLength
0x180074b32  cmovnz  rax, [r12]
0x180074b37  mov     [rbp+37h+var_70], rax
0x180074b3b  lea     r8, [rbp+37h+var_58]
0x180074b3f  lea     rax, [rbp+37h+var_70]
0x180074b43  mov     dword ptr [rbp+37h+Block], ebx
0x180074b46  mov     [rsp+0E0h+var_B0], rax
0x180074b4b  lea     rdx, word_18012A2C2
0x180074b52  lea     rax, [rbp+37h+Block]
0x180074b56  mov     [rbp+37h+var_68], 1000000h
0x180074b5e  mov     [rsp+0E0h+var_B8], rax
0x180074b63  lea     rcx, dword_18013D150
0x180074b6a  lea     rax, [rbp+37h+var_68]
0x180074b6e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180074b73  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180074b78  lea     rcx, [rbp+37h+var_60]
0x180074b7c  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180074b81  test    ebx, ebx
0x180074b83  jns     short loc_180074B94
0x180074b85  mov     r9d, ebx
0x180074b88  lea     r8, aCreatenewkey; "CreateNewKey"
0x180074b8f  jmp     loc_180074A1D
0x180074b94  mov     [r12], rdi
0x180074b98  xor     edi, edi
0x180074b9a  mov     rcx, rdi; Block
0x180074b9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180074ba2  xor     edi, edi
0x180074ba4  test    ebx, ebx
0x180074ba6  jns     short loc_180074BB9
0x180074ba8  mov     rcx, [r14]; hObject
0x180074bab  test    rcx, rcx
0x180074bae  jz      short loc_180074BB9
0x180074bb0  call    cs:__imp_NCryptFreeObject
0x180074bb6  mov     [r14], rdi
0x180074bb9  mov     rcx, [rbp+37h+hObject]; hObject
0x180074bbd  test    rcx, rcx
0x180074bc0  jz      short loc_180074BCC
0x180074bc2  call    cs:__imp_NCryptFreeObject
0x180074bc8  mov     [rbp+37h+hObject], rdi
0x180074bcc  test    r15d, r15d
0x180074bcf  jz      short loc_180074C13
0x180074bd1  cmp     [rbp+37h+var_98], edi
0x180074bd4  jz      short loc_180074C13
0x180074bd6  mov     ecx, ebx; int
0x180074bd8  call    ?IsTpmError@@YAHJ@Z; IsTpmError(long)
0x180074bdd  test    eax, eax
0x180074bdf  jz      short loc_180074C13
0x180074be1  mov     r8d, ebx
0x180074be4  lea     rdx, aRegistrationke_13; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074beb  lea     rcx, aSError0x08xIsD; "%s: Error 0x%08X is detected as TPM-rel"...
0x180074bf2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180074bf7  mov     ebx, 3
0x180074bfc  mov     r15d, edi
0x180074bff  test    rsi, rsi
0x180074c02  jz      loc_1800749B0
0x180074c08  mov     dword ptr [rsi], 1
0x180074c0e  jmp     loc_1800749B0
0x180074c13  mov     r8d, ebx
0x180074c16  lea     rdx, aRegistrationke_13; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074c1d  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180074c24  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180074c29  mov     eax, ebx
0x180074c2b  mov     rcx, [rbp+37h+var_38]
0x180074c2f  xor     rcx, rsp; StackCookie
0x180074c32  call    __security_check_cookie
0x180074c37  mov     rbx, [rsp+0E0h+arg_8]
0x180074c3f  add     rsp, 0B0h
0x180074c46  pop     r15
0x180074c48  pop     r14
0x180074c4a  pop     r13
0x180074c4c  pop     r12
0x180074c4e  pop     rdi
0x180074c4f  pop     rsi
0x180074c50  pop     rbp
0x180074c51  retn
```
