# DpspRetrieveClientSID(void *,void * *)

- ea: `0x18001246c`
- end: `0x180012669`
- name: `?DpspRetrieveClientSID@@YAJPEAXPEAPEAX@Z`
- size: `509`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006eec`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000a856`
- `0x18001246c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001256f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001263e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001256f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001263e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800124e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012565`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800124e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012565`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800125c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800125c2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001259d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001259d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180012606`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180012606`

## string_xrefs

- `0x1800124ab`: `DpspRetrieveClientSID`

## pseudocode

```c
__int64 __fastcall DpspRetrieveClientSID(HANDLE TokenHandle, void **a2)
{
  void *v2; // rsi
  PSID *v3; // rdi
  int v6; // r8d
  signed int v7; // ebx
  PSID *v8; // rax
  signed int LastError; // eax
  size_t LengthSid; // rbx
  void *v11; // rax
  signed int v13; // eax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  TokenInformationLength = 0;
  if ( TokenHandle )
  {
    if ( a2 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
        GetLastError();
      if ( GetLastError() != 122 )
      {
        v7 = -2147467259;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveClientSID",
          1233,
          (int)L"Error = %d",
          5);
        goto LABEL_25;
      }
      v8 = (PSID *)WdipAlloc(TokenInformationLength);
      v3 = v8;
      if ( !v8 )
      {
        v7 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveClientSID",
          1238,
          (int)L"Error = %d",
          14);
        goto LABEL_25;
      }
      memset_0(v8, 0, TokenInformationLength);
      if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 < 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
            (int)L"DpspRetrieveClientSID",
            1249,
            (int)L"Error = %d",
            v7);
          goto LABEL_25;
        }
      }
      if ( !IsValidSid(*v3) )
      {
        v7 = -2147467259;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveClientSID",
          1253,
          (int)L"Error = %d",
          5);
        goto LABEL_25;
      }
      LengthSid = GetLengthSid(*v3);
      v11 = (void *)WdipAlloc(LengthSid);
      v2 = v11;
      if ( !v11 )
      {
        v7 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveClientSID",
          1259,
          (int)L"Error = %d",
          14);
        goto LABEL_25;
      }
      memset_0(v11, 0, LengthSid);
      if ( CopySid(LengthSid, v2, *v3) )
      {
        v7 = 0;
      }
      else
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        if ( v7 < 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
            (int)L"DpspRetrieveClientSID",
            1266,
            (int)L"Error = %d",
            v7);
          goto LABEL_25;
        }
      }
      *a2 = v2;
      goto LABEL_25;
    }
    v6 = 1222;
  }
  else
  {
    v6 = 1221;
  }
  v7 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
    (int)L"DpspRetrieveClientSID",
    v6,
    (int)L"Error = %d",
    87);
