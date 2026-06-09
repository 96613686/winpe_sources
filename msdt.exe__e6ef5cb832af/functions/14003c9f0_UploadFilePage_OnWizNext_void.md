# UploadFilePage::OnWizNext(void)

- ea: `0x14003c9f0`
- end: `0x14003cd38`
- name: `?OnWizNext@UploadFilePage@@MEAA_JXZ`
- size: `840`
- prototype: `__int64 __fastcall(UploadFilePage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x1400039b1`
- `0x14000e72c`
- `0x14000f720`
- `0x140020420`
- `0x140020b00`
- `0x14003c9f0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14003ca2c`
- `KERNEL32!HeapAlloc` at `0x14003cb2e`
- `KERNEL32!HeapAlloc` at `0x14003ca2c`
- `KERNEL32!HeapAlloc` at `0x14003cb2e`
- `KERNEL32!HeapFree` at `0x14003cc55`
- `KERNEL32!HeapFree` at `0x14003cc85`
- `KERNEL32!HeapFree` at `0x14003cd10`
- `KERNEL32!HeapFree` at `0x14003cc55`
- `KERNEL32!HeapFree` at `0x14003cc85`
- `KERNEL32!HeapFree` at `0x14003cd10`
- `KERNEL32!GetProcessHeap` at `0x14003ca15`
- `KERNEL32!GetProcessHeap` at `0x14003cb17`
- `KERNEL32!GetProcessHeap` at `0x14003cc41`
- `KERNEL32!GetProcessHeap` at `0x14003cc71`
- `KERNEL32!GetProcessHeap` at `0x14003ccf7`
- `KERNEL32!GetProcessHeap` at `0x14003ca15`
- `KERNEL32!GetProcessHeap` at `0x14003cb17`
- `KERNEL32!GetProcessHeap` at `0x14003cc41`
- `KERNEL32!GetProcessHeap` at `0x14003cc71`
- `KERNEL32!GetProcessHeap` at `0x14003ccf7`
- `USER32!SendMessageW` at `0x14003caad`
- `USER32!SendMessageW` at `0x14003cae4`
- `USER32!SendMessageW` at `0x14003cb88`
- `USER32!SendMessageW` at `0x14003cbe3`
- `USER32!SendMessageW` at `0x14003caad`
- `USER32!SendMessageW` at `0x14003cae4`
- `USER32!SendMessageW` at `0x14003cb88`
- `USER32!SendMessageW` at `0x14003cbe3`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003ccc5`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003ccc5`

## pseudocode

