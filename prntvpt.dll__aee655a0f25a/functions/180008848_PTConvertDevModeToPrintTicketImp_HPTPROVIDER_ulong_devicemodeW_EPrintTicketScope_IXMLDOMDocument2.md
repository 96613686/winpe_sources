# PTConvertDevModeToPrintTicketImp(HPTPROVIDER__ *,ulong,_devicemodeW *,EPrintTicketScope,IXMLDOMDocument2 * *)

- ea: `0x180008848`
- end: `0x180008a5f`
- name: `?PTConvertDevModeToPrintTicketImp@@YAJPEAUHPTPROVIDER__@@KPEAU_devicemodeW@@W4EPrintTicketScope@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(HPTPROVIDER this, size_t DevmodeSize, struct _devicemodeW *, enum EPrintTicketScope, struct IXMLDOMDocument2 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800087e0`
- `0x18000f13c`
- `0x18001f2bc`

## callees

- `0x180005e70`
- `0x180008848`
- `0x180008a68`
- `0x180008acc`
- `0x180008e68`
- `0x180009150`
- `0x180009214`
- `0x180009268`
- `0x180009354`
- `0x180009da8`
- `0x180023010`

## import_xrefs

- `WINSPOOL!IsValidDevmodeW` at `0x1800088bf`
- `WINSPOOL!IsValidDevmodeW` at `0x1800088bf`

## pseudocode

