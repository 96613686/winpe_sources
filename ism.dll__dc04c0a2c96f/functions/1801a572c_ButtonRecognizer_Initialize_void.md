# ButtonRecognizer::Initialize(void)

- ea: `0x1801a572c`
- end: `0x1801a59aa`
- name: `?Initialize@ButtonRecognizer@@IEAAJXZ`
- size: `638`
- prototype: `__int64 __fastcall(ButtonRecognizer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801a521c`

## callees

- `0x180012b74`
- `0x18003afb0`
- `0x18003cc50`
- `0x18007d670`
- `0x18008ead4`
- `0x1801a572c`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x1801a5772`
- `CoreMessaging!CoreUICreate` at `0x1801a5772`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x1801a587e`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x1801a587e`

## string_xrefs

- `0x1801a5783`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\processors\combobutton\system\lib\buttonrecognizer.cpp`
- `0x1801a5892`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\processors\combobutton\system\lib\buttonrecognizer.cpp`
- `0x1801a5923`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\processors\combobutton\system\lib\buttonrecognizer.cpp`
- `0x1801a5905`: `System\Input\ComboButton`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ButtonRecognizer::Initialize(ButtonRecognizer *this)
{
  _QWORD *v2; // rsi
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v6; // rdx
  int EndpointHost; // eax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, char *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 (__fastcall *)(void *, const void *, int), ButtonRecognizer *, _QWORD); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, void *, ButtonRecognizer *, char *); // rdi
  int v19; // [rsp+20h] [rbp-20h]
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  char v21; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v23; // [rsp+70h] [rbp+30h] BYREF

  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 5) = 0;
  *(_WORD *)((char *)this + 17) = 0;
  *((_BYTE *)this + 16) = 0;
  v2 = (_QWORD *)((char *)this + 160);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 160);
  v3 = CoreUICreate(v2);
  if ( v3 < 0 )
  {
    v4 = 124;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\combobutton\\system\\lib"
                    "\\buttonrecognizer.cpp",
      (const char *)(unsigned int)v3,
      v19);
    return (unsigned int)v3;
  }
  wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
    (char *)this + 168,
    *v2);
  v20 = 0;
  v21 = 0;
  EndpointHost = InputSecurityDescriptor::QueryDescriptor(&v20, v6, c_wszMessagePortNames);
  v3 = EndpointHost;
  if ( EndpointHost < 0 )
  {
    v8 = 131;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\combobutton\\system\\lib"
                    "\\buttonrecognizer.cpp",
      (const char *)(unsigned int)EndpointHost,
      v19);
    InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&v20);
    return (unsigned int)v3;
  }
  v9 = *v2;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)*v2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 184);
  EndpointHost = v10(v9, v20, (char *)this + 184);
  v3 = EndpointHost;
  if ( EndpointHost < 0 )
  {
    v8 = 135;
    goto LABEL_13;
  }
  v11 = *v2;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(void *, const void *, int), ButtonRecognizer *, _QWORD))(*(_QWORD *)*v2 + 104LL);
  wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
    (char *)this + 168,
    *((_QWORD *)this + 21));
  v19 = (_DWORD)this + 176;
  EndpointHost = v12(v11, ButtonRecognizer::MessageProc, this, *((_QWORD *)this + 23));
  v3 = EndpointHost;
  if ( EndpointHost < 0 )
  {
    v8 = 141;
    goto LABEL_13;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 200);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 192);
  EndpointHost = CoreUICallCreateEndpointHost(*v2, (char *)this + 192, (char *)this + 200);
  v3 = EndpointHost;
  if ( EndpointHost < 0 )
  {
    v8 = 146;
    goto LABEL_13;
  }
  InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&v20);
  v23 = 0;
  v13 = *v2;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v2 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v15 = v14(v13, &v23);
  v3 = v15;
  if ( v15 < 0 )
  {
    v16 = 155;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\combobutton\\system\\lib"
                    "\\buttonrecognizer.cpp",
      (const char *)(unsigned int)v15,
      v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    return (unsigned int)v3;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v23 + 40LL))(
          v23,
          L"System\\Input\\ComboButton",
          *((_QWORD *)this + 22),
          1);
  v3 = v15;
  if ( v15 < 0 )
  {
    v16 = 160;
    goto LABEL_18;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v17 = *v2;
  v18 = *(__int64 (__fastcall **)(__int64, void *, ButtonRecognizer *, char *))(*(_QWORD *)v17 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 152);
  v3 = v18(v17, &lambda_f1854fe2ac21130f928d03576a8a1bbe_::_lambda_invoker_cdecl_, this, (char *)this + 152);
  if ( v3 < 0 )
  {
    v4 = 172;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1801a572c  mov     [rsp-28h+arg_8], rbx
0x1801a5731  mov     [rsp-28h+arg_10], rsi
0x1801a5736  push    rbp
0x1801a5737  push    rdi
0x1801a5738  push    r12
0x1801a573a  push    r14
0x1801a573c  push    r15
0x1801a573e  mov     rbp, rsp
0x1801a5741  sub     rsp, 40h
0x1801a5745  mov     r14, rcx
0x1801a5748  mov     dword ptr [rcx+18h], 1
0x1801a574f  mov     dword ptr [rcx+14h], 0
0x1801a5756  mov     word ptr [rcx+11h], 0
0x1801a575c  mov     byte ptr [rcx+10h], 0
0x1801a5760  lea     rsi, [rcx+0A0h]
0x1801a5767  mov     rcx, rsi
0x1801a576a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a576f  mov     rcx, rsi
0x1801a5772  call    cs:__imp_CoreUICreate
0x1801a5778  mov     ebx, eax
0x1801a577a  test    eax, eax
0x1801a577c  jns     short loc_1801A579D
0x1801a577e  mov     edx, 7Ch ; '|'; void *
0x1801a5783  lea     r8, aOnecoreuapWind_50; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801a578a  mov     r9d, ebx; char *
0x1801a578d  mov     rcx, [rbp+28h]; this
0x1801a5791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a5796  mov     eax, ebx
0x1801a5798  jmp     loc_1801A5991
0x1801a579d  lea     r15, [r14+0A8h]
0x1801a57a4  mov     rdx, [rsi]
0x1801a57a7  mov     rcx, r15
0x1801a57aa  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x1801a57af  mov     [rbp+var_10], 0
0x1801a57b7  mov     [rbp+var_8], 0
0x1801a57bb  mov     r8, cs:?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x1801a57c2  lea     rcx, [rbp+var_10]
0x1801a57c6  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x1801a57cb  mov     ebx, eax
0x1801a57cd  test    eax, eax
0x1801a57cf  jns     short loc_1801A57DB
0x1801a57d1  mov     edx, 83h
0x1801a57d6  jmp     loc_1801A588F
0x1801a57db  mov     rdi, [rsi]
0x1801a57de  mov     rax, [rdi]
0x1801a57e1  mov     rbx, [rax+40h]
0x1801a57e5  lea     r12, [r14+0B8h]
0x1801a57ec  mov     rcx, r12
0x1801a57ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a57f4  mov     r8, r12
0x1801a57f7  mov     rdx, [rbp+var_10]
0x1801a57fb  mov     rcx, rdi
0x1801a57fe  mov     rax, rbx
0x1801a5801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5806  mov     ebx, eax
0x1801a5808  test    eax, eax
0x1801a580a  jns     short loc_1801A5813
0x1801a580c  mov     edx, 87h
0x1801a5811  jmp     short loc_1801A588F
0x1801a5813  mov     rdi, [rsi]
0x1801a5816  mov     rax, [rdi]
0x1801a5819  mov     rbx, [rax+68h]
0x1801a581d  mov     rdx, [r15]
0x1801a5820  mov     rcx, r15
0x1801a5823  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x1801a5828  lea     rdx, [r15+8]
0x1801a582c  mov     qword ptr [rsp+40h+var_20], rdx; int
0x1801a5831  mov     r9, [r12]
0x1801a5835  mov     r8, r14
0x1801a5838  lea     rdx, ?MessageProc@ButtonRecognizer@@SAJPEAXPEBXH@Z; ButtonRecognizer::MessageProc(void *,void const *,int)
0x1801a583f  mov     rcx, rdi
0x1801a5842  mov     rax, rbx
0x1801a5845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a584a  mov     ebx, eax
0x1801a584c  test    eax, eax
0x1801a584e  jns     short loc_1801A5857
0x1801a5850  mov     edx, 8Dh
0x1801a5855  jmp     short loc_1801A588F
0x1801a5857  lea     rdi, [r14+0C8h]
0x1801a585e  mov     rcx, rdi
0x1801a5861  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a5866  lea     rbx, [r14+0C0h]
0x1801a586d  mov     rcx, rbx
0x1801a5870  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a5875  mov     r8, rdi
0x1801a5878  mov     rdx, rbx
0x1801a587b  mov     rcx, [rsi]
0x1801a587e  call    cs:__imp_CoreUICallCreateEndpointHost
0x1801a5884  mov     ebx, eax
0x1801a5886  test    eax, eax
0x1801a5888  jns     short loc_1801A58B1
0x1801a588a  mov     edx, 92h; void *
0x1801a588f  mov     r9d, eax; char *
0x1801a5892  lea     r8, aOnecoreuapWind_50; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801a5899  mov     rcx, [rbp+28h]; this
0x1801a589d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a58a2  nop
0x1801a58a3  lea     rcx, [rbp+var_10]; this
0x1801a58a7  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x1801a58ac  jmp     loc_1801A5796
0x1801a58b1  lea     rcx, [rbp+var_10]; this
0x1801a58b5  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x1801a58ba  mov     [rbp+arg_0], 0
0x1801a58c2  mov     rdi, [rsi]
0x1801a58c5  mov     rax, [rdi]
0x1801a58c8  mov     rbx, [rax+18h]
0x1801a58cc  lea     rcx, [rbp+arg_0]
0x1801a58d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a58d5  lea     rdx, [rbp+arg_0]
0x1801a58d9  mov     rcx, rdi
0x1801a58dc  mov     rax, rbx
0x1801a58df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a58e4  mov     ebx, eax
0x1801a58e6  test    eax, eax
0x1801a58e8  jns     short loc_1801A58F1
0x1801a58ea  mov     edx, 9Bh
0x1801a58ef  jmp     short loc_1801A5920
0x1801a58f1  mov     rcx, [rbp+arg_0]
0x1801a58f5  mov     rax, [rcx]
0x1801a58f8  mov     r9d, 1
0x1801a58fe  mov     r8, [r14+0B0h]
0x1801a5905  lea     rdx, aSystemInputCom; "System\\Input\\ComboButton"
0x1801a590c  mov     rax, [rax+28h]
0x1801a5910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5915  mov     ebx, eax
0x1801a5917  test    eax, eax
0x1801a5919  jns     short loc_1801A5942
0x1801a591b  mov     edx, 0A0h; void *
0x1801a5920  mov     r9d, eax; char *
0x1801a5923  lea     r8, aOnecoreuapWind_50; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801a592a  mov     rcx, [rbp+28h]; this
0x1801a592e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a5933  nop
0x1801a5934  lea     rcx, [rbp+arg_0]
0x1801a5938  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a593d  jmp     loc_1801A5796
0x1801a5942  lea     rcx, [rbp+arg_0]
0x1801a5946  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a594b  mov     rsi, [rsi]
0x1801a594e  mov     rax, [rsi]
0x1801a5951  mov     rdi, [rax+90h]
0x1801a5958  lea     rbx, [r14+98h]
0x1801a595f  mov     rcx, rbx
0x1801a5962  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a5967  mov     r9, rbx
0x1801a596a  mov     r8, r14
0x1801a596d  lea     rdx, _lambda_f1854fe2ac21130f928d03576a8a1bbe____lambda_invoker_cdecl_
0x1801a5974  mov     rcx, rsi
0x1801a5977  mov     rax, rdi
0x1801a597a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a597f  mov     ebx, eax
0x1801a5981  test    eax, eax
0x1801a5983  jns     short loc_1801A598F
0x1801a5985  mov     edx, 0ACh
0x1801a598a  jmp     loc_1801A5783
0x1801a598f  xor     eax, eax
0x1801a5991  lea     r11, [rsp+40h+var_s0]
0x1801a5996  mov     rbx, [r11+38h]
0x1801a599a  mov     rsi, [r11+40h]
0x1801a599e  mov     rsp, r11
0x1801a59a1  pop     r15
0x1801a59a3  pop     r14
0x1801a59a5  pop     r12
0x1801a59a7  pop     rdi
0x1801a59a8  pop     rbp
0x1801a59a9  retn
```
