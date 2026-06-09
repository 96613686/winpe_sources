# CCreateLocalUserTask::RunTask(void)

- ea: `0x180032270`
- end: `0x1800325d6`
- name: `?RunTask@CCreateLocalUserTask@@UEAAJXZ`
- size: `870`
- prototype: `__int64 __fastcall(CCreateLocalUserTask *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800325e0`

## callees

- `0x18000abe4`
- `0x18000b1fc`
- `0x18000b2b0`
- `0x180019a38`
- `0x180026b68`
- `0x180032270`
- `0x180032884`
- `0x180032afc`
- `0x180032c50`
- `0x1800b8834`
- `0x1800bd9b8`
- `0x1800c4010`

## import_xrefs

- `SHELL32!__imp_SHSetUserPicturePath` at `0x1800324a7`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x1800324a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800322a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800322a6`

## string_xrefs

- `0x18003240f`: `Failed to commit new user settings. [hr=0x%08X]`
- `0x180032549`: `Reverting the account created [hr=0x%08X]`
- `0x180032570`: `Failed to create new user account for user %s. [hr=0x%08X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCreateLocalUserTask::RunTask(CCreateLocalUserTask *this)
{
  __int64 v2; // rcx
  HRESULT UInt32; // ebx
  int v4; // eax
  const WCHAR *v5; // rax
  CCreateLocalUserTask *v6; // rcx
  int v7; // eax
  int v8; // eax
  CCreateLocalUserTask *v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // eax
  int v14; // eax
  LPCWSTR StringSid[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h]
  unsigned int v18; // [rsp+88h] [rbp+38h] BYREF
  struct IPropertyStore *v19; // [rsp+90h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+48h] BYREF

  ppv = 0;
  UInt32 = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv);
  if ( UInt32 < 0 )
    goto LABEL_38;
  v19 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, char *, struct IPropertyStore **))(*(_QWORD *)ppv + 56LL))(
         ppv,
         (char *)this + 552,
         &v19);
  UInt32 = v4;
  if ( v4 < 0 )
  {
    UnattendLogW(1, L"Failed to create new user account for user %s. [hr=0x%08X]", (char *)this + 552, (unsigned int)v4);
    goto LABEL_35;
  }
  if ( *((_QWORD *)this + 134)
    && ((UInt32 = IPropertyStore_SetSecureString(v19), UInt32 < 0)
     || (v5 = (const WCHAR *)*((_QWORD *)this + 135)) != 0
     && !*((_DWORD *)this + 277)
     && (v17 = 0,
         StringSid[0] = (LPCWSTR)31,
         StringSid[1] = v5,
         UInt32 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, LPCWSTR *))v19->lpVtbl->SetValue)(
                    v19,
                    PKEY_SAM_PasswordHint,
                    StringSid),
         UInt32 < 0)
     || (UInt32 = ((__int64 (__fastcall *)(struct IPropertyStore *))v19->lpVtbl->Commit)(v19), UInt32 < 0)) )
  {
    UnattendLogW(1, L"Failed to set password and password hint with hr=0x%8X", (unsigned int)UInt32);
  }
  else
  {
    v18 = 0;
    UInt32 = IPropertyStore_GetUInt32(v19, PKEY_SAM_UserAccountControl, &v18);
    if ( UInt32 >= 0 )
    {
      v18 = v18 & 0xFFFDFDFF | 0x200;
      *(_OWORD *)StringSid = 0;
      v17 = 0;
      LOWORD(StringSid[0]) = 19;
      LODWORD(StringSid[1]) = v18;
      UInt32 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, LPCWSTR *))v19->lpVtbl->SetValue)(
                 v19,
                 PKEY_SAM_UserAccountControl,
                 StringSid);
      if ( UInt32 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(struct IPropertyStore *))v19->lpVtbl->Commit)(v19);
        UInt32 = v7;
        if ( v7 < 0 )
          UnattendLogW(2, L"Failed to commit new user settings. [hr=0x%08X]", (unsigned int)v7);
      }
    }
  }
  if ( !*((_BYTE *)this + 1105) )
  {
LABEL_22:
    if ( UInt32 < 0 )
      goto LABEL_32;
    goto LABEL_23;
  }
  if ( UInt32 < 0 )
    goto LABEL_32;
  v8 = CCreateLocalUserTask::_AddUserToAdministratorsGroup(v6, v19);
  UInt32 = v8;
  if ( v8 < 0 )
  {
    UnattendLogW(2, L"Failed to add user to Administrator's group. Trying again. [hr=0x%08X]", (unsigned int)v8);
    v10 = CCreateLocalUserTask::_AddUserToAdministratorsGroup(v9, v19);
    UInt32 = v10;
    if ( v10 < 0 )
    {
      UnattendLogW(1, L"Failed to add user to Administrator's group second time. [hr=0x%08X]", (unsigned int)v10);
      goto LABEL_32;
    }
  }
  if ( *((_BYTE *)this + 1106) )
  {
    UInt32 = RemoveUserFromUsersGroup(v19);
    goto LABEL_22;
  }
