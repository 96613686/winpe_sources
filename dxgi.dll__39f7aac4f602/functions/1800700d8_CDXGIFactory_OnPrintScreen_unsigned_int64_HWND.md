# CDXGIFactory::OnPrintScreen(unsigned __int64,HWND__ *)

- ea: `0x1800700d8`
- end: `0x180070550`
- name: `?OnPrintScreen@CDXGIFactory@@QEAAH_KPEAUHWND__@@@Z`
- size: `1144`
- prototype: `__int64 __fastcall(CDXGIFactory *__hidden this, unsigned __int64, HWND)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18006ffd8`

## callees

- `0x18001960c`
- `0x18001a6d4`
- `0x18001c08c`
- `0x180037850`
- `0x180037e50`
- `0x18004f400`
- `0x180050784`
- `0x180061258`
- `0x18006ec58`
- `0x1800700d8`
- `0x180075fa0`
- `0x180098160`
- `0x180098ad0`
- `0x1800cb010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800704b4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800704b4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x1800702a9`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x1800702a9`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800703e9`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800703e9`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18007033f`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18007033f`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18007036e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800703e0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18007036e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800703e0`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18007035a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18007035a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800703c3`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800703d4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800703c3`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800703d4`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1800703f4`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1800703f4`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18007032a`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18007032a`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x18007037c`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x18007037c`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x1800703aa`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x1800703aa`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x1800703c9`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x1800703c9`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1800703b8`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1800703b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDXGIFactory::OnPrintScreen(CDXGIFactory *this, __int64 a2, HWND a3)
{
  HWND v3; // rsi
  __int64 v4; // r14
  CDXGIFactory *v5; // r13
  __int64 v6; // rcx
  CDXGIOutput **v7; // r12
  CDXGIOutput *v8; // rbx
  _QWORD **v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  CDXGIOutput *OutputFromWindow; // rax
  unsigned int v14; // esi
  unsigned int i; // edx
  unsigned int j; // ebx
  int v17; // r15d
  int v18; // ebx
  HDC DC; // rax
  HDC v20; // r14
  HDC CompatibleDC; // rsi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v23; // rbx
  HGDIOBJ v24; // r15
  _QWORD **v25; // rcx
  _QWORD *v26; // rbx
  _QWORD *v27; // rcx
  _QWORD *v28; // rbx
  _DWORD *v29; // rsi
  _QWORD **v30; // r15
  __int64 size_of; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rcx
  struct IDXGIAdapter *v34; // [rsp+30h] [rbp-A8h] BYREF
  CDXGIOutput *v35; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD **v36; // [rsp+40h] [rbp-98h] BYREF
  __int64 v37; // [rsp+48h] [rbp-90h]
  HWND hWndNewOwner; // [rsp+50h] [rbp-88h]
  __int64 v39; // [rsp+58h] [rbp-80h] BYREF
  char v40; // [rsp+60h] [rbp-78h]
  CDXGIFactory *v41; // [rsp+68h] [rbp-70h]
  HWND v42; // [rsp+70h] [rbp-68h]
  CDXGIOutput **v43; // [rsp+78h] [rbp-60h]
  struct tagRECT rcDst; // [rsp+80h] [rbp-58h] BYREF
  RECT rcSrc2; // [rsp+90h] [rbp-48h] BYREF

  v3 = a3;
  hWndNewOwner = a3;
  v4 = a2;
  v5 = this;
  v41 = this;
  v42 = a3;
  rcDst = 0;
  std::list<CDXGIOutput *>::list<CDXGIOutput *>(&v36);
  v40 = 0;
  v39 = ((unsigned __int64)v5 + 264) & -(__int64)(v5 != 0);
  CThreadLock<0>::TakeLock(&v39);
  v7 = (CDXGIOutput **)((char *)v5 + 344);
  v43 = (CDXGIOutput **)((char *)v5 + 344);
  v8 = (CDXGIOutput *)*((_QWORD *)v5 + 43);
  while ( 1 )
  {
    v8 = *(CDXGIOutput **)v8;
    v35 = v8;
    if ( v8 == *v7 )
      break;
    try
    {
      v29 = *(_DWORD **)(*((_QWORD *)v8 + 2) + 2128LL);
      if ( v29 && (unsigned int)(v29[131] - 1) <= 1 )
      {
        v34 = *(struct IDXGIAdapter **)(*((_QWORD *)v8 + 2) + 2128LL);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v29 + 8LL))(v29);
        if ( v37 == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("list too long");
        v30 = v36;
        *(_QWORD *)&rcSrc2.left = &v36;
        *(_QWORD *)&rcSrc2.right = 0;
        size_of = std::_Get_size_of_n<24>(1);
        v32 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
        v32[2] = v29;
        ++v37;
        v33 = v30[1];
        *v32 = v30;
        v32[1] = v33;
        *(_QWORD *)&rcSrc2.right = 0;
        v30[1] = v32;
        *v33 = v32;
        std::_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>(&rcSrc2);
      }
      v3 = hWndNewOwner;
    }
    catch ( std::bad_alloc )
    {
      ((void (__fastcall *)(struct IDXGIAdapter *))v34->lpVtbl->Release)(v34);
      v4 = a2;
      v8 = v35;
      v5 = v41;
      v3 = v42;
      hWndNewOwner = v42;
      v7 = v43;
      continue;
    }
  }
  if ( v37 )
  {
    if ( v4 == -1 )
    {
      OutputFromWindow = (CDXGIOutput *)CDXGIFactory::GetOutputFromWindow(v6, v3, &v36);
      if ( OutputFromWindow )
        CDXGIOutput::GetMonitorRect(OutputFromWindow, &rcDst);
    }
    else if ( v4 == -2 || v4 == IDHOT_CTRL_SNAPDESKTOP )
    {
      v34 = 0;
      v14 = 0;
      for ( i = 0; (int)CDXGIFactory::EnumAdapters(v5, i, &v34) >= 0; i = v14 )
      {
        v35 = 0;
        for ( j = 0;
              ((int (__fastcall *)(struct IDXGIAdapter *, _QWORD, CDXGIOutput **))v34->lpVtbl->EnumOutputs)(
                v34,
                j,
                &v35) >= 0;
              ++j )
        {
          rcSrc2 = 0;
          CDXGIOutput::GetMonitorRect(v35, &rcSrc2);
          UnionRect(&rcDst, &rcDst, &rcSrc2);
          (*(void (__fastcall **)(CDXGIOutput *))(*(_QWORD *)v35 + 16LL))(v35);
        }
        ((void (__fastcall *)(struct IDXGIAdapter *))v34->lpVtbl->Release)(v34);
        ++v14;
      }
    }
    CThreadLock<0>::ReleaseLock(&v39);
    v17 = rcDst.right - rcDst.left;
    if ( rcDst.right - rcDst.left > 0 )
    {
      v18 = rcDst.bottom - rcDst.top;
      if ( rcDst.bottom - rcDst.top > 0 )
      {
        DC = GetDC(0);
        v20 = DC;
        if ( DC )
        {
          CompatibleDC = CreateCompatibleDC(DC);
          if ( CompatibleDC )
          {
            CompatibleBitmap = CreateCompatibleBitmap(v20, v17, v18);
            v23 = CompatibleBitmap;
            if ( CompatibleBitmap )
            {
              v24 = SelectObject(CompatibleDC, CompatibleBitmap);
              if ( OpenClipboard(hWndNewOwner) )
              {
                if ( (int)CDXGIFactory::GetAllFrontBuffers(v5, CompatibleDC, v20, &rcDst, &v36) < 0 )
                {
                  DeleteObject(v23);
                }
                else
                {
                  EmptyClipboard();
                  SetClipboardData(2u, v23);
                }
                CloseClipboard();
              }
              else
              {
                DeleteObject(v23);
              }
              SelectObject(CompatibleDC, v24);
            }
            DeleteDC(CompatibleDC);
          }
          ReleaseDC(0, v20);
        }
      }
    }
    v25 = v36;
    v26 = *v36;
    while ( v26 != v25 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26[2] + 16LL))(v26[2]);
      v26 = (_QWORD *)*v26;
      v25 = v36;
    }
    *v25[1] = 0;
    v27 = *v25;
    if ( v27 )
    {
      do
      {
        v28 = (_QWORD *)*v27;
        std::_Deallocate<16>(v27, 24);
        v27 = v28;
      }
      while ( v28 );
    }
    std::_Deallocate<16>(v36, 24);
    return 1;
  }
  else
  {
    CThreadLock<0>::ReleaseLock(&v39);
    v9 = v36;
    *v36[1] = 0;
    v10 = *v9;
    if ( v10 )
    {
      do
      {
        v11 = (_QWORD *)*v10;
        std::_Deallocate<16>(v10, 24);
        v10 = v11;
      }
      while ( v11 );
    }
    std::_Deallocate<16>(v36, 24);
    return 0;
  }
}

