# CDXGISwapChain::Present(uint,uint)

- ea: `0x1800076e0`
- end: `0x180007b4c`
- name: `?Present@CDXGISwapChain@@UEAAJII@Z`
- size: `1132`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180099310`

## callees

- `0x1800076e0`
- `0x180007b54`
- `0x18000c6b0`
- `0x18000d120`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007987`
- `ntdll!EtwEventWrite` at `0x180007a1a`
- `ntdll!EtwEventWrite` at `0x180007987`
- `ntdll!EtwEventWrite` at `0x180007a1a`

## pseudocode

```c
__int64 __fastcall CDXGISwapChain::Present(CDXGISwapChain *this, int a2, int a3)
{
  __int64 v6; // rcx
  int v7; // eax
  CModule *v8; // rcx
  int v9; // r8d
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rsi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  char v22; // [rsp+50h] [rbp-B0h]
  char v23; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v24; // [rsp+55h] [rbp-ABh]
  char v25; // [rsp+57h] [rbp-A9h]
  CDXGISwapChain *v26; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v27[6]; // [rsp+60h] [rbp-A0h] BYREF
  char v28; // [rsp+78h] [rbp-88h]
  __int128 v29; // [rsp+7Ch] [rbp-84h]
  int v30; // [rsp+8Ch] [rbp-74h]
  __int128 v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h]
  __int128 v33; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+D0h] [rbp-30h]
  __int128 v36; // [rsp+E0h] [rbp-20h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  __int128 v38; // [rsp+100h] [rbp+0h]
  __int128 v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+120h] [rbp+20h]
  CDXGISwapChain **v41; // [rsp+130h] [rbp+30h] BYREF
  __int64 v42; // [rsp+138h] [rbp+38h]
  CDXGISwapChain **v43; // [rsp+140h] [rbp+40h]
  __int64 v44; // [rsp+148h] [rbp+48h]
  int *v45; // [rsp+150h] [rbp+50h]
  __int64 v46; // [rsp+158h] [rbp+58h]

  v21 = a3;
  v20 = a2;
  v26 = this;
  v22 = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v41 = &v26;
    v22 = 1;
    v43 = (CDXGISwapChain **)&v20;
    v42 = 8;
    v45 = &v21;
    v44 = 4;
    v46 = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_Present_Start, 3, &v41);
  }
  if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
  {
    LODWORD(v26) = 0;
    *(_QWORD *)&v32 = &v41;
    v27[0] = 0;
    *(_QWORD *)&v33 = &v21;
    v20 = a2;
    *(_QWORD *)&v34 = &v20;
    *(_QWORD *)&v35 = v27;
    *(_QWORD *)&v36 = &v26;
    v21 = a3;
    v41 = (CDXGISwapChain **)this;
    *((_QWORD *)&v32 + 1) = 8;
    *((_QWORD *)&v33 + 1) = 4;
    *((_QWORD *)&v34 + 1) = 4;
    *((_QWORD *)&v35 + 1) = 4;
    *((_QWORD *)&v36 + 1) = 4;
    McGenEventWrite_EtwEventWriteTransfer((_DWORD)this, (unsigned int)EventPresentStart, a3, 6, (__int64)&v31);
  }
  v27[2] = 1;
  v27[3] = a3;
  v27[4] = a2;
  v27[5] = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v40 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( *((_DWORD *)this + 82) )
  {
    if ( *((_DWORD *)this + 111) != 1 )
    {
      v6 = *((_QWORD *)this + 266);
      if ( v6 )
      {
        if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6 + 216LL))(v6, &v31) >= 0 )
        {
          v29 = v35;
          v30 = DWORD1(v36);
        }
      }
    }
  }
  v7 = CDXGISwapChain::PresentImpl(this, 0, 0, 0);
  v20 = v7;
  v10 = v7;
  v11 = 0x400000000351LL;
  v12 = 0x20200000219LL;
  if ( v7 )
  {
    CModule::RecordJournalImpl(v8, v7, "Non-zero return value");
    if ( v10 != -2005532292 && v10 != -2147024809 && v10 != -2147024882 )
    {
      v13 = v10 - 142213121;
      if ( (unsigned int)v13 > 0x2E || !_bittest64(&v11, v13) )
      {
        v14 = v10 + 2005270527;
        if ( (unsigned int)v14 > 0x29 || !_bittest64(&v12, v14) )
          CModule::RecordJournalImpl(v8, v10, "Contract breached!");
      }
    }
  }
  if ( v10 == 142213122 )
  {
    v10 = 0;
    v20 = 0;
  }
  else if ( v10 == 142213125 )
  {
    v10 = 142213121;
    v20 = 142213121;
    CModule::RecordJournalImpl(v8, 142213121, "Non-zero return value");
  }
  if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
  {
    if ( v10 )
    {
      if ( v10 != -2147024809 && v10 != -2147024882 )
      {
        v18 = v10 - 142213121;
        if ( ((unsigned int)v18 > 0x2E || !_bittest64(&v11, v18)) && v10 != -2005532292 )
        {
          v19 = v10 + 2005270527;
          if ( (unsigned int)v19 > 0x29 || !_bittest64(&v12, v19) )
            CModule::RecordJournalImpl(v8, v10, "Contract breached!");
        }
      }
    }
    LODWORD(v26) = v10;
    v43 = &v26;
    v44 = 4;
    McGenEventWrite_EtwEventWriteTransfer((_DWORD)v8, (unsigned int)EventPresentStop, v9, 2, (__int64)&v41);
  }
  if ( v10 )
  {
    if ( v10 != -2147024809 && v10 != -2147024882 )
    {
      v16 = v10 - 142213121;
      if ( ((unsigned int)v16 > 0x2E || !_bittest64(&v11, v16)) && v10 != -2005532292 )
      {
        v17 = v10 + 2005270527;
        if ( (unsigned int)v17 > 0x29 || !_bittest64(&v12, v17) )
          CModule::RecordJournalImpl(v8, v10, "Contract breached!");
      }
    }
  }
  v24 = *(_WORD *)((char *)&v20 + 1);
  v25 = HIBYTE(v20);
  v23 = v10;
  if ( v22 )
  {
    v41 = (CDXGISwapChain **)&v23;
    v42 = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_Present_Stop, 1, &v41);
  }
  return v10;
}

```

