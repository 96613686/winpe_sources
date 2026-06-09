# EapHost::ECPDeviceManager::GetAllECPComponentDevices(ATL::CComPtr<IUMBusPDO> &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>> &,std::vector<ATL::CComPtr<IUMBusPDO>,std::allocator<ATL::CComPtr<IUMBusPDO>>> &)

- ea: `0x180012cf8`
- end: `0x1800133a0`
- name: `?GetAllECPComponentDevices@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@@std@@AEAV?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@6@@Z`
- size: `1704`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 *, char **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f77c`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000ab70`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c40c`
- `0x18000ea5c`
- `0x18001100c`
- `0x18001129c`
- `0x18001140c`
- `0x180011698`
- `0x180012cf8`
- `0x1800139f8`
- `0x180013a4c`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180012d71`
- `ntdll!EtwEventEnabled` at `0x180012ee8`
- `ntdll!EtwEventEnabled` at `0x180012fd4`
- `ntdll!EtwEventEnabled` at `0x1800130a6`
- `ntdll!EtwEventEnabled` at `0x1800131be`
- `ntdll!EtwEventEnabled` at `0x1800132a1`
- `ntdll!EtwEventEnabled` at `0x18001332d`
- `ntdll!EtwEventEnabled` at `0x180012d71`
- `ntdll!EtwEventEnabled` at `0x180012ee8`
- `ntdll!EtwEventEnabled` at `0x180012fd4`
- `ntdll!EtwEventEnabled` at `0x1800130a6`
- `ntdll!EtwEventEnabled` at `0x1800131be`
- `ntdll!EtwEventEnabled` at `0x1800132a1`
- `ntdll!EtwEventEnabled` at `0x18001332d`

## string_xrefs

