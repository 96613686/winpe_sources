# Package::UpdateRootCausesWithVerifyXml(ushort *)

- ea: `0x140059278`
- end: `0x14005969d`
- name: `?UpdateRootCausesWithVerifyXml@Package@@QEAAJPEAG@Z`
- size: `1061`
- prototype: `int(Package *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x140055a60`

## callees

- `0x140020420`
- `0x140059278`
- `0x14005ab14`
- `0x14005b038`
- `0x14005b190`
- `0x14005b6e4`
- `0x140063010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14005947e`
- `msvcrt!_wcsicmp` at `0x1400594a0`
- `msvcrt!_wcsicmp` at `0x1400594c2`
- `msvcrt!_wcsicmp` at `0x14005947e`
- `msvcrt!_wcsicmp` at `0x1400594a0`
- `msvcrt!_wcsicmp` at `0x1400594c2`
- `OLEAUT32!__imp_SysFreeString` at `0x140059413`
- `OLEAUT32!__imp_SysFreeString` at `0x1400594f8`
- `OLEAUT32!__imp_SysFreeString` at `0x140059511`
- `OLEAUT32!__imp_SysFreeString` at `0x14005952a`
- `OLEAUT32!__imp_SysFreeString` at `0x14005960c`
- `OLEAUT32!__imp_SysFreeString` at `0x140059625`
- `OLEAUT32!__imp_SysFreeString` at `0x14005963e`
- `OLEAUT32!__imp_SysFreeString` at `0x140059413`
- `OLEAUT32!__imp_SysFreeString` at `0x1400594f8`
- `OLEAUT32!__imp_SysFreeString` at `0x140059511`
- `OLEAUT32!__imp_SysFreeString` at `0x14005952a`
- `OLEAUT32!__imp_SysFreeString` at `0x14005960c`
- `OLEAUT32!__imp_SysFreeString` at `0x140059625`
- `OLEAUT32!__imp_SysFreeString` at `0x14005963e`

## string_xrefs

- `0x1400592eb`: `Package::UpdateRootCausesWithVerifyXml`
- `0x140059336`: `Package::UpdateRootCausesWithVerifyXml`
- `0x14005957f`: `Package::UpdateRootCausesWithVerifyXml`
- `0x1400595be`: `Package::UpdateRootCausesWithVerifyXml`
- `0x1400595eb`: `Package::UpdateRootCausesWithVerifyXml`

## pseudocode

