# ActivateApp(ushort const *,_GUID,ushort const *)

- ea: `0x1800500e0`
- end: `0x18005038a`
- name: `?ActivateApp@@YAJPEBGU_GUID@@0@Z`
- size: `682`
- prototype: `__int64 __fastcall(PCWSTR sourceString, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800457a8`

## callees

- `0x180015b64`
- `0x18003bc80`
- `0x18004b700`
- `0x18004b7e4`
- `0x18004ffb4`
- `0x1800500e0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800501c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050252`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800502b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800501c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050252`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800502b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800501d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800502cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800501d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800502cd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050273`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050273`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18005035b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18005035b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180050119`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180050119`

## pseudocode

```c
__int64 __fastcall ActivateApp(PCWSTR sourceString, struct _GUID *a2, const unsigned __int16 *a3)
{
  int v5; // edx
  int v6; // ebx
  int v7; // r8d
  __int64 v8; // rcx
  int v9; // edx
  int ActivationFactory; // edi
  int v11; // r8d
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, HSTRING); // r12
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rdi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, _QWORD *); // rdi
  HSTRING v18; // rdi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING, __int128 *, __int64, _DWORD); // r15
  __int64 v21; // rsi
  int v23; // [rsp+28h] [rbp-51h]
  __int64 v24; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v27; // [rsp+60h] [rbp-19h] BYREF
  HSTRING string; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF

  *(_QWORD *)&v27 = a2;
  v6 = RoInitialize(1);
  v24 = 0;
  v26[0] = 0;
  v25 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v5,
      v7,
      10,
      &WPP_f52ee67adea2375213ce6bab3a9a4bca_Traceguids,
      (__int64)" ");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  ActivationFactory = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
                        v8,
                        &v24);
  if ( ActivationFactory >= 0 )
  {
    v12 = v24;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v24 + 104LL);
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      LODWORD(v15) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(a3, v15, &hstringHeader, &string);
    ActivationFactory = v13(v12, string);
    if ( ActivationFactory >= 0 )
    {
      v16 = v24;
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v24 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
      ActivationFactory = v17(v16, v26);
      if ( ActivationFactory >= 0 )
      {
        if ( WindowsCreateStringReference(
               L"Windows.ApplicationModel.Activation.Private.ApplicationActivation",
               0x41u,
               &hstringHeader,
               &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v18 = string;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        ActivationFactory = RoGetActivationFactory(v18, &GUID_193d1b8e_e23f_4e26_b40f_3b91a99b383f, &v25);
        if ( ActivationFactory >= 0 )
        {
          v19 = v25;
          v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int128 *, __int64, _DWORD))(*(_QWORD *)v25 + 64LL);
          v21 = v26[0];
          do
            ++v14;
          while ( sourceString[v14] );
          if ( v14 > 0xFFFFFFFF )
          {
            LODWORD(v14) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(sourceString, v14, &hstringHeader, &string);
          v27 = *(_OWORD *)v27;
          v23 = 0;
          ActivationFactory = v20(v19, string, &v27, v21, 0);
        }
      }
    }
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v9,
      v11,
      11,
      &WPP_f52ee67adea2375213ce6bab3a9a4bca_Traceguids,
      v23,
      ActivationFactory);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  if ( v6 >= 0 )
    RoUninitialize();
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800500e0  mov     [rsp-8+arg_18], rbx
0x1800500e5  push    rbp
0x1800500e6  push    rsi
0x1800500e7  push    rdi
0x1800500e8  push    r12
0x1800500ea  push    r13
0x1800500ec  push    r14
0x1800500ee  push    r15
0x1800500f0  lea     rbp, [rsp-27h]
0x1800500f5  sub     rsp, 0A0h
0x1800500fc  mov     rax, cs:__security_cookie
0x180050103  xor     rax, rsp
0x180050106  mov     [rbp+57h+var_40], rax
0x18005010a  mov     r15, r8
0x18005010d  mov     qword ptr [rbp+57h+var_70], rdx
0x180050111  mov     r13, rcx
0x180050114  mov     ecx, 1
0x180050119  call    cs:__imp_RoInitialize
0x18005011f  mov     ebx, eax
0x180050121  xor     r12d, r12d
0x180050124  mov     [rbp+57h+var_90], r12
0x180050128  mov     [rbp+57h+var_80], r12
0x18005012c  mov     [rbp+57h+var_88], r12
0x180050130  lea     rax, WPP_RECORDER_INITIALIZED
0x180050137  lea     rsi, WPP_f52ee67adea2375213ce6bab3a9a4bca_Traceguids
0x18005013e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180050145  jz      short loc_18005016D
0x180050147  lea     r9d, [r12+0Ah]; int
0x18005014c  lea     rax, asc_18008C82C; " "
0x180050153  mov     [rsp+0D0h+var_A8], rax; __int64
0x180050158  mov     [rsp+0D0h+MessageGuid], rsi; MessageGuid
0x18005015d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050164  mov     rcx, [rcx+28h]; int
0x180050168  call    WPP_RECORDER_SF_s
0x18005016d  lea     rcx, [rbp+57h+var_90]
0x180050171  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050176  lea     rdx, [rbp+57h+var_90]
0x18005017a  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18005017f  mov     edi, eax
0x180050181  test    eax, eax
0x180050183  js      loc_18005030D
0x180050189  mov     rsi, [rbp+57h+var_90]
0x18005018d  mov     rax, [rsi]
0x180050190  mov     r12, [rax+68h]
0x180050194  or      r14, 0FFFFFFFFFFFFFFFFh
0x180050198  mov     rdi, r14
0x18005019b  xor     eax, eax
0x18005019d  inc     rdi
0x1800501a0  cmp     [r15+rdi*2], ax
0x1800501a5  jnz     short loc_18005019D
0x1800501a7  mov     eax, 0FFFFFFFFh
0x1800501ac  cmp     rdi, rax
0x1800501af  jbe     short loc_1800501C8
0x1800501b1  mov     edi, eax
0x1800501b3  xor     r9d, r9d; lpArguments
0x1800501b6  xor     r8d, r8d; nNumberOfArguments
0x1800501b9  lea     edx, [r9+1]; dwExceptionFlags
0x1800501bd  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800501c2  call    cs:__imp_RaiseException
0x1800501c8  lea     r9, [rbp+57h+string]; string
0x1800501cc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800501d0  mov     edx, edi; length
0x1800501d2  mov     rcx, r15; sourceString
0x1800501d5  call    cs:__imp_WindowsCreateStringReference
0x1800501db  mov     rdx, [rbp+57h+string]
0x1800501df  mov     rcx, rsi
0x1800501e2  mov     rax, r12
0x1800501e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501ea  mov     edi, eax
0x1800501ec  xor     r12d, r12d
0x1800501ef  test    eax, eax
0x1800501f1  js      loc_180050306
0x1800501f7  mov     rsi, [rbp+57h+var_90]
0x1800501fb  mov     rax, [rsi]
0x1800501fe  mov     rdi, [rax+40h]
0x180050202  lea     rcx, [rbp+57h+var_80]
0x180050206  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005020b  lea     rdx, [rbp+57h+var_80]
0x18005020f  mov     rcx, rsi
0x180050212  mov     rax, rdi
0x180050215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005021a  mov     edi, eax
0x18005021c  test    eax, eax
0x18005021e  js      loc_180050306
0x180050224  lea     r9, [rbp+57h+string]; string
0x180050228  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005022c  lea     edx, [r12+41h]; length
0x180050231  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Activation_Private_ApplicationActivation@@3QBGB; "Windows.ApplicationModel.Activation.Pri"...
0x180050238  call    cs:__imp_WindowsCreateStringReference
0x18005023e  test    eax, eax
0x180050240  jns     short loc_180050258
0x180050242  xor     r9d, r9d; lpArguments
0x180050245  xor     r8d, r8d; nNumberOfArguments
0x180050248  lea     edx, [r12+1]; dwExceptionFlags
0x18005024d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180050252  call    cs:__imp_RaiseException
0x180050258  mov     rdi, [rbp+57h+string]
0x18005025c  lea     rcx, [rbp+57h+var_88]
0x180050260  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050265  lea     r8, [rbp+57h+var_88]
0x180050269  lea     rdx, _GUID_193d1b8e_e23f_4e26_b40f_3b91a99b383f
0x180050270  mov     rcx, rdi
0x180050273  call    cs:__imp_RoGetActivationFactory
0x180050279  mov     edi, eax
0x18005027b  test    eax, eax
0x18005027d  js      loc_180050306
0x180050283  mov     rdi, [rbp+57h+var_88]
0x180050287  mov     rax, [rdi]
0x18005028a  mov     r15, [rax+40h]
0x18005028e  mov     rsi, [rbp+57h+var_80]
0x180050292  inc     r14
0x180050295  cmp     [r13+r14*2+0], r12w
0x18005029b  jnz     short loc_180050292
0x18005029d  mov     eax, 0FFFFFFFFh
0x1800502a2  cmp     r14, rax
0x1800502a5  jbe     short loc_1800502BF
0x1800502a7  mov     r14d, eax
0x1800502aa  xor     r9d, r9d; lpArguments
0x1800502ad  xor     r8d, r8d; nNumberOfArguments
0x1800502b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800502b4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800502b9  call    cs:__imp_RaiseException
0x1800502bf  lea     r9, [rbp+57h+string]; string
0x1800502c3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800502c7  mov     edx, r14d; length
0x1800502ca  mov     rcx, r13; sourceString
0x1800502cd  call    cs:__imp_WindowsCreateStringReference
0x1800502d3  mov     rax, qword ptr [rbp+57h+var_70]
0x1800502d7  movaps  xmm0, xmmword ptr [rax]
0x1800502da  movdqa  [rbp+57h+var_70], xmm0
0x1800502df  mov     qword ptr [rsp+0D0h+var_A0], r12
0x1800502e4  mov     [rsp+0D0h+var_A8], r12; int
0x1800502e9  mov     dword ptr [rsp+0D0h+MessageGuid], r12d
0x1800502ee  mov     r9, rsi
0x1800502f1  lea     r8, [rbp+57h+var_70]
0x1800502f5  mov     rdx, [rbp+57h+string]
0x1800502f9  mov     rcx, rdi
0x1800502fc  mov     rax, r15
0x1800502ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050304  mov     edi, eax
0x180050306  lea     rsi, WPP_f52ee67adea2375213ce6bab3a9a4bca_Traceguids
0x18005030d  lea     rax, WPP_RECORDER_INITIALIZED
0x180050314  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005031b  jz      short loc_18005033C
0x18005031d  mov     r9d, 0Bh; int
0x180050323  mov     dword ptr [rsp+0D0h+var_A0], edi; char
0x180050327  mov     [rsp+0D0h+MessageGuid], rsi; MessageGuid
0x18005032c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050333  mov     rcx, [rcx+28h]; int
0x180050337  call    WPP_RECORDER_SF_sd
0x18005033c  lea     rcx, [rbp+57h+var_88]
0x180050340  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050345  lea     rcx, [rbp+57h+var_80]
0x180050349  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005034e  lea     rcx, [rbp+57h+var_90]
0x180050352  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050357  test    ebx, ebx
0x180050359  js      short loc_180050361
0x18005035b  call    cs:__imp_RoUninitialize
0x180050361  mov     eax, edi
0x180050363  mov     rcx, [rbp+57h+var_40]
0x180050367  xor     rcx, rsp; StackCookie
0x18005036a  call    __security_check_cookie
0x18005036f  mov     rbx, [rsp+0D0h+arg_18]
0x180050377  add     rsp, 0A0h
0x18005037e  pop     r15
0x180050380  pop     r14
0x180050382  pop     r13
0x180050384  pop     r12
0x180050386  pop     rdi
0x180050387  pop     rsi
0x180050388  pop     rbp
0x180050389  retn
```
