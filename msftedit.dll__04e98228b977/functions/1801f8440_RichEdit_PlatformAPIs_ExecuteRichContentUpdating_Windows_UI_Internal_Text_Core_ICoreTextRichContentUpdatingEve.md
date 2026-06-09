# RichEdit::PlatformAPIs::ExecuteRichContentUpdating(Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *,RichEdit::IRichEditSmartLinkHandler *)

- ea: `0x1801f8440`
- end: `0x1801f86b7`
- name: `?ExecuteRichContentUpdating@PlatformAPIs@RichEdit@@UEAAJPEAUICoreTextRichContentUpdatingEventArgs@Core@Text@Internal@UI@Windows@@PEAUIRichEditSmartLinkHandler@2@@Z`
- size: `631`
- prototype: `__int64 __fastcall(RichEdit::PlatformAPIs *__hidden this, struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, struct RichEdit::IRichEditSmartLinkHandler *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180043e7c`
- `0x18006ad18`
- `0x180138ae4`
- `0x1801f8440`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f85ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f85cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f85ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f85cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f865f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f865f`

## pseudocode

```c
__int64 __fastcall RichEdit::PlatformAPIs::ExecuteRichContentUpdating(
        RichEdit::PlatformAPIs *this,
        struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *a2,
        struct RichEdit::IRichEditSmartLinkHandler *a3)
{
  __int64 v5; // rax
  char v6; // al
  __int64 v7; // r8
  __int64 result; // rax
  __int64 (__fastcall *v9)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *); // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  int v13; // r15d
  __int64 v14; // rax
  void (__fastcall *v15)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  void (__fastcall *v16)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int16 *v18; // rdi
  const unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rbx
  __int64 v21; // rax
  HSTRING v22; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v24; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  __int128 v26; // [rsp+50h] [rbp-30h] BYREF
  __int128 v27; // [rsp+60h] [rbp-20h]
  unsigned __int16 *v28; // [rsp+70h] [rbp-10h]
  int v29; // [rsp+C0h] [rbp+40h] BYREF
  UINT32 length; // [rsp+C8h] [rbp+48h] BYREF

  if ( !a3 )
  {
    v5 = *(_QWORD *)a2;
    return (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v5 + 104))(
             a2,
             1);
  }
  v6 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *))(*(_QWORD *)a3 + 16LL))(a3);
  v7 = *(_QWORD *)a2;
  if ( v6 )
    return (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v7 + 104))(
             a2,
             1);
  v9 = *(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *))(v7 + 48);
  v25 = 0;
  v10 = v9(a2, &v25);
  v29 = 0;
  if ( v10 < 0
    || (*(int (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, int *))(*(_QWORD *)a2 + 88LL))(
         a2,
         &v29) < 0 )
  {
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *))(*(_QWORD *)a3 + 8LL))(a3);
  if ( v29 != 4 )
  {
    if ( (v11 & v29) == 0 || (_DWORD)v25 == HIDWORD(v25) )
      goto LABEL_14;
    v12 = *(_QWORD *)a3;
    v24 = 0;
    v13 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *, __int64, _QWORD, __int64 *))(v12 + 24))(
            a3,
            v25,
            HIDWORD(v25),
            &v24);
    if ( v13 >= 0 )
    {
      v14 = *(_QWORD *)a2;
      string = 0;
      v22 = 0;
      length = 0;
      v15 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(v14 + 72);
      WindowsDeleteString(0);
      v22 = 0;
      v15(a2, &v22);
      v16 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a2 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v16(a2, &string);
      v26 = 0;
      v28 = 0;
      v27 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v18 = CW32System::SysAllocString(StringRawBuffer);
      v19 = WindowsGetStringRawBuffer(v22, &length);
      v20 = CW32System::SysAllocString(v19);
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 112LL))(v24, (char *)&v26 + 4);
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 128LL))(v24, (char *)&v26 + 8);
      HIDWORD(v26) = v29;
      v21 = *(_QWORD *)a3;
      *((_QWORD *)&v27 + 1) = v18;
      v28 = v20;
      v13 = (*(__int64 (__fastcall **)(struct RichEdit::IRichEditSmartLinkHandler *, __int128 *))(v21 + 32))(a3, &v26);
      CW32System::SysFreeString(v18);
      CW32System::SysFreeString(v20);
      WindowsDeleteString(v22);
      v22 = 0;
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    if ( v13 < 0 )
      goto LABEL_14;
  }
  result = (**(__int64 (__fastcall ***)(struct RichEdit::IRichEditSmartLinkHandler *))a3)(a3);
  if ( (int)result < 0 )
  {
LABEL_14:
    v5 = *(_QWORD *)a2;
    return (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v5 + 104))(
             a2,
             1);
  }
  return result;
}

