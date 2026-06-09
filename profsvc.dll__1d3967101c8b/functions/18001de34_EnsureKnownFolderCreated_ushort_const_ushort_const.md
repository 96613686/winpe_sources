# EnsureKnownFolderCreated(ushort const *,ushort const *)

- ea: `0x18001de34`
- end: `0x18001e061`
- name: `?EnsureKnownFolderCreated@@YAJPEBG0@Z`
- size: `557`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001dd04`

## callees

- `0x180005fd0`
- `0x180010f30`
- `0x1800111a0`
- `0x18001de34`
- `0x18001e070`
- `0x18002d2d8`
- `0x18002f8e0`
- `0x18003a730`
- `0x18003b310`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18001de85`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18001de85`

## string_xrefs

- `0x18001df71`: `Security`
- `0x18001dea9`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001def4`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001df49`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001dfcf`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001de9a`: `Failed to get USERPROFILE path.`
- `0x18001df12`: `RelativePath`

## pseudocode

```c
__int64 __fastcall EnsureKnownFolderCreated(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int BasicProfileFolderPath; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-E0h]
  const char *v11; // [rsp+28h] [rbp-D8h]
  _QWORD v12[3]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR StringSecurityDescriptor[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v15[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v16[528]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset_0(v16, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(5, a1, v16, 260);
  if ( (BasicProfileFolderPath & 0x80000000) == 0 )
  {
    memset(v15, 0, sizeof(v15));
    v5 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
           v15,
           L"%s\\%s",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderDescriptions",
           a2);
    BasicProfileFolderPath = v5;
    if ( v5 >= 0 )
    {
      memset(v12, 0, sizeof(v12));
      v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
             v12,
             -2147483646,
             v15[0],
             L"RelativePath");
      BasicProfileFolderPath = v6;
      if ( v6 >= 0 )
      {
        memset(StringSecurityDescriptor, 0, sizeof(StringSecurityDescriptor));
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
          StringSecurityDescriptor,
          -2147483646,
          v15[0],
          L"Security");
        memset(v13, 0, sizeof(v13));
        v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
               v13,
               L"%s\\%s",
               v16,
               v12[0]);
        BasicProfileFolderPath = v7;
        if ( v7 >= 0 )
        {
          v7 = EnsurePathCreated(v13[0], StringSecurityDescriptor[0]);
          BasicProfileFolderPath = v7;
          if ( v7 >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v13);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)StringSecurityDescriptor);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v12);
            BasicProfileFolderPath = 0;
            goto LABEL_14;
          }
          v8 = 1037;
        }
        else
        {
          v8 = 1035;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v7,
          v10);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v13);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)StringSecurityDescriptor);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x404,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v6,
          v10);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x401,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v5,
        v10);
    }
LABEL_14:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v15);
    return BasicProfileFolderPath;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x3FD,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)BasicProfileFolderPath,
    (int)"Failed to get USERPROFILE path.",
    v11);
  return BasicProfileFolderPath;
}

