# ConfigureRetailDemoInternal::StartRetailDemoService(bool)

- ea: `0x18004e628`
- end: `0x18004e805`
- name: `?StartRetailDemoService@ConfigureRetailDemoInternal@@IEAAJ_N@Z`
- size: `477`
- prototype: `__int64 __fastcall(ConfigureRetailDemoInternal *__hidden this, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004de10`
- `0x18004e110`

## callees

- `0x180007bbc`
- `0x180008544`
- `0x18004e628`
- `0x18004ea30`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e6c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e6c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e77b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e77b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e794`

## string_xrefs

- `0x18004e6ac`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e6e2`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e721`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e766`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e7df`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConfigureRetailDemoInternal::StartRetailDemoService(ConfigureRetailDemoInternal *this, char a2)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v18; // [rsp+50h] [rbp+20h] BYREF
  SIZE_T cb; // [rsp+58h] [rbp+28h] BYREF
  _DWORD *v20; // [rsp+60h] [rbp+30h]

  v18 = 0;
  if ( !a2 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    v14 = WindowsService_CreateInstance(v13, 16, &v18);
    v4 = v14;
    if ( v14 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 40LL))(v18);
      v4 = v14;
      if ( v14 >= 0 )
        goto LABEL_23;
      v15 = 216;
    }
    else
    {
      v15 = 215;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      (const char *)(unsigned int)v14,
      v16);
    goto LABEL_16;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v3 = WindowsService_CreateInstance(v2, 19, &v18);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 197;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      (const char *)v5,
      v16);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return v4;
  }
  LODWORD(cb) = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, SIZE_T *))(*(_QWORD *)v18 + 24LL))(v18, 0, 0, &cb);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147024774 )
  {
    v5 = v4;
    v6 = 201;
    goto LABEL_7;
  }
  v7 = CoTaskMemAlloc((unsigned int)cb);
  v8 = v7;
  v20 = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      (const char *)0x8007000ELL,
      v16);
    goto LABEL_16;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, SIZE_T *))(*(_QWORD *)v18 + 24LL))(
         v18,
         v7,
         (unsigned int)cb,
         &cb);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      (const char *)(unsigned int)v9,
      v16);
    CoTaskMemFree(v8);
LABEL_15:
    v4 = v10;
    goto LABEL_16;
  }
  if ( v8[1] != 2 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
        (const char *)(unsigned int)v11,
        v16);
      CoTaskMemFree(v8);
      goto LABEL_15;
    }
  }
  CoTaskMemFree(v8);
LABEL_23:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x18004e628  mov     [rsp-18h+arg_0], rcx
0x18004e62d  push    rbp
0x18004e62e  push    rbx
0x18004e62f  push    rdi
0x18004e630  mov     rbp, rsp
0x18004e633  sub     rsp, 30h
0x18004e637  mov     [rbp+arg_0], 0
0x18004e63f  test    dl, dl
0x18004e641  jz      loc_18004E79D
0x18004e647  lea     rcx, [rbp+arg_0]
0x18004e64b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e650  lea     r8, [rbp+arg_0]
0x18004e654  mov     edx, 13h
0x18004e659  call    WindowsService_CreateInstance
0x18004e65e  mov     ebx, eax
0x18004e660  test    eax, eax
0x18004e662  jns     short loc_18004E66E
0x18004e664  mov     r9d, eax
0x18004e667  mov     edx, 0C5h
0x18004e66c  jmp     short loc_18004E6AC
0x18004e66e  mov     dword ptr [rbp+cb], 0
0x18004e675  mov     rcx, [rbp+arg_0]
0x18004e679  mov     rax, [rcx]
0x18004e67c  lea     r9, [rbp+cb]
0x18004e680  xor     r8d, r8d
0x18004e683  xor     edx, edx
0x18004e685  mov     rax, [rax+18h]
0x18004e689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e68e  mov     ebx, eax
0x18004e690  mov     eax, 80000000h
0x18004e695  lea     ecx, [rbx+rax]
0x18004e698  test    eax, ecx
0x18004e69a  jnz     short loc_18004E6C1
0x18004e69c  cmp     ebx, 8007007Ah
0x18004e6a2  jz      short loc_18004E6C1
0x18004e6a4  mov     r9d, ebx; char *
0x18004e6a7  mov     edx, 0C9h; void *
0x18004e6ac  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e6b3  mov     rcx, [rbp+18h]; this
0x18004e6b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e6bc  jmp     loc_18004E784
0x18004e6c1  mov     ecx, dword ptr [rbp+cb]; cb
0x18004e6c4  call    cs:__imp_CoTaskMemAlloc
0x18004e6ca  mov     rbx, rax
0x18004e6cd  mov     [rbp+arg_10], rax
0x18004e6d1  test    rax, rax
0x18004e6d4  jnz     short loc_18004E6F9
0x18004e6d6  mov     rcx, [rbp+18h]; this
0x18004e6da  mov     ebx, 8007000Eh
0x18004e6df  mov     r9d, ebx; char *
0x18004e6e2  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e6e9  mov     edx, 0CCh; void *
0x18004e6ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e6f3  nop
0x18004e6f4  jmp     loc_18004E784
0x18004e6f9  mov     rcx, [rbp+arg_0]
0x18004e6fd  mov     rax, [rcx]
0x18004e700  lea     r9, [rbp+cb]
0x18004e704  mov     r8d, dword ptr [rbp+cb]
0x18004e708  mov     rdx, rbx
0x18004e70b  mov     rax, [rax+18h]
0x18004e70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e714  mov     edi, eax
0x18004e716  test    eax, eax
0x18004e718  jns     short loc_18004E73F
0x18004e71a  mov     rcx, [rbp+18h]; this
0x18004e71e  mov     r9d, eax; char *
0x18004e721  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e728  mov     edx, 0CEh; void *
0x18004e72d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e732  nop
0x18004e733  mov     rcx, rbx; pv
0x18004e736  call    cs:__imp_CoTaskMemFree
0x18004e73c  nop
0x18004e73d  jmp     short loc_18004E782
0x18004e73f  mov     edx, 2
0x18004e744  cmp     [rbx+4], edx
0x18004e747  jz      short loc_18004E791
0x18004e749  mov     rcx, [rbp+arg_0]
0x18004e74d  mov     rax, [rcx]
0x18004e750  mov     rax, [rax+20h]
0x18004e754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e759  mov     edi, eax
0x18004e75b  test    eax, eax
0x18004e75d  jns     short loc_18004E791
0x18004e75f  mov     rcx, [rbp+18h]; this
0x18004e763  mov     r9d, eax; char *
0x18004e766  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e76d  mov     edx, 0D1h; void *
0x18004e772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e777  nop
0x18004e778  mov     rcx, rbx; pv
0x18004e77b  call    cs:__imp_CoTaskMemFree
0x18004e781  nop
0x18004e782  mov     ebx, edi
0x18004e784  lea     rcx, [rbp+arg_0]
0x18004e788  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e78d  mov     eax, ebx
0x18004e78f  jmp     short loc_18004E7FD
0x18004e791  mov     rcx, rbx; pv
0x18004e794  call    cs:__imp_CoTaskMemFree
0x18004e79a  nop
0x18004e79b  jmp     short loc_18004E7F2
0x18004e79d  lea     rcx, [rbp+arg_0]
0x18004e7a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e7a6  lea     r8, [rbp+arg_0]
0x18004e7aa  mov     edx, 10h
0x18004e7af  call    WindowsService_CreateInstance
0x18004e7b4  mov     ebx, eax
0x18004e7b6  test    eax, eax
0x18004e7b8  jns     short loc_18004E7C1
0x18004e7ba  mov     edx, 0D7h
0x18004e7bf  jmp     short loc_18004E7DC
0x18004e7c1  mov     rcx, [rbp+arg_0]
0x18004e7c5  mov     rax, [rcx]
0x18004e7c8  mov     rax, [rax+28h]
0x18004e7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7d1  mov     ebx, eax
0x18004e7d3  test    eax, eax
0x18004e7d5  jns     short loc_18004E7F2
0x18004e7d7  mov     edx, 0D8h; void *
0x18004e7dc  mov     r9d, eax; char *
0x18004e7df  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e7e6  mov     rcx, [rbp+18h]; this
0x18004e7ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e7ef  nop
0x18004e7f0  jmp     short loc_18004E784
0x18004e7f2  lea     rcx, [rbp+arg_0]
0x18004e7f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e7fb  xor     eax, eax
0x18004e7fd  add     rsp, 30h
0x18004e801  pop     rdi
0x18004e802  pop     rbx
0x18004e803  pop     rbp
0x18004e804  retn
```