```

## disassembly

```asm
0x1801f8440  mov     [rsp-28h+arg_0], rbx
0x1801f8445  push    rbp
0x1801f8446  push    rsi
0x1801f8447  push    rdi
0x1801f8448  push    r14
0x1801f844a  push    r15
0x1801f844c  mov     rbp, rsp
0x1801f844f  sub     rsp, 80h
0x1801f8456  mov     r14, r8
0x1801f8459  mov     rsi, rdx
0x1801f845c  test    r8, r8
0x1801f845f  jnz     short loc_1801F8469
0x1801f8461  mov     rax, [rdx]
0x1801f8464  jmp     loc_1801F868E
0x1801f8469  mov     rax, [r8]
0x1801f846c  mov     rcx, r14
0x1801f846f  mov     rax, [rax+10h]
0x1801f8473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8478  mov     r8, [rsi]
0x1801f847b  mov     rcx, rsi
0x1801f847e  test    al, al
0x1801f8480  jz      short loc_1801F848B
0x1801f8482  mov     rax, [r8+68h]
0x1801f8486  jmp     loc_1801F8695
0x1801f848b  mov     rax, [r8+30h]
0x1801f848f  lea     rdx, [rbp+var_38]
0x1801f8493  mov     [rbp+var_38], 0
0x1801f849b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84a0  mov     [rbp+arg_10], 0
0x1801f84a7  test    eax, eax
0x1801f84a9  js      loc_1801F868B
0x1801f84af  mov     rax, [rsi]
0x1801f84b2  lea     rdx, [rbp+arg_10]
0x1801f84b6  mov     rcx, rsi
0x1801f84b9  mov     rax, [rax+58h]
0x1801f84bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84c2  test    eax, eax
0x1801f84c4  js      loc_1801F868B
0x1801f84ca  mov     rax, [r14]
0x1801f84cd  mov     rcx, r14
0x1801f84d0  mov     rax, [rax+8]
0x1801f84d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84d9  mov     ecx, [rbp+arg_10]
0x1801f84dc  cmp     ecx, 4
0x1801f84df  jz      loc_1801F8679
0x1801f84e5  test    ecx, eax
0x1801f84e7  jz      loc_1801F868B
0x1801f84ed  mov     rdx, [rbp+var_38]
0x1801f84f1  mov     r8d, dword ptr [rbp+var_38+4]
0x1801f84f5  cmp     edx, r8d
0x1801f84f8  jz      loc_1801F868B
0x1801f84fe  mov     rax, [r14]
0x1801f8501  lea     r9, [rbp+var_40]
0x1801f8505  mov     rcx, r14
0x1801f8508  mov     [rbp+var_40], 0
0x1801f8510  mov     rax, [rax+18h]
0x1801f8514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8519  mov     r15d, eax
0x1801f851c  test    eax, eax
0x1801f851e  js      loc_1801F866B
0x1801f8524  mov     rax, [rsi]
0x1801f8527  xor     ecx, ecx; string
0x1801f8529  mov     [rbp+string], 0
0x1801f8531  mov     [rbp+var_50], 0
0x1801f8539  mov     [rbp+length], 0
0x1801f8540  mov     rbx, [rax+48h]
0x1801f8544  call    cs:__imp_WindowsDeleteString
0x1801f854b  nop     dword ptr [rax+rax+00h]
0x1801f8550  lea     rdx, [rbp+var_50]
0x1801f8554  mov     [rbp+var_50], 0
0x1801f855c  mov     rcx, rsi
0x1801f855f  mov     rax, rbx
0x1801f8562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8567  mov     rax, [rsi]
0x1801f856a  mov     rcx, [rbp+string]; string
0x1801f856e  mov     rbx, [rax+38h]
0x1801f8572  call    cs:__imp_WindowsDeleteString
0x1801f8579  nop     dword ptr [rax+rax+00h]
0x1801f857e  lea     rdx, [rbp+string]
0x1801f8582  mov     [rbp+string], 0
0x1801f858a  mov     rcx, rsi
0x1801f858d  mov     rax, rbx
0x1801f8590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8595  mov     rcx, [rbp+string]; string
0x1801f8599  lea     rdx, [rbp+length]; length
0x1801f859d  xorps   xmm0, xmm0
0x1801f85a0  xor     eax, eax
0x1801f85a2  movups  [rbp+var_30], xmm0
0x1801f85a6  mov     [rbp+var_10], rax
0x1801f85aa  movups  [rbp+var_20], xmm0
0x1801f85ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f85b5  nop     dword ptr [rax+rax+00h]
0x1801f85ba  mov     rcx, rax; unsigned __int16 *
0x1801f85bd  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801f85c2  mov     rcx, [rbp+var_50]; string
0x1801f85c6  lea     rdx, [rbp+length]; length
0x1801f85ca  mov     rdi, rax
0x1801f85cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f85d4  nop     dword ptr [rax+rax+00h]
0x1801f85d9  mov     rcx, rax; unsigned __int16 *
0x1801f85dc  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801f85e1  mov     rcx, [rbp+var_40]
0x1801f85e5  mov     rbx, rax
0x1801f85e8  mov     rdx, [rcx]
0x1801f85eb  mov     rax, [rdx+70h]
0x1801f85ef  lea     rdx, [rbp+var_30+4]
0x1801f85f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f85f8  mov     rcx, [rbp+var_40]
0x1801f85fc  mov     rdx, [rcx]
0x1801f85ff  mov     rax, [rdx+80h]
0x1801f8606  lea     rdx, [rbp+var_30+8]
0x1801f860a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f860f  mov     eax, [rbp+arg_10]
0x1801f8612  lea     rdx, [rbp+var_30]
0x1801f8616  mov     dword ptr [rbp+var_30+0Ch], eax
0x1801f8619  mov     rcx, r14
0x1801f861c  mov     rax, [r14]
0x1801f861f  mov     qword ptr [rbp+var_20+8], rdi
0x1801f8623  mov     [rbp+var_10], rbx
0x1801f8627  mov     rax, [rax+20h]
0x1801f862b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8630  mov     rcx, rdi; unsigned __int16 *
0x1801f8633  mov     r15d, eax
0x1801f8636  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801f863b  mov     rcx, rbx; unsigned __int16 *
0x1801f863e  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801f8643  mov     rcx, [rbp+var_50]; string
0x1801f8647  call    cs:__imp_WindowsDeleteString
0x1801f864e  nop     dword ptr [rax+rax+00h]
0x1801f8653  mov     rcx, [rbp+string]; string
0x1801f8657  mov     [rbp+var_50], 0
0x1801f865f  call    cs:__imp_WindowsDeleteString
0x1801f8666  nop     dword ptr [rax+rax+00h]
0x1801f866b  lea     rcx, [rbp+var_40]
0x1801f866f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f8674  test    r15d, r15d
0x1801f8677  js      short loc_1801F868B
0x1801f8679  mov     rax, [r14]
0x1801f867c  mov     rcx, r14
0x1801f867f  mov     rax, [rax]
0x1801f8682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8687  test    eax, eax
0x1801f8689  jns     short loc_1801F869F
0x1801f868b  mov     rax, [rsi]
0x1801f868e  mov     rax, [rax+68h]
0x1801f8692  mov     rcx, rsi
0x1801f8695  mov     edx, 1
0x1801f869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f869f  mov     rbx, [rsp+80h+arg_0]
0x1801f86a7  add     rsp, 80h
0x1801f86ae  pop     r15
0x1801f86b0  pop     r14
0x1801f86b2  pop     rdi
0x1801f86b3  pop     rsi
0x1801f86b4  pop     rbp
0x1801f86b5  retn
```
