# microsoft::fs::cryptography::CapiCipher::CapiCipher(unsigned __int64,unsigned __int64,ulong,bool,bool)

- ea: `0x180035284`
- end: `0x180035515`
- name: `??0CapiCipher@cryptography@fs@microsoft@@QEAA@_K0K_N1@Z`
- size: `657`
- prototype: `microsoft::fs::cryptography::CapiCipher *__fastcall(microsoft::fs::cryptography::CapiCipher *this, HCRYPTPROV, unsigned __int64, int, unsigned int, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fa58`
- `0x18002ff74`
- `0x180030c48`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x1800312ec`
- `0x180031850`
- `0x180035284`
- `0x180036954`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003540e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003540e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035436`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x1800353ff`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x1800353ff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003541d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003542a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003541d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003542a`
- `CRYPTSP!CryptDuplicateKey` at `0x1800353ee`
- `CRYPTSP!CryptDuplicateKey` at `0x1800353ee`
- `CRYPTSP!CryptContextAddRef` at `0x180035377`
- `CRYPTSP!CryptContextAddRef` at `0x180035377`

## string_xrefs

- `0x180035348`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x18003539f`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x18003545c`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
microsoft::fs::cryptography::CapiCipher *__fastcall microsoft::fs::cryptography::CapiCipher::CapiCipher(
        microsoft::fs::cryptography::CapiCipher *this,
        HCRYPTPROV a2,
        unsigned __int64 a3,
        int a4,
        unsigned int a5,
        bool a6)
{
  unsigned __int64 v6; // rbx
  unsigned __int8 *v9; // r15
  unsigned __int64 *v10; // rdi
  DWORD LastError; // eax
  int v12; // eax
  BOOL v13; // esi
  DWORD v14; // ebx
  DWORD v15; // eax
  int v16; // eax
  _BYTE pExceptionObject[48]; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v19[48]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v20[48]; // [rsp+A0h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+118h] [rbp+20h] BYREF

  v6 = a3;
  *(_QWORD *)this = &microsoft::fs::common::IConfigurable::`vftable';
  *((_QWORD *)this + 1) = &microsoft::fs::cryptography::IExportableKey::`vftable';
  *(_QWORD *)this = &microsoft::fs::cryptography::ICipher::`vftable'{for `microsoft::fs::common::IConfigurable'};
  *((_QWORD *)this + 1) = &microsoft::fs::cryptography::ICipher::`vftable'{for `microsoft::fs::cryptography::IExportableKey'};
  *(_QWORD *)this = &microsoft::fs::cryptography::BaseCipher::`vftable'{for `microsoft::fs::common::IConfigurable'};
  *((_QWORD *)this + 1) = &microsoft::fs::cryptography::BaseCipher::`vftable'{for `microsoft::fs::cryptography::IExportableKey'};
  *(_QWORD *)this = &microsoft::fs::cryptography::CapiCipher::`vftable'{for `microsoft::fs::common::IConfigurable'};
  *((_QWORD *)this + 1) = &microsoft::fs::cryptography::CapiCipher::`vftable'{for `microsoft::fs::cryptography::IExportableKey'};
  *((_DWORD *)this + 4) = 1;
  v9 = (unsigned __int8 *)this + 20;
  *((_DWORD *)this + 5) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 7) = a4;
  *((_BYTE *)this + 32) = 1;
  *((_QWORD *)this + 5) = 0;
  v10 = (unsigned __int64 *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  try
  {
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x40u,
        L"0 != hKey",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( a2 )
    {
      if ( !CryptContextAddRef(a2, 0, 0) )
      {
        LastError = GetLastError();
        v12 = HR_FROM_WIN32(LastError);
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v19,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x46u,
          L"CryptContextAddRef(hProv, 0, 0)",
          v12);
        throw (microsoft::fs::common::FsException *)v19;
      }
      microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::reset(
        (char *)this + 40,
        a2);
    }
    if ( a6 )
    {
      microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiKeyFunctor>::close(v10);
      *v10 = v6;
LABEL_19:
      a5 = 4;
      fsCryptGetKeyParam(v6, 7u, (unsigned __int8 *)this + 24, &a5, 0);
      v22 = 4;
      if ( (unsigned int)fsCryptGetKeyParam(*v10, 8u, v9, &v22, 0) )
        *(_DWORD *)v9 >>= 3;
      return this;
    }
    v13 = CryptDuplicateKey(v6, 0, 0, v10);
    if ( v13 )
    {
      if ( !DbgIsSSActive(0x404u) )
      {
LABEL_15:
        if ( !v13 )
        {
          v15 = GetLastError();
          v16 = HR_FROM_WIN32(v15);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v20,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
            0x4Eu,
            L"CryptDuplicateKey(hKey, 0, 0, &m_hKey)",
            v16);
          throw (microsoft::fs::common::FsException *)v20;
        }
        v6 = *v10;
        goto LABEL_19;
      }
      v14 = 0;
    }
    else
    {
      v14 = GetLastError();
    }
    CSPrintErrorLineFile(0x36C0C22u, v14);
    CSPrintErrorLineFile(0x36D0C22u, 0);
    if ( v14 )
      SetLastError(v14);
    goto LABEL_15;
  }
  catch ( ... )
  {
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 5) = 0;
    throw;
  }
  return this;
}

