# ReadXMLControlBlock(FILE_ATTRIBUTES *,ushort *)

- ea: `0x140046600`
- end: `0x140046bbb`
- name: `?ReadXMLControlBlock@@YAJPEAUFILE_ATTRIBUTES@@PEAG@Z`
- size: `1467`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140048730`

## callees

- `0x140034ce4`
- `0x140035788`
- `0x140046600`
- `0x14004d010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14004694a`
- `KERNEL32!CompareStringW` at `0x14004694a`
- `KERNEL32!HeapFree` at `0x140046978`
- `KERNEL32!HeapFree` at `0x140046a7a`
- `KERNEL32!HeapFree` at `0x140046ae5`
- `KERNEL32!HeapFree` at `0x140046b11`
- `KERNEL32!HeapFree` at `0x140046b4e`
- `KERNEL32!HeapFree` at `0x140046978`
- `KERNEL32!HeapFree` at `0x140046a7a`
- `KERNEL32!HeapFree` at `0x140046ae5`
- `KERNEL32!HeapFree` at `0x140046b11`
- `KERNEL32!HeapFree` at `0x140046b4e`
- `KERNEL32!GetProcessHeap` at `0x140046964`
- `KERNEL32!GetProcessHeap` at `0x140046a66`
- `KERNEL32!GetProcessHeap` at `0x140046ad1`
- `KERNEL32!GetProcessHeap` at `0x140046afd`
- `KERNEL32!GetProcessHeap` at `0x140046b3a`
- `KERNEL32!GetProcessHeap` at `0x140046964`
- `KERNEL32!GetProcessHeap` at `0x140046a66`
- `KERNEL32!GetProcessHeap` at `0x140046ad1`
- `KERNEL32!GetProcessHeap` at `0x140046afd`
- `KERNEL32!GetProcessHeap` at `0x140046b3a`
- `msvcrt!_wtoi` at `0x140046a02`
- `msvcrt!_wtoi` at `0x140046aa9`
- `msvcrt!_wtoi` at `0x140046a02`
- `msvcrt!_wtoi` at `0x140046aa9`
- `ole32!CoCreateInstance` at `0x14004670d`
- `ole32!CoCreateInstance` at `0x14004670d`
- `OLEAUT32!__imp_SysAllocString` at `0x140046646`
- `OLEAUT32!__imp_SysAllocString` at `0x140046646`
- `OLEAUT32!__imp_SysFreeString` at `0x140046b29`
- `OLEAUT32!__imp_SysFreeString` at `0x140046b29`
- `OLEAUT32!__imp_VariantClear` at `0x14004676e`
- `OLEAUT32!__imp_VariantClear` at `0x1400467d1`
- `OLEAUT32!__imp_VariantClear` at `0x140046834`
- `OLEAUT32!__imp_VariantClear` at `0x14004676e`
- `OLEAUT32!__imp_VariantClear` at `0x1400467d1`
- `OLEAUT32!__imp_VariantClear` at `0x140046834`

## string_xrefs

- `0x14004663f`: `RCCOMMAND`
- `0x140046687`: `ReadXMLControlBlock`
- `0x1400466c6`: `ReadXMLControlBlock`
- `0x1400469d3`: `ReadXMLControlBlock`
- `0x140046a40`: `ReadXMLControlBlock`

## pseudocode

```c
__int64 __fastcall ReadXMLControlBlock(unsigned __int16 **a1, unsigned __int16 *a2)
{
  WCHAR *v4; // rdi
  OLECHAR *v5; // r15
  signed int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // r9d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  signed int AttributeFromAttributeListAsString; // eax
  unsigned int v13; // r9d
  HANDLE v14; // rax
  int v15; // eax
  HANDLE v16; // rax
  int v17; // eax
  int v18; // eax
  unsigned __int16 *v19; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v21; // r14
  HANDLE v22; // rax
  HANDLE v23; // rax
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  struct IXMLDOMNamedNodeMap *v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v29; // [rsp+60h] [rbp-20h] BYREF
  __int16 v30; // [rsp+D0h] [rbp+50h] BYREF
  PCNZWCH lpString1; // [rsp+D8h] [rbp+58h] BYREF

  ppv = 0;
  v30 = -1;
  v27 = 0;
  v26 = 0;
  v4 = 0;
  lpString1 = 0;
  v5 = SysAllocString(L"RCCOMMAND");
  if ( !v5 )
  {
    v6 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)L"ReadXMLControlBlock",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      0x24Cu,
      L"ReadXMLControlBlock",
      0x8007000E);
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    CEventLogger::LogError(
      (CEventLogger *)L"ReadXMLControlBlock",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      0x24Eu,
      L"ReadXMLControlBlock",
      0x80004003);
