# CSpellerGlobalState::Initialize(bool)

- ea: `0x180274b8c`
- end: `0x180274dad`
- name: `?Initialize@CSpellerGlobalState@@QEAAJ_N@Z`
- size: `545`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180113f84`

## callees

- `0x18000e87c`
- `0x18010c5e8`
- `0x180114790`
- `0x18013ce80`
- `0x18013d268`
- `0x1801406c0`
- `0x180274b8c`
- `0x180277e64`
- `0x180277fb4`
- `0x18027c810`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180274c07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180274c07`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180274d2e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180274d2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180274be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180274be8`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::Initialize(CSpellerGlobalState *this)
{
  int inited; // edi
  _DWORD *v3; // rax
  bool v4; // dl
  _QWORD *v5; // rax
  char v6; // cl
  _QWORD *v7; // rax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  if ( !IsSpellCheckFacilityPresent() )
    return (unsigned int)-2147467259;
  *((_BYTE *)this + 340) = (unsigned __int8)IsMappingGetServicesPresent() == 0;
  if ( WindowsCreateStringReference(L"Windows.Globalization.Language", 0x1Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  inited = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(
             string,
             (char *)this + 296);
  if ( inited >= 0 )
  {
    *((_DWORD *)this + 18) = CSpellerGlobalState::GetCurrentInputMethodLCID(this);
    v3 = operator new(0x18u);
    *(_QWORD *)v3 = 0;
    v3[2] = 8;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)this + 4) = v3;
    inited = CSpellerGlobalState::InitMultilingualResources(this, v4);
    if ( inited >= 0 )
    {
      inited = CSpellerGlobalState::AddNewInputMethod(this, *((_DWORD *)this + 18), 0);
      if ( inited >= 0 )
      {
        v5 = operator new(0xA8u);
        v6 = *((_BYTE *)this + 340);
        *v5 = 0;
        v5[1] = 0;
        v5[5] = 0;
        v5[6] = 0;
        v5[7] = 0;
        v5[18] = 0;
        *((_BYTE *)v5 + 158) = v6;
        v5[2] = 0;
        v5[3] = 0;
        *((_DWORD *)v5 + 38) = 0;
        *((_WORD *)v5 + 78) = 1;
        *((_BYTE *)v5 + 159) = 1;
        *((_DWORD *)v5 + 40) = 2;
        *(_QWORD *)((char *)v5 + 100) = 0;
        *(_QWORD *)((char *)v5 + 108) = 0;
        v5[8] = 0;
        v5[9] = 0;
        v5[10] = 0;
        v5[11] = 0;
        *((_DWORD *)v5 + 24) = 0;
        *(_QWORD *)((char *)v5 + 116) = 0;
        *(_QWORD *)((char *)v5 + 124) = 0;
        *(_QWORD *)((char *)v5 + 132) = 0;
        *((_QWORD *)this + 7) = v5;
        if ( *((_BYTE *)this + 66) )
        {
          (*(void (__fastcall **)(CSpellerGlobalState *))(*(_QWORD *)this + 8LL))(this);
          *((_DWORD *)this + 26) = 1;
          if ( !QueueUserWorkItem(CSpellerGlobalState::BackgroundInitializeThreadProc, this, 0) )
          {
            (*(void (__fastcall **)(CSpellerGlobalState *))(*(_QWORD *)this + 16LL))(this);
            *((_DWORD *)this + 26) = 2;
            return (unsigned int)-2147467259;
          }
        }
        else
        {
          inited = CSpellerGlobalState::ForegroundInitialize(this);
          if ( inited < 0 )
            return (unsigned int)inited;
        }
        v7 = operator new(0x30u);
        *v7 = 2;
        v7[1] = 0;
        v7[2] = 0;
        v7[3] = 0;
        v7[4] = 0;
        v7[5] = 0;
        *((_QWORD *)this + 10) = v7;
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180274b8c  mov     [rsp+arg_8], rbx
0x180274b91  mov     [rsp+arg_10], rsi
0x180274b96  push    rdi
0x180274b97  sub     rsp, 50h
0x180274b9b  mov     rax, cs:__security_cookie
0x180274ba2  xor     rax, rsp
0x180274ba5  mov     [rsp+58h+var_18], rax
0x180274baa  mov     rbx, rcx
0x180274bad  call    ?IsSpellCheckFacilityPresent@@YA_NXZ; IsSpellCheckFacilityPresent(void)
0x180274bb2  xor     esi, esi
0x180274bb4  test    al, al
0x180274bb6  jnz     short loc_180274BC2
0x180274bb8  mov     edi, 80004005h
0x180274bbd  jmp     loc_180274D8D
0x180274bc2  call    IsMappingGetServicesPresent
0x180274bc7  test    al, al
0x180274bc9  lea     r9, [rsp+58h+string]; string
0x180274bce  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180274bd3  mov     edx, 1Eh; length
0x180274bd8  setz    al
0x180274bdb  lea     rcx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x180274be2  mov     [rbx+154h], al
0x180274be8  call    cs:__imp_WindowsCreateStringReference
0x180274bef  nop     dword ptr [rax+rax+00h]
0x180274bf4  test    eax, eax
0x180274bf6  jns     short loc_180274C13
0x180274bf8  xor     r9d, r9d; lpArguments
0x180274bfb  xor     r8d, r8d; nNumberOfArguments
0x180274bfe  mov     ecx, 0C000000Dh; dwExceptionCode
0x180274c03  lea     edx, [r9+1]; dwExceptionFlags
0x180274c07  call    cs:__imp_RaiseException
0x180274c0e  nop     dword ptr [rax+rax+00h]
0x180274c13  mov     rcx, [rsp+58h+string]
0x180274c18  lea     rdx, [rbx+128h]
0x180274c1f  call    ??$GetActivationFactory@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>)
0x180274c24  mov     edi, eax
0x180274c26  test    eax, eax
0x180274c28  js      loc_180274D8D
0x180274c2e  mov     rcx, rbx; this
0x180274c31  call    ?GetCurrentInputMethodLCID@CSpellerGlobalState@@QEBAKXZ; CSpellerGlobalState::GetCurrentInputMethodLCID(void)
0x180274c36  mov     ecx, 18h; Size
0x180274c3b  mov     [rbx+48h], eax
0x180274c3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180274c43  mov     rcx, rbx; this
0x180274c46  mov     [rax], rsi
0x180274c49  mov     dword ptr [rax+8], 8
0x180274c50  mov     [rax+10h], rsi
0x180274c54  mov     [rbx+20h], rax
0x180274c58  call    ?InitMultilingualResources@CSpellerGlobalState@@AEAAJ_N@Z; CSpellerGlobalState::InitMultilingualResources(bool)
0x180274c5d  mov     edi, eax
0x180274c5f  test    eax, eax
0x180274c61  js      loc_180274D8D
0x180274c67  mov     edx, [rbx+48h]; unsigned int
0x180274c6a  xor     r8d, r8d; struct Microsoft::WRL::Wrappers::HString *
0x180274c6d  mov     rcx, rbx; this
0x180274c70  call    ?AddNewInputMethod@CSpellerGlobalState@@QEAAJKPEAVHString@Wrappers@WRL@Microsoft@@@Z; CSpellerGlobalState::AddNewInputMethod(ulong,Microsoft::WRL::Wrappers::HString *)
0x180274c75  mov     edi, eax
0x180274c77  test    eax, eax
0x180274c79  js      loc_180274D8D
0x180274c7f  mov     ecx, 0A8h; Size
0x180274c84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180274c89  mov     cl, [rbx+154h]
0x180274c8f  mov     [rax], rsi
0x180274c92  mov     [rax+8], rsi
0x180274c96  mov     [rax+28h], rsi
0x180274c9a  mov     [rax+30h], rsi
0x180274c9e  mov     [rax+38h], rsi
0x180274ca2  mov     [rax+90h], rsi
0x180274ca9  mov     [rax+9Eh], cl
0x180274caf  mov     rcx, rbx; this
0x180274cb2  mov     [rax+10h], rsi
0x180274cb6  mov     [rax+18h], rsi
0x180274cba  mov     [rax+98h], esi
0x180274cc0  mov     word ptr [rax+9Ch], 1
0x180274cc9  mov     byte ptr [rax+9Fh], 1
0x180274cd0  mov     dword ptr [rax+0A0h], 2
0x180274cda  mov     [rax+64h], rsi
0x180274cde  mov     [rax+6Ch], rsi
0x180274ce2  mov     [rax+40h], rsi
0x180274ce6  mov     [rax+48h], rsi
0x180274cea  mov     [rax+50h], rsi
0x180274cee  mov     [rax+58h], rsi
0x180274cf2  mov     [rax+60h], esi
0x180274cf5  mov     [rax+74h], rsi
0x180274cf9  mov     [rax+7Ch], rsi
0x180274cfd  mov     [rax+84h], rsi
0x180274d04  mov     [rbx+38h], rax
0x180274d08  cmp     [rbx+42h], sil
0x180274d0c  jz      short loc_180274D59
0x180274d0e  mov     rax, [rbx]
0x180274d11  mov     rax, [rax+8]
0x180274d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274d1a  xor     r8d, r8d; Flags
0x180274d1d  mov     dword ptr [rbx+68h], 1
0x180274d24  mov     rdx, rbx; Context
0x180274d27  lea     rcx, ?BackgroundInitializeThreadProc@CSpellerGlobalState@@CAKPEAX@Z; Function
0x180274d2e  call    cs:__imp_QueueUserWorkItem
0x180274d35  nop     dword ptr [rax+rax+00h]
0x180274d3a  test    eax, eax
0x180274d3c  jnz     short loc_180274D64
0x180274d3e  mov     rax, [rbx]
0x180274d41  mov     rcx, rbx
0x180274d44  mov     rax, [rax+10h]
0x180274d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274d4d  mov     dword ptr [rbx+68h], 2
0x180274d54  jmp     loc_180274BB8
0x180274d59  call    ?ForegroundInitialize@CSpellerGlobalState@@AEAAJXZ; CSpellerGlobalState::ForegroundInitialize(void)
0x180274d5e  mov     edi, eax
0x180274d60  test    eax, eax
0x180274d62  js      short loc_180274D8D
0x180274d64  mov     ecx, 30h ; '0'; Size
0x180274d69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180274d6e  mov     qword ptr [rax], 2
0x180274d75  mov     [rax+8], rsi
0x180274d79  mov     [rax+10h], rsi
0x180274d7d  mov     [rax+18h], rsi
0x180274d81  mov     [rax+20h], rsi
0x180274d85  mov     [rax+28h], rsi
0x180274d89  mov     [rbx+50h], rax
0x180274d8d  mov     eax, edi
0x180274d8f  mov     rcx, [rsp+58h+var_18]
0x180274d94  xor     rcx, rsp; StackCookie
0x180274d97  call    __security_check_cookie
0x180274d9c  mov     rbx, [rsp+58h+arg_8]
0x180274da1  mov     rsi, [rsp+58h+arg_10]
0x180274da6  add     rsp, 50h
0x180274daa  pop     rdi
0x180274dab  retn
```
