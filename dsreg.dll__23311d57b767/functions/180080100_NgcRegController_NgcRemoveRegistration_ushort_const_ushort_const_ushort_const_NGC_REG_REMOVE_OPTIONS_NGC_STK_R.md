# NgcRegController::NgcRemoveRegistration(ushort const *,ushort const *,ushort const *,_NGC_REG_REMOVE_OPTIONS,NGC_STK_REMOVE_OPTIONS)

- ea: `0x180080100`
- end: `0x1800805c8`
- name: `?NgcRemoveRegistration@NgcRegController@@SAJPEBG00W4_NGC_REG_REMOVE_OPTIONS@@W4NGC_STK_REMOVE_OPTIONS@@@Z`
- size: `1224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18007dd88`
- `0x18007e020`
- `0x18007f064`
- `0x18007fb20`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000ab70`
- `0x18000bac0`
- `0x18000bd20`
- `0x18001288c`
- `0x180012eb8`
- `0x180043cac`
- `0x180080100`
- `0x180081b74`
- `0x1800822b0`
- `0x18008271c`
- `0x1800830b0`
- `0x180094d24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008036c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008051b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008036c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008051b`

## string_xrefs

- `0x1800803ba`: `%s: Password-less state successfully reset for UserSid: %s`
- `0x1800803ac`: `%s: ResetPasswordLessNgcSetState for UserSid %s failed with error code: 0x%08x.`
- `0x1800805bb`: `KeyManager::DeleteContainer`
- `0x18008015e`: `NgcRegController::NgcRemoveRegistration`
- `0x18008038b`: `%s: User SID is empty. Cannot reset password-less NGC set state.`
- `0x18008035c`: `%s: GetCurrentUserSid failed with error code: 0x%08x.`
- `0x180080418`: `%s: User SID is empty. Cannot delete NGC container or keys.`
- `0x180080596`: `%s: Tenant ID is empty. Cannot delete user NGC key.`
- `0x180080445`: `%s: User email is empty. Cannot delete user NGC key.`
- `0x1800804a2`: `%s: KeyManager::DeleteUserKey failed with error code: 0x%08x. Ignoring this error as requested.`
- `0x180080580`: `KeyManager::DeleteUserKey`
- `0x180080501`: `NgcStatusStorage::Delete`
- `0x1800804e7`: `%s: NGC container and keys are successfully deleted. IDP domain: %s, Tenant ID: %s, User email: %s, UserSid: %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcRegController::NgcRemoveRegistration(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  const unsigned __int16 *v5; // rsi
  const unsigned __int16 *v6; // rdi
  const unsigned __int16 *v7; // r14
  const wchar_t *v8; // r15
  const wchar_t *v9; // rax
  const wchar_t *v10; // r9
  const wchar_t *v11; // r8
  char v12; // dl
  char v13; // r8
  int v14; // r9d
  char v15; // al
  int JoinInfo; // eax
  const WCHAR *v17; // r9
  const WCHAR *v18; // r8
  __int64 v19; // rdx
  const unsigned __int16 **v20; // rax
  const unsigned __int16 *v21; // rcx
  const WCHAR *v22; // r8
  __int64 v23; // rdx
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rdx
  const unsigned __int16 *v26; // rcx
  int CurrentUserSid; // eax
  const unsigned __int16 *v28; // rcx
  const unsigned __int16 *v29; // rcx
  int v30; // eax
  int v31; // eax
  const wchar_t *v32; // r8
  NgcStatusStorage *v33; // rcx
  const wchar_t *v34; // rdx
  int v35; // ebx
  int v36; // ebx
  int v37; // eax
  const wchar_t *v38; // rcx
  const wchar_t *v39; // rax
  const wchar_t *v40; // r9
  int v41; // eax
  unsigned int v42; // ebx
  char v44; // dl
  _QWORD v45[2]; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int16 *v46[2]; // [rsp+50h] [rbp-61h] BYREF
  __int128 v47; // [rsp+60h] [rbp-51h]
  __int64 v48; // [rsp+70h] [rbp-41h]
  __int64 v49; // [rsp+78h] [rbp-39h]
  __int64 v50; // [rsp+80h] [rbp-31h]
  int v51; // [rsp+88h] [rbp-29h]
  __int128 v52; // [rsp+90h] [rbp-21h]
  __int64 v53; // [rsp+A0h] [rbp-11h]
  __int64 v54; // [rsp+A8h] [rbp-9h]
  __int64 v55; // [rsp+B0h] [rbp-1h]
  int v56; // [rsp+B8h] [rbp+7h]
  __int64 v57; // [rsp+C0h] [rbp+Fh]
  __int64 v58; // [rsp+C8h] [rbp+17h]
  HLOCAL hMem; // [rsp+110h] [rbp+5Fh] BYREF
  const unsigned __int16 *v60; // [rsp+118h] [rbp+67h] BYREF
  void *Block; // [rsp+120h] [rbp+6Fh] BYREF

  v5 = a3;
  v6 = a2;
  v7 = a1;
  v8 = L"<NULL>";
  v9 = L"<NULL>";
  if ( a3 )
    v9 = a3;
  v10 = L"<NULL>";
  if ( a2 )
    v10 = a2;
  v11 = L"<NULL>";
  if ( a1 )
    v11 = a1;
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. User email: %s, Tenant ID: %s, IDP domain: %s, Options: %d, STK Opions: %d.",
    L"NgcRegController::NgcRemoveRegistration",
    v11,
    v10,
    v9,
    a4,
    0);
  v47 = 0;
  v48 = 0;
  *(_OWORD *)v46 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v45[0] = 0;
  v45[1] = 0;
  Block = 0;
  v60 = 0;
  hMem = 0;
  IsEmptyString(v7);
  IsEmptyString(v6);
  if ( !(unsigned int)IsEmptyString(v5) || (v15 = 1, (a4 & v14) == 0) )
    v15 = 0;
  if ( v13 || v12 || v15 )
  {
    if ( !(unsigned int)IsEmptyString(v6) )
      v60 = v6;
    JoinInfo = DsrGetJoinInfoEx(1, &v60, &Block);
    if ( JoinInfo >= 0 )
    {
      if ( Block )
      {
        if ( (unsigned int)IsEmptyString(v7) )
        {
          v20 = *(const unsigned __int16 ***)(v19 + 176);
          if ( !v20 || (unsigned int)IsEmptyString(*v20) )
          {
            v22 = &cchOriginalDestLength;
            if ( v60 )
              v22 = v60;
            Logger::TraceVerbose(
              (wchar_t *)L"%s: DsrGetJoinInfoEx returns empty NGC user email. Tenand ID: %s.",
              L"NgcRegController::NgcRemoveRegistration",
              v22);
          }
          else
          {
            v7 = v21;
          }
        }
        if ( (unsigned int)IsEmptyString(v6) )
        {
          if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(v23 + 32)) )
            Logger::TraceVerbose(
              (wchar_t *)L"%s: DsrGetJoinInfoEx returns empty tenant ID.",
              L"NgcRegController::NgcRemoveRegistration");
          else
            v6 = v24;
        }
        if ( (unsigned int)IsEmptyString(v5) )
        {
          if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(v25 + 24)) )
            Logger::TraceVerbose(
              (wchar_t *)L"%s: DsrGetJoinInfoEx returns empty IDP domain.",
              L"NgcRegController::NgcRemoveRegistration");
          else
            v5 = v26;
        }
      }
      else
      {
        v18 = &cchOriginalDestLength;
        if ( v60 )
          v18 = v60;
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Device is not joined. DsrGetJoinInfoEx returns NULL. Tenand ID: %s.",
          L"NgcRegController::NgcRemoveRegistration",
          v18);
      }
    }
    else
    {
      v17 = &cchOriginalDestLength;
      if ( v60 )
        v17 = v60;
      Logger::TraceError(
        L"%s: DsrGetJoinInfoEx failed with error code: 0x%08x. Level = 1, Tenant ID = %s.",
        L"NgcRegController::NgcRemoveRegistration",
        (unsigned int)JoinInfo,
        v17);
    }
  }
  CurrentUserSid = GetCurrentUserSid((LPWSTR *)&hMem);
  if ( CurrentUserSid >= 0 )
  {
    v28 = (const unsigned __int16 *)hMem;
  }
  else
  {
    Logger::TraceError(
      L"%s: GetCurrentUserSid failed with error code: 0x%08x.",
      L"NgcRegController::NgcRemoveRegistration",
      (unsigned int)CurrentUserSid);
    LocalFree(hMem);
    v28 = 0;
    hMem = 0;
  }
  if ( (unsigned int)IsEmptyString(v28) )
  {
    Logger::TraceError(
      L"%s: User SID is empty. Cannot reset password-less NGC set state.",
      L"NgcRegController::NgcRemoveRegistration");
  }
  else
  {
    v30 = ResetPasswordLessNgcSetState(v29);
    if ( v30 >= 0 )
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Password-less state successfully reset for UserSid: %s",
        L"NgcRegController::NgcRemoveRegistration",
        hMem);
    else
      Logger::TraceError(
        L"%s: ResetPasswordLessNgcSetState for UserSid %s failed with error code: 0x%08x.",
        L"NgcRegController::NgcRemoveRegistration",
        hMem,
        (unsigned int)v30);
  }
  v31 = KeyManager::Initialize(v46, v5, v6, v7, (const unsigned __int16 *)hMem, 0);
  if ( v31 < 0 )
  {
    v32 = L"KeyManager::Initialize";
LABEL_48:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"NgcRegController::NgcRemoveRegistration",
      v32,
      (unsigned int)v31);
    goto LABEL_72;
  }
  if ( (unsigned int)IsEmptyString((const unsigned __int16 *)hMem) )
  {
    Logger::TraceError(
      L"%s: User SID is empty. Cannot delete NGC container or keys.",
      L"NgcRegController::NgcRemoveRegistration");
    goto LABEL_72;
  }
  if ( !a4 )
  {
    v44 = 1;
LABEL_80:
    v31 = KeyManager::DeleteContainer((const unsigned __int16 **)v46, v44, 0, 0);
    if ( v31 < 0 )
    {
      v32 = L"KeyManager::DeleteContainer";
      goto LABEL_48;
    }
    goto LABEL_62;
  }
  if ( a4 == 4 )
    goto LABEL_63;
  if ( (unsigned int)IsEmptyString(v7) )
  {
    Logger::TraceError(
      L"%s: User email is empty. Cannot delete user NGC key.",
      L"NgcRegController::NgcRemoveRegistration");
    goto LABEL_72;
  }
  if ( (unsigned int)IsEmptyString(v6) || (unsigned int)IsEmptyString(v5) )
  {
    Logger::TraceError(
      L"%s: Tenant ID is empty. Cannot delete user NGC key.",
      L"NgcRegController::NgcRemoveRegistration");
    goto LABEL_72;
  }
  v35 = a4 - 1;
  if ( !v35 )
  {
    v44 = 0;
    goto LABEL_80;
  }
  v36 = v35 - 1;
  if ( !v36 )
  {
    v31 = KeyManager::DeleteUserKey((KeyManager *)v46, 0);
    if ( v31 < 0 )
    {
      v32 = L"KeyManager::DeleteUserKey";
      goto LABEL_48;
    }
    goto LABEL_62;
  }
  if ( v36 == 1 )
  {
    v37 = KeyManager::DeleteUserKey((KeyManager *)v46, 0);
    if ( v37 < 0 )
      Logger::TraceError(
        L"%s: KeyManager::DeleteUserKey failed with error code: 0x%08x. Ignoring this error as requested.",
        L"NgcRegController::NgcRemoveRegistration",
        (unsigned int)v37);
LABEL_62:
    v34 = (const wchar_t *)hMem;
  }
