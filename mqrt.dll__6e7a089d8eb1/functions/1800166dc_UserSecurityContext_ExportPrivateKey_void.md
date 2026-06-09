# UserSecurityContext::ExportPrivateKey(void)

- ea: `0x1800166dc`
- end: `0x1800168ee`
- name: `?ExportPrivateKey@UserSecurityContext@@QEAAJXZ`
- size: `530`
- prototype: `__int64 __fastcall(UserSecurityContext *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180017728`

## callees

- `0x1800087f8`
- `0x180013c74`
- `0x180013d20`
- `0x18001620c`
- `0x1800166dc`
- `0x1800175c0`
- `0x180021010`
- `0x180026010`

## import_xrefs

- `ADVAPI32!CryptExportKey` at `0x1800167a9`
- `ADVAPI32!CryptExportKey` at `0x180016847`
- `ADVAPI32!CryptExportKey` at `0x1800167a9`
- `ADVAPI32!CryptExportKey` at `0x180016847`
- `ADVAPI32!CryptGetUserKey` at `0x18001670b`
- `ADVAPI32!CryptGetUserKey` at `0x18001670b`
- `KERNEL32!GetLastError` at `0x180016715`
- `KERNEL32!GetLastError` at `0x18001671d`
- `KERNEL32!GetLastError` at `0x1800167b3`
- `KERNEL32!GetLastError` at `0x1800167bb`
- `KERNEL32!GetLastError` at `0x180016851`
- `KERNEL32!GetLastError` at `0x180016859`
- `KERNEL32!GetLastError` at `0x180016715`
- `KERNEL32!GetLastError` at `0x18001671d`
- `KERNEL32!GetLastError` at `0x1800167b3`
- `KERNEL32!GetLastError` at `0x1800167bb`
- `KERNEL32!GetLastError` at `0x180016851`
- `KERNEL32!GetLastError` at `0x180016859`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserSecurityContext::ExportPrivateKey(UserSecurityContext *this)
{
  DWORD v2; // ebx
  HCRYPTPROV v3; // rax
  DWORD v4; // ebx
  DWORD v5; // eax
  unsigned __int16 v6; // r8
  DWORD v7; // ebx
  DWORD v8; // eax
  unsigned __int64 v9; // rcx
  BYTE *pbData; // rax
  DWORD LastError; // ebx
  DWORD v12; // eax
  unsigned int v13; // ebx
  DWORD pdwDataLen; // [rsp+40h] [rbp+8h] BYREF
  HCRYPTKEY phUserKey; // [rsp+48h] [rbp+10h] BYREF

  phUserKey = 0;
  v2 = *((_DWORD *)this + 16);
  v3 = (*(__int64 (__fastcall **)(UserSecurityContext *))(*(_QWORD *)this + 16LL))(this);
  if ( CryptGetUserKey(v3, v2, &phUserKey) )
  {
    pdwDataLen = 0;
    if ( CryptExportKey(phUserKey, 0, 7u, 0, 0, &pdwDataLen) )
    {
      v9 = pdwDataLen;
      *((_DWORD *)this + 24) = pdwDataLen;
      pbData = (BYTE *)MmAllocate(v9);
      *((_QWORD *)this + 11) = pbData;
      if ( CryptExportKey(phUserKey, 0, 7u, 0, pbData, &pdwDataLen) )
      {
        UserSecurityContext::ReleaseNonCacheableCryptoProvider(this);
        *((_BYTE *)this + 80) = 1;
        v13 = 0;
        goto LABEL_24;
      }
      LastError = GetLastError();
      v12 = GetLastError();
      if ( v12 )
        LogMsgNTStatus(v12, (wchar_t *)L"rt/rtsecctx", 0x77u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, LastError);
      v6 = 480;
    }
    else
    {
      v7 = GetLastError();
      v8 = GetLastError();
      if ( v8 )
        LogMsgNTStatus(v8, (wchar_t *)L"rt/rtsecctx", 0x1CCu);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v7);
      v6 = 470;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = GetLastError();
    if ( v5 )
      LogMsgNTStatus(v5, (wchar_t *)L"rt/rtsecctx", 0x63u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 15, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v4);
    v6 = 450;
  }
  v13 = -1072824272;
  LogMsgHR(-1072824272, (wchar_t *)L"rt/rtsecctx", v6);
LABEL_24:
  CHCryptKey::~CHCryptKey((CHCryptKey *)&phUserKey);
  return v13;
}

