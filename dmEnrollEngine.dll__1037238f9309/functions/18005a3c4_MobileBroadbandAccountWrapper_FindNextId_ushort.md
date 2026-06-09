# MobileBroadbandAccountWrapper::FindNextId(ushort * *)

- ea: `0x18005a3c4`
- end: `0x18005a5de`
- name: `?FindNextId@MobileBroadbandAccountWrapper@@QEAAJPEAPEAG@Z`
- size: `538`
- prototype: `__int64 __fastcall(MobileBroadbandAccountWrapper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800141d0`

## callees

- `0x18003c41c`
- `0x18003c968`
- `0x18005a3c4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005a4e4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005a4e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005a566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005a566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a4a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a581`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a4a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a581`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005a447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005a447`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MobileBroadbandAccountWrapper::FindNextId(HSTRING *this, PCWSTR *a2)
{
  HRESULT ActivationFactory; // edi
  HSTRING v5; // rbx
  HSTRING v6; // rsi
  __int64 (__fastcall *v7)(HSTRING, _QWORD, __int64 *); // rdi
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  __int64 v15; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HSTRING v18[3]; // [rsp+38h] [rbp-18h] BYREF
  HSTRING v19; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  v16 = 0;
  v15 = 0;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  memset(v18, 0, sizeof(v18));
  if ( *((_DWORD *)this + 5) <= *((_DWORD *)this + 4) )
  {
    string = 0;
    ActivationFactory = WindowsCreateString(L"Windows.Networking.NetworkOperators.MobileBroadbandModem", 0x38u, &string);
    if ( ActivationFactory >= 0 )
    {
      v5 = string;
      v18[0] = string;
      WindowsDeleteString(0);
      v6 = *this;
      v7 = *(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(*(_QWORD *)*this + 48LL);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v15);
      ActivationFactory = v7(v6, *((unsigned int *)this + 5), &v15);
      if ( ActivationFactory >= 0 )
      {
        v8 = v15;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 48LL);
        WindowsDeleteString(v19);
        v19 = 0;
        ActivationFactory = v9(v8, &v19);
        if ( ActivationFactory >= 0 )
        {
          Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v21);
          ActivationFactory = RoGetActivationFactory(v5, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v21);
          if ( ActivationFactory >= 0 )
          {
            v10 = v21;
            v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 56LL);
            Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
            ActivationFactory = v11(v10, v19, &v20);
            if ( ActivationFactory >= 0 )
            {
              v12 = v20;
              v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 56LL);
              Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v16);
              ActivationFactory = v13(v12, &v16);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v16 + 104LL))(
                                      v16,
                                      (char *)this + 24);
                if ( ActivationFactory >= 0 )
                  *a2 = WindowsGetStringRawBuffer(this[3], 0);
              }
            }
          }
        }
      }
    }
    ++*((_DWORD *)this + 5);
  }
  else
  {
    ActivationFactory = -2147024878;
  }
  Windows::Internal::String::~String(v18);
  WindowsDeleteString(v19);
  v19 = 0;
  WindowsDeleteString(0);
  WindowsDeleteString(0);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v16);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18005a3c4  mov     [rsp-28h+arg_8], rbx
