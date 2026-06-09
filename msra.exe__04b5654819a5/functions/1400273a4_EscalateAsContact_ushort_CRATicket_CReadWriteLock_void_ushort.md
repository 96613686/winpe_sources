# EscalateAsContact(ushort *,CRATicket *,CReadWriteLock *,void * *,ushort *)

- ea: `0x1400273a4`
- end: `0x14002795e`
- name: `?EscalateAsContact@@YAJPEAGPEAVCRATicket@@PEAVCReadWriteLock@@PEAPEAX0@Z`
- size: `1466`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, struct CRATicket *@<rdx>, struct CReadWriteLock *@<r8>, void **@<r9>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140031440`

## callees

- `0x1400020f4`
- `0x140002156`
- `0x140002463`
- `0x1400080fc`
- `0x140027098`
- `0x1400273a4`
- `0x140029418`
- `0x140034ce4`
- `0x1400383c8`
- `0x140038470`
- `0x140040220`
- `0x140040390`
- `0x140041234`
- `0x140041998`
- `0x140043b64`
- `0x14004ad80`

## import_xrefs

- `ADVAPI32!CryptEncrypt` at `0x140027544`
- `ADVAPI32!CryptEncrypt` at `0x140027633`
- `ADVAPI32!CryptEncrypt` at `0x140027544`
- `ADVAPI32!CryptEncrypt` at `0x140027633`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002759d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400275ec`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140027721`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140027735`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002759d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400275ec`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140027721`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140027735`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278fb`
- `OLEAUT32!__imp_SysFreeString` at `0x14002790f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400278fb`
- `OLEAUT32!__imp_SysFreeString` at `0x14002790f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140027797`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400277ad`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140027797`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400277ad`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140027665`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400277c2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140027665`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400277c2`

## string_xrefs