LABEL_23:
  if ( *((_QWORD *)this + 136) && (v11 = SHSetUserPicturePath((char *)this + 552, 0), UInt32 = v11, v11 < 0) )
  {
    UnattendLogW(1, L"Failed to set user tile [hr=0x%08X]", (unsigned int)v11);
  }
  else
  {
    if ( !*((_QWORD *)this + 135) )
      goto LABEL_33;
    if ( *((_DWORD *)this + 277) == 1 )
    {
      StringSid[0] = 0;
      StringSid[1] = 0;
      v17 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(StringSid);
      StringSid[1] = (LPCWSTR)-1LL;
      v17 = -1;
      UInt32 = IPropertyStore_GetSecurityIDString(v19, v12, StringSid);
      if ( UInt32 >= 0 )
        UInt32 = WriteSecurityQuestionData(StringSid[0], *((PCWSTR *)this + 135));
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(StringSid);
    }
    if ( UInt32 >= 0 )
      goto LABEL_33;
  }
LABEL_32:
  v13 = (*(__int64 (__fastcall **)(LPVOID, struct IPropertyStore *))(*(_QWORD *)ppv + 64LL))(ppv, v19);
  UnattendLogW(1, L"Reverting the account created [hr=0x%08X]", v13);
LABEL_33:
  ((void (__fastcall *)(struct IPropertyStore *))v19->lpVtbl->Release)(v19);
LABEL_35:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( UInt32 >= 0 )
  {
    v14 = CCreateLocalUserTask::_SetAutologonIfNecessary(this);
    if ( v14 < 0 )
      UnattendLogW(1, L"Failed to set autologon with hr=0x%08X", (unsigned int)v14);
  }
LABEL_38:
  if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v2, CreateUserAccount_Info, (unsigned int)UInt32);
  return (unsigned int)UInt32;
}