LABEL_25:
  WdipFree(v3);
  if ( v7 < 0 )
    WdipFree(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001246c  mov     [rsp+arg_8], rbx
0x180012471  mov     [rsp+arg_10], rbp
0x180012476  push    rsi
0x180012477  push    rdi
0x180012478  push    r14
0x18001247a  sub     rsp, 30h
0x18001247e  xor     esi, esi
0x180012480  xor     edi, edi
0x180012482  mov     [rsp+48h+TokenInformationLength], esi
0x180012486  mov     r14, rdx
0x180012489  mov     rbx, rcx
0x18001248c  test    rcx, rcx
0x18001248f  jnz     short loc_1800124C3
0x180012491  mov     r8d, 4C5h; int
0x180012497  mov     dword ptr [rsp+48h+ReturnLength], 57h ; 'W'; Args
0x18001249f  mov     ebx, 80070057h
0x1800124a4  lea     r9, aErrorD; "Error = %d"
0x1800124ab  lea     rdx, aDpspretrievecl; "DpspRetrieveClientSID"
0x1800124b2  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800124b9  call    WdipTraceError
0x1800124be  jmp     loc_180012615
0x1800124c3  test    r14, r14
0x1800124c6  jnz     short loc_1800124D0
0x1800124c8  mov     r8d, 4C6h
0x1800124ce  jmp     short loc_180012497
0x1800124d0  xor     r9d, r9d; TokenInformationLength
0x1800124d3  lea     rax, [rsp+48h+TokenInformationLength]
0x1800124d8  xor     r8d, r8d; TokenInformation
0x1800124db  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800124e0  lea     ebp, [r9+1]
0x1800124e4  mov     edx, ebp; TokenInformationClass
0x1800124e6  call    cs:__imp_GetTokenInformation
0x1800124ec  test    eax, eax
0x1800124ee  jnz     short loc_1800124F6
0x1800124f0  call    cs:__imp_GetLastError
0x1800124f6  call    cs:__imp_GetLastError
0x1800124fc  cmp     eax, 7Ah ; 'z'
0x1800124ff  jz      short loc_180012516
0x180012501  mov     ebx, 80004005h
0x180012506  mov     dword ptr [rsp+48h+ReturnLength], 4005h
0x18001250e  mov     r8d, 4D1h
0x180012514  jmp     short loc_1800124A4
0x180012516  mov     ecx, [rsp+48h+TokenInformationLength]
0x18001251a  call    WdipAlloc
0x18001251f  mov     rdi, rax
0x180012522  test    rax, rax
0x180012525  jnz     short loc_18001253F
0x180012527  mov     ebx, 8007000Eh
0x18001252c  mov     dword ptr [rsp+48h+ReturnLength], 0Eh
0x180012534  mov     r8d, 4D6h
0x18001253a  jmp     loc_1800124A4
0x18001253f  mov     r8d, [rsp+48h+TokenInformationLength]; Size
0x180012544  xor     edx, edx; Val
0x180012546  mov     rcx, rdi; void *
0x180012549  call    memset_0
0x18001254e  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180012553  lea     rax, [rsp+48h+TokenInformationLength]
0x180012558  mov     r8, rdi; TokenInformation
0x18001255b  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180012560  mov     edx, ebp; TokenInformationClass
0x180012562  mov     rcx, rbx; TokenHandle
0x180012565  call    cs:__imp_GetTokenInformation
0x18001256b  test    eax, eax
0x18001256d  jnz     short loc_18001259A
0x18001256f  call    cs:__imp_GetLastError
0x180012575  mov     ebx, eax
0x180012577  test    eax, eax
0x180012579  jle     short loc_180012584
0x18001257b  movzx   ebx, ax
0x18001257e  or      ebx, 80070000h
0x180012584  test    ebx, ebx
0x180012586  jns     short loc_18001259A
0x180012588  movzx   eax, bx
0x18001258b  mov     r8d, 4E1h
0x180012591  mov     dword ptr [rsp+48h+ReturnLength], eax
0x180012595  jmp     loc_1800124A4
0x18001259a  mov     rcx, [rdi]; pSid
0x18001259d  call    cs:__imp_IsValidSid
0x1800125a3  test    eax, eax
0x1800125a5  jnz     short loc_1800125BF
0x1800125a7  mov     ebx, 80004005h
0x1800125ac  mov     dword ptr [rsp+48h+ReturnLength], 4005h
0x1800125b4  mov     r8d, 4E5h
0x1800125ba  jmp     loc_1800124A4
0x1800125bf  mov     rcx, [rdi]; pSid
0x1800125c2  call    cs:__imp_GetLengthSid
0x1800125c8  mov     ecx, eax
0x1800125ca  mov     ebx, eax
0x1800125cc  call    WdipAlloc
0x1800125d1  mov     rsi, rax
0x1800125d4  test    rax, rax
0x1800125d7  jnz     short loc_1800125F1
0x1800125d9  mov     ebx, 8007000Eh
0x1800125de  mov     dword ptr [rsp+48h+ReturnLength], 0Eh
0x1800125e6  mov     r8d, 4EBh
0x1800125ec  jmp     loc_1800124A4
0x1800125f1  mov     r8, rbx; Size
0x1800125f4  xor     edx, edx; Val
0x1800125f6  mov     rcx, rsi; void *
0x1800125f9  call    memset_0
0x1800125fe  mov     r8, [rdi]; pSourceSid
0x180012601  mov     rdx, rsi; pDestinationSid
0x180012604  mov     ecx, ebx; nDestinationSidLength
0x180012606  call    cs:__imp_CopySid
0x18001260c  test    eax, eax
0x18001260e  jz      short loc_18001263E
0x180012610  xor     ebx, ebx
0x180012612  mov     [r14], rsi
0x180012615  mov     rcx, rdi
0x180012618  call    WdipFree
0x18001261d  test    ebx, ebx
0x18001261f  jns     short loc_180012629
0x180012621  mov     rcx, rsi
0x180012624  call    WdipFree
0x180012629  mov     rbp, [rsp+48h+arg_10]
0x18001262e  mov     eax, ebx
0x180012630  mov     rbx, [rsp+48h+arg_8]
0x180012635  add     rsp, 30h
0x180012639  pop     r14
0x18001263b  pop     rdi
0x18001263c  pop     rsi
0x18001263d  retn
0x18001263e  call    cs:__imp_GetLastError
0x180012644  mov     ebx, eax
0x180012646  test    eax, eax
0x180012648  jle     short loc_180012653
0x18001264a  movzx   ebx, ax
0x18001264d  or      ebx, 80070000h
0x180012653  test    ebx, ebx
0x180012655  jns     short loc_180012612
0x180012657  movzx   eax, bx
0x18001265a  mov     r8d, 4F2h
0x180012660  mov     dword ptr [rsp+48h+ReturnLength], eax
0x180012664  jmp     loc_1800124A4
```
