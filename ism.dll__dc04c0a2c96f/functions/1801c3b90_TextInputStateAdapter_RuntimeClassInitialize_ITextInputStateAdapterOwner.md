# TextInputStateAdapter::RuntimeClassInitialize(ITextInputStateAdapterOwner *)

- ea: `0x1801c3b90`
- end: `0x1801c3d7a`
- name: `?RuntimeClassInitialize@TextInputStateAdapter@@QEAAJPEAUITextInputStateAdapterOwner@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(TextInputStateAdapter *__hidden this, struct ITextInputStateAdapterOwner *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801c2274`

## callees

- `0x180012b74`
- `0x180057cac`
- `0x1800f08d8`
- `0x1800f0990`
- `0x18013bc74`
- `0x18019e348`
- `0x18019fc60`
- `0x1801c3b90`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801c3c51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801c3c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c3c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c3c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c3c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c3c5f`
- `CoreMessaging!CoreUICreate` at `0x1801c3bca`
- `CoreMessaging!CoreUICreate` at `0x1801c3bca`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801c3c05`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801c3c05`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1801c3d19`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1801c3d19`

## string_xrefs

- `0x1801c3c46`: `CoreUIFactoryCreate`
- `0x1801c3bfe`: `CoreUIComponents.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TextInputStateAdapter::RuntimeClassInitialize(
        TextInputStateAdapter *this,
        struct ITextInputStateAdapterOwner *a2)
{
  int v4; // eax
  int v5; // edx
  int v6; // ecx
  signed int v7; // ebx
  int v8; // r9d
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  int v11; // edx
  int v12; // ecx
  FARPROC ProcAddress; // rsi
  signed int v14; // eax
  int v15; // edx
  int v16; // ecx
  unsigned int v17; // r8d
  int v18; // eax
  __int64 v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-268h] BYREF
  _QWORD v22[3]; // [rsp+38h] [rbp-260h] BYREF
  wchar_t v23[264]; // [rsp+50h] [rbp-248h] BYREF
  unsigned __int64 retaddr; // [rsp+298h] [rbp+0h]

  v21 = 0;
  v22[1] = 0;
  v4 = CoreUICreate((char *)this + 32);
  v7 = v4;
  if ( v4 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_26;
    v8 = 907;
LABEL_4:
    McTemplateU0sqq_EventWriteTransfer(v6, v5, (unsigned int)"TextInputStateAdapter::RuntimeClassInitialize", v8, v4);
    goto LABEL_26;
  }
  LibraryW = LoadLibraryW(L"CoreUIComponents.dll");
  *((_QWORD *)this + 13) = LibraryW;
  if ( LibraryW )
    goto LABEL_12;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_12:
    ProcAddress = GetProcAddress(*((HMODULE *)this + 13), "CoreUIFactoryCreate");
    if ( ProcAddress )
      goto LABEL_18;
    v14 = GetLastError();
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_18:
      v4 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v21);
      v7 = v4;
      if ( v4 < 0 )
      {
        if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
          goto LABEL_26;
        v8 = 915;
        goto LABEL_4;
      }
      memset_0(v23, 0, 0x208u);
      GetDesktopUniqueName(L"System\\RemoteTextInputState", v23, v17);
      v22[0] = this;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
      v18 = Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,unsigned short (&)[260],HotkeyRegistrationForwarder *>(
              (char *)this + 48,
              &GUID_cf1538c5_01ef_4a39_acb7_1b68f01b7ef4,
              v23,
              v22);
      v7 = v18;
      if ( v18 >= 0 )
      {
        *((_QWORD *)this + 3) = a2;
        v7 = 0;
      }
      else
      {
        if ( v18 == -2147024882 )
          TerminateProcessOnMemoryExhaustion(0);
        FailFastWithHR(v7, retaddr, 0x39Eu);
      }
    }
    else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      McTemplateU0sqq_EventWriteTransfer(
        v16,
        v15,
        (unsigned int)"TextInputStateAdapter::RuntimeClassInitialize",
        914,
        v7);
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    McTemplateU0sqq_EventWriteTransfer(v12, v11, (unsigned int)"TextInputStateAdapter::RuntimeClassInitialize", 911, v7);
  }
