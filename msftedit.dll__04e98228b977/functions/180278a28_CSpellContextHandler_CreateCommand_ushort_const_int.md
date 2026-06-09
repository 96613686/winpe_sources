# CSpellContextHandler::CreateCommand(ushort const *,int)

- ea: `0x180278a28`
- end: `0x180278bd2`
- name: `?CreateCommand@CSpellContextHandler@@AEAAJPEBGH@Z`
- size: `426`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this, PCWSTR sourceString, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180278bd8`
- `0x18027942c`
- `0x180279718`

## callees

- `0x18006ad18`
- `0x180108394`
- `0x18013ce80`
- `0x18013d268`
- `0x180278174`
- `0x1802781cc`
- `0x1802785e4`
- `0x180278a28`
- `0x180278e80`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180278aad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180278aad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180278ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180278ac7`

## string_xrefs

- `0x180278a52`: `Windows.UI.Popups.UICommand`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::CreateCommand(
        CSpellContextHandler *this,
        PCWSTR sourceString,
        unsigned int a3)
{
  _QWORD *v6; // rax
  int PropertyValueUInt32; // ebx
  unsigned __int64 v8; // rcx
  CSpellContextHandler *v9; // rcx
  CSpellingCommandHandler *v10; // rax
  CSpellingCommandHandler *v11; // rax
  CSpellingCommandHandler *v12; // rdi
  UINT32 length[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF

  v15 = 0;
  v6 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, L"Windows.UI.Popups.UICommand");
  PropertyValueUInt32 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(
                          *v6,
                          &v15);
  if ( PropertyValueUInt32 >= 0 )
  {
    length[0] = 0;
    v8 = -1;
    do
      ++v8;
    while ( sourceString[v8] );
    if ( (int)ULongLongToUInt(v8, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(sourceString, length[0], &hstringHeader, &string);
    PropertyValueUInt32 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v15 + 56LL))(v15, string);
    if ( PropertyValueUInt32 >= 0 )
    {
      *(_QWORD *)length = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(length);
      PropertyValueUInt32 = CSpellContextHandler::CreatePropertyValueUInt32(v9, a3, (struct IInspectable **)length);
      if ( PropertyValueUInt32 >= 0 )
      {
        PropertyValueUInt32 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 88LL))(
                                v15,
                                *(_QWORD *)length);
        if ( PropertyValueUInt32 >= 0 )
        {
          v10 = (CSpellingCommandHandler *)operator new(0x20u);
          v11 = CSpellingCommandHandler::CSpellingCommandHandler(v10, this, a3);
          v12 = v11;
          if ( v11 )
          {
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v11 + 8LL))(v11);
            PropertyValueUInt32 = (*(__int64 (__fastcall **)(__int64, CSpellingCommandHandler *))(*(_QWORD *)v15 + 72LL))(
                                    v15,
                                    v12);
            if ( PropertyValueUInt32 >= 0 )
              PropertyValueUInt32 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 104LL))(
                                      *((_QWORD *)this + 18),
                                      v15);
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(length);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)PropertyValueUInt32;
}

