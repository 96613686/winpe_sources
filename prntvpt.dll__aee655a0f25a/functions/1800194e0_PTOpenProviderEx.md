# PTOpenProviderEx

- ea: `0x1800194e0`
- end: `0x1800196b5`
- name: `PTOpenProviderEx`
- size: `469`
- prototype: `HRESULT __stdcall(PCWSTR pszPrinterName, DWORD dwMaxVersion, DWORD dwPrefVersion, HPTPROVIDER *phProvider, DWORD *pUsedVersion)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x18000b42c`
- `0x18000ba64`
- `0x18000f53c`
- `0x18000f970`
- `0x180018838`
- `0x1800188d8`
- `0x1800189c8`
- `0x180018d08`
- `0x1800194e0`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019552`
- `OLEAUT32!__imp_SysAllocString` at `0x180019552`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019662`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019662`

## pseudocode

```c
HRESULT __stdcall PTOpenProviderEx(
        PCWSTR pszPrinterName,
        DWORD dwMaxVersion,
        DWORD dwPrefVersion,
        HPTPROVIDER *phProvider,
        DWORD *pUsedVersion)
{
  HPTPROVIDER v5; // r14
  BSTR v9; // rax
  ULONGLONG v10; // rsi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int COMStateTLSSlot; // ebx
  int ModernPrinterType; // eax
  unsigned int v16; // edi
  int v17; // r12d
  void *v18; // rax
  int v20; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-44h] BYREF
  DWORD v22; // [rsp+38h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+40h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+50h] [rbp-28h] BYREF

  v5 = 0;
  v22 = dwPrefVersion;
  if ( !pszPrinterName || !phProvider || !pUsedVersion )
    return -2147024809;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (int)pszPrinterName,
      (int)&DocPerf_PrintTicket_OpenProvider_Start,
      dwPrefVersion,
      (int)phProvider,
      &v24);
  v9 = SysAllocString(pszPrinterName);
  v24.Ptr = 0;
  v10 = (ULONGLONG)v9;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v24);
  v24.Ptr = v10;
  v21 = 0;
  v20 = 0;
  if ( v10 )
  {
    COMStateTLSSlot = ReadCOMStateTLSSlot((enum EPTCallType::_enum *)&v20);
    if ( COMStateTLSSlot >= 0 )
    {
      COMStateTLSSlot = MyCoInit(&v21, (unsigned int)v20);
      if ( COMStateTLSSlot >= 0 )
      {
        v23.Ptr = 0;
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v23);
        v23.Ptr = 0;
        v20 = 0;
        COMStateTLSSlot = CreatePTServiceObject(pszPrinterName, (LPVOID *)&v23, &v20);
        if ( COMStateTLSSlot >= 0 )
          COMStateTLSSlot = (*(__int64 (__fastcall **)(ULONGLONG, ULONGLONG, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v23.Ptr + 32LL))(
                              v23.Ptr,
                              v10,
                              dwMaxVersion,
                              v22,
                              pUsedVersion);
        ModernPrinterType = GetModernPrinterType(pszPrinterName);
        v16 = v21;
        v17 = ModernPrinterType;
        if ( COMStateTLSSlot < 0
          || (v18 = operator new(0x38u)) != 0
          && (v5 = (HPTPROVIDER)CPrintTicketHandle::CPrintTicketHandle(v18, v23.Ptr, v16, (unsigned int)v20, v17, v10)) != 0 )
        {
          *phProvider = v5;
          v24.Ptr = 0;
        }
        else
        {
          COMStateTLSSlot = -2147024882;
        }
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v23);
        if ( COMStateTLSSlot < 0 && v16 )
          CoUninitialize();
      }
    }
  }
  else
  {
    COMStateTLSSlot = -2147024882;
  }
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, (int)&DocPerf_PrintTicket_OpenProvider_Stop, v12, v13, &v23);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v24);
  return COMStateTLSSlot;
}

