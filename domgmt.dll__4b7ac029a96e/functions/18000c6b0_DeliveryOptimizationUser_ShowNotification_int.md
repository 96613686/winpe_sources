# DeliveryOptimizationUser::ShowNotification(int)

- ea: `0x18000c6b0`
- end: `0x18000c94a`
- name: `?ShowNotification@DeliveryOptimizationUser@@UEAAJH@Z`
- size: `666`
- prototype: `__int64 __fastcall(DeliveryOptimizationUser *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001ba0`
- `0x180005964`
- `0x180008d88`
- `0x18000c1cc`
- `0x18000c6b0`
- `0x18000c950`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c763`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c763`

## pseudocode

```c
__int64 __fastcall DeliveryOptimizationUser::ShowNotification(DeliveryOptimizationUser *this, int a2)
{
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  HRESULT v7; // eax
  LPVOID v8; // rcx
  int v9; // eax
  _QWORD *v10; // rcx
  LPVOID v11; // rcx
  __int64 v12; // rax
  __int128 *v13; // rdx
  int v14; // eax
  _QWORD *v15; // rcx
  LPVOID v16; // rcx
  _QWORD *v17; // rcx
  LPVOID v18; // rcx
  LPVOID ppv; // [rsp+90h] [rbp-29h] BYREF
  _QWORD *v21; // [rsp+98h] [rbp-21h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-9h] BYREF
  int v24; // [rsp+B8h] [rbp-1h]
  __int128 v25; // [rsp+C0h] [rbp+7h] BYREF
  __m128i si128; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = CheckCallerAccess();
  v5 = v3;
  if ( v3 >= 0 )
  {
    v25 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v25) = 0;
    v6 = DeliveryOptimizationUser::_BuildToastXml(v4, a2 != 0, (__int64)&v25);
    v5 = v6;
    if ( v6 >= 0 )
    {
      ppv = 0;
      v7 = CoCreateInstance(
             &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
             0,
             4u,
             &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
             &ppv);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v21 = 0;
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD **))(*(_QWORD *)ppv + 24LL))(ppv, &v21);
        v5 = v9;
        if ( v9 >= 0 )
        {
          v22[0] = 0;
          v12 = *v21;
          v13 = &v25;
          if ( si128.m128i_i64[1] > 7uLL )
            v13 = (__int128 *)v25;
          v23 = 0;
          v24 = 0;
          v14 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, const wchar_t *, _QWORD, int, __int128 *, _QWORD, _QWORD, __int64 *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, int, _DWORD *))(v12 + 64))(
                  v21,
                  L"NonImmersivePackage",
                  L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                  0,
                  1,
                  v13,
                  0,
                  0,
                  &v23,
                  0,
                  0,
                  0,
                  0,
                  0,
                  1,
                  v22);
          v5 = v14;
          if ( v14 >= 0 )
          {
            v17 = v21;
            if ( v21 )
            {
              v21 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
            }
            v18 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
            }
            v5 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D,
              (int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
              (const char *)(unsigned int)v14);
            v15 = v21;
            if ( v21 )
            {
              v21 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
            }
            v16 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x27,
            (int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
            (const char *)(unsigned int)v9);
          v10 = v21;
          if ( v21 )
          {
            v21 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
          }
          v11 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24,
          (int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
          (const char *)(unsigned int)v7);
        v8 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
        (const char *)(unsigned int)v6);
    }
    std::wstring::~wstring((char **)&v25);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
      (const char *)(unsigned int)v3);
  }
  return v5;
}

```

## disassembly

