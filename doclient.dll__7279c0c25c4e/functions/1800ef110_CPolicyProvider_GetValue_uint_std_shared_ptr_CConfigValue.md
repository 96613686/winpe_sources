# CPolicyProvider::GetValue(uint,std::shared_ptr<CConfigValue> &)

- ea: `0x1800ef110`
- end: `0x1800ef5c2`
- name: `?GetValue@CPolicyProvider@@UEAAJIAEAV?$shared_ptr@VCConfigValue@@@std@@@Z`
- size: `1202`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x1800179a4`
- `0x18001dea0`
- `0x1800a1ea4`
- `0x1800a98f8`
- `0x1800ec2f0`
- `0x1800ec7c4`
- `0x1800eeedc`
- `0x1800ef110`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef39f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef39f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef3b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef431`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef3b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef431`

## string_xrefs

- `0x1800ef20f`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\PolicyProvider.cpp`
- `0x1800ef270`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\PolicyProvider.cpp`
- `0x1800ef340`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\PolicyProvider.cpp`
- `0x1800ef468`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\PolicyProvider.cpp`
- `0x1800ef2e2`: `Ignoring data type %d for policy config %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPolicyProvider::GetValue(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v4; // r15
  volatile signed __int32 *v6; // rbx
  const char *v7; // rdi
  int NamedPolicy; // ebx
  const char *v9; // r9
  __int64 v10; // rcx
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rdi
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  int Value; // ebx
  __int64 v32; // rcx
  BOOL v33; // ebx
  __int64 v34; // rcx
  int v35; // [rsp+20h] [rbp-A8h]
  __int64 v36; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v37[4]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v38[4]; // [rsp+58h] [rbp-70h] BYREF
  UINT32 length; // [rsp+5Ch] [rbp-6Ch] BYREF
  int v40; // [rsp+60h] [rbp-68h] BYREF
  HSTRING string; // [rsp+68h] [rbp-60h] BYREF
  _OWORD v42[2]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = a2;
  *a3 = 0;
  v6 = (volatile signed __int32 *)a3[1];
  a3[1] = 0;
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  if ( *(_DWORD *)(a1 + 8) == 7 )
    v7 = (const char *)qword_180124FD0[10 * v4 + 1];
  else
    v7 = (const char *)qword_180124FD0[10 * v4];
  try
  {
    v36 = 0;
    NamedPolicy = GetNamedPolicy(v7, &v36);
    if ( NamedPolicy < 0 )
    {
      v10 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      return (unsigned int)NamedPolicy;
    }
    v38[0] = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v36 + 72LL))(v36, v38);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\PolicyProvider.cpp",
        (const char *)(unsigned int)v12,
        v35);
      v14 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return v13;
    }
    v40 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 64LL))(v36, &v40);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\PolicyProvider.cpp",
        (const char *)(unsigned int)v15,
        v35);
      v17 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      return v16;
    }
    v42[0] = 0;
    v42[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v42[0]) = 0;
    if ( v40 != 3 )
    {
      if ( v40 != 5 )
      {
        LogMessage(3u, "CPolicyProvider::GetValue", 0x52u, "Ignoring data type %d for policy config %s", v40, v7);
        goto LABEL_43;
      }
      string = 0;
      v18 = v36;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 128LL);
      WindowsDeleteString(0);
      string = 0;
      v20 = v19(v18, &string);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\PolicyProvider.cpp",
          (const char *)(unsigned int)v20,
          v35);
        WindowsDeleteString(string);
        string = 0;
        std::string::~string(v42);
        v22 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        return v21;
      }
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      if ( !v38[0] && !length )
      {
        WindowsDeleteString(string);
        string = 0;
        std::string::~string(v42);
        v24 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        return 2147943568LL;
      }
      v25 = WstrToUTF8(v37, StringRawBuffer, 0);
      std::string::operator=(v42, v25);
      std::string::~string(v37);
      CConfigProvider::_UpdateValue(a1, (unsigned int)v4, v42);
      WindowsDeleteString(string);
