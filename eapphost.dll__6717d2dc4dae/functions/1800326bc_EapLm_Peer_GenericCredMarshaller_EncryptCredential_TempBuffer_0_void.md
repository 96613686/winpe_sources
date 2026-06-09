# EapLm::Peer::GenericCredMarshaller::EncryptCredential(TempBuffer<0> &,void *)

- ea: `0x1800326bc`
- end: `0x1800329b4`
- name: `?EncryptCredential@GenericCredMarshaller@Peer@EapLm@@SAKAEAV?$TempBuffer@$0A@@@PEAX@Z`
- size: `760`
- prototype: `__int64 __fastcall(struct ConstBuffer *, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013860`
- `0x180016250`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x1800072cc`
- `0x180009dec`
- `0x18000ada8`
- `0x180011ee8`
- `0x18002fcc8`
- `0x1800326bc`
- `0x1800329bc`
- `0x180032a04`
- `0x180032e90`
- `0x180033d78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003286c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003286c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180032775`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180032775`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800327b3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800327b3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800328dc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800328dc`
- `CRYPT32!CryptProtectData` at `0x180032849`
- `CRYPT32!CryptProtectData` at `0x180032849`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  TempBuffer<0>::Assign((__int64)a1, v16);
  HeapAllocator::Free(*(void **)&pDataIn.cbData);
LABEL_30:
  Free<HeapAllocator>(lpWideCharStr);
  return v4;
}

```

## disassembly

