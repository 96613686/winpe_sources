# CreateProfileP(ushort const *,void *,ushort const *,ushort *,ulong)

- ea: `0x18002ed00`
- end: `0x18002f21e`
- name: `?CreateProfileP@@YAJPEBGPEAX0PEAGK@Z`
- size: `1310`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002af20`

## callees

- `0x1800085cc`
- `0x180008ccc`
- `0x180008ef4`
- `0x18000f1b0`
- `0x180010f30`
- `0x1800111a0`
- `0x180011200`
- `0x1800128b0`
- `0x18001fb70`
- `0x180021980`
- `0x18002b938`
- `0x18002d2d8`
- `0x18002ed00`
- `0x180038de4`
- `0x18003962c`
- `0x18003f42c`
- `0x18003f6f4`
- `0x18003fd6c`
- `0x180040484`
- `0x18004066c`
- `0x18004cdc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002ee9d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002ee9d`

## string_xrefs

- `0x18002ed48`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18002edbb`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18002edeb`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18002ee29`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateProfileP(
        const unsigned __int16 *a1,
        void *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v8; // edi
  __int64 result; // rax
  int LocalProfileName; // eax
  HANDLE v11; // rdi
  int DirectoryForUser; // esi
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  HKEY v16; // rcx
  HKEY v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  int v25; // eax
  int ProfileListKeyNameFromSid; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  wil::details::in1diag3 *v31; // rcx
  int v32; // eax
  int v33; // [rsp+20h] [rbp-B1h]
  void *v34; // [rsp+30h] [rbp-A1h] BYREF
  void *v35; // [rsp+38h] [rbp-99h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+40h] [rbp-91h] BYREF
  unsigned __int16 *p_lpString1; // [rsp+58h] [rbp-79h] BYREF
  __int64 v38; // [rsp+60h] [rbp-71h]
  __int64 v39; // [rsp+68h] [rbp-69h]
  HANDLE hEvent; // [rsp+70h] [rbp-61h] BYREF
  __int64 v41; // [rsp+78h] [rbp-59h]
  __int64 v42; // [rsp+80h] [rbp-51h]
  unsigned __int16 *v43; // [rsp+88h] [rbp-49h] BYREF
  __int64 v44; // [rsp+90h] [rbp-41h]
  __int64 v45; // [rsp+98h] [rbp-39h]
  _QWORD v46[6]; // [rsp+A0h] [rbp-31h] BYREF
  char v47; // [rsp+D0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]
  LPCWCH lpString1; // [rsp+130h] [rbp+5Fh] BYREF

  lpString1 = a1;
  v8 = _CheckIfProfileListKeyExists(a1);
  result = 2147942583LL;
  if ( v8 != -2147024713 )
  {
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)v8,
        v33);
      return v8;
    }
    v43 = 0;
    v44 = 0;
    v45 = 0;
    hEvent = 0;
    v41 = 0;
    v42 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&hEvent);
    v41 = -1;
    v42 = -1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v43);
    v44 = -1;
    v45 = -1;
    LocalProfileName = GetLocalProfileName(0, a3, &v43, (unsigned __int16 **)&hEvent);
    v8 = LocalProfileName;
    if ( LocalProfileName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)LocalProfileName,
        v33);
LABEL_51:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&hEvent);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v43);
      return v8;
    }
    v11 = hEvent;
    DirectoryForUser = CreateDirectoryForUser((const unsigned __int16 *)hEvent, lpString1);
    if ( DirectoryForUser < 0 )
    {
      v13 = 101;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)DirectoryForUser,
        v33);
LABEL_9:
      v8 = DirectoryForUser;
      goto LABEL_51;
    }
    DirectoryForUser = _CopyFromDefaultProfile(v11);
    if ( DirectoryForUser < 0 )
    {
      v13 = 102;
      goto LABEL_8;
    }
    v14 = ChangeProfileDirectoryOwner((const unsigned __int16 *)v11, a2);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x68,
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)v14);
    memset(lpFileName, 0, sizeof(lpFileName));
    DirectoryForUser = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                         lpFileName,
                         L"%s\\%s",
                         v11,
                         L"ntuser.dat");
    if ( DirectoryForUser < 0 )
    {
      v15 = 107;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)DirectoryForUser,
        v33);