```

## disassembly

```asm
0x1800700d8  mov     r11, rsp
0x1800700db  mov     [r11+20h], rbx
0x1800700df  mov     [r11+10h], rdx
0x1800700e3  push    rsi
0x1800700e4  push    r12
0x1800700e6  push    r13
0x1800700e8  push    r14
0x1800700ea  push    r15
0x1800700ec  sub     rsp, 0B0h
0x1800700f3  mov     rax, cs:__security_cookie
0x1800700fa  xor     rax, rsp
0x1800700fd  mov     [rsp+0D8h+var_38], rax
0x180070105  mov     rsi, r8
0x180070108  mov     [rsp+0D8h+hWndNewOwner], r8
0x18007010d  mov     r14, rdx
0x180070110  mov     r13, rcx
0x180070113  mov     [rsp+0D8h+var_70], rcx
0x180070118  mov     [rsp+0D8h+var_68], r8
0x18007011d  xorps   xmm0, xmm0
0x180070120  movups  xmmword ptr [r11-58h], xmm0
0x180070125  lea     rcx, [rsp+0D8h+var_98]
0x18007012a  call    ??0?$list@PEAVCDXGIOutput@@V?$allocator@PEAVCDXGIOutput@@@std@@@std@@QEAA@XZ; std::list<CDXGIOutput *>::list<CDXGIOutput *>(void)
0x18007012f  nop
0x180070130  mov     [rsp+0D8h+var_78], 0
0x180070135  mov     rax, r13
0x180070138  lea     rdx, [r13+108h]
0x18007013f  neg     rax
0x180070142  sbb     rcx, rcx
0x180070145  and     rcx, rdx
0x180070148  mov     [rsp+0D8h+var_80], rcx
0x18007014d  lea     rcx, [rsp+0D8h+var_80]
0x180070152  call    ?TakeLock@?$CThreadLock@$0A@@@QEAAXXZ; CThreadLock<0>::TakeLock(void)
0x180070157  nop
0x180070158  lea     r12, [r13+158h]
0x18007015f  mov     [rsp+0D8h+var_60], r12
0x180070164  mov     rbx, [r12]
0x180070168  mov     rbx, [rbx]
0x18007016b  mov     [rsp+0D8h+var_A0], rbx
0x180070170  cmp     rbx, [r12]
0x180070174  jnz     loc_180070462
0x18007017a  cmp     [rsp+0D8h+var_90], 0
0x180070180  jnz     short loc_1800701F4
0x180070182  lea     rcx, [rsp+0D8h+var_80]
0x180070187  call    ?ReleaseLock@?$CThreadLock@$0A@@@QEAAXXZ; CThreadLock<0>::ReleaseLock(void)
0x18007018c  nop
0x18007018d  mov     rcx, [rsp+0D8h+var_98]
0x180070192  mov     rax, [rcx+8]
0x180070196  mov     qword ptr [rax], 0
0x18007019d  mov     rcx, [rcx]
0x1800701a0  test    rcx, rcx
0x1800701a3  jz      short loc_1800701BA
0x1800701a5  mov     rbx, [rcx]
0x1800701a8  mov     edx, 18h
0x1800701ad  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800701b2  mov     rcx, rbx
0x1800701b5  test    rbx, rbx
0x1800701b8  jnz     short loc_1800701A5
0x1800701ba  mov     edx, 18h
0x1800701bf  mov     rcx, [rsp+0D8h+var_98]
0x1800701c4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800701c9  xor     eax, eax
0x1800701cb  mov     rcx, [rsp+0D8h+var_38]
0x1800701d3  xor     rcx, rsp; StackCookie
0x1800701d6  call    __security_check_cookie
0x1800701db  mov     rbx, [rsp+0D8h+arg_18]
0x1800701e3  add     rsp, 0B0h
0x1800701ea  pop     r15
0x1800701ec  pop     r14
0x1800701ee  pop     r13
0x1800701f0  pop     r12
0x1800701f2  pop     rsi
0x1800701f3  retn
0x1800701f4  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800701f8  jnz     short loc_180070225
0x1800701fa  lea     r8, [rsp+0D8h+var_98]
0x1800701ff  mov     rdx, rsi
0x180070202  call    ?GetOutputFromWindow@CDXGIFactory@@QEAAPEAVCDXGIOutput@@PEAUHWND__@@AEAV?$list@PEAVCDXGIOutput@@V?$allocator@PEAVCDXGIOutput@@@std@@@std@@@Z; CDXGIFactory::GetOutputFromWindow(HWND__ *,std::list<CDXGIOutput *> &)
0x180070207  test    rax, rax
0x18007020a  jz      loc_1800702EE
0x180070210  lea     rdx, [rsp+0D8h+rcDst]; struct tagRECT *
0x180070218  mov     rcx, rax; this
0x18007021b  call    ?GetMonitorRect@CDXGIOutput@@QEAAXPEAUtagRECT@@@Z; CDXGIOutput::GetMonitorRect(tagRECT *)
0x180070220  jmp     loc_1800702EE
0x180070225  cmp     r14, 0FFFFFFFFFFFFFFFEh
0x180070229  jz      short loc_18007023B
0x18007022b  movzx   eax, cs:?IDHOT_CTRL_SNAPDESKTOP@@3GB; ushort const IDHOT_CTRL_SNAPDESKTOP
0x180070232  cmp     r14, rax
0x180070235  jnz     loc_1800702EE
0x18007023b  mov     [rsp+0D8h+var_A8], 0
0x180070244  xor     esi, esi
0x180070246  xor     edx, edx
0x180070248  jmp     loc_1800702D9
0x18007024d  mov     [rsp+0D8h+var_A0], 0
0x180070256  xor     ebx, ebx
0x180070258  mov     rcx, [rsp+0D8h+var_A8]
0x18007025d  mov     rax, [rcx]
0x180070260  lea     r8, [rsp+0D8h+var_A0]
0x180070265  mov     edx, ebx
0x180070267  mov     rax, [rax+38h]
0x18007026b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070270  test    eax, eax
0x180070272  js      short loc_1800702C4
0x180070274  xorps   xmm0, xmm0
0x180070277  movups  xmmword ptr [rsp+0D8h+rcSrc2.left], xmm0
0x18007027f  lea     rdx, [rsp+0D8h+rcSrc2]; struct tagRECT *
0x180070287  mov     rcx, [rsp+0D8h+var_A0]; this
0x18007028c  call    ?GetMonitorRect@CDXGIOutput@@QEAAXPEAUtagRECT@@@Z; CDXGIOutput::GetMonitorRect(tagRECT *)
0x180070291  lea     r8, [rsp+0D8h+rcSrc2]; lprcSrc2
0x180070299  lea     rdx, [rsp+0D8h+rcDst]; lprcSrc1
0x1800702a1  lea     rcx, [rsp+0D8h+rcDst]; lprcDst
0x1800702a9  call    cs:__imp_UnionRect
0x1800702af  mov     rcx, [rsp+0D8h+var_A0]
0x1800702b4  mov     rax, [rcx]
0x1800702b7  mov     rax, [rax+10h]
0x1800702bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800702c0  inc     ebx
0x1800702c2  jmp     short loc_180070258
0x1800702c4  mov     rcx, [rsp+0D8h+var_A8]
0x1800702c9  mov     rax, [rcx]
0x1800702cc  mov     rax, [rax+10h]
0x1800702d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800702d5  inc     esi
0x1800702d7  mov     edx, esi; unsigned int
0x1800702d9  lea     r8, [rsp+0D8h+var_A8]; struct IDXGIAdapter **
0x1800702de  mov     rcx, r13; this
0x1800702e1  call    ?EnumAdapters@CDXGIFactory@@UEAAJIPEAPEAUIDXGIAdapter@@@Z; CDXGIFactory::EnumAdapters(uint,IDXGIAdapter * *)
0x1800702e6  test    eax, eax
0x1800702e8  jns     loc_18007024D
0x1800702ee  lea     rcx, [rsp+0D8h+var_80]
0x1800702f3  call    ?ReleaseLock@?$CThreadLock@$0A@@@QEAAXXZ; CThreadLock<0>::ReleaseLock(void)
0x1800702f8  nop
0x1800702f9  mov     r15d, [rsp+0D8h+rcDst.right]
0x180070301  sub     r15d, [rsp+0D8h+rcDst.left]
0x180070309  test    r15d, r15d
0x18007030c  jle     loc_1800703FA
0x180070312  mov     ebx, [rsp+0D8h+rcDst.bottom]
0x180070319  sub     ebx, [rsp+0D8h+rcDst.top]
0x180070320  test    ebx, ebx
0x180070322  jle     loc_1800703FA
0x180070328  xor     ecx, ecx; hWnd
0x18007032a  call    cs:__imp_GetDC
0x180070330  mov     r14, rax
0x180070333  test    rax, rax
0x180070336  jz      loc_1800703FA
0x18007033c  mov     rcx, rax; hdc
0x18007033f  call    cs:__imp_CreateCompatibleDC
0x180070345  mov     rsi, rax
0x180070348  test    rax, rax
0x18007034b  jz      loc_1800703EF
0x180070351  mov     r8d, ebx; cy
0x180070354  mov     edx, r15d; cx
0x180070357  mov     rcx, r14; hdc
0x18007035a  call    cs:__imp_CreateCompatibleBitmap
0x180070360  mov     rbx, rax
0x180070363  test    rax, rax
0x180070366  jz      short loc_1800703E6
0x180070368  mov     rdx, rax; h
0x18007036b  mov     rcx, rsi; hdc
0x18007036e  call    cs:__imp_SelectObject
0x180070374  mov     r15, rax
0x180070377  mov     rcx, [rsp+0D8h+hWndNewOwner]; hWndNewOwner
0x18007037c  call    cs:__imp_OpenClipboard
0x180070382  test    eax, eax
0x180070384  jz      short loc_1800703D1
0x180070386  lea     rax, [rsp+0D8h+var_98]
0x18007038b  mov     [rsp+0D8h+var_B8], rax
0x180070390  lea     r9, [rsp+0D8h+rcDst]
0x180070398  mov     r8, r14
0x18007039b  mov     rdx, rsi
0x18007039e  mov     rcx, r13
0x1800703a1  call    ?GetAllFrontBuffers@CDXGIFactory@@QEAAJPEAUHDC__@@0PEAUtagRECT@@AEAV?$list@PEAVCDXGIOutput@@V?$allocator@PEAVCDXGIOutput@@@std@@@std@@@Z; CDXGIFactory::GetAllFrontBuffers(HDC__ *,HDC__ *,tagRECT *,std::list<CDXGIOutput *> &)
0x1800703a6  test    eax, eax
0x1800703a8  js      short loc_1800703C0
0x1800703aa  call    cs:__imp_EmptyClipboard
0x1800703b0  mov     rdx, rbx; hMem
0x1800703b3  mov     ecx, 2; uFormat
0x1800703b8  call    cs:__imp_SetClipboardData
0x1800703be  jmp     short loc_1800703C9
0x1800703c0  mov     rcx, rbx; ho
0x1800703c3  call    cs:__imp_DeleteObject
0x1800703c9  call    cs:__imp_CloseClipboard
0x1800703cf  jmp     short loc_1800703DA
0x1800703d1  mov     rcx, rbx; ho
0x1800703d4  call    cs:__imp_DeleteObject
0x1800703da  mov     rdx, r15; h
0x1800703dd  mov     rcx, rsi; hdc
0x1800703e0  call    cs:__imp_SelectObject
0x1800703e6  mov     rcx, rsi; hdc
0x1800703e9  call    cs:__imp_DeleteDC
0x1800703ef  mov     rdx, r14; hDC
0x1800703f2  xor     ecx, ecx; hWnd
0x1800703f4  call    cs:__imp_ReleaseDC
0x1800703fa  mov     rcx, [rsp+0D8h+var_98]
0x1800703ff  mov     rbx, [rcx]
0x180070402  cmp     rbx, rcx
0x180070405  jz      short loc_180070421
0x180070407  mov     rcx, [rbx+10h]
0x18007040b  mov     rax, [rcx]
0x18007040e  mov     rax, [rax+10h]
0x180070412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070417  mov     rbx, [rbx]
0x18007041a  mov     rcx, [rsp+0D8h+var_98]
0x18007041f  jmp     short loc_180070402
0x180070421  mov     rax, [rcx+8]
0x180070425  mov     qword ptr [rax], 0
0x18007042c  mov     rcx, [rcx]
0x18007042f  test    rcx, rcx
0x180070432  jz      short loc_180070449
0x180070434  mov     rbx, [rcx]
0x180070437  mov     edx, 18h
0x18007043c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180070441  mov     rcx, rbx
0x180070444  test    rbx, rbx
0x180070447  jnz     short loc_180070434
0x180070449  mov     edx, 18h
0x18007044e  mov     rcx, [rsp+0D8h+var_98]
0x180070453  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180070458  mov     eax, 1
0x18007045d  jmp     loc_1800701CB
0x180070462  mov     rax, [rbx+10h]
0x180070466  mov     rsi, [rax+850h]
0x18007046d  test    rsi, rsi
0x180070470  jz      loc_18007051F
0x180070476  mov     eax, [rsi+20Ch]
0x18007047c  dec     eax
0x18007047e  cmp     eax, 1
0x180070481  ja      loc_18007051F
0x180070487  mov     [rsp+0D8h+var_A8], rsi
0x18007048c  mov     rax, [rsi]
0x18007048f  mov     rcx, rsi
0x180070492  mov     rax, [rax+8]
0x180070496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007049b  nop
0x18007049c  mov     rax, 0AAAAAAAAAAAAAAAh
0x1800704a6  cmp     [rsp+0D8h+var_90], rax
0x1800704ab  jnz     short loc_1800704BA
0x1800704ad  lea     rcx, aListTooLong; "list too long"
0x1800704b4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800704ba  mov     r15, [rsp+0D8h+var_98]
0x1800704bf  lea     rax, [rsp+0D8h+var_98]
0x1800704c4  mov     qword ptr [rsp+0D8h+rcSrc2.left], rax
0x1800704cc  mov     qword ptr [rsp+0D8h+rcSrc2.right], 0
0x1800704d8  mov     ecx, 1
0x1800704dd  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x1800704e2  mov     rcx, rax
0x1800704e5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800704ea  mov     [rax+10h], rsi
0x1800704ee  inc     [rsp+0D8h+var_90]
0x1800704f3  mov     rcx, [r15+8]
0x1800704f7  mov     [rax], r15
0x1800704fa  mov     [rax+8], rcx
0x1800704fe  mov     qword ptr [rsp+0D8h+rcSrc2.right], 0
0x18007050a  mov     [r15+8], rax
0x18007050e  mov     [rcx], rax
0x180070511  lea     rcx, [rsp+0D8h+rcSrc2]
0x180070519  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAVCDXGISwapChain@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>(void)
0x18007051e  nop
0x18007051f  mov     rsi, [rsp+0D8h+hWndNewOwner]
0x180070524  jmp     loc_180070168
0x180070529  mov     r14, [rsp+0D8h+arg_8]
0x180070531  mov     rbx, [rsp+0D8h+var_A0]
0x180070536  mov     r13, [rsp+0D8h+var_70]
0x18007053b  mov     rsi, [rsp+0D8h+var_68]
0x180070540  mov     [rsp+0D8h+hWndNewOwner], rsi
0x180070545  mov     r12, [rsp+0D8h+var_60]
0x18007054a  jmp     loc_180070168
```
