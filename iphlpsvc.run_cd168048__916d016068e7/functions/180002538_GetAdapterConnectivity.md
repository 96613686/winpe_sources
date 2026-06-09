# GetAdapterConnectivity

- ea: `0x180002538`
- end: `0x1800028cc`
- name: `GetAdapterConnectivity`
- size: `916`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022bc`
- `0x1800023e0`
- `0x180044ed0`

## callees

- `0x180002538`
- `0x1800190e0`
- `0x18004b630`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180002686`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180002686`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000289a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000289a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800025e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800025e2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000259a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000259a`
- `OLEAUT32!__imp_VariantInit` at `0x1800026ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800026ca`

## string_xrefs

- `0x1800025af`: `Get adapter's connectivity: Com initialization failed with error %u.`
- `0x180002791`: `Get adapter's connectivity: PropertyBag->Read failed with Status(%d) and Ptr(%p).`

## pseudocode

```c
__int64 __fastcall GetAdapterConnectivity(void *Source1, __int16 a2, __int64 a3, LONG *a4)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-29h] BYREF
  __int64 v22; // [rsp+38h] [rbp-21h] BYREF
  __int64 v23; // [rsp+40h] [rbp-19h] BYREF
  __int64 v24; // [rsp+48h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-1h] BYREF
  __int128 Source2; // [rsp+70h] [rbp+17h] BYREF

  ppv = 0;
  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v8 = CoInitializeEx(0, 4u);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkListManager, &ppv);
    v9 = v10;
    if ( v10 || !ppv )
    {
      EventWriteError0(0x800000, L"Get adapter's connectivity: Unable to find Network List Manager. Status(%d)", v10);
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, &v24);
      v12 = v24;
      v9 = v11;
      if ( v11 || !v24 )
      {
        EventWriteError0(
          0x800000,
          L"Get adapter's connectivity: GetNetworks failed with Status(%d) and Ptr(%p).",
          v11,
          v24);
      }
      else
      {
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 64LL))(v12, 1, &v21);
          if ( v9 || !v21 )
            break;
          Source2 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 96LL))(v21, &Source2);
          v9 = v13;
          if ( v13 )
          {
            EventWriteError0(
              0x800000,
              L"Get adapter's connectivity: GetAdapterId failed with Status(%d) and Ptr(%p).",
              v13,
              v21);
            break;
          }
          if ( RtlCompareMemory(Source1, &Source2, 0x10u) == 16 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 56LL))(v21, &v22);
            v9 = v14;
            if ( v14 || !v22 )
            {
              EventWriteError0(
                0x800000,
                L"Get adapter's connectivity: GetNetwork failed with Status(%d) and Ptr(%p).",
                v14,
                v21);
            }
            else
            {
              v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 136LL))(v22, a3);
              v9 = v15;
              if ( v15 )
              {
                EventWriteError0(
                  0x800000,
                  L"Get adapter's connectivity: GetConnectivity failed with Status(%d) and Ptr(%p).",
                  v15,
                  v22);
              }
              else
              {
                v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(v22, &IID_IPropertyBag, &v23);
                v9 = v16;
                if ( v16 )
                {
                  EventWriteError0(
                    0x800000,
                    L"Get adapter's connectivity: Network->QueryInterface failed with Status(%d) and Ptr(%p).",
                    v16,
                    v22);
                }
                else
                {
                  v17 = L"NA_InternetConnectivityV4";
                  if ( a2 != 2 )
                    v17 = L"NA_InternetConnectivityV6";
                  v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v23 + 24LL))(
                          v23,
                          v17,
                          &pvarg,
                          0);
                  v9 = v18;
                  if ( v18 )
                  {
                    EventWriteError0(
                      0x800000,
                      L"Get adapter's connectivity: PropertyBag->Read failed with Status(%d) and Ptr(%p).",
                      v18,
                      v22);
                  }
                  else
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                    v19 = v22;
                    *a4 = pvarg.lVal;
                    v23 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                    v22 = 0;
                  }
                }
              }
            }
            break;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          v12 = v24;
          v21 = 0;
        }
      }
    }
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    CoUninitialize();
  }
  else
  {
    EventWriteError0(
      0x800000,
      L"Get adapter's connectivity: Com initialization failed with error %u.",
      (unsigned int)v8);
  }
  return v9;
}

```

