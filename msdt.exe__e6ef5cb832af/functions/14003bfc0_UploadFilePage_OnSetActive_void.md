# UploadFilePage::OnSetActive(void)

- ea: `0x14003bfc0`
- end: `0x14003c468`
- name: `?OnSetActive@UploadFilePage@@MEAA_JXZ`
- size: `1192`
- prototype: `__int64 __fastcall(UploadFilePage *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1400039b1`
- `0x1400070b0`
- `0x14000e6bc`
- `0x14000e72c`
- `0x14000f480`
- `0x1400104bc`
- `0x140020420`
- `0x14003a138`
- `0x14003bfc0`
- `0x140041c54`
- `0x140061c90`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14003c05d`
- `KERNEL32!HeapAlloc` at `0x14003c0b4`
- `KERNEL32!HeapAlloc` at `0x14003c236`
- `KERNEL32!HeapAlloc` at `0x14003c05d`
- `KERNEL32!HeapAlloc` at `0x14003c0b4`
- `KERNEL32!HeapAlloc` at `0x14003c236`
- `KERNEL32!HeapFree` at `0x14003c3d4`
- `KERNEL32!HeapFree` at `0x14003c3f9`
- `KERNEL32!HeapFree` at `0x14003c41e`
- `KERNEL32!HeapFree` at `0x14003c3d4`
- `KERNEL32!HeapFree` at `0x14003c3f9`
- `KERNEL32!HeapFree` at `0x14003c41e`
- `KERNEL32!GetProcessHeap` at `0x14003c046`
- `KERNEL32!GetProcessHeap` at `0x14003c09d`
- `KERNEL32!GetProcessHeap` at `0x14003c21f`
- `KERNEL32!GetProcessHeap` at `0x14003c3c0`
- `KERNEL32!GetProcessHeap` at `0x14003c3e5`
- `KERNEL32!GetProcessHeap` at `0x14003c40a`
- `KERNEL32!GetProcessHeap` at `0x14003c046`
- `KERNEL32!GetProcessHeap` at `0x14003c09d`
- `KERNEL32!GetProcessHeap` at `0x14003c21f`
- `KERNEL32!GetProcessHeap` at `0x14003c3c0`
- `KERNEL32!GetProcessHeap` at `0x14003c3e5`
- `KERNEL32!GetProcessHeap` at `0x14003c40a`
- `USER32!GetWindowLongPtrW` at `0x14003c338`
- `USER32!GetWindowLongPtrW` at `0x14003c338`
- `USER32!SetWindowLongPtrW` at `0x14003c353`
- `USER32!SetWindowLongPtrW` at `0x14003c353`
- `USER32!GetSystemMetrics` at `0x14003c2c1`
- `USER32!GetSystemMetrics` at `0x14003c2c1`
- `USER32!GetClientRect` at `0x14003c2a3`
- `USER32!GetClientRect` at `0x14003c2a3`
- `USER32!SendMessageW` at `0x14003c1a2`
- `USER32!SendMessageW` at `0x14003c1cb`
- `USER32!SendMessageW` at `0x14003c2e8`
- `USER32!SendMessageW` at `0x14003c303`
- `USER32!SendMessageW` at `0x14003c320`
- `USER32!SendMessageW` at `0x14003c3ad`
- `USER32!SendMessageW` at `0x14003c1a2`
- `USER32!SendMessageW` at `0x14003c1cb`
- `USER32!SendMessageW` at `0x14003c2e8`
- `USER32!SendMessageW` at `0x14003c303`
- `USER32!SendMessageW` at `0x14003c320`
- `USER32!SendMessageW` at `0x14003c3ad`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x14003c28b`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x14003c28b`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003c438`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003c438`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003c013`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003c013`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14003c031`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14003c031`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003c20e`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003c20e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UploadFilePage::OnSetActive(UploadFilePage *this)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // r12
  void *v4; // r14
  HANDLE v5; // rax
  WCHAR *v6; // rax
  unsigned __int16 *v7; // rsi
  int v8; // r9d
  int LocalString; // eax
  int v10; // eax
  int v11; // eax
  int NamedHandle; // eax
  int v13; // edi
  unsigned int v14; // r13d
  unsigned int i; // r15d
  int v16; // eax
  int v17; // ecx
  HANDLE v18; // rax
  int NamedElement; // eax
  HWND v20; // rdi
  LONG_PTR WindowLongPtrW; // rax
  int v22; // eax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  HWND hWnd; // [rsp+30h] [rbp-D0h] BYREF
  struct DirectUI::Element *v28; // [rsp+38h] [rbp-C8h] BYREF
  DirectUI::Element *Element; // [rsp+40h] [rbp-C0h]
  unsigned int v30; // [rsp+48h] [rbp-B8h] BYREF
  LPARAM lParam[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  LPARAM v35; // [rsp+90h] [rbp-70h] BYREF
  int v36; // [rsp+9Ch] [rbp-64h]
  int v37; // [rsp+A0h] [rbp-60h]
  struct tagRECT Rect; // [rsp+F0h] [rbp-10h] BYREF

  hWnd = 0;
  v28 = 0;
  *(_OWORD *)lParam = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  Rect = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v30 = 0;
  DirectUI::Element::StartDefer(Element, &v30);
  WizardPage::OnSetActive(this);
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v3 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1030, -2147024882);
    goto LABEL_32;
  }
  v4 = 0;
  v5 = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(v5, 0, 0x200u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = 1031;
LABEL_5:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", v8, -2147024882);
    goto LABEL_28;
  }
  LocalString = DwzLoadLocalString(0x130u, v6, 0x100u);
  if ( LocalString >= 0 )
  {
    v10 = StringCchPrintfW(v3, 0x400u, v7, *((_QWORD *)Config + 13));
    if ( v10 >= 0 )
    {
      v11 = WizardPage::SetHeader(this, v3);
      if ( v11 >= 0 )
      {
        NamedHandle = WizardPage::GetNamedHandle(this, L"lstView", &hWnd);
        if ( NamedHandle >= 0 )
        {
          if ( *((_DWORD *)this + 28) )
          {
            v13 = 0;
            v14 = SendMessageW(hWnd, 0x1004u, 0, 0);
            for ( i = 0; i < v14; ++i )
            {
              v16 = SendMessageW(hWnd, 0x102Cu, i, 61440);
              v17 = v13 + 1;
              if ( (v16 & 0xFFFFF000) == 0x1000 )
                v17 = v13;
              v13 = v17;
            }
            DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, v13 != 0 ? 2 : 0, 2);
            goto LABEL_28;
          }
          v18 = GetProcessHeap();
          v4 = HeapAlloc(v18, 0, 0x208u);
          if ( v4 )
          {
            NamedElement = WizardPage::GetNamedElement(this, L"lstView", &v28);
            if ( NamedElement >= 0 )
            {
              DirectUI::CCBase::SetNotifyHandler(
                v28,
                (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))UploadFilePage::NotifyHandler,
                this);
              v20 = hWnd;
              GetClientRect(hWnd, &Rect);
              LODWORD(lParam[0]) = 10;
              HIDWORD(v32) = 0;
              LODWORD(lParam[1]) = Rect.right - GetSystemMetrics(2);
              SendMessageW(v20, 0x1061u, SHIDWORD(v32), (LPARAM)lParam);
              SendMessageW(v20, 0x108Eu, 1u, 0);
              SendMessageW(v20, 0x1036u, 0x14004u, 81924);
              WindowLongPtrW = GetWindowLongPtrW(v20, -16);
              SetWindowLongPtrW(v20, -16, WindowLongPtrW | 0x4004);
              v22 = UploadFilePage::AddPath(this, g_HistoryDirectory);
              if ( v22 >= 0 )
              {
                memset_0(&v35, 0, 0x58u);
                v37 = 1;
                v36 = 1;
                SendMessageW(v20, 0x102Bu, 0, (LPARAM)&v35);
                *((_DWORD *)this + 28) = 1;
              }
              else
              {
                SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1103, v22);
              }
            }
            else
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1070, NamedElement);
            }
            goto LABEL_28;
          }
          v8 = 1067;
          goto LABEL_5;
        }
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1046, NamedHandle);
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1043, v11);
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1040, v10);
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnSetActive", 1037, LocalString);
  }
