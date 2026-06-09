# ListViewPage::OnSetActive(void)

- ea: `0x140030410`
- end: `0x1400309d3`
- name: `?OnSetActive@ListViewPage@@MEAA_JXZ`
- size: `1475`
- prototype: `__int64 __fastcall(ListViewPage *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400039b1`
- `0x14000e6bc`
- `0x14000e72c`
- `0x140020420`
- `0x14002ad30`
- `0x14002fc60`
- `0x140030410`
- `0x140041e30`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140030895`
- `KERNEL32!GetLastError` at `0x1400308b5`
- `KERNEL32!GetLastError` at `0x140030895`
- `KERNEL32!GetLastError` at `0x1400308b5`
- `USER32!GetWindowLongPtrW` at `0x140030624`
- `USER32!GetWindowLongPtrW` at `0x14003094b`
- `USER32!GetWindowLongPtrW` at `0x140030624`
- `USER32!GetWindowLongPtrW` at `0x14003094b`
- `USER32!SetWindowLongPtrW` at `0x14003063d`
- `USER32!SetWindowLongPtrW` at `0x140030963`
- `USER32!SetWindowLongPtrW` at `0x14003063d`
- `USER32!SetWindowLongPtrW` at `0x140030963`
- `USER32!LoadImageW` at `0x140030793`
- `USER32!LoadImageW` at `0x140030793`
- `USER32!GetWindowLongW` at `0x14003055c`
- `USER32!GetWindowLongW` at `0x14003055c`
- `USER32!GetSystemMetrics` at `0x1400305ad`
- `USER32!GetSystemMetrics` at `0x1400306d2`
- `USER32!GetSystemMetrics` at `0x1400306e5`
- `USER32!GetSystemMetrics` at `0x140030756`
- `USER32!GetSystemMetrics` at `0x140030769`
- `USER32!GetSystemMetrics` at `0x1400305ad`
- `USER32!GetSystemMetrics` at `0x1400306d2`
- `USER32!GetSystemMetrics` at `0x1400306e5`
- `USER32!GetSystemMetrics` at `0x140030756`
- `USER32!GetSystemMetrics` at `0x140030769`
- `USER32!GetClientRect` at `0x140030592`
- `USER32!GetClientRect` at `0x140030592`
- `USER32!SendMessageW` at `0x1400305d0`
- `USER32!SendMessageW` at `0x1400305ed`
- `USER32!SendMessageW` at `0x14003060e`
- `USER32!SendMessageW` at `0x140030657`
- `USER32!SendMessageW` at `0x140030731`
- `USER32!SendMessageW` at `0x1400307fb`
- `USER32!SendMessageW` at `0x14003087b`
- `USER32!SendMessageW` at `0x140030921`
- `USER32!SendMessageW` at `0x1400305d0`
- `USER32!SendMessageW` at `0x1400305ed`
- `USER32!SendMessageW` at `0x14003060e`
- `USER32!SendMessageW` at `0x140030657`
- `USER32!SendMessageW` at `0x140030731`
- `USER32!SendMessageW` at `0x1400307fb`
- `USER32!SendMessageW` at `0x14003087b`
- `USER32!SendMessageW` at `0x140030921`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400307ba`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400307d5`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400307ba`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400307d5`
- `COMCTL32!ImageList_Destroy` at `0x140030745`
- `COMCTL32!ImageList_Destroy` at `0x140030745`
- `COMCTL32!ImageList_Create` at `0x140030702`
- `COMCTL32!ImageList_Create` at `0x140030702`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x1400308f1`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x1400308f1`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003099f`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003099f`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140030487`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140030487`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400304a5`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1400304a5`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140030985`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140030985`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ListViewPage::OnSetActive(ListViewPage *this)
{
  __int64 v2; // rbx
  int NamedElement; // eax
  LPARAM v4; // rbx
  signed int NamedHandle; // eax
  int v6; // r9d
  HWND v7; // r14
  UINT v8; // r15d
  LONG_PTR WindowLongPtrW; // rax
  unsigned int v10; // r13d
  struct _IMAGELIST *v11; // rbx
  struct InteractivityChoice *v12; // r12
  const unsigned __int16 *v13; // rcx
  int SystemMetrics; // ebx
  int v15; // eax
  HIMAGELIST v16; // rcx
  struct _IMAGELIST *v17; // rax
  int v18; // ebx
  int v19; // eax
  HICON ImageW; // r8
  LONG_PTR v21; // rax
  int v23; // [rsp+30h] [rbp-D0h]
  struct _IMAGELIST *himl; // [rsp+38h] [rbp-C8h]
  HWND hWnd; // [rsp+40h] [rbp-C0h] BYREF
  struct InteractivityChoice *v26; // [rsp+48h] [rbp-B8h] BYREF
  HICON hicon; // [rsp+50h] [rbp-B0h] BYREF
  struct DirectUI::Element *v28; // [rsp+58h] [rbp-A8h] BYREF
  DirectUI::Element *Element; // [rsp+60h] [rbp-A0h]
  unsigned int v30; // [rsp+68h] [rbp-98h] BYREF
  LPARAM lParam[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  _DWORD v35[6]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+D4h] [rbp-2Ch]
  LPARAM v38; // [rsp+110h] [rbp+10h] BYREF
  int v39; // [rsp+11Ch] [rbp+1Ch]
  int v40; // [rsp+120h] [rbp+20h]
  struct tagRECT Rect; // [rsp+170h] [rbp+70h] BYREF

  v2 = -1;
  hWnd = 0;
  memset_0(v35, 0, 0x58u);
  v26 = 0;
  v28 = 0;
  hicon = 0;
  *(_OWORD *)lParam = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  Rect = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v30 = 0;
  DirectUI::Element::StartDefer(Element, &v30);
  NamedElement = WizardPage::GetNamedElement(this, L"lstView", &v28);
  if ( NamedElement < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ListViewPage::OnSetActive", 3232, NamedElement);
    goto LABEL_39;
  }
  v4 = (-(__int64)(*((_DWORD *)this + 46) != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 66596;
  NamedHandle = WizardPage::GetNamedHandle(this, L"lstView", &hWnd);
  if ( NamedHandle >= 0 )
  {
    v23 = 0;
    v7 = hWnd;
    v8 = (GetWindowLongW(hWnd, -20) & 0x400000 | 0x4200u) >> 9;
    if ( dword_14007F4A4 )
    {
      GetClientRect(v7, &Rect);
      LODWORD(lParam[0]) = 10;
      HIDWORD(v32) = 0;
      LODWORD(lParam[1]) = Rect.right - GetSystemMetrics(2);
      SendMessageW(v7, 0x108Eu, 1u, 0);
      SendMessageW(v7, 0x1061u, SHIDWORD(v32), (LPARAM)lParam);
      dword_14007F4A4 = 0;
    }
    SendMessageW(v7, 0x1036u, 0x10424u, v4);
    WindowLongPtrW = GetWindowLongPtrW(v7, -16);
    SetWindowLongPtrW(v7, -16, WindowLongPtrW | 0x4000);
    SendMessageW(v7, 0x1009u, 0, 0);
    *(_QWORD *)&v35[1] = 0;
    v10 = 0;
    v11 = 0;
    while ( 1 )
    {
      if ( v10 >= *((_DWORD *)this + 42) )
      {
        DirectUI::CCBase::SetNotifyHandler(
          v28,
          (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))ListViewPage::NotifyHandler,
          this);
        memset_0(&v38, 0, 0x58u);
        v40 = 1;
        v39 = 1;
        SendMessageW(v7, 0x102Bu, 0, (LPARAM)&v38);
        v2 = InteractivityPage::OnSetActive(this);
        if ( *((_DWORD *)this + 46) )
        {
          v21 = GetWindowLongPtrW(v7, -16);
          SetWindowLongPtrW(v7, -16, v21 | 4);
          if ( !v23 )
            DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, 0, 2);
        }
        goto LABEL_39;
      }
      v35[0] = 1;
      v37 = 0;
      NamedHandle = InteractivityPage::GetItem(this, v10, &v26);
      if ( NamedHandle < 0 )
      {
        v6 = 3281;
        goto LABEL_5;
      }
      v12 = v26;
      v13 = (const unsigned __int16 *)*((_QWORD *)v26 + 3);
      if ( v13 )
        NamedHandle = DwzLoadSmallIcon(v13, &hicon);
      if ( *((_QWORD *)v12 + 3) && NamedHandle >= 0 )
      {
        if ( !v11 )
        {
          SystemMetrics = GetSystemMetrics(50);
          v15 = GetSystemMetrics(49);
          v16 = ImageList_Create(v15, SystemMetrics, v8, 2, 1);
          himl = v16;
          if ( (unsigned __int64)v16 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
          {
            NamedHandle = GetLastError();
            if ( NamedHandle > 0 )
              NamedHandle = (unsigned __int16)NamedHandle | 0x80070000;
            v6 = 3304;
            goto LABEL_5;
          }
          v17 = (struct _IMAGELIST *)SendMessageW(v7, 0x1003u, 1u, (LPARAM)v16);
          if ( v17 )
            ImageList_Destroy(v17);
          v18 = GetSystemMetrics(50);
          v19 = GetSystemMetrics(49);
          ImageW = (HICON)LoadImageW(g_hInstance, (LPCWSTR)0x6D, 1u, v19, v18, 0);
          if ( (unsigned __int64)ImageW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
          {
            NamedHandle = GetLastError();
            if ( NamedHandle > 0 )
              NamedHandle = (unsigned __int16)NamedHandle | 0x80070000;
            v6 = 3325;
            goto LABEL_5;
          }
          v11 = himl;
          ImageList_ReplaceIcon(himl, -1, ImageW);
        }
        v35[0] |= 2u;
        v37 = ImageList_ReplaceIcon(v11, -1, hicon);
      }
      v36 = *(_QWORD *)v12;
      SendMessageW(v7, 0x104Du, 0, (LPARAM)v35);
      if ( !*((_DWORD *)this + 46) )
        break;
      if ( !v23 && *((_DWORD *)v12 + 10) )
      {
        v23 = 1;
        memset_0(&v38, 0, 0x58u);
        v40 = 2;
        v39 = 2;
LABEL_27:
        SendMessageW(v7, 0x102Bu, v10, (LPARAM)&v38);
      }
      ++v35[1];
      ++v10;
    }
    memset_0(&v38, 0, 0x58u);
    v40 = 61440;
    v39 = *((_DWORD *)v12 + 10) != 0 ? 0x2000 : 4096;
    goto LABEL_27;
  }
  v6 = 3242;
LABEL_5:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ListViewPage::OnSetActive", v6, NamedHandle);
  v2 = -1;
LABEL_39:
  if ( v30 )
    DirectUI::Element::EndDefer(Element, v30);
  return v2;
}

```

