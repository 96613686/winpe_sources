# CPacketReceiver::ReceivePacket(uchar *,ulong,sockaddr *,unsigned __int64,_porttype_)

- ea: `0x1800151cc`
- end: `0x1800155fe`
- name: `?ReceivePacket@CPacketReceiver@@QEAAJPEAEKPEAUsockaddr@@_KW4_porttype_@@@Z`
- size: `1074`
- prototype: `int __high(unsigned __int8 *, unsigned int, struct sockaddr *, unsigned __int64, enum _porttype_)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015938`
- `0x18002ec8a`

## callees

- `0x1800094e4`
- `0x180009b10`
- `0x180009b24`
- `0x180009c80`
- `0x18000a430`
- `0x18000dc54`
- `0x18000e4e0`
- `0x180012764`
- `0x180013f90`
- `0x180014a20`
- `0x1800151cc`
- `0x180016d2c`
- `0x18001d31c`
- `0x18002819c`
- `0x1800283c0`
- `0x18002be9c`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `msvcrt!free` at `0x18001535b`
- `msvcrt!free` at `0x1800153c1`
- `msvcrt!free` at `0x1800155b5`
- `msvcrt!free` at `0x18001535b`
- `msvcrt!free` at `0x1800153c1`
- `msvcrt!free` at `0x1800155b5`
- `iassvcs!IASReportEvent` at `0x18001538c`
- `iassvcs!IASReportEvent` at `0x18001552e`
- `iassvcs!IASReportEvent` at `0x18001538c`
- `iassvcs!IASReportEvent` at `0x18001552e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015451`

## string_xrefs

