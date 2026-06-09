# SaveResultsPage::OnWizNext(void)

- ea: `0x14003c470`
- end: `0x14003c8d3`
- name: `?OnWizNext@SaveResultsPage@@MEAA_JXZ`
- size: `1123`
- prototype: `__int64 __fastcall(SaveResultsPage *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task`

## callees

- `0x1400070b0`
- `0x140020420`
- `0x14003c470`
- `0x14003f93c`
- `0x1400404f4`
- `0x140041c54`
- `0x140043a14`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14003c8ab`
- `KERNEL32!CloseHandle` at `0x14003c8ab`
- `KERNEL32!HeapAlloc` at `0x14003c4bd`
- `KERNEL32!HeapAlloc` at `0x14003c4fc`
- `KERNEL32!HeapAlloc` at `0x14003c610`
- `KERNEL32!HeapAlloc` at `0x14003c64f`
- `KERNEL32!HeapAlloc` at `0x14003c689`
- `KERNEL32!HeapAlloc` at `0x14003c4bd`
- `KERNEL32!HeapAlloc` at `0x14003c4fc`
- `KERNEL32!HeapAlloc` at `0x14003c610`
- `KERNEL32!HeapAlloc` at `0x14003c64f`
- `KERNEL32!HeapAlloc` at `0x14003c689`
- `KERNEL32!HeapFree` at `0x14003c7fe`
- `KERNEL32!HeapFree` at `0x14003c823`
- `KERNEL32!HeapFree` at `0x14003c848`
- `KERNEL32!HeapFree` at `0x14003c86d`
- `KERNEL32!HeapFree` at `0x14003c892`
- `KERNEL32!HeapFree` at `0x14003c7fe`
- `KERNEL32!HeapFree` at `0x14003c823`
- `KERNEL32!HeapFree` at `0x14003c848`
- `KERNEL32!HeapFree` at `0x14003c86d`
- `KERNEL32!HeapFree` at `0x14003c892`
- `KERNEL32!GetProcessHeap` at `0x14003c4a4`
- `KERNEL32!GetProcessHeap` at `0x14003c4e8`
- `KERNEL32!GetProcessHeap` at `0x14003c5f9`
- `KERNEL32!GetProcessHeap` at `0x14003c636`
- `KERNEL32!GetProcessHeap` at `0x14003c675`
- `KERNEL32!GetProcessHeap` at `0x14003c7ea`
- `KERNEL32!GetProcessHeap` at `0x14003c80f`
- `KERNEL32!GetProcessHeap` at `0x14003c834`
- `KERNEL32!GetProcessHeap` at `0x14003c859`
- `KERNEL32!GetProcessHeap` at `0x14003c87e`
- `KERNEL32!GetProcessHeap` at `0x14003c4a4`
- `KERNEL32!GetProcessHeap` at `0x14003c4e8`
- `KERNEL32!GetProcessHeap` at `0x14003c5f9`
- `KERNEL32!GetProcessHeap` at `0x14003c636`
- `KERNEL32!GetProcessHeap` at `0x14003c675`
- `KERNEL32!GetProcessHeap` at `0x14003c7ea`
- `KERNEL32!GetProcessHeap` at `0x14003c80f`
- `KERNEL32!GetProcessHeap` at `0x14003c834`
- `KERNEL32!GetProcessHeap` at `0x14003c859`
- `KERNEL32!GetProcessHeap` at `0x14003c87e`
- `KERNEL32!CreateFileW` at `0x14003c5e0`
- `KERNEL32!CreateFileW` at `0x14003c5e0`
- `USER32!PostMessageW` at `0x14003c7a0`
- `USER32!PostMessageW` at `0x14003c7a0`
- `USER32!MessageBoxW` at `0x14003c722`
- `USER32!MessageBoxW` at `0x14003c722`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14003c528`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14003c786`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14003c528`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14003c786`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003c7cf`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003c7cf`

## pseudocode

```c
__int64 __fastcall SaveResultsPage::OnWizNext(SaveResultsPage *this)
{
  WCHAR *v2; // r14
  WCHAR *v3; // r15
  unsigned __int16 *v4; // r12
  char *FileW; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rbp
  int HistoryDirectory; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rsi
  int v11; // r9d
  HANDLE v12; // rax
  HWND ParentHWND; // rax
  unsigned __int16 *v14; // r8
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  __int64 v18; // rdi
  HWND v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int64 v27; // [rsp+88h] [rbp+10h]

  v27 = -1;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  FileW = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v7 )
  {
    HistoryDirectory = -2147024882;
    v9 = -2147024882;
    v10 = 0;
    v11 = 1776;
    goto LABEL_29;
  }
  v12 = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(v12, 0, 0x800u);
  if ( !v10 )
  {
    HistoryDirectory = -2147024882;
    v9 = -2147024882;
    v11 = 1777;
    goto LABEL_29;
  }
  ParentHWND = DirectUI::TaskPage::GetParentHWND(this);
  HistoryDirectory = FolderBrowser(ParentHWND, v7);
  v9 = HistoryDirectory;
  if ( HistoryDirectory < 0 )
  {
    v11 = 1783;
    goto LABEL_29;
  }
  if ( HistoryDirectory == 1 )
  {
    v18 = -1;
  }
  else
  {
    g_ErrorContext = 405;
    HistoryDirectory = MakeHistoryDirectory(0);
    v9 = HistoryDirectory;
    if ( HistoryDirectory < 0 )
    {
      v11 = 1792;
      goto LABEL_29;
    }
    v27 = 0;
    HistoryDirectory = StringCchPrintfW(v10, 0x400u, L"%s\\%s", v7, L"results.cab");
    v9 = HistoryDirectory;
    if ( HistoryDirectory < 0 )
    {
      v11 = 1800;
      goto LABEL_29;
    }
    FileW = (char *)CreateFileW(v10, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (char *)-1LL )
      goto LABEL_27;
    v15 = GetProcessHeap();
    v2 = (WCHAR *)HeapAlloc(v15, 0, 0x200u);
    if ( !v2 )
    {
      HistoryDirectory = -2147024882;
      v11 = 1818;
      v9 = -2147024882;
      goto LABEL_29;
    }
    v16 = GetProcessHeap();
    v3 = (WCHAR *)HeapAlloc(v16, 0, 0x800u);
    if ( !v3 )
    {
      HistoryDirectory = -2147024882;
      v11 = 1819;
      v9 = -2147024882;
      goto LABEL_29;
    }
    v17 = GetProcessHeap();
    v4 = (unsigned __int16 *)HeapAlloc(v17, 0, 0x800u);
    if ( !v4 )
    {
      HistoryDirectory = -2147024882;
      v11 = 1820;
      v9 = -2147024882;
      goto LABEL_29;
    }
    HistoryDirectory = DwzLoadLocalString(0x172u, v2, 0x100u);
    v9 = HistoryDirectory;
    if ( HistoryDirectory < 0 )
    {
      v11 = 1823;
      goto LABEL_29;
    }
    HistoryDirectory = DwzLoadLocalString(0x173u, v3, 0x400u);
    v9 = HistoryDirectory;
    if ( HistoryDirectory < 0 )
    {
      v11 = 1826;
      goto LABEL_29;
    }
    HistoryDirectory = StringCchPrintfW(v4, 0x400u, v3, v10);
    v9 = HistoryDirectory;
    if ( HistoryDirectory < 0 )
    {
      v11 = 1829;
      goto LABEL_29;
    }
    if ( MessageBoxW(0, v4, v2, 0x34u) == 6 )
    {
LABEL_27:
      HistoryDirectory = CreateCabFromPath(v7, L"results.cab", v14, 0);
      v9 = HistoryDirectory;
      if ( HistoryDirectory >= 0 )
      {
        v18 = 0;
LABEL_32:
        DirectUI::TaskPage::PropSheet_SendMessage(this, 0x471u, 5u, 0);
LABEL_33:
        if ( !v7 )
          goto LABEL_37;
        goto LABEL_36;
      }
      v11 = 1839;
LABEL_29:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SaveResultsPage::OnWizNext", v11, HistoryDirectory);
      v18 = v27;
      v19 = DirectUI::TaskPage::GetParentHWND(this);
      PostMessageW(v19, 0x9E2u, 0, v9);
      if ( v27 )
        goto LABEL_33;
      goto LABEL_32;
    }
    v18 = -1;
  }
