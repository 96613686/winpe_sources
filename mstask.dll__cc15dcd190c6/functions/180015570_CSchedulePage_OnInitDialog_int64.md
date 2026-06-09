# CSchedulePage::_OnInitDialog(__int64)

- ea: `0x180015570`
- end: `0x18001587a`
- name: `?_OnInitDialog@CSchedulePage@@EEAA_J_J@Z`
- size: `778`
- prototype: `__int64 __fastcall(CSchedulePage *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ef8`
- `0x180010b5c`
- `0x180010c38`
- `0x1800132b4`
- `0x1800135a4`
- `0x18001388c`
- `0x180013fd8`
- `0x1800144ac`
- `0x180015570`
- `0x180015db8`
- `0x180017df4`
- `0x18001a238`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157a7`
- `USER32!SendMessageW` at `0x18001571b`
- `USER32!SendMessageW` at `0x18001571b`
- `USER32!EnableWindow` at `0x18001584d`
- `USER32!EnableWindow` at `0x18001584d`
- `USER32!GetParent` at `0x180015704`
- `USER32!GetParent` at `0x180015704`
- `USER32!GetDlgItem` at `0x1800155aa`
- `USER32!GetDlgItem` at `0x1800155c6`
- `USER32!GetDlgItem` at `0x180015608`
- `USER32!GetDlgItem` at `0x18001564a`
- `USER32!GetDlgItem` at `0x18001568c`
- `USER32!GetDlgItem` at `0x1800155aa`
- `USER32!GetDlgItem` at `0x1800155c6`
- `USER32!GetDlgItem` at `0x180015608`
- `USER32!GetDlgItem` at `0x18001564a`
- `USER32!GetDlgItem` at `0x18001568c`
- `USER32!GetWindowRect` at `0x1800155b7`
- `USER32!GetWindowRect` at `0x1800155d3`
- `USER32!GetWindowRect` at `0x180015615`
- `USER32!GetWindowRect` at `0x180015657`
- `USER32!GetWindowRect` at `0x180015699`
- `USER32!GetWindowRect` at `0x1800155b7`
- `USER32!GetWindowRect` at `0x1800155d3`
- `USER32!GetWindowRect` at `0x180015615`
- `USER32!GetWindowRect` at `0x180015657`
- `USER32!GetWindowRect` at `0x180015699`

## pseudocode

```c
__int64 __fastcall CSchedulePage::_OnInitDialog(CSchedulePage *this)
{
  HWND v2; // rcx
  HWND DlgItem; // rax
  HWND v4; // rax
  int v5; // r9d
  HWND v6; // rax
  int v7; // r9d
  HWND v8; // rax
  int v9; // r9d
  HWND v10; // rax
  int v11; // r9d
  unsigned int v12; // edx
  __int64 v13; // rcx
  HWND v14; // rcx
  HWND Parent; // rax
  _DWORD *v16; // rax
  struct _IMAGELIST **v17; // rax
  struct _IMAGELIST **v18; // rdi
  __int64 v19; // rcx
  int Triggers; // edi
  int v21; // edx
  UINT v22; // edx
  int v23; // r8d
  int v25; // [rsp+20h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-38h] BYREF
  struct tagRECT v27; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-20h] BYREF

  v2 = (HWND)*((_QWORD *)this + 14);
  Rect = 0;
  v27 = 0;
  DlgItem = GetDlgItem(v2, 1701);
  GetWindowRect(DlgItem, &Rect);
  v4 = GetDlgItem(*((HWND *)this + 14), 1711);
  GetWindowRect(v4, &v27);
  v5 = Rect.left - v27.left;
  if ( Rect.left - v27.left < 0 )
    v5 = v27.left - Rect.left;
  MoveControlGroup(*((HWND *)this + 14), &aCtrlsWeekly, 0xCu, v5);
  v6 = GetDlgItem(*((HWND *)this + 14), 1731);
  GetWindowRect(v6, &v27);
  v7 = Rect.left - v27.left;
  if ( Rect.left - v27.left < 0 )
    v7 = v27.left - Rect.left;
  MoveControlGroup(*((HWND *)this + 14), &aCtrlsMonthly, 0xAu, v7);
  v8 = GetDlgItem(*((HWND *)this + 14), 1761);
  GetWindowRect(v8, &v27);
  v9 = Rect.left - v27.left;
  if ( Rect.left - v27.left < 0 )
    v9 = v27.left - Rect.left;
  MoveControlGroup(*((HWND *)this + 14), &aCtrlsOnce, 3u, v9);
  v10 = GetDlgItem(*((HWND *)this + 14), 1764);
  GetWindowRect(v10, &v27);
  v11 = Rect.left - v27.left;
  if ( Rect.left - v27.left < 0 )
    v11 = v27.left - Rect.left;
  MoveControlGroup(*((HWND *)this + 14), &aCtrlsIdle, 5u, v11);
  UpdateTimeFormat((unsigned __int16 *)this + 386, v12);
  v13 = *((_QWORD *)this + 83);
  v25 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 232LL))(v13, &v25);
  v14 = (HWND)*((_QWORD *)this + 14);
  *((_DWORD *)this + 192) = v25 & 0x200000;
  Parent = GetParent(v14);
  v16 = (_DWORD *)SendMessageW(Parent, 0x46Cu, 0x1CAEu, 0);
  *((_QWORD *)this + 84) = v16;
  if ( v16 )
  {
    ++*v16;
  }
  else
  {
    v17 = (struct _IMAGELIST **)operator new(0x30u);
    v18 = v17;
    if ( !v17 )
    {
      *((_QWORD *)this + 84) = 0;
      Triggers = -2147024882;
      goto LABEL_19;
    }
    *(_DWORD *)v17 = 1;
    CJobIcon::CJobIcon(v17 + 1);
    v18[4] = 0;
    v18[5] = 0;
    v19 = *((_QWORD *)this + 83);
    *((_QWORD *)this + 84) = v18;
    pv = 0;
    Triggers = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v19 + 264LL))(v19, &pv);
    if ( Triggers < 0 )
      goto LABEL_19;
    CIconHelper::SetAppIcon(*((CIconHelper **)this + 84), (unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    v21 = 0;
    if ( *((_DWORD *)this + 33) )
      v21 = ((unsigned __int8)~(_BYTE)v25 >> 2) & 1;
    CIconHelper::SetJobIcon(*((CIconHelper **)this + 84), v21);
  }
  Triggers = CSchedulePage::_LoadTriggers(this);
  if ( Triggers >= 0 )
  {
    CSchedulePage::_InitPage(this);
    CSchedulePage::_RefreshPage(this);
    *((_DWORD *)this + 30) = 0;
  }
LABEL_19:
  if ( *((_DWORD *)this + 192) )
    CSchedulePage::_DisableUI(this);
  if ( Triggers >= 0 )
    return 1;
  v22 = 4135;
  v23 = Triggers;
  if ( Triggers == -2147024882 )
    v23 = 0;
  else
    v22 = 4137;
  SchedUIErrorDialog(*((HWND *)this + 14), v22, v23, 0);
  EnableWindow(*((HWND *)this + 14), 0);
  return 0;
}

