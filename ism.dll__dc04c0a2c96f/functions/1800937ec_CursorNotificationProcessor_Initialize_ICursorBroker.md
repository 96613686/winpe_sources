# CursorNotificationProcessor::Initialize(ICursorBroker *)

- ea: `0x1800937ec`
- end: `0x180093aa2`
- name: `?Initialize@CursorNotificationProcessor@@QEAAJPEAUICursorBroker@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(CursorNotificationProcessor *__hidden this, struct ICursorBroker *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180093458`

## callees

- `0x180012b74`
- `0x180012ee0`
- `0x18002009c`
- `0x180030260`
- `0x18003cc50`
- `0x18008e1b8`
- `0x18008ead4`
- `0x1800937ec`
- `0x1800f0990`
- `0x180130268`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x1800938b7`
- `CoreMessaging!CoreUICreate` at `0x1800938b7`
- `win32u!NtMITCoreMsgKOpenConnectionTo` at `0x1800939ad`
- `win32u!NtMITCoreMsgKOpenConnectionTo` at `0x1800939ad`

## string_xrefs

- `0x18009385a`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\cursornotificationprocessor.cpp`
- `0x180093913`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\cursornotificationprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CursorNotificationProcessor::Initialize(CursorNotificationProcessor *this, struct ICursorBroker *a2)
{
  struct InputSystemServerConnection *BamoServerConnection; // rax
  SystemCursorController2 *v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, const wchar_t *, __int64 *); // rbx
  unsigned __int64 v12; // r9
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 (__fastcall *)(void *, const void *, int), CursorNotificationProcessor *, __int64); // rbx
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 *v19; // [rsp+20h] [rbp-29h]
  __int64 v20; // [rsp+30h] [rbp-19h] BYREF
  __int64 v21; // [rsp+38h] [rbp-11h] BYREF
  __int64 v22; // [rsp+40h] [rbp-9h] BYREF
  __int64 v23; // [rsp+48h] [rbp-1h] BYREF
  __int64 v24; // [rsp+50h] [rbp+7h] BYREF
  _OWORD v25[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( IsEdition(0x3DDA1u) )
    goto LABEL_7;
  BamoServerConnection = ISMStatics::GetBamoServerConnection();
  v5 = (SystemCursorController2 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)BamoServerConnection + 31)
                                                                                 + 8LL)
                                                                     + 232LL))(*((_QWORD *)BamoServerConnection + 31) + 8LL);
  v6 = SystemCursorController2::InitializeDesktopCursorService(v5);
  if ( v6 >= 0 )
  {
    v6 = CursorNotificationProcessor::EnsureMouseCursorForDesktopPen(this, a2);
    if ( v6 < 0 )
    {
      v7 = 30;
      goto LABEL_4;
    }
LABEL_7:
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v20 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v8 = CoreUICreate(&v20);
    v6 = v8;
    if ( v8 >= 0 )
    {
      wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
        &v22,
        v20);
      v10 = v20;
      v11 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v20 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      v8 = v11(v10, L"Kernel\\MIT\\InputPort", &v21);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v13 = v20;
        v14 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(void *, const void *, int), CursorNotificationProcessor *, __int64))(*(_QWORD *)v20 + 104LL);
        wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
          &v22,
          v22);
        v19 = &v23;
        v8 = v14(v13, CursorNotificationProcessor::OnMitMessageReceived, this, v21);
        v6 = v8;
        if ( v8 >= 0 )
        {
          memset(v25, 0, sizeof(v25));
          v26 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *))(*(_QWORD *)v20 + 136LL))(v20, v23, v25);
          v6 = v8;
          if ( v8 >= 0 )
          {
            v15 = NtMITCoreMsgKOpenConnectionTo(0, v25);
            v6 = v15 | 0x10000000;
            if ( v15 >= 0 )
            {
              if ( *(struct ICursorBroker **)this != a2 )
              {
                if ( a2 )
                  (*(void (__fastcall **)(struct ICursorBroker *))(*(_QWORD *)a2 + 8LL))(a2);
                v24 = *(_QWORD *)this;
                *(_QWORD *)this = a2;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
              }
              Microsoft::WRL::ComPtr<IMPCFocusTarget>::operator=((char *)this + 16, &v20);
              v16 = v21;
              v21 = 0;
              if ( *((_QWORD *)this + 4) != v16 )
              {
                if ( v16 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
                v24 = *((_QWORD *)this + 4);
                *((_QWORD *)this + 4) = v16;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
              }
              v17 = v23;
              v23 = 0;
              wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
                &v22,
                0);
              *((_QWORD *)this + 5) = v17;
              v6 = 0;
              goto LABEL_28;
            }
            v12 = (unsigned int)v6;
            v9 = 57;
LABEL_12:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v9,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib\\"
                            "cursornotificationprocessor.cpp",
              (const char *)v12,
              (int)v19);
