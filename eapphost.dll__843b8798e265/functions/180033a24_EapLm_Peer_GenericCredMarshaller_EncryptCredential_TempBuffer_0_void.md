# EapLm::Peer::GenericCredMarshaller::EncryptCredential(TempBuffer<0> &,void *)

- ea: `0x180033a24`
- end: `0x180033d4d`
- name: `?EncryptCredential@GenericCredMarshaller@Peer@EapLm@@SAKAEAV?$TempBuffer@$0A@@@PEAX@Z`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014050`
- `0x180016ad0`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x180007564`
- `0x18000a24c`
- `0x18000b248`
- `0x180012660`
- `0x180030ed8`
- `0x180033a24`
- `0x180033d54`
- `0x180033da0`
- `0x180034230`
- `0x180035138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c8a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180033add`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180033add`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180033b27`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180033b27`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033c68`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033c68`
- `CRYPT32!CryptProtectData` at `0x180033bc9`
- `CRYPT32!CryptProtectData` at `0x180033bc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EapLm::Peer::GenericCredMarshaller::EncryptCredential(struct ConstBuffer *a1, void *a2)
{
  DWORD v4; // r14d
  _BYTE *v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r15
  DWORD LastError; // eax
  __int64 v10; // rdx
  EapHost::Peer::Host *v11; // rcx
  __int64 v12; // rax
  DWORD v13; // eax
  CHAR *v14; // rax
  __int64 j; // rax
  __int64 v16; // rdx
  __int64 v18; // rcx
  CHAR *v19; // rax
  LPCWCH v20; // rax
  __int64 v21; // rcx
  __int64 i; // rcx
  DWORD v23; // eax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-198h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-188h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+60h] [rbp-178h] BYREF
  __int128 v27; // [rsp+70h] [rbp-168h]
  void *v28; // [rsp+80h] [rbp-158h]
  CHAR MultiByteStr[272]; // [rsp+90h] [rbp-148h] BYREF

  v4 = 0;
  *(_OWORD *)lpWideCharStr = 0;
  v27 = 0;
  v28 = 0;
  EapLm::Peer::GenericCredMarshaller::Unmarshal(a1);
  v5 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( lpWideCharStr[1][v7] );
  if ( !v7 )
    goto LABEL_30;
  v8 = 257;
  memset_0(MultiByteStr, 0, 0x101u);
  if ( WideCharToMultiByte(0, 0x400u, 0, -1, MultiByteStr, 257, 0, 0) )
  {
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_24;
      }
      v10 = 15;
      goto LABEL_23;
    }
    *(&pDataIn.cbData + 1) = 0;
    pDataOut = 0;
    v12 = -1;
    do
      ++v12;
    while ( MultiByteStr[v12] );
    pDataIn.cbData = v12 + 1;
    pDataIn.pbData = (BYTE *)MultiByteStr;
    if ( CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
    {
      try
      {
        v28 = 0;
        DWORD2(v27) = 0;
        v28 = HeapAllocator::Alloc(pDataOut.cbData);
        memcpy_0(v28, pDataOut.pbData, pDataOut.cbData);
        DWORD2(v27) = pDataOut.cbData;
        EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
      }
      catch ( std::bad_alloc )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids);
        }
        v18 = 257;
        v19 = MultiByteStr;
        do
        {
          *v19++ = 0;
          --v18;
        }
        while ( v18 );
        v20 = lpWideCharStr[1];
        v21 = -1;
        do
          ++v21;
        while ( lpWideCharStr[1][v21] );
        for ( i = 2 * v21; i; --i )
        {
          *(_BYTE *)v20 = 0;
          v20 = (LPCWCH)((char *)v20 + 1);
        }
        DWORD2(v27) = 0;
        EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
        if ( !RevertToSelf()
          && WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v23);
        }
        throw;
      }
    }
    else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v13);
    }
    if ( RevertToSelf()
      || WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_24;
    }
    LastError = GetLastError();
    v4 = LastError;
    v10 = 19;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_24;
    }
    LastError = GetLastError();
    v10 = 14;
  }
  v11 = WPP_GLOBAL_Control;
LABEL_23:
  WPP_SF_d(*((_QWORD *)v11 + 2), v10, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, LastError);
