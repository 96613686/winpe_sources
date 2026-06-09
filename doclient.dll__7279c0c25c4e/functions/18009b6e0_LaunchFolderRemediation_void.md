# LaunchFolderRemediation(void)

- ea: `0x18009b6e0`
- end: `0x18009b87a`
- name: `?LaunchFolderRemediation@@YAJXZ`
- size: `410`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009b880`

## callees

- `0x18000933c`
- `0x18009b6e0`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b723`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b723`
- `OLEAUT32!__imp_SysAllocString` at `0x18009b754`
- `OLEAUT32!__imp_SysAllocString` at `0x18009b791`
- `OLEAUT32!__imp_SysAllocString` at `0x18009b754`
- `OLEAUT32!__imp_SysAllocString` at `0x18009b791`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b823`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b832`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b823`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b832`
- `OLEAUT32!__imp_VariantInit` at `0x18009b7c9`
- `OLEAUT32!__imp_VariantInit` at `0x18009b7c9`
- `OLEAUT32!__imp_VariantClear` at `0x18009b814`
- `OLEAUT32!__imp_VariantClear` at `0x18009b814`

## string_xrefs

- `0x18009b74d`: `DynamicProtectionPlugin`

## pseudocode

```c
__int64 LaunchFolderRemediation(void)
{
  HRESULT v0; // eax
  unsigned int v1; // esi
  OLECHAR *v2; // rbx
  OLECHAR *v3; // rdi
  int v4; // eax
  LPVOID v5; // rcx
  int v7; // [rsp+20h] [rbp-58h]
  LPVOID v8; // [rsp+40h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8 = 0;
  v0 = CoCreateInstance(
         &GUID_72566e27_1abb_4eb3_b4f0_eb431cb1cb32,
         0,
         4u,
         &GUID_b4c1d279_966e_44e9_a9c5_ccaf4a77023d,
         &v8);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v2 = SysAllocString(L"DynamicProtectionPlugin");
    if ( v2 )
    {
      v3 = SysAllocString(L"dosvc");
      if ( v3 )
      {
        VariantInit(&pvarg);
        v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, OLECHAR *, VARIANTARG *))(*(_QWORD *)v8 + 64LL))(
               v8,
               v2,
               v3,
               &pvarg);
        v1 = v4;
        if ( v4 >= 0 )
          v1 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDA,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
            (const char *)(unsigned int)v4,
            v7);
        VariantClear(&pvarg);
      }
      else
      {
        v1 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
          (const char *)0x8007000ELL,
          v7);
      }
      if ( v3 )
        SysFreeString(v3);
    }
    else
    {
      v1 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
        (const char *)0x8007000ELL,
        v7);
    }
    if ( v2 )
      SysFreeString(v2);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
      (const char *)(unsigned int)v0,
      v7);
  }
  v5 = v8;
  if ( v8 )
  {
    v8 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return v1;
}

