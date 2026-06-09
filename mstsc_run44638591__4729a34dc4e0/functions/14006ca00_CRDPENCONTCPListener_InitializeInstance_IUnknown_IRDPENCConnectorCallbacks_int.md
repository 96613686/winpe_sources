# CRDPENCONTCPListener::InitializeInstance(IUnknown *,IRDPENCConnectorCallbacks *,int)

- ea: `0x14006ca00`
- end: `0x14006cc6e`
- name: `?InitializeInstance@CRDPENCONTCPListener@@UEAAJPEAUIUnknown@@PEAUIRDPENCConnectorCallbacks@@H@Z`
- size: `622`
- prototype: `__int64 __fastcall(CRDPENCONTCPListener *__hidden this, struct IUnknown *, struct IRDPENCConnectorCallbacks *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x14003e0b4`
- `0x14005b6d8`
- `0x14005bc74`
- `0x14006ca00`
- `0x14006df80`
- `0x140076a2c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14006cb41`
- `KERNEL32!CreateEventW` at `0x14006cbc8`
- `KERNEL32!CreateEventW` at `0x14006cb41`
- `KERNEL32!CreateEventW` at `0x14006cbc8`
- `KERNEL32!GetLastError` at `0x14006cb53`
- `KERNEL32!GetLastError` at `0x14006cbda`
- `KERNEL32!GetLastError` at `0x14006cb53`
- `KERNEL32!GetLastError` at `0x14006cbda`

## pseudocode

```c
__int64 __fastcall CRDPENCONTCPListener::InitializeInstance(
        CRDPENCONTCPListener *this,
        struct IUnknown *a2,
        struct IRDPENCConnectorCallbacks *a3,
        int a4)
{
  signed int LastError; // edi
  _QWORD *v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v11; // eax
  HANDLE EventW; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  HANDLE v15; // rax
  char *v17; // [rsp+70h] [rbp+8h] BYREF

  v17 = (char *)this + 112;
  CTSCriticalSection::Lock((CRDPENCONTCPListener *)((char *)this + 112));
  *((_DWORD *)this - 5) |= 2u;
  LastError = 0;
  if ( a4 )
  {
    v9 = operator new(0x40u);
    if ( v9 )
    {
      *v9 = 0;
      v9[1] = 0;
      v9[3] = 0;
      v9[4] = 0;
      *((_DWORD *)v9 + 10) = 0;
      v9[2] = &CTSSimpleComPtrArray<IStaticPortMapping>::`vftable';
      v9[6] = 0;
      v9[7] = 0;
    }
    *((_QWORD *)this + 13) = v9;
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
          CurrentThreadActivityIdPrefix,
          -2147024882);
      }
      LastError = -2147024882;
      goto LABEL_35;
    }
    LastError = CRDPENCNATHelper::Initialize((CRDPENCNATHelper *)v9);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
          v11,
          (__int64)"Failed to initialize the NAT manager",
          LastError);
      }
      goto LABEL_35;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 21) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 29;
LABEL_20:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
      v13,
      LastError);
LABEL_21:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_35;
  }
  v15 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 22) = v15;
  if ( !v15 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 30;
    goto LABEL_20;
  }
  if ( a2 != *((struct IUnknown **)this + 11) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 88);
    *((_QWORD *)this + 11) = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 88);
  }
  if ( a3 != *((struct IRDPENCConnectorCallbacks **)this + 12) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 96);
    *((_QWORD *)this + 12) = a3;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 96);
  }