LABEL_24:
  v14 = MultiByteStr;
  do
  {
    *v14++ = 0;
    --v8;
  }
  while ( v8 );
  do
    ++v6;
  while ( *(_WORD *)(2 * v6) );
  for ( j = 2 * v6; j; --j )
    *v5++ = 0;
  v16 = EapLm::Peer::GenericCredMarshaller::Marshal(&pDataIn, lpWideCharStr);
  TempBuffer<0>::Assign(a1, v16);
  HeapAllocator::Free(*(void **)&pDataIn.cbData);
LABEL_30:
  Free<HeapAllocator>(lpWideCharStr);
  return v4;
}

```

## disassembly

```asm
0x180033a24  mov     [rsp+arg_10], rbx
0x180033a29  mov     [rsp+arg_18], rsi
0x180033a2e  push    rdi
0x180033a2f  push    r12
0x180033a31  push    r13
0x180033a33  push    r14
0x180033a35  push    r15
0x180033a37  sub     rsp, 1B0h
0x180033a3e  mov     rax, cs:__security_cookie
0x180033a45  xor     rax, rsp
0x180033a48  mov     [rsp+1D8h+var_38], rax
0x180033a50  mov     rbx, rdx
0x180033a53  mov     r12, rcx
0x180033a56  xor     r13d, r13d
0x180033a59  mov     r14d, r13d
0x180033a5c  xorps   xmm0, xmm0
0x180033a5f  xor     eax, eax
0x180033a61  movups  xmmword ptr [rsp+1D8h+lpWideCharStr], xmm0
0x180033a66  movups  [rsp+1D8h+var_168], xmm0
0x180033a6b  mov     [rsp+1D8h+var_158], rax
0x180033a73  lea     rdx, [rsp+1D8h+lpWideCharStr]
0x180033a78  call    ?Unmarshal@GenericCredMarshaller@Peer@EapLm@@SAXAEBUConstBuffer@@AEAV?$crt_ref@U_GENERIC_USER_DATA@Peer@EapHost@@@@@Z; EapLm::Peer::GenericCredMarshaller::Unmarshal(ConstBuffer const &,crt_ref<EapHost::Peer::_GENERIC_USER_DATA> &)
0x180033a7d  mov     rdi, [rsp+1D8h+lpWideCharStr+8]
0x180033a82  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180033a86  mov     rax, rsi
0x180033a89  inc     rax
0x180033a8c  cmp     [rdi+rax*2], r13w
0x180033a91  jnz     short loc_180033A89
0x180033a93  test    rax, rax
0x180033a96  jz      loc_180033D12
0x180033a9c  mov     r15d, 101h
0x180033aa2  mov     r8d, r15d; Size
0x180033aa5  xor     edx, edx; Val
0x180033aa7  lea     rcx, [rsp+1D8h+MultiByteStr]; void *
0x180033aaf  call    memset_0
0x180033ab4  mov     [rsp+1D8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180033ab9  mov     [rsp+1D8h+lpDefaultChar], r13; lpDefaultChar
0x180033abe  mov     [rsp+1D8h+cbMultiByte], r15d; cbMultiByte
0x180033ac3  lea     rax, [rsp+1D8h+MultiByteStr]
0x180033acb  mov     [rsp+1D8h+lpMultiByteStr], rax; lpMultiByteStr
0x180033ad0  mov     r9d, esi; cchWideChar
0x180033ad3  mov     r8, rdi; lpWideCharStr
0x180033ad6  mov     edx, 400h; dwFlags
0x180033adb  xor     ecx, ecx; CodePage
0x180033add  call    cs:__imp_WideCharToMultiByte
0x180033ae4  nop     dword ptr [rax+rax+00h]
0x180033ae9  test    eax, eax
0x180033aeb  jnz     short loc_180033B24
0x180033aed  lea     rbx, WPP_GLOBAL_Control
0x180033af4  mov     rax, cs:WPP_GLOBAL_Control
0x180033afb  cmp     rax, rbx
0x180033afe  jz      loc_180033CB8
0x180033b04  test    byte ptr [rax+1Ch], 1
0x180033b08  jz      loc_180033CB8
0x180033b0e  call    cs:__imp_GetLastError
0x180033b15  nop     dword ptr [rax+rax+00h]
0x180033b1a  mov     edx, 0Eh
0x180033b1f  jmp     loc_180033C9E
0x180033b24  mov     rcx, rbx; hToken
0x180033b27  call    cs:__imp_ImpersonateLoggedOnUser
0x180033b2e  nop     dword ptr [rax+rax+00h]
0x180033b33  test    eax, eax
0x180033b35  jnz     short loc_180033B71
0x180033b37  call    cs:__imp_GetLastError
0x180033b3e  nop     dword ptr [rax+rax+00h]
0x180033b43  mov     r14d, eax
0x180033b46  lea     rbx, WPP_GLOBAL_Control
0x180033b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b54  cmp     rcx, rbx
0x180033b57  jz      loc_180033CB8
0x180033b5d  test    byte ptr [rcx+1Ch], 1
0x180033b61  jz      loc_180033CB8
0x180033b67  mov     edx, 0Fh
0x180033b6c  jmp     loc_180033CA5
0x180033b71  mov     dword ptr [rsp+1D8h+pDataIn+4], r13d
0x180033b76  xorps   xmm0, xmm0
0x180033b79  movups  xmmword ptr [rsp+1D8h+pDataOut.cbData], xmm0
0x180033b7e  lea     rcx, [rsp+1D8h+MultiByteStr]
0x180033b86  mov     rax, rsi
0x180033b89  inc     rax
0x180033b8c  cmp     [rcx+rax], r13b
0x180033b90  jnz     short loc_180033B89
0x180033b92  inc     eax
0x180033b94  mov     [rsp+1D8h+pDataIn.cbData], eax
0x180033b98  lea     rax, [rsp+1D8h+MultiByteStr]
0x180033ba0  mov     [rsp+1D8h+pDataIn.pbData], rax
0x180033ba5  lea     rax, [rsp+1D8h+pDataOut]
0x180033baa  mov     [rsp+1D8h+lpDefaultChar], rax; pDataOut
0x180033baf  mov     [rsp+1D8h+cbMultiByte], 1; dwFlags
0x180033bb7  mov     [rsp+1D8h+lpMultiByteStr], r13; pPromptStruct
0x180033bbc  xor     r9d, r9d; pvReserved
0x180033bbf  xor     r8d, r8d; pOptionalEntropy
0x180033bc2  xor     edx, edx; szDataDescr
0x180033bc4  lea     rcx, [rsp+1D8h+pDataIn]; pDataIn
0x180033bc9  call    cs:__imp_CryptProtectData
0x180033bd0  nop     dword ptr [rax+rax+00h]
0x180033bd5  test    eax, eax
0x180033bd7  jnz     short loc_180033C1F
0x180033bd9  lea     rbx, WPP_GLOBAL_Control
0x180033be0  mov     rax, cs:WPP_GLOBAL_Control
0x180033be7  cmp     rax, rbx
0x180033bea  jz      short loc_180033C68
0x180033bec  test    byte ptr [rax+1Ch], 1
0x180033bf0  jz      short loc_180033C68
0x180033bf2  call    cs:__imp_GetLastError
0x180033bf9  nop     dword ptr [rax+rax+00h]
0x180033bfe  mov     edx, 10h
0x180033c03  mov     r9d, eax
0x180033c06  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x180033c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c14  mov     rcx, [rcx+10h]
0x180033c18  call    WPP_SF_d
0x180033c1d  jmp     short loc_180033C68
0x180033c1f  mov     [rsp+1D8h+var_158], r13
0x180033c27  mov     dword ptr [rsp+1D8h+var_168+8], r13d
0x180033c2c  mov     ecx, [rsp+1D8h+pDataOut.cbData]; unsigned __int64
0x180033c30  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180033c35  mov     [rsp+1D8h+var_158], rax
0x180033c3d  mov     r8d, [rsp+1D8h+pDataOut.cbData]; Size
0x180033c42  mov     rdx, [rsp+1D8h+pDataOut.pbData]; Src
0x180033c47  mov     rcx, rax; void *
0x180033c4a  call    memcpy_0
0x180033c4f  mov     eax, [rsp+1D8h+pDataOut.cbData]
0x180033c53  mov     dword ptr [rsp+1D8h+var_168+8], eax
0x180033c57  lea     rcx, [rsp+1D8h+pDataOut]; struct _CRYPTOAPI_BLOB *
0x180033c5c  call    ?FreeCredential@GenericCredMarshaller@Peer@EapLm@@SAXPEAU_CRYPTOAPI_BLOB@@@Z; EapLm::Peer::GenericCredMarshaller::FreeCredential(_CRYPTOAPI_BLOB *)
0x180033c61  lea     rbx, WPP_GLOBAL_Control
0x180033c68  call    cs:__imp_RevertToSelf
0x180033c6f  nop     dword ptr [rax+rax+00h]
0x180033c74  test    eax, eax
0x180033c76  jnz     short loc_180033CB8
0x180033c78  mov     rax, cs:WPP_GLOBAL_Control
0x180033c7f  cmp     rax, rbx
0x180033c82  jz      short loc_180033CB8
0x180033c84  test    byte ptr [rax+1Ch], 1
0x180033c88  jz      short loc_180033CB8
0x180033c8a  call    cs:__imp_GetLastError
0x180033c91  nop     dword ptr [rax+rax+00h]
0x180033c96  mov     r14d, eax
0x180033c99  mov     edx, 13h
0x180033c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ca5  mov     r9d, eax
0x180033ca8  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x180033caf  mov     rcx, [rcx+10h]
0x180033cb3  call    WPP_SF_d
0x180033cb8  lea     rax, [rsp+1D8h+MultiByteStr]
0x180033cc0  mov     [rax], r13b
0x180033cc3  inc     rax
0x180033cc6  sub     r15, 1
0x180033cca  jnz     short loc_180033CC0
0x180033ccc  inc     rsi
0x180033ccf  cmp     [rdi+rsi*2], r13w
0x180033cd4  jnz     short loc_180033CCC
0x180033cd6  lea     rax, [rsi+rsi]
0x180033cda  test    rax, rax
0x180033cdd  jz      short loc_180033CEB
0x180033cdf  mov     [rdi], r13b
0x180033ce2  inc     rdi
0x180033ce5  sub     rax, 1
0x180033ce9  jnz     short loc_180033CDF
0x180033ceb  lea     rdx, [rsp+1D8h+lpWideCharStr]
0x180033cf0  lea     rcx, [rsp+1D8h+pDataIn]
0x180033cf5  call    ?Marshal@GenericCredMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@AEBU_GENERIC_USER_DATA@2EapHost@@@Z; EapLm::Peer::GenericCredMarshaller::Marshal(EapHost::Peer::_GENERIC_USER_DATA const &)
0x180033cfa  nop
0x180033cfb  mov     rdx, rax
0x180033cfe  mov     rcx, r12
0x180033d01  call    ?Assign@?$TempBuffer@$0A@@@AEAAXAEBV1@@Z; TempBuffer<0>::Assign(TempBuffer<0> const &)
0x180033d06  nop
0x180033d07  mov     rcx, qword ptr [rsp+1D8h+pDataIn.cbData]; void *
0x180033d0c  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180033d11  nop
0x180033d12  lea     rcx, [rsp+1D8h+lpWideCharStr]
0x180033d17  call    ??$Free@VHeapAllocator@@@@YAXAEAU_GENERIC_USER_DATA@Peer@EapHost@@@Z; Free<HeapAllocator>(EapHost::Peer::_GENERIC_USER_DATA &)
0x180033d1c  mov     eax, r14d
0x180033d1f  mov     rcx, [rsp+1D8h+var_38]
0x180033d27  xor     rcx, rsp; StackCookie
0x180033d2a  call    __security_check_cookie
0x180033d2f  lea     r11, [rsp+1D8h+var_28]
0x180033d37  mov     rbx, [r11+40h]
0x180033d3b  mov     rsi, [r11+48h]
0x180033d3f  mov     rsp, r11
0x180033d42  pop     r15
0x180033d44  pop     r14
0x180033d46  pop     r13
0x180033d48  pop     r12
0x180033d4a  pop     rdi
0x180033d4b  retn
```
