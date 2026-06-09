# _lambda_0a0260c43a5fa9f240b6fbebbf77784e_::operator()

- ea: `0x18006ae74`
- end: `0x18006afa6`
- name: `_lambda_0a0260c43a5fa9f240b6fbebbf77784e_::operator()`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006c000`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x18006ae74`
- `0x180070d90`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006af70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006af70`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_0a0260c43a5fa9f240b6fbebbf77784e_::operator()(
        __int64 *a1,
        struct Windows::Foundation::IAsyncAction *a2)
{
  unsigned int v3; // ebp
  HSTRING *v4; // rcx
  HSTRING v5; // rbx
  HSTRING v6; // r14
  WebRuntimeDiagnostics::TargetContext *v7; // rdi
  __int64 v8; // rdi
  _QWORD v11[4]; // [rsp+28h] [rbp-20h] BYREF
  struct Windows::Foundation::IAsyncAction *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = a2;
  v3 = 0;
  while ( *(_QWORD *)(*a1 + 280) )
  {
    v4 = *(HSTRING **)(*(_QWORD *)(*a1 + 256) + 8 * (*(_QWORD *)(*a1 + 272) & (*(_QWORD *)(*a1 + 264) - 1LL)));
    v5 = *v4;
    v6 = v4[1];
    v11[0] = v6;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v11);
    v12 = 0;
    WindowsDeleteString(0);
    v7 = *(WebRuntimeDiagnostics::TargetContext **)(*a1 + 120);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    v3 = WebRuntimeDiagnostics::TargetContext::PostMessageAsync(v7, v5, &v12);
    if ( !v3 )
      (*(void (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, 0);
    v8 = *a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(*(_QWORD *)(*(_QWORD *)(*a1 + 256) + 8 * (*(_QWORD *)(*a1 + 272) & (*(_QWORD *)(*a1 + 264) - 1LL))) + 8LL);
    if ( (*(_QWORD *)(v8 + 280))-- == 1 )
      *(_QWORD *)(v8 + 272) = 0;
    else
      ++*(_QWORD *)(v8 + 272);
    WindowsDeleteString(v5);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v11);
  }
  return v3;
}

```

## disassembly

```asm
0x18006ae74  mov     [rsp+arg_10], rbx
0x18006ae79  mov     [rsp+arg_18], rbp
0x18006ae7e  mov     [rsp+arg_8], rdx
0x18006ae83  push    rsi
0x18006ae84  push    rdi
0x18006ae85  push    r14
0x18006ae87  sub     rsp, 30h
0x18006ae8b  mov     rsi, rcx
0x18006ae8e  xor     ebp, ebp
0x18006ae90  mov     rax, [rsi]
0x18006ae93  cmp     qword ptr [rax+118h], 0
0x18006ae9b  jz      loc_18006AF91
0x18006aea1  mov     rcx, [rax+108h]
0x18006aea8  dec     rcx
0x18006aeab  and     rcx, [rax+110h]
0x18006aeb2  mov     rax, [rax+100h]
0x18006aeb9  mov     rcx, [rax+rcx*8]
0x18006aebd  mov     rbx, [rcx]
0x18006aec0  mov     [rsp+48h+var_28], rbx
0x18006aec5  mov     r14, [rcx+8]
0x18006aec9  mov     [rsp+48h+var_20], r14
0x18006aece  lea     rcx, [rsp+48h+var_20]
0x18006aed3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006aed8  nop
0x18006aed9  mov     [rsp+48h+arg_8], 0
0x18006aee2  xor     ecx, ecx; string
0x18006aee4  call    cs:__imp_WindowsDeleteString
0x18006aeea  mov     [rsp+48h+arg_0], rbx
0x18006aeef  mov     rax, [rsi]
0x18006aef2  mov     rdi, [rax+78h]
0x18006aef6  lea     rcx, [rsp+48h+arg_8]
0x18006aefb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006af00  lea     r8, [rsp+48h+arg_8]; struct Windows::Foundation::IAsyncAction **
0x18006af05  mov     rdx, rbx; HSTRING
0x18006af08  mov     rcx, rdi; this
0x18006af0b  call    ?PostMessageAsync@TargetContext@WebRuntimeDiagnostics@@UEAAJPEAUHSTRING__@@PEAPEAUIAsyncAction@Foundation@Windows@@@Z; WebRuntimeDiagnostics::TargetContext::PostMessageAsync(HSTRING__ *,Windows::Foundation::IAsyncAction * *)
0x18006af10  mov     ebp, eax
0x18006af12  test    eax, eax
0x18006af14  jnz     short loc_18006AF27
0x18006af16  mov     rdx, [r14]
0x18006af19  mov     rax, [rdx+18h]
0x18006af1d  xor     edx, edx
0x18006af1f  mov     rcx, r14
0x18006af22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af27  mov     rdi, [rsi]
0x18006af2a  mov     rcx, [rdi+108h]
0x18006af31  dec     rcx
0x18006af34  and     rcx, [rdi+110h]
0x18006af3b  mov     rax, [rdi+100h]
0x18006af42  mov     rcx, [rax+rcx*8]
0x18006af46  add     rcx, 8
0x18006af4a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006af4f  sub     qword ptr [rdi+118h], 1
0x18006af57  jnz     short loc_18006AF66
0x18006af59  mov     qword ptr [rdi+110h], 0
0x18006af64  jmp     short loc_18006AF6D
0x18006af66  inc     qword ptr [rdi+110h]
0x18006af6d  mov     rcx, rbx; string
0x18006af70  call    cs:__imp_WindowsDeleteString
0x18006af76  nop
0x18006af77  lea     rcx, [rsp+48h+arg_8]
0x18006af7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006af81  nop
0x18006af82  lea     rcx, [rsp+48h+var_20]
0x18006af87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006af8c  jmp     loc_18006AE90
0x18006af91  mov     eax, ebp
0x18006af93  mov     rbx, [rsp+48h+arg_10]
0x18006af98  mov     rbp, [rsp+48h+arg_18]
0x18006af9d  add     rsp, 30h
0x18006afa1  pop     r14
0x18006afa3  pop     rdi
0x18006afa4  pop     rsi
0x18006afa5  retn
```
