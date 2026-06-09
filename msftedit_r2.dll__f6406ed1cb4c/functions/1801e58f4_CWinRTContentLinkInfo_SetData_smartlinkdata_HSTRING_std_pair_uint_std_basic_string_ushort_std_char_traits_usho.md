# CWinRTContentLinkInfo::SetData(_smartlinkdata *,HSTRING__ *,std::pair<uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const * const)

- ea: `0x1801e58f4`
- end: `0x1801e5a70`
- name: `?SetData@CWinRTContentLinkInfo@@QEAAJPEAU_smartlinkdata@@PEAUHSTRING__@@QEBU?$pair@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801e6240`

## callees

- `0x1800441ac`
- `0x18006ad18`
- `0x1800caaa4`
- `0x180111748`
- `0x18013ce80`
- `0x1801e58f4`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801e59c2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801e59c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e5a3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e5a3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e5939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e5979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e59e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e5939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e5979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e59e1`

## string_xrefs

- `0x1801e598f`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall CWinRTContentLinkInfo::SetData(HSTRING *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 *v5; // rcx
  UINT32 v9; // eax
  __int64 v10; // r9
  __int64 v11; // r8
  int i; // ecx
  const WCHAR *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  UINT32 v16; // eax
  __int64 v17; // rsi
  void (__fastcall *v18)(__int64, HSTRING, HSTRING *); // rdi
  __int64 v20; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h]

  v5 = *(unsigned __int16 **)(a2 + 32);
  string = 0;
  v9 = CW32System::SysStringLen(v5);
  WindowsCreateString(*(PCNZWCH *)(a2 + 32), v9, a1 + 6);
  v11 = *(unsigned int *)(a2 + 12);
  for ( i = 0; i < 2; ++i )
  {
    if ( *(_DWORD *)(a4 + 40LL * i) == (_DWORD)v11 )
    {
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                             a4 + 8 + 40LL * i,
                             5LL * i,
                             v11,
                             v10);
      WindowsCreateString(v13, *(_DWORD *)(a4 + 8 * v14 + 24), a1 + 8);
      break;
    }
  }
  v20 = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v15 = v23;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  RoGetActivationFactory(v15, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v20);
  v16 = CW32System::SysStringLen(*(unsigned __int16 **)(a2 + 24));
  WindowsCreateString(*(PCNZWCH *)(a2 + 24), v16, &string);
  v17 = v20;
  v18 = *(void (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v20 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 7);
  v18(v17, string, a1 + 7);
  (*((void (__fastcall **)(HSTRING *, _QWORD))*a1 + 7))(a1, *(unsigned int *)(a2 + 16));
  (*((void (__fastcall **)(HSTRING *, __int64))*a1 + 9))(a1, a3);
  WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x1801e58f4  push    rbp
0x1801e58f6  push    rbx
0x1801e58f7  push    rsi
0x1801e58f8  push    rdi
0x1801e58f9  push    r12
0x1801e58fb  push    r14
0x1801e58fd  push    r15
0x1801e58ff  mov     rbp, rsp
0x1801e5902  sub     rsp, 60h
0x1801e5906  mov     rax, cs:__security_cookie
0x1801e590d  xor     rax, rsp
0x1801e5910  mov     [rbp+var_10], rax
0x1801e5914  mov     r15, rcx
0x1801e5917  xor     edi, edi
0x1801e5919  mov     rcx, [rdx+20h]; unsigned __int16 *
0x1801e591d  mov     rbx, r9
0x1801e5920  mov     [rbp+string], rdi
0x1801e5924  mov     r12, r8
0x1801e5927  mov     r14, rdx
0x1801e592a  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x1801e592f  mov     rcx, [r14+20h]; sourceString
0x1801e5933  lea     r8, [r15+30h]; string
0x1801e5937  mov     edx, eax; length
0x1801e5939  call    cs:__imp_WindowsCreateString
0x1801e5940  nop     dword ptr [rax+rax+00h]
0x1801e5945  mov     r8d, [r14+0Ch]
0x1801e5949  mov     ecx, edi
0x1801e594b  cmp     ecx, 2
0x1801e594e  jge     short loc_1801E5985
0x1801e5950  movsxd  rax, ecx
0x1801e5953  lea     rdx, [rax+rax*4]
0x1801e5957  cmp     [rbx+rdx*8], r8d
0x1801e595b  jz      short loc_1801E5961
0x1801e595d  inc     ecx
0x1801e595f  jmp     short loc_1801E594B
0x1801e5961  lea     rcx, [rbx+8]
0x1801e5965  lea     rcx, [rcx+rdx*8]
0x1801e5969  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801e596e  mov     edx, [rbx+rdx*8+18h]; length
0x1801e5972  lea     r8, [r15+40h]; string
0x1801e5976  mov     rcx, rax; sourceString
0x1801e5979  call    cs:__imp_WindowsCreateString
0x1801e5980  nop     dword ptr [rax+rax+00h]
0x1801e5985  mov     r9d, 16h; unsigned int
0x1801e598b  mov     [rbp+var_40], rdi
0x1801e598f  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1801e5996  mov     [rbp+var_18], rdi
0x1801e599a  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e599e  lea     r8d, [r9+1]; unsigned int
0x1801e59a2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e59a7  mov     rbx, [rbp+var_18]
0x1801e59ab  lea     rcx, [rbp+var_40]
0x1801e59af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e59b4  lea     r8, [rbp+var_40]
0x1801e59b8  mov     rcx, rbx
0x1801e59bb  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1801e59c2  call    cs:__imp_RoGetActivationFactory
0x1801e59c9  nop     dword ptr [rax+rax+00h]
0x1801e59ce  mov     rcx, [r14+18h]; unsigned __int16 *
0x1801e59d2  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x1801e59d7  mov     rcx, [r14+18h]; sourceString
0x1801e59db  lea     r8, [rbp+string]; string
0x1801e59df  mov     edx, eax; length
0x1801e59e1  call    cs:__imp_WindowsCreateString
0x1801e59e8  nop     dword ptr [rax+rax+00h]
0x1801e59ed  mov     rsi, [rbp+var_40]
0x1801e59f1  lea     rcx, [r15+38h]
0x1801e59f5  mov     rax, [rsi]
0x1801e59f8  mov     rdi, [rax+30h]
0x1801e59fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e5a01  mov     rdx, [rbp+string]
0x1801e5a05  lea     r8, [r15+38h]
0x1801e5a09  mov     rcx, rsi
0x1801e5a0c  mov     rax, rdi
0x1801e5a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e5a14  mov     rax, [r15]
0x1801e5a17  mov     rcx, r15
0x1801e5a1a  mov     edx, [r14+10h]
0x1801e5a1e  mov     rax, [rax+38h]
0x1801e5a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e5a27  mov     rax, [r15]
0x1801e5a2a  mov     rdx, r12
0x1801e5a2d  mov     rcx, r15
0x1801e5a30  mov     rax, [rax+48h]
0x1801e5a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e5a39  mov     rcx, [rbp+string]; string
0x1801e5a3d  call    cs:__imp_WindowsDeleteString
0x1801e5a44  nop     dword ptr [rax+rax+00h]
0x1801e5a49  lea     rcx, [rbp+var_40]
0x1801e5a4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e5a52  xor     eax, eax
0x1801e5a54  mov     rcx, [rbp+var_10]
0x1801e5a58  xor     rcx, rsp; StackCookie
0x1801e5a5b  call    __security_check_cookie
0x1801e5a60  add     rsp, 60h
0x1801e5a64  pop     r15
0x1801e5a66  pop     r14
0x1801e5a68  pop     r12
0x1801e5a6a  pop     rdi
0x1801e5a6b  pop     rsi
0x1801e5a6c  pop     rbx
0x1801e5a6d  pop     rbp
0x1801e5a6e  retn
```
