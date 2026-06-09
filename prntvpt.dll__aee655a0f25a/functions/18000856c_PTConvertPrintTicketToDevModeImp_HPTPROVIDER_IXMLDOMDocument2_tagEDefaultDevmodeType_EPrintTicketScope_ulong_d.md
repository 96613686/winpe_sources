# PTConvertPrintTicketToDevModeImp(HPTPROVIDER__ *,IXMLDOMDocument2 *,tagEDefaultDevmodeType,EPrintTicketScope,ulong *,_devicemodeW * *,ushort * *)

- ea: `0x18000856c`
- end: `0x1800087cf`
- name: `?PTConvertPrintTicketToDevModeImp@@YAJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@W4tagEDefaultDevmodeType@@W4EPrintTicketScope@@PEAKPEAPEAU_devicemodeW@@PEAPEAG@Z`
- size: `611`
- prototype: `__int64 __fastcall(HPTPROVIDER this, struct IXMLDOMDocument2 *, unsigned __int16 **, enum EPrintTicketScope, unsigned int *, struct _devicemodeW **, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800121d0`

## callees

- `0x180003708`
- `0x180008498`
- `0x18000856c`
- `0x180008a68`
- `0x180009150`
- `0x180009268`
- `0x180009354`
- `0x18000c6e4`
- `0x18000df24`
- `0x18001c93c`
- `0x18001ea4c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000876b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000876b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008785`

## pseudocode