- `0x18001333e`: `Cannot get the component device at index %u, 0x%x`
- `0x180012f0a`: `The device id string already exists in the map: index=%u string=%S`
- `0x180012ff6`: `Device added to componentDeviceMap: index=%u, string=%S`
- `0x1800131dc`: `Finished getting all ECP component devices. Good %Iu, bad %Iu`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::GetAllECPComponentDevices(__int64 a1, _QWORD *a2, __int64 *a3, char **a4)
{
  __int64 *v5; // r14
  unsigned int v6; // ebx
  __int64 v7; // r12
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rax
  unsigned int v11; // esi
  __m128i si128; // xmm6
  int v13; // ebx
  const wchar_t *v14; // rax
  char v15; // bl
  LPCVOID *v16; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rax
  LPCVOID *v20; // rax
  char *v21; // rdx
  __int64 v22; // rcx
  LPCVOID *v23; // rax
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rax
  LPCVOID *v27; // rax
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 result; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // r9d
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // [rsp+28h] [rbp-E0h]
  __int64 v39; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v41; // [rsp+48h] [rbp-C0h]
  _QWORD *v42; // [rsp+50h] [rbp-B8h]
  _BYTE v43[16]; // [rsp+58h] [rbp-B0h] BYREF
  LPCVOID lpMem[2]; // [rsp+68h] [rbp-A0h] BYREF
  char *v45; // [rsp+78h] [rbp-90h]
  unsigned __int64 v46; // [rsp+80h] [rbp-88h]
  __int64 v47; // [rsp+88h] [rbp-80h]
  LPCVOID v48[2]; // [rsp+90h] [rbp-78h] BYREF
  __m128i v49; // [rsp+A0h] [rbp-68h]
  char v50[2048]; // [rsp+B8h] [rbp-50h] BYREF

  v5 = a3;
  v41 = a3;
  v42 = a2;
  LODWORD(v39) = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 64LL))(*a2, &v39);
  if ( v6 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v50, 0x800u, "Cannot GetChildCount for ECP bus enumerator, 0x%x", v6) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v50);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v6);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v6);
  }
  v7 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v50, 0x800u, "Total number of ECP devices found: %u", v39) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v50[v10] );
    v49.m128i_i64[0] = (__int64)v50;
    v49.m128i_i64[1] = (unsigned int)(v10 + 1);
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v8,
      v9,
      (__int64)v48);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids,
      (unsigned int)v39);
  v11 = 0;
  if ( (_DWORD)v39 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v40 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*(_QWORD *)*v42 + 72LL))(*v42, v11, &v40);
      if ( v13 )
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
          && (int)StringCchPrintfA(v50, 0x800u, "Cannot get the component device at index %u, 0x%x", v11, v13) >= 0
          && (byte_180020AC1 & 8) != 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v50);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(v38) = v13;
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, v37, v11, v38);
        }
        SystemError::Throw<long>((__int64)&byte_180018CBC, v13);
      }
      *(_OWORD *)v48 = 0;
      v49 = si128;
      LOWORD(v48[0]) = 0;
      if ( EapHost::ECPDeviceManager::CheckECPComponentDevice(&v40, (__int64)v48) )
      {
        v14 = (const wchar_t *)std::make_pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,ATL::CComPtr<IUMBusPDO> &>(
                                 (__int64)lpMem,
                                 (__int64)v48,
                                 &v40);
        v15 = *(_BYTE *)(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>,0>(
                           v41,
                           (__int64)v43,
                           v14)
                       + 8);
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        if ( v46 > 7 )
          operator delete((void *)lpMem[0]);
        if ( v15 )
        {
          if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
          {
            v23 = v48;
            if ( v49.m128i_i64[1] > 7uLL )
              v23 = (LPCVOID *)v48[0];
            if ( (int)StringCchPrintfA(
                        v50,
                        0x800u,
                        "Device added to componentDeviceMap: index=%u, string=%S",
                        v11,
                        (const wchar_t *)v23) >= 0
              && Microsoft_Windows_EapHostEnableBits < 0 )
            {
              v26 = -1;
              do
                ++v26;
              while ( v50[v26] );
              v45 = v50;
              v46 = (unsigned int)(v26 + 1);
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)&eaphost_Context,
                (unsigned int)DebugInfoEvent,
                v24,
                v25,
                (__int64)lpMem);
            }
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v27 = v48;
            if ( v49.m128i_i64[1] > 7uLL )
              v27 = (LPCVOID *)v48[0];
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              (unsigned int)WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids,
              v11,
              (__int64)v27);
          }
          goto LABEL_64;
        }
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent) )
        {
          v16 = v48;
          if ( v49.m128i_i64[1] > 7uLL )
            v16 = (LPCVOID *)v48[0];
          if ( (int)StringCchPrintfA(
                      v50,
                      0x800u,
                      "The device id string already exists in the map: index=%u string=%S",
                      v11,
                      (const wchar_t *)v16) >= 0
            && (byte_180020AC1 & 8) != 0 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v50[v19] );
            v45 = v50;
            v46 = (unsigned int)(v19 + 1);
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&eaphost_Context,
              (unsigned int)DebugErrorEvent,
              v17,
              v18,
              (__int64)lpMem);
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = v48;
          if ( v49.m128i_i64[1] > 7uLL )
            v20 = (LPCVOID *)v48[0];
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            (unsigned int)WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids,
            v11,
            (__int64)v20);
        }
        v21 = a4[1];
        if ( v21 == a4[2] )
        {
LABEL_63:
          std::vector<ATL::CComPtr<IUMBusPDO>>::_Emplace_reallocate<ATL::CComPtr<IUMBusPDO> const &>(a4, v21, &v40);
          goto LABEL_64;
        }
        v22 = v40;
        *(_QWORD *)v21 = v40;
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      }
      else
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
          && (int)StringCchPrintfA(v50, 0x800u, "Device did not pass check, index=%u", v11) >= 0
          && (byte_180020AC1 & 8) != 0 )
        {
          v30 = -1;
          do
            ++v30;
          while ( v50[v30] );
          v45 = v50;
          v46 = (unsigned int)(v30 + 1);
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&eaphost_Context,
            (unsigned int)DebugErrorEvent,
            v28,
            v29,
            (__int64)lpMem);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v11);
        v21 = a4[1];
        if ( v21 == a4[2] )
          goto LABEL_63;
        v31 = v40;
        *(_QWORD *)v21 = v40;
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      }
      a4[1] += 8;