```

## disassembly

```asm
0x180035284  mov     [rsp+arg_8], rbx
0x180035289  mov     [rsp+arg_10], rsi
0x18003528e  mov     [rsp+arg_0], rcx
0x180035293  push    rdi
0x180035294  push    r12
0x180035296  push    r13
0x180035298  push    r14
0x18003529a  push    r15
0x18003529c  sub     rsp, 0D0h
0x1800352a3  mov     rbx, r8
0x1800352a6  mov     rsi, rdx
0x1800352a9  mov     r14, rcx
0x1800352ac  lea     rax, ??_7IConfigurable@common@fs@microsoft@@6B@; const microsoft::fs::common::IConfigurable::`vftable'
0x1800352b3  mov     [rcx], rax
0x1800352b6  lea     rax, ??_7IExportableKey@cryptography@fs@microsoft@@6B@; const microsoft::fs::cryptography::IExportableKey::`vftable'
0x1800352bd  mov     [rcx+8], rax
0x1800352c1  lea     rax, ??_7ICipher@cryptography@fs@microsoft@@6BIConfigurable@common@23@@; const microsoft::fs::cryptography::ICipher::`vftable'{for `microsoft::fs::common::IConfigurable'}
0x1800352c8  mov     [rcx], rax
0x1800352cb  lea     rax, ??_7ICipher@cryptography@fs@microsoft@@6BIExportableKey@123@@; const microsoft::fs::cryptography::ICipher::`vftable'{for `microsoft::fs::cryptography::IExportableKey'}
0x1800352d2  mov     [rcx+8], rax
0x1800352d6  lea     rax, ??_7BaseCipher@cryptography@fs@microsoft@@6BIConfigurable@common@23@@; const microsoft::fs::cryptography::BaseCipher::`vftable'{for `microsoft::fs::common::IConfigurable'}
0x1800352dd  mov     [rcx], rax
0x1800352e0  lea     rax, ??_7BaseCipher@cryptography@fs@microsoft@@6BIExportableKey@123@@; const microsoft::fs::cryptography::BaseCipher::`vftable'{for `microsoft::fs::cryptography::IExportableKey'}
0x1800352e7  mov     [rcx+8], rax
0x1800352eb  lea     rax, ??_7CapiCipher@cryptography@fs@microsoft@@6BIConfigurable@common@23@@; const microsoft::fs::cryptography::CapiCipher::`vftable'{for `microsoft::fs::common::IConfigurable'}
0x1800352f2  mov     [rcx], rax
0x1800352f5  lea     rax, ??_7CapiCipher@cryptography@fs@microsoft@@6BIExportableKey@123@@; const microsoft::fs::cryptography::CapiCipher::`vftable'{for `microsoft::fs::cryptography::IExportableKey'}
0x1800352fc  mov     [rcx+8], rax
0x180035300  mov     dword ptr [rcx+10h], 1
0x180035307  lea     r15, [rcx+14h]
0x18003530b  xor     eax, eax
0x18003530d  mov     [r15], eax
0x180035310  mov     [rcx+18h], eax
0x180035313  mov     [rcx+1Ch], r9d
0x180035317  mov     byte ptr [rcx+20h], 1
0x18003531b  mov     [rcx+28h], rax
0x18003531f  lea     rdi, [rcx+30h]
0x180035323  mov     [rdi], rax
0x180035326  mov     [rsp+0F8h+var_C0], rax
0x18003532b  mov     [rsp+0F8h+var_C8], rax
0x180035330  test    rbx, rbx
0x180035333  jnz     short loc_18003536A
0x180035335  mov     [rsp+0F8h+var_D8], 80070057h; int
0x18003533d  lea     r9, a0Hkey; "0 != hKey"
0x180035344  lea     r8d, [rbx+40h]; unsigned int
0x180035348  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003534f  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180035354  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035359  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035360  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180035365  call    _CxxThrowException_0
0x18003536a  test    rsi, rsi
0x18003536d  jz      short loc_1800353D2
0x18003536f  xor     r8d, r8d; dwFlags
0x180035372  xor     edx, edx; pdwReserved
0x180035374  mov     rcx, rsi; hProv
0x180035377  call    cs:__imp_CryptContextAddRef
0x18003537d  test    eax, eax
0x18003537f  jnz     short loc_1800353C1
0x180035381  call    cs:__imp_GetLastError
0x180035387  mov     ecx, eax; unsigned int
0x180035389  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003538e  mov     [rsp+0F8h+var_D8], eax; int
0x180035392  lea     r9, aCryptcontextad_1; "CryptContextAddRef(hProv, 0, 0)"
0x180035399  mov     r8d, 46h ; 'F'; unsigned int
0x18003539f  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800353a6  lea     rcx, [rsp+0F8h+var_88]; this
0x1800353ab  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800353b0  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800353b7  lea     rcx, [rsp+0F8h+var_88]; pExceptionObject
0x1800353bc  call    _CxxThrowException_0
0x1800353c1  mov     [rsp+0F8h+var_C0], rsi
0x1800353c6  mov     rdx, rsi
0x1800353c9  lea     rcx, [r14+28h]
0x1800353cd  call    ?reset@?$auto_handle_t@_K$0A@VCloseCapiProviderFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAX_K@Z; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::reset(unsigned __int64)
0x1800353d2  xor     r12d, r12d
0x1800353d5  cmp     [rsp+0F8h+arg_28], r12b
0x1800353dd  jnz     loc_18003548E
0x1800353e3  mov     r9, rdi; phKey
0x1800353e6  xor     r8d, r8d; dwFlags
0x1800353e9  xor     edx, edx; pdwReserved
0x1800353eb  mov     rcx, rbx; hKey
0x1800353ee  call    cs:__imp_CryptDuplicateKey
0x1800353f4  mov     esi, eax
0x1800353f6  test    eax, eax
0x1800353f8  jz      short loc_18003540E
0x1800353fa  mov     ecx, 404h
0x1800353ff  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180035405  test    eax, eax
0x180035407  jz      short loc_18003543C
0x180035409  mov     ebx, r12d
0x18003540c  jmp     short loc_180035416
0x18003540e  call    cs:__imp_GetLastError
0x180035414  mov     ebx, eax
0x180035416  mov     edx, ebx
0x180035418  mov     ecx, 36C0C22h
0x18003541d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035423  xor     edx, edx
0x180035425  mov     ecx, 36D0C22h
0x18003542a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035430  test    ebx, ebx
0x180035432  jz      short loc_18003543C
0x180035434  mov     ecx, ebx; dwErrCode
0x180035436  call    cs:__imp_SetLastError
0x18003543c  test    esi, esi
0x18003543e  jnz     short loc_180035484
0x180035440  call    cs:__imp_GetLastError
0x180035446  mov     ecx, eax; unsigned int
0x180035448  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003544d  mov     [rsp+0F8h+var_D8], eax; int
0x180035451  lea     r9, aCryptduplicate_0; "CryptDuplicateKey(hKey, 0, 0, &m_hKey)"
0x180035458  lea     r8d, [rsi+4Eh]; unsigned int
0x18003545c  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035463  lea     rcx, [rsp+0F8h+var_58]; this
0x18003546b  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035470  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035477  lea     rcx, [rsp+0F8h+var_58]; pExceptionObject
0x18003547f  call    _CxxThrowException_0
0x180035484  mov     rbx, [rdi]
0x180035487  mov     [rsp+0F8h+var_C8], rbx
0x18003548c  jmp     short loc_180035499
0x18003548e  mov     rcx, rdi
0x180035491  call    ?close@?$auto_handle_t@_K$0A@VCloseCapiKeyFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiKeyFunctor>::close(void)
0x180035496  mov     [rdi], rbx
0x180035499  mov     esi, 4
0x18003549e  mov     [rsp+0F8h+arg_20], esi
0x1800354a5  mov     [rsp+0F8h+var_D8], r12d; DWORD
0x1800354aa  lea     r9, [rsp+0F8h+arg_20]; unsigned int *
0x1800354b2  lea     r8, [r14+18h]; unsigned __int8 *
0x1800354b6  lea     edx, [rsi+3]; unsigned int
0x1800354b9  mov     rcx, rbx; unsigned __int64
0x1800354bc  call    ?fsCryptGetKeyParam@@YAH_KKPEAEPEAKK@Z; fsCryptGetKeyParam(unsigned __int64,ulong,uchar *,ulong *,ulong)
0x1800354c1  mov     [rsp+0F8h+arg_18], esi
0x1800354c8  mov     [rsp+0F8h+var_D8], r12d; DWORD
0x1800354cd  lea     r9, [rsp+0F8h+arg_18]; unsigned int *
0x1800354d5  mov     r8, r15; unsigned __int8 *
0x1800354d8  lea     edx, [rsi+4]; unsigned int
0x1800354db  mov     rcx, [rdi]; unsigned __int64
0x1800354de  call    ?fsCryptGetKeyParam@@YAH_KKPEAEPEAKK@Z; fsCryptGetKeyParam(unsigned __int64,ulong,uchar *,ulong *,ulong)
0x1800354e3  test    eax, eax
0x1800354e5  jz      short loc_1800354EB
0x1800354e7  shr     dword ptr [r15], 3
0x1800354eb  mov     [rsp+0F8h+var_C0], r12
0x1800354f0  mov     [rsp+0F8h+var_C8], r12
0x1800354f5  mov     rax, r14
0x1800354f8  lea     r11, [rsp+0F8h+var_28]
0x180035500  mov     rbx, [r11+38h]
0x180035504  mov     rsi, [r11+40h]
0x180035508  mov     rsp, r11
0x18003550b  pop     r15
0x18003550d  pop     r14
0x18003550f  pop     r13
0x180035511  pop     r12
0x180035513  pop     rdi
0x180035514  retn
```