LABEL_5:
    if ( !a1 )
      goto LABEL_51;
    goto LABEL_47;
  }
  if ( a1 )
  {
    v7 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 598;
LABEL_38:
      CEventLogger::LogError(
        (CEventLogger *)L"ReadXMLControlBlock",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        v8,
        L"ReadXMLControlBlock",
        v7);
      goto LABEL_47;
    }
    v9 = *(_QWORD *)ppv;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v29 = pvarg;
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v9 + 640))(ppv, L"ProhibitDTD", &v29);
    VariantClear(&pvarg);
    if ( v6 < 0 )
    {
      CEventLogger::LogError(
        (CEventLogger *)L"ReadXMLControlBlock",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        0x258u,
        L"ReadXMLControlBlock",
        v6);
      goto LABEL_47;
    }
    v10 = *(_QWORD *)ppv;
    pvarg.vt = 11;
    pvarg.iVal = 0;
    v29 = pvarg;
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v10 + 640))(ppv, L"AllowXsltScript", &v29);
    VariantClear(&pvarg);
    if ( v6 < 0 )
    {
      CEventLogger::LogError(
        (CEventLogger *)L"ReadXMLControlBlock",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        0x259u,
        L"ReadXMLControlBlock",
        v6);
      goto LABEL_47;
    }
    v11 = *(_QWORD *)ppv;
    pvarg.vt = 11;
    pvarg.iVal = 0;
    v29 = pvarg;
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v11 + 640))(
           ppv,
           L"AllowDocumentFunction",
           &v29);
    VariantClear(&pvarg);
    if ( v6 < 0 )
    {
      CEventLogger::LogError(
        (CEventLogger *)L"ReadXMLControlBlock",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        0x25Au,
        L"ReadXMLControlBlock",
        v6);
      goto LABEL_47;
    }
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 607;
      goto LABEL_38;
    }
    if ( (*(int (__fastcall **)(LPVOID, unsigned __int16 *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a2, &v30) >= 0
      && v30 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 296LL))(ppv, v5, &v27);
      if ( v6 < 0 )
        goto LABEL_47;
      if ( !v27 )
        goto LABEL_52;
      v6 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)v27 + 136LL))(v27, &v26);
      if ( v6 < 0 )
      {
LABEL_47:
        v19 = *a1;
        if ( *a1 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v19);
          *a1 = 0;
        }
        v21 = a1[2];
        if ( v21 )
        {
          v22 = GetProcessHeap();
          HeapFree(v22, 0, v21);
          a1[2] = 0;
        }
