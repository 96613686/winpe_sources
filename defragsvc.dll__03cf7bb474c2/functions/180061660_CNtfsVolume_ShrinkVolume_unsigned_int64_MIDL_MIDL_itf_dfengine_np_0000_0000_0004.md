# CNtfsVolume::ShrinkVolume(unsigned __int64,__MIDL___MIDL_itf_dfengine_np_0000_0000_0004)

- ea: `0x180061660`
- end: `0x180061a6d`
- name: `?ShrinkVolume@CNtfsVolume@@UEAAJ_KW4__MIDL___MIDL_itf_dfengine_np_0000_0000_0004@@@Z`
- size: `1037`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800029a8`
- `0x180006400`
- `0x18000ad50`
- `0x1800156a0`
- `0x180038c3c`
- `0x18004b73c`
- `0x180061660`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006179d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006187b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006179d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006187b`
- `ntdll!RtlGetLastNtStatus` at `0x1800617ae`
- `ntdll!RtlGetLastNtStatus` at `0x180061889`
- `ntdll!RtlGetLastNtStatus` at `0x1800617ae`
- `ntdll!RtlGetLastNtStatus` at `0x180061889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800616be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800616be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsVolume::ShrinkVolume(__int64 a1, __int64 a2, int a3)
{
  int v6; // ebx
  unsigned int LastNtStatus; // esi
  CSxGlobalTracer *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD *v11; // r14
  CSxGlobalTracer *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int16 v15; // ax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int16 v19[2]; // [rsp+70h] [rbp-49h] BYREF
  DWORD BytesReturned; // [rsp+74h] [rbp-45h] BYREF
  int v21; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v22; // [rsp+7Ch] [rbp-3Dh] BYREF
  int v23; // [rsp+80h] [rbp-39h] BYREF
  int v24; // [rsp+84h] [rbp-35h] BYREF
  int v25; // [rsp+88h] [rbp-31h] BYREF
  __int64 InBuffer; // [rsp+90h] [rbp-29h] BYREF
  int v27; // [rsp+98h] [rbp-21h] BYREF
  __int16 v28; // [rsp+9Ch] [rbp-1Dh]
  __int16 v29; // [rsp+9Eh] [rbp-1Bh]
  __int64 v30; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v31; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v32; // [rsp+E0h] [rbp+27h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "CNtfsVolume::ShrinkVolume", 940, 1);
  InBuffer = 0;
  BytesReturned = 0;
  v6 = 0;
  v33 = 0;
  LastNtStatus = 0;
  v11 = CoTaskMemAlloc(0x18u);
  if ( !v11 )
  {
    v27 = -2147024882;
    v29 = 953;
    goto LABEL_42;
  }
  v27 = 0;
  v28 = 953;
  if ( a3 )
  {
    if ( a3 == 1 )
    {
      v14 = a2 * *(unsigned int *)(a1 + 520);
      InBuffer = v14;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e997f3a212193354f3db96f04e525e21_Traceguids, v14);
      }
      if ( !DeviceIoControl(*(HANDLE *)(a1 + 40), 0x56C05Cu, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
      {
        v33 = 1;
        LastNtStatus = RtlGetLastNtStatus();
        v27 = HRESULTFromNTSTATUS(LastNtStatus);
        v15 = 982;
        if ( v27 < 0 )
          goto LABEL_40;
        v28 = 982;
      }
      *(_DWORD *)v11 = 2;
      v11[2] = 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v13 = 18;
        goto LABEL_20;
      }
    }
    else
    {
      *(_DWORD *)v11 = 3;
      v11[2] = 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v13 = 19;
LABEL_20:
        WPP_SF_i(*((_QWORD *)v12 + 2), v13, WPP_e997f3a212193354f3db96f04e525e21_Traceguids, a2);
      }
    }
  }
  else
  {
    *(_DWORD *)v11 = 1;
    v11[2] = a2;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      v13 = 16;
      goto LABEL_20;
    }
  }
  v11[1] = 0;
  if ( !DeviceIoControl(*(HANDLE *)(a1 + 40), 0x901B0u, v11, 0x18u, 0, 0, &BytesReturned, 0) )
  {
    v16 = RtlGetLastNtStatus();
    LastNtStatus = v16;
    if ( v16 == -1073741810 )
      goto LABEL_36;
    if ( v16 + 1073741791 <= 1 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_e997f3a212193354f3db96f04e525e21_Traceguids);
      }
      v27 = -1996488671;
      v15 = 1030;
      goto LABEL_40;
    }
    if ( v16 == -1073741774 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e997f3a212193354f3db96f04e525e21_Traceguids);
      }
      v27 = -1996488675;
      v15 = 1024;
      goto LABEL_40;
    }
    if ( v16 == -1073741202 )
    {
LABEL_36:
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e997f3a212193354f3db96f04e525e21_Traceguids);
      }
      v27 = -1996488687;
      v15 = 1019;
    }
    else
    {
      v27 = HRESULTFromNTSTATUS(v16);
      v15 = 1034;
      if ( v27 >= 0 )
      {
        v28 = 1034;
        goto LABEL_41;
      }
    }
LABEL_40:
    v29 = v15;
  }
LABEL_41:
  v6 = v33;
LABEL_42:
  if ( (unsigned int)dword_1800840E0 > 5 )
  {
    v21 = v27;
    v19[0] = v29;
    v22 = LastNtStatus;
    v30 = a2;
    v23 = *(_DWORD *)(a1 + 520);
    LOBYTE(v33) = a3;
    v24 = v6;
    v31 = *(const unsigned __int16 **)(a1 + 48);
    v25 = 2;
    v32 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (__int64)byte_1800786F3,
      v9,
      v10,
      (__int64)&v32,
      (__int64)&v25,
      &v31,
      (__int64)&v24,
      (__int64)&v33,
      (__int64)&v23,
      (__int64)&v30,
      (__int64)&v22,
      (__int64)v19,
      (__int64)&v21);
  }
  CoTaskMemFree(v11);
  v17 = v27;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v17;
}

```