LABEL_17:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
      goto LABEL_9;
    }
    if ( GetFileAttributesW(lpFileName[0]) == -1 )
    {
      v8 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)0x8007139FLL,
        v33);
LABEL_20:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
      goto LABEL_51;
    }
    v34 = 0;
    DirectoryForUser = MountRegHive(v16, lpString1, lpFileName[0], 0, 0, &v34);
    if ( DirectoryForUser < 0 )
    {
      v15 = 121;
      goto LABEL_16;
    }
    v46[4] = &lpString1;
    v46[5] = &v34;
    v47 = 1;
    VerifyCriticalKeysInUserHive(lpString1);
    DirectoryForUser = SetDefaultUserHiveSecurity(lpString1, v17);
    if ( DirectoryForUser >= 0 )
    {
      DirectoryForUser = _SaveProfileListKeyInfo(lpString1, (BYTE *)a2, v43);
      if ( DirectoryForUser >= 0 )
      {
        v35 = 0;
        DirectoryForUser = LoadChangeUserClasses(lpString1, 0, 1, 0, &v35, 0);
        if ( DirectoryForUser >= 0 )
        {
          p_lpString1 = (unsigned __int16 *)&lpString1;
          v38 = (__int64)&v35;
          LOBYTE(v39) = 1;
          v46[2] = 0;
          v46[3] = 0;
          v46[0] = lpString1;
          v46[1] = v11;
          v21 = SendNotification(1, v46, 0xFFFFFFFFLL, 0);
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x98,
              (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
              (const char *)(unsigned int)v21);
          v22 = StringCchCopyW(a4, a5, (const unsigned __int16 *)v11);
          v8 = v22;
          if ( v22 >= 0 )
          {
            p_lpString1 = 0;
            v38 = 0;
            v39 = 0;
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&p_lpString1);
            v38 = -1;
            v39 = -1;
            ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, &p_lpString1, 0);
            v8 = ProfileListKeyNameFromSid;
            if ( ProfileListKeyNameFromSid >= 0 )
            {
              v28 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, p_lpString1, L"FullProfile", 1u);
              v8 = v28;
              if ( v28 >= 0 )
              {
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&p_lpString1);
                v30 = UnloadUserClasses(lpString1, &v35);
                v31 = retaddr;
                if ( v30 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x8F,
                    (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                    (const char *)(unsigned int)v30);
                v32 = UnmountRegHive(v31, lpString1, 0, &v34);
                if ( v32 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x7C,
                    (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                    (const char *)(unsigned int)v32);
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpFileName);
                v8 = 0;
                goto LABEL_51;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA0,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                (const char *)(unsigned int)v28,
                v33);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&p_lpString1);
              v29 = UnloadUserClasses(lpString1, &v35);
              v24 = retaddr;
              if ( v29 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8F,
                  (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                  (const char *)(unsigned int)v29);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9F,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                (const char *)(unsigned int)ProfileListKeyNameFromSid,
                v33);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&p_lpString1);
              v27 = UnloadUserClasses(lpString1, &v35);
              v24 = retaddr;
              if ( v27 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8F,
                  (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                  (const char *)(unsigned int)v27);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9B,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
              (const char *)(unsigned int)v22,
              v33);
            v23 = UnloadUserClasses(lpString1, &v35);
            v24 = retaddr;
            if ( v23 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8F,
                (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                (const char *)(unsigned int)v23);
          }
          v25 = UnmountRegHive(v24, lpString1, 0, &v34);
          if ( v25 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7C,
              (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
              (const char *)(unsigned int)v25);
          goto LABEL_20;
        }
        v18 = 139;
      }
      else
      {
        v18 = 133;
      }
    }
    else
    {
      v18 = 130;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)DirectoryForUser,
      v33);
    v20 = UnmountRegHive(v19, lpString1, 0, &v34);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7C,
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)v20);
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x18002ed00  mov     [rsp-8+lpString1], rcx
0x18002ed05  push    rbp
0x18002ed06  push    rbx
0x18002ed07  push    rsi
0x18002ed08  push    rdi
0x18002ed09  push    r12
0x18002ed0b  push    r13
0x18002ed0d  push    r14
0x18002ed0f  push    r15
0x18002ed11  lea     rbp, [rsp-17h]
0x18002ed16  sub     rsp, 0E8h
0x18002ed1d  mov     r15, r9
0x18002ed20  mov     rbx, r8
0x18002ed23  mov     r14, rdx
0x18002ed26  call    ?_CheckIfProfileListKeyExists@@YAJPEBG@Z; _CheckIfProfileListKeyExists(ushort const *)
0x18002ed2b  mov     edi, eax
0x18002ed2d  mov     eax, 800700B7h
0x18002ed32  cmp     edi, eax
0x18002ed34  jz      loc_18002F20A
0x18002ed3a  xor     r12d, r12d
0x18002ed3d  test    edi, edi
0x18002ed3f  jns     short loc_18002ED5E
0x18002ed41  mov     rcx, [rbp+57h]; this
0x18002ed45  mov     r9d, edi; char *
0x18002ed48  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ed4f  lea     edx, [r12+5Fh]; void *
0x18002ed54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ed59  jmp     loc_18002F208
0x18002ed5e  mov     [rbp+4Fh+var_98], r12
0x18002ed62  mov     [rbp+4Fh+var_90], r12
0x18002ed66  mov     [rbp+4Fh+var_88], r12
0x18002ed6a  mov     [rbp+4Fh+hEvent], r12
0x18002ed6e  mov     [rbp+4Fh+var_A8], r12
0x18002ed72  mov     [rbp+4Fh+var_A0], r12
0x18002ed76  lea     rcx, [rbp+4Fh+hEvent]
0x18002ed7a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ed7f  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002ed83  mov     [rbp+4Fh+var_A8], r13
0x18002ed87  mov     [rbp+4Fh+var_A0], r13
0x18002ed8b  lea     rcx, [rbp+4Fh+var_98]
0x18002ed8f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ed94  mov     [rbp+4Fh+var_90], r13
0x18002ed98  mov     [rbp+4Fh+var_88], r13
0x18002ed9c  lea     r9, [rbp+4Fh+hEvent]; unsigned __int16 **
0x18002eda0  lea     r8, [rbp+4Fh+var_98]; unsigned __int16 **
0x18002eda4  mov     rdx, rbx; unsigned __int16 *
0x18002eda7  xor     ecx, ecx; void *
0x18002eda9  call    ?GetLocalProfileName@@YAJPEAXPEBGPEAPEAG2@Z; GetLocalProfileName(void *,ushort const *,ushort * *,ushort * *)
0x18002edae  mov     edi, eax
0x18002edb0  test    eax, eax
0x18002edb2  jns     short loc_18002EDD0
0x18002edb4  mov     rcx, [rbp+57h]; this
0x18002edb8  mov     r9d, eax; char *
0x18002edbb  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002edc2  lea     edx, [r13+64h]; void *
0x18002edc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002edcb  jmp     loc_18002F1F5
0x18002edd0  mov     rdx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18002edd4  mov     rdi, [rbp+4Fh+hEvent]
0x18002edd8  mov     rcx, rdi; unsigned __int16 *
0x18002eddb  call    ?CreateDirectoryForUser@@YAJPEBG0H@Z; CreateDirectoryForUser(ushort const *,ushort const *,int)
0x18002ede0  mov     esi, eax
0x18002ede2  test    eax, eax
0x18002ede4  jns     short loc_18002EE05
0x18002ede6  mov     edx, 65h ; 'e'; void *
0x18002edeb  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002edf2  mov     r9d, esi; char *
0x18002edf5  mov     rcx, [rbp+57h]; this
0x18002edf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002edfe  mov     edi, esi
0x18002ee00  jmp     loc_18002F1F5
0x18002ee05  mov     rcx, rdi; hEvent
0x18002ee08  call    ?_CopyFromDefaultProfile@@YAJPEBG@Z; _CopyFromDefaultProfile(ushort const *)
0x18002ee0d  mov     esi, eax
0x18002ee0f  test    eax, eax
0x18002ee11  jns     short loc_18002EE1A
0x18002ee13  mov     edx, 66h ; 'f'
0x18002ee18  jmp     short loc_18002EDEB
0x18002ee1a  mov     rdx, r14; void *
0x18002ee1d  mov     rcx, rdi; unsigned __int16 *
0x18002ee20  call    ?ChangeProfileDirectoryOwner@@YAJPEBGPEAX@Z; ChangeProfileDirectoryOwner(ushort const *,void *)
0x18002ee25  mov     rcx, [rbp+57h]; this
0x18002ee29  lea     rbx, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ee30  test    eax, eax
0x18002ee32  jns     short loc_18002EE44
0x18002ee34  mov     r9d, eax; char *
0x18002ee37  mov     r8, rbx; unsigned int
0x18002ee3a  mov     edx, 68h ; 'h'; void *
0x18002ee3f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ee44  mov     [rsp+120h+lpFileName], r12
0x18002ee49  mov     [rsp+120h+var_D8], r12
0x18002ee4e  mov     [rsp+120h+var_D0], r12
0x18002ee53  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18002ee5a  mov     r8, rdi
0x18002ee5d  lea     rdx, aSS_0; "%s\\%s"
0x18002ee64  lea     rcx, [rsp+120h+lpFileName]
0x18002ee69  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002ee6e  mov     esi, eax
0x18002ee70  test    eax, eax
0x18002ee72  jns     short loc_18002EE98
0x18002ee74  mov     edx, 6Bh ; 'k'; void *
0x18002ee79  mov     r8, rbx; unsigned int
0x18002ee7c  mov     r9d, esi; char *
0x18002ee7f  mov     rcx, [rbp+57h]; this
0x18002ee83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee88  nop
0x18002ee89  lea     rcx, [rsp+120h+lpFileName]
0x18002ee8e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ee93  jmp     loc_18002EDFE
0x18002ee98  mov     rcx, [rsp+120h+lpFileName]; lpFileName
0x18002ee9d  call    cs:__imp_GetFileAttributesW
0x18002eea3  cmp     eax, 0FFFFFFFFh
0x18002eea6  jnz     short loc_18002EED1
0x18002eea8  mov     rcx, [rbp+57h]; this
0x18002eeac  mov     edi, 8007139Fh
0x18002eeb1  mov     r9d, edi; char *
0x18002eeb4  mov     r8, rbx; unsigned int
0x18002eeb7  mov     edx, 70h ; 'p'; void *
0x18002eebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eec1  nop
0x18002eec2  lea     rcx, [rsp+120h+lpFileName]
0x18002eec7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002eecc  jmp     loc_18002F1F5
0x18002eed1  mov     [rsp+120h+var_F0], r12
0x18002eed6  lea     rax, [rsp+120h+var_F0]
0x18002eedb  mov     [rsp+120h+var_F8], rax; void **
0x18002eee0  mov     [rsp+120h+var_100], r12; int
0x18002eee5  xor     r9d, r9d; HKEY
0x18002eee8  mov     r8, [rsp+120h+lpFileName]; unsigned __int16 *
0x18002eeed  mov     rdx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18002eef1  call    ?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z; MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)
0x18002eef6  mov     esi, eax
0x18002eef8  test    eax, eax
0x18002eefa  jns     short loc_18002EF06
0x18002eefc  mov     edx, 79h ; 'y'
0x18002ef01  jmp     loc_18002EE79
0x18002ef06  lea     rax, [rbp+4Fh+lpString1]
0x18002ef0a  mov     [rbp+4Fh+var_60], rax
0x18002ef0e  lea     rax, [rsp+120h+var_F0]
0x18002ef13  mov     [rbp+4Fh+var_58], rax
0x18002ef17  mov     [rbp+4Fh+var_50], 1
0x18002ef1b  mov     rcx, [rbp+4Fh+lpString1]; lpSubKey
0x18002ef1f  call    ?VerifyCriticalKeysInUserHive@@YAXPEBG@Z; VerifyCriticalKeysInUserHive(ushort const *)
0x18002ef24  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18002ef28  call    ?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z; SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)
0x18002ef2d  mov     esi, eax
0x18002ef2f  test    eax, eax
0x18002ef31  jns     short loc_18002EF7A
0x18002ef33  mov     edx, 82h; void *
0x18002ef38  mov     rcx, [rbp+57h]; this
0x18002ef3c  mov     r9d, esi; char *
0x18002ef3f  mov     r8, rbx; unsigned int
0x18002ef42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef47  nop
0x18002ef48  lea     r9, [rsp+120h+var_F0]
0x18002ef4d  xor     r8d, r8d
0x18002ef50  mov     rdx, [rbp+4Fh+lpString1]
0x18002ef54  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x18002ef59  mov     rcx, [rbp+57h]; this
0x18002ef5d  test    eax, eax
0x18002ef5f  jns     loc_18002EE89
0x18002ef65  mov     r9d, eax; char *
0x18002ef68  mov     r8, rbx; unsigned int
0x18002ef6b  mov     edx, 7Ch ; '|'; void *
0x18002ef70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ef75  jmp     loc_18002EE89
0x18002ef7a  mov     r8, [rbp+4Fh+var_98]; unsigned __int16 *
0x18002ef7e  mov     rdx, r14; lpData
0x18002ef81  mov     rcx, [rbp+4Fh+lpString1]; lpString1
0x18002ef85  call    ?_SaveProfileListKeyInfo@@YAJPEBGPEAX0@Z; _SaveProfileListKeyInfo(ushort const *,void *,ushort const *)
0x18002ef8a  mov     esi, eax
0x18002ef8c  test    eax, eax
0x18002ef8e  jns     short loc_18002EF97
0x18002ef90  mov     edx, 85h
0x18002ef95  jmp     short loc_18002EF38
0x18002ef97  mov     [rsp+120h+var_E8], r12
0x18002ef9c  mov     [rsp+120h+var_F8], r12; void *
0x18002efa1  lea     rax, [rsp+120h+var_E8]
0x18002efa6  mov     [rsp+120h+var_100], rax; int
0x18002efab  xor     r9d, r9d; int
0x18002efae  lea     r14d, [r9+1]
0x18002efb2  mov     r8d, r14d; int
0x18002efb5  xor     edx, edx; unsigned __int16 *
0x18002efb7  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18002efbb  call    ?LoadChangeUserClasses@@YAJPEBG0HHPEAPEAXPEAX@Z; LoadChangeUserClasses(ushort const *,ushort const *,int,int,void * *,void *)
0x18002efc0  mov     esi, eax
0x18002efc2  test    eax, eax
0x18002efc4  jns     short loc_18002EFD0
0x18002efc6  mov     edx, 8Bh
0x18002efcb  jmp     loc_18002EF38
0x18002efd0  lea     rax, [rbp+4Fh+lpString1]
0x18002efd4  mov     [rbp+4Fh+var_C8], rax
0x18002efd8  lea     rax, [rsp+120h+var_E8]
0x18002efdd  mov     [rbp+4Fh+var_C0], rax
0x18002efe1  mov     byte ptr [rbp+4Fh+var_B8], r14b
0x18002efe5  mov     [rbp+4Fh+var_70], r12
0x18002efe9  mov     [rbp+4Fh+var_68], r12
0x18002efed  mov     rax, [rbp+4Fh+lpString1]
0x18002eff1  mov     [rbp+4Fh+var_80], rax
0x18002eff5  mov     [rbp+4Fh+var_78], rdi
0x18002eff9  xor     r9d, r9d
0x18002effc  or      r8d, 0FFFFFFFFh
0x18002f000  lea     rdx, [rbp+4Fh+var_80]
0x18002f004  mov     ecx, r14d
0x18002f007  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x18002f00c  mov     rcx, [rbp+57h]; this
0x18002f010  test    eax, eax
0x18002f012  jns     short loc_18002F024
0x18002f014  mov     r9d, eax; char *
0x18002f017  mov     r8, rbx; unsigned int
0x18002f01a  mov     edx, 98h; void *
0x18002f01f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f024  mov     edx, [rbp+4Fh+arg_20]; unsigned __int64
0x18002f027  mov     r8, rdi; unsigned __int16 *
0x18002f02a  mov     rcx, r15; unsigned __int16 *
0x18002f02d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002f032  mov     edi, eax
0x18002f034  test    eax, eax
0x18002f036  jns     short loc_18002F0A6
0x18002f038  mov     rcx, [rbp+57h]; this
0x18002f03c  mov     r9d, eax; char *
0x18002f03f  mov     r8, rbx; unsigned int
0x18002f042  mov     edx, 9Bh; void *
0x18002f047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f04c  nop
0x18002f04d  lea     rdx, [rsp+120h+var_E8]; void **
0x18002f052  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18002f056  call    ?UnloadUserClasses@@YAJPEBGPEAPEAX@Z; UnloadUserClasses(ushort const *,void * *)
0x18002f05b  mov     rcx, [rbp+57h]; this
0x18002f05f  test    eax, eax
0x18002f061  jns     short loc_18002F074
0x18002f063  mov     r9d, eax; char *
0x18002f066  mov     r8, rbx; unsigned int
0x18002f069  mov     edx, 8Fh; void *
0x18002f06e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f073  nop
0x18002f074  lea     r9, [rsp+120h+var_F0]
0x18002f079  xor     r8d, r8d
0x18002f07c  mov     rdx, [rbp+4Fh+lpString1]
0x18002f080  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x18002f085  mov     rcx, [rbp+57h]; this
0x18002f089  test    eax, eax
0x18002f08b  jns     loc_18002EEC2
0x18002f091  mov     r9d, eax; char *
0x18002f094  mov     r8, rbx; unsigned int
0x18002f097  mov     edx, 7Ch ; '|'; void *
0x18002f09c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f0a1  jmp     loc_18002EEC2
0x18002f0a6  mov     [rbp+4Fh+var_C8], r12
0x18002f0aa  mov     [rbp+4Fh+var_C0], r12
0x18002f0ae  mov     [rbp+4Fh+var_B8], r12
0x18002f0b2  lea     rcx, [rbp+4Fh+var_C8]
0x18002f0b6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f0bb  mov     [rbp+4Fh+var_C0], r13
0x18002f0bf  mov     [rbp+4Fh+var_B8], r13
0x18002f0c3  xor     r8d, r8d; int *
0x18002f0c6  lea     rdx, [rbp+4Fh+var_C8]; unsigned __int16 **
0x18002f0ca  mov     rcx, [rbp+4Fh+lpString1]; lpString1
0x18002f0ce  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002f0d3  mov     edi, eax
0x18002f0d5  test    eax, eax
0x18002f0d7  jns     short loc_18002F123
0x18002f0d9  mov     rcx, [rbp+57h]; this
0x18002f0dd  mov     r9d, eax; char *
0x18002f0e0  mov     r8, rbx; unsigned int
0x18002f0e3  mov     edx, 9Fh; void *
0x18002f0e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f0ed  lea     rcx, [rbp+4Fh+var_C8]
0x18002f0f1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f0f6  nop
0x18002f0f7  lea     rdx, [rsp+120h+var_E8]; void **
0x18002f0fc  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18002f100  call    ?UnloadUserClasses@@YAJPEBGPEAPEAX@Z; UnloadUserClasses(ushort const *,void * *)
0x18002f105  mov     rcx, [rbp+57h]; this
0x18002f109  test    eax, eax
0x18002f10b  jns     short loc_18002F11E
0x18002f10d  mov     r9d, eax; char *
0x18002f110  mov     r8, rbx; unsigned int
0x18002f113  mov     edx, 8Fh; void *
0x18002f118  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f11d  nop
0x18002f11e  jmp     loc_18002F074
0x18002f123  mov     r9d, r14d; unsigned int
0x18002f126  lea     r8, aFullprofile; "FullProfile"
0x18002f12d  mov     rdx, [rbp+4Fh+var_C8]; unsigned __int16 *
0x18002f131  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002f138  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002f13d  mov     edi, eax
0x18002f13f  test    eax, eax
0x18002f141  jns     short loc_18002F18D
0x18002f143  mov     rcx, [rbp+57h]; this
0x18002f147  mov     r9d, eax; char *
0x18002f14a  mov     r8, rbx; unsigned int
0x18002f14d  mov     edx, 0A0h; void *
0x18002f152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f157  lea     rcx, [rbp+4Fh+var_C8]
0x18002f15b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f160  nop
0x18002f161  lea     rdx, [rsp+120h+var_E8]; void **
0x18002f166  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
  ... truncated ...
```
