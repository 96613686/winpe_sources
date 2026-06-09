# CSH::SH_DisplayClientHelp(HWND__ *,ushort const *,ushort const *,int,ushort const *)

- ea: `0x140028bf0`
- end: `0x140028db1`
- name: `?SH_DisplayClientHelp@CSH@@QEAAXPEAUHWND__@@PEBG1H1@Z`
- size: `449`
- prototype: `void(CSH *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017fe4`
- `0x14001d3e0`
- `0x140047e30`
- `0x1400533e0`

## callees

- `0x14000b7d8`
- `0x14000d078`
- `0x140011960`
- `0x140028bf0`
- `0x1400b4844`
- `0x140112010`

## import_xrefs

- `ole32!CoInitialize` at `0x140028c16`
- `ole32!CoInitialize` at `0x140028c16`
- `ole32!CoUninitialize` at `0x140028d88`
- `ole32!CoUninitialize` at `0x140028d88`
- `ole32!CoCreateInstance` at `0x140028ca9`
- `ole32!CoCreateInstance` at `0x140028ca9`
- `OLEAUT32!__imp_SysFreeString` at `0x140028d24`
- `OLEAUT32!__imp_SysFreeString` at `0x140028d24`

## string_xrefs

- `0x140028ce8`: `Failed to cocreate CLSID_HxHelpPane`

## pseudocode

```c
void __fastcall CSH::SH_DisplayClientHelp(
        OLECHAR *this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HRESULT v7; // ebx
  int v8; // r8d
  int v9; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  __int64 (__fastcall *v13)(LPVOID, _QWORD); // rbx
  _QWORD *v14; // rax
  HRESULT v15; // [rsp+28h] [rbp-20h]
  BSTR bstrString; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  bstrString = this;
  ppv = 0;
  v7 = CoInitialize(0);
  if ( v7 >= 0 )
  {
    v9 = 1;
    v7 = CoCreateInstance(&CLSID_HxHelpPane, 0, 0x17u, &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee, &ppv);
    if ( v7 >= 0 )
    {
      v13 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL);
      v14 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a3);
      v7 = v13(ppv, *v14);
      SysFreeString(bstrString);
      if ( v7 >= 0 )
      {
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 48;
        v12 = "Failed DisplayContents on Help Pane";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 47;
      v12 = "Failed to cocreate CLSID_HxHelpPane";
      goto LABEL_6;
    }
  }
  else
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 46;
      v12 = "Failed to call CoInitialize";
LABEL_6:
      v15 = v7;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v12,
        v15);
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v9 )
    CoUninitialize();
  if ( v7 < 0 )
    CSharedSH::SH_DisplayMsgBox(a2, 0x411u, v8, a5);
}

```

## disassembly

