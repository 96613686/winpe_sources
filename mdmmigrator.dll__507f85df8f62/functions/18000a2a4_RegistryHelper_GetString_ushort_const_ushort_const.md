# RegistryHelper::GetString(ushort const *,ushort const *)

- ea: `0x18000a2a4`
- end: `0x18000a682`
- name: `?GetString@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z`
- size: `990`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180008520`

## callees

- `0x18000138c`
- `0x18000139c`
- `0x1800013c8`
- `0x180001628`
- `0x1800022e0`
- `0x180002cbc`
- `0x1800034ac`
- `0x180004224`
- `0x180007b38`
- `0x18000970c`
- `0x180009e34`
- `0x180009ed0`
- `0x18000a2a4`
- `0x18000a888`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a2ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a497`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a2ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a497`

## string_xrefs

- `0x18000a546`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a5aa`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a609`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a66d`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a55d`: `RegistryHelper::GetString`
- `0x18000a620`: `RegistryHelper::GetString`

## pseudocode

```c
_QWORD *__fastcall RegistryHelper::GetString(_QWORD *a1, const WCHAR *a2, const WCHAR *a3)
{
  const WCHAR *v3; // r14
  const WCHAR *v4; // r15
  LSTATUS ValueW; // eax
  unsigned int v7; // ebx
  int v8; // ecx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // eax
  size_t v12; // rsi
  _QWORD *v13; // rax
  void *v14; // rax
  void *v15; // rcx
  char *v16; // rbx
  LSTATUS v17; // eax
  unsigned int v18; // ebx
  _WORD *v19; // rdx
  unsigned __int64 v20; // r8
  const unsigned __int16 **v22; // rax
  const unsigned __int16 **v23; // r8
  const unsigned __int16 **v24; // r9
  unsigned int v25; // eax
  const unsigned __int16 **v26; // rax
  const unsigned __int16 **v27; // r8
  const unsigned __int16 **v28; // r9
  unsigned int v29; // eax
  int pdwType; // [rsp+20h] [rbp-B9h]
  int pdwTypea; // [rsp+20h] [rbp-B9h]
  DWORD pcbData; // [rsp+50h] [rbp-89h] BYREF
  int v33; // [rsp+54h] [rbp-85h] BYREF
  _QWORD *v34; // [rsp+58h] [rbp-81h] BYREF
  PVOID pvData[2]; // [rsp+60h] [rbp-79h] BYREF
  char *v36; // [rsp+70h] [rbp-69h]
  _BYTE v37[8]; // [rsp+80h] [rbp-59h] BYREF
  _BYTE v38[8]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v39[16]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v40[32]; // [rsp+A0h] [rbp-39h] BYREF
  const char *v41; // [rsp+C0h] [rbp-19h]
  __int64 v42; // [rsp+C8h] [rbp-11h]
  const WCHAR *v43; // [rsp+D0h] [rbp-9h]
  int v44; // [rsp+D8h] [rbp-1h]
  int v45; // [rsp+DCh] [rbp+3h]
  const WCHAR *v46; // [rsp+E0h] [rbp+7h]
  int v47; // [rsp+E8h] [rbp+Fh]
  int v48; // [rsp+ECh] [rbp+13h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v3 = a3;
  v4 = a2;
  v34 = a1;
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 6u, 0, 0, &pcbData);
  v7 = ValueW;
  v8 = 2;
  if ( ValueW == 2 )
  {
    if ( (unsigned int)dword_18002B0C0 > 5 )
    {
      v9 = -1;
      if ( v3 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v3[v10] );
        v11 = 2 * v10 + 2;
      }
      else
      {
        v3 = &dword_18002237C;
        v11 = 2;
      }
      v46 = v3;
      v47 = v11;
      v48 = 0;
      if ( v4 )
      {
        do
          ++v9;
        while ( v4[v9] );
        v8 = 2 * v9 + 2;
      }
      else
      {
        v4 = &dword_18002237C;
      }
      v43 = v4;
      v44 = v8;
      v45 = 0;
      v41 = "Did not find the source string value.";
      v42 = 38;
      tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, byte_1800255E5, 0, 0, 5, v40);
    }
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 7;
    *(_WORD *)a1 = 0;
  }
  else
  {
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v7 = (unsigned __int16)ValueW | 0x80070000;
      if ( (unsigned int)dword_18002B0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002B0C0, 0x400000000000LL) )
      {
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v37, "RegGetValue failed to get string buffer length.");
        v33 = v7;
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
          v38,
          "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp");
        LODWORD(v34) = 74;
        v26 = (const unsigned __int16 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
                                           v39,
                                           L"RegistryHelper::GetString");
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)&v34,
          (__int64)&unk_180025570,
          (__int64)v27,
          (__int64)v28,
          v26,
          (__int64)&v34,
          v27,
          (__int64)&v33,
          v28);
      }
      v29 = wil::verify_hresult<long>(v7);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp",
        (const char *)v29,
        pdwType);
    }
    *(_OWORD *)pvData = 0;
    v36 = 0;
    if ( pcbData >= 2uLL )
    {
      v12 = pcbData & 0xFFFFFFFE;
      if ( (pcbData & 0xFFFFFFFE) != 0 )
      {
        if ( v12 < 0x1000 )
        {
          v13 = operator new(v12);
        }
        else
        {
          if ( v12 + 39 < v12 )
            __scrt_throw_std_bad_array_new_length();
          v14 = operator new(v12 + 39);
          v15 = v14;
          if ( !v14 )
            __fastfail(5u);
          v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v13 - 1) = v15;
        }
      }
      else
      {
        v13 = 0;
      }
      pvData[0] = v13;
      v16 = (char *)v13 + v12;
      v36 = (char *)v13 + v12;
      memset_0(v13, 0, v12);
      pvData[1] = v16;
      v34 = 0;
      std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&v34);
    }
    v17 = RegGetValueW(HKEY_LOCAL_MACHINE, v4, v3, 6u, 0, pvData[0], &pcbData);
    v18 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)dword_18002B0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002B0C0, 0x400000000000LL) )
      {
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v39, "RegGetValue failed to get string.");
        LODWORD(v34) = v18;
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
          v38,
          "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp");
        v33 = 81;
        v22 = (const unsigned __int16 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
                                           v37,
                                           L"RegistryHelper::GetString");
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)&v33,
          (__int64)byte_180025509,
          (__int64)v23,
          (__int64)v24,
          v22,
          (__int64)&v33,
          v23,
          (__int64)&v34,
          v24);
      }
      v25 = wil::verify_hresult<long>(v18);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp",
        (const char *)v25,
        pdwTypea);
    }
    v19 = pvData[0];
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    std::wstring::_Construct<1,unsigned short const *>(a1, v19, v20);
    std::vector<unsigned short>::~vector<unsigned short>(pvData);
  }
  return a1;
}