- `0x18001546e`: `Unable to create Packet-Radius object during packet processing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPacketReceiver::ReceivePacket(
        __int64 a1,
        void *a2,
        unsigned int a3,
        struct sockaddr *a4,
        __int64 a5,
        int a6)
{
  int v10; // ebx
  const struct std::nothrow_t *v11; // rdx
  unsigned int v12; // r12d
  __int64 v13; // rcx
  void *v14; // rax
  CPacketRadius *v15; // rbx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+64h] [rbp-9Ch]
  unsigned int v22[2]; // [rsp+68h] [rbp-98h] BYREF
  struct IIasClient *v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  _BYTE v25[144]; // [rsp+80h] [rbp-80h] BYREF

  v22[0] = a3;
  v21 = a6;
  v20 = 0;
  v10 = ConvertFromV4MappedAddressIfNeeded(a4);
  if ( !v10 )
  {
    ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v23);
    v24 = 65;
    if ( !(unsigned int)CClients::FindObject(*(LPCRITICAL_SECTION *)(a1 + 152), a4, &v23) )
    {
      CoTaskMemFree(a2);
      v10 = ias_inet_htow(a4, v25);
      v20 = v10;
      if ( v10 >= 0 )
      {
        *(_QWORD *)v22 = v25;
        v12 = 1;
        IASReportEvent(3221225485LL, 1, 0, v22, 0);
        if ( v21 != 1 )
          v12 = 4;
        CReportEvent::Process(v13, 2, v12, a3, a4);
        if ( a4 )
          free(a4);
        v10 = -1073741801;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Error in ias_inet_htow %!hresult!\n");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
            (unsigned int)"NPSRAD",
            v20);
          v10 = v20;
        }
        if ( a4 )
          free(a4);
      }
      goto LABEL_47;
    }
    v14 = operator new[](0xB0u, v11);
    v24 = (__int64)v14;
    if ( v14 )
      v15 = (CPacketRadius *)CPacketRadius::CPacketRadius(
                               v14,
                               *(_QWORD *)(a1 + 128),
                               *(_QWORD *)(a1 + 136),
                               v23,
                               *(_QWORD *)(a1 + 160),
                               a2,
                               a3,
                               a4,
                               a5,
                               a6,
                               *(_DWORD *)(a1 + 168));
    else
      v15 = 0;
    if ( v15 )
    {
      v16 = CPacketRadius::PrelimVerification(v15, *(struct CDictionary **)(a1 + 144), v22[0]);
      v20 = v16;
      if ( v16 >= 0 )
      {
        if ( *(_QWORD *)(a1 + 104) && (unsigned int)IASRadiusIsPing(v15, (const struct RegularExpression *)(a1 + 112)) )
        {
          (**(void (__fastcall ***)(CPacketRadius *, __int64))v15)(v15, 1);
          v10 = 0;
LABEL_47:
          ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v23);
          return (unsigned int)v10;
        }
        v16 = CPreValidator::StartInValidation(*(CPreValidator **)(a1 + 120), v15);
        v20 = v16;
        if ( v16 >= 0 )
        {
LABEL_46:
          v10 = v20;
          goto LABEL_47;
        }
      }
      if ( v16 == -1073741801 )
      {
LABEL_45:
        (**(void (__fastcall ***)(CPacketRadius *, __int64))v15)(v15, 1);
        goto LABEL_46;
      }
    }
    else
    {
      CoTaskMemFree(a2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to create Packet-Radius object during packet processing");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
      }
      v20 = -2147024882;
    }
    IASReportEvent(3221225484LL, 0, 4, 0, &v20);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Silently discarding packet received from:%S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
        (unsigned int)"NPSRAD",
        (__int64)v25);
    }
    v18 = 1;
    if ( v21 != 1 )
      v18 = 4;
    CReportEvent::Process(v17, 0, v18, v22[0], a4);
    if ( !v15 )
    {
      if ( a4 )
        free(a4);
      goto LABEL_46;
    }
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("ConvertFromV4MappedAddressIfNeeded failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
      (unsigned int)"NPSRAD",
      v10);
  }
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800151cc  push    rbp
0x1800151ce  push    rbx
0x1800151cf  push    rsi
0x1800151d0  push    rdi
0x1800151d1  push    r12
0x1800151d3  push    r13
0x1800151d5  push    r14
0x1800151d7  push    r15
0x1800151d9  lea     rbp, [rsp-28h]
0x1800151de  sub     rsp, 128h
0x1800151e5  mov     rax, cs:__security_cookie
0x1800151ec  xor     rax, rsp
0x1800151ef  mov     [rbp+60h+var_50], rax
0x1800151f3  mov     rdi, r9
0x1800151f6  mov     r14d, r8d
0x1800151f9  mov     [rsp+160h+var_F8], r8d
0x1800151fe  mov     r13, rdx
0x180015201  mov     r15, rcx
0x180015204  mov     rsi, [rbp+60h+arg_20]
0x18001520b  mov     r12d, [rbp+60h+arg_28]
0x180015212  mov     [rsp+160h+var_FC], r12d
0x180015217  mov     [rsp+160h+var_100], 0
0x18001521f  mov     rcx, r9; void *
0x180015222  call    ConvertFromV4MappedAddressIfNeeded
0x180015227  mov     ebx, eax
0x180015229  test    eax, eax
0x18001522b  jz      short loc_18001529B
0x18001522d  lea     r14, WPP_GLOBAL_Control
0x180015234  mov     rax, cs:WPP_GLOBAL_Control
0x18001523b  cmp     rax, r14
0x18001523e  jz      short loc_180015285
0x180015240  cmp     byte ptr [rax+19h], 2
0x180015244  jb      short loc_180015285
0x180015246  mov     esi, 100h
0x18001524b  test    [rax+1Ch], esi
0x18001524e  jz      short loc_180015285
0x180015250  mov     edx, ebx
0x180015252  lea     rcx, aConvertfromv4m; "ConvertFromV4MappedAddressIfNeeded fail"...
0x180015259  call    WppDbgPrint
0x18001525e  mov     edx, 0Ch
0x180015263  mov     dword ptr [rsp+160h+var_140], ebx
0x180015267  lea     r9, aNpsrad; "NPSRAD"
0x18001526e  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015275  mov     rcx, cs:WPP_GLOBAL_Control
0x18001527c  mov     rcx, [rcx+10h]
0x180015280  call    WPP_SF_sd
0x180015285  test    ebx, ebx
0x180015287  jle     loc_1800155DC
0x18001528d  movzx   ebx, bx
0x180015290  or      ebx, 80070000h
0x180015296  jmp     loc_1800155DC
0x18001529b  lea     rcx, [rsp+160h+var_F0]; void *
0x1800152a0  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x1800152a5  nop
0x1800152a6  mov     [rsp+160h+var_E8], 41h ; 'A'
0x1800152af  lea     r8, [rsp+160h+var_F0]; struct IIasClient **
0x1800152b4  mov     rdx, rdi; struct sockaddr *
0x1800152b7  mov     rcx, [r15+98h]; lpCriticalSection
0x1800152be  call    ?FindObject@CClients@@QEAAHPEAUsockaddr@@PEAPEAUIIasClient@@@Z; CClients::FindObject(sockaddr *,IIasClient * *)
0x1800152c3  test    eax, eax
0x1800152c5  jnz     loc_1800153D1
0x1800152cb  mov     rcx, r13; pv
0x1800152ce  call    cs:__imp_CoTaskMemFree
0x1800152d4  lea     r8, [rsp+160h+var_E8]
0x1800152d9  lea     rdx, [rbp+60h+var_E0]; void *
0x1800152dd  mov     rcx, rdi; pSockaddr
0x1800152e0  call    ias_inet_htow
0x1800152e5  mov     ebx, eax
0x1800152e7  mov     [rsp+160h+var_100], eax
0x1800152eb  test    eax, eax
0x1800152ed  jns     short loc_180015366
0x1800152ef  lea     r14, WPP_GLOBAL_Control
0x1800152f6  mov     rax, cs:WPP_GLOBAL_Control
0x1800152fd  cmp     rax, r14
0x180015300  jz      short loc_18001534F
0x180015302  cmp     byte ptr [rax+19h], 2
0x180015306  jb      short loc_18001534F
0x180015308  mov     esi, 100h
0x18001530d  test    [rax+1Ch], esi
0x180015310  jz      short loc_18001534F
0x180015312  mov     edx, ebx
0x180015314  lea     rcx, aErrorInIasInet; "Error in ias_inet_htow %!hresult!\n"
0x18001531b  call    WppDbgPrint
0x180015320  mov     edx, 0Dh
0x180015325  mov     eax, [rsp+160h+var_100]
0x180015329  mov     dword ptr [rsp+160h+var_140], eax
0x18001532d  lea     r9, aNpsrad; "NPSRAD"
0x180015334  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x18001533b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015342  mov     rcx, [rcx+10h]
0x180015346  call    WPP_SF_sd
0x18001534b  mov     ebx, [rsp+160h+var_100]
0x18001534f  test    rdi, rdi
0x180015352  jz      loc_1800155D2
0x180015358  mov     rcx, rdi; Block
0x18001535b  call    cs:__imp_free
0x180015361  jmp     loc_1800155D2
0x180015366  lea     rax, [rbp+60h+var_E0]
0x18001536a  mov     qword ptr [rsp+160h+var_F8], rax
0x18001536f  mov     [rsp+160h+var_140], 0
0x180015378  lea     r9, [rsp+160h+var_F8]
0x18001537d  xor     r8d, r8d
0x180015380  lea     r12d, [r8+1]
0x180015384  mov     edx, r12d
0x180015387  mov     ecx, 0C000000Dh
0x18001538c  call    cs:__imp_IASReportEvent
0x180015392  lea     r15d, [r12+3]
0x180015397  cmp     [rsp+160h+var_FC], r12d
0x18001539c  cmovnz  r12d, r15d
0x1800153a0  mov     [rsp+160h+var_130], r13
0x1800153a5  mov     [rsp+160h+var_140], rdi
0x1800153aa  mov     r9d, r14d
0x1800153ad  mov     r8d, r12d
0x1800153b0  lea     edx, [r15-2]
0x1800153b4  call    ?Process@CReportEvent@@QEAAXW4_radiuslogtype_@@W4_packettype_@@KPEAUsockaddr@@PEBGPEAX@Z; CReportEvent::Process(_radiuslogtype_,_packettype_,ulong,sockaddr *,ushort const *,void *)
0x1800153b9  test    rdi, rdi
0x1800153bc  jz      short loc_1800153C7
0x1800153be  mov     rcx, rdi; Block
0x1800153c1  call    cs:__imp_free
0x1800153c7  mov     ebx, 0C0000017h
0x1800153cc  jmp     loc_1800155D2
0x1800153d1  mov     ecx, 0B0h; Size
0x1800153d6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800153db  mov     [rsp+160h+var_E8], rax
0x1800153e0  test    rax, rax
0x1800153e3  jz      short loc_180015435
0x1800153e5  mov     ecx, [r15+0A8h]
0x1800153ec  mov     [rsp+160h+var_110], ecx
0x1800153f0  mov     [rsp+160h+var_118], r12d
0x1800153f5  mov     [rsp+160h+var_120], rsi
0x1800153fa  mov     [rsp+160h+var_128], rdi
0x1800153ff  mov     dword ptr [rsp+160h+var_130], r14d
0x180015404  mov     [rsp+160h+var_138], r13
0x180015409  mov     rcx, [r15+0A0h]
0x180015410  mov     [rsp+160h+var_140], rcx
0x180015415  mov     r9, [rsp+160h+var_F0]
0x18001541a  mov     r8, [r15+88h]
0x180015421  mov     rdx, [r15+80h]
0x180015428  mov     rcx, rax
0x18001542b  call    ??0CPacketRadius@@QEAA@PEAVCHashMD5@@PEAVCHashHmacMD5@@PEAUIIasClient@@PEAVCReportEvent@@PEAEKPEAUsockaddr@@_KW4_porttype_@@H@Z; CPacketRadius::CPacketRadius(CHashMD5 *,CHashHmacMD5 *,IIasClient *,CReportEvent *,uchar *,ulong,sockaddr *,unsigned __int64,_porttype_,int)
0x180015430  mov     rbx, rax
0x180015433  jmp     short loc_180015437
0x180015435  xor     ebx, ebx
0x180015437  mov     r12d, 1
0x18001543d  lea     r14, WPP_GLOBAL_Control
0x180015444  mov     esi, 100h
0x180015449  test    rbx, rbx
0x18001544c  jnz     short loc_1800154A5
0x18001544e  mov     rcx, r13; pv
0x180015451  call    cs:__imp_CoTaskMemFree
0x180015457  mov     rax, cs:WPP_GLOBAL_Control
0x18001545e  cmp     rax, r14
0x180015461  jz      short loc_18001549B
0x180015463  cmp     byte ptr [rax+19h], 2
0x180015467  jb      short loc_18001549B
0x180015469  test    [rax+1Ch], esi
0x18001546c  jz      short loc_18001549B
0x18001546e  lea     rcx, aUnableToCreate_8; "Unable to create Packet-Radius object d"...
0x180015475  call    WppDbgPrint
0x18001547a  lea     edx, [rbx+0Eh]
0x18001547d  lea     r9, aNpsrad; "NPSRAD"
0x180015484  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x18001548b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015492  mov     rcx, [rcx+10h]
0x180015496  call    WPP_SF_s
0x18001549b  mov     [rsp+160h+var_100], 8007000Eh
0x1800154a3  jmp     short loc_180015513
0x1800154a5  mov     r8d, [rsp+160h+var_F8]; unsigned int
0x1800154aa  mov     rdx, [r15+90h]; struct CDictionary *
0x1800154b1  mov     rcx, rbx; this
0x1800154b4  call    ?PrelimVerification@CPacketRadius@@QEAAJPEAVCDictionary@@K@Z; CPacketRadius::PrelimVerification(CDictionary *,ulong)
0x1800154b9  mov     [rsp+160h+var_100], eax
0x1800154bd  test    eax, eax
0x1800154bf  js      short loc_180015508
0x1800154c1  cmp     qword ptr [r15+68h], 0
0x1800154c6  jz      short loc_1800154F0
0x1800154c8  lea     rdx, [r15+70h]; struct RegularExpression *
0x1800154cc  mov     rcx, rbx; this
0x1800154cf  call    ?IASRadiusIsPing@@YAHAEAVCPacketRadius@@AEBVRegularExpression@@@Z; IASRadiusIsPing(CPacketRadius &,RegularExpression const &)
0x1800154d4  test    eax, eax
0x1800154d6  jz      short loc_1800154F0
0x1800154d8  mov     rax, [rbx]
0x1800154db  mov     edx, r12d
0x1800154de  mov     rcx, rbx
0x1800154e1  mov     rax, [rax]
0x1800154e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154e9  xor     ebx, ebx
0x1800154eb  jmp     loc_1800155D2
0x1800154f0  mov     rdx, rbx; struct CPacketRadius *
0x1800154f3  mov     rcx, [r15+78h]; this
0x1800154f7  call    ?StartInValidation@CPreValidator@@QEAAJPEAVCPacketRadius@@@Z; CPreValidator::StartInValidation(CPacketRadius *)
0x1800154fc  mov     [rsp+160h+var_100], eax
0x180015500  test    eax, eax
0x180015502  jns     loc_1800155CE
0x180015508  cmp     eax, 0C0000017h
0x18001550d  jz      loc_1800155BD
0x180015513  lea     rax, [rsp+160h+var_100]
0x180015518  mov     [rsp+160h+var_140], rax
0x18001551d  xor     r9d, r9d
0x180015520  lea     r15d, [r9+4]
0x180015524  mov     r8d, r15d
0x180015527  xor     edx, edx
0x180015529  mov     ecx, 0C000000Ch
0x18001552e  call    cs:__imp_IASReportEvent
0x180015534  mov     rax, cs:WPP_GLOBAL_Control
0x18001553b  cmp     rax, r14
0x18001553e  jz      short loc_180015586
0x180015540  cmp     byte ptr [rax+19h], 2
0x180015544  jb      short loc_180015586
0x180015546  test    [rax+1Ch], esi
0x180015549  jz      short loc_180015586
0x18001554b  lea     rdx, [rbp+60h+var_E0]
0x18001554f  lea     rcx, aSilentlyDiscar; "Silently discarding packet received fro"...
0x180015556  call    WppDbgPrint
0x18001555b  lea     edx, [r15+0Bh]
0x18001555f  lea     rax, [rbp+60h+var_E0]
0x180015563  mov     [rsp+160h+var_140], rax
0x180015568  lea     r9, aNpsrad; "NPSRAD"
0x18001556f  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015576  mov     rcx, cs:WPP_GLOBAL_Control
0x18001557d  mov     rcx, [rcx+10h]
0x180015581  call    WPP_SF_sS
0x180015586  mov     r8d, r12d
0x180015589  cmp     [rsp+160h+var_FC], r12d
0x18001558e  cmovnz  r8d, r15d
0x180015592  mov     [rsp+160h+var_130], r13
0x180015597  mov     [rsp+160h+var_140], rdi
0x18001559c  mov     r9d, [rsp+160h+var_F8]
0x1800155a1  xor     edx, edx
0x1800155a3  call    ?Process@CReportEvent@@QEAAXW4_radiuslogtype_@@W4_packettype_@@KPEAUsockaddr@@PEBGPEAX@Z; CReportEvent::Process(_radiuslogtype_,_packettype_,ulong,sockaddr *,ushort const *,void *)
0x1800155a8  test    rbx, rbx
0x1800155ab  jnz     short loc_1800155BD
0x1800155ad  test    rdi, rdi
0x1800155b0  jz      short loc_1800155CE
0x1800155b2  mov     rcx, rdi; Block
0x1800155b5  call    cs:__imp_free
0x1800155bb  jmp     short loc_1800155CE
0x1800155bd  mov     rax, [rbx]
0x1800155c0  mov     edx, r12d
0x1800155c3  mov     rcx, rbx
0x1800155c6  mov     rax, [rax]
0x1800155c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ce  mov     ebx, [rsp+160h+var_100]
0x1800155d2  lea     rcx, [rsp+160h+var_F0]
0x1800155d7  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800155dc  mov     eax, ebx
0x1800155de  mov     rcx, [rbp+60h+var_50]
0x1800155e2  xor     rcx, rsp; StackCookie
0x1800155e5  call    __security_check_cookie
0x1800155ea  add     rsp, 128h
0x1800155f1  pop     r15
0x1800155f3  pop     r14
0x1800155f5  pop     r13
0x1800155f7  pop     r12
0x1800155f9  pop     rdi
0x1800155fa  pop     rsi
0x1800155fb  pop     rbx
0x1800155fc  pop     rbp
0x1800155fd  retn
```
