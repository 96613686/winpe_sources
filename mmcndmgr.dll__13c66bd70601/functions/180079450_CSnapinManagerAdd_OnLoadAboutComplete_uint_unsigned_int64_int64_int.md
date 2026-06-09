# CSnapinManagerAdd::OnLoadAboutComplete(uint,unsigned __int64,__int64,int &)

- ea: `0x180079450`
- end: `0x180079716`
- name: `?OnLoadAboutComplete@CSnapinManagerAdd@@IEAA_JI_K_JAEAH@Z`
- size: `710`
- prototype: `__int64(CSnapinManagerAdd *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180079d40`

## callees

- `0x180057074`
- `0x18006a220`
- `0x180073f70`
- `0x180077384`
- `0x180077ca0`
- `0x180079450`
- `0x18007a490`
- `0x18007bc0c`

## import_xrefs

- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180079542`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180079542`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180079533`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180079533`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18007954e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18007954e`
- `USER32!PostThreadMessageW` at `0x1800796e9`
- `USER32!PostThreadMessageW` at `0x1800796e9`
- `USER32!SendMessageW` at `0x1800794c0`
- `USER32!SendMessageW` at `0x1800794ee`
- `USER32!SendMessageW` at `0x180079582`
- `USER32!SendMessageW` at `0x18007959d`
- `USER32!SendMessageW` at `0x1800795ba`
- `USER32!SendMessageW` at `0x1800795d7`
- `USER32!SendMessageW` at `0x1800795e4`
- `USER32!SendMessageW` at `0x180079658`
- `USER32!SendMessageW` at `0x1800794c0`
- `USER32!SendMessageW` at `0x1800794ee`
- `USER32!SendMessageW` at `0x180079582`
- `USER32!SendMessageW` at `0x18007959d`
- `USER32!SendMessageW` at `0x1800795ba`
- `USER32!SendMessageW` at `0x1800795d7`
- `USER32!SendMessageW` at `0x1800795e4`
- `USER32!SendMessageW` at `0x180079658`
- `USER32!GetDlgItem` at `0x180079517`
- `USER32!GetDlgItem` at `0x180079517`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSnapinManagerAdd::OnLoadAboutComplete(
        CSnapinManagerAdd *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  int v7; // ebx
  __int64 v8; // rax
  const OLECHAR *v9; // rbx
  HWND DlgItem; // rax
  WPARAM v11; // rbx
  int v12; // esi
  int v13; // ebx
  int v14; // eax
  HWND v15; // rcx
  int v16; // ebp
  unsigned int i; // esi
  HWND *v18; // rcx
  __int64 ItemData; // rax
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rsi
  LPARAM v24; // rdi
  _BYTE v26[24]; // [rsp+20h] [rbp-68h] BYREF
  _DWORD lParam[4]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v28; // [rsp+48h] [rbp-40h]
  __int128 v29; // [rsp+50h] [rbp-38h]

  if ( a3 )
  {
    if ( *(_DWORD *)(a3 + 76) == -2147467262 )
    {
      *(_BYTE *)(a3 + 152) |= 1u;
      CSnapinInfo::LoadAboutInfo((CSnapinInfo *)a3);
    }
    *(_QWORD *)&lParam[1] = 0;
    lParam[3] = 0;
    v29 = 0;
    lParam[0] = 1;
    v28 = a3;
    v7 = SendMessageW(**((HWND **)this + 9), 0x1053u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
    CSnapinInfo::LoadImages(a3, *(_QWORD *)(*((_QWORD *)this + 7) + 320LL));
    SendMessageW(**((HWND **)this + 9), 0x102Au, v7, 0);
    v8 = *((_QWORD *)this + 11);
    if ( a3 == v8 )
    {
      v9 = &WindowName;
      if ( *(_QWORD *)(v8 + 24) )
        v9 = *(const OLECHAR **)(v8 + 24);
      DlgItem = GetDlgItem(*((HWND *)this + 1), 4007);
      ScSetDescriptionUIText(v26, DlgItem, v9);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v26) )
        mmcerror::SC::TraceAndClear((mmcerror::SC *)v26);
      mmcerror::SC::~SC((mmcerror::SC *)v26);
    }
  }
  v11 = *((_QWORD *)this + 11);
  if ( v11 && (*(_BYTE *)(v11 + 152) & 1) != 0 && !*(_DWORD *)(v11 + 4) )
  {
LABEL_33:
    v23 = *((_QWORD *)this + 7);
    v24 = *((_QWORD *)this + 1);
    if ( (unsigned int)CAboutInfoThread::StartThread((CAboutInfoThread *)(v23 + 424)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 112));
      if ( !PostThreadMessageW(*(_DWORD *)(v23 + 440), 0x464u, v11, v24) )
        CSnapinInfo::Release((CSnapinInfo *)v11);
    }
  }
  else
  {
    v12 = SendMessageW(**((HWND **)this + 9), 0x1027u, 0, 0);
    v13 = SendMessageW(**((HWND **)this + 9), 0x1004u, 0, 0);
    v14 = SendMessageW(**((HWND **)this + 9), 0x1028u, 0, 0);
    v15 = (HWND)**((_QWORD **)this + 9);
    if ( v13 >= v14 + v12 )
      v16 = v12 + SendMessageW(v15, 0x1028u, 0, 0);
    else
      v16 = SendMessageW(v15, 0x1004u, 0, 0);
    for ( i = 0; ; ++i )
    {
      v18 = (HWND *)*((_QWORD *)this + 9);
      if ( (int)i >= v16 )
        break;
      ItemData = WTL::CListViewCtrlT<ATL::CWindow>::GetItemData(v18, i);
      v11 = ItemData;
      if ( ItemData )
      {
        if ( (*(_BYTE *)(ItemData + 152) & 1) != 0 && !*(_DWORD *)(ItemData + 4) )
          goto LABEL_33;
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids, i);
      }
    }
    v20 = SendMessageW(*v18, 0x1004u, 0, 0);
    while ( 1 )
    {
      v21 = (unsigned int)(*((_DWORD *)this + 24) + 1);
      *((_DWORD *)this + 24) = v21;
      if ( (int)v21 >= v20 )
        break;
      v22 = WTL::CListViewCtrlT<ATL::CWindow>::GetItemData(*((_QWORD *)this + 9), v21);
      v11 = v22;
      if ( v22 )
      {
        if ( (*(_BYTE *)(v22 + 152) & 1) != 0 && !*(_DWORD *)(v22 + 4) )
          goto LABEL_33;
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          42,
          WPP_ee98353176bb36a24e89b23920f5a524_Traceguids,
          *((unsigned int *)this + 24));
      }
    }
  }
  *a5 = 1;
  return 0;
}

```

