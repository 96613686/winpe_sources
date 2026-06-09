# CHost::GetEngineFromName(ushort const *)

- ea: `0x140001950`
- end: `0x140001bca`
- name: `?GetEngineFromName@CHost@@IEAAJPEBG@Z`
- size: `634`
- prototype: `__int64 __fastcall(CHost *__hidden this, LPCOLESTR lpsz)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400014b0`

## callees

- `0x140001950`
- `0x140005760`
- `0x140008530`
- `0x1400098d4`
- `0x14000f464`
- `0x140016176`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x140001a32`
- `msvcrt!wcscat_s` at `0x140001a32`
- `ole32!CLSIDFromString` at `0x140001aa0`
- `ole32!CLSIDFromString` at `0x140001aa0`
- `ADVAPI32!RegCloseKey` at `0x140001a10`
- `ADVAPI32!RegCloseKey` at `0x140001a7d`
- `ADVAPI32!RegCloseKey` at `0x140001a10`
- `ADVAPI32!RegCloseKey` at `0x140001a7d`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x140001b13`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x140001b13`

## pseudocode

```c
__int64 __fastcall CHost::GetEngineFromName(CHost *this, unsigned __int16 *lpsz)
{
  unsigned __int16 *v2; // rbx
  const WCHAR *v4; // rcx
  WCHAR v5; // dx
  const WCHAR *v6; // r10
  bool v7; // zf
  const WCHAR *v8; // rax
  const unsigned __int16 *v9; // rdx
  int RegSettingsString; // ebx
  const unsigned __int16 *v11; // rdx
  int IsFeatureEnabledInternal; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  const OLECHAR *v16; // [rsp+20h] [rbp-A68h]
  HKEY hKey; // [rsp+30h] [rbp-A58h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-A50h] BYREF
  unsigned __int16 v19[256]; // [rsp+50h] [rbp-A38h] BYREF
  wchar_t Destination[1040]; // [rsp+250h] [rbp-838h] BYREF

  v2 = lpsz;
  if ( lpsz )
    goto LABEL_14;
  v4 = (const WCHAR *)*((_QWORD *)this + 77);
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 )
    {
      v6 = 0;
      do
      {
        v7 = v5 == 46;
        v8 = v4;
        v5 = v4[1];
        if ( !v7 )
          v8 = v6;
        ++v4;
        v6 = v8;
      }
      while ( v5 );
      if ( v8 )
      {
        hKey = 0;
        RegSettingsString = OpenRegSettings(HKEY_CLASSES_ROOT, v8, 0x20019u, &hKey);
        if ( RegSettingsString < 0 )
          return (unsigned int)RegSettingsString;
        RegSettingsString = GetRegSettingsString(hKey, v9, Destination, 0x400u);
        RegCloseKey(hKey);
        if ( RegSettingsString < 0 )
          return (unsigned int)RegSettingsString;
        wcscat_s(Destination, 0x40Eu, L"\\ScriptEngine");
        RegSettingsString = OpenRegSettings(HKEY_CLASSES_ROOT, Destination, 0x20019u, &hKey);
        if ( RegSettingsString < 0 )
          return (unsigned int)RegSettingsString;
        RegSettingsString = GetRegSettingsString(hKey, v11, v19, 0x100u);
        RegCloseKey(hKey);
        if ( RegSettingsString < 0 )
          return (unsigned int)RegSettingsString;
        v2 = v19;
LABEL_14:
        pclsid = 0;
        if ( CLSIDFromString(v2, &pclsid) < 0 )
          goto LABEL_23;
        if ( !memcmp_0(&pclsid, &CLSID_Chakra, 0x10u) )
          return (*(__int64 (__fastcall **)(CHost *, _QWORD, __int64, const OLECHAR *, const OLECHAR *))(*(_QWORD *)this + 8LL))(
                   this,
                   (unsigned int)(Global::g_lResourceBase + 20),
                   3216,
                   &Default,
                   &Default);
        if ( memcmp_0(&pclsid, &CLSID_VBScript, 0x10u) )
          goto LABEL_23;
        if ( FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST )
        {
          IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
          if ( IsFeatureEnabledInternal < 0 )
          {
LABEL_23:
            if ( (int)CScriptingEngine::Create(v2, this, (struct CScriptingEngine **)this + 79) >= 0 )
              return 0;
            v14 = 3201;
            v15 = (unsigned int)(Global::g_lResourceBase + 20);
            v16 = v2;
            return (*(__int64 (__fastcall **)(CHost *, __int64, __int64, _QWORD, const OLECHAR *))(*(_QWORD *)this + 8LL))(
                     this,
                     v15,
                     v14,
                     *((_QWORD *)this + 76),
                     v16);
          }
          dword_14001E1F8 = IsFeatureEnabledInternal == 0;
          FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST = 0;
        }
        if ( dword_14001E1F8 )
          SendVBScriptToastNotification();
        goto LABEL_23;
      }
    }
  }
  v16 = &Default;
  v15 = (unsigned int)(Global::g_lResourceBase + 21);
  v14 = 3306;
  return (*(__int64 (__fastcall **)(CHost *, __int64, __int64, _QWORD, const OLECHAR *))(*(_QWORD *)this + 8LL))(
           this,
           v15,
           v14,
           *((_QWORD *)this + 76),
           v16);
}

