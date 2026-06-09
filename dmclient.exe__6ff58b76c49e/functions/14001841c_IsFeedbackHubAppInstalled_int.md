# IsFeedbackHubAppInstalled(int *)

- ea: `0x14001841c`
- end: `0x1400185bc`
- name: `?IsFeedbackHubAppInstalled@@YAJPEAH@Z`
- size: `416`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c47c`

## callees

- `0x14000a9f0`
- `0x14001841c`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140018492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140018528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140018492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140018528`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400184d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400184d0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140018449`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140018449`

## pseudocode

```c
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
    JUMPOUT(0x1400185BBLL);
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
0x14001841c  push    rbp
0x14001841e  push    rbx
0x14001841f  push    rsi
0x140018420  push    rdi
0x140018421  mov     rbp, rsp
0x140018424  sub     rsp, 78h
0x140018428  mov     rax, cs:__security_cookie
0x14001842f  xor     rax, rsp
0x140018432  mov     [rbp+var_10], rax
0x140018436  mov     rdi, rcx
0x140018439  mov     [rbp+var_38], 0
0x140018440  xor     r8d, r8d
0x140018443  lea     rdx, [rbp+var_38]
0x140018447  xor     ecx, ecx
0x140018449  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x14001844f  cmp     [rbp+var_38], 3
0x140018453  jz      short loc_14001845F
0x140018455  mov     eax, 5DD008h
0x14001845a  jmp     loc_140018597
0x14001845f  test    rdi, rdi
0x140018462  jnz     short loc_14001846E
0x140018464  mov     eax, 80004003h
0x140018469  jmp     loc_140018597
0x14001846e  mov     [rbp+var_40], 0
0x140018476  mov     [rbp+string], 0
0x14001847e  lea     r9, [rbp+string]; string
0x140018482  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140018486  mov     edx, 28h ; '('; length
0x14001848b  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x140018492  call    cs:__imp_WindowsCreateStringReference
0x140018498  test    eax, eax
0x14001849a  js      loc_1400185B4
0x1400184a0  mov     rbx, [rbp+string]
0x1400184a4  mov     rcx, [rbp+var_40]
0x1400184a8  test    rcx, rcx
0x1400184ab  jz      short loc_1400184C2
0x1400184ad  mov     [rbp+var_40], 0
0x1400184b5  mov     rax, [rcx]
0x1400184b8  mov     rax, [rax+10h]
0x1400184bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400184c1  nop
0x1400184c2  lea     r8, [rbp+var_40]
0x1400184c6  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1400184cd  mov     rcx, rbx
0x1400184d0  call    cs:__imp_RoGetActivationFactory
0x1400184d6  mov     ebx, eax
0x1400184d8  test    eax, eax
0x1400184da  jns     short loc_140018501
0x1400184dc  mov     rcx, [rbp+var_40]
0x1400184e0  test    rcx, rcx
0x1400184e3  jz      short loc_1400184FA
0x1400184e5  mov     [rbp+var_40], 0
0x1400184ed  mov     rdx, [rcx]
0x1400184f0  mov     rax, [rdx+10h]
0x1400184f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400184f9  nop
0x1400184fa  mov     eax, ebx
0x1400184fc  jmp     loc_140018597
0x140018501  mov     [rbp+var_48], 0
0x140018505  mov     rbx, [rbp+var_40]
0x140018509  mov     rsi, [rbx]
0x14001850c  mov     [rbp+string], 0
0x140018514  lea     r9, [rbp+string]; string
0x140018518  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001851c  mov     edx, 2Eh ; '.'; length
0x140018521  lea     rcx, aMicrosoftWindo_0; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x140018528  call    cs:__imp_WindowsCreateStringReference
0x14001852e  test    eax, eax
0x140018530  js      short loc_1400185AC
0x140018532  lea     r9, [rbp+var_48]
0x140018536  mov     r8, [rbp+string]
0x14001853a  xor     edx, edx
0x14001853c  mov     rcx, rbx
0x14001853f  mov     rax, [rsi+138h]
0x140018546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001854b  mov     ebx, eax
0x14001854d  test    eax, eax
0x14001854f  jns     short loc_140018571
0x140018551  mov     rcx, [rbp+var_40]
0x140018555  test    rcx, rcx
0x140018558  jz      short loc_14001856F
0x14001855a  mov     [rbp+var_40], 0
0x140018562  mov     rdx, [rcx]
0x140018565  mov     rax, [rdx+10h]
0x140018569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001856e  nop
0x14001856f  jmp     short loc_1400184FA
0x140018571  movzx   eax, [rbp+var_48]
0x140018575  mov     [rdi], eax
0x140018577  mov     rcx, [rbp+var_40]
0x14001857b  test    rcx, rcx
0x14001857e  jz      short loc_140018595
0x140018580  mov     [rbp+var_40], 0
0x140018588  mov     rax, [rcx]
0x14001858b  mov     rax, [rax+10h]
0x14001858f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018594  nop
0x140018595  xor     eax, eax
0x140018597  mov     rcx, [rbp+var_10]
0x14001859b  xor     rcx, rsp; StackCookie
0x14001859e  call    __security_check_cookie
0x1400185a3  add     rsp, 78h
0x1400185a7  pop     rdi
0x1400185a8  pop     rsi
0x1400185a9  pop     rbx
0x1400185aa  pop     rbp
0x1400185ab  retn
0x1400185ac  mov     ecx, eax; this
0x1400185ae  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400185b3  int     3; Trap to Debugger
0x1400185b4  mov     ecx, eax; this
0x1400185b6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