LABEL_35:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v17);
  if ( LastError < 0 )
    CRDPENCONTCPListener::Terminate((CRDPENCONTCPListener *)((char *)this - 40));
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14006ca00  push    rbx
0x14006ca02  push    rbp
0x14006ca03  push    rsi
0x14006ca04  push    rdi
0x14006ca05  push    r14
0x14006ca07  push    r15
0x14006ca09  sub     rsp, 38h
0x14006ca0d  mov     rsi, rcx
0x14006ca10  mov     ebx, r9d
0x14006ca13  add     rcx, 70h ; 'p'; this
0x14006ca17  mov     rbp, r8
0x14006ca1a  mov     [rsp+68h+arg_0], rcx
0x14006ca1f  mov     r14, rdx
0x14006ca22  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14006ca27  or      dword ptr [rsi-14h], 2
0x14006ca2b  xor     edi, edi
0x14006ca2d  test    ebx, ebx
0x14006ca2f  jz      loc_14006CB37
0x14006ca35  lea     ecx, [rdi+40h]; Size
0x14006ca38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006ca3d  test    rax, rax
0x14006ca40  jz      short loc_14006CA67
0x14006ca42  mov     [rax], rdi
0x14006ca45  lea     rcx, ??_7?$CTSSimpleComPtrArray@UIStaticPortMapping@@@@6B@; const CTSSimpleComPtrArray<IStaticPortMapping>::`vftable'
0x14006ca4c  mov     [rax+8], rdi
0x14006ca50  mov     [rax+18h], rdi
0x14006ca54  mov     [rax+20h], rdi
0x14006ca58  mov     [rax+28h], edi
0x14006ca5b  mov     [rax+10h], rcx
0x14006ca5f  mov     [rax+30h], rdi
0x14006ca63  mov     [rax+38h], rdi
0x14006ca67  mov     [rsi+68h], rax
0x14006ca6b  test    rax, rax
0x14006ca6e  jnz     short loc_14006CAC5
0x14006ca70  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ca77  lea     rax, WPP_GLOBAL_Control
0x14006ca7e  cmp     rcx, rax
0x14006ca81  jz      short loc_14006CABB
0x14006ca83  test    byte ptr [rcx+1Ch], 8
0x14006ca87  jz      short loc_14006CABB
0x14006ca89  cmp     byte ptr [rcx+19h], 2
0x14006ca8d  jb      short loc_14006CABB
0x14006ca8f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006ca94  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ca9b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006caa2  mov     edx, 1Bh
0x14006caa7  mov     dword ptr [rsp+68h+var_48], 8007000Eh
0x14006caaf  mov     r9d, eax
0x14006cab2  mov     rcx, [rcx+10h]
0x14006cab6  call    WPP_SF_Dd
0x14006cabb  mov     edi, 8007000Eh
0x14006cac0  jmp     loc_14006CC48
0x14006cac5  mov     rcx, rax; this
0x14006cac8  call    ?Initialize@CRDPENCNATHelper@@QEAAJXZ; CRDPENCNATHelper::Initialize(void)
0x14006cacd  mov     edi, eax
0x14006cacf  test    eax, eax
0x14006cad1  jns     short loc_14006CB37
0x14006cad3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cada  lea     rax, WPP_GLOBAL_Control
0x14006cae1  cmp     rcx, rax
0x14006cae4  jz      loc_14006CC48
0x14006caea  test    byte ptr [rcx+1Ch], 8
0x14006caee  jz      loc_14006CC48
0x14006caf4  cmp     byte ptr [rcx+19h], 2
0x14006caf8  jb      loc_14006CC48
0x14006cafe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006cb03  lea     rcx, aFailedToInitia_33; "Failed to initialize the NAT manager"
0x14006cb0a  mov     [rsp+68h+var_40], edi
0x14006cb0e  mov     [rsp+68h+var_48], rcx
0x14006cb13  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006cb1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb21  mov     edx, 1Ch
0x14006cb26  mov     r9d, eax
0x14006cb29  mov     rcx, [rcx+10h]
0x14006cb2d  call    WPP_SF_DsD
0x14006cb32  jmp     loc_14006CC48
0x14006cb37  xor     r9d, r9d; lpName
0x14006cb3a  xor     r8d, r8d; bInitialState
0x14006cb3d  xor     edx, edx; bManualReset
0x14006cb3f  xor     ecx, ecx; lpEventAttributes
0x14006cb41  call    cs:__imp_CreateEventW
0x14006cb47  mov     [rsi+0A8h], rax
0x14006cb4e  test    rax, rax
0x14006cb51  jnz     short loc_14006CBBE
0x14006cb53  call    cs:__imp_GetLastError
0x14006cb59  mov     edi, eax
0x14006cb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb62  lea     rax, WPP_GLOBAL_Control
0x14006cb69  cmp     rcx, rax
0x14006cb6c  jz      short loc_14006CBA2
0x14006cb6e  test    byte ptr [rcx+1Ch], 8
0x14006cb72  jz      short loc_14006CBA2
0x14006cb74  cmp     byte ptr [rcx+19h], 2
0x14006cb78  jb      short loc_14006CBA2
0x14006cb7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006cb7f  mov     edx, 1Dh
0x14006cb84  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb8b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006cb92  mov     r9d, eax
0x14006cb95  mov     dword ptr [rsp+68h+var_48], edi
0x14006cb99  mov     rcx, [rcx+10h]
0x14006cb9d  call    WPP_SF_Dd
0x14006cba2  test    edi, edi
0x14006cba4  jle     short loc_14006CBAF
0x14006cba6  movzx   edi, di
0x14006cba9  or      edi, 80070000h
0x14006cbaf  test    edi, edi
0x14006cbb1  mov     eax, 80004005h
0x14006cbb6  cmovns  edi, eax
0x14006cbb9  jmp     loc_14006CC48
0x14006cbbe  xor     r9d, r9d; lpName
0x14006cbc1  xor     r8d, r8d; bInitialState
0x14006cbc4  xor     edx, edx; bManualReset
0x14006cbc6  xor     ecx, ecx; lpEventAttributes
0x14006cbc8  call    cs:__imp_CreateEventW
0x14006cbce  mov     [rsi+0B0h], rax
0x14006cbd5  test    rax, rax
0x14006cbd8  jnz     short loc_14006CC10
0x14006cbda  call    cs:__imp_GetLastError
0x14006cbe0  mov     edi, eax
0x14006cbe2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cbe9  lea     rax, WPP_GLOBAL_Control
0x14006cbf0  cmp     rcx, rax
0x14006cbf3  jz      short loc_14006CBA2
0x14006cbf5  test    byte ptr [rcx+1Ch], 8
0x14006cbf9  jz      short loc_14006CBA2
0x14006cbfb  cmp     byte ptr [rcx+19h], 2
0x14006cbff  jb      short loc_14006CBA2
0x14006cc01  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006cc06  mov     edx, 1Eh
0x14006cc0b  jmp     loc_14006CB84
0x14006cc10  lea     rbx, [rsi+58h]
0x14006cc14  cmp     r14, [rbx]
0x14006cc17  jz      short loc_14006CC2C
0x14006cc19  mov     rcx, rbx
0x14006cc1c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14006cc21  mov     rcx, rbx
0x14006cc24  mov     [rbx], r14
0x14006cc27  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14006cc2c  lea     rbx, [rsi+60h]
0x14006cc30  cmp     rbp, [rbx]
0x14006cc33  jz      short loc_14006CC48
0x14006cc35  mov     rcx, rbx
0x14006cc38  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14006cc3d  mov     rcx, rbx
0x14006cc40  mov     [rbx], rbp
0x14006cc43  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14006cc48  lea     rcx, [rsp+68h+arg_0]; this
0x14006cc4d  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14006cc52  test    edi, edi
0x14006cc54  jns     short loc_14006CC5F
0x14006cc56  lea     rcx, [rsi-28h]; this
0x14006cc5a  call    ?Terminate@CRDPENCONTCPListener@@UEAAJXZ; CRDPENCONTCPListener::Terminate(void)
0x14006cc5f  mov     eax, edi
0x14006cc61  add     rsp, 38h
0x14006cc65  pop     r15
0x14006cc67  pop     r14
0x14006cc69  pop     rdi
0x14006cc6a  pop     rsi
0x14006cc6b  pop     rbp
0x14006cc6c  pop     rbx
0x14006cc6d  retn
```