```

## disassembly

```asm
0x140001950  mov     [rsp+arg_10], rbx
0x140001955  push    rdi
0x140001956  sub     rsp, 0A80h
0x14000195d  mov     rax, cs:__security_cookie
0x140001964  xor     rax, rsp
0x140001967  mov     [rsp+0A88h+var_18], rax
0x14000196f  mov     rbx, rdx
0x140001972  mov     rdi, rcx
0x140001975  test    rdx, rdx
0x140001978  jnz     loc_140001A90
0x14000197e  mov     rcx, [rcx+268h]
0x140001985  test    rcx, rcx
0x140001988  jz      loc_140001B78
0x14000198e  movzx   edx, word ptr [rcx]
0x140001991  test    dx, dx
0x140001994  jz      loc_140001B78
0x14000199a  xor     r10d, r10d
0x14000199d  nop     dword ptr [rax]
0x1400019a0  cmp     dx, 2Eh ; '.'
0x1400019a4  mov     rax, rcx
0x1400019a7  movzx   edx, word ptr [rcx+2]
0x1400019ab  cmovnz  rax, r10
0x1400019af  add     rcx, 2
0x1400019b3  mov     r10, rax
0x1400019b6  test    dx, dx
0x1400019b9  jnz     short loc_1400019A0
0x1400019bb  test    rax, rax
0x1400019be  jz      loc_140001B78
0x1400019c4  lea     r9, [rsp+0A88h+hKey]; phkResult
0x1400019c9  mov     [rsp+0A88h+hKey], 0
0x1400019d2  mov     r8d, 20019h; samDesired
0x1400019d8  mov     rdx, rax; lpWideCharStr
0x1400019db  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1400019e2  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x1400019e7  mov     ebx, eax
0x1400019e9  test    eax, eax
0x1400019eb  js      loc_140001B74
0x1400019f1  mov     rcx, [rsp+0A88h+hKey]; hKey
0x1400019f6  lea     r8, [rsp+0A88h+Destination]; unsigned __int16 *
0x1400019fe  mov     r9d, 400h; unsigned int
0x140001a04  call    ?GetRegSettingsString@@YAJPEAUHKEY__@@PEBGPEAGK@Z; GetRegSettingsString(HKEY__ *,ushort const *,ushort *,ulong)
0x140001a09  mov     rcx, [rsp+0A88h+hKey]; hKey
0x140001a0e  mov     ebx, eax
0x140001a10  call    cs:__imp_RegCloseKey
0x140001a16  test    ebx, ebx
0x140001a18  js      loc_140001B74
0x140001a1e  lea     r8, aScriptengine; "\\ScriptEngine"
0x140001a25  mov     edx, 40Eh; SizeInWords
0x140001a2a  lea     rcx, [rsp+0A88h+Destination]; Destination
0x140001a32  call    cs:__imp_wcscat_s
0x140001a38  lea     r9, [rsp+0A88h+hKey]; phkResult
0x140001a3d  mov     r8d, 20019h; samDesired
0x140001a43  lea     rdx, [rsp+0A88h+Destination]; lpWideCharStr
0x140001a4b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140001a52  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140001a57  mov     ebx, eax
0x140001a59  test    eax, eax
0x140001a5b  js      loc_140001B74
0x140001a61  mov     rcx, [rsp+0A88h+hKey]; hKey
0x140001a66  lea     r8, [rsp+0A88h+var_A38]; unsigned __int16 *
0x140001a6b  mov     r9d, 100h; unsigned int
0x140001a71  call    ?GetRegSettingsString@@YAJPEAUHKEY__@@PEBGPEAGK@Z; GetRegSettingsString(HKEY__ *,ushort const *,ushort *,ulong)
0x140001a76  mov     rcx, [rsp+0A88h+hKey]; hKey
0x140001a7b  mov     ebx, eax
0x140001a7d  call    cs:__imp_RegCloseKey
0x140001a83  test    ebx, ebx
0x140001a85  js      loc_140001B74
0x140001a8b  lea     rbx, [rsp+0A88h+var_A38]
0x140001a90  xorps   xmm0, xmm0
0x140001a93  lea     rdx, [rsp+0A88h+pclsid]; pclsid
0x140001a98  mov     rcx, rbx; lpsz
0x140001a9b  movups  xmmword ptr [rsp+0A88h+pclsid.Data1], xmm0
0x140001aa0  call    cs:__imp_CLSIDFromString
0x140001aa6  test    eax, eax
0x140001aa8  js      loc_140001B44
0x140001aae  mov     r8d, 10h; Size
0x140001ab4  lea     rdx, CLSID_Chakra; Buf2
0x140001abb  lea     rcx, [rsp+0A88h+pclsid]; Buf1
0x140001ac0  call    memcmp_0
0x140001ac5  test    eax, eax
0x140001ac7  jnz     short loc_140001AEC
0x140001ac9  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140001acf  lea     r8, Default
0x140001ad6  mov     [rsp+0A88h+var_A68], r8
0x140001adb  mov     r9, r8
0x140001ade  mov     r8d, 0C90h
0x140001ae4  add     edx, 14h
0x140001ae7  jmp     loc_140001B9A
0x140001aec  mov     r8d, 10h; Size
0x140001af2  lea     rdx, CLSID_VBScript; Buf2
0x140001af9  lea     rcx, [rsp+0A88h+pclsid]; Buf1
0x140001afe  call    memcmp_0
0x140001b03  test    eax, eax
0x140001b05  jnz     short loc_140001B44
0x140001b07  mov     rcx, cs:?FEATURE_VBSCRIPT_DEPRECATION_TOAST@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST
0x140001b0e  test    rcx, rcx
0x140001b11  jz      short loc_140001B35
0x140001b13  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x140001b19  test    eax, eax
0x140001b1b  js      short loc_140001B44
0x140001b1d  xor     ecx, ecx
0x140001b1f  test    eax, eax
0x140001b21  setz    cl
0x140001b24  mov     cs:dword_14001E1F8, ecx
0x140001b2a  mov     cs:?FEATURE_VBSCRIPT_DEPRECATION_TOAST@FCK@@3VCFeatureControlKey@@A, 0; CFeatureControlKey FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST
0x140001b35  mov     eax, cs:dword_14001E1F8
0x140001b3b  test    eax, eax
0x140001b3d  jz      short loc_140001B44
0x140001b3f  call    SendVBScriptToastNotification
0x140001b44  lea     r8, [rdi+278h]; struct CScriptingEngine **
0x140001b4b  mov     rdx, rdi; struct CHost *
0x140001b4e  mov     rcx, rbx; lpsz
0x140001b51  call    ?Create@CScriptingEngine@@SAJPEBGPEAVCHost@@PEAPEAV1@@Z; CScriptingEngine::Create(ushort const *,CHost *,CScriptingEngine * *)
0x140001b56  test    eax, eax
0x140001b58  jns     short loc_140001B70
0x140001b5a  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140001b60  mov     r8d, 0C81h
0x140001b66  add     edx, 14h
0x140001b69  mov     [rsp+0A88h+var_A68], rbx
0x140001b6e  jmp     short loc_140001B93
0x140001b70  xor     eax, eax
0x140001b72  jmp     short loc_140001BA9
0x140001b74  mov     eax, ebx
0x140001b76  jmp     short loc_140001BA9
0x140001b78  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140001b7e  lea     r8, Default
0x140001b85  mov     [rsp+0A88h+var_A68], r8
0x140001b8a  add     edx, 15h
0x140001b8d  mov     r8d, 0CEAh
0x140001b93  mov     r9, [rdi+260h]
0x140001b9a  mov     rax, [rdi]
0x140001b9d  mov     rcx, rdi
0x140001ba0  mov     rax, [rax+8]
0x140001ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ba9  mov     rcx, [rsp+0A88h+var_18]
0x140001bb1  xor     rcx, rsp; StackCookie
0x140001bb4  call    __security_check_cookie
0x140001bb9  mov     rbx, [rsp+0A88h+arg_10]
0x140001bc1  add     rsp, 0A80h
0x140001bc8  pop     rdi
0x140001bc9  retn
```
