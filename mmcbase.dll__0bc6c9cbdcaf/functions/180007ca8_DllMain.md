# DllMain

- ea: `0x180007ca8`
- end: `0x180007fa1`
- name: `DllMain`
- size: `761`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e34`

## callees

- `0x1800023e0`
- `0x180003f10`
- `0x1800041f0`
- `0x1800052dc`
- `0x180007310`
- `0x180007978`
- `0x180007ca8`
- `0x180007fa8`
- `0x180008030`
- `0x18000bd34`
- `0x180012320`
- `0x180012834`
- `0x1800141f0`
- `0x1800143b8`
- `0x18001452c`
- `0x180019a5c`
- `0x18001b522`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x180007f70`
- `ntdll!EtwUnregisterTraceGuids` at `0x180007f70`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007eea`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007eea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  bool v4; // bl
  CHeapFactory *v5; // rcx
  unsigned int v6; // r8d
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  CMMCWatson *v9; // rcx
  __int64 inited; // rax
  char v11; // bl
  struct ATL::_ATL_OBJMAP_ENTRY *v12; // rdx
  struct ATL::_ATL_MODULE *v13; // rcx
  CMMCWatson *v15; // rbx
  CHeapFactory *v16; // rcx
  _QWORD *v17; // rbx
  void **v18; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-18h]
  __int64 v20; // [rsp+30h] [rbp-10h]
  int v21; // [rsp+38h] [rbp-8h]

  if ( fdwReason == 1 )
  {
    qword_18002C478 = 0;
    WPP_MAIN_CB = 0;
    qword_18002C480 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_MMC;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm(hinstDLL, fdwReason, lpvReserved);
    v4 = 1;
    CSimpleLock::Enter((CSimpleLock *)&g_lckLkrInit);
    if ( ++dword_18002F8E8 == 1 )
    {
      v4 = (unsigned int)Locks_Initialize() != 0;
      byte_18002F8EC = v4;
    }
    _InterlockedExchange((volatile __int32 *)&g_lckLkrInit, 0);
    if ( !v4 )
      return 0;
    mmcerror::SC::s_hInst = hinstDLL;
    v7 = CHeapFactory::Alloc(v5, 0x470u, v6);
    v8 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[1] = 0;
      v7[2] = 0;
      v7[3] = 0;
      *((_BYTE *)v7 + 32) = 0;
      v7[70] = -1;
      v7[71] = 0;
      v7[76] = -1;
      memset_0((char *)v7 + 34, 0, 0x208u);
      memset_0(v8 + 77, 0, 0x208u);
    }
    else
    {
      v8 = 0;
    }
    g_pMMCWatson = (CMMCWatson *)v8;
    if ( v8 )
    {
      v18 = &CStr::`vftable';
      v19 = (unsigned __int64)&CStr::s_rgwchEmptyStringBuffer;
      v20 = 0;
      v21 = 0;
      CStr::LoadStringW((CStr *)&v18, hinstDLL, 0x80u);
      if ( !CMMCWatson::Init(v9, (const unsigned __int16 *)(v19 & -(__int64)((_DWORD)v20 != 0)))
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_73b71224c4bd363cc9399bf9c3c5eafe_Traceguids);
      }
      v18 = &CStr::`vftable';
      CStr::Empty((CStr *)&v18);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_73b71224c4bd363cc9399bf9c3c5eafe_Traceguids);
    }
    inited = ScInitAsMFCExtensionModule((__int64)&v18, hinstDLL);
    v11 = mmcerror::SC::operator bool(inited);
    --mmcerror::SC::s_CallDepth;
    mmcerror::SC::Trace_((mmcerror::SC *)&v18);
    if ( v11 )
      return 0;
    qword_18002C438 = (__int64)&ATL::GUID_ATLVer30;
    ATL::_pModule = (struct ATL::CComModule *)&_Module;
    _Module = 248;
    dword_18002C420 = 769;
    if ( (int)ATL::AtlModuleInit(v13, v12, (__int64)hinstDLL) >= 0 )
      dword_18002C460 = 1;
    DisableThreadLibraryCalls(hinstDLL);
  }
  else if ( !fdwReason )
  {
    ATL::AtlModuleTerm((struct ATL::_ATL_MODULE *)hinstDLL);
    CSimpleLock::Enter((CSimpleLock *)&g_lckLkrInit);
    if ( !--dword_18002F8E8 )
      byte_18002F8EC = 0;
    _InterlockedExchange((volatile __int32 *)&g_lckLkrInit, 0);
    v15 = g_pMMCWatson;
    if ( g_pMMCWatson )
    {
      CMMCWatson::~CMMCWatson(g_pMMCWatson);
      CHeapFactory::Free(v16, v15);
      g_pMMCWatson = 0;
    }
    v17 = (_QWORD *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v17 )
      {
        if ( v17[1] )
        {
          EtwUnregisterTraceGuids();
          v17[1] = 0;
        }
        v17 = (_QWORD *)*v17;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180007ca8  mov     [rsp-18h+arg_0], rbx
0x180007cad  mov     [rsp-18h+arg_10], rsi
0x180007cb2  push    rbp
0x180007cb3  push    rdi
0x180007cb4  push    r14
0x180007cb6  mov     rbp, rsp
0x180007cb9  sub     rsp, 40h
0x180007cbd  mov     r14, rcx
0x180007cc0  cmp     edx, 1
0x180007cc3  jnz     loc_180007EFC
0x180007cc9  xor     edi, edi
0x180007ccb  mov     cs:qword_18002C478, rdi
0x180007cd2  mov     cs:WPP_MAIN_CB, rdi
0x180007cd9  mov     cs:qword_18002C480, 1
0x180007ce4  lea     rax, WPP_ThisDir_CTLGUID_MMC
0x180007ceb  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180007cf2  lea     rax, WPP_MAIN_CB
0x180007cf9  mov     cs:WPP_GLOBAL_Control, rax
0x180007d00  call    WppInitUm
0x180007d05  mov     bl, 1
0x180007d07  lea     rcx, ?g_lckLkrInit@@3VCSimpleLock@@A; this
0x180007d0e  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180007d13  mov     eax, cs:dword_18002F8E8
0x180007d19  inc     eax
0x180007d1b  mov     cs:dword_18002F8E8, eax
0x180007d21  cmp     eax, 1
0x180007d24  jnz     short loc_180007D36
0x180007d26  call    Locks_Initialize
0x180007d2b  test    eax, eax
0x180007d2d  setnz   bl
0x180007d30  mov     cs:byte_18002F8EC, bl
0x180007d36  mov     eax, edi
0x180007d38  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180007d3e  test    bl, bl
0x180007d40  jz      loc_180007EF5
0x180007d46  mov     cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * mmcerror::SC::s_hInst
0x180007d4d  mov     edx, 470h; unsigned __int64
0x180007d52  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x180007d57  mov     rbx, rax
0x180007d5a  mov     [rbp+arg_18], rax
0x180007d5e  test    rax, rax
0x180007d61  jz      short loc_180007DB5
0x180007d63  mov     [rax], rdi
0x180007d66  mov     [rax+8], rdi
0x180007d6a  mov     [rax+10h], rdi
0x180007d6e  mov     [rax+18h], rdi
0x180007d72  mov     [rax+20h], dil
0x180007d76  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007d7a  mov     [rbx+230h], rax
0x180007d81  mov     [rbx+238h], rdi
0x180007d88  mov     [rbx+260h], rax
0x180007d8f  lea     rcx, [rbx+22h]; void *
0x180007d93  mov     esi, 208h
0x180007d98  mov     r8d, esi; Size
0x180007d9b  xor     edx, edx; Val
0x180007d9d  call    memset_0
0x180007da2  lea     rcx, [rbx+268h]; void *
0x180007da9  mov     r8d, esi; Size
0x180007dac  xor     edx, edx; Val
0x180007dae  call    memset_0
0x180007db3  jmp     short loc_180007DB8
0x180007db5  mov     rbx, rdi
0x180007db8  mov     cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA, rbx; CMMCWatson * g_pMMCWatson
0x180007dbf  test    rbx, rbx
0x180007dc2  jz      loc_180007E4A
0x180007dc8  lea     rbx, ??_7CStr@@6B@; const CStr::`vftable'
0x180007dcf  mov     [rbp+var_20], rbx
0x180007dd3  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180007dda  mov     [rbp+var_18], rax
0x180007dde  mov     [rbp+var_10], rdi
0x180007de2  mov     [rbp+var_8], edi
0x180007de5  mov     r8d, 80h; uID
0x180007deb  mov     rdx, r14; hInstance
0x180007dee  lea     rcx, [rbp+var_20]; this
0x180007df2  call    ?LoadStringW@CStr@@QEAAJPEAUHINSTANCE__@@I@Z; CStr::LoadStringW(HINSTANCE__ *,uint)
0x180007df7  mov     eax, dword ptr [rbp+var_10]
0x180007dfa  neg     eax
0x180007dfc  sbb     rdx, rdx
0x180007dff  and     rdx, [rbp+var_18]; unsigned __int16 *
0x180007e03  call    ?Init@CMMCWatson@@QEAA_NPEBG@Z; CMMCWatson::Init(ushort const *)
0x180007e08  test    al, al
0x180007e0a  jnz     short loc_180007E3B
0x180007e0c  lea     rsi, WPP_GLOBAL_Control
0x180007e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e1a  cmp     rcx, rsi
0x180007e1d  jz      short loc_180007E3B
0x180007e1f  cmp     byte ptr [rcx+19h], 2
0x180007e23  jb      short loc_180007E3B
0x180007e25  mov     edx, 0Ah
0x180007e2a  lea     r8, WPP_73b71224c4bd363cc9399bf9c3c5eafe_Traceguids
0x180007e31  mov     rcx, [rcx+10h]
0x180007e35  call    WPP_SF_
0x180007e3a  nop
0x180007e3b  mov     [rbp+var_20], rbx
0x180007e3f  lea     rcx, [rbp+var_20]; this
0x180007e43  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180007e48  jmp     short loc_180007E78
0x180007e4a  lea     rsi, WPP_GLOBAL_Control
0x180007e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e58  cmp     rcx, rsi
0x180007e5b  jz      short loc_180007E78
0x180007e5d  cmp     byte ptr [rcx+19h], 2
0x180007e61  jb      short loc_180007E78
0x180007e63  mov     edx, 0Bh
0x180007e68  lea     r8, WPP_73b71224c4bd363cc9399bf9c3c5eafe_Traceguids
0x180007e6f  mov     rcx, [rcx+10h]
0x180007e73  call    WPP_SF_
0x180007e78  mov     rdx, r14
0x180007e7b  lea     rcx, [rbp+var_20]
0x180007e7f  call    ScInitAsMFCExtensionModule
0x180007e84  mov     rcx, rax
0x180007e87  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180007e8c  mov     bl, al
0x180007e8e  dec     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180007e94  lea     rcx, [rbp+var_20]; this
0x180007e98  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x180007e9d  test    bl, bl
0x180007e9f  jnz     short loc_180007EF5
0x180007ea1  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x180007ea8  mov     cs:qword_18002C438, rax
0x180007eaf  lea     rax, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x180007eb6  mov     cs:?_pModule@ATL@@3PEAVCComModule@1@EA, rax; ATL::CComModule * ATL::_pModule
0x180007ebd  mov     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x180007ec7  mov     cs:dword_18002C420, 301h
0x180007ed1  mov     r8, r14; HINSTANCE
0x180007ed4  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x180007ed9  test    eax, eax
0x180007edb  js      short loc_180007EE7
0x180007edd  mov     cs:dword_18002C460, 1
0x180007ee7  mov     rcx, r14; hLibModule
0x180007eea  call    cs:__imp_DisableThreadLibraryCalls
0x180007ef0  jmp     loc_180007F89
0x180007ef5  xor     eax, eax
0x180007ef7  jmp     loc_180007F8E
0x180007efc  xor     edi, edi
0x180007efe  test    edx, edx
0x180007f00  jnz     loc_180007F89
0x180007f06  call    ?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z; ATL::AtlModuleTerm(ATL::_ATL_MODULE *)
0x180007f0b  lea     rcx, ?g_lckLkrInit@@3VCSimpleLock@@A; this
0x180007f12  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180007f17  sub     cs:dword_18002F8E8, 1
0x180007f1e  jnz     short loc_180007F27
0x180007f20  mov     cs:byte_18002F8EC, dil
0x180007f27  mov     eax, edi
0x180007f29  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180007f2f  mov     rbx, cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA; CMMCWatson * g_pMMCWatson
0x180007f36  test    rbx, rbx
0x180007f39  jz      short loc_180007F52
0x180007f3b  mov     rcx, rbx; this
0x180007f3e  call    ??1CMMCWatson@@QEAA@XZ; CMMCWatson::~CMMCWatson(void)
0x180007f43  mov     rdx, rbx; void *
0x180007f46  call    ?Free@CHeapFactory@@QEAAHPEAX@Z; CHeapFactory::Free(void *)
0x180007f4b  mov     cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA, rdi; CMMCWatson * g_pMMCWatson
0x180007f52  lea     rsi, WPP_GLOBAL_Control
0x180007f59  mov     rbx, cs:WPP_GLOBAL_Control
0x180007f60  cmp     rbx, rsi
0x180007f63  jz      short loc_180007F89
0x180007f65  jmp     short loc_180007F7D
0x180007f67  mov     rcx, [rbx+8]
0x180007f6b  test    rcx, rcx
0x180007f6e  jz      short loc_180007F7A
0x180007f70  call    cs:__imp_EtwUnregisterTraceGuids
0x180007f76  mov     [rbx+8], rdi
0x180007f7a  mov     rbx, [rbx]
0x180007f7d  test    rbx, rbx
0x180007f80  jnz     short loc_180007F67
0x180007f82  mov     cs:WPP_GLOBAL_Control, rsi
0x180007f89  mov     eax, 1
0x180007f8e  mov     rbx, [rsp+40h+arg_0]
0x180007f93  mov     rsi, [rsp+40h+arg_10]
0x180007f98  add     rsp, 40h
0x180007f9c  pop     r14
0x180007f9e  pop     rdi
0x180007f9f  pop     rbp
0x180007fa0  retn
```
