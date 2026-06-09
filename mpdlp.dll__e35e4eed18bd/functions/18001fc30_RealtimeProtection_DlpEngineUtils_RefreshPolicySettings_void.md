# RealtimeProtection::DlpEngineUtils::RefreshPolicySettings(void)

- ea: `0x18001fc30`
- end: `0x18001fdf7`
- name: `?RefreshPolicySettings@DlpEngineUtils@RealtimeProtection@@YAJXZ`
- size: `455`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007a790`
- `0x180144650`
- `0x18019d7f8`

## callees

- `0x18001fc30`
- `0x18001fdf8`
- `0x18002082c`
- `0x18002ece0`
- `0x1800809d0`
- `0x180089510`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18001fd38`
- `MpClient!MpConfigSetValue` at `0x18001fd8d`
- `MpClient!MpConfigSetValue` at `0x18001fd38`
- `MpClient!MpConfigSetValue` at `0x18001fd8d`
- `MpClient!MpConfigClose` at `0x18001fd04`
- `MpClient!MpConfigClose` at `0x18001fdc9`
- `MpClient!MpConfigClose` at `0x18001fd04`
- `MpClient!MpConfigClose` at `0x18001fdc9`
- `MpClient!MpConfigOpen` at `0x18001fcef`
- `MpClient!MpConfigOpen` at `0x18001fcef`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::RefreshPolicySettings(RealtimeProtection::DlpEngineUtils *this)
{
  int v1; // esi
  EndpointDlp::endpointDlpImpl **Instance; // rax
  int PolicySettings; // ebx
  int v4; // edi
  EndpointDlp::endpointDlpImpl **v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int v12; // eax
  int v13; // eax
  _BYTE v14[16]; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  v1 = -1;
  Instance = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(v14);
  PolicySettings = EndpointDlp::endpointDlpImpl::endpointDlpGetPolicySettings(*Instance, L"BusinessJustification");
  std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(v14);
  v4 = -1;
  if ( PolicySettings >= 0 )
    v4 = PolicySettings;
  v5 = (EndpointDlp::endpointDlpImpl **)EndpointDlp::endpointDlpImpl::GetInstance(v14);
  v6 = EndpointDlp::endpointDlpImpl::endpointDlpGetPolicySettings(*v5, L"IconOverlay");
  std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(v14);
  if ( v6 >= 0 )
    v1 = v6;
  v16 = 0;
  v8 = MpConfigOpen(L"Features", &v16);
  if ( v8 >= 0 )
  {
    if ( v4 >= 0 )
    {
      v15 = v4;
      v12 = MpConfigSetValue(v16, L"SenseDlpShowBypassReasonUx", 1, 4, &v15);
      if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v12);
    }
    if ( v1 >= 0 )
    {
      v15 = v1;
      v13 = MpConfigSetValue(v16, L"DlpShowIconOverlay", 1, 4, &v15);
      if ( v13 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v13);
    }
    if ( v16 )
      MpConfigClose(v16, v7, v9, v10);
    return 0;
  }
  else
  {
    if ( v16 )
      MpConfigClose(v16, v7, v9, v10);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x18001fc30  mov     rax, rsp
0x18001fc33  mov     [rax+8], rbx
0x18001fc37  mov     [rax+10h], rsi
0x18001fc3b  mov     [rax+18h], rdi
0x18001fc3f  mov     [rax+20h], r14
0x18001fc43  push    rbp
0x18001fc44  mov     rbp, rsp
0x18001fc47  sub     rsp, 60h
0x18001fc4b  mov     rax, cs:__security_cookie
0x18001fc52  xor     rax, rsp
0x18001fc55  mov     [rbp+var_10], rax
0x18001fc59  lea     r14, WPP_GLOBAL_Control
0x18001fc60  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc67  cmp     rcx, r14
0x18001fc6a  jz      short loc_18001FC87
0x18001fc6c  test    byte ptr [rcx+1Ch], 4
0x18001fc70  jz      short loc_18001FC87
0x18001fc72  mov     edx, 7Dh ; '}'
0x18001fc77  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18001fc7e  mov     rcx, [rcx+10h]
0x18001fc82  call    WPP_SF_
0x18001fc87  or      esi, 0FFFFFFFFh
0x18001fc8a  lea     rcx, [rbp+var_30]
0x18001fc8e  call    ?GetInstance@endpointDlpImpl@EndpointDlp@@SA?AV?$shared_ptr@VendpointDlpImpl@EndpointDlp@@@std@@XZ; EndpointDlp::endpointDlpImpl::GetInstance(void)
0x18001fc93  lea     rdx, aBusinessjustif; "BusinessJustification"
0x18001fc9a  mov     rcx, [rax]; this
0x18001fc9d  call    ?endpointDlpGetPolicySettings@endpointDlpImpl@EndpointDlp@@QEBAHPEB_W@Z; EndpointDlp::endpointDlpImpl::endpointDlpGetPolicySettings(wchar_t const *)
0x18001fca2  mov     ebx, eax
0x18001fca4  lea     rcx, [rbp+var_30]
0x18001fca8  call    ?_Decref@?$_Ptr_base@VendpointDlpImpl@EndpointDlp@@@std@@IEAAXXZ; std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(void)
0x18001fcad  mov     edi, esi
0x18001fcaf  test    ebx, ebx
0x18001fcb1  cmovns  edi, ebx
0x18001fcb4  lea     rcx, [rbp+var_30]
0x18001fcb8  call    ?GetInstance@endpointDlpImpl@EndpointDlp@@SA?AV?$shared_ptr@VendpointDlpImpl@EndpointDlp@@@std@@XZ; EndpointDlp::endpointDlpImpl::GetInstance(void)
0x18001fcbd  lea     rdx, aIconoverlay; "IconOverlay"
0x18001fcc4  mov     rcx, [rax]; this
0x18001fcc7  call    ?endpointDlpGetPolicySettings@endpointDlpImpl@EndpointDlp@@QEBAHPEB_W@Z; EndpointDlp::endpointDlpImpl::endpointDlpGetPolicySettings(wchar_t const *)
0x18001fccc  mov     ebx, eax
0x18001fcce  lea     rcx, [rbp+var_30]
0x18001fcd2  call    ?_Decref@?$_Ptr_base@VendpointDlpImpl@EndpointDlp@@@std@@IEAAXXZ; std::_Ptr_base<EndpointDlp::endpointDlpImpl>::_Decref(void)
0x18001fcd7  test    ebx, ebx
0x18001fcd9  cmovns  esi, ebx
0x18001fcdc  mov     [rbp+var_18], 0
0x18001fce4  lea     rdx, [rbp+var_18]
0x18001fce8  lea     rcx, aFeatures_0; "Features"
0x18001fcef  call    cs:__imp_MpConfigOpen
0x18001fcf5  mov     ebx, eax
0x18001fcf7  test    eax, eax
0x18001fcf9  jns     short loc_18001FD11
0x18001fcfb  mov     rcx, [rbp+var_18]
0x18001fcff  test    rcx, rcx
0x18001fd02  jz      short loc_18001FD0A
0x18001fd04  call    cs:__imp_MpConfigClose
0x18001fd0a  mov     eax, ebx
0x18001fd0c  jmp     loc_18001FDD1
0x18001fd11  mov     ebx, 1
0x18001fd16  test    edi, edi
0x18001fd18  js      short loc_18001FD69
0x18001fd1a  mov     [rbp+var_20], edi
0x18001fd1d  lea     rax, [rbp+var_20]
0x18001fd21  mov     [rsp+60h+var_40], rax
0x18001fd26  lea     r9d, [rbx+3]
0x18001fd2a  mov     r8d, ebx
0x18001fd2d  lea     rdx, aSensedlpshowby; "SenseDlpShowBypassReasonUx"
0x18001fd34  mov     rcx, [rbp+var_18]
0x18001fd38  call    cs:__imp_MpConfigSetValue
0x18001fd3e  test    eax, eax
0x18001fd40  jns     short loc_18001FD69
0x18001fd42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd49  cmp     rcx, r14
0x18001fd4c  jz      short loc_18001FD69
0x18001fd4e  test    [rcx+1Ch], bl
0x18001fd51  jz      short loc_18001FD69
0x18001fd53  lea     edx, [rbx+7Dh]
0x18001fd56  mov     r9d, eax
0x18001fd59  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18001fd60  mov     rcx, [rcx+10h]
0x18001fd64  call    WPP_SF_d
0x18001fd69  test    esi, esi
0x18001fd6b  js      short loc_18001FDC0
0x18001fd6d  mov     [rbp+var_20], esi
0x18001fd70  lea     rax, [rbp+var_20]
0x18001fd74  mov     [rsp+60h+var_40], rax
0x18001fd79  mov     r9d, 4
0x18001fd7f  mov     r8d, ebx
0x18001fd82  lea     rdx, aDlpshowiconove; "DlpShowIconOverlay"
0x18001fd89  mov     rcx, [rbp+var_18]
0x18001fd8d  call    cs:__imp_MpConfigSetValue
0x18001fd93  test    eax, eax
0x18001fd95  jns     short loc_18001FDC0
0x18001fd97  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd9e  cmp     rcx, r14
0x18001fda1  jz      short loc_18001FDC0
0x18001fda3  test    [rcx+1Ch], bl
0x18001fda6  jz      short loc_18001FDC0
0x18001fda8  mov     edx, 7Fh
0x18001fdad  mov     r9d, eax
0x18001fdb0  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18001fdb7  mov     rcx, [rcx+10h]
0x18001fdbb  call    WPP_SF_d
0x18001fdc0  mov     rcx, [rbp+var_18]
0x18001fdc4  test    rcx, rcx
0x18001fdc7  jz      short loc_18001FDCF
0x18001fdc9  call    cs:__imp_MpConfigClose
0x18001fdcf  xor     eax, eax
0x18001fdd1  mov     rcx, [rbp+var_10]
0x18001fdd5  xor     rcx, rsp; StackCookie
0x18001fdd8  call    __security_check_cookie
0x18001fddd  lea     r11, [rsp+60h+var_s0]
0x18001fde2  mov     rbx, [r11+10h]
0x18001fde6  mov     rsi, [r11+18h]
0x18001fdea  mov     rdi, [r11+20h]
0x18001fdee  mov     r14, [r11+28h]
0x18001fdf2  mov     rsp, r11
0x18001fdf5  pop     rbp
0x18001fdf6  retn
```