- `0x14002746b`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002775d`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400277f0`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002789f`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140027694`: `CRAEncryption::LoopEncrypt`
- `0x1400276c5`: `CRAEncryption::LoopEncrypt`
- `0x1400276f9`: `CRAEncryption::LoopEncrypt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EscalateAsContact(
        unsigned __int16 *a1,
        struct CRATicket *a2,
        struct CReadWriteLock *a3,
        void **a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v7; // r12
  BYTE *pbData; // rsi
  struct CReadWriteLock *v9; // r8
  int v10; // r9d
  signed int RAConnectionString; // eax
  void *v12; // r15
  OLECHAR *v13; // r13
  signed int SelfHistoryItem; // eax
  unsigned int v15; // r9d
  __int64 v16; // rax
  DWORD dwBufLen; // r15d
  void *v18; // r14
  signed int v19; // ebx
  CEventLogger *v20; // rcx
  DWORD v21; // eax
  void *v22; // rax
  CEventLogger *v23; // rcx
  BYTE *v24; // rax
  CEventLogger *v25; // rcx
  unsigned int v26; // r9d
  unsigned int v27; // r9d
  CRATicket *v28; // rcx
  size_t v29; // rsi
  UINT v30; // eax
  size_t v31; // r14
  BSTR v32; // rax
  int v33; // eax
  unsigned int v34; // r9d
  unsigned int pdwDataLen; // [rsp+28h] [rbp-D8h]
  DWORD len; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstr; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+5Ch] [rbp-A4h]
  unsigned int v42; // [rsp+60h] [rbp-A0h]
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  CRATicket *v44; // [rsp+78h] [rbp-88h]
  HCRYPTKEY v45[4]; // [rsp+80h] [rbp-80h] BYREF
  HCRYPTKEY hKey; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  _OWORD v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h]
  __int128 v50; // [rsp+D8h] [rbp-28h]
  int v51; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v52[1024]; // [rsp+F0h] [rbp-10h] BYREF

  v44 = a2;
  v7 = a5;
  Src = a5;
  v50 = 0;
  pbData = 0;
  v51 = 0;
  memset(v48, 0, sizeof(v48));
  v49 = 0;
  bstr = 0;
  bstrString = 0;
  memset(v45, 0, sizeof(v45));
  hKey = 0;
  v47 = 0;
  memset_0(v52, 0, sizeof(v52));
  if ( a5 )
  {
    v42 = -2147483122;
    v41 = 0;
  }
  else
  {
    RAConnectionString = GetRAConnectionString((unsigned __int16 **)&Src, a2, v9);
    v42 = RAConnectionString;
    if ( RAConnectionString < 0 )
    {
      CEventLogger::LogError(
        (CEventLogger *)L"EscalateAsContact",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x15F0u,
        L"EscalateAsContact",
        RAConnectionString);
      goto LABEL_59;
    }
    v41 = 1;
    v7 = (unsigned __int16 *)Src;
  }
  v12 = 0;
  Src = 0;
  v13 = 0;
  SelfHistoryItem = CRAEncryption::ExportKeyEnh((CRAEncryption *)v45, a1, &bstr, v10);
  if ( SelfHistoryItem < 0 )
  {
    v15 = 5624;
LABEL_8:
    CEventLogger::LogError(
      (CEventLogger *)L"EscalateAsContact",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v15,
      L"EscalateAsContact",
      SelfHistoryItem);
    goto LABEL_48;
  }
  SelfHistoryItem = CreateSelfHistoryItem((struct CRAInvitationHistoryItem *)v48);
  if ( SelfHistoryItem < 0 )
  {
    v15 = 5629;
    goto LABEL_8;
  }
  SelfHistoryItem = CRAInvitationHistoryItem::get_Address((CRAInvitationHistoryItem *)v48, &bstrString);
  if ( SelfHistoryItem < 0 )
  {
    v15 = 5630;
    goto LABEL_8;
  }
  v16 = -1;
  do
    ++v16;
  while ( v7[v16] );
  dwBufLen = 2 * v16;
  len = 2 * v16;
  v18 = 0;
  v40 = 0;
  v19 = 0;
  while ( 1 )
  {
    if ( !CryptEncrypt(hKey, 0, 1, 0, 0, &len, dwBufLen) )
    {
      v27 = 1230;
      goto LABEL_35;
    }
    v21 = len;
    if ( (unsigned int)v13 < len )
      break;
LABEL_26:
    if ( !CryptEncrypt(hKey, 0, 1, 0, pbData, &len, (DWORD)v13) )
    {
      v27 = 1270;
LABEL_35:
      CEventLogger::LogError(
        v20,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
        v27,
        L"CRAEncryption::LoopEncrypt",
        0);
      v19 = -2147467259;
      goto LABEL_36;
    }
    dwBufLen = len;
    if ( ++v40 )
    {
      Src = SysAllocStringByteLen((LPCSTR)pbData, len);
      if ( !Src )
      {
        v26 = 1299;
        goto LABEL_32;
      }
      goto LABEL_36;
    }
  }
  if ( pbData )
  {
    v22 = operator new[]((unsigned int)v13, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v22;
    if ( !v22 )
    {
      v19 = -2147024882;
      CEventLogger::LogError(
        v23,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
        0x4D5u,
        L"CRAEncryption::LoopEncrypt",
        0x8007000E);
      goto LABEL_39;
    }
    memcpy_0(v22, pbData, (unsigned int)v13);
    operator delete[](pbData);
    v21 = len;
  }
  v24 = (BYTE *)operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
  pbData = v24;
  if ( v24 )
  {
    memset_0(v24, 0, len);
    if ( v18 )
    {
      memcpy_0(pbData, v18, (unsigned int)v13);
      operator delete[](v18);
      v18 = 0;
    }
    else
    {
      memcpy_0(pbData, v7, dwBufLen);
    }
    LODWORD(v13) = len;
    len = dwBufLen;
    goto LABEL_26;
  }
  v26 = 1245;
LABEL_32:
  v19 = -2147024882;
  CEventLogger::LogError(
    v25,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
    v26,
    L"CRAEncryption::LoopEncrypt",
    0x8007000E);
LABEL_36:
  if ( v18 )
    operator delete[](v18);
  if ( pbData )
LABEL_39:
    operator delete[](pbData);
  if ( v19 >= 0 )
  {
    v28 = v44;
    *((_DWORD *)v44 + 34) = 8;
    CRATicket::put_UserPassword(v28, bstr);
    v29 = SysStringByteLen(bstr);
    v12 = Src;
    v30 = SysStringByteLen((BSTR)Src);
    v31 = v30;
    v32 = SysAllocStringByteLen(0, v30 + (unsigned int)v29);
    v13 = v32;
    if ( v32 )
    {
      memcpy_0(v32, bstr, v29);
      memcpy_0((char *)v13 + v29, v12, v31);
      v33 = StringCchPrintfW(v52, 0x400u, L"%d", (unsigned int)v29);
      if ( v33 >= 0 )
      {
        CSqmManager::StartTimer((CEventLogger *)((char *)_AtlModule + 496), 2u);
        CSqmManager::StopTimer((CEventLogger *)((char *)_AtlModule + 496), 2u, 1);
        pdwDataLen = -2147467263;
        v34 = 5679;
      }
      else
      {
        pdwDataLen = v33;
        v34 = 5663;
      }
      CEventLogger::LogError(
        (CEventLogger *)L"EscalateAsContact",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        v34,
        L"EscalateAsContact",
        pdwDataLen);
    }
    else
    {
      CEventLogger::LogError(
        (CEventLogger *)L"EscalateAsContact",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x1614u,
        L"EscalateAsContact",
        0x8007000E);
    }
  }
  else
  {
    CEventLogger::LogError(
      (CEventLogger *)L"EscalateAsContact",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1609u,
      L"EscalateAsContact",
      v19);
    v12 = Src;
    v13 = 0;
  }
LABEL_48:
  if ( v41 && v7 )
    SysFreeString(v7);
  if ( v12 )
    SysFreeString((BSTR)v12);
  if ( bstr )
    SysFreeString(bstr);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v13 )
    SysFreeString(v13);
LABEL_59:
  CRAEncryption::~CRAEncryption((CRAEncryption *)v45);
  CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)v48);
  return v42;
}

```

