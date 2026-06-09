# IsFeedbackHubAppInstalled(int *)

- ea: `0x14001920c`
- end: `0x1400193c5`
- name: `?IsFeedbackHubAppInstalled@@YAJPEAH@Z`
- size: `441`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x14000ac50`
- `0x14001920c`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140019288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001932a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140019288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001932a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400192cc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400192cc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140019239`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140019239`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IsFeedbackHubAppInstalled(int *a1)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // ebx
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // rsi
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  _QWORD *v13; // rcx
  _QWORD *v14; // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-40h] BYREF
  int v17; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF

  v17 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v17, 0);
  if ( v17 != 3 )
    return 6148104;
  if ( !a1 )
    return 2147500035LL;
  v16 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x1400193C4LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v16);
  if ( ActivationFactory < 0 )
  {
    v7 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
    }
    return (unsigned int)ActivationFactory;
  }
  v15[0] = 0;
  v8 = v16;
  v9 = *v16;
  string = 0;
  v10 = WindowsCreateStringReference(L"Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe!App", 0x2Eu, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    __debugbreak();
  }
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, _BYTE *))(v9 + 312))(v8, 0, string, v15);
  if ( ActivationFactory < 0 )
  {
    v13 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    }
    return (unsigned int)ActivationFactory;
  }
  *a1 = v15[0];
  v14 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x14001920c  push    rbp
0x14001920e  push    rbx
0x14001920f  push    rsi
0x140019210  push    rdi
0x140019211  mov     rbp, rsp
0x140019214  sub     rsp, 78h
0x140019218  mov     rax, cs:__security_cookie
0x14001921f  xor     rax, rsp
0x140019222  mov     [rbp+var_10], rax
0x140019226  mov     rdi, rcx
0x140019229  mov     [rbp+var_38], 0
0x140019230  xor     r8d, r8d
0x140019233  lea     rdx, [rbp+var_38]
0x140019237  xor     ecx, ecx
0x140019239  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140019240  nop     dword ptr [rax+rax+00h]
0x140019245  cmp     [rbp+var_38], 3
0x140019249  jz      short loc_140019255
0x14001924b  mov     eax, 5DD008h
0x140019250  jmp     loc_14001939F
0x140019255  test    rdi, rdi
0x140019258  jnz     short loc_140019264
0x14001925a  mov     eax, 80004003h
0x14001925f  jmp     loc_14001939F
0x140019264  mov     [rbp+var_40], 0
0x14001926c  mov     [rbp+string], 0
0x140019274  lea     r9, [rbp+string]; string
0x140019278  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001927c  mov     edx, 28h ; '('; length
0x140019281  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x140019288  call    cs:__imp_WindowsCreateStringReference
0x14001928f  nop     dword ptr [rax+rax+00h]
0x140019294  test    eax, eax
0x140019296  js      loc_1400193BD
0x14001929c  mov     rbx, [rbp+string]
0x1400192a0  mov     rcx, [rbp+var_40]
0x1400192a4  test    rcx, rcx
0x1400192a7  jz      short loc_1400192BE
0x1400192a9  mov     [rbp+var_40], 0
0x1400192b1  mov     rax, [rcx]
0x1400192b4  mov     rax, [rax+10h]
0x1400192b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400192bd  nop
0x1400192be  lea     r8, [rbp+var_40]
0x1400192c2  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1400192c9  mov     rcx, rbx
0x1400192cc  call    cs:__imp_RoGetActivationFactory
0x1400192d3  nop     dword ptr [rax+rax+00h]
0x1400192d8  mov     ebx, eax
0x1400192da  test    eax, eax
0x1400192dc  jns     short loc_140019303
0x1400192de  mov     rcx, [rbp+var_40]
0x1400192e2  test    rcx, rcx
0x1400192e5  jz      short loc_1400192FC
0x1400192e7  mov     [rbp+var_40], 0
0x1400192ef  mov     rdx, [rcx]
0x1400192f2  mov     rax, [rdx+10h]
0x1400192f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400192fb  nop
0x1400192fc  mov     eax, ebx
0x1400192fe  jmp     loc_14001939F
0x140019303  mov     [rbp+var_48], 0
0x140019307  mov     rbx, [rbp+var_40]
0x14001930b  mov     rsi, [rbx]
0x14001930e  mov     [rbp+string], 0
0x140019316  lea     r9, [rbp+string]; string
0x14001931a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001931e  mov     edx, 2Eh ; '.'; length
0x140019323  lea     rcx, aMicrosoftWindo_0; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x14001932a  call    cs:__imp_WindowsCreateStringReference
0x140019331  nop     dword ptr [rax+rax+00h]
0x140019336  test    eax, eax
0x140019338  js      short loc_1400193B5
0x14001933a  lea     r9, [rbp+var_48]
0x14001933e  mov     r8, [rbp+string]
0x140019342  xor     edx, edx
0x140019344  mov     rcx, rbx
0x140019347  mov     rax, [rsi+138h]
0x14001934e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019353  mov     ebx, eax
0x140019355  test    eax, eax
0x140019357  jns     short loc_140019379
0x140019359  mov     rcx, [rbp+var_40]
0x14001935d  test    rcx, rcx
0x140019360  jz      short loc_140019377
0x140019362  mov     [rbp+var_40], 0
0x14001936a  mov     rdx, [rcx]
0x14001936d  mov     rax, [rdx+10h]
0x140019371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019376  nop
0x140019377  jmp     short loc_1400192FC
0x140019379  movzx   eax, [rbp+var_48]
0x14001937d  mov     [rdi], eax
0x14001937f  mov     rcx, [rbp+var_40]
0x140019383  test    rcx, rcx
0x140019386  jz      short loc_14001939D
0x140019388  mov     [rbp+var_40], 0
0x140019390  mov     rax, [rcx]
0x140019393  mov     rax, [rax+10h]
0x140019397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001939c  nop
0x14001939d  xor     eax, eax
0x14001939f  mov     rcx, [rbp+var_10]
0x1400193a3  xor     rcx, rsp; StackCookie
0x1400193a6  call    __security_check_cookie
0x1400193ab  add     rsp, 78h
0x1400193af  pop     rdi
0x1400193b0  pop     rsi
0x1400193b1  pop     rbx
0x1400193b2  pop     rbp
0x1400193b3  retn
0x1400193b5  mov     ecx, eax; this
0x1400193b7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400193bc  int     3; Trap to Debugger
0x1400193bd  mov     ecx, eax; this
0x1400193bf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