LABEL_28:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
            wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
              &v22,
              0);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
            return (unsigned int)v6;
          }
          v9 = 53;
        }
        else
        {
          v9 = 49;
        }
      }
      else
      {
        v9 = 42;
      }
    }
    else
    {
      v9 = 38;
    }
    v12 = (unsigned int)v8;
    goto LABEL_12;
  }
  v7 = 29;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib\\cursornoti"
                  "ficationprocessor.cpp",
    (const char *)(unsigned int)v6,
    (int)v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800937ec  mov     [rsp-8+arg_10], rbx
0x1800937f1  mov     [rsp-8+arg_18], rsi
0x1800937f6  push    rbp
0x1800937f7  push    rdi
0x1800937f8  push    r14
0x1800937fa  lea     rbp, [rsp-47h]
0x1800937ff  sub     rsp, 90h
0x180093806  mov     rax, cs:__security_cookie
0x18009380d  xor     rax, rsp
0x180093810  mov     [rbp+57h+var_20], rax
0x180093814  mov     r14, rdx
0x180093817  mov     rsi, rcx
0x18009381a  mov     ecx, 3DDA1h; unsigned __int64
0x18009381f  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x180093824  test    al, al
0x180093826  jnz     short loc_18009388A
0x180093828  call    ?GetBamoServerConnection@ISMStatics@@SAPEAVInputSystemServerConnection@@XZ; ISMStatics::GetBamoServerConnection(void)
0x18009382d  mov     rcx, [rax+0F8h]
0x180093834  add     rcx, 8
0x180093838  mov     rax, [rcx]
0x18009383b  mov     rax, [rax+0E8h]
0x180093842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093847  mov     rcx, rax; this
0x18009384a  call    ?InitializeDesktopCursorService@SystemCursorController2@@QEAAJXZ; SystemCursorController2::InitializeDesktopCursorService(void)
0x18009384f  mov     ebx, eax
0x180093851  test    eax, eax
0x180093853  jns     short loc_180093872
0x180093855  mov     edx, 1Dh; void *
0x18009385a  lea     r8, aOnecoreuapWind_196; "onecoreuap\\windows\\moderncore\\inputv"...
0x180093861  mov     r9d, ebx; char *
0x180093864  mov     rcx, [rbp+5Fh]; this
0x180093868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009386d  jmp     loc_180093A7C
0x180093872  mov     rdx, r14; struct ICursorBroker *
0x180093875  mov     rcx, rsi; this
0x180093878  call    ?EnsureMouseCursorForDesktopPen@CursorNotificationProcessor@@AEAAJPEAUICursorBroker@@@Z; CursorNotificationProcessor::EnsureMouseCursorForDesktopPen(ICursorBroker *)
0x18009387d  mov     ebx, eax
0x18009387f  test    eax, eax
0x180093881  jns     short loc_18009388A
0x180093883  mov     edx, 1Eh
0x180093888  jmp     short loc_18009385A
0x18009388a  mov     [rbp+57h+var_68], 0
0x180093892  mov     [rbp+57h+var_60], 0
0x18009389a  mov     [rbp+57h+var_58], 0
0x1800938a2  mov     [rbp+57h+var_70], 0
0x1800938aa  lea     rcx, [rbp+57h+var_70]
0x1800938ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800938b3  lea     rcx, [rbp+57h+var_70]
0x1800938b7  call    cs:__imp_CoreUICreate
0x1800938bd  mov     ebx, eax
0x1800938bf  test    eax, eax
0x1800938c1  jns     short loc_1800938CA
0x1800938c3  mov     edx, 26h ; '&'
0x1800938c8  jmp     short loc_18009390C
0x1800938ca  mov     rdx, [rbp+57h+var_70]
0x1800938ce  lea     rcx, [rbp+57h+var_60]
0x1800938d2  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x1800938d7  mov     rdi, [rbp+57h+var_70]
0x1800938db  mov     rax, [rdi]
0x1800938de  mov     rbx, [rax+50h]
0x1800938e2  lea     rcx, [rbp+57h+var_68]
0x1800938e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800938eb  lea     r8, [rbp+57h+var_68]
0x1800938ef  lea     rdx, aKernelMitInput; "Kernel\\MIT\\InputPort"
0x1800938f6  mov     rcx, rdi
0x1800938f9  mov     rax, rbx
0x1800938fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093901  mov     ebx, eax
0x180093903  test    eax, eax
0x180093905  jns     short loc_180093924
0x180093907  mov     edx, 2Ah ; '*'; void *
0x18009390c  mov     r9d, eax; char *
0x18009390f  mov     rcx, [rbp+5Fh]; this
0x180093913  lea     r8, aOnecoreuapWind_196; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009391a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009391f  jmp     loc_180093A5D
0x180093924  mov     rdi, [rbp+57h+var_70]
0x180093928  mov     rax, [rdi]
0x18009392b  mov     rbx, [rax+68h]
0x18009392f  mov     rdx, [rbp+57h+var_60]
0x180093933  lea     rcx, [rbp+57h+var_60]
0x180093937  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x18009393c  lea     rax, [rbp+57h+var_58]
0x180093940  mov     [rsp+0A0h+var_80], rax
0x180093945  mov     r9, [rbp+57h+var_68]
0x180093949  mov     r8, rsi
0x18009394c  lea     rdx, ?OnMitMessageReceived@CursorNotificationProcessor@@CAJPEAXPEBXH@Z; CursorNotificationProcessor::OnMitMessageReceived(void *,void const *,int)
0x180093953  mov     rcx, rdi
0x180093956  mov     rax, rbx
0x180093959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009395e  mov     ebx, eax
0x180093960  test    eax, eax
0x180093962  jns     short loc_18009396B
0x180093964  mov     edx, 31h ; '1'
0x180093969  jmp     short loc_18009390C
0x18009396b  xorps   xmm0, xmm0
0x18009396e  xor     eax, eax
0x180093970  movups  [rbp+57h+var_48], xmm0
0x180093974  movups  [rbp+57h+var_38], xmm0
0x180093978  mov     [rbp+57h+var_28], rax
0x18009397c  mov     rcx, [rbp+57h+var_70]
0x180093980  mov     rax, [rcx]
0x180093983  lea     r8, [rbp+57h+var_48]
0x180093987  mov     rdx, [rbp+57h+var_58]
0x18009398b  mov     rax, [rax+88h]
0x180093992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093997  mov     ebx, eax
0x180093999  test    eax, eax
0x18009399b  jns     short loc_1800939A7
0x18009399d  mov     edx, 35h ; '5'
0x1800939a2  jmp     loc_18009390C
0x1800939a7  lea     rdx, [rbp+57h+var_48]
0x1800939ab  xor     ecx, ecx
0x1800939ad  call    cs:__imp_NtMITCoreMsgKOpenConnectionTo
0x1800939b3  mov     ebx, eax
0x1800939b5  or      ebx, 10000000h
0x1800939bb  jge     short loc_1800939CA
0x1800939bd  mov     r9d, ebx
0x1800939c0  mov     edx, 39h ; '9'
0x1800939c5  jmp     loc_18009390F
0x1800939ca  cmp     [rsi], r14
0x1800939cd  jz      short loc_1800939F7
0x1800939cf  test    r14, r14
0x1800939d2  jz      short loc_1800939E4
0x1800939d4  mov     rax, [r14]
0x1800939d7  mov     rcx, r14
0x1800939da  mov     rax, [rax+8]
0x1800939de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939e3  nop
0x1800939e4  mov     rax, [rsi]
0x1800939e7  mov     [rbp+57h+var_50], rax
0x1800939eb  mov     [rsi], r14
0x1800939ee  lea     rcx, [rbp+57h+var_50]
0x1800939f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800939f7  lea     rcx, [rsi+10h]
0x1800939fb  lea     rdx, [rbp+57h+var_70]
0x1800939ff  call    ??4?$ComPtr@UIMPCFocusTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMPCFocusTarget>::operator=(Microsoft::WRL::ComPtr<IMPCFocusTarget> const &)
0x180093a04  mov     rbx, [rbp+57h+var_68]
0x180093a08  mov     [rbp+57h+var_68], 0
0x180093a10  cmp     [rsi+20h], rbx
0x180093a14  jz      short loc_180093A40
0x180093a16  test    rbx, rbx
0x180093a19  jz      short loc_180093A2B
0x180093a1b  mov     rax, [rbx]
0x180093a1e  mov     rcx, rbx
0x180093a21  mov     rax, [rax+8]
0x180093a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a2a  nop
0x180093a2b  mov     rax, [rsi+20h]
0x180093a2f  mov     [rbp+57h+var_50], rax
0x180093a33  mov     [rsi+20h], rbx
0x180093a37  lea     rcx, [rbp+57h+var_50]
0x180093a3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180093a40  mov     rbx, [rbp+57h+var_58]
0x180093a44  mov     [rbp+57h+var_58], 0
0x180093a4c  xor     edx, edx
0x180093a4e  lea     rcx, [rbp+57h+var_60]
0x180093a52  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x180093a57  mov     [rsi+28h], rbx
0x180093a5b  xor     ebx, ebx
0x180093a5d  lea     rcx, [rbp+57h+var_70]
0x180093a61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180093a66  nop
0x180093a67  xor     edx, edx
0x180093a69  lea     rcx, [rbp+57h+var_60]
0x180093a6d  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x180093a72  nop
0x180093a73  lea     rcx, [rbp+57h+var_68]
0x180093a77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180093a7c  mov     eax, ebx
0x180093a7e  mov     rcx, [rbp+57h+var_20]
0x180093a82  xor     rcx, rsp; StackCookie
0x180093a85  call    __security_check_cookie
0x180093a8a  lea     r11, [rsp+0A0h+var_10]
0x180093a92  mov     rbx, [r11+30h]
0x180093a96  mov     rsi, [r11+38h]
0x180093a9a  mov     rsp, r11
0x180093a9d  pop     r14
0x180093a9f  pop     rdi
0x180093aa0  pop     rbp
0x180093aa1  retn
```
