# EapLm::Peer::GenericCredMarshaller::DecryptCredential(TempBuffer<0> &,wchar_t *,ulong,void *)

- ea: `0x18002e7b0`
- end: `0x18002ea01`
- name: `?DecryptCredential@GenericCredMarshaller@Peer@EapLm@@SAKAEAV?$TempBuffer@$0A@@@PEA_WKPEAX@Z`
- size: `593`
- prototype: `__int64 __fastcall(__int64, WCHAR *, __int64, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023250`
- `0x180025920`

## callees

- `0x1800020f2`
- `0x18000213c`
- `0x180003e38`
- `0x18000439c`
- `0x180005894`
- `0x18000bf94`
- `0x18002e7b0`
- `0x18002ed08`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e8fa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e908`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e8fa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e908`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002e93a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002e93a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9cc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e9b0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e9b0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002e7da`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002e7da`
- `CRYPT32!CryptUnprotectData` at `0x18002e854`
- `CRYPT32!CryptUnprotectData` at `0x18002e854`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EapLm::Peer::GenericCredMarshaller::DecryptCredential(__int64 a1, WCHAR *a2, __int64 a3, void *a4)
{
  DWORD LastError; // eax
  DWORD v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  void *v11; // rsi
  unsigned __int64 cbData; // rbx
  BYTE *pbData; // r14
  unsigned __int64 v14; // rdi
  DWORD v15; // eax
  __int64 v16; // rcx
  _BYTE *v17; // rax
  DWORD v19; // eax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-48h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-38h] BYREF

  pDataOut = 0;
  pDataIn = 0;
  *a2 = 0;
  if ( !ImpersonateLoggedOnUser(a4) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 20;
LABEL_30:
      WPP_SF_d(v8[2], v9, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, LastError);
      return v7;
    }
    return v7;
  }
  pDataIn.cbData = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(a1 + 8));
  pDataIn.pbData = *(BYTE **)a1;
  if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v10);
    goto LABEL_26;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v11 = HeapAllocator::Alloc(pDataOut.cbData + 1);
    cbData = pDataOut.cbData;
    if ( !pDataOut.cbData )
      goto LABEL_19;
    if ( !v11 )
      goto LABEL_17;
    pbData = pDataOut.pbData;
    v14 = pDataOut.cbData + 1;
    if ( pDataOut.pbData && v14 >= pDataOut.cbData )
    {
      memcpy_0(v11, pDataOut.pbData, pDataOut.cbData);
      goto LABEL_19;
    }
    memset_0(v11, 0, pDataOut.cbData + 1);
    if ( pbData )
    {
      if ( v14 >= cbData )
        goto LABEL_19;
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
LABEL_17:
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
LABEL_19:
    v7 = 0;
    *((_BYTE *)v11 + pDataOut.cbData) = 0;
    if ( !MultiByteToWideChar(0, 0, (LPCCH)v11, -1, a2, 257) )
    {
      v15 = GetLastError();
      v7 = v15;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v15);
    }
    EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
    v16 = pDataOut.cbData;
    v17 = v11;
    if ( pDataOut.cbData )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    HeapAllocator::Free(v11);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids);
      EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
      if ( !RevertToSelf()
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v19);
      }
      throw;
    }
  }
LABEL_26:
  if ( !RevertToSelf()
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v7 = LastError;
    v9 = 25;
    v8 = WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  return v7;
}

