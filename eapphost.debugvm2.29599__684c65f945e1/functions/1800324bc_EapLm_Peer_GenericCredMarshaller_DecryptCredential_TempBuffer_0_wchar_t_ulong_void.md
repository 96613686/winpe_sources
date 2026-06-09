# EapLm::Peer::GenericCredMarshaller::DecryptCredential(TempBuffer<0> &,wchar_t *,ulong,void *)

- ea: `0x1800324bc`
- end: `0x1800326b6`
- name: `?DecryptCredential@GenericCredMarshaller@Peer@EapLm@@SAKAEAV?$TempBuffer@$0A@@@PEA_WKPEAX@Z`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012900`
- `0x180015140`

## callees

- `0x1800072cc`
- `0x180009dec`
- `0x18000a1b4`
- `0x18000ada8`
- `0x1800121ec`
- `0x1800324bc`
- `0x1800329bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032683`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800325f1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800325f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800324e4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800324e4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032667`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032667`
- `CRYPT32!CryptUnprotectData` at `0x18003255c`
- `CRYPT32!CryptUnprotectData` at `0x18003255c`

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
0x1800324bc  push    rbx
0x1800324be  push    rsi
0x1800324bf  push    rdi
0x1800324c0  push    r14
0x1800324c2  sub     rsp, 68h
0x1800324c6  mov     r14, rdx
0x1800324c9  mov     rdi, rcx
0x1800324cc  xorps   xmm0, xmm0
0x1800324cf  movups  xmmword ptr [rsp+88h+var_48.cbData], xmm0
0x1800324d4  xorps   xmm1, xmm1
0x1800324d7  movups  xmmword ptr [rsp+88h+pDataIn.cbData], xmm1
0x1800324dc  xor     eax, eax
0x1800324de  mov     [rdx], ax
0x1800324e1  mov     rcx, r9; hToken
0x1800324e4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800324ea  test    eax, eax
0x1800324ec  jnz     short loc_180032521
0x1800324ee  call    cs:__imp_GetLastError
0x1800324f4  mov     ebx, eax
0x1800324f6  lea     rdi, WPP_GLOBAL_Control
0x1800324fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180032504  cmp     rcx, rdi
0x180032507  jz      loc_1800326AA
0x18003250d  test    byte ptr [rcx+1Ch], 1
0x180032511  jz      loc_1800326AA
0x180032517  mov     edx, 14h
0x18003251c  jmp     loc_180032697
0x180032521  xor     ebx, ebx
0x180032523  mov     rcx, [rdi+8]
0x180032527  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18003252c  mov     [rsp+88h+pDataIn.cbData], eax
0x180032530  mov     rax, [rdi]
0x180032533  mov     [rsp+88h+pDataIn.pbData], rax
0x180032538  lea     rax, [rsp+88h+var_48]
0x18003253d  mov     [rsp+88h+pDataOut], rax; pDataOut
0x180032542  mov     [rsp+88h+dwFlags], 1; dwFlags
0x18003254a  mov     [rsp+88h+pPromptStruct], rbx; pPromptStruct
0x18003254f  xor     r9d, r9d; pvReserved
0x180032552  xor     r8d, r8d; pOptionalEntropy
0x180032555  xor     edx, edx; ppszDataDescr
0x180032557  lea     rcx, [rsp+88h+pDataIn]; pDataIn
0x18003255c  call    cs:__imp_CryptUnprotectData
0x180032562  test    eax, eax
0x180032564  jnz     short loc_1800325AC
0x180032566  call    cs:__imp_GetLastError
0x18003256c  mov     ebx, eax
0x18003256e  lea     rdi, WPP_GLOBAL_Control
0x180032575  mov     rcx, cs:WPP_GLOBAL_Control
0x18003257c  cmp     rcx, rdi
0x18003257f  jz      loc_180032667
0x180032585  test    byte ptr [rcx+1Ch], 1
0x180032589  jz      loc_180032667
0x18003258f  mov     edx, 15h
0x180032594  mov     r9d, eax
0x180032597  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18003259e  mov     rcx, [rcx+10h]
0x1800325a2  call    WPP_SF_d
0x1800325a7  jmp     loc_180032667
0x1800325ac  mov     ecx, [rsp+88h+var_48.cbData]
0x1800325b0  inc     ecx; unsigned __int64
0x1800325b2  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800325b7  mov     rsi, rax
0x1800325ba  mov     eax, [rsp+88h+var_48.cbData]
0x1800325be  mov     r9d, eax; SourceSize
0x1800325c1  lea     edx, [rax+1]; DestinationSize
0x1800325c4  mov     r8, [rsp+88h+var_48.pbData]; Source
0x1800325c9  mov     rcx, rsi; Destination
0x1800325cc  call    memcpy_s_0
0x1800325d1  mov     eax, [rsp+88h+var_48.cbData]
0x1800325d5  mov     byte ptr [rax+rsi], 0
0x1800325d9  mov     [rsp+88h+dwFlags], 101h; cchWideChar
0x1800325e1  mov     [rsp+88h+pPromptStruct], r14; lpWideCharStr
0x1800325e6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800325ea  mov     r8, rsi; lpMultiByteStr
0x1800325ed  xor     edx, edx; dwFlags
0x1800325ef  xor     ecx, ecx; CodePage
0x1800325f1  call    cs:__imp_MultiByteToWideChar
0x1800325f7  test    eax, eax
0x1800325f9  jnz     short loc_180032636
0x1800325fb  call    cs:__imp_GetLastError
0x180032601  mov     ebx, eax
0x180032603  lea     rdi, WPP_GLOBAL_Control
0x18003260a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032611  cmp     rcx, rdi
0x180032614  jz      short loc_18003263D
0x180032616  test    byte ptr [rcx+1Ch], 1
0x18003261a  jz      short loc_18003263D
0x18003261c  mov     edx, 18h
0x180032621  mov     r9d, eax
0x180032624  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x18003262b  mov     rcx, [rcx+10h]
0x18003262f  call    WPP_SF_d
0x180032634  jmp     short loc_18003263D
0x180032636  lea     rdi, WPP_GLOBAL_Control
0x18003263d  lea     rcx, [rsp+88h+var_48]; struct _CRYPTOAPI_BLOB *
0x180032642  call    ?FreeCredential@GenericCredMarshaller@Peer@EapLm@@SAXPEAU_CRYPTOAPI_BLOB@@@Z; EapLm::Peer::GenericCredMarshaller::FreeCredential(_CRYPTOAPI_BLOB *)
0x180032647  mov     edx, [rsp+88h+var_48.cbData]
0x18003264b  mov     rax, rsi
0x18003264e  test    rdx, rdx
0x180032651  jz      short loc_18003265F
0x180032653  mov     byte ptr [rax], 0
0x180032656  inc     rax
0x180032659  sub     rdx, 1
0x18003265d  jnz     short loc_180032653
0x18003265f  mov     rcx, rsi; void *
0x180032662  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180032667  call    cs:__imp_RevertToSelf
0x18003266d  test    eax, eax
0x18003266f  jnz     short loc_1800326AA
0x180032671  mov     rax, cs:WPP_GLOBAL_Control
0x180032678  cmp     rax, rdi
0x18003267b  jz      short loc_1800326AA
0x18003267d  test    byte ptr [rax+1Ch], 1
0x180032681  jz      short loc_1800326AA
0x180032683  call    cs:__imp_GetLastError
0x180032689  mov     ebx, eax
0x18003268b  mov     edx, 19h
0x180032690  mov     rcx, cs:WPP_GLOBAL_Control
0x180032697  mov     r9d, eax
0x18003269a  lea     r8, WPP_11241dfdb44f3a66398a59577becbc95_Traceguids
0x1800326a1  mov     rcx, [rcx+10h]
0x1800326a5  call    WPP_SF_d
0x1800326aa  mov     eax, ebx
0x1800326ac  add     rsp, 68h
0x1800326b0  pop     r14
0x1800326b2  pop     rdi
0x1800326b3  pop     rsi
0x1800326b4  pop     rbx
0x1800326b5  retn
```