```c
__int64 __fastcall UploadFilePage::OnWizNext(UploadFilePage *this)
{
  __int64 v2; // rbp
  HANDLE ProcessHeap; // rax
  int NamedHandle; // eax
  unsigned int v5; // esi
  unsigned int v6; // ebx
  unsigned int v7; // r14d
  int v8; // eax
  unsigned int v9; // ecx
  HANDLE v10; // rax
  unsigned __int16 **v11; // rbx
  __int64 v12; // r15
  unsigned int i; // r14d
  int v14; // eax
  __int64 j; // r14
  unsigned __int16 *v16; // r12
  HANDLE v17; // rax
  HANDLE v18; // rax
  Configuration *v19; // rax
  HANDLE v20; // rax
  LPARAM lParam[4]; // [rsp+30h] [rbp-88h] BYREF
  int v23; // [rsp+50h] [rbp-68h]
  HWND hWnd; // [rsp+C8h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+D0h] [rbp+18h]
  LRESULT v26; // [rsp+D8h] [rbp+20h]

  hWnd = 0;
  v2 = -1;
  ProcessHeap = GetProcessHeap();
  lpMem = HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !lpMem )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnWizNext", 938, -2147024882);
    return v2;
  }
  NamedHandle = WizardPage::GetNamedHandle(this, L"lstView", &hWnd);
  if ( NamedHandle < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnWizNext", 941, NamedHandle);
    goto LABEL_26;
  }
  v5 = 0;
  v6 = 0;
  v26 = SendMessageW(hWnd, 0x1004u, 0, 0);
  v7 = v26;
  if ( !(_DWORD)v26 )
    goto LABEL_25;
  do
  {
    v8 = SendMessageW(hWnd, 0x102Cu, v6, 61440);
    v9 = v5 + 1;
    if ( (v8 & 0xFFFFF000) == 0x1000 )
      v9 = v5;
    ++v6;
    v5 = v9;
  }
  while ( v6 < v7 );
  if ( !v9 )
  {
LABEL_25:
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, 0, 2);
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnWizNext", 957, -2147467259);
    goto LABEL_26;
  }
  v10 = GetProcessHeap();
  v11 = (unsigned __int16 **)HeapAlloc(v10, 8u, 8LL * v5);
  if ( !v11 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnWizNext", 961, -2147024882);
    goto LABEL_26;
  }
  v12 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)v26 || (unsigned int)v12 >= v5 )
    {
      v19 = Config;
      *((_QWORD *)Config + 17) = v11;
      *((_DWORD *)v19 + 52) = v5;
      v2 = WizardPage::OnWizNext(this);
      goto LABEL_26;
    }
    if ( (unsigned int)SendMessageW(hWnd, 0x102Cu, i, 61440) >> 12 != 1 )
      break;
LABEL_18:
    ;
  }
  *(_WORD *)lpMem = 0;
  memset_0(lParam, 0, 0x58u);
  lParam[3] = (LPARAM)lpMem;
  v23 = 260;
  SendMessageW(hWnd, 0x1073u, i, (LPARAM)lParam);
  v14 = DwzStrCpy(&v11[v12], (const unsigned __int16 *)lpMem);
  if ( v14 >= 0 )
  {
    v12 = (unsigned int)(v12 + 1);
    goto LABEL_18;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::OnWizNext", 970, v14);
  for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
  {
    v16 = v11[j];
    if ( v16 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v16);
      v11[j] = 0;
    }
  }
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v11);
LABEL_26:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, lpMem);
  return v2;
}

```

## disassembly