```

## disassembly

```asm
0x1800166dc  mov     [rsp+arg_10], rbx
0x1800166e1  push    rdi
0x1800166e2  sub     rsp, 30h
0x1800166e6  mov     rdi, rcx
0x1800166e9  mov     [rsp+38h+phUserKey], 0
0x1800166f2  mov     ebx, [rcx+40h]
0x1800166f5  mov     rax, [rcx]
0x1800166f8  mov     rax, [rax+10h]
0x1800166fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016701  lea     r8, [rsp+38h+phUserKey]; phUserKey
0x180016706  mov     edx, ebx; dwKeySpec
0x180016708  mov     rcx, rax; hProv
0x18001670b  call    cs:__imp_CryptGetUserKey
0x180016711  test    eax, eax
0x180016713  jnz     short loc_18001677D
0x180016715  call    cs:__imp_GetLastError
0x18001671b  mov     ebx, eax
0x18001671d  call    cs:__imp_GetLastError
0x180016723  test    eax, eax
0x180016725  jz      short loc_18001673B
0x180016727  mov     r8d, 63h ; 'c'; unsigned __int16
0x18001672d  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016734  mov     ecx, eax; int
0x180016736  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001673b  lea     rdx, WPP_GLOBAL_Control
0x180016742  mov     rcx, cs:WPP_GLOBAL_Control
0x180016749  cmp     rcx, rdx
0x18001674c  jz      short loc_180016772
0x18001674e  test    byte ptr [rcx+10Ch], 1
0x180016755  jz      short loc_180016772
0x180016757  mov     edx, 0Fh
0x18001675c  mov     r9d, ebx
0x18001675f  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180016766  mov     rcx, [rcx+100h]
0x18001676d  call    WPP_SF_d
0x180016772  mov     r8d, 1C2h
0x180016778  jmp     loc_1800168B4
0x18001677d  mov     [rsp+38h+arg_0], 0
0x180016785  lea     rax, [rsp+38h+arg_0]
0x18001678a  mov     [rsp+38h+pdwDataLen], rax; pdwDataLen
0x18001678f  mov     [rsp+38h+pbData], 0; pbData
0x180016798  xor     r9d, r9d; dwFlags
0x18001679b  lea     ebx, [r9+7]
0x18001679f  mov     r8d, ebx; dwBlobType
0x1800167a2  xor     edx, edx; hExpKey
0x1800167a4  mov     rcx, [rsp+38h+phUserKey]; hKey
0x1800167a9  call    cs:__imp_CryptExportKey
0x1800167af  test    eax, eax
0x1800167b1  jnz     short loc_18001681B
0x1800167b3  call    cs:__imp_GetLastError
0x1800167b9  mov     ebx, eax
0x1800167bb  call    cs:__imp_GetLastError
0x1800167c1  test    eax, eax
0x1800167c3  jz      short loc_1800167D9
0x1800167c5  mov     r8d, 1CCh; unsigned __int16
0x1800167cb  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800167d2  mov     ecx, eax; int
0x1800167d4  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x1800167d9  lea     rdx, WPP_GLOBAL_Control
0x1800167e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167e7  cmp     rcx, rdx
0x1800167ea  jz      short loc_180016810
0x1800167ec  test    byte ptr [rcx+10Ch], 1
0x1800167f3  jz      short loc_180016810
0x1800167f5  mov     edx, 10h
0x1800167fa  mov     r9d, ebx
0x1800167fd  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180016804  mov     rcx, [rcx+100h]
0x18001680b  call    WPP_SF_d
0x180016810  mov     r8d, 1D6h
0x180016816  jmp     loc_1800168B4
0x18001681b  mov     ecx, [rsp+38h+arg_0]; unsigned __int64
0x18001681f  mov     [rdi+60h], ecx
0x180016822  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016827  mov     [rdi+58h], rax
0x18001682b  lea     rcx, [rsp+38h+arg_0]
0x180016830  mov     [rsp+38h+pdwDataLen], rcx; pdwDataLen
0x180016835  mov     [rsp+38h+pbData], rax; pbData
0x18001683a  xor     r9d, r9d; dwFlags
0x18001683d  mov     r8d, ebx; dwBlobType
0x180016840  xor     edx, edx; hExpKey
0x180016842  mov     rcx, [rsp+38h+phUserKey]; hKey
0x180016847  call    cs:__imp_CryptExportKey
0x18001684d  test    eax, eax
0x18001684f  jnz     short loc_1800168C9
0x180016851  call    cs:__imp_GetLastError
0x180016857  mov     ebx, eax
0x180016859  call    cs:__imp_GetLastError
0x18001685f  test    eax, eax
0x180016861  jz      short loc_180016877
0x180016863  mov     r8d, 77h ; 'w'; unsigned __int16
0x180016869  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016870  mov     ecx, eax; int
0x180016872  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180016877  lea     rdx, WPP_GLOBAL_Control
0x18001687e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016885  cmp     rcx, rdx
0x180016888  jz      short loc_1800168AE
0x18001688a  test    byte ptr [rcx+10Ch], 1
0x180016891  jz      short loc_1800168AE
0x180016893  mov     edx, 11h
0x180016898  mov     r9d, ebx
0x18001689b  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x1800168a2  mov     rcx, [rcx+100h]
0x1800168a9  call    WPP_SF_d
0x1800168ae  mov     r8d, 1E0h; unsigned __int16
0x1800168b4  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800168bb  mov     ebx, 0C00E0030h
0x1800168c0  mov     ecx, ebx; int
0x1800168c2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800168c7  jmp     short loc_1800168D7
0x1800168c9  mov     rcx, rdi; this
0x1800168cc  call    ?ReleaseNonCacheableCryptoProvider@UserSecurityContext@@AEAAXXZ; UserSecurityContext::ReleaseNonCacheableCryptoProvider(void)
0x1800168d1  mov     byte ptr [rdi+50h], 1
0x1800168d5  xor     ebx, ebx
0x1800168d7  lea     rcx, [rsp+38h+phUserKey]; this
0x1800168dc  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x1800168e1  mov     eax, ebx
0x1800168e3  mov     rbx, [rsp+38h+arg_10]
0x1800168e8  add     rsp, 30h
0x1800168ec  pop     rdi
0x1800168ed  retn
```