LABEL_43:
      Value = CConfigProvider::GetValue(a1, (unsigned int)v4, a3);
      if ( Value >= 0 )
      {
        v33 = v38[0] == 0;
        std::string::~string(v42);
        v34 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        return v33;
      }
      else
      {
        std::string::~string(v42);
        v32 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        return (unsigned int)Value;
      }
    }
    length = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v36 + 112LL))(v36, &length);
    v27 = v26;
    if ( v26 >= 0 )
    {
      if ( v38[0] || length )
      {
        v30 = std::to_string(v37, length);
        std::string::operator=(v42, v30);
        std::string::~string(v37);
        CConfigProvider::_UpdateValue(a1, (unsigned int)v4, v42);
        goto LABEL_43;
      }
      std::string::~string(v42);
      v29 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      result = 2147943568LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\PolicyProvider.cpp",
        (const char *)(unsigned int)v26,
        v35);
      std::string::~string(v42);
      v28 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      result = v27;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x59,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\PolicyProvider.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800ef110  mov     [rsp+arg_18], rbx
0x1800ef115  push    rsi
0x1800ef116  push    rdi
0x1800ef117  push    r12
0x1800ef119  push    r14
0x1800ef11b  push    r15
0x1800ef11d  sub     rsp, 0A0h
0x1800ef124  mov     rax, cs:__security_cookie
0x1800ef12b  xor     rax, rsp
0x1800ef12e  mov     [rsp+0C8h+var_38], rax
0x1800ef136  mov     rsi, r8
0x1800ef139  movsxd  r15, edx
0x1800ef13c  mov     r14, rcx
0x1800ef13f  xor     r12d, r12d
0x1800ef142  mov     [r8], r12
0x1800ef145  mov     rbx, [r8+8]
0x1800ef149  mov     [r8+8], r12
0x1800ef14d  test    rbx, rbx
0x1800ef150  jz      short loc_1800EF188
0x1800ef152  or      edi, 0FFFFFFFFh
0x1800ef155  mov     eax, edi
0x1800ef157  lock xadd [rbx+8], eax
0x1800ef15c  add     eax, edi
0x1800ef15e  jnz     short loc_1800EF188
0x1800ef160  mov     rax, [rbx]
0x1800ef163  mov     rcx, rbx
0x1800ef166  mov     rax, [rax]
0x1800ef169  call    _guard_dispatch_icall
0x1800ef16e  mov     eax, edi
0x1800ef170  lock xadd [rbx+0Ch], eax
0x1800ef175  add     eax, edi
0x1800ef177  jnz     short loc_1800EF188
0x1800ef179  mov     rax, [rbx]
0x1800ef17c  mov     rcx, rbx
0x1800ef17f  mov     rax, [rax+8]
0x1800ef183  call    _guard_dispatch_icall
0x1800ef188  lea     rcx, [r15+r15*4]
0x1800ef18c  add     rcx, rcx
0x1800ef18f  lea     rax, qword_180124FD0
0x1800ef196  cmp     dword ptr [r14+8], 7
0x1800ef19b  jnz     short loc_1800EF1A4
0x1800ef19d  mov     rdi, [rax+rcx*8+8]
0x1800ef1a2  jmp     short loc_1800EF1A8
0x1800ef1a4  mov     rdi, [rax+rcx*8]
0x1800ef1a8  mov     [rsp+0C8h+var_98], r12
0x1800ef1ad  lea     rdx, [rsp+0C8h+var_98]
0x1800ef1b2  mov     rcx, rdi
0x1800ef1b5  call    _GetNamedPolicy
0x1800ef1ba  mov     ebx, eax
0x1800ef1bc  test    eax, eax
0x1800ef1be  jns     short loc_1800EF1E3
0x1800ef1c0  mov     rcx, [rsp+0C8h+var_98]
0x1800ef1c5  test    rcx, rcx
0x1800ef1c8  jz      short loc_1800EF1DC
0x1800ef1ca  mov     [rsp+0C8h+var_98], r12
0x1800ef1cf  mov     rax, [rcx]
0x1800ef1d2  mov     rax, [rax+10h]
0x1800ef1d6  call    _guard_dispatch_icall
0x1800ef1db  nop
0x1800ef1dc  mov     eax, ebx
0x1800ef1de  jmp     loc_1800EF599
0x1800ef1e3  mov     [rsp+0C8h+var_70], r12b
0x1800ef1e8  mov     rcx, [rsp+0C8h+var_98]
0x1800ef1ed  mov     rax, [rcx]
0x1800ef1f0  lea     rdx, [rsp+0C8h+var_70]
0x1800ef1f5  mov     rax, [rax+48h]
0x1800ef1f9  call    _guard_dispatch_icall
0x1800ef1fe  mov     ebx, eax
0x1800ef200  test    eax, eax
0x1800ef202  jns     short loc_1800EF244
0x1800ef204  mov     rcx, [rsp+0C8h]; this
0x1800ef20c  mov     r9d, eax; char *
0x1800ef20f  lea     r8, aCW1SSrcDeliver_31; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef216  mov     edx, 33h ; '3'; void *
0x1800ef21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef220  nop
0x1800ef221  mov     rcx, [rsp+0C8h+var_98]
0x1800ef226  test    rcx, rcx
0x1800ef229  jz      short loc_1800EF23D
0x1800ef22b  mov     [rsp+0C8h+var_98], r12
0x1800ef230  mov     rax, [rcx]
0x1800ef233  mov     rax, [rax+10h]
0x1800ef237  call    _guard_dispatch_icall
0x1800ef23c  nop
0x1800ef23d  mov     eax, ebx
0x1800ef23f  jmp     loc_1800EF599
0x1800ef244  mov     [rsp+0C8h+var_68], r12d
0x1800ef249  mov     rcx, [rsp+0C8h+var_98]
0x1800ef24e  mov     rax, [rcx]
0x1800ef251  lea     rdx, [rsp+0C8h+var_68]
0x1800ef256  mov     rax, [rax+40h]
0x1800ef25a  call    _guard_dispatch_icall
0x1800ef25f  mov     ebx, eax
0x1800ef261  test    eax, eax
0x1800ef263  jns     short loc_1800EF2A5
0x1800ef265  mov     rcx, [rsp+0C8h]; this
0x1800ef26d  mov     r9d, eax; char *
0x1800ef270  lea     r8, aCW1SSrcDeliver_31; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef277  mov     edx, 36h ; '6'; void *
0x1800ef27c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef281  nop
0x1800ef282  mov     rcx, [rsp+0C8h+var_98]
0x1800ef287  test    rcx, rcx
0x1800ef28a  jz      short loc_1800EF29E
0x1800ef28c  mov     [rsp+0C8h+var_98], r12
0x1800ef291  mov     rax, [rcx]
0x1800ef294  mov     rax, [rax+10h]
0x1800ef298  call    _guard_dispatch_icall
0x1800ef29d  nop
0x1800ef29e  mov     eax, ebx
0x1800ef2a0  jmp     loc_1800EF599
0x1800ef2a5  xorps   xmm0, xmm0
0x1800ef2a8  movups  [rsp+0C8h+var_58], xmm0
0x1800ef2ad  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ef2b5  movdqu  [rsp+0C8h+var_48], xmm1
0x1800ef2be  mov     byte ptr [rsp+0C8h+var_58], r12b
0x1800ef2c3  mov     eax, [rsp+0C8h+var_68]
0x1800ef2c7  mov     ecx, 3; unsigned __int8
0x1800ef2cc  cmp     eax, ecx
0x1800ef2ce  jz      loc_1800EF43C
0x1800ef2d4  cmp     eax, 5
0x1800ef2d7  jz      short loc_1800EF2FE
0x1800ef2d9  mov     [rsp+0C8h+var_A0], rdi
0x1800ef2de  mov     [rsp+0C8h+var_A8], eax
0x1800ef2e2  lea     r9, aIgnoringDataTy; "Ignoring data type %d for policy config"...
0x1800ef2e9  lea     r8d, [rcx+4Fh]; unsigned int
0x1800ef2ed  lea     rdx, aCpolicyprovide; "CPolicyProvider::GetValue"
0x1800ef2f4  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800ef2f9  jmp     loc_1800EF519
0x1800ef2fe  mov     [rsp+0C8h+string], r12
0x1800ef303  mov     rbx, [rsp+0C8h+var_98]
0x1800ef308  mov     rax, [rbx]
0x1800ef30b  mov     rdi, [rax+80h]
0x1800ef312  xor     ecx, ecx; string
0x1800ef314  call    cs:__imp_WindowsDeleteString
0x1800ef31a  mov     [rsp+0C8h+string], r12
0x1800ef31f  lea     rdx, [rsp+0C8h+string]
0x1800ef324  mov     rcx, rbx
0x1800ef327  mov     rax, rdi
0x1800ef32a  call    _guard_dispatch_icall
0x1800ef32f  mov     ebx, eax
0x1800ef331  test    eax, eax
0x1800ef333  jns     short loc_1800EF390
0x1800ef335  mov     rcx, [rsp+0C8h]; this
0x1800ef33d  mov     r9d, eax; char *
0x1800ef340  lea     r8, aCW1SSrcDeliver_31; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef347  mov     edx, 48h ; 'H'; void *
0x1800ef34c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef351  nop
0x1800ef352  mov     rcx, [rsp+0C8h+string]; string
0x1800ef357  call    cs:__imp_WindowsDeleteString
0x1800ef35d  mov     [rsp+0C8h+string], r12
0x1800ef362  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800ef367  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef36c  nop
0x1800ef36d  mov     rcx, [rsp+0C8h+var_98]
0x1800ef372  test    rcx, rcx
0x1800ef375  jz      short loc_1800EF389
0x1800ef377  mov     [rsp+0C8h+var_98], r12
0x1800ef37c  mov     rax, [rcx]
0x1800ef37f  mov     rax, [rax+10h]
0x1800ef383  call    _guard_dispatch_icall
0x1800ef388  nop
0x1800ef389  mov     eax, ebx
0x1800ef38b  jmp     loc_1800EF599
0x1800ef390  mov     [rsp+0C8h+length], r12d
0x1800ef395  lea     rdx, [rsp+0C8h+length]; length
0x1800ef39a  mov     rcx, [rsp+0C8h+string]; string
0x1800ef39f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef3a5  cmp     [rsp+0C8h+var_70], r12b
0x1800ef3aa  jnz     short loc_1800EF3F4
0x1800ef3ac  cmp     [rsp+0C8h+length], r12d
0x1800ef3b1  jnz     short loc_1800EF3F4
0x1800ef3b3  mov     rcx, [rsp+0C8h+string]; string
0x1800ef3b8  call    cs:__imp_WindowsDeleteString
0x1800ef3be  mov     [rsp+0C8h+string], r12
0x1800ef3c3  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800ef3c8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef3cd  nop
0x1800ef3ce  mov     rcx, [rsp+0C8h+var_98]
0x1800ef3d3  test    rcx, rcx
0x1800ef3d6  jz      short loc_1800EF3EA
0x1800ef3d8  mov     [rsp+0C8h+var_98], r12
0x1800ef3dd  mov     rax, [rcx]
0x1800ef3e0  mov     rax, [rax+10h]
0x1800ef3e4  call    _guard_dispatch_icall
0x1800ef3e9  nop
0x1800ef3ea  mov     eax, 80070490h
0x1800ef3ef  jmp     loc_1800EF599
0x1800ef3f4  xor     r8d, r8d
0x1800ef3f7  mov     rdx, rax
0x1800ef3fa  lea     rcx, [rsp+0C8h+var_90]
0x1800ef3ff  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x1800ef404  mov     rdx, rax
0x1800ef407  lea     rcx, [rsp+0C8h+var_58]
0x1800ef40c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800ef411  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800ef416  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef41b  lea     r8, [rsp+0C8h+var_58]
0x1800ef420  mov     edx, r15d
0x1800ef423  mov     rcx, r14
0x1800ef426  call    ?_UpdateValue@CConfigProvider@@IEAAXIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CConfigProvider::_UpdateValue(uint,std::string const &)
0x1800ef42b  nop
0x1800ef42c  mov     rcx, [rsp+0C8h+string]; string
0x1800ef431  call    cs:__imp_WindowsDeleteString
0x1800ef437  jmp     loc_1800EF519
0x1800ef43c  mov     [rsp+0C8h+length], r12d
0x1800ef441  mov     rcx, [rsp+0C8h+var_98]
0x1800ef446  mov     rax, [rcx]
0x1800ef449  lea     rdx, [rsp+0C8h+length]
0x1800ef44e  mov     rax, [rax+70h]
0x1800ef452  call    _guard_dispatch_icall
0x1800ef457  mov     ebx, eax
0x1800ef459  test    eax, eax
0x1800ef45b  jns     short loc_1800EF4A8
0x1800ef45d  mov     rcx, [rsp+0C8h]; this
0x1800ef465  mov     r9d, eax; char *
0x1800ef468  lea     r8, aCW1SSrcDeliver_31; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ef46f  mov     edx, 3Eh ; '>'; void *
0x1800ef474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef479  nop
0x1800ef47a  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800ef47f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef484  nop
0x1800ef485  mov     rcx, [rsp+0C8h+var_98]
0x1800ef48a  test    rcx, rcx
0x1800ef48d  jz      short loc_1800EF4A1
0x1800ef48f  mov     [rsp+0C8h+var_98], r12
0x1800ef494  mov     rax, [rcx]
0x1800ef497  mov     rax, [rax+10h]
0x1800ef49b  call    _guard_dispatch_icall
0x1800ef4a0  nop
0x1800ef4a1  mov     eax, ebx
0x1800ef4a3  jmp     loc_1800EF599
0x1800ef4a8  mov     edx, [rsp+0C8h+length]
0x1800ef4ac  cmp     [rsp+0C8h+var_70], r12b
0x1800ef4b1  jnz     short loc_1800EF4E8
0x1800ef4b3  test    edx, edx
0x1800ef4b5  jnz     short loc_1800EF4E8
0x1800ef4b7  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800ef4bc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef4c1  nop
0x1800ef4c2  mov     rcx, [rsp+0C8h+var_98]
0x1800ef4c7  test    rcx, rcx
0x1800ef4ca  jz      short loc_1800EF4DE
0x1800ef4cc  mov     [rsp+0C8h+var_98], r12
0x1800ef4d1  mov     rax, [rcx]
0x1800ef4d4  mov     rax, [rax+10h]
0x1800ef4d8  call    _guard_dispatch_icall
0x1800ef4dd  nop
0x1800ef4de  mov     eax, 80070490h
0x1800ef4e3  jmp     loc_1800EF599
0x1800ef4e8  lea     rcx, [rsp+0C8h+var_90]
0x1800ef4ed  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x1800ef4f2  mov     rdx, rax
0x1800ef4f5  lea     rcx, [rsp+0C8h+var_58]
0x1800ef4fa  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800ef4ff  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800ef504  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef509  lea     r8, [rsp+0C8h+var_58]
0x1800ef50e  mov     edx, r15d
0x1800ef511  mov     rcx, r14
0x1800ef514  call    ?_UpdateValue@CConfigProvider@@IEAAXIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CConfigProvider::_UpdateValue(uint,std::string const &)
0x1800ef519  mov     r8, rsi
0x1800ef51c  mov     edx, r15d
0x1800ef51f  mov     rcx, r14
0x1800ef522  call    ?GetValue@CConfigProvider@@UEAAJIAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigProvider::GetValue(uint,std::shared_ptr<CConfigValue> &)
0x1800ef527  mov     ebx, eax
0x1800ef529  test    eax, eax
0x1800ef52b  jns     short loc_1800EF558
0x1800ef52d  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800ef532  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef537  nop
0x1800ef538  mov     rcx, [rsp+0C8h+var_98]
0x1800ef53d  test    rcx, rcx
0x1800ef540  jz      short loc_1800EF554
0x1800ef542  mov     [rsp+0C8h+var_98], r12
0x1800ef547  mov     rax, [rcx]
0x1800ef54a  mov     rax, [rax+10h]
0x1800ef54e  call    _guard_dispatch_icall
0x1800ef553  nop
0x1800ef554  mov     eax, ebx
0x1800ef556  jmp     short loc_1800EF599
0x1800ef558  mov     ebx, r12d
0x1800ef55b  cmp     [rsp+0C8h+var_70], r12b
0x1800ef560  setz    bl
0x1800ef563  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800ef568  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ef56d  nop
0x1800ef56e  mov     rcx, [rsp+0C8h+var_98]
0x1800ef573  test    rcx, rcx
0x1800ef576  jz      short loc_1800EF58A
0x1800ef578  mov     [rsp+0C8h+var_98], r12
0x1800ef57d  mov     rdx, [rcx]
0x1800ef580  mov     rax, [rdx+10h]
0x1800ef584  call    _guard_dispatch_icall
0x1800ef589  nop
0x1800ef58a  mov     eax, ebx
0x1800ef58c  jmp     short loc_1800EF599
0x1800ef58e  mov     eax, 8007000Eh
  ... truncated ...
```
