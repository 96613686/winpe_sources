# CreateConfigManagerFromSession(IConfigSession2 *,IConfigManager2 * *)

- ea: `0x18005a370`
- end: `0x18005a64c`
- name: `?CreateConfigManagerFromSession@@YAJPEAUIConfigSession2@@PEAPEAUIConfigManager2@@@Z`
- size: `732`
- prototype: `__int64 __fastcall(struct IConfigSession2 *, struct IConfigManager2 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c628`
- `0x18005ce1c`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x18005a370`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005a4e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a4e0`
- `OLEAUT32!__imp_VariantInit` at `0x18005a415`
- `OLEAUT32!__imp_VariantInit` at `0x18005a4c7`
- `OLEAUT32!__imp_VariantInit` at `0x18005a574`
- `OLEAUT32!__imp_VariantInit` at `0x18005a415`
- `OLEAUT32!__imp_VariantInit` at `0x18005a4c7`
- `OLEAUT32!__imp_VariantInit` at `0x18005a574`
- `OLEAUT32!__imp_VariantClear` at `0x18005a478`
- `OLEAUT32!__imp_VariantClear` at `0x18005a4b0`
- `OLEAUT32!__imp_VariantClear` at `0x18005a4f9`
- `OLEAUT32!__imp_VariantClear` at `0x18005a55f`
- `OLEAUT32!__imp_VariantClear` at `0x18005a5e1`
- `OLEAUT32!__imp_VariantClear` at `0x18005a605`
- `OLEAUT32!__imp_VariantClear` at `0x18005a616`
- `OLEAUT32!__imp_VariantClear` at `0x18005a478`
- `OLEAUT32!__imp_VariantClear` at `0x18005a4b0`
- `OLEAUT32!__imp_VariantClear` at `0x18005a4f9`
- `OLEAUT32!__imp_VariantClear` at `0x18005a55f`
- `OLEAUT32!__imp_VariantClear` at `0x18005a5e1`
- `OLEAUT32!__imp_VariantClear` at `0x18005a605`
- `OLEAUT32!__imp_VariantClear` at `0x18005a616`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a3c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a3c2`

## string_xrefs

- `0x18005a52c`: `pdcustomtaskname`
- `0x18005a4d9`: `configmanager2_nodecache`
- `0x18005a3db`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\cfgmgr2utils.cpp`
- `0x18005a498`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\cfgmgr2utils.cpp`
- `0x18005a549`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\cfgmgr2utils.cpp`
- `0x18005a5cb`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\cfgmgr2utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateConfigManagerFromSession(struct IConfigSession2 *a1, struct IConfigManager2 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int *i; // rbx
  __int64 v7; // r14
  int v8; // eax
  int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  struct IConfigManager2 *v13; // rax
  int ppv; // [rsp+20h] [rbp-49h]
  VARIANTARG v16; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-21h] BYREF
  VARIANTARG v18; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG v19; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LPVOID v21; // [rsp+E0h] [rbp+77h] BYREF

  v21 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
  v4 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v21);
  v5 = v4;
  if ( v4 >= 0 )
  {
    for ( i = (int *)&g_omaDmSessionVariableNames; i != &dword_180155958; i += 2 )
    {
      v7 = *(_QWORD *)i;
      VariantInit(&pvarg);
      v8 = (*(__int64 (__fastcall **)(struct IConfigSession2 *, __int64, VARIANTARG *))(*(_QWORD *)a1 + 32LL))(
             a1,
             v7,
             &pvarg);
      v9 = v8;
      if ( v8 != -2147023728 )
      {
        if ( v8 < 0 )
        {
          v10 = 630;
          goto LABEL_11;
        }
        v19 = pvarg;
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)v21 + 104LL))(v21, v7, &v19);
        if ( v9 < 0 )
        {
          v10 = 631;
LABEL_11:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\cfgmgr2utils.cpp",
            (const char *)(unsigned int)v9,
            ppv);
          VariantClear(&pvarg);
          v5 = v9;
          goto LABEL_20;
        }
      }
      VariantClear(&pvarg);
    }
    VariantInit(&v16);
    v16.vt = 8;
    v16.llVal = (LONGLONG)SysAllocString(L"configmanager2_nodecache");
    if ( v16.llVal )
    {
      v19 = v16;
      v11 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v21 + 104LL))(
              v21,
              L"pdcustomtaskname",
              &v19);
      v5 = v11;
      if ( v11 >= 0 )
      {
        VariantInit(&v18);
        v18.lVal = 0;
        v18.vt = 19;
        v19 = v18;
        v12 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v21 + 104LL))(
                v21,
                L"OMADM::TelemetryLevel",
                &v19);
        v5 = v12;
        if ( v12 >= 0 )
        {
          v13 = (struct IConfigManager2 *)v21;
          v21 = 0;
          *a2 = v13;
          VariantClear(&v18);
          VariantClear(&v16);
          v5 = 0;
          goto LABEL_20;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\cfgmgr2utils.cpp",
          (const char *)(unsigned int)v12,
          ppv);
        VariantClear(&v18);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x283,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\cfgmgr2utils.cpp",
          (const char *)(unsigned int)v11,
          ppv);
      }
      VariantClear(&v16);
    }
    else
    {
      VariantClear(&v16);
      v5 = -2147024882;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x269,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\cfgmgr2utils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  }