LABEL_51:
        if ( !v5 )
          goto LABEL_53;
        goto LABEL_52;
      }
      if ( !v26 )
        goto LABEL_52;
      AttributeFromAttributeListAsString = GetAttributeFromAttributeListAsString(
                                             v26,
                                             L"NAME",
                                             (unsigned __int16 **)&lpString1);
      v6 = AttributeFromAttributeListAsString;
      if ( AttributeFromAttributeListAsString < 0 )
      {
        v13 = 631;
LABEL_34:
        CEventLogger::LogError(
          (CEventLogger *)L"ReadXMLControlBlock",
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
          v13,
          L"ReadXMLControlBlock",
          AttributeFromAttributeListAsString);
        v4 = (WCHAR *)lpString1;
        goto LABEL_47;
      }
      v4 = (WCHAR *)lpString1;
      if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"FILEXFER", -1) == 2 )
      {
        if ( v4 )
        {
          v14 = GetProcessHeap();
          HeapFree(v14, 0, v4);
          v4 = 0;
          lpString1 = 0;
        }
        v7 = GetAttributeFromAttributeListAsString(v26, L"FILENAME", a1);
        v6 = v7;
        if ( v7 < 0 )
        {
          v8 = 654;
          goto LABEL_38;
        }
        AttributeFromAttributeListAsString = GetAttributeFromAttributeListAsString(
                                               v26,
                                               L"FILESIZE",
                                               (unsigned __int16 **)&lpString1);
        v6 = AttributeFromAttributeListAsString;
        if ( AttributeFromAttributeListAsString < 0 )
        {
          v13 = 659;
          goto LABEL_34;
        }
        v4 = (WCHAR *)lpString1;
        v15 = _wtoi(lpString1);
        if ( v15 >= 0 )
        {
          a1[1] = (unsigned __int16 *)v15;
          v7 = GetAttributeFromAttributeListAsString(v26, L"CHANNELID", a1 + 2);
          v6 = v7;
          if ( v7 < 0 )
          {
            v8 = 671;
            goto LABEL_38;
          }
          if ( v4 )
          {
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v4);
            lpString1 = 0;
          }
          v17 = GetAttributeFromAttributeListAsString(v26, L"INTERNALDATA", (unsigned __int16 **)&lpString1);
          v4 = (WCHAR *)lpString1;
          if ( v17 < 0 )
          {
            *((_DWORD *)a1 + 6) = 0;
            goto LABEL_52;
          }
          v18 = _wtoi(lpString1);
          if ( v18 >= 0 )
          {
            *((_DWORD *)a1 + 6) = v18;
            goto LABEL_52;
          }
        }
      }
    }
    v6 = -2147467259;
    goto LABEL_47;
  }
  v6 = -2147467261;
  CEventLogger::LogError(
    (CEventLogger *)L"ReadXMLControlBlock",
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
    0x24Fu,
    L"ReadXMLControlBlock",
    0x80004003);
LABEL_52:
  SysFreeString(v5);
