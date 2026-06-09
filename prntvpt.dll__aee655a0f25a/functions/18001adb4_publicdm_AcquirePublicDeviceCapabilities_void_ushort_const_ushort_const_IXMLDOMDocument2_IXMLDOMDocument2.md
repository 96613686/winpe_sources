# publicdm::AcquirePublicDeviceCapabilities(void *,ushort const *,ushort const *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *)

- ea: `0x18001adb4`
- end: `0x18001b056`
- name: `?AcquirePublicDeviceCapabilities@publicdm@@YAJPEAXPEBG1PEAUIXMLDOMDocument2@@PEAPEAU2@@Z`
- size: `674`
- prototype: `__int64 __fastcall(publicdm *this, const WCHAR *, struct _devicemodeW *, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008f20`

## callees

- `0x180008a68`
- `0x180008acc`
- `0x180009214`
- `0x180009268`
- `0x1800093dc`
- `0x18000c6e4`
- `0x18001adb4`
- `0x18001b590`
- `0x18001c93c`
- `0x18001ca28`
- `0x18001ea4c`
- `0x18001eb5c`
- `0x1800225b8`
- `0x180023010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001b00b`
- `KERNEL32!FreeLibrary` at `0x18001b00b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ae4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ae4d`

## pseudocode

```c
__int64 __fastcall publicdm::AcquirePublicDeviceCapabilities(
        publicdm *this,
        const WCHAR *a2,
        struct _devicemodeW *a3,
        struct IXMLDOMDocument2 *a4,
        struct IXMLDOMDocument2 **a5)
{
  int Devmode; // ebx
  void *v10; // rdi
  unsigned int v11; // ebx
  void *v12; // rax
  const unsigned __int16 *v13; // rcx
  struct _devicemodeW *v14; // r9
  int v15; // eax
  struct IXMLDOMElement **v16; // r8
  HMODULE v17; // rsi
  struct NPrintTicketUtil::CPrintTicketWrapper *v18; // r9
  int i; // r14d
  __int64 (__fastcall *v20)(_QWORD *); // rax
  unsigned __int16 *v22; // [rsp+20h] [rbp-E0h]
  void *Src; // [rsp+30h] [rbp-D0h] BYREF
  SIZE_T cb; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE hLibModule; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v26[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int16 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+6Ch] [rbp-94h]
  void **v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int16 v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+94h] [rbp-6Ch]
  _QWORD v36[5]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v37[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  __int128 v40; // [rsp+F0h] [rbp-10h]
  HMODULE v41; // [rsp+100h] [rbp+0h]
  void *v42; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v43; // [rsp+110h] [rbp+10h]

  *(_QWORD *)v26 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v28 = 0;
  v29 = 0;
  v30 = 0;
  Src = 0;
  LODWORD(cb) = 0;
  hLibModule = 0;
  v27 = 0;
  if ( a5 )
  {
    v10 = 0;
    *a5 = 0;
    Devmode = publicdm::GetDevmode(this, 0, (unsigned int *)&cb, &Src);
    if ( Devmode >= 0 )
    {
      v11 = cb;
      v12 = CoTaskMemAlloc((unsigned int)cb);
      v10 = v12;
      if ( v12 )
      {
        memcpy_0(v12, Src, v11);
        if ( !a4 )
          goto LABEL_10;
        v33 = 0;
        v31 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
        v34 = 0;
        v35 = 0;
        v32 = 0;
        Devmode = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                    (NPrintTicketUtil::CPrintTicketWrapper *)&v31,
                    a4,
                    0);
        if ( Devmode >= 0 )
        {
          Devmode = publicdm::DevmodeSnapshotFromJT(
                      (publicdm *)&v31,
                      (struct NPrintTicketUtil::CPrintTicketWrapper *)a3,
                      (const unsigned __int16 *)Src,
                      v14);
          if ( Devmode >= 0 )
          {
            LODWORD(v22) = 0;
            Devmode = publicdm::JobTicketToPublicDevmode(this, &v31, a2, a3->dmDeviceName, v22, (DEVMODEW *)Src);
          }
        }
        NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v31);
        if ( Devmode >= 0 )
        {
LABEL_10:
          v15 = LoadImageFromSystemDirectory(v13, &hLibModule);
          v17 = hLibModule;
          Devmode = v15;
          if ( v15 >= 0 )
          {
            v36[2] = Src;
            v36[1] = this;
            v37[0] = &NPrintTicketUtil::CPrinterWrapper::`vftable';
            v36[3] = a2;
            v36[0] = &publicdm::CPrintCapsInfo::`vftable';
            v43 = v26;
            v36[4] = a3;
            v37[1] = this;
            v37[2] = a2;
            v38 = 0;
            v39 = 0;
            v40 = 0;
            v41 = hLibModule;
            v42 = v10;
            v30 = 1;
            Devmode = NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
                        (NPrintTicketUtil::CPrintTicketWrapper *)v26,
                        L"psf:PrintCapabilities",
                        v16);
            if ( Devmode >= 0 )
              Devmode = publicdm::DevmodeSnapshotToPC((publicdm *)Src, a3, v26, v18);
            for ( i = 0; Devmode >= 0; Devmode = v20(v36) )
            {
              v20 = (__int64 (__fastcall *)(_QWORD *))*(&funcs_18001AFCE + 5 * i);
              if ( !v20 )
                break;
              ++i;
            }
            v36[0] = &publicdm::CCommonInfo::`vftable';
            NPrintTicketUtil::CPrinterWrapper::~CPrinterWrapper((NPrintTicketUtil::CPrinterWrapper *)v37);
            if ( Devmode >= 0 )
              Devmode = NPrintTicketUtil::CPrintTicketWrapper::GetXML((NPrintTicketUtil::CPrintTicketWrapper *)v26, a5);
          }
          if ( v17 )
            FreeLibrary(v17);
        }
      }
      else
      {
        Devmode = -2147024882;
      }
    }
    if ( Src )
      CoTaskMemFree(Src);
    if ( v10 )
      CoTaskMemFree(v10);
  }
  else
  {
    Devmode = -2147024809;
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v26);
  return (unsigned int)Devmode;
}

