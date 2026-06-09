# TpmSymmetricPopKey::DeriveKey(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x18001dfb0`
- end: `0x18001e19b`
- name: `?DeriveKey@TpmSymmetricPopKey@@MEAAJPEAEK0K0K@Z`
- size: `491`
- prototype: `__int64 __fastcall(TpmSymmetricPopKey *this, unsigned __int8 *, int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000132c`
- `0x180004de0`
- `0x18000b0fc`
- `0x1800136d4`
- `0x180014f38`
- `0x180018560`
- `0x18001dfb0`
- `0x1800202c4`

## import_xrefs

- `ncrypt!NCryptKeyDerivation` at `0x18001e0ab`
- `ncrypt!NCryptKeyDerivation` at `0x18001e165`
- `ncrypt!NCryptKeyDerivation` at `0x18001e0ab`
- `ncrypt!NCryptKeyDerivation` at `0x18001e165`

## string_xrefs

- `0x18001e075`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall TpmSymmetricPopKey::DeriveKey(
        TpmSymmetricPopKey *this,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  unsigned int v8; // eax
  int v9; // edi
  __int64 v10; // rbx
  unsigned int v11; // esi
  int v12; // eax
  int TpmHmacKeyHandle; // ebx
  __int64 v14; // rdx
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  int v19; // ebx
  __int64 v20; // rdi
  unsigned int v21; // esi
  int v22; // eax
  char v23; // [rsp+20h] [rbp-81h]
  unsigned int *v24; // [rsp+20h] [rbp-81h]
  __int64 v25; // [rsp+30h] [rbp-71h] BYREF
  int v26; // [rsp+38h] [rbp-69h] BYREF
  _DWORD v27[2]; // [rsp+40h] [rbp-61h] BYREF
  _DWORD *v28; // [rsp+48h] [rbp-59h]
  _BYTE v29[32]; // [rsp+50h] [rbp-51h] BYREF
  _DWORD v30[2]; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int8 *v31; // [rsp+78h] [rbp-29h]
  int v32; // [rsp+80h] [rbp-21h]
  int v33; // [rsp+84h] [rbp-1Dh]
  unsigned __int8 *v34; // [rsp+88h] [rbp-19h]
  __int64 v35; // [rsp+90h] [rbp-11h]
  const wchar_t *v36; // [rsp+98h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v30[0] = a5;
  v33 = 14;
  v35 = 14;
  v36 = L"SHA256";
  v28 = v30;
  v30[1] = 13;
  v31 = a4;
  v32 = a3;
  v34 = a2;
  v27[0] = 0;
  v27[1] = 3;
  v25 = 0;
  v8 = (unsigned int)TpmKeysManager::Instance();
  v9 = *((_DWORD *)this + 4);
  v10 = *((_QWORD *)this + 1);
  v11 = v8;
  v12 = std::wstring::wstring(v29, (char *)this + 24);
  v23 = 0;
  TpmHmacKeyHandle = TpmKeysManager::GetTpmHmacKeyHandle(v11, v12, v10, v9, v23, (__int64)&v25);
  if ( TpmHmacKeyHandle < 0 )
  {
    v14 = 236;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)(unsigned int)TpmHmacKeyHandle,
      (int)v24);
    return (unsigned int)TpmHmacKeyHandle;
  }
  v24 = &a7;
  v16 = NCryptKeyDerivation(v25, v27, a6, a7);
  TpmHmacKeyHandle = v16;
  if ( v16 == -2144795614 || NgcUtils::ShouldReloadTpmHandle((NgcUtils *)v16, v17) )
  {
    if ( (unsigned int)dword_180037000 > 4 )
    {
      v26 = TpmHmacKeyHandle;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180037000,
        (unsigned int)&dword_18002F04C,
        0,
        0,
        (__int64)&v26);
    }
    v18 = (unsigned int)TpmKeysManager::Instance();
    v19 = *((_DWORD *)this + 4);
    v20 = *((_QWORD *)this + 1);
    v21 = v18;
    v22 = std::wstring::wstring(v29, (char *)this + 24);
    LOBYTE(v24) = 1;
    TpmHmacKeyHandle = TpmKeysManager::GetTpmHmacKeyHandle(v21, v22, v20, v19, (_DWORD)v24, (__int64)&v25);
    if ( TpmHmacKeyHandle < 0 )
    {
      v14 = 261;
      goto LABEL_3;
    }
    v24 = &a7;
    TpmHmacKeyHandle = NCryptKeyDerivation(v25, v27, a6, a7);
  }
  if ( TpmHmacKeyHandle < 0 )
  {
    v14 = 271;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001dfb0  push    rbp
0x18001dfb2  push    rbx
0x18001dfb3  push    rsi
0x18001dfb4  push    rdi
0x18001dfb5  push    r12
0x18001dfb7  push    r14
0x18001dfb9  push    r15
0x18001dfbb  lea     rbp, [rsp-0Fh]
0x18001dfc0  sub     rsp, 0B0h
0x18001dfc7  mov     rax, cs:__security_cookie
0x18001dfce  xor     rax, rsp
0x18001dfd1  mov     [rbp+3Fh+var_40], rax
0x18001dfd5  mov     eax, [rbp+3Fh+arg_20]
0x18001dfd8  mov     r15, rcx
0x18001dfdb  mov     r14, [rbp+3Fh+arg_28]
0x18001dfdf  mov     [rbp+3Fh+var_70], eax
0x18001dfe2  mov     eax, 0Eh
0x18001dfe7  mov     [rbp+3Fh+var_5C], eax
0x18001dfea  mov     [rbp+3Fh+var_50], rax
0x18001dfee  lea     rax, aSha256; "SHA256"
0x18001dff5  mov     [rbp+3Fh+var_48], rax
0x18001dff9  lea     rax, [rbp+3Fh+var_70]
0x18001dffd  mov     [rbp+3Fh+var_98], rax
0x18001e001  mov     [rbp+3Fh+var_6C], 0Dh
0x18001e008  mov     [rbp+3Fh+var_68], r9
0x18001e00c  mov     [rbp+3Fh+var_60], r8d
0x18001e010  mov     [rbp+3Fh+var_58], rdx
0x18001e014  mov     [rbp+3Fh+var_A0], 0
0x18001e01b  mov     [rbp+3Fh+var_9C], 3
0x18001e022  mov     [rbp+3Fh+var_B0], 0
0x18001e02a  call    ?Instance@TpmKeysManager@@SAAEAV1@XZ; TpmKeysManager::Instance(void)
0x18001e02f  mov     edi, [r15+10h]
0x18001e033  lea     rdx, [r15+18h]
0x18001e037  mov     rbx, [r15+8]
0x18001e03b  lea     rcx, [rbp+3Fh+var_90]
0x18001e03f  mov     rsi, rax
0x18001e042  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e047  lea     rcx, [rbp+3Fh+var_B0]
0x18001e04b  mov     r9d, edi
0x18001e04e  mov     [rsp+0E0h+var_B8], rcx
0x18001e053  mov     r8, rbx
0x18001e056  mov     rcx, rsi
0x18001e059  mov     byte ptr [rsp+0E0h+var_C0], 0; int
0x18001e05e  mov     rdx, rax
0x18001e061  call    ?GetTpmHmacKeyHandle@TpmKeysManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAEK_NPEA_K@Z; TpmKeysManager::GetTpmHmacKeyHandle(std::wstring,uchar *,ulong,bool,unsigned __int64 *)
0x18001e066  mov     ebx, eax
0x18001e068  test    eax, eax
0x18001e06a  jns     short loc_18001E08B
0x18001e06c  mov     edx, 0ECh; void *
0x18001e071  mov     rcx, [rbp+47h]; this
0x18001e075  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e07c  mov     r9d, ebx; char *
0x18001e07f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e084  mov     eax, ebx
0x18001e086  jmp     loc_18001E17D
0x18001e08b  mov     r9d, [rbp+3Fh+arg_30]
0x18001e08f  lea     rax, [rbp+3Fh+arg_30]
0x18001e093  mov     rcx, [rbp+3Fh+var_B0]
0x18001e097  lea     rdx, [rbp+3Fh+var_A0]
0x18001e09b  mov     dword ptr [rsp+0E0h+var_B8], 0
0x18001e0a3  mov     r8, r14
0x18001e0a6  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001e0ab  call    cs:__imp_NCryptKeyDerivation
0x18001e0b1  mov     ebx, eax
0x18001e0b3  cmp     eax, 80290422h
0x18001e0b8  jz      short loc_18001E0C9
0x18001e0ba  mov     ecx, eax; this
0x18001e0bc  call    ?ShouldReloadTpmHandle@NgcUtils@@YA_NJ@Z; NgcUtils::ShouldReloadTpmHandle(long)
0x18001e0c1  test    al, al
0x18001e0c3  jz      loc_18001E16D
0x18001e0c9  mov     ecx, cs:dword_180037000
0x18001e0cf  cmp     ecx, 4
0x18001e0d2  jbe     short loc_18001E0F9
0x18001e0d4  lea     rax, [rbp+3Fh+var_A8]
0x18001e0d8  mov     [rbp+3Fh+var_A8], ebx
0x18001e0db  xor     r9d, r9d
0x18001e0de  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001e0e3  xor     r8d, r8d
0x18001e0e6  lea     rdx, dword_18002F04C
0x18001e0ed  lea     rcx, dword_180037000
0x18001e0f4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e0f9  call    ?Instance@TpmKeysManager@@SAAEAV1@XZ; TpmKeysManager::Instance(void)
0x18001e0fe  mov     ebx, [r15+10h]
0x18001e102  lea     rdx, [r15+18h]
0x18001e106  mov     rdi, [r15+8]
0x18001e10a  lea     rcx, [rbp+3Fh+var_90]
0x18001e10e  mov     rsi, rax
0x18001e111  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e116  lea     rcx, [rbp+3Fh+var_B0]
0x18001e11a  mov     r9d, ebx
0x18001e11d  mov     [rsp+0E0h+var_B8], rcx
0x18001e122  mov     r8, rdi
0x18001e125  mov     rcx, rsi
0x18001e128  mov     byte ptr [rsp+0E0h+var_C0], 1
0x18001e12d  mov     rdx, rax
0x18001e130  call    ?GetTpmHmacKeyHandle@TpmKeysManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAEK_NPEA_K@Z; TpmKeysManager::GetTpmHmacKeyHandle(std::wstring,uchar *,ulong,bool,unsigned __int64 *)
0x18001e135  mov     ebx, eax
0x18001e137  test    eax, eax
0x18001e139  jns     short loc_18001E145
0x18001e13b  mov     edx, 105h
0x18001e140  jmp     loc_18001E071
0x18001e145  mov     r9d, [rbp+3Fh+arg_30]
0x18001e149  lea     rax, [rbp+3Fh+arg_30]
0x18001e14d  mov     rcx, [rbp+3Fh+var_B0]
0x18001e151  lea     rdx, [rbp+3Fh+var_A0]
0x18001e155  mov     dword ptr [rsp+0E0h+var_B8], 0
0x18001e15d  mov     r8, r14
0x18001e160  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001e165  call    cs:__imp_NCryptKeyDerivation
0x18001e16b  mov     ebx, eax
0x18001e16d  test    ebx, ebx
0x18001e16f  jns     short loc_18001E17B
0x18001e171  mov     edx, 10Fh
0x18001e176  jmp     loc_18001E071
0x18001e17b  xor     eax, eax
0x18001e17d  mov     rcx, [rbp+3Fh+var_40]
0x18001e181  xor     rcx, rsp; StackCookie
0x18001e184  call    __security_check_cookie
0x18001e189  add     rsp, 0B0h
0x18001e190  pop     r15
0x18001e192  pop     r14
0x18001e194  pop     r12
0x18001e196  pop     rdi
0x18001e197  pop     rsi
0x18001e198  pop     rbx
0x18001e199  pop     rbp
0x18001e19a  retn
```
