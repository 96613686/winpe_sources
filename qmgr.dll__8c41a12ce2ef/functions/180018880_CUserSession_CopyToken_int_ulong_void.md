# CUserSession::CopyToken(int,ulong,void * *)

- ea: `0x180018880`
- end: `0x180018cef`
- name: `?CopyToken@CUserSession@@QEAAJHKPEAPEAX@Z`
- size: `1135`
- prototype: `__int64 __fastcall(PSID *this, int, DWORD, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001a6fc`

## callees

- `0x18000db20`
- `0x180016d60`
- `0x180018880`
- `0x180019514`
- `0x180072910`
- `0x180096b4c`
- `0x180098f3c`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800ab7b0`
- `0x1800c56e4`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018c74`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018c9e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018a9d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018a9d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180018be2`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180018be2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180018b3e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180018b3e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180018a1b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180018a1b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018905`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018905`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserSession::CopyToken(PSID *this, int a2, DWORD a3, void **a4)
{
  DWORD LastError; // eax
  signed int v9; // ebx
  unsigned int TokenIntegrityLevel; // ebx
  HANDLE v11; // r15
  unsigned int v12; // eax
  HANDLE v13; // rbx
  int v14; // ecx
  DWORD v15; // eax
  signed int v16; // ebx
  PDWORD SidSubAuthority; // rsi
  __int64 v18; // r9
  unsigned int v19; // ecx
  void *v20; // rcx
  __int64 result; // rax
  const ComError *v22; // rbx
  ComError *v23; // rax
  HANDLE TokenHandle; // [rsp+40h] [rbp-258h] BYREF
  void *v25; // [rsp+48h] [rbp-250h] BYREF
  PSID pSid; // [rsp+50h] [rbp-248h] BYREF
  void *v27; // [rsp+58h] [rbp-240h]
  const ComError *v28; // [rsp+60h] [rbp-238h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-228h] BYREF
  __int128 v30; // [rsp+78h] [rbp-220h]
  signed int v31; // [rsp+88h] [rbp-210h]
  int v32; // [rsp+8Ch] [rbp-20Ch]
  int v33; // [rsp+90h] [rbp-208h]
  void **v34; // [rsp+D0h] [rbp-1C8h] BYREF
  __int128 v35; // [rsp+D8h] [rbp-1C0h]
  signed int v36; // [rsp+E8h] [rbp-1B0h]
  int v37; // [rsp+ECh] [rbp-1ACh]
  int v38; // [rsp+F0h] [rbp-1A8h]
  void **v39; // [rsp+130h] [rbp-168h] BYREF
  __int128 v40; // [rsp+138h] [rbp-160h]
  int v41; // [rsp+148h] [rbp-150h]
  int v42; // [rsp+14Ch] [rbp-14Ch]
  int v43; // [rsp+150h] [rbp-148h]
  void **v44; // [rsp+190h] [rbp-108h] BYREF
  __int128 v45; // [rsp+198h] [rbp-100h]
  unsigned int v46; // [rsp+1A8h] [rbp-F0h]
  int v47; // [rsp+1ACh] [rbp-ECh]
  int v48; // [rsp+1B0h] [rbp-E8h]
  PSID TokenInformation; // [rsp+1F0h] [rbp-A8h] BYREF
  int v50; // [rsp+1F8h] [rbp-A0h]

  TokenHandle = 0;
  *a4 = 0;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dD_sid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      (int)&WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
      a2,
      a3,
      this[5]);
  try
  {
    CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v25);
    if ( !RevertToSelf() )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, LastError);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v30 = 0;
      pExceptionObject = &ComError::`vftable';
      v31 = v9;
      v32 = 1646;
      v33 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( a2 )
    {
      GetElevatedToken(this[2], &TokenHandle);
    }
    else if ( !DuplicateTokenEx(this[3], 0, 0, SecurityImpersonation, TokenPrimary, &TokenHandle) )
    {
      v15 = GetLastError();
      v16 = v15;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, v15);
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v35 = 0;
      v34 = &ComError::`vftable';
      v36 = v16;
      v37 = 1668;
      v38 = 1;
      throw (ComError *)&v34;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TokenIntegrityLevel = GetTokenIntegrityLevel(TokenHandle);
      v11 = TokenHandle;
      v12 = GetTokenIntegrityLevel(this[2]);
      WPP_SF_qDqD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
        this[2],
        v12,
        v11,
        TokenIntegrityLevel);
    }
    v13 = TokenHandle;
    GetTokenIntegrityLevelSid(&pSid, TokenHandle);
    v14 = *GetSidSubAuthorityCount(pSid);
    if ( !(_BYTE)v14 )
    {
      v40 = 0;
      v39 = &ComError::`vftable';
      v41 = -2147023537;
      v42 = 1456;
      v43 = 1;
      throw (ComError *)&v39;
    }
    SidSubAuthority = GetSidSubAuthority(pSid, v14 - 1);
    v18 = *SidSubAuthority;
    if ( (_DWORD)v18 == a3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27, 0xFFFFFFFF) == 1 )
      {
        operator delete(v27, 4u);
        operator delete(pSid, 0);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v18, a3);
      *SidSubAuthority = a3;
      v50 = 0;
      TokenInformation = pSid;
      if ( !SetTokenInformation(v13, TokenIntegrityLevel, &TokenInformation, 0x54u) )
      {
        if ( (int)GetLastError() > 0 )
          v19 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v19 = GetLastError();
        v45 = 0;
        v44 = &ComError::`vftable';
        v46 = v19;
        v47 = 1487;
        v48 = 1;
        throw (ComError *)&v44;
      }
      SidHandle::~SidHandle((SidHandle *)&pSid);
    }
    SetThreadToken(0, *(HANDLE *)v25);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 )
    {
      v20 = v25;
      if ( (unsigned __int64)(*(_QWORD *)v25 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v25);
        *(_QWORD *)v25 = 0;
        v20 = v25;
      }
      operator delete(v20, 0x10u);
    }
    *a4 = TokenHandle;
    result = 0;
  }
  catch ( const ComError *v28 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids);
    v22 = v28;
    v23 = ComError::ComError((ComError *)&TokenInformation, v28);
    LogException(v23);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return *((unsigned int *)v22 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x180018880  push    rbx
0x180018882  push    rsi
0x180018883  push    rdi
0x180018884  push    r12
0x180018886  push    r13
0x180018888  push    r14
0x18001888a  push    r15
0x18001888c  sub     rsp, 260h
0x180018893  mov     rax, cs:__security_cookie
0x18001889a  xor     rax, rsp
0x18001889d  mov     [rsp+298h+var_48], rax
0x1800188a5  mov     rdi, r9
0x1800188a8  mov     r14d, r8d
0x1800188ab  mov     ebx, edx
0x1800188ad  mov     rsi, rcx
0x1800188b0  xor     r13d, r13d
0x1800188b3  mov     [rsp+298h+TokenHandle], r13
0x1800188b8  mov     [r9], r13
0x1800188bb  lea     r12, WPP_GLOBAL_Control
0x1800188c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188c9  cmp     rcx, r12
0x1800188cc  jz      short loc_1800188FA
0x1800188ce  test    byte ptr [rcx+1Ch], 1
0x1800188d2  jz      short loc_1800188FA
0x1800188d4  mov     edx, 5Ah ; 'Z'; int
0x1800188d9  mov     rax, [rsi+28h]
0x1800188dd  mov     [rsp+298h+phNewToken], rax; pSid
0x1800188e2  mov     [rsp+298h+TokenType], r8d; char
0x1800188e7  mov     r9d, ebx; int
0x1800188ea  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids; int
0x1800188f1  mov     rcx, [rcx+10h]; int
0x1800188f5  call    WPP_SF_dD_sid_
0x1800188fa  lea     rcx, [rsp+298h+var_250]; this
0x1800188ff  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x180018904  nop
0x180018905  call    cs:__imp_RevertToSelf
0x18001890b  test    eax, eax
0x18001890d  jnz     loc_180018994
0x180018913  call    cs:__imp_GetLastError
0x180018919  mov     ebx, eax
0x18001891b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018922  cmp     rcx, r12
0x180018925  jz      short loc_180018945
0x180018927  test    byte ptr [rcx+1Ch], 4
0x18001892b  jz      short loc_180018945
0x18001892d  mov     edx, 5Bh ; '['
0x180018932  mov     r9d, eax
0x180018935  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x18001893c  mov     rcx, [rcx+10h]
0x180018940  call    WPP_SF_d
0x180018945  test    ebx, ebx
0x180018947  jle     short loc_180018952
0x180018949  movzx   ebx, bx
0x18001894c  or      ebx, 80070000h
0x180018952  xorps   xmm0, xmm0
0x180018955  movups  [rsp+298h+var_220], xmm0
0x18001895a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018961  mov     [rsp+298h+pExceptionObject], rax
0x180018966  mov     [rsp+298h+var_210], ebx
0x18001896d  mov     [rsp+298h+var_20C], 66Eh
0x180018978  mov     [rsp+298h+var_208], 1
0x180018983  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001898a  lea     rcx, [rsp+298h+pExceptionObject]; pExceptionObject
0x18001898f  call    _CxxThrowException_0
0x180018994  test    ebx, ebx
0x180018996  jz      loc_180018A7C
0x18001899c  lea     rdx, [rsp+298h+TokenHandle]; phNewToken
0x1800189a1  mov     rcx, [rsi+10h]; TokenHandle
0x1800189a5  call    ?GetElevatedToken@@YAXPEAXPEAPEAX@Z; GetElevatedToken(void *,void * *)
0x1800189aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800189b1  cmp     rax, r12
0x1800189b4  jz      short loc_180018A03
0x1800189b6  test    byte ptr [rax+1Ch], 1
0x1800189ba  jz      short loc_180018A03
0x1800189bc  mov     rcx, [rsp+298h+TokenHandle]; void *
0x1800189c1  call    ?GetTokenIntegrityLevel@@YAKPEAX@Z; GetTokenIntegrityLevel(void *)
0x1800189c6  mov     ebx, eax
0x1800189c8  mov     r15, [rsp+298h+TokenHandle]
0x1800189cd  mov     rcx, [rsi+10h]; void *
0x1800189d1  call    ?GetTokenIntegrityLevel@@YAKPEAX@Z; GetTokenIntegrityLevel(void *)
0x1800189d6  mov     edx, 5Dh ; ']'
0x1800189db  mov     [rsp+298h+var_268], ebx
0x1800189df  mov     [rsp+298h+phNewToken], r15
0x1800189e4  mov     [rsp+298h+TokenType], eax
0x1800189e8  mov     r9, [rsi+10h]
0x1800189ec  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x1800189f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189fa  mov     rcx, [rcx+10h]
0x1800189fe  call    WPP_SF_qDqD
0x180018a03  mov     rbx, [rsp+298h+TokenHandle]
0x180018a08  mov     rdx, rbx
0x180018a0b  lea     rcx, [rsp+298h+pSid]
0x180018a10  call    ?GetTokenIntegrityLevelSid@@YA?AVSidHandle@@PEAX@Z; GetTokenIntegrityLevelSid(void *)
0x180018a15  nop
0x180018a16  mov     rcx, [rsp+298h+pSid]; pSid
0x180018a1b  call    cs:__imp_GetSidSubAuthorityCount
0x180018a21  movzx   ecx, byte ptr [rax]
0x180018a24  test    cl, cl
0x180018a26  jnz     loc_180018B36
0x180018a2c  xorps   xmm0, xmm0
0x180018a2f  movups  [rsp+298h+var_160], xmm0
0x180018a37  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018a3e  mov     [rsp+298h+var_168], rax
0x180018a46  mov     [rsp+298h+var_150], 8007054Fh
0x180018a51  mov     [rsp+298h+var_14C], 5B0h
0x180018a5c  mov     [rsp+298h+var_148], 1
0x180018a67  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018a6e  lea     rcx, [rsp+298h+var_168]; pExceptionObject
0x180018a76  call    _CxxThrowException_0
0x180018a7c  lea     rax, [rsp+298h+TokenHandle]
0x180018a81  mov     [rsp+298h+phNewToken], rax; phNewToken
0x180018a86  mov     [rsp+298h+TokenType], 1; TokenType
0x180018a8e  mov     r9d, 2; ImpersonationLevel
0x180018a94  xor     r8d, r8d; lpTokenAttributes
0x180018a97  xor     edx, edx; dwDesiredAccess
0x180018a99  mov     rcx, [rsi+18h]; hExistingToken
0x180018a9d  call    cs:__imp_DuplicateTokenEx
0x180018aa3  test    eax, eax
0x180018aa5  jnz     loc_1800189AA
0x180018aab  call    cs:__imp_GetLastError
0x180018ab1  mov     ebx, eax
0x180018ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180018aba  cmp     rcx, r12
0x180018abd  jz      short loc_180018ADD
0x180018abf  test    byte ptr [rcx+1Ch], 4
0x180018ac3  jz      short loc_180018ADD
0x180018ac5  mov     edx, 5Ch ; '\'
0x180018aca  mov     r9d, eax
0x180018acd  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x180018ad4  mov     rcx, [rcx+10h]
0x180018ad8  call    WPP_SF_d
0x180018add  test    ebx, ebx
0x180018adf  jle     short loc_180018AEA
0x180018ae1  movzx   ebx, bx
0x180018ae4  or      ebx, 80070000h
0x180018aea  xorps   xmm0, xmm0
0x180018aed  movups  [rsp+298h+var_1C0], xmm0
0x180018af5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018afc  mov     [rsp+298h+var_1C8], rax
0x180018b04  mov     [rsp+298h+var_1B0], ebx
0x180018b0b  mov     [rsp+298h+var_1AC], 684h
0x180018b16  mov     [rsp+298h+var_1A8], 1
0x180018b21  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018b28  lea     rcx, [rsp+298h+var_1C8]; pExceptionObject
0x180018b30  call    _CxxThrowException_0
0x180018b36  lea     edx, [rcx-1]; nSubAuthority
0x180018b39  mov     rcx, [rsp+298h+pSid]; pSid
0x180018b3e  call    cs:__imp_GetSidSubAuthority
0x180018b44  mov     rsi, rax
0x180018b47  mov     r9d, [rax]
0x180018b4a  cmp     r9d, r14d
0x180018b4d  jnz     short loc_180018B88
0x180018b4f  mov     rcx, [rsp+298h+var_240]
0x180018b54  mov     ebx, 0FFFFFFFFh
0x180018b59  mov     eax, ebx
0x180018b5b  lock xadd [rcx], eax
0x180018b5f  cmp     eax, 1
0x180018b62  jnz     loc_180018C6A
0x180018b68  mov     edx, 4; unsigned __int64
0x180018b6d  mov     rcx, [rsp+298h+var_240]; void *
0x180018b72  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018b77  xor     edx, edx; unsigned __int64
0x180018b79  mov     rcx, [rsp+298h+pSid]; void *
0x180018b7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018b83  jmp     loc_180018C6A
0x180018b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b8f  cmp     rcx, r12
0x180018b92  jz      short loc_180018BB4
0x180018b94  test    byte ptr [rcx+1Ch], 2
0x180018b98  jz      short loc_180018BB4
0x180018b9a  mov     edx, 33h ; '3'
0x180018b9f  mov     [rsp+298h+TokenType], r14d
0x180018ba4  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180018bab  mov     rcx, [rcx+10h]
0x180018baf  call    WPP_SF_Dd
0x180018bb4  mov     [rsi], r14d
0x180018bb7  mov     [rsp+298h+var_A0], r13d
0x180018bbf  mov     rax, [rsp+298h+pSid]
0x180018bc4  mov     [rsp+298h+TokenInformation], rax
0x180018bcc  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180018bd2  lea     r8, [rsp+298h+TokenInformation]; TokenInformation
0x180018bda  mov     edx, 19h; TokenInformationClass
0x180018bdf  mov     rcx, rbx; TokenHandle
0x180018be2  call    cs:__imp_SetTokenInformation
0x180018be8  test    eax, eax
0x180018bea  jnz     short loc_180018C5B
0x180018bec  call    cs:__imp_GetLastError
0x180018bf2  test    eax, eax
0x180018bf4  jg      short loc_180018C00
0x180018bf6  call    cs:__imp_GetLastError
0x180018bfc  mov     ecx, eax
0x180018bfe  jmp     short loc_180018C0F
0x180018c00  call    cs:__imp_GetLastError
0x180018c06  movzx   ecx, ax
0x180018c09  or      ecx, 80070000h
0x180018c0f  xorps   xmm0, xmm0
0x180018c12  movups  [rsp+298h+var_100], xmm0
0x180018c1a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018c21  mov     [rsp+298h+var_108], rax
0x180018c29  mov     [rsp+298h+var_F0], ecx
0x180018c30  mov     [rsp+298h+var_EC], 5CFh
0x180018c3b  mov     [rsp+298h+var_E8], 1
0x180018c46  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018c4d  lea     rcx, [rsp+298h+var_108]; pExceptionObject
0x180018c55  call    _CxxThrowException_0
0x180018c5b  lea     rcx, [rsp+298h+pSid]; this
0x180018c60  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x180018c65  mov     ebx, 0FFFFFFFFh
0x180018c6a  mov     rdx, [rsp+298h+var_250]
0x180018c6f  mov     rdx, [rdx]; Token
0x180018c72  xor     ecx, ecx; Thread
0x180018c74  call    cs:__imp_SetThreadToken
0x180018c7a  mov     rax, [rsp+298h+var_250]
0x180018c7f  lock xadd [rax+8], ebx
0x180018c84  cmp     ebx, 1
0x180018c87  jnz     short loc_180018CBC
0x180018c89  mov     rcx, [rsp+298h+var_250]
0x180018c8e  mov     rdx, [rcx]
0x180018c91  lea     rax, [rdx-1]
0x180018c95  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018c99  ja      short loc_180018CB1
0x180018c9b  mov     rcx, rdx; hObject
0x180018c9e  call    cs:__imp_CloseHandle
0x180018ca4  mov     rax, [rsp+298h+var_250]
0x180018ca9  mov     [rax], r13
0x180018cac  mov     rcx, [rsp+298h+var_250]; void *
0x180018cb1  mov     edx, 10h; unsigned __int64
0x180018cb6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018cbb  nop
0x180018cbc  mov     rax, [rsp+298h+TokenHandle]
0x180018cc1  mov     [rdi], rax
0x180018cc4  xor     eax, eax
0x180018cc6  jmp     short loc_180018CCC
0x180018cc8  mov     eax, dword ptr [rsp+298h+TokenHandle]
0x180018ccc  mov     rcx, [rsp+298h+var_48]
0x180018cd4  xor     rcx, rsp; StackCookie
0x180018cd7  call    __security_check_cookie
0x180018cdc  add     rsp, 260h
0x180018ce3  pop     r15
0x180018ce5  pop     r14
0x180018ce7  pop     r13
0x180018ce9  pop     r12
0x180018ceb  pop     rdi
0x180018cec  pop     rsi
0x180018ced  pop     rbx
0x180018cee  retn
```