```

## disassembly

```asm
0x18009b6e0  mov     r11, rsp
0x18009b6e3  mov     [r11+8], rbx
0x18009b6e7  mov     [r11+10h], rsi
0x18009b6eb  push    rdi
0x18009b6ec  sub     rsp, 70h
0x18009b6f0  mov     rax, cs:__security_cookie
0x18009b6f7  xor     rax, rsp
0x18009b6fa  mov     [rsp+78h+var_18], rax
0x18009b6ff  mov     qword ptr [r11-38h], 0
0x18009b707  lea     rax, [r11-38h]
0x18009b70b  mov     [r11-58h], rax
0x18009b70f  lea     r9, _GUID_b4c1d279_966e_44e9_a9c5_ccaf4a77023d; riid
0x18009b716  xor     edx, edx; pUnkOuter
0x18009b718  lea     r8d, [rdx+4]; dwClsContext
0x18009b71c  lea     rcx, _GUID_72566e27_1abb_4eb3_b4f0_eb431cb1cb32; rclsid
0x18009b723  call    cs:__imp_CoCreateInstance
0x18009b729  mov     esi, eax
0x18009b72b  test    eax, eax
0x18009b72d  jns     short loc_18009B74D
0x18009b72f  mov     rcx, [rsp+78h]; this
0x18009b734  mov     r9d, eax; char *
0x18009b737  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009b73e  mov     edx, 0D2h; void *
0x18009b743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b748  jmp     loc_18009B839
0x18009b74d  lea     rcx, psz; "DynamicProtectionPlugin"
0x18009b754  call    cs:__imp_SysAllocString
0x18009b75a  mov     rbx, rax
0x18009b75d  mov     [rsp+78h+var_48], rax
0x18009b762  test    rax, rax
0x18009b765  jnz     short loc_18009B78A
0x18009b767  mov     rcx, [rsp+78h]; this
0x18009b76c  mov     esi, 8007000Eh
0x18009b771  mov     r9d, esi; char *
0x18009b774  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009b77b  mov     edx, 0D6h; void *
0x18009b780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b785  jmp     loc_18009B82A
0x18009b78a  lea     rcx, aDosvc_0; "dosvc"
0x18009b791  call    cs:__imp_SysAllocString
0x18009b797  mov     rdi, rax
0x18009b79a  mov     [rsp+78h+var_40], rax
0x18009b79f  test    rax, rax
0x18009b7a2  jnz     short loc_18009B7C4
0x18009b7a4  mov     rcx, [rsp+78h]; this
0x18009b7a9  mov     esi, 8007000Eh
0x18009b7ae  mov     r9d, esi; char *
0x18009b7b1  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009b7b8  mov     edx, 0D8h; void *
0x18009b7bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b7c2  jmp     short loc_18009B81B
0x18009b7c4  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18009b7c9  call    cs:__imp_VariantInit
0x18009b7cf  nop
0x18009b7d0  mov     rcx, [rsp+78h+var_38]
0x18009b7d5  mov     rax, [rcx]
0x18009b7d8  lea     r9, [rsp+78h+pvarg]
0x18009b7dd  mov     r8, rdi
0x18009b7e0  mov     rdx, rbx
0x18009b7e3  mov     rax, [rax+40h]
0x18009b7e7  call    _guard_dispatch_icall
0x18009b7ec  mov     esi, eax
0x18009b7ee  test    eax, eax
0x18009b7f0  jns     short loc_18009B80D
0x18009b7f2  mov     rcx, [rsp+78h]; this
0x18009b7f7  mov     r9d, eax; char *
0x18009b7fa  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009b801  mov     edx, 0DAh; void *
0x18009b806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b80b  jmp     short loc_18009B80F
0x18009b80d  xor     esi, esi
0x18009b80f  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18009b814  call    cs:__imp_VariantClear
0x18009b81a  nop
0x18009b81b  test    rdi, rdi
0x18009b81e  jz      short loc_18009B82A
0x18009b820  mov     rcx, rdi; bstrString
0x18009b823  call    cs:__imp_SysFreeString
0x18009b829  nop
0x18009b82a  test    rbx, rbx
0x18009b82d  jz      short loc_18009B839
0x18009b82f  mov     rcx, rbx; bstrString
0x18009b832  call    cs:__imp_SysFreeString
0x18009b838  nop
0x18009b839  mov     rcx, [rsp+78h+var_38]
0x18009b83e  test    rcx, rcx
0x18009b841  jz      short loc_18009B859
0x18009b843  mov     [rsp+78h+var_38], 0
0x18009b84c  mov     rdx, [rcx]
0x18009b84f  mov     rax, [rdx+10h]
0x18009b853  call    _guard_dispatch_icall
0x18009b858  nop
0x18009b859  mov     eax, esi
0x18009b85b  mov     rcx, [rsp+78h+var_18]
0x18009b860  xor     rcx, rsp; StackCookie
0x18009b863  call    __security_check_cookie
0x18009b868  lea     r11, [rsp+78h+var_8]
0x18009b86d  mov     rbx, [r11+10h]
0x18009b871  mov     rsi, [r11+18h]
0x18009b875  mov     rsp, r11
0x18009b878  pop     rdi
0x18009b879  retn
```
