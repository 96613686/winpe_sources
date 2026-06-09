# LaunchRASWizard

- ea: `0x18002cdb8`
- end: `0x18002d077`
- name: `LaunchRASWizard`
- size: `703`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014b40`

## callees

- `0x18000f338`
- `0x18002c594`
- `0x18002cdb8`
- `0x18002d284`
- `0x18003c4ec`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d028`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d028`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ce8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ce8d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ce44`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ce44`
- `rtutils!TracePrintfExA` at `0x18002cf06`
- `rtutils!TracePrintfExA` at `0x18002cf32`
- `rtutils!TracePrintfExA` at `0x18002cfce`
- `rtutils!TracePrintfExA` at `0x18002d003`
- `rtutils!TracePrintfExA` at `0x18002d04a`
- `rtutils!TracePrintfExA` at `0x18002cf06`
- `rtutils!TracePrintfExA` at `0x18002cf32`
- `rtutils!TracePrintfExA` at `0x18002cfce`
- `rtutils!TracePrintfExA` at `0x18002d003`
- `rtutils!TracePrintfExA` at `0x18002d04a`

## string_xrefs

- `0x18002cfc2`: `Failed to make call LaunchIncomingConnectionWizard on IRasDlgAdmin interface. hr = %#x`

## pseudocode

```c
__int64 __fastcall LaunchRASWizard(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v4; // eax
  int v5; // r14d
  __int64 *v9; // rdi
  HRESULT v10; // eax
  const struct _GUID *v11; // rdx
  int v12; // ebx
  HRESULT v13; // r15d
  HRESULT v14; // eax
  unsigned __int16 v15; // r14
  __int64 v16; // rdx
  int v17; // eax
  unsigned __int16 v18; // di
  void *v19; // rcx
  HWND v20; // rcx
  int v21; // eax
  DWORD v22; // edi
  int v23; // eax
  unsigned __int16 v24; // di
  HMODULE v25; // rcx
  const wchar_t *StringPcch; // rax
  void *v28; // [rsp+50h] [rbp-30h] BYREF
  __int128 v29; // [rsp+58h] [rbp-28h] BYREF
  __int128 v30; // [rsp+68h] [rbp-18h]
  LPVOID ppv; // [rsp+D0h] [rbp+50h] BYREF

  v4 = *(_DWORD *)(a3 + 12);
  v5 = 0;
  v29 = 0;
  v30 = 0;
  if ( (v4 & 2) != 0 )
  {
    v9 = qword_180056FF8;
    goto LABEL_11;
  }
  if ( (v4 & 0x10) != 0 )
  {
    v9 = qword_180057028;
    goto LABEL_11;
  }
  if ( (v4 & 0x20) != 0 )
  {
    v9 = qword_180057018;
    goto LABEL_11;
  }
  if ( (v4 & 0x80u) != 0 )
  {
    v9 = qword_180056FE8;
    goto LABEL_11;
  }
  if ( (v4 & 0x400) != 0 )
  {
    v9 = qword_180057008;
    v5 = 1;
LABEL_11:
    v10 = CoInitializeEx(0, 6u);
    v12 = 0;
    v13 = v10;
    if ( v10 != -2147417850 )
      v12 = v10;
    if ( v12 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CoInitializeEx failed. hr = %#x", v12);
      return (unsigned __int16)v12;
    }
    v12 = 0;
    if ( v5 )
    {
      v20 = *(HWND *)(a3 + 4);
      v28 = 0;
      v21 = CoCreateInstanceAsAdmin(v20, v11, &IID_IRasDlgAdmin, &v28);
      v22 = v21;
      if ( v21 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get IRasDlgAdmin interface. hr = %#x", v21);
        if ( v22 != -2147023673 )
        {
          v12 = (unsigned __int16)v22;
          ThrowErrorBox(*(HWND *)(a3 + 4), v22);
        }
        goto LABEL_37;
      }
      v23 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v28 + 40LL))(v28, *(_QWORD *)(a3 + 4));
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "Failed to make call LaunchIncomingConnectionWizard on IRasDlgAdmin interface. hr = %#x",
            v23);
        v12 = v24;
      }
      else if ( !v23 )
      {
        v25 = g_hinstDll;
        *a4 = 1;
        LODWORD(ppv) = 0;
        StringPcch = (const wchar_t *)PszLoadStringPcch(v25);
        StringCchCopyW((STRSAFE_LPWSTR)(a3 + 24), 0x101u, StringPcch);
      }
      v19 = v28;
    }
    else
    {
      ppv = 0;
      v14 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get IXWizard interface. hr = %#x", v14);
        v12 = v15;
        goto LABEL_37;
      }
      v16 = *(_QWORD *)(a3 + 4);
      *((_QWORD *)&v29 + 1) = a1;
      *(_QWORD *)&v29 = a3;
      *(_QWORD *)&v30 = a2;
      *((_QWORD *)&v30 + 1) = a4;
      v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *, _DWORD, _DWORD, _QWORD, __int128 *, _DWORD))(*(_QWORD *)ppv + 176LL))(
              ppv,
              v16,
              0,
              v9,
              0,
              0,
              0,
              &v29,
              0);
      v18 = v17;
      if ( v17 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to make call RunWizard on IXWizard interface. hr = %#x", v17);
        v12 = v18;
      }
      v19 = ppv;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_37:
    if ( v13 != -2147417850 )
      CoUninitialize();
    return (unsigned int)v12;
  }
  return 87;
}

```

