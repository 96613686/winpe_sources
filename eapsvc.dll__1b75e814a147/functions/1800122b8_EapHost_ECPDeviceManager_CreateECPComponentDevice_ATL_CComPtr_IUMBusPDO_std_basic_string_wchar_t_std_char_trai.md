# EapHost::ECPDeviceManager::CreateECPComponentDevice(ATL::CComPtr<IUMBusPDO> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x1800122b8`
- end: `0x18001295f`
- name: `?CreateECPComponentDevice@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `1703`
- prototype: `void __fastcall(__int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f77c`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000ab70`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000c7b8`
- `0x18000de8c`
- `0x18000e4ac`
- `0x18000e530`
- `0x180010fac`
- `0x1800122b8`
- `0x180013750`
- `0x180014e98`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180012534`
- `ntdll!EtwEventEnabled` at `0x1800125ee`
- `ntdll!EtwEventEnabled` at `0x180012722`
- `ntdll!EtwEventEnabled` at `0x1800127a8`
- `ntdll!EtwEventEnabled` at `0x18001283d`
- `ntdll!EtwEventEnabled` at `0x1800128d8`
- `ntdll!EtwEventEnabled` at `0x180012534`
- `ntdll!EtwEventEnabled` at `0x1800125ee`
- `ntdll!EtwEventEnabled` at `0x180012722`
- `ntdll!EtwEventEnabled` at `0x1800127a8`
- `ntdll!EtwEventEnabled` at `0x18001283d`
- `ntdll!EtwEventEnabled` at `0x1800128d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012314`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012314`

## string_xrefs

- `0x1800127b5`: `Failed to create IPropertyStore while creating ECP component device, 0x%x`
- `0x18001284a`: `Failed to set PKEY_PNPX_SilentInstall while creating ECP component device, 0x%x`
- `0x1800128e5`: `Failed to set PKEY_Device_HardwareIds while adding ECP component device, 0x%x`
- `0x18001254a`: `AddChild for adding ECP component device returned 0x%x`
- `0x18001272c`: `AddChild for ECP component device is considered failure`
- `0x180012607`: `ECP component device is created, id=%S`

## pseudocode

```c
void __fastcall EapHost::ECPDeviceManager::CreateECPComponentDevice(__int64 a1, _QWORD *a2, __int64 *a3)
{
  unsigned int v5; // r14d
  unsigned int v6; // r14d
  unsigned __int64 v7; // rdx
  const void *v8; // r9
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  LPCVOID *v11; // rbx
  LPCVOID *v12; // rcx
  LPCVOID *v13; // rax
  LPCVOID v14; // r12
  unsigned int v15; // r14d
  const void *v16; // rdx
  unsigned int v17; // r14d
  __int64 v18; // r15
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rax
  const wchar_t *v22; // r9
  int v23; // r8d
  int v24; // r9d
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID v27[3]; // [rsp+50h] [rbp-B0h] BYREF
  LPCVOID *v28; // [rsp+68h] [rbp-98h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  LPCVOID v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  LPCVOID v33[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v34; // [rsp+B0h] [rbp-50h]
  LPCVOID lpMem[2]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-30h]
  char v37[2048]; // [rsp+E0h] [rbp-20h] BYREF

  ppv = 0;
  v5 = CoCreateInstance(&CLSID_PropertyStore, 0, 1u, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v5 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v37,
                0x800u,
                "Failed to create IPropertyStore while creating ECP component device, 0x%x",
                v5) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v37);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v5);
    SystemError::Throw<long>(&byte_180018CBC, v5);
  }
  v31 = 0;
  v32 = 0;
  LOWORD(v31) = 19;
  DWORD2(v31) = 1;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(ppv, qword_18001ABA0, &v31);
  if ( v6 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v37,
                0x800u,
                "Failed to set PKEY_PNPX_SilentInstall while creating ECP component device, 0x%x",
                v6) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v37);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v6);
    SystemError::Throw<long>(&byte_180018CBC, v6);
  }
  v29 = 0;
  v30 = 0;
  LOWORD(v29) = 4127;
  DWORD2(v29) = 2;
  v27[0] = 0;
  v27[1] = 0;
  if ( !(unsigned __int8)TempBuffer<0>::ReserveBytesNoThrow(v27, 16, 0) )
    ThrowNewFailure();
  v27[2] = 0;
  *(_OWORD *)lpMem = 0;
  si128 = 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
    lpMem,
    L"EH\\",
    3);
  v7 = a3[2];
  if ( (unsigned __int64)a3[3] <= 7 )
    v8 = a3;
  else
    v8 = (const void *)*a3;
  v9 = si128.m128i_i64[0];
  if ( v7 > si128.m128i_i64[1] - si128.m128i_i64[0] )
  {
    v12 = (LPCVOID *)std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Reallocate_grow_by<_lambda_76cbdebd20ca3f382dcb2591d79a3e65_,wchar_t const *,unsigned __int64>(
                       lpMem,
                       a3[2]);
  }
  else
  {
    v10 = v7 + si128.m128i_i64[0];
    si128.m128i_i64[0] += v7;
    v11 = lpMem;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (LPCVOID *)lpMem[0];
    memmove_0((char *)v11 + 2 * v9, v8, 2 * v7);
    *((_WORD *)v11 + v10) = 0;
    v12 = lpMem;
  }
  *(_OWORD *)v33 = 0;
  v34 = 0;
  *(_OWORD *)v33 = *(_OWORD *)v12;
  v34 = *((__m128i *)v12 + 1);
  v12[2] = 0;
  v12[3] = (LPCVOID)7;
  *(_WORD *)v12 = 0;
  if ( si128.m128i_i64[1] > 7uLL )
    operator delete(lpMem[0]);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpMem[0]) = 0;
  v13 = v33;
  if ( v34.m128i_i64[1] > 7uLL )
    v13 = (LPCVOID *)v33[0];
  v28 = v13;
  PodVector<wchar_t *,0>::PushBack(v27, &v28);
  PodVector<wchar_t *,0>::PushBack(v27, &off_1800182D8);
  v14 = v27[0];
  v30 = v27[0];
  v15 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
          ppv,
          &PKEY_Device_HardwareIds,
          &v29);
  if ( v15 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v37,
                0x800u,
                "Failed to set PKEY_Device_HardwareIds while adding ECP component device, 0x%x",
                v15) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v37);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v15);
    SystemError::Throw<long>(&byte_180018CBC, v15);
  }
  v26 = 0;
  if ( (unsigned __int64)a3[3] <= 7 )
    v16 = a3;
  else
    v16 = (const void *)*a3;
  v17 = (*(__int64 (__fastcall **)(_QWORD, const void *, LPVOID, _QWORD, _DWORD, __int64 *))(*(_QWORD *)*a2 + 88LL))(
          *a2,
          v16,
          ppv,
          0,
          0,
          &v26);
  v18 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v37, 0x800u, "AddChild for adding ECP component device returned 0x%x", v17) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v21 = -1;
    do
      ++v21;
    while ( v37[v21] );
    si128.m128i_i64[0] = (__int64)v37;
    si128.m128i_i64[1] = (unsigned int)(v21 + 1);
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v19,
      v20,
      (__int64)lpMem);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v17);
  if ( v17 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v37, 0x800u, "AddChild for ECP component device is considered failure") >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v37);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids);
    SystemError::Throw<long>(&byte_180018CBC, v17);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    v22 = (unsigned __int64)a3[3] <= 7 ? (const wchar_t *)a3 : (const wchar_t *)*a3;
    if ( (int)StringCchPrintfA(v37, 0x800u, "ECP component device is created, id=%S", v22) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v18;
      while ( v37[v18] );
      si128.m128i_i64[0] = (__int64)v37;
      si128.m128i_i64[1] = (unsigned int)(v18 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v23,
        v24,
        (__int64)lpMem);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( (unsigned __int64)a3[3] > 7 )
      a3 = (__int64 *)*a3;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, a3);
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v34.m128i_i64[1] > 7uLL )
    operator delete(v33[0]);
  v34 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v33[0]) = 0;
  operator delete(v14);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x1800122b8  mov     [rsp-8+arg_0], rbx