```c
__int64 __fastcall PTConvertPrintTicketToDevModeImp(
        HPTPROVIDER this,
        struct IXMLDOMDocument2 *a2,
        unsigned __int16 **a3,
        enum EPrintTicketScope a4,
        unsigned int *a5,
        struct _devicemodeW **a6,
        struct IXMLDOMDocument2 *a7)
{
  struct IXMLDOMDocument2 *v8; // r15
  unsigned int v9; // r13d
  unsigned int *v11; // r14
  LPVOID *v12; // rsi
  int IsValidPrintTicket; // eax
  int Devmode; // ebx
  int v16; // r9d
  int (*v17)(HPTPROVIDER, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **, unsigned __int16 **); // rdx
  struct NPrintTicketUtil::TFeatureListRoot *v18; // r8
  struct _devicemodeW *v19; // r9
  struct IPrintTicketProvider *v20; // rax
  struct IPrintTicketProvider *v21; // r15
  unsigned __int16 *v22; // [rsp+20h] [rbp-60h]
  struct _devicemodeW *v23; // [rsp+30h] [rbp-50h]
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  struct NPrintTicketUtil::CPrintTicketWrapper *v25; // [rsp+48h] [rbp-38h] BYREF
  __int64 v26; // [rsp+50h] [rbp-30h] BYREF
  void **v27; // [rsp+58h] [rbp-28h] BYREF
  __int128 v28; // [rsp+60h] [rbp-20h]
  __int64 v29; // [rsp+70h] [rbp-10h]
  __int16 v30; // [rsp+78h] [rbp-8h]
  int v31; // [rsp+7Ch] [rbp-4h]
  unsigned int v32; // [rsp+C0h] [rbp+40h] BYREF
  struct NPrintTicketUtil::CPrintTicketWrapper *v33; // [rsp+D8h] [rbp+58h]

  LODWORD(v33) = a4;
  v27 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v8 = (struct IXMLDOMDocument2 *)&v26;
  v26 = 0;
  v32 = 0;
  if ( a7 )
    v8 = a7;
  pv = 0;
  v29 = 0;
  v9 = (unsigned int)a3;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  v28 = 0;
  if ( !this || this != *((HPTPROVIDER *)this + 2) || !a2 || (v11 = a5) == 0 || (v12 = (LPVOID *)a6) == 0 )
  {
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v27);
    return 2147942487LL;
  }
  *a5 = 0;
  *v12 = 0;
  IsValidPrintTicket = NPrintTicketUtil::IsValidPrintTicket(a2, v8, a3);
  Devmode = IsValidPrintTicket;
  if ( IsValidPrintTicket == 1 )
  {
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v27);
    return 2147745795LL;
  }
  if ( IsValidPrintTicket >= 0 )
  {
    Devmode = publicdm::GetDevmode(*((_QWORD *)this + 3), v9, &v32, &pv);
    if ( Devmode >= 0 )
    {
      Devmode = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v27, a2, 0);
      if ( Devmode >= 0 )
      {
        Devmode = NPrintTicketUtil::FilterPrintTicket(
                    (NPrintTicketUtil *)&v27,
                    (struct NPrintTicketUtil::CPrintTicketWrapper *)(unsigned int)v33,
                    kPTPageScope,
                    v16);
        if ( Devmode >= 0 )
        {
          Devmode = TProviderInfo::GetSupportedFeaturesList((TProviderInfo *)this, v17, &v25, (unsigned __int16 **)v8);
          if ( Devmode >= 0 )
          {
            Devmode = NPrintTicketUtil::AutoMapPrintTicketToFeatureList((NPrintTicketUtil *)&v27, v25, v18);
            if ( Devmode >= 0 )
            {
              if ( ((_BYTE)this[11] & 1) != 0
                || (Devmode = publicdm::DevmodeSnapshotFromJT(
                                (publicdm *)&v27,
                                *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 10),
                                (const unsigned __int16 *)pv,
                                v19),
                    Devmode >= 0) )
              {
                v20 = TProviderInfo::Provider((TProviderInfo *)this);
                v21 = v20;
                if ( !v20 )
                {
                  *v11 = v32;
                  *v12 = pv;
                  pv = 0;
LABEL_22:
                  LODWORD(v22) = this[10];
                  Devmode = publicdm::JobTicketToPublicDevmode(
                              *((publicdm **)this + 3),
                              &v27,
                              *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 11),
                              *((const unsigned __int16 **)this + 10),
                              v22,
                              (unsigned int)*v12,
                              v23);
                  goto LABEL_23;
                }
                Devmode = ((__int64 (__fastcall *)(struct IPrintTicketProvider *, struct IXMLDOMDocument2 *, _QWORD, LPVOID, unsigned int *, LPVOID *))v20->lpVtbl->ConvertPrintTicketToDevMode)(
                            v20,
                            a2,
                            v32,
                            pv,
                            v11,
                            v12);
                ((void (__fastcall *)(struct IPrintTicketProvider *))v21->lpVtbl->Release)(v21);
                if ( Devmode >= 0 )
                  goto LABEL_22;
              }
            }
          }
        }
      }
    }
  }
LABEL_23:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( Devmode < 0 )
  {
    if ( *v12 )
      CoTaskMemFree(*v12);
    *v12 = 0;
    *v11 = 0;
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v27);
  return (unsigned int)Devmode;
}

```

## disassembly