LABEL_28:
  v23 = GetProcessHeap();
  HeapFree(v23, 0, v3);
  if ( v7 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v7);
  }
  if ( v4 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v4);
  }
LABEL_32:
  if ( v30 )
    DirectUI::Element::EndDefer(Element, v30);
  return 0;
}

```

## disassembly

```asm
0x14003bfc0  push    rbp
0x14003bfc2  push    rbx
0x14003bfc3  push    rsi
0x14003bfc4  push    rdi
0x14003bfc5  push    r12
0x14003bfc7  push    r13
0x14003bfc9  push    r14
0x14003bfcb  push    r15
0x14003bfcd  lea     rbp, [rsp-18h]
0x14003bfd2  sub     rsp, 118h
0x14003bfd9  mov     rax, cs:__security_cookie
0x14003bfe0  xor     rax, rsp
0x14003bfe3  mov     [rbp+50h+var_50], rax
0x14003bfe7  mov     rbx, rcx
0x14003bfea  xor     r13d, r13d
0x14003bfed  mov     [rsp+150h+hWnd], r13
0x14003bff2  mov     [rsp+150h+var_118], r13
0x14003bff7  xorps   xmm0, xmm0
0x14003bffa  xor     eax, eax
0x14003bffc  movups  xmmword ptr [rsp+150h+lParam], xmm0
0x14003c001  movups  [rsp+150h+var_F0], xmm0
0x14003c006  movups  [rsp+150h+var_E0], xmm0
0x14003c00b  mov     [rbp+50h+var_D0], rax
0x14003c00f  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x14003c013  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003c01a  nop     dword ptr [rax+rax+00h]
0x14003c01f  mov     [rsp+150h+var_110], rax
0x14003c024  mov     [rsp+150h+var_108], r13d
0x14003c029  lea     rdx, [rsp+150h+var_108]
0x14003c02e  mov     rcx, rax
0x14003c031  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14003c038  nop     dword ptr [rax+rax+00h]
0x14003c03d  nop
0x14003c03e  mov     rcx, rbx; this
0x14003c041  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x14003c046  call    cs:__imp_GetProcessHeap
0x14003c04d  nop     dword ptr [rax+rax+00h]
0x14003c052  mov     rcx, rax; hHeap
0x14003c055  xor     edx, edx; dwFlags
0x14003c057  mov     r8d, 800h; dwBytes
0x14003c05d  call    cs:__imp_HeapAlloc
0x14003c064  nop     dword ptr [rax+rax+00h]
0x14003c069  mov     r12, rax
0x14003c06c  test    rax, rax
0x14003c06f  jnz     short loc_14003C09A
0x14003c071  mov     [rsp+150h+var_130], 8007000Eh
0x14003c079  mov     r9d, 406h
0x14003c07f  lea     r8, aUploadfilepage_8; "UploadFilePage::OnSetActive"
0x14003c086  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003c08d  lea     ecx, [rax+1]; Level
0x14003c090  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003c095  jmp     loc_14003C42B
0x14003c09a  mov     r14, r13
0x14003c09d  call    cs:__imp_GetProcessHeap
0x14003c0a4  nop     dword ptr [rax+rax+00h]
0x14003c0a9  mov     rcx, rax; hHeap
0x14003c0ac  xor     edx, edx; dwFlags
0x14003c0ae  mov     r8d, 200h; dwBytes
0x14003c0b4  call    cs:__imp_HeapAlloc
0x14003c0bb  nop     dword ptr [rax+rax+00h]
0x14003c0c0  mov     rsi, rax
0x14003c0c3  test    rax, rax
0x14003c0c6  jnz     short loc_14003C0F3
0x14003c0c8  mov     r9d, 407h
0x14003c0ce  mov     [rsp+150h+var_130], 8007000Eh
0x14003c0d6  lea     r8, aUploadfilepage_8; "UploadFilePage::OnSetActive"
0x14003c0dd  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003c0e4  mov     ecx, 1; Level
0x14003c0e9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003c0ee  jmp     loc_14003C3C0
0x14003c0f3  mov     r8d, 100h; cchBufferMax
0x14003c0f9  mov     rdx, rsi; lpBuffer
0x14003c0fc  lea     ecx, [r8+30h]; uID
0x14003c100  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003c105  test    eax, eax
0x14003c107  jns     short loc_14003C115
0x14003c109  mov     [rsp+150h+var_130], eax
0x14003c10d  mov     r9d, 40Dh
0x14003c113  jmp     short loc_14003C0D6
0x14003c115  mov     r9, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003c11c  mov     r9, [r9+68h]
0x14003c120  mov     r8, rsi; unsigned __int16 *
0x14003c123  mov     edx, 400h; unsigned __int64
0x14003c128  mov     rcx, r12; unsigned __int16 *
0x14003c12b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003c130  test    eax, eax
0x14003c132  jns     short loc_14003C140
0x14003c134  mov     [rsp+150h+var_130], eax
0x14003c138  mov     r9d, 410h
0x14003c13e  jmp     short loc_14003C0D6
0x14003c140  mov     rdx, r12; unsigned __int16 *
0x14003c143  mov     rcx, rbx; this
0x14003c146  call    ?SetHeader@WizardPage@@IEAAJPEBG@Z; WizardPage::SetHeader(ushort const *)
0x14003c14b  test    eax, eax
0x14003c14d  jns     short loc_14003C15E
0x14003c14f  mov     [rsp+150h+var_130], eax
0x14003c153  mov     r9d, 413h
0x14003c159  jmp     loc_14003C0D6
0x14003c15e  lea     r8, [rsp+150h+hWnd]; HWND *
0x14003c163  lea     rdx, aLstview; "lstView"
0x14003c16a  mov     rcx, rbx; this
0x14003c16d  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14003c172  test    eax, eax
0x14003c174  jns     short loc_14003C185
0x14003c176  mov     [rsp+150h+var_130], eax
0x14003c17a  mov     r9d, 416h
0x14003c180  jmp     loc_14003C0D6
0x14003c185  cmp     [rbx+70h], r13d
0x14003c189  jz      loc_14003C21F
0x14003c18f  mov     edi, r13d
0x14003c192  xor     r9d, r9d; lParam
0x14003c195  xor     r8d, r8d; wParam
0x14003c198  mov     edx, 1004h; Msg
0x14003c19d  mov     rcx, [rsp+150h+hWnd]; hWnd
0x14003c1a2  call    cs:__imp_SendMessageW
0x14003c1a9  nop     dword ptr [rax+rax+00h]
0x14003c1ae  mov     r13, rax
0x14003c1b1  xor     r15d, r15d
0x14003c1b4  test    eax, eax
0x14003c1b6  jz      short loc_14003C1F1
0x14003c1b8  mov     r8d, r15d; wParam
0x14003c1bb  mov     edx, 102Ch; Msg
0x14003c1c0  mov     r9d, 0F000h; lParam
0x14003c1c6  mov     rcx, [rsp+150h+hWnd]; hWnd
0x14003c1cb  call    cs:__imp_SendMessageW
0x14003c1d2  nop     dword ptr [rax+rax+00h]
0x14003c1d7  and     eax, 0FFFFF000h
0x14003c1dc  lea     ecx, [rdi+1]
0x14003c1df  cmp     eax, 1000h
0x14003c1e4  cmovz   ecx, edi
0x14003c1e7  mov     edi, ecx
0x14003c1e9  inc     r15d
0x14003c1ec  cmp     r15d, r13d
0x14003c1ef  jb      short loc_14003C1B8
0x14003c1f1  xor     r13d, r13d
0x14003c1f4  mov     eax, r13d
0x14003c1f7  sub     eax, edi
0x14003c1f9  neg     eax
0x14003c1fb  sbb     r8, r8
0x14003c1fe  and     r8d, 2
0x14003c202  mov     edx, 48Bh
0x14003c207  lea     r9d, [r13+2]
0x14003c20b  mov     rcx, rbx
0x14003c20e  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003c215  nop     dword ptr [rax+rax+00h]
0x14003c21a  jmp     loc_14003C3C0
0x14003c21f  call    cs:__imp_GetProcessHeap
0x14003c226  nop     dword ptr [rax+rax+00h]
0x14003c22b  mov     rcx, rax; hHeap
0x14003c22e  xor     edx, edx; dwFlags
0x14003c230  mov     r8d, 208h; dwBytes
0x14003c236  call    cs:__imp_HeapAlloc
0x14003c23d  nop     dword ptr [rax+rax+00h]
0x14003c242  mov     r14, rax
0x14003c245  test    rax, rax
0x14003c248  jnz     short loc_14003C255
0x14003c24a  mov     r9d, 42Bh
0x14003c250  jmp     loc_14003C0CE
0x14003c255  lea     r8, [rsp+150h+var_118]; struct DirectUI::Element **
0x14003c25a  lea     rdx, aLstview; "lstView"
0x14003c261  mov     rcx, rbx; this
0x14003c264  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14003c269  test    eax, eax
0x14003c26b  jns     short loc_14003C27C
0x14003c26d  mov     [rsp+150h+var_130], eax
0x14003c271  mov     r9d, 42Eh
0x14003c277  jmp     loc_14003C0D6
0x14003c27c  mov     r8, rbx
0x14003c27f  lea     rdx, ?NotifyHandler@UploadFilePage@@CAHI_K_JPEA_JPEAX@Z; UploadFilePage::NotifyHandler(uint,unsigned __int64,__int64,__int64 *,void *)
0x14003c286  mov     rcx, [rsp+150h+var_118]
0x14003c28b  call    cs:__imp_?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z; DirectUI::CCBase::SetNotifyHandler(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *)
0x14003c292  nop     dword ptr [rax+rax+00h]
0x14003c297  lea     rdx, [rbp+50h+Rect]; lpRect
0x14003c29b  mov     rdi, [rsp+150h+hWnd]
0x14003c2a0  mov     rcx, rdi; hWnd
0x14003c2a3  call    cs:__imp_GetClientRect
0x14003c2aa  nop     dword ptr [rax+rax+00h]
0x14003c2af  mov     dword ptr [rsp+150h+lParam], 0Ah
0x14003c2b7  mov     dword ptr [rsp+150h+var_F0+0Ch], r13d
0x14003c2bc  mov     ecx, 2; nIndex
0x14003c2c1  call    cs:__imp_GetSystemMetrics
0x14003c2c8  nop     dword ptr [rax+rax+00h]
0x14003c2cd  mov     ecx, [rbp+50h+Rect.right]
0x14003c2d0  sub     ecx, eax
0x14003c2d2  mov     dword ptr [rsp+150h+lParam+8], ecx
0x14003c2d6  movsxd  r8, dword ptr [rsp+150h+var_F0+0Ch]; wParam
0x14003c2db  lea     r9, [rsp+150h+lParam]; lParam
0x14003c2e0  mov     edx, 1061h; Msg
0x14003c2e5  mov     rcx, rdi; hWnd
0x14003c2e8  call    cs:__imp_SendMessageW
0x14003c2ef  nop     dword ptr [rax+rax+00h]
0x14003c2f4  xor     r9d, r9d; lParam
0x14003c2f7  mov     edx, 108Eh; Msg
0x14003c2fc  lea     r8d, [r9+1]; wParam
0x14003c300  mov     rcx, rdi; hWnd
0x14003c303  call    cs:__imp_SendMessageW
0x14003c30a  nop     dword ptr [rax+rax+00h]
0x14003c30f  mov     r8d, 14004h; wParam
0x14003c315  mov     r9d, r8d; lParam
0x14003c318  mov     edx, 1036h; Msg
0x14003c31d  mov     rcx, rdi; hWnd
0x14003c320  call    cs:__imp_SendMessageW
0x14003c327  nop     dword ptr [rax+rax+00h]
0x14003c32c  mov     r15d, 0FFFFFFF0h
0x14003c332  mov     edx, r15d; nIndex
0x14003c335  mov     rcx, rdi; hWnd
0x14003c338  call    cs:__imp_GetWindowLongPtrW
0x14003c33f  nop     dword ptr [rax+rax+00h]
0x14003c344  or      rax, 4004h
0x14003c34a  mov     r8, rax; dwNewLong
0x14003c34d  mov     edx, r15d; nIndex
0x14003c350  mov     rcx, rdi; hWnd
0x14003c353  call    cs:__imp_SetWindowLongPtrW
0x14003c35a  nop     dword ptr [rax+rax+00h]
0x14003c35f  mov     rdx, cs:?g_HistoryDirectory@@3PEAGEA; unsigned __int16 *
0x14003c366  mov     rcx, rbx; this
0x14003c369  call    ?AddPath@UploadFilePage@@IEAAJPEBG@Z; UploadFilePage::AddPath(ushort const *)
0x14003c36e  test    eax, eax
0x14003c370  jns     short loc_14003C381
0x14003c372  mov     [rsp+150h+var_130], eax
0x14003c376  mov     r9d, 44Fh
0x14003c37c  jmp     loc_14003C0D6
0x14003c381  xor     edx, edx; Val
0x14003c383  lea     r8d, [rdx+58h]; Size
0x14003c387  lea     rcx, [rbp+50h+var_C0]; void *
0x14003c38b  call    memset_0
0x14003c390  mov     [rbp+50h+var_B0], 1
0x14003c397  mov     [rbp+50h+var_B4], 1
0x14003c39e  lea     r9, [rbp+50h+var_C0]; lParam
0x14003c3a2  xor     r8d, r8d; wParam
0x14003c3a5  mov     edx, 102Bh; Msg
0x14003c3aa  mov     rcx, rdi; hWnd
0x14003c3ad  call    cs:__imp_SendMessageW
0x14003c3b4  nop     dword ptr [rax+rax+00h]
0x14003c3b9  mov     dword ptr [rbx+70h], 1
0x14003c3c0  call    cs:__imp_GetProcessHeap
0x14003c3c7  nop     dword ptr [rax+rax+00h]
0x14003c3cc  mov     rcx, rax; hHeap
0x14003c3cf  mov     r8, r12; lpMem
0x14003c3d2  xor     edx, edx; dwFlags
0x14003c3d4  call    cs:__imp_HeapFree
0x14003c3db  nop     dword ptr [rax+rax+00h]
0x14003c3e0  test    rsi, rsi
0x14003c3e3  jz      short loc_14003C405
0x14003c3e5  call    cs:__imp_GetProcessHeap
0x14003c3ec  nop     dword ptr [rax+rax+00h]
0x14003c3f1  mov     rcx, rax; hHeap
0x14003c3f4  mov     r8, rsi; lpMem
0x14003c3f7  xor     edx, edx; dwFlags
0x14003c3f9  call    cs:__imp_HeapFree
0x14003c400  nop     dword ptr [rax+rax+00h]
0x14003c405  test    r14, r14
0x14003c408  jz      short loc_14003C42B
0x14003c40a  call    cs:__imp_GetProcessHeap
0x14003c411  nop     dword ptr [rax+rax+00h]
0x14003c416  mov     rcx, rax; hHeap
0x14003c419  mov     r8, r14; lpMem
0x14003c41c  xor     edx, edx; dwFlags
0x14003c41e  call    cs:__imp_HeapFree
0x14003c425  nop     dword ptr [rax+rax+00h]
0x14003c42a  nop
0x14003c42b  mov     edx, [rsp+150h+var_108]
0x14003c42f  test    edx, edx
0x14003c431  jz      short loc_14003C445
0x14003c433  mov     rcx, [rsp+150h+var_110]
0x14003c438  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14003c43f  nop     dword ptr [rax+rax+00h]
0x14003c444  nop
0x14003c445  xor     eax, eax
0x14003c447  mov     rcx, [rbp+50h+var_50]
0x14003c44b  xor     rcx, rsp; StackCookie
0x14003c44e  call    __security_check_cookie
0x14003c453  add     rsp, 118h
0x14003c45a  pop     r15
0x14003c45c  pop     r14
0x14003c45e  pop     r13
0x14003c460  pop     r12
0x14003c462  pop     rdi
0x14003c463  pop     rsi
0x14003c464  pop     rbx
0x14003c465  pop     rbp
0x14003c466  retn
```
