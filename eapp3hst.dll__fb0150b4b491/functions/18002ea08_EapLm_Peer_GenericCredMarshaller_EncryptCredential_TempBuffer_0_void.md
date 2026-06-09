# EapLm::Peer::GenericCredMarshaller::EncryptCredential(TempBuffer<0> &,void *)

- ea: `0x18002ea08`
- end: `0x18002ed00`
- name: `?EncryptCredential@GenericCredMarshaller@Peer@EapLm@@SAKAEAV?$TempBuffer@$0A@@@PEAX@Z`
- size: `760`
- prototype: `__int64 __fastcall(struct ConstBuffer *, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024200`
- `0x180026ac0`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x180003e38`
- `0x18000439c`
- `0x18000bf94`
- `0x18001267c`
- `0x180022c84`
- `0x18002ea08`
- `0x18002ed08`
- `0x18002ed50`
- `0x18002ef54`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002eac1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002eac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eaec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eaec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec44`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ec28`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ec28`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002eaff`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002eaff`
- `CRYPT32!CryptProtectData` at `0x18002eb95`
- `CRYPT32!CryptProtectData` at `0x18002eb95`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::GenericCredMarshaller::EncryptCredential(struct ConstBuffer *a1, void *a2)
{
  DWORD v4; // r14d
  _BYTE *v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r15
  DWORD LastError; // eax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
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
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
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
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v28 = 0;
        DWORD2(v27) = 0;
        v28 = HeapAllocator::Alloc(pDataOut.cbData);
        memcpy_0(v28, pDataOut.pbData, pDataOut.cbData);
        DWORD2(v27) = pDataOut.cbData;
        EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids);
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
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v23 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v23);
          }
          throw;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v13);
    }
    if ( RevertToSelf()
      || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
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
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    LastError = GetLastError();
    v10 = 14;
  }
  v11 = WPP_GLOBAL_Control;
LABEL_23:
  WPP_SF_d(v11[2], v10, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, LastError);
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
  TempBuffer<0>::Assign((__int64)a1, v16);
  HeapAllocator::Free(*(void **)&pDataIn.cbData);
LABEL_30:
  Free<HeapAllocator>(lpWideCharStr);
  return v4;
}