```

## disassembly

```asm
0x18000a2a4  push    rbp
0x18000a2a6  push    rbx
0x18000a2a7  push    rsi
0x18000a2a8  push    rdi
0x18000a2a9  push    r12
0x18000a2ab  push    r14
0x18000a2ad  push    r15
0x18000a2af  lea     rbp, [rsp-27h]
0x18000a2b4  sub     rsp, 100h
0x18000a2bb  mov     rax, cs:__security_cookie
0x18000a2c2  xor     rax, rsp
0x18000a2c5  mov     [rbp+57h+var_40], rax
0x18000a2c9  mov     r14, r8
0x18000a2cc  mov     r15, rdx
0x18000a2cf  mov     rdi, rcx
0x18000a2d2  mov     [rsp+130h+var_D8], rcx
0x18000a2d7  xor     r12d, r12d
0x18000a2da  mov     [rsp+130h+var_E0], r12d
0x18000a2df  lea     rax, [rsp+130h+var_E0]
0x18000a2e4  mov     [rsp+130h+pcbData], rax; pcbData
0x18000a2e9  mov     [rsp+130h+pvData], r12; pvData
0x18000a2ee  mov     [rsp+130h+pdwType], r12; pdwType
0x18000a2f3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a2fa  lea     r9d, [r12+6]; dwFlags
0x18000a2ff  call    cs:__imp_RegGetValueW
0x18000a305  mov     ebx, eax
0x18000a307  lea     ecx, [r12+2]
0x18000a30c  cmp     eax, ecx
0x18000a30e  jnz     loc_18000A3D9
0x18000a314  mov     eax, cs:dword_18002B0C0
0x18000a31a  cmp     eax, 5
0x18000a31d  jbe     loc_18000A3BE
0x18000a323  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a327  test    r14, r14
0x18000a32a  jz      short loc_18000A342
0x18000a32c  mov     rax, r8
0x18000a32f  inc     rax
0x18000a332  cmp     [r14+rax*2], r12w
0x18000a337  jnz     short loc_18000A32F
0x18000a339  lea     eax, ds:2[rax*2]
0x18000a340  jmp     short loc_18000A34B
0x18000a342  lea     r14, dword_18002237C
0x18000a349  mov     eax, ecx
0x18000a34b  mov     [rbp+57h+var_50], r14
0x18000a34f  mov     [rbp+57h+var_48], eax
0x18000a352  mov     [rbp+57h+var_44], r12d
0x18000a356  test    r15, r15
0x18000a359  jz      short loc_18000A36F
0x18000a35b  inc     r8
0x18000a35e  cmp     [r15+r8*2], r12w
0x18000a363  jnz     short loc_18000A35B
0x18000a365  lea     ecx, ds:2[r8*2]
0x18000a36d  jmp     short loc_18000A376
0x18000a36f  lea     r15, dword_18002237C
0x18000a376  mov     [rbp+57h+var_60], r15
0x18000a37a  mov     [rbp+57h+var_58], ecx
0x18000a37d  mov     [rbp+57h+var_54], r12d
0x18000a381  lea     rax, aDidNotFindTheS; "Did not find the source string value."
0x18000a388  mov     [rbp+57h+var_70], rax
0x18000a38c  mov     [rbp+57h+var_68], 26h ; '&'
0x18000a394  lea     rax, [rbp+57h+var_90]
0x18000a398  mov     [rsp+130h+pvData], rax
0x18000a39d  mov     dword ptr [rsp+130h+pdwType], 5
0x18000a3a5  xor     r9d, r9d
0x18000a3a8  xor     r8d, r8d
0x18000a3ab  lea     rdx, byte_1800255E5
0x18000a3b2  lea     rcx, dword_18002B0C0
0x18000a3b9  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a3be  xorps   xmm0, xmm0
0x18000a3c1  movups  xmmword ptr [rdi], xmm0
0x18000a3c4  mov     [rdi+10h], r12
0x18000a3c8  mov     qword ptr [rdi+18h], 7
0x18000a3d0  mov     [rdi], r12w
0x18000a3d4  jmp     loc_18000A4D5
0x18000a3d9  test    eax, eax
0x18000a3db  jnz     loc_18000A5B9
0x18000a3e1  mov     esi, [rsp+130h+var_E0]
0x18000a3e5  xorps   xmm0, xmm0
0x18000a3e8  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18000a3ed  mov     [rbp+57h+var_C0], r12
0x18000a3f1  cmp     rsi, rcx
0x18000a3f4  jb      short loc_18000A46C
0x18000a3f6  and     rsi, 0FFFFFFFFFFFFFFFEh
0x18000a3fa  jnz     short loc_18000A401
0x18000a3fc  mov     rax, r12
0x18000a3ff  jmp     short loc_18000A43F
0x18000a401  cmp     rsi, 1000h
0x18000a408  jb      short loc_18000A437
0x18000a40a  lea     rcx, [rsi+27h]; Size
0x18000a40e  cmp     rcx, rsi
0x18000a411  jbe     loc_18000A67C
0x18000a417  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a41c  mov     rcx, rax
0x18000a41f  test    rax, rax
0x18000a422  jnz     short loc_18000A429
0x18000a424  lea     ecx, [rax+5]
0x18000a427  int     29h; Win8: RtlFailFast(ecx)
0x18000a429  add     rax, 27h ; '''
0x18000a42d  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000a431  mov     [rax-8], rcx
0x18000a435  jmp     short loc_18000A43F
0x18000a437  mov     rcx, rsi; Size
0x18000a43a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a43f  mov     [rbp+57h+var_D0], rax
0x18000a443  lea     rbx, [rsi+rax]
0x18000a447  mov     [rbp+57h+var_C0], rbx
0x18000a44b  mov     r8, rsi; Size
0x18000a44e  xor     edx, edx; Val
0x18000a450  mov     rcx, rax; void *
0x18000a453  call    memset_0
0x18000a458  mov     [rbp+57h+var_D0+8], rbx
0x18000a45c  mov     [rsp+130h+var_D8], r12
0x18000a461  lea     rcx, [rsp+130h+var_D8]
0x18000a466  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x18000a46b  nop
0x18000a46c  lea     rax, [rsp+130h+var_E0]
0x18000a471  mov     [rsp+130h+pcbData], rax; pcbData
0x18000a476  mov     rax, [rbp+57h+var_D0]
0x18000a47a  mov     [rsp+130h+pvData], rax; pvData
0x18000a47f  mov     [rsp+130h+pdwType], r12; pdwType
0x18000a484  mov     r9d, 6; dwFlags
0x18000a48a  mov     r8, r14; lpValue
0x18000a48d  mov     rdx, r15; lpSubKey
0x18000a490  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a497  call    cs:__imp_RegGetValueW
0x18000a49d  mov     ebx, eax
0x18000a49f  test    eax, eax
0x18000a4a1  jnz     short loc_18000A4F6
0x18000a4a3  mov     rdx, [rbp+57h+var_D0]
0x18000a4a7  xorps   xmm0, xmm0
0x18000a4aa  movups  xmmword ptr [rdi], xmm0
0x18000a4ad  mov     [rdi+10h], r12
0x18000a4b1  mov     [rdi+18h], r12
0x18000a4b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a4b9  inc     r8
0x18000a4bc  cmp     [rdx+r8*2], r12w
0x18000a4c1  jnz     short loc_18000A4B9
0x18000a4c3  mov     rcx, rdi
0x18000a4c6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000a4cb  nop
0x18000a4cc  lea     rcx, [rbp+57h+var_D0]
0x18000a4d0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18000a4d5  mov     rax, rdi
0x18000a4d8  mov     rcx, [rbp+57h+var_40]
0x18000a4dc  xor     rcx, rsp; StackCookie
0x18000a4df  call    __security_check_cookie
0x18000a4e4  add     rsp, 100h
0x18000a4eb  pop     r15
0x18000a4ed  pop     r14
0x18000a4ef  pop     r12
0x18000a4f1  pop     rdi
0x18000a4f2  pop     rsi
0x18000a4f3  pop     rbx
0x18000a4f4  pop     rbp
0x18000a4f5  retn
0x18000a4f6  jle     short loc_18000A501
0x18000a4f8  movzx   ebx, ax
0x18000a4fb  or      ebx, 80070000h
0x18000a501  mov     eax, cs:dword_18002B0C0
0x18000a507  mov     edi, 51h ; 'Q'
0x18000a50c  cmp     eax, 5
0x18000a50f  jbe     loc_18000A59C
0x18000a515  mov     rdx, 400000000000h
0x18000a51f  lea     rcx, dword_18002B0C0
0x18000a526  call    _tlgKeywordOn
0x18000a52b  test    al, al
0x18000a52d  jz      short loc_18000A59C
0x18000a52f  lea     rdx, aReggetvalueFai; "RegGetValue failed to get string."
0x18000a536  lea     rcx, [rbp+57h+var_A0]
0x18000a53a  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a53f  mov     r9, rax
0x18000a542  mov     dword ptr [rsp+130h+var_D8], ebx
0x18000a546  lea     rdx, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a54d  lea     rcx, [rbp+57h+var_A8]
0x18000a551  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a556  mov     r8, rax
0x18000a559  mov     [rsp+130h+var_DC], edi
0x18000a55d  lea     rdx, aRegistryhelper_0; "RegistryHelper::GetString"
0x18000a564  lea     rcx, [rbp+57h+var_B0]
0x18000a568  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a56d  mov     [rsp+130h+var_F0], r9
0x18000a572  lea     rcx, [rsp+130h+var_D8]
0x18000a577  mov     [rsp+130h+var_F8], rcx
0x18000a57c  mov     [rsp+130h+pcbData], r8
0x18000a581  lea     rcx, [rsp+130h+var_DC]
0x18000a586  mov     [rsp+130h+pvData], rcx
0x18000a58b  mov     [rsp+130h+pdwType], rax; int
0x18000a590  lea     rdx, byte_180025509
0x18000a597  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000a59c  mov     ecx, ebx
0x18000a59e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000a5a3  mov     r9d, eax; char *
0x18000a5a6  mov     rcx, [rbp+5Fh]; this
0x18000a5aa  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a5b1  mov     edx, edi; void *
0x18000a5b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a5b9  jle     short loc_18000A5C4
0x18000a5bb  movzx   ebx, ax
0x18000a5be  or      ebx, 80070000h
0x18000a5c4  mov     eax, cs:dword_18002B0C0
0x18000a5ca  mov     edi, 4Ah ; 'J'
0x18000a5cf  cmp     eax, 5
0x18000a5d2  jbe     loc_18000A65F
0x18000a5d8  mov     rdx, 400000000000h
0x18000a5e2  lea     rcx, dword_18002B0C0
0x18000a5e9  call    _tlgKeywordOn
0x18000a5ee  test    al, al
0x18000a5f0  jz      short loc_18000A65F
0x18000a5f2  lea     rdx, aReggetvalueFai_0; "RegGetValue failed to get string buffer"...
0x18000a5f9  lea     rcx, [rbp+57h+var_B0]
0x18000a5fd  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a602  mov     r9, rax
0x18000a605  mov     [rsp+130h+var_DC], ebx
0x18000a609  lea     rdx, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a610  lea     rcx, [rbp+57h+var_A8]
0x18000a614  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a619  mov     r8, rax
0x18000a61c  mov     dword ptr [rsp+130h+var_D8], edi
0x18000a620  lea     rdx, aRegistryhelper_0; "RegistryHelper::GetString"
0x18000a627  lea     rcx, [rbp+57h+var_A0]
0x18000a62b  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a630  mov     [rsp+130h+var_F0], r9
0x18000a635  lea     rcx, [rsp+130h+var_DC]
0x18000a63a  mov     [rsp+130h+var_F8], rcx
0x18000a63f  mov     [rsp+130h+pcbData], r8
0x18000a644  lea     rcx, [rsp+130h+var_D8]
0x18000a649  mov     [rsp+130h+pvData], rcx
0x18000a64e  mov     [rsp+130h+pdwType], rax; int
0x18000a653  lea     rdx, unk_180025570
0x18000a65a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000a65f  mov     ecx, ebx
0x18000a661  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000a666  mov     r9d, eax; char *
0x18000a669  mov     rcx, [rbp+5Fh]; this
0x18000a66d  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a674  mov     edx, edi; void *
0x18000a676  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a67c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
