# InputRedirectionProcessor::Initialize(IInputDeviceInfoStore *)

- ea: `0x18003aa60`
- end: `0x18003ac1b`
- name: `?Initialize@InputRedirectionProcessor@@IEAAJPEAUIInputDeviceInfoStore@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(InputRedirectionProcessor *__hidden this, struct IInputDeviceInfoStore *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007c198`

## callees

- `0x180012b74`
- `0x18003aa60`
- `0x18003afb0`
- `0x18007d670`
- `0x18008ead4`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x18003aa99`
- `CoreMessaging!CoreUICreate` at `0x18003aa99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abd7`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18003ab0b`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18003ab0b`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18003abbb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18003abbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InputRedirectionProcessor::Initialize(
        InputRedirectionProcessor *this,
        struct IInputDeviceInfoStore *a2)
{
  __int64 *v3; // rdi
  __int64 v4; // rdx
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HLOCAL, const wchar_t *, char *); // rbx
  _QWORD *v9; // rsi
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, unsigned __int64, _QWORD, _QWORD); // rdi
  __int64 v12; // rdx
  __int64 v14; // rdx
  const char *v15; // [rsp+20h] [rbp-38h]
  HLOCAL hMem; // [rsp+40h] [rbp-18h] BYREF
  char v17; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  unsigned int v19; // [rsp+90h] [rbp+38h] BYREF

  v19 = 0;
  hMem = 0;
  v17 = 0;
  *((_QWORD *)this + 9) = a2;
  v3 = (__int64 *)((char *)this + 40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 40);
  v5 = CoreUICreate(v3);
  if ( v5 < 0 )
  {
    v12 = 26;
    goto LABEL_8;
  }
  v6 = InputSecurityDescriptor::QueryDescriptor(&hMem, v4, L"System\\TouchInputRedirection");
  v5 = v6;
  if ( v6 < 0 )
  {
    v14 = 30;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\inputredirection\\system"
                    "\\lib\\inputredirectionprocessor.cpp",
      (const char *)(unsigned int)v6,
      (int)v15);
    goto LABEL_20;
  }
  v7 = *v3;
  v8 = *(__int64 (__fastcall **)(__int64, HLOCAL, const wchar_t *, char *))(*(_QWORD *)v7 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 56);
  v6 = v8(v7, hMem, L"System\\TouchInputRedirection", (char *)this + 56);
  v5 = v6;
  if ( v6 < 0 )
  {
    v14 = 35;
    goto LABEL_18;
  }
  v9 = (_QWORD *)((char *)this + 48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
  v6 = CoreUIFactoryCreate((char *)this + 48);
  v5 = v6;
  if ( v6 < 0 )
  {
    v14 = 37;
    goto LABEL_18;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)*v9 + 24LL))(
         *v9,
         &GUID_548c27d0_a710_4ec7_92d1_67a7dee54efb,
         &v19);
  if ( v5 >= 0 )
  {
    v10 = *v9;
    v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
    v15 = L"TouchInputRedirection";
    v5 = v11(v10, ((unsigned __int64)this + 8) & -(__int64)(this != 0), 0, v19);
    if ( v5 < 0 )
    {
      v12 = 49;
      goto LABEL_8;
    }
    v5 = 0;
LABEL_20:
    InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&hMem);
    return (unsigned int)v5;
  }
  v12 = 41;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\inputredirection\\system\\"
                  "lib\\inputredirectionprocessor.cpp",
    (const char *)(unsigned int)v5,
    (int)v15);
  if ( hMem )
  {
    if ( v17 )
      FreeTransientObjectSecurityDescriptor();
    else
      LocalFree(hMem);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003aa60  push    rbp
0x18003aa62  push    rbx
0x18003aa63  push    rsi
0x18003aa64  push    rdi
0x18003aa65  push    r14
0x18003aa67  push    r15
0x18003aa69  mov     rbp, rsp
0x18003aa6c  sub     rsp, 58h
0x18003aa70  mov     r14, rcx
0x18003aa73  mov     [rbp+arg_0], 0
0x18003aa7a  mov     [rbp+hMem], 0
0x18003aa82  mov     [rbp+var_10], 0
0x18003aa86  mov     [rcx+48h], rdx
0x18003aa8a  lea     rdi, [rcx+28h]
0x18003aa8e  mov     rcx, rdi
0x18003aa91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003aa96  mov     rcx, rdi
0x18003aa99  call    cs:__imp_CoreUICreate
0x18003aa9f  mov     ebx, eax
0x18003aaa1  test    eax, eax
0x18003aaa3  js      loc_18003ABDF
0x18003aaa9  lea     r8, aSystemTouchinp; "System\\TouchInputRedirection"
0x18003aab0  lea     rcx, [rbp+hMem]
0x18003aab4  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x18003aab9  mov     ebx, eax
0x18003aabb  test    eax, eax
0x18003aabd  js      loc_18003ABE6
0x18003aac3  mov     rdi, [rdi]
0x18003aac6  mov     rax, [rdi]
0x18003aac9  mov     rbx, [rax+38h]
0x18003aacd  lea     r15, [r14+38h]
0x18003aad1  mov     rcx, r15
0x18003aad4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003aad9  mov     r9, r15
0x18003aadc  lea     r8, aSystemTouchinp; "System\\TouchInputRedirection"
0x18003aae3  mov     rdx, [rbp+hMem]
0x18003aae7  mov     rcx, rdi
0x18003aaea  mov     rax, rbx
0x18003aaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaf2  mov     ebx, eax
0x18003aaf4  test    eax, eax
0x18003aaf6  js      loc_18003ABED
0x18003aafc  lea     rsi, [r14+30h]
0x18003ab00  mov     rcx, rsi
0x18003ab03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ab08  mov     rcx, rsi
0x18003ab0b  call    cs:__imp_CoreUIFactoryCreate
0x18003ab11  mov     ebx, eax
0x18003ab13  test    eax, eax
0x18003ab15  js      loc_18003ABF4
0x18003ab1b  mov     rcx, [rsi]
0x18003ab1e  mov     rax, [rcx]
0x18003ab21  lea     r8, [rbp+arg_0]
0x18003ab25  lea     rdx, _GUID_548c27d0_a710_4ec7_92d1_67a7dee54efb
0x18003ab2c  mov     rax, [rax+18h]
0x18003ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab35  mov     ebx, eax
0x18003ab37  test    eax, eax
0x18003ab39  js      loc_18003ABD0
0x18003ab3f  mov     rsi, [rsi]
0x18003ab42  mov     rax, [rsi]
0x18003ab45  mov     rdi, [rax+20h]
0x18003ab49  lea     rbx, [r14+40h]
0x18003ab4d  mov     rcx, rbx
0x18003ab50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ab55  lea     r8, [r14+8]
0x18003ab59  neg     r14
0x18003ab5c  sbb     rdx, rdx
0x18003ab5f  and     rdx, r8
0x18003ab62  mov     [rsp+58h+var_28], rbx
0x18003ab67  mov     r8, [r15]
0x18003ab6a  mov     [rsp+58h+var_30], r8
0x18003ab6f  lea     rax, aTouchinputredi; "TouchInputRedirection"
0x18003ab76  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003ab7b  mov     r9d, [rbp+arg_0]
0x18003ab7f  xor     r8d, r8d
0x18003ab82  mov     rcx, rsi
0x18003ab85  mov     rax, rdi
0x18003ab88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab8d  mov     ebx, eax
0x18003ab8f  test    eax, eax
0x18003ab91  jns     short loc_18003AC0E
0x18003ab93  mov     edx, 31h ; '1'; void *
0x18003ab98  lea     r8, aOnecoreuapWind_153; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003ab9f  mov     r9d, ebx; char *
0x18003aba2  mov     rcx, [rbp+30h]; this
0x18003aba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003abab  nop
0x18003abac  mov     rcx, [rbp+hMem]; hMem
0x18003abb0  test    rcx, rcx
0x18003abb3  jz      short loc_18003ABC1
0x18003abb5  cmp     [rbp+var_10], 0
0x18003abb9  jz      short loc_18003ABD7
0x18003abbb  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18003abc1  mov     eax, ebx
0x18003abc3  add     rsp, 58h
0x18003abc7  pop     r15
0x18003abc9  pop     r14
0x18003abcb  pop     rdi
0x18003abcc  pop     rsi
0x18003abcd  pop     rbx
0x18003abce  pop     rbp
0x18003abcf  retn
0x18003abd0  mov     edx, 29h ; ')'
0x18003abd5  jmp     short loc_18003AB98
0x18003abd7  call    cs:__imp_LocalFree
0x18003abdd  jmp     short loc_18003ABC1
0x18003abdf  mov     edx, 1Ah
0x18003abe4  jmp     short loc_18003AB98
0x18003abe6  mov     edx, 1Eh
0x18003abeb  jmp     short loc_18003ABF9
0x18003abed  mov     edx, 23h ; '#'
0x18003abf2  jmp     short loc_18003ABF9
0x18003abf4  mov     edx, 25h ; '%'; void *
0x18003abf9  mov     rcx, [rbp+30h]; this
0x18003abfd  mov     r9d, eax; char *
0x18003ac00  lea     r8, aOnecoreuapWind_153; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003ac07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac0c  jmp     short loc_18003AC10
0x18003ac0e  xor     ebx, ebx
0x18003ac10  lea     rcx, [rbp+hMem]; this
0x18003ac14  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x18003ac19  jmp     short loc_18003ABC1
```