## disassembly

```asm
0x140030410  push    rbp
0x140030412  push    rbx
0x140030413  push    rsi
0x140030414  push    rdi
0x140030415  push    r12
0x140030417  push    r13
0x140030419  push    r14
0x14003041b  push    r15
0x14003041d  lea     rbp, [rsp-98h]
0x140030425  sub     rsp, 198h
0x14003042c  mov     rax, cs:__security_cookie
0x140030433  xor     rax, rsp
0x140030436  mov     [rbp+0D0h+var_50], rax
0x14003043d  mov     rsi, rcx
0x140030440  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140030444  xor     r12d, r12d
0x140030447  mov     [rsp+1D0h+hWnd], r12
0x14003044c  xor     edx, edx; Val
0x14003044e  lea     r8d, [rbx+59h]; Size
0x140030452  lea     rcx, [rbp+0D0h+var_120]; void *
0x140030456  call    memset_0
0x14003045b  mov     [rsp+1D0h+var_188], r12
0x140030460  mov     [rsp+1D0h+var_178], r12
0x140030465  mov     [rsp+1D0h+hicon], r12
0x14003046a  xorps   xmm0, xmm0
0x14003046d  xor     eax, eax
0x14003046f  movups  xmmword ptr [rsp+1D0h+lParam], xmm0
0x140030474  movups  [rbp+0D0h+var_150], xmm0
0x140030478  movups  [rbp+0D0h+var_140], xmm0
0x14003047c  mov     [rbp+0D0h+var_130], rax
0x140030480  movups  xmmword ptr [rbp+0D0h+Rect.left], xmm0
0x140030484  mov     rcx, rsi
0x140030487  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003048e  nop     dword ptr [rax+rax+00h]
0x140030493  mov     [rsp+1D0h+var_170], rax
0x140030498  mov     [rsp+1D0h+var_168], r12d
0x14003049d  lea     rdx, [rsp+1D0h+var_168]
0x1400304a2  mov     rcx, rax
0x1400304a5  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1400304ac  nop     dword ptr [rax+rax+00h]
0x1400304b1  nop
0x1400304b2  lea     r8, [rsp+1D0h+var_178]; struct DirectUI::Element **
0x1400304b7  lea     rdx, aLstview; "lstView"
0x1400304be  mov     rcx, rsi; this
0x1400304c1  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x1400304c6  test    eax, eax
0x1400304c8  jns     short loc_1400304EF
0x1400304ca  mov     [rsp+1D0h+cGrow], eax
0x1400304ce  mov     r9d, 0CA0h
0x1400304d4  lea     r8, aListviewpageOn_0; "ListViewPage::OnSetActive"
0x1400304db  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400304e2  lea     ecx, [rbx+2]; Level
0x1400304e5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400304ea  jmp     loc_140030992
0x1400304ef  mov     eax, [rsi+0B8h]
0x1400304f5  neg     eax
0x1400304f7  sbb     rbx, rbx
0x1400304fa  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400304fe  mov     r13d, 10424h
0x140030504  add     rbx, r13
0x140030507  lea     r8, [rsp+1D0h+hWnd]; HWND *
0x14003050c  lea     rdx, aLstview; "lstView"
0x140030513  mov     rcx, rsi; this
0x140030516  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14003051b  test    eax, eax
0x14003051d  jns     short loc_14003054A
0x14003051f  mov     r9d, 0CAAh
0x140030525  mov     ecx, 1; Level
0x14003052a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140030531  lea     r8, aListviewpageOn_0; "ListViewPage::OnSetActive"
0x140030538  mov     [rsp+1D0h+cGrow], eax
0x14003053c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140030541  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140030545  jmp     loc_140030992
0x14003054a  mov     [rsp+1D0h+var_1A0], r12d
0x14003054f  mov     edx, 0FFFFFFECh; nIndex
0x140030554  mov     r14, [rsp+1D0h+hWnd]
0x140030559  mov     rcx, r14; hWnd
0x14003055c  call    cs:__imp_GetWindowLongW
0x140030563  nop     dword ptr [rax+rax+00h]
0x140030568  mov     r15d, eax
0x14003056b  and     r15d, 400000h
0x140030572  or      r15d, 4200h
0x140030579  shr     r15d, 9
0x14003057d  mov     edi, 1
0x140030582  cmp     cs:dword_14007F4A4, r12d
0x140030589  jz      short loc_140030600
0x14003058b  lea     rdx, [rbp+0D0h+Rect]; lpRect
0x14003058f  mov     rcx, r14; hWnd
0x140030592  call    cs:__imp_GetClientRect
0x140030599  nop     dword ptr [rax+rax+00h]
0x14003059e  mov     dword ptr [rsp+1D0h+lParam], 0Ah
0x1400305a6  mov     dword ptr [rbp+0D0h+var_150+0Ch], r12d
0x1400305aa  lea     ecx, [rdi+1]; nIndex
0x1400305ad  call    cs:__imp_GetSystemMetrics
0x1400305b4  nop     dword ptr [rax+rax+00h]
0x1400305b9  mov     ecx, [rbp+0D0h+Rect.right]
0x1400305bc  sub     ecx, eax
0x1400305be  mov     dword ptr [rsp+1D0h+lParam+8], ecx
0x1400305c2  xor     r9d, r9d; lParam
0x1400305c5  mov     r8d, edi; wParam
0x1400305c8  mov     edx, 108Eh; Msg
0x1400305cd  mov     rcx, r14; hWnd
0x1400305d0  call    cs:__imp_SendMessageW
0x1400305d7  nop     dword ptr [rax+rax+00h]
0x1400305dc  movsxd  r8, dword ptr [rbp+0D0h+var_150+0Ch]; wParam
0x1400305e0  lea     r9, [rsp+1D0h+lParam]; lParam
0x1400305e5  mov     edx, 1061h; Msg
0x1400305ea  mov     rcx, r14; hWnd
0x1400305ed  call    cs:__imp_SendMessageW
0x1400305f4  nop     dword ptr [rax+rax+00h]
0x1400305f9  mov     cs:dword_14007F4A4, r12d
0x140030600  mov     r9, rbx; lParam
0x140030603  mov     r8, r13; wParam
0x140030606  mov     edx, 1036h; Msg
0x14003060b  mov     rcx, r14; hWnd
0x14003060e  call    cs:__imp_SendMessageW
0x140030615  nop     dword ptr [rax+rax+00h]
0x14003061a  mov     ebx, 0FFFFFFF0h
0x14003061f  mov     edx, ebx; nIndex
0x140030621  mov     rcx, r14; hWnd
0x140030624  call    cs:__imp_GetWindowLongPtrW
0x14003062b  nop     dword ptr [rax+rax+00h]
0x140030630  bts     rax, 0Eh
0x140030635  mov     r8, rax; dwNewLong
0x140030638  mov     edx, ebx; nIndex
0x14003063a  mov     rcx, r14; hWnd
0x14003063d  call    cs:__imp_SetWindowLongPtrW
0x140030644  nop     dword ptr [rax+rax+00h]
0x140030649  xor     r9d, r9d; lParam
0x14003064c  xor     r8d, r8d; wParam
0x14003064f  mov     edx, 1009h; Msg
0x140030654  mov     rcx, r14; hWnd
0x140030657  call    cs:__imp_SendMessageW
0x14003065e  nop     dword ptr [rax+rax+00h]
0x140030663  mov     qword ptr [rbp+0D0h+var_120+4], r12
0x140030667  mov     r13d, r12d
0x14003066a  mov     ebx, r13d
0x14003066d  cmp     r13d, [rsi+0A8h]
0x140030674  jnb     loc_1400308E2
0x14003067a  mov     [rbp+0D0h+var_120], edi
0x14003067d  mov     [rbp+0D0h+var_FC], r12d
0x140030681  lea     r8, [rsp+1D0h+var_188]; struct InteractivityChoice **
0x140030686  mov     edx, r13d; unsigned int
0x140030689  mov     rcx, rsi; this
0x14003068c  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x140030691  test    eax, eax
0x140030693  js      loc_1400308D5
0x140030699  mov     r12, [rsp+1D0h+var_188]
0x14003069e  mov     rcx, [r12+18h]; unsigned __int16 *
0x1400306a3  test    rcx, rcx
0x1400306a6  jz      short loc_1400306B2
0x1400306a8  lea     rdx, [rsp+1D0h+hicon]; HICON *
0x1400306ad  call    ?DwzLoadSmallIcon@@YAJPEBGPEAPEAUHICON__@@@Z; DwzLoadSmallIcon(ushort const *,HICON__ * *)
0x1400306b2  cmp     qword ptr [r12+18h], 0
0x1400306b8  jz      loc_1400307E4
0x1400306be  test    eax, eax
0x1400306c0  js      loc_1400307E4
0x1400306c6  test    rbx, rbx
0x1400306c9  jnz     loc_1400307C6
0x1400306cf  lea     ecx, [rbx+32h]; nIndex
0x1400306d2  call    cs:__imp_GetSystemMetrics
0x1400306d9  nop     dword ptr [rax+rax+00h]
0x1400306de  mov     ebx, eax
0x1400306e0  mov     ecx, 31h ; '1'; nIndex
0x1400306e5  call    cs:__imp_GetSystemMetrics
0x1400306ec  nop     dword ptr [rax+rax+00h]
0x1400306f1  mov     [rsp+1D0h+cGrow], edi; cGrow
0x1400306f5  mov     r9d, 2; cInitial
0x1400306fb  mov     r8d, r15d; flags
0x1400306fe  mov     edx, ebx; cy
0x140030700  mov     ecx, eax; cx
0x140030702  call    cs:__imp_ImageList_Create
0x140030709  nop     dword ptr [rax+rax+00h]
0x14003070e  mov     rcx, rax
0x140030711  mov     [rsp+1D0h+himl], rax
0x140030716  dec     rax
0x140030719  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003071d  ja      loc_1400308B5
0x140030723  mov     r9, rcx; lParam
0x140030726  mov     r8, rdi; wParam
0x140030729  mov     edx, 1003h; Msg
0x14003072e  mov     rcx, r14; hWnd
0x140030731  call    cs:__imp_SendMessageW
0x140030738  nop     dword ptr [rax+rax+00h]
0x14003073d  test    rax, rax
0x140030740  jz      short loc_140030751
0x140030742  mov     rcx, rax; himl
0x140030745  call    cs:__imp_ImageList_Destroy
0x14003074c  nop     dword ptr [rax+rax+00h]
0x140030751  mov     ecx, 32h ; '2'; nIndex
0x140030756  call    cs:__imp_GetSystemMetrics
0x14003075d  nop     dword ptr [rax+rax+00h]
0x140030762  mov     ebx, eax
0x140030764  mov     ecx, 31h ; '1'; nIndex
0x140030769  call    cs:__imp_GetSystemMetrics
0x140030770  nop     dword ptr [rax+rax+00h]
0x140030775  mov     [rsp+1D0h+fuLoad], 0; fuLoad
0x14003077d  mov     [rsp+1D0h+cGrow], ebx; cy
0x140030781  mov     r9d, eax; cx
0x140030784  mov     r8d, edi; type
0x140030787  mov     edx, 6Dh ; 'm'; name
0x14003078c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInst
0x140030793  call    cs:__imp_LoadImageW
0x14003079a  nop     dword ptr [rax+rax+00h]
0x14003079f  mov     r8, rax; hicon
0x1400307a2  dec     rax
0x1400307a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400307a9  ja      loc_140030895
0x1400307af  or      edx, 0FFFFFFFFh; i
0x1400307b2  mov     rbx, [rsp+1D0h+himl]
0x1400307b7  mov     rcx, rbx; himl
0x1400307ba  call    cs:__imp_ImageList_ReplaceIcon
0x1400307c1  nop     dword ptr [rax+rax+00h]
0x1400307c6  or      [rbp+0D0h+var_120], 2
0x1400307ca  mov     r8, [rsp+1D0h+hicon]; hicon
0x1400307cf  or      edx, 0FFFFFFFFh; i
0x1400307d2  mov     rcx, rbx; himl
0x1400307d5  call    cs:__imp_ImageList_ReplaceIcon
0x1400307dc  nop     dword ptr [rax+rax+00h]
0x1400307e1  mov     [rbp+0D0h+var_FC], eax
0x1400307e4  mov     rax, [r12]
0x1400307e8  mov     [rbp+0D0h+var_108], rax
0x1400307ec  lea     r9, [rbp+0D0h+var_120]; lParam
0x1400307f0  xor     r8d, r8d; wParam
0x1400307f3  mov     edx, 104Dh; Msg
0x1400307f8  mov     rcx, r14; hWnd
0x1400307fb  call    cs:__imp_SendMessageW
0x140030802  nop     dword ptr [rax+rax+00h]
0x140030807  xor     eax, eax
0x140030809  cmp     [rsi+0B8h], eax
0x14003080f  jz      short loc_140030841
0x140030811  cmp     [rsp+1D0h+var_1A0], eax
0x140030815  jnz     short loc_140030887
0x140030817  cmp     [r12+28h], eax
0x14003081c  jz      short loc_140030887
0x14003081e  mov     [rsp+1D0h+var_1A0], edi
0x140030822  xor     edx, edx; Val
0x140030824  lea     r8d, [rax+58h]; Size
0x140030828  lea     rcx, [rbp+0D0h+var_C0]; void *
0x14003082c  call    memset_0
0x140030831  mov     [rbp+0D0h+var_B0], 2
0x140030838  mov     [rbp+0D0h+var_B4], 2
0x14003083f  jmp     short loc_14003086C
0x140030841  xor     edx, edx; Val
0x140030843  lea     r8d, [rdx+58h]; Size
0x140030847  lea     rcx, [rbp+0D0h+var_C0]; void *
0x14003084b  call    memset_0
0x140030850  mov     [rbp+0D0h+var_B0], 0F000h
0x140030857  mov     eax, [r12+28h]
0x14003085c  neg     eax
0x14003085e  sbb     ecx, ecx
0x140030860  mov     eax, 1000h
0x140030865  and     ecx, eax
0x140030867  add     ecx, eax
0x140030869  mov     [rbp+0D0h+var_B4], ecx
0x14003086c  lea     r9, [rbp+0D0h+var_C0]; lParam
0x140030870  mov     r8d, r13d; wParam
0x140030873  mov     edx, 102Bh; Msg
0x140030878  mov     rcx, r14; hWnd
0x14003087b  call    cs:__imp_SendMessageW
0x140030882  nop     dword ptr [rax+rax+00h]
0x140030887  add     [rbp+0D0h+var_120+4], edi
0x14003088a  add     r13d, edi
0x14003088d  xor     r12d, r12d
0x140030890  jmp     loc_14003066D
0x140030895  call    cs:__imp_GetLastError
0x14003089c  nop     dword ptr [rax+rax+00h]
0x1400308a1  test    eax, eax
0x1400308a3  jle     short loc_1400308AD
0x1400308a5  movzx   eax, ax
0x1400308a8  or      eax, 80070000h
0x1400308ad  mov     r9d, 0CFDh
0x1400308b3  jmp     short loc_1400308DB
0x1400308b5  call    cs:__imp_GetLastError
0x1400308bc  nop     dword ptr [rax+rax+00h]
0x1400308c1  test    eax, eax
0x1400308c3  jle     short loc_1400308CD
0x1400308c5  movzx   eax, ax
0x1400308c8  or      eax, 80070000h
0x1400308cd  mov     r9d, 0CE8h
0x1400308d3  jmp     short loc_1400308DB
0x1400308d5  mov     r9d, 0CD1h
0x1400308db  mov     ecx, edi
0x1400308dd  jmp     loc_14003052A
0x1400308e2  mov     r8, rsi
0x1400308e5  lea     rdx, ?NotifyHandler@ListViewPage@@CAHI_K_JPEA_JPEAX@Z; ListViewPage::NotifyHandler(uint,unsigned __int64,__int64,__int64 *,void *)
0x1400308ec  mov     rcx, [rsp+1D0h+var_178]
0x1400308f1  call    cs:__imp_?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z; DirectUI::CCBase::SetNotifyHandler(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *)
0x1400308f8  nop     dword ptr [rax+rax+00h]
0x1400308fd  xor     edx, edx; Val
0x1400308ff  lea     r8d, [rdx+58h]; Size
0x140030903  lea     rcx, [rbp+0D0h+var_C0]; void *
0x140030907  call    memset_0
0x14003090c  mov     [rbp+0D0h+var_B0], edi
0x14003090f  mov     [rbp+0D0h+var_B4], edi
0x140030912  lea     r9, [rbp+0D0h+var_C0]; lParam
0x140030916  xor     r8d, r8d; wParam
0x140030919  mov     edx, 102Bh; Msg
0x14003091e  mov     rcx, r14; hWnd
  ... truncated ...
```