## disassembly

```asm
0x1800076e0  mov     [rsp-8+arg_8], rbx
0x1800076e5  mov     [rsp-8+arg_10], rsi
0x1800076ea  push    rbp
0x1800076eb  push    rdi
0x1800076ec  push    r14
0x1800076ee  lea     rbp, [rsp-70h]
0x1800076f3  sub     rsp, 170h
0x1800076fa  mov     rax, cs:__security_cookie
0x180007701  xor     rax, rsp
0x180007704  mov     [rbp+80h+var_20], rax
0x180007708  xor     r14d, r14d
0x18000770b  mov     [rsp+180h+var_138], r8d
0x180007710  cmp     cs:dword_180108134, r14d
0x180007717  mov     edi, r8d
0x18000771a  mov     esi, edx
0x18000771c  mov     [rsp+180h+var_140], edx
0x180007720  mov     rbx, rcx
0x180007723  mov     [rsp+180h+var_128], rcx
0x180007728  mov     [rsp+180h+var_130], 0
0x18000772d  jz      short loc_180007746
0x18000772f  mov     rdx, 4000000000000000h
0x180007739  test    cs:qword_180108120, rdx
0x180007740  jnz     loc_1800079B3
0x180007746  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x18000774d  jz      loc_1800077D8
0x180007753  lea     rax, [rbp+80h+var_50]
0x180007757  mov     dword ptr [rsp+180h+var_128], r14d
0x18000775c  mov     qword ptr [rbp+80h+var_E0], rax
0x180007760  lea     rdx, EventPresentStart
0x180007767  lea     rax, [rsp+180h+var_138]
0x18000776c  mov     [rsp+180h+var_120], r14d
0x180007771  mov     qword ptr [rbp+80h+var_D0], rax
0x180007775  mov     r9d, 6
0x18000777b  lea     rax, [rsp+180h+var_140]
0x180007780  mov     [rsp+180h+var_140], esi
0x180007784  mov     qword ptr [rbp+80h+var_C0], rax
0x180007788  lea     rax, [rsp+180h+var_120]
0x18000778d  mov     qword ptr [rbp+80h+var_B0], rax
0x180007791  lea     rax, [rsp+180h+var_128]
0x180007796  mov     qword ptr [rbp+80h+var_A0], rax
0x18000779a  lea     rax, [rbp+80h+var_F0]
0x18000779e  mov     qword ptr [rsp+180h+var_160], rax
0x1800077a3  mov     [rsp+180h+var_138], edi
0x1800077a7  mov     [rbp+80h+var_50], rbx
0x1800077ab  mov     qword ptr [rbp+80h+var_E0+8], 8
0x1800077b3  mov     qword ptr [rbp+80h+var_D0+8], 4
0x1800077bb  mov     qword ptr [rbp+80h+var_C0+8], 4
0x1800077c3  mov     qword ptr [rbp+80h+var_B0+8], 4
0x1800077cb  mov     qword ptr [rbp+80h+var_A0+8], 4
0x1800077d3  call    McGenEventWrite_EtwEventWriteTransfer
0x1800077d8  xorps   xmm1, xmm1
0x1800077db  mov     [rsp+180h+var_118], 1
0x1800077e3  xor     eax, eax
0x1800077e5  mov     [rsp+180h+var_114], edi
0x1800077e9  xorps   xmm0, xmm0
0x1800077ec  mov     [rsp+180h+var_110], esi
0x1800077f0  mov     [rsp+180h+var_10C], r14d
0x1800077f5  mov     [rsp+180h+var_108], r14b
0x1800077fa  movdqu  [rsp+180h+var_104], xmm0
0x180007800  mov     [rbp+80h+var_F4], r14d
0x180007804  movups  [rbp+80h+var_F0], xmm1
0x180007808  mov     [rbp+80h+var_60], rax
0x18000780c  movups  [rbp+80h+var_E0], xmm1
0x180007810  movups  [rbp+80h+var_D0], xmm1
0x180007814  movups  [rbp+80h+var_C0], xmm1
0x180007818  movups  [rbp+80h+var_B0], xmm1
0x18000781c  movups  [rbp+80h+var_A0], xmm1
0x180007820  movups  [rbp+80h+var_90], xmm1
0x180007824  movups  [rbp+80h+var_80], xmm1
0x180007828  movups  [rbp+80h+var_70], xmm1
0x18000782c  cmp     [rbx+148h], eax
0x180007832  jz      short loc_18000787F
0x180007834  cmp     dword ptr [rbx+1BCh], 1
0x18000783b  jz      short loc_18000787F
0x18000783d  mov     rcx, [rbx+850h]
0x180007844  test    rcx, rcx
0x180007847  jz      short loc_18000787F
0x180007849  mov     rax, [rcx]
0x18000784c  lea     rdx, [rbp+80h+var_F0]
0x180007850  mov     rax, [rax+0D8h]
0x180007857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785c  test    eax, eax
0x18000785e  js      short loc_18000787F
0x180007860  mov     eax, dword ptr [rbp+80h+var_B0]
0x180007863  mov     dword ptr [rsp+180h+var_104], eax
0x180007867  mov     eax, dword ptr [rbp+80h+var_B0+4]
0x18000786a  mov     dword ptr [rbp+80h+var_104+4], eax
0x18000786d  mov     eax, dword ptr [rbp+80h+var_B0+8]
0x180007870  mov     dword ptr [rbp+80h+var_104+8], eax
0x180007873  mov     eax, dword ptr [rbp+80h+var_B0+0Ch]
0x180007876  mov     dword ptr [rbp+80h+var_104+0Ch], eax
0x180007879  mov     eax, dword ptr [rbp+80h+var_A0+4]
0x18000787c  mov     [rbp+80h+var_F4], eax
0x18000787f  mov     [rsp+180h+var_150], r14; __int64
0x180007884  lea     rdx, [rsp+180h+var_118]
0x180007889  mov     [rsp+180h+var_158], r14; __int64
0x18000788e  xor     r9d, r9d
0x180007891  xor     r8d, r8d
0x180007894  mov     [rsp+180h+var_160], r14d; int
0x180007899  mov     rcx, rbx; this
0x18000789c  call    ?PresentImpl@CDXGISwapChain@@QEAAJPEBU?$SPresentArgsCore@UCDXGISwapChainWrapper@@@@IPEBUtagRECT@@IPEBUDXGI_SCROLL_RECT@@PEAUIDXGIResource@@@Z; CDXGISwapChain::PresentImpl(SPresentArgsCore<CDXGISwapChainWrapper> const *,uint,tagRECT const *,uint,DXGI_SCROLL_RECT const *,IDXGIResource *)
0x1800078a1  mov     [rsp+180h+var_140], eax
0x1800078a5  mov     ebx, eax
0x1800078a7  mov     rdi, 400000000351h
0x1800078b1  mov     rsi, 20200000219h
0x1800078bb  test    eax, eax
0x1800078bd  jz      short loc_180007915
0x1800078bf  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x1800078c6  mov     edx, eax; unsigned int
0x1800078c8  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800078cd  cmp     ebx, 8876017Ch
0x1800078d3  jz      short loc_180007915
0x1800078d5  cmp     ebx, 80070057h
0x1800078db  jz      short loc_180007915
0x1800078dd  cmp     ebx, 8007000Eh
0x1800078e3  jz      short loc_180007915
0x1800078e5  lea     eax, [rbx-87A0001h]
0x1800078eb  cmp     eax, 2Eh ; '.'
0x1800078ee  ja      short loc_1800078F6
0x1800078f0  bt      rdi, rax
0x1800078f4  jb      short loc_180007915
0x1800078f6  lea     eax, [rbx+7785FFFFh]
0x1800078fc  cmp     eax, 29h ; ')'
0x1800078ff  ja      short loc_180007907
0x180007901  bt      rsi, rax
0x180007905  jb      short loc_180007915
0x180007907  lea     r8, aContractBreach; "Contract breached!"
0x18000790e  mov     edx, ebx; unsigned int
0x180007910  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180007915  mov     eax, ebx
0x180007917  sub     eax, 87A0002h
0x18000791c  jz      loc_180007A7E
0x180007922  cmp     eax, 3
0x180007925  jz      loc_180007A62
0x18000792b  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x180007932  jnz     loc_180007A25
0x180007938  test    ebx, ebx
0x18000793a  jnz     loc_180007A8A
0x180007940  movzx   eax, word ptr [rsp+180h+var_140+1]
0x180007945  mov     [rsp+180h+var_12B], ax
0x18000794a  movzx   eax, byte ptr [rsp+180h+var_140+3]
0x18000794f  mov     [rsp+180h+var_129], al
0x180007953  mov     [rsp+180h+var_12C], bl
0x180007957  cmp     [rsp+180h+var_130], r14b
0x18000795c  jz      short loc_18000798D
0x18000795e  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180007965  lea     rax, [rsp+180h+var_12C]
0x18000796a  lea     r9, [rbp+80h+var_50]
0x18000796e  mov     [rbp+80h+var_50], rax
0x180007972  mov     r8d, 1
0x180007978  mov     [rbp+80h+var_48], 4
0x180007980  lea     rdx, IDXGISwapChain_Present_Stop
0x180007987  call    cs:__imp_EtwEventWrite
0x18000798d  mov     eax, ebx
0x18000798f  mov     rcx, [rbp+80h+var_20]
0x180007993  xor     rcx, rsp; StackCookie
0x180007996  call    __security_check_cookie
0x18000799b  lea     r11, [rsp+180h+var_10]
0x1800079a3  mov     rbx, [r11+28h]
0x1800079a7  mov     rsi, [r11+30h]
0x1800079ab  mov     rsp, r11
0x1800079ae  pop     r14
0x1800079b0  pop     rdi
0x1800079b1  pop     rbp
0x1800079b2  retn
0x1800079b3  mov     rax, cs:qword_180108128
0x1800079ba  and     rax, rdx
0x1800079bd  cmp     rax, cs:qword_180108128
0x1800079c4  jnz     loc_180007746
0x1800079ca  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800079d1  lea     rax, [rsp+180h+var_128]
0x1800079d6  mov     [rbp+80h+var_50], rax
0x1800079da  lea     r9, [rbp+80h+var_50]
0x1800079de  lea     rax, [rsp+180h+var_140]
0x1800079e3  mov     [rsp+180h+var_130], 1
0x1800079e8  mov     [rbp+80h+var_40], rax
0x1800079ec  lea     rdx, IDXGISwapChain_Present_Start
0x1800079f3  lea     rax, [rsp+180h+var_138]
0x1800079f8  mov     [rbp+80h+var_48], 8
0x180007a00  mov     r8d, 3
0x180007a06  mov     [rbp+80h+var_30], rax
0x180007a0a  mov     [rbp+80h+var_38], 4
0x180007a12  mov     [rbp+80h+var_28], 4
0x180007a1a  call    cs:__imp_EtwEventWrite
0x180007a20  jmp     loc_180007746
0x180007a25  test    ebx, ebx
0x180007a27  jnz     loc_180007AEB
0x180007a2d  lea     rax, [rsp+180h+var_128]
0x180007a32  mov     dword ptr [rsp+180h+var_128], ebx
0x180007a36  mov     [rbp+80h+var_40], rax
0x180007a3a  lea     rdx, EventPresentStop
0x180007a41  lea     rax, [rbp+80h+var_50]
0x180007a45  mov     [rbp+80h+var_38], 4
0x180007a4d  mov     r9d, 2
0x180007a53  mov     qword ptr [rsp+180h+var_160], rax
0x180007a58  call    McGenEventWrite_EtwEventWriteTransfer
0x180007a5d  jmp     loc_180007938
0x180007a62  mov     ebx, 87A0001h
0x180007a67  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x180007a6e  mov     edx, ebx; unsigned int
0x180007a70  mov     [rsp+180h+var_140], ebx
0x180007a74  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180007a79  jmp     loc_18000792B
0x180007a7e  mov     ebx, r14d
0x180007a81  mov     [rsp+180h+var_140], ebx
0x180007a85  jmp     loc_18000792B
0x180007a8a  cmp     ebx, 80070057h
0x180007a90  jz      loc_180007940
0x180007a96  cmp     ebx, 8007000Eh
0x180007a9c  jz      loc_180007940
0x180007aa2  lea     eax, [rbx-87A0001h]
0x180007aa8  cmp     eax, 2Eh ; '.'
0x180007aab  ja      short loc_180007AB7
0x180007aad  bt      rdi, rax
0x180007ab1  jb      loc_180007940
0x180007ab7  cmp     ebx, 8876017Ch
0x180007abd  jz      loc_180007940
0x180007ac3  lea     eax, [rbx+7785FFFFh]
0x180007ac9  cmp     eax, 29h ; ')'
0x180007acc  ja      short loc_180007AD8
0x180007ace  bt      rsi, rax
0x180007ad2  jb      loc_180007940
0x180007ad8  lea     r8, aContractBreach; "Contract breached!"
0x180007adf  mov     edx, ebx; unsigned int
0x180007ae1  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180007ae6  jmp     loc_180007940
0x180007aeb  cmp     ebx, 80070057h
0x180007af1  jz      loc_180007A2D
0x180007af7  cmp     ebx, 8007000Eh
0x180007afd  jz      loc_180007A2D
0x180007b03  lea     eax, [rbx-87A0001h]
0x180007b09  cmp     eax, 2Eh ; '.'
0x180007b0c  ja      short loc_180007B18
0x180007b0e  bt      rdi, rax
0x180007b12  jb      loc_180007A2D
0x180007b18  cmp     ebx, 8876017Ch
0x180007b1e  jz      loc_180007A2D
0x180007b24  lea     eax, [rbx+7785FFFFh]
0x180007b2a  cmp     eax, 29h ; ')'
0x180007b2d  ja      short loc_180007B39
0x180007b2f  bt      rsi, rax
0x180007b33  jb      loc_180007A2D
0x180007b39  lea     r8, aContractBreach; "Contract breached!"
0x180007b40  mov     edx, ebx; unsigned int
0x180007b42  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180007b47  jmp     loc_180007A2D
```
