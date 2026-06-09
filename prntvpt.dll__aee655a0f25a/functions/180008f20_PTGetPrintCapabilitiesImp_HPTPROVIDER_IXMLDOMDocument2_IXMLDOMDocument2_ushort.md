# PTGetPrintCapabilitiesImp(HPTPROVIDER__ *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *,ushort * *)

- ea: `0x180008f20`
- end: `0x180009148`
- name: `?PTGetPrintCapabilitiesImp@@YAJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@PEAPEAU2@PEAPEAG@Z`
- size: `552`
- prototype: `__int64 __fastcall(HPTPROVIDER this, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **, struct IXMLDOMDocument2 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008190`
- `0x180008498`

## callees

- `0x180003708`
- `0x1800060fc`
- `0x180008498`
- `0x180008a68`
- `0x180008f20`
- `0x180009150`
- `0x180009180`
- `0x180009268`
- `0x18000df24`
- `0x18000e03c`
- `0x18001adb4`
- `0x18001c920`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall PTGetPrintCapabilitiesImp(
        HPTPROVIDER this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 **a3,
        struct IXMLDOMDocument2 *a4)
{
  struct IXMLDOMDocument2 *v4; // r12
  __int64 v9; // rcx
  struct IXMLDOMDocument2 *v10; // rax
  struct IPrintTicketProvider *v11; // rbx
  int (*v12)(HPTPROVIDER, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **, unsigned __int16 **); // rdx
  struct NPrintTicketUtil::TFeatureListRoot *v13; // r8
  int v14; // esi
  struct NPrintTicketUtil::TFeatureListRoot **v15; // r9
  unsigned __int16 *v16; // rcx
  struct NPrintTicketUtil::TFeatureListRoot *v17; // rdx
  NPrintTicketUtil *v18; // rdi
  NPrintTicketUtil *v19; // r15
  struct IXMLDOMDocument2 **v20; // [rsp+28h] [rbp-38h]
  void **v21; // [rsp+30h] [rbp-30h] BYREF
  __int128 v22; // [rsp+38h] [rbp-28h]
  __int64 v23; // [rsp+48h] [rbp-18h]
  __int16 v24; // [rsp+50h] [rbp-10h]
  int v25; // [rsp+54h] [rbp-Ch]
  NPrintTicketUtil *v26; // [rsp+90h] [rbp+30h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+48h] BYREF

  v27 = 0;
  v4 = (struct IXMLDOMDocument2 *)&v27;
  if ( a4 )
    v4 = a4;
  if ( this && this == *((HPTPROVIDER *)this + 2) && a3 )
  {
    if ( a2 && (unsigned int)NPrintTicketUtil::IsValidPrintTicket(a2, v4, (unsigned __int16 **)a3) )
      return 2147745795LL;
    *a3 = 0;
    if ( !a2 )
    {
      v9 = *((_QWORD *)this + 8);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      v10 = (struct IXMLDOMDocument2 *)*((_QWORD *)this + 8);
      if ( v10 )
      {
        v14 = 0;
        *a3 = v10;
        return (unsigned int)v14;
      }
      *a3 = 0;
    }
    v11 = TProviderInfo::Provider((TProviderInfo *)this);
    if ( a2 )
    {
      v23 = 0;
      v21 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v22 = 0;
      if ( (int)NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v21, a2, 0) >= 0
        && (int)TProviderInfo::GetSupportedFeaturesList((TProviderInfo *)this, v12, &v26, (unsigned __int16 **)v4) >= 0 )
      {
        NPrintTicketUtil::AutoMapPrintTicketToFeatureList((NPrintTicketUtil *)&v21, v26, v13);
      }
      NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v21);
    }
    if ( v11 )
    {
      v14 = ((__int64 (__fastcall *)(struct IPrintTicketProvider *, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **))v11->lpVtbl->GetPrintCapabilities)(
              v11,
              a2,
              a3);
    }
    else
    {
      v14 = publicdm::AcquirePublicDeviceCapabilities(
              *((publicdm **)this + 3),
              *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 11),
              *((struct _devicemodeW **)this + 10),
              a2,
              a3,
              v20);
      if ( v14 == 1 )
      {
        v14 = 0;
        goto LABEL_22;
      }
    }
    if ( v14 < 0 )
      goto LABEL_32;
LABEL_22:
    v16 = (unsigned __int16 *)*a3;
    if ( !*a3 )
    {
      v14 = -2147418113;
LABEL_32:
      if ( v11 )
        ((void (__fastcall *)(struct IPrintTicketProvider *))v11->lpVtbl->Release)(v11);
      return (unsigned int)v14;
    }
    v26 = 0;
    if ( (unsigned int)NPrintTicketUtil::IsValidPrintCapabilities((struct IXMLDOMDocument2 *)v16, v4, &v26, v15) )
    {
      v14 = -2147221500;
    }
    else if ( !a2 )
    {
      if ( *a3 )
      {
        NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<unsigned long>>::operator=(this + 16);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 8LL))(*((_QWORD *)this + 8));
      }
      v18 = v26;
      v19 = 0;
      if ( v26 )
      {
        v19 = v26;
        v18 = 0;
      }
      if ( *((_QWORD *)this + 12) )
        NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(this + 24);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(this + 24);
      *((_QWORD *)this + 12) = v19;
      goto LABEL_30;
    }
    v18 = v26;
