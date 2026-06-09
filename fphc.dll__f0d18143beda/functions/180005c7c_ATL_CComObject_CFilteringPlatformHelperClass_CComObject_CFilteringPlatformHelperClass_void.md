# ATL::CComObject<CFilteringPlatformHelperClass>::CComObject<CFilteringPlatformHelperClass>(void *)

- ea: `0x180005c7c`
- end: `0x180005e2d`
- name: `??0?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@QEAA@PEAX@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006368`

## callees

- `0x180005c7c`
- `0x1800060c0`
- `0x18000a118`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005de1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005de1`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d91`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005d84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005d84`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFilteringPlatformHelperClass>::CComObject<CFilteringPlatformHelperClass>(
        __int64 a1)
{
  LPVOID *ppv; // rdx
  _BYTE *v3; // rax
  __int64 v4; // rcx
  const struct ATL::ATLSTRINGRESOURCEIMAGE *v5; // rdi
  ATL::CAtlBaseModule *v6; // rcx
  HINSTANCE HInstanceAt; // rax
  int v8; // esi
  const struct ATL::ATLSTRINGRESOURCEIMAGE *StringResourceImage; // rax
  int v10; // edx
  ATL::CAtlBaseModule *v11; // rcx
  struct ATL::CAtlModule *v12; // rcx

  ppv = (LPVOID *)(a1 + 544);
  *(_DWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_BYTE *)(a1 + 112) = 0;
  *(_QWORD *)a1 = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'};
  *(_QWORD *)(a1 + 8) = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'};
  *(_QWORD *)(a1 + 56) = &CNetDiagHelperExImpl::`vftable';
  v3 = (_BYTE *)(a1 + 524);
  *(_QWORD *)(a1 + 20) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_BYTE *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 408) = 0;
  *(_QWORD *)(a1 + 416) = 0;
  *(_QWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_WORD *)(a1 + 464) = 0;
  *(_BYTE *)(a1 + 466) = 0;
  *(_BYTE *)(a1 + 520) = 0;
  *(_QWORD *)(a1 + 552) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  v4 = 16;
  *ppv = 0;
  do
  {
    *v3++ = 0;
    --v4;
  }
  while ( v4 );
  *(_OWORD *)(a1 + 472) = 0;
  *(_OWORD *)(a1 + 488) = 0;
  *(_OWORD *)(a1 + 504) = 0;
  CoCreateInstance(&CLSID_NDFEtw, 0, 0x17u, &GUID_c0b35739_ebf5_11d8_bbe9_505054503030, ppv);
  SysFreeString(*(BSTR *)(a1 + 552));
  *(_QWORD *)(a1 + 552) = 0;
  v5 = 0;
  HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v6, 0);
  v8 = 1;
  if ( HInstanceAt )
  {
    while ( !v5 )
    {
      StringResourceImage = ATL::AtlGetStringResourceImage(HInstanceAt, 0x1388u);
      v10 = v8;
      v5 = StringResourceImage;
      ++v8;
      HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v11, v10);
      if ( !HInstanceAt )
      {
        if ( !v5 )
          goto LABEL_8;
        break;
      }
    }
    *(_QWORD *)(a1 + 552) = SysAllocStringLen((const OLECHAR *)v5 + 1, *(unsigned __int16 *)v5);
  }
LABEL_8:
  v12 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelper'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  *(_QWORD *)(a1 + 56) = &ATL::CComObject<CFilteringPlatformHelperClass>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v12 + 8LL))(v12);
  return a1;
}

