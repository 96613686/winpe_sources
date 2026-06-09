# CDXGIFactory::MakeWindowAssociation(HWND__ *,uint)

- ea: `0x18001d9b0`
- end: `0x18001dd80`
- name: `?MakeWindowAssociation@CDXGIFactory@@UEAAJPEAUHWND__@@I@Z`
- size: `976`
- prototype: `__int64 __fastcall(CDXGIFactory *__hidden this, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x18002fe28`

## callees

- `0x18000cb1c`
- `0x18001960c`
- `0x18001a6d4`
- `0x18001b4f8`
- `0x18001d9b0`
- `0x18001dd88`
- `0x18001ddec`
- `0x18001e968`
- `0x180037850`
- `0x180075fa0`
- `0x180076440`
- `0x1800cb010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001daa6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001daa6`
- `ntdll!EtwEventWrite` at `0x18001dc35`
- `ntdll!EtwEventWrite` at `0x18001dc35`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CDXGIFactory::MakeWindowAssociation(CDXGIFactory *this, HWND a2, unsigned int a3)
{
  unsigned __int64 v6; // r15
  _QWORD *v7; // rbx
  _QWORD **v8; // rcx
  _QWORD **v9; // rbx
  HWND *v10; // r15
  _QWORD *v11; // rcx
  _QWORD *v13; // rbx
  HWND *v14; // rax
  HWND v15; // rdx
  HWND **v16; // rcx
  enum DXGI_Message_Id v17; // edx
  unsigned int v18; // ebx
  _QWORD *v19; // rbx
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  _QWORD **v22; // rbx
  _QWORD **v23; // rax
  bool v24; // [rsp+20h] [rbp-A8h]
  _BYTE v25[4]; // [rsp+28h] [rbp-A0h] BYREF
  int v26; // [rsp+2Ch] [rbp-9Ch]
  void *v27[2]; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-88h] BYREF
  HWND v29; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-78h] BYREF
  char v31; // [rsp+58h] [rbp-70h]
  void **v32; // [rsp+60h] [rbp-68h]
  __int64 v33; // [rsp+68h] [rbp-60h]
  _QWORD v34[6]; // [rsp+70h] [rbp-58h] BYREF

  v28 = a3;
  v29 = a2;
  v27[0] = this;
  v25[0] = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v25[0] = 1;
    v34[0] = v27;
    v34[1] = 8;
    v34[2] = &v29;
    v34[3] = 8;
    v34[4] = &v28;
    v34[5] = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGIFactory_MakeWindowAssociation_Start, 3, v34);
  }
  if ( (unsigned int)IsMultiSession0() )
  {
    v17 = DXGI_MSG_IDXGIFactory_MakeWindowAssociation_UnavailableInSession0;
LABEL_30:
    DXGI_SDK_MSG(this, v17);
    v18 = -2005270494;
LABEL_31:
    v26 = v18;
    CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation((CETWEvent_IDXGIFactory_MakeWindowAssociation *)v25);
    return v18;
  }
  if ( (_DWORD)qword_180109A08 )
  {
    v17 = DXGI_MSG_IDXGIFactory_MakeWindowAssociation_ModernApp;
    goto LABEL_30;
  }
  if ( (a3 & 0xFFFFFFF8) != 0 )
  {
    DXGI_SDK_MSG(this, DXGI_MSG_IDXGIFactory_MakeWindowAssociation_InvalidFlags);
    v18 = -2005270527;
    goto LABEL_31;
  }
  v24 = a2 != 0;
  *(_OWORD *)v27 = 0;
  std::list<CDXGISwapChain *>::_Alloc_sentinel_and_proxy(v27);
  v6 = ((unsigned __int64)this + 264) & -(__int64)(this != 0);
  v31 = 0;
  v30 = v6;
  (**(void (__fastcall ***)(unsigned __int64))v6)(v6);
  v31 = 1;
  v7 = (_QWORD *)*((_QWORD *)this + 43);
  while ( 1 )
  {
    v7 = (_QWORD *)*v7;
    if ( v7 == *((_QWORD **)this + 43) )
      break;
    try
    {
      if ( v27[1] == (void *)0xAAAAAAAAAAAAAAALL )
        std::_Xlength_error("list too long");
      v32 = v27;
      v33 = 0;
      v29 = (HWND)v27[0];
      v14 = (HWND *)std::_Allocate<16,std::_Default_allocate_traits>(24);
      v14[2] = (HWND)v7[2];
      ++v27[1];
      v15 = v29;
      v16 = (HWND **)*((_QWORD *)v29 + 1);
      *v14 = v29;
      v14[1] = (HWND)v16;
      v33 = 0;
      *((_QWORD *)v15 + 1) = v14;
      *v16 = v14;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7[2] + 8LL))(v7[2]);
    }
    catch ( std::bad_alloc )
    {
      v23 = (_QWORD **)v27[0];
      v22 = *(_QWORD ***)v27[0];
      while ( v22 != v23 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v22[2] + 16LL))(v22[2]);
        v22 = (_QWORD **)*v22;
        v23 = (_QWORD **)v27[0];
      }
      v26 = -2147024882;
      CThreadLock<0>::ReleaseLock(&v30);
      v21 = v27[0];
      **((_QWORD **)v27[0] + 1) = 0;
      v20 = (_QWORD *)*v21;
      if ( v20 )
      {
        do
        {
          v19 = (_QWORD *)*v20;
          std::_Deallocate<16>(v20, 24);
          v20 = v19;
        }
        while ( v19 );
      }
      std::_Deallocate<16>(v27[0], 24);
      CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation((CETWEvent_IDXGIFactory_MakeWindowAssociation *)v25);
      return 2147942414LL;
    }
  }
  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 8LL))(((unsigned __int64)this + 264) & -(__int64)(this != 0));
  v8 = (_QWORD **)v27[0];
  v9 = *(_QWORD ***)v27[0];
  while ( v9 != v8 )
  {
    v10 = (HWND *)v9[2];
    if ( a2 )
    {
      if ( a2 == v10[42] )
      {
        CDXGISwapChain::MakeWindowAssociation((CDXGISwapChain *)v9[2], a3);
        v24 = 0;
      }
    }
    else
    {
      CDXGISwapChain::MakeWindowAssociation((CDXGISwapChain *)v9[2], a3);
    }
    (*((void (__fastcall **)(HWND *))*v10 + 2))(v10);
    v9 = (_QWORD **)*v9;
    v8 = (_QWORD **)v27[0];
  }
  *v8[1] = 0;
  v11 = *v8;
  if ( v11 )
  {
    do
    {
      v13 = (_QWORD *)*v11;
      std::_Deallocate<16>(v11, 24);
      v11 = v13;
    }
    while ( v13 );
  }
  operator delete(v27[0], 0x18u);
  if ( !a2 && *((_BYTE *)this + 744) )
    *((_DWORD *)this + 102) = a3;
  if ( v24 )
    DXGI_SDK_MSG(
      this,
      DXGI_MSG_IDXGISwapChain_SetFullscreenState_PerMonitorDpiShimApplied|DXGI_MSG_IDXGISwapChain_GetDesc_pDescIsNULL);
  v26 = 0;
  CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation((CETWEvent_IDXGIFactory_MakeWindowAssociation *)v25);
  return 0;
}

