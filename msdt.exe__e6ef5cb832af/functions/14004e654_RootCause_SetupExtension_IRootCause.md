# RootCause_SetupExtension(IRootCause *)

- ea: `0x14004e654`
- end: `0x14004eaf8`
- name: `?RootCause_SetupExtension@@YAJPEAVIRootCause@@@Z`
- size: `1188`
- prototype: `__int64 __fastcall(struct IRootCause *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140048d70`

## callees

- `0x140001d54`
- `0x14001b578`
- `0x140020420`
- `0x1400210f0`
- `0x140044700`
- `0x1400481d0`
- `0x14004e654`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14004eacc`
- `KERNEL32!HeapFree` at `0x14004eacc`
- `KERNEL32!GetProcessHeap` at `0x14004eab8`
- `KERNEL32!GetProcessHeap` at `0x14004eab8`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e8b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ea8a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004eaa3`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e8b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004ea8a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004eaa3`

## string_xrefs

- `0x14004e735`: `RootCause_SetupExtension`
- `0x14004e989`: `RootCause_SetupExtension`
- `0x14004ea28`: `RootCause_SetupExtension`
- `0x14004e910`: `./ExtensionPoint/SecurityBoundarySafe`

## pseudocode

```c
__int64 __fastcall RootCause_SetupExtension(struct IRootCause *a1)
{
  __int64 v1; // rax
  struct IXMLDOMDocument2 *v3; // rsi
  unsigned __int16 *v4; // r14
  __int64 (__fastcall *v5)(struct IRootCause *, RootCauseExtension **); // rax
  int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // ebx
  RootCauseExtension *v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // r9d
  int v13; // eax
  int v14; // eax
  int v15; // r9d
  int v16; // eax
  Configuration *v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int16 *v19; // rdx
  HANDLE ProcessHeap; // rax
  struct IXMLDOMDocument2 *v22; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMNode *v23; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+90h] [rbp+40h] BYREF
  BSTR v26; // [rsp+98h] [rbp+48h] BYREF
  RootCauseExtension *v27; // [rsp+A0h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp+58h] BYREF

  v1 = *(_QWORD *)a1;
  v27 = 0;
  v3 = 0;
  bstrString = 0;
  v4 = 0;
  v5 = *(__int64 (__fastcall **)(struct IRootCause *, RootCauseExtension **))(v1 + 32);
  v26 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v6 = v5(a1, &v27);
  v8 = v6;
  if ( v6 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", 685, v6);
    goto LABEL_54;
  }
  if ( v27 )
    goto LABEL_4;
  v9 = (RootCauseExtension *)operator new(0x10u);
  v27 = v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = 0;
    *((_QWORD *)v9 + 1) = 0;
    v27 = v9;
    v10 = (*(__int64 (__fastcall **)(struct IRootCause *, BSTR *))(*(_QWORD *)a1 + 96LL))(a1, &bstrString);
    v8 = v10;
    if ( v10 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", 696, v10);
      goto LABEL_54;
    }
    v11 = DwzXmlCreate(bstrString, &v22);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 699;
LABEL_10:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", v12, v11);
      v3 = v22;
      goto LABEL_54;
    }
    v3 = v22;
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct IXMLDOMNode **))v22->lpVtbl->get_documentElement)(
            v22,
            &v23);
    v8 = v13;
    if ( v13 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", 702, v13);
      goto LABEL_54;
    }
    if ( v13 != 1 && v23 )
    {
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v23->lpVtbl->selectSingleNode)(
              v23,
              L"./Parameter/Name[.='Keywords']/../Value",
              &v25);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = 713;
