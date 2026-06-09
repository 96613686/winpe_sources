# GetAdapterConnectivity

- ea: `0x180002548`
- end: `0x1800028dc`
- name: `GetAdapterConnectivity`
- size: `916`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022cc`
- `0x1800023f0`
- `0x180044e90`

## callees

- `0x180002548`
- `0x1800190f0`
- `0x18004b5f0`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180002696`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180002696`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800028aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800028aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800025f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800025f2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800025aa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800025aa`
- `OLEAUT32!__imp_VariantInit` at `0x1800026da`
- `OLEAUT32!__imp_VariantInit` at `0x1800026da`

## string_xrefs

- `0x1800025bf`: `Get adapter's connectivity: Com initialization failed with error %u.`
- `0x1800027a1`: `Get adapter's connectivity: PropertyBag->Read failed with Status(%d) and Ptr(%p).`

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
0x180002548  mov     [rsp-8+arg_8], rbx
0x18000254d  push    rbp
0x18000254e  push    rsi
0x18000254f  push    rdi
0x180002550  push    r14
0x180002552  push    r15
0x180002554  lea     rbp, [rsp-37h]
0x180002559  sub     rsp, 90h
0x180002560  mov     rax, cs:__security_cookie
0x180002567  xor     rax, rsp
0x18000256a  mov     [rbp+57h+var_30], rax
0x18000256e  movzx   r14d, dx
0x180002572  mov     [rbp+57h+var_60], 0
0x18000257a  mov     rdi, rcx
0x18000257d  mov     [rbp+57h+var_68], 0
0x180002585  mov     edx, 4; dwCoInit
0x18000258a  mov     [rbp+57h+var_80], 0
0x180002592  xor     ecx, ecx; pvReserved
0x180002594  mov     [rbp+57h+var_78], 0
0x18000259c  mov     r15, r9
0x18000259f  mov     [rbp+57h+var_70], 0
0x1800025a7  mov     rsi, r8
0x1800025aa  call    cs:__imp_CoInitializeEx
0x1800025b1  nop     dword ptr [rax+rax+00h]
0x1800025b6  mov     ebx, eax
0x1800025b8  test    eax, eax
0x1800025ba  jns     short loc_1800025D5
0x1800025bc  mov     r8d, eax
0x1800025bf  lea     rdx, aGetAdapterSCon_3; "Get adapter's connectivity: Com initial"...
0x1800025c6  mov     ecx, 800000h
0x1800025cb  call    EventWriteError0
0x1800025d0  jmp     loc_1800028B6
0x1800025d5  xor     edx, edx; pUnkOuter
0x1800025d7  lea     rax, [rbp+57h+var_60]
0x1800025db  lea     r9, IID_INetworkListManager; riid
0x1800025e2  mov     [rsp+0B0h+ppv], rax; ppv
0x1800025e7  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800025ee  lea     r8d, [rdx+17h]; dwClsContext
0x1800025f2  call    cs:__imp_CoCreateInstance
0x1800025f9  nop     dword ptr [rax+rax+00h]
0x1800025fe  mov     ebx, eax
0x180002600  test    eax, eax
0x180002602  jnz     loc_180002815
0x180002608  mov     rcx, [rbp+57h+var_60]
0x18000260c  test    rcx, rcx
0x18000260f  jz      loc_180002815
0x180002615  mov     rax, [rcx]
0x180002618  lea     rdx, [rbp+57h+var_68]
0x18000261c  mov     rax, [rax+48h]
0x180002620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002625  mov     rcx, [rbp+57h+var_68]
0x180002629  mov     ebx, eax
0x18000262b  test    eax, eax
0x18000262d  jnz     loc_1800027FC
0x180002633  test    rcx, rcx
0x180002636  jz      loc_1800027FC
0x18000263c  mov     rax, [rcx]
0x18000263f  lea     r8, [rbp+57h+var_80]
0x180002643  xor     r9d, r9d
0x180002646  mov     rax, [rax+40h]
0x18000264a  lea     edx, [r9+1]
0x18000264e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002653  mov     ebx, eax
0x180002655  test    eax, eax
0x180002657  jnz     loc_180002829
0x18000265d  mov     rcx, [rbp+57h+var_80]
0x180002661  test    rcx, rcx
0x180002664  jz      loc_180002829
0x18000266a  xorps   xmm0, xmm0
0x18000266d  lea     rdx, [rbp+57h+Source2]
0x180002671  movups  [rbp+57h+Source2], xmm0
0x180002675  mov     rax, [rcx]
0x180002678  mov     rax, [rax+60h]
0x18000267c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002681  mov     ebx, eax
0x180002683  test    eax, eax
0x180002685  jnz     loc_1800027EF
0x18000268b  lea     r8d, [rax+10h]; Length
0x18000268f  mov     rcx, rdi; Source1
0x180002692  lea     rdx, [rbp+57h+Source2]; Source2
0x180002696  call    cs:__imp_RtlCompareMemory
0x18000269d  nop     dword ptr [rax+rax+00h]
0x1800026a2  cmp     rax, 10h
0x1800026a6  jz      short loc_1800026C9
0x1800026a8  mov     rcx, [rbp+57h+var_80]
0x1800026ac  mov     rax, [rcx]
0x1800026af  mov     rax, [rax+10h]
0x1800026b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026b8  mov     rcx, [rbp+57h+var_68]
0x1800026bc  mov     [rbp+57h+var_80], 0
0x1800026c4  jmp     loc_18000263C
0x1800026c9  xorps   xmm0, xmm0
0x1800026cc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800026d0  xor     eax, eax
0x1800026d2  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800026d6  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800026da  call    cs:__imp_VariantInit
0x1800026e1  nop     dword ptr [rax+rax+00h]
0x1800026e6  mov     rcx, [rbp+57h+var_80]
0x1800026ea  lea     rdx, [rbp+57h+var_78]
0x1800026ee  mov     rax, [rcx]
0x1800026f1  mov     rax, [rax+38h]
0x1800026f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026fa  mov     ebx, eax
0x1800026fc  test    eax, eax
0x1800026fe  jnz     loc_1800027E2
0x180002704  mov     rcx, [rbp+57h+var_78]
0x180002708  test    rcx, rcx
0x18000270b  jz      loc_1800027E2
0x180002711  mov     rax, [rcx]
0x180002714  mov     rdx, rsi
0x180002717  mov     rax, [rax+88h]
0x18000271e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002723  mov     ebx, eax
0x180002725  test    eax, eax
0x180002727  jz      short loc_180002739
0x180002729  mov     r9, [rbp+57h+var_78]
0x18000272d  lea     rdx, aGetAdapterSCon_1; "Get adapter's connectivity: GetConnecti"...
0x180002734  jmp     loc_180002806
0x180002739  mov     rcx, [rbp+57h+var_78]
0x18000273d  lea     r8, [rbp+57h+var_70]
0x180002741  lea     rdx, IID_IPropertyBag
0x180002748  mov     rax, [rcx]
0x18000274b  mov     rax, [rax]
0x18000274e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002753  mov     ebx, eax
0x180002755  test    eax, eax
0x180002757  jz      short loc_180002769
0x180002759  mov     r9, [rbp+57h+var_78]
0x18000275d  lea     rdx, aGetAdapterSCon; "Get adapter's connectivity: Network->Qu"...
0x180002764  jmp     loc_180002806
0x180002769  mov     rcx, [rbp+57h+var_70]
0x18000276d  lea     r8, aNaInternetconn; "NA_InternetConnectivityV6"
0x180002774  cmp     r14w, 2
0x180002779  lea     rdx, aNaInternetconn_0; "NA_InternetConnectivityV4"
0x180002780  cmovnz  rdx, r8
0x180002784  xor     r9d, r9d
0x180002787  mov     rax, [rcx]
0x18000278a  lea     r8, [rbp+57h+pvarg]
0x18000278e  mov     rax, [rax+18h]
0x180002792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002797  mov     ebx, eax
0x180002799  test    eax, eax
0x18000279b  jz      short loc_1800027AA
0x18000279d  mov     r9, [rbp+57h+var_78]
0x1800027a1  lea     rdx, aGetAdapterSCon_0; "Get adapter's connectivity: PropertyBag"...
0x1800027a8  jmp     short loc_180002806
0x1800027aa  mov     rcx, [rbp+57h+var_70]
0x1800027ae  mov     rax, [rcx]
0x1800027b1  mov     rax, [rax+10h]
0x1800027b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ba  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x1800027bd  mov     rcx, [rbp+57h+var_78]
0x1800027c1  mov     [r15], eax
0x1800027c4  mov     [rbp+57h+var_70], 0
0x1800027cc  mov     rax, [rcx]
0x1800027cf  mov     rax, [rax+10h]
0x1800027d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d8  mov     [rbp+57h+var_78], 0
0x1800027e0  jmp     short loc_180002829
0x1800027e2  mov     r9, [rbp+57h+var_80]
0x1800027e6  lea     rdx, aGetAdapterSCon_5; "Get adapter's connectivity: GetNetwork "...
0x1800027ed  jmp     short loc_180002806
0x1800027ef  mov     r9, [rbp+57h+var_80]
0x1800027f3  lea     rdx, aGetAdapterSCon_2; "Get adapter's connectivity: GetAdapterI"...
0x1800027fa  jmp     short loc_180002806
0x1800027fc  mov     r9, rcx
0x1800027ff  lea     rdx, aGetAdapterSCon_4; "Get adapter's connectivity: GetNetworks"...
0x180002806  mov     r8d, eax
0x180002809  mov     ecx, 800000h
0x18000280e  call    EventWriteError0
0x180002813  jmp     short loc_180002829
0x180002815  mov     r8d, eax
0x180002818  lea     rdx, aGetAdapterSCon_6; "Get adapter's connectivity: Unable to f"...
0x18000281f  mov     ecx, 800000h
0x180002824  call    EventWriteError0
0x180002829  mov     rcx, [rbp+57h+var_70]
0x18000282d  test    rcx, rcx
0x180002830  jz      short loc_18000283E
0x180002832  mov     rax, [rcx]
0x180002835  mov     rax, [rax+10h]
0x180002839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283e  mov     rcx, [rbp+57h+var_78]
0x180002842  test    rcx, rcx
0x180002845  jz      short loc_180002853
0x180002847  mov     rax, [rcx]
0x18000284a  mov     rax, [rax+10h]
0x18000284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002853  mov     rcx, [rbp+57h+var_80]
0x180002857  test    rcx, rcx
0x18000285a  jz      short loc_180002870
0x18000285c  mov     rax, [rcx]
0x18000285f  mov     rax, [rax+10h]
0x180002863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002868  mov     [rbp+57h+var_80], 0
0x180002870  mov     rcx, [rbp+57h+var_68]
0x180002874  test    rcx, rcx
0x180002877  jz      short loc_18000288D
0x180002879  mov     rax, [rcx]
0x18000287c  mov     rax, [rax+10h]
0x180002880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002885  mov     [rbp+57h+var_68], 0
0x18000288d  mov     rcx, [rbp+57h+var_60]
0x180002891  test    rcx, rcx
0x180002894  jz      short loc_1800028AA
0x180002896  mov     rax, [rcx]
0x180002899  mov     rax, [rax+10h]
0x18000289d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a2  mov     [rbp+57h+var_60], 0
0x1800028aa  call    cs:__imp_CoUninitialize
0x1800028b1  nop     dword ptr [rax+rax+00h]
0x1800028b6  mov     eax, ebx
0x1800028b8  mov     rcx, [rbp+57h+var_30]
0x1800028bc  xor     rcx, rsp; StackCookie
0x1800028bf  call    __security_check_cookie
0x1800028c4  mov     rbx, [rsp+0B0h+arg_8]
0x1800028cc  add     rsp, 90h
0x1800028d3  pop     r15
0x1800028d5  pop     r14
0x1800028d7  pop     rdi
0x1800028d8  pop     rsi
0x1800028d9  pop     rbp
0x1800028da  retn
```
