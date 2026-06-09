# CRDPENCONTCPListener::InitializeInstance(IUnknown *,IRDPENCConnectorCallbacks *,int)

- ea: `0x180100580`
- end: `0x1801007ee`
- name: `?InitializeInstance@CRDPENCONTCPListener@@UEAAJPEAUIUnknown@@PEAUIRDPENCConnectorCallbacks@@H@Z`
- size: `622`
- prototype: `__int64 __fastcall(CRDPENCONTCPListener *__hidden this, struct IUnknown *, struct IRDPENCConnectorCallbacks *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x180046a84`
- `0x1800506ac`
- `0x1800711c8`
- `0x1800721d4`
- `0x180075500`
- `0x1800787d4`
- `0x180100580`
- `0x180107b44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801006d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010075a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801006d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010075a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801006c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180100748`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801006c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180100748`

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
0x180100580  push    rbx
0x180100582  push    rbp
0x180100583  push    rsi
0x180100584  push    rdi
0x180100585  push    r14
0x180100587  push    r15
0x180100589  sub     rsp, 38h
0x18010058d  mov     rsi, rcx
0x180100590  mov     ebx, r9d
0x180100593  add     rcx, 70h ; 'p'; this
0x180100597  mov     rbp, r8
0x18010059a  mov     [rsp+68h+arg_0], rcx
0x18010059f  mov     r14, rdx
0x1801005a2  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1801005a7  or      dword ptr [rsi-14h], 2
0x1801005ab  xor     edi, edi
0x1801005ad  test    ebx, ebx
0x1801005af  jz      loc_1801006B7
0x1801005b5  lea     ecx, [rdi+40h]; Size
0x1801005b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801005bd  test    rax, rax
0x1801005c0  jz      short loc_1801005E7
0x1801005c2  mov     [rax], rdi
0x1801005c5  lea     rcx, ??_7?$CTSSimpleComPtrArray@UIStaticPortMapping@@@@6B@; const CTSSimpleComPtrArray<IStaticPortMapping>::`vftable'
0x1801005cc  mov     [rax+8], rdi
0x1801005d0  mov     [rax+18h], rdi
0x1801005d4  mov     [rax+20h], rdi
0x1801005d8  mov     [rax+28h], edi
0x1801005db  mov     [rax+10h], rcx
0x1801005df  mov     [rax+30h], rdi
0x1801005e3  mov     [rax+38h], rdi
0x1801005e7  mov     [rsi+68h], rax
0x1801005eb  test    rax, rax
0x1801005ee  jnz     short loc_180100645
0x1801005f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801005f7  lea     rax, WPP_GLOBAL_Control
0x1801005fe  cmp     rcx, rax
0x180100601  jz      short loc_18010063B
0x180100603  test    byte ptr [rcx+1Ch], 8
0x180100607  jz      short loc_18010063B
0x180100609  cmp     byte ptr [rcx+19h], 2
0x18010060d  jb      short loc_18010063B
0x18010060f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180100614  mov     rcx, cs:WPP_GLOBAL_Control
0x18010061b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x180100622  mov     edx, 1Bh
0x180100627  mov     dword ptr [rsp+68h+var_48], 8007000Eh
0x18010062f  mov     r9d, eax
0x180100632  mov     rcx, [rcx+10h]
0x180100636  call    WPP_SF_Dd
0x18010063b  mov     edi, 8007000Eh
0x180100640  jmp     loc_1801007C8
0x180100645  mov     rcx, rax; this
0x180100648  call    ?Initialize@CRDPENCNATHelper@@QEAAJXZ; CRDPENCNATHelper::Initialize(void)
0x18010064d  mov     edi, eax
0x18010064f  test    eax, eax
0x180100651  jns     short loc_1801006B7
0x180100653  mov     rcx, cs:WPP_GLOBAL_Control
0x18010065a  lea     rax, WPP_GLOBAL_Control
0x180100661  cmp     rcx, rax
0x180100664  jz      loc_1801007C8
0x18010066a  test    byte ptr [rcx+1Ch], 8
0x18010066e  jz      loc_1801007C8
0x180100674  cmp     byte ptr [rcx+19h], 2
0x180100678  jb      loc_1801007C8
0x18010067e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180100683  lea     rcx, aFailedToInitia_71; "Failed to initialize the NAT manager"
0x18010068a  mov     [rsp+68h+var_40], edi
0x18010068e  mov     [rsp+68h+var_48], rcx
0x180100693  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x18010069a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801006a1  mov     edx, 1Ch
0x1801006a6  mov     r9d, eax
0x1801006a9  mov     rcx, [rcx+10h]
0x1801006ad  call    WPP_SF_DsD
0x1801006b2  jmp     loc_1801007C8
0x1801006b7  xor     r9d, r9d; lpName
0x1801006ba  xor     r8d, r8d; bInitialState
0x1801006bd  xor     edx, edx; bManualReset
0x1801006bf  xor     ecx, ecx; lpEventAttributes
0x1801006c1  call    cs:__imp_CreateEventW
0x1801006c7  mov     [rsi+0A8h], rax
0x1801006ce  test    rax, rax
0x1801006d1  jnz     short loc_18010073E
0x1801006d3  call    cs:__imp_GetLastError
0x1801006d9  mov     edi, eax
0x1801006db  mov     rcx, cs:WPP_GLOBAL_Control
0x1801006e2  lea     rax, WPP_GLOBAL_Control
0x1801006e9  cmp     rcx, rax
0x1801006ec  jz      short loc_180100722
0x1801006ee  test    byte ptr [rcx+1Ch], 8
0x1801006f2  jz      short loc_180100722
0x1801006f4  cmp     byte ptr [rcx+19h], 2
0x1801006f8  jb      short loc_180100722
0x1801006fa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801006ff  mov     edx, 1Dh
0x180100704  mov     rcx, cs:WPP_GLOBAL_Control
0x18010070b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x180100712  mov     r9d, eax
0x180100715  mov     dword ptr [rsp+68h+var_48], edi
0x180100719  mov     rcx, [rcx+10h]
0x18010071d  call    WPP_SF_Dd
0x180100722  test    edi, edi
0x180100724  jle     short loc_18010072F
0x180100726  movzx   edi, di
0x180100729  or      edi, 80070000h
0x18010072f  test    edi, edi
0x180100731  mov     eax, 80004005h
0x180100736  cmovns  edi, eax
0x180100739  jmp     loc_1801007C8
0x18010073e  xor     r9d, r9d; lpName
0x180100741  xor     r8d, r8d; bInitialState
0x180100744  xor     edx, edx; bManualReset
0x180100746  xor     ecx, ecx; lpEventAttributes
0x180100748  call    cs:__imp_CreateEventW
0x18010074e  mov     [rsi+0B0h], rax
0x180100755  test    rax, rax
0x180100758  jnz     short loc_180100790
0x18010075a  call    cs:__imp_GetLastError
0x180100760  mov     edi, eax
0x180100762  mov     rcx, cs:WPP_GLOBAL_Control
0x180100769  lea     rax, WPP_GLOBAL_Control
0x180100770  cmp     rcx, rax
0x180100773  jz      short loc_180100722
0x180100775  test    byte ptr [rcx+1Ch], 8
0x180100779  jz      short loc_180100722
0x18010077b  cmp     byte ptr [rcx+19h], 2
0x18010077f  jb      short loc_180100722
0x180100781  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180100786  mov     edx, 1Eh
0x18010078b  jmp     loc_180100704
0x180100790  lea     rbx, [rsi+58h]
0x180100794  cmp     r14, [rbx]
0x180100797  jz      short loc_1801007AC
0x180100799  mov     rcx, rbx; void *
0x18010079c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801007a1  mov     rcx, rbx
0x1801007a4  mov     [rbx], r14
0x1801007a7  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801007ac  lea     rbx, [rsi+60h]
0x1801007b0  cmp     rbp, [rbx]
0x1801007b3  jz      short loc_1801007C8
0x1801007b5  mov     rcx, rbx; void *
0x1801007b8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801007bd  mov     rcx, rbx
0x1801007c0  mov     [rbx], rbp
0x1801007c3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801007c8  lea     rcx, [rsp+68h+arg_0]; this
0x1801007cd  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1801007d2  test    edi, edi
0x1801007d4  jns     short loc_1801007DF
0x1801007d6  lea     rcx, [rsi-28h]; this
0x1801007da  call    ?Terminate@CRDPENCONTCPListener@@UEAAJXZ; CRDPENCONTCPListener::Terminate(void)
0x1801007df  mov     eax, edi
0x1801007e1  add     rsp, 38h
0x1801007e5  pop     r15
0x1801007e7  pop     r14
0x1801007e9  pop     rdi
0x1801007ea  pop     rsi
0x1801007eb  pop     rbp
0x1801007ec  pop     rbx
0x1801007ed  retn
```
