# PTGetPrintDeviceResourcesImp(HPTPROVIDER__ *,ushort const *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *,ushort * *)

- ea: `0x18000f13c`
- end: `0x18000f33e`
- name: `?PTGetPrintDeviceResourcesImp@@YAJPEAUHPTPROVIDER__@@PEBGPEAUIXMLDOMDocument2@@PEAPEAU2@PEAPEAG@Z`
- size: `514`
- prototype: `__int64 __usercall@<rax>(HPTPROVIDER this@<rcx>, const unsigned __int16 *@<rdx>, struct IXMLDOMDocument2 *@<r8>, struct IXMLDOMDocument2 **@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013420`

## callees

- `0x180005e70`
- `0x180008848`
- `0x180009150`
- `0x18000df24`
- `0x18000f13c`
- `0x18000f344`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f1cc`
- `KERNEL32!GetLastError` at `0x18000f21f`
- `KERNEL32!GetLastError` at `0x18000f1cc`
- `KERNEL32!GetLastError` at `0x18000f21f`
- `KERNEL32!GetProcessHeap` at `0x18000f1de`
- `KERNEL32!GetProcessHeap` at `0x18000f1de`
- `KERNEL32!HeapAlloc` at `0x18000f1ec`
- `KERNEL32!HeapAlloc` at `0x18000f1ec`
- `WINSPOOL!GetPrinterW` at `0x18000f1bc`
- `WINSPOOL!GetPrinterW` at `0x18000f215`
- `WINSPOOL!GetPrinterW` at `0x18000f1bc`
- `WINSPOOL!GetPrinterW` at `0x18000f215`

## pseudocode

```c
__int64 __fastcall PTGetPrintDeviceResourcesImp(
        HPTPROVIDER this,
        const unsigned __int16 *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMDocument2 **a4,
        struct IXMLDOMDocument2 *a5)
{
  struct IXMLDOMDocument2 *v6; // rsi
  DWORD *p_cbBuf; // rdx
  void *v10; // rcx
  int v11; // ebx
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  struct _devicemodeW **v14; // r15
  signed int LastError; // eax
  void *v16; // rdx
  struct IPrintTicketProvider *v17; // rax
  struct IXMLDOMDocument2 *v19[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbBuf; // [rsp+70h] [rbp+30h] BYREF
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF

  v19[0] = 0;
  v6 = a3;
  if ( !this || this != *((HPTPROVIDER *)this + 2) )
    goto LABEL_27;
  p_cbBuf = &cbBuf;
  if ( a5 )
    p_cbBuf = (DWORD *)a5;
  if ( !a4 )
  {
LABEL_27:
    v11 = -2147024809;
    goto LABEL_28;
  }
  *a4 = 0;
  if ( a3 )
  {
    if ( (unsigned int)NPrintTicketUtil::IsValidPrintTicket(
                         a3,
                         (struct IXMLDOMDocument2 *)p_cbBuf,
                         (unsigned __int16 **)a3) )
    {
      v11 = -2147221501;
      goto LABEL_28;
    }
LABEL_17:
    v21 = 0;
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v21);
    v21 = 0;
    if ( TProviderInfo::Provider((TProviderInfo *)this)
      && (v17 = TProviderInfo::Provider((TProviderInfo *)this),
          ((__int64 (__fastcall *)(struct IPrintTicketProvider *, GUID *, __int64 *))v17->lpVtbl->QueryInterface)(
            v17,
            &GUID_b8a70ab2_3dfc_4fec_a074_511b13c651cb,
            &v21) >= 0) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **))(*(_QWORD *)v21 + 88LL))(
              v21,
              a2,
              v6,
              a4);
      if ( v11 >= 0 && !*a4 )
        v11 = -2147418113;
    }
    else
    {
      v11 = -2147024846;
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v21);
    goto LABEL_28;
  }
  v10 = (void *)*((_QWORD *)this + 3);
  cbBuf = 0;
  if ( GetPrinterW(v10, 8u, 0, 0, &cbBuf) )
    goto LABEL_17;
  v11 = 0;
  if ( GetLastError() == 122 )
  {
    v12 = cbBuf;
    ProcessHeap = GetProcessHeap();
    v14 = (struct _devicemodeW **)HeapAlloc(ProcessHeap, 0, v12);
    if ( !v14 )
    {
      v11 = -2147024882;
      goto LABEL_28;
    }
    if ( GetPrinterW(*((HANDLE *)this + 3), (_DWORD)v6 + 8, (LPBYTE)v14, cbBuf, &cbBuf) )
    {
      v11 = PTConvertDevModeToPrintTicketImp(this, cbBuf, *v14, kPTJobScope, v19);
      if ( v11 >= 0 )
        v6 = v19[0];
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::FreeProcessHeap((wil::details *)v14, v16);
  }
  if ( v11 >= 0 )
    goto LABEL_17;
LABEL_28:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f13c  mov     [rsp-28h+arg_8], rbx
0x18000f141  mov     [rsp-28h+arg_18], rsi
0x18000f146  push    rbp
0x18000f147  push    rdi
0x18000f148  push    r12
0x18000f14a  push    r14
0x18000f14c  push    r15
0x18000f14e  mov     rbp, rsp
0x18000f151  sub     rsp, 40h
0x18000f155  mov     [rbp+var_10], 0
0x18000f15d  mov     r14, r9
0x18000f160  mov     rsi, r8
0x18000f163  mov     r12, rdx
0x18000f166  mov     rdi, rcx
0x18000f169  test    rcx, rcx
0x18000f16c  jz      loc_18000F315
0x18000f172  cmp     rcx, [rcx+10h]
0x18000f176  jnz     loc_18000F315
0x18000f17c  mov     rax, [rbp+arg_20]
0x18000f180  lea     rdx, [rbp+cbBuf]
0x18000f184  test    rax, rax
0x18000f187  cmovnz  rdx, rax; struct IXMLDOMDocument2 *
0x18000f18b  test    r9, r9
0x18000f18e  jz      loc_18000F315
0x18000f194  mov     qword ptr [r9], 0
0x18000f19b  test    r8, r8
0x18000f19e  jnz     loc_18000F2EE
0x18000f1a4  mov     rcx, [rcx+18h]; hPrinter
0x18000f1a8  lea     rax, [rbp+cbBuf]
0x18000f1ac  xor     r9d, r9d; cbBuf
0x18000f1af  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x18000f1b4  lea     edx, [r8+8]; Level
0x18000f1b8  mov     [rbp+cbBuf], r8d
0x18000f1bc  call    cs:__imp_GetPrinterW
0x18000f1c2  test    eax, eax
0x18000f1c4  jnz     loc_18000F26D
0x18000f1ca  xor     ebx, ebx
0x18000f1cc  call    cs:__imp_GetLastError
0x18000f1d2  cmp     eax, 7Ah ; 'z'
0x18000f1d5  jnz     loc_18000F265
0x18000f1db  mov     ebx, [rbp+cbBuf]
0x18000f1de  call    cs:__imp_GetProcessHeap
0x18000f1e4  mov     r8d, ebx; dwBytes
0x18000f1e7  xor     edx, edx; dwFlags
0x18000f1e9  mov     rcx, rax; hHeap
0x18000f1ec  call    cs:__imp_HeapAlloc
0x18000f1f2  mov     r15, rax
0x18000f1f5  test    rax, rax
0x18000f1f8  jz      loc_18000F2E7
0x18000f1fe  mov     r9d, [rbp+cbBuf]; cbBuf
0x18000f202  lea     rax, [rbp+cbBuf]
0x18000f206  mov     rcx, [rdi+18h]; hPrinter
0x18000f20a  lea     edx, [rsi+8]; Level
0x18000f20d  mov     r8, r15; pPrinter
0x18000f210  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x18000f215  call    cs:__imp_GetPrinterW
0x18000f21b  test    eax, eax
0x18000f21d  jnz     short loc_18000F236
0x18000f21f  call    cs:__imp_GetLastError
0x18000f225  mov     ebx, eax
0x18000f227  test    eax, eax
0x18000f229  jle     short loc_18000F25D
0x18000f22b  movzx   ebx, ax
0x18000f22e  or      ebx, 80070000h
0x18000f234  jmp     short loc_18000F25D
0x18000f236  mov     r8, [r15]; struct _devicemodeW *
0x18000f239  lea     rax, [rbp+var_10]
0x18000f23d  mov     edx, [rbp+cbBuf]; DevmodeSize
0x18000f240  mov     r9d, 2; enum EPrintTicketScope
0x18000f246  mov     rcx, rdi; this
0x18000f249  mov     [rsp+40h+pcbNeeded], rax; struct IXMLDOMDocument2 **
0x18000f24e  call    ?PTConvertDevModeToPrintTicketImp@@YAJPEAUHPTPROVIDER__@@KPEAU_devicemodeW@@W4EPrintTicketScope@@PEAPEAUIXMLDOMDocument2@@@Z; PTConvertDevModeToPrintTicketImp(HPTPROVIDER__ *,ulong,_devicemodeW *,EPrintTicketScope,IXMLDOMDocument2 * *)
0x18000f253  mov     ebx, eax
0x18000f255  test    eax, eax
0x18000f257  js      short loc_18000F25D
0x18000f259  mov     rsi, [rbp+var_10]
0x18000f25d  mov     rcx, r15; this
0x18000f260  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000f265  test    ebx, ebx
0x18000f267  js      loc_18000F31A
0x18000f26d  lea     rcx, [rbp+arg_10]
0x18000f271  mov     [rbp+arg_10], 0
0x18000f279  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000f27e  mov     rcx, rdi; this
0x18000f281  mov     [rbp+arg_10], 0
0x18000f289  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x18000f28e  test    rax, rax
0x18000f291  jz      short loc_18000F305
0x18000f293  mov     rcx, rdi; this
0x18000f296  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x18000f29b  mov     r9, rax
0x18000f29e  lea     r8, [rbp+arg_10]
0x18000f2a2  lea     rdx, _GUID_b8a70ab2_3dfc_4fec_a074_511b13c651cb
0x18000f2a9  mov     rcx, [rax]
0x18000f2ac  mov     rax, [rcx]
0x18000f2af  mov     rcx, r9
0x18000f2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b7  test    eax, eax
0x18000f2b9  js      short loc_18000F305
0x18000f2bb  mov     rcx, [rbp+arg_10]
0x18000f2bf  mov     r9, r14
0x18000f2c2  mov     r8, rsi
0x18000f2c5  mov     rdx, r12
0x18000f2c8  mov     rax, [rcx]
0x18000f2cb  mov     rax, [rax+58h]
0x18000f2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2d4  mov     ebx, eax
0x18000f2d6  test    eax, eax
0x18000f2d8  js      short loc_18000F30A
0x18000f2da  cmp     qword ptr [r14], 0
0x18000f2de  jnz     short loc_18000F30A
0x18000f2e0  mov     ebx, 8000FFFFh
0x18000f2e5  jmp     short loc_18000F30A
0x18000f2e7  mov     ebx, 8007000Eh
0x18000f2ec  jmp     short loc_18000F31A
0x18000f2ee  mov     rcx, r8; this
0x18000f2f1  call    ?IsValidPrintTicket@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintTicket(IXMLDOMDocument2 *,ushort * *)
0x18000f2f6  test    eax, eax
0x18000f2f8  jz      loc_18000F26D
0x18000f2fe  mov     ebx, 80040003h
0x18000f303  jmp     short loc_18000F31A
0x18000f305  mov     ebx, 80070032h
0x18000f30a  lea     rcx, [rbp+arg_10]
0x18000f30e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000f313  jmp     short loc_18000F31A
0x18000f315  mov     ebx, 80070057h
0x18000f31a  lea     rcx, [rbp+var_10]
0x18000f31e  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000f323  lea     r11, [rsp+40h+var_s0]
0x18000f328  mov     eax, ebx
0x18000f32a  mov     rbx, [r11+38h]
0x18000f32e  mov     rsi, [r11+48h]
0x18000f332  mov     rsp, r11
0x18000f335  pop     r15
0x18000f337  pop     r14
0x18000f339  pop     r12
0x18000f33b  pop     rdi
0x18000f33c  pop     rbp
0x18000f33d  retn
```
