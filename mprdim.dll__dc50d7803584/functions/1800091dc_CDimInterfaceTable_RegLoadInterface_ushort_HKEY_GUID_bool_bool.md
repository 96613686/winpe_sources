# CDimInterfaceTable::RegLoadInterface(ushort *,HKEY__ *,_GUID *,bool &,bool &)

- ea: `0x1800091dc`
- end: `0x180009bf0`
- name: `?RegLoadInterface@CDimInterfaceTable@@AEAAKPEAGPEAUHKEY__@@PEAU_GUID@@AEA_N3@Z`
- size: `2580`
- prototype: `unsigned int __usercall@<eax>(CDimInterfaceTable *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY hKey@<r8>, struct _GUID *@<r9>, bool *, bool *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180003f40`
- `0x180005340`
- `0x180005670`
- `0x180005d14`
- `0x1800067e0`
- `0x1800076ac`
- `0x180007bf0`
- `0x1800091dc`
- `0x180009bf8`
- `0x180009cb8`
- `0x18000df70`
- `0x1800165cc`
- `0x18001b4b0`
- `0x18001e590`
- `0x18001e788`
- `0x18001f298`
- `0x1800244d0`
- `0x1800268b8`
- `0x180033e90`
- `0x180035d10`
- `0x180036a40`
- `0x180045d40`
- `0x180046e06`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800093db`
- `msvcrt!wcsrchr` at `0x1800093db`
- `rtutils!RouterLogEventW` at `0x1800096dc`
- `rtutils!RouterLogEventW` at `0x1800096dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097d5`

## string_xrefs

- `0x1800095bf`: `GetRoutingDomainConfiguration failed : %d`
- `0x180009626`: `The routing domain for interface is not yet configured - skipping.`
- `0x180009646`: `The routing domain for interface is configured but not available - skipping.`
- `0x180009956`: `Failed  to load custom IKE configuration for interface '%s'. Error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDimInterfaceTable::RegLoadInterface(
        CDimInterfaceTable *this,
        unsigned __int16 *a2,
        HKEY hKey,
        struct _GUID *a4,
        bool *a5,
        bool *a6)
{
  bool *v10; // r12
  unsigned int InterfaceInfo; // edi
  _ROUTER_INTERFACE_TYPE v12; // r13d
  __int64 v13; // rax
  char v14; // al
  wchar_t *v15; // rax
  wchar_t *v16; // r14
  wchar_t v17; // r12
  bool v18; // r14
  __int64 v19; // rax
  __int64 v20; // rax
  const wchar_t *v21; // r8
  __int128 *v22; // r9
  int v23; // r9d
  _QWORD *v24; // rdx
  __int64 *Interface; // rax
  std::tr1::_Ref_count_base *v26; // rbx
  __int64 v27; // rax
  __int128 *v28; // r9
  __int64 v29; // rax
  __int128 *v30; // r9
  __int64 v31; // rax
  void *v32; // rax
  __int64 v33; // rax
  __int128 *v34; // r9
  bool v36; // [rsp+60h] [rbp-C38h] BYREF
  unsigned __int8 v37; // [rsp+61h] [rbp-C37h]
  _ROUTER_INTERFACE_TYPE v38; // [rsp+64h] [rbp-C34h] BYREF
  int v39; // [rsp+68h] [rbp-C30h] BYREF
  int v40; // [rsp+6Ch] [rbp-C2Ch] BYREF
  unsigned int v41[2]; // [rsp+70h] [rbp-C28h] BYREF
  unsigned int v42; // [rsp+78h] [rbp-C20h] BYREF
  HKEY hkey; // [rsp+80h] [rbp-C18h]
  std::tr1::_Ref_count_base *v44[2]; // [rsp+88h] [rbp-C10h] BYREF
  bool *v45; // [rsp+98h] [rbp-C00h] BYREF
  std::tr1::_Ref_count_base *v46; // [rsp+A0h] [rbp-BF8h]
  bool *v47; // [rsp+A8h] [rbp-BF0h]
  LPWSTR plpszSubStringArray[2]; // [rsp+B0h] [rbp-BE8h] BYREF
  __int128 v49; // [rsp+C0h] [rbp-BD8h] BYREF
  _QWORD v50[3]; // [rsp+D0h] [rbp-BC8h] BYREF
  unsigned __int64 v51; // [rsp+E8h] [rbp-BB0h]
  struct in_addr v52; // [rsp+100h] [rbp-B98h] BYREF
  _BYTE v53[24]; // [rsp+104h] [rbp-B94h] BYREF
  struct _GUID Buf1[43]; // [rsp+11Ch] [rbp-B7Ch] BYREF
  int v55; // [rsp+3D0h] [rbp-8C8h] BYREF
  __int128 v56; // [rsp+3D4h] [rbp-8C4h]
  __int128 v57; // [rsp+3E4h] [rbp-8B4h]
  int v58; // [rsp+3F4h] [rbp-8A4h]
  _OWORD v59[3]; // [rsp+400h] [rbp-898h] BYREF
  _BYTE v60[30]; // [rsp+430h] [rbp-868h]
  __int16 v61; // [rsp+44Eh] [rbp-84Ah]
  int v62; // [rsp+450h] [rbp-848h] BYREF
  _BYTE v63[2044]; // [rsp+454h] [rbp-844h] BYREF

  hkey = hKey;
  v10 = a5;
  v45 = a5;
  v47 = a6;
  v39 = 5;
  v52 = 0;
  memset_0(v53, 0, 0x2C4u);
  v41[0] = 0;
  v40 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  v59[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v59[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v59[2] = *(_OWORD *)L"000-0000-000000000000}";
  *(_OWORD *)v60 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v60[14] = *(_OWORD *)L"000000}";
  v61 = 0;
  v51 = 7;
  v50[2] = 0;
  LOWORD(v50[0]) = 0;
  v38 = ROUTER_IF_TYPE_CLIENT;
  v36 = 0;
  v42 = 0;
  v41[1] = 0;
  v37 = *((_BYTE *)this + 116);
  *(_OWORD *)v44 = 0;
  v49 = 0;
  v62 = 0;
  memset_0(v63, 0, sizeof(v63));
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  *a5 = 0;
  *a6 = 0;
  InterfaceInfo = CDimInterfaceTable::RegGetInterfaceInfo(hKey, a2, &v38, &v36, &v42, &v41[1]);
  if ( !InterfaceInfo )
  {
    v12 = v38;
    if ( v38 == ROUTER_IF_TYPE_TUNNEL1 )
    {
      InterfaceInfo = 50;
      goto LABEL_104;
    }
    if ( !a4 )
      goto LABEL_9;
    v13 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v13 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v13 )
      v14 = 0;
    else
LABEL_9:
      v14 = 1;
    if ( v38 == ROUTER_IF_TYPE_DEDICATED && v14 )
    {
      v15 = wcsrchr(a2, (unsigned __int16)v38 + 122);
      v16 = v15;
      if ( !v15 )
      {
        InterfaceInfo = 87;
        goto LABEL_104;
      }
      v17 = v15[1];
      v15[1] = 0;
      if ( !CDimDedicatedInterface::IsLANDeviceActive(a2, (enum _UNREACHABILITY_REASON *)&v39) && v39 == 6 )
      {
        v16[1] = v17;
        goto LABEL_104;
      }
      v16[1] = v17;
      v10 = v45;
    }
    InterfaceInfo = ReadInterfaceExtraInfo(hkey, v12, v37, &v52);
    if ( !InterfaceInfo )
    {
      v18 = memcmp_0(Buf1, &GUID_NULL, 0x10u) == 0;
      if ( !a4 )
        goto LABEL_23;
      v19 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v19 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( !v19 )
      {
LABEL_23:
        if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
          goto LABEL_32;
        if ( !a4 )
        {
LABEL_28:
          *v10 = 1;
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
          {
LABEL_31:
            InterfaceInfo = 905;
            goto LABEL_104;
          }
          v21 = L"Interface does not belong to the right routing domain - skipping.";
LABEL_30:
          LOWORD(v55) = 0;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (_DWORD)v21,
            (unsigned int)Buf1,
            (__int64)a2,
            (__int64)&v55);
          goto LABEL_31;
        }
      }
      v20 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&Buf1[0].Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&Buf1[0].Data1 )
        v20 = *(_QWORD *)a4->Data4 - *(_QWORD *)Buf1[0].Data4;
      if ( v20 )
        goto LABEL_28;
LABEL_32:
      if ( !v18 && !*((_BYTE *)this + 116) )
      {
        *v10 = 1;
        if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
          goto LABEL_31;
        v21 = L"Interface is in non-default routing domain while multi tenancy is disabled - skipping.";
        goto LABEL_30;
      }
      InterfaceInfo = 0;
      if ( *((_BYTE *)this + 116) && !v18 )
      {
        v40 = 4;
        InterfaceInfo = GetRoutingDomainConfiguration(Buf1, 0x200u, 0, (__int64)&v40, (__int64)v41);
        if ( InterfaceInfo )
        {
          *v10 = 1;
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_31;
          LOWORD(v62) = 0;
          LOWORD(v55) = 0;
          FormatRRASErrorString(&v62, L"GetRoutingDomainConfiguration failed : %d", InterfaceInfo);
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_31;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v62,
            (unsigned int)Buf1,
            (__int64)a2,
            (__int64)&v55);
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_31;
          v21 = L"The routing domain for interface is not yet configured - skipping.";
          goto LABEL_30;
        }
        if ( (v41[0] & 1) == 0 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_31;
          v21 = L"The routing domain for interface is configured but not available - skipping.";
          goto LABEL_30;
        }
      }
      if ( (unsigned int)(v12 - 3) <= 2 )
      {
        v23 = 2;
      }
      else
      {
        if ( (gblDIMConfigInfo & 0x12) == gblDIMConfigInfo )
        {
          if ( a4 )
            MprConvertGuidToString(a4, 40, v59);
          plpszSubStringArray[0] = (LPWSTR)v59;
          plpszSubStringArray[1] = a2;
          if ( (unsigned int)dword_180070F40 > 1 )
            RouterLogEventW(hLogHandle, 2u, 0x4E9Fu, 2u, plpszSubStringArray, 0);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            LOWORD(v55) = 0;
            v22 = &v49;
            if ( a4 )
              LODWORD(v22) = (_DWORD)a4;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)L"The Demand Dial interface was not loaded. The router was not started in in Demand Dial mode.",
              (_DWORD)v22,
              (__int64)a2,
              (__int64)&v55);
          }
          InterfaceInfo = 0;
          goto LABEL_104;
        }
        v23 = 0;
      }
      v24 = v50;
      if ( v51 >= 8 )
        v24 = (_QWORD *)v50[0];
      Interface = CDimInterfaceTable::CreateInterface(
                    (__int64)this,
                    (__int64 *)&v45,
                    (__int64)a2,
                    v23,
                    v12,
                    0,
                    v36,
                    v42,
                    v41[1],
                    (__int64)v24,
                    (__int64)&v52);
      std::tr1::shared_ptr<CDimInterface>::operator=(v44, Interface);
      if ( v46 )
        std::tr1::_Ref_count_base::_Decref(v46);
      v26 = v44[0];
      if ( !v44[0] )
      {
        InterfaceInfo = GetLastError();
        goto LABEL_104;
      }
      CDimInterfaceTable::AcquireExclusive(this);
      (**(void (__fastcall ***)(std::tr1::_Ref_count_base *))v26)(v26);
      if ( (*(unsigned int (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 72LL))(v26) == 2 )
      {
        if ( (*(unsigned int (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 456LL))(v26) == 9 )
        {
          if ( (*((_BYTE *)v26 + 116) & 4) != 0
            && (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(this, v44, 44) )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
            {
              LOWORD(v62) = 0;
              LOWORD(v55) = 0;
              FormatRRASErrorString(
                &v62,
                L"Disabling interface '%s' as there is another interface exists with same destination and same (PSK) auth method.",
                a2);
              if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
              {
                v33 = (*(__int64 (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 280LL))(v26);
                LODWORD(v34) = (_DWORD)v26 + 3104;
                if ( v26 == (std::tr1::_Ref_count_base *)-3104LL )
                  v34 = &v49;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDimParamTraceAdminInfo,
                  (unsigned int)&v62,
                  (_DWORD)v34,
                  v33,
                  (__int64)&v55);
              }
            }
            *((_DWORD *)v26 + 29) &= ~4u;
          }
          goto LABEL_84;
        }
        if ( (*((_BYTE *)v26 + 116) & 4) != 0
          && ((*(__int64 (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 120LL))(v26) & 0x10000000) != 0
          && (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(this, v44, 14) )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
          {
            LOWORD(v62) = 0;
            LOWORD(v55) = 0;
            FormatRRASErrorString(
              &v62,
              L"Disabling interface '%s' as there is another interface exists with same destination and same (PSK) auth method.",
              a2);
            if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
            {
              v27 = (*(__int64 (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 280LL))(v26);
              LODWORD(v28) = (_DWORD)v26 + 3104;
              if ( v26 == (std::tr1::_Ref_count_base *)-3104LL )
                v28 = &v49;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceAdminInfo,
                (unsigned int)&v62,
                (_DWORD)v28,
                v27,
                (__int64)&v55);
            }
          }
          *((_DWORD *)v26 + 29) &= ~4u;
        }
        *((_DWORD *)v26 + 214) = 0;
        InterfaceInfo = RegLoadIkev2CustomConfiguration(hkey, (std::tr1::_Ref_count_base *)((char *)v26 + 864));
        if ( InterfaceInfo )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v62) = 0;
            LOWORD(v55) = 0;
            FormatRRASErrorString(
              &v62,
              L"Failed  to load custom IKE configuration for interface '%s'. Error %d.",
              a2,
              InterfaceInfo);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v29 = (*(__int64 (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 280LL))(v26);
              LODWORD(v30) = (_DWORD)v26 + 3104;
              if ( v26 == (std::tr1::_Ref_count_base *)-3104LL )
                v30 = &v49;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v62,
                (_DWORD)v30,
                v29,
                (__int64)&v55);
            }
          }
        }
        *((_DWORD *)v26 + 214) = 1;
        CDimInterface::PrintIkev2CustomPolicy(v26);
      }
      if ( InterfaceInfo )
      {
LABEL_103:
        (*(void (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 8LL))(v26);
        CDimInterfaceTable::ReleaseExclusive(this);
        goto LABEL_104;
      }
LABEL_84:
      CDimInterfaceTable::InsertInterface((__int64)this, (__int64 *)v44);
      v26 = v44[0];
      InterfaceInfo = CDimInterface::AddTransportFromRegistry((GUID *)v44[0], 0, hkey);
      v31 = *(_QWORD *)v26;
      if ( InterfaceInfo )
      {
        v32 = (void *)(*(__int64 (__fastcall **)(std::tr1::_Ref_count_base *))(v31 + 16))(v26);
        CDimInterfaceTable::RemoveInterface(this, v32);
      }
      else
      {
        if ( (*(unsigned int (__fastcall **)(std::tr1::_Ref_count_base *))(v31 + 72))(v26) == 3 && v39 == 5 )
        {
          *((_DWORD *)v26 + 772) = 0;
          *((_DWORD *)v26 + 29) |= 0x80u;
          CDimInterface::NotifyOfReachabilityChange((__int64)v26, 0, 5u);
        }
        if ( (*(unsigned int (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 72LL))(v26) == 2
          && (*((_BYTE *)v26 + 116) & 8) != 0 )
        {
          CDimInterface::NotifyOfReachabilityChange((__int64)v26, 0, 1u);
        }
        if ( (*(unsigned int (__fastcall **)(std::tr1::_Ref_count_base *))(*(_QWORD *)v26 + 72LL))(v26) == 2
          && (*((_DWORD *)v26 + 30) & 0x100) != 0 )
        {
          *v47 = 1;
        }
      }
      goto LABEL_103;
    }
  }
