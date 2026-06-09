# GetV2TemplateName(_CERT_INFO *)

- ea: `0x180014694`
- end: `0x180014825`
- name: `?GetV2TemplateName@@YA?AVCString@WTL@@PEAU_CERT_INFO@@@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800140ec`

## callees

- `0x180001f4c`
- `0x180013544`
- `0x180013a30`
- `0x180014694`
- `0x180014cec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014722`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800147c7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800147c7`
- `CRYPT32!CryptDecodeObjectEx` at `0x180014718`
- `CRYPT32!CryptDecodeObjectEx` at `0x180014718`
- `CRYPT32!CryptFindOIDInfo` at `0x18001475b`
- `CRYPT32!CryptFindOIDInfo` at `0x18001475b`
- `CRYPT32!CertFindExtension` at `0x1800146dd`
- `CRYPT32!CertFindExtension` at `0x1800146dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180014788`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180014788`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WTL::CString *__fastcall GetV2TemplateName(WTL::CString *a1, __int64 a2)
{
  signed int v3; // ebx
  PCERT_EXTENSION Extension; // rax
  signed int LastError; // eax
  PCCRYPT_OID_INFO OIDInfo; // rax
  unsigned __int16 *pwszName; // rdx
  const CHAR *v8; // r14
  int v9; // esi
  int v10; // edx
  bool v11; // zf
  int v12; // eax
  WCHAR *v13; // rsi
  int v14; // eax
  DWORD pcbStructInfo; // [rsp+88h] [rbp+38h] BYREF
  signed int pExceptionObject; // [rsp+90h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hMem = 0;
  pcbStructInfo = 0;
  *(_QWORD *)a1 = WTL::_atltmpPchNil;
  Extension = CertFindExtension("1.3.6.1.4.1.311.21.7", *(_DWORD *)(a2 + 192), *(CERT_EXTENSION **)(a2 + 200));
  if ( Extension )
  {
    if ( CryptDecodeObjectEx(
           1u,
           (LPCSTR)0x40,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0x8000u,
           0,
           &hMem,
           &pcbStructInfo) )
    {
      if ( *(_QWORD *)hMem )
      {
        OIDInfo = CryptFindOIDInfo(1u, *(void **)hMem, 0);
        if ( OIDInfo && (pwszName = (unsigned __int16 *)OIDInfo->pwszName) != 0 )
        {
          WTL::CString::operator=(a1, pwszName);
        }
        else
        {
          v8 = *(const CHAR **)hMem;
          if ( *(_QWORD *)hMem )
            v9 = lstrlenA(*(LPCSTR *)hMem);
          else
            v9 = 0;
          if ( (unsigned int)WTL::CString::AllocBeforeWrite(a1, v9) )
          {
            v11 = v9 == -1;
            v12 = v9 + 1;
            v13 = *(WCHAR **)a1;
            if ( !v11 || !v13 )
            {
              v14 = MultiByteToWideChar(0, 0, v8, -1, v13, v12);
              if ( v14 > 0 )
                v13[v14 - 1] = 0;
            }
            WTL::CString::ReleaseBuffer(a1, v10);
          }
        }
        if ( !*(_QWORD *)a1 )
          v3 = -2147024882;
      }
      else
      {
        v3 = -2146885628;
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v3 < 0 )
  {
    pExceptionObject = v3;
    throw (long *)&pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180014694  mov     [rsp-28h+arg_0], rcx
0x180014699  push    rbp
0x18001469a  push    rbx
0x18001469b  push    rsi
0x18001469c  push    rdi
0x18001469d  push    r14
0x18001469f  mov     rbp, rsp
0x1800146a2  sub     rsp, 50h
0x1800146a6  mov     rdi, rcx
0x1800146a9  mov     [rbp+var_10], 0
0x1800146b0  xor     ebx, ebx
0x1800146b2  mov     [rbp+hMem], rbx
0x1800146b6  mov     [rbp+arg_8], ebx
0x1800146b9  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800146c0  mov     [rcx], rax
0x1800146c3  lea     esi, [rbx+1]
0x1800146c6  mov     [rbp+var_10], esi
0x1800146c9  mov     r8, [rdx+0C8h]; rgExtensions
0x1800146d0  mov     edx, [rdx+0C0h]; cExtensions
0x1800146d6  lea     rcx, a136141311217; "1.3.6.1.4.1.311.21.7"
0x1800146dd  call    cs:__imp_CertFindExtension
0x1800146e3  test    rax, rax
0x1800146e6  jz      loc_1800147EF
0x1800146ec  lea     rcx, [rbp+arg_8]
0x1800146f0  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x1800146f5  lea     rcx, [rbp+hMem]
0x1800146f9  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x1800146fe  mov     [rsp+50h+pDecodePara], rbx; pDecodePara
0x180014703  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x18001470b  mov     r9d, [rax+10h]; cbEncoded
0x18001470f  mov     r8, [rax+18h]; pbEncoded
0x180014713  lea     edx, [rbx+40h]; lpszStructType
0x180014716  mov     ecx, esi; dwCertEncodingType
0x180014718  call    cs:__imp_CryptDecodeObjectEx
0x18001471e  test    eax, eax
0x180014720  jnz     short loc_180014740
0x180014722  call    cs:__imp_GetLastError
0x180014728  mov     ebx, eax
0x18001472a  test    eax, eax
0x18001472c  jle     loc_1800147EF
0x180014732  movzx   ebx, ax
0x180014735  or      ebx, 80070000h
0x18001473b  jmp     loc_1800147EF
0x180014740  mov     rax, [rbp+hMem]
0x180014744  mov     rdx, [rax]; pvKey
0x180014747  test    rdx, rdx
0x18001474a  jnz     short loc_180014756
0x18001474c  mov     ebx, 80092004h
0x180014751  jmp     loc_1800147EF
0x180014756  xor     r8d, r8d; dwGroupId
0x180014759  mov     ecx, esi; dwKeyType
0x18001475b  call    cs:__imp_CryptFindOIDInfo
0x180014761  test    rax, rax
0x180014764  jz      short loc_180014779
0x180014766  mov     rdx, [rax+10h]; unsigned __int16 *
0x18001476a  test    rdx, rdx
0x18001476d  jz      short loc_180014779
0x18001476f  mov     rcx, rdi; this
0x180014772  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x180014777  jmp     short loc_1800147E3
0x180014779  mov     rax, [rbp+hMem]
0x18001477d  mov     r14, [rax]
0x180014780  test    r14, r14
0x180014783  jz      short loc_180014792
0x180014785  mov     rcx, r14; lpString
0x180014788  call    cs:__imp_lstrlenA
0x18001478e  mov     esi, eax
0x180014790  jmp     short loc_180014794
0x180014792  xor     esi, esi
0x180014794  mov     edx, esi; int
0x180014796  mov     rcx, rdi; this
0x180014799  call    ?AllocBeforeWrite@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBeforeWrite(int)
0x18001479e  test    eax, eax
0x1800147a0  jz      short loc_1800147E3
0x1800147a2  movsxd  rax, esi
0x1800147a5  add     rax, 1
0x1800147a9  mov     rsi, [rdi]
0x1800147ac  jnz     short loc_1800147B3
0x1800147ae  test    rsi, rsi
0x1800147b1  jnz     short loc_1800147DB
0x1800147b3  mov     dword ptr [rsp+50h+pDecodePara], eax; cchWideChar
0x1800147b7  mov     qword ptr [rsp+50h+dwFlags], rsi; lpWideCharStr
0x1800147bc  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800147c0  mov     r8, r14; lpMultiByteStr
0x1800147c3  xor     edx, edx; dwFlags
0x1800147c5  xor     ecx, ecx; CodePage
0x1800147c7  call    cs:__imp_MultiByteToWideChar
0x1800147cd  test    eax, eax
0x1800147cf  jle     short loc_1800147DB
0x1800147d1  movsxd  rcx, eax
0x1800147d4  xor     eax, eax
0x1800147d6  mov     [rsi+rcx*2-2], ax
0x1800147db  mov     rcx, rdi; this
0x1800147de  call    ?ReleaseBuffer@CString@WTL@@QEAAXH@Z; WTL::CString::ReleaseBuffer(int)
0x1800147e3  mov     eax, 8007000Eh
0x1800147e8  cmp     qword ptr [rdi], 0
0x1800147ec  cmovz   ebx, eax
0x1800147ef  mov     rcx, [rbp+hMem]; hMem
0x1800147f3  test    rcx, rcx
0x1800147f6  jz      short loc_1800147FE
0x1800147f8  call    cs:__imp_LocalFree
0x1800147fe  test    ebx, ebx
0x180014800  jns     short loc_180014816
0x180014802  mov     [rbp+pExceptionObject], ebx
0x180014805  lea     rdx, _TI1J; pThrowInfo
0x18001480c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014810  call    _CxxThrowException_0
0x180014816  mov     rax, rdi
0x180014819  add     rsp, 50h
0x18001481d  pop     r14
0x18001481f  pop     rdi
0x180014820  pop     rsi
0x180014821  pop     rbx
0x180014822  pop     rbp
0x180014823  retn
```
