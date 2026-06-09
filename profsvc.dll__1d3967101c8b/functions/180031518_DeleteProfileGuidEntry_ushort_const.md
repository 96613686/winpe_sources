# DeleteProfileGuidEntry(ushort const *)

- ea: `0x180031518`
- end: `0x1800316b1`
- name: `?DeleteProfileGuidEntry@@YAJPEBG@Z`
- size: `409`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e0cc`
- `0x18002fb04`

## callees

- `0x18000f1b0`
- `0x180010f30`
- `0x1800111a0`
- `0x18001e070`
- `0x18002d2d8`
- `0x18002e648`
- `0x180031518`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003165e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003165e`

## string_xrefs

- `0x18003156e`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800315cf`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18003162e`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18003166c`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

## pseudocode

```c
__int64 __fastcall DeleteProfileGuidEntry(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // eax
  unsigned __int16 *v8[3]; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int16 *v9; // [rsp+38h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-30h]
  __int64 v11; // [rsp+48h] [rbp-28h]
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v9 = 0;
  v10 = 0;
  v11 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v9);
  v10 = -1;
  v11 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, &v9, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    memset(v8, 0, sizeof(v8));
    v4 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
           v8,
           -2147483646,
           v9,
           L"Guid");
    v3 = v4;
    if ( v4 != -2147024894 )
    {
      if ( v4 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v4,
          (int)v8[0]);
LABEL_6:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v8);
        goto LABEL_14;
      }
      memset(lpSubKey, 0, 24);
      v5 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             lpSubKey,
             L"%s\\%s",
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileGuid",
             v8[0]);
      v3 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v5,
          (int)v8[0]);
LABEL_9:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
        goto LABEL_6;
      }
      v6 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0);
      if ( v6 )
      {
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x94,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
               (const char *)v6,
               (unsigned int)v8[0]);
        goto LABEL_9;
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v8);
    v3 = 0;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x86,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    (int)v8[0]);
LABEL_14:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v9);
  return v3;
}

```

## disassembly

```asm
0x180031518  mov     [rsp-8+arg_0], rbx
0x18003151d  push    rbp
0x18003151e  mov     rbp, rsp
0x180031521  sub     rsp, 70h
0x180031525  mov     rbx, rcx
0x180031528  mov     [rbp+var_38], 0
0x180031530  lea     rcx, [rbp+var_38]
0x180031534  mov     [rbp+var_30], 0
0x18003153c  mov     [rbp+var_28], 0
0x180031544  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031549  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003154d  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x180031551  xor     r8d, r8d; int *
0x180031554  mov     [rbp+var_30], rax
0x180031558  mov     rcx, rbx; lpString1
0x18003155b  mov     [rbp+var_28], rax
0x18003155f  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180031564  mov     ebx, eax
0x180031566  test    eax, eax
0x180031568  jns     short loc_180031587
0x18003156a  mov     rcx, [rbp+8]; this
0x18003156e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031575  mov     r9d, eax; char *
0x180031578  mov     edx, 86h; void *
0x18003157d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031582  jmp     loc_180031698
0x180031587  mov     r8, [rbp+var_38]
0x18003158b  lea     r9, aGuid; "Guid"
0x180031592  mov     rdx, 0FFFFFFFF80000002h
0x180031599  mov     [rbp+var_50], 0
0x1800315a1  lea     rcx, [rbp+var_50]
0x1800315a5  mov     [rbp+var_48], 0
0x1800315ad  mov     [rbp+var_40], 0
0x1800315b5  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800315ba  mov     ebx, eax
0x1800315bc  cmp     eax, 80070002h
0x1800315c1  jz      loc_18003168D
0x1800315c7  test    eax, eax
0x1800315c9  jns     short loc_1800315F1
0x1800315cb  mov     rcx, [rbp+8]; this
0x1800315cf  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800315d6  mov     r9d, eax; char *
0x1800315d9  mov     edx, 8Dh; void *
0x1800315de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315e3  lea     rcx, [rbp+var_50]
0x1800315e7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800315ec  jmp     loc_180031698
0x1800315f1  mov     r9, [rbp+var_50]
0x1800315f5  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800315fc  lea     rdx, aSS_0; "%s\\%s"
0x180031603  mov     [rbp+lpSubKey], 0
0x18003160b  lea     rcx, [rbp+lpSubKey]
0x18003160f  mov     [rbp+var_18], 0
0x180031617  mov     [rbp+var_10], 0
0x18003161f  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180031624  mov     ebx, eax
0x180031626  test    eax, eax
0x180031628  jns     short loc_18003164D
0x18003162a  mov     rcx, [rbp+8]; this
0x18003162e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031635  mov     r9d, eax; char *
0x180031638  mov     edx, 91h; void *
0x18003163d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031642  lea     rcx, [rbp+lpSubKey]
0x180031646  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003164b  jmp     short loc_1800315E3
0x18003164d  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180031651  xor     r9d, r9d; Reserved
0x180031654  xor     r8d, r8d; samDesired
0x180031657  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003165e  call    cs:__imp_RegDeleteKeyExW
0x180031664  test    eax, eax
0x180031666  jz      short loc_180031684
0x180031668  mov     rcx, [rbp+8]; this
0x18003166c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031673  mov     r9d, eax; char *
0x180031676  mov     edx, 94h; void *
0x18003167b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031680  mov     ebx, eax
0x180031682  jmp     short loc_180031642
0x180031684  lea     rcx, [rbp+lpSubKey]
0x180031688  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003168d  lea     rcx, [rbp+var_50]
0x180031691  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031696  xor     ebx, ebx
0x180031698  lea     rcx, [rbp+var_38]
0x18003169c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800316a1  mov     eax, ebx
0x1800316a3  mov     rbx, [rsp+70h+arg_0]
0x1800316ab  add     rsp, 70h
0x1800316af  pop     rbp
0x1800316b0  retn
```
