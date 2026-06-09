# EnsureKnownFolderCreated(ushort const *,ushort const *)

- ea: `0x180021eec`
- end: `0x180022120`
- name: `?EnsureKnownFolderCreated@@YAJPEBG0@Z`
- size: `564`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021dd4`

## callees

- `0x18000d030`
- `0x18000e1a0`
- `0x1800115c0`
- `0x180021eec`
- `0x180022130`
- `0x180030ad0`
- `0x180035860`
- `0x18003bc70`
- `0x18003c870`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180021f3d`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180021f3d`

## string_xrefs

- `0x18002202f`: `Security`
- `0x180021f67`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180021fb2`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180022007`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002208d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180021f58`: `Failed to get USERPROFILE path.`
- `0x180021fd0`: `RelativePath`

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
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v13);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(StringSecurityDescriptor);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v12);
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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v13);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(StringSecurityDescriptor);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v12);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v15);
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
0x180021eec  mov     [rsp-8+arg_10], rbx
0x180021ef1  push    rbp
0x180021ef2  push    rsi
0x180021ef3  push    rdi
0x180021ef4  lea     rbp, [rsp-1B0h]
0x180021efc  sub     rsp, 2B0h
0x180021f03  mov     rax, cs:__security_cookie
0x180021f0a  xor     rax, rsp
0x180021f0d  mov     [rbp+1C0h+var_20], rax
0x180021f14  mov     rdi, rdx
0x180021f17  mov     rbx, rcx
0x180021f1a  xor     edx, edx; Val
0x180021f1c  lea     rcx, [rbp+1C0h+var_230]; void *
0x180021f20  mov     r8d, 208h; Size
0x180021f26  call    memset_0
0x180021f2b  mov     r9d, 104h
0x180021f31  lea     r8, [rbp+1C0h+var_230]
0x180021f35  mov     rdx, rbx
0x180021f38  mov     ecx, 5
0x180021f3d  call    cs:__imp_GetBasicProfileFolderPath
0x180021f44  nop     dword ptr [rax+rax+00h]
0x180021f49  xor     esi, esi
0x180021f4b  mov     ebx, eax
0x180021f4d  test    eax, eax
0x180021f4f  jns     short loc_180021F7D
0x180021f51  mov     rcx, [rbp+1C8h]; this
0x180021f58  lea     rax, aFailedToGetUse; "Failed to get USERPROFILE path."
0x180021f5f  mov     r9d, ebx; char *
0x180021f62  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180021f67  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180021f6e  mov     edx, 3FDh; void *
0x180021f73  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180021f78  jmp     loc_1800220FB
0x180021f7d  mov     r9, rdi
0x180021f80  mov     [rsp+2C0h+var_248], rsi
0x180021f85  lea     r8, aSoftwareMicros_37; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021f8c  mov     [rbp+1C0h+var_240], rsi
0x180021f90  lea     rdx, aSS_0; "%s\\%s"
0x180021f97  mov     [rbp+1C0h+var_238], rsi
0x180021f9b  lea     rcx, [rsp+2C0h+var_248]
0x180021fa0  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180021fa5  mov     ebx, eax
0x180021fa7  test    eax, eax
0x180021fa9  jns     short loc_180021FCB
0x180021fab  mov     rcx, [rbp+1C8h]; this
0x180021fb2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180021fb9  mov     r9d, eax; char *
0x180021fbc  mov     edx, 401h; void *
0x180021fc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021fc6  jmp     loc_1800220F1
0x180021fcb  mov     r8, [rsp+2C0h+var_248]
0x180021fd0  lea     r9, aRelativepath; "RelativePath"
0x180021fd7  mov     rdi, 0FFFFFFFF80000002h
0x180021fde  mov     [rsp+2C0h+var_290], rsi
0x180021fe3  mov     rdx, rdi
0x180021fe6  mov     [rsp+2C0h+var_288], rsi
0x180021feb  lea     rcx, [rsp+2C0h+var_290]
0x180021ff0  mov     [rsp+2C0h+var_280], rsi
0x180021ff5  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180021ffa  mov     ebx, eax
0x180021ffc  test    eax, eax
0x180021ffe  jns     short loc_18002202A
0x180022000  mov     rcx, [rbp+1C8h]; this
0x180022007  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002200e  mov     r9d, eax; char *
0x180022011  mov     edx, 404h; void *
0x180022016  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002201b  lea     rcx, [rsp+2C0h+var_290]
0x180022020  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180022025  jmp     loc_1800220F1
0x18002202a  mov     r8, [rsp+2C0h+var_248]
0x18002202f  lea     r9, aSecurity; "Security"
0x180022036  mov     rdx, rdi
0x180022039  mov     [rsp+2C0h+StringSecurityDescriptor], rsi
0x18002203e  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x180022043  mov     [rsp+2C0h+var_258], rsi
0x180022048  mov     [rsp+2C0h+var_250], rsi
0x18002204d  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180022052  mov     r9, [rsp+2C0h+var_290]
0x180022057  lea     r8, [rbp+1C0h+var_230]
0x18002205b  lea     rdx, aSS_0; "%s\\%s"
0x180022062  mov     [rsp+2C0h+var_278], rsi
0x180022067  lea     rcx, [rsp+2C0h+var_278]
0x18002206c  mov     [rsp+2C0h+var_270], rsi
0x180022071  mov     [rsp+2C0h+var_268], rsi
0x180022076  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002207b  mov     ebx, eax
0x18002207d  test    eax, eax
0x18002207f  jns     short loc_1800220B5
0x180022081  mov     edx, 40Bh; void *
0x180022086  mov     rcx, [rbp+1C8h]; this
0x18002208d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180022094  mov     r9d, eax; char *
0x180022097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002209c  lea     rcx, [rsp+2C0h+var_278]
0x1800220a1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800220a6  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x1800220ab  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800220b0  jmp     loc_18002201B
0x1800220b5  mov     rdx, [rsp+2C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800220ba  mov     rcx, [rsp+2C0h+var_278]; unsigned __int16 *
0x1800220bf  call    ?EnsurePathCreated@@YAJPEBG0@Z; EnsurePathCreated(ushort const *,ushort const *)
0x1800220c4  mov     ebx, eax
0x1800220c6  test    eax, eax
0x1800220c8  jns     short loc_1800220D1
0x1800220ca  mov     edx, 40Dh
0x1800220cf  jmp     short loc_180022086
0x1800220d1  lea     rcx, [rsp+2C0h+var_278]
0x1800220d6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800220db  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x1800220e0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800220e5  lea     rcx, [rsp+2C0h+var_290]
0x1800220ea  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800220ef  mov     ebx, esi
0x1800220f1  lea     rcx, [rsp+2C0h+var_248]
0x1800220f6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800220fb  mov     eax, ebx
0x1800220fd  mov     rcx, [rbp+1C0h+var_20]
0x180022104  xor     rcx, rsp; StackCookie
0x180022107  call    __security_check_cookie
0x18002210c  mov     rbx, [rsp+2C0h+arg_10]
0x180022114  add     rsp, 2B0h
0x18002211b  pop     rdi
0x18002211c  pop     rsi
0x18002211d  pop     rbp
0x18002211e  retn
```
