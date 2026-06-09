# GetClientContext(void *,ushort,R<CAuthzClientContext> *)

- ea: `0x180061024`
- end: `0x180061340`
- name: `?GetClientContext@@YAXPEAXGPEAV?$R@VCAuthzClientContext@@@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048e24`

## callees

- `0x180004d91`
- `0x180009924`
- `0x18000f35c`
- `0x18000f430`
- `0x18000f7e4`
- `0x18000faec`
- `0x18002c61c`
- `0x180060fc0`
- `0x180061024`
- `0x1800613e4`
- `0x180061728`
- `0x180061884`
- `0x1800618f4`
- `0x1800619a4`
- `0x18009aa2c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800611fb`
- `msvcrt!free` at `0x18006131d`
- `msvcrt!free` at `0x1800611fb`
- `msvcrt!free` at `0x18006131d`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180061264`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180061264`
- `KERNEL32!GetLastError` at `0x18006126e`
- `KERNEL32!GetLastError` at `0x18006126e`
- `KERNEL32!LeaveCriticalSection` at `0x1800611f0`
- `KERNEL32!LeaveCriticalSection` at `0x180061312`
- `KERNEL32!LeaveCriticalSection` at `0x1800611f0`
- `KERNEL32!LeaveCriticalSection` at `0x180061312`
- `mqsec!MQSec_GetWorldSid` at `0x180061118`
- `mqsec!MQSec_GetWorldSid` at `0x180061118`
- `mqsec!MQSec_GetAnonymousSid` at `0x180061124`
- `mqsec!MQSec_GetAnonymousSid` at `0x180061124`

## string_xrefs