```

## disassembly

```asm
0x18002ea08  mov     [rsp+arg_10], rbx
0x18002ea0d  mov     [rsp+arg_18], rsi
0x18002ea12  push    rdi
0x18002ea13  push    r12
0x18002ea15  push    r13
0x18002ea17  push    r14
0x18002ea19  push    r15
0x18002ea1b  sub     rsp, 1B0h
0x18002ea22  mov     rax, cs:__security_cookie
0x18002ea29  xor     rax, rsp
0x18002ea2c  mov     [rsp+1D8h+var_38], rax
0x18002ea34  mov     rbx, rdx
0x18002ea37  mov     r12, rcx
0x18002ea3a  xor     r13d, r13d
0x18002ea3d  mov     r14d, r13d
0x18002ea40  xorps   xmm0, xmm0
0x18002ea43  xor     eax, eax
0x18002ea45  movups  xmmword ptr [rsp+1D8h+lpWideCharStr], xmm0
0x18002ea4a  movups  [rsp+1D8h+var_168], xmm0
0x18002ea4f  mov     [rsp+1D8h+var_158], rax
0x18002ea57  lea     rdx, [rsp+1D8h+lpWideCharStr]
0x18002ea5c  call    ?Unmarshal@GenericCredMarshaller@Peer@EapLm@@SAXAEBUConstBuffer@@AEAV?$crt_ref@U_GENERIC_USER_DATA@Peer@EapHost@@@@@Z; EapLm::Peer::GenericCredMarshaller::Unmarshal(ConstBuffer const &,crt_ref<EapHost::Peer::_GENERIC_USER_DATA> &)
0x18002ea61  mov     rdi, [rsp+1D8h+lpWideCharStr+8]
0x18002ea66  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ea6a  mov     rax, rsi
0x18002ea6d  inc     rax
0x18002ea70  cmp     [rdi+rax*2], r13w
0x18002ea75  jnz     short loc_18002EA6D
0x18002ea77  test    rax, rax
0x18002ea7a  jz      loc_18002ECC6
0x18002ea80  mov     r15d, 101h
0x18002ea86  mov     r8d, r15d; Size
0x18002ea89  xor     edx, edx; Val
0x18002ea8b  lea     rcx, [rsp+1D8h+MultiByteStr]; void *
0x18002ea93  call    memset_0
0x18002ea98  mov     [rsp+1D8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18002ea9d  mov     [rsp+1D8h+lpDefaultChar], r13; lpDefaultChar
0x18002eaa2  mov     [rsp+1D8h+cbMultiByte], r15d; cbMultiByte
0x18002eaa7  lea     rax, [rsp+1D8h+MultiByteStr]
0x18002eaaf  mov     [rsp+1D8h+lpMultiByteStr], rax; lpMultiByteStr
0x18002eab4  mov     r9d, esi; cchWideChar
0x18002eab7  mov     r8, rdi; lpWideCharStr
0x18002eaba  mov     edx, 400h; dwFlags
0x18002eabf  xor     ecx, ecx; CodePage
0x18002eac1  call    cs:__imp_WideCharToMultiByte
0x18002eac7  test    eax, eax
0x18002eac9  jnz     short loc_18002EAFC
0x18002eacb  lea     rbx, WPP_GLOBAL_Control
0x18002ead2  mov     rax, cs:WPP_GLOBAL_Control
0x18002ead9  cmp     rax, rbx
0x18002eadc  jz      loc_18002EC6C
0x18002eae2  test    byte ptr [rax+1Ch], 1
0x18002eae6  jz      loc_18002EC6C
0x18002eaec  call    cs:__imp_GetLastError
0x18002eaf2  mov     edx, 0Eh
0x18002eaf7  jmp     loc_18002EC52
0x18002eafc  mov     rcx, rbx; hToken
0x18002eaff  call    cs:__imp_ImpersonateLoggedOnUser
0x18002eb05  test    eax, eax
0x18002eb07  jnz     short loc_18002EB3D
0x18002eb09  call    cs:__imp_GetLastError
0x18002eb0f  mov     r14d, eax
0x18002eb12  lea     rbx, WPP_GLOBAL_Control
0x18002eb19  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb20  cmp     rcx, rbx
0x18002eb23  jz      loc_18002EC6C
0x18002eb29  test    byte ptr [rcx+1Ch], 1
0x18002eb2d  jz      loc_18002EC6C
0x18002eb33  mov     edx, 0Fh
0x18002eb38  jmp     loc_18002EC59
0x18002eb3d  mov     dword ptr [rsp+1D8h+pDataIn+4], r13d
0x18002eb42  xorps   xmm0, xmm0
0x18002eb45  movups  xmmword ptr [rsp+1D8h+pDataOut.cbData], xmm0
0x18002eb4a  lea     rcx, [rsp+1D8h+MultiByteStr]
0x18002eb52  mov     rax, rsi
0x18002eb55  inc     rax
0x18002eb58  cmp     [rcx+rax], r13b
0x18002eb5c  jnz     short loc_18002EB55
0x18002eb5e  inc     eax
0x18002eb60  mov     [rsp+1D8h+pDataIn.cbData], eax
0x18002eb64  lea     rax, [rsp+1D8h+MultiByteStr]
0x18002eb6c  mov     [rsp+1D8h+pDataIn.pbData], rax
0x18002eb71  lea     rax, [rsp+1D8h+pDataOut]
0x18002eb76  mov     [rsp+1D8h+lpDefaultChar], rax; pDataOut
0x18002eb7b  mov     [rsp+1D8h+cbMultiByte], 1; dwFlags
0x18002eb83  mov     [rsp+1D8h+lpMultiByteStr], r13; pPromptStruct
0x18002eb88  xor     r9d, r9d; pvReserved
0x18002eb8b  xor     r8d, r8d; pOptionalEntropy
0x18002eb8e  xor     edx, edx; szDataDescr
0x18002eb90  lea     rcx, [rsp+1D8h+pDataIn]; pDataIn
0x18002eb95  call    cs:__imp_CryptProtectData
0x18002eb9b  test    eax, eax
0x18002eb9d  jnz     short loc_18002EBDF
0x18002eb9f  lea     rbx, WPP_GLOBAL_Control
0x18002eba6  mov     rax, cs:WPP_GLOBAL_Control
0x18002ebad  cmp     rax, rbx
0x18002ebb0  jz      short loc_18002EC28
0x18002ebb2  test    byte ptr [rax+1Ch], 1
0x18002ebb6  jz      short loc_18002EC28
0x18002ebb8  call    cs:__imp_GetLastError
0x18002ebbe  mov     edx, 10h
0x18002ebc3  mov     r9d, eax
0x18002ebc6  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18002ebcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebd4  mov     rcx, [rcx+10h]
0x18002ebd8  call    WPP_SF_d
0x18002ebdd  jmp     short loc_18002EC28
0x18002ebdf  mov     [rsp+1D8h+var_158], r13
0x18002ebe7  mov     dword ptr [rsp+1D8h+var_168+8], r13d
0x18002ebec  mov     ecx, [rsp+1D8h+pDataOut.cbData]; unsigned __int64
0x18002ebf0  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18002ebf5  mov     [rsp+1D8h+var_158], rax
0x18002ebfd  mov     r8d, [rsp+1D8h+pDataOut.cbData]; Size
0x18002ec02  mov     rdx, [rsp+1D8h+pDataOut.pbData]; Src
0x18002ec07  mov     rcx, rax; void *
0x18002ec0a  call    memcpy_0
0x18002ec0f  mov     eax, [rsp+1D8h+pDataOut.cbData]
0x18002ec13  mov     dword ptr [rsp+1D8h+var_168+8], eax
0x18002ec17  lea     rcx, [rsp+1D8h+pDataOut]; struct _CRYPTOAPI_BLOB *
0x18002ec1c  call    ?FreeCredential@GenericCredMarshaller@Peer@EapLm@@SAXPEAU_CRYPTOAPI_BLOB@@@Z; EapLm::Peer::GenericCredMarshaller::FreeCredential(_CRYPTOAPI_BLOB *)
0x18002ec21  lea     rbx, WPP_GLOBAL_Control
0x18002ec28  call    cs:__imp_RevertToSelf
0x18002ec2e  test    eax, eax
0x18002ec30  jnz     short loc_18002EC6C
0x18002ec32  mov     rax, cs:WPP_GLOBAL_Control
0x18002ec39  cmp     rax, rbx
0x18002ec3c  jz      short loc_18002EC6C
0x18002ec3e  test    byte ptr [rax+1Ch], 1
0x18002ec42  jz      short loc_18002EC6C
0x18002ec44  call    cs:__imp_GetLastError
0x18002ec4a  mov     r14d, eax
0x18002ec4d  mov     edx, 13h
0x18002ec52  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec59  mov     r9d, eax
0x18002ec5c  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18002ec63  mov     rcx, [rcx+10h]
0x18002ec67  call    WPP_SF_d
0x18002ec6c  lea     rax, [rsp+1D8h+MultiByteStr]
0x18002ec74  mov     [rax], r13b
0x18002ec77  inc     rax
0x18002ec7a  sub     r15, 1
0x18002ec7e  jnz     short loc_18002EC74
0x18002ec80  inc     rsi
0x18002ec83  cmp     [rdi+rsi*2], r13w
0x18002ec88  jnz     short loc_18002EC80
0x18002ec8a  lea     rax, [rsi+rsi]
0x18002ec8e  test    rax, rax
0x18002ec91  jz      short loc_18002EC9F
0x18002ec93  mov     [rdi], r13b
0x18002ec96  inc     rdi
0x18002ec99  sub     rax, 1
0x18002ec9d  jnz     short loc_18002EC93
0x18002ec9f  lea     rdx, [rsp+1D8h+lpWideCharStr]
0x18002eca4  lea     rcx, [rsp+1D8h+pDataIn]
0x18002eca9  call    ?Marshal@GenericCredMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@AEBU_GENERIC_USER_DATA@2EapHost@@@Z; EapLm::Peer::GenericCredMarshaller::Marshal(EapHost::Peer::_GENERIC_USER_DATA const &)
0x18002ecae  nop
0x18002ecaf  mov     rdx, rax
0x18002ecb2  mov     rcx, r12
0x18002ecb5  call    ?Assign@?$TempBuffer@$0A@@@AEAAXAEBV1@@Z; TempBuffer<0>::Assign(TempBuffer<0> const &)
0x18002ecba  nop
0x18002ecbb  mov     rcx, qword ptr [rsp+1D8h+pDataIn.cbData]; void *
0x18002ecc0  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ecc5  nop
0x18002ecc6  lea     rcx, [rsp+1D8h+lpWideCharStr]
0x18002eccb  call    ??$Free@VHeapAllocator@@@@YAXAEAU_GENERIC_USER_DATA@Peer@EapHost@@@Z; Free<HeapAllocator>(EapHost::Peer::_GENERIC_USER_DATA &)
0x18002ecd0  mov     eax, r14d
0x18002ecd3  mov     rcx, [rsp+1D8h+var_38]
0x18002ecdb  xor     rcx, rsp; StackCookie
0x18002ecde  call    __security_check_cookie
0x18002ece3  lea     r11, [rsp+1D8h+var_28]
0x18002eceb  mov     rbx, [r11+40h]
0x18002ecef  mov     rsi, [r11+48h]
0x18002ecf3  mov     rsp, r11
0x18002ecf6  pop     r15
0x18002ecf8  pop     r14
0x18002ecfa  pop     r13
0x18002ecfc  pop     r12
0x18002ecfe  pop     rdi
0x18002ecff  retn
```