```

## disassembly

```asm
0x18001de34  mov     [rsp-8+arg_10], rbx
0x18001de39  push    rbp
0x18001de3a  push    rsi
0x18001de3b  push    rdi
0x18001de3c  lea     rbp, [rsp-1B0h]
0x18001de44  sub     rsp, 2B0h
0x18001de4b  mov     rax, cs:__security_cookie
0x18001de52  xor     rax, rsp
0x18001de55  mov     [rbp+1C0h+var_20], rax
0x18001de5c  mov     rdi, rdx
0x18001de5f  mov     rbx, rcx
0x18001de62  xor     edx, edx; Val
0x18001de64  lea     rcx, [rbp+1C0h+var_230]; void *
0x18001de68  mov     r8d, 208h; Size
0x18001de6e  call    memset_0
0x18001de73  mov     r9d, 104h
0x18001de79  lea     r8, [rbp+1C0h+var_230]
0x18001de7d  mov     rdx, rbx
0x18001de80  mov     ecx, 5
0x18001de85  call    cs:__imp_GetBasicProfileFolderPath
0x18001de8b  xor     esi, esi
0x18001de8d  mov     ebx, eax
0x18001de8f  test    eax, eax
0x18001de91  jns     short loc_18001DEBF
0x18001de93  mov     rcx, [rbp+1C8h]; this
0x18001de9a  lea     rax, aFailedToGetUse; "Failed to get USERPROFILE path."
0x18001dea1  mov     r9d, ebx; char *
0x18001dea4  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18001dea9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001deb0  mov     edx, 3FDh; void *
0x18001deb5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001deba  jmp     loc_18001E03D
0x18001debf  mov     r9, rdi
0x18001dec2  mov     [rsp+2C0h+var_248], rsi
0x18001dec7  lea     r8, aSoftwareMicros_37; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001dece  mov     [rbp+1C0h+var_240], rsi
0x18001ded2  lea     rdx, aSS_0; "%s\\%s"
0x18001ded9  mov     [rbp+1C0h+var_238], rsi
0x18001dedd  lea     rcx, [rsp+2C0h+var_248]
0x18001dee2  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001dee7  mov     ebx, eax
0x18001dee9  test    eax, eax
0x18001deeb  jns     short loc_18001DF0D
0x18001deed  mov     rcx, [rbp+1C8h]; this
0x18001def4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001defb  mov     r9d, eax; char *
0x18001defe  mov     edx, 401h; void *
0x18001df03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df08  jmp     loc_18001E033
0x18001df0d  mov     r8, [rsp+2C0h+var_248]
0x18001df12  lea     r9, aRelativepath; "RelativePath"
0x18001df19  mov     rdi, 0FFFFFFFF80000002h
0x18001df20  mov     [rsp+2C0h+var_290], rsi
0x18001df25  mov     rdx, rdi
0x18001df28  mov     [rsp+2C0h+var_288], rsi
0x18001df2d  lea     rcx, [rsp+2C0h+var_290]
0x18001df32  mov     [rsp+2C0h+var_280], rsi
0x18001df37  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18001df3c  mov     ebx, eax
0x18001df3e  test    eax, eax
0x18001df40  jns     short loc_18001DF6C
0x18001df42  mov     rcx, [rbp+1C8h]; this
0x18001df49  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001df50  mov     r9d, eax; char *
0x18001df53  mov     edx, 404h; void *
0x18001df58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df5d  lea     rcx, [rsp+2C0h+var_290]
0x18001df62  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001df67  jmp     loc_18001E033
0x18001df6c  mov     r8, [rsp+2C0h+var_248]
0x18001df71  lea     r9, aSecurity; "Security"
0x18001df78  mov     rdx, rdi
0x18001df7b  mov     [rsp+2C0h+StringSecurityDescriptor], rsi
0x18001df80  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18001df85  mov     [rsp+2C0h+var_258], rsi
0x18001df8a  mov     [rsp+2C0h+var_250], rsi
0x18001df8f  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18001df94  mov     r9, [rsp+2C0h+var_290]
0x18001df99  lea     r8, [rbp+1C0h+var_230]
0x18001df9d  lea     rdx, aSS_0; "%s\\%s"
0x18001dfa4  mov     [rsp+2C0h+var_278], rsi
0x18001dfa9  lea     rcx, [rsp+2C0h+var_278]
0x18001dfae  mov     [rsp+2C0h+var_270], rsi
0x18001dfb3  mov     [rsp+2C0h+var_268], rsi
0x18001dfb8  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001dfbd  mov     ebx, eax
0x18001dfbf  test    eax, eax
0x18001dfc1  jns     short loc_18001DFF7
0x18001dfc3  mov     edx, 40Bh; void *
0x18001dfc8  mov     rcx, [rbp+1C8h]; this
0x18001dfcf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dfd6  mov     r9d, eax; char *
0x18001dfd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfde  lea     rcx, [rsp+2C0h+var_278]
0x18001dfe3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001dfe8  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18001dfed  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001dff2  jmp     loc_18001DF5D
0x18001dff7  mov     rdx, [rsp+2C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001dffc  mov     rcx, [rsp+2C0h+var_278]; unsigned __int16 *
0x18001e001  call    ?EnsurePathCreated@@YAJPEBG0@Z; EnsurePathCreated(ushort const *,ushort const *)
0x18001e006  mov     ebx, eax
0x18001e008  test    eax, eax
0x18001e00a  jns     short loc_18001E013
0x18001e00c  mov     edx, 40Dh
0x18001e011  jmp     short loc_18001DFC8
0x18001e013  lea     rcx, [rsp+2C0h+var_278]
0x18001e018  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e01d  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18001e022  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e027  lea     rcx, [rsp+2C0h+var_290]
0x18001e02c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e031  mov     ebx, esi
0x18001e033  lea     rcx, [rsp+2C0h+var_248]
0x18001e038  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e03d  mov     eax, ebx
0x18001e03f  mov     rcx, [rbp+1C0h+var_20]
0x18001e046  xor     rcx, rsp; StackCookie
0x18001e049  call    __security_check_cookie
0x18001e04e  mov     rbx, [rsp+2C0h+arg_10]
0x18001e056  add     rsp, 2B0h
0x18001e05d  pop     rdi
0x18001e05e  pop     rsi
0x18001e05f  pop     rbp
0x18001e060  retn
```