- `0x180061060`: `security`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall GetClientContext(void *a1, unsigned __int16 a2, __int64 a3)
{
  unsigned int v4; // ebx
  DWORD v6; // r15d
  void *AnonymousSid; // rax
  _DWORD *v8; // rdi
  __int64 AssocAt; // rax
  int v10; // ebx
  __int64 v11; // rbx
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  AUTHZ_RESOURCE_MANAGER_HANDLE ResourceManager; // rax
  DWORD LastError; // eax
  signed int v16; // ebx
  signed int v17; // ecx
  _DWORD *pExceptionObject; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h]
  _RTL_CRITICAL_SECTION *v20; // [rsp+60h] [rbp+7h]
  int v21; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v22; // [rsp+70h] [rbp+17h]
  const wchar_t *v23; // [rsp+78h] [rbp+1Fh]
  int v24; // [rsp+80h] [rbp+27h]
  __int64 v25; // [rsp+88h] [rbp+2Fh]
  int v26; // [rsp+C8h] [rbp+6Fh] BYREF
  void *Block; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = a2;
  if ( !byte_18013C620 )
  {
    v21 = 0;
    v22 = L"security";
    v23 = L"AuthzFlags";
    v24 = 0;
    v25 = 0;
    Flags = 0;
    QueryValueInternal((struct RegEntry *)&v21);
    byte_18013C620 = 1;
  }
  v6 = Flags;
  if ( !v4 )
  {
    AnonymousSid = MQSec_GetAnonymousSid();
LABEL_12:
    a1 = AnonymousSid;
    goto LABEL_13;
  }
  if ( v4 != 1 )
  {
    if ( v4 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, &WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids, v4);
      bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, 0x539u);
      throw (bad_win32_error *)&pExceptionObject;
    }
    AnonymousSid = MQSec_GetWorldSid();
    v6 |= 2u;
    goto LABEL_12;
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_d_sid_(*((_QWORD *)WPP_GLOBAL_Control + 32), a1);
  Block = 0;
  CUserSid::SetSid((CUserSid *)&Block, a1);
  v20 = &stru_18013AF58;
  CCriticalSection::Lock((CCriticalSection *)&stru_18013AF58);
  v8 = 0;
  pExceptionObject = 0;
  v19 = 0;
  v26 = 0;
  AssocAt = CMap<CUserSid,CUserSid const &,CCacheEntry<R<CAuthzClientContext>,R<CAuthzClientContext> const &>,CCacheEntry<R<CAuthzClientContext>,R<CAuthzClientContext> const &> const &>::GetAssocAt(
              &qword_18013AFD0,
              &Block,
              &v26);
  if ( AssocAt )
  {
    v11 = AssocAt + 24;
    R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(&pExceptionObject, AssocAt + 24);
    v19 = *(_QWORD *)(v11 + 8);
    v10 = 1;
    v8 = pExceptionObject;
  }
  else
  {
    v10 = 0;
  }
  R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(a3, &pExceptionObject);
  SafeRelease<CSockTransport>(v8);
  if ( v10 )
  {
    LeaveCriticalSection(&stru_18013AF58);
    free(Block);
  }
  else
  {
    v12 = MmAllocate(0x18u);
    v13 = v12;
    pExceptionObject = v12;
    if ( v12 )
    {
      v12[2] = 1;
      *(_QWORD *)v12 = &CAuthzClientContext::`vftable';
      *((_QWORD *)v12 + 2) = 0;
    }
    else
    {
      v13 = 0;
    }
    pExceptionObject = v13;
    ResourceManager = (AUTHZ_RESOURCE_MANAGER_HANDLE)GetResourceManager();
    if ( !AuthzInitializeContextFromSid(v6, a1, ResourceManager, 0, 0, 0, (PAUTHZ_CLIENT_CONTEXT_HANDLE)v13 + 2) )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), LastError);
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      else
        v17 = v16;
      if ( v17 < 0 )
        LogMsgHR(v17, (wchar_t *)L"usermap", 0xAu);
      bad_win32_error::bad_win32_error((bad_win32_error *)&v21, v16);
      throw (bad_win32_error *)&v21;
    }
    CCache<CUserSid,R<CAuthzClientContext>,CNullExpirationHandler<R<CAuthzClientContext>>>::SetAt(
      &qword_18013AF50,
      &Block,
      &pExceptionObject);
    R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(a3, &pExceptionObject);
    SafeRelease<CSockTransport>(v13);
    LeaveCriticalSection(&stru_18013AF58);
    free(Block);
  }
}

```

## disassembly

```asm
0x180061024  mov     [rsp-8+arg_0], rbx
0x180061029  mov     [rsp-8+arg_10], rsi
0x18006102e  push    rbp
0x18006102f  push    rdi
0x180061030  push    r12
0x180061032  push    r14
0x180061034  push    r15
0x180061036  lea     rbp, [rsp-37h]
0x18006103b  sub     rsp, 90h
0x180061042  mov     r12, r8
0x180061045  movzx   ebx, dx
0x180061048  mov     rsi, rcx
0x18006104b  mov     edi, 4
0x180061050  cmp     cs:byte_18013C620, 0
0x180061057  jnz     short loc_1800610AB
0x180061059  mov     [rbp+57h+var_48], 0
0x180061060  lea     rax, aSecurity_0; "security"
0x180061067  mov     [rbp+57h+var_40], rax
0x18006106b  lea     rax, aAuthzflags; "AuthzFlags"
0x180061072  mov     [rbp+57h+var_38], rax
0x180061076  mov     [rbp+57h+var_30], 0
0x18006107d  mov     [rbp+57h+var_28], 0
0x180061085  mov     cs:Flags, 0
0x18006108f  mov     r9d, edi
0x180061092  lea     r8, Flags
0x180061099  mov     edx, edi
0x18006109b  lea     rcx, [rbp+57h+var_48]; struct RegEntry *
0x18006109f  call    QueryValueInternal
0x1800610a4  mov     cs:byte_18013C620, 1
0x1800610ab  mov     r15d, cs:Flags
0x1800610b2  mov     ecx, ebx
0x1800610b4  test    ebx, ebx
0x1800610b6  jz      short loc_180061124
0x1800610b8  sub     ecx, 1
0x1800610bb  jz      short loc_18006112D
0x1800610bd  cmp     ecx, 1
0x1800610c0  jz      short loc_180061118
0x1800610c2  lea     r14, WPP_GLOBAL_Control
0x1800610c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800610d0  cmp     rcx, r14
0x1800610d3  jz      short loc_1800610F9
0x1800610d5  test    byte ptr [rcx+10Ch], 1
0x1800610dc  jz      short loc_1800610F9
0x1800610de  mov     edx, 0Ah
0x1800610e3  mov     r9d, ebx
0x1800610e6  lea     r8, WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids
0x1800610ed  mov     rcx, [rcx+100h]
0x1800610f4  call    WPP_SF_d
0x1800610f9  mov     edx, 539h; unsigned int
0x1800610fe  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180061102  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180061107  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18006110e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180061112  call    _CxxThrowException_0
0x180061118  call    cs:__imp_?MQSec_GetWorldSid@@YAPEAXXZ; MQSec_GetWorldSid(void)
0x18006111e  or      r15d, 2
0x180061122  jmp     short loc_18006112A
0x180061124  call    cs:__imp_?MQSec_GetAnonymousSid@@YAPEAXXZ; MQSec_GetAnonymousSid(void)
0x18006112a  mov     rsi, rax
0x18006112d  lea     r14, WPP_GLOBAL_Control
0x180061134  mov     rcx, cs:WPP_GLOBAL_Control
0x18006113b  cmp     rcx, r14
0x18006113e  jz      short loc_18006115D
0x180061140  test    [rcx+10Ch], dil
0x180061147  jz      short loc_18006115D
0x180061149  mov     qword ptr [rsp+0B0h+Identifier.LowPart], rsi; pSid
0x18006114e  mov     r9d, ebx
0x180061151  mov     rcx, [rcx+100h]; LoggerHandle
0x180061158  call    WPP_SF_d_sid_
0x18006115d  mov     [rbp+57h+Block], 0
0x180061165  mov     rdx, rsi; void *
0x180061168  lea     rcx, [rbp+57h+Block]; this
0x18006116c  call    ?SetSid@CUserSid@@QEAAXPEBX@Z; CUserSid::SetSid(void const *)
0x180061171  lea     rax, stru_18013AF58
0x180061178  mov     [rbp+57h+var_50], rax
0x18006117c  mov     rcx, rax; this
0x18006117f  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180061184  nop
0x180061185  xor     edi, edi
0x180061187  mov     [rbp+57h+pExceptionObject], rdi
0x18006118b  mov     [rbp+57h+var_68], rdi
0x18006118f  mov     [rbp+57h+arg_8], edi
0x180061192  lea     r8, [rbp+57h+arg_8]
0x180061196  lea     rdx, [rbp+57h+Block]
0x18006119a  lea     rcx, qword_18013AFD0
0x1800611a1  call    ?GetAssocAt@?$CMap@VCUserSid@@AEBV1@V?$CCacheEntry@V?$R@VCAuthzClientContext@@@@AEBV1@@@AEBV2@@@IEBAPEAUCAssoc@1@AEBVCUserSid@@AEAI@Z; CMap<CUserSid,CUserSid const &,CCacheEntry<R<CAuthzClientContext>,R<CAuthzClientContext> const &>,CCacheEntry<R<CAuthzClientContext>,R<CAuthzClientContext> const &> const &>::GetAssocAt(CUserSid const &,uint &)
0x1800611a6  test    rax, rax
0x1800611a9  jnz     short loc_1800611AF
0x1800611ab  xor     ebx, ebx
0x1800611ad  jmp     short loc_1800611D0
0x1800611af  lea     rbx, [rax+18h]
0x1800611b3  mov     rdx, rbx
0x1800611b6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800611ba  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x1800611bf  mov     rax, [rbx+8]
0x1800611c3  mov     [rbp+57h+var_68], rax
0x1800611c7  mov     ebx, 1
0x1800611cc  mov     rdi, [rbp+57h+pExceptionObject]
0x1800611d0  lea     rdx, [rbp+57h+pExceptionObject]
0x1800611d4  mov     rcx, r12
0x1800611d7  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x1800611dc  nop
0x1800611dd  mov     rcx, rdi
0x1800611e0  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x1800611e5  test    ebx, ebx
0x1800611e7  jz      short loc_180061207
0x1800611e9  lea     rcx, stru_18013AF58; lpCriticalSection
0x1800611f0  call    cs:__imp_LeaveCriticalSection
0x1800611f6  nop
0x1800611f7  mov     rcx, [rbp+57h+Block]; Block
0x1800611fb  call    cs:__imp_free
0x180061201  nop
0x180061202  jmp     loc_180061324
0x180061207  mov     ecx, 18h; unsigned __int64
0x18006120c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180061211  mov     rdi, rax
0x180061214  mov     [rbp+57h+pExceptionObject], rax
0x180061218  test    rax, rax
0x18006121b  jz      short loc_180061238
0x18006121d  mov     dword ptr [rax+8], 1
0x180061224  lea     rax, ??_7CAuthzClientContext@@6B@; const CAuthzClientContext::`vftable'
0x18006122b  mov     [rdi], rax
0x18006122e  mov     qword ptr [rdi+10h], 0
0x180061236  jmp     short loc_18006123A
0x180061238  xor     edi, edi
0x18006123a  mov     [rbp+57h+pExceptionObject], rdi
0x18006123e  xor     ebx, ebx
0x180061240  call    GetResourceManager
0x180061245  lea     rdx, [rdi+10h]
0x180061249  mov     [rsp+0B0h+phAuthzClientContext], rdx; phAuthzClientContext
0x18006124e  mov     [rsp+0B0h+DynamicGroupArgs], rbx; DynamicGroupArgs
0x180061253  mov     qword ptr [rsp+0B0h+Identifier.LowPart], rbx; Identifier
0x180061258  xor     r9d, r9d; pExpirationTime
0x18006125b  mov     r8, rax; hAuthzResourceManager
0x18006125e  mov     rdx, rsi; UserSid
0x180061261  mov     ecx, r15d; Flags
0x180061264  call    cs:__imp_AuthzInitializeContextFromSid
0x18006126a  test    eax, eax
0x18006126c  jnz     short loc_1800612E1
0x18006126e  call    cs:__imp_GetLastError
0x180061274  mov     ebx, eax
0x180061276  mov     rcx, cs:WPP_GLOBAL_Control
0x18006127d  cmp     rcx, r14
0x180061280  jz      short loc_18006129E
0x180061282  test    byte ptr [rcx+10Ch], 1
0x180061289  jz      short loc_18006129E
0x18006128b  mov     [rsp+0B0h+Identifier.LowPart], eax; char
0x18006128f  mov     r9, rsi
0x180061292  mov     rcx, [rcx+100h]; LoggerHandle
0x180061299  call    WPP_SF__sid_D
0x18006129e  test    ebx, ebx
0x1800612a0  jg      short loc_1800612A6
0x1800612a2  mov     ecx, ebx
0x1800612a4  jmp     short loc_1800612AF
0x1800612a6  movzx   ecx, bx
0x1800612a9  or      ecx, 80070000h; int
0x1800612af  test    ecx, ecx
0x1800612b1  jns     short loc_1800612C5
0x1800612b3  mov     r8d, 0Ah; unsigned __int16
0x1800612b9  lea     rdx, aUsermap; "usermap"
0x1800612c0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800612c5  mov     edx, ebx; unsigned int
0x1800612c7  lea     rcx, [rbp+57h+var_48]; this
0x1800612cb  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800612d0  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800612d7  lea     rcx, [rbp+57h+var_48]; pExceptionObject
0x1800612db  call    _CxxThrowException_0
0x1800612e1  lea     r8, [rbp+57h+pExceptionObject]
0x1800612e5  lea     rdx, [rbp+57h+Block]
0x1800612e9  lea     rcx, qword_18013AF50
0x1800612f0  call    ?SetAt@?$CCache@VCUserSid@@V?$R@VCAuthzClientContext@@@@V?$CNullExpirationHandler@V?$R@VCAuthzClientContext@@@@@@@@QEAAXAEBVCUserSid@@AEBV?$R@VCAuthzClientContext@@@@@Z; CCache<CUserSid,R<CAuthzClientContext>,CNullExpirationHandler<R<CAuthzClientContext>>>::SetAt(CUserSid const &,R<CAuthzClientContext> const &)
0x1800612f5  lea     rdx, [rbp+57h+pExceptionObject]
0x1800612f9  mov     rcx, r12
0x1800612fc  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x180061301  nop
0x180061302  mov     rcx, rdi
0x180061305  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x18006130a  nop
0x18006130b  lea     rcx, stru_18013AF58; lpCriticalSection
0x180061312  call    cs:__imp_LeaveCriticalSection
0x180061318  nop
0x180061319  mov     rcx, [rbp+57h+Block]; Block
0x18006131d  call    cs:__imp_free
0x180061323  nop
0x180061324  lea     r11, [rsp+0B0h+var_20]
0x18006132c  mov     rbx, [r11+30h]
0x180061330  mov     rsi, [r11+40h]
0x180061334  mov     rsp, r11
0x180061337  pop     r15
0x180061339  pop     r14
0x18006133b  pop     r12
0x18006133d  pop     rdi
0x18006133e  pop     rbp
0x18006133f  retn
```
