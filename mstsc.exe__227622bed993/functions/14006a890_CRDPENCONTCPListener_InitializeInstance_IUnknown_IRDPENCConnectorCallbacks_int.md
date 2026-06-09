# CRDPENCONTCPListener::InitializeInstance(IUnknown *,IRDPENCConnectorCallbacks *,int)

- ea: `0x14006a890`
- end: `0x14006aafe`
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
- `0x14003c0f0`
- `0x140059568`
- `0x140059b04`
- `0x14006a890`
- `0x14006be10`
- `0x1400748bc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14006a9d1`
- `KERNEL32!CreateEventW` at `0x14006aa58`
- `KERNEL32!CreateEventW` at `0x14006a9d1`
- `KERNEL32!CreateEventW` at `0x14006aa58`
- `KERNEL32!GetLastError` at `0x14006a9e3`
- `KERNEL32!GetLastError` at `0x14006aa6a`
- `KERNEL32!GetLastError` at `0x14006a9e3`
- `KERNEL32!GetLastError` at `0x14006aa6a`

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
0x14006a890  push    rbx
0x14006a892  push    rbp
0x14006a893  push    rsi
0x14006a894  push    rdi
0x14006a895  push    r14
0x14006a897  push    r15
0x14006a899  sub     rsp, 38h
0x14006a89d  mov     rsi, rcx
0x14006a8a0  mov     ebx, r9d
0x14006a8a3  add     rcx, 70h ; 'p'; this
0x14006a8a7  mov     rbp, r8
0x14006a8aa  mov     [rsp+68h+arg_0], rcx
0x14006a8af  mov     r14, rdx
0x14006a8b2  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14006a8b7  or      dword ptr [rsi-14h], 2
0x14006a8bb  xor     edi, edi
0x14006a8bd  test    ebx, ebx
0x14006a8bf  jz      loc_14006A9C7
0x14006a8c5  lea     ecx, [rdi+40h]; Size
0x14006a8c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006a8cd  test    rax, rax
0x14006a8d0  jz      short loc_14006A8F7
0x14006a8d2  mov     [rax], rdi
0x14006a8d5  lea     rcx, ??_7?$CTSSimpleComPtrArray@UIStaticPortMapping@@@@6B@; const CTSSimpleComPtrArray<IStaticPortMapping>::`vftable'
0x14006a8dc  mov     [rax+8], rdi
0x14006a8e0  mov     [rax+18h], rdi
0x14006a8e4  mov     [rax+20h], rdi
0x14006a8e8  mov     [rax+28h], edi
0x14006a8eb  mov     [rax+10h], rcx
0x14006a8ef  mov     [rax+30h], rdi
0x14006a8f3  mov     [rax+38h], rdi
0x14006a8f7  mov     [rsi+68h], rax
0x14006a8fb  test    rax, rax
0x14006a8fe  jnz     short loc_14006A955
0x14006a900  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a907  lea     rax, WPP_GLOBAL_Control
0x14006a90e  cmp     rcx, rax
0x14006a911  jz      short loc_14006A94B
0x14006a913  test    byte ptr [rcx+1Ch], 8
0x14006a917  jz      short loc_14006A94B
0x14006a919  cmp     byte ptr [rcx+19h], 2
0x14006a91d  jb      short loc_14006A94B
0x14006a91f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006a924  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a92b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006a932  mov     edx, 1Bh
0x14006a937  mov     dword ptr [rsp+68h+var_48], 8007000Eh
0x14006a93f  mov     r9d, eax
0x14006a942  mov     rcx, [rcx+10h]
0x14006a946  call    WPP_SF_Dd
0x14006a94b  mov     edi, 8007000Eh
0x14006a950  jmp     loc_14006AAD8
0x14006a955  mov     rcx, rax; this
0x14006a958  call    ?Initialize@CRDPENCNATHelper@@QEAAJXZ; CRDPENCNATHelper::Initialize(void)
0x14006a95d  mov     edi, eax
0x14006a95f  test    eax, eax
0x14006a961  jns     short loc_14006A9C7
0x14006a963  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a96a  lea     rax, WPP_GLOBAL_Control
0x14006a971  cmp     rcx, rax
0x14006a974  jz      loc_14006AAD8
0x14006a97a  test    byte ptr [rcx+1Ch], 8
0x14006a97e  jz      loc_14006AAD8
0x14006a984  cmp     byte ptr [rcx+19h], 2
0x14006a988  jb      loc_14006AAD8
0x14006a98e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006a993  lea     rcx, aFailedToInitia_33; "Failed to initialize the NAT manager"
0x14006a99a  mov     [rsp+68h+var_40], edi
0x14006a99e  mov     [rsp+68h+var_48], rcx
0x14006a9a3  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006a9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a9b1  mov     edx, 1Ch
0x14006a9b6  mov     r9d, eax
0x14006a9b9  mov     rcx, [rcx+10h]
0x14006a9bd  call    WPP_SF_DsD
0x14006a9c2  jmp     loc_14006AAD8
0x14006a9c7  xor     r9d, r9d; lpName
0x14006a9ca  xor     r8d, r8d; bInitialState
0x14006a9cd  xor     edx, edx; bManualReset
0x14006a9cf  xor     ecx, ecx; lpEventAttributes
0x14006a9d1  call    cs:__imp_CreateEventW
0x14006a9d7  mov     [rsi+0A8h], rax
0x14006a9de  test    rax, rax
0x14006a9e1  jnz     short loc_14006AA4E
0x14006a9e3  call    cs:__imp_GetLastError
0x14006a9e9  mov     edi, eax
0x14006a9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a9f2  lea     rax, WPP_GLOBAL_Control
0x14006a9f9  cmp     rcx, rax
0x14006a9fc  jz      short loc_14006AA32
0x14006a9fe  test    byte ptr [rcx+1Ch], 8
0x14006aa02  jz      short loc_14006AA32
0x14006aa04  cmp     byte ptr [rcx+19h], 2
0x14006aa08  jb      short loc_14006AA32
0x14006aa0a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006aa0f  mov     edx, 1Dh
0x14006aa14  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aa1b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006aa22  mov     r9d, eax
0x14006aa25  mov     dword ptr [rsp+68h+var_48], edi
0x14006aa29  mov     rcx, [rcx+10h]
0x14006aa2d  call    WPP_SF_Dd
0x14006aa32  test    edi, edi
0x14006aa34  jle     short loc_14006AA3F
0x14006aa36  movzx   edi, di
0x14006aa39  or      edi, 80070000h
0x14006aa3f  test    edi, edi
0x14006aa41  mov     eax, 80004005h
0x14006aa46  cmovns  edi, eax
0x14006aa49  jmp     loc_14006AAD8
0x14006aa4e  xor     r9d, r9d; lpName
0x14006aa51  xor     r8d, r8d; bInitialState
0x14006aa54  xor     edx, edx; bManualReset
0x14006aa56  xor     ecx, ecx; lpEventAttributes
0x14006aa58  call    cs:__imp_CreateEventW
0x14006aa5e  mov     [rsi+0B0h], rax
0x14006aa65  test    rax, rax
0x14006aa68  jnz     short loc_14006AAA0
0x14006aa6a  call    cs:__imp_GetLastError
0x14006aa70  mov     edi, eax
0x14006aa72  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aa79  lea     rax, WPP_GLOBAL_Control
0x14006aa80  cmp     rcx, rax
0x14006aa83  jz      short loc_14006AA32
0x14006aa85  test    byte ptr [rcx+1Ch], 8
0x14006aa89  jz      short loc_14006AA32
0x14006aa8b  cmp     byte ptr [rcx+19h], 2
0x14006aa8f  jb      short loc_14006AA32
0x14006aa91  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006aa96  mov     edx, 1Eh
0x14006aa9b  jmp     loc_14006AA14
0x14006aaa0  lea     rbx, [rsi+58h]
0x14006aaa4  cmp     r14, [rbx]
0x14006aaa7  jz      short loc_14006AABC
0x14006aaa9  mov     rcx, rbx
0x14006aaac  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14006aab1  mov     rcx, rbx
0x14006aab4  mov     [rbx], r14
0x14006aab7  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14006aabc  lea     rbx, [rsi+60h]
0x14006aac0  cmp     rbp, [rbx]
0x14006aac3  jz      short loc_14006AAD8
0x14006aac5  mov     rcx, rbx
0x14006aac8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14006aacd  mov     rcx, rbx
0x14006aad0  mov     [rbx], rbp
0x14006aad3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14006aad8  lea     rcx, [rsp+68h+arg_0]; this
0x14006aadd  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14006aae2  test    edi, edi
0x14006aae4  jns     short loc_14006AAEF
0x14006aae6  lea     rcx, [rsi-28h]; this
0x14006aaea  call    ?Terminate@CRDPENCONTCPListener@@UEAAJXZ; CRDPENCONTCPListener::Terminate(void)
0x14006aaef  mov     eax, edi
0x14006aaf1  add     rsp, 38h
0x14006aaf5  pop     r15
0x14006aaf7  pop     r14
0x14006aaf9  pop     rdi
0x14006aafa  pop     rsi
0x14006aafb  pop     rbp
0x14006aafc  pop     rbx
0x14006aafd  retn
```