```

## disassembly

```asm
0x180032270  push    rbp
0x180032272  push    rbx
0x180032273  push    rsi
0x180032274  push    rdi
0x180032275  push    r15
0x180032277  mov     rbp, rsp
0x18003227a  sub     rsp, 50h
0x18003227e  mov     rdi, rcx
0x180032281  mov     [rbp+arg_18], 0
0x180032289  lea     rax, [rbp+arg_18]
0x18003228d  mov     [rsp+50h+ppv], rax; ppv
0x180032292  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180032299  xor     edx, edx; pUnkOuter
0x18003229b  lea     r8d, [rdx+3]; dwClsContext
0x18003229f  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x1800322a6  call    cs:__imp_CoCreateInstance
0x1800322ac  mov     ebx, eax
0x1800322ae  mov     r15d, 1
0x1800322b4  test    eax, eax
0x1800322b6  js      loc_1800325B1
0x1800322bc  mov     [rbp+arg_10], 0
0x1800322c4  lea     rsi, [rdi+228h]
0x1800322cb  mov     rcx, [rbp+arg_18]
0x1800322cf  mov     rax, [rcx]
0x1800322d2  lea     r8, [rbp+arg_10]
0x1800322d6  mov     rdx, rsi
0x1800322d9  mov     rax, [rax+38h]
0x1800322dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322e2  mov     ebx, eax
0x1800322e4  test    eax, eax
0x1800322e6  js      loc_18003256A
0x1800322ec  mov     r8, [rdi+430h]
0x1800322f3  test    r8, r8
0x1800322f6  jz      loc_18003238A
0x1800322fc  mov     rcx, [rbp+arg_10]
0x180032300  call    IPropertyStore_SetSecureString
0x180032305  mov     ebx, eax
0x180032307  test    eax, eax
0x180032309  js      short loc_180032370
0x18003230b  mov     rax, [rdi+438h]
0x180032312  test    rax, rax
0x180032315  jz      short loc_18003235A
0x180032317  cmp     dword ptr [rdi+454h], 0
0x18003231e  jnz     short loc_18003235A
0x180032320  mov     rcx, [rbp+arg_10]
0x180032324  xorps   xmm0, xmm0
0x180032327  xor     edx, edx
0x180032329  movups  xmmword ptr [rbp+StringSid], xmm0
0x18003232d  mov     [rbp+var_10], rdx
0x180032331  lea     edx, [r15+1Eh]
0x180032335  mov     word ptr [rbp+StringSid], dx
0x180032339  mov     [rbp+StringSid+8], rax
0x18003233d  mov     rax, [rcx]
0x180032340  lea     r8, [rbp+StringSid]
0x180032344  lea     rdx, PKEY_SAM_PasswordHint
0x18003234b  mov     rax, [rax+30h]
0x18003234f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032354  mov     ebx, eax
0x180032356  test    eax, eax
0x180032358  js      short loc_180032370
0x18003235a  mov     rcx, [rbp+arg_10]
0x18003235e  mov     rax, [rcx]
0x180032361  mov     rax, [rax+38h]
0x180032365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003236a  mov     ebx, eax
0x18003236c  test    eax, eax
0x18003236e  jns     short loc_18003238A
0x180032370  mov     r8d, ebx
0x180032373  lea     rdx, aFailedToSetPas; "Failed to set password and password hin"...
0x18003237a  mov     ecx, r15d
0x18003237d  call    UnattendLogW
0x180032382  test    ebx, ebx
0x180032384  js      loc_180032420
0x18003238a  mov     [rbp+arg_8], 0
0x180032391  lea     r8, [rbp+arg_8]
0x180032395  lea     rdx, PKEY_SAM_UserAccountControl
0x18003239c  mov     rcx, [rbp+arg_10]
0x1800323a0  call    IPropertyStore_GetUInt32
0x1800323a5  mov     ebx, eax
0x1800323a7  test    eax, eax
0x1800323a9  js      short loc_180032420
0x1800323ab  mov     eax, [rbp+arg_8]
0x1800323ae  btr     eax, 11h
0x1800323b2  bts     eax, 9
0x1800323b6  mov     [rbp+arg_8], eax
0x1800323b9  mov     rcx, [rbp+arg_10]
0x1800323bd  xorps   xmm0, xmm0
0x1800323c0  xor     r8d, r8d
0x1800323c3  movups  xmmword ptr [rbp+StringSid], xmm0
0x1800323c7  mov     [rbp+var_10], r8
0x1800323cb  mov     r8d, 13h
0x1800323d1  mov     word ptr [rbp+StringSid], r8w
0x1800323d6  mov     dword ptr [rbp+StringSid+8], eax
0x1800323d9  mov     rax, [rcx]
0x1800323dc  lea     r8, [rbp+StringSid]
0x1800323e0  lea     rdx, PKEY_SAM_UserAccountControl
0x1800323e7  mov     rax, [rax+30h]
0x1800323eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323f0  mov     ebx, eax
0x1800323f2  test    eax, eax
0x1800323f4  js      short loc_180032420
0x1800323f6  mov     rcx, [rbp+arg_10]
0x1800323fa  mov     rax, [rcx]
0x1800323fd  mov     rax, [rax+38h]
0x180032401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032406  mov     ebx, eax
0x180032408  test    eax, eax
0x18003240a  jns     short loc_180032420
0x18003240c  mov     r8d, eax
0x18003240f  lea     rdx, aFailedToCommit_3; "Failed to commit new user settings. [hr"...
0x180032416  mov     ecx, 2
0x18003241b  call    UnattendLogW
0x180032420  cmp     byte ptr [rdi+451h], 0
0x180032427  jz      short loc_18003248E
0x180032429  test    ebx, ebx
0x18003242b  js      loc_180032532
0x180032431  mov     rdx, [rbp+arg_10]; struct IPropertyStore *
0x180032435  call    ?_AddUserToAdministratorsGroup@CCreateLocalUserTask@@AEAAJPEAUIPropertyStore@@@Z; CCreateLocalUserTask::_AddUserToAdministratorsGroup(IPropertyStore *)
0x18003243a  mov     ebx, eax
0x18003243c  test    eax, eax
0x18003243e  jns     short loc_18003247A
0x180032440  mov     r8d, eax
0x180032443  lea     rdx, aFailedToAddUse; "Failed to add user to Administrator's g"...
0x18003244a  mov     ecx, 2
0x18003244f  call    UnattendLogW
0x180032454  mov     rdx, [rbp+arg_10]; struct IPropertyStore *
0x180032458  call    ?_AddUserToAdministratorsGroup@CCreateLocalUserTask@@AEAAJPEAUIPropertyStore@@@Z; CCreateLocalUserTask::_AddUserToAdministratorsGroup(IPropertyStore *)
0x18003245d  mov     ebx, eax
0x18003245f  test    eax, eax
0x180032461  jns     short loc_18003247A
0x180032463  lea     rdx, aFailedToAddUse_0; "Failed to add user to Administrator's g"...
0x18003246a  mov     r8d, eax
0x18003246d  mov     ecx, r15d
0x180032470  call    UnattendLogW
0x180032475  jmp     loc_180032532
0x18003247a  cmp     byte ptr [rdi+452h], 0
0x180032481  jz      short loc_180032496
0x180032483  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180032487  call    ?RemoveUserFromUsersGroup@@YAJPEAUIPropertyStore@@@Z; RemoveUserFromUsersGroup(IPropertyStore *)
0x18003248c  mov     ebx, eax
0x18003248e  test    ebx, ebx
0x180032490  js      loc_180032532
0x180032496  mov     r8, [rdi+440h]
0x18003249d  test    r8, r8
0x1800324a0  jz      short loc_1800324BC
0x1800324a2  xor     edx, edx
0x1800324a4  mov     rcx, rsi
0x1800324a7  call    cs:__imp_SHSetUserPicturePath
0x1800324ad  mov     ebx, eax
0x1800324af  test    eax, eax
0x1800324b1  jns     short loc_1800324BC
0x1800324b3  lea     rdx, aFailedToSetUse; "Failed to set user tile [hr=0x%08X]"
0x1800324ba  jmp     short loc_18003246A
0x1800324bc  cmp     qword ptr [rdi+438h], 0
0x1800324c4  jz      loc_180032558
0x1800324ca  cmp     [rdi+454h], r15d
0x1800324d1  jnz     short loc_18003252E
0x1800324d3  mov     [rbp+StringSid], 0
0x1800324db  mov     [rbp+StringSid+8], 0
0x1800324e3  mov     [rbp+var_10], 0
0x1800324eb  lea     rcx, [rbp+StringSid]
0x1800324ef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800324f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800324f8  mov     [rbp+StringSid+8], rax
0x1800324fc  mov     [rbp+var_10], rax
0x180032500  lea     r8, [rbp+StringSid]
0x180032504  mov     rcx, [rbp+arg_10]
0x180032508  call    IPropertyStore_GetSecurityIDString
0x18003250d  mov     ebx, eax
0x18003250f  test    eax, eax
0x180032511  js      short loc_180032525
0x180032513  mov     rdx, [rdi+438h]; SourceString
0x18003251a  mov     rcx, [rbp+StringSid]; StringSid
0x18003251e  call    ?WriteSecurityQuestionData@@YAJPEBG0@Z; WriteSecurityQuestionData(ushort const *,ushort const *)
0x180032523  mov     ebx, eax
0x180032525  lea     rcx, [rbp+StringSid]
0x180032529  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003252e  test    ebx, ebx
0x180032530  jns     short loc_180032558
0x180032532  mov     rcx, [rbp+arg_18]
0x180032536  mov     rax, [rcx]
0x180032539  mov     rdx, [rbp+arg_10]
0x18003253d  mov     rax, [rax+40h]
0x180032541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032546  mov     r8d, eax
0x180032549  lea     rdx, aRevertingTheAc; "Reverting the account created [hr=0x%08"...
0x180032550  mov     ecx, r15d
0x180032553  call    UnattendLogW
0x180032558  mov     rcx, [rbp+arg_10]
0x18003255c  mov     rax, [rcx]
0x18003255f  mov     rax, [rax+10h]
0x180032563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032568  jmp     short loc_18003257F
0x18003256a  mov     r9d, eax
0x18003256d  mov     r8, rsi
0x180032570  lea     rdx, aFailedToCreate_9; "Failed to create new user account for u"...
0x180032577  mov     ecx, r15d
0x18003257a  call    UnattendLogW
0x18003257f  mov     rcx, [rbp+arg_18]
0x180032583  mov     rax, [rcx]
0x180032586  mov     rax, [rax+10h]
0x18003258a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003258f  test    ebx, ebx
0x180032591  js      short loc_1800325B1
0x180032593  mov     rcx, rdi; this
0x180032596  call    ?_SetAutologonIfNecessary@CCreateLocalUserTask@@AEAAJXZ; CCreateLocalUserTask::_SetAutologonIfNecessary(void)
0x18003259b  test    eax, eax
0x18003259d  jns     short loc_1800325B1
0x18003259f  mov     r8d, eax
0x1800325a2  lea     rdx, aFailedToSetAut; "Failed to set autologon with hr=0x%08X"
0x1800325a9  mov     ecx, r15d
0x1800325ac  call    UnattendLogW
0x1800325b1  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, r15b
0x1800325b8  jz      short loc_1800325C9
0x1800325ba  mov     r8d, ebx
0x1800325bd  lea     rdx, CreateUserAccount_Info
0x1800325c4  call    McTemplateU0q_EventWriteTransfer
0x1800325c9  mov     eax, ebx
0x1800325cb  add     rsp, 50h
0x1800325cf  pop     r15
0x1800325d1  pop     rdi
0x1800325d2  pop     rsi
0x1800325d3  pop     rbx
0x1800325d4  pop     rbp
0x1800325d5  retn
```