0x1800122bd  push    rbp
0x1800122be  push    rsi
0x1800122bf  push    rdi
0x1800122c0  push    r12
0x1800122c2  push    r13
0x1800122c4  push    r14
0x1800122c6  push    r15
0x1800122c8  lea     rbp, [rsp-7F0h]
0x1800122d0  sub     rsp, 8F0h
0x1800122d7  mov     rax, cs:__security_cookie
0x1800122de  xor     rax, rsp
0x1800122e1  mov     [rbp+820h+var_40], rax
0x1800122e8  mov     rsi, r8
0x1800122eb  mov     r15, rdx
0x1800122ee  xor     r13d, r13d
0x1800122f1  mov     [rsp+920h+var_8E0], r13
0x1800122f6  lea     rax, [rsp+920h+var_8E0]
0x1800122fb  mov     [rsp+920h+ppv], rax; ppv
0x180012300  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180012307  xor     edx, edx; pUnkOuter
0x180012309  lea     r8d, [r13+1]; dwClsContext
0x18001230d  lea     rcx, CLSID_PropertyStore; rclsid
0x180012314  call    cs:__imp_CoCreateInstance
0x18001231a  mov     r14d, eax
0x18001231d  test    eax, eax
0x18001231f  jnz     loc_18001279A
0x180012325  xorps   xmm0, xmm0
0x180012328  xor     eax, eax
0x18001232a  movups  [rbp+820h+var_898], xmm0
0x18001232e  mov     [rbp+820h+var_888], rax
0x180012332  lea     eax, [r13+13h]
0x180012336  mov     word ptr [rbp+820h+var_898], ax
0x18001233a  mov     dword ptr [rbp+820h+var_898+8], 1
0x180012341  mov     rcx, [rsp+920h+var_8E0]
0x180012346  mov     rax, [rcx]
0x180012349  lea     r8, [rbp+820h+var_898]
0x18001234d  lea     rdx, qword_18001ABA0
0x180012354  mov     rax, [rax+30h]
0x180012358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001235d  mov     r14d, eax
0x180012360  test    eax, eax
0x180012362  jnz     loc_18001282F
0x180012368  xorps   xmm0, xmm0
0x18001236b  xor     eax, eax
0x18001236d  movups  [rsp+920h+var_8B0], xmm0
0x180012372  mov     [rbp+820h+var_8A0], rax
0x180012376  mov     eax, 101Fh
0x18001237b  mov     word ptr [rsp+920h+var_8B0], ax
0x180012380  mov     dword ptr [rsp+920h+var_8B0+8], 2
0x180012388  mov     [rsp+920h+var_8D0], r13
0x18001238d  mov     [rsp+920h+var_8C8], r13
0x180012392  xor     r8d, r8d
0x180012395  lea     edx, [r13+10h]
0x180012399  lea     rcx, [rsp+920h+var_8D0]
0x18001239e  call    ?ReserveBytesNoThrow@?$TempBuffer@$0A@@@IEAA_N_K0@Z; TempBuffer<0>::ReserveBytesNoThrow(unsigned __int64,unsigned __int64)
0x1800123a3  test    al, al
0x1800123a5  jz      loc_1800128C4
0x1800123ab  mov     [rsp+920h+var_8C0], r13
0x1800123b0  xorps   xmm0, xmm0
0x1800123b3  movups  xmmword ptr [rbp+820h+lpMem], xmm0
0x1800123b7  xorps   xmm1, xmm1
0x1800123ba  movdqu  [rbp+820h+var_850], xmm1
0x1800123bf  lea     r8d, [r13+3]
0x1800123c3  lea     rdx, aEh; "EH\\"
0x1800123ca  lea     rcx, [rbp+820h+lpMem]
0x1800123ce  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800123d3  nop
0x1800123d4  mov     rdx, [rsi+10h]
0x1800123d8  lea     r14d, [r13+7]
0x1800123dc  cmp     [rsi+18h], r14
0x1800123e0  jbe     short loc_1800123E7
0x1800123e2  mov     r9, [rsi]
0x1800123e5  jmp     short loc_1800123EA
0x1800123e7  mov     r9, rsi
0x1800123ea  mov     rcx, qword ptr [rbp+820h+var_850]
0x1800123ee  mov     rax, qword ptr [rbp+820h+var_850+8]
0x1800123f2  sub     rax, rcx
0x1800123f5  cmp     rdx, rax
0x1800123f8  ja      short loc_18001242A
0x1800123fa  lea     rdi, [rdx+rcx]
0x1800123fe  mov     qword ptr [rbp+820h+var_850], rdi
0x180012402  lea     rbx, [rbp+820h+lpMem]
0x180012406  cmp     qword ptr [rbp+820h+var_850+8], r14
0x18001240a  cmova   rbx, [rbp+820h+lpMem]
0x18001240f  lea     r8, [rdx+rdx]; Size
0x180012413  lea     rcx, [rbx+rcx*2]; void *
0x180012417  mov     rdx, r9; Src
0x18001241a  call    memmove_0
0x18001241f  mov     [rbx+rdi*2], r13w
0x180012424  lea     rcx, [rbp+820h+lpMem]
0x180012428  jmp     short loc_18001243B
0x18001242a  mov     [rsp+920h+ppv], rdx; __int64
0x18001242f  lea     rcx, [rbp+820h+lpMem]; Src
0x180012433  call    ??$_Reallocate_grow_by@V_lambda_76cbdebd20ca3f382dcb2591d79a3e65_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@_KV_lambda_76cbdebd20ca3f382dcb2591d79a3e65_@@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Reallocate_grow_by<_lambda_76cbdebd20ca3f382dcb2591d79a3e65_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_76cbdebd20ca3f382dcb2591d79a3e65_,wchar_t const *,unsigned __int64)
0x180012438  mov     rcx, rax
0x18001243b  xorps   xmm0, xmm0
0x18001243e  movups  xmmword ptr [rbp+820h+var_880], xmm0
0x180012442  xorps   xmm1, xmm1
0x180012445  movdqu  [rbp+820h+var_870], xmm1
0x18001244a  movups  xmm0, xmmword ptr [rcx]
0x18001244d  movups  xmmword ptr [rbp+820h+var_880], xmm0
0x180012451  movups  xmm1, xmmword ptr [rcx+10h]
0x180012455  movups  [rbp+820h+var_870], xmm1
0x180012459  mov     [rcx+10h], r13
0x18001245d  mov     [rcx+18h], r14
0x180012461  mov     [rcx], r13w
0x180012465  cmp     qword ptr [rbp+820h+var_850+8], r14
0x180012469  jbe     short loc_180012474
0x18001246b  mov     rcx, [rbp+820h+lpMem]; lpMem
0x18001246f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012474  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001247c  movdqu  [rbp+820h+var_850], xmm0
0x180012481  mov     word ptr [rbp+820h+lpMem], r13w
0x180012486  lea     rax, [rbp+820h+var_880]
0x18001248a  cmp     qword ptr [rbp+820h+var_870+8], r14
0x18001248e  cmova   rax, [rbp+820h+var_880]
0x180012493  mov     [rsp+920h+var_8B8], rax
0x180012498  lea     rdx, [rsp+920h+var_8B8]
0x18001249d  lea     rcx, [rsp+920h+var_8D0]
0x1800124a2  call    ?PushBack@?$PodVector@PEA_W$0A@@@QEAAXAEBQEA_W@Z; PodVector<wchar_t *,0>::PushBack(wchar_t * const &)
0x1800124a7  lea     rdx, off_1800182D8; "EH\\0"
0x1800124ae  lea     rcx, [rsp+920h+var_8D0]
0x1800124b3  call    ?PushBack@?$PodVector@PEA_W$0A@@@QEAAXAEBQEA_W@Z; PodVector<wchar_t *,0>::PushBack(wchar_t * const &)
0x1800124b8  mov     r12, [rsp+920h+var_8D0]
0x1800124bd  mov     [rbp+820h+var_8A0], r12
0x1800124c1  mov     rcx, [rsp+920h+var_8E0]
0x1800124c6  mov     rax, [rcx]
0x1800124c9  lea     r8, [rsp+920h+var_8B0]
0x1800124ce  lea     rdx, PKEY_Device_HardwareIds
0x1800124d5  mov     rax, [rax+30h]
0x1800124d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124de  mov     r14d, eax
0x1800124e1  test    eax, eax
0x1800124e3  jnz     loc_1800128CA
0x1800124e9  mov     [rsp+920h+var_8D8], r13
0x1800124ee  mov     rcx, [r15]
0x1800124f1  mov     rax, [rcx]
0x1800124f4  cmp     qword ptr [rsi+18h], 7
0x1800124f9  jbe     short loc_180012500
0x1800124fb  mov     rdx, [rsi]
0x1800124fe  jmp     short loc_180012503
0x180012500  mov     rdx, rsi
0x180012503  lea     r8, [rsp+920h+var_8D8]
0x180012508  mov     [rsp+920h+var_8F8], r8
0x18001250d  mov     dword ptr [rsp+920h+ppv], r13d
0x180012512  xor     r9d, r9d
0x180012515  mov     r8, [rsp+920h+var_8E0]
0x18001251a  mov     rax, [rax+58h]
0x18001251e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012523  mov     r14d, eax
0x180012526  lea     rdx, DebugInfoEvent
0x18001252d  mov     rcx, cs:eaphost_Context
0x180012534  call    cs:__imp_EtwEventEnabled
0x18001253a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001253e  mov     edi, 800h
0x180012543  test    al, al
0x180012545  jz      short loc_1800125A6
0x180012547  mov     r9d, r14d
0x18001254a  lea     r8, aAddchildForAdd; "AddChild for adding ECP component devic"...
0x180012551  mov     edx, edi; unsigned __int64
0x180012553  lea     rcx, [rbp+820h+var_840]; char *
0x180012557  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001255c  test    eax, eax
0x18001255e  js      short loc_1800125A6
0x180012560  cmp     cs:Microsoft_Windows_EapHostEnableBits, r13b
0x180012567  jge     short loc_1800125A6
0x180012569  lea     rcx, [rbp+820h+var_840]
0x18001256d  mov     rax, r15
0x180012570  inc     rax
0x180012573  cmp     [rcx+rax], r13b
0x180012577  jnz     short loc_180012570
0x180012579  inc     eax
0x18001257b  lea     rcx, [rbp+820h+var_840]
0x18001257f  mov     qword ptr [rbp+820h+var_850], rcx
0x180012583  mov     dword ptr [rbp+820h+var_850+8], eax
0x180012586  mov     dword ptr [rbp+820h+var_850+0Ch], r13d
0x18001258a  lea     rax, [rbp+820h+lpMem]
0x18001258e  mov     [rsp+920h+ppv], rax
0x180012593  lea     rdx, DebugInfoEvent
0x18001259a  lea     rcx, eaphost_Context
0x1800125a1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800125a6  lea     rbx, WPP_GLOBAL_Control
0x1800125ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125b4  cmp     rcx, rbx
0x1800125b7  jz      short loc_1800125D7
0x1800125b9  test    byte ptr [rcx+1Ch], 4
0x1800125bd  jz      short loc_1800125D7
0x1800125bf  mov     edx, 1Ah
0x1800125c4  mov     r9d, r14d
0x1800125c7  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x1800125ce  mov     rcx, [rcx+10h]
0x1800125d2  call    WPP_SF_d
0x1800125d7  mov     rcx, cs:eaphost_Context
0x1800125de  test    r14d, r14d
0x1800125e1  jnz     loc_18001271B
0x1800125e7  lea     rdx, DebugInfoEvent
0x1800125ee  call    cs:__imp_EtwEventEnabled
0x1800125f4  test    al, al
0x1800125f6  jz      short loc_180012663
0x1800125f8  cmp     qword ptr [rsi+18h], 7
0x1800125fd  jbe     short loc_180012604
0x1800125ff  mov     r9, [rsi]
0x180012602  jmp     short loc_180012607
0x180012604  mov     r9, rsi
0x180012607  lea     r8, aEcpComponentDe; "ECP component device is created, id=%S"
0x18001260e  mov     rdx, rdi; unsigned __int64
0x180012611  lea     rcx, [rbp+820h+var_840]; char *
0x180012615  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001261a  test    eax, eax
0x18001261c  js      short loc_180012663
0x18001261e  cmp     cs:Microsoft_Windows_EapHostEnableBits, r13b
0x180012625  jge     short loc_180012663
0x180012627  lea     rax, [rbp+820h+var_840]
0x18001262b  inc     r15
0x18001262e  cmp     [rax+r15], r13b
0x180012632  jnz     short loc_18001262B
0x180012634  lea     eax, [r15+1]
0x180012638  lea     rcx, [rbp+820h+var_840]
0x18001263c  mov     qword ptr [rbp+820h+var_850], rcx
0x180012640  mov     dword ptr [rbp+820h+var_850+8], eax
0x180012643  mov     dword ptr [rbp+820h+var_850+0Ch], r13d
0x180012647  lea     rax, [rbp+820h+lpMem]
0x18001264b  mov     [rsp+920h+ppv], rax
0x180012650  lea     rdx, DebugInfoEvent
0x180012657  lea     rcx, eaphost_Context
0x18001265e  call    McGenEventWrite_EtwEventWriteTransfer
0x180012663  mov     rcx, cs:WPP_GLOBAL_Control
0x18001266a  cmp     rcx, rbx
0x18001266d  jz      short loc_180012698
0x18001266f  test    byte ptr [rcx+1Ch], 4
0x180012673  jz      short loc_180012698
0x180012675  cmp     qword ptr [rsi+18h], 7
0x18001267a  jbe     short loc_18001267F
0x18001267c  mov     rsi, [rsi]
0x18001267f  mov     edx, 1Ch
0x180012684  mov     r9, rsi
0x180012687  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x18001268e  mov     rcx, [rcx+10h]
0x180012692  call    WPP_SF_S
0x180012697  nop
0x180012698  mov     rcx, [rsp+920h+var_8D8]
0x18001269d  test    rcx, rcx
0x1800126a0  jz      short loc_1800126AF
0x1800126a2  mov     rax, [rcx]
0x1800126a5  mov     rax, [rax+10h]
0x1800126a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ae  nop
0x1800126af  cmp     qword ptr [rbp+820h+var_870+8], 7
0x1800126b4  jbe     short loc_1800126BF
0x1800126b6  mov     rcx, [rbp+820h+var_880]; lpMem
0x1800126ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126bf  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800126c7  movdqu  [rbp+820h+var_870], xmm0
0x1800126cc  mov     word ptr [rbp+820h+var_880], r13w
0x1800126d1  mov     rcx, r12; lpMem
0x1800126d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126d9  nop
0x1800126da  mov     rcx, [rsp+920h+var_8E0]
0x1800126df  test    rcx, rcx
0x1800126e2  jz      short loc_1800126F1
0x1800126e4  mov     rax, [rcx]
0x1800126e7  mov     rax, [rax+10h]
0x1800126eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126f0  nop
0x1800126f1  mov     rcx, [rbp+820h+var_40]
0x1800126f8  xor     rcx, rsp; StackCookie
0x1800126fb  call    __security_check_cookie
0x180012700  mov     rbx, [rsp+920h+arg_0]
0x180012708  add     rsp, 8F0h
0x18001270f  pop     r15
0x180012711  pop     r14
0x180012713  pop     r13
0x180012715  pop     r12
0x180012717  pop     rdi
0x180012718  pop     rsi
0x180012719  pop     rbp
0x18001271a  retn
0x18001271b  lea     rdx, DebugErrorEvent
0x180012722  call    cs:__imp_EtwEventEnabled
0x180012728  test    al, al
0x18001272a  jz      short loc_180012763
0x18001272c  lea     r8, aAddchildForEcp; "AddChild for ECP component device is co"...
0x180012733  mov     rdx, rdi; unsigned __int64
0x180012736  lea     rcx, [rbp+820h+var_840]; char *
0x18001273a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001273f  test    eax, eax
0x180012741  js      short loc_180012763
0x180012743  test    cs:byte_180020AC1, 8
0x18001274a  jz      short loc_180012763
0x18001274c  lea     r8, [rbp+820h+var_840]
0x180012750  lea     rdx, DebugErrorEvent
0x180012757  lea     rcx, eaphost_Context
0x18001275e  call    McTemplateU0s_EtwEventWriteTransfer
0x180012763  mov     rcx, cs:WPP_GLOBAL_Control
0x18001276a  cmp     rcx, rbx
0x18001276d  jz      short loc_18001278A
0x18001276f  test    byte ptr [rcx+1Ch], 1
0x180012773  jz      short loc_18001278A
0x180012775  mov     edx, 1Bh
  ... truncated ...
```
