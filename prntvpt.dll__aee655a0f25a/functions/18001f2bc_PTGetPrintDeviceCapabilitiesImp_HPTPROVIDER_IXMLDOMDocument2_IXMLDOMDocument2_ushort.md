# PTGetPrintDeviceCapabilitiesImp(HPTPROVIDER__ *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *,ushort * *)

- ea: `0x18001f2bc`
- end: `0x18001f543`
- name: `?PTGetPrintDeviceCapabilitiesImp@@YAJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@PEAPEAU2@PEAPEAG@Z`
- size: `647`
- prototype: `__int64 __fastcall(HPTPROVIDER this, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013380`

## callees

- `0x180005e70`
- `0x180008848`
- `0x180009150`
- `0x18000df24`
- `0x18000e03c`
- `0x18000f344`
- `0x18001e948`
- `0x18001f2bc`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f38b`
- `KERNEL32!GetLastError` at `0x18001f3dd`
- `KERNEL32!GetLastError` at `0x18001f38b`
- `KERNEL32!GetLastError` at `0x18001f3dd`
- `KERNEL32!GetProcessHeap` at `0x18001f39d`
- `KERNEL32!GetProcessHeap` at `0x18001f39d`
- `KERNEL32!HeapAlloc` at `0x18001f3ab`
- `KERNEL32!HeapAlloc` at `0x18001f3ab`
- `WINSPOOL!GetPrinterW` at `0x18001f37d`
- `WINSPOOL!GetPrinterW` at `0x18001f3d3`
- `WINSPOOL!GetPrinterW` at `0x18001f37d`
- `WINSPOOL!GetPrinterW` at `0x18001f3d3`

## pseudocode

```c
__int64 __fastcall PTGetPrintDeviceCapabilitiesImp(
        HPTPROVIDER this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 **a3,
        DWORD *a4)
{
  DWORD *p_cbBuf; // r12
  int v8; // edi
  __int64 v9; // rcx
  struct IXMLDOMDocument2 *v10; // r13
  void *v11; // rcx
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  struct _devicemodeW **v14; // rbx
  signed int LastError; // eax
  void *v16; // rdx
  struct IPrintTicketProvider *v17; // rbx
  struct IPrintTicketProviderVtbl *lpVtbl; // rax
  unsigned __int16 **v19; // r8
  struct IPrintTicketProvider *v21; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v22; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbBuf; // [rsp+80h] [rbp+40h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF

  v22 = 0;
  if ( !this || this != *((HPTPROVIDER *)this + 2) )
    goto LABEL_38;
  p_cbBuf = &cbBuf;
  if ( a4 )
    p_cbBuf = a4;
  if ( !a3 )
  {
LABEL_38:
    v8 = -2147024809;
    goto LABEL_39;
  }
  *a3 = 0;
  if ( a2 )
  {
    if ( (unsigned int)NPrintTicketUtil::IsValidPrintTicket(
                         a2,
                         (struct IXMLDOMDocument2 *)p_cbBuf,
                         (unsigned __int16 **)a3) )
    {
      v8 = -2147221501;
      goto LABEL_39;
    }
    v8 = 0;
  }
  else
  {
    v9 = *((_QWORD *)this + 9);
    v8 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    *a3 = (struct IXMLDOMDocument2 *)*((_QWORD *)this + 9);
  }
  if ( !*a3 )
  {
    v10 = a2;
    if ( a2 )
      goto LABEL_24;
    v11 = (void *)*((_QWORD *)this + 3);
    cbBuf = 0;
    if ( GetPrinterW(v11, 8u, 0, 0, &cbBuf) || GetLastError() != 122 )
      goto LABEL_24;
    v12 = cbBuf;
    ProcessHeap = GetProcessHeap();
    v14 = (struct _devicemodeW **)HeapAlloc(ProcessHeap, 0, v12);
    if ( !v14 )
    {
      v8 = -2147024882;
      goto LABEL_39;
    }
    if ( GetPrinterW(*((HANDLE *)this + 3), 8u, (LPBYTE)v14, cbBuf, &cbBuf) )
    {
      v8 = PTConvertDevModeToPrintTicketImp(this, cbBuf, *v14, kPTJobScope, &v22);
      if ( v8 >= 0 )
        v10 = v22;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::FreeProcessHeap((wil::details *)v14, v16);
    if ( v8 >= 0 )
    {
LABEL_24:
      v24 = 0;
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v24);
      v24 = 0;
      v21 = 0;
      v17 = TProviderInfo::Provider((TProviderInfo *)this);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v21);
      if ( v17 )
      {
        lpVtbl = v17->lpVtbl;
        v21 = v17;
        if ( ((int (__fastcall *)(struct IPrintTicketProvider *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               v17,
               &GUID_b8a70ab2_3dfc_4fec_a074_511b13c651cb,
               &v24) >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **))(*(_QWORD *)v24 + 80LL))(
                 v24,
                 v10,
                 a3);
          if ( v8 >= 0 )
          {
            if ( *a3 )
            {
              if ( (unsigned int)NPrintTicketUtil::IsValidPrintDeviceCapabilities(
                                   *a3,
                                   (struct IXMLDOMDocument2 *)p_cbBuf,
                                   v19) )
              {
                v8 = -2147221498;
              }
              else if ( !a2 && *a3 )
              {
                NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(this + 18);
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
              }
            }
            else
            {
              v8 = -2147418113;
            }
          }
          goto LABEL_27;
        }
      }
      else
      {
        v21 = 0;
      }
      v8 = -2147024846;
LABEL_27:
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v21);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v24);
    }
  }