## disassembly

```asm
0x180002538  mov     [rsp-8+arg_8], rbx
0x18000253d  push    rbp
0x18000253e  push    rsi
0x18000253f  push    rdi
0x180002540  push    r14
0x180002542  push    r15
0x180002544  lea     rbp, [rsp-37h]
0x180002549  sub     rsp, 90h
0x180002550  mov     rax, cs:__security_cookie
0x180002557  xor     rax, rsp
0x18000255a  mov     [rbp+57h+var_30], rax
0x18000255e  movzx   r14d, dx
0x180002562  mov     [rbp+57h+var_60], 0
0x18000256a  mov     rdi, rcx
0x18000256d  mov     [rbp+57h+var_68], 0
0x180002575  mov     edx, 4; dwCoInit
0x18000257a  mov     [rbp+57h+var_80], 0
0x180002582  xor     ecx, ecx; pvReserved
0x180002584  mov     [rbp+57h+var_78], 0
0x18000258c  mov     r15, r9
0x18000258f  mov     [rbp+57h+var_70], 0
0x180002597  mov     rsi, r8
0x18000259a  call    cs:__imp_CoInitializeEx
0x1800025a1  nop     dword ptr [rax+rax+00h]
0x1800025a6  mov     ebx, eax
0x1800025a8  test    eax, eax
0x1800025aa  jns     short loc_1800025C5
0x1800025ac  mov     r8d, eax
0x1800025af  lea     rdx, aGetAdapterSCon_3; "Get adapter's connectivity: Com initial"...
0x1800025b6  mov     ecx, 800000h
0x1800025bb  call    EventWriteError0
0x1800025c0  jmp     loc_1800028A6
0x1800025c5  xor     edx, edx; pUnkOuter
0x1800025c7  lea     rax, [rbp+57h+var_60]
0x1800025cb  lea     r9, IID_INetworkListManager; riid
0x1800025d2  mov     [rsp+0B0h+ppv], rax; ppv
0x1800025d7  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800025de  lea     r8d, [rdx+17h]; dwClsContext
0x1800025e2  call    cs:__imp_CoCreateInstance
0x1800025e9  nop     dword ptr [rax+rax+00h]
0x1800025ee  mov     ebx, eax
0x1800025f0  test    eax, eax
0x1800025f2  jnz     loc_180002805
0x1800025f8  mov     rcx, [rbp+57h+var_60]
0x1800025fc  test    rcx, rcx
0x1800025ff  jz      loc_180002805
0x180002605  mov     rax, [rcx]
0x180002608  lea     rdx, [rbp+57h+var_68]
0x18000260c  mov     rax, [rax+48h]
0x180002610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002615  mov     rcx, [rbp+57h+var_68]
0x180002619  mov     ebx, eax
0x18000261b  test    eax, eax
0x18000261d  jnz     loc_1800027EC
0x180002623  test    rcx, rcx
0x180002626  jz      loc_1800027EC
0x18000262c  mov     rax, [rcx]
0x18000262f  lea     r8, [rbp+57h+var_80]
0x180002633  xor     r9d, r9d
0x180002636  mov     rax, [rax+40h]
0x18000263a  lea     edx, [r9+1]
0x18000263e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002643  mov     ebx, eax
0x180002645  test    eax, eax
0x180002647  jnz     loc_180002819
0x18000264d  mov     rcx, [rbp+57h+var_80]
0x180002651  test    rcx, rcx
0x180002654  jz      loc_180002819
0x18000265a  xorps   xmm0, xmm0
0x18000265d  lea     rdx, [rbp+57h+Source2]
0x180002661  movups  [rbp+57h+Source2], xmm0
0x180002665  mov     rax, [rcx]
0x180002668  mov     rax, [rax+60h]
0x18000266c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002671  mov     ebx, eax
0x180002673  test    eax, eax
0x180002675  jnz     loc_1800027DF
0x18000267b  lea     r8d, [rax+10h]; Length
0x18000267f  mov     rcx, rdi; Source1
0x180002682  lea     rdx, [rbp+57h+Source2]; Source2
0x180002686  call    cs:__imp_RtlCompareMemory
0x18000268d  nop     dword ptr [rax+rax+00h]
0x180002692  cmp     rax, 10h
0x180002696  jz      short loc_1800026B9
0x180002698  mov     rcx, [rbp+57h+var_80]
0x18000269c  mov     rax, [rcx]
0x18000269f  mov     rax, [rax+10h]
0x1800026a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a8  mov     rcx, [rbp+57h+var_68]
0x1800026ac  mov     [rbp+57h+var_80], 0
0x1800026b4  jmp     loc_18000262C
0x1800026b9  xorps   xmm0, xmm0
0x1800026bc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800026c0  xor     eax, eax
0x1800026c2  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800026c6  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800026ca  call    cs:__imp_VariantInit
0x1800026d1  nop     dword ptr [rax+rax+00h]
0x1800026d6  mov     rcx, [rbp+57h+var_80]
0x1800026da  lea     rdx, [rbp+57h+var_78]
0x1800026de  mov     rax, [rcx]
0x1800026e1  mov     rax, [rax+38h]
0x1800026e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ea  mov     ebx, eax
0x1800026ec  test    eax, eax
0x1800026ee  jnz     loc_1800027D2
0x1800026f4  mov     rcx, [rbp+57h+var_78]
0x1800026f8  test    rcx, rcx
0x1800026fb  jz      loc_1800027D2
0x180002701  mov     rax, [rcx]
0x180002704  mov     rdx, rsi
0x180002707  mov     rax, [rax+88h]
0x18000270e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002713  mov     ebx, eax
0x180002715  test    eax, eax
0x180002717  jz      short loc_180002729
0x180002719  mov     r9, [rbp+57h+var_78]
0x18000271d  lea     rdx, aGetAdapterSCon_1; "Get adapter's connectivity: GetConnecti"...
0x180002724  jmp     loc_1800027F6
0x180002729  mov     rcx, [rbp+57h+var_78]
0x18000272d  lea     r8, [rbp+57h+var_70]
0x180002731  lea     rdx, IID_IPropertyBag
0x180002738  mov     rax, [rcx]
0x18000273b  mov     rax, [rax]
0x18000273e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002743  mov     ebx, eax
0x180002745  test    eax, eax
0x180002747  jz      short loc_180002759
0x180002749  mov     r9, [rbp+57h+var_78]
0x18000274d  lea     rdx, aGetAdapterSCon; "Get adapter's connectivity: Network->Qu"...
0x180002754  jmp     loc_1800027F6
0x180002759  mov     rcx, [rbp+57h+var_70]
0x18000275d  lea     r8, aNaInternetconn; "NA_InternetConnectivityV6"
0x180002764  cmp     r14w, 2
0x180002769  lea     rdx, aNaInternetconn_0; "NA_InternetConnectivityV4"
0x180002770  cmovnz  rdx, r8
0x180002774  xor     r9d, r9d
0x180002777  mov     rax, [rcx]
0x18000277a  lea     r8, [rbp+57h+pvarg]
0x18000277e  mov     rax, [rax+18h]
0x180002782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002787  mov     ebx, eax
0x180002789  test    eax, eax
0x18000278b  jz      short loc_18000279A
0x18000278d  mov     r9, [rbp+57h+var_78]
0x180002791  lea     rdx, aGetAdapterSCon_0; "Get adapter's connectivity: PropertyBag"...
0x180002798  jmp     short loc_1800027F6
0x18000279a  mov     rcx, [rbp+57h+var_70]
0x18000279e  mov     rax, [rcx]
0x1800027a1  mov     rax, [rax+10h]
0x1800027a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027aa  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x1800027ad  mov     rcx, [rbp+57h+var_78]
0x1800027b1  mov     [r15], eax
0x1800027b4  mov     [rbp+57h+var_70], 0
0x1800027bc  mov     rax, [rcx]
0x1800027bf  mov     rax, [rax+10h]
0x1800027c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c8  mov     [rbp+57h+var_78], 0
0x1800027d0  jmp     short loc_180002819
0x1800027d2  mov     r9, [rbp+57h+var_80]
0x1800027d6  lea     rdx, aGetAdapterSCon_5; "Get adapter's connectivity: GetNetwork "...
0x1800027dd  jmp     short loc_1800027F6
0x1800027df  mov     r9, [rbp+57h+var_80]
0x1800027e3  lea     rdx, aGetAdapterSCon_2; "Get adapter's connectivity: GetAdapterI"...
0x1800027ea  jmp     short loc_1800027F6
0x1800027ec  mov     r9, rcx
0x1800027ef  lea     rdx, aGetAdapterSCon_4; "Get adapter's connectivity: GetNetworks"...
0x1800027f6  mov     r8d, eax
0x1800027f9  mov     ecx, 800000h
0x1800027fe  call    EventWriteError0
0x180002803  jmp     short loc_180002819
0x180002805  mov     r8d, eax
0x180002808  lea     rdx, aGetAdapterSCon_6; "Get adapter's connectivity: Unable to f"...
0x18000280f  mov     ecx, 800000h
0x180002814  call    EventWriteError0
0x180002819  mov     rcx, [rbp+57h+var_70]
0x18000281d  test    rcx, rcx
0x180002820  jz      short loc_18000282E
0x180002822  mov     rax, [rcx]
0x180002825  mov     rax, [rax+10h]
0x180002829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282e  mov     rcx, [rbp+57h+var_78]
0x180002832  test    rcx, rcx
0x180002835  jz      short loc_180002843
0x180002837  mov     rax, [rcx]
0x18000283a  mov     rax, [rax+10h]
0x18000283e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002843  mov     rcx, [rbp+57h+var_80]
0x180002847  test    rcx, rcx
0x18000284a  jz      short loc_180002860
0x18000284c  mov     rax, [rcx]
0x18000284f  mov     rax, [rax+10h]
0x180002853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002858  mov     [rbp+57h+var_80], 0
0x180002860  mov     rcx, [rbp+57h+var_68]
0x180002864  test    rcx, rcx
0x180002867  jz      short loc_18000287D
0x180002869  mov     rax, [rcx]
0x18000286c  mov     rax, [rax+10h]
0x180002870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002875  mov     [rbp+57h+var_68], 0
0x18000287d  mov     rcx, [rbp+57h+var_60]
0x180002881  test    rcx, rcx
0x180002884  jz      short loc_18000289A
0x180002886  mov     rax, [rcx]
0x180002889  mov     rax, [rax+10h]
0x18000288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002892  mov     [rbp+57h+var_60], 0
0x18000289a  call    cs:__imp_CoUninitialize
0x1800028a1  nop     dword ptr [rax+rax+00h]
0x1800028a6  mov     eax, ebx
0x1800028a8  mov     rcx, [rbp+57h+var_30]
0x1800028ac  xor     rcx, rsp; StackCookie
0x1800028af  call    __security_check_cookie
0x1800028b4  mov     rbx, [rsp+0B0h+arg_8]
0x1800028bc  add     rsp, 90h
0x1800028c3  pop     r15
0x1800028c5  pop     r14
0x1800028c7  pop     rdi
0x1800028c8  pop     rsi
0x1800028c9  pop     rbp
0x1800028ca  retn
```
