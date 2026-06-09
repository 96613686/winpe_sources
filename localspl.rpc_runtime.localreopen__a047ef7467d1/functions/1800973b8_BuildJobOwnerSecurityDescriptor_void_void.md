# BuildJobOwnerSecurityDescriptor(void *,void * *)

- ea: `0x1800973b8`
- end: `0x18009754a`
- name: `?BuildJobOwnerSecurityDescriptor@@YAHPEAXPEAPEAX@Z`
- size: `402`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180097a3c`

## callees

- `0x1800239a0`
- `0x180047330`
- `0x1800973b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009741b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009751b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009741b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009751b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180097525`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180097525`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009740a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009745a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009740a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009745a`
- `SPOOLSS!DllFreeSplMem` at `0x180097513`
- `SPOOLSS!DllFreeSplMem` at `0x180097513`
- `SPOOLSS!DllAllocSplMem` at `0x180097430`
- `SPOOLSS!DllAllocSplMem` at `0x180097430`

## pseudocode

```c
_BOOL8 __fastcall BuildJobOwnerSecurityDescriptor(HANDLE TokenHandle, void **a2)
{
  DWORD LastError; // ebx
  void **v5; // rdi
  void *pOwner; // rcx
  DWORD v8; // [rsp+38h] [rbp-C8h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v10; // [rsp+58h] [rbp-A8h] BYREF
  char v11; // [rsp+5Ah] [rbp-A6h]
  __int16 v12; // [rsp+70h] [rbp-90h] BYREF
  char v13; // [rsp+72h] [rbp-8Eh]
  int v14[20]; // [rsp+90h] [rbp-70h] BYREF
  int v15[2]; // [rsp+E0h] [rbp-20h] BYREF
  PSID v16; // [rsp+E8h] [rbp-18h]
  PSID v17; // [rsp+F0h] [rbp-10h]
  _BYTE v18[136]; // [rsp+F8h] [rbp-8h] BYREF

  LastError = 87;
  if ( TokenHandle && a2 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        v5 = (void **)DllAllocSplMem(TokenInformationLength);
        if ( v5 )
        {
          if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength)
            || (LastError = GetLastError()) == 0 )
          {
            memset_0(v18, 0, sizeof(v18));
            pOwner = *v5;
            v16 = pLocalSystemSid;
            v17 = gRestrictedSpoolerServiceSid;
            *(_QWORD *)v15 = pOwner;
            v14[1] = 983088;
            v14[2] = 983088;
            v12 = 0;
            v14[0] = 131104;
            v10 = 0;
            v13 = 0;
            v11 = 0;
            if ( (unsigned int)BuildPrintObjectProtection(
                                 (__int64)&v12,
                                 3u,
                                 (__int64)v15,
                                 (__int64)v14,
                                 (__int64)&v10,
                                 pOwner,
                                 0,
                                 v8,
                                 a2) )
              LastError = 0;
            else
              LastError = GetLastError();
          }
          DllFreeSplMem(v5);
        }
        else
        {
          LastError = GetLastError();
        }
      }
    }
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1800973b8  mov     [rsp-8+arg_10], rbx
0x1800973bd  mov     [rsp-8+arg_18], rsi
0x1800973c2  push    rbp
0x1800973c3  push    rdi
0x1800973c4  push    r14
0x1800973c6  lea     rbp, [rsp-80h]
0x1800973cb  sub     rsp, 180h
0x1800973d2  mov     r14, rdx
0x1800973d5  mov     rsi, rcx
0x1800973d8  mov     ebx, 57h ; 'W'
0x1800973dd  test    rcx, rcx
0x1800973e0  jz      loc_180097523
0x1800973e6  test    rdx, rdx
0x1800973e9  jz      loc_180097523
0x1800973ef  lea     rax, [rsp+190h+TokenInformationLength]
0x1800973f4  mov     [rsp+190h+TokenInformationLength], 0
0x1800973fc  xor     r9d, r9d; TokenInformationLength
0x1800973ff  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x180097404  xor     r8d, r8d; TokenInformation
0x180097407  lea     edx, [rbx-56h]; TokenInformationClass
0x18009740a  call    cs:__imp_GetTokenInformation
0x180097410  test    eax, eax
0x180097412  jz      short loc_18009741B
0x180097414  xor     ebx, ebx
0x180097416  jmp     loc_180097523
0x18009741b  call    cs:__imp_GetLastError
0x180097421  mov     ebx, eax
0x180097423  cmp     eax, 7Ah ; 'z'
0x180097426  jnz     loc_180097523
0x18009742c  mov     ecx, [rsp+190h+TokenInformationLength]
0x180097430  call    cs:__imp_DllAllocSplMem
0x180097436  mov     rdi, rax
0x180097439  test    rax, rax
0x18009743c  jz      loc_18009751B
0x180097442  mov     r9d, [rsp+190h+TokenInformationLength]; TokenInformationLength
0x180097447  lea     rax, [rsp+190h+TokenInformationLength]
0x18009744c  mov     r8, rdi; TokenInformation
0x18009744f  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x180097454  lea     edx, [rbx-79h]; TokenInformationClass
0x180097457  mov     rcx, rsi; TokenHandle
0x18009745a  call    cs:__imp_GetTokenInformation
0x180097460  test    eax, eax
0x180097462  jnz     short loc_180097474
0x180097464  call    cs:__imp_GetLastError
0x18009746a  mov     ebx, eax
0x18009746c  test    eax, eax
0x18009746e  jnz     loc_180097510
0x180097474  xor     edx, edx; Val
0x180097476  lea     rcx, [rbp+90h+var_98]; void *
0x18009747a  mov     r8d, 88h; Size
0x180097480  call    memset_0
0x180097485  mov     rcx, [rdi]
0x180097488  lea     r9, [rbp+90h+var_100]; int
0x18009748c  mov     rax, cs:?pLocalSystemSid@@3PEAXEA; void * pLocalSystemSid
0x180097493  lea     r8, [rbp+90h+var_B0]; int
0x180097497  mov     edx, 0F0030h
0x18009749c  mov     [rbp+90h+var_A8], rax
0x1800974a0  mov     rax, cs:?gRestrictedSpoolerServiceSid@@3PEAXEA; void * gRestrictedSpoolerServiceSid
0x1800974a7  mov     [rsp+190h+var_150], r14; __int64
0x1800974ac  mov     [rbp+90h+var_A0], rax
0x1800974b0  lea     rax, [rsp+190h+var_138]
0x1800974b5  mov     [rsp+190h+pGroup], 0; pGroup
0x1800974be  mov     [rsp+190h+pOwner], rcx; pOwner
0x1800974c3  mov     qword ptr [rbp+90h+var_B0], rcx
0x1800974c7  lea     rcx, [rsp+190h+var_120]; int
0x1800974cc  mov     [rbp+90h+var_FC], edx
0x1800974cf  mov     [rbp+90h+var_F8], edx
0x1800974d2  mov     edx, 3; int
0x1800974d7  mov     [rsp+190h+ReturnLength], rax; __int64
0x1800974dc  mov     word ptr [rsp+190h+var_120], 0
0x1800974e3  mov     [rbp+90h+var_100], 20020h
0x1800974ea  mov     word ptr [rsp+190h+var_138], 0
0x1800974f1  mov     byte ptr [rsp+190h+var_120+2], 0
0x1800974f6  mov     byte ptr [rsp+190h+var_138+2], 0
0x1800974fb  call    BuildPrintObjectProtection
0x180097500  test    eax, eax
0x180097502  jz      short loc_180097508
0x180097504  xor     ebx, ebx
0x180097506  jmp     short loc_180097510
0x180097508  call    cs:__imp_GetLastError
0x18009750e  mov     ebx, eax
0x180097510  mov     rcx, rdi
0x180097513  call    cs:__imp_DllFreeSplMem
0x180097519  jmp     short loc_180097523
0x18009751b  call    cs:__imp_GetLastError
0x180097521  mov     ebx, eax
0x180097523  mov     ecx, ebx; dwErrCode
0x180097525  call    cs:__imp_SetLastError
0x18009752b  xor     eax, eax
0x18009752d  lea     r11, [rsp+190h+var_10]
0x180097535  mov     rsi, [r11+38h]
0x180097539  test    ebx, ebx
0x18009753b  mov     rbx, [r11+30h]
0x18009753f  setz    al
0x180097542  mov     rsp, r11
0x180097545  pop     r14
0x180097547  pop     rdi
0x180097548  pop     rbp
0x180097549  retn
```