LABEL_53:
  if ( v4 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v4);
  }
  if ( v26 )
    ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v26->lpVtbl->Release)(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140046600  mov     [rsp-38h+arg_0], rbx
0x140046605  push    rbp
0x140046606  push    rsi
0x140046607  push    rdi
0x140046608  push    r12
0x14004660a  push    r13
0x14004660c  push    r14
0x14004660e  push    r15
0x140046610  mov     rbp, rsp
0x140046613  sub     rsp, 80h
0x14004661a  mov     r14, rdx
0x14004661d  mov     rsi, rcx
0x140046620  xor     r12d, r12d
0x140046623  mov     [rbp+var_50], r12
0x140046627  or      r13d, 0FFFFFFFFh
0x14004662b  mov     [rbp+arg_10], r13w
0x140046630  mov     [rbp+var_40], r12
0x140046634  mov     [rbp+var_48], r12
0x140046638  mov     edi, r12d
0x14004663b  mov     [rbp+lpString1], r12
0x14004663f  lea     rcx, aRccommand; "RCCOMMAND"
0x140046646  call    cs:__imp_SysAllocString
0x14004664d  nop     dword ptr [rax+rax+00h]
0x140046652  mov     r15, rax
0x140046655  test    rax, rax
0x140046658  jnz     short loc_14004666F
0x14004665a  mov     ebx, 8007000Eh
0x14004665f  mov     [rsp+80h+cchCount2], 8007000Eh
0x140046667  mov     r9d, 24Ch
0x14004666d  jmp     short loc_140046687
0x14004666f  test    r14, r14
0x140046672  jnz     short loc_1400466B4
0x140046674  mov     ebx, 80004003h
0x140046679  mov     [rsp+80h+cchCount2], 80004003h; unsigned int
0x140046681  mov     r9d, 24Eh; unsigned int
0x140046687  lea     rcx, aReadxmlcontrol; "ReadXMLControlBlock"
0x14004668e  mov     [rsp+80h+ppv], rcx; unsigned __int16 *
0x140046693  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x14004669a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400466a1  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400466a6  test    rsi, rsi
0x1400466a9  jz      loc_140046B21
0x1400466af  jmp     loc_140046AC9
0x1400466b4  test    rsi, rsi
0x1400466b7  jnz     short loc_1400466F0
0x1400466b9  mov     ebx, 80004003h
0x1400466be  mov     [rsp+80h+cchCount2], 80004003h; unsigned int
0x1400466c6  lea     rcx, aReadxmlcontrol; "ReadXMLControlBlock"
0x1400466cd  mov     [rsp+80h+ppv], rcx; unsigned __int16 *
0x1400466d2  mov     r9d, 24Fh; unsigned int
0x1400466d8  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x1400466df  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400466e6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400466eb  jmp     loc_140046B26
0x1400466f0  lea     rax, [rbp+var_50]
0x1400466f4  mov     [rsp+80h+ppv], rax; ppv
0x1400466f9  lea     r9, IID_IXMLDOMDocument; riid
0x140046700  xor     edx, edx; pUnkOuter
0x140046702  lea     r8d, [rdx+1]; dwClsContext
0x140046706  lea     rcx, CLSID_DOMDocument60; rclsid
0x14004670d  call    cs:__imp_CoCreateInstance
0x140046714  nop     dword ptr [rax+rax+00h]
0x140046719  mov     ebx, eax
0x14004671b  test    eax, eax
0x14004671d  jns     short loc_14004672A
0x14004671f  mov     r9d, 256h
0x140046725  jmp     loc_140046A3C
0x14004672a  mov     rcx, [rbp+var_50]
0x14004672e  mov     rax, [rcx]
0x140046731  mov     edx, 0Bh
0x140046736  mov     word ptr [rbp+pvarg], dx
0x14004673a  mov     word ptr [rbp+pvarg+8], r13w
0x14004673f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140046743  movaps  [rbp+var_20], xmm0
0x140046747  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14004674c  movsd   [rbp+var_10], xmm1
0x140046751  lea     r8, [rbp+var_20]
0x140046755  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x14004675c  mov     rax, [rax+280h]
0x140046763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046768  mov     ebx, eax
0x14004676a  lea     rcx, [rbp+pvarg]; pvarg
0x14004676e  call    cs:__imp_VariantClear
0x140046775  nop     dword ptr [rax+rax+00h]
0x14004677a  test    ebx, ebx
0x14004677c  jns     short loc_14004678D
0x14004677e  mov     [rsp+80h+cchCount2], ebx
0x140046782  mov     r9d, 258h
0x140046788  jmp     loc_140046A40
0x14004678d  mov     rcx, [rbp+var_50]
0x140046791  mov     rax, [rcx]
0x140046794  mov     edx, 0Bh
0x140046799  mov     word ptr [rbp+pvarg], dx
0x14004679d  mov     word ptr [rbp+pvarg+8], r12w
0x1400467a2  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400467a6  movaps  [rbp+var_20], xmm0
0x1400467aa  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400467af  movsd   [rbp+var_10], xmm1
0x1400467b4  lea     r8, [rbp+var_20]
0x1400467b8  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x1400467bf  mov     rax, [rax+280h]
0x1400467c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400467cb  mov     ebx, eax
0x1400467cd  lea     rcx, [rbp+pvarg]; pvarg
0x1400467d1  call    cs:__imp_VariantClear
0x1400467d8  nop     dword ptr [rax+rax+00h]
0x1400467dd  test    ebx, ebx
0x1400467df  jns     short loc_1400467F0
0x1400467e1  mov     [rsp+80h+cchCount2], ebx
0x1400467e5  mov     r9d, 259h
0x1400467eb  jmp     loc_140046A40
0x1400467f0  mov     rcx, [rbp+var_50]
0x1400467f4  mov     rax, [rcx]
0x1400467f7  mov     edx, 0Bh
0x1400467fc  mov     word ptr [rbp+pvarg], dx
0x140046800  mov     word ptr [rbp+pvarg+8], r12w
0x140046805  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140046809  movaps  [rbp+var_20], xmm0
0x14004680d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140046812  movsd   [rbp+var_10], xmm1
0x140046817  lea     r8, [rbp+var_20]
0x14004681b  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x140046822  mov     rax, [rax+280h]
0x140046829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004682e  mov     ebx, eax
0x140046830  lea     rcx, [rbp+pvarg]; pvarg
0x140046834  call    cs:__imp_VariantClear
0x14004683b  nop     dword ptr [rax+rax+00h]
0x140046840  test    ebx, ebx
0x140046842  jns     short loc_140046853
0x140046844  mov     [rsp+80h+cchCount2], ebx
0x140046848  mov     r9d, 25Ah
0x14004684e  jmp     loc_140046A40
0x140046853  mov     rcx, [rbp+var_50]
0x140046857  mov     rax, [rcx]
0x14004685a  xor     edx, edx
0x14004685c  mov     rax, [rax+1F8h]
0x140046863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046868  mov     ebx, eax
0x14004686a  test    eax, eax
0x14004686c  jns     short loc_140046879
0x14004686e  mov     r9d, 25Fh
0x140046874  jmp     loc_140046A3C
0x140046879  mov     rcx, [rbp+var_50]
0x14004687d  mov     rax, [rcx]
0x140046880  lea     r8, [rbp+arg_10]
0x140046884  mov     rdx, r14
0x140046887  mov     rax, [rax+208h]
0x14004688e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046893  test    eax, eax
0x140046895  js      loc_140046AC4
0x14004689b  cmp     [rbp+arg_10], r12w
0x1400468a0  jz      loc_140046AC4
0x1400468a6  mov     rcx, [rbp+var_50]
0x1400468aa  mov     rax, [rcx]
0x1400468ad  lea     r8, [rbp+var_40]
0x1400468b1  mov     rdx, r15
0x1400468b4  mov     rax, [rax+128h]
0x1400468bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400468c0  mov     ebx, eax
0x1400468c2  test    eax, eax
0x1400468c4  js      loc_140046AC9
0x1400468ca  mov     rcx, [rbp+var_40]
0x1400468ce  test    rcx, rcx
0x1400468d1  jz      loc_140046B26
0x1400468d7  mov     rax, [rcx]
0x1400468da  lea     rdx, [rbp+var_48]
0x1400468de  mov     rax, [rax+88h]
0x1400468e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400468ea  mov     ebx, eax
0x1400468ec  test    eax, eax
0x1400468ee  js      loc_140046AC9
0x1400468f4  mov     rcx, [rbp+var_48]; struct IXMLDOMNamedNodeMap *
0x1400468f8  test    rcx, rcx
0x1400468fb  setz    al
0x1400468fe  test    al, al
0x140046900  jnz     loc_140046B26
0x140046906  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x14004690a  lea     rdx, aName; "NAME"
0x140046911  call    ?GetAttributeFromAttributeListAsString@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeListAsString(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x140046916  mov     ebx, eax
0x140046918  test    eax, eax
0x14004691a  jns     short loc_140046927
0x14004691c  mov     r9d, 277h
0x140046922  jmp     loc_1400469CF
0x140046927  mov     [rsp+80h+cchCount2], r13d; cchCount2
0x14004692c  lea     rax, aFilexfer; "FILEXFER"
0x140046933  mov     [rsp+80h+ppv], rax; lpString2
0x140046938  mov     r9d, r13d; cchCount1
0x14004693b  mov     rdi, [rbp+lpString1]
0x14004693f  mov     r8, rdi; lpString1
0x140046942  mov     edx, 1; dwCmpFlags
0x140046947  lea     ecx, [rdx+7Eh]; Locale
0x14004694a  call    cs:__imp_CompareStringW
0x140046951  nop     dword ptr [rax+rax+00h]
0x140046956  cmp     eax, 2
0x140046959  jnz     loc_140046AC4
0x14004695f  test    rdi, rdi
0x140046962  jz      short loc_14004698B
0x140046964  call    cs:__imp_GetProcessHeap
0x14004696b  nop     dword ptr [rax+rax+00h]
0x140046970  mov     r8, rdi; lpMem
0x140046973  xor     edx, edx; dwFlags
0x140046975  mov     rcx, rax; hHeap
0x140046978  call    cs:__imp_HeapFree
0x14004697f  nop     dword ptr [rax+rax+00h]
0x140046984  mov     rdi, r12
0x140046987  mov     [rbp+lpString1], r12
0x14004698b  mov     r8, rsi; unsigned __int16 **
0x14004698e  lea     rdx, aFilename; "FILENAME"
0x140046995  mov     rcx, [rbp+var_48]; struct IXMLDOMNamedNodeMap *
0x140046999  call    ?GetAttributeFromAttributeListAsString@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeListAsString(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x14004699e  mov     ebx, eax
0x1400469a0  test    eax, eax
0x1400469a2  jns     short loc_1400469AF
0x1400469a4  mov     r9d, 28Eh
0x1400469aa  jmp     loc_140046A3C
0x1400469af  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x1400469b3  lea     rdx, aFilesize; "FILESIZE"
0x1400469ba  mov     rcx, [rbp+var_48]; struct IXMLDOMNamedNodeMap *
0x1400469be  call    ?GetAttributeFromAttributeListAsString@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeListAsString(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x1400469c3  mov     ebx, eax
0x1400469c5  test    eax, eax
0x1400469c7  jns     short loc_1400469FB
0x1400469c9  mov     r9d, 293h; unsigned int
0x1400469cf  mov     [rsp+80h+cchCount2], eax; unsigned int
0x1400469d3  lea     rcx, aReadxmlcontrol; "ReadXMLControlBlock"
0x1400469da  mov     [rsp+80h+ppv], rcx; unsigned __int16 *
0x1400469df  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x1400469e6  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400469ed  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400469f2  mov     rdi, [rbp+lpString1]
0x1400469f6  jmp     loc_140046AC9
0x1400469fb  mov     rdi, [rbp+lpString1]
0x1400469ff  mov     rcx, rdi; String
0x140046a02  call    cs:__imp__wtoi
0x140046a09  nop     dword ptr [rax+rax+00h]
0x140046a0e  test    eax, eax
0x140046a10  js      loc_140046AC4
0x140046a16  cdqe
0x140046a18  mov     [rsi+8], rax
0x140046a1c  lea     r8, [rsi+10h]; unsigned __int16 **
0x140046a20  lea     rdx, aChannelid; "CHANNELID"
0x140046a27  mov     rcx, [rbp+var_48]; struct IXMLDOMNamedNodeMap *
0x140046a2b  call    ?GetAttributeFromAttributeListAsString@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeListAsString(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x140046a30  mov     ebx, eax
0x140046a32  test    eax, eax
0x140046a34  jns     short loc_140046A61
0x140046a36  mov     r9d, 29Fh; unsigned int
0x140046a3c  mov     [rsp+80h+cchCount2], eax; unsigned int
0x140046a40  lea     rcx, aReadxmlcontrol; "ReadXMLControlBlock"
0x140046a47  mov     [rsp+80h+ppv], rcx; unsigned __int16 *
0x140046a4c  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x140046a53  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140046a5a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140046a5f  jmp     short loc_140046AC9
0x140046a61  test    rdi, rdi
0x140046a64  jz      short loc_140046A8A
0x140046a66  call    cs:__imp_GetProcessHeap
0x140046a6d  nop     dword ptr [rax+rax+00h]
0x140046a72  mov     r8, rdi; lpMem
0x140046a75  xor     edx, edx; dwFlags
0x140046a77  mov     rcx, rax; hHeap
0x140046a7a  call    cs:__imp_HeapFree
0x140046a81  nop     dword ptr [rax+rax+00h]
0x140046a86  mov     [rbp+lpString1], r12
0x140046a8a  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x140046a8e  lea     rdx, aInternaldata; "INTERNALDATA"
0x140046a95  mov     rcx, [rbp+var_48]; struct IXMLDOMNamedNodeMap *
0x140046a99  call    ?GetAttributeFromAttributeListAsString@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeListAsString(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x140046a9e  mov     rdi, [rbp+lpString1]
0x140046aa2  test    eax, eax
0x140046aa4  js      short loc_140046ABE
0x140046aa6  mov     rcx, rdi; String
0x140046aa9  call    cs:__imp__wtoi
0x140046ab0  nop     dword ptr [rax+rax+00h]
0x140046ab5  test    eax, eax
0x140046ab7  js      short loc_140046AC4
0x140046ab9  mov     [rsi+18h], eax
0x140046abc  jmp     short loc_140046B26
0x140046abe  mov     [rsi+18h], r12d
0x140046ac2  jmp     short loc_140046B26
0x140046ac4  mov     ebx, 80004005h
0x140046ac9  mov     r14, [rsi]
0x140046acc  test    r14, r14
0x140046acf  jz      short loc_140046AF4
0x140046ad1  call    cs:__imp_GetProcessHeap
0x140046ad8  nop     dword ptr [rax+rax+00h]
0x140046add  mov     r8, r14; lpMem
0x140046ae0  xor     edx, edx; dwFlags
0x140046ae2  mov     rcx, rax; hHeap
0x140046ae5  call    cs:__imp_HeapFree
0x140046aec  nop     dword ptr [rax+rax+00h]
0x140046af1  mov     [rsi], r12
0x140046af4  mov     r14, [rsi+10h]
0x140046af8  test    r14, r14
0x140046afb  jz      short loc_140046B21
0x140046afd  call    cs:__imp_GetProcessHeap
0x140046b04  nop     dword ptr [rax+rax+00h]
0x140046b09  mov     r8, r14; lpMem
  ... truncated ...
```