```

## disassembly

```asm
0x18001adb4  push    rbp
0x18001adb6  push    rbx
0x18001adb7  push    rsi
0x18001adb8  push    rdi
0x18001adb9  push    r12
0x18001adbb  push    r13
0x18001adbd  push    r14
0x18001adbf  push    r15
0x18001adc1  lea     rbp, [rsp-28h]
0x18001adc6  sub     rsp, 128h
0x18001adcd  mov     r12, [rbp+60h+arg_20]
0x18001add4  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18001addb  mov     r15, rcx
0x18001adde  mov     qword ptr [rsp+160h+var_118], rax
0x18001ade3  xor     ecx, ecx
0x18001ade5  xorps   xmm0, xmm0
0x18001ade8  mov     [rsp+160h+var_100], rcx
0x18001aded  mov     rsi, r9
0x18001adf0  mov     [rsp+160h+var_F8], cx
0x18001adf5  mov     r14, r8
0x18001adf8  mov     [rsp+160h+var_F4], ecx
0x18001adfc  mov     r13, rdx
0x18001adff  mov     [rsp+160h+Src], rcx; struct _devicemodeW *
0x18001ae04  mov     dword ptr [rsp+160h+cb], ecx
0x18001ae08  mov     [rsp+160h+hLibModule], rcx
0x18001ae0d  movdqu  [rsp+160h+var_110], xmm0
0x18001ae13  test    r12, r12
0x18001ae16  jnz     short loc_18001AE22
0x18001ae18  mov     ebx, 80070057h
0x18001ae1d  jmp     loc_18001B036
0x18001ae22  mov     rdi, rcx
0x18001ae25  mov     [r12], rcx
0x18001ae29  mov     rcx, r15
0x18001ae2c  lea     r9, [rsp+160h+Src]
0x18001ae31  lea     r8, [rsp+160h+cb]
0x18001ae36  xor     edx, edx
0x18001ae38  call    ?GetDevmode@publicdm@@YAJPEAXW4DEVMODE_TYPE@1@PEAKPEAPEAU_devicemodeW@@@Z; publicdm::GetDevmode(void *,publicdm::DEVMODE_TYPE,ulong *,_devicemodeW * *)
0x18001ae3d  mov     ebx, eax
0x18001ae3f  test    eax, eax
0x18001ae41  js      loc_18001B018
0x18001ae47  mov     ebx, dword ptr [rsp+160h+cb]
0x18001ae4b  mov     ecx, ebx; cb
0x18001ae4d  call    cs:__imp_CoTaskMemAlloc
0x18001ae53  mov     rdi, rax
0x18001ae56  test    rax, rax
0x18001ae59  jz      loc_18001B013
0x18001ae5f  mov     rdx, [rsp+160h+Src]; Src
0x18001ae64  mov     r8d, ebx; Size
0x18001ae67  mov     rcx, rax; void *
0x18001ae6a  call    memcpy_0
0x18001ae6f  test    rsi, rsi
0x18001ae72  jz      loc_18001AF05
0x18001ae78  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18001ae7f  mov     [rbp+60h+var_D8], 0
0x18001ae87  mov     [rsp+160h+var_F0], rax
0x18001ae8c  lea     rcx, [rsp+160h+var_F0]; this
0x18001ae91  xor     eax, eax
0x18001ae93  xorps   xmm0, xmm0
0x18001ae96  xor     r8d, r8d; int
0x18001ae99  mov     [rbp+60h+var_D0], ax
0x18001ae9d  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x18001aea0  mov     [rbp+60h+var_CC], eax
0x18001aea3  movdqu  [rsp+160h+var_E8], xmm0
0x18001aea9  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18001aeae  mov     ebx, eax
0x18001aeb0  test    eax, eax
0x18001aeb2  js      short loc_18001AEF3
0x18001aeb4  mov     r8, [rsp+160h+Src]; unsigned __int16 *
0x18001aeb9  lea     rcx, [rsp+160h+var_F0]; this
0x18001aebe  mov     rdx, r14; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001aec1  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x18001aec6  mov     ebx, eax
0x18001aec8  test    eax, eax
0x18001aeca  js      short loc_18001AEF3
0x18001aecc  mov     rax, [rsp+160h+Src]
0x18001aed1  lea     rdx, [rsp+160h+var_F0]; void *
0x18001aed6  mov     qword ptr [rsp+160h+var_138], rax; unsigned int
0x18001aedb  mov     r9, r14; unsigned __int16 *
0x18001aede  mov     r8, r13; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001aee1  mov     dword ptr [rsp+160h+var_140], 0; unsigned __int16 *
0x18001aee9  mov     rcx, r15; this
0x18001aeec  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x18001aef1  mov     ebx, eax
0x18001aef3  lea     rcx, [rsp+160h+var_F0]; this
0x18001aef8  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18001aefd  test    ebx, ebx
0x18001aeff  js      loc_18001B018
0x18001af05  lea     rdx, [rsp+160h+hLibModule]; HINSTANCE *
0x18001af0a  call    ?LoadImageFromSystemDirectory@@YAJPEBGPEAPEAUHINSTANCE__@@@Z; LoadImageFromSystemDirectory(ushort const *,HINSTANCE__ * *)
0x18001af0f  mov     rsi, [rsp+160h+hLibModule]
0x18001af14  mov     ebx, eax
0x18001af16  test    eax, eax
0x18001af18  js      loc_18001B003
0x18001af1e  mov     rax, [rsp+160h+Src]
0x18001af23  lea     rdx, aPsfPrintcapabi; "psf:PrintCapabilities"
0x18001af2a  mov     [rbp+60h+var_B0], rax
0x18001af2e  lea     rcx, [rsp+160h+var_118]; this
0x18001af33  lea     rax, ??_7CPrinterWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrinterWrapper::`vftable'
0x18001af3a  mov     [rbp+60h+var_B8], r15
0x18001af3e  mov     [rbp+60h+var_98], rax
0x18001af42  xorps   xmm0, xmm0
0x18001af45  lea     rax, ??_7CPrintCapsInfo@publicdm@@6B@; const publicdm::CPrintCapsInfo::`vftable'
0x18001af4c  mov     [rbp+60h+var_A8], r13
0x18001af50  mov     [rbp+60h+var_C0], rax
0x18001af54  lea     rax, [rsp+160h+var_118]
0x18001af59  mov     [rbp+60h+var_50], rax
0x18001af5d  mov     [rbp+60h+var_A0], r14
0x18001af61  mov     [rbp+60h+var_90], r15
0x18001af65  mov     [rbp+60h+var_88], r13
0x18001af69  mov     [rbp+60h+var_80], 0
0x18001af70  mov     [rbp+60h+var_78], 0
0x18001af78  movdqa  [rbp+60h+var_70], xmm0
0x18001af7d  mov     [rbp+60h+var_60], rsi
0x18001af81  mov     [rbp+60h+var_58], rdi
0x18001af85  mov     [rsp+160h+var_F4], 1
0x18001af8d  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x18001af92  mov     ebx, eax
0x18001af94  test    eax, eax
0x18001af96  js      short loc_18001AFAC
0x18001af98  mov     rcx, [rsp+160h+Src]; this
0x18001af9d  lea     r8, [rsp+160h+var_118]; unsigned __int16 *
0x18001afa2  mov     rdx, r14; struct _devicemodeW *
0x18001afa5  call    ?DevmodeSnapshotToPC@publicdm@@YAJPEAU_devicemodeW@@PEBGPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::DevmodeSnapshotToPC(_devicemodeW *,ushort const *,NPrintTicketUtil::CPrintTicketWrapper *)
0x18001afaa  mov     ebx, eax
0x18001afac  xor     r14d, r14d
0x18001afaf  test    ebx, ebx
0x18001afb1  js      short loc_18001AFDC
0x18001afb3  movsxd  rax, r14d
0x18001afb6  lea     rcx, [rax+rax*4]
0x18001afba  lea     rax, funcs_18001AFCE
0x18001afc1  mov     rax, ds:(funcs_18001AFCE - 180024060h)[rax+rcx*8]
0x18001afc5  test    rax, rax
0x18001afc8  jz      short loc_18001AFDC
0x18001afca  lea     rcx, [rbp+60h+var_C0]; this
0x18001afce  call    _guard_dispatch_icall$thunk$10345483385596137414; publicdm::CollateToPrintCapabilities(publicdm::CPrintCapsInfo &) ...
0x18001afd3  inc     r14d
0x18001afd6  mov     ebx, eax
0x18001afd8  test    eax, eax
0x18001afda  jns     short loc_18001AFB3
0x18001afdc  lea     rax, ??_7CCommonInfo@publicdm@@6B@; const publicdm::CCommonInfo::`vftable'
0x18001afe3  lea     rcx, [rbp+60h+var_98]; this
0x18001afe7  mov     [rbp+60h+var_C0], rax
0x18001afeb  call    ??1CPrinterWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrinterWrapper::~CPrinterWrapper(void)
0x18001aff0  test    ebx, ebx
0x18001aff2  js      short loc_18001B003
0x18001aff4  mov     rdx, r12; struct IXMLDOMDocument2 **
0x18001aff7  lea     rcx, [rsp+160h+var_118]; this
0x18001affc  call    ?GetXML@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetXML(IXMLDOMDocument2 * *)
0x18001b001  mov     ebx, eax
0x18001b003  test    rsi, rsi
0x18001b006  jz      short loc_18001B018
0x18001b008  mov     rcx, rsi; hLibModule
0x18001b00b  call    cs:__imp_FreeLibrary
0x18001b011  jmp     short loc_18001B018
0x18001b013  mov     ebx, 8007000Eh
0x18001b018  mov     rcx, [rsp+160h+Src]; pv
0x18001b01d  test    rcx, rcx
0x18001b020  jz      short loc_18001B028
0x18001b022  call    cs:__imp_CoTaskMemFree
0x18001b028  test    rdi, rdi
0x18001b02b  jz      short loc_18001B036
0x18001b02d  mov     rcx, rdi; pv
0x18001b030  call    cs:__imp_CoTaskMemFree
0x18001b036  lea     rcx, [rsp+160h+var_118]; this
0x18001b03b  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18001b040  mov     eax, ebx
0x18001b042  add     rsp, 128h
0x18001b049  pop     r15
0x18001b04b  pop     r14
0x18001b04d  pop     r13
0x18001b04f  pop     r12
0x18001b051  pop     rdi
0x18001b052  pop     rsi
0x18001b053  pop     rbx
0x18001b054  pop     rbp
0x18001b055  retn
```
