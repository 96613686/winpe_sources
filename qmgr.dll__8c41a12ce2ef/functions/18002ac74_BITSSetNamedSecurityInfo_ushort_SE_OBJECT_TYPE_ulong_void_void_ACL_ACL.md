# BITSSetNamedSecurityInfo(ushort *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)

- ea: `0x18002ac74`
- end: `0x18002af09`
- name: `?BITSSetNamedSecurityInfo@@YAJPEAGW4_SE_OBJECT_TYPE@@KPEAX2PEAU_ACL@@3@Z`
- size: `661`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, enum _SE_OBJECT_TYPE, SECURITY_INFORMATION, void *, PSID psidGroup, struct _ACL *pDacl, struct _ACL *pSacl)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180029d80`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000f5f0`
- `0x180012b18`
- `0x180014310`
- `0x18002ac74`
- `0x18009d024`
- `0x1800c7278`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ada8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ada8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002adbc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002adbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adc6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002ad0c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002ae6c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002ad0c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002ae6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BITSSetNamedSecurityInfo(
        LPWSTR pObjectName,
        enum _SE_OBJECT_TYPE a2,
        SECURITY_INFORMATION a3,
        void *a4,
        PSID psidGroup,
        struct _ACL *pDacl,
        struct _ACL *pSacl)
{
  int v10; // esi
  signed int v11; // eax
  _DWORD *v12; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  __int64 result; // rax
  signed int v16; // eax
  ComError *v17; // rbx
  ComError *v18; // rax
  _BYTE v19[8]; // [rsp+40h] [rbp-178h] BYREF
  _DWORD *v20; // [rsp+48h] [rbp-170h] BYREF
  ComError *v21; // [rsp+50h] [rbp-168h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-158h] BYREF
  __int128 v23; // [rsp+68h] [rbp-150h]
  signed int v24; // [rsp+78h] [rbp-140h]
  int v25; // [rsp+7Ch] [rbp-13Ch]
  int v26; // [rsp+80h] [rbp-138h]
  void **v27; // [rsp+C0h] [rbp-F8h] BYREF
  __int128 v28; // [rsp+C8h] [rbp-F0h]
  signed int v29; // [rsp+D8h] [rbp-E0h]
  int v30; // [rsp+DCh] [rbp-DCh]
  int v31; // [rsp+E0h] [rbp-D8h]
  _BYTE v32[152]; // [rsp+120h] [rbp-98h] BYREF