LABEL_17:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", v15, v14);
        goto LABEL_54;
      }
      if ( !v14 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 208LL))(v25, &v26);
        v8 = v14;
        if ( v14 < 0 )
        {
          v15 = 717;
          goto LABEL_17;
        }
        *(_QWORD *)v27 = v26;
        v26 = 0;
      }
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v25 = 0;
      }
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v23->lpVtbl->selectSingleNode)(
              v23,
              L"./Parameter/Name[.='WERParameter']/../Value",
              &v25);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = 729;
        goto LABEL_17;
      }
      if ( !v14 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 208LL))(v25, &v26);
        v8 = v14;
        if ( v14 < 0 )
        {
          v15 = 733;
          goto LABEL_17;
        }
        *((_QWORD *)v27 + 1) = v26;
        v26 = 0;
      }
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v25 = 0;
      }
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
      v3 = 0;
      v22 = 0;
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v14 = (*(__int64 (__fastcall **)(struct IRootCause *, BSTR *))(*(_QWORD *)a1 + 40LL))(a1, &bstrString);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = 748;
        goto LABEL_17;
      }
      v11 = DwzXmlCreate(bstrString, &v22);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 751;
        goto LABEL_10;
      }
      v3 = v22;
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v22->lpVtbl->selectSingleNode)(
              v22,
              L"./ExtensionPoint/SecurityBoundarySafe",
              &v25);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = 758;
        goto LABEL_17;
      }
      if ( !v14 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 208LL))(v25, &v26);
        v8 = v14;
        if ( v14 < 0 )
        {
          v15 = 761;
          goto LABEL_17;
        }
        v16 = DwzSubstituteXmlParameters(&v24, v26, v23);
        v8 = v16;
        if ( v16 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", 767, v16);
          v4 = v24;
          goto LABEL_54;
        }
        v4 = v24;
        v18 = -1;
        do
          ++v18;
        while ( v24[v18] );
        if ( v18 < 0x28 )
        {
          v19 = v24;
          *((_DWORD *)Config + 5) = 1;
          Configuration::SecurityBoundarySafe(v17, v19);
          v4 = 0;
        }
      }
      v14 = (*(__int64 (__fastcall **)(struct IRootCause *, RootCauseExtension *))(*(_QWORD *)a1 + 24LL))(a1, v27);
      v8 = v14;
      if ( v14 >= 0 )
      {
LABEL_4:
        v27 = 0;
        goto LABEL_54;
      }
      v15 = 777;
      goto LABEL_17;
    }
    v8 = -2147467259;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", 706, -2147467259);
  }
  else
  {
    v8 = -2147024882;
    v27 = 0;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RootCause_SetupExtension", 693, -2147024882);
  }