```

## disassembly

```asm
0x18001d9b0  mov     [rsp+arg_8], rbx
0x18001d9b5  mov     [rsp+arg_10], rsi
0x18001d9ba  push    r12
0x18001d9bc  push    r13
0x18001d9be  push    r15
0x18001d9c0  sub     rsp, 0B0h
0x18001d9c7  mov     rax, cs:__security_cookie
0x18001d9ce  xor     rax, rsp
0x18001d9d1  mov     [rsp+0C8h+var_28], rax
0x18001d9d9  mov     r13d, r8d
0x18001d9dc  mov     r12, rdx
0x18001d9df  mov     rsi, rcx
0x18001d9e2  mov     [rsp+0C8h+var_88], r8d
0x18001d9e7  mov     [rsp+0C8h+var_80], rdx
0x18001d9ec  mov     [rsp+0C8h+var_98], rcx
0x18001d9f1  mov     [rsp+0C8h+var_A0], 0
0x18001d9f6  cmp     cs:dword_180108134, 0
0x18001d9fd  jnz     loc_18001DBA4
0x18001da03  call    ?IsMultiSession0@@YAHXZ; IsMultiSession0(void)
0x18001da08  test    eax, eax
0x18001da0a  jnz     loc_18001DCAA
0x18001da10  cmp     dword ptr cs:qword_180109A08, eax
0x18001da16  jnz     loc_18001DCD1
0x18001da1c  test    r13d, 0FFFFFFF8h
0x18001da23  jnz     loc_18001DCD8
0x18001da29  test    r12, r12
0x18001da2c  setnz   al
0x18001da2f  mov     [rsp+0C8h+var_A8], al
0x18001da33  xorps   xmm0, xmm0
0x18001da36  movdqu  xmmword ptr [rsp+0C8h+var_98], xmm0
0x18001da3c  lea     rcx, [rsp+0C8h+var_98]
0x18001da41  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCDXGISwapChain@@V?$allocator@PEAVCDXGISwapChain@@@std@@@std@@AEAAXXZ; std::list<CDXGISwapChain *>::_Alloc_sentinel_and_proxy(void)
0x18001da46  nop
0x18001da47  mov     rax, rsi
0x18001da4a  lea     rcx, [rsi+108h]
0x18001da51  neg     rax
0x18001da54  sbb     r15, r15
0x18001da57  and     r15, rcx
0x18001da5a  mov     [rsp+0C8h+var_70], 0
0x18001da5f  mov     [rsp+0C8h+var_78], r15
0x18001da64  mov     rax, [r15]
0x18001da67  mov     rcx, r15
0x18001da6a  mov     rax, [rax]
0x18001da6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da72  mov     [rsp+0C8h+var_70], 1
0x18001da77  mov     rbx, [rsi+158h]
0x18001da7e  mov     rbx, [rbx]
0x18001da81  cmp     rbx, [rsi+158h]
0x18001da88  jz      short loc_18001DAAD
0x18001da8a  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001da94  cmp     [rsp+0C8h+var_98+8], rax
0x18001da99  jnz     loc_18001DC40
0x18001da9f  lea     rcx, aListTooLong; "list too long"
0x18001daa6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001daad  mov     rax, [r15]
0x18001dab0  mov     rcx, r15
0x18001dab3  mov     rax, [rax+8]
0x18001dab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dabc  nop
0x18001dabd  mov     rcx, [rsp+0C8h+var_98]
0x18001dac2  mov     rbx, [rcx]
0x18001dac5  cmp     rbx, rcx
0x18001dac8  jz      short loc_18001DB09
0x18001daca  mov     r15, [rbx+10h]
0x18001dace  test    r12, r12
0x18001dad1  jz      loc_18001DCEC
0x18001dad7  cmp     r12, [r15+150h]
0x18001dade  jnz     short loc_18001DAF0
0x18001dae0  mov     edx, r13d; unsigned int
0x18001dae3  mov     rcx, r15; this
0x18001dae6  call    ?MakeWindowAssociation@CDXGISwapChain@@QEAAXI@Z; CDXGISwapChain::MakeWindowAssociation(uint)
0x18001daeb  mov     [rsp+0C8h+var_A8], 0
0x18001daf0  mov     rax, [r15]
0x18001daf3  mov     rcx, r15
0x18001daf6  mov     rax, [rax+10h]
0x18001dafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daff  mov     rbx, [rbx]
0x18001db02  mov     rcx, [rsp+0C8h+var_98]
0x18001db07  jmp     short loc_18001DAC5
0x18001db09  mov     rax, [rcx+8]
0x18001db0d  mov     qword ptr [rax], 0
0x18001db14  mov     rcx, [rcx]
0x18001db17  test    rcx, rcx
0x18001db1a  jnz     short loc_18001DB8A
0x18001db1c  mov     edx, 18h; unsigned __int64
0x18001db21  mov     rcx, [rsp+0C8h+var_98]; void *
0x18001db26  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001db2b  nop
0x18001db2c  test    r12, r12
0x18001db2f  jnz     short loc_18001DB41
0x18001db31  cmp     [rsi+2E8h], r12b
0x18001db38  jz      short loc_18001DB41
0x18001db3a  mov     [rsi+198h], r13d
0x18001db41  cmp     [rsp+0C8h+var_A8], 0
0x18001db46  jnz     loc_18001DD5A
0x18001db4c  mov     [rsp+0C8h+var_9C], 0
0x18001db54  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001db59  call    ??1CETWEvent_IDXGIFactory_MakeWindowAssociation@@QEAA@XZ; CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation(void)
0x18001db5e  xor     eax, eax
0x18001db60  mov     rcx, [rsp+0C8h+var_28]
0x18001db68  xor     rcx, rsp; StackCookie
0x18001db6b  call    __security_check_cookie
0x18001db70  lea     r11, [rsp+0C8h+var_18]
0x18001db78  mov     rbx, [r11+28h]
0x18001db7c  mov     rsi, [r11+30h]
0x18001db80  mov     rsp, r11
0x18001db83  pop     r15
0x18001db85  pop     r13
0x18001db87  pop     r12
0x18001db89  retn
0x18001db8a  mov     rbx, [rcx]
0x18001db8d  mov     edx, 18h
0x18001db92  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001db97  mov     rcx, rbx
0x18001db9a  test    rbx, rbx
0x18001db9d  jnz     short loc_18001DB8A
0x18001db9f  jmp     loc_18001DB1C
0x18001dba4  mov     rdx, 4000000000000000h
0x18001dbae  test    cs:qword_180108120, rdx
0x18001dbb5  jz      loc_18001DA03
0x18001dbbb  mov     rax, cs:qword_180108128
0x18001dbc2  and     rax, rdx
0x18001dbc5  cmp     rax, cs:qword_180108128
0x18001dbcc  jnz     loc_18001DA03
0x18001dbd2  mov     [rsp+0C8h+var_A0], 1
0x18001dbd7  lea     rax, [rsp+0C8h+var_98]
0x18001dbdc  mov     [rsp+0C8h+var_58], rax
0x18001dbe1  mov     [rsp+0C8h+var_50], 8
0x18001dbea  lea     rax, [rsp+0C8h+var_80]
0x18001dbef  mov     [rsp+0C8h+var_48], rax
0x18001dbf7  mov     [rsp+0C8h+var_40], 8
0x18001dc03  lea     rax, [rsp+0C8h+var_88]
0x18001dc08  mov     [rsp+0C8h+var_38], rax
0x18001dc10  mov     [rsp+0C8h+var_30], 4
0x18001dc1c  lea     r9, [rsp+0C8h+var_58]
0x18001dc21  mov     r8d, 3
0x18001dc27  lea     rdx, IDXGIFactory_MakeWindowAssociation_Start
0x18001dc2e  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x18001dc35  call    cs:__imp_EtwEventWrite
0x18001dc3b  jmp     loc_18001DA03
0x18001dc40  lea     rax, [rsp+0C8h+var_98]
0x18001dc45  mov     [rsp+0C8h+var_68], rax
0x18001dc4a  mov     [rsp+0C8h+var_60], 0
0x18001dc53  mov     rax, [rsp+0C8h+var_98]
0x18001dc58  mov     [rsp+0C8h+var_80], rax
0x18001dc5d  mov     ecx, 18h
0x18001dc62  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001dc67  mov     rcx, [rbx+10h]
0x18001dc6b  mov     [rax+10h], rcx
0x18001dc6f  inc     [rsp+0C8h+var_98+8]
0x18001dc74  mov     rdx, [rsp+0C8h+var_80]
0x18001dc79  mov     rcx, [rdx+8]
0x18001dc7d  mov     [rax], rdx
0x18001dc80  mov     [rax+8], rcx
0x18001dc84  mov     [rsp+0C8h+var_60], 0
0x18001dc8d  mov     [rdx+8], rax
0x18001dc91  mov     [rcx], rax
0x18001dc94  mov     rcx, [rbx+10h]
0x18001dc98  mov     rax, [rcx]
0x18001dc9b  mov     rax, [rax+8]
0x18001dc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca4  nop
0x18001dca5  jmp     loc_18001DA7E
0x18001dcaa  mov     edx, 7Dh ; '}'; enum DXGI_Message_Id
0x18001dcaf  mov     rcx, rsi; struct CDXGIFactory *
0x18001dcb2  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x18001dcb7  mov     ebx, 887A0022h
0x18001dcbc  mov     [rsp+0C8h+var_9C], ebx
0x18001dcc0  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001dcc5  call    ??1CETWEvent_IDXGIFactory_MakeWindowAssociation@@QEAA@XZ; CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation(void)
0x18001dcca  mov     eax, ebx
0x18001dccc  jmp     loc_18001DB60
0x18001dcd1  mov     edx, 0A7h
0x18001dcd6  jmp     short loc_18001DCAF
0x18001dcd8  mov     edx, 25h ; '%'; enum DXGI_Message_Id
0x18001dcdd  mov     rcx, rsi; struct CDXGIFactory *
0x18001dce0  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x18001dce5  mov     ebx, 887A0001h
0x18001dcea  jmp     short loc_18001DCBC
0x18001dcec  mov     edx, r13d; unsigned int
0x18001dcef  mov     rcx, r15; this
0x18001dcf2  call    ?MakeWindowAssociation@CDXGISwapChain@@QEAAXI@Z; CDXGISwapChain::MakeWindowAssociation(uint)
0x18001dcf7  jmp     loc_18001DAF0
0x18001dcfc  mov     rbx, [rcx]
0x18001dcff  mov     edx, 18h
0x18001dd04  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001dd09  mov     rcx, rbx
0x18001dd0c  test    rbx, rbx
0x18001dd0f  jnz     short loc_18001DCFC
0x18001dd11  mov     edx, 18h
0x18001dd16  mov     rcx, [rsp+0C8h+var_98]
0x18001dd1b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001dd20  nop
0x18001dd21  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001dd26  call    ??1CETWEvent_IDXGIFactory_MakeWindowAssociation@@QEAA@XZ; CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation(void)
0x18001dd2b  mov     eax, 8007000Eh
0x18001dd30  jmp     loc_18001DB60
0x18001dd35  lea     rcx, [rsp+0C8h+var_78]
0x18001dd3a  call    ?ReleaseLock@?$CThreadLock@$0A@@@QEAAXXZ; CThreadLock<0>::ReleaseLock(void)
0x18001dd3f  nop
0x18001dd40  mov     rcx, [rsp+0C8h+var_98]
0x18001dd45  mov     rax, [rcx+8]
0x18001dd49  mov     qword ptr [rax], 0
0x18001dd50  mov     rcx, [rcx]
0x18001dd53  test    rcx, rcx
0x18001dd56  jz      short loc_18001DD11
0x18001dd58  jmp     short loc_18001DCFC
0x18001dd5a  mov     edx, 12Ah; enum DXGI_Message_Id
0x18001dd5f  mov     rcx, rsi; struct CDXGIFactory *
0x18001dd62  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x18001dd67  jmp     loc_18001DB4C
0x18001dd6c  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001dd71  call    ??1CETWEvent_IDXGIFactory_MakeWindowAssociation@@QEAA@XZ; CETWEvent_IDXGIFactory_MakeWindowAssociation::~CETWEvent_IDXGIFactory_MakeWindowAssociation(void)
0x18001dd76  mov     eax, 8007000Eh
0x18001dd7b  jmp     loc_18001DB60
```