0x18005a3c9  push    rbp
0x18005a3ca  push    rsi
0x18005a3cb  push    rdi
0x18005a3cc  push    r14
0x18005a3ce  push    r15
0x18005a3d0  mov     rbp, rsp
0x18005a3d3  sub     rsp, 50h
0x18005a3d7  mov     r15, rdx
0x18005a3da  mov     r14, rcx
0x18005a3dd  mov     [rbp+var_28], 0
0x18005a3e5  mov     [rbp+var_30], 0
0x18005a3ed  mov     [rbp+arg_18], 0
0x18005a3f5  mov     [rbp+arg_10], 0
0x18005a3fd  mov     [rbp+var_10], 0
0x18005a405  mov     [rbp+var_8], 0
0x18005a40d  mov     [rbp+arg_0], 0
0x18005a415  mov     [rbp+var_18], 0
0x18005a41d  mov     eax, [rcx+10h]
0x18005a420  cmp     [rcx+14h], eax
0x18005a423  jbe     short loc_18005A42F
0x18005a425  mov     edi, 80070012h
0x18005a42a  jmp     loc_18005A573
0x18005a42f  mov     [rbp+string], 0
0x18005a437  lea     r8, [rbp+string]; string
0x18005a43b  mov     edx, 38h ; '8'; length
0x18005a440  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x18005a447  call    cs:__imp_WindowsCreateString
0x18005a44d  mov     edi, eax
0x18005a44f  test    eax, eax
0x18005a451  js      loc_18005A56F
0x18005a457  mov     rbx, [rbp+string]
0x18005a45b  mov     [rbp+var_18], rbx
0x18005a45f  xor     ecx, ecx; string
0x18005a461  call    cs:__imp_WindowsDeleteString
0x18005a467  mov     rsi, [r14]
0x18005a46a  mov     rax, [rsi]
0x18005a46d  mov     rdi, [rax+30h]
0x18005a471  lea     rcx, [rbp+var_30]
0x18005a475  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a47a  lea     r8, [rbp+var_30]
0x18005a47e  mov     edx, [r14+14h]
0x18005a482  mov     rcx, rsi
0x18005a485  mov     rax, rdi
0x18005a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a48d  mov     edi, eax
0x18005a48f  test    eax, eax
0x18005a491  js      loc_18005A56F
0x18005a497  mov     rsi, [rbp+var_30]
0x18005a49b  mov     rax, [rsi]
0x18005a49e  mov     rdi, [rax+30h]
0x18005a4a2  mov     rcx, [rbp+arg_0]; string
0x18005a4a6  call    cs:__imp_WindowsDeleteString
0x18005a4ac  mov     [rbp+arg_0], 0
0x18005a4b4  lea     rdx, [rbp+arg_0]
0x18005a4b8  mov     rcx, rsi
0x18005a4bb  mov     rax, rdi
0x18005a4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4c3  mov     edi, eax
0x18005a4c5  test    eax, eax
0x18005a4c7  js      loc_18005A56F
0x18005a4cd  lea     rcx, [rbp+arg_18]
0x18005a4d1  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a4d6  lea     r8, [rbp+arg_18]
0x18005a4da  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x18005a4e1  mov     rcx, rbx
0x18005a4e4  call    cs:__imp_RoGetActivationFactory
0x18005a4ea  mov     edi, eax
0x18005a4ec  test    eax, eax
0x18005a4ee  js      short loc_18005A56F
0x18005a4f0  mov     rdi, [rbp+arg_18]
0x18005a4f4  mov     rax, [rdi]
0x18005a4f7  mov     rbx, [rax+38h]
0x18005a4fb  lea     rcx, [rbp+arg_10]
0x18005a4ff  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a504  lea     r8, [rbp+arg_10]
0x18005a508  mov     rdx, [rbp+arg_0]
0x18005a50c  mov     rcx, rdi
0x18005a50f  mov     rax, rbx
0x18005a512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a517  mov     edi, eax
0x18005a519  test    eax, eax
0x18005a51b  js      short loc_18005A56F
0x18005a51d  mov     rdi, [rbp+arg_10]
0x18005a521  mov     rax, [rdi]
0x18005a524  mov     rbx, [rax+38h]
0x18005a528  lea     rcx, [rbp+var_28]
0x18005a52c  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a531  lea     rdx, [rbp+var_28]
0x18005a535  mov     rcx, rdi
0x18005a538  mov     rax, rbx
0x18005a53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a540  mov     edi, eax
0x18005a542  test    eax, eax
0x18005a544  js      short loc_18005A56F
0x18005a546  mov     rcx, [rbp+var_28]
0x18005a54a  mov     rax, [rcx]
0x18005a54d  lea     rdx, [r14+18h]
0x18005a551  mov     rax, [rax+68h]
0x18005a555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a55a  mov     edi, eax
0x18005a55c  test    eax, eax
0x18005a55e  js      short loc_18005A56F
0x18005a560  xor     edx, edx; length
0x18005a562  mov     rcx, [r14+18h]; string
0x18005a566  call    cs:__imp_WindowsGetStringRawBuffer
0x18005a56c  mov     [r15], rax
0x18005a56f  inc     dword ptr [r14+14h]
0x18005a573  lea     rcx, [rbp+var_18]; this
0x18005a577  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005a57c  nop
0x18005a57d  mov     rcx, [rbp+arg_0]; string
0x18005a581  call    cs:__imp_WindowsDeleteString
0x18005a587  mov     [rbp+arg_0], 0
0x18005a58f  xor     ecx, ecx; string
0x18005a591  call    cs:__imp_WindowsDeleteString
0x18005a597  nop
0x18005a598  xor     ecx, ecx; string
0x18005a59a  call    cs:__imp_WindowsDeleteString
0x18005a5a0  nop
0x18005a5a1  lea     rcx, [rbp+arg_10]
0x18005a5a5  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a5aa  nop
0x18005a5ab  lea     rcx, [rbp+arg_18]
0x18005a5af  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a5b4  nop
0x18005a5b5  lea     rcx, [rbp+var_30]
0x18005a5b9  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a5be  nop
0x18005a5bf  lea     rcx, [rbp+var_28]
0x18005a5c3  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005a5c8  mov     eax, edi
0x18005a5ca  mov     rbx, [rsp+50h+arg_8]
0x18005a5d2  add     rsp, 50h
0x18005a5d6  pop     r15
0x18005a5d8  pop     r14
0x18005a5da  pop     rdi
0x18005a5db  pop     rsi
0x18005a5dc  pop     rbp
0x18005a5dd  retn
```
