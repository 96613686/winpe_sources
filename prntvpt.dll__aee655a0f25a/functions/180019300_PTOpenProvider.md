# PTOpenProvider

- ea: `0x180019300`
- end: `0x1800194d9`
- name: `PTOpenProvider`
- size: `473`
- prototype: `HRESULT __stdcall(PCWSTR pszPrinterName, DWORD dwVersion, HPTPROVIDER *phProvider)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004acc`
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
- `0x180019300`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001938d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001938d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001947a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001947a`

## pseudocode

```c
HRESULT __stdcall PTOpenProvider(PCWSTR pszPrinterName, DWORD dwVersion, HPTPROVIDER *phProvider)
{
  int v3; // r9d
  int v7; // ecx
  int COMStateTLSSlot; // ebx
  int v9; // r8d
  int v10; // r9d
  BSTR v11; // rax
  __int64 v12; // r15
  int ModernPrinterType; // edi
  void *v14; // rax
  HPTPROVIDER v15; // rax
  int v17; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+40h] [rbp-20h] BYREF

  v18 = 0;
  v19 = 0;
  v17 = 0;
  if ( pszPrinterName && phProvider )
  {
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(
        (int)pszPrinterName,
        (int)&DocPerf_PrintTicket_OpenProvider_Start,
        (int)phProvider,
        v3,
        &v20);
    *phProvider = 0;
    COMStateTLSSlot = ReadCOMStateTLSSlot((enum EPTCallType::_enum *)&v17);
    if ( COMStateTLSSlot >= 0 )
    {
      v11 = SysAllocString(pszPrinterName);
      if ( NCoreLibrary::TAutoPtrBSTR::operator=(&v19, v11) )
      {
        COMStateTLSSlot = MyCoInit(&v18, (unsigned int)v17);
        if ( COMStateTLSSlot >= 0 )
        {
          v20.Ptr = 0;
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v20);
          v20.Ptr = 0;
          v17 = 0;
          COMStateTLSSlot = CreatePTServiceObject(pszPrinterName, (LPVOID *)&v20, &v17);
          if ( COMStateTLSSlot >= 0 )
          {
            v12 = v19;
            COMStateTLSSlot = (*(__int64 (__fastcall **)(ULONGLONG, __int64, _QWORD))(*(_QWORD *)v20.Ptr + 24LL))(
                                v20.Ptr,
                                v19,
                                dwVersion);
            if ( COMStateTLSSlot >= 0 )
            {
              ModernPrinterType = GetModernPrinterType(pszPrinterName);
              v14 = operator new(0x38u);
              if ( v14
                && (v15 = (HPTPROVIDER)CPrintTicketHandle::CPrintTicketHandle(
                                         v14,
                                         v20.Ptr,
                                         v18,
                                         (unsigned int)v17,
                                         ModernPrinterType,
                                         v12)) != 0 )
              {
                *phProvider = v15;
                v19 = 0;
              }
              else
              {
                COMStateTLSSlot = -2147024882;
              }
            }
          }
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v20);
          if ( COMStateTLSSlot < 0 && v18 )
            CoUninitialize();
        }
      }
      else
      {
        COMStateTLSSlot = -2147024882;
      }
    }
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, (int)&DocPerf_PrintTicket_OpenProvider_Stop, v9, v10, &v20);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v19);
    return COMStateTLSSlot;
  }
  else
  {
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v19);
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180019300  mov     [rsp-28h+arg_18], rbx
0x180019305  push    rbp
0x180019306  push    rsi
0x180019307  push    rdi
0x180019308  push    r12
0x18001930a  push    r15
0x18001930c  mov     rbp, rsp
0x18001930f  sub     rsp, 60h
0x180019313  mov     rax, cs:__security_cookie
0x18001931a  xor     rax, rsp
0x18001931d  mov     [rbp+var_10], rax
0x180019321  mov     [rbp+var_2C], 0
0x180019328  mov     rsi, r8
0x18001932b  mov     [rbp+var_28], 0
0x180019333  mov     r12d, edx
0x180019336  mov     [rbp+var_30], 0
0x18001933d  mov     rdi, rcx
0x180019340  test    rcx, rcx
0x180019343  jz      loc_1800194AB
0x180019349  test    r8, r8
0x18001934c  jz      loc_1800194AB
0x180019352  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180019359  jz      short loc_180019370
0x18001935b  lea     rax, [rbp+var_20]
0x18001935f  lea     rdx, DocPerf_PrintTicket_OpenProvider_Start; int
0x180019366  mov     [rsp+60h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x18001936b  call    McGenEventWrite_EventWriteTransfer
0x180019370  lea     rcx, [rbp+var_30]; enum EPTCallType::_enum *
0x180019374  mov     qword ptr [rsi], 0
0x18001937b  call    ?ReadCOMStateTLSSlot@@YAJPEAW4_enum@EPTCallType@@@Z; ReadCOMStateTLSSlot(EPTCallType::_enum *)
0x180019380  mov     ebx, eax
0x180019382  test    eax, eax
0x180019384  js      loc_180019480
0x18001938a  mov     rcx, rdi; psz
0x18001938d  call    cs:__imp_SysAllocString
0x180019393  mov     rdx, rax
0x180019396  lea     rcx, [rbp+var_28]
0x18001939a  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x18001939f  test    rax, rax
0x1800193a2  jnz     short loc_1800193AE
0x1800193a4  mov     ebx, 8007000Eh
0x1800193a9  jmp     loc_180019480
0x1800193ae  mov     edx, [rbp+var_30]
0x1800193b1  lea     rcx, [rbp+var_2C]
0x1800193b5  call    ?MyCoInit@@YAJPEAHW4_enum@EPTCallType@@@Z; MyCoInit(int *,EPTCallType::_enum)
0x1800193ba  mov     ebx, eax
0x1800193bc  test    eax, eax
0x1800193be  js      loc_180019480
0x1800193c4  lea     rcx, [rbp+var_20]
0x1800193c8  mov     [rbp+var_20.Ptr], 0
0x1800193d0  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800193d5  lea     r8, [rbp+var_30]; int *
0x1800193d9  mov     [rbp+var_20.Ptr], 0
0x1800193e1  lea     rdx, [rbp+var_20]; ppv
0x1800193e5  mov     [rbp+var_30], 0
0x1800193ec  mov     rcx, rdi; unsigned __int16 *
0x1800193ef  call    ?CreatePTServiceObject@@YAJPEBGPEAPEAUIPrintTicketService@@PEAH@Z; CreatePTServiceObject(ushort const *,IPrintTicketService * *,int *)
0x1800193f4  mov     ebx, eax
0x1800193f6  test    eax, eax
0x1800193f8  js      short loc_180019467
0x1800193fa  mov     rcx, [rbp+var_20.Ptr]
0x1800193fe  mov     r8d, r12d
0x180019401  mov     r15, [rbp+var_28]
0x180019405  mov     rdx, r15
0x180019408  mov     rax, [rcx]
0x18001940b  mov     rax, [rax+18h]
0x18001940f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019414  mov     ebx, eax
0x180019416  test    eax, eax
0x180019418  js      short loc_180019467
0x18001941a  mov     rcx, rdi
0x18001941d  call    ?GetModernPrinterType@@YA?AW4ModernPrinterType@PrintCore@@PEBG@Z; GetModernPrinterType(ushort const *)
0x180019422  mov     ecx, 38h ; '8'; Size
0x180019427  mov     edi, eax
0x180019429  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001942e  test    rax, rax
0x180019431  jz      short loc_180019462
0x180019433  mov     r9d, [rbp+var_30]
0x180019437  mov     rcx, rax
0x18001943a  mov     r8d, [rbp+var_2C]
0x18001943e  mov     rdx, [rbp+var_20.Ptr]
0x180019442  mov     [rsp+60h+var_38], r15
0x180019447  mov     dword ptr [rsp+60h+var_40], edi
0x18001944b  call    ??0CPrintTicketHandle@@QEAA@PEAUIPrintTicketService@@HHW4ModernPrinterType@PrintCore@@PEAG@Z; CPrintTicketHandle::CPrintTicketHandle(IPrintTicketService *,int,int,PrintCore::ModernPrinterType,ushort *)
0x180019450  test    rax, rax
0x180019453  jz      short loc_180019462
0x180019455  mov     [rsi], rax
0x180019458  mov     [rbp+var_28], 0
0x180019460  jmp     short loc_180019467
0x180019462  mov     ebx, 8007000Eh
0x180019467  lea     rcx, [rbp+var_20]
0x18001946b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180019470  test    ebx, ebx
0x180019472  jns     short loc_180019480
0x180019474  cmp     [rbp+var_2C], 0
0x180019478  jz      short loc_180019480
0x18001947a  call    cs:__imp_CoUninitialize
0x180019480  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180019487  jz      short loc_18001949E
0x180019489  lea     rax, [rbp+var_20]
0x18001948d  lea     rdx, DocPerf_PrintTicket_OpenProvider_Stop; int
0x180019494  mov     [rsp+60h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x180019499  call    McGenEventWrite_EventWriteTransfer
0x18001949e  lea     rcx, [rbp+var_28]
0x1800194a2  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800194a7  mov     eax, ebx
0x1800194a9  jmp     short loc_1800194B9
0x1800194ab  lea     rcx, [rbp+var_28]
0x1800194af  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800194b4  mov     eax, 80070057h
0x1800194b9  mov     rcx, [rbp+var_10]
0x1800194bd  xor     rcx, rsp; StackCookie
0x1800194c0  call    __security_check_cookie
0x1800194c5  mov     rbx, [rsp+60h+arg_18]
0x1800194cd  add     rsp, 60h
0x1800194d1  pop     r15
0x1800194d3  pop     r12
0x1800194d5  pop     rdi
0x1800194d6  pop     rsi
0x1800194d7  pop     rbp
0x1800194d8  retn
```
