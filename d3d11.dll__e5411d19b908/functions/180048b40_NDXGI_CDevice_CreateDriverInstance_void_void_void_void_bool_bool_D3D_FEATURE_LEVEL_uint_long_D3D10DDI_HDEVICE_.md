# NDXGI::CDevice::CreateDriverInstance(void *,void *,void *,void *,bool,bool,D3D_FEATURE_LEVEL,uint,long (**)(D3D10DDI_HDEVICE,uint,unsigned __int64,void *,unsigned __int64,void *))

- ea: `0x180048b40`
- end: `0x180048f1e`
- name: `?CreateDriverInstance@CDevice@NDXGI@@UEAAJPEAX000_N1W4D3D_FEATURE_LEVEL@@IPEAP6AJUD3D10DDI_HDEVICE@@I_K040@Z@Z`
- size: `990`
- prototype: `__int64 __usercall@<rax>(NDXGI::CDevice *__hidden this@<rcx>, void *@<rdx>, void *@<r8>, void *@<r9>, void *, bool, bool, enum D3D_FEATURE_LEVEL, unsigned int, int (__high **)(struct D3D10DDI_HDEVICE, unsigned int, unsigned __int64, void *, unsigned __int64, void *))`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180022400`
- `0x1800226c0`
- `0x1800229a0`
- `0x180048b40`
- `0x180048f24`
- `0x1800494b0`
- `0x1800494d4`
- `0x18005ec80`
- `0x1801cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180048e64`
- `ntdll!EtwEventWrite` at `0x180048e92`
- `ntdll!EtwEventWrite` at `0x180048ecd`
- `ntdll!EtwEventWrite` at `0x180048e64`
- `ntdll!EtwEventWrite` at `0x180048e92`
- `ntdll!EtwEventWrite` at `0x180048ecd`

## string_xrefs

- `0x180048dab`: `pfnCreateDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NDXGI::CDevice::CreateDriverInstance(
        NDXGI::CDevice *this,
        void *a2,
        void *a3,
        void *a4,
        void *a5,
        bool a6,
        bool a7,
        enum D3D_FEATURE_LEVEL a8,
        unsigned int a9,
        int (__high **a10)(struct D3D10DDI_HDEVICE, unsigned int, unsigned __int64, void *, unsigned __int64, void *))
{
  int v14; // esi
  int v15; // eax
  __int64 v16; // rdx
  _QWORD *v17; // r9
  char *v18; // r11
  __int64 v19; // rcx
  unsigned __int8 v20; // r10
  int v21; // edx
  __int64 v22; // rcx
  signed int v23; // eax
  bool v24; // r9
  int v25; // edi
  _QWORD v27[2]; // [rsp+30h] [rbp-108h] BYREF
  _QWORD v28[8]; // [rsp+40h] [rbp-F8h] BYREF
  __int64 *v29; // [rsp+80h] [rbp-B8h] BYREF
  NDXGI::CDevice *v30; // [rsp+90h] [rbp-A8h] BYREF
  int v31; // [rsp+98h] [rbp-A0h]
  int v32; // [rsp+9Ch] [rbp-9Ch]
  char *v33; // [rsp+A0h] [rbp-98h]
  void *v34; // [rsp+A8h] [rbp-90h]
  void *v35; // [rsp+B0h] [rbp-88h]
  _QWORD *v36; // [rsp+B8h] [rbp-80h]
  char *v37; // [rsp+C0h] [rbp-78h]
  void *v38; // [rsp+C8h] [rbp-70h]
  void *v39; // [rsp+D0h] [rbp-68h]
  unsigned int v40; // [rsp+D8h] [rbp-60h]
  int v41; // [rsp+DCh] [rbp-5Ch]
  int (__high **v42)(struct D3D10DDI_HDEVICE, unsigned int, unsigned __int64, void *, unsigned __int64, void *); // [rsp+E0h] [rbp-58h]

  *((_BYTE *)this + 898) = a6;
  memset(v28, 0, sizeof(v28));
  LODWORD(v28[0]) = *(_DWORD *)(*((_QWORD *)this + 12) + 96LL);
  LODWORD(v28[1]) = 2;
  if ( a7 )
    LODWORD(v28[1]) = 6;
  if ( dword_1802282A4
    && (qword_180228290 & 0x2000000000000002LL) != 0
    && (qword_180228298 & 0x2000000000000002LL) == qword_180228298 )
  {
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, EventInitiatingKMDCreateDevice, 0, 0);
  }
  v27[0] = EventFinishedKMDCreateDevice;
  v14 = CallAndLogImpl<long (*)(_D3DKMT_CREATEDEVICE *),_D3DKMT_CREATEDEVICE *>(
          *(_QWORD *)(*((_QWORD *)this + 12) + 224LL),
          a2,
          v28);
  CETWEventPair::~CETWEventPair((CETWEventPair *)v27);
  v15 = NDXGI::CUMDAdapter::NTStatusToHResult(v14);
  if ( v15 == -2005530512 )
    v15 = -2005270523;
  ThrowFailure(v15);
  NDXGI::CDevice::SetPrivateData(this, &GUID_KMT_HANDLE, 4u, (char *)&v28[1] + 4);
  *((_DWORD *)this + 26) = HIDWORD(v28[1]);
  v17 = (_QWORD *)((char *)this + 856);
  v18 = (char *)this + 680;
  v19 = *((_QWORD *)this + 9);
  if ( *(_BYTE *)(v19 + 1112) != 1 )
  {
    LOBYTE(v16) = 7;
    if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v19, v16, 4) )
    {
      if ( v20 < 0xAu )
      {
        *v17 = NDXGI::CDevice::PresentCB_PreWDDM2_2;
        *((_QWORD *)this + 109) = NDXGI::CDevice::PresentMultiplaneOverlay1CB_PreWDDM2_2;
      }
    }
    else
    {
      *v17 = NDXGI::CDevice::PresentCB_PreWDDM2;
    }
  }
  v30 = this;
  v31 = HIDWORD(*((_QWORD *)this + 11));
  v32 = *((_DWORD *)this + 22);
  v33 = (char *)this + 112;
  v34 = a2;
  v35 = a3;
  v36 = v17;
  v37 = v18;
  v38 = a4;
  v39 = a5;
  v40 = a9;
  v41 = 0;
  v42 = a10;
  v21 = dword_1802282A4;
  v22 = qword_180228298;
  if ( dword_1802282A4
    && (qword_180228290 & 0x2000000000000002LL) != 0
    && (qword_180228298 & 0x2000000000000002LL) == qword_180228298 )
  {
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, EventInitiatingUMDCreateDevice, 0, 0);
    v21 = dword_1802282A4;
    v22 = qword_180228298;
  }
  v29 = EventFinishedUMDCreateDevice;
  if ( a8 <= D3D_FEATURE_LEVEL_9_3 )
  {
    v27[0] = 0;
  }
  else
  {
    if ( v21 && (qword_180228290 & 0x2000000000000002LL) != 0 && (v22 & 0x2000000000000002LL) == v22 )
      EtwEventWrite(Direct3D11EtwProviderGuid_Context, EventInitiatingUMD10CreateDevice, 0, 0);
    v27[0] = EventFinishedUMD10CreateDevice;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, NDXGI::CDevice **))(*((_QWORD *)this + 12) + 872LL))(
          *(_QWORD *)(*((_QWORD *)this + 12) + 904LL),
          &v30);
  v25 = v23;
  if ( v23 < 0 )
    CModule::RecordJournal((CModule *)&g_Module, v23, "pfnCreateDevice", v24, 1);
  CETWEventPair::~CETWEventPair((CETWEventPair *)v27);
  CETWEventPair::~CETWEventPair((CETWEventPair *)&v29);
  if ( v25 == -2005530512 || *(int *)(*(_QWORD *)(*((_QWORD *)this + 9) + 1232LL) + 1248LL) < 0 )
    v25 = -2005270523;
  ThrowFailure(v25);
  if ( v25 == 142213124 )
    *((_BYTE *)this + 896) = 1;
  *((_QWORD *)this + 84) = a3;
  return 0;
}