```asm
0x140028bf0  mov     rax, rsp
0x140028bf3  mov     [rax+10h], rbx
0x140028bf7  mov     [rax+20h], r9
0x140028bfb  mov     [rax+8], rcx
0x140028bff  push    rbp
0x140028c00  push    rsi
0x140028c01  push    rdi
0x140028c02  sub     rsp, 30h
0x140028c06  xor     ecx, ecx; pvReserved
0x140028c08  mov     qword ptr [rax+20h], 0
0x140028c10  mov     rsi, r8
0x140028c13  mov     rbp, rdx
0x140028c16  call    cs:__imp_CoInitialize
0x140028c1c  mov     ebx, eax
0x140028c1e  test    eax, eax
0x140028c20  jns     short loc_140028C86
0x140028c22  xor     edi, edi
0x140028c24  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c2b  lea     rax, WPP_GLOBAL_Control
0x140028c32  cmp     rcx, rax
0x140028c35  jz      loc_140028D65
0x140028c3b  test    byte ptr [rcx+1Ch], 8
0x140028c3f  jz      loc_140028D65
0x140028c45  cmp     byte ptr [rcx+19h], 2
0x140028c49  jb      loc_140028D65
0x140028c4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140028c54  lea     edx, [rdi+2Eh]
0x140028c57  lea     rcx, aFailedToCallCo; "Failed to call CoInitialize"
0x140028c5e  mov     [rsp+48h+var_20], ebx
0x140028c62  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140028c69  mov     [rsp+48h+ppv], rcx
0x140028c6e  mov     r9d, eax
0x140028c71  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c78  mov     rcx, [rcx+10h]
0x140028c7c  call    WPP_SF_DsD
0x140028c81  jmp     loc_140028D65
0x140028c86  lea     rax, [rsp+48h+arg_18]
0x140028c8b  mov     edi, 1
0x140028c90  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x140028c97  mov     [rsp+48h+ppv], rax; ppv
0x140028c9c  xor     edx, edx; pUnkOuter
0x140028c9e  lea     rcx, CLSID_HxHelpPane; rclsid
0x140028ca5  lea     r8d, [rdi+16h]; dwClsContext
0x140028ca9  call    cs:__imp_CoCreateInstance
0x140028caf  mov     ebx, eax
0x140028cb1  test    eax, eax
0x140028cb3  jns     short loc_140028CF4
0x140028cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140028cbc  lea     rax, WPP_GLOBAL_Control
0x140028cc3  cmp     rcx, rax
0x140028cc6  jz      loc_140028D65
0x140028ccc  test    byte ptr [rcx+1Ch], 8
0x140028cd0  jz      loc_140028D65
0x140028cd6  cmp     byte ptr [rcx+19h], 2
0x140028cda  jb      loc_140028D65
0x140028ce0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140028ce5  lea     edx, [rdi+2Eh]
0x140028ce8  lea     rcx, aFailedToCocrea; "Failed to cocreate CLSID_HxHelpPane"
0x140028cef  jmp     loc_140028C5E
0x140028cf4  mov     rax, [rsp+48h+arg_18]
0x140028cf9  mov     rdx, rsi; unsigned __int16 *
0x140028cfc  mov     rcx, [rax]
0x140028cff  mov     rbx, [rcx+18h]
0x140028d03  lea     rcx, [rsp+48h+bstrString]; this
0x140028d08  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140028d0d  mov     rcx, [rsp+48h+arg_18]
0x140028d12  mov     rdx, [rax]
0x140028d15  mov     rax, rbx
0x140028d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028d1d  mov     rcx, [rsp+48h+bstrString]; bstrString
0x140028d22  mov     ebx, eax
0x140028d24  call    cs:__imp_SysFreeString
0x140028d2a  test    ebx, ebx
0x140028d2c  jns     short loc_140028D63
0x140028d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028d35  lea     rax, WPP_GLOBAL_Control
0x140028d3c  cmp     rcx, rax
0x140028d3f  jz      short loc_140028D65
0x140028d41  test    byte ptr [rcx+1Ch], 8
0x140028d45  jz      short loc_140028D65
0x140028d47  cmp     byte ptr [rcx+19h], 2
0x140028d4b  jb      short loc_140028D65
0x140028d4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140028d52  mov     edx, 30h ; '0'
0x140028d57  lea     rcx, aFailedDisplayc; "Failed DisplayContents on Help Pane"
0x140028d5e  jmp     loc_140028C5E
0x140028d63  xor     ebx, ebx
0x140028d65  mov     rcx, [rsp+48h+arg_18]
0x140028d6a  test    rcx, rcx
0x140028d6d  jz      short loc_140028D84
0x140028d6f  mov     rax, [rcx]
0x140028d72  mov     rax, [rax+10h]
0x140028d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028d7b  mov     [rsp+48h+arg_18], 0
0x140028d84  test    edi, edi
0x140028d86  jz      short loc_140028D8E
0x140028d88  call    cs:__imp_CoUninitialize
0x140028d8e  test    ebx, ebx
0x140028d90  jns     short loc_140028DA4
0x140028d92  mov     r9d, [rsp+48h+arg_20]; int
0x140028d97  mov     edx, 411h; unsigned int
0x140028d9c  mov     rcx, rbp; hWnd
0x140028d9f  call    ?SH_DisplayMsgBox@CSharedSH@@SAHPEAUHWND__@@HHH@Z; CSharedSH::SH_DisplayMsgBox(HWND__ *,int,int,int)
0x140028da4  mov     rbx, [rsp+48h+arg_8]
0x140028da9  add     rsp, 30h
0x140028dad  pop     rdi
0x140028dae  pop     rsi
0x140028daf  pop     rbp
0x140028db0  retn
```