```

## disassembly

```asm
0x180015570  mov     [rsp-8+arg_8], rbx
0x180015575  mov     [rsp-8+arg_10], rdi
0x18001557a  push    rbp
0x18001557b  mov     rbp, rsp
0x18001557e  sub     rsp, 60h
0x180015582  mov     rax, cs:__security_cookie
0x180015589  xor     rax, rsp
0x18001558c  mov     [rbp+var_10], rax
0x180015590  mov     rbx, rcx
0x180015593  xorps   xmm0, xmm0
0x180015596  mov     rcx, [rcx+70h]; hDlg
0x18001559a  xorps   xmm1, xmm1
0x18001559d  mov     edx, 6A5h; nIDDlgItem
0x1800155a2  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800155a6  movups  xmmword ptr [rbp+var_30.left], xmm1
0x1800155aa  call    cs:__imp_GetDlgItem
0x1800155b0  mov     rcx, rax; hWnd
0x1800155b3  lea     rdx, [rbp+Rect]; lpRect
0x1800155b7  call    cs:__imp_GetWindowRect
0x1800155bd  mov     rcx, [rbx+70h]; hDlg
0x1800155c1  mov     edx, 6AFh; nIDDlgItem
0x1800155c6  call    cs:__imp_GetDlgItem
0x1800155cc  mov     rcx, rax; hWnd
0x1800155cf  lea     rdx, [rbp+var_30]; lpRect
0x1800155d3  call    cs:__imp_GetWindowRect
0x1800155d9  mov     eax, [rbp+var_30.left]
0x1800155dc  lea     rdx, ?aCtrlsWeekly@@3PAHA; int *
0x1800155e3  sub     eax, [rbp+Rect.left]
0x1800155e6  mov     r8d, 0Ch; unsigned int
0x1800155ec  mov     rcx, [rbx+70h]; hWndTo
0x1800155f0  mov     r9d, eax
0x1800155f3  neg     r9d
0x1800155f6  cmovs   r9d, eax; int
0x1800155fa  call    ?MoveControlGroup@@YAXPEAUHWND__@@QEAHKJ@Z; MoveControlGroup(HWND__ *,int * const,ulong,long)
0x1800155ff  mov     rcx, [rbx+70h]; hDlg
0x180015603  mov     edx, 6C3h; nIDDlgItem
0x180015608  call    cs:__imp_GetDlgItem
0x18001560e  mov     rcx, rax; hWnd
0x180015611  lea     rdx, [rbp+var_30]; lpRect
0x180015615  call    cs:__imp_GetWindowRect
0x18001561b  mov     eax, [rbp+var_30.left]
0x18001561e  lea     rdx, ?aCtrlsMonthly@@3PAHA; int *
0x180015625  sub     eax, [rbp+Rect.left]
0x180015628  mov     r8d, 0Ah; unsigned int
0x18001562e  mov     rcx, [rbx+70h]; hWndTo
0x180015632  mov     r9d, eax
0x180015635  neg     r9d
0x180015638  cmovs   r9d, eax; int
0x18001563c  call    ?MoveControlGroup@@YAXPEAUHWND__@@QEAHKJ@Z; MoveControlGroup(HWND__ *,int * const,ulong,long)
0x180015641  mov     rcx, [rbx+70h]; hDlg
0x180015645  mov     edx, 6E1h; nIDDlgItem
0x18001564a  call    cs:__imp_GetDlgItem
0x180015650  mov     rcx, rax; hWnd
0x180015653  lea     rdx, [rbp+var_30]; lpRect
0x180015657  call    cs:__imp_GetWindowRect
0x18001565d  mov     eax, [rbp+var_30.left]
0x180015660  lea     rdx, ?aCtrlsOnce@@3PAHA; int *
0x180015667  sub     eax, [rbp+Rect.left]
0x18001566a  mov     r8d, 3; unsigned int
0x180015670  mov     rcx, [rbx+70h]; hWndTo
0x180015674  mov     r9d, eax
0x180015677  neg     r9d
0x18001567a  cmovs   r9d, eax; int
0x18001567e  call    ?MoveControlGroup@@YAXPEAUHWND__@@QEAHKJ@Z; MoveControlGroup(HWND__ *,int * const,ulong,long)
0x180015683  mov     rcx, [rbx+70h]; hDlg
0x180015687  mov     edx, 6E4h; nIDDlgItem
0x18001568c  call    cs:__imp_GetDlgItem
0x180015692  mov     rcx, rax; hWnd
0x180015695  lea     rdx, [rbp+var_30]; lpRect
0x180015699  call    cs:__imp_GetWindowRect
0x18001569f  mov     eax, [rbp+var_30.left]
0x1800156a2  lea     rdx, ?aCtrlsIdle@@3PAHA; int *
0x1800156a9  sub     eax, [rbp+Rect.left]
0x1800156ac  mov     r8d, 5; unsigned int
0x1800156b2  mov     rcx, [rbx+70h]; hWndTo
0x1800156b6  mov     r9d, eax
0x1800156b9  neg     r9d
0x1800156bc  cmovs   r9d, eax; int
0x1800156c0  call    ?MoveControlGroup@@YAXPEAUHWND__@@QEAHKJ@Z; MoveControlGroup(HWND__ *,int * const,ulong,long)
0x1800156c5  lea     rcx, [rbx+304h]; unsigned __int16 *
0x1800156cc  call    ?UpdateTimeFormat@@YAXPEAGK@Z; UpdateTimeFormat(ushort *,ulong)
0x1800156d1  mov     rcx, [rbx+298h]
0x1800156d8  lea     rdx, [rbp+var_40]
0x1800156dc  mov     [rbp+var_40], 0
0x1800156e3  mov     rax, [rcx]
0x1800156e6  mov     rax, [rax+0E8h]
0x1800156ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156f2  mov     eax, [rbp+var_40]
0x1800156f5  and     eax, 200000h
0x1800156fa  mov     rcx, [rbx+70h]; hWnd
0x1800156fe  mov     [rbx+300h], eax
0x180015704  call    cs:__imp_GetParent
0x18001570a  xor     r9d, r9d; lParam
0x18001570d  mov     edx, 46Ch; Msg
0x180015712  mov     rcx, rax; hWnd
0x180015715  mov     r8d, 1CAEh; wParam
0x18001571b  call    cs:__imp_SendMessageW
0x180015721  mov     [rbx+2A0h], rax
0x180015728  test    rax, rax
0x18001572b  jnz     loc_1800157E5
0x180015731  lea     ecx, [rax+30h]; Size
0x180015734  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015739  mov     rdi, rax
0x18001573c  test    rax, rax
0x18001573f  jz      loc_1800157D3
0x180015745  lea     rcx, [rax+8]; this
0x180015749  mov     dword ptr [rax], 1
0x18001574f  call    ??0CJobIcon@@QEAA@XZ; CJobIcon::CJobIcon(void)
0x180015754  mov     qword ptr [rdi+20h], 0
0x18001575c  lea     rdx, [rbp+pv]
0x180015760  mov     qword ptr [rdi+28h], 0
0x180015768  mov     rcx, [rbx+298h]
0x18001576f  mov     [rbx+2A0h], rdi
0x180015776  mov     [rbp+pv], 0
0x18001577e  mov     rax, [rcx]
0x180015781  mov     rax, [rax+108h]
0x180015788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001578d  mov     edi, eax
0x18001578f  test    eax, eax
0x180015791  js      short loc_18001580C
0x180015793  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180015797  mov     rcx, [rbx+2A0h]; this
0x18001579e  call    ?SetAppIcon@CIconHelper@@QEAAXPEAG@Z; CIconHelper::SetAppIcon(ushort *)
0x1800157a3  mov     rcx, [rbp+pv]; pv
0x1800157a7  call    cs:__imp_CoTaskMemFree
0x1800157ad  xor     edx, edx
0x1800157af  cmp     [rbx+84h], edx
0x1800157b5  jz      short loc_1800157C5
0x1800157b7  mov     al, byte ptr [rbp+var_40]
0x1800157ba  not     al
0x1800157bc  movzx   edx, al
0x1800157bf  shr     edx, 2
0x1800157c2  and     edx, 1; int
0x1800157c5  mov     rcx, [rbx+2A0h]; this
0x1800157cc  call    ?SetJobIcon@CIconHelper@@QEAAXH@Z; CIconHelper::SetJobIcon(int)
0x1800157d1  jmp     short loc_1800157E7
0x1800157d3  mov     qword ptr [rbx+2A0h], 0
0x1800157de  mov     edi, 8007000Eh
0x1800157e3  jmp     short loc_18001580C
0x1800157e5  inc     dword ptr [rax]
0x1800157e7  mov     rcx, rbx; this
0x1800157ea  call    ?_LoadTriggers@CSchedulePage@@AEAAJXZ; CSchedulePage::_LoadTriggers(void)
0x1800157ef  mov     edi, eax
0x1800157f1  test    eax, eax
0x1800157f3  js      short loc_18001580C
0x1800157f5  mov     rcx, rbx; this
0x1800157f8  call    ?_InitPage@CSchedulePage@@AEAAHXZ; CSchedulePage::_InitPage(void)
0x1800157fd  mov     rcx, rbx; this
0x180015800  call    ?_RefreshPage@CSchedulePage@@AEAAHXZ; CSchedulePage::_RefreshPage(void)
0x180015805  mov     dword ptr [rbx+78h], 0
0x18001580c  cmp     dword ptr [rbx+300h], 0
0x180015813  jz      short loc_18001581D
0x180015815  mov     rcx, rbx; this
0x180015818  call    ?_DisableUI@CSchedulePage@@AEAAXXZ; CSchedulePage::_DisableUI(void)
0x18001581d  test    edi, edi
0x18001581f  jns     short loc_180015857
0x180015821  mov     rcx, [rbx+70h]; hWnd
0x180015825  xor     eax, eax
0x180015827  mov     edx, 1027h
0x18001582c  cmp     edi, 8007000Eh
0x180015832  mov     r8d, edi
0x180015835  cmovz   r8d, eax; int
0x180015839  lea     eax, [rdx+2]
0x18001583c  cmovnz  edx, eax; uID
0x18001583f  xor     r9d, r9d; UINT
0x180015842  call    ?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z; SchedUIErrorDialog(HWND__ *,int,long,uint)
0x180015847  mov     rcx, [rbx+70h]; hWnd
0x18001584b  xor     edx, edx; bEnable
0x18001584d  call    cs:__imp_EnableWindow
0x180015853  xor     eax, eax
0x180015855  jmp     short loc_18001585C
0x180015857  mov     eax, 1
0x18001585c  mov     rcx, [rbp+var_10]
0x180015860  xor     rcx, rsp; StackCookie
0x180015863  call    __security_check_cookie
0x180015868  lea     r11, [rsp+60h+var_s0]
0x18001586d  mov     rbx, [r11+18h]
0x180015871  mov     rdi, [r11+20h]
0x180015875  mov     rsp, r11
0x180015878  pop     rbp
0x180015879  retn
```