```

## disassembly

```asm
0x1800194e0  push    rbp
0x1800194e2  push    rbx
0x1800194e3  push    rsi
0x1800194e4  push    rdi
0x1800194e5  push    r12
0x1800194e7  push    r13
0x1800194e9  push    r14
0x1800194eb  push    r15
0x1800194ed  mov     rbp, rsp
0x1800194f0  sub     rsp, 78h
0x1800194f4  mov     rax, cs:__security_cookie
0x1800194fb  xor     rax, rsp
0x1800194fe  mov     [rbp+var_18], rax
0x180019502  mov     r12, [rbp+pUsedVersion]
0x180019506  xor     r14d, r14d
0x180019509  mov     [rbp+var_40], r8d
0x18001950d  mov     r15, r9
0x180019510  mov     r13d, edx
0x180019513  mov     rdi, rcx
0x180019516  test    rcx, rcx
0x180019519  jz      loc_180019693
0x18001951f  test    r9, r9
0x180019522  jz      loc_180019693
0x180019528  test    r12, r12
0x18001952b  jz      loc_180019693
0x180019531  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180019538  jz      short loc_18001954F
0x18001953a  lea     rax, [rbp+var_28]
0x18001953e  lea     rdx, DocPerf_PrintTicket_OpenProvider_Start; int
0x180019545  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x18001954a  call    McGenEventWrite_EventWriteTransfer
0x18001954f  mov     rcx, rdi; psz
0x180019552  call    cs:__imp_SysAllocString
0x180019558  lea     rcx, [rbp+var_28]
0x18001955c  mov     [rbp+var_28.Ptr], r14
0x180019560  mov     rsi, rax
0x180019563  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180019568  mov     [rbp+var_28.Ptr], rsi
0x18001956c  mov     [rbp+var_44], r14d
0x180019570  mov     [rbp+var_48], r14d
0x180019574  test    rsi, rsi
0x180019577  jnz     short loc_180019583
0x180019579  mov     ebx, 8007000Eh
0x18001957e  jmp     loc_180019668
0x180019583  lea     rcx, [rbp+var_48]; enum EPTCallType::_enum *
0x180019587  call    ?ReadCOMStateTLSSlot@@YAJPEAW4_enum@EPTCallType@@@Z; ReadCOMStateTLSSlot(EPTCallType::_enum *)
0x18001958c  mov     ebx, eax
0x18001958e  test    eax, eax
0x180019590  js      loc_180019668
0x180019596  mov     edx, [rbp+var_48]
0x180019599  lea     rcx, [rbp+var_44]
0x18001959d  call    ?MyCoInit@@YAJPEAHW4_enum@EPTCallType@@@Z; MyCoInit(int *,EPTCallType::_enum)
0x1800195a2  mov     ebx, eax
0x1800195a4  test    eax, eax
0x1800195a6  js      loc_180019668
0x1800195ac  xor     ebx, ebx
0x1800195ae  lea     rcx, [rbp+var_38]
0x1800195b2  mov     [rbp+var_38.Ptr], rbx
0x1800195b6  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800195bb  lea     r8, [rbp+var_48]; int *
0x1800195bf  mov     [rbp+var_38.Ptr], rbx
0x1800195c3  lea     rdx, [rbp+var_38]; ppv
0x1800195c7  mov     [rbp+var_48], ebx
0x1800195ca  mov     rcx, rdi; unsigned __int16 *
0x1800195cd  call    ?CreatePTServiceObject@@YAJPEBGPEAPEAUIPrintTicketService@@PEAH@Z; CreatePTServiceObject(ushort const *,IPrintTicketService * *,int *)
0x1800195d2  mov     ebx, eax
0x1800195d4  test    eax, eax
0x1800195d6  js      short loc_1800195F9
0x1800195d8  mov     rcx, [rbp+var_38.Ptr]
0x1800195dc  mov     r8d, r13d
0x1800195df  mov     r9d, [rbp+var_40]
0x1800195e3  mov     rdx, rsi
0x1800195e6  mov     [rsp+78h+var_58], r12
0x1800195eb  mov     rax, [rcx]
0x1800195ee  mov     rax, [rax+20h]
0x1800195f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f7  mov     ebx, eax
0x1800195f9  mov     rcx, rdi
0x1800195fc  call    ?GetModernPrinterType@@YA?AW4ModernPrinterType@PrintCore@@PEBG@Z; GetModernPrinterType(ushort const *)
0x180019601  mov     edi, [rbp+var_44]
0x180019604  mov     r12d, eax
0x180019607  test    ebx, ebx
0x180019609  js      short loc_180019646
0x18001960b  mov     ecx, 38h ; '8'; Size
0x180019610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019615  test    rax, rax
0x180019618  jz      short loc_18001963F
0x18001961a  mov     r9d, [rbp+var_48]
0x18001961e  mov     r8d, edi
0x180019621  mov     rdx, [rbp+var_38.Ptr]
0x180019625  mov     rcx, rax
0x180019628  mov     [rsp+78h+var_50], rsi
0x18001962d  mov     dword ptr [rsp+78h+var_58], r12d
0x180019632  call    ??0CPrintTicketHandle@@QEAA@PEAUIPrintTicketService@@HHW4ModernPrinterType@PrintCore@@PEAG@Z; CPrintTicketHandle::CPrintTicketHandle(IPrintTicketService *,int,int,PrintCore::ModernPrinterType,ushort *)
0x180019637  mov     r14, rax
0x18001963a  test    rax, rax
0x18001963d  jnz     short loc_180019646
0x18001963f  mov     ebx, 8007000Eh
0x180019644  jmp     short loc_180019651
0x180019646  mov     [r15], r14
0x180019649  mov     [rbp+var_28.Ptr], 0
0x180019651  lea     rcx, [rbp+var_38]
0x180019655  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001965a  test    ebx, ebx
0x18001965c  jns     short loc_180019668
0x18001965e  test    edi, edi
0x180019660  jz      short loc_180019668
0x180019662  call    cs:__imp_CoUninitialize
0x180019668  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18001966f  jz      short loc_180019686
0x180019671  lea     rax, [rbp+var_38]
0x180019675  lea     rdx, DocPerf_PrintTicket_OpenProvider_Stop; int
0x18001967c  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x180019681  call    McGenEventWrite_EventWriteTransfer
0x180019686  lea     rcx, [rbp+var_28]
0x18001968a  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001968f  mov     eax, ebx
0x180019691  jmp     short loc_180019698
0x180019693  mov     eax, 80070057h
0x180019698  mov     rcx, [rbp+var_18]
0x18001969c  xor     rcx, rsp; StackCookie
0x18001969f  call    __security_check_cookie
0x1800196a4  add     rsp, 78h
0x1800196a8  pop     r15
0x1800196aa  pop     r14
0x1800196ac  pop     r13
0x1800196ae  pop     r12
0x1800196b0  pop     rdi
0x1800196b1  pop     rsi
0x1800196b2  pop     rbx
0x1800196b3  pop     rbp
0x1800196b4  retn
```