LABEL_104:
  FreeInterfaceExtraInfo(&v52);
  if ( v44[1] )
    std::tr1::_Ref_count_base::_Decref(v44[1]);
  std::wstring::_Tidy(v50, 1, 0);
  return InterfaceInfo;
}

```

## disassembly

```asm
0x1800091dc  push    rbx
0x1800091de  push    rsi
0x1800091df  push    rdi
0x1800091e0  push    r12
0x1800091e2  push    r13
0x1800091e4  push    r14
0x1800091e6  push    r15
0x1800091e8  sub     rsp, 0C60h
0x1800091ef  mov     rax, cs:__security_cookie
0x1800091f6  xor     rax, rsp
0x1800091f9  mov     [rsp+0C98h+var_48], rax
0x180009201  mov     rbx, r9
0x180009204  mov     rdi, r8
0x180009207  mov     [rsp+0C98h+hkey], r8
0x18000920f  mov     rsi, rdx
0x180009212  mov     r15, rcx
0x180009215  mov     r12, [rsp+0C98h+arg_20]
0x18000921d  mov     [rsp+0C98h+var_C00], r12
0x180009225  mov     r14, [rsp+0C98h+arg_28]
0x18000922d  mov     [rsp+0C98h+var_BF0], r14
0x180009235  mov     [rsp+0C98h+var_C30], 5
0x18000923d  mov     [rsp+0C98h+var_B98], 0
0x180009248  xor     edx, edx; Val
0x18000924a  mov     r8d, 2C4h; Size
0x180009250  lea     rcx, [rsp+0C98h+var_B94]; void *
0x180009258  call    memset_0
0x18000925d  mov     [rsp+0C98h+var_C28], 0
0x180009265  mov     [rsp+0C98h+var_C2C], 0
0x18000926d  xorps   xmm0, xmm0
0x180009270  movups  xmmword ptr [rsp+0C98h+var_BE8], xmm0
0x180009278  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18000927f  movaps  [rsp+0C98h+var_898], xmm1
0x180009287  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18000928e  movaps  [rsp+0C98h+var_888], xmm0
0x180009296  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18000929d  movaps  [rsp+0C98h+var_878], xmm1
0x1800092a5  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x1800092ac  movaps  xmmword ptr [rsp+0C98h+var_868], xmm0
0x1800092b4  movups  xmm1, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x1800092bb  movups  xmmword ptr [rsp+0C98h+var_868+0Eh], xmm1
0x1800092c3  xor     eax, eax
0x1800092c5  mov     [rsp+0C98h+var_84A], ax
0x1800092cd  mov     [rsp+0C98h+var_BB0], 7
0x1800092d9  mov     [rsp+0C98h+var_BB8], rax
0x1800092e1  mov     word ptr [rsp+0C98h+var_BC8], ax
0x1800092e9  mov     [rsp+0C98h+var_C34], eax
0x1800092ed  mov     [rsp+0C98h+var_C38], al
0x1800092f1  mov     [rsp+0C98h+var_C20], eax
0x1800092f5  mov     [rsp+0C98h+var_C28+4], eax
0x1800092f9  mov     al, [r15+74h]
0x1800092fd  mov     [rsp+0C98h+var_C37], al
0x180009301  xorps   xmm0, xmm0
0x180009304  movdqu  xmmword ptr [rsp+0C98h+var_C10], xmm0
0x18000930d  movups  [rsp+0C98h+var_BD8], xmm0
0x180009315  xor     eax, eax
0x180009317  mov     [rsp+0C98h+var_848], eax
0x18000931e  xor     edx, edx; Val
0x180009320  mov     r8d, 7FCh; Size
0x180009326  lea     rcx, [rsp+0C98h+var_844]; void *
0x18000932e  call    memset_0
0x180009333  xor     eax, eax
0x180009335  mov     [rsp+0C98h+var_8C8], eax
0x18000933c  xorps   xmm0, xmm0
0x18000933f  movups  [rsp+0C98h+var_8C4], xmm0
0x180009347  movups  [rsp+0C98h+var_8B4], xmm0
0x18000934f  mov     [rsp+0C98h+var_8A4], eax
0x180009356  mov     [r12], al
0x18000935a  mov     [r14], al
0x18000935d  lea     rax, [rsp+0C98h+var_C28+4]
0x180009362  mov     qword ptr [rsp+0C98h+dwErrorCode], rax; unsigned int *
0x180009367  lea     rax, [rsp+0C98h+var_C20]
0x18000936c  mov     [rsp+0C98h+plpszSubStringArray], rax; unsigned int *
0x180009371  lea     r9, [rsp+0C98h+var_C38]; bool *
0x180009376  lea     r8, [rsp+0C98h+var_C34]; enum _ROUTER_INTERFACE_TYPE *
0x18000937b  mov     rdx, rsi; unsigned __int16 *
0x18000937e  mov     rcx, rdi; hKey
0x180009381  call    ?RegGetInterfaceInfo@CDimInterfaceTable@@CAKPEAUHKEY__@@PEAGAEAW4_ROUTER_INTERFACE_TYPE@@AEA_NAEAK4@Z; CDimInterfaceTable::RegGetInterfaceInfo(HKEY__ *,ushort *,_ROUTER_INTERFACE_TYPE &,bool &,ulong &,ulong &)
0x180009386  mov     edi, eax
0x180009388  test    eax, eax
0x18000938a  jnz     loc_180009B98
0x180009390  mov     r13d, [rsp+0C98h+var_C34]
0x180009395  cmp     r13d, 6
0x180009399  jnz     short loc_1800093A3
0x18000939b  lea     edi, [rax+32h]
0x18000939e  jmp     loc_180009B98
0x1800093a3  test    rbx, rbx
0x1800093a6  jz      short loc_1800093C8
0x1800093a8  mov     rax, [rbx]
0x1800093ab  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800093b2  jnz     short loc_1800093BF
0x1800093b4  mov     rax, [rbx+8]
0x1800093b8  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800093bf  test    rax, rax
0x1800093c2  jz      short loc_1800093C8
0x1800093c4  xor     al, al
0x1800093c6  jmp     short loc_1800093CA
0x1800093c8  mov     al, 1
0x1800093ca  cmp     r13d, 3
0x1800093ce  jnz     short loc_18000942C
0x1800093d0  test    al, al
0x1800093d2  jz      short loc_18000942C
0x1800093d4  lea     edx, [r13+7Ah]; Ch
0x1800093d8  mov     rcx, rsi; Str
0x1800093db  call    cs:__imp_wcsrchr
0x1800093e1  mov     r14, rax
0x1800093e4  test    rax, rax
0x1800093e7  jnz     short loc_1800093F1
0x1800093e9  lea     edi, [rax+57h]
0x1800093ec  jmp     loc_180009B98
0x1800093f1  movzx   r12d, word ptr [rax+2]
0x1800093f6  xor     eax, eax
0x1800093f8  mov     [r14+2], ax
0x1800093fd  lea     rdx, [rsp+0C98h+var_C30]; enum _UNREACHABILITY_REASON *
0x180009402  mov     rcx, rsi; unsigned __int16 *
0x180009405  call    ?IsLANDeviceActive@CDimDedicatedInterface@@SA_NPEAGAEAW4_UNREACHABILITY_REASON@@@Z; CDimDedicatedInterface::IsLANDeviceActive(ushort *,_UNREACHABILITY_REASON &)
0x18000940a  test    al, al
0x18000940c  jnz     short loc_18000941F
0x18000940e  cmp     [rsp+0C98h+var_C30], 6
0x180009413  jnz     short loc_18000941F
0x180009415  mov     [r14+2], r12w
0x18000941a  jmp     loc_180009B98
0x18000941f  mov     [r14+2], r12w
0x180009424  mov     r12, [rsp+0C98h+var_C00]
0x18000942c  movzx   r8d, [rsp+0C98h+var_C37]
0x180009432  lea     r9, [rsp+0C98h+var_B98]
0x18000943a  mov     edx, r13d
0x18000943d  mov     rcx, [rsp+0C98h+hkey]; hKey
0x180009445  call    ReadInterfaceExtraInfo
0x18000944a  mov     edi, eax
0x18000944c  test    eax, eax
0x18000944e  jnz     loc_180009B98
0x180009454  lea     edi, [rax+10h]
0x180009457  mov     r8d, edi; Size
0x18000945a  lea     rdx, GUID_NULL; Buf2
0x180009461  lea     rcx, [rsp+0C98h+Buf1]; Buf1
0x180009469  call    memcmp_0
0x18000946e  test    eax, eax
0x180009470  setz    r14b
0x180009474  test    rbx, rbx
0x180009477  jz      short loc_180009495
0x180009479  mov     rax, [rbx]
0x18000947c  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180009483  jnz     short loc_180009490
0x180009485  mov     rax, [rbx+8]
0x180009489  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180009490  test    rax, rax
0x180009493  jnz     short loc_1800094B5
0x180009495  mov     r8, rdi; Size
0x180009498  lea     rdx, GUID_NULL; Buf2
0x18000949f  lea     rcx, [rsp+0C98h+Buf1]; Buf1
0x1800094a7  call    memcmp_0
0x1800094ac  test    eax, eax
0x1800094ae  jz      short loc_180009529
0x1800094b0  test    rbx, rbx
0x1800094b3  jz      short loc_1800094D3
0x1800094b5  mov     rax, [rbx]
0x1800094b8  sub     rax, [rsp+0C98h+Buf1]
0x1800094c0  jnz     short loc_1800094CE
0x1800094c2  mov     rax, [rbx+8]
0x1800094c6  sub     rax, [rsp+0C98h+var_B74]
0x1800094ce  test    rax, rax
0x1800094d1  jz      short loc_180009529
0x1800094d3  mov     byte ptr [r12], 1
0x1800094d8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800094df  jz      short loc_18000951F
0x1800094e1  lea     r8, aInterfaceDoesN; "Interface does not belong to the right "...
0x1800094e8  xor     eax, eax
0x1800094ea  mov     word ptr [rsp+0C98h+var_8C8], ax
0x1800094f2  lea     rax, [rsp+0C98h+var_8C8]
0x1800094fa  mov     qword ptr [rsp+0C98h+dwErrorCode], rax
0x1800094ff  lea     r9, [rsp+0C98h+Buf1]
0x180009507  mov     [rsp+0C98h+plpszSubStringArray], rsi
0x18000950c  lea     rdx, RasDimParamTraceError
0x180009513  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000951a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000951f  mov     edi, 389h
0x180009524  jmp     loc_180009B98
0x180009529  test    r14b, r14b
0x18000952c  jnz     short loc_18000954B
0x18000952e  cmp     [r15+74h], r14b
0x180009532  jnz     short loc_18000954B
0x180009534  mov     byte ptr [r12], 1
0x180009539  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180009540  jz      short loc_18000951F
0x180009542  lea     r8, aInterfaceIsInN; "Interface is in non-default routing dom"...
0x180009549  jmp     short loc_1800094E8
0x18000954b  xor     edi, edi
0x18000954d  cmp     [r15+74h], dil
0x180009551  jz      loc_180009652
0x180009557  test    r14b, r14b
0x18000955a  jnz     loc_180009652
0x180009560  mov     [rsp+0C98h+var_C2C], 4
0x180009568  lea     rax, [rsp+0C98h+var_C28]
0x18000956d  mov     [rsp+0C98h+plpszSubStringArray], rax; __int64
0x180009572  lea     r9, [rsp+0C98h+var_C2C]
0x180009577  xor     r8d, r8d
0x18000957a  mov     edx, 200h
0x18000957f  lea     rcx, [rsp+0C98h+Buf1]; struct _GUID *
0x180009587  call    GetRoutingDomainConfiguration
0x18000958c  mov     edi, eax
0x18000958e  test    eax, eax
0x180009590  jz      loc_180009632
0x180009596  mov     byte ptr [r12], 1
0x18000959b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800095a2  test    al, 4
0x1800095a4  jz      loc_18000951F
0x1800095aa  xor     eax, eax
0x1800095ac  mov     word ptr [rsp+0C98h+var_848], ax
0x1800095b4  mov     word ptr [rsp+0C98h+var_8C8], ax
0x1800095bc  mov     r8d, edi
0x1800095bf  lea     rdx, aGetroutingdoma_0; "GetRoutingDomainConfiguration failed : "...
0x1800095c6  lea     rcx, [rsp+0C98h+var_848]
0x1800095ce  call    FormatRRASErrorString
0x1800095d3  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800095da  test    al, 4
0x1800095dc  jz      loc_18000951F
0x1800095e2  lea     rax, [rsp+0C98h+var_8C8]
0x1800095ea  mov     qword ptr [rsp+0C98h+dwErrorCode], rax
0x1800095ef  mov     [rsp+0C98h+plpszSubStringArray], rsi
0x1800095f4  lea     r9, [rsp+0C98h+Buf1]
0x1800095fc  lea     r8, [rsp+0C98h+var_848]
0x180009604  lea     rdx, RasDimParamTraceError
0x18000960b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009612  call    McTemplateU0zjzz_EventWriteTransfer
0x180009617  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000961e  test    al, 4
0x180009620  jz      loc_18000951F
0x180009626  lea     r8, aTheRoutingDoma; "The routing domain for interface is not"...
0x18000962d  jmp     loc_1800094E8
0x180009632  test    byte ptr [rsp+0C98h+var_C28], 1
0x180009637  jnz     short loc_180009652
0x180009639  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180009640  jz      loc_18000951F
0x180009646  lea     r8, aTheRoutingDoma_0; "The routing domain for interface is con"...
0x18000964d  jmp     loc_1800094E8
0x180009652  lea     eax, [r13-3]
0x180009656  mov     r14d, 2
0x18000965c  cmp     eax, r14d
0x18000965f  jbe     loc_18000973C
0x180009665  mov     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x18000966b  and     eax, 12h
0x18000966e  cmp     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x180009674  jnz     loc_180009737
0x18000967a  test    rbx, rbx
0x18000967d  jz      short loc_180009693
0x18000967f  lea     r8, [rsp+0C98h+var_898]
0x180009687  lea     edx, [r14+26h]
0x18000968b  mov     rcx, rbx
0x18000968e  call    MprConvertGuidToString
0x180009693  lea     rax, [rsp+0C98h+var_898]
0x18000969b  mov     [rsp+0C98h+var_BE8], rax
0x1800096a3  mov     [rsp+0C98h+var_BE8+8], rsi
0x1800096ab  cmp     cs:dword_180070F40, 1
0x1800096b2  jbe     short loc_1800096E2
0x1800096b4  mov     [rsp+0C98h+dwErrorCode], 0; dwErrorCode
0x1800096bc  lea     rax, [rsp+0C98h+var_BE8]
0x1800096c4  mov     [rsp+0C98h+plpszSubStringArray], rax; plpszSubStringArray
0x1800096c9  mov     r9d, r14d; dwSubStringCount
0x1800096cc  mov     r8d, 4E9Fh; dwMessageId
0x1800096d2  mov     edx, r14d; dwEventType
0x1800096d5  mov     rcx, cs:hLogHandle; hLogHandle
0x1800096dc  call    cs:__imp_RouterLogEventW
0x1800096e2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800096e9  jz      short loc_180009730
0x1800096eb  xor     eax, eax
0x1800096ed  mov     word ptr [rsp+0C98h+var_8C8], ax
0x1800096f5  lea     r9, [rsp+0C98h+var_BD8]
0x1800096fd  test    rbx, rbx
0x180009700  cmovnz  r9, rbx
0x180009704  lea     rax, [rsp+0C98h+var_8C8]
0x18000970c  mov     qword ptr [rsp+0C98h+dwErrorCode], rax
0x180009711  mov     [rsp+0C98h+plpszSubStringArray], rsi
0x180009716  lea     r8, aTheDemandDialI; "The Demand Dial interface was not loade"...
0x18000971d  lea     rdx, RasDimParamTraceAdminError
0x180009724  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000972b  call    McTemplateU0zjzz_EventWriteTransfer
0x180009730  xor     edi, edi
0x180009732  jmp     loc_180009B98
0x180009737  xor     r9d, r9d
0x18000973a  jmp     short loc_18000973F
0x18000973c  mov     r9d, r14d
0x18000973f  lea     rdx, [rsp+0C98h+var_BC8]
0x180009747  cmp     [rsp+0C98h+var_BB0], 8
0x180009750  cmovnb  rdx, [rsp+0C98h+var_BC8]
0x180009759  mov     eax, [rsp+0C98h+var_C28+4]
0x18000975d  mov     ecx, [rsp+0C98h+var_C20]
0x180009761  lea     r8, [rsp+0C98h+var_B98]
0x180009769  mov     [rsp+0C98h+var_C48], r8
0x18000976e  mov     [rsp+0C98h+var_C50], rdx
0x180009773  mov     [rsp+0C98h+var_C58], eax
0x180009777  mov     [rsp+0C98h+var_C60], ecx
0x18000977b  mov     al, [rsp+0C98h+var_C38]
0x18000977f  mov     [rsp+0C98h+var_C68], al
0x180009783  mov     qword ptr [rsp+0C98h+dwErrorCode], 0
0x18000978c  mov     dword ptr [rsp+0C98h+plpszSubStringArray], r13d
0x180009791  mov     r8, rsi
0x180009794  lea     rdx, [rsp+0C98h+var_C00]
0x18000979c  mov     rcx, r15
0x18000979f  call    ?CreateInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAGW4ROUTER_INTERFACE_STATE@@W4_ROUTER_INTERFACE_TYPE@@PEAX_NKK0PEAU_DIM_INTERFACE_OBJECT_EXTRA_INFO@@@Z; CDimInterfaceTable::CreateInterface(ushort *,ROUTER_INTERFACE_STATE,_ROUTER_INTERFACE_TYPE,void *,bool,ulong,ulong,ushort *,_DIM_INTERFACE_OBJECT_EXTRA_INFO *)
0x1800097a4  mov     rdx, rax
  ... truncated ...
```