```asm
0x14003c9f0  mov     rax, rsp
0x14003c9f3  mov     [rax+8], rbx
0x14003c9f7  push    rbp
0x14003c9f8  push    rsi
0x14003c9f9  push    r12
0x14003c9fb  push    r14
0x14003c9fd  push    r15
0x14003c9ff  sub     rsp, 90h
0x14003ca06  mov     r12, rcx
0x14003ca09  mov     qword ptr [rax+10h], 0
0x14003ca11  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14003ca15  call    cs:__imp_GetProcessHeap
0x14003ca1c  nop     dword ptr [rax+rax+00h]
0x14003ca21  xor     edx, edx; dwFlags
0x14003ca23  mov     r8d, 208h; dwBytes
0x14003ca29  mov     rcx, rax; hHeap
0x14003ca2c  call    cs:__imp_HeapAlloc
0x14003ca33  nop     dword ptr [rax+rax+00h]
0x14003ca38  mov     [rsp+0B8h+lpMem], rax
0x14003ca40  test    rax, rax
0x14003ca43  jnz     short loc_14003CA6E
0x14003ca45  mov     r9d, 3AAh
0x14003ca4b  mov     [rsp+0B8h+var_98], 8007000Eh
0x14003ca53  lea     r8, aUploadfilepage_5; "UploadFilePage::OnWizNext"
0x14003ca5a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003ca61  lea     ecx, [rbp+2]; Level
0x14003ca64  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003ca69  jmp     loc_14003CD1C
0x14003ca6e  lea     r8, [rsp+0B8h+hWnd]; HWND *
0x14003ca76  mov     rcx, r12; this
0x14003ca79  lea     rdx, aLstview; "lstView"
0x14003ca80  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14003ca85  test    eax, eax
0x14003ca87  jns     short loc_14003CA98
0x14003ca89  mov     [rsp+0B8h+var_98], eax
0x14003ca8d  mov     r9d, 3ADh
0x14003ca93  jmp     loc_14003CCDF
0x14003ca98  mov     rcx, [rsp+0B8h+hWnd]; hWnd
0x14003caa0  xor     r9d, r9d; lParam
0x14003caa3  xor     r8d, r8d; wParam
0x14003caa6  mov     edx, 1004h; Msg
0x14003caab  xor     esi, esi
0x14003caad  call    cs:__imp_SendMessageW
0x14003cab4  nop     dword ptr [rax+rax+00h]
0x14003cab9  xor     ebx, ebx
0x14003cabb  mov     [rsp+0B8h+arg_18], rax
0x14003cac3  mov     r14, rax
0x14003cac6  test    eax, eax
0x14003cac8  jz      loc_14003CCB4
0x14003cace  mov     rcx, [rsp+0B8h+hWnd]; hWnd
0x14003cad6  mov     edx, 102Ch; Msg
0x14003cadb  mov     r8d, ebx; wParam
0x14003cade  mov     r9d, 0F000h; lParam
0x14003cae4  call    cs:__imp_SendMessageW
0x14003caeb  nop     dword ptr [rax+rax+00h]
0x14003caf0  and     eax, 0FFFFF000h
0x14003caf5  lea     ecx, [rsi+1]
0x14003caf8  cmp     eax, 1000h
0x14003cafd  cmovz   ecx, esi
0x14003cb00  inc     ebx
0x14003cb02  mov     esi, ecx
0x14003cb04  cmp     ebx, r14d
0x14003cb07  jb      short loc_14003CACE
0x14003cb09  test    ecx, ecx
0x14003cb0b  jz      loc_14003CCB4
0x14003cb11  mov     ebx, esi
0x14003cb13  shl     rbx, 3
0x14003cb17  call    cs:__imp_GetProcessHeap
0x14003cb1e  nop     dword ptr [rax+rax+00h]
0x14003cb23  mov     r8, rbx; dwBytes
0x14003cb26  mov     edx, 8; dwFlags
0x14003cb2b  mov     rcx, rax; hHeap
0x14003cb2e  call    cs:__imp_HeapAlloc
0x14003cb35  nop     dword ptr [rax+rax+00h]
0x14003cb3a  mov     rbx, rax
0x14003cb3d  test    rax, rax
0x14003cb40  jnz     short loc_14003CB55
0x14003cb42  mov     [rsp+0B8h+var_98], 8007000Eh
0x14003cb4a  mov     r9d, 3C1h
0x14003cb50  jmp     loc_14003CCDF
0x14003cb55  xor     r15d, r15d
0x14003cb58  xor     r14d, r14d
0x14003cb5b  cmp     r14d, dword ptr [rsp+0B8h+arg_18]
0x14003cb63  jnb     loc_14003CC93
0x14003cb69  cmp     r15d, esi
0x14003cb6c  jnb     loc_14003CC93
0x14003cb72  mov     rcx, [rsp+0B8h+hWnd]; hWnd
0x14003cb7a  mov     edx, 102Ch; Msg
0x14003cb7f  mov     r8d, r14d; wParam
0x14003cb82  mov     r9d, 0F000h; lParam
0x14003cb88  call    cs:__imp_SendMessageW
0x14003cb8f  nop     dword ptr [rax+rax+00h]
0x14003cb94  shr     eax, 0Ch
0x14003cb97  cmp     eax, 1
0x14003cb9a  jz      short loc_14003CC07
0x14003cb9c  mov     rcx, [rsp+0B8h+lpMem]
0x14003cba4  xor     eax, eax
0x14003cba6  xor     edx, edx; Val
0x14003cba8  mov     [rcx], ax
0x14003cbab  lea     r8d, [rax+58h]; Size
0x14003cbaf  lea     rcx, [rsp+0B8h+lParam]; void *
0x14003cbb4  call    memset_0
0x14003cbb9  mov     rax, [rsp+0B8h+lpMem]
0x14003cbc1  lea     r9, [rsp+0B8h+lParam]; lParam
0x14003cbc6  mov     rcx, [rsp+0B8h+hWnd]; hWnd
0x14003cbce  mov     edx, 1073h; Msg
0x14003cbd3  mov     r8d, r14d; wParam
0x14003cbd6  mov     [rsp+0B8h+var_70], rax
0x14003cbdb  mov     [rsp+0B8h+var_68], 104h
0x14003cbe3  call    cs:__imp_SendMessageW
0x14003cbea  nop     dword ptr [rax+rax+00h]
0x14003cbef  mov     rdx, [rsp+0B8h+lpMem]; unsigned __int16 *
0x14003cbf7  lea     rcx, [rbx+r15*8]; unsigned __int16 **
0x14003cbfb  call    ?DwzStrCpy@@YAJPEAPEAGPEBG@Z; DwzStrCpy(ushort * *,ushort const *)
0x14003cc00  test    eax, eax
0x14003cc02  js      short loc_14003CC0F
0x14003cc04  inc     r15d
0x14003cc07  inc     r14d
0x14003cc0a  jmp     loc_14003CB5B
0x14003cc0f  mov     r9d, 3CAh
0x14003cc15  mov     [rsp+0B8h+var_98], eax
0x14003cc19  lea     r8, aUploadfilepage_5; "UploadFilePage::OnWizNext"
0x14003cc20  mov     ecx, 1; Level
0x14003cc25  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003cc2c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003cc31  xor     r14d, r14d
0x14003cc34  test    esi, esi
0x14003cc36  jz      short loc_14003CC71
0x14003cc38  mov     r12, [rbx+r14*8]
0x14003cc3c  test    r12, r12
0x14003cc3f  jz      short loc_14003CC69
0x14003cc41  call    cs:__imp_GetProcessHeap
0x14003cc48  nop     dword ptr [rax+rax+00h]
0x14003cc4d  mov     r8, r12; lpMem
0x14003cc50  xor     edx, edx; dwFlags
0x14003cc52  mov     rcx, rax; hHeap
0x14003cc55  call    cs:__imp_HeapFree
0x14003cc5c  nop     dword ptr [rax+rax+00h]
0x14003cc61  mov     qword ptr [rbx+r14*8], 0
0x14003cc69  inc     r14d
0x14003cc6c  cmp     r14d, esi
0x14003cc6f  jb      short loc_14003CC38
0x14003cc71  call    cs:__imp_GetProcessHeap
0x14003cc78  nop     dword ptr [rax+rax+00h]
0x14003cc7d  mov     r8, rbx; lpMem
0x14003cc80  xor     edx, edx; dwFlags
0x14003cc82  mov     rcx, rax; hHeap
0x14003cc85  call    cs:__imp_HeapFree
0x14003cc8c  nop     dword ptr [rax+rax+00h]
0x14003cc91  jmp     short loc_14003CCF7
0x14003cc93  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003cc9a  mov     rcx, r12; this
0x14003cc9d  mov     [rax+88h], rbx
0x14003cca4  mov     [rax+0D0h], esi
0x14003ccaa  call    ?OnWizNext@WizardPage@@MEAA_JXZ; WizardPage::OnWizNext(void)
0x14003ccaf  mov     rbp, rax
0x14003ccb2  jmp     short loc_14003CCF7
0x14003ccb4  mov     r9d, 2
0x14003ccba  xor     r8d, r8d
0x14003ccbd  mov     edx, 48Bh
0x14003ccc2  mov     rcx, r12
0x14003ccc5  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003cccc  nop     dword ptr [rax+rax+00h]
0x14003ccd1  mov     r9d, 3BDh
0x14003ccd7  mov     [rsp+0B8h+var_98], 80004005h
0x14003ccdf  lea     r8, aUploadfilepage_5; "UploadFilePage::OnWizNext"
0x14003cce6  mov     ecx, 1; Level
0x14003cceb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003ccf2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003ccf7  call    cs:__imp_GetProcessHeap
0x14003ccfe  nop     dword ptr [rax+rax+00h]
0x14003cd03  mov     r8, [rsp+0B8h+lpMem]; lpMem
0x14003cd0b  xor     edx, edx; dwFlags
0x14003cd0d  mov     rcx, rax; hHeap
0x14003cd10  call    cs:__imp_HeapFree
0x14003cd17  nop     dword ptr [rax+rax+00h]
0x14003cd1c  mov     rbx, [rsp+0B8h+arg_0]
0x14003cd24  mov     rax, rbp
0x14003cd27  add     rsp, 90h
0x14003cd2e  pop     r15
0x14003cd30  pop     r14
0x14003cd32  pop     r12
0x14003cd34  pop     rsi
0x14003cd35  pop     rbp
0x14003cd36  retn
```
