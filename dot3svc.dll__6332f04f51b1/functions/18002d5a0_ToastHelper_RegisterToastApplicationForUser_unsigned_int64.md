# ToastHelper::RegisterToastApplicationForUser(unsigned __int64)

- ea: `0x18002d5a0`
- end: `0x18002da1e`
- name: `?RegisterToastApplicationForUser@ToastHelper@@CAJ_K@Z`
- size: `1150`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002f3c8`

## callees

- `0x1800084ec`
- `0x18000c230`
- `0x18002d5a0`
- `0x18002f258`
- `0x18002fc58`
- `0x1800309d0`
- `0x180040010`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x18002d642`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18002d642`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d5eb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d5eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d68f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d710`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d78c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d7f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d875`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d970`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d9ef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d68f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d710`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d78c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d7f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d875`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d970`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d9ef`

## pseudocode

```c
__int64 __fastcall ToastHelper::RegisterToastApplicationForUser(__int64 a1)
{
  HRESULT v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  int InstanceAsUser; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // [rsp+20h] [rbp-78h]
  __int64 v16; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17; // [rsp+48h] [rbp-50h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, __int64 *, __int64 *); // [rsp+50h] [rbp-48h] BYREF
  __int64 v19; // [rsp+58h] [rbp-40h] BYREF
  int v20; // [rsp+60h] [rbp-38h] BYREF
  __int128 v21; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v23; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
  }
  v2 = CoInitializeEx(0, 0);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, v15);
    v17 = 0;
    v16 = 0;
    v23 = 0;
    InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1048580, a1);
    v6 = InstanceAsUser;
    if ( InstanceAsUser >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 48LL))(v17, &v16);
      v6 = v7;
      if ( v7 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, int *))(*(_QWORD *)v16 + 24LL))(
               v16,
               L"Windows.SystemToast.Ethernet",
               2098180,
               &v23);
        v6 = v8;
        if ( v8 >= 0 )
        {
          if ( v23 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 11, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
            }
            if ( v16 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v16);
            if ( v17 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v17);
          }
          else
          {
            v18 = 0;
            v11 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)v17 + 40LL))(
                    v17,
                    &v18);
            v6 = v11;
            if ( v11 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4B,
                (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
                (const char *)(unsigned int)v11,
                (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
              if ( v18 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v18);
              if ( v16 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v16);
              if ( v17 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v17);
              goto LABEL_49;
            }
            if ( v18 )
            {
              v19 = 0;
              v20 = 0;
              v21 = 0;
              v13 = (**v18)(v18, winrt::impl::guid_v<IWpnSystemRegistrationEndpoint>, &v19);
              winrt::check_hresult((int *)&v24, v13, (__int64)&v20);
              v12 = v19;
              v24 = v19;
            }
            else
            {
              v24 = 0;
              v12 = 0;
            }
            v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64))(*(_QWORD *)v12 + 24LL))(
                    v12,
                    L"System",
                    L"Windows.SystemToast.Ethernet",
                    2098180);
            v6 = v14;
            if ( v14 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x53,
                (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
                (const char *)(unsigned int)v14,
                0);
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v24);
              if ( v18 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v18);
              if ( v16 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v16);
              if ( v17 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v17);
              goto LABEL_49;
            }
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 12, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
            }
            winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v24);
            if ( v18 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v18);
            if ( v16 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v16);
            if ( v17 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v17);
          }
          CoUninitialize();
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
          (const char *)(unsigned int)v8,
          (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
        if ( v16 )
          winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v16);
        if ( v17 )
          winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
          (const char *)(unsigned int)v7,
          (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
        if ( v16 )
          winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v16);
        if ( v17 )
          winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v17);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
        (const char *)(unsigned int)InstanceAsUser,
        (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    }
LABEL_49:
    CoUninitialize();
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x57,
                           (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18002d5a0  mov     [rsp+arg_0], rbx
0x18002d5a5  push    rsi
0x18002d5a6  push    rdi
0x18002d5a7  push    r14
0x18002d5a9  sub     rsp, 80h
0x18002d5b0  mov     rbx, rcx
0x18002d5b3  xor     esi, esi
0x18002d5b5  lea     r14, WPP_GLOBAL_Control
0x18002d5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5c3  cmp     rcx, r14
0x18002d5c6  jz      short loc_18002D5E7
0x18002d5c8  cmp     byte ptr [rcx+19h], 4
0x18002d5cc  jb      short loc_18002D5E7
0x18002d5ce  test    byte ptr [rcx+1Ch], 1
0x18002d5d2  jz      short loc_18002D5E7
0x18002d5d4  lea     edx, [rsi+0Ah]
0x18002d5d7  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d5de  mov     rcx, [rcx+10h]
0x18002d5e2  call    WPP_SF_
0x18002d5e7  xor     edx, edx; dwCoInit
0x18002d5e9  xor     ecx, ecx; pvReserved
0x18002d5eb  call    cs:__imp_CoInitializeEx
0x18002d5f1  mov     rcx, [rsp+98h]; this
0x18002d5f9  test    eax, eax
0x18002d5fb  js      loc_18002DA14
0x18002d601  mov     byte ptr [rsp+98h+arg_8], 1
0x18002d609  mov     [rsp+98h+var_50], rsi
0x18002d60e  mov     [rsp+98h+var_58], rsi
0x18002d613  mov     [rsp+98h+arg_10], esi
0x18002d61a  lea     rax, [rsp+98h+var_50]
0x18002d61f  mov     [rsp+98h+var_70], rax
0x18002d624  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18002d62b  mov     qword ptr [rsp+98h+var_78], rax; int
0x18002d630  mov     r9, rbx
0x18002d633  xor     edx, edx
0x18002d635  mov     r8d, 100004h
0x18002d63b  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x18002d642  call    cs:__imp_CoCreateInstanceAsUser
0x18002d648  mov     ebx, eax
0x18002d64a  test    eax, eax
0x18002d64c  jns     short loc_18002D69C
0x18002d64e  mov     rcx, [rsp+98h]; this
0x18002d656  mov     r9d, eax; char *
0x18002d659  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d660  mov     edx, 3Eh ; '>'; void *
0x18002d665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d66a  nop
0x18002d66b  cmp     [rsp+98h+var_58], rsi
0x18002d670  jz      short loc_18002D67D
0x18002d672  lea     rcx, [rsp+98h+var_58]
0x18002d677  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d67c  nop
0x18002d67d  cmp     [rsp+98h+var_50], rsi
0x18002d682  jz      short loc_18002D68F
0x18002d684  lea     rcx, [rsp+98h+var_50]
0x18002d689  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d68e  nop
0x18002d68f  call    cs:__imp_CoUninitialize
0x18002d695  mov     eax, ebx
0x18002d697  jmp     loc_18002DA00
0x18002d69c  mov     rbx, [rsp+98h+var_50]
0x18002d6a1  mov     rax, [rbx]
0x18002d6a4  mov     rdi, [rax+30h]
0x18002d6a8  cmp     [rsp+98h+var_58], rsi
0x18002d6ad  jz      short loc_18002D6B9
0x18002d6af  lea     rcx, [rsp+98h+var_58]
0x18002d6b4  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d6b9  lea     rdx, [rsp+98h+var_58]
0x18002d6be  mov     rcx, rbx
0x18002d6c1  mov     rax, rdi
0x18002d6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6c9  mov     ebx, eax
0x18002d6cb  test    eax, eax
0x18002d6cd  jns     short loc_18002D71D
0x18002d6cf  mov     rcx, [rsp+98h]; this
0x18002d6d7  mov     r9d, eax; char *
0x18002d6da  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d6e1  mov     edx, 3Fh ; '?'; void *
0x18002d6e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d6eb  nop
0x18002d6ec  cmp     [rsp+98h+var_58], rsi
0x18002d6f1  jz      short loc_18002D6FE
0x18002d6f3  lea     rcx, [rsp+98h+var_58]
0x18002d6f8  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d6fd  nop
0x18002d6fe  cmp     [rsp+98h+var_50], rsi
0x18002d703  jz      short loc_18002D710
0x18002d705  lea     rcx, [rsp+98h+var_50]
0x18002d70a  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d70f  nop
0x18002d710  call    cs:__imp_CoUninitialize
0x18002d716  mov     eax, ebx
0x18002d718  jmp     loc_18002DA00
0x18002d71d  mov     rcx, [rsp+98h+var_58]
0x18002d722  mov     rax, [rcx]
0x18002d725  lea     r9, [rsp+98h+arg_10]
0x18002d72d  mov     edi, 200404h
0x18002d732  mov     r8d, edi
0x18002d735  lea     rdx, aWindowsSystemt; "Windows.SystemToast.Ethernet"
0x18002d73c  mov     rax, [rax+18h]
0x18002d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d745  mov     ebx, eax
0x18002d747  test    eax, eax
0x18002d749  jns     short loc_18002D799
0x18002d74b  mov     rcx, [rsp+98h]; this
0x18002d753  mov     r9d, eax; char *
0x18002d756  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d75d  mov     edx, 43h ; 'C'; void *
0x18002d762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d767  nop
0x18002d768  cmp     [rsp+98h+var_58], rsi
0x18002d76d  jz      short loc_18002D77A
0x18002d76f  lea     rcx, [rsp+98h+var_58]
0x18002d774  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d779  nop
0x18002d77a  cmp     [rsp+98h+var_50], rsi
0x18002d77f  jz      short loc_18002D78C
0x18002d781  lea     rcx, [rsp+98h+var_50]
0x18002d786  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d78b  nop
0x18002d78c  call    cs:__imp_CoUninitialize
0x18002d792  mov     eax, ebx
0x18002d794  jmp     loc_18002DA00
0x18002d799  cmp     [rsp+98h+arg_10], esi
0x18002d7a0  jz      short loc_18002D801
0x18002d7a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7a9  cmp     rcx, r14
0x18002d7ac  jz      short loc_18002D7D0
0x18002d7ae  cmp     byte ptr [rcx+19h], 4
0x18002d7b2  jb      short loc_18002D7D0
0x18002d7b4  test    byte ptr [rcx+1Ch], 1
0x18002d7b8  jz      short loc_18002D7D0
0x18002d7ba  mov     edx, 0Bh
0x18002d7bf  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d7c6  mov     rcx, [rcx+10h]
0x18002d7ca  call    WPP_SF_
0x18002d7cf  nop
0x18002d7d0  cmp     [rsp+98h+var_58], rsi
0x18002d7d5  jz      short loc_18002D7E2
0x18002d7d7  lea     rcx, [rsp+98h+var_58]
0x18002d7dc  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d7e1  nop
0x18002d7e2  cmp     [rsp+98h+var_50], rsi
0x18002d7e7  jz      short loc_18002D7F4
0x18002d7e9  lea     rcx, [rsp+98h+var_50]
0x18002d7ee  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d7f3  nop
0x18002d7f4  call    cs:__imp_CoUninitialize
0x18002d7fa  xor     eax, eax
0x18002d7fc  jmp     loc_18002DA00
0x18002d801  mov     [rsp+98h+var_48], rsi
0x18002d806  mov     rcx, [rsp+98h+var_50]
0x18002d80b  mov     rax, [rcx]
0x18002d80e  lea     rdx, [rsp+98h+var_48]
0x18002d813  mov     rax, [rax+28h]
0x18002d817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d81c  mov     ebx, eax
0x18002d81e  test    eax, eax
0x18002d820  jns     short loc_18002D882
0x18002d822  mov     rcx, [rsp+98h]; this
0x18002d82a  mov     r9d, eax; char *
0x18002d82d  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d834  mov     edx, 4Bh ; 'K'; void *
0x18002d839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d83e  nop
0x18002d83f  cmp     [rsp+98h+var_48], rsi
0x18002d844  jz      short loc_18002D851
0x18002d846  lea     rcx, [rsp+98h+var_48]
0x18002d84b  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d850  nop
0x18002d851  cmp     [rsp+98h+var_58], rsi
0x18002d856  jz      short loc_18002D863
0x18002d858  lea     rcx, [rsp+98h+var_58]
0x18002d85d  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d862  nop
0x18002d863  cmp     [rsp+98h+var_50], rsi
0x18002d868  jz      short loc_18002D875
0x18002d86a  lea     rcx, [rsp+98h+var_50]
0x18002d86f  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d874  nop
0x18002d875  call    cs:__imp_CoUninitialize
0x18002d87b  mov     eax, ebx
0x18002d87d  jmp     loc_18002DA00
0x18002d882  mov     rcx, [rsp+98h+var_48]
0x18002d887  test    rcx, rcx
0x18002d88a  jnz     short loc_18002D899
0x18002d88c  mov     [rsp+98h+arg_18], rsi
0x18002d894  mov     rcx, rsi
0x18002d897  jmp     short loc_18002D8E3
0x18002d899  mov     [rsp+98h+var_40], rsi
0x18002d89e  mov     [rsp+98h+var_38], esi
0x18002d8a2  xorps   xmm0, xmm0
0x18002d8a5  movdqu  [rsp+98h+var_30], xmm0
0x18002d8ab  mov     rax, [rcx]
0x18002d8ae  lea     r8, [rsp+98h+var_40]
0x18002d8b3  lea     rdx, ??$guid_v@UIWpnSystemRegistrationEndpoint@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IWpnSystemRegistrationEndpoint>
0x18002d8ba  mov     rax, [rax]
0x18002d8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8c2  lea     r8, [rsp+98h+var_38]
0x18002d8c7  mov     edx, eax
0x18002d8c9  lea     rcx, [rsp+98h+arg_18]
0x18002d8d1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002d8d6  mov     rcx, [rsp+98h+var_40]
0x18002d8db  mov     [rsp+98h+arg_18], rcx
0x18002d8e3  mov     rax, [rcx]
0x18002d8e6  mov     [rsp+98h+var_70], rsi
0x18002d8eb  mov     [rsp+98h+var_78], esi; int
0x18002d8ef  mov     r9d, edi
0x18002d8f2  lea     r8, aWindowsSystemt; "Windows.SystemToast.Ethernet"
0x18002d8f9  lea     rdx, aSystem; "System"
0x18002d900  mov     rax, [rax+18h]
0x18002d904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d909  mov     ebx, eax
0x18002d90b  test    eax, eax
0x18002d90d  jns     short loc_18002D97D
0x18002d90f  mov     rcx, [rsp+98h]; this
0x18002d917  mov     r9d, eax; char *
0x18002d91a  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d921  mov     edx, 53h ; 'S'; void *
0x18002d926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d92b  nop
0x18002d92c  lea     rcx, [rsp+98h+arg_18]
0x18002d934  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d939  nop
0x18002d93a  cmp     [rsp+98h+var_48], rsi
0x18002d93f  jz      short loc_18002D94C
0x18002d941  lea     rcx, [rsp+98h+var_48]
0x18002d946  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d94b  nop
0x18002d94c  cmp     [rsp+98h+var_58], rsi
0x18002d951  jz      short loc_18002D95E
0x18002d953  lea     rcx, [rsp+98h+var_58]
0x18002d958  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d95d  nop
0x18002d95e  cmp     [rsp+98h+var_50], rsi
0x18002d963  jz      short loc_18002D970
0x18002d965  lea     rcx, [rsp+98h+var_50]
0x18002d96a  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d96f  nop
0x18002d970  call    cs:__imp_CoUninitialize
0x18002d976  mov     eax, ebx
0x18002d978  jmp     loc_18002DA00
0x18002d97d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d984  cmp     rcx, r14
0x18002d987  jz      short loc_18002D9AB
0x18002d989  cmp     byte ptr [rcx+19h], 4
0x18002d98d  jb      short loc_18002D9AB
0x18002d98f  test    byte ptr [rcx+1Ch], 1
0x18002d993  jz      short loc_18002D9AB
0x18002d995  mov     edx, 0Ch
0x18002d99a  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d9a1  mov     rcx, [rcx+10h]
0x18002d9a5  call    WPP_SF_
0x18002d9aa  nop
0x18002d9ab  lea     rcx, [rsp+98h+arg_18]
0x18002d9b3  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d9b8  nop
0x18002d9b9  cmp     [rsp+98h+var_48], rsi
0x18002d9be  jz      short loc_18002D9CB
0x18002d9c0  lea     rcx, [rsp+98h+var_48]
0x18002d9c5  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d9ca  nop
0x18002d9cb  cmp     [rsp+98h+var_58], rsi
0x18002d9d0  jz      short loc_18002D9DD
0x18002d9d2  lea     rcx, [rsp+98h+var_58]
0x18002d9d7  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d9dc  nop
0x18002d9dd  cmp     [rsp+98h+var_50], rsi
0x18002d9e2  jz      short loc_18002D9EF
0x18002d9e4  lea     rcx, [rsp+98h+var_50]
0x18002d9e9  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x18002d9ee  nop
0x18002d9ef  call    cs:__imp_CoUninitialize
0x18002d9f5  xor     eax, eax
0x18002d9f7  jmp     short loc_18002DA00
0x18002d9f9  mov     eax, [rsp+98h+arg_8]
0x18002da00  mov     rbx, [rsp+98h+arg_0]
0x18002da08  add     rsp, 80h
0x18002da0f  pop     r14
0x18002da11  pop     rdi
0x18002da12  pop     rsi
0x18002da13  retn
0x18002da14  mov     r9d, eax; char *
0x18002da17  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
