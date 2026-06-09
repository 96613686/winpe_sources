# AdapGetNamingContext(ushort const *,ushort * *)

- ea: `0x1800e9e84`
- end: `0x1800ea0b3`
- name: `?AdapGetNamingContext@@YAJPEBGPEAPEAG@Z`
- size: `559`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e88d4`

## callees

- `0x1800090c0`
- `0x1800e8894`
- `0x1800e9e84`
- `0x180129010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800e9f67`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ea043`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e9f67`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ea043`
- `OLEAUT32!__imp_VariantInit` at `0x1800e9eb5`
- `OLEAUT32!__imp_VariantInit` at `0x1800e9eb5`
- `OLEAUT32!__imp_VariantClear` at `0x1800ea081`
- `OLEAUT32!__imp_VariantClear` at `0x1800ea081`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800ea00b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800ea00b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800ea01c`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800ea01c`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800e9ee8`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800e9ee8`

## pseudocode

```c
__int64 __fastcall AdapGetNamingContext(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v3; // eax
  int v4; // ebx
  __int64 (__fastcall *v5)(void *, _QWORD, VARIANTARG *); // rbx
  ATL::CComBSTR *v6; // rax
  PVOID *v7; // rcx
  __int64 v8; // rdx
  BSTR *v9; // rax
  LPCSTR *v10; // rbx
  UINT v11; // eax
  unsigned __int16 *v12; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  void *ppObject; // [rsp+70h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF

  ppObject = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v3 = ADsOpenObject(L"LDAP://RootDSE", 0, 0, 0xC5u, &IID_IADs, &ppObject);
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v3);
    if ( v4 < 0 )
      goto LABEL_30;
  }
  v5 = *(__int64 (__fastcall **)(void *, _QWORD, VARIANTARG *))(*(_QWORD *)ppObject + 120LL);
  v6 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"schemaNamingContext");
  v4 = v5(ppObject, *(_QWORD *)v6, &pvarg);
  SysFreeString(bstrString);
  if ( v4 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
        (unsigned int)v4);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 < 0 )
      goto LABEL_30;
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( pvarg.vt != 8 )
  {
    v4 = -2144272373;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
    {
      v8 = 68;
LABEL_29:
      WPP_SF_d(v7[2], v8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, (unsigned int)v4);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  v9 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, pvarg.bstrVal);
  v10 = (LPCSTR *)v9;
  if ( a2 )
  {
    if ( *v9 )
    {
      v11 = SysStringByteLen(*v9);
      v12 = SysAllocStringByteLen(*v10, v11);
      *a2 = v12;
      if ( v12 )
        goto LABEL_24;
    }
    else
    {
      *a2 = 0;
    }
    if ( *v10 )
    {
      v4 = -2147024882;
      goto LABEL_25;
    }
LABEL_24:
    v4 = 0;
    goto LABEL_25;
  }
  v4 = -2147467261;
LABEL_25:
  SysFreeString(bstrString);
  if ( v4 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v8 = 69;
      goto LABEL_29;
    }
  }
LABEL_30:
  VariantClear(&pvarg);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800e9e84  mov     [rsp-18h+arg_8], rbx
0x1800e9e89  mov     [rsp-18h+arg_0], rcx
0x1800e9e8e  push    rbp
0x1800e9e8f  push    rdi
0x1800e9e90  push    r15
0x1800e9e92  mov     rbp, rsp
0x1800e9e95  sub     rsp, 50h
0x1800e9e99  xorps   xmm0, xmm0
0x1800e9e9c  mov     [rbp+arg_0], 0
0x1800e9ea4  xor     eax, eax
0x1800e9ea6  lea     rcx, [rbp+pvarg]; pvarg
0x1800e9eaa  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800e9eae  mov     qword ptr [rbp+pvarg+10h], rax
0x1800e9eb2  mov     rdi, rdx
0x1800e9eb5  call    cs:__imp_VariantInit
0x1800e9ebc  nop     dword ptr [rax+rax+00h]
0x1800e9ec1  lea     rax, [rbp+arg_0]
0x1800e9ec5  mov     r9d, 0C5h; dwReserved
0x1800e9ecb  mov     [rsp+50h+ppObject], rax; ppObject
0x1800e9ed0  lea     rcx, szPathName; "LDAP://RootDSE"
0x1800e9ed7  lea     rax, IID_IADs
0x1800e9ede  xor     r8d, r8d; lpszPassword
0x1800e9ee1  xor     edx, edx; lpszUserName
0x1800e9ee3  mov     [rsp+50h+riid], rax; riid
0x1800e9ee8  call    cs:__imp_ADsOpenObject
0x1800e9eef  nop     dword ptr [rax+rax+00h]
0x1800e9ef4  lea     r15, WPP_GLOBAL_Control
0x1800e9efb  mov     ebx, eax
0x1800e9efd  test    eax, eax
0x1800e9eff  jz      short loc_1800E9F33
0x1800e9f01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9f08  cmp     rcx, r15
0x1800e9f0b  jz      short loc_1800E9F2B
0x1800e9f0d  test    byte ptr [rcx+1Ch], 40h
0x1800e9f11  jz      short loc_1800E9F2B
0x1800e9f13  mov     rcx, [rcx+10h]
0x1800e9f17  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9f1e  mov     edx, 42h ; 'B'
0x1800e9f23  mov     r9d, eax
0x1800e9f26  call    WPP_SF_d
0x1800e9f2b  test    ebx, ebx
0x1800e9f2d  js      loc_1800EA07D
0x1800e9f33  mov     rax, [rbp+arg_0]
0x1800e9f37  lea     rdx, aSchemanamingco; "schemaNamingContext"
0x1800e9f3e  mov     rcx, [rax]
0x1800e9f41  mov     rbx, [rcx+78h]
0x1800e9f45  lea     rcx, [rbp+bstrString]; this
0x1800e9f49  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800e9f4e  mov     rcx, [rbp+arg_0]
0x1800e9f52  lea     r8, [rbp+pvarg]
0x1800e9f56  mov     rdx, [rax]
0x1800e9f59  mov     rax, rbx
0x1800e9f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9f61  mov     rcx, [rbp+bstrString]; bstrString
0x1800e9f65  mov     ebx, eax
0x1800e9f67  call    cs:__imp_SysFreeString
0x1800e9f6e  nop     dword ptr [rax+rax+00h]
0x1800e9f73  test    ebx, ebx
0x1800e9f75  jz      short loc_1800E9FB2
0x1800e9f77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9f7e  cmp     rcx, r15
0x1800e9f81  jz      short loc_1800E9FA8
0x1800e9f83  test    byte ptr [rcx+1Ch], 40h
0x1800e9f87  jz      short loc_1800E9FA8
0x1800e9f89  mov     rcx, [rcx+10h]
0x1800e9f8d  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9f94  mov     edx, 43h ; 'C'
0x1800e9f99  mov     r9d, ebx
0x1800e9f9c  call    WPP_SF_d
0x1800e9fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9fa8  test    ebx, ebx
0x1800e9faa  js      loc_1800EA07D
0x1800e9fb0  jmp     short loc_1800E9FB9
0x1800e9fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9fb9  cmp     word ptr [rbp+pvarg], 8
0x1800e9fbe  jz      short loc_1800E9FE2
0x1800e9fc0  mov     ebx, 8031000Bh
0x1800e9fc5  cmp     rcx, r15
0x1800e9fc8  jz      loc_1800EA07D
0x1800e9fce  test    byte ptr [rcx+1Ch], 40h
0x1800e9fd2  jz      loc_1800EA07D
0x1800e9fd8  mov     edx, 44h ; 'D'
0x1800e9fdd  jmp     loc_1800EA06A
0x1800e9fe2  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x1800e9fe6  lea     rcx, [rbp+bstrString]; this
0x1800e9fea  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800e9fef  mov     rbx, rax
0x1800e9ff2  test    rdi, rdi
0x1800e9ff5  jnz     short loc_1800E9FFE
0x1800e9ff7  mov     ebx, 80004003h
0x1800e9ffc  jmp     short loc_1800EA03F
0x1800e9ffe  mov     rcx, [rax]; bstr
0x1800ea001  test    rcx, rcx
0x1800ea004  jnz     short loc_1800EA00B
0x1800ea006  mov     [rdi], rcx
0x1800ea009  jmp     short loc_1800EA030
0x1800ea00b  call    cs:__imp_SysStringByteLen
0x1800ea012  nop     dword ptr [rax+rax+00h]
0x1800ea017  mov     rcx, [rbx]; psz
0x1800ea01a  mov     edx, eax; len
0x1800ea01c  call    cs:__imp_SysAllocStringByteLen
0x1800ea023  nop     dword ptr [rax+rax+00h]
0x1800ea028  mov     [rdi], rax
0x1800ea02b  test    rax, rax
0x1800ea02e  jnz     short loc_1800EA03D
0x1800ea030  cmp     qword ptr [rbx], 0
0x1800ea034  jz      short loc_1800EA03D
0x1800ea036  mov     ebx, 8007000Eh
0x1800ea03b  jmp     short loc_1800EA03F
0x1800ea03d  xor     ebx, ebx
0x1800ea03f  mov     rcx, [rbp+bstrString]; bstrString
0x1800ea043  call    cs:__imp_SysFreeString
0x1800ea04a  nop     dword ptr [rax+rax+00h]
0x1800ea04f  test    ebx, ebx
0x1800ea051  jz      short loc_1800EA07D
0x1800ea053  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea05a  cmp     rcx, r15
0x1800ea05d  jz      short loc_1800EA07D
0x1800ea05f  test    byte ptr [rcx+1Ch], 40h
0x1800ea063  jz      short loc_1800EA07D
0x1800ea065  mov     edx, 45h ; 'E'
0x1800ea06a  mov     rcx, [rcx+10h]
0x1800ea06e  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800ea075  mov     r9d, ebx
0x1800ea078  call    WPP_SF_d
0x1800ea07d  lea     rcx, [rbp+pvarg]; pvarg
0x1800ea081  call    cs:__imp_VariantClear
0x1800ea088  nop     dword ptr [rax+rax+00h]
0x1800ea08d  mov     rcx, [rbp+arg_0]
0x1800ea091  test    rcx, rcx
0x1800ea094  jz      short loc_1800EA0A2
0x1800ea096  mov     rax, [rcx]
0x1800ea099  mov     rax, [rax+10h]
0x1800ea09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea0a2  mov     eax, ebx
0x1800ea0a4  mov     rbx, [rsp+50h+arg_8]
0x1800ea0a9  add     rsp, 50h
0x1800ea0ad  pop     r15
0x1800ea0af  pop     rdi
0x1800ea0b0  pop     rbp
0x1800ea0b1  retn
```
