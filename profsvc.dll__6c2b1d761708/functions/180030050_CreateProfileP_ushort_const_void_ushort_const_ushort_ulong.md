# CreateProfileP(ushort const *,void *,ushort const *,ushort *,ulong)

- ea: `0x180030050`
- end: `0x180030575`
- name: `?CreateProfileP@@YAJPEBGPEAX0PEAGK@Z`
- size: `1317`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004e150`

## callees

- `0x18000626c`
- `0x180006498`
- `0x18000d030`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x180014b4c`
- `0x180014e90`
- `0x180016150`
- `0x1800178bc`
- `0x180024540`
- `0x180030050`
- `0x180030ad0`
- `0x180031e70`
- `0x18003a7d8`
- `0x180040bcc`
- `0x180040e94`
- `0x180041560`
- `0x180041c28`
- `0x180041e04`
- `0x180041f2c`
- `0x1800500c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800301ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800301ed`

## string_xrefs

- `0x180030098`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18003010b`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18003013b`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180030179`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

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
  int v11; // r8d
  HANDLE v12; // rdi
  int DirectoryForUser; // esi
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  HKEY v17; // rcx
  HKEY v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  wil::details::in1diag3 *v25; // rcx
  int v26; // eax
  int ProfileListKeyNameFromSid; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  wil::details::in1diag3 *v32; // rcx
  int v33; // eax
  int v34; // [rsp+20h] [rbp-B1h]
  int v35; // [rsp+20h] [rbp-B1h]
  int v36; // [rsp+20h] [rbp-B1h]
  void *v37; // [rsp+30h] [rbp-A1h] BYREF
  void *v38; // [rsp+38h] [rbp-99h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+40h] [rbp-91h] BYREF
  unsigned __int16 *p_lpString1; // [rsp+58h] [rbp-79h] BYREF
  __int64 v41; // [rsp+60h] [rbp-71h]
  __int64 v42; // [rsp+68h] [rbp-69h]
  HANDLE hEvent; // [rsp+70h] [rbp-61h] BYREF
  __int64 v44; // [rsp+78h] [rbp-59h]
  __int64 v45; // [rsp+80h] [rbp-51h]
  unsigned __int16 *v46; // [rsp+88h] [rbp-49h] BYREF
  __int64 v47; // [rsp+90h] [rbp-41h]
  __int64 v48; // [rsp+98h] [rbp-39h]
  _QWORD v49[6]; // [rsp+A0h] [rbp-31h] BYREF
  char v50; // [rsp+D0h] [rbp-1h]
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
        v34);
      return v8;
    }
    v46 = 0;
    v47 = 0;
    v48 = 0;
    hEvent = 0;
    v44 = 0;
    v45 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&hEvent);
    v44 = -1;
    v45 = -1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v46);
    v47 = -1;
    v48 = -1;
    LocalProfileName = GetLocalProfileName(0, a3, &v46, (unsigned __int16 **)&hEvent);
    v8 = LocalProfileName;
    if ( LocalProfileName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)LocalProfileName,
        v34);
LABEL_51:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&hEvent);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v46);
      return v8;
    }
    v12 = hEvent;
    DirectoryForUser = CreateDirectoryForUser((const unsigned __int16 *)hEvent, lpString1, v11);
    if ( DirectoryForUser < 0 )
    {
      v14 = 101;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)DirectoryForUser,
        v34);
LABEL_9:
      v8 = DirectoryForUser;
      goto LABEL_51;
    }
    DirectoryForUser = _CopyFromDefaultProfile(v12);
    if ( DirectoryForUser < 0 )
    {
      v14 = 102;
      goto LABEL_8;
    }
    v15 = ChangeProfileDirectoryOwner((const unsigned __int16 *)v12, a2);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)v15,
        v34);
    memset(lpFileName, 0, sizeof(lpFileName));
    DirectoryForUser = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                         lpFileName,
                         L"%s\\%s",
                         v12,
                         L"ntuser.dat");
    if ( DirectoryForUser < 0 )
    {
      v16 = 107;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)DirectoryForUser,
        v34);
LABEL_17:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
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
        v34);
LABEL_20:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
      goto LABEL_51;
    }
    v37 = 0;
    DirectoryForUser = MountRegHive(v17, lpString1, lpFileName[0], 0, 0, &v37);
    if ( DirectoryForUser < 0 )
    {
      v16 = 121;
      goto LABEL_16;
    }
    v49[4] = &lpString1;
    v49[5] = &v37;
    v50 = 1;
    VerifyCriticalKeysInUserHive(lpString1);
    DirectoryForUser = SetDefaultUserHiveSecurity(lpString1, v18);
    if ( DirectoryForUser >= 0 )
    {
      DirectoryForUser = _SaveProfileListKeyInfo(lpString1, (BYTE *)a2, v46);
      if ( DirectoryForUser >= 0 )
      {
        v38 = 0;
        DirectoryForUser = LoadChangeUserClasses(lpString1, 0, 1, 0, &v38, 0);
        if ( DirectoryForUser >= 0 )
        {
          p_lpString1 = (unsigned __int16 *)&lpString1;
          v41 = (__int64)&v38;
          LOBYTE(v42) = 1;
          v49[2] = 0;
          v49[3] = 0;
          v49[0] = lpString1;
          v49[1] = v12;
          v22 = SendNotification(1, v49, 0xFFFFFFFFLL);
          if ( v22 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x98,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
              (const char *)(unsigned int)v22,
              v34);
          v23 = StringCchCopyW(a4, a5, (const unsigned __int16 *)v12);
          v8 = v23;
          if ( v23 >= 0 )
          {
            p_lpString1 = 0;
            v41 = 0;
            v42 = 0;
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&p_lpString1);
            v41 = -1;
            v42 = -1;
            ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, &p_lpString1, 0);
            v8 = ProfileListKeyNameFromSid;
            if ( ProfileListKeyNameFromSid >= 0 )
            {
              v29 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, p_lpString1, L"FullProfile", 1u);
              v8 = v29;
              if ( v29 >= 0 )
              {
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&p_lpString1);
                v31 = UnloadUserClasses(lpString1, &v38);
                v32 = retaddr;
                if ( v31 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x8F,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                    (const char *)(unsigned int)v31,
                    v34);
                v33 = UnmountRegHive(v32, lpString1, 0, &v37);
                if ( v33 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x7C,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                    (const char *)(unsigned int)v33,
                    v34);
                Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
                v8 = 0;
                goto LABEL_51;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA0,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                (const char *)(unsigned int)v29,
                v34);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&p_lpString1);
              v30 = UnloadUserClasses(lpString1, &v38);
              v25 = retaddr;
              if ( v30 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                  (const char *)(unsigned int)v30,
                  v36);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9F,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                (const char *)(unsigned int)ProfileListKeyNameFromSid,
                v34);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&p_lpString1);
              v28 = UnloadUserClasses(lpString1, &v38);
              v25 = retaddr;
              if ( v28 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                  (const char *)(unsigned int)v28,
                  v36);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9B,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
              (const char *)(unsigned int)v23,
              v34);
            v24 = UnloadUserClasses(lpString1, &v38);
            v25 = retaddr;
            if ( v24 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8F,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                (const char *)(unsigned int)v24,
                v36);
          }
          v26 = UnmountRegHive(v25, lpString1, 0, &v37);
          if ( v26 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
              (const char *)(unsigned int)v26,
              v36);
          goto LABEL_20;
        }
        v19 = 139;
      }
      else
      {
        v19 = 133;
      }
    }
    else
    {
      v19 = 130;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)DirectoryForUser,
      v34);
    v21 = UnmountRegHive(v20, lpString1, 0, &v37);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)v21,
        v35);
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x180030050  mov     [rsp-8+lpString1], rcx
0x180030055  push    rbp
0x180030056  push    rbx
0x180030057  push    rsi
0x180030058  push    rdi
0x180030059  push    r12
0x18003005b  push    r13
0x18003005d  push    r14
0x18003005f  push    r15
0x180030061  lea     rbp, [rsp-17h]
0x180030066  sub     rsp, 0E8h
0x18003006d  mov     r15, r9
0x180030070  mov     rbx, r8
0x180030073  mov     r14, rdx
0x180030076  call    ?_CheckIfProfileListKeyExists@@YAJPEBG@Z; _CheckIfProfileListKeyExists(ushort const *)
0x18003007b  mov     edi, eax
0x18003007d  mov     eax, 800700B7h
0x180030082  cmp     edi, eax
0x180030084  jz      loc_180030560
0x18003008a  xor     r12d, r12d
0x18003008d  test    edi, edi
0x18003008f  jns     short loc_1800300AE
0x180030091  mov     rcx, [rbp+57h]; this
0x180030095  mov     r9d, edi; char *
0x180030098  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003009f  lea     edx, [r12+5Fh]; void *
0x1800300a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300a9  jmp     loc_18003055E
0x1800300ae  mov     [rbp+4Fh+var_98], r12
0x1800300b2  mov     [rbp+4Fh+var_90], r12
0x1800300b6  mov     [rbp+4Fh+var_88], r12
0x1800300ba  mov     [rbp+4Fh+hEvent], r12
0x1800300be  mov     [rbp+4Fh+var_A8], r12
0x1800300c2  mov     [rbp+4Fh+var_A0], r12
0x1800300c6  lea     rcx, [rbp+4Fh+hEvent]
0x1800300ca  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800300cf  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800300d3  mov     [rbp+4Fh+var_A8], r13
0x1800300d7  mov     [rbp+4Fh+var_A0], r13
0x1800300db  lea     rcx, [rbp+4Fh+var_98]
0x1800300df  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800300e4  mov     [rbp+4Fh+var_90], r13
0x1800300e8  mov     [rbp+4Fh+var_88], r13
0x1800300ec  lea     r9, [rbp+4Fh+hEvent]; unsigned __int16 **
0x1800300f0  lea     r8, [rbp+4Fh+var_98]; unsigned __int16 **
0x1800300f4  mov     rdx, rbx; unsigned __int16 *
0x1800300f7  xor     ecx, ecx; void *
0x1800300f9  call    ?GetLocalProfileName@@YAJPEAXPEBGPEAPEAG2@Z; GetLocalProfileName(void *,ushort const *,ushort * *,ushort * *)
0x1800300fe  mov     edi, eax
0x180030100  test    eax, eax
0x180030102  jns     short loc_180030120
0x180030104  mov     rcx, [rbp+57h]; this
0x180030108  mov     r9d, eax; char *
0x18003010b  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030112  lea     edx, [r13+64h]; void *
0x180030116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003011b  jmp     loc_18003054B
0x180030120  mov     rdx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x180030124  mov     rdi, [rbp+4Fh+hEvent]
0x180030128  mov     rcx, rdi; unsigned __int16 *
0x18003012b  call    ?CreateDirectoryForUser@@YAJPEBG0H@Z; CreateDirectoryForUser(ushort const *,ushort const *,int)
0x180030130  mov     esi, eax
0x180030132  test    eax, eax
0x180030134  jns     short loc_180030155
0x180030136  mov     edx, 65h ; 'e'; void *
0x18003013b  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030142  mov     r9d, esi; char *
0x180030145  mov     rcx, [rbp+57h]; this
0x180030149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003014e  mov     edi, esi
0x180030150  jmp     loc_18003054B
0x180030155  mov     rcx, rdi; hEvent
0x180030158  call    ?_CopyFromDefaultProfile@@YAJPEBG@Z; _CopyFromDefaultProfile(ushort const *)
0x18003015d  mov     esi, eax
0x18003015f  test    eax, eax
0x180030161  jns     short loc_18003016A
0x180030163  mov     edx, 66h ; 'f'
0x180030168  jmp     short loc_18003013B
0x18003016a  mov     rdx, r14; void *
0x18003016d  mov     rcx, rdi; unsigned __int16 *
0x180030170  call    ?ChangeProfileDirectoryOwner@@YAJPEBGPEAX@Z; ChangeProfileDirectoryOwner(ushort const *,void *)
0x180030175  mov     rcx, [rbp+57h]; this
0x180030179  lea     rbx, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030180  test    eax, eax
0x180030182  jns     short loc_180030194
0x180030184  mov     r9d, eax; char *
0x180030187  mov     r8, rbx; unsigned int
0x18003018a  mov     edx, 68h ; 'h'; void *
0x18003018f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030194  mov     [rsp+120h+lpFileName], r12
0x180030199  mov     [rsp+120h+var_D8], r12
0x18003019e  mov     [rsp+120h+var_D0], r12
0x1800301a3  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x1800301aa  mov     r8, rdi
0x1800301ad  lea     rdx, aSS_0; "%s\\%s"
0x1800301b4  lea     rcx, [rsp+120h+lpFileName]
0x1800301b9  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800301be  mov     esi, eax
0x1800301c0  test    eax, eax
0x1800301c2  jns     short loc_1800301E8
0x1800301c4  mov     edx, 6Bh ; 'k'; void *
0x1800301c9  mov     r8, rbx; unsigned int
0x1800301cc  mov     r9d, esi; char *
0x1800301cf  mov     rcx, [rbp+57h]; this
0x1800301d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301d8  nop
0x1800301d9  lea     rcx, [rsp+120h+lpFileName]
0x1800301de  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800301e3  jmp     loc_18003014E
0x1800301e8  mov     rcx, [rsp+120h+lpFileName]; lpFileName
0x1800301ed  call    cs:__imp_GetFileAttributesW
0x1800301f4  nop     dword ptr [rax+rax+00h]
0x1800301f9  cmp     eax, 0FFFFFFFFh
0x1800301fc  jnz     short loc_180030227
0x1800301fe  mov     rcx, [rbp+57h]; this
0x180030202  mov     edi, 8007139Fh
0x180030207  mov     r9d, edi; char *
0x18003020a  mov     r8, rbx; unsigned int
0x18003020d  mov     edx, 70h ; 'p'; void *
0x180030212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030217  nop
0x180030218  lea     rcx, [rsp+120h+lpFileName]
0x18003021d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180030222  jmp     loc_18003054B
0x180030227  mov     [rsp+120h+var_F0], r12
0x18003022c  lea     rax, [rsp+120h+var_F0]
0x180030231  mov     [rsp+120h+var_F8], rax; void **
0x180030236  mov     [rsp+120h+var_100], r12; int
0x18003023b  xor     r9d, r9d; HKEY
0x18003023e  mov     r8, [rsp+120h+lpFileName]; unsigned __int16 *
0x180030243  mov     rdx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x180030247  call    ?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z; MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)
0x18003024c  mov     esi, eax
0x18003024e  test    eax, eax
0x180030250  jns     short loc_18003025C
0x180030252  mov     edx, 79h ; 'y'
0x180030257  jmp     loc_1800301C9
0x18003025c  lea     rax, [rbp+4Fh+lpString1]
0x180030260  mov     [rbp+4Fh+var_60], rax
0x180030264  lea     rax, [rsp+120h+var_F0]
0x180030269  mov     [rbp+4Fh+var_58], rax
0x18003026d  mov     [rbp+4Fh+var_50], 1
0x180030271  mov     rcx, [rbp+4Fh+lpString1]; lpSubKey
0x180030275  call    ?VerifyCriticalKeysInUserHive@@YAXPEBG@Z; VerifyCriticalKeysInUserHive(ushort const *)
0x18003027a  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x18003027e  call    ?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z; SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)
0x180030283  mov     esi, eax
0x180030285  test    eax, eax
0x180030287  jns     short loc_1800302D0
0x180030289  mov     edx, 82h; void *
0x18003028e  mov     rcx, [rbp+57h]; this
0x180030292  mov     r9d, esi; char *
0x180030295  mov     r8, rbx; unsigned int
0x180030298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003029d  nop
0x18003029e  lea     r9, [rsp+120h+var_F0]
0x1800302a3  xor     r8d, r8d
0x1800302a6  mov     rdx, [rbp+4Fh+lpString1]
0x1800302aa  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x1800302af  mov     rcx, [rbp+57h]; this
0x1800302b3  test    eax, eax
0x1800302b5  jns     loc_1800301D9
0x1800302bb  mov     r9d, eax; char *
0x1800302be  mov     r8, rbx; unsigned int
0x1800302c1  mov     edx, 7Ch ; '|'; void *
0x1800302c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800302cb  jmp     loc_1800301D9
0x1800302d0  mov     r8, [rbp+4Fh+var_98]; unsigned __int16 *
0x1800302d4  mov     rdx, r14; lpData
0x1800302d7  mov     rcx, [rbp+4Fh+lpString1]; lpString1
0x1800302db  call    ?_SaveProfileListKeyInfo@@YAJPEBGPEAX0@Z; _SaveProfileListKeyInfo(ushort const *,void *,ushort const *)
0x1800302e0  mov     esi, eax
0x1800302e2  test    eax, eax
0x1800302e4  jns     short loc_1800302ED
0x1800302e6  mov     edx, 85h
0x1800302eb  jmp     short loc_18003028E
0x1800302ed  mov     [rsp+120h+var_E8], r12
0x1800302f2  mov     [rsp+120h+var_F8], r12; void *
0x1800302f7  lea     rax, [rsp+120h+var_E8]
0x1800302fc  mov     [rsp+120h+var_100], rax; int
0x180030301  xor     r9d, r9d; int
0x180030304  lea     r14d, [r9+1]
0x180030308  mov     r8d, r14d; int
0x18003030b  xor     edx, edx; unsigned __int16 *
0x18003030d  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x180030311  call    ?LoadChangeUserClasses@@YAJPEBG0HHPEAPEAXPEAX@Z; LoadChangeUserClasses(ushort const *,ushort const *,int,int,void * *,void *)
0x180030316  mov     esi, eax
0x180030318  test    eax, eax
0x18003031a  jns     short loc_180030326
0x18003031c  mov     edx, 8Bh
0x180030321  jmp     loc_18003028E
0x180030326  lea     rax, [rbp+4Fh+lpString1]
0x18003032a  mov     [rbp+4Fh+var_C8], rax
0x18003032e  lea     rax, [rsp+120h+var_E8]
0x180030333  mov     [rbp+4Fh+var_C0], rax
0x180030337  mov     byte ptr [rbp+4Fh+var_B8], r14b
0x18003033b  mov     [rbp+4Fh+var_70], r12
0x18003033f  mov     [rbp+4Fh+var_68], r12
0x180030343  mov     rax, [rbp+4Fh+lpString1]
0x180030347  mov     [rbp+4Fh+var_80], rax
0x18003034b  mov     [rbp+4Fh+var_78], rdi
0x18003034f  xor     r9d, r9d
0x180030352  or      r8d, 0FFFFFFFFh
0x180030356  lea     rdx, [rbp+4Fh+var_80]
0x18003035a  mov     ecx, r14d
0x18003035d  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x180030362  mov     rcx, [rbp+57h]; this
0x180030366  test    eax, eax
0x180030368  jns     short loc_18003037A
0x18003036a  mov     r9d, eax; char *
0x18003036d  mov     r8, rbx; unsigned int
0x180030370  mov     edx, 98h; void *
0x180030375  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003037a  mov     edx, [rbp+4Fh+arg_20]; unsigned __int64
0x18003037d  mov     r8, rdi; unsigned __int16 *
0x180030380  mov     rcx, r15; unsigned __int16 *
0x180030383  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030388  mov     edi, eax
0x18003038a  test    eax, eax
0x18003038c  jns     short loc_1800303FC
0x18003038e  mov     rcx, [rbp+57h]; this
0x180030392  mov     r9d, eax; char *
0x180030395  mov     r8, rbx; unsigned int
0x180030398  mov     edx, 9Bh; void *
0x18003039d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800303a2  nop
0x1800303a3  lea     rdx, [rsp+120h+var_E8]; void **
0x1800303a8  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x1800303ac  call    ?UnloadUserClasses@@YAJPEBGPEAPEAX@Z; UnloadUserClasses(ushort const *,void * *)
0x1800303b1  mov     rcx, [rbp+57h]; this
0x1800303b5  test    eax, eax
0x1800303b7  jns     short loc_1800303CA
0x1800303b9  mov     r9d, eax; char *
0x1800303bc  mov     r8, rbx; unsigned int
0x1800303bf  mov     edx, 8Fh; void *
0x1800303c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800303c9  nop
0x1800303ca  lea     r9, [rsp+120h+var_F0]
0x1800303cf  xor     r8d, r8d
0x1800303d2  mov     rdx, [rbp+4Fh+lpString1]
0x1800303d6  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x1800303db  mov     rcx, [rbp+57h]; this
0x1800303df  test    eax, eax
0x1800303e1  jns     loc_180030218
0x1800303e7  mov     r9d, eax; char *
0x1800303ea  mov     r8, rbx; unsigned int
0x1800303ed  mov     edx, 7Ch ; '|'; void *
0x1800303f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800303f7  jmp     loc_180030218
0x1800303fc  mov     [rbp+4Fh+var_C8], r12
0x180030400  mov     [rbp+4Fh+var_C0], r12
0x180030404  mov     [rbp+4Fh+var_B8], r12
0x180030408  lea     rcx, [rbp+4Fh+var_C8]
0x18003040c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180030411  mov     [rbp+4Fh+var_C0], r13
0x180030415  mov     [rbp+4Fh+var_B8], r13
0x180030419  xor     r8d, r8d; int *
0x18003041c  lea     rdx, [rbp+4Fh+var_C8]; unsigned __int16 **
0x180030420  mov     rcx, [rbp+4Fh+lpString1]; lpString1
0x180030424  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180030429  mov     edi, eax
0x18003042b  test    eax, eax
0x18003042d  jns     short loc_180030479
0x18003042f  mov     rcx, [rbp+57h]; this
0x180030433  mov     r9d, eax; char *
0x180030436  mov     r8, rbx; unsigned int
0x180030439  mov     edx, 9Fh; void *
0x18003043e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030443  lea     rcx, [rbp+4Fh+var_C8]
0x180030447  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003044c  nop
0x18003044d  lea     rdx, [rsp+120h+var_E8]; void **
0x180030452  mov     rcx, [rbp+4Fh+lpString1]; unsigned __int16 *
0x180030456  call    ?UnloadUserClasses@@YAJPEBGPEAPEAX@Z; UnloadUserClasses(ushort const *,void * *)
0x18003045b  mov     rcx, [rbp+57h]; this
0x18003045f  test    eax, eax
0x180030461  jns     short loc_180030474
0x180030463  mov     r9d, eax; char *
0x180030466  mov     r8, rbx; unsigned int
0x180030469  mov     edx, 8Fh; void *
0x18003046e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030473  nop
0x180030474  jmp     loc_1800303CA
0x180030479  mov     r9d, r14d; unsigned int
0x18003047c  lea     r8, aFullprofile; "FullProfile"
0x180030483  mov     rdx, [rbp+4Fh+var_C8]; unsigned __int16 *
0x180030487  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18003048e  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180030493  mov     edi, eax
0x180030495  test    eax, eax
0x180030497  jns     short loc_1800304E3
0x180030499  mov     rcx, [rbp+57h]; this
0x18003049d  mov     r9d, eax; char *
0x1800304a0  mov     r8, rbx; unsigned int
0x1800304a3  mov     edx, 0A0h; void *
0x1800304a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304ad  lea     rcx, [rbp+4Fh+var_C8]
0x1800304b1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800304b6  nop
0x1800304b7  lea     rdx, [rsp+120h+var_E8]; void **
  ... truncated ...
```