LABEL_30:
    if ( v18 )
      NPrintTicketUtil::DeletePrintTicketFeatureList(v18, v17);
    goto LABEL_32;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008f20  mov     [rsp-28h+arg_8], rbx
0x180008f25  mov     [rsp-28h+arg_10], rsi
0x180008f2a  push    rbp
0x180008f2b  push    rdi
0x180008f2c  push    r12
0x180008f2e  push    r14
0x180008f30  push    r15
0x180008f32  mov     rbp, rsp
0x180008f35  sub     rsp, 60h
0x180008f39  test    r9, r9
0x180008f3c  mov     [rbp+arg_18], 0
0x180008f44  lea     r12, [rbp+arg_18]
0x180008f48  mov     rdi, r8
0x180008f4b  cmovnz  r12, r9
0x180008f4f  mov     r15, rdx
0x180008f52  mov     r14, rcx
0x180008f55  test    rcx, rcx
0x180008f58  jz      loc_18000912A
0x180008f5e  cmp     rcx, [rcx+10h]
0x180008f62  jnz     loc_18000912A
0x180008f68  test    r8, r8
0x180008f6b  jz      loc_18000912A
0x180008f71  test    rdx, rdx
0x180008f74  jz      short loc_180008F8F
0x180008f76  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180008f79  mov     rcx, r15; this
0x180008f7c  call    ?IsValidPrintTicket@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintTicket(IXMLDOMDocument2 *,ushort * *)
0x180008f81  test    eax, eax
0x180008f83  jz      short loc_180008F8F
0x180008f85  mov     eax, 80040003h
0x180008f8a  jmp     loc_18000912F
0x180008f8f  mov     qword ptr [rdi], 0
0x180008f96  test    r15, r15
0x180008f99  jnz     short loc_180008FC0
0x180008f9b  mov     rcx, [r14+40h]
0x180008f9f  test    rcx, rcx
0x180008fa2  jz      short loc_180008FB0
0x180008fa4  mov     rax, [rcx]
0x180008fa7  mov     rax, [rax+8]
0x180008fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb0  mov     rax, [r14+40h]
0x180008fb4  test    rax, rax
0x180008fb7  jnz     loc_180009063
0x180008fbd  mov     [rdi], rax
0x180008fc0  mov     rcx, r14; this
0x180008fc3  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x180008fc8  mov     rbx, rax
0x180008fcb  test    r15, r15
0x180008fce  jz      short loc_180009034
0x180008fd0  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180008fd7  mov     [rbp+var_18], 0
0x180008fdf  mov     [rbp+var_30], rax
0x180008fe3  lea     rcx, [rbp+var_30]; this
0x180008fe7  xor     eax, eax
0x180008fe9  xorps   xmm0, xmm0
0x180008fec  xor     r8d, r8d; int
0x180008fef  mov     [rbp+var_10], ax
0x180008ff3  mov     rdx, r15; struct IXMLDOMDocument2 *
0x180008ff6  mov     [rbp+var_C], eax
0x180008ff9  mov     [rbp+arg_0], rax
0x180008ffd  movdqu  [rbp+var_28], xmm0
0x180009002  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180009007  test    eax, eax
0x180009009  js      short loc_18000902B
0x18000900b  mov     r9, r12; unsigned __int16 **
0x18000900e  lea     r8, [rbp+arg_0]; struct NPrintTicketUtil::TFeatureListRoot **
0x180009012  mov     rcx, r14; this
0x180009015  call    ?GetSupportedFeaturesList@TProviderInfo@@QEAAJP6AJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@PEAPEAU3@PEAPEAG@ZPEAPEAUTFeatureListRoot@NPrintTicketUtil@@3@Z; TProviderInfo::GetSupportedFeaturesList(long (*)(HPTPROVIDER__ *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *,ushort * *),NPrintTicketUtil::TFeatureListRoot * *,ushort * *)
0x18000901a  test    eax, eax
0x18000901c  js      short loc_18000902B
0x18000901e  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180009022  lea     rcx, [rbp+var_30]; this
0x180009026  call    ?AutoMapPrintTicketToFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::AutoMapPrintTicketToFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot *)
0x18000902b  lea     rcx, [rbp+var_30]; this
0x18000902f  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180009034  test    rbx, rbx
0x180009037  jz      short loc_18000906A
0x180009039  mov     rax, [rbx]
0x18000903c  mov     r8, rdi
0x18000903f  mov     rdx, r15
0x180009042  mov     rcx, rbx
0x180009045  mov     rax, [rax+40h]
0x180009049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000904e  mov     esi, eax
0x180009050  test    esi, esi
0x180009052  js      short loc_1800090BC
0x180009054  mov     rcx, [rdi]; this
0x180009057  test    rcx, rcx
0x18000905a  jnz     short loc_18000908E
0x18000905c  mov     esi, 8000FFFFh
0x180009061  jmp     short loc_1800090BC
0x180009063  xor     esi, esi
0x180009065  mov     [rdi], rax
0x180009068  jmp     short loc_1800090D0
0x18000906a  mov     r8, [r14+50h]; struct _devicemodeW *
0x18000906e  mov     r9, r15; struct IXMLDOMDocument2 *
0x180009071  mov     rdx, [r14+58h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180009075  mov     rcx, [r14+18h]; this
0x180009079  mov     [rsp+60h+var_40], rdi; struct IXMLDOMDocument2 **
0x18000907e  call    ?AcquirePublicDeviceCapabilities@publicdm@@YAJPEAXPEBG1PEAUIXMLDOMDocument2@@PEAPEAU2@@Z; publicdm::AcquirePublicDeviceCapabilities(void *,ushort const *,ushort const *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *)
0x180009083  mov     esi, eax
0x180009085  cmp     eax, 1
0x180009088  jnz     short loc_180009050
0x18000908a  xor     esi, esi
0x18000908c  jmp     short loc_180009054
0x18000908e  lea     r8, [rbp+arg_0]; struct NPrintTicketUtil::TFeatureListRoot **
0x180009092  mov     [rbp+arg_0], 0
0x18000909a  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18000909d  call    ?IsValidPrintCapabilities@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAGPEAPEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::IsValidPrintCapabilities(IXMLDOMDocument2 *,ushort * *,NPrintTicketUtil::TFeatureListRoot * *)
0x1800090a2  test    eax, eax
0x1800090a4  jz      short loc_1800090D4
0x1800090a6  mov     esi, 80040004h
0x1800090ab  mov     rdi, [rbp+arg_0]
0x1800090af  test    rdi, rdi
0x1800090b2  jz      short loc_1800090BC
0x1800090b4  mov     rcx, rdi; this
0x1800090b7  call    ?DeletePrintTicketFeatureList@NPrintTicketUtil@@YAXPEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::DeletePrintTicketFeatureList(NPrintTicketUtil::TFeatureListRoot *)
0x1800090bc  test    rbx, rbx
0x1800090bf  jz      short loc_1800090D0
0x1800090c1  mov     rax, [rbx]
0x1800090c4  mov     rcx, rbx
0x1800090c7  mov     rax, [rax+10h]
0x1800090cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d0  mov     eax, esi
0x1800090d2  jmp     short loc_18000912F
0x1800090d4  test    r15, r15
0x1800090d7  jnz     short loc_1800090AB
0x1800090d9  mov     rdx, [rdi]
0x1800090dc  test    rdx, rdx
0x1800090df  jz      short loc_1800090FA
0x1800090e1  lea     rcx, [r14+40h]
0x1800090e5  call    ??4?$TAutoPtrCOM@V?$BufferEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@QEAAPEAV?$BufferEnumerator@K@NPrintTicketUtil@@PEAV23@@Z; NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::BufferEnumerator<ulong>>::operator=(NPrintTicketUtil::BufferEnumerator<ulong> *)
0x1800090ea  mov     rcx, [r14+40h]
0x1800090ee  mov     rax, [rcx]
0x1800090f1  mov     rax, [rax+8]
0x1800090f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090fa  mov     rdi, [rbp+arg_0]
0x1800090fe  xor     r15d, r15d
0x180009101  test    rdi, rdi
0x180009104  jz      short loc_18000910B
0x180009106  mov     r15, rdi
0x180009109  xor     edi, edi
0x18000910b  cmp     qword ptr [r14+60h], 0
0x180009110  jz      short loc_18000911B
0x180009112  lea     rcx, [r14+60h]
0x180009116  call    ?Reset@?$TGenericSP@UTFeatureListRoot@NPrintTicketUtil@@VTAutoPtrFeatureList@2@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(void)
0x18000911b  lea     rcx, [r14+60h]
0x18000911f  call    ?Reset@?$TGenericSP@UTFeatureListRoot@NPrintTicketUtil@@VTAutoPtrFeatureList@2@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(void)
0x180009124  mov     [r14+60h], r15
0x180009128  jmp     short loc_1800090AF
0x18000912a  mov     eax, 80070057h
0x18000912f  lea     r11, [rsp+60h+var_s0]
0x180009134  mov     rbx, [r11+38h]
0x180009138  mov     rsi, [r11+40h]
0x18000913c  mov     rsp, r11
0x18000913f  pop     r15
0x180009141  pop     r14
0x180009143  pop     r12
0x180009145  pop     rdi
0x180009146  pop     rbp
0x180009147  retn
```