  try
  {
    v10 = a3 & 1;
    if ( (a3 & 1) != 0 || (a3 & 0xA) != 0 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
      v12 = operator new(0x10u);
      v20 = v12;
      v12[2] = 1;
      *(_QWORD *)v12 = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, (PHANDLE)v12) )
      {
        LastError = GetLastError();
        TokenHandle::Decrement((TokenHandle *)&v20);
        return LastError;
      }
      TokenHandle::copyEx(&v20, v19, 2, 2);
      if ( v10 || (a3 & 2) != 0 )
        TokenHandle::EnablePrivilege((TokenHandle *)v19, 18);
      if ( (a3 & 8) != 0 )
        TokenHandle::EnablePrivilege((TokenHandle *)v19, 8);
      CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v32, (const struct TokenHandle *)v19);
      v16 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, a3, a4, psidGroup, pDacl, pSacl);
      if ( v16 )
      {
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        v28 = 0;
        v27 = &ComError::`vftable';
        v29 = v16;
        v30 = 2917;
        v31 = 1;
        throw (ComError *)&v27;
      }
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v32);
      TokenHandle::Decrement((TokenHandle *)v19);
      TokenHandle::Decrement((TokenHandle *)&v20);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
      v11 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, a3, a4, psidGroup, pDacl, pSacl);
      if ( v11 )
      {
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        v23 = 0;
        pExceptionObject = &ComError::`vftable';
        v24 = v11;
        v25 = 2936;
        v26 = 1;
        throw (ComError *)&pExceptionObject;
      }
    }
    result = 0;
  }
  catch ( ComError *v21 )
  {
    v17 = v21;
    v18 = ComError::ComError((ComError *)v32, v21);
    LogException(v18);
    return *((unsigned int *)v17 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18002ac74  mov     [rsp+arg_8], edx
0x18002ac78  push    rbx
0x18002ac79  push    rsi
0x18002ac7a  push    rdi
0x18002ac7b  push    r12
0x18002ac7d  push    r14
0x18002ac7f  push    r15
0x18002ac81  sub     rsp, 188h
0x18002ac88  mov     r14, r9
0x18002ac8b  mov     edi, r8d
0x18002ac8e  mov     r15, rcx
0x18002ac91  mov     esi, r8d
0x18002ac94  mov     r12d, 1
0x18002ac9a  and     esi, r12d
0x18002ac9d  jnz     loc_18002AD5D
0x18002aca3  test    dil, 0Ah
0x18002aca7  jnz     loc_18002AD5D
0x18002acad  lea     rax, WPP_GLOBAL_Control
0x18002acb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acbb  cmp     rcx, rax
0x18002acbe  jz      short loc_18002ACD9
0x18002acc0  test    [rcx+1Ch], r12b
0x18002acc4  jz      short loc_18002ACD9
0x18002acc6  lea     edx, [rsi+2Dh]
0x18002acc9  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002acd0  mov     rcx, [rcx+10h]
0x18002acd4  call    WPP_SF_
0x18002acd9  mov     rax, [rsp+1B8h+arg_30]
0x18002ace1  mov     [rsp+1B8h+pSacl], rax; pSacl
0x18002ace6  mov     rax, [rsp+1B8h+arg_28]
0x18002acee  mov     [rsp+1B8h+pDacl], rax; pDacl
0x18002acf3  mov     rax, [rsp+1B8h+arg_20]
0x18002acfb  mov     [rsp+1B8h+psidGroup], rax; psidGroup
0x18002ad00  mov     r9, r14; psidOwner
0x18002ad03  mov     r8d, edi; SecurityInfo
0x18002ad06  mov     edx, r12d; ObjectType
0x18002ad09  mov     rcx, r15; pObjectName
0x18002ad0c  call    cs:__imp_SetNamedSecurityInfoW
0x18002ad12  test    eax, eax
0x18002ad14  jz      loc_18002AEEC
0x18002ad1a  jle     short loc_18002AD24
0x18002ad1c  movzx   eax, ax
0x18002ad1f  or      eax, 80070000h
0x18002ad24  xorps   xmm0, xmm0
0x18002ad27  movups  [rsp+1B8h+var_150], xmm0
0x18002ad2c  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ad33  mov     [rsp+1B8h+pExceptionObject], rcx
0x18002ad38  mov     [rsp+1B8h+var_140], eax
0x18002ad3c  mov     [rsp+1B8h+var_13C], 0B78h
0x18002ad44  mov     [rsp+1B8h+var_138], r12d
0x18002ad4c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002ad53  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x18002ad58  call    _CxxThrowException_0
0x18002ad5d  lea     rax, WPP_GLOBAL_Control
0x18002ad64  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad6b  cmp     rcx, rax
0x18002ad6e  jz      short loc_18002AD8B
0x18002ad70  test    [rcx+1Ch], r12b
0x18002ad74  jz      short loc_18002AD8B
0x18002ad76  mov     edx, 2Ch ; ','
0x18002ad7b  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002ad82  mov     rcx, [rcx+10h]
0x18002ad86  call    WPP_SF_
0x18002ad8b  mov     ecx, 10h; dwBytes
0x18002ad90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ad95  mov     rbx, rax
0x18002ad98  mov     [rsp+1B8h+var_170], rax
0x18002ad9d  mov     [rax+8], r12d
0x18002ada1  mov     qword ptr [rax], 0
0x18002ada8  call    cs:__imp_GetCurrentThread
0x18002adae  mov     r9, rbx; TokenHandle
0x18002adb1  mov     r8d, r12d; OpenAsSelf
0x18002adb4  mov     edx, 0F01FFh; DesiredAccess
0x18002adb9  mov     rcx, rax; ThreadHandle
0x18002adbc  call    cs:__imp_OpenThreadToken
0x18002adc2  test    eax, eax
0x18002adc4  jnz     short loc_18002ADDF
0x18002adc6  call    cs:__imp_GetLastError
0x18002adcc  mov     ebx, eax
0x18002adce  lea     rcx, [rsp+1B8h+var_170]; this
0x18002add3  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18002add8  mov     eax, ebx
0x18002adda  jmp     loc_18002AEF7
0x18002addf  mov     ebx, 2
0x18002ade4  mov     r9d, ebx
0x18002ade7  mov     r8d, ebx
0x18002adea  lea     rdx, [rsp+1B8h+var_178]
0x18002adef  lea     rcx, [rsp+1B8h+var_170]
0x18002adf4  call    ?copyEx@TokenHandle@@QEBA?AV1@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z; TokenHandle::copyEx(_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)
0x18002adf9  nop
0x18002adfa  test    esi, esi
0x18002adfc  jnz     short loc_18002AE03
0x18002adfe  test    bl, dil
0x18002ae01  jz      short loc_18002AE12
0x18002ae03  mov     edx, 12h; int
0x18002ae08  lea     rcx, [rsp+1B8h+var_178]; this
0x18002ae0d  call    ?EnablePrivilege@TokenHandle@@QEAAXJ@Z; TokenHandle::EnablePrivilege(long)
0x18002ae12  mov     edx, 8; int
0x18002ae17  test    dl, dil
0x18002ae1a  jz      short loc_18002AE26
0x18002ae1c  lea     rcx, [rsp+1B8h+var_178]; this
0x18002ae21  call    ?EnablePrivilege@TokenHandle@@QEAAXJ@Z; TokenHandle::EnablePrivilege(long)
0x18002ae26  lea     rdx, [rsp+1B8h+var_178]; struct TokenHandle *
0x18002ae2b  lea     rcx, [rsp+1B8h+var_98]; this
0x18002ae33  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x18002ae38  nop
0x18002ae39  mov     rax, [rsp+1B8h+arg_30]
0x18002ae41  mov     [rsp+1B8h+pSacl], rax; pSacl
0x18002ae46  mov     rax, [rsp+1B8h+arg_28]
0x18002ae4e  mov     [rsp+1B8h+pDacl], rax; pDacl
0x18002ae53  mov     rax, [rsp+1B8h+arg_20]
0x18002ae5b  mov     [rsp+1B8h+psidGroup], rax; psidGroup
0x18002ae60  mov     r9, r14; psidOwner
0x18002ae63  mov     r8d, edi; SecurityInfo
0x18002ae66  mov     edx, r12d; ObjectType
0x18002ae69  mov     rcx, r15; pObjectName
0x18002ae6c  call    cs:__imp_SetNamedSecurityInfoW
0x18002ae72  test    eax, eax
0x18002ae74  jz      short loc_18002AEC9
0x18002ae76  jle     short loc_18002AE80
0x18002ae78  movzx   eax, ax
0x18002ae7b  or      eax, 80070000h
0x18002ae80  xorps   xmm0, xmm0
0x18002ae83  movups  [rsp+1B8h+var_F0], xmm0
0x18002ae8b  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ae92  mov     [rsp+1B8h+var_F8], rcx
0x18002ae9a  mov     [rsp+1B8h+var_E0], eax
0x18002aea1  mov     [rsp+1B8h+var_DC], 0B65h
0x18002aeac  mov     [rsp+1B8h+var_D8], r12d
0x18002aeb4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002aebb  lea     rcx, [rsp+1B8h+var_F8]; pExceptionObject
0x18002aec3  call    _CxxThrowException_0
0x18002aec9  lea     rcx, [rsp+1B8h+var_98]; this
0x18002aed1  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x18002aed6  nop
0x18002aed7  lea     rcx, [rsp+1B8h+var_178]; this
0x18002aedc  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18002aee1  nop
0x18002aee2  lea     rcx, [rsp+1B8h+var_170]; this
0x18002aee7  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18002aeec  xor     eax, eax
0x18002aeee  jmp     short loc_18002AEF7
0x18002aef0  mov     eax, [rsp+1B8h+arg_8]
0x18002aef7  add     rsp, 188h
0x18002aefe  pop     r15
0x18002af00  pop     r14
0x18002af02  pop     r12
0x18002af04  pop     rdi
0x18002af05  pop     rsi
0x18002af06  pop     rbx
0x18002af07  retn
```