LABEL_64:
      if ( v49.m128i_i64[1] > 7uLL )
        operator delete((void *)v48[0]);
      v49 = si128;
      LOWORD(v48[0]) = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      if ( ++v11 >= (unsigned int)v39 )
      {
        v5 = v41;
        break;
      }
    }
  }
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  if ( (_BYTE)result )
  {
    result = StringCchPrintfA(
               v50,
               0x800u,
               "Finished getting all ECP component devices. Good %Iu, bad %Iu",
               v5[1],
               (a4[1] - *a4) >> 3);
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v7;
      while ( v50[v7] );
      v45 = v50;
      v46 = (unsigned int)(v7 + 1);
      result = McGenEventWrite_EtwEventWriteTransfer(
                 (unsigned int)&eaphost_Context,
                 (unsigned int)DebugInfoEvent,
                 v34,
                 v35,
                 (__int64)lpMem);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return WPP_SF_PP(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, v34, v5[1], (a4[1] - *a4) >> 3);
  return result;
}

```

## disassembly

```asm
0x180012cf8  mov     rax, rsp
0x180012cfb  mov     [rax+8], rbx
0x180012cff  push    rbp
0x180012d00  push    rsi
0x180012d01  push    rdi
0x180012d02  push    r12
0x180012d04  push    r13
0x180012d06  push    r14
0x180012d08  push    r15
0x180012d0a  lea     rbp, [rax-808h]
0x180012d11  sub     rsp, 8D0h
0x180012d18  movaps  xmmword ptr [rax-48h], xmm6
0x180012d1c  mov     rax, cs:__security_cookie
0x180012d23  xor     rax, rsp
0x180012d26  mov     [rbp+800h+var_50], rax
0x180012d2d  mov     rdi, r9
0x180012d30  mov     r14, r8
0x180012d33  mov     [rsp+900h+var_8C0], r8
0x180012d38  mov     [rsp+900h+var_8B8], rdx
0x180012d3d  mov     dword ptr [rsp+900h+var_8D0], 0
0x180012d45  mov     rcx, [rdx]
0x180012d48  mov     rax, [rcx]
0x180012d4b  lea     rdx, [rsp+900h+var_8D0]
0x180012d50  mov     rax, [rax+40h]
0x180012d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d59  mov     ebx, eax
0x180012d5b  mov     rcx, cs:eaphost_Context
0x180012d62  test    eax, eax
0x180012d64  jnz     loc_180013297
0x180012d6a  lea     rdx, DebugInfoEvent
0x180012d71  call    cs:__imp_EtwEventEnabled
0x180012d77  lea     r13, eaphost_Context
0x180012d7e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012d82  xor     ebx, ebx
0x180012d84  test    al, al
0x180012d86  jz      short loc_180012DE5
0x180012d88  mov     r9d, dword ptr [rsp+900h+var_8D0]
0x180012d8d  lea     r8, aTotalNumberOfE; "Total number of ECP devices found: %u"
0x180012d94  mov     edx, 800h; unsigned __int64
0x180012d99  lea     rcx, [rbp+800h+var_850]; char *
0x180012d9d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012da2  test    eax, eax
0x180012da4  js      short loc_180012DE5
0x180012da6  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180012dac  jge     short loc_180012DE5
0x180012dae  lea     rcx, [rbp+800h+var_850]
0x180012db2  mov     rax, r12
0x180012db5  inc     rax
0x180012db8  cmp     [rcx+rax], bl
0x180012dbb  jnz     short loc_180012DB5
0x180012dbd  inc     eax
0x180012dbf  lea     rcx, [rbp+800h+var_850]
0x180012dc3  mov     qword ptr [rbp+800h+var_868], rcx
0x180012dc7  mov     dword ptr [rbp+800h+var_868+8], eax
0x180012dca  mov     dword ptr [rbp+800h+var_868+0Ch], ebx
0x180012dcd  lea     rax, [rbp+800h+var_878]
0x180012dd1  mov     [rsp+900h+var_8E0], rax
0x180012dd6  lea     rdx, DebugInfoEvent
0x180012ddd  mov     rcx, r13
0x180012de0  call    McGenEventWrite_EtwEventWriteTransfer
0x180012de5  lea     r15, WPP_GLOBAL_Control
0x180012dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180012df3  cmp     rcx, r15
0x180012df6  jz      short loc_180012E18
0x180012df8  test    byte ptr [rcx+1Ch], 4
0x180012dfc  jz      short loc_180012E18
0x180012dfe  mov     edx, 20h ; ' '
0x180012e03  mov     r9d, dword ptr [rsp+900h+var_8D0]
0x180012e08  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180012e0f  mov     rcx, [rcx+10h]
0x180012e13  call    WPP_SF_d
0x180012e18  mov     esi, ebx
0x180012e1a  cmp     dword ptr [rsp+900h+var_8D0], ebx
0x180012e1e  jbe     loc_1800131B0
0x180012e24  lea     r14, DebugErrorEvent
0x180012e2b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180012e33  mov     [rsp+900h+var_8C8], rbx
0x180012e38  mov     rax, [rsp+900h+var_8B8]
0x180012e3d  mov     rcx, [rax]
0x180012e40  mov     rax, [rcx]
0x180012e43  lea     r8, [rsp+900h+var_8C8]
0x180012e48  mov     edx, esi
0x180012e4a  mov     rax, [rax+48h]
0x180012e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e53  mov     ebx, eax
0x180012e55  test    eax, eax
0x180012e57  jnz     loc_180013323
0x180012e5d  xorps   xmm0, xmm0
0x180012e60  movups  xmmword ptr [rbp+800h+var_878], xmm0
0x180012e64  movdqu  [rbp+800h+var_868], xmm6
0x180012e69  xor     ebx, ebx
0x180012e6b  mov     word ptr [rbp+800h+var_878], bx
0x180012e6f  lea     rdx, [rbp+800h+var_878]
0x180012e73  lea     rcx, [rsp+900h+var_8C8]
0x180012e78  call    ?CheckECPComponentDevice@ECPDeviceManager@EapHost@@CA_NAEAV?$CComPtr@UIUMBusPDO@@@ATL@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::ECPDeviceManager::CheckECPComponentDevice(ATL::CComPtr<IUMBusPDO> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x180012e7d  test    al, al
0x180012e7f  jz      loc_18001309C
0x180012e85  lea     r8, [rsp+900h+var_8C8]
0x180012e8a  lea     rdx, [rbp+800h+var_878]
0x180012e8e  lea     rcx, [rsp+900h+lpMem]
0x180012e93  call    ??$make_pair@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAV?$CComPtr@UIUMBusPDO@@@ATL@@@std@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEAV?$CComPtr@UIUMBusPDO@@@ATL@@@Z; std::make_pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,ATL::CComPtr<IUMBusPDO> &>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,ATL::CComPtr<IUMBusPDO> &)
0x180012e98  nop
0x180012e99  mov     r8, rax
0x180012e9c  lea     rdx, [rsp+900h+var_8B0]
0x180012ea1  mov     rcx, [rsp+900h+var_8C0]
0x180012ea6  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@1@@Z; std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>,0>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>> &&)
0x180012eab  mov     bl, [rax+8]
0x180012eae  mov     rcx, [rbp+800h+var_880]
0x180012eb2  test    rcx, rcx
0x180012eb5  jz      short loc_180012EC4
0x180012eb7  mov     rax, [rcx]
0x180012eba  mov     rax, [rax+10h]
0x180012ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec3  nop
0x180012ec4  cmp     [rsp+900h+var_888], 7
0x180012eca  jbe     short loc_180012ED6
0x180012ecc  mov     rcx, [rsp+900h+lpMem]; lpMem
0x180012ed1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012ed6  mov     rcx, cs:eaphost_Context
0x180012edd  test    bl, bl
0x180012edf  jnz     loc_180012FCD
0x180012ee5  mov     rdx, r14
0x180012ee8  call    cs:__imp_EtwEventEnabled
0x180012eee  xor     ebx, ebx
0x180012ef0  test    al, al
0x180012ef2  jz      short loc_180012F63
0x180012ef4  lea     rax, [rbp+800h+var_878]
0x180012ef8  cmp     qword ptr [rbp+800h+var_868+8], 7
0x180012efd  cmova   rax, [rbp+800h+var_878]
0x180012f02  mov     [rsp+900h+var_8E0], rax
0x180012f07  mov     r9d, esi
0x180012f0a  lea     r8, aTheDeviceIdStr; "The device id string already exists in "...
0x180012f11  mov     edx, 800h; unsigned __int64
0x180012f16  lea     rcx, [rbp+800h+var_850]; char *
0x180012f1a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012f1f  test    eax, eax
0x180012f21  js      short loc_180012F63
0x180012f23  test    cs:byte_180020AC1, 8
0x180012f2a  jz      short loc_180012F63
0x180012f2c  lea     rcx, [rbp+800h+var_850]
0x180012f30  mov     rax, r12
0x180012f33  inc     rax
0x180012f36  cmp     [rcx+rax], bl
0x180012f39  jnz     short loc_180012F33
0x180012f3b  inc     eax
0x180012f3d  lea     rcx, [rbp+800h+var_850]
0x180012f41  mov     [rsp+900h+var_890], rcx
0x180012f46  mov     dword ptr [rsp+900h+var_888], eax
0x180012f4a  mov     dword ptr [rsp+900h+var_888+4], ebx
0x180012f4e  lea     rax, [rsp+900h+lpMem]
0x180012f53  mov     [rsp+900h+var_8E0], rax
0x180012f58  mov     rdx, r14
0x180012f5b  mov     rcx, r13
0x180012f5e  call    McGenEventWrite_EtwEventWriteTransfer
0x180012f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f6a  cmp     rcx, r15
0x180012f6d  jz      short loc_180012FA0
0x180012f6f  test    byte ptr [rcx+1Ch], 1
0x180012f73  jz      short loc_180012FA0
0x180012f75  lea     rax, [rbp+800h+var_878]
0x180012f79  cmp     qword ptr [rbp+800h+var_868+8], 7
0x180012f7e  cmova   rax, [rbp+800h+var_878]
0x180012f83  mov     edx, 22h ; '"'
0x180012f88  mov     [rsp+900h+var_8E0], rax
0x180012f8d  mov     r9d, esi
0x180012f90  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180012f97  mov     rcx, [rcx+10h]
0x180012f9b  call    WPP_SF_DS
0x180012fa0  mov     rdx, [rdi+8]
0x180012fa4  cmp     rdx, [rdi+10h]
0x180012fa8  jz      loc_180013161
0x180012fae  mov     rcx, [rsp+900h+var_8C8]
0x180012fb3  mov     [rdx], rcx
0x180012fb6  test    rcx, rcx
0x180012fb9  jz      short loc_180012FC8
0x180012fbb  mov     rax, [rcx]
0x180012fbe  mov     rax, [rax+8]
0x180012fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fc7  nop
0x180012fc8  jmp     loc_18001315A
0x180012fcd  lea     rdx, DebugInfoEvent
0x180012fd4  call    cs:__imp_EtwEventEnabled
0x180012fda  xor     ebx, ebx
0x180012fdc  test    al, al
0x180012fde  jz      short loc_180013052
0x180012fe0  lea     rax, [rbp+800h+var_878]
0x180012fe4  cmp     qword ptr [rbp+800h+var_868+8], 7
0x180012fe9  cmova   rax, [rbp+800h+var_878]
0x180012fee  mov     [rsp+900h+var_8E0], rax
0x180012ff3  mov     r9d, esi
0x180012ff6  lea     r8, aDeviceAddedToC; "Device added to componentDeviceMap: ind"...
0x180012ffd  mov     edx, 800h; unsigned __int64
0x180013002  lea     rcx, [rbp+800h+var_850]; char *
0x180013006  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001300b  test    eax, eax
0x18001300d  js      short loc_180013052
0x18001300f  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180013015  jge     short loc_180013052
0x180013017  lea     rcx, [rbp+800h+var_850]
0x18001301b  mov     rax, r12
0x18001301e  inc     rax
0x180013021  cmp     [rcx+rax], bl
0x180013024  jnz     short loc_18001301E
0x180013026  inc     eax
0x180013028  lea     rcx, [rbp+800h+var_850]
0x18001302c  mov     [rsp+900h+var_890], rcx
0x180013031  mov     dword ptr [rsp+900h+var_888], eax
0x180013035  mov     dword ptr [rsp+900h+var_888+4], ebx
0x180013039  lea     rax, [rsp+900h+lpMem]
0x18001303e  mov     [rsp+900h+var_8E0], rax
0x180013043  lea     rdx, DebugInfoEvent
0x18001304a  mov     rcx, r13
0x18001304d  call    McGenEventWrite_EtwEventWriteTransfer
0x180013052  mov     rcx, cs:WPP_GLOBAL_Control
0x180013059  cmp     rcx, r15
0x18001305c  jz      loc_18001316F
0x180013062  test    byte ptr [rcx+1Ch], 4
0x180013066  jz      loc_18001316F
0x18001306c  lea     rax, [rbp+800h+var_878]
0x180013070  cmp     qword ptr [rbp+800h+var_868+8], 7
0x180013075  cmova   rax, [rbp+800h+var_878]
0x18001307a  mov     edx, 23h ; '#'
0x18001307f  mov     [rsp+900h+var_8E0], rax
0x180013084  mov     r9d, esi
0x180013087  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x18001308e  mov     rcx, [rcx+10h]
0x180013092  call    WPP_SF_DS
0x180013097  jmp     loc_18001316F
0x18001309c  mov     rdx, r14
0x18001309f  mov     rcx, cs:eaphost_Context
0x1800130a6  call    cs:__imp_EtwEventEnabled
0x1800130ac  test    al, al
0x1800130ae  jz      short loc_18001310C
0x1800130b0  mov     r9d, esi
0x1800130b3  lea     r8, aDeviceDidNotPa; "Device did not pass check, index=%u"
0x1800130ba  mov     edx, 800h; unsigned __int64
0x1800130bf  lea     rcx, [rbp+800h+var_850]; char *
0x1800130c3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800130c8  test    eax, eax
0x1800130ca  js      short loc_18001310C
0x1800130cc  test    cs:byte_180020AC1, 8
0x1800130d3  jz      short loc_18001310C
0x1800130d5  lea     rcx, [rbp+800h+var_850]
0x1800130d9  mov     rax, r12
0x1800130dc  inc     rax
0x1800130df  cmp     [rcx+rax], bl
0x1800130e2  jnz     short loc_1800130DC
0x1800130e4  inc     eax
0x1800130e6  lea     rcx, [rbp+800h+var_850]
0x1800130ea  mov     [rsp+900h+var_890], rcx
0x1800130ef  mov     dword ptr [rsp+900h+var_888], eax
0x1800130f3  mov     dword ptr [rsp+900h+var_888+4], ebx
0x1800130f7  lea     rax, [rsp+900h+lpMem]
0x1800130fc  mov     [rsp+900h+var_8E0], rax
0x180013101  mov     rdx, r14
0x180013104  mov     rcx, r13
0x180013107  call    McGenEventWrite_EtwEventWriteTransfer
0x18001310c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013113  cmp     rcx, r15
0x180013116  jz      short loc_180013136
0x180013118  test    byte ptr [rcx+1Ch], 1
0x18001311c  jz      short loc_180013136
0x18001311e  mov     edx, 24h ; '$'
0x180013123  mov     r9d, esi
0x180013126  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x18001312d  mov     rcx, [rcx+10h]
0x180013131  call    WPP_SF_d
0x180013136  mov     rdx, [rdi+8]
0x18001313a  cmp     rdx, [rdi+10h]
0x18001313e  jz      short loc_180013161
0x180013140  mov     rcx, [rsp+900h+var_8C8]
0x180013145  mov     [rdx], rcx
0x180013148  test    rcx, rcx
0x18001314b  jz      short loc_18001315A
0x18001314d  mov     rax, [rcx]
0x180013150  mov     rax, [rax+8]
0x180013154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013159  nop
0x18001315a  add     qword ptr [rdi+8], 8
0x18001315f  jmp     short loc_18001316F
0x180013161  lea     r8, [rsp+900h+var_8C8]
0x180013166  mov     rcx, rdi
0x180013169  call    ??$_Emplace_reallocate@AEBV?$CComPtr@UIUMBusPDO@@@ATL@@@?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@AEAAPEAV?$CComPtr@UIUMBusPDO@@@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CComPtr<IUMBusPDO>>::_Emplace_reallocate<ATL::CComPtr<IUMBusPDO> const &>(ATL::CComPtr<IUMBusPDO> * const,ATL::CComPtr<IUMBusPDO> const &)
0x18001316e  nop
0x18001316f  cmp     qword ptr [rbp+800h+var_868+8], 7
0x180013174  jbe     short loc_18001317F
0x180013176  mov     rcx, [rbp+800h+var_878]; lpMem
0x18001317a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001317f  movdqu  [rbp+800h+var_868], xmm6
0x180013184  mov     word ptr [rbp+800h+var_878], bx
0x180013188  mov     rcx, [rsp+900h+var_8C8]
0x18001318d  test    rcx, rcx
0x180013190  jz      short loc_18001319F
0x180013192  mov     rax, [rcx]
0x180013195  mov     rax, [rax+10h]
0x180013199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001319e  nop
0x18001319f  inc     esi
0x1800131a1  cmp     esi, dword ptr [rsp+900h+var_8D0]
0x1800131a5  jb      loc_180012E33
  ... truncated ...
```