## disassembly

```asm
0x180079450  push    rbx
0x180079452  push    rbp
0x180079453  push    rsi
0x180079454  push    rdi
0x180079455  push    r12
0x180079457  sub     rsp, 60h
0x18007945b  mov     rsi, r8
0x18007945e  mov     rdi, rcx
0x180079461  test    r8, r8
0x180079464  jz      loc_180079554
0x18007946a  cmp     dword ptr [r8+4Ch], 80004002h
0x180079472  jnz     short loc_180079484
0x180079474  or      byte ptr [r8+98h], 1
0x18007947c  mov     rcx, r8; this
0x18007947f  call    ?LoadAboutInfo@CSnapinInfo@@QEAAHXZ; CSnapinInfo::LoadAboutInfo(void)
0x180079484  mov     qword ptr [rsp+88h+lParam+4], 0
0x18007948d  mov     [rsp+88h+var_44], 0
0x180079495  xorps   xmm0, xmm0
0x180079498  movdqu  [rsp+88h+var_38], xmm0
0x18007949e  mov     dword ptr [rsp+88h+lParam], 1
0x1800794a6  mov     [rsp+88h+var_40], rsi
0x1800794ab  mov     rcx, [rdi+48h]
0x1800794af  lea     r9, [rsp+88h+lParam]; lParam
0x1800794b4  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800794b8  mov     edx, 1053h; Msg
0x1800794bd  mov     rcx, [rcx]; hWnd
0x1800794c0  call    cs:__imp_SendMessageW
0x1800794c6  mov     rbx, rax
0x1800794c9  mov     rdx, [rdi+38h]
0x1800794cd  mov     rdx, [rdx+140h]
0x1800794d4  mov     rcx, rsi
0x1800794d7  call    ?LoadImages@CSnapinInfo@@QEAAXVCImageList@WTL@@@Z; CSnapinInfo::LoadImages(WTL::CImageList)
0x1800794dc  movsxd  r8, ebx; wParam
0x1800794df  mov     rcx, [rdi+48h]
0x1800794e3  xor     r9d, r9d; lParam
0x1800794e6  mov     edx, 102Ah; Msg
0x1800794eb  mov     rcx, [rcx]; hWnd
0x1800794ee  call    cs:__imp_SendMessageW
0x1800794f4  mov     rax, [rdi+58h]
0x1800794f8  cmp     rsi, rax
0x1800794fb  jnz     short loc_180079554
0x1800794fd  lea     rbx, WindowName
0x180079504  cmp     qword ptr [rax+18h], 0
0x180079509  cmovnz  rbx, [rax+18h]
0x18007950e  mov     edx, 0FA7h; nIDDlgItem
0x180079513  mov     rcx, [rdi+8]; hDlg
0x180079517  call    cs:__imp_GetDlgItem
0x18007951d  mov     rdx, rax
0x180079520  mov     r8, rbx
0x180079523  lea     rcx, [rsp+88h+var_68]
0x180079528  call    ?ScSetDescriptionUIText@@YA?AVSC@mmcerror@@PEAUHWND__@@PEBG@Z; ScSetDescriptionUIText(HWND__ *,ushort const *)
0x18007952d  nop
0x18007952e  lea     rcx, [rsp+88h+var_68]
0x180079533  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180079539  test    al, al
0x18007953b  jz      short loc_180079549
0x18007953d  lea     rcx, [rsp+88h+var_68]
0x180079542  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x180079548  nop
0x180079549  lea     rcx, [rsp+88h+var_68]
0x18007954e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180079554  mov     rbx, [rdi+58h]
0x180079558  test    rbx, rbx
0x18007955b  jz      short loc_180079570
0x18007955d  test    byte ptr [rbx+98h], 1
0x180079564  jz      short loc_180079570
0x180079566  cmp     dword ptr [rbx+4], 0
0x18007956a  jz      loc_1800796BC
0x180079570  mov     rcx, [rdi+48h]
0x180079574  xor     r9d, r9d; lParam
0x180079577  xor     r8d, r8d; wParam
0x18007957a  mov     edx, 1027h; Msg
0x18007957f  mov     rcx, [rcx]; hWnd
0x180079582  call    cs:__imp_SendMessageW
0x180079588  mov     rsi, rax
0x18007958b  mov     rcx, [rdi+48h]
0x18007958f  xor     r9d, r9d; lParam
0x180079592  xor     r8d, r8d; wParam
0x180079595  mov     edx, 1004h; Msg
0x18007959a  mov     rcx, [rcx]; hWnd
0x18007959d  call    cs:__imp_SendMessageW
0x1800795a3  mov     rbx, rax
0x1800795a6  mov     rcx, [rdi+48h]
0x1800795aa  xor     r9d, r9d; lParam
0x1800795ad  xor     r8d, r8d; wParam
0x1800795b0  mov     ebp, 1028h
0x1800795b5  mov     edx, ebp; Msg
0x1800795b7  mov     rcx, [rcx]; hWnd
0x1800795ba  call    cs:__imp_SendMessageW
0x1800795c0  lea     edx, [rax+rsi]
0x1800795c3  mov     rcx, [rdi+48h]
0x1800795c7  mov     rcx, [rcx]; hWnd
0x1800795ca  xor     r9d, r9d; lParam
0x1800795cd  xor     r8d, r8d; wParam
0x1800795d0  cmp     ebx, edx
0x1800795d2  jge     short loc_1800795E2
0x1800795d4  lea     edx, [rbp-24h]; Msg
0x1800795d7  call    cs:__imp_SendMessageW
0x1800795dd  mov     rbp, rax
0x1800795e0  jmp     short loc_1800795ED
0x1800795e2  mov     edx, ebp; Msg
0x1800795e4  call    cs:__imp_SendMessageW
0x1800795ea  lea     ebp, [rsi+rax]
0x1800795ed  xor     esi, esi
0x1800795ef  lea     r12, WPP_GLOBAL_Control
0x1800795f6  mov     rcx, [rdi+48h]
0x1800795fa  cmp     esi, ebp
0x1800795fc  jge     short loc_18007964A
0x1800795fe  mov     edx, esi
0x180079600  call    ?GetItemData@?$CListViewCtrlT@VCWindow@ATL@@@WTL@@QEBA_KH@Z; WTL::CListViewCtrlT<ATL::CWindow>::GetItemData(int)
0x180079605  mov     rbx, rax
0x180079608  test    rax, rax
0x18007960b  jnz     short loc_180079637
0x18007960d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079614  cmp     rcx, r12
0x180079617  jz      short loc_180079646
0x180079619  cmp     byte ptr [rcx+19h], 2
0x18007961d  jb      short loc_180079646
0x18007961f  lea     edx, [rax+29h]
0x180079622  mov     r9d, esi
0x180079625  lea     r8, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids
0x18007962c  mov     rcx, [rcx+10h]
0x180079630  call    WPP_SF_d
0x180079635  jmp     short loc_180079646
0x180079637  test    byte ptr [rax+98h], 1
0x18007963e  jz      short loc_180079646
0x180079640  cmp     dword ptr [rax+4], 0
0x180079644  jz      short loc_1800796BC
0x180079646  inc     esi
0x180079648  jmp     short loc_1800795F6
0x18007964a  xor     r9d, r9d; lParam
0x18007964d  xor     r8d, r8d; wParam
0x180079650  mov     edx, 1004h; Msg
0x180079655  mov     rcx, [rcx]; hWnd
0x180079658  call    cs:__imp_SendMessageW
0x18007965e  mov     rsi, rax
0x180079661  mov     edx, [rdi+60h]
0x180079664  inc     edx
0x180079666  mov     [rdi+60h], edx
0x180079669  cmp     edx, esi
0x18007966b  jge     loc_1800796FB
0x180079671  mov     rcx, [rdi+48h]
0x180079675  call    ?GetItemData@?$CListViewCtrlT@VCWindow@ATL@@@WTL@@QEBA_KH@Z; WTL::CListViewCtrlT<ATL::CWindow>::GetItemData(int)
0x18007967a  mov     rbx, rax
0x18007967d  test    rax, rax
0x180079680  jnz     short loc_1800796AD
0x180079682  mov     rcx, cs:WPP_GLOBAL_Control
0x180079689  cmp     rcx, r12
0x18007968c  jz      short loc_180079661
0x18007968e  cmp     byte ptr [rcx+19h], 2
0x180079692  jb      short loc_180079661
0x180079694  lea     edx, [rax+2Ah]
0x180079697  mov     r9d, [rdi+60h]
0x18007969b  lea     r8, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids
0x1800796a2  mov     rcx, [rcx+10h]
0x1800796a6  call    WPP_SF_d
0x1800796ab  jmp     short loc_180079661
0x1800796ad  test    byte ptr [rax+98h], 1
0x1800796b4  jz      short loc_180079661
0x1800796b6  cmp     dword ptr [rax+4], 0
0x1800796ba  jnz     short loc_180079661
0x1800796bc  mov     rsi, [rdi+38h]
0x1800796c0  mov     rdi, [rdi+8]
0x1800796c4  lea     rcx, [rsi+1A8h]; this
0x1800796cb  call    ?StartThread@CAboutInfoThread@@QEAAHXZ; CAboutInfoThread::StartThread(void)
0x1800796d0  test    eax, eax
0x1800796d2  jz      short loc_1800796FB
0x1800796d4  lock inc dword ptr [rbx+70h]
0x1800796d8  mov     r9, rdi; lParam
0x1800796db  mov     r8, rbx; wParam
0x1800796de  mov     edx, 464h; Msg
0x1800796e3  mov     ecx, [rsi+1B8h]; idThread
0x1800796e9  call    cs:__imp_PostThreadMessageW
0x1800796ef  test    eax, eax
0x1800796f1  jnz     short loc_1800796FB
0x1800796f3  mov     rcx, rbx; this
0x1800796f6  call    ?Release@CSnapinInfo@@QEAAKXZ; CSnapinInfo::Release(void)
0x1800796fb  mov     rax, [rsp+88h+arg_20]
0x180079703  mov     dword ptr [rax], 1
0x180079709  xor     eax, eax
0x18007970b  add     rsp, 60h
0x18007970f  pop     r12
0x180079711  pop     rdi
0x180079712  pop     rsi
0x180079713  pop     rbp
0x180079714  pop     rbx
0x180079715  retn
```