LABEL_39:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f2bc  mov     [rsp-38h+arg_10], rbx
0x18001f2c1  push    rbp
0x18001f2c2  push    rsi
0x18001f2c3  push    rdi
0x18001f2c4  push    r12
0x18001f2c6  push    r13
0x18001f2c8  push    r14
0x18001f2ca  push    r15
0x18001f2cc  mov     rbp, rsp
0x18001f2cf  sub     rsp, 40h
0x18001f2d3  xor     ebx, ebx
0x18001f2d5  mov     r14, r8
0x18001f2d8  mov     [rbp+var_8], rbx
0x18001f2dc  mov     r15, rdx
0x18001f2df  mov     rsi, rcx
0x18001f2e2  test    rcx, rcx
0x18001f2e5  jz      loc_18001F51B
0x18001f2eb  cmp     rcx, [rcx+10h]
0x18001f2ef  jnz     loc_18001F51B
0x18001f2f5  test    r9, r9
0x18001f2f8  lea     r12, [rbp+cbBuf]
0x18001f2fc  cmovnz  r12, r9
0x18001f300  test    r8, r8
0x18001f303  jz      loc_18001F51B
0x18001f309  mov     [r8], rbx
0x18001f30c  test    rdx, rdx
0x18001f30f  jz      short loc_18001F32E
0x18001f311  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18001f314  mov     rcx, r15; this
0x18001f317  call    ?IsValidPrintTicket@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintTicket(IXMLDOMDocument2 *,ushort * *)
0x18001f31c  test    eax, eax
0x18001f31e  jz      short loc_18001F32A
0x18001f320  mov     edi, 80040003h
0x18001f325  jmp     loc_18001F520
0x18001f32a  mov     edi, ebx
0x18001f32c  jmp     short loc_18001F34C
0x18001f32e  mov     rcx, [rcx+48h]
0x18001f332  mov     edi, ebx
0x18001f334  test    rcx, rcx
0x18001f337  jz      short loc_18001F345
0x18001f339  mov     rax, [rcx]
0x18001f33c  mov     rax, [rax+8]
0x18001f340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f345  mov     rax, [rsi+48h]
0x18001f349  mov     [r14], rax
0x18001f34c  cmp     [r14], rbx
0x18001f34f  jnz     loc_18001F520
0x18001f355  mov     r13, r15
0x18001f358  test    r15, r15
0x18001f35b  jnz     loc_18001F42D
0x18001f361  mov     rcx, [rsi+18h]; hPrinter
0x18001f365  lea     rax, [rbp+cbBuf]
0x18001f369  lea     edi, [r15+8]
0x18001f36d  mov     [rbp+cbBuf], ebx
0x18001f370  mov     edx, edi; Level
0x18001f372  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x18001f377  xor     r9d, r9d; cbBuf
0x18001f37a  xor     r8d, r8d; pPrinter
0x18001f37d  call    cs:__imp_GetPrinterW
0x18001f383  test    eax, eax
0x18001f385  jnz     loc_18001F42D
0x18001f38b  call    cs:__imp_GetLastError
0x18001f391  cmp     eax, 7Ah ; 'z'
0x18001f394  jnz     loc_18001F42D
0x18001f39a  mov     ebx, [rbp+cbBuf]
0x18001f39d  call    cs:__imp_GetProcessHeap
0x18001f3a3  mov     r8d, ebx; dwBytes
0x18001f3a6  xor     edx, edx; dwFlags
0x18001f3a8  mov     rcx, rax; hHeap
0x18001f3ab  call    cs:__imp_HeapAlloc
0x18001f3b1  mov     rbx, rax
0x18001f3b4  test    rax, rax
0x18001f3b7  jz      loc_18001F47F
0x18001f3bd  mov     r9d, [rbp+cbBuf]; cbBuf
0x18001f3c1  lea     rax, [rbp+cbBuf]
0x18001f3c5  mov     rcx, [rsi+18h]; hPrinter
0x18001f3c9  mov     r8, rbx; pPrinter
0x18001f3cc  mov     edx, edi; Level
0x18001f3ce  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x18001f3d3  call    cs:__imp_GetPrinterW
0x18001f3d9  test    eax, eax
0x18001f3db  jnz     short loc_18001F3F4
0x18001f3dd  call    cs:__imp_GetLastError
0x18001f3e3  mov     edi, eax
0x18001f3e5  test    eax, eax
0x18001f3e7  jle     short loc_18001F41B
0x18001f3e9  movzx   edi, ax
0x18001f3ec  or      edi, 80070000h
0x18001f3f2  jmp     short loc_18001F41B
0x18001f3f4  mov     r8, [rbx]; struct _devicemodeW *
0x18001f3f7  lea     rax, [rbp+var_8]
0x18001f3fb  mov     edx, [rbp+cbBuf]; DevmodeSize
0x18001f3fe  mov     r9d, 2; enum EPrintTicketScope
0x18001f404  mov     rcx, rsi; this
0x18001f407  mov     [rsp+40h+pcbNeeded], rax; struct IXMLDOMDocument2 **
0x18001f40c  call    ?PTConvertDevModeToPrintTicketImp@@YAJPEAUHPTPROVIDER__@@KPEAU_devicemodeW@@W4EPrintTicketScope@@PEAPEAUIXMLDOMDocument2@@@Z; PTConvertDevModeToPrintTicketImp(HPTPROVIDER__ *,ulong,_devicemodeW *,EPrintTicketScope,IXMLDOMDocument2 * *)
0x18001f411  mov     edi, eax
0x18001f413  test    eax, eax
0x18001f415  js      short loc_18001F41B
0x18001f417  mov     r13, [rbp+var_8]
0x18001f41b  mov     rcx, rbx; this
0x18001f41e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001f423  xor     ebx, ebx
0x18001f425  test    edi, edi
0x18001f427  js      loc_18001F520
0x18001f42d  lea     rcx, [rbp+arg_8]
0x18001f431  mov     [rbp+arg_8], rbx
0x18001f435  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f43a  mov     rcx, rsi; this
0x18001f43d  mov     [rbp+arg_8], rbx
0x18001f441  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x18001f446  lea     rcx, [rbp+var_10]
0x18001f44a  mov     [rbp+var_10], 0
0x18001f452  mov     rbx, rax
0x18001f455  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f45a  test    rbx, rbx
0x18001f45d  jnz     short loc_18001F489
0x18001f45f  mov     [rbp+var_10], rbx
0x18001f463  mov     edi, 80070032h
0x18001f468  lea     rcx, [rbp+var_10]
0x18001f46c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f471  lea     rcx, [rbp+arg_8]
0x18001f475  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f47a  jmp     loc_18001F520
0x18001f47f  mov     edi, 8007000Eh
0x18001f484  jmp     loc_18001F520
0x18001f489  mov     rax, [rbx]
0x18001f48c  lea     r8, [rbp+arg_8]
0x18001f490  lea     rdx, _GUID_b8a70ab2_3dfc_4fec_a074_511b13c651cb
0x18001f497  mov     [rbp+var_10], rbx
0x18001f49b  mov     rcx, rbx
0x18001f49e  mov     rax, [rax]
0x18001f4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a6  test    eax, eax
0x18001f4a8  js      short loc_18001F463
0x18001f4aa  mov     rcx, [rbp+arg_8]
0x18001f4ae  mov     r8, r14
0x18001f4b1  mov     rdx, r13
0x18001f4b4  mov     rax, [rcx]
0x18001f4b7  mov     rax, [rax+50h]
0x18001f4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4c0  mov     edi, eax
0x18001f4c2  test    eax, eax
0x18001f4c4  js      short loc_18001F468
0x18001f4c6  mov     rcx, [r14]; this
0x18001f4c9  test    rcx, rcx
0x18001f4cc  jnz     short loc_18001F4D5
0x18001f4ce  mov     edi, 8000FFFFh
0x18001f4d3  jmp     short loc_18001F468
0x18001f4d5  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18001f4d8  call    ?IsValidPrintDeviceCapabilities@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintDeviceCapabilities(IXMLDOMDocument2 *,ushort * *)
0x18001f4dd  test    eax, eax
0x18001f4df  jz      short loc_18001F4E8
0x18001f4e1  mov     edi, 80040006h
0x18001f4e6  jmp     short loc_18001F468
0x18001f4e8  test    r15, r15
0x18001f4eb  jnz     loc_18001F468
0x18001f4f1  mov     rdx, [r14]
0x18001f4f4  test    rdx, rdx
0x18001f4f7  jz      loc_18001F468
0x18001f4fd  lea     rcx, [rsi+48h]
0x18001f501  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x18001f506  mov     rcx, [rsi+48h]
0x18001f50a  mov     rax, [rcx]
0x18001f50d  mov     rax, [rax+8]
0x18001f511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f516  jmp     loc_18001F468
0x18001f51b  mov     edi, 80070057h
0x18001f520  lea     rcx, [rbp+var_8]
0x18001f524  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f529  mov     rbx, [rsp+40h+arg_10]
0x18001f531  mov     eax, edi
0x18001f533  add     rsp, 40h
0x18001f537  pop     r15
0x18001f539  pop     r14
0x18001f53b  pop     r13
0x18001f53d  pop     r12
0x18001f53f  pop     rdi
0x18001f540  pop     rsi
0x18001f541  pop     rbp
0x18001f542  retn
```