```c
__int64 __fastcall Package::UpdateRootCausesWithVerifyXml(Package *this, unsigned __int16 *a2)
{
  unsigned int v2; // r12d
  struct IXMLDOMDocument2 *v3; // r15
  struct IXMLDOMNodeList *v4; // r14
  struct IXMLDOMNode *v5; // rsi
  unsigned int v6; // ebx
  int v7; // r9d
  int v8; // eax
  int Nodes; // eax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r13d
  int v13; // eax
  int NodeText; // eax
  int v15; // eax
  _DWORD *v16; // r13
  int v17; // eax
  BSTR v18; // rax
  int v19; // ecx
  int v20; // edx
  int v21; // eax
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-18h] BYREF
  BSTR v25; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMNode *v26; // [rsp+48h] [rbp-8h] BYREF
  int v28; // [rsp+98h] [rbp+48h] BYREF
  struct IXMLDOMDocument2 *v29; // [rsp+A0h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v30; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  v29 = 0;
  v3 = 0;
  v30 = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v28 = 0;
  v25 = 0;
  bstrString = 0;
  String1 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 1344;
LABEL_48:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", v7, v6);
    goto LABEL_49;
  }
  v8 = MetXmlCreate(a2, (LPVOID *)&v29);
  v6 = v8;
  if ( v8 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1350, v8);
    v3 = v29;
    goto LABEL_49;
  }
  v3 = v29;
  Nodes = MetXmlGetNodes(L"/Rootcauses/Rootcause", v29, 0, &v30);
  v6 = Nodes;
  if ( Nodes < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1353, Nodes);
    v4 = v30;
    goto LABEL_49;
  }
  v4 = v30;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v30->lpVtbl->get_length)(v30, &v28);
  v6 = v10;
  if ( v10 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1356, v10);
    goto LABEL_49;
  }
  v11 = v28;
  LODWORD(v30) = v28;
  if ( v28 < 0 )
  {
    v6 = -2147024362;
    v7 = 1359;
    goto LABEL_48;
  }
  v12 = 0;
  v6 = 0;
  while ( 1 )
  {
    LODWORD(v29) = v12;
    if ( v12 >= v11 )
      break;
    v13 = MetXmlNextNode(v4, &v26);
    v6 = v13;
    if ( v13 < 0 )
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1369, v13);
      v5 = v26;
      break;
    }
    v5 = v26;
    NodeText = MetXmlGetNodeText(L"./ID", 0, v26, &v25);
    v6 = NodeText;
    if ( NodeText < 0 )
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1372, NodeText);
      break;
    }
    v15 = MetXmlGetNodeText(L"./Status", 0, v5, &String1);
    v6 = v15;
    if ( v15 < 0 )
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1375, v15);
      break;
    }
    while ( v2 < *((_DWORD *)this + 16) )
    {
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v16 = *(_DWORD **)(*((_QWORD *)this + 7) + 8LL * v2);
      v17 = (*(__int64 (__fastcall **)(_DWORD *, BSTR *))(*(_QWORD *)v16 + 48LL))(v16, &bstrString);
      v6 = v17;
      if ( v17 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::UpdateRootCausesWithVerifyXml", 1386, v17);
        goto LABEL_49;
      }
      v18 = v25;
      do
      {
        v19 = *(BSTR)((char *)v18 + (char *)bstrString - (char *)v25);
        v20 = *v18 - v19;
        if ( v20 )
          break;
        ++v18;
      }
      while ( v19 );
      if ( !v20 )
      {
        if ( _wcsicmp(String1, L"Fixed") )
        {
          if ( _wcsicmp(String1, L"Not Fixed") )
          {
            if ( _wcsicmp(String1, L"Detected") )
            {
              v6 = -2147418113;
              SdpDebugPrint(
                1u,
                "Met ERROR: %s:%d - hr = 0x%08X\n",
                "Package::UpdateRootCausesWithVerifyXml",
                1407,
                -2147418113);
              goto LABEL_49;
            }
            v21 = 2;
          }
          else
          {
            v21 = 6;
          }
        }
        else
        {
          v21 = 5;
        }
        if ( v16[16] != 3 )
          v16[16] = v21;
        v6 = 0;
      }
      ++v2;
    }
    v2 = 0;
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v25 )
    {
      SysFreeString(v25);
      v25 = 0;
    }
    if ( String1 )
    {
      SysFreeString(String1);
      String1 = 0;
    }
    if ( v5 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
      v5 = 0;
      v26 = 0;
    }
    v11 = (unsigned int)v30;
    v12 = (_DWORD)v29 + 1;
  }
LABEL_49:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v25 )
  {
    SysFreeString(v25);
    v25 = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v4->lpVtbl->Release)(v4);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
  return v6;
}

```

## disassembly