LABEL_26:
  v19 = v21;
  v21 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801c3b90  push    rbx
0x1801c3b92  push    rbp
0x1801c3b93  push    rsi
0x1801c3b94  push    rdi
0x1801c3b95  sub     rsp, 278h
0x1801c3b9c  mov     rax, cs:__security_cookie
0x1801c3ba3  xor     rax, rsp
0x1801c3ba6  mov     [rsp+298h+var_38], rax
0x1801c3bae  mov     rbp, rdx
0x1801c3bb1  mov     rdi, rcx
0x1801c3bb4  mov     [rsp+298h+var_268], 0
0x1801c3bbd  mov     [rsp+298h+var_258], 0
0x1801c3bc6  add     rcx, 20h ; ' '
0x1801c3bca  call    cs:__imp_CoreUICreate
0x1801c3bd0  mov     ebx, eax
0x1801c3bd2  test    eax, eax
0x1801c3bd4  jns     short loc_1801C3BFE
0x1801c3bd6  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c3bdd  jz      loc_1801C3D3C
0x1801c3be3  mov     r9d, 38Bh
0x1801c3be9  mov     [rsp+298h+var_278], eax
0x1801c3bed  lea     r8, aTextinputstate_3; "TextInputStateAdapter::RuntimeClassInit"...
0x1801c3bf4  call    McTemplateU0sqq_EventWriteTransfer
0x1801c3bf9  jmp     loc_1801C3D3C
0x1801c3bfe  lea     rcx, aCoreuicomponen_0; "CoreUIComponents.dll"
0x1801c3c05  call    cs:__imp_LoadLibraryW
0x1801c3c0b  mov     [rdi+68h], rax
0x1801c3c0f  test    rax, rax
0x1801c3c12  jnz     short loc_1801C3C46
0x1801c3c14  call    cs:__imp_GetLastError
0x1801c3c1a  mov     ebx, eax
0x1801c3c1c  test    eax, eax
0x1801c3c1e  jle     short loc_1801C3C29
0x1801c3c20  movzx   ebx, ax
0x1801c3c23  or      ebx, 80070000h
0x1801c3c29  test    ebx, ebx
0x1801c3c2b  jns     short loc_1801C3C46
0x1801c3c2d  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c3c34  jz      loc_1801C3D3C
0x1801c3c3a  mov     [rsp+298h+var_278], ebx
0x1801c3c3e  mov     r9d, 38Fh
0x1801c3c44  jmp     short loc_1801C3BED
0x1801c3c46  lea     rdx, aCoreuifactoryc; "CoreUIFactoryCreate"
0x1801c3c4d  mov     rcx, [rdi+68h]; hModule
0x1801c3c51  call    cs:__imp_GetProcAddress
0x1801c3c57  mov     rsi, rax
0x1801c3c5a  test    rax, rax
0x1801c3c5d  jnz     short loc_1801C3C94
0x1801c3c5f  call    cs:__imp_GetLastError
0x1801c3c65  mov     ebx, eax
0x1801c3c67  test    eax, eax
0x1801c3c69  jle     short loc_1801C3C74
0x1801c3c6b  movzx   ebx, ax
0x1801c3c6e  or      ebx, 80070000h
0x1801c3c74  test    ebx, ebx
0x1801c3c76  jns     short loc_1801C3C94
0x1801c3c78  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c3c7f  jz      loc_1801C3D3C
0x1801c3c85  mov     [rsp+298h+var_278], ebx
0x1801c3c89  mov     r9d, 392h
0x1801c3c8f  jmp     loc_1801C3BED
0x1801c3c94  lea     rcx, [rsp+298h+var_268]
0x1801c3c99  mov     rax, rsi
0x1801c3c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3ca1  mov     ebx, eax
0x1801c3ca3  test    eax, eax
0x1801c3ca5  jns     short loc_1801C3CBF
0x1801c3ca7  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c3cae  jz      loc_1801C3D3C
0x1801c3cb4  mov     r9d, 393h
0x1801c3cba  jmp     loc_1801C3BE9
0x1801c3cbf  xor     edx, edx; Val
0x1801c3cc1  mov     r8d, 208h; Size
0x1801c3cc7  lea     rcx, [rsp+298h+var_248]; void *
0x1801c3ccc  call    memset_0
0x1801c3cd1  lea     rdx, [rsp+298h+var_248]; wchar_t *
0x1801c3cd6  lea     rcx, aSystemRemotete; "System\\RemoteTextInputState"
0x1801c3cdd  call    ?GetDesktopUniqueName@@YAXPEB_WPEA_WK@Z; GetDesktopUniqueName(wchar_t const *,wchar_t *,ulong)
0x1801c3ce2  mov     [rsp+298h+var_260], rdi
0x1801c3ce7  lea     rcx, [rdi+30h]
0x1801c3ceb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c3cf0  lea     r9, [rsp+298h+var_260]
0x1801c3cf5  lea     r8, [rsp+298h+var_248]
0x1801c3cfa  lea     rdx, _GUID_cf1538c5_01ef_4a39_acb7_1b68f01b7ef4
0x1801c3d01  lea     rcx, [rdi+30h]
0x1801c3d05  call    ??$MakeAndInitialize@VMessageProxyReconnectAdapter@@V1@AEBU_GUID@@AEAY0BAE@GPEAVHotkeyRegistrationForwarder@@@Details@WRL@Microsoft@@YAJPEAPEAVMessageProxyReconnectAdapter@@AEBU_GUID@@AEAY0BAE@G$$QEAPEAVHotkeyRegistrationForwarder@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,ushort (&)[260],HotkeyRegistrationForwarder *>(MessageProxyReconnectAdapter * *,_GUID const &,ushort (&)[260],HotkeyRegistrationForwarder * &&)
0x1801c3d0a  mov     ebx, eax
0x1801c3d0c  test    eax, eax
0x1801c3d0e  jns     short loc_1801C3D36
0x1801c3d10  cmp     eax, 8007000Eh
0x1801c3d15  jnz     short loc_1801C3D1F
0x1801c3d17  xor     ecx, ecx; FailedAllocationSize
0x1801c3d19  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x1801c3d1f  mov     rdx, [rsp+298h]; unsigned __int64
0x1801c3d27  mov     r8d, 39Eh; unsigned __int64
0x1801c3d2d  mov     ecx, ebx; int
0x1801c3d2f  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1801c3d34  jmp     short loc_1801C3D3C
0x1801c3d36  mov     [rdi+18h], rbp
0x1801c3d3a  xor     ebx, ebx
0x1801c3d3c  mov     rcx, [rsp+298h+var_268]
0x1801c3d41  mov     [rsp+298h+var_268], 0
0x1801c3d4a  test    rcx, rcx
0x1801c3d4d  jz      short loc_1801C3D5C
0x1801c3d4f  mov     rax, [rcx]
0x1801c3d52  mov     rax, [rax+10h]
0x1801c3d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c3d5b  nop
0x1801c3d5c  mov     eax, ebx
0x1801c3d5e  mov     rcx, [rsp+298h+var_38]
0x1801c3d66  xor     rcx, rsp; StackCookie
0x1801c3d69  call    __security_check_cookie
0x1801c3d6e  add     rsp, 278h
0x1801c3d75  pop     rdi
0x1801c3d76  pop     rsi
0x1801c3d77  pop     rbp
0x1801c3d78  pop     rbx
0x1801c3d79  retn
```
