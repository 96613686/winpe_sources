# DeleteProfileGuidEntry(ushort const *)

- ea: `0x1800314a4`
- end: `0x180031644`
- name: `?DeleteProfileGuidEntry@@YAJPEBG@Z`
- size: `416`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f6e8`
- `0x18002fa8c`

## callees

- `0x18000d030`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x180022130`
- `0x180030ad0`
- `0x180031060`
- `0x1800314a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800315ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800315ea`

## string_xrefs

- `0x1800314fa`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18003155b`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800315ba`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800315fe`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v9);
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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v8);
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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v8);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v9);
  return v3;
}

```

## disassembly

```asm
0x1800314a4  mov     [rsp-8+arg_0], rbx
0x1800314a9  push    rbp
0x1800314aa  mov     rbp, rsp
0x1800314ad  sub     rsp, 70h
0x1800314b1  mov     rbx, rcx
0x1800314b4  mov     [rbp+var_38], 0
0x1800314bc  lea     rcx, [rbp+var_38]
0x1800314c0  mov     [rbp+var_30], 0
0x1800314c8  mov     [rbp+var_28], 0
0x1800314d0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800314d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800314d9  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x1800314dd  xor     r8d, r8d; int *
0x1800314e0  mov     [rbp+var_30], rax
0x1800314e4  mov     rcx, rbx; lpString1
0x1800314e7  mov     [rbp+var_28], rax
0x1800314eb  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x1800314f0  mov     ebx, eax
0x1800314f2  test    eax, eax
0x1800314f4  jns     short loc_180031513
0x1800314f6  mov     rcx, [rbp+8]; this
0x1800314fa  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031501  mov     r9d, eax; char *
0x180031504  mov     edx, 86h; void *
0x180031509  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003150e  jmp     loc_18003162A
0x180031513  mov     r8, [rbp+var_38]
0x180031517  lea     r9, aGuid; "Guid"
0x18003151e  mov     rdx, 0FFFFFFFF80000002h
0x180031525  mov     [rbp+var_50], 0
0x18003152d  lea     rcx, [rbp+var_50]
0x180031531  mov     [rbp+var_48], 0
0x180031539  mov     [rbp+var_40], 0
0x180031541  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180031546  mov     ebx, eax
0x180031548  cmp     eax, 80070002h
0x18003154d  jz      loc_18003161F
0x180031553  test    eax, eax
0x180031555  jns     short loc_18003157D
0x180031557  mov     rcx, [rbp+8]; this
0x18003155b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031562  mov     r9d, eax; char *
0x180031565  mov     edx, 8Dh; void *
0x18003156a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003156f  lea     rcx, [rbp+var_50]
0x180031573  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031578  jmp     loc_18003162A
0x18003157d  mov     r9, [rbp+var_50]
0x180031581  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x180031588  lea     rdx, aSS_0; "%s\\%s"
0x18003158f  mov     [rbp+lpSubKey], 0
0x180031597  lea     rcx, [rbp+lpSubKey]
0x18003159b  mov     [rbp+var_18], 0
0x1800315a3  mov     [rbp+var_10], 0
0x1800315ab  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800315b0  mov     ebx, eax
0x1800315b2  test    eax, eax
0x1800315b4  jns     short loc_1800315D9
0x1800315b6  mov     rcx, [rbp+8]; this
0x1800315ba  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800315c1  mov     r9d, eax; char *
0x1800315c4  mov     edx, 91h; void *
0x1800315c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315ce  lea     rcx, [rbp+lpSubKey]
0x1800315d2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800315d7  jmp     short loc_18003156F
0x1800315d9  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800315dd  xor     r9d, r9d; Reserved
0x1800315e0  xor     r8d, r8d; samDesired
0x1800315e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800315ea  call    cs:__imp_RegDeleteKeyExW
0x1800315f1  nop     dword ptr [rax+rax+00h]
0x1800315f6  test    eax, eax
0x1800315f8  jz      short loc_180031616
0x1800315fa  mov     rcx, [rbp+8]; this
0x1800315fe  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031605  mov     r9d, eax; char *
0x180031608  mov     edx, 94h; void *
0x18003160d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031612  mov     ebx, eax
0x180031614  jmp     short loc_1800315CE
0x180031616  lea     rcx, [rbp+lpSubKey]
0x18003161a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003161f  lea     rcx, [rbp+var_50]
0x180031623  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031628  xor     ebx, ebx
0x18003162a  lea     rcx, [rbp+var_38]
0x18003162e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031633  mov     eax, ebx
0x180031635  mov     rbx, [rsp+70h+arg_0]
0x18003163d  add     rsp, 70h
0x180031641  pop     rbp
0x180031642  retn
```