LABEL_54:
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
  if ( v23 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  if ( v26 )
  {
    SysFreeString(v26);
    v26 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( v27 )
    RootCauseExtension::`scalar deleting destructor'(v27, v7);
  return v8;
}

```

## disassembly

```asm
0x14004e654  push    rbp
0x14004e656  push    rbx
0x14004e657  push    rsi
0x14004e658  push    rdi
0x14004e659  push    r12
0x14004e65b  push    r14
0x14004e65d  push    r15
0x14004e65f  mov     rbp, rsp
0x14004e662  sub     rsp, 50h
0x14004e666  mov     rax, [rcx]
0x14004e669  lea     rdx, [rbp+arg_10]
0x14004e66d  xor     r12d, r12d
0x14004e670  mov     r15, rcx
0x14004e673  mov     [rbp+arg_10], r12
0x14004e677  mov     esi, r12d
0x14004e67a  mov     [rbp+bstrString], r12
0x14004e67e  mov     r14d, r12d
0x14004e681  mov     rax, [rax+20h]
0x14004e685  mov     [rbp+arg_8], r12
0x14004e689  mov     [rbp+var_20], r12
0x14004e68d  mov     [rbp+var_18], r12
0x14004e691  mov     [rbp+arg_0], r12
0x14004e695  mov     [rbp+var_10], r12
0x14004e699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e69e  mov     ebx, eax
0x14004e6a0  test    eax, eax
0x14004e6a2  jns     short loc_14004E6B3
0x14004e6a4  mov     [rsp+50h+var_30], eax
0x14004e6a8  mov     r9d, 2ADh
0x14004e6ae  jmp     loc_14004EA23
0x14004e6b3  cmp     [rbp+arg_10], r12
0x14004e6b7  jz      short loc_14004E6C2
0x14004e6b9  mov     [rbp+arg_10], r12
0x14004e6bd  jmp     loc_14004EA3B
0x14004e6c2  mov     ecx, 10h; Size
0x14004e6c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004e6cc  mov     [rbp+arg_10], rax
0x14004e6d0  test    rax, rax
0x14004e6d3  jz      loc_14004EA10
0x14004e6d9  mov     [rax], r12
0x14004e6dc  lea     rdx, [rbp+bstrString]
0x14004e6e0  mov     [rax+8], r12
0x14004e6e4  mov     rcx, r15
0x14004e6e7  mov     [rbp+arg_10], rax
0x14004e6eb  mov     rax, [r15]
0x14004e6ee  mov     rax, [rax+60h]
0x14004e6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e6f7  mov     ebx, eax
0x14004e6f9  test    eax, eax
0x14004e6fb  jns     short loc_14004E70C
0x14004e6fd  mov     [rsp+50h+var_30], eax
0x14004e701  mov     r9d, 2B8h
0x14004e707  jmp     loc_14004EA23
0x14004e70c  mov     rcx, [rbp+bstrString]; psz
0x14004e710  lea     rdx, [rbp+var_20]; struct IXMLDOMDocument2 **
0x14004e714  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x14004e719  mov     ebx, eax
0x14004e71b  test    eax, eax
0x14004e71d  jns     short loc_14004E74A
0x14004e71f  mov     r9d, 2BBh
0x14004e725  mov     ecx, 1; Level
0x14004e72a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004e731  mov     [rsp+50h+var_30], eax
0x14004e735  lea     r8, aRootcauseSetup; "RootCause_SetupExtension"
0x14004e73c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004e741  mov     rsi, [rbp+var_20]
0x14004e745  jmp     loc_14004EA3B
0x14004e74a  mov     rsi, [rbp+var_20]
0x14004e74e  lea     rdx, [rbp+var_18]
0x14004e752  mov     rcx, rsi
0x14004e755  mov     rax, [rsi]
0x14004e758  mov     rax, [rax+168h]
0x14004e75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e764  mov     ebx, eax
0x14004e766  test    eax, eax
0x14004e768  jns     short loc_14004E779
0x14004e76a  mov     [rsp+50h+var_30], eax
0x14004e76e  mov     r9d, 2BEh
0x14004e774  jmp     loc_14004EA23
0x14004e779  mov     edi, 1
0x14004e77e  cmp     eax, edi
0x14004e780  jz      loc_14004E9FC
0x14004e786  mov     rcx, [rbp+var_18]
0x14004e78a  test    rcx, rcx
0x14004e78d  jz      loc_14004E9FC
0x14004e793  mov     rax, [rcx]
0x14004e796  lea     r8, [rbp+arg_0]
0x14004e79a  lea     rdx, aParameterNameK; "./Parameter/Name[.='Keywords']/../Value"
0x14004e7a1  mov     rax, [rax+128h]
0x14004e7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e7ad  mov     ebx, eax
0x14004e7af  test    eax, eax
0x14004e7b1  jns     short loc_14004E7C4
0x14004e7b3  mov     r9d, 2C9h
0x14004e7b9  mov     [rsp+50h+var_30], eax
0x14004e7bd  mov     ecx, edi
0x14004e7bf  jmp     loc_14004EA28
0x14004e7c4  jnz     short loc_14004E7FA
0x14004e7c6  mov     rcx, [rbp+arg_0]
0x14004e7ca  lea     rdx, [rbp+arg_8]
0x14004e7ce  mov     rax, [rcx]
0x14004e7d1  mov     rax, [rax+0D0h]
0x14004e7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e7dd  mov     ebx, eax
0x14004e7df  test    eax, eax
0x14004e7e1  jns     short loc_14004E7EB
0x14004e7e3  mov     r9d, 2CDh
0x14004e7e9  jmp     short loc_14004E7B9
0x14004e7eb  mov     rax, [rbp+arg_8]
0x14004e7ef  mov     rcx, [rbp+arg_10]
0x14004e7f3  mov     [rcx], rax
0x14004e7f6  mov     [rbp+arg_8], r12
0x14004e7fa  mov     rcx, [rbp+arg_0]
0x14004e7fe  test    rcx, rcx
0x14004e801  jz      short loc_14004E813
0x14004e803  mov     rax, [rcx]
0x14004e806  mov     rax, [rax+10h]
0x14004e80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e80f  mov     [rbp+arg_0], r12
0x14004e813  mov     rcx, [rbp+var_18]
0x14004e817  lea     r8, [rbp+arg_0]
0x14004e81b  lea     rdx, aParameterNameW; "./Parameter/Name[.='WERParameter']/../V"...
0x14004e822  mov     rax, [rcx]
0x14004e825  mov     rax, [rax+128h]
0x14004e82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e831  mov     ebx, eax
0x14004e833  test    eax, eax
0x14004e835  jns     short loc_14004E842
0x14004e837  mov     r9d, 2D9h
0x14004e83d  jmp     loc_14004E7B9
0x14004e842  jnz     short loc_14004E87C
0x14004e844  mov     rcx, [rbp+arg_0]
0x14004e848  lea     rdx, [rbp+arg_8]
0x14004e84c  mov     rax, [rcx]
0x14004e84f  mov     rax, [rax+0D0h]
0x14004e856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e85b  mov     ebx, eax
0x14004e85d  test    eax, eax
0x14004e85f  jns     short loc_14004E86C
0x14004e861  mov     r9d, 2DDh
0x14004e867  jmp     loc_14004E7B9
0x14004e86c  mov     rcx, [rbp+arg_8]
0x14004e870  mov     rax, [rbp+arg_10]
0x14004e874  mov     [rax+8], rcx
0x14004e878  mov     [rbp+arg_8], r12
0x14004e87c  mov     rcx, [rbp+arg_0]
0x14004e880  test    rcx, rcx
0x14004e883  jz      short loc_14004E895
0x14004e885  mov     rax, [rcx]
0x14004e888  mov     rax, [rax+10h]
0x14004e88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e891  mov     [rbp+arg_0], r12
0x14004e895  mov     rax, [rsi]
0x14004e898  mov     rcx, rsi
0x14004e89b  mov     rax, [rax+10h]
0x14004e89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e8a4  mov     rcx, [rbp+bstrString]; bstrString
0x14004e8a8  mov     rsi, r12
0x14004e8ab  mov     [rbp+var_20], r12
0x14004e8af  test    rcx, rcx
0x14004e8b2  jz      short loc_14004E8C4
0x14004e8b4  call    cs:__imp_SysFreeString
0x14004e8bb  nop     dword ptr [rax+rax+00h]
0x14004e8c0  mov     [rbp+bstrString], r12
0x14004e8c4  mov     rax, [r15]
0x14004e8c7  lea     rdx, [rbp+bstrString]
0x14004e8cb  mov     rcx, r15
0x14004e8ce  mov     rax, [rax+28h]
0x14004e8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e8d7  mov     ebx, eax
0x14004e8d9  test    eax, eax
0x14004e8db  jns     short loc_14004E8E8
0x14004e8dd  mov     r9d, 2ECh
0x14004e8e3  jmp     loc_14004E7B9
0x14004e8e8  mov     rcx, [rbp+bstrString]; psz
0x14004e8ec  lea     rdx, [rbp+var_20]; struct IXMLDOMDocument2 **
0x14004e8f0  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x14004e8f5  mov     ebx, eax
0x14004e8f7  test    eax, eax
0x14004e8f9  jns     short loc_14004E908
0x14004e8fb  mov     r9d, 2EFh
0x14004e901  mov     ecx, edi
0x14004e903  jmp     loc_14004E72A
0x14004e908  mov     rsi, [rbp+var_20]
0x14004e90c  lea     r8, [rbp+arg_0]
0x14004e910  lea     rdx, aExtensionpoint_5; "./ExtensionPoint/SecurityBoundarySafe"
0x14004e917  mov     rcx, rsi
0x14004e91a  mov     rax, [rsi]
0x14004e91d  mov     rax, [rax+128h]
0x14004e924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e929  mov     ebx, eax
0x14004e92b  test    eax, eax
0x14004e92d  jns     short loc_14004E93A
0x14004e92f  mov     r9d, 2F6h
0x14004e935  jmp     loc_14004E7B9
0x14004e93a  jnz     loc_14004E9D4
0x14004e940  mov     rcx, [rbp+arg_0]
0x14004e944  lea     rdx, [rbp+arg_8]
0x14004e948  mov     rax, [rcx]
0x14004e94b  mov     rax, [rax+0D0h]
0x14004e952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e957  mov     ebx, eax
0x14004e959  test    eax, eax
0x14004e95b  jns     short loc_14004E968
0x14004e95d  mov     r9d, 2F9h
0x14004e963  jmp     loc_14004E7B9
0x14004e968  mov     r8, [rbp+var_18]; struct IXMLDOMNode *
0x14004e96c  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x14004e970  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x14004e974  call    ?DwzSubstituteXmlParameters@@YAJPEAPEAGPEBGPEAUIXMLDOMNode@@@Z; DwzSubstituteXmlParameters(ushort * *,ushort const *,IXMLDOMNode *)
0x14004e979  mov     ebx, eax
0x14004e97b  test    eax, eax
0x14004e97d  jns     short loc_14004E9A7
0x14004e97f  mov     r9d, 2FFh
0x14004e985  mov     [rsp+50h+var_30], eax
0x14004e989  lea     r8, aRootcauseSetup; "RootCause_SetupExtension"
0x14004e990  mov     ecx, edi; Level
0x14004e992  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004e999  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004e99e  mov     r14, [rbp+var_10]
0x14004e9a2  jmp     loc_14004EA3B
0x14004e9a7  mov     r14, [rbp+var_10]
0x14004e9ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004e9af  inc     rax
0x14004e9b2  cmp     [r14+rax*2], r12w
0x14004e9b7  jnz     short loc_14004E9AF
0x14004e9b9  cmp     rax, 28h ; '('
0x14004e9bd  jnb     short loc_14004E9D4
0x14004e9bf  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14004e9c6  mov     rdx, r14; unsigned __int16 *
0x14004e9c9  mov     [rax+14h], edi
0x14004e9cc  call    ?SecurityBoundarySafe@Configuration@@QEAAXPEAG@Z; Configuration::SecurityBoundarySafe(ushort *)
0x14004e9d1  mov     r14, r12
0x14004e9d4  mov     rax, [r15]
0x14004e9d7  mov     rcx, r15
0x14004e9da  mov     rdx, [rbp+arg_10]
0x14004e9de  mov     rax, [rax+18h]
0x14004e9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e9e7  mov     ebx, eax
0x14004e9e9  test    eax, eax
0x14004e9eb  jns     loc_14004E6B9
0x14004e9f1  mov     r9d, 309h
0x14004e9f7  jmp     loc_14004E7B9
0x14004e9fc  mov     ebx, 80004005h
0x14004ea01  mov     r9d, 2C2h
0x14004ea07  mov     [rsp+50h+var_30], ebx
0x14004ea0b  jmp     loc_14004E7BD
0x14004ea10  mov     ebx, 8007000Eh
0x14004ea15  mov     [rbp+arg_10], r12
0x14004ea19  mov     [rsp+50h+var_30], ebx
0x14004ea1d  mov     r9d, 2B5h
0x14004ea23  mov     ecx, 1; Level
0x14004ea28  lea     r8, aRootcauseSetup; "RootCause_SetupExtension"
0x14004ea2f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004ea36  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004ea3b  mov     rcx, [rbp+arg_0]
0x14004ea3f  test    rcx, rcx
0x14004ea42  jz      short loc_14004EA54
0x14004ea44  mov     rax, [rcx]
0x14004ea47  mov     rax, [rax+10h]
0x14004ea4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ea50  mov     [rbp+arg_0], r12
0x14004ea54  test    rsi, rsi
0x14004ea57  jz      short loc_14004EA68
0x14004ea59  mov     rax, [rsi]
0x14004ea5c  mov     rcx, rsi
0x14004ea5f  mov     rax, [rax+10h]
0x14004ea63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ea68  mov     rcx, [rbp+var_18]
0x14004ea6c  test    rcx, rcx
0x14004ea6f  jz      short loc_14004EA81
0x14004ea71  mov     rax, [rcx]
0x14004ea74  mov     rax, [rax+10h]
0x14004ea78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ea7d  mov     [rbp+var_18], r12
0x14004ea81  mov     rcx, [rbp+arg_8]; bstrString
0x14004ea85  test    rcx, rcx
0x14004ea88  jz      short loc_14004EA9A
0x14004ea8a  call    cs:__imp_SysFreeString
0x14004ea91  nop     dword ptr [rax+rax+00h]
0x14004ea96  mov     [rbp+arg_8], r12
0x14004ea9a  mov     rcx, [rbp+bstrString]; bstrString
0x14004ea9e  test    rcx, rcx
0x14004eaa1  jz      short loc_14004EAB3
0x14004eaa3  call    cs:__imp_SysFreeString
0x14004eaaa  nop     dword ptr [rax+rax+00h]
0x14004eaaf  mov     [rbp+bstrString], r12
0x14004eab3  test    r14, r14
0x14004eab6  jz      short loc_14004EAD8
0x14004eab8  call    cs:__imp_GetProcessHeap
0x14004eabf  nop     dword ptr [rax+rax+00h]
0x14004eac4  mov     r8, r14; lpMem
0x14004eac7  xor     edx, edx; dwFlags
0x14004eac9  mov     rcx, rax; hHeap
0x14004eacc  call    cs:__imp_HeapFree
0x14004ead3  nop     dword ptr [rax+rax+00h]
0x14004ead8  mov     rcx, [rbp+arg_10]; this
0x14004eadc  test    rcx, rcx
0x14004eadf  jz      short loc_14004EAE6
0x14004eae1  call    ??_GRootCauseExtension@@QEAAPEAXI@Z; RootCauseExtension::`scalar deleting destructor'(uint)
  ... truncated ...
```