## disassembly

```asm
0x1400273a4  mov     [rsp-8+arg_10], rbx
0x1400273a9  push    rbp
0x1400273aa  push    rsi
0x1400273ab  push    rdi
0x1400273ac  push    r12
0x1400273ae  push    r13
0x1400273b0  push    r14
0x1400273b2  push    r15
0x1400273b4  lea     rbp, [rsp-800h]
0x1400273bc  sub     rsp, 900h
0x1400273c3  mov     rax, cs:__security_cookie
0x1400273ca  xor     rax, rsp
0x1400273cd  mov     [rbp+830h+var_40], rax
0x1400273d4  mov     rdi, rdx
0x1400273d7  mov     [rsp+930h+var_8B8], rdx
0x1400273dc  mov     rbx, rcx
0x1400273df  mov     r12, [rbp+830h+arg_20]
0x1400273e6  mov     [rsp+930h+Src], r12
0x1400273eb  xorps   xmm0, xmm0
0x1400273ee  movups  [rbp+830h+var_858], xmm0
0x1400273f2  xor     esi, esi
0x1400273f4  mov     [rbp+830h+var_848], esi
0x1400273f7  movdqa  [rbp+830h+var_880], xmm0
0x1400273fc  xorps   xmm1, xmm1
0x1400273ff  movdqa  [rbp+830h+var_870], xmm1
0x140027404  mov     [rbp+830h+var_860], rsi
0x140027408  mov     [rsp+930h+bstr], rsi
0x14002740d  mov     [rsp+930h+bstrString], rsi
0x140027412  mov     [rbp+830h+var_8B0], rsi
0x140027416  mov     [rbp+830h+var_8A8], rsi
0x14002741a  mov     [rbp+830h+var_8A0], rsi
0x14002741e  mov     [rbp+830h+var_898], rsi
0x140027422  mov     [rbp+830h+hKey], rsi
0x140027426  mov     [rbp+830h+var_888], rsi
0x14002742a  xor     edx, edx; Val
0x14002742c  mov     r8d, 800h; Size
0x140027432  lea     rcx, [rbp+830h+var_840]; void *
0x140027436  call    memset_0
0x14002743b  test    r12, r12
0x14002743e  jnz     short loc_140027492
0x140027440  mov     rdx, rdi; this
0x140027443  lea     rcx, [rsp+930h+Src]; unsigned __int16 **
0x140027448  call    ?GetRAConnectionString@@YAJPEAPEAGPEAVCRATicket@@PEAVCReadWriteLock@@@Z; GetRAConnectionString(ushort * *,CRATicket *,CReadWriteLock *)
0x14002744d  mov     [rsp+930h+var_8D0], eax
0x140027451  test    eax, eax
0x140027453  jns     short loc_140027483
0x140027455  mov     dword ptr [rsp+930h+pdwDataLen], eax; unsigned int
0x140027459  lea     rcx, aEscalateascont; "EscalateAsContact"
0x140027460  mov     [rsp+930h+pbData], rcx; unsigned __int16 *
0x140027465  mov     r9d, 15F0h; unsigned int
0x14002746b  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140027472  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140027479  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002747e  jmp     loc_14002791C
0x140027483  mov     [rsp+930h+var_8D4], 1
0x14002748b  mov     r12, [rsp+930h+Src]
0x140027490  jmp     short loc_14002749E
0x140027492  mov     [rsp+930h+var_8D0], 8000020Eh
0x14002749a  mov     [rsp+930h+var_8D4], esi
0x14002749e  mov     r15, rsi
0x1400274a1  mov     [rsp+930h+Src], rsi
0x1400274a6  mov     r13, rsi
0x1400274a9  lea     r8, [rsp+930h+bstr]; unsigned __int16 **
0x1400274ae  mov     rdx, rbx; unsigned __int16 *
0x1400274b1  lea     rcx, [rbp+830h+var_8B0]; this
0x1400274b5  call    ?ExportKeyEnh@CRAEncryption@@QEAAJPEAGPEAPEAGH@Z; CRAEncryption::ExportKeyEnh(ushort *,ushort * *,int)
0x1400274ba  test    eax, eax
0x1400274bc  jns     short loc_1400274D4
0x1400274be  mov     r9d, 15F8h
0x1400274c4  mov     dword ptr [rsp+930h+pdwDataLen], eax
0x1400274c8  lea     rdx, Recoverable_Error
0x1400274cf  jmp     loc_140027893
0x1400274d4  lea     rcx, [rbp+830h+var_880]; this
0x1400274d8  call    ?CreateSelfHistoryItem@@YAJPEAVCRAInvitationHistoryItem@@@Z; CreateSelfHistoryItem(CRAInvitationHistoryItem *)
0x1400274dd  test    eax, eax
0x1400274df  jns     short loc_1400274E9
0x1400274e1  mov     r9d, 15FDh
0x1400274e7  jmp     short loc_1400274C4
0x1400274e9  lea     rdx, [rsp+930h+bstrString]; unsigned __int16 **
0x1400274ee  lea     rcx, [rbp+830h+var_880]; this
0x1400274f2  call    ?get_Address@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Address(ushort * *)
0x1400274f7  test    eax, eax
0x1400274f9  jns     short loc_140027503
0x1400274fb  mov     r9d, 15FEh
0x140027501  jmp     short loc_1400274C4
0x140027503  or      rax, 0FFFFFFFFFFFFFFFFh
0x140027507  inc     rax
0x14002750a  cmp     [r12+rax*2], si
0x14002750f  jnz     short loc_140027507
0x140027511  lea     r15d, [rax+rax]
0x140027515  mov     [rsp+930h+len], r15d
0x14002751a  mov     r14, rsi
0x14002751d  mov     [rsp+930h+var_8D8], esi
0x140027521  xor     ebx, ebx
0x140027523  mov     [rsp+930h+dwBufLen], r15d; dwBufLen
0x140027528  lea     rax, [rsp+930h+len]
0x14002752d  mov     [rsp+930h+pdwDataLen], rax; pdwDataLen
0x140027532  mov     [rsp+930h+pbData], rbx; pbData
0x140027537  xor     r9d, r9d; dwFlags
0x14002753a  xor     edx, edx; hHash
0x14002753c  lea     r8d, [r9+1]; Final
0x140027540  mov     rcx, [rbp+830h+hKey]; hKey
0x140027544  call    cs:__imp_CryptEncrypt
0x14002754b  nop     dword ptr [rax+rax+00h]
0x140027550  lea     rdi, Recoverable_Error
0x140027557  test    eax, eax
0x140027559  jz      loc_1400276EF
0x14002755f  mov     eax, [rsp+930h+len]
0x140027563  cmp     r13d, eax
0x140027566  jnb     loc_140027612
0x14002756c  test    rsi, rsi
0x14002756f  jz      short loc_1400275AD
0x140027571  mov     ecx, r13d; unsigned __int64
0x140027574  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002757b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140027580  mov     r14, rax
0x140027583  test    rax, rax
0x140027586  jz      loc_140027687
0x14002758c  mov     r8d, r13d; Size
0x14002758f  mov     rdx, rsi; Src
0x140027592  mov     rcx, rax; void *
0x140027595  call    memcpy_0
0x14002759a  mov     rcx, rsi
0x14002759d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400275a4  nop     dword ptr [rax+rax+00h]
0x1400275a9  mov     eax, [rsp+930h+len]
0x1400275ad  mov     ecx, eax; unsigned __int64
0x1400275af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400275b6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400275bb  mov     rsi, rax
0x1400275be  test    rax, rax
0x1400275c1  jz      loc_1400276B7
0x1400275c7  mov     r8d, [rsp+930h+len]; Size
0x1400275cc  xor     edx, edx; Val
0x1400275ce  mov     rcx, rax; void *
0x1400275d1  call    memset_0
0x1400275d6  mov     rcx, rsi; void *
0x1400275d9  test    r14, r14
0x1400275dc  jz      short loc_1400275FD
0x1400275de  mov     r8d, r13d; Size
0x1400275e1  mov     rdx, r14; Src
0x1400275e4  call    memcpy_0
0x1400275e9  mov     rcx, r14
0x1400275ec  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400275f3  nop     dword ptr [rax+rax+00h]
0x1400275f8  xor     r14d, r14d
0x1400275fb  jmp     short loc_140027608
0x1400275fd  mov     r8d, r15d; Size
0x140027600  mov     rdx, r12; Src
0x140027603  call    memcpy_0
0x140027608  mov     r13d, [rsp+930h+len]
0x14002760d  mov     [rsp+930h+len], r15d
0x140027612  mov     [rsp+930h+dwBufLen], r13d; dwBufLen
0x140027617  lea     rax, [rsp+930h+len]
0x14002761c  mov     [rsp+930h+pdwDataLen], rax; pdwDataLen
0x140027621  mov     [rsp+930h+pbData], rsi; pbData
0x140027626  xor     r9d, r9d; dwFlags
0x140027629  xor     edx, edx; hHash
0x14002762b  lea     r8d, [r9+1]; Final
0x14002762f  mov     rcx, [rbp+830h+hKey]; hKey
0x140027633  call    cs:__imp_CryptEncrypt
0x14002763a  nop     dword ptr [rax+rax+00h]
0x14002763f  test    eax, eax
0x140027641  jz      loc_1400276E7
0x140027647  mov     r15d, [rsp+930h+len]
0x14002764c  mov     eax, [rsp+930h+var_8D8]
0x140027650  inc     eax
0x140027652  mov     [rsp+930h+var_8D8], eax
0x140027656  cmp     eax, 1
0x140027659  jb      loc_140027523
0x14002765f  mov     edx, r15d; len
0x140027662  mov     rcx, rsi; psz
0x140027665  call    cs:__imp_SysAllocStringByteLen
0x14002766c  nop     dword ptr [rax+rax+00h]
0x140027671  mov     [rsp+930h+Src], rax
0x140027676  test    rax, rax
0x140027679  jnz     loc_140027719
0x14002767f  mov     r9d, 513h
0x140027685  jmp     short loc_1400276BD
0x140027687  mov     ebx, 8007000Eh
0x14002768c  mov     dword ptr [rsp+930h+pdwDataLen], 8007000Eh; unsigned int
0x140027694  lea     rax, aCraencryptionL; "CRAEncryption::LoopEncrypt"
0x14002769b  mov     [rsp+930h+pbData], rax; unsigned __int16 *
0x1400276a0  mov     r9d, 4D5h; unsigned int
0x1400276a6  lea     r8, aBaseDiagnosisR_29; "base\\diagnosis\\ra\\core\\lib\\raencry"...
0x1400276ad  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x1400276b0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400276b5  jmp     short loc_140027732
0x1400276b7  mov     r9d, 4DDh; unsigned int
0x1400276bd  mov     dword ptr [rsp+930h+pdwDataLen], 8007000Eh; unsigned int
0x1400276c5  lea     rax, aCraencryptionL; "CRAEncryption::LoopEncrypt"
0x1400276cc  mov     [rsp+930h+pbData], rax; unsigned __int16 *
0x1400276d1  mov     ebx, 8007000Eh
0x1400276d6  lea     r8, aBaseDiagnosisR_29; "base\\diagnosis\\ra\\core\\lib\\raencry"...
0x1400276dd  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x1400276e0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400276e5  jmp     short loc_140027719
0x1400276e7  mov     r9d, 4F6h
0x1400276ed  jmp     short loc_1400276F5
0x1400276ef  mov     r9d, 4CEh; unsigned int
0x1400276f5  mov     dword ptr [rsp+930h+pdwDataLen], ebx; unsigned int
0x1400276f9  lea     rax, aCraencryptionL; "CRAEncryption::LoopEncrypt"
0x140027700  mov     [rsp+930h+pbData], rax; unsigned __int16 *
0x140027705  lea     r8, aBaseDiagnosisR_29; "base\\diagnosis\\ra\\core\\lib\\raencry"...
0x14002770c  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x14002770f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140027714  mov     ebx, 80004005h
0x140027719  test    r14, r14
0x14002771c  jz      short loc_14002772D
0x14002771e  mov     rcx, r14
0x140027721  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140027728  nop     dword ptr [rax+rax+00h]
0x14002772d  test    rsi, rsi
0x140027730  jz      short loc_140027741
0x140027732  mov     rcx, rsi
0x140027735  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002773c  nop     dword ptr [rax+rax+00h]
0x140027741  xor     esi, esi
0x140027743  test    ebx, ebx
0x140027745  jns     short loc_140027779
0x140027747  mov     dword ptr [rsp+930h+pdwDataLen], ebx; unsigned int
0x14002774b  lea     rcx, aEscalateascont; "EscalateAsContact"
0x140027752  mov     [rsp+930h+pbData], rcx; unsigned __int16 *
0x140027757  mov     r9d, 1609h; unsigned int
0x14002775d  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140027764  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x140027767  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002776c  mov     r15, [rsp+930h+Src]
0x140027771  mov     r13d, esi
0x140027774  jmp     loc_1400278AB
0x140027779  mov     rcx, [rsp+930h+var_8B8]; this
0x14002777e  mov     dword ptr [rcx+88h], 8
0x140027788  mov     rdx, [rsp+930h+bstr]; unsigned __int16 *
0x14002778d  call    ?put_UserPassword@CRATicket@@QEAAJPEAG@Z; CRATicket::put_UserPassword(ushort *)
0x140027792  mov     rcx, [rsp+930h+bstr]; bstr
0x140027797  call    cs:__imp_SysStringByteLen
0x14002779e  nop     dword ptr [rax+rax+00h]
0x1400277a3  mov     esi, eax
0x1400277a5  mov     r15, [rsp+930h+Src]
0x1400277aa  mov     rcx, r15; bstr
0x1400277ad  call    cs:__imp_SysStringByteLen
0x1400277b4  nop     dword ptr [rax+rax+00h]
0x1400277b9  mov     r14d, eax
0x1400277bc  lea     edx, [r14+rsi]; len
0x1400277c0  xor     ecx, ecx; psz
0x1400277c2  call    cs:__imp_SysAllocStringByteLen
0x1400277c9  nop     dword ptr [rax+rax+00h]
0x1400277ce  mov     r13, rax
0x1400277d1  test    rax, rax
0x1400277d4  jnz     short loc_140027806
0x1400277d6  mov     dword ptr [rsp+930h+pdwDataLen], 8007000Eh; unsigned int
0x1400277de  lea     rcx, aEscalateascont; "EscalateAsContact"
0x1400277e5  mov     [rsp+930h+pbData], rcx; unsigned __int16 *
0x1400277ea  mov     r9d, 1614h; unsigned int
0x1400277f0  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400277f7  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x1400277fa  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400277ff  xor     esi, esi
0x140027801  jmp     loc_1400278AB
0x140027806  mov     r8, rsi; Size
0x140027809  mov     rdx, [rsp+930h+bstr]; Src
0x14002780e  mov     rcx, r13; void *
0x140027811  call    memcpy_0
0x140027816  mov     r8, r14; Size
0x140027819  lea     rcx, [rsi+r13]; void *
0x14002781d  mov     rdx, r15; Src
0x140027820  call    memcpy_0
0x140027825  mov     r9d, esi
0x140027828  lea     r8, aD; "%d"
0x14002782f  mov     edx, 400h; unsigned __int64
0x140027834  lea     rcx, [rbp+830h+var_840]; unsigned __int16 *
0x140027838  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002783d  xor     esi, esi
0x14002783f  test    eax, eax
0x140027841  jns     short loc_14002784F
0x140027843  mov     dword ptr [rsp+930h+pdwDataLen], eax
0x140027847  mov     r9d, 161Fh
0x14002784d  jmp     short loc_140027890
0x14002784f  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140027856  add     rcx, 1F0h; this
0x14002785d  mov     ebx, 2
0x140027862  mov     edx, ebx; unsigned int
0x140027864  call    ?StartTimer@CSqmManager@@QEAAXK@Z; CSqmManager::StartTimer(ulong)
0x140027869  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140027870  add     rcx, 1F0h; this
0x140027877  lea     r8d, [rbx-1]; int
0x14002787b  mov     edx, ebx; unsigned int
0x14002787d  call    ?StopTimer@CSqmManager@@QEAAKKH@Z; CSqmManager::StopTimer(ulong,int)
0x140027882  mov     dword ptr [rsp+930h+pdwDataLen], 80004001h; unsigned int
0x14002788a  mov     r9d, 162Fh; unsigned int
0x140027890  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x140027893  lea     rcx, aEscalateascont; "EscalateAsContact"
0x14002789a  mov     [rsp+930h+pbData], rcx; unsigned __int16 *
0x14002789f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400278a6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400278ab  cmp     [rsp+930h+var_8D4], esi
0x1400278af  jz      short loc_1400278C5
0x1400278b1  test    r12, r12
0x1400278b4  jz      short loc_1400278C5
0x1400278b6  mov     rcx, r12; bstrString
  ... truncated ...
```