## disassembly

```asm
0x180061660  mov     [rsp-8+arg_0], rbx
0x180061665  mov     [rsp-8+arg_8], rsi
0x18006166a  push    rbp
0x18006166b  push    r12
0x18006166d  push    r13
0x18006166f  push    r14
0x180061671  push    r15
0x180061673  lea     rbp, [rsp-37h]
0x180061678  sub     rsp, 0F0h
0x18006167f  mov     r12d, r8d
0x180061682  mov     r15, rdx
0x180061685  mov     r13, rcx
0x180061688  mov     r9d, 1; unsigned __int16
0x18006168e  mov     r8d, 3ACh; unsigned __int16
0x180061694  lea     rdx, aCntfsvolumeShr; "CNtfsVolume::ShrinkVolume"
0x18006169b  lea     rcx, [rbp+57h+var_78]; this
0x18006169f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800616a4  nop
0x1800616a5  mov     [rbp+57h+InBuffer], 0
0x1800616ad  mov     [rbp+57h+BytesReturned], 0
0x1800616b4  xor     ebx, ebx
0x1800616b6  mov     [rbp+57h+arg_18], ebx
0x1800616b9  xor     esi, esi
0x1800616bb  lea     ecx, [rbx+18h]; cb
0x1800616be  call    cs:__imp_CoTaskMemAlloc
0x1800616c4  mov     r14, rax
0x1800616c7  test    rax, rax
0x1800616ca  mov     eax, 3B9h
0x1800616cf  jnz     short loc_1800616E1
0x1800616d1  mov     [rbp+57h+var_78], 8007000Eh
0x1800616d8  mov     [rbp+57h+var_72], ax
0x1800616dc  jmp     loc_180061987
0x1800616e1  mov     [rbp+57h+var_78], ebx
0x1800616e4  mov     [rbp+57h+var_74], ax
0x1800616e8  lea     rax, WPP_e997f3a212193354f3db96f04e525e21_Traceguids
0x1800616ef  test    r12d, r12d
0x1800616f2  jz      loc_180061803
0x1800616f8  cmp     r12d, 1
0x1800616fc  jz      short loc_180061737
0x1800616fe  mov     dword ptr [r14], 3
0x180061705  mov     [r14+10h], rbx
0x180061709  lea     rbx, WPP_GLOBAL_Control
0x180061710  mov     rcx, cs:WPP_GLOBAL_Control
0x180061717  cmp     rcx, rbx
0x18006171a  jz      loc_18006183E
0x180061720  test    dword ptr [rcx+1Ch], 800h
0x180061727  jz      loc_18006183E
0x18006172d  mov     edx, 13h
0x180061732  jmp     loc_18006182F
0x180061737  mov     r9d, [r13+208h]
0x18006173e  imul    r9, r15
0x180061742  mov     [rbp+57h+InBuffer], r9
0x180061746  lea     rbx, WPP_GLOBAL_Control
0x18006174d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061754  cmp     rcx, rbx
0x180061757  jz      short loc_180061773
0x180061759  test    dword ptr [rcx+1Ch], 800h
0x180061760  jz      short loc_180061773
0x180061762  mov     edx, 11h
0x180061767  mov     r8, rax
0x18006176a  mov     rcx, [rcx+10h]
0x18006176e  call    WPP_SF_i
0x180061773  xor     ecx, ecx
0x180061775  mov     [rsp+110h+lpOverlapped], rcx; lpOverlapped
0x18006177a  lea     rax, [rbp+57h+BytesReturned]
0x18006177e  mov     [rsp+110h+lpBytesReturned], rax; lpBytesReturned
0x180061783  mov     [rsp+110h+nOutBufferSize], ecx; nOutBufferSize
0x180061787  mov     [rsp+110h+lpOutBuffer], rcx; lpOutBuffer
0x18006178c  lea     r9d, [rcx+8]; nInBufferSize
0x180061790  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180061794  mov     edx, 56C05Ch; dwIoControlCode
0x180061799  mov     rcx, [r13+28h]; hDevice
0x18006179d  call    cs:__imp_DeviceIoControl
0x1800617a3  test    eax, eax
0x1800617a5  jnz     short loc_1800617D1
0x1800617a7  mov     [rbp+57h+arg_18], 1
0x1800617ae  call    cs:__imp_RtlGetLastNtStatus
0x1800617b4  mov     esi, eax
0x1800617b6  mov     ecx, eax
0x1800617b8  call    HRESULTFromNTSTATUS
0x1800617bd  mov     [rbp+57h+var_78], eax
0x1800617c0  test    eax, eax
0x1800617c2  mov     eax, 3D6h
0x1800617c7  js      loc_180061980
0x1800617cd  mov     [rbp+57h+var_74], ax
0x1800617d1  mov     dword ptr [r14], 2
0x1800617d8  mov     qword ptr [r14+10h], 0
0x1800617e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617e7  cmp     rcx, rbx
0x1800617ea  jz      short loc_18006183E
0x1800617ec  test    dword ptr [rcx+1Ch], 800h
0x1800617f3  jz      short loc_18006183E
0x1800617f5  mov     edx, 12h
0x1800617fa  lea     r8, WPP_e997f3a212193354f3db96f04e525e21_Traceguids
0x180061801  jmp     short loc_180061832
0x180061803  mov     dword ptr [r14], 1
0x18006180a  mov     [r14+10h], r15
0x18006180e  lea     rbx, WPP_GLOBAL_Control
0x180061815  mov     rcx, cs:WPP_GLOBAL_Control
0x18006181c  cmp     rcx, rbx
0x18006181f  jz      short loc_18006183E
0x180061821  test    dword ptr [rcx+1Ch], 800h
0x180061828  jz      short loc_18006183E
0x18006182a  mov     edx, 10h
0x18006182f  mov     r8, rax
0x180061832  mov     r9, r15
0x180061835  mov     rcx, [rcx+10h]
0x180061839  call    WPP_SF_i
0x18006183e  mov     qword ptr [r14+8], 0
0x180061846  mov     [rsp+110h+lpOverlapped], 0; lpOverlapped
0x18006184f  lea     rax, [rbp+57h+BytesReturned]
0x180061853  mov     [rsp+110h+lpBytesReturned], rax; lpBytesReturned
0x180061858  mov     [rsp+110h+nOutBufferSize], 0; nOutBufferSize
0x180061860  mov     [rsp+110h+lpOutBuffer], 0; lpOutBuffer
0x180061869  mov     r9d, 18h; nInBufferSize
0x18006186f  mov     r8, r14; lpInBuffer
0x180061872  mov     edx, 901B0h; dwIoControlCode
0x180061877  mov     rcx, [r13+28h]; hDevice
0x18006187b  call    cs:__imp_DeviceIoControl
0x180061881  test    eax, eax
0x180061883  jnz     loc_180061984
0x180061889  call    cs:__imp_RtlGetLastNtStatus
0x18006188f  mov     esi, eax
0x180061891  cmp     eax, 0C000000Eh
0x180061896  jz      loc_18006194A
0x18006189c  add     eax, 3FFFFFDFh
0x1800618a1  cmp     eax, 1
0x1800618a4  jbe     short loc_180061912
0x1800618a6  cmp     esi, 0C0000032h
0x1800618ac  jz      short loc_1800618DA
0x1800618ae  cmp     esi, 0C000026Eh
0x1800618b4  jz      loc_18006194A
0x1800618ba  mov     ecx, esi
0x1800618bc  call    HRESULTFromNTSTATUS
0x1800618c1  mov     [rbp+57h+var_78], eax
0x1800618c4  test    eax, eax
0x1800618c6  mov     eax, 40Ah
0x1800618cb  js      loc_180061980
0x1800618d1  mov     [rbp+57h+var_74], ax
0x1800618d5  jmp     loc_180061984
0x1800618da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800618e1  cmp     rcx, rbx
0x1800618e4  jz      short loc_180061904
0x1800618e6  test    dword ptr [rcx+1Ch], 2000000h
0x1800618ed  jz      short loc_180061904
0x1800618ef  mov     edx, 15h
0x1800618f4  lea     r8, WPP_e997f3a212193354f3db96f04e525e21_Traceguids
0x1800618fb  mov     rcx, [rcx+10h]
0x1800618ff  call    WPP_SF_
0x180061904  mov     [rbp+57h+var_78], 8900001Dh
0x18006190b  mov     eax, 400h
0x180061910  jmp     short loc_180061980
0x180061912  mov     rcx, cs:WPP_GLOBAL_Control
0x180061919  cmp     rcx, rbx
0x18006191c  jz      short loc_18006193C
0x18006191e  test    dword ptr [rcx+1Ch], 2000000h
0x180061925  jz      short loc_18006193C
0x180061927  mov     edx, 16h
0x18006192c  lea     r8, WPP_e997f3a212193354f3db96f04e525e21_Traceguids
0x180061933  mov     rcx, [rcx+10h]
0x180061937  call    WPP_SF_
0x18006193c  mov     [rbp+57h+var_78], 89000021h
0x180061943  mov     eax, 406h
0x180061948  jmp     short loc_180061980
0x18006194a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061951  cmp     rcx, rbx
0x180061954  jz      short loc_180061974
0x180061956  test    dword ptr [rcx+1Ch], 2000000h
0x18006195d  jz      short loc_180061974
0x18006195f  mov     edx, 14h
0x180061964  lea     r8, WPP_e997f3a212193354f3db96f04e525e21_Traceguids
0x18006196b  mov     rcx, [rcx+10h]
0x18006196f  call    WPP_SF_
0x180061974  mov     [rbp+57h+var_78], 89000011h
0x18006197b  mov     eax, 3FBh
0x180061980  mov     [rbp+57h+var_72], ax
0x180061984  mov     ebx, [rbp+57h+arg_18]
0x180061987  mov     eax, cs:dword_1800840E0
0x18006198d  cmp     eax, 5
0x180061990  jbe     loc_180061A39
0x180061996  mov     eax, [rbp+57h+var_78]
0x180061999  mov     [rbp+57h+var_98], eax
0x18006199c  movzx   eax, [rbp+57h+var_72]
0x1800619a0  mov     [rbp+57h+var_A0], ax
0x1800619a4  mov     [rbp+57h+var_94], esi
0x1800619a7  mov     [rbp+57h+var_40], r15
0x1800619ab  mov     eax, [r13+208h]
0x1800619b2  mov     [rbp+57h+var_90], eax
0x1800619b5  mov     byte ptr [rbp+57h+arg_18], r12b
0x1800619b9  mov     [rbp+57h+var_8C], ebx
0x1800619bc  mov     rax, [r13+30h]
0x1800619c0  mov     [rbp+57h+var_38], rax
0x1800619c4  mov     [rbp+57h+var_88], 2
0x1800619cb  mov     [rbp+57h+var_30], 1000000h
0x1800619d3  lea     rax, [rbp+57h+var_98]
0x1800619d7  mov     [rsp+110h+var_A8], rax
0x1800619dc  lea     rax, [rbp+57h+var_A0]
0x1800619e0  mov     [rsp+110h+var_B0], rax
0x1800619e5  lea     rax, [rbp+57h+var_94]
0x1800619e9  mov     [rsp+110h+var_B8], rax
0x1800619ee  lea     rax, [rbp+57h+var_40]
0x1800619f2  mov     [rsp+110h+var_C0], rax
0x1800619f7  lea     rax, [rbp+57h+var_90]
0x1800619fb  mov     [rsp+110h+var_C8], rax
0x180061a00  lea     rax, [rbp+57h+arg_18]
0x180061a04  mov     [rsp+110h+var_D0], rax
0x180061a09  lea     rax, [rbp+57h+var_8C]
0x180061a0d  mov     [rsp+110h+lpOverlapped], rax
0x180061a12  lea     rax, [rbp+57h+var_38]
0x180061a16  mov     [rsp+110h+lpBytesReturned], rax
0x180061a1b  lea     rax, [rbp+57h+var_88]
0x180061a1f  mov     qword ptr [rsp+110h+nOutBufferSize], rax
0x180061a24  lea     rax, [rbp+57h+var_30]
0x180061a28  mov     [rsp+110h+lpOutBuffer], rax
0x180061a2d  lea     rdx, byte_1800786F3
0x180061a34  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$00@@U2@U1@U2@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$00@@434AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180061a39  mov     rcx, r14; pv
0x180061a3c  call    cs:__imp_CoTaskMemFree
0x180061a42  mov     ebx, [rbp+57h+var_78]
0x180061a45  lea     rcx, [rbp+57h+var_78]; this
0x180061a49  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180061a4e  mov     eax, ebx
0x180061a50  lea     r11, [rsp+110h+var_20]
0x180061a58  mov     rbx, [r11+30h]
0x180061a5c  mov     rsi, [r11+38h]
0x180061a60  mov     rsp, r11
0x180061a63  pop     r15
0x180061a65  pop     r14
0x180061a67  pop     r13
0x180061a69  pop     r12
0x180061a6b  pop     rbp
0x180061a6c  retn
```