LABEL_20:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
  return v5;
}

```

## disassembly

```asm
0x18005a370  mov     [rsp-8+arg_0], rbx
0x18005a375  mov     [rsp-8+arg_8], rsi
0x18005a37a  push    rbp
0x18005a37b  push    rdi
0x18005a37c  push    r13
0x18005a37e  push    r14
0x18005a380  push    r15
0x18005a382  lea     rbp, [rsp-37h]
0x18005a387  sub     rsp, 0A0h
0x18005a38e  mov     r15, rdx
0x18005a391  mov     rsi, rcx
0x18005a394  mov     [rbp+57h+arg_10], 0
0x18005a39c  lea     rcx, [rbp+57h+arg_10]
0x18005a3a0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005a3a5  lea     rax, [rbp+57h+arg_10]
0x18005a3a9  mov     qword ptr [rsp+0C0h+ppv], rax; int
0x18005a3ae  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18005a3b5  xor     edx, edx; pUnkOuter
0x18005a3b7  lea     r8d, [rdx+1]; dwClsContext
0x18005a3bb  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18005a3c2  call    cs:__imp_CoCreateInstance
0x18005a3c9  nop     dword ptr [rax+rax+00h]
0x18005a3ce  mov     ebx, eax
0x18005a3d0  test    eax, eax
0x18005a3d2  jns     short loc_18005A3F1
0x18005a3d4  mov     rcx, [rbp+5Fh]; this
0x18005a3d8  mov     r9d, eax; char *
0x18005a3db  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005a3e2  mov     edx, 269h; void *
0x18005a3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a3ec  jmp     loc_18005A624
0x18005a3f1  lea     rbx, ?g_omaDmSessionVariableNames@@3PAPEBGA; ushort const * near * g_omaDmSessionVariableNames
0x18005a3f8  mov     r13d, 8
0x18005a3fe  lea     rax, dword_180155958
0x18005a405  cmp     rbx, rax
0x18005a408  jz      loc_18005A4C3
0x18005a40e  mov     r14, [rbx]
0x18005a411  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005a415  call    cs:__imp_VariantInit
0x18005a41c  nop     dword ptr [rax+rax+00h]
0x18005a421  nop
0x18005a422  mov     rax, [rsi]
0x18005a425  lea     r8, [rbp+57h+pvarg]
0x18005a429  mov     rdx, r14
0x18005a42c  mov     rcx, rsi
0x18005a42f  mov     rax, [rax+20h]
0x18005a433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a438  mov     edi, eax
0x18005a43a  cmp     eax, 80070490h
0x18005a43f  jz      short loc_18005A474
0x18005a441  test    eax, eax
0x18005a443  js      short loc_18005A493
0x18005a445  mov     rcx, [rbp+57h+arg_10]
0x18005a449  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18005a44d  movaps  [rbp+57h+var_40], xmm0
0x18005a451  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18005a456  movsd   [rbp+57h+var_30], xmm1
0x18005a45b  mov     rax, [rcx]
0x18005a45e  lea     r8, [rbp+57h+var_40]
0x18005a462  mov     rdx, r14
0x18005a465  mov     rax, [rax+68h]
0x18005a469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a46e  mov     edi, eax
0x18005a470  test    eax, eax
0x18005a472  js      short loc_18005A48C
0x18005a474  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005a478  call    cs:__imp_VariantClear
0x18005a47f  nop     dword ptr [rax+rax+00h]
0x18005a484  add     rbx, r13
0x18005a487  jmp     loc_18005A3FE
0x18005a48c  mov     edx, 277h
0x18005a491  jmp     short loc_18005A498
0x18005a493  mov     edx, 276h; void *
0x18005a498  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005a49f  mov     r9d, edi; char *
0x18005a4a2  mov     rcx, [rbp+5Fh]; this
0x18005a4a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a4ab  nop
0x18005a4ac  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005a4b0  call    cs:__imp_VariantClear
0x18005a4b7  nop     dword ptr [rax+rax+00h]
0x18005a4bc  mov     ebx, edi
0x18005a4be  jmp     loc_18005A624
0x18005a4c3  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005a4c7  call    cs:__imp_VariantInit
0x18005a4ce  nop     dword ptr [rax+rax+00h]
0x18005a4d3  nop
0x18005a4d4  mov     word ptr [rbp+57h+var_90], r13w
0x18005a4d9  lea     rcx, aConfigmanager2; "configmanager2_nodecache"
0x18005a4e0  call    cs:__imp_SysAllocString
0x18005a4e7  nop     dword ptr [rax+rax+00h]
0x18005a4ec  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005a4f0  test    rax, rax
0x18005a4f3  jnz     short loc_18005A50F
0x18005a4f5  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005a4f9  call    cs:__imp_VariantClear
0x18005a500  nop     dword ptr [rax+rax+00h]
0x18005a505  mov     ebx, 8007000Eh
0x18005a50a  jmp     loc_18005A624
0x18005a50f  mov     rcx, [rbp+57h+arg_10]
0x18005a513  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x18005a517  movaps  [rbp+57h+var_40], xmm0
0x18005a51b  movsd   xmm1, qword ptr [rbp+57h+var_90+10h]
0x18005a520  movsd   [rbp+57h+var_30], xmm1
0x18005a525  mov     rax, [rcx]
0x18005a528  lea     r8, [rbp+57h+var_40]
0x18005a52c  lea     rdx, aPdcustomtaskna; "pdcustomtaskname"
0x18005a533  mov     rax, [rax+68h]
0x18005a537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a53c  mov     ebx, eax
0x18005a53e  test    eax, eax
0x18005a540  jns     short loc_18005A570
0x18005a542  mov     rcx, [rbp+5Fh]; this
0x18005a546  mov     r9d, eax; char *
0x18005a549  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005a550  mov     edx, 283h; void *
0x18005a555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a55a  nop
0x18005a55b  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005a55f  call    cs:__imp_VariantClear
0x18005a566  nop     dword ptr [rax+rax+00h]
0x18005a56b  jmp     loc_18005A624
0x18005a570  lea     rcx, [rbp+57h+var_60]; pvarg
0x18005a574  call    cs:__imp_VariantInit
0x18005a57b  nop     dword ptr [rax+rax+00h]
0x18005a580  nop
0x18005a581  mov     dword ptr [rbp+57h+var_60+8], 0
0x18005a588  mov     eax, 13h
0x18005a58d  mov     word ptr [rbp+57h+var_60], ax
0x18005a591  mov     rcx, [rbp+57h+arg_10]
0x18005a595  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x18005a599  movaps  [rbp+57h+var_40], xmm0
0x18005a59d  movsd   xmm1, qword ptr [rbp+57h+var_60+10h]
0x18005a5a2  movsd   [rbp+57h+var_30], xmm1
0x18005a5a7  mov     rax, [rcx]
0x18005a5aa  lea     r8, [rbp+57h+var_40]
0x18005a5ae  lea     rdx, aOmadmTelemetry; "OMADM::TelemetryLevel"
0x18005a5b5  mov     rax, [rax+68h]
0x18005a5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5be  mov     ebx, eax
0x18005a5c0  test    eax, eax
0x18005a5c2  jns     short loc_18005A5F2
0x18005a5c4  mov     rcx, [rbp+5Fh]; this
0x18005a5c8  mov     r9d, eax; char *
0x18005a5cb  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005a5d2  mov     edx, 28Bh; void *
0x18005a5d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a5dc  nop
0x18005a5dd  lea     rcx, [rbp+57h+var_60]; pvarg
0x18005a5e1  call    cs:__imp_VariantClear
0x18005a5e8  nop     dword ptr [rax+rax+00h]
0x18005a5ed  jmp     loc_18005A55B
0x18005a5f2  mov     rax, [rbp+57h+arg_10]
0x18005a5f6  mov     [rbp+57h+arg_10], 0
0x18005a5fe  mov     [r15], rax
0x18005a601  lea     rcx, [rbp+57h+var_60]; pvarg
0x18005a605  call    cs:__imp_VariantClear
0x18005a60c  nop     dword ptr [rax+rax+00h]
0x18005a611  nop
0x18005a612  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005a616  call    cs:__imp_VariantClear
0x18005a61d  nop     dword ptr [rax+rax+00h]
0x18005a622  xor     ebx, ebx
0x18005a624  lea     rcx, [rbp+57h+arg_10]
0x18005a628  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005a62d  mov     eax, ebx
0x18005a62f  lea     r11, [rsp+0C0h+var_20]
0x18005a637  mov     rbx, [r11+30h]
0x18005a63b  mov     rsi, [r11+38h]
0x18005a63f  mov     rsp, r11
0x18005a642  pop     r15
0x18005a644  pop     r14
0x18005a646  pop     r13
0x18005a648  pop     rdi
0x18005a649  pop     rbp
0x18005a64a  retn
```