## disassembly

```asm
0x18002cdb8  mov     [rsp-38h+arg_8], rbx
0x18002cdbd  mov     [rsp-38h+arg_0], rcx
0x18002cdc2  push    rbp
0x18002cdc3  push    rsi
0x18002cdc4  push    rdi
0x18002cdc5  push    r12
0x18002cdc7  push    r13
0x18002cdc9  push    r14
0x18002cdcb  push    r15
0x18002cdcd  mov     rbp, rsp
0x18002cdd0  sub     rsp, 80h
0x18002cdd7  mov     eax, [r8+0Ch]
0x18002cddb  xorps   xmm0, xmm0
0x18002cdde  xor     r14d, r14d
0x18002cde1  mov     r12, r9
0x18002cde4  mov     rsi, r8
0x18002cde7  mov     r13, rdx
0x18002cdea  movups  [rbp+var_28], xmm0
0x18002cdee  movups  [rbp+var_18], xmm0
0x18002cdf2  test    al, 2
0x18002cdf4  jz      short loc_18002CDFF
0x18002cdf6  lea     rdi, qword_180056FF8
0x18002cdfd  jmp     short loc_18002CE3D
0x18002cdff  test    al, 10h
0x18002ce01  jz      short loc_18002CE0C
0x18002ce03  lea     rdi, qword_180057028
0x18002ce0a  jmp     short loc_18002CE3D
0x18002ce0c  test    al, 20h
0x18002ce0e  jz      short loc_18002CE19
0x18002ce10  lea     rdi, qword_180057018
0x18002ce17  jmp     short loc_18002CE3D
0x18002ce19  test    al, al
0x18002ce1b  jns     short loc_18002CE26
0x18002ce1d  lea     rdi, qword_180056FE8
0x18002ce24  jmp     short loc_18002CE3D
0x18002ce26  bt      eax, 0Ah
0x18002ce2a  jnb     loc_18002D057
0x18002ce30  lea     rdi, qword_180057008
0x18002ce37  mov     r14d, 1
0x18002ce3d  mov     edx, 6; dwCoInit
0x18002ce42  xor     ecx, ecx; pvReserved
0x18002ce44  call    cs:__imp_CoInitializeEx
0x18002ce4a  xor     ebx, ebx
0x18002ce4c  mov     r15d, eax
0x18002ce4f  cmp     eax, 80010106h
0x18002ce54  cmovnz  ebx, eax
0x18002ce57  test    ebx, ebx
0x18002ce59  js      loc_18002D030
0x18002ce5f  xor     ebx, ebx
0x18002ce61  test    r14d, r14d
0x18002ce64  jnz     loc_18002CF41
0x18002ce6a  lea     rax, [rbp+arg_10]
0x18002ce6e  mov     [rbp+arg_10], rbx
0x18002ce72  lea     r9, IID_IXWizard; riid
0x18002ce79  mov     [rsp+80h+ppv], rax; ppv
0x18002ce7e  xor     edx, edx; pUnkOuter
0x18002ce80  lea     rcx, CLSID_CXWizard; rclsid
0x18002ce87  mov     r8d, 401h; dwClsContext
0x18002ce8d  call    cs:__imp_CoCreateInstance
0x18002ce93  xor     r8d, r8d
0x18002ce96  mov     r14d, eax
0x18002ce99  test    eax, eax
0x18002ce9b  js      short loc_18002CF18
0x18002ce9d  mov     rcx, [rbp+arg_10]
0x18002cea1  lea     rdx, [rbp+var_28]
0x18002cea5  mov     rax, [rbp+arg_0]
0x18002cea9  mov     r9, rdi
0x18002ceac  mov     [rsp+80h+var_40], r8d
0x18002ceb1  mov     [rsp+80h+var_48], rdx
0x18002ceb6  mov     rdx, [rsi+4]
0x18002ceba  mov     qword ptr [rbp+var_28+8], rax
0x18002cebe  mov     [rsp+80h+var_50], r8
0x18002cec3  mov     qword ptr [rbp+var_28], rsi
0x18002cec7  mov     qword ptr [rbp+var_18], r13
0x18002cecb  mov     qword ptr [rbp+var_18+8], r12
0x18002cecf  mov     rax, [rcx]
0x18002ced2  mov     [rsp+80h+var_58], r8d
0x18002ced7  mov     dword ptr [rsp+80h+ppv], r8d
0x18002cedc  mov     rax, [rax+0B0h]
0x18002cee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cee8  mov     edi, eax
0x18002ceea  test    eax, eax
0x18002ceec  jns     short loc_18002CF0F
0x18002ceee  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cef4  cmp     ecx, 0FFFFFFFFh
0x18002cef7  jz      short loc_18002CF0C
0x18002cef9  mov     r9d, eax
0x18002cefc  lea     r8, aFailedToMakeCa_1; "Failed to make call RunWizard on IXWiza"...
0x18002cf03  lea     edx, [rbx+0Ch]; dwFlags
0x18002cf06  call    cs:__imp_TracePrintfExA
0x18002cf0c  movzx   ebx, di
0x18002cf0f  mov     rcx, [rbp+arg_10]
0x18002cf13  jmp     loc_18002CFDB
0x18002cf18  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cf1e  cmp     ecx, 0FFFFFFFFh
0x18002cf21  jz      short loc_18002CF38
0x18002cf23  mov     r9d, r14d
0x18002cf26  lea     r8, aFailedToGetIxw; "Failed to get IXWizard interface. hr = "...
0x18002cf2d  mov     edx, 0Ch; dwFlags
0x18002cf32  call    cs:__imp_TracePrintfExA
0x18002cf38  movzx   ebx, r14w
0x18002cf3c  jmp     loc_18002D01F
0x18002cf41  mov     rcx, [rsi+4]; HWND
0x18002cf45  lea     r9, [rbp+var_30]; void **
0x18002cf49  lea     r8, IID_IRasDlgAdmin; struct _GUID *
0x18002cf50  mov     [rbp+var_30], rbx
0x18002cf54  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18002cf59  mov     edi, eax
0x18002cf5b  test    eax, eax
0x18002cf5d  js      loc_18002CFE9
0x18002cf63  mov     rcx, [rbp+var_30]
0x18002cf67  mov     rdx, [rsi+4]
0x18002cf6b  mov     rax, [rcx]
0x18002cf6e  mov     rax, [rax+28h]
0x18002cf72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf77  mov     edi, eax
0x18002cf79  test    eax, eax
0x18002cf7b  js      short loc_18002CFB4
0x18002cf7d  test    eax, eax
0x18002cf7f  jnz     short loc_18002CFD7
0x18002cf81  mov     rcx, cs:g_hinstDll; hModule
0x18002cf88  lea     r8, [rbp+arg_10]
0x18002cf8c  mov     edx, 1CC7h
0x18002cf91  mov     dword ptr [r12], 1
0x18002cf99  mov     dword ptr [rbp+arg_10], ebx
0x18002cf9c  call    PszLoadStringPcch
0x18002cfa1  lea     rcx, [rsi+18h]; pszDest
0x18002cfa5  mov     r8, rax; pszSrc
0x18002cfa8  mov     edx, 101h; cchDest
0x18002cfad  call    StringCchCopyW
0x18002cfb2  jmp     short loc_18002CFD7
0x18002cfb4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cfba  cmp     ecx, 0FFFFFFFFh
0x18002cfbd  jz      short loc_18002CFD4
0x18002cfbf  mov     r9d, edi
0x18002cfc2  lea     r8, aFailedToMakeCa_0; "Failed to make call LaunchIncomingConne"...
0x18002cfc9  mov     edx, 0Ch; dwFlags
0x18002cfce  call    cs:__imp_TracePrintfExA
0x18002cfd4  movzx   ebx, di
0x18002cfd7  mov     rcx, [rbp+var_30]
0x18002cfdb  mov     rax, [rcx]
0x18002cfde  mov     rax, [rax+10h]
0x18002cfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfe7  jmp     short loc_18002D01F
0x18002cfe9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cfef  cmp     ecx, 0FFFFFFFFh
0x18002cff2  jz      short loc_18002D009
0x18002cff4  mov     r9d, edi
0x18002cff7  lea     r8, aFailedToGetIra_0; "Failed to get IRasDlgAdmin interface. h"...
0x18002cffe  mov     edx, 0Ch; dwFlags
0x18002d003  call    cs:__imp_TracePrintfExA
0x18002d009  cmp     edi, 800704C7h
0x18002d00f  jz      short loc_18002D01F
0x18002d011  mov     rcx, [rsi+4]; hwndOwner
0x18002d015  mov     edx, edi; dwMessageId
0x18002d017  movzx   ebx, di
0x18002d01a  call    ThrowErrorBox
0x18002d01f  cmp     r15d, 80010106h
0x18002d026  jz      short loc_18002D053
0x18002d028  call    cs:__imp_CoUninitialize
0x18002d02e  jmp     short loc_18002D053
0x18002d030  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002d036  cmp     ecx, 0FFFFFFFFh
0x18002d039  jz      short loc_18002D050
0x18002d03b  mov     r9d, ebx
0x18002d03e  lea     r8, aCoinitializeex; "CoInitializeEx failed. hr = %#x"
0x18002d045  mov     edx, 0Ch; dwFlags
0x18002d04a  call    cs:__imp_TracePrintfExA
0x18002d050  movzx   ebx, bx
0x18002d053  mov     eax, ebx
0x18002d055  jmp     short loc_18002D05C
0x18002d057  mov     eax, 57h ; 'W'
0x18002d05c  mov     rbx, [rsp+80h+arg_8]
0x18002d064  add     rsp, 80h
0x18002d06b  pop     r15
0x18002d06d  pop     r14
0x18002d06f  pop     r13
0x18002d071  pop     r12
0x18002d073  pop     rdi
0x18002d074  pop     rsi
0x18002d075  pop     rbp
0x18002d076  retn
```
