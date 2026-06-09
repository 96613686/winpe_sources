# EapLm::Peer::GenericCredMarshaller::DecryptCredential(TempBuffer<0> &,wchar_t *,ulong,void *)

- ea: `0x1800337f0`
- end: `0x180033a1b`
- name: `?DecryptCredential@GenericCredMarshaller@Peer@EapLm@@SAKAEAV?$TempBuffer@$0A@@@PEA_WKPEAX@Z`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013090`
- `0x180015980`

## callees

- `0x180007564`
- `0x18000a24c`
- `0x18000a658`
- `0x18000b248`
- `0x18001296c`
- `0x1800337f0`
- `0x180033d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003394d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003394d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339e1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003393d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003393d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180033818`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180033818`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800339bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800339bf`
- `CRYPT32!CryptUnprotectData` at `0x18003389c`
- `CRYPT32!CryptUnprotectData` at `0x18003389c`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::GenericCredMarshaller::DecryptCredential(__int64 a1, WCHAR *a2, __int64 a3, void *a4)
{
  DWORD v6; // eax
  DWORD v7; // ebx
  EapHost::Peer::Host *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  void *v11; // rsi
  DWORD LastError; // eax
  __int64 cbData; // rdx
  _BYTE *v14; // rax
  DWORD v16; // eax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-48h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-38h] BYREF

  pDataOut = 0;
  pDataIn = 0;
  *a2 = 0;
  if ( ImpersonateLoggedOnUser(a4) )
  {
    v7 = 0;
    pDataIn.cbData = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(a1 + 8));
    pDataIn.pbData = *(BYTE **)a1;
    if ( CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
    {
      try
      {
        v11 = HeapAllocator::Alloc(pDataOut.cbData + 1);
        memcpy_s_0(v11, pDataOut.cbData + 1, pDataOut.pbData, pDataOut.cbData);
        *((_BYTE *)v11 + pDataOut.cbData) = 0;
        if ( !MultiByteToWideChar(0, 0, (LPCCH)v11, -1, a2, 257) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              WPP_11241dfdb44f3a66398a59577becbc95_Traceguids,
              LastError);
          }
        }
        EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
        cbData = pDataOut.cbData;
        v14 = v11;
        if ( pDataOut.cbData )
        {
          do
          {
            *v14++ = 0;
            --cbData;
          }
          while ( cbData );
        }
        HeapAllocator::Free(v11);
      }
      catch ( std::bad_alloc )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids);
        }
        EapLm::Peer::GenericCredMarshaller::FreeCredential(&pDataOut);
        if ( !RevertToSelf()
          && WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v16);
        }
        throw;
      }
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v10);
      }
    }
    if ( !RevertToSelf()
      && WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = GetLastError();
      v7 = v6;
      v9 = 25;
      v8 = WPP_GLOBAL_Control;
      goto LABEL_20;
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 20;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids, v6);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800337f0  push    rbx
0x1800337f2  push    rsi
0x1800337f3  push    rdi
0x1800337f4  push    r14
0x1800337f6  sub     rsp, 68h
0x1800337fa  mov     r14, rdx
0x1800337fd  mov     rdi, rcx
0x180033800  xorps   xmm0, xmm0
0x180033803  movups  xmmword ptr [rsp+88h+var_48.cbData], xmm0
0x180033808  xorps   xmm1, xmm1
0x18003380b  movups  xmmword ptr [rsp+88h+pDataIn.cbData], xmm1
0x180033810  xor     eax, eax
0x180033812  mov     [rdx], ax
0x180033815  mov     rcx, r9; hToken
0x180033818  call    cs:__imp_ImpersonateLoggedOnUser
0x18003381f  nop     dword ptr [rax+rax+00h]
0x180033824  test    eax, eax
0x180033826  jnz     short loc_180033861
0x180033828  call    cs:__imp_GetLastError
0x18003382f  nop     dword ptr [rax+rax+00h]
0x180033834  mov     ebx, eax
0x180033836  lea     rdi, WPP_GLOBAL_Control
0x18003383d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033844  cmp     rcx, rdi
0x180033847  jz      loc_180033A0E
0x18003384d  test    byte ptr [rcx+1Ch], 1
0x180033851  jz      loc_180033A0E
0x180033857  mov     edx, 14h
0x18003385c  jmp     loc_1800339FB
0x180033861  xor     ebx, ebx
0x180033863  mov     rcx, [rdi+8]
0x180033867  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18003386c  mov     [rsp+88h+pDataIn.cbData], eax
0x180033870  mov     rax, [rdi]
0x180033873  mov     [rsp+88h+pDataIn.pbData], rax
0x180033878  lea     rax, [rsp+88h+var_48]
0x18003387d  mov     [rsp+88h+pDataOut], rax; pDataOut
0x180033882  mov     [rsp+88h+dwFlags], 1; dwFlags
0x18003388a  mov     [rsp+88h+pPromptStruct], rbx; pPromptStruct
0x18003388f  xor     r9d, r9d; pvReserved
0x180033892  xor     r8d, r8d; pOptionalEntropy
0x180033895  xor     edx, edx; ppszDataDescr
0x180033897  lea     rcx, [rsp+88h+pDataIn]; pDataIn
0x18003389c  call    cs:__imp_CryptUnprotectData
0x1800338a3  nop     dword ptr [rax+rax+00h]
0x1800338a8  test    eax, eax
0x1800338aa  jnz     short loc_1800338F8
0x1800338ac  call    cs:__imp_GetLastError
0x1800338b3  nop     dword ptr [rax+rax+00h]
0x1800338b8  mov     ebx, eax
0x1800338ba  lea     rdi, WPP_GLOBAL_Control
0x1800338c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338c8  cmp     rcx, rdi
0x1800338cb  jz      loc_1800339BF
0x1800338d1  test    byte ptr [rcx+1Ch], 1
0x1800338d5  jz      loc_1800339BF
0x1800338db  mov     edx, 15h
0x1800338e0  mov     r9d, eax
0x1800338e3  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x1800338ea  mov     rcx, [rcx+10h]
0x1800338ee  call    WPP_SF_d
0x1800338f3  jmp     loc_1800339BF
0x1800338f8  mov     ecx, [rsp+88h+var_48.cbData]
0x1800338fc  inc     ecx; unsigned __int64
0x1800338fe  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180033903  mov     rsi, rax
0x180033906  mov     eax, [rsp+88h+var_48.cbData]
0x18003390a  mov     r9d, eax; SourceSize
0x18003390d  lea     edx, [rax+1]; DestinationSize
0x180033910  mov     r8, [rsp+88h+var_48.pbData]; Source
0x180033915  mov     rcx, rsi; Destination
0x180033918  call    memcpy_s_0
0x18003391d  mov     eax, [rsp+88h+var_48.cbData]
0x180033921  mov     byte ptr [rax+rsi], 0
0x180033925  mov     [rsp+88h+dwFlags], 101h; cchWideChar
0x18003392d  mov     [rsp+88h+pPromptStruct], r14; lpWideCharStr
0x180033932  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180033936  mov     r8, rsi; lpMultiByteStr
0x180033939  xor     edx, edx; dwFlags
0x18003393b  xor     ecx, ecx; CodePage
0x18003393d  call    cs:__imp_MultiByteToWideChar
0x180033944  nop     dword ptr [rax+rax+00h]
0x180033949  test    eax, eax
0x18003394b  jnz     short loc_18003398E
0x18003394d  call    cs:__imp_GetLastError
0x180033954  nop     dword ptr [rax+rax+00h]
0x180033959  mov     ebx, eax
0x18003395b  lea     rdi, WPP_GLOBAL_Control
0x180033962  mov     rcx, cs:WPP_GLOBAL_Control
0x180033969  cmp     rcx, rdi
0x18003396c  jz      short loc_180033995
0x18003396e  test    byte ptr [rcx+1Ch], 1
0x180033972  jz      short loc_180033995
0x180033974  mov     edx, 18h
0x180033979  mov     r9d, eax
0x18003397c  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x180033983  mov     rcx, [rcx+10h]
0x180033987  call    WPP_SF_d
0x18003398c  jmp     short loc_180033995
0x18003398e  lea     rdi, WPP_GLOBAL_Control
0x180033995  lea     rcx, [rsp+88h+var_48]; struct _CRYPTOAPI_BLOB *
0x18003399a  call    ?FreeCredential@GenericCredMarshaller@Peer@EapLm@@SAXPEAU_CRYPTOAPI_BLOB@@@Z; EapLm::Peer::GenericCredMarshaller::FreeCredential(_CRYPTOAPI_BLOB *)
0x18003399f  mov     edx, [rsp+88h+var_48.cbData]
0x1800339a3  mov     rax, rsi
0x1800339a6  test    rdx, rdx
0x1800339a9  jz      short loc_1800339B7
0x1800339ab  mov     byte ptr [rax], 0
0x1800339ae  inc     rax
0x1800339b1  sub     rdx, 1
0x1800339b5  jnz     short loc_1800339AB
0x1800339b7  mov     rcx, rsi; void *
0x1800339ba  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800339bf  call    cs:__imp_RevertToSelf
0x1800339c6  nop     dword ptr [rax+rax+00h]
0x1800339cb  test    eax, eax
0x1800339cd  jnz     short loc_180033A0E
0x1800339cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800339d6  cmp     rax, rdi
0x1800339d9  jz      short loc_180033A0E
0x1800339db  test    byte ptr [rax+1Ch], 1
0x1800339df  jz      short loc_180033A0E
0x1800339e1  call    cs:__imp_GetLastError
0x1800339e8  nop     dword ptr [rax+rax+00h]
0x1800339ed  mov     ebx, eax
0x1800339ef  mov     edx, 19h
0x1800339f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339fb  mov     r9d, eax
0x1800339fe  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x180033a05  mov     rcx, [rcx+10h]
0x180033a09  call    WPP_SF_d
0x180033a0e  mov     eax, ebx
0x180033a10  add     rsp, 68h
0x180033a14  pop     r14
0x180033a16  pop     rdi
0x180033a17  pop     rsi
0x180033a18  pop     rbx
0x180033a19  retn
```
