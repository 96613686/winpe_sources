# CDimInterfaceTable::CreateInterface(ushort *,ROUTER_INTERFACE_STATE,_ROUTER_INTERFACE_TYPE,void *,bool,ulong,ulong,ushort *,_DIM_INTERFACE_OBJECT_EXTRA_INFO *)

- ea: `0x180005d14`
- end: `0x1800067d7`
- name: `?CreateInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAGW4ROUTER_INTERFACE_STATE@@W4_ROUTER_INTERFACE_TYPE@@PEAX_NKK0PEAU_DIM_INTERFACE_OBJECT_EXTRA_INFO@@@Z`
- size: `2755`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64, int, int, __int64, unsigned __int8, int, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180003f80`
- `0x1800057f0`
- `0x180006fac`
- `0x1800091dc`

## callees

- `0x18000322c`
- `0x180005670`
- `0x180005d14`
- `0x1800067e0`
- `0x180007f70`
- `0x180009cb8`
- `0x18000b604`
- `0x18000def0`
- `0x18001a36c`
- `0x18001a3ac`
- `0x18001a3d4`
- `0x18001a6d8`
- `0x18001e53c`
- `0x180021b5c`
- `0x18002223c`
- `0x18002262c`
- `0x18002268c`
- `0x1800226ec`
- `0x18002274c`
- `0x1800227fc`
- `0x18002285c`
- `0x1800228bc`
- `0x18002291c`
- `0x18002297c`
- `0x180023290`
- `0x18003486c`
- `0x1800454dc`
- `0x180045d40`
- `0x180046e06`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006782`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000667d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000667d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800066ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800066ac`
- `MPRDDM!IfObjectUpdatePbkInfo` at `0x180006628`
- `MPRDDM!IfObjectUpdatePbkInfo` at `0x180006628`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x18000669d`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x18000669d`

## string_xrefs

- `0x18000657b`: `CreateInterface: NsiGetInterfaceIndexAndLuidFromIsolationInfo failed with error %d `
- `0x1800066e8`: `CreateInterface: IfObjectLoadPhonebookInfo failed with error %d `
- `0x180006748`: `CreateInterface: failed with error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall CDimInterfaceTable::CreateInterface(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        unsigned __int8 a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11)
{
  int v11; // r14d
  __int64 *v13; // rdi
  DWORD PhonebookInfo; // esi
  std::tr1::_Ref_count_base *v16; // rax
  std::tr1::_Ref_count_base *v17; // r14
  std::tr1::_Ref_count_base *v18; // rax
  std::tr1::_Ref_count_base *v19; // r14
  std::tr1::_Ref_count_base *v20; // rax
  std::tr1::_Ref_count_base *v21; // r14
  std::tr1::_Ref_count_base *v22; // rax
  std::tr1::_Ref_count_base *v23; // r14
  std::tr1::_Ref_count_base *v24; // rax
  std::tr1::_Ref_count_base *v25; // r14
  std::tr1::_Ref_count_base *v26; // rax
  CDimDedicatedInterface *v27; // rax
  std::tr1::_Ref_count_base *v28; // rax
  CDimS2SInterface *v29; // rax
  std::tr1::_Ref_count_base *v30; // rax
  std::tr1::_Ref_count_base *v31; // r14
  std::tr1::_Ref_count_base *v32; // rax
  std::tr1::_Ref_count_base *v33; // r14
  void *v34; // rax
  void *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // ecx
  __int64 v39; // rax
  unsigned int i; // r9d
  unsigned int j; // edx
  __int64 k; // rcx
  std::tr1::_Ref_count_base *v43; // r8
  __int64 v44; // rcx
  DWORD InterfaceIndexAndLuidFromIsolationInfo; // eax
  void *v46; // rax
  std::tr1::_Ref_count_base *v48[2]; // [rsp+30h] [rbp-AA8h] BYREF
  int v49; // [rsp+40h] [rbp-A98h]
  int v50; // [rsp+44h] [rbp-A94h]
  __int64 v51; // [rsp+48h] [rbp-A90h]
  __int64 *v52; // [rsp+50h] [rbp-A88h]
  _QWORD v53[5]; // [rsp+58h] [rbp-A80h] BYREF
  _BYTE v54[528]; // [rsp+80h] [rbp-A58h] BYREF
  int v55; // [rsp+290h] [rbp-848h] BYREF
  _BYTE v56[2044]; // [rsp+294h] [rbp-844h] BYREF

  v11 = a4;
  v49 = a4;
  v13 = a2;
  v52 = a2;
  v51 = a10;
  memset_0(v54, 0, 0x202u);
  *v13 = 0;
  v13[1] = 0;
  v50 = 1;
  v55 = 0;
  memset_0(v56, 0, sizeof(v56));
  if ( !a3 )
    goto LABEL_2;
  if ( a5 == 2 && !*(_BYTE *)(a1 + 118) )
  {
    PhonebookInfo = 50;
    goto LABEL_129;
  }
  PhonebookInfo = 0;
  if ( ((a5 - 3) & 0xFFFFFFFC) == 0 && a5 != 5 && !a7 )
  {
LABEL_2:
    PhonebookInfo = 87;
    goto LABEL_129;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    switch ( a5 )
    {
      case 0:
        v32 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
        v33 = v32;
        v48[0] = v32;
        if ( v32 )
        {
          CDimInterface::CDimInterface(v32, *(_BYTE *)(a1 + 116));
          *(_QWORD *)v33 = &CDimClientInterface::`vftable';
        }
        else
        {
          v33 = 0;
        }
        *(_OWORD *)v48 = 0;
        std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimClientInterface>(v48, v33);
        std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
        if ( v48[1] )
          std::tr1::_Ref_count_base::_Decref(v48[1]);
        goto LABEL_75;
      case 1:
        v30 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
        v31 = v30;
        v48[0] = v30;
        if ( v30 )
        {
          CDimInterface::CDimInterface(v30, *(_BYTE *)(a1 + 116));
          *(_QWORD *)v31 = &CDimHomeRouterInterface::`vftable';
        }
        else
        {
          v31 = 0;
        }
        *(_OWORD *)v48 = 0;
        std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimHomeRouterInterface>(v48, v31);
        std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
        if ( v48[1] )
          std::tr1::_Ref_count_base::_Decref(v48[1]);
        goto LABEL_75;
      case 2:
        v28 = (std::tr1::_Ref_count_base *)operator new(0xCE0u);
        v48[0] = v28;
        if ( v28 )
          v29 = CDimS2SInterface::CDimS2SInterface(v28, *(_BYTE *)(a1 + 116));
        else
          v29 = 0;
        *(_OWORD *)v48 = 0;
        std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimS2SInterface>(v48, v29);
        std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
        if ( v48[1] )
          std::tr1::_Ref_count_base::_Decref(v48[1]);
        break;
      case 3:
        if ( *(_BYTE *)(a1 + 116) && a11 && memcmp_0((const void *)(a11 + 28), &GUID_NULL, 0x10u) )
        {
          v24 = (std::tr1::_Ref_count_base *)operator new(0xC98u);
          v25 = v24;
          v48[0] = v24;
          if ( v24 )
          {
            CDimDedicatedInterface::CDimDedicatedInterface(v24, *(_BYTE *)(a1 + 116));
            *(_QWORD *)v25 = &CDimVsidInterface::`vftable';
            *((_DWORD *)v25 + 798) = 0;
            *((_QWORD *)v25 + 400) = 0;
            *((_DWORD *)v25 + 804) = 0;
            *((_QWORD *)v25 + 401) = 0;
          }
          else
          {
            v25 = 0;
          }
          *(_OWORD *)v48 = 0;
          std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimVsidInterface>((__int64)v48, v25);
          std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
          if ( v48[1] )
            std::tr1::_Ref_count_base::_Decref(v48[1]);
LABEL_75:
          v11 = v49;
          goto LABEL_137;
        }
        v26 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
        v48[0] = v26;
        if ( v26 )
          v27 = CDimDedicatedInterface::CDimDedicatedInterface(v26, *(_BYTE *)(a1 + 116));
        else
          v27 = 0;
        *(_OWORD *)v48 = 0;
        std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimDedicatedInterface>(v48, v27);
        std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
        if ( v48[1] )
          std::tr1::_Ref_count_base::_Decref(v48[1]);
        break;
      default:
        switch ( a5 )
        {
          case 4:
            v22 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
            v23 = v22;
            v48[0] = v22;
            if ( v22 )
            {
              CDimInterface::CDimInterface(v22, *(_BYTE *)(a1 + 116));
              *(_QWORD *)v23 = &CDimInternalInterface::`vftable';
            }
            else
            {
              v23 = 0;
            }
            *(_OWORD *)v48 = 0;
            std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimInternalInterface>(v48, v23);
            std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
            if ( v48[1] )
              std::tr1::_Ref_count_base::_Decref(v48[1]);
            break;
          case 5:
            v20 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
            v21 = v20;
            v48[0] = v20;
            if ( v20 )
            {
              CDimInterface::CDimInterface(v20, *(_BYTE *)(a1 + 116));
              *(_QWORD *)v21 = &CDimLoopbackInterface::`vftable';
            }
            else
            {
              v21 = 0;
            }
            *(_OWORD *)v48 = 0;
            std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimLoopbackInterface>(v48, v21);
            std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
            if ( v48[1] )
              std::tr1::_Ref_count_base::_Decref(v48[1]);
            break;
          case 6:
            v18 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
            v19 = v18;
            v48[0] = v18;
            if ( v18 )
            {
              CDimInterface::CDimInterface(v18, *(_BYTE *)(a1 + 116));
              *(_QWORD *)v19 = &CDimTunnel1Interface::`vftable';
            }
            else
            {
              v19 = 0;
            }
            *(_OWORD *)v48 = 0;
            std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimTunnel1Interface>(v48, v19);
            std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
            if ( v48[1] )
              std::tr1::_Ref_count_base::_Decref(v48[1]);
            break;
          case 7:
            v16 = (std::tr1::_Ref_count_base *)operator new(0xC78u);
            v17 = v16;
            v48[0] = v16;
            if ( v16 )
            {
              CDimInterface::CDimInterface(v16, *(_BYTE *)(a1 + 116));
              *(_QWORD *)v17 = &CDimDialOutInterface::`vftable';
            }
            else
            {
              v17 = 0;
            }
            *(_OWORD *)v48 = 0;
            std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimDialOutInterface>(v48, v17);
            std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
            if ( v48[1] )
              std::tr1::_Ref_count_base::_Decref(v48[1]);
            break;
          default:
            PhonebookInfo = 87;
            goto LABEL_137;
        }
        goto LABEL_75;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v49 = 8;
      PhonebookInfo = 8;
      v13 = v52;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180006729);
      goto LABEL_129;
    }
  }
LABEL_137:
  if ( PhonebookInfo )
    goto LABEL_129;
  v34 = (void *)std::wstring::wstring(v53, a3);
  std::wstring::operator=((void *)(*v13 + 8), v34);
  std::wstring::_Tidy(v53, 1, 0);
  if ( (unsigned int)GetInterfaceFriendlyName(a3, v54) )
  {
    std::wstring::assign(*v13 + 48, *v13 + 8, 0, -1);
  }
  else
  {
    v35 = (void *)std::wstring::wstring(v53, v54);
    std::wstring::operator=((void *)(*v13 + 48), v35);
    std::wstring::_Tidy(v53, 1, 0);
  }
  *(_DWORD *)(*v13 + 144) = a8;
  *(_DWORD *)(*v13 + 148) = a9;
  *(_DWORD *)(*v13 + 152) = 0;
  *(_DWORD *)(*v13 + 3088) = v11;
  *(_QWORD *)(*v13 + 3096) = a6;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*v13 + 72LL))(*v13) != 5 || *(_BYTE *)(a1 + 116) )
    *(_QWORD *)(*v13 + 96) = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 112));
  else
    *(_QWORD *)(*v13 + 96) = 1;
  *(_DWORD *)(*v13 + 116) = 4 * a7;
  *(_QWORD *)(*v13 + 160) = -1;
  *(_DWORD *)(*v13 + 296) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*v13 + 72LL))(*v13);
  *(_DWORD *)(*v13 + 856) = 0;
  *(_DWORD *)(*v13 + 864) = 3600;
  *(_DWORD *)(*v13 + 912) = 28800;
  *(_DWORD *)(*v13 + 868) = 33553408;
  v36 = *v13;
  if ( a11 )
  {
    *(_OWORD *)(v36 + 3104) = *(_OWORD *)(a11 + 28);
    *(_OWORD *)(*v13 + 944) = *(_OWORD *)(a11 + 28);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*v13 + 72LL))(*v13) == 2 )
    {
      if ( *(_BYTE *)(a1 + 116) )
        StringCchCopyW((STRSAFE_LPWSTR)(*v13 + 996), 0x101u, (STRSAFE_LPCWSTR)(a11 + 56));
      v37 = *v13;
      if ( *(_DWORD *)(a11 + 572) )
        *(_DWORD *)(v37 + 2024) |= 1u;
      else
        *(_DWORD *)(v37 + 2024) &= ~1u;
      v38 = *(_DWORD *)(a11 + 592);
      v39 = *v13;
      *(_OWORD *)(v39 + 2028) = *(_OWORD *)(a11 + 576);
      *(_DWORD *)(v39 + 2044) = v38;
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*v13 + 72LL))(*v13) == 2
      || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*v13 + 72LL))(*v13) == 4 )
    {
      for ( i = 0; i < 2; ++i )
      {
        *(_DWORD *)(*v13 + 12LL * i + 968) = i != 0;
        *(_DWORD *)(*v13 + 12LL * i + 972) = _InterlockedIncrement(&dword_180071170);
      }
      *(_DWORD *)(*v13 + 960) = 2;
      for ( j = 0; j < *(_DWORD *)a11; ++j )
      {
        for ( k = 0; k != 2; ++k )
        {
          if ( *(_DWORD *)(a11 + 12LL * j + 8) == *(_DWORD *)(*v13 + 12 * k + 968) )
            *(_DWORD *)(*v13 + 12 * k + 964) = *(_DWORD *)(a11 + 12LL * j + 4);
        }
      }
    }
    if ( CDimInterface::IsDimVsidInterface((CDimInterface *)*v13) )
    {
      std::tr1::static_pointer_cast<CDimVsidInterface,CDimInterface>(v48, v13);
      v43 = v48[0];
      *((_DWORD *)v48[0] + 804) = *(_DWORD *)(a11 + 44);
      v44 = *(_QWORD *)(a11 + 48);
      *((_QWORD *)v43 + 401) = v44;
      InterfaceIndexAndLuidFromIsolationInfo = NsiGetInterfaceIndexAndLuidFromIsolationInfo(
                                                 (int)v44,
                                                 (int)v43 + 3104,
                                                 *((_DWORD *)v43 + 804),
                                                 (ULONG64 *)((int)v43 + 3200),
                                                 (PNET_IFINDEX)v43 + 798);
      PhonebookInfo = InterfaceIndexAndLuidFromIsolationInfo;
      if ( InterfaceIndexAndLuidFromIsolationInfo )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v55) = 0;
          FormatRRASErrorString(
            &v55,
            L"CreateInterface: NsiGetInterfaceIndexAndLuidFromIsolationInfo failed with error %d ",
            InterfaceIndexAndLuidFromIsolationInfo);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v55);
        }
        if ( v48[1] )
          std::tr1::_Ref_count_base::_Decref(v48[1]);
        goto LABEL_129;
      }
      if ( v48[1] )
        std::tr1::_Ref_count_base::_Decref(v48[1]);
    }
  }
  else
  {
    *(_DWORD *)(v36 + 2024) |= 1u;
  }
  if ( (gblDIMConfigInfo & 0x12) == gblDIMConfigInfo
    || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*v13 + 72LL))(*v13) != 2 )
  {
    return v13;
  }
  if ( (gbldwDIMComponentsLoaded & 4) == 0 )
  {
    PhonebookInfo = 903;
    goto LABEL_129;
  }
  if ( *(_BYTE *)(a1 + 117) )
  {
    IfObjectUpdatePbkInfo(*v13, a11);
    goto LABEL_119;
  }
  AcquireSRWLockShared(&gblPbkContextRWLock);
  PhonebookInfo = IfObjectLoadPhonebookInfo(
                    *v13,
                    (unsigned __int64)&gblPbkContext
                  & ((unsigned __int128)-(__int128)(unsigned __int64)gblPbkContext >> 64));
  ReleaseSRWLockShared(&gblPbkContextRWLock);
  if ( PhonebookInfo )
  {
    if ( PhonebookInfo == 925 )
    {
      *(_DWORD *)(*v13 + 116) |= 8u;
      goto LABEL_119;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0
      || (LOWORD(v55) = 0,
          FormatRRASErrorString(
            &v55,
            L"CreateInterface: IfObjectLoadPhonebookInfo failed with error %d ",
            PhonebookInfo),
          (Microsoft_Windows_RRASEnableBits & 4) == 0) )
    {
LABEL_132:
      SetLastError(PhonebookInfo);
      std::tr1::shared_ptr<CDimInterface>::shared_ptr<CDimInterface>(v48);
      std::tr1::shared_ptr<CDimInterface>::operator=(v13, v48);
      if ( v48[1] )
        std::tr1::_Ref_count_base::_Decref(v48[1]);
      return v13;
    }
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v55);
LABEL_129:
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"CreateInterface: failed with error %d", PhonebookInfo);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v55);
    }
    goto LABEL_132;
  }
LABEL_119:
  if ( v51 )
  {
    v46 = (void *)std::wstring::wstring(v53, v51);
    std::wstring::operator=((void *)(*v13 + 176), v46);
    std::wstring::_Tidy(v53, 1, 0);
  }
  return v13;
}

```

## disassembly

```asm
0x180005d14  push    rbx
0x180005d16  push    rsi
0x180005d17  push    rdi
0x180005d18  push    r12
0x180005d1a  push    r13
0x180005d1c  push    r14
0x180005d1e  push    r15
0x180005d20  sub     rsp, 0AA0h
0x180005d27  mov     rax, cs:__security_cookie
0x180005d2e  xor     rax, rsp
0x180005d31  mov     [rsp+0AD8h+var_48], rax
0x180005d39  mov     r14d, r9d
0x180005d3c  mov     [rsp+0AD8h+var_A98], r9d
0x180005d41  mov     r12, r8
0x180005d44  mov     rdi, rdx
0x180005d47  mov     r15, rcx
0x180005d4a  mov     [rsp+0AD8h+var_A88], rdx
0x180005d4f  mov     rax, [rsp+0AD8h+arg_48]
0x180005d57  mov     [rsp+0AD8h+var_A90], rax
0x180005d5c  mov     r13, [rsp+0AD8h+arg_50]
0x180005d64  xor     ebx, ebx
0x180005d66  mov     [rsp+0AD8h+var_A94], ebx
0x180005d6a  xor     edx, edx; Val
0x180005d6c  mov     r8d, 202h; Size
0x180005d72  lea     rcx, [rsp+0AD8h+var_A58]; void *
0x180005d7a  call    memset_0
0x180005d7f  mov     [rdi], rbx
0x180005d82  mov     [rdi+8], rbx
0x180005d86  mov     [rsp+0AD8h+var_A94], 1
0x180005d8e  mov     [rsp+0AD8h+var_848], ebx
0x180005d95  xor     edx, edx; Val
0x180005d97  mov     r8d, 7FCh; Size
0x180005d9d  lea     rcx, [rsp+0AD8h+var_844]; void *
0x180005da5  call    memset_0
0x180005daa  test    r12, r12
0x180005dad  jnz     short loc_180005DB9
0x180005daf  mov     esi, 57h ; 'W'
0x180005db4  jmp     loc_180006734
0x180005db9  mov     ecx, [rsp+0AD8h+arg_20]
0x180005dc0  cmp     ecx, 2
0x180005dc3  jnz     short loc_180005DD3
0x180005dc5  cmp     [r15+76h], bl
0x180005dc9  jnz     short loc_180005DD3
0x180005dcb  lea     esi, [rcx+30h]
0x180005dce  jmp     loc_180006734
0x180005dd3  mov     esi, ebx
0x180005dd5  lea     eax, [rcx-3]
0x180005dd8  test    eax, 0FFFFFFFCh
0x180005ddd  jnz     short loc_180005DED
0x180005ddf  cmp     ecx, 5
0x180005de2  jz      short loc_180005DED
0x180005de4  cmp     [rsp+0AD8h+arg_30], bl
0x180005deb  jz      short loc_180005DAF
0x180005ded  test    ecx, ecx
0x180005def  jz      loc_1800061BE
0x180005df5  sub     ecx, 1
0x180005df8  jz      loc_180006156
0x180005dfe  sub     ecx, 1
0x180005e01  jz      loc_1800060F8
0x180005e07  sub     ecx, 1
0x180005e0a  jz      loc_180005FE2
0x180005e10  sub     ecx, 1
0x180005e13  jz      loc_180005F77
0x180005e19  sub     ecx, 1
0x180005e1c  jz      loc_180005F0C
0x180005e22  sub     ecx, 1
0x180005e25  jz      short loc_180005EA1
0x180005e27  cmp     ecx, 1
0x180005e2a  jz      short loc_180005E36
0x180005e2c  mov     esi, 57h ; 'W'
0x180005e31  jmp     loc_180006229
0x180005e36  mov     ecx, 0C78h; Size
0x180005e3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e40  mov     r14, rax
0x180005e43  mov     [rsp+0AD8h+var_AA8], rax
0x180005e48  test    rax, rax
0x180005e4b  jz      short loc_180005E65
0x180005e4d  mov     dl, [r15+74h]; bool
0x180005e51  mov     rcx, rax; this
0x180005e54  call    ??0CDimInterface@@QEAA@_N@Z; CDimInterface::CDimInterface(bool)
0x180005e59  lea     rax, ??_7CDimDialOutInterface@@6B@; const CDimDialOutInterface::`vftable'
0x180005e60  mov     [r14], rax
0x180005e63  jmp     short loc_180005E68
0x180005e65  mov     r14, rbx
0x180005e68  xorps   xmm0, xmm0
0x180005e6b  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x180005e71  mov     rdx, r14
0x180005e74  lea     rcx, [rsp+0AD8h+var_AA8]
0x180005e79  call    ??$_Resetp@VCDimDialOutInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimDialOutInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimDialOutInterface>(CDimDialOutInterface *)
0x180005e7e  lea     rdx, [rsp+0AD8h+var_AA8]
0x180005e83  mov     rcx, rdi
0x180005e86  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180005e8b  nop
0x180005e8c  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x180005e91  test    rcx, rcx
0x180005e94  jz      short loc_180005E9C
0x180005e96  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005e9b  nop
0x180005e9c  jmp     loc_180006224
0x180005ea1  mov     ecx, 0C78h; Size
0x180005ea6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005eab  mov     r14, rax
0x180005eae  mov     [rsp+0AD8h+var_AA8], rax
0x180005eb3  test    rax, rax
0x180005eb6  jz      short loc_180005ED0
0x180005eb8  mov     dl, [r15+74h]; bool
0x180005ebc  mov     rcx, rax; this
0x180005ebf  call    ??0CDimInterface@@QEAA@_N@Z; CDimInterface::CDimInterface(bool)
0x180005ec4  lea     rax, ??_7CDimTunnel1Interface@@6B@; const CDimTunnel1Interface::`vftable'
0x180005ecb  mov     [r14], rax
0x180005ece  jmp     short loc_180005ED3
0x180005ed0  mov     r14, rbx
0x180005ed3  xorps   xmm0, xmm0
0x180005ed6  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x180005edc  mov     rdx, r14
0x180005edf  lea     rcx, [rsp+0AD8h+var_AA8]
0x180005ee4  call    ??$_Resetp@VCDimTunnel1Interface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimTunnel1Interface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimTunnel1Interface>(CDimTunnel1Interface *)
0x180005ee9  lea     rdx, [rsp+0AD8h+var_AA8]
0x180005eee  mov     rcx, rdi
0x180005ef1  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180005ef6  nop
0x180005ef7  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x180005efc  test    rcx, rcx
0x180005eff  jz      short loc_180005F07
0x180005f01  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005f06  nop
0x180005f07  jmp     loc_180006224
0x180005f0c  mov     ecx, 0C78h; Size
0x180005f11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f16  mov     r14, rax
0x180005f19  mov     [rsp+0AD8h+var_AA8], rax
0x180005f1e  test    rax, rax
0x180005f21  jz      short loc_180005F3B
0x180005f23  mov     dl, [r15+74h]; bool
0x180005f27  mov     rcx, rax; this
0x180005f2a  call    ??0CDimInterface@@QEAA@_N@Z; CDimInterface::CDimInterface(bool)
0x180005f2f  lea     rax, ??_7CDimLoopbackInterface@@6B@; const CDimLoopbackInterface::`vftable'
0x180005f36  mov     [r14], rax
0x180005f39  jmp     short loc_180005F3E
0x180005f3b  mov     r14, rbx
0x180005f3e  xorps   xmm0, xmm0
0x180005f41  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x180005f47  mov     rdx, r14
0x180005f4a  lea     rcx, [rsp+0AD8h+var_AA8]
0x180005f4f  call    ??$_Resetp@VCDimLoopbackInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimLoopbackInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimLoopbackInterface>(CDimLoopbackInterface *)
0x180005f54  lea     rdx, [rsp+0AD8h+var_AA8]
0x180005f59  mov     rcx, rdi
0x180005f5c  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180005f61  nop
0x180005f62  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x180005f67  test    rcx, rcx
0x180005f6a  jz      short loc_180005F72
0x180005f6c  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005f71  nop
0x180005f72  jmp     loc_180006224
0x180005f77  mov     ecx, 0C78h; Size
0x180005f7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f81  mov     r14, rax
0x180005f84  mov     [rsp+0AD8h+var_AA8], rax
0x180005f89  test    rax, rax
0x180005f8c  jz      short loc_180005FA6
0x180005f8e  mov     dl, [r15+74h]; bool
0x180005f92  mov     rcx, rax; this
0x180005f95  call    ??0CDimInterface@@QEAA@_N@Z; CDimInterface::CDimInterface(bool)
0x180005f9a  lea     rax, ??_7CDimInternalInterface@@6B@; const CDimInternalInterface::`vftable'
0x180005fa1  mov     [r14], rax
0x180005fa4  jmp     short loc_180005FA9
0x180005fa6  mov     r14, rbx
0x180005fa9  xorps   xmm0, xmm0
0x180005fac  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x180005fb2  mov     rdx, r14
0x180005fb5  lea     rcx, [rsp+0AD8h+var_AA8]
0x180005fba  call    ??$_Resetp@VCDimInternalInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimInternalInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimInternalInterface>(CDimInternalInterface *)
0x180005fbf  lea     rdx, [rsp+0AD8h+var_AA8]
0x180005fc4  mov     rcx, rdi
0x180005fc7  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180005fcc  nop
0x180005fcd  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x180005fd2  test    rcx, rcx
0x180005fd5  jz      short loc_180005FDD
0x180005fd7  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005fdc  nop
0x180005fdd  jmp     loc_180006224
0x180005fe2  cmp     [r15+74h], bl
0x180005fe6  jz      loc_18000609A
0x180005fec  test    r13, r13
0x180005fef  jz      loc_18000609A
0x180005ff5  lea     rcx, [r13+1Ch]; Buf1
0x180005ff9  mov     r8d, 10h; Size
0x180005fff  lea     rdx, GUID_NULL; Buf2
0x180006006  call    memcmp_0
0x18000600b  test    eax, eax
0x18000600d  jz      loc_18000609A
0x180006013  mov     ecx, 0C98h; Size
0x180006018  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000601d  mov     r14, rax
0x180006020  mov     [rsp+0AD8h+var_AA8], rax
0x180006025  test    rax, rax
0x180006028  jz      short loc_18000605E
0x18000602a  mov     dl, [r15+74h]; bool
0x18000602e  mov     rcx, rax; this
0x180006031  call    ??0CDimDedicatedInterface@@QEAA@_N@Z; CDimDedicatedInterface::CDimDedicatedInterface(bool)
0x180006036  lea     rax, ??_7CDimVsidInterface@@6B@; const CDimVsidInterface::`vftable'
0x18000603d  mov     [r14], rax
0x180006040  mov     [r14+0C78h], ebx
0x180006047  mov     [r14+0C80h], rbx
0x18000604e  mov     [r14+0C90h], ebx
0x180006055  mov     [r14+0C88h], rbx
0x18000605c  jmp     short loc_180006061
0x18000605e  mov     r14, rbx
0x180006061  xorps   xmm0, xmm0
0x180006064  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x18000606a  mov     rdx, r14
0x18000606d  lea     rcx, [rsp+0AD8h+var_AA8]
0x180006072  call    ??$_Resetp@VCDimVsidInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimVsidInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimVsidInterface>(CDimVsidInterface *)
0x180006077  lea     rdx, [rsp+0AD8h+var_AA8]
0x18000607c  mov     rcx, rdi
0x18000607f  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180006084  nop
0x180006085  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x18000608a  test    rcx, rcx
0x18000608d  jz      short loc_180006095
0x18000608f  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180006094  nop
0x180006095  jmp     loc_180006224
0x18000609a  mov     ecx, 0C78h; Size
0x18000609f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800060a4  mov     [rsp+0AD8h+var_AA8], rax
0x1800060a9  test    rax, rax
0x1800060ac  jz      short loc_1800060BC
0x1800060ae  mov     dl, [r15+74h]; bool
0x1800060b2  mov     rcx, rax; this
0x1800060b5  call    ??0CDimDedicatedInterface@@QEAA@_N@Z; CDimDedicatedInterface::CDimDedicatedInterface(bool)
0x1800060ba  jmp     short loc_1800060BF
0x1800060bc  mov     rax, rbx
0x1800060bf  xorps   xmm0, xmm0
0x1800060c2  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x1800060c8  mov     rdx, rax
0x1800060cb  lea     rcx, [rsp+0AD8h+var_AA8]
0x1800060d0  call    ??$_Resetp@VCDimDedicatedInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimDedicatedInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimDedicatedInterface>(CDimDedicatedInterface *)
0x1800060d5  lea     rdx, [rsp+0AD8h+var_AA8]
0x1800060da  mov     rcx, rdi
0x1800060dd  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x1800060e2  nop
0x1800060e3  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x1800060e8  test    rcx, rcx
0x1800060eb  jz      short loc_1800060F3
0x1800060ed  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800060f2  nop
0x1800060f3  jmp     loc_180006229
0x1800060f8  mov     ecx, 0CE0h; Size
0x1800060fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006102  mov     [rsp+0AD8h+var_AA8], rax
0x180006107  test    rax, rax
0x18000610a  jz      short loc_18000611A
0x18000610c  mov     dl, [r15+74h]; bool
0x180006110  mov     rcx, rax; this
0x180006113  call    ??0CDimS2SInterface@@QEAA@_N@Z; CDimS2SInterface::CDimS2SInterface(bool)
0x180006118  jmp     short loc_18000611D
0x18000611a  mov     rax, rbx
0x18000611d  xorps   xmm0, xmm0
0x180006120  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x180006126  mov     rdx, rax
0x180006129  lea     rcx, [rsp+0AD8h+var_AA8]
0x18000612e  call    ??$_Resetp@VCDimS2SInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimS2SInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimS2SInterface>(CDimS2SInterface *)
0x180006133  lea     rdx, [rsp+0AD8h+var_AA8]
0x180006138  mov     rcx, rdi
0x18000613b  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180006140  nop
0x180006141  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x180006146  test    rcx, rcx
0x180006149  jz      short loc_180006151
0x18000614b  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180006150  nop
0x180006151  jmp     loc_180006229
0x180006156  mov     ecx, 0C78h; Size
0x18000615b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006160  mov     r14, rax
0x180006163  mov     [rsp+0AD8h+var_AA8], rax
0x180006168  test    rax, rax
0x18000616b  jz      short loc_180006185
0x18000616d  mov     dl, [r15+74h]; bool
0x180006171  mov     rcx, rax; this
0x180006174  call    ??0CDimInterface@@QEAA@_N@Z; CDimInterface::CDimInterface(bool)
0x180006179  lea     rax, ??_7CDimHomeRouterInterface@@6B@; const CDimHomeRouterInterface::`vftable'
0x180006180  mov     [r14], rax
0x180006183  jmp     short loc_180006188
0x180006185  mov     r14, rbx
0x180006188  xorps   xmm0, xmm0
0x18000618b  movdqu  xmmword ptr [rsp+0AD8h+var_AA8], xmm0
0x180006191  mov     rdx, r14
0x180006194  lea     rcx, [rsp+0AD8h+var_AA8]
0x180006199  call    ??$_Resetp@VCDimHomeRouterInterface@@@?$shared_ptr@VCDimInterface@@@tr1@std@@AEAAXPEAVCDimHomeRouterInterface@@@Z; std::tr1::shared_ptr<CDimInterface>::_Resetp<CDimHomeRouterInterface>(CDimHomeRouterInterface *)
0x18000619e  lea     rdx, [rsp+0AD8h+var_AA8]
0x1800061a3  mov     rcx, rdi
0x1800061a6  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x1800061ab  nop
0x1800061ac  mov     rcx, [rsp+0AD8h+var_AA8+8]; this
0x1800061b1  test    rcx, rcx
0x1800061b4  jz      short loc_1800061BC
  ... truncated ...
```
