# CDXGISwapChain::GetDesc(DXGI_SWAP_CHAIN_DESC *)

- ea: `0x180042f60`
- end: `0x1800431e0`
- name: `?GetDesc@CDXGISwapChain@@UEAAJPEAUDXGI_SWAP_CHAIN_DESC@@@Z`
- size: `640`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, struct DXGI_SWAP_CHAIN_DESC *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800989e0`

## callees

- `0x18000c6b0`
- `0x18000ce70`
- `0x1800202ac`
- `0x180042f60`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800430bc`
- `ntdll!EtwEventWrite` at `0x180043158`
- `ntdll!EtwEventWrite` at `0x1800431b9`
- `ntdll!EtwEventWrite` at `0x1800430bc`
- `ntdll!EtwEventWrite` at `0x180043158`
- `ntdll!EtwEventWrite` at `0x1800431b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDXGISwapChain::GetDesc(CDXGISwapChain *this, struct DXGI_SWAP_CHAIN_DESC *a2)
{
  unsigned __int64 v4; // rsi
  HWND v5; // rax
  __int64 v6; // rcx
  CModule *v8; // rcx
  bool v9; // r9
  char v10; // [rsp+20h] [rbp-59h]
  int v11; // [rsp+24h] [rbp-55h] BYREF
  int *v12; // [rsp+28h] [rbp-51h] BYREF
  __int64 v13; // [rsp+30h] [rbp-49h]
  _QWORD v14[2]; // [rsp+38h] [rbp-41h] BYREF
  struct DXGI_SWAP_CHAIN_DESC *v15; // [rsp+48h] [rbp-31h]
  __int64 v16; // [rsp+50h] [rbp-29h]
  char v17; // [rsp+60h] [rbp-19h] BYREF

  v12 = (int *)this;
  v10 = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v10 = 1;
    v14[0] = &v12;
    v14[1] = 8;
    v16 = 72;
    if ( a2 )
      v15 = a2;
    else
      v15 = (struct DXGI_SWAP_CHAIN_DESC *)&v17;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetDesc_Start, 2, v14);
  }
  v4 = ((unsigned __int64)this + 136) & -(__int64)(this != 0);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 8) + 24LL))(*(_QWORD *)(v4 + 8));
  if ( a2 )
  {
    a2->BufferDesc.Width = *((_DWORD *)this + 94);
    a2->BufferDesc.Height = *((_DWORD *)this + 95);
    a2->BufferDesc.Format = *((_DWORD *)this + 98);
    a2->BufferDesc.RefreshRate = (DXGI_RATIONAL)*((_QWORD *)this + 48);
    a2->BufferDesc.ScanlineOrdering = *((_DWORD *)this + 99);
    a2->BufferDesc.Scaling = *((_DWORD *)this + 100);
    a2->SampleDesc = (DXGI_SAMPLE_DESC)*((_QWORD *)this + 51);
    a2->BufferUsage = *((_DWORD *)this + 104);
    a2->BufferCount = *((_DWORD *)this + 105);
    if ( *((_DWORD *)this + 82) == 2 )
      v5 = (HWND)*((_QWORD *)this + 42);
    else
      v5 = 0;
    a2->OutputWindow = v5;
    if ( *((_DWORD *)this + 551) )
      CDXGISwapChain::ScenarioEnterOrLeaveFullscreen(this, 0, 0);
    a2->Windowed = *((_DWORD *)this + 111);
    a2->SwapEffect = *((_DWORD *)this + 107);
    a2->Flags = *((_DWORD *)this + 109);
    v11 = 0;
    if ( v4 )
    {
      v6 = *(_QWORD *)((((unsigned __int64)this + 136) & -(__int64)(this != 0)) + 8);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
    }
    if ( v10 )
    {
      v12 = &v11;
      v13 = 4;
      EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetDesc_Stop, 1, &v12);
    }
    return 0;
  }
  else
  {
    DXGI_SDK_MSG_SWAPCHAIN(*((struct IDXGIDebugProducer **)this + 38), DXGI_MSG_IDXGISwapChain_GetDesc_pDescIsNULL);
    CModule::RecordJournalImpl(v8, 0x80070057, "Non-zero return value", v9);
    v11 = -2147024809;
    if ( v4 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 8) + 32LL))(*(_QWORD *)(v4 + 8));
    if ( v10 )
    {
      v12 = &v11;
      v13 = 4;
      EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetDesc_Stop, 1, &v12);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180042f60  mov     [rsp-8+arg_10], rbx
0x180042f65  push    rbp
0x180042f66  push    rsi
0x180042f67  push    rdi
0x180042f68  lea     rbp, [rsp-47h]
0x180042f6d  sub     rsp, 0C0h
0x180042f74  mov     rax, cs:__security_cookie
0x180042f7b  xor     rax, rsp
0x180042f7e  mov     [rbp+57h+var_20], rax
0x180042f82  mov     rdi, rdx
0x180042f85  mov     rbx, rcx
0x180042f88  mov     [rbp+57h+var_A8], rcx
0x180042f8c  mov     [rbp+57h+var_B0], 0
0x180042f90  cmp     cs:dword_180108134, 0
0x180042f97  jz      short loc_180042FB0
0x180042f99  mov     rdx, 4000000000000000h
0x180042fa3  test    cs:qword_180108120, rdx
0x180042faa  jnz     loc_180043165
0x180042fb0  mov     rax, rbx
0x180042fb3  lea     rcx, [rbx+88h]
0x180042fba  neg     rax
0x180042fbd  sbb     rsi, rsi
0x180042fc0  and     rsi, rcx
0x180042fc3  mov     rcx, [rsi+8]
0x180042fc7  mov     rax, [rcx]
0x180042fca  mov     rax, [rax+18h]
0x180042fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fd3  test    rdi, rdi
0x180042fd6  jz      loc_1800430EA
0x180042fdc  mov     eax, [rbx+178h]
0x180042fe2  mov     [rdi], eax
0x180042fe4  mov     eax, [rbx+17Ch]
0x180042fea  mov     [rdi+4], eax
0x180042fed  mov     eax, [rbx+188h]
0x180042ff3  mov     [rdi+10h], eax
0x180042ff6  mov     rax, [rbx+180h]
0x180042ffd  mov     [rdi+8], rax
0x180043001  mov     eax, [rbx+18Ch]
0x180043007  mov     [rdi+14h], eax
0x18004300a  mov     eax, [rbx+190h]
0x180043010  mov     [rdi+18h], eax
0x180043013  mov     rax, [rbx+198h]
0x18004301a  mov     [rdi+1Ch], rax
0x18004301e  mov     eax, [rbx+1A0h]
0x180043024  mov     [rdi+24h], eax
0x180043027  mov     eax, [rbx+1A4h]
0x18004302d  mov     [rdi+28h], eax
0x180043030  cmp     dword ptr [rbx+148h], 2
0x180043037  jnz     loc_1800430E3
0x18004303d  mov     rax, [rbx+150h]
0x180043044  mov     [rdi+30h], rax
0x180043048  mov     eax, [rbx+89Ch]
0x18004304e  test    eax, eax
0x180043050  jnz     loc_1800431CE
0x180043056  mov     eax, [rbx+1BCh]
0x18004305c  mov     [rdi+38h], eax
0x18004305f  mov     eax, [rbx+1ACh]
0x180043065  mov     [rdi+3Ch], eax
0x180043068  mov     eax, [rbx+1B4h]
0x18004306e  mov     [rdi+40h], eax
0x180043071  mov     [rbp+57h+var_AC], 0
0x180043078  test    rsi, rsi
0x18004307b  jz      short loc_18004308E
0x18004307d  mov     rcx, [rsi+8]
0x180043081  mov     rax, [rcx]
0x180043084  mov     rax, [rax+20h]
0x180043088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004308d  nop
0x18004308e  cmp     [rbp+57h+var_B0], 0
0x180043092  jz      short loc_1800430C2
0x180043094  lea     rax, [rbp+57h+var_AC]
0x180043098  mov     [rbp+57h+var_A8], rax
0x18004309c  mov     [rbp+57h+var_A0], 4
0x1800430a4  lea     r9, [rbp+57h+var_A8]
0x1800430a8  mov     r8d, 1
0x1800430ae  lea     rdx, IDXGISwapChain_GetDesc_Stop
0x1800430b5  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800430bc  call    cs:__imp_EtwEventWrite
0x1800430c2  xor     eax, eax
0x1800430c4  mov     rcx, [rbp+57h+var_20]
0x1800430c8  xor     rcx, rsp; StackCookie
0x1800430cb  call    __security_check_cookie
0x1800430d0  mov     rbx, [rsp+0D0h+arg_10]
0x1800430d8  add     rsp, 0C0h
0x1800430df  pop     rdi
0x1800430e0  pop     rsi
0x1800430e1  pop     rbp
0x1800430e2  retn
0x1800430e3  xor     eax, eax
0x1800430e5  jmp     loc_180043044
0x1800430ea  mov     edx, 8; enum DXGI_Message_Id
0x1800430ef  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x1800430f6  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x1800430fb  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x180043102  mov     edx, 80070057h; unsigned int
0x180043107  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18004310c  mov     ebx, 80070057h
0x180043111  mov     [rbp+57h+var_AC], ebx
0x180043114  test    rsi, rsi
0x180043117  jz      short loc_18004312A
0x180043119  mov     rcx, [rsi+8]
0x18004311d  mov     rax, [rcx]
0x180043120  mov     rax, [rax+20h]
0x180043124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043129  nop
0x18004312a  cmp     [rbp+57h+var_B0], 0
0x18004312e  jz      short loc_18004315E
0x180043130  lea     rcx, [rbp+57h+var_AC]
0x180043134  mov     [rbp+57h+var_A8], rcx
0x180043138  mov     [rbp+57h+var_A0], 4
0x180043140  lea     r9, [rbp+57h+var_A8]
0x180043144  mov     r8d, 1
0x18004314a  lea     rdx, IDXGISwapChain_GetDesc_Stop
0x180043151  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180043158  call    cs:__imp_EtwEventWrite
0x18004315e  mov     eax, ebx
0x180043160  jmp     loc_1800430C4
0x180043165  mov     rax, cs:qword_180108128
0x18004316c  and     rax, rdx
0x18004316f  cmp     rax, cs:qword_180108128
0x180043176  jnz     loc_180042FB0
0x18004317c  mov     [rbp+57h+var_B0], 1
0x180043180  lea     rax, [rbp+57h+var_A8]
0x180043184  mov     [rbp+57h+var_98], rax
0x180043188  mov     [rbp+57h+var_90], 8
0x180043190  mov     [rbp+57h+var_80], 48h ; 'H'
0x180043198  test    rdi, rdi
0x18004319b  jz      short loc_1800431C4
0x18004319d  mov     [rbp+57h+var_88], rdi
0x1800431a1  lea     r9, [rbp+57h+var_98]
0x1800431a5  mov     r8d, 2
0x1800431ab  lea     rdx, IDXGISwapChain_GetDesc_Start
0x1800431b2  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800431b9  call    cs:__imp_EtwEventWrite
0x1800431bf  jmp     loc_180042FB0
0x1800431c4  lea     rax, [rbp+57h+var_70]
0x1800431c8  mov     [rbp+57h+var_88], rax
0x1800431cc  jmp     short loc_1800431A1
0x1800431ce  xor     r8d, r8d; bool
0x1800431d1  xor     edx, edx; struct CDXGIOutput *
0x1800431d3  mov     rcx, rbx; this
0x1800431d6  call    ?ScenarioEnterOrLeaveFullscreen@CDXGISwapChain@@QEAAJPEAVCDXGIOutput@@_N@Z; CDXGISwapChain::ScenarioEnterOrLeaveFullscreen(CDXGIOutput *,bool)
0x1800431db  jmp     loc_180043056
```