```

## disassembly

```asm
0x180048b40  mov     [rsp+arg_0], rcx
0x180048b45  push    rbx
0x180048b46  push    rsi
0x180048b47  push    rdi
0x180048b48  push    r12
0x180048b4a  push    r14
0x180048b4c  push    r15
0x180048b4e  sub     rsp, 108h
0x180048b55  mov     r14, r9
0x180048b58  mov     r12, r8
0x180048b5b  mov     r15, rdx
0x180048b5e  mov     rbx, rcx
0x180048b61  mov     al, [rsp+138h+arg_28]
0x180048b68  mov     [rcx+382h], al
0x180048b6e  mov     [rsp+138h+var_F8], 0
0x180048b77  xor     r8d, r8d
0x180048b7a  mov     [rsp+138h+var_F0], r8
0x180048b7f  mov     [rsp+138h+var_E8], r8
0x180048b84  mov     [rsp+138h+var_E0], r8
0x180048b89  mov     [rsp+138h+var_D8], r8
0x180048b8e  mov     [rsp+138h+var_D0], r8
0x180048b93  mov     [rsp+138h+var_C8], r8
0x180048b98  mov     [rsp+138h+var_C0], r8
0x180048b9d  mov     rax, [rcx+60h]
0x180048ba1  mov     ecx, [rax+60h]
0x180048ba4  mov     dword ptr [rsp+138h+var_F8], ecx
0x180048ba8  or      r8d, 2
0x180048bac  mov     dword ptr [rsp+138h+var_F0], r8d
0x180048bb1  cmp     [rsp+138h+arg_30], 0
0x180048bb9  jnz     loc_180048ED8
0x180048bbf  mov     rdi, 2000000000000002h
0x180048bc9  cmp     cs:dword_1802282A4, 0
0x180048bd0  jz      short loc_180048BDF
0x180048bd2  test    cs:qword_180228290, rdi
0x180048bd9  jnz     loc_180048E39
0x180048bdf  lea     rax, EventFinishedKMDCreateDevice
0x180048be6  mov     [rsp+138h+var_108], rax
0x180048beb  mov     rcx, [rbx+60h]
0x180048bef  lea     r8, [rsp+138h+var_F8]
0x180048bf4  mov     rcx, [rcx+0E0h]
0x180048bfb  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATEDEVICE@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATEDEVICE@@@ZPEBD0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATEDEVICE *),_D3DKMT_CREATEDEVICE *>(long (*)(_D3DKMT_CREATEDEVICE *),char const *,_D3DKMT_CREATEDEVICE *)
0x180048c00  mov     esi, eax
0x180048c02  lea     rcx, [rsp+138h+var_108]; this
0x180048c07  call    ??1CETWEventPair@@QEAA@XZ; CETWEventPair::~CETWEventPair(void)
0x180048c0c  mov     ecx, esi; int
0x180048c0e  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJ@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long)
0x180048c13  mov     esi, 887A0005h
0x180048c18  cmp     eax, 88760870h
0x180048c1d  cmovz   eax, esi
0x180048c20  mov     ecx, eax; int
0x180048c22  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180048c27  lea     r9, [rsp+138h+var_F0+4]; void *
0x180048c2c  mov     r8d, 4; unsigned int
0x180048c32  lea     rdx, GUID_KMT_HANDLE; struct _GUID *
0x180048c39  mov     rcx, rbx; this
0x180048c3c  call    ?SetPrivateData@CDevice@NDXGI@@UEAAJAEBU_GUID@@IPEBX@Z; NDXGI::CDevice::SetPrivateData(_GUID const &,uint,void const *)
0x180048c41  mov     eax, dword ptr [rsp+138h+var_F0+4]
0x180048c45  mov     [rbx+68h], eax
0x180048c48  lea     r9, [rbx+358h]
0x180048c4f  lea     r11, [rbx+2A8h]
0x180048c56  mov     rcx, [rbx+48h]
0x180048c5a  mov     r10b, [rcx+458h]
0x180048c61  cmp     r10b, 1
0x180048c65  jz      short loc_180048C9A
0x180048c67  mov     r8d, 4
0x180048c6d  mov     dl, 7
0x180048c6f  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x180048c74  test    al, al
0x180048c76  jz      loc_180048EE6
0x180048c7c  cmp     r10b, 0Ah
0x180048c80  jnb     short loc_180048C9A
0x180048c82  lea     rax, ?PresentCB_PreWDDM2_2@CDevice@NDXGI@@KAJPEAXPEAUDXGIDDICB_PRESENT_PREWDDM2_2@@@Z; NDXGI::CDevice::PresentCB_PreWDDM2_2(void *,DXGIDDICB_PRESENT_PREWDDM2_2 *)
0x180048c89  mov     [r9], rax
0x180048c8c  lea     rax, ?PresentMultiplaneOverlay1CB_PreWDDM2_2@CDevice@NDXGI@@KAJPEAXPEBUDXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1_PREWDDM2_2@@@Z; NDXGI::CDevice::PresentMultiplaneOverlay1CB_PreWDDM2_2(void *,DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1_PREWDDM2_2 const *)
0x180048c93  mov     [rbx+368h], rax
0x180048c9a  mov     [rsp+138h+var_A8], rbx
0x180048ca2  mov     rax, [rbx+58h]
0x180048ca6  shr     rax, 20h
0x180048caa  mov     [rsp+138h+var_A0], eax
0x180048cb1  mov     eax, [rbx+58h]
0x180048cb4  mov     [rsp+138h+var_9C], eax
0x180048cbb  lea     rax, [rbx+70h]
0x180048cbf  mov     [rsp+138h+var_98], rax
0x180048cc7  mov     [rsp+138h+var_90], r15
0x180048ccf  mov     [rsp+138h+var_88], r12
0x180048cd7  mov     [rsp+138h+var_80], r9
0x180048cdf  mov     [rsp+138h+var_78], r11
0x180048ce7  mov     [rsp+138h+var_70], r14
0x180048cef  mov     rax, [rsp+138h+arg_20]
0x180048cf7  mov     [rsp+138h+var_68], rax
0x180048cff  mov     eax, [rsp+138h+arg_40]
0x180048d06  mov     [rsp+138h+var_60], eax
0x180048d0d  xor     eax, eax
0x180048d0f  mov     [rsp+138h+var_5C], eax
0x180048d16  mov     rax, [rsp+138h+arg_48]
0x180048d1e  mov     [rsp+138h+var_58], rax
0x180048d26  mov     edx, cs:dword_1802282A4
0x180048d2c  mov     rcx, cs:qword_180228298
0x180048d33  test    edx, edx
0x180048d35  jz      short loc_180048D44
0x180048d37  test    cs:qword_180228290, rdi
0x180048d3e  jnz     loc_180048E6F
0x180048d44  lea     rax, EventFinishedUMDCreateDevice
0x180048d4b  mov     [rsp+138h+var_B8], rax
0x180048d53  cmp     [rsp+138h+arg_38], 9300h
0x180048d5e  jle     loc_180048E2B
0x180048d64  test    edx, edx
0x180048d66  jz      short loc_180048D75
0x180048d68  test    cs:qword_180228290, rdi
0x180048d6f  jnz     loc_180048EAA
0x180048d75  lea     rax, EventFinishedUMD10CreateDevice
0x180048d7c  mov     [rsp+138h+var_108], rax
0x180048d81  mov     rcx, [rbx+60h]
0x180048d85  mov     rax, [rcx+368h]
0x180048d8c  lea     rdx, [rsp+138h+var_A8]
0x180048d94  mov     rcx, [rcx+388h]
0x180048d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048da0  mov     edi, eax
0x180048da2  test    eax, eax
0x180048da4  jns     short loc_180048DC1
0x180048da6  mov     [rsp+138h+var_118], 1; bool
0x180048dab  lea     r8, aPfncreatedevic; "pfnCreateDevice"
0x180048db2  mov     edx, eax; unsigned int
0x180048db4  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180048dbb  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180048dc0  nop
0x180048dc1  lea     rcx, [rsp+138h+var_108]; this
0x180048dc6  call    ??1CETWEventPair@@QEAA@XZ; CETWEventPair::~CETWEventPair(void)
0x180048dcb  nop
0x180048dcc  lea     rcx, [rsp+138h+var_B8]; this
0x180048dd4  call    ??1CETWEventPair@@QEAA@XZ; CETWEventPair::~CETWEventPair(void)
0x180048dd9  cmp     edi, 88760870h
0x180048ddf  jz      loc_180048EF5
0x180048de5  mov     rax, [rbx+48h]
0x180048de9  mov     rcx, [rax+4D0h]
0x180048df0  mov     eax, [rcx+4E0h]
0x180048df6  test    eax, eax
0x180048df8  js      loc_180048EF5
0x180048dfe  mov     ecx, edi; int
0x180048e00  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180048e05  cmp     edi, 87A0004h
0x180048e0b  jz      loc_180048EFC
0x180048e11  mov     [rbx+2A0h], r12
0x180048e18  xor     eax, eax
0x180048e1a  add     rsp, 108h
0x180048e21  pop     r15
0x180048e23  pop     r14
0x180048e25  pop     r12
0x180048e27  pop     rdi
0x180048e28  pop     rsi
0x180048e29  pop     rbx
0x180048e2a  retn
0x180048e2b  mov     [rsp+138h+var_108], 0
0x180048e34  jmp     loc_180048D81
0x180048e39  mov     rax, cs:qword_180228298
0x180048e40  and     rax, rdi
0x180048e43  cmp     rax, cs:qword_180228298
0x180048e4a  jnz     loc_180048BDF
0x180048e50  xor     r9d, r9d
0x180048e53  xor     r8d, r8d
0x180048e56  lea     rdx, EventInitiatingKMDCreateDevice
0x180048e5d  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x180048e64  call    cs:__imp_EtwEventWrite
0x180048e6a  jmp     loc_180048BDF
0x180048e6f  mov     rax, rcx
0x180048e72  and     rax, rdi
0x180048e75  cmp     rax, rcx
0x180048e78  jnz     loc_180048D44
0x180048e7e  xor     r9d, r9d
0x180048e81  xor     r8d, r8d
0x180048e84  lea     rdx, EventInitiatingUMDCreateDevice
0x180048e8b  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x180048e92  call    cs:__imp_EtwEventWrite
0x180048e98  mov     edx, cs:dword_1802282A4
0x180048e9e  mov     rcx, cs:qword_180228298
0x180048ea5  jmp     loc_180048D44
0x180048eaa  mov     rax, rcx
0x180048ead  and     rax, rdi
0x180048eb0  cmp     rax, rcx
0x180048eb3  jnz     loc_180048D75
0x180048eb9  xor     r9d, r9d
0x180048ebc  xor     r8d, r8d
0x180048ebf  lea     rdx, EventInitiatingUMD10CreateDevice
0x180048ec6  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x180048ecd  call    cs:__imp_EtwEventWrite
0x180048ed3  jmp     loc_180048D75
0x180048ed8  or      r8d, 4
0x180048edc  mov     dword ptr [rsp+138h+var_F0], r8d
0x180048ee1  jmp     loc_180048BBF
0x180048ee6  lea     rax, ?PresentCB_PreWDDM2@CDevice@NDXGI@@KAJPEAXPEAUDXGIDDICB_PRESENT_PREWDDM2@@@Z; NDXGI::CDevice::PresentCB_PreWDDM2(void *,DXGIDDICB_PRESENT_PREWDDM2 *)
0x180048eed  mov     [r9], rax
0x180048ef0  jmp     loc_180048C9A
0x180048ef5  mov     edi, esi
0x180048ef7  jmp     loc_180048DFE
0x180048efc  mov     byte ptr [rbx+380h], 1
0x180048f03  jmp     loc_180048E11
0x180048f08  mov     eax, 8007000Eh
0x180048f0d  jmp     loc_1800EAB2C
0x180048f12  mov     eax, dword ptr [rsp+138h+arg_28]
0x180048f19  jmp     loc_1800EAB2C
0x1800eab2c  jmp     loc_180048E1A
```