```

## disassembly

```asm
0x180005c7c  push    rbx
0x180005c7e  push    rbp
0x180005c7f  push    rsi
0x180005c80  push    rdi
0x180005c81  sub     rsp, 38h
0x180005c85  xor     ebp, ebp
0x180005c87  lea     rdx, [rcx+220h]
0x180005c8e  mov     [rcx+40h], ebp
0x180005c91  xor     eax, eax
0x180005c93  xorps   xmm0, xmm0
0x180005c96  mov     rbx, rcx
0x180005c99  movups  xmmword ptr [rcx+48h], xmm0
0x180005c9d  movups  xmmword ptr [rcx+58h], xmm0
0x180005ca1  mov     [rcx+68h], rax
0x180005ca5  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x180005cac  mov     [rcx+70h], bpl
0x180005cb0  mov     [rcx], rax
0x180005cb3  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x180005cba  mov     [rcx+8], rax
0x180005cbe  lea     rax, ??_7CNetDiagHelperExImpl@@6B@; const CNetDiagHelperExImpl::`vftable'
0x180005cc5  mov     [rcx+38h], rax
0x180005cc9  lea     rax, [rbx+20Ch]
0x180005cd0  mov     [rcx+14h], rbp
0x180005cd4  mov     [rcx+20h], rbp
0x180005cd8  mov     [rcx+10h], ebp
0x180005cdb  mov     [rcx+78h], rbp
0x180005cdf  mov     [rcx+80h], bpl
0x180005ce6  mov     [rcx+88h], rbp
0x180005ced  mov     [rcx+90h], rbp
0x180005cf4  mov     [rcx+198h], rbp
0x180005cfb  mov     [rcx+1A0h], rbp
0x180005d02  mov     [rcx+1A8h], rbp
0x180005d09  mov     [rcx+1B0h], rbp
0x180005d10  mov     [rcx+1B8h], rbp
0x180005d17  mov     [rcx+1D0h], bp
0x180005d1e  mov     [rcx+1D2h], bpl
0x180005d25  mov     [rcx+208h], bpl
0x180005d2c  mov     [rcx+228h], rbp
0x180005d33  mov     [rcx+1C0h], rbp
0x180005d3a  mov     [rcx+1C8h], rbp
0x180005d41  lea     ecx, [rbp+10h]
0x180005d44  mov     [rdx], rbp
0x180005d47  mov     [rax], bpl
0x180005d4a  inc     rax
0x180005d4d  sub     rcx, 1
0x180005d51  jnz     short loc_180005D47
0x180005d53  xorps   xmm0, xmm0
0x180005d56  mov     [rsp+58h+ppv], rdx; ppv
0x180005d5b  movups  xmmword ptr [rbx+1D8h], xmm0
0x180005d62  lea     r8d, [rcx+17h]; dwClsContext
0x180005d66  xor     edx, edx; pUnkOuter
0x180005d68  movups  xmmword ptr [rbx+1E8h], xmm0
0x180005d6f  lea     r9, _GUID_c0b35739_ebf5_11d8_bbe9_505054503030; riid
0x180005d76  lea     rcx, CLSID_NDFEtw; rclsid
0x180005d7d  movups  xmmword ptr [rbx+1F8h], xmm0
0x180005d84  call    cs:__imp_CoCreateInstance
0x180005d8a  mov     rcx, [rbx+228h]; bstrString
0x180005d91  call    cs:__imp_SysFreeString
0x180005d97  xor     edx, edx; int
0x180005d99  mov     [rbx+228h], rbp
0x180005da0  mov     rdi, rbp
0x180005da3  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180005da8  mov     esi, 1
0x180005dad  test    rax, rax
0x180005db0  jz      short loc_180005DEE
0x180005db2  test    rdi, rdi
0x180005db5  jnz     short loc_180005DDA
0x180005db7  mov     edx, 1388h; unsigned int
0x180005dbc  mov     rcx, rax; hModule
0x180005dbf  call    ?AtlGetStringResourceImage@ATL@@YAPEBUATLSTRINGRESOURCEIMAGE@1@PEAUHINSTANCE__@@I@Z; ATL::AtlGetStringResourceImage(HINSTANCE__ *,uint)
0x180005dc4  mov     edx, esi; int
0x180005dc6  mov     rdi, rax
0x180005dc9  inc     esi
0x180005dcb  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x180005dd0  test    rax, rax
0x180005dd3  jnz     short loc_180005DB2
0x180005dd5  test    rdi, rdi
0x180005dd8  jz      short loc_180005DEE
0x180005dda  movzx   edx, word ptr [rdi]; ui
0x180005ddd  lea     rcx, [rdi+2]; strIn
0x180005de1  call    cs:__imp_SysAllocStringLen
0x180005de7  mov     [rbx+228h], rax
0x180005dee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005df5  lea     rax, ??_7?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelper'}
0x180005dfc  mov     [rbx], rax
0x180005dff  lea     rax, ??_7?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180005e06  mov     [rbx+8], rax
0x180005e0a  lea     rax, ??_7?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@6B@; const ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'
0x180005e11  mov     [rbx+38h], rax
0x180005e15  mov     rax, [rcx]
0x180005e18  mov     rax, [rax+8]
0x180005e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e21  mov     rax, rbx
0x180005e24  add     rsp, 38h
0x180005e28  pop     rdi
0x180005e29  pop     rsi
0x180005e2a  pop     rbp
0x180005e2b  pop     rbx
0x180005e2c  retn
```