```asm
0x18000c6b0  push    rbp
0x18000c6b2  push    rbx
0x18000c6b3  push    rsi
0x18000c6b4  push    rdi
0x18000c6b5  lea     rbp, [rsp-3Fh]
0x18000c6ba  sub     rsp, 0F8h
0x18000c6c1  mov     rax, cs:__security_cookie
0x18000c6c8  xor     rax, rsp
0x18000c6cb  mov     [rbp+57h+var_30], rax
0x18000c6cf  mov     edi, edx
0x18000c6d1  call    ?CheckCallerAccess@@YAJXZ; CheckCallerAccess(void)
0x18000c6d6  mov     ebx, eax
0x18000c6d8  xor     esi, esi
0x18000c6da  test    eax, eax
0x18000c6dc  jns     short loc_18000C6F9
0x18000c6de  mov     rcx, [rbp+5Fh]; this
0x18000c6e2  mov     r9d, eax; char *
0x18000c6e5  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c6ec  lea     edx, [rsi+1Eh]; void *
0x18000c6ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6f4  jmp     loc_18000C930
0x18000c6f9  xorps   xmm0, xmm0
0x18000c6fc  movups  [rbp+57h+var_50], xmm0
0x18000c700  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000c708  movdqu  [rbp+57h+var_40], xmm1
0x18000c70d  mov     word ptr [rbp+57h+var_50], si
0x18000c711  test    edi, edi
0x18000c713  setnz   dl
0x18000c716  lea     r8, [rbp+57h+var_50]
0x18000c71a  call    ?_BuildToastXml@DeliveryOptimizationUser@@AEAAJ_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeliveryOptimizationUser::_BuildToastXml(bool,std::wstring &)
0x18000c71f  mov     ebx, eax
0x18000c721  test    eax, eax
0x18000c723  jns     short loc_18000C742
0x18000c725  mov     rcx, [rbp+5Fh]; this
0x18000c729  mov     r9d, eax; char *
0x18000c72c  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c733  mov     edx, 21h ; '!'; void *
0x18000c738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c73d  jmp     loc_18000C927
0x18000c742  mov     [rbp+57h+var_80], rsi
0x18000c746  lea     rax, [rbp+57h+var_80]
0x18000c74a  mov     [rsp+110h+ppv], rax; int
0x18000c74f  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18000c756  xor     edx, edx; pUnkOuter
0x18000c758  lea     r8d, [rdx+4]; dwClsContext
0x18000c75c  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000c763  call    cs:__imp_CoCreateInstance
0x18000c769  mov     ebx, eax
0x18000c76b  test    eax, eax
0x18000c76d  jns     short loc_18000C7A7
0x18000c76f  mov     rcx, [rbp+5Fh]; this
0x18000c773  mov     r9d, eax; char *
0x18000c776  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c77d  mov     edx, 24h ; '$'; void *
0x18000c782  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c787  nop
0x18000c788  mov     rcx, [rbp+57h+var_80]
0x18000c78c  test    rcx, rcx
0x18000c78f  jz      short loc_18000C7A2
0x18000c791  mov     [rbp+57h+var_80], rsi
0x18000c795  mov     rax, [rcx]
0x18000c798  mov     rax, [rax+10h]
0x18000c79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a1  nop
0x18000c7a2  jmp     loc_18000C927
0x18000c7a7  mov     [rbp+57h+var_78], rsi
0x18000c7ab  mov     rcx, [rbp+57h+var_80]
0x18000c7af  mov     rax, [rcx]
0x18000c7b2  lea     rdx, [rbp+57h+var_78]
0x18000c7b6  mov     rax, [rax+18h]
0x18000c7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7bf  mov     ebx, eax
0x18000c7c1  test    eax, eax
0x18000c7c3  jns     short loc_18000C817
0x18000c7c5  mov     rcx, [rbp+5Fh]; this
0x18000c7c9  mov     r9d, eax; char *
0x18000c7cc  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c7d3  mov     edx, 27h ; '''; void *
0x18000c7d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7dd  nop
0x18000c7de  mov     rcx, [rbp+57h+var_78]
0x18000c7e2  test    rcx, rcx
0x18000c7e5  jz      short loc_18000C7F8
0x18000c7e7  mov     [rbp+57h+var_78], rsi
0x18000c7eb  mov     rax, [rcx]
0x18000c7ee  mov     rax, [rax+10h]
0x18000c7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f7  nop
0x18000c7f8  mov     rcx, [rbp+57h+var_80]
0x18000c7fc  test    rcx, rcx
0x18000c7ff  jz      short loc_18000C812
0x18000c801  mov     [rbp+57h+var_80], rsi
0x18000c805  mov     rax, [rcx]
0x18000c808  mov     rax, [rax+10h]
0x18000c80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c811  nop
0x18000c812  jmp     loc_18000C927
0x18000c817  mov     [rbp+57h+var_70], esi
0x18000c81a  xor     r8d, r8d
0x18000c81d  mov     rcx, [rbp+57h+var_78]
0x18000c821  mov     rax, [rcx]
0x18000c824  lea     rdx, [rbp+57h+var_50]
0x18000c828  cmp     qword ptr [rbp+57h+var_40+8], 7
0x18000c82d  cmova   rdx, qword ptr [rbp+57h+var_50]
0x18000c832  mov     [rbp+57h+var_60], r8
0x18000c836  mov     [rbp+57h+var_58], r8d
0x18000c83a  lea     r8, [rbp+57h+var_70]
0x18000c83e  mov     [rsp+110h+var_98], r8
0x18000c843  mov     r9d, 1
0x18000c849  mov     [rsp+110h+var_A0], r9d
0x18000c84e  mov     [rsp+110h+var_A8], rsi
0x18000c853  mov     [rsp+110h+var_B0], rsi
0x18000c858  mov     [rsp+110h+var_B8], rsi
0x18000c85d  mov     [rsp+110h+var_C0], esi
0x18000c861  mov     [rsp+110h+var_C8], esi
0x18000c865  lea     r8, [rbp+57h+var_60]
0x18000c869  mov     [rsp+110h+var_D0], r8
0x18000c86e  mov     [rsp+110h+var_D8], rsi
0x18000c873  mov     [rsp+110h+var_E0], rsi
0x18000c878  mov     [rsp+110h+var_E8], rdx
0x18000c87d  mov     dword ptr [rsp+110h+ppv], r9d; int
0x18000c882  xor     r9d, r9d
0x18000c885  lea     r8, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18000c88c  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x18000c893  mov     rax, [rax+40h]
0x18000c897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89c  mov     ebx, eax
0x18000c89e  test    eax, eax
0x18000c8a0  jns     short loc_18000C8F1
0x18000c8a2  mov     rcx, [rbp+5Fh]; this
0x18000c8a6  mov     r9d, eax; char *
0x18000c8a9  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c8b0  mov     edx, 2Dh ; '-'; void *
0x18000c8b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8ba  nop
0x18000c8bb  mov     rcx, [rbp+57h+var_78]
0x18000c8bf  test    rcx, rcx
0x18000c8c2  jz      short loc_18000C8D5
0x18000c8c4  mov     [rbp+57h+var_78], rsi
0x18000c8c8  mov     rax, [rcx]
0x18000c8cb  mov     rax, [rax+10h]
0x18000c8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8d4  nop
0x18000c8d5  mov     rcx, [rbp+57h+var_80]
0x18000c8d9  test    rcx, rcx
0x18000c8dc  jz      short loc_18000C8EF
0x18000c8de  mov     [rbp+57h+var_80], rsi
0x18000c8e2  mov     rax, [rcx]
0x18000c8e5  mov     rax, [rax+10h]
0x18000c8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8ee  nop
0x18000c8ef  jmp     short loc_18000C927
0x18000c8f1  mov     rcx, [rbp+57h+var_78]
0x18000c8f5  test    rcx, rcx
0x18000c8f8  jz      short loc_18000C90B
0x18000c8fa  mov     [rbp+57h+var_78], rsi
0x18000c8fe  mov     rax, [rcx]
0x18000c901  mov     rax, [rax+10h]
0x18000c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90a  nop
0x18000c90b  mov     rcx, [rbp+57h+var_80]
0x18000c90f  test    rcx, rcx
0x18000c912  jz      short loc_18000C925
0x18000c914  mov     [rbp+57h+var_80], rsi
0x18000c918  mov     rax, [rcx]
0x18000c91b  mov     rax, [rax+10h]
0x18000c91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c924  nop
0x18000c925  mov     ebx, esi
0x18000c927  lea     rcx, [rbp+57h+var_50]
0x18000c92b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c930  mov     eax, ebx
0x18000c932  mov     rcx, [rbp+57h+var_30]
0x18000c936  xor     rcx, rsp; StackCookie
0x18000c939  call    __security_check_cookie
0x18000c93e  add     rsp, 0F8h
0x18000c945  pop     rdi
0x18000c946  pop     rsi
0x18000c947  pop     rbx
0x18000c948  pop     rbp
0x18000c949  retn
```