```

## disassembly

```asm
0x180278a28  mov     [rsp-28h+arg_18], rbx
0x180278a2d  push    rbp
0x180278a2e  push    rsi
0x180278a2f  push    rdi
0x180278a30  push    r14
0x180278a32  push    r15
0x180278a34  mov     rbp, rsp
0x180278a37  sub     rsp, 60h
0x180278a3b  mov     rax, cs:__security_cookie
0x180278a42  xor     rax, rsp
0x180278a45  mov     [rbp+var_10], rax
0x180278a49  mov     rsi, rdx
0x180278a4c  mov     r14, rcx
0x180278a4f  xor     r15d, r15d
0x180278a52  lea     rdx, ?RuntimeClass_Windows_UI_Popups_UICommand@@3QBGB; "Windows.UI.Popups.UICommand"
0x180278a59  lea     rcx, [rbp+string]; string
0x180278a5d  mov     [rbp+var_38], r15
0x180278a61  mov     edi, r8d
0x180278a64  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x180278a69  lea     rdx, [rbp+var_38]
0x180278a6d  mov     rcx, [rax]
0x180278a70  call    ??$ActivateInstance@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>)
0x180278a75  mov     ebx, eax
0x180278a77  test    eax, eax
0x180278a79  js      loc_180278BA6
0x180278a7f  mov     [rbp+length], r15d
0x180278a83  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180278a87  inc     rcx; unsigned __int64
0x180278a8a  cmp     [rsi+rcx*2], r15w
0x180278a8f  jnz     short loc_180278A87
0x180278a91  lea     rdx, [rbp+length]; unsigned int *
0x180278a95  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180278a9a  test    eax, eax
0x180278a9c  jns     short loc_180278AB9
0x180278a9e  xor     r9d, r9d; lpArguments
0x180278aa1  xor     r8d, r8d; nNumberOfArguments
0x180278aa4  mov     ecx, 0C000000Dh; dwExceptionCode
0x180278aa9  lea     edx, [r9+1]; dwExceptionFlags
0x180278aad  call    cs:__imp_RaiseException
0x180278ab4  nop     dword ptr [rax+rax+00h]
0x180278ab9  mov     edx, [rbp+length]; length
0x180278abc  lea     r9, [rbp+string]; string
0x180278ac0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180278ac4  mov     rcx, rsi; sourceString
0x180278ac7  call    cs:__imp_WindowsCreateStringReference
0x180278ace  nop     dword ptr [rax+rax+00h]
0x180278ad3  mov     rcx, [rbp+var_38]
0x180278ad7  mov     rdx, [rbp+string]
0x180278adb  mov     rax, [rcx]
0x180278ade  mov     rax, [rax+38h]
0x180278ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278ae7  mov     ebx, eax
0x180278ae9  test    eax, eax
0x180278aeb  js      loc_180278BA6
0x180278af1  lea     rcx, [rbp+length]
0x180278af5  mov     qword ptr [rbp+length], r15
0x180278af9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180278afe  lea     r8, [rbp+length]; struct IInspectable **
0x180278b02  mov     edx, edi; unsigned int
0x180278b04  call    ?CreatePropertyValueUInt32@CSpellContextHandler@@AEAAJIPEAPEAUIInspectable@@@Z; CSpellContextHandler::CreatePropertyValueUInt32(uint,IInspectable * *)
0x180278b09  mov     ebx, eax
0x180278b0b  test    eax, eax
0x180278b0d  js      loc_180278B9D
0x180278b13  mov     rcx, [rbp+var_38]
0x180278b17  mov     rdx, qword ptr [rbp+length]
0x180278b1b  mov     rax, [rcx]
0x180278b1e  mov     rax, [rax+58h]
0x180278b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278b27  mov     ebx, eax
0x180278b29  test    eax, eax
0x180278b2b  js      short loc_180278B9D
0x180278b2d  mov     ecx, 20h ; ' '; Size
0x180278b32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180278b37  mov     r8d, edi; int
0x180278b3a  mov     rdx, r14; struct CSpellContextHandler *
0x180278b3d  mov     rcx, rax; this
0x180278b40  call    ??0CSpellingCommandHandler@@QEAA@PEAVCSpellContextHandler@@H@Z; CSpellingCommandHandler::CSpellingCommandHandler(CSpellContextHandler *,int)
0x180278b45  mov     rdi, rax
0x180278b48  test    rax, rax
0x180278b4b  jz      short loc_180278B9D
0x180278b4d  mov     rcx, [rax]
0x180278b50  mov     rax, [rcx+8]
0x180278b54  mov     rcx, rdi
0x180278b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278b5c  mov     rcx, [rbp+var_38]
0x180278b60  mov     rdx, [rcx]
0x180278b63  mov     rax, [rdx+48h]
0x180278b67  mov     rdx, rdi
0x180278b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278b6f  mov     ebx, eax
0x180278b71  test    eax, eax
0x180278b73  js      short loc_180278B8E
0x180278b75  mov     rcx, [r14+90h]
0x180278b7c  mov     rdx, [rbp+var_38]
0x180278b80  mov     rax, [rcx]
0x180278b83  mov     rax, [rax+68h]
0x180278b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278b8c  mov     ebx, eax
0x180278b8e  mov     rax, [rdi]
0x180278b91  mov     rcx, rdi
0x180278b94  mov     rax, [rax+10h]
0x180278b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180278b9d  lea     rcx, [rbp+length]
0x180278ba1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180278ba6  lea     rcx, [rbp+var_38]
0x180278baa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180278baf  mov     eax, ebx
0x180278bb1  mov     rcx, [rbp+var_10]
0x180278bb5  xor     rcx, rsp; StackCookie
0x180278bb8  call    __security_check_cookie
0x180278bbd  mov     rbx, [rsp+60h+arg_18]
0x180278bc5  add     rsp, 60h
0x180278bc9  pop     r15
0x180278bcb  pop     r14
0x180278bcd  pop     rdi
0x180278bce  pop     rsi
0x180278bcf  pop     rbp
0x180278bd0  retn
```
