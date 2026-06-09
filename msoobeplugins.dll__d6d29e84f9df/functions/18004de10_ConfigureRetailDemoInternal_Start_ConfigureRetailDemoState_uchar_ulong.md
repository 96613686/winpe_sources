# ConfigureRetailDemoInternal::Start(ConfigureRetailDemoState,uchar *,ulong)

- ea: `0x18004de10`
- end: `0x18004e0a0`
- name: `?Start@ConfigureRetailDemoInternal@@UEAAJW4ConfigureRetailDemoState@@PEAEK@Z`
- size: `656`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007bbc`
- `0x180008544`
- `0x180019080`
- `0x18004dbc4`
- `0x18004de10`
- `0x18004e628`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004debe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004df95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e012`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004debe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004df95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e012`

## string_xrefs

- `0x18004de43`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004df13`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004dfc3`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e025`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConfigureRetailDemoInternal::Start(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  unsigned int started; // ebx
  __int64 v8; // rdx
  ConfigureRetailDemoInternal *v9; // rcx
  HRESULT v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  ConfigureRetailDemoInternal *v13; // rcx
  HRESULT v14; // eax
  __int64 v15; // rdx
  HRESULT v16; // eax
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  int ppvb; // [rsp+20h] [rbp-20h]
  LPVOID v21; // [rsp+30h] [rbp-10h] BYREF
  LPVOID v22; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v24; // [rsp+68h] [rbp+28h] BYREF

  if ( a2 != 1 )
  {
    v24 = 0;
    if ( (int)SHRegGetBOOLWithREGSAM(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
                L"TestBlockRdxWebApp",
                a4,
                &v24) >= 0
      && v24 )
    {
      v21 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      v10 = CoCreateInstance(
              &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
              0,
              1u,
              &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
              &v21);
      started = v10;
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 343;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
          (const char *)v11,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
        return started;
      }
      started = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)v21 + 32LL))(v21, a3, a4, 1);
      if ( a2 != 2 && (int)(started + 0x80000000) >= 0 && started != -2147023580 )
      {
        v11 = started;
        v12 = 348;
        goto LABEL_12;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    }
    started = ConfigureRetailDemoInternal::SetRegistryInfo(v9);
    if ( (started & 0x80000000) != 0 )
    {
      v8 = 352;
      goto LABEL_3;
    }
    started = ConfigureRetailDemoInternal::StartRetailDemoService(v13, 0);
    if ( (started & 0x80000000) != 0 )
    {
      v8 = 353;
      goto LABEL_3;
    }
    v22 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    v14 = CoCreateInstance(
            &GUID_a8d93b39_2113_492e_b014_801d01c95eca,
            0,
            0x17u,
            &GUID_b1857662_f8e5_4ba3_8eb9_c08097932bae,
            &v22);
    started = v14;
    if ( v14 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 24LL))(v22);
      started = v14;
      if ( v14 >= 0 )
      {
        if ( a2 == 2 )
        {
          v21 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
          v16 = CoCreateInstance(
                  &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
                  0,
                  1u,
                  &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
                  &v21);
          started = v16;
          if ( v16 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x169,
              (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
              (const char *)(unsigned int)v16,
              ppvb);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
            goto LABEL_28;
          }
          (*(void (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)v21 + 32LL))(v21, a3, a4, 1);
          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v21 + 32LL))(v21, 0, 0, 0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
        }
        started = 0;
        goto LABEL_28;
      }
      v15 = 356;
    }
    else
    {
      v15 = 355;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      (const char *)(unsigned int)v14,
      ppva);
LABEL_28:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    return started;
  }
  started = -2147024809;
  v8 = 335;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
    (const char *)started,
    ppv);
  return started;
}