```asm
0x140059278  mov     [rsp-38h+arg_0], rcx
0x14005927d  push    rbp
0x14005927e  push    rbx
0x14005927f  push    rsi
0x140059280  push    r12
0x140059282  push    r13
0x140059284  push    r14
0x140059286  push    r15
0x140059288  mov     rbp, rsp
0x14005928b  sub     rsp, 50h
0x14005928f  xor     r12d, r12d
0x140059292  mov     rax, rdx
0x140059295  mov     [rbp+arg_10], r12
0x140059299  mov     r15d, r12d
0x14005929c  mov     [rbp+arg_18], r12
0x1400592a0  mov     r14d, r12d
0x1400592a3  mov     [rbp+var_8], r12
0x1400592a7  mov     esi, r12d
0x1400592aa  mov     [rbp+arg_8], r12d
0x1400592ae  mov     [rbp+var_10], r12
0x1400592b2  mov     [rbp+bstrString], r12
0x1400592b6  mov     [rbp+String1], r12
0x1400592ba  test    rdx, rdx
0x1400592bd  jnz     short loc_1400592CF
0x1400592bf  mov     ebx, 80070057h
0x1400592c4  mov     r9d, 540h
0x1400592ca  jmp     loc_1400595E7
0x1400592cf  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x1400592d3  mov     rcx, rax; psz
0x1400592d6  call    ?MetXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; MetXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1400592db  mov     ebx, eax
0x1400592dd  test    eax, eax
0x1400592df  jns     short loc_14005930C
0x1400592e1  mov     r9d, 546h
0x1400592e7  mov     [rsp+50h+var_30], eax
0x1400592eb  lea     r8, aPackageUpdater_0; "Package::UpdateRootCausesWithVerifyXml"
0x1400592f2  mov     ecx, 1; Level
0x1400592f7  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400592fe  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140059303  mov     r15, [rbp+arg_10]
0x140059307  jmp     loc_140059603
0x14005930c  mov     r15, [rbp+arg_10]
0x140059310  lea     r9, [rbp+arg_18]; struct IXMLDOMNodeList **
0x140059314  mov     rdx, r15; struct IXMLDOMDocument2 *
0x140059317  lea     rcx, aRootcausesRoot; "/Rootcauses/Rootcause"
0x14005931e  xor     r8d, r8d; struct IXMLDOMNode *
0x140059321  call    ?MetXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; MetXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x140059326  mov     ebx, eax
0x140059328  test    eax, eax
0x14005932a  jns     short loc_140059357
0x14005932c  mov     r9d, 549h
0x140059332  mov     [rsp+50h+var_30], eax
0x140059336  lea     r8, aPackageUpdater_0; "Package::UpdateRootCausesWithVerifyXml"
0x14005933d  mov     ecx, 1; Level
0x140059342  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140059349  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005934e  mov     r14, [rbp+arg_18]
0x140059352  jmp     loc_140059603
0x140059357  mov     r14, [rbp+arg_18]
0x14005935b  lea     rdx, [rbp+arg_8]
0x14005935f  mov     rcx, r14
0x140059362  mov     rax, [r14]
0x140059365  mov     rax, [rax+40h]
0x140059369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005936e  mov     ebx, eax
0x140059370  test    eax, eax
0x140059372  jns     short loc_140059383
0x140059374  mov     [rsp+50h+var_30], eax
0x140059378  mov     r9d, 54Ch
0x14005937e  jmp     loc_1400595EB
0x140059383  mov     eax, [rbp+arg_8]
0x140059386  mov     dword ptr [rbp+arg_18], eax
0x140059389  test    eax, eax
0x14005938b  js      loc_1400595DC
0x140059391  mov     r13d, r12d
0x140059394  mov     ebx, r12d
0x140059397  mov     dword ptr [rbp+arg_10], r13d
0x14005939b  cmp     r13d, eax
0x14005939e  jnb     loc_140059603
0x1400593a4  lea     rdx, [rbp+var_8]; struct IXMLDOMNode **
0x1400593a8  mov     rcx, r14; struct IXMLDOMNodeList *
0x1400593ab  call    ?MetXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; MetXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1400593b0  mov     ebx, eax
0x1400593b2  test    eax, eax
0x1400593b4  js      loc_1400595B4
0x1400593ba  mov     rsi, [rbp+var_8]
0x1400593be  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1400593c2  mov     r8, rsi; struct IXMLDOMNode *
0x1400593c5  lea     rcx, aId_2; "./ID"
0x1400593cc  xor     edx, edx; struct IXMLDOMDocument2 *
0x1400593ce  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x1400593d3  mov     ebx, eax
0x1400593d5  test    eax, eax
0x1400593d7  js      loc_1400595A8
0x1400593dd  lea     r9, [rbp+String1]; unsigned __int16 **
0x1400593e1  mov     r8, rsi; struct IXMLDOMNode *
0x1400593e4  xor     edx, edx; struct IXMLDOMDocument2 *
0x1400593e6  lea     rcx, aStatus; "./Status"
0x1400593ed  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x1400593f2  mov     ebx, eax
0x1400593f4  test    eax, eax
0x1400593f6  js      loc_14005959C
0x1400593fc  mov     r13, [rbp+arg_0]
0x140059400  mov     rcx, [rbp+bstrString]; bstrString
0x140059404  cmp     r12d, [r13+40h]
0x140059408  jnb     loc_1400594F0
0x14005940e  test    rcx, rcx
0x140059411  jz      short loc_140059427
0x140059413  call    cs:__imp_SysFreeString
0x14005941a  nop     dword ptr [rax+rax+00h]
0x14005941f  mov     [rbp+bstrString], 0
0x140059427  mov     rax, [r13+38h]
0x14005942b  lea     rdx, [rbp+bstrString]
0x14005942f  mov     ecx, r12d
0x140059432  mov     r13, [rax+rcx*8]
0x140059436  mov     rcx, r13
0x140059439  mov     rax, [r13+0]
0x14005943d  mov     rax, [rax+30h]
0x140059441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059446  mov     ebx, eax
0x140059448  test    eax, eax
0x14005944a  js      loc_140059575
0x140059450  mov     rax, [rbp+var_10]
0x140059454  mov     r8, [rbp+bstrString]
0x140059458  sub     r8, rax
0x14005945b  movzx   edx, word ptr [rax]
0x14005945e  movzx   ecx, word ptr [rax+r8]
0x140059463  sub     edx, ecx
0x140059465  jnz     short loc_14005946F
0x140059467  add     rax, 2
0x14005946b  test    ecx, ecx
0x14005946d  jnz     short loc_14005945B
0x14005946f  test    edx, edx
0x140059471  jnz     short loc_1400594E8
0x140059473  mov     rcx, [rbp+String1]; String1
0x140059477  lea     rdx, aFixed; "Fixed"
0x14005947e  call    cs:__imp__wcsicmp
0x140059485  nop     dword ptr [rax+rax+00h]
0x14005948a  test    eax, eax
0x14005948c  jnz     short loc_140059495
0x14005948e  mov     eax, 5
0x140059493  jmp     short loc_1400594DB
0x140059495  mov     rcx, [rbp+String1]; String1
0x140059499  lea     rdx, aNotFixed; "Not Fixed"
0x1400594a0  call    cs:__imp__wcsicmp
0x1400594a7  nop     dword ptr [rax+rax+00h]
0x1400594ac  test    eax, eax
0x1400594ae  jnz     short loc_1400594B7
0x1400594b0  mov     eax, 6
0x1400594b5  jmp     short loc_1400594DB
0x1400594b7  mov     rcx, [rbp+String1]; String1
0x1400594bb  lea     rdx, aDetected; "Detected"
0x1400594c2  call    cs:__imp__wcsicmp
0x1400594c9  nop     dword ptr [rax+rax+00h]
0x1400594ce  test    eax, eax
0x1400594d0  jnz     loc_140059564
0x1400594d6  mov     eax, 2
0x1400594db  cmp     dword ptr [r13+40h], 3
0x1400594e0  jz      short loc_1400594E6
0x1400594e2  mov     [r13+40h], eax
0x1400594e6  xor     ebx, ebx
0x1400594e8  inc     r12d
0x1400594eb  jmp     loc_1400593FC
0x1400594f0  xor     r12d, r12d
0x1400594f3  test    rcx, rcx
0x1400594f6  jz      short loc_140059508
0x1400594f8  call    cs:__imp_SysFreeString
0x1400594ff  nop     dword ptr [rax+rax+00h]
0x140059504  mov     [rbp+bstrString], r12
0x140059508  mov     rcx, [rbp+var_10]; bstrString
0x14005950c  test    rcx, rcx
0x14005950f  jz      short loc_140059521
0x140059511  call    cs:__imp_SysFreeString
0x140059518  nop     dword ptr [rax+rax+00h]
0x14005951d  mov     [rbp+var_10], r12
0x140059521  mov     rcx, [rbp+String1]; bstrString
0x140059525  test    rcx, rcx
0x140059528  jz      short loc_14005953A
0x14005952a  call    cs:__imp_SysFreeString
0x140059531  nop     dword ptr [rax+rax+00h]
0x140059536  mov     [rbp+String1], r12
0x14005953a  test    rsi, rsi
0x14005953d  jz      short loc_140059555
0x14005953f  mov     rax, [rsi]
0x140059542  mov     rcx, rsi
0x140059545  mov     rax, [rax+10h]
0x140059549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005954e  mov     rsi, r12
0x140059551  mov     [rbp+var_8], r12
0x140059555  mov     r13d, dword ptr [rbp+arg_10]
0x140059559  mov     eax, dword ptr [rbp+arg_18]
0x14005955c  inc     r13d
0x14005955f  jmp     loc_140059397
0x140059564  mov     ebx, 8000FFFFh
0x140059569  mov     r9d, 57Fh
0x14005956f  mov     [rsp+50h+var_30], ebx
0x140059573  jmp     short loc_14005957F
0x140059575  mov     [rsp+50h+var_30], eax
0x140059579  mov     r9d, 56Ah
0x14005957f  lea     r8, aPackageUpdater_0; "Package::UpdateRootCausesWithVerifyXml"
0x140059586  mov     ecx, 1; Level
0x14005958b  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140059592  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140059597  xor     r12d, r12d
0x14005959a  jmp     short loc_140059603
0x14005959c  mov     [rsp+50h+var_30], eax
0x1400595a0  mov     r9d, 55Fh
0x1400595a6  jmp     short loc_1400595EB
0x1400595a8  mov     [rsp+50h+var_30], eax
0x1400595ac  mov     r9d, 55Ch
0x1400595b2  jmp     short loc_1400595EB
0x1400595b4  mov     r9d, 559h
0x1400595ba  mov     [rsp+50h+var_30], eax
0x1400595be  lea     r8, aPackageUpdater_0; "Package::UpdateRootCausesWithVerifyXml"
0x1400595c5  mov     ecx, 1; Level
0x1400595ca  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400595d1  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400595d6  mov     rsi, [rbp+var_8]
0x1400595da  jmp     short loc_140059603
0x1400595dc  mov     ebx, 80070216h
0x1400595e1  mov     r9d, 54Fh
0x1400595e7  mov     [rsp+50h+var_30], ebx
0x1400595eb  lea     r8, aPackageUpdater_0; "Package::UpdateRootCausesWithVerifyXml"
0x1400595f2  mov     ecx, 1; Level
0x1400595f7  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400595fe  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140059603  mov     rcx, [rbp+bstrString]; bstrString
0x140059607  test    rcx, rcx
0x14005960a  jz      short loc_14005961C
0x14005960c  call    cs:__imp_SysFreeString
0x140059613  nop     dword ptr [rax+rax+00h]
0x140059618  mov     [rbp+bstrString], r12
0x14005961c  mov     rcx, [rbp+var_10]; bstrString
0x140059620  test    rcx, rcx
0x140059623  jz      short loc_140059635
0x140059625  call    cs:__imp_SysFreeString
0x14005962c  nop     dword ptr [rax+rax+00h]
0x140059631  mov     [rbp+var_10], r12
0x140059635  mov     rcx, [rbp+String1]; bstrString
0x140059639  test    rcx, rcx
0x14005963c  jz      short loc_14005964E
0x14005963e  call    cs:__imp_SysFreeString
0x140059645  nop     dword ptr [rax+rax+00h]
0x14005964a  mov     [rbp+String1], r12
0x14005964e  test    rsi, rsi
0x140059651  jz      short loc_140059662
0x140059653  mov     rax, [rsi]
0x140059656  mov     rcx, rsi
0x140059659  mov     rax, [rax+10h]
0x14005965d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059662  test    r14, r14
0x140059665  jz      short loc_140059676
0x140059667  mov     rax, [r14]
0x14005966a  mov     rcx, r14
0x14005966d  mov     rax, [rax+10h]
0x140059671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059676  test    r15, r15
0x140059679  jz      short loc_14005968A
0x14005967b  mov     rax, [r15]
0x14005967e  mov     rcx, r15
0x140059681  mov     rax, [rax+10h]
0x140059685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005968a  mov     eax, ebx
0x14005968c  add     rsp, 50h
0x140059690  pop     r15
0x140059692  pop     r14
0x140059694  pop     r13
0x140059696  pop     r12
0x140059698  pop     rsi
0x140059699  pop     rbx
0x14005969a  pop     rbp
0x14005969b  retn
```