```asm
0x1800326bc  mov     [rsp+arg_10], rbx
0x1800326c1  mov     [rsp+arg_18], rsi
0x1800326c6  push    rdi
0x1800326c7  push    r12
0x1800326c9  push    r13
0x1800326cb  push    r14
0x1800326cd  push    r15
0x1800326cf  sub     rsp, 1B0h
0x1800326d6  mov     rax, cs:__security_cookie
0x1800326dd  xor     rax, rsp
0x1800326e0  mov     [rsp+1D8h+var_38], rax
0x1800326e8  mov     rbx, rdx
0x1800326eb  mov     r12, rcx
0x1800326ee  xor     r13d, r13d
0x1800326f1  mov     r14d, r13d
0x1800326f4  xorps   xmm0, xmm0
0x1800326f7  xor     eax, eax
0x1800326f9  movups  xmmword ptr [rsp+1D8h+lpWideCharStr], xmm0
0x1800326fe  movups  [rsp+1D8h+var_168], xmm0
0x180032703  mov     [rsp+1D8h+var_158], rax
0x18003270b  lea     rdx, [rsp+1D8h+lpWideCharStr]
0x180032710  call    ?Unmarshal@GenericCredMarshaller@Peer@EapLm@@SAXAEBUConstBuffer@@AEAV?$crt_ref@U_GENERIC_USER_DATA@Peer@EapHost@@@@@Z; EapLm::Peer::GenericCredMarshaller::Unmarshal(ConstBuffer const &,crt_ref<EapHost::Peer::_GENERIC_USER_DATA> &)
0x180032715  mov     rdi, [rsp+1D8h+lpWideCharStr+8]
0x18003271a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003271e  mov     rax, rsi
0x180032721  inc     rax
0x180032724  cmp     [rdi+rax*2], r13w
0x180032729  jnz     short loc_180032721
0x18003272b  test    rax, rax
0x18003272e  jz      loc_18003297A
0x180032734  mov     r15d, 101h
0x18003273a  mov     r8d, r15d; Size
0x18003273d  xor     edx, edx; Val
0x18003273f  lea     rcx, [rsp+1D8h+MultiByteStr]; void *
0x180032747  call    memset_0
0x18003274c  mov     [rsp+1D8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180032751  mov     [rsp+1D8h+lpDefaultChar], r13; lpDefaultChar
0x180032756  mov     [rsp+1D8h+cbMultiByte], r15d; cbMultiByte
0x18003275b  lea     rax, [rsp+1D8h+MultiByteStr]
0x180032763  mov     [rsp+1D8h+lpMultiByteStr], rax; lpMultiByteStr
0x180032768  mov     r9d, esi; cchWideChar
0x18003276b  mov     r8, rdi; lpWideCharStr
0x18003276e  mov     edx, 400h; dwFlags
0x180032773  xor     ecx, ecx; CodePage
0x180032775  call    cs:__imp_WideCharToMultiByte
0x18003277b  test    eax, eax
0x18003277d  jnz     short loc_1800327B0
0x18003277f  lea     rbx, WPP_GLOBAL_Control
0x180032786  mov     rax, cs:WPP_GLOBAL_Control
0x18003278d  cmp     rax, rbx
0x180032790  jz      loc_180032920
0x180032796  test    byte ptr [rax+1Ch], 1
0x18003279a  jz      loc_180032920
0x1800327a0  call    cs:__imp_GetLastError
0x1800327a6  mov     edx, 0Eh
0x1800327ab  jmp     loc_180032906
0x1800327b0  mov     rcx, rbx; hToken
0x1800327b3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800327b9  test    eax, eax
0x1800327bb  jnz     short loc_1800327F1
0x1800327bd  call    cs:__imp_GetLastError
0x1800327c3  mov     r14d, eax
0x1800327c6  lea     rbx, WPP_GLOBAL_Control
0x1800327cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327d4  cmp     rcx, rbx
0x1800327d7  jz      loc_180032920
0x1800327dd  test    byte ptr [rcx+1Ch], 1
0x1800327e1  jz      loc_180032920
0x1800327e7  mov     edx, 0Fh
0x1800327ec  jmp     loc_18003290D
0x1800327f1  mov     dword ptr [rsp+1D8h+pDataIn+4], r13d
0x1800327f6  xorps   xmm0, xmm0
0x1800327f9  movups  xmmword ptr [rsp+1D8h+pDataOut.cbData], xmm0
0x1800327fe  lea     rcx, [rsp+1D8h+MultiByteStr]
0x180032806  mov     rax, rsi
0x180032809  inc     rax
0x18003280c  cmp     [rcx+rax], r13b
0x180032810  jnz     short loc_180032809
0x180032812  inc     eax
0x180032814  mov     [rsp+1D8h+pDataIn.cbData], eax
0x180032818  lea     rax, [rsp+1D8h+MultiByteStr]
0x180032820  mov     [rsp+1D8h+pDataIn.pbData], rax
0x180032825  lea     rax, [rsp+1D8h+pDataOut]
0x18003282a  mov     [rsp+1D8h+lpDefaultChar], rax; pDataOut
0x18003282f  mov     [rsp+1D8h+cbMultiByte], 1; dwFlags
0x180032837  mov     [rsp+1D8h+lpMultiByteStr], r13; pPromptStruct
0x18003283c  xor     r9d, r9d; pvReserved
0x18003283f  xor     r8d, r8d; pOptionalEntropy
0x180032842  xor     edx, edx; szDataDescr
0x180032844  lea     rcx, [rsp+1D8h+pDataIn]; pDataIn
0x180032849  call    cs:__imp_CryptProtectData
0x18003284f  test    eax, eax
0x180032851  jnz     short loc_180032893
0x180032853  lea     rbx, WPP_GLOBAL_Control
0x18003285a  mov     rax, cs:WPP_GLOBAL_Control
0x180032861  cmp     rax, rbx
0x180032864  jz      short loc_1800328DC
0x180032866  test    byte ptr [rax+1Ch], 1
0x18003286a  jz      short loc_1800328DC
0x18003286c  call    cs:__imp_GetLastError
0x180032872  mov     edx, 10h
0x180032877  mov     r9d, eax
0x18003287a  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x180032881  mov     rcx, cs:WPP_GLOBAL_Control
0x180032888  mov     rcx, [rcx+10h]
0x18003288c  call    WPP_SF_d
0x180032891  jmp     short loc_1800328DC
0x180032893  mov     [rsp+1D8h+var_158], r13
0x18003289b  mov     dword ptr [rsp+1D8h+var_168+8], r13d
0x1800328a0  mov     ecx, [rsp+1D8h+pDataOut.cbData]; unsigned __int64
0x1800328a4  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800328a9  mov     [rsp+1D8h+var_158], rax
0x1800328b1  mov     r8d, [rsp+1D8h+pDataOut.cbData]; Size
0x1800328b6  mov     rdx, [rsp+1D8h+pDataOut.pbData]; Src
0x1800328bb  mov     rcx, rax; void *
0x1800328be  call    memcpy_0
0x1800328c3  mov     eax, [rsp+1D8h+pDataOut.cbData]
0x1800328c7  mov     dword ptr [rsp+1D8h+var_168+8], eax
0x1800328cb  lea     rcx, [rsp+1D8h+pDataOut]; struct _CRYPTOAPI_BLOB *
0x1800328d0  call    ?FreeCredential@GenericCredMarshaller@Peer@EapLm@@SAXPEAU_CRYPTOAPI_BLOB@@@Z; EapLm::Peer::GenericCredMarshaller::FreeCredential(_CRYPTOAPI_BLOB *)
0x1800328d5  lea     rbx, WPP_GLOBAL_Control
0x1800328dc  call    cs:__imp_RevertToSelf
0x1800328e2  test    eax, eax
0x1800328e4  jnz     short loc_180032920
0x1800328e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800328ed  cmp     rax, rbx
0x1800328f0  jz      short loc_180032920
0x1800328f2  test    byte ptr [rax+1Ch], 1
0x1800328f6  jz      short loc_180032920
0x1800328f8  call    cs:__imp_GetLastError
0x1800328fe  mov     r14d, eax
0x180032901  mov     edx, 13h
0x180032906  mov     rcx, cs:WPP_GLOBAL_Control
0x18003290d  mov     r9d, eax
0x180032910  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x180032917  mov     rcx, [rcx+10h]
0x18003291b  call    WPP_SF_d
0x180032920  lea     rax, [rsp+1D8h+MultiByteStr]
0x180032928  mov     [rax], r13b
0x18003292b  inc     rax
0x18003292e  sub     r15, 1
0x180032932  jnz     short loc_180032928
0x180032934  inc     rsi
0x180032937  cmp     [rdi+rsi*2], r13w
0x18003293c  jnz     short loc_180032934
0x18003293e  lea     rax, [rsi+rsi]
0x180032942  test    rax, rax
0x180032945  jz      short loc_180032953
0x180032947  mov     [rdi], r13b
0x18003294a  inc     rdi
0x18003294d  sub     rax, 1
0x180032951  jnz     short loc_180032947
0x180032953  lea     rdx, [rsp+1D8h+lpWideCharStr]
0x180032958  lea     rcx, [rsp+1D8h+pDataIn]
0x18003295d  call    ?Marshal@GenericCredMarshaller@Peer@EapLm@@SA?AV?$TempBuffer@$0A@@@AEBU_GENERIC_USER_DATA@2EapHost@@@Z; EapLm::Peer::GenericCredMarshaller::Marshal(EapHost::Peer::_GENERIC_USER_DATA const &)
0x180032962  nop
0x180032963  mov     rdx, rax
0x180032966  mov     rcx, r12
0x180032969  call    ?Assign@?$TempBuffer@$0A@@@AEAAXAEBV1@@Z; TempBuffer<0>::Assign(TempBuffer<0> const &)
0x18003296e  nop
0x18003296f  mov     rcx, qword ptr [rsp+1D8h+pDataIn.cbData]; void *
0x180032974  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180032979  nop
0x18003297a  lea     rcx, [rsp+1D8h+lpWideCharStr]
0x18003297f  call    ??$Free@VHeapAllocator@@@@YAXAEAU_GENERIC_USER_DATA@Peer@EapHost@@@Z; Free<HeapAllocator>(EapHost::Peer::_GENERIC_USER_DATA &)
0x180032984  mov     eax, r14d
0x180032987  mov     rcx, [rsp+1D8h+var_38]
0x18003298f  xor     rcx, rsp; StackCookie
0x180032992  call    __security_check_cookie
0x180032997  lea     r11, [rsp+1D8h+var_28]
0x18003299f  mov     rbx, [r11+40h]
0x1800329a3  mov     rsi, [r11+48h]
0x1800329a7  mov     rsp, r11
0x1800329aa  pop     r15
0x1800329ac  pop     r14
0x1800329ae  pop     r13
0x1800329b0  pop     r12
0x1800329b2  pop     rdi
0x1800329b3  retn
```