LABEL_63:
  v38 = L"<NULL>";
  if ( v34 )
    v38 = v34;
  v39 = L"<NULL>";
  if ( v7 )
    v39 = v7;
  v40 = L"<NULL>";
  if ( v6 )
    v40 = v6;
  if ( v5 )
    v8 = v5;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: NGC container and keys are successfully deleted. IDP domain: %s, Tenant ID: %s, User email: %s, UserSid: %s.",
    L"NgcRegController::NgcRemoveRegistration",
    v8,
    v40,
    v39,
    v38);
LABEL_72:
  v41 = NgcStatusStorage::Delete(v33);
  v42 = v41;
  if ( v41 < 0 )
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"NgcRegController::NgcRemoveRegistration",
      L"NgcStatusStorage::Delete",
      (unsigned int)v41);
  LocalFree(hMem);
  DsrFreeJoinInfoEx(Block);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcRegController::NgcRemoveRegistration", v42);
  NgcStatusStorage::Cleanup((NgcStatusStorage *)v45);
  KeyManager::Cleanup((KeyManager *)v46);
  return v42;
}

```

## disassembly

```asm
0x180080100  mov     [rsp-8+arg_18], rbx
0x180080105  push    rbp
0x180080106  push    rsi
0x180080107  push    rdi
0x180080108  push    r12
0x18008010a  push    r13
0x18008010c  push    r14
0x18008010e  push    r15
0x180080110  lea     rbp, [rsp-1Fh]
0x180080115  sub     rsp, 0D0h
0x18008011c  mov     ebx, r9d
0x18008011f  mov     rsi, r8
0x180080122  mov     rdi, rdx
0x180080125  mov     r14, rcx
0x180080128  lea     r15, aNull_2; "<NULL>"
0x18008012f  mov     rax, r15
0x180080132  xor     r12d, r12d
0x180080135  test    r8, r8
0x180080138  cmovnz  rax, r8
0x18008013c  mov     r9, r15
0x18008013f  test    rdx, rdx
0x180080142  cmovnz  r9, rdx
0x180080146  mov     r8, r15
0x180080149  test    rcx, rcx
0x18008014c  cmovnz  r8, rcx
0x180080150  mov     [rsp+100h+var_D0], r12d
0x180080155  mov     dword ptr [rsp+100h+var_D8], ebx
0x180080159  mov     [rsp+100h+var_E0], rax
0x18008015e  lea     r13, aNgcregcontroll_15; "NgcRegController::NgcRemoveRegistration"
0x180080165  mov     rdx, r13
0x180080168  lea     rcx, aSStartedUserEm; "%s started. User email: %s, Tenant ID: "...
0x18008016f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180080174  xorps   xmm0, xmm0
0x180080177  movdqa  [rbp+4Fh+var_A0], xmm0
0x18008017c  mov     [rbp+4Fh+var_90], r12
0x180080180  xorps   xmm1, xmm1
0x180080183  movdqa  xmmword ptr [rbp+4Fh+var_B0], xmm1
0x180080188  mov     [rbp+4Fh+var_88], r12
0x18008018c  mov     [rbp+4Fh+var_80], r12
0x180080190  mov     [rbp+4Fh+var_78], r12d
0x180080194  movdqa  [rbp+4Fh+var_70], xmm0
0x180080199  mov     [rbp+4Fh+var_60], r12
0x18008019d  mov     [rbp+4Fh+var_58], r12
0x1800801a1  mov     [rbp+4Fh+var_50], r12
0x1800801a5  mov     [rbp+4Fh+var_48], r12d
0x1800801a9  mov     [rbp+4Fh+var_40], r12
0x1800801ad  mov     [rbp+4Fh+var_38], r12
0x1800801b1  mov     [rbp+4Fh+var_C0], r12
0x1800801b5  mov     [rbp+4Fh+var_B8], r12
0x1800801b9  mov     [rbp+4Fh+Block], r12
0x1800801bd  mov     [rbp+4Fh+arg_8], r12
0x1800801c1  mov     [rbp+4Fh+hMem], r12
0x1800801c5  mov     rcx, r14; unsigned __int16 *
0x1800801c8  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800801cd  mov     r9d, 0FFFFFFFBh
0x1800801d3  test    eax, eax
0x1800801d5  jz      short loc_1800801DF
0x1800801d7  test    r9d, ebx
0x1800801da  mov     r8b, 1
0x1800801dd  jnz     short loc_1800801E2
0x1800801df  mov     r8b, r12b
0x1800801e2  mov     rcx, rdi; unsigned __int16 *
0x1800801e5  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800801ea  test    eax, eax
0x1800801ec  jz      short loc_1800801F5
0x1800801ee  test    r9d, ebx
0x1800801f1  mov     dl, 1
0x1800801f3  jnz     short loc_1800801F8
0x1800801f5  mov     dl, r12b
0x1800801f8  mov     rcx, rsi; unsigned __int16 *
0x1800801fb  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080200  test    eax, eax
0x180080202  jz      short loc_18008020B
0x180080204  test    r9d, ebx
0x180080207  mov     al, 1
0x180080209  jnz     short loc_18008020E
0x18008020b  mov     al, r12b
0x18008020e  test    r8b, r8b
0x180080211  jnz     short loc_18008021F
0x180080213  test    dl, dl
0x180080215  jnz     short loc_18008021F
0x180080217  test    al, al
0x180080219  jz      loc_180080349
0x18008021f  mov     rcx, rdi; unsigned __int16 *
0x180080222  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080227  test    eax, eax
0x180080229  jnz     short loc_18008022F
0x18008022b  mov     [rbp+4Fh+arg_8], rdi
0x18008022f  lea     r8, [rbp+4Fh+Block]
0x180080233  lea     rdx, [rbp+4Fh+arg_8]
0x180080237  mov     ecx, 1
0x18008023c  call    DsrGetJoinInfoEx
0x180080241  test    eax, eax
0x180080243  jns     short loc_18008026E
0x180080245  lea     r9, cchOriginalDestLength
0x18008024c  mov     rcx, [rbp+4Fh+arg_8]
0x180080250  test    rcx, rcx
0x180080253  cmovnz  r9, rcx
0x180080257  mov     r8d, eax
0x18008025a  mov     rdx, r13
0x18008025d  lea     rcx, aSDsrgetjoininf_5; "%s: DsrGetJoinInfoEx failed with error "...
0x180080264  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080269  jmp     loc_180080349
0x18008026e  mov     rdx, [rbp+4Fh+Block]
0x180080272  test    rdx, rdx
0x180080275  jnz     short loc_18008029D
0x180080277  lea     r8, cchOriginalDestLength
0x18008027e  mov     rax, [rbp+4Fh+arg_8]
0x180080282  test    rax, rax
0x180080285  cmovnz  r8, rax
0x180080289  mov     rdx, r13
0x18008028c  lea     rcx, aSDeviceIsNotJo; "%s: Device is not joined. DsrGetJoinInf"...
0x180080293  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180080298  jmp     loc_180080349
0x18008029d  mov     rcx, r14; unsigned __int16 *
0x1800802a0  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800802a5  test    eax, eax
0x1800802a7  jz      short loc_1800802EB
0x1800802a9  mov     rax, [rdx+0B0h]
0x1800802b0  test    rax, rax
0x1800802b3  jz      short loc_1800802C6
0x1800802b5  mov     rcx, [rax]; unsigned __int16 *
0x1800802b8  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800802bd  test    eax, eax
0x1800802bf  jnz     short loc_1800802C6
0x1800802c1  mov     r14, rcx
0x1800802c4  jmp     short loc_1800802EB
0x1800802c6  lea     r8, cchOriginalDestLength
0x1800802cd  mov     rax, [rbp+4Fh+arg_8]
0x1800802d1  test    rax, rax
0x1800802d4  cmovnz  r8, rax
0x1800802d8  mov     rdx, r13
0x1800802db  lea     rcx, aSDsrgetjoininf_1; "%s: DsrGetJoinInfoEx returns empty NGC "...
0x1800802e2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800802e7  mov     rdx, [rbp+4Fh+Block]
0x1800802eb  mov     rcx, rdi; unsigned __int16 *
0x1800802ee  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800802f3  test    eax, eax
0x1800802f5  jz      short loc_18008031C
0x1800802f7  mov     rcx, [rdx+20h]; unsigned __int16 *
0x1800802fb  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080300  test    eax, eax
0x180080302  jz      short loc_180080319
0x180080304  mov     rdx, r13
0x180080307  lea     rcx, aSDsrgetjoininf_4; "%s: DsrGetJoinInfoEx returns empty tena"...
0x18008030e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180080313  mov     rdx, [rbp+4Fh+Block]
0x180080317  jmp     short loc_18008031C
0x180080319  mov     rdi, rcx
0x18008031c  mov     rcx, rsi; unsigned __int16 *
0x18008031f  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080324  test    eax, eax
0x180080326  jz      short loc_180080349
0x180080328  mov     rcx, [rdx+18h]; unsigned __int16 *
0x18008032c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080331  test    eax, eax
0x180080333  jz      short loc_180080346
0x180080335  mov     rdx, r13
0x180080338  lea     rcx, aSDsrgetjoininf_2; "%s: DsrGetJoinInfoEx returns empty IDP "...
0x18008033f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180080344  jmp     short loc_180080349
0x180080346  mov     rsi, rcx
0x180080349  lea     rcx, [rbp+4Fh+hMem]; StringSid
0x18008034d  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x180080352  test    eax, eax
0x180080354  jns     short loc_18008037B
0x180080356  mov     r8d, eax
0x180080359  mov     rdx, r13
0x18008035c  lea     rcx, aSGetcurrentuse_0; "%s: GetCurrentUserSid failed with error"...
0x180080363  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080368  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18008036c  call    cs:__imp_LocalFree
0x180080372  mov     rcx, r12
0x180080375  mov     [rbp+4Fh+hMem], rcx
0x180080379  jmp     short loc_18008037F
0x18008037b  mov     rcx, [rbp+4Fh+hMem]; unsigned __int16 *
0x18008037f  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080384  test    eax, eax
0x180080386  jz      short loc_180080399
0x180080388  mov     rdx, r13
0x18008038b  lea     rcx, aSUserSidIsEmpt; "%s: User SID is empty. Cannot reset pas"...
0x180080392  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080397  jmp     short loc_1800803C6
0x180080399  call    ?ResetPasswordLessNgcSetState@@YAJPEBG@Z; ResetPasswordLessNgcSetState(ushort const *)
0x18008039e  mov     r8, [rbp+4Fh+hMem]
0x1800803a2  mov     rdx, r13
0x1800803a5  test    eax, eax
0x1800803a7  jns     short loc_1800803BA
0x1800803a9  mov     r9d, eax
0x1800803ac  lea     rcx, aSResetpassword; "%s: ResetPasswordLessNgcSetState for Us"...
0x1800803b3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800803b8  jmp     short loc_1800803C6
0x1800803ba  lea     rcx, aSPasswordLessS; "%s: Password-less state successfully re"...
0x1800803c1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800803c6  mov     [rsp+100h+var_D8], r12; unsigned __int16 *
0x1800803cb  mov     rax, [rbp+4Fh+hMem]
0x1800803cf  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x1800803d4  mov     r9, r14; unsigned __int16 *
0x1800803d7  mov     r8, rdi; unsigned __int16 *
0x1800803da  mov     rdx, rsi; unsigned __int16 *
0x1800803dd  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800803e1  call    ?Initialize@KeyManager@@QEAAJPEBG0000@Z; KeyManager::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800803e6  test    eax, eax
0x1800803e8  jns     short loc_180080408
0x1800803ea  lea     r8, aKeymanagerInit; "KeyManager::Initialize"
0x1800803f1  mov     r9d, eax
0x1800803f4  mov     rdx, r13
0x1800803f7  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800803fe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080403  jmp     loc_1800804F3
0x180080408  mov     rdx, [rbp+4Fh+hMem]
0x18008040c  mov     rcx, rdx; unsigned __int16 *
0x18008040f  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080414  test    eax, eax
0x180080416  jz      short loc_18008042C
0x180080418  lea     rcx, aSUserSidIsEmpt_0; "%s: User SID is empty. Cannot delete NG"...
0x18008041f  mov     rdx, r13
0x180080422  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080427  jmp     loc_1800804F3
0x18008042c  test    ebx, ebx
0x18008042e  jz      loc_1800805A2
0x180080434  cmp     ebx, 4
0x180080437  jz      short loc_1800804B2
0x180080439  mov     rcx, r14; unsigned __int16 *
0x18008043c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080441  test    eax, eax
0x180080443  jz      short loc_18008044E
0x180080445  lea     rcx, aSUserEmailIsEm; "%s: User email is empty. Cannot delete "...
0x18008044c  jmp     short loc_18008041F
0x18008044e  mov     rcx, rdi; unsigned __int16 *
0x180080451  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080456  test    eax, eax
0x180080458  jnz     loc_180080596
0x18008045e  mov     rcx, rsi; unsigned __int16 *
0x180080461  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180080466  test    eax, eax
0x180080468  jnz     loc_180080596
0x18008046e  test    ebx, ebx
0x180080470  jz      loc_1800805A2
0x180080476  sub     ebx, 1
0x180080479  jz      loc_18008058C
0x18008047f  sub     ebx, 1
0x180080482  jz      loc_18008056D
0x180080488  cmp     ebx, 1
0x18008048b  jnz     short loc_1800804B2
0x18008048d  xor     edx, edx; unsigned __int16 *
0x18008048f  lea     rcx, [rbp+4Fh+var_B0]; this
0x180080493  call    ?DeleteUserKey@KeyManager@@AEAAJPEBG@Z; KeyManager::DeleteUserKey(ushort const *)
0x180080498  test    eax, eax
0x18008049a  jns     short loc_1800804AE
0x18008049c  mov     r8d, eax
0x18008049f  mov     rdx, r13
0x1800804a2  lea     rcx, aSKeymanagerDel_0; "%s: KeyManager::DeleteUserKey failed wi"...
0x1800804a9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800804ae  mov     rdx, [rbp+4Fh+hMem]
0x1800804b2  mov     rcx, r15
0x1800804b5  test    rdx, rdx
0x1800804b8  cmovnz  rcx, rdx
0x1800804bc  mov     rax, r15
0x1800804bf  test    r14, r14
0x1800804c2  cmovnz  rax, r14
0x1800804c6  mov     r9, r15
0x1800804c9  test    rdi, rdi
0x1800804cc  cmovnz  r9, rdi
0x1800804d0  test    rsi, rsi
0x1800804d3  cmovnz  r15, rsi
0x1800804d7  mov     [rsp+100h+var_D8], rcx
0x1800804dc  mov     [rsp+100h+var_E0], rax
0x1800804e1  mov     r8, r15
0x1800804e4  mov     rdx, r13
0x1800804e7  lea     rcx, aSNgcContainerA; "%s: NGC container and keys are successf"...
0x1800804ee  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800804f3  call    ?Delete@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Delete(void)
0x1800804f8  mov     ebx, eax
0x1800804fa  test    eax, eax
0x1800804fc  jns     short loc_180080517
0x1800804fe  mov     r9d, eax
0x180080501  lea     r8, aNgcstatusstora_4; "NgcStatusStorage::Delete"
0x180080508  mov     rdx, r13
0x18008050b  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180080512  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080517  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18008051b  call    cs:__imp_LocalFree
0x180080521  mov     rcx, [rbp+4Fh+Block]; Block
0x180080525  call    DsrFreeJoinInfoEx
0x18008052a  mov     r8d, ebx
0x18008052d  mov     rdx, r13
0x180080530  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180080537  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008053c  nop
0x18008053d  lea     rcx, [rbp+4Fh+var_C0]; this
0x180080541  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180080546  nop
0x180080547  lea     rcx, [rbp+4Fh+var_B0]; this
0x18008054b  call    ?Cleanup@KeyManager@@AEAAXXZ; KeyManager::Cleanup(void)
0x180080550  mov     eax, ebx
0x180080552  mov     rbx, [rsp+100h+arg_18]
0x18008055a  add     rsp, 0D0h
0x180080561  pop     r15
0x180080563  pop     r14
  ... truncated ...
```