```asm
0x18000856c  mov     [rsp-38h+arg_8], rbx
0x180008571  mov     dword ptr [rsp-38h+arg_18], r9d
0x180008576  push    rbp
0x180008577  push    rsi
0x180008578  push    rdi
0x180008579  push    r12
0x18000857b  push    r13
0x18000857d  push    r14
0x18000857f  push    r15
0x180008581  mov     rbp, rsp
0x180008584  sub     rsp, 80h
0x18000858b  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180008592  mov     rdi, rcx
0x180008595  xor     ecx, ecx
0x180008597  mov     [rbp+var_28], rax
0x18000859b  mov     rax, [rbp+arg_30]
0x18000859f  lea     r15, [rbp+var_30]
0x1800085a3  test    rax, rax
0x1800085a6  mov     [rbp+var_30], rcx
0x1800085aa  xorps   xmm0, xmm0
0x1800085ad  mov     [rbp+arg_0], ecx
0x1800085b0  cmovnz  r15, rax
0x1800085b4  mov     [rbp+pv], rcx
0x1800085b8  mov     [rbp+var_10], rcx
0x1800085bc  mov     r13d, r8d
0x1800085bf  mov     [rbp+var_8], cx
0x1800085c3  mov     r12, rdx
0x1800085c6  mov     [rbp+var_4], ecx
0x1800085c9  mov     [rbp+var_38], rcx
0x1800085cd  movdqu  [rbp+var_20], xmm0
0x1800085d2  test    rdi, rdi
0x1800085d5  jz      loc_1800087A6
0x1800085db  cmp     rdi, [rdi+10h]
0x1800085df  jnz     loc_1800087A6
0x1800085e5  test    rdx, rdx
0x1800085e8  jz      loc_1800087A6
0x1800085ee  mov     r14, [rbp+arg_20]
0x1800085f2  test    r14, r14
0x1800085f5  jz      loc_1800087A6
0x1800085fb  mov     rsi, [rbp+arg_28]
0x1800085ff  test    rsi, rsi
0x180008602  jz      loc_1800087A6
0x180008608  mov     [r14], ecx
0x18000860b  mov     rdx, r15; struct IXMLDOMDocument2 *
0x18000860e  mov     [rsi], rcx
0x180008611  mov     rcx, r12; this
0x180008614  call    ?IsValidPrintTicket@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintTicket(IXMLDOMDocument2 *,ushort * *)
0x180008619  mov     ebx, eax
0x18000861b  cmp     eax, 1
0x18000861e  jnz     short loc_180008633
0x180008620  lea     rcx, [rbp+var_28]; this
0x180008624  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180008629  mov     eax, 80040003h
0x18000862e  jmp     loc_1800087B4
0x180008633  test    eax, eax
0x180008635  js      loc_180008762
0x18000863b  mov     rcx, [rdi+18h]
0x18000863f  lea     r9, [rbp+pv]
0x180008643  lea     r8, [rbp+arg_0]
0x180008647  mov     edx, r13d
0x18000864a  call    ?GetDevmode@publicdm@@YAJPEAXW4DEVMODE_TYPE@1@PEAKPEAPEAU_devicemodeW@@@Z; publicdm::GetDevmode(void *,publicdm::DEVMODE_TYPE,ulong *,_devicemodeW * *)
0x18000864f  mov     ebx, eax
0x180008651  test    eax, eax
0x180008653  js      loc_180008762
0x180008659  xor     r8d, r8d; int
0x18000865c  lea     rcx, [rbp+var_28]; this
0x180008660  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180008663  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180008668  mov     ebx, eax
0x18000866a  test    eax, eax
0x18000866c  js      loc_180008762
0x180008672  mov     edx, dword ptr [rbp+arg_18]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180008675  lea     rcx, [rbp+var_28]; this
0x180008679  xor     r8d, r8d; enum EPrintTicketScope
0x18000867c  call    ?FilterPrintTicket@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@W4EPrintTicketScope@@H@Z; NPrintTicketUtil::FilterPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,EPrintTicketScope,int)
0x180008681  mov     ebx, eax
0x180008683  test    eax, eax
0x180008685  js      loc_180008762
0x18000868b  mov     r9, r15; unsigned __int16 **
0x18000868e  lea     r8, [rbp+var_38]; struct NPrintTicketUtil::TFeatureListRoot **
0x180008692  mov     rcx, rdi; this
0x180008695  call    ?GetSupportedFeaturesList@TProviderInfo@@QEAAJP6AJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@PEAPEAU3@PEAPEAG@ZPEAPEAUTFeatureListRoot@NPrintTicketUtil@@3@Z; TProviderInfo::GetSupportedFeaturesList(long (*)(HPTPROVIDER__ *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *,ushort * *),NPrintTicketUtil::TFeatureListRoot * *,ushort * *)
0x18000869a  mov     ebx, eax
0x18000869c  test    eax, eax
0x18000869e  js      loc_180008762
0x1800086a4  mov     rdx, [rbp+var_38]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800086a8  lea     rcx, [rbp+var_28]; this
0x1800086ac  call    ?AutoMapPrintTicketToFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::AutoMapPrintTicketToFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot *)
0x1800086b1  mov     ebx, eax
0x1800086b3  test    eax, eax
0x1800086b5  js      loc_180008762
0x1800086bb  test    byte ptr [rdi+2Ch], 1
0x1800086bf  jnz     short loc_1800086DC
0x1800086c1  mov     r8, [rbp+pv]; unsigned __int16 *
0x1800086c5  lea     rcx, [rbp+var_28]; this
0x1800086c9  mov     rdx, [rdi+50h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800086cd  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x1800086d2  mov     ebx, eax
0x1800086d4  test    eax, eax
0x1800086d6  js      loc_180008762
0x1800086dc  mov     rcx, rdi; this
0x1800086df  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x1800086e4  mov     r15, rax
0x1800086e7  test    rax, rax
0x1800086ea  jz      short loc_180008727
0x1800086ec  mov     rcx, [rax]
0x1800086ef  mov     rdx, r12
0x1800086f2  mov     r9, [rbp+pv]
0x1800086f6  mov     r8d, [rbp+arg_0]
0x1800086fa  mov     qword ptr [rsp+80h+var_58], rsi
0x1800086ff  mov     rax, [rcx+30h]
0x180008703  mov     rcx, r15
0x180008706  mov     [rsp+80h+var_60], r14
0x18000870b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008710  mov     ebx, eax
0x180008712  mov     rcx, r15
0x180008715  mov     rax, [r15]
0x180008718  mov     rax, [rax+10h]
0x18000871c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008721  test    ebx, ebx
0x180008723  js      short loc_180008762
0x180008725  jmp     short loc_18000873C
0x180008727  mov     eax, [rbp+arg_0]
0x18000872a  mov     [r14], eax
0x18000872d  mov     rax, [rbp+pv]
0x180008731  mov     [rsi], rax
0x180008734  mov     [rbp+pv], 0
0x18000873c  mov     ecx, [rdi+28h]
0x18000873f  lea     rdx, [rbp+var_28]; void *
0x180008743  mov     rax, [rsi]
0x180008746  mov     r9, [rdi+50h]; unsigned __int16 *
0x18000874a  mov     r8, [rdi+58h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000874e  mov     qword ptr [rsp+80h+var_58], rax; unsigned int
0x180008753  mov     dword ptr [rsp+80h+var_60], ecx; unsigned __int16 *
0x180008757  mov     rcx, [rdi+18h]; this
0x18000875b  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x180008760  mov     ebx, eax
0x180008762  mov     rcx, [rbp+pv]; pv
0x180008766  test    rcx, rcx
0x180008769  jz      short loc_180008779
0x18000876b  call    cs:__imp_CoTaskMemFree
0x180008771  mov     [rbp+pv], 0
0x180008779  test    ebx, ebx
0x18000877b  jns     short loc_180008799
0x18000877d  mov     rcx, [rsi]; pv
0x180008780  test    rcx, rcx
0x180008783  jz      short loc_18000878B
0x180008785  call    cs:__imp_CoTaskMemFree
0x18000878b  mov     qword ptr [rsi], 0
0x180008792  mov     dword ptr [r14], 0
0x180008799  lea     rcx, [rbp+var_28]; this
0x18000879d  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x1800087a2  mov     eax, ebx
0x1800087a4  jmp     short loc_1800087B4
0x1800087a6  lea     rcx, [rbp+var_28]; this
0x1800087aa  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x1800087af  mov     eax, 80070057h
0x1800087b4  mov     rbx, [rsp+80h+arg_8]
0x1800087bc  add     rsp, 80h
0x1800087c3  pop     r15
0x1800087c5  pop     r14
0x1800087c7  pop     r13
0x1800087c9  pop     r12
0x1800087cb  pop     rdi
0x1800087cc  pop     rsi
0x1800087cd  pop     rbp
0x1800087ce  retn
```