```

## disassembly

```asm
0x18002e7b0  push    rbx
0x18002e7b2  push    rsi
0x18002e7b3  push    rdi
0x18002e7b4  push    r14
0x18002e7b6  push    r15
0x18002e7b8  sub     rsp, 60h
0x18002e7bc  mov     r15, rdx
0x18002e7bf  mov     rbx, rcx
0x18002e7c2  xorps   xmm0, xmm0
0x18002e7c5  movups  xmmword ptr [rsp+88h+var_48.cbData], xmm0
0x18002e7ca  xorps   xmm1, xmm1
0x18002e7cd  movups  xmmword ptr [rsp+88h+pDataIn.cbData], xmm1
0x18002e7d2  xor     eax, eax
0x18002e7d4  mov     [rdx], ax
0x18002e7d7  mov     rcx, r9; hToken
0x18002e7da  call    cs:__imp_ImpersonateLoggedOnUser
0x18002e7e0  test    eax, eax
0x18002e7e2  jnz     short loc_18002E817
0x18002e7e4  call    cs:__imp_GetLastError
0x18002e7ea  mov     ebx, eax
0x18002e7ec  lea     rdi, WPP_GLOBAL_Control
0x18002e7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7fa  cmp     rcx, rdi
0x18002e7fd  jz      loc_18002E9F3
0x18002e803  test    byte ptr [rcx+1Ch], 1
0x18002e807  jz      loc_18002E9F3
0x18002e80d  mov     edx, 14h
0x18002e812  jmp     loc_18002E9E0
0x18002e817  mov     rcx, [rbx+8]
0x18002e81b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002e820  mov     [rsp+88h+pDataIn.cbData], eax
0x18002e824  mov     rax, [rbx]
0x18002e827  mov     [rsp+88h+pDataIn.pbData], rax
0x18002e82c  lea     rax, [rsp+88h+var_48]
0x18002e831  mov     [rsp+88h+pDataOut], rax; pDataOut
0x18002e836  mov     [rsp+88h+dwFlags], 1; dwFlags
0x18002e83e  mov     [rsp+88h+pPromptStruct], 0; pPromptStruct
0x18002e847  xor     r9d, r9d; pvReserved
0x18002e84a  xor     r8d, r8d; pOptionalEntropy
0x18002e84d  xor     edx, edx; ppszDataDescr
0x18002e84f  lea     rcx, [rsp+88h+pDataIn]; pDataIn
0x18002e854  call    cs:__imp_CryptUnprotectData
0x18002e85a  test    eax, eax
0x18002e85c  jnz     short loc_18002E8A4
0x18002e85e  call    cs:__imp_GetLastError
0x18002e864  mov     ebx, eax
0x18002e866  lea     rdi, WPP_GLOBAL_Control
0x18002e86d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e874  cmp     rcx, rdi
0x18002e877  jz      loc_18002E9B0
0x18002e87d  test    byte ptr [rcx+1Ch], 1
0x18002e881  jz      loc_18002E9B0
0x18002e887  mov     edx, 15h
0x18002e88c  mov     r9d, eax
0x18002e88f  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18002e896  mov     rcx, [rcx+10h]
0x18002e89a  call    WPP_SF_d
0x18002e89f  jmp     loc_18002E9B0
0x18002e8a4  mov     ecx, [rsp+88h+var_48.cbData]
0x18002e8a8  inc     ecx; unsigned __int64
0x18002e8aa  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18002e8af  mov     rsi, rax
0x18002e8b2  mov     eax, [rsp+88h+var_48.cbData]
0x18002e8b6  mov     ebx, eax
0x18002e8b8  test    eax, eax
0x18002e8ba  jz      short loc_18002E919
0x18002e8bc  test    rsi, rsi
0x18002e8bf  jz      short loc_18002E908
0x18002e8c1  mov     r14, [rsp+88h+var_48.pbData]
0x18002e8c6  lea     edi, [rax+1]
0x18002e8c9  test    r14, r14
0x18002e8cc  jz      short loc_18002E8E3
0x18002e8ce  cmp     rdi, rax
0x18002e8d1  jb      short loc_18002E8E3
0x18002e8d3  mov     r8d, eax; Size
0x18002e8d6  mov     rdx, r14; Src
0x18002e8d9  mov     rcx, rsi; void *
0x18002e8dc  call    memcpy_0
0x18002e8e1  jmp     short loc_18002E919
0x18002e8e3  mov     r8, rdi; Size
0x18002e8e6  xor     edx, edx; Val
0x18002e8e8  mov     rcx, rsi; void *
0x18002e8eb  call    memset_0
0x18002e8f0  test    r14, r14
0x18002e8f3  jz      short loc_18002E908
0x18002e8f5  cmp     rdi, rbx
0x18002e8f8  jnb     short loc_18002E919
0x18002e8fa  call    cs:__imp__o__errno
0x18002e900  mov     dword ptr [rax], 22h ; '"'
0x18002e906  jmp     short loc_18002E914
0x18002e908  call    cs:__imp__o__errno
0x18002e90e  mov     dword ptr [rax], 16h
0x18002e914  call    _invalid_parameter_noinfo
0x18002e919  xor     ebx, ebx
0x18002e91b  mov     eax, [rsp+88h+var_48.cbData]
0x18002e91f  mov     [rax+rsi], bl
0x18002e922  mov     [rsp+88h+dwFlags], 101h; cchWideChar
0x18002e92a  mov     [rsp+88h+pPromptStruct], r15; lpWideCharStr
0x18002e92f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002e933  mov     r8, rsi; lpMultiByteStr
0x18002e936  xor     edx, edx; dwFlags
0x18002e938  xor     ecx, ecx; CodePage
0x18002e93a  call    cs:__imp_MultiByteToWideChar
0x18002e940  test    eax, eax
0x18002e942  jnz     short loc_18002E97F
0x18002e944  call    cs:__imp_GetLastError
0x18002e94a  mov     ebx, eax
0x18002e94c  lea     rdi, WPP_GLOBAL_Control
0x18002e953  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e95a  cmp     rcx, rdi
0x18002e95d  jz      short loc_18002E986
0x18002e95f  test    byte ptr [rcx+1Ch], 1
0x18002e963  jz      short loc_18002E986
0x18002e965  mov     edx, 18h
0x18002e96a  mov     r9d, eax
0x18002e96d  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18002e974  mov     rcx, [rcx+10h]
0x18002e978  call    WPP_SF_d
0x18002e97d  jmp     short loc_18002E986
0x18002e97f  lea     rdi, WPP_GLOBAL_Control
0x18002e986  lea     rcx, [rsp+88h+var_48]; struct _CRYPTOAPI_BLOB *
0x18002e98b  call    ?FreeCredential@GenericCredMarshaller@Peer@EapLm@@SAXPEAU_CRYPTOAPI_BLOB@@@Z; EapLm::Peer::GenericCredMarshaller::FreeCredential(_CRYPTOAPI_BLOB *)
0x18002e990  mov     ecx, [rsp+88h+var_48.cbData]
0x18002e994  mov     rax, rsi
0x18002e997  test    rcx, rcx
0x18002e99a  jz      short loc_18002E9A8
0x18002e99c  mov     byte ptr [rax], 0
0x18002e99f  inc     rax
0x18002e9a2  sub     rcx, 1
0x18002e9a6  jnz     short loc_18002E99C
0x18002e9a8  mov     rcx, rsi; void *
0x18002e9ab  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002e9b0  call    cs:__imp_RevertToSelf
0x18002e9b6  test    eax, eax
0x18002e9b8  jnz     short loc_18002E9F3
0x18002e9ba  mov     rax, cs:WPP_GLOBAL_Control
0x18002e9c1  cmp     rax, rdi
0x18002e9c4  jz      short loc_18002E9F3
0x18002e9c6  test    byte ptr [rax+1Ch], 1
0x18002e9ca  jz      short loc_18002E9F3
0x18002e9cc  call    cs:__imp_GetLastError
0x18002e9d2  mov     ebx, eax
0x18002e9d4  mov     edx, 19h
0x18002e9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9e0  mov     r9d, eax
0x18002e9e3  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18002e9ea  mov     rcx, [rcx+10h]
0x18002e9ee  call    WPP_SF_d
0x18002e9f3  mov     eax, ebx
0x18002e9f5  add     rsp, 60h
0x18002e9f9  pop     r15
0x18002e9fb  pop     r14
0x18002e9fd  pop     rdi
0x18002e9fe  pop     rsi
0x18002e9ff  pop     rbx
0x18002ea00  retn
```