```

## disassembly

```asm
0x18004de10  mov     [rsp-18h+arg_0], rbx
0x18004de15  mov     [rsp-18h+arg_10], rsi
0x18004de1a  push    rbp
0x18004de1b  push    rdi
0x18004de1c  push    r14
0x18004de1e  mov     rbp, rsp
0x18004de21  sub     rsp, 40h
0x18004de25  mov     esi, r9d
0x18004de28  mov     r14, r8
0x18004de2b  mov     edi, edx
0x18004de2d  cmp     edx, 1
0x18004de30  jnz     short loc_18004DE54
0x18004de32  mov     ebx, 80070057h
0x18004de37  mov     edx, 14Fh; void *
0x18004de3c  mov     rcx, [rbp+18h]; this
0x18004de40  mov     r9d, ebx; char *
0x18004de43  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004de4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004de4f  jmp     loc_18004E08B
0x18004de54  mov     [rbp+arg_8], 0
0x18004de5b  lea     rax, [rbp+arg_8]
0x18004de5f  mov     qword ptr [rsp+40h+ppv], rax; int *
0x18004de64  lea     r8, aTestblockrdxwe; "TestBlockRdxWebApp"
0x18004de6b  lea     rdx, aSoftwareMicros_39; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004de72  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004de79  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18004de7e  test    eax, eax
0x18004de80  js      loc_18004DF3B
0x18004de86  cmp     [rbp+arg_8], 0
0x18004de8a  jz      loc_18004DF3B
0x18004de90  mov     [rbp+var_10], 0
0x18004de98  lea     rcx, [rbp+var_10]
0x18004de9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004dea1  lea     rax, [rbp+var_10]
0x18004dea5  mov     qword ptr [rsp+40h+ppv], rax; int
0x18004deaa  lea     r9, _GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c; riid
0x18004deb1  xor     edx, edx; pUnkOuter
0x18004deb3  lea     r8d, [rdx+1]; dwClsContext
0x18004deb7  lea     rcx, _GUID_54337179_c8b2_4ed4_95e4_95601c850d8c; rclsid
0x18004debe  call    cs:__imp_CoCreateInstance
0x18004dec4  mov     ebx, eax
0x18004dec6  test    eax, eax
0x18004dec8  jns     short loc_18004DED4
0x18004deca  mov     r9d, eax
0x18004decd  mov     edx, 157h
0x18004ded2  jmp     short loc_18004DF13
0x18004ded4  mov     rcx, [rbp+var_10]
0x18004ded8  mov     rax, [rcx]
0x18004dedb  mov     r9d, 1
0x18004dee1  mov     r8d, esi
0x18004dee4  mov     rdx, r14
0x18004dee7  mov     rax, [rax+20h]
0x18004deeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004def0  mov     ebx, eax
0x18004def2  cmp     edi, 2
0x18004def5  jz      short loc_18004DF32
0x18004def7  mov     eax, 80000000h
0x18004defc  lea     ecx, [rbx+rax]
0x18004deff  test    eax, ecx
0x18004df01  jnz     short loc_18004DF32
0x18004df03  cmp     ebx, 80070524h
0x18004df09  jz      short loc_18004DF32
0x18004df0b  mov     r9d, ebx; char *
0x18004df0e  mov     edx, 15Ch; void *
0x18004df13  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004df1a  mov     rcx, [rbp+18h]; this
0x18004df1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004df23  nop
0x18004df24  lea     rcx, [rbp+var_10]
0x18004df28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004df2d  jmp     loc_18004E08B
0x18004df32  lea     rcx, [rbp+var_10]
0x18004df36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004df3b  call    ?SetRegistryInfo@ConfigureRetailDemoInternal@@IEAAJXZ; ConfigureRetailDemoInternal::SetRegistryInfo(void)
0x18004df40  mov     ebx, eax
0x18004df42  test    eax, eax
0x18004df44  jns     short loc_18004DF50
0x18004df46  mov     edx, 160h
0x18004df4b  jmp     loc_18004DE3C
0x18004df50  xor     edx, edx; bool
0x18004df52  call    ?StartRetailDemoService@ConfigureRetailDemoInternal@@IEAAJ_N@Z; ConfigureRetailDemoInternal::StartRetailDemoService(bool)
0x18004df57  mov     ebx, eax
0x18004df59  test    eax, eax
0x18004df5b  jns     short loc_18004DF67
0x18004df5d  mov     edx, 161h
0x18004df62  jmp     loc_18004DE3C
0x18004df67  mov     [rbp+var_8], 0
0x18004df6f  lea     rcx, [rbp+var_8]
0x18004df73  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004df78  lea     rax, [rbp+var_8]
0x18004df7c  mov     qword ptr [rsp+40h+ppv], rax; int
0x18004df81  lea     r9, _GUID_b1857662_f8e5_4ba3_8eb9_c08097932bae; riid
0x18004df88  xor     edx, edx; pUnkOuter
0x18004df8a  lea     r8d, [rdx+17h]; dwClsContext
0x18004df8e  lea     rcx, _GUID_a8d93b39_2113_492e_b014_801d01c95eca; rclsid
0x18004df95  call    cs:__imp_CoCreateInstance
0x18004df9b  mov     ebx, eax
0x18004df9d  test    eax, eax
0x18004df9f  jns     short loc_18004DFA8
0x18004dfa1  mov     edx, 163h
0x18004dfa6  jmp     short loc_18004DFC3
0x18004dfa8  mov     rcx, [rbp+var_8]
0x18004dfac  mov     rax, [rcx]
0x18004dfaf  mov     rax, [rax+18h]
0x18004dfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfb8  mov     ebx, eax
0x18004dfba  test    eax, eax
0x18004dfbc  jns     short loc_18004DFDB
0x18004dfbe  mov     edx, 164h; void *
0x18004dfc3  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004dfca  mov     r9d, eax; char *
0x18004dfcd  mov     rcx, [rbp+18h]; this
0x18004dfd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dfd6  jmp     loc_18004E082
0x18004dfdb  cmp     edi, 2
0x18004dfde  jnz     loc_18004E080
0x18004dfe4  mov     [rbp+var_10], 0
0x18004dfec  lea     rcx, [rbp+var_10]
0x18004dff0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004dff5  lea     rax, [rbp+var_10]
0x18004dff9  mov     qword ptr [rsp+40h+ppv], rax; int
0x18004dffe  lea     r9, _GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c; riid
0x18004e005  xor     edx, edx; pUnkOuter
0x18004e007  lea     r8d, [rdi-1]; dwClsContext
0x18004e00b  lea     rcx, _GUID_54337179_c8b2_4ed4_95e4_95601c850d8c; rclsid
0x18004e012  call    cs:__imp_CoCreateInstance
0x18004e018  mov     ebx, eax
0x18004e01a  test    eax, eax
0x18004e01c  jns     short loc_18004E042
0x18004e01e  mov     rcx, [rbp+18h]; this
0x18004e022  mov     r9d, eax; char *
0x18004e025  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e02c  mov     edx, 169h; void *
0x18004e031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e036  nop
0x18004e037  lea     rcx, [rbp+var_10]
0x18004e03b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e040  jmp     short loc_18004E082
0x18004e042  mov     rcx, [rbp+var_10]
0x18004e046  mov     rax, [rcx]
0x18004e049  mov     r9d, 1
0x18004e04f  mov     r8d, esi
0x18004e052  mov     rdx, r14
0x18004e055  mov     rax, [rax+20h]
0x18004e059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e05e  mov     rcx, [rbp+var_10]
0x18004e062  mov     rax, [rcx]
0x18004e065  xor     r9d, r9d
0x18004e068  xor     r8d, r8d
0x18004e06b  xor     edx, edx
0x18004e06d  mov     rax, [rax+20h]
0x18004e071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e076  nop
0x18004e077  lea     rcx, [rbp+var_10]
0x18004e07b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e080  xor     ebx, ebx
0x18004e082  lea     rcx, [rbp+var_8]
0x18004e086  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e08b  mov     eax, ebx
0x18004e08d  mov     rbx, [rsp+40h+arg_0]
0x18004e092  mov     rsi, [rsp+40h+arg_10]
0x18004e097  add     rsp, 40h
0x18004e09b  pop     r14
0x18004e09d  pop     rdi
0x18004e09e  pop     rbp
0x18004e09f  retn
```