```c
__int64 __fastcall PTConvertDevModeToPrintTicketImp(
        HPTPROVIDER this,
        size_t DevmodeSize,
        struct _devicemodeW *a3,
        enum EPrintTicketScope a4,
        struct IXMLDOMDocument2 **a5)
{
  unsigned int v5; // r13d
  struct IXMLDOMDocument2 **v8; // r12
  struct IXMLDOMElement **v9; // r8
  int started; // ebx
  struct NPrintTicketUtil::CPrintTicketWrapper *v11; // r9
  struct IPrintTicketProvider *v12; // rax
  struct IXMLDOMDocument2 *v13; // rdi
  struct IPrintTicketProvider *v14; // r15
  int v15; // r9d
  struct IXMLDOMDocument2 *v16; // rax
  struct _devicemodeW *v18; // [rsp+20h] [rbp-60h]
  unsigned __int16 v19[4]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v20; // [rsp+38h] [rbp-48h]
  __int64 v21; // [rsp+48h] [rbp-38h]
  __int16 v22; // [rsp+50h] [rbp-30h]
  int v23; // [rsp+54h] [rbp-2Ch]
  void **v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h]
  __int64 v26; // [rsp+70h] [rbp-10h]
  __int16 v27; // [rsp+78h] [rbp-8h]
  int v28; // [rsp+7Ch] [rbp-4h]
  struct IXMLDOMDocument2 *v29; // [rsp+C0h] [rbp+40h] BYREF
  struct NPrintTicketUtil::CPrintTicketWrapper *v30; // [rsp+D8h] [rbp+58h]

  LODWORD(v30) = a4;
  v5 = DevmodeSize;
  v21 = 0;
  *(_QWORD *)v19 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v22 = 0;
  v23 = 0;
  v29 = 0;
  v20 = 0;
  if ( (unsigned int)DevmodeSize >= 0xDC && a3 && (v8 = a5) != 0 && IsValidDevmodeW(a3, (unsigned int)DevmodeSize) )
  {
    if ( this && this == *((HPTPROVIDER *)this + 2) )
    {
      started = NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
                  (NPrintTicketUtil::CPrintTicketWrapper *)v19,
                  L"psf:PrintTicket",
                  v9);
      if ( started < 0 )
        goto LABEL_23;
      if ( ((_BYTE)this[11] & 1) == 0 )
      {
        started = publicdm::DevmodeSnapshotToJT((publicdm *)a3, *((struct _devicemodeW **)this + 10), v19, v11);
        if ( started < 0 )
          goto LABEL_23;
      }
      LODWORD(v18) = this[10];
      started = publicdm::PublicDevmodeToJobTicket(
                  *((publicdm **)this + 3),
                  *((void **)this + 11),
                  *((const unsigned __int16 **)this + 10),
                  a3->dmDeviceName,
                  v18,
                  (unsigned int)v19,
                  *(struct NPrintTicketUtil::CPrintTicketWrapper **)v19);
      if ( started < 0 )
        goto LABEL_23;
      started = NPrintTicketUtil::CPrintTicketWrapper::GetXML((NPrintTicketUtil::CPrintTicketWrapper *)v19, &v29);
      if ( started < 0 )
      {
        v13 = v29;
      }
      else
      {
        v12 = TProviderInfo::Provider((TProviderInfo *)this);
        v13 = v29;
        v14 = v12;
        if ( v12 )
        {
          started = ((__int64 (__fastcall *)(struct IPrintTicketProvider *, _QWORD, struct _devicemodeW *, struct IXMLDOMDocument2 *))v12->lpVtbl->ConvertDevModeToPrintTicket)(
                      v12,
                      v5,
                      a3,
                      v29);
          ((void (__fastcall *)(struct IPrintTicketProvider *))v14->lpVtbl->Release)(v14);
        }
        if ( started >= 0 )
        {
          v26 = 0;
          v24 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
          v27 = 0;
          v28 = 0;
          v25 = 0;
          started = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                      (NPrintTicketUtil::CPrintTicketWrapper *)&v24,
                      v13,
                      0);
          if ( started >= 0 )
            started = NPrintTicketUtil::FilterPrintTicket(
                        (NPrintTicketUtil *)&v24,
                        (struct NPrintTicketUtil::CPrintTicketWrapper *)(unsigned int)v30,
                        (enum EPrintTicketScope)*((_DWORD *)this + 15),
                        v15);
          NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v24);
          if ( started >= 0 )
          {
            if ( !v13 )
            {
LABEL_23:
              NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v19);
              return (unsigned int)started;
            }
            v16 = v13;
            v13 = 0;
            *v8 = v16;
          }
        }
      }
      if ( v13 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v13->lpVtbl->Release)(v13);
      goto LABEL_23;
    }
  }
  else
  {
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v29);
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008848  mov     [rsp-38h+arg_8], rbx
0x18000884d  mov     dword ptr [rsp-38h+arg_18], r9d
0x180008852  push    rbp
0x180008853  push    rsi
0x180008854  push    rdi
0x180008855  push    r12
0x180008857  push    r13
0x180008859  push    r14
0x18000885b  push    r15
0x18000885d  mov     rbp, rsp
0x180008860  sub     rsp, 80h
0x180008867  xor     r15d, r15d
0x18000886a  mov     r13d, edx
0x18000886d  mov     [rbp+var_38], r15
0x180008871  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180008878  mov     qword ptr [rbp+var_50], rax
0x18000887c  xorps   xmm0, xmm0
0x18000887f  mov     [rbp+var_30], r15w
0x180008884  mov     r14, r8
0x180008887  mov     [rbp+var_2C], r15d
0x18000888b  mov     rsi, rcx
0x18000888e  mov     [rbp+arg_0], r15
0x180008892  movdqu  [rbp+var_48], xmm0
0x180008897  cmp     edx, 0DCh
0x18000889d  jb      loc_180008A2D
0x1800088a3  test    r8, r8
0x1800088a6  jz      loc_180008A2D
0x1800088ac  mov     r12, [rbp+arg_20]
0x1800088b0  test    r12, r12
0x1800088b3  jz      loc_180008A2D
0x1800088b9  mov     edx, r13d; DevmodeSize
0x1800088bc  mov     rcx, r8; pDevmode
0x1800088bf  call    cs:__imp_IsValidDevmodeW
0x1800088c5  test    eax, eax
0x1800088c7  jz      loc_180008A2D
0x1800088cd  test    rsi, rsi
0x1800088d0  jz      loc_180008A36
0x1800088d6  cmp     rsi, [rsi+10h]
0x1800088da  jnz     loc_180008A36
0x1800088e0  lea     rdx, aPsfPrintticket; "psf:PrintTicket"
0x1800088e7  lea     rcx, [rbp+var_50]; this
0x1800088eb  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x1800088f0  mov     ebx, eax
0x1800088f2  test    eax, eax
0x1800088f4  js      loc_180008A20
0x1800088fa  test    byte ptr [rsi+2Ch], 1
0x1800088fe  jnz     short loc_18000891A
0x180008900  mov     rdx, [rsi+50h]; struct _devicemodeW *
0x180008904  lea     r8, [rbp+var_50]; unsigned __int16 *
0x180008908  mov     rcx, r14; this
0x18000890b  call    ?DevmodeSnapshotToJT@publicdm@@YAJPEAU_devicemodeW@@PEBGPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::DevmodeSnapshotToJT(_devicemodeW *,ushort const *,NPrintTicketUtil::CPrintTicketWrapper *)
0x180008910  mov     ebx, eax
0x180008912  test    eax, eax
0x180008914  js      loc_180008A20
0x18000891a  mov     eax, [rsi+28h]
0x18000891d  lea     rcx, [rbp+var_50]
0x180008921  mov     r8, [rsi+50h]; unsigned __int16 *
0x180008925  mov     r9, r14; unsigned __int16 *
0x180008928  mov     rdx, [rsi+58h]; void *
0x18000892c  mov     qword ptr [rsp+80h+var_58], rcx; unsigned int
0x180008931  mov     rcx, [rsi+18h]; this
0x180008935  mov     dword ptr [rsp+80h+var_60], eax; struct _devicemodeW *
0x180008939  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x18000893e  mov     ebx, eax
0x180008940  test    eax, eax
0x180008942  js      loc_180008A20
0x180008948  lea     rdx, [rbp+arg_0]; struct IXMLDOMDocument2 **
0x18000894c  lea     rcx, [rbp+var_50]; this
0x180008950  call    ?GetXML@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetXML(IXMLDOMDocument2 * *)
0x180008955  mov     ebx, eax
0x180008957  test    eax, eax
0x180008959  js      loc_180008A08
0x18000895f  mov     rcx, rsi; this
0x180008962  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x180008967  mov     rdi, [rbp+arg_0]
0x18000896b  mov     r15, rax
0x18000896e  test    rax, rax
0x180008971  jz      short loc_18000899C
0x180008973  mov     rcx, [rax]
0x180008976  mov     r9, rdi
0x180008979  mov     r8, r14
0x18000897c  mov     edx, r13d
0x18000897f  mov     rax, [rcx+38h]
0x180008983  mov     rcx, r15
0x180008986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000898b  mov     ebx, eax
0x18000898d  mov     rcx, r15
0x180008990  mov     rax, [r15]
0x180008993  mov     rax, [rax+10h]
0x180008997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000899c  xor     r15d, r15d
0x18000899f  test    ebx, ebx
0x1800089a1  js      short loc_180008A0C
0x1800089a3  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x1800089aa  mov     [rbp+var_10], r15
0x1800089ae  xorps   xmm0, xmm0
0x1800089b1  mov     [rbp+var_28], rax
0x1800089b5  xor     r8d, r8d; int
0x1800089b8  mov     [rbp+var_8], r15w
0x1800089bd  mov     rdx, rdi; struct IXMLDOMDocument2 *
0x1800089c0  mov     [rbp+var_4], r15d
0x1800089c4  lea     rcx, [rbp+var_28]; this
0x1800089c8  movdqu  [rbp+var_20], xmm0
0x1800089cd  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x1800089d2  mov     ebx, eax
0x1800089d4  test    eax, eax
0x1800089d6  js      short loc_1800089EA
0x1800089d8  mov     r8d, [rsi+3Ch]; enum EPrintTicketScope
0x1800089dc  lea     rcx, [rbp+var_28]; this
0x1800089e0  mov     edx, dword ptr [rbp+arg_18]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800089e3  call    ?FilterPrintTicket@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@W4EPrintTicketScope@@H@Z; NPrintTicketUtil::FilterPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,EPrintTicketScope,int)
0x1800089e8  mov     ebx, eax
0x1800089ea  lea     rcx, [rbp+var_28]; this
0x1800089ee  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x1800089f3  test    ebx, ebx
0x1800089f5  js      short loc_180008A0C
0x1800089f7  test    rdi, rdi
0x1800089fa  jz      short loc_180008A20
0x1800089fc  mov     rax, rdi
0x1800089ff  mov     rdi, r15
0x180008a02  mov     [r12], rax
0x180008a06  jmp     short loc_180008A0C
0x180008a08  mov     rdi, [rbp+arg_0]
0x180008a0c  test    rdi, rdi
0x180008a0f  jz      short loc_180008A20
0x180008a11  mov     rax, [rdi]
0x180008a14  mov     rcx, rdi
0x180008a17  mov     rax, [rax+10h]
0x180008a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a20  lea     rcx, [rbp+var_50]; this
0x180008a24  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180008a29  mov     eax, ebx
0x180008a2b  jmp     short loc_180008A44
0x180008a2d  lea     rcx, [rbp+arg_0]
0x180008a31  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180008a36  lea     rcx, [rbp+var_50]; this
0x180008a3a  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180008a3f  mov     eax, 80070057h
0x180008a44  mov     rbx, [rsp+80h+arg_8]
0x180008a4c  add     rsp, 80h
0x180008a53  pop     r15
0x180008a55  pop     r14
0x180008a57  pop     r13
0x180008a59  pop     r12
0x180008a5b  pop     rdi
0x180008a5c  pop     rsi
0x180008a5d  pop     rbp
0x180008a5e  retn
```
