# KeyboardOverriderDispatcher::RuntimeClassInitialize(Microsoft::WRL::ComPtr<IMessageSession> &)

- ea: `0x18013125c`
- end: `0x1801313fd`
- name: `?RuntimeClassInitialize@KeyboardOverriderDispatcher@@QEAAJAEAV?$ComPtr@UIMessageSession@@@WRL@Microsoft@@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18009457c`

## callees

- `0x180012b74`
- `0x18002009c`
- `0x180030260`
- `0x18008daac`
- `0x18008ead4`
- `0x18013125c`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801312bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801312bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180131319`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180131319`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x180131355`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x180131355`

## string_xrefs

- `0x1801312cb`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`
- `0x18013132d`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`

## pseudocode

```c
__int64 __fastcall KeyboardOverriderDispatcher::RuntimeClassInitialize(__int64 a1, __int64 a2)
{
  __int64 *v2; // rdi
  const char *v5; // r9
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, PSECURITY_DESCRIPTOR, const wchar_t *, __int64); // rbx
  int v8; // ebx
  __int64 v9; // rdx
  _QWORD *v10; // rsi
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, _QWORD); // rdi
  const wchar_t *v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v15; // [rsp+60h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+18h] BYREF

  v2 = (__int64 *)(a1 + 752);
  v15 = 0;
  Microsoft::WRL::ComPtr<IMPCFocusTarget>::operator=(a1 + 752, a2);
  SecurityDescriptor = 0;
  if ( !IsEdition(0x3DDA1u) )
    return 2147942405LL;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;0x01;;;SY)(A;;0x01;;;BA)(A;;0x01;;;AU)(A;;0x01;;;S-1-15-3-1024-681439765-775820322-820945240-645585533-5"
           "24008629-2436029359-2385409943-1660172268)",
          1u,
          &SecurityDescriptor,
          0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x47,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib\\k"
                           "eyboardoverriderdispatcher.cpp",
             v5);
  v6 = *v2;
  v7 = *(__int64 (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, const wchar_t *, __int64))(*(_QWORD *)v6 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 768);
  v8 = v7(v6, SecurityDescriptor, L"KeyboardOverriderDispatcher", a1 + 768);
  LocalFree(SecurityDescriptor);
  if ( v8 < 0 )
  {
    v9 = 82;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib\\keyboard"
                    "overriderdispatcher.cpp",
      (const char *)(unsigned int)v8,
      (int)v13);
    return (unsigned int)v8;
  }
  v10 = (_QWORD *)(a1 + 760);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 760);
  v8 = CoreUIFactoryCreate(a1 + 760);
  if ( v8 < 0 )
  {
    v9 = 84;
    goto LABEL_7;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)*v10 + 24LL))(
         *v10,
         &GUID_2c657f91_d10a_486d_b793_25a3c5057719,
         &v15);
  if ( v8 < 0 )
  {
    v9 = 88;
    goto LABEL_7;
  }
  v11 = *v10;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 776);
  v13 = L"System\\LowLevelKeyboardOverriderCallback";
  v8 = v12(v11, a1, 0, v15);
  if ( v8 < 0 )
  {
    v9 = 96;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x18013125c  mov     [rsp+arg_8], rbx
0x180131261  mov     [rsp+arg_18], rbp
0x180131266  push    rsi
0x180131267  push    rdi
0x180131268  push    r14
0x18013126a  sub     rsp, 40h
0x18013126e  lea     rdi, [rcx+2F0h]
0x180131275  mov     [rsp+58h+arg_0], 0
0x18013127d  mov     rbp, rcx
0x180131280  mov     rcx, rdi
0x180131283  call    ??4?$ComPtr@UIMPCFocusTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMPCFocusTarget>::operator=(Microsoft::WRL::ComPtr<IMPCFocusTarget> const &)
0x180131288  mov     ecx, 3DDA1h; unsigned __int64
0x18013128d  mov     [rsp+58h+SecurityDescriptor], 0
0x180131296  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x18013129b  test    al, al
0x18013129d  jnz     short loc_1801312A9
0x18013129f  mov     eax, 80070005h
0x1801312a4  jmp     loc_1801313EA
0x1801312a9  xor     r9d, r9d; SecurityDescriptorSize
0x1801312ac  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1801312b1  lea     rcx, aDA0x01SyA0x01B; "D:(A;;0x01;;;SY)(A;;0x01;;;BA)(A;;0x01;"...
0x1801312b8  lea     edx, [r9+1]; StringSDRevision
0x1801312bc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801312c2  test    eax, eax
0x1801312c4  jnz     short loc_1801312DF
0x1801312c6  mov     rcx, [rsp+58h]; this
0x1801312cb  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801312d2  lea     edx, [rax+47h]; void *
0x1801312d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801312da  jmp     loc_1801313EA
0x1801312df  mov     rdi, [rdi]
0x1801312e2  lea     r14, [rbp+300h]
0x1801312e9  mov     rcx, r14
0x1801312ec  mov     rax, [rdi]
0x1801312ef  mov     rbx, [rax+38h]
0x1801312f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801312f8  mov     rdx, [rsp+58h+SecurityDescriptor]
0x1801312fd  lea     r8, aKeyboardoverri_0; "KeyboardOverriderDispatcher"
0x180131304  mov     r9, r14
0x180131307  mov     rcx, rdi
0x18013130a  mov     rax, rbx
0x18013130d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131312  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x180131317  mov     ebx, eax
0x180131319  call    cs:__imp_LocalFree
0x18013131f  test    ebx, ebx
0x180131321  jns     short loc_180131343
0x180131323  mov     edx, 52h ; 'R'; void *
0x180131328  mov     rcx, [rsp+58h]; this
0x18013132d  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x180131334  mov     r9d, ebx; char *
0x180131337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013133c  mov     eax, ebx
0x18013133e  jmp     loc_1801313EA
0x180131343  lea     rsi, [rbp+2F8h]
0x18013134a  mov     rcx, rsi
0x18013134d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180131352  mov     rcx, rsi
0x180131355  call    cs:__imp_CoreUIFactoryCreate
0x18013135b  mov     ebx, eax
0x18013135d  test    eax, eax
0x18013135f  jns     short loc_180131368
0x180131361  mov     edx, 54h ; 'T'
0x180131366  jmp     short loc_180131328
0x180131368  mov     rcx, [rsi]
0x18013136b  lea     r8, [rsp+58h+arg_0]
0x180131370  lea     rdx, _GUID_2c657f91_d10a_486d_b793_25a3c5057719
0x180131377  mov     rax, [rcx]
0x18013137a  mov     rax, [rax+18h]
0x18013137e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131383  mov     ebx, eax
0x180131385  test    eax, eax
0x180131387  jns     short loc_180131390
0x180131389  mov     edx, 58h ; 'X'
0x18013138e  jmp     short loc_180131328
0x180131390  mov     rsi, [rsi]
0x180131393  lea     rbx, [rbp+308h]
0x18013139a  mov     rcx, rbx
0x18013139d  mov     rax, [rsi]
0x1801313a0  mov     rdi, [rax+20h]
0x1801313a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801313a9  mov     rdx, [r14]
0x1801313ac  lea     rax, aSystemLowlevel; "System\\LowLevelKeyboardOverriderCallba"...
0x1801313b3  mov     r9d, [rsp+58h+arg_0]
0x1801313b8  xor     r8d, r8d
0x1801313bb  mov     [rsp+58h+var_28], rbx
0x1801313c0  mov     rcx, rsi
0x1801313c3  mov     [rsp+58h+var_30], rdx
0x1801313c8  mov     rdx, rbp
0x1801313cb  mov     [rsp+58h+var_38], rax
0x1801313d0  mov     rax, rdi
0x1801313d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801313d8  mov     ebx, eax
0x1801313da  test    eax, eax
0x1801313dc  jns     short loc_1801313E8
0x1801313de  mov     edx, 60h ; '`'
0x1801313e3  jmp     loc_180131328
0x1801313e8  xor     eax, eax
0x1801313ea  mov     rbx, [rsp+58h+arg_8]
0x1801313ef  mov     rbp, [rsp+58h+arg_18]
0x1801313f4  add     rsp, 40h
0x1801313f8  pop     r14
0x1801313fa  pop     rdi
0x1801313fb  pop     rsi
0x1801313fc  retn
```