LABEL_36:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v7);
LABEL_37:
  if ( v2 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v2);
  }
  if ( v3 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v3);
  }
  if ( v4 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v4);
  }
  if ( v10 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v10);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v18;
}

```

## disassembly

```asm
0x14003c470  mov     [rsp+arg_10], rbx
0x14003c475  mov     [rsp+arg_0], rcx
0x14003c47a  push    rbp
0x14003c47b  push    rsi
0x14003c47c  push    rdi
0x14003c47d  push    r12
0x14003c47f  push    r13
0x14003c481  push    r14
0x14003c483  push    r15
0x14003c485  sub     rsp, 40h
0x14003c489  mov     rbx, rcx
0x14003c48c  mov     [rsp+78h+arg_8], 0FFFFFFFFFFFFFFFFh
0x14003c498  xor     r14d, r14d
0x14003c49b  xor     r15d, r15d
0x14003c49e  xor     r12d, r12d
0x14003c4a1  xor     r13d, r13d
0x14003c4a4  call    cs:__imp_GetProcessHeap
0x14003c4ab  nop     dword ptr [rax+rax+00h]
0x14003c4b0  mov     edi, 800h
0x14003c4b5  xor     edx, edx; dwFlags
0x14003c4b7  mov     rcx, rax; hHeap
0x14003c4ba  mov     r8d, edi; dwBytes
0x14003c4bd  call    cs:__imp_HeapAlloc
0x14003c4c4  nop     dword ptr [rax+rax+00h]
0x14003c4c9  mov     rbp, rax
0x14003c4cc  test    rax, rax
0x14003c4cf  jnz     short loc_14003C4E8
0x14003c4d1  mov     eax, 8007000Eh
0x14003c4d6  lea     edi, [rbp+1]
0x14003c4d9  mov     ebx, eax
0x14003c4db  xor     esi, esi
0x14003c4dd  mov     r9d, 6F0h
0x14003c4e3  jmp     loc_14003C75A
0x14003c4e8  call    cs:__imp_GetProcessHeap
0x14003c4ef  nop     dword ptr [rax+rax+00h]
0x14003c4f4  mov     r8, rdi; dwBytes
0x14003c4f7  xor     edx, edx; dwFlags
0x14003c4f9  mov     rcx, rax; hHeap
0x14003c4fc  call    cs:__imp_HeapAlloc
0x14003c503  nop     dword ptr [rax+rax+00h]
0x14003c508  mov     rsi, rax
0x14003c50b  test    rax, rax
0x14003c50e  jnz     short loc_14003C525
0x14003c510  mov     eax, 8007000Eh
0x14003c515  lea     edi, [rsi+1]
0x14003c518  mov     ebx, eax
0x14003c51a  mov     r9d, 6F1h
0x14003c520  jmp     loc_14003C75A
0x14003c525  mov     rcx, rbx
0x14003c528  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x14003c52f  nop     dword ptr [rax+rax+00h]
0x14003c534  mov     rcx, rax; HWND
0x14003c537  mov     rdx, rbp; unsigned __int16 *
0x14003c53a  call    ?FolderBrowser@@YAJPEAUHWND__@@PEAG@Z; FolderBrowser(HWND__ *,ushort *)
0x14003c53f  mov     ebx, eax
0x14003c541  mov     edi, 1
0x14003c546  test    eax, eax
0x14003c548  jns     short loc_14003C555
0x14003c54a  mov     r9d, 6F7h
0x14003c550  jmp     loc_14003C75A
0x14003c555  cmp     eax, edi
0x14003c557  jz      loc_14003C7E2
0x14003c55d  xor     ecx, ecx; int
0x14003c55f  mov     cs:?g_ErrorContext@@3IC, 195h; uint volatile g_ErrorContext
0x14003c569  call    ?MakeHistoryDirectory@@YAJH@Z; MakeHistoryDirectory(int)
0x14003c56e  mov     ebx, eax
0x14003c570  test    eax, eax
0x14003c572  jns     short loc_14003C57F
0x14003c574  mov     r9d, 700h
0x14003c57a  jmp     loc_14003C75A
0x14003c57f  xor     eax, eax
0x14003c581  lea     r8, aSS_1; "%s\\%s"
0x14003c588  mov     [rsp+78h+arg_8], rax
0x14003c590  mov     r9, rbp
0x14003c593  lea     rax, aResultsCab; "results.cab"
0x14003c59a  mov     edx, 400h; unsigned __int64
0x14003c59f  mov     rcx, rsi; unsigned __int16 *
0x14003c5a2  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x14003c5a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003c5ac  mov     ebx, eax
0x14003c5ae  test    eax, eax
0x14003c5b0  jns     short loc_14003C5BD
0x14003c5b2  mov     r9d, 708h
0x14003c5b8  jmp     loc_14003C75A
0x14003c5bd  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x14003c5c2  xor     r9d, r9d; lpSecurityAttributes
0x14003c5c5  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003c5cd  mov     r8d, edi; dwShareMode
0x14003c5d0  mov     edx, 80000000h; dwDesiredAccess
0x14003c5d5  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x14003c5dd  mov     rcx, rsi; lpFileName
0x14003c5e0  call    cs:__imp_CreateFileW
0x14003c5e7  nop     dword ptr [rax+rax+00h]
0x14003c5ec  mov     r13, rax
0x14003c5ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003c5f3  jz      loc_14003C73C
0x14003c5f9  call    cs:__imp_GetProcessHeap
0x14003c600  nop     dword ptr [rax+rax+00h]
0x14003c605  xor     edx, edx; dwFlags
0x14003c607  mov     r8d, 200h; dwBytes
0x14003c60d  mov     rcx, rax; hHeap
0x14003c610  call    cs:__imp_HeapAlloc
0x14003c617  nop     dword ptr [rax+rax+00h]
0x14003c61c  mov     r14, rax
0x14003c61f  test    rax, rax
0x14003c622  jnz     short loc_14003C636
0x14003c624  mov     eax, 8007000Eh
0x14003c629  mov     r9d, 71Ah
0x14003c62f  mov     ebx, eax
0x14003c631  jmp     loc_14003C75A
0x14003c636  call    cs:__imp_GetProcessHeap
0x14003c63d  nop     dword ptr [rax+rax+00h]
0x14003c642  mov     ebx, 800h
0x14003c647  xor     edx, edx; dwFlags
0x14003c649  mov     rcx, rax; hHeap
0x14003c64c  mov     r8d, ebx; dwBytes
0x14003c64f  call    cs:__imp_HeapAlloc
0x14003c656  nop     dword ptr [rax+rax+00h]
0x14003c65b  mov     r15, rax
0x14003c65e  test    rax, rax
0x14003c661  jnz     short loc_14003C675
0x14003c663  mov     eax, 8007000Eh
0x14003c668  mov     r9d, 71Bh
0x14003c66e  mov     ebx, eax
0x14003c670  jmp     loc_14003C75A
0x14003c675  call    cs:__imp_GetProcessHeap
0x14003c67c  nop     dword ptr [rax+rax+00h]
0x14003c681  mov     r8, rbx; dwBytes
0x14003c684  xor     edx, edx; dwFlags
0x14003c686  mov     rcx, rax; hHeap
0x14003c689  call    cs:__imp_HeapAlloc
0x14003c690  nop     dword ptr [rax+rax+00h]
0x14003c695  mov     r12, rax
0x14003c698  test    rax, rax
0x14003c69b  jnz     short loc_14003C6AF
0x14003c69d  mov     eax, 8007000Eh
0x14003c6a2  mov     r9d, 71Ch
0x14003c6a8  mov     ebx, eax
0x14003c6aa  jmp     loc_14003C75A
0x14003c6af  mov     r8d, 100h; cchBufferMax
0x14003c6b5  mov     rdx, r14; lpBuffer
0x14003c6b8  lea     ecx, [r8+72h]; uID
0x14003c6bc  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003c6c1  mov     ebx, eax
0x14003c6c3  test    eax, eax
0x14003c6c5  jns     short loc_14003C6D2
0x14003c6c7  mov     r9d, 71Fh
0x14003c6cd  jmp     loc_14003C75A
0x14003c6d2  mov     r8d, 400h; cchBufferMax
0x14003c6d8  mov     rdx, r15; lpBuffer
0x14003c6db  mov     ecx, 173h; uID
0x14003c6e0  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003c6e5  mov     ebx, eax
0x14003c6e7  test    eax, eax
0x14003c6e9  jns     short loc_14003C6F3
0x14003c6eb  mov     r9d, 722h
0x14003c6f1  jmp     short loc_14003C75A
0x14003c6f3  mov     r9, rsi
0x14003c6f6  mov     r8, r15; unsigned __int16 *
0x14003c6f9  mov     edx, 400h; unsigned __int64
0x14003c6fe  mov     rcx, r12; unsigned __int16 *
0x14003c701  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003c706  mov     ebx, eax
0x14003c708  test    eax, eax
0x14003c70a  jns     short loc_14003C714
0x14003c70c  mov     r9d, 725h
0x14003c712  jmp     short loc_14003C75A
0x14003c714  mov     r9d, 34h ; '4'; uType
0x14003c71a  mov     r8, r14; lpCaption
0x14003c71d  mov     rdx, r12; lpText
0x14003c720  xor     ecx, ecx; hWnd
0x14003c722  call    cs:__imp_MessageBoxW
0x14003c729  nop     dword ptr [rax+rax+00h]
0x14003c72e  cmp     eax, 6
0x14003c731  jz      short loc_14003C73C
0x14003c733  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003c737  jmp     loc_14003C7EA
0x14003c73c  xor     r9d, r9d; int
0x14003c73f  lea     rdx, aResultsCab; "results.cab"
0x14003c746  mov     rcx, rbp; unsigned __int16 *
0x14003c749  call    ?CreateCabFromPath@@YAJPEBG0PEAGH@Z; CreateCabFromPath(ushort const *,ushort const *,ushort *,int)
0x14003c74e  mov     ebx, eax
0x14003c750  test    eax, eax
0x14003c752  jns     short loc_14003C7B3
0x14003c754  mov     r9d, 72Fh
0x14003c75a  lea     r8, aSaveresultspag_0; "SaveResultsPage::OnWizNext"
0x14003c761  mov     [rsp+78h+dwCreationDisposition], eax
0x14003c765  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003c76c  mov     ecx, edi; Level
0x14003c76e  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003c773  mov     rcx, [rsp+78h+arg_0]
0x14003c77b  mov     rdi, [rsp+78h+arg_8]
0x14003c783  movsxd  rbx, ebx
0x14003c786  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x14003c78d  nop     dword ptr [rax+rax+00h]
0x14003c792  mov     r9, rbx; lParam
0x14003c795  xor     r8d, r8d; wParam
0x14003c798  mov     rcx, rax; hWnd
0x14003c79b  mov     edx, 9E2h; Msg
0x14003c7a0  call    cs:__imp_PostMessageW
0x14003c7a7  nop     dword ptr [rax+rax+00h]
0x14003c7ac  test    rdi, rdi
0x14003c7af  jnz     short loc_14003C7DB
0x14003c7b1  jmp     short loc_14003C7BB
0x14003c7b3  mov     rdi, [rsp+78h+arg_8]
0x14003c7bb  mov     rcx, [rsp+78h+arg_0]
0x14003c7c3  xor     r9d, r9d
0x14003c7c6  mov     edx, 471h
0x14003c7cb  lea     r8d, [r9+5]
0x14003c7cf  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003c7d6  nop     dword ptr [rax+rax+00h]
0x14003c7db  test    rbp, rbp
0x14003c7de  jz      short loc_14003C80A
0x14003c7e0  jmp     short loc_14003C7EA
0x14003c7e2  mov     rdi, [rsp+78h+arg_8]
0x14003c7ea  call    cs:__imp_GetProcessHeap
0x14003c7f1  nop     dword ptr [rax+rax+00h]
0x14003c7f6  mov     r8, rbp; lpMem
0x14003c7f9  xor     edx, edx; dwFlags
0x14003c7fb  mov     rcx, rax; hHeap
0x14003c7fe  call    cs:__imp_HeapFree
0x14003c805  nop     dword ptr [rax+rax+00h]
0x14003c80a  test    r14, r14
0x14003c80d  jz      short loc_14003C82F
0x14003c80f  call    cs:__imp_GetProcessHeap
0x14003c816  nop     dword ptr [rax+rax+00h]
0x14003c81b  mov     r8, r14; lpMem
0x14003c81e  xor     edx, edx; dwFlags
0x14003c820  mov     rcx, rax; hHeap
0x14003c823  call    cs:__imp_HeapFree
0x14003c82a  nop     dword ptr [rax+rax+00h]
0x14003c82f  test    r15, r15
0x14003c832  jz      short loc_14003C854
0x14003c834  call    cs:__imp_GetProcessHeap
0x14003c83b  nop     dword ptr [rax+rax+00h]
0x14003c840  mov     r8, r15; lpMem
0x14003c843  xor     edx, edx; dwFlags
0x14003c845  mov     rcx, rax; hHeap
0x14003c848  call    cs:__imp_HeapFree
0x14003c84f  nop     dword ptr [rax+rax+00h]
0x14003c854  test    r12, r12
0x14003c857  jz      short loc_14003C879
0x14003c859  call    cs:__imp_GetProcessHeap
0x14003c860  nop     dword ptr [rax+rax+00h]
0x14003c865  mov     r8, r12; lpMem
0x14003c868  xor     edx, edx; dwFlags
0x14003c86a  mov     rcx, rax; hHeap
0x14003c86d  call    cs:__imp_HeapFree
0x14003c874  nop     dword ptr [rax+rax+00h]
0x14003c879  test    rsi, rsi
0x14003c87c  jz      short loc_14003C89E
0x14003c87e  call    cs:__imp_GetProcessHeap
0x14003c885  nop     dword ptr [rax+rax+00h]
0x14003c88a  mov     r8, rsi; lpMem
0x14003c88d  xor     edx, edx; dwFlags
0x14003c88f  mov     rcx, rax; hHeap
0x14003c892  call    cs:__imp_HeapFree
0x14003c899  nop     dword ptr [rax+rax+00h]
0x14003c89e  lea     rcx, [r13-1]
0x14003c8a2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14003c8a6  ja      short loc_14003C8B7
0x14003c8a8  mov     rcx, r13; hObject
0x14003c8ab  call    cs:__imp_CloseHandle
0x14003c8b2  nop     dword ptr [rax+rax+00h]
0x14003c8b7  mov     rbx, [rsp+78h+arg_10]
0x14003c8bf  mov     rax, rdi
0x14003c8c2  add     rsp, 40h
0x14003c8c6  pop     r15
0x14003c8c8  pop     r14
0x14003c8ca  pop     r13
0x14003c8cc  pop     r12
0x14003c8ce  pop     rdi
0x14003c8cf  pop     rsi
0x14003c8d0  pop     rbp
0x14003c8d1  retn
```
