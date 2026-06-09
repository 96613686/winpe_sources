# DllGetClassObject

- ea: `0x1800183e0`
- end: `0x18001856c`
- name: `DllGetClassObject`
- size: `396`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002928`
- `0x18001435c`
- `0x1800183e0`
- `0x180024010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800184ec`
- `RPCRT4!NdrDllGetClassObject` at `0x1800184ec`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  _DWORD *v9; // rdi
  HRESULT v10; // ebx
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx
  _DWORD *v13; // rdi

  *ppv = 0;
  v5 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_EventLogSnapin.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_EventLogSnapin.Data1 )
    v5 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_EventLogSnapin.Data4;
  if ( v5 )
  {
    v7 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_SysToolsExt.Data1;
    if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_SysToolsExt.Data1 )
      v7 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_SysToolsExt.Data4;
    if ( v7 )
    {
      v8 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_SnapinAbout.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_SnapinAbout.Data1 )
        v8 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_SnapinAbout.Data4;
      if ( v8 )
      {
        pStubVtblList = aProxyFileList->pStubVtblList;
        if ( *pStubVtblList )
          pclsid = **(const CLSID ***)pStubVtblList;
        else
          pclsid = 0;
        return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
      }
      v9 = operator new(0x10u);
      if ( v9 )
      {
        *(_QWORD *)v9 = &CSnapinAboutCF::`vftable';
        if ( !CDll::s_cObjs )
          InitGlobals();
        _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
        v9[3] = 1;
        v10 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v9)(v9, riid, ppv);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
        return v10;
      }
      return -2147024882;
    }
  }
  v13 = operator new(0x10u);
  if ( !v13 )
    return -2147024882;
  *(_QWORD *)v13 = &CComponentDataCF::`vftable';
  if ( !CDll::s_cObjs )
    InitGlobals();
  _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
  v13[3] = 1;
  v10 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v13)(v13, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 16LL))(v13);
  return v10;
}

```

## disassembly

```asm
0x1800183e0  mov     [rsp+arg_0], rbx
0x1800183e5  mov     [rsp+arg_8], rsi
0x1800183ea  push    rdi
0x1800183eb  sub     rsp, 30h
0x1800183ef  mov     qword ptr [r8], 0
0x1800183f6  mov     rbx, r8
0x1800183f9  mov     rax, [rcx]
0x1800183fc  mov     rsi, rdx
0x1800183ff  sub     rax, qword ptr cs:?CLSID_EventLogSnapin@@3U_GUID@@B.Data1; _GUID const CLSID_EventLogSnapin ...
0x180018406  mov     r10, rcx
0x180018409  jnz     short loc_180018416
0x18001840b  mov     rax, [rcx+8]
0x18001840f  sub     rax, qword ptr cs:?CLSID_EventLogSnapin@@3U_GUID@@B.Data4; _GUID const CLSID_EventLogSnapin ...
0x180018416  test    rax, rax
0x180018419  jz      loc_1800184F6
0x18001841f  mov     rax, [rcx]
0x180018422  sub     rax, qword ptr cs:?CLSID_SysToolsExt@@3U_GUID@@B.Data1; _GUID const CLSID_SysToolsExt ...
0x180018429  jnz     short loc_180018436
0x18001842b  mov     rax, [rcx+8]
0x18001842f  sub     rax, qword ptr cs:?CLSID_SysToolsExt@@3U_GUID@@B.Data4; _GUID const CLSID_SysToolsExt ...
0x180018436  test    rax, rax
0x180018439  jz      loc_1800184F6
0x18001843f  mov     rax, [rcx]
0x180018442  sub     rax, qword ptr cs:?CLSID_SnapinAbout@@3U_GUID@@B.Data1; _GUID const CLSID_SnapinAbout ...
0x180018449  jnz     short loc_180018456
0x18001844b  mov     rax, [rcx+8]
0x18001844f  sub     rax, qword ptr cs:?CLSID_SnapinAbout@@3U_GUID@@B.Data4; _GUID const CLSID_SnapinAbout ...
0x180018456  test    rax, rax
0x180018459  jnz     short loc_1800184B7
0x18001845b  lea     ecx, [rax+10h]; Size
0x18001845e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018463  mov     rdi, rax
0x180018466  test    rax, rax
0x180018469  jz      loc_180018555
0x18001846f  lea     rax, ??_7CSnapinAboutCF@@6B@; const CSnapinAboutCF::`vftable'
0x180018476  mov     [rdi], rax
0x180018479  cmp     cs:?s_cObjs@CDll@@2KA, 0; ulong CDll::s_cObjs
0x180018480  jnz     short loc_180018487
0x180018482  call    ?InitGlobals@@YAXXZ; InitGlobals(void)
0x180018487  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x18001848e  mov     dword ptr [rdi+0Ch], 1
0x180018495  mov     r8, rbx
0x180018498  mov     rax, [rdi]
0x18001849b  mov     rdx, rsi
0x18001849e  mov     rcx, rdi
0x1800184a1  mov     rax, [rax]
0x1800184a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184a9  mov     rcx, [rdi]
0x1800184ac  mov     ebx, eax
0x1800184ae  mov     rax, [rcx+10h]
0x1800184b2  jmp     loc_18001854B
0x1800184b7  mov     rax, cs:aProxyFileList
0x1800184be  mov     rcx, [rax+8]
0x1800184c2  mov     rax, [rcx]
0x1800184c5  test    rax, rax
0x1800184c8  jz      short loc_1800184CF
0x1800184ca  mov     rcx, [rax]
0x1800184cd  jmp     short loc_1800184D1
0x1800184cf  xor     ecx, ecx
0x1800184d1  lea     rax, gPFactory
0x1800184d8  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800184dd  lea     r9, aProxyFileList; pProxyFileList
0x1800184e4  mov     [rsp+38h+pclsid], rcx; pclsid
0x1800184e9  mov     rcx, r10; rclsid
0x1800184ec  call    cs:__imp_NdrDllGetClassObject
0x1800184f2  mov     ebx, eax
0x1800184f4  jmp     short loc_18001855A
0x1800184f6  mov     ecx, 10h; Size
0x1800184fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018500  mov     rdi, rax
0x180018503  test    rax, rax
0x180018506  jz      short loc_180018555
0x180018508  lea     rax, ??_7CComponentDataCF@@6B@; const CComponentDataCF::`vftable'
0x18001850f  mov     [rdi], rax
0x180018512  cmp     cs:?s_cObjs@CDll@@2KA, 0; ulong CDll::s_cObjs
0x180018519  jnz     short loc_180018520
0x18001851b  call    ?InitGlobals@@YAXXZ; InitGlobals(void)
0x180018520  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x180018527  mov     dword ptr [rdi+0Ch], 1
0x18001852e  mov     r8, rbx
0x180018531  mov     rax, [rdi]
0x180018534  mov     rdx, rsi
0x180018537  mov     rcx, rdi
0x18001853a  mov     rax, [rax]
0x18001853d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018542  mov     ebx, eax
0x180018544  mov     rax, [rdi]
0x180018547  mov     rax, [rax+10h]
0x18001854b  mov     rcx, rdi
0x18001854e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018553  jmp     short loc_18001855A
0x180018555  mov     ebx, 8007000Eh
0x18001855a  mov     rsi, [rsp+38h+arg_8]
0x18001855f  mov     eax, ebx
0x180018561  mov     rbx, [rsp+38h+arg_0]
0x180018566  add     rsp, 30h
0x18001856a  pop     rdi
0x18001856b  retn
```
