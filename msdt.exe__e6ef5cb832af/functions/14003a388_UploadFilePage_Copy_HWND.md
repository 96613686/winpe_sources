# UploadFilePage::Copy(HWND__ *)

- ea: `0x14003a388`
- end: `0x14003a5e3`
- name: `?Copy@UploadFilePage@@IEAAJPEAUHWND__@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(UploadFilePage *__hidden this, HWND hWndNewOwner)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14003a760`

## callees

- `0x140006fe0`
- `0x140010eb4`
- `0x140020420`
- `0x14003a388`
- `0x14003a610`
- `0x14003ce68`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003a4d7`
- `KERNEL32!GetLastError` at `0x14003a4d7`
- `KERNEL32!HeapAlloc` at `0x14003a3cb`
- `KERNEL32!HeapAlloc` at `0x14003a3cb`
- `KERNEL32!HeapFree` at `0x14003a5c7`
- `KERNEL32!HeapFree` at `0x14003a5c7`
- `KERNEL32!GetProcessHeap` at `0x14003a3b4`
- `KERNEL32!GetProcessHeap` at `0x14003a5b3`
- `KERNEL32!GetProcessHeap` at `0x14003a3b4`
- `KERNEL32!GetProcessHeap` at `0x14003a5b3`
- `USER32!SetClipboardData` at `0x14003a555`
- `USER32!SetClipboardData` at `0x14003a555`
- `USER32!EmptyClipboard` at `0x14003a502`
- `USER32!EmptyClipboard` at `0x14003a502`
- `USER32!OpenClipboard` at `0x14003a4c7`
- `USER32!OpenClipboard` at `0x14003a4c7`
- `USER32!CloseClipboard` at `0x14003a561`
- `USER32!CloseClipboard` at `0x14003a561`
- `ole32!GetHGlobalFromStream` at `0x14003a516`
- `ole32!GetHGlobalFromStream` at `0x14003a516`
- `ole32!CreateStreamOnHGlobal` at `0x14003a417`
- `ole32!CreateStreamOnHGlobal` at `0x14003a417`

## string_xrefs

- `0x14003a532`: `UploadFilePage::Copy`
- `0x14003a579`: `UploadFilePage::Copy`

## pseudocode

```c
__int64 __fastcall UploadFilePage::Copy(UploadFilePage *this, HWND hWndNewOwner)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rax
  unsigned __int64 v6; // r8
  unsigned __int16 *v7; // rdi
  signed int v8; // ebx
  HRESULT SelectedFile; // eax
  int v10; // r9d
  size_t v11; // rdx
  signed int LastError; // eax
  HRESULT HGlobalFromStream; // eax
  HANDLE v14; // rax
  size_t pcchLength; // [rsp+30h] [rbp-10h] BYREF
  HGLOBAL phglobal; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+30h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp+38h] BYREF

  v18 = 0;
  phglobal = 0;
  ppstm = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v7 = v5;
  if ( !v5 )
  {
    v8 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::Copy", 1618, -2147024882);
    goto LABEL_25;
  }
  SelectedFile = UploadFilePage::GetSelectedFile(this, v5, v6);
  v8 = SelectedFile;
  if ( SelectedFile < 0 )
  {
    v10 = 1621;
LABEL_24:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::Copy", v10, SelectedFile);
    goto LABEL_25;
  }
  SelectedFile = CreateStreamOnHGlobal(0, 0, &ppstm);
  v8 = SelectedFile;
  if ( SelectedFile < 0 )
  {
    v10 = 1627;
    goto LABEL_24;
  }
  SelectedFile = StringCchCatW(v7, 0x104u, L" ");
  v8 = SelectedFile;
  if ( SelectedFile < 0 )
  {
    v10 = 1630;
    goto LABEL_24;
  }
  pcchLength = 0;
  SelectedFile = StringLengthWorkerW_0(v7, v11, &pcchLength);
  v8 = SelectedFile;
  if ( SelectedFile < 0 )
  {
    v10 = 1633;
    goto LABEL_24;
  }
  SelectedFile = ULongLongToULong(2 * pcchLength, &v18);
  v8 = SelectedFile;
  if ( SelectedFile < 0 )
  {
    v10 = 1636;
    goto LABEL_24;
  }
  SelectedFile = (*(__int64 (__fastcall **)(LPSTREAM, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
                   ppstm,
                   v7,
                   v18,
                   0);
  v8 = SelectedFile;
  if ( SelectedFile < 0 )
  {
    v10 = 1639;
    goto LABEL_24;
  }
  if ( OpenClipboard(hWndNewOwner) )
    goto LABEL_19;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_19:
    EmptyClipboard();
    HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
    v8 = HGlobalFromStream;
    if ( HGlobalFromStream >= 0 )
      SetClipboardData(0xDu, phglobal);
    else
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::Copy", 1653, HGlobalFromStream);
    CloseClipboard();
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "UploadFilePage::Copy", 1646, v8);
  }
LABEL_25:
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v7 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003a388  mov     [rsp-18h+arg_0], rbx
0x14003a38d  push    rbp
0x14003a38e  push    rsi
0x14003a38f  push    rdi
0x14003a390  mov     rbp, rsp
0x14003a393  sub     rsp, 40h
0x14003a397  mov     rsi, rdx
0x14003a39a  mov     [rbp+arg_10], 0
0x14003a3a1  mov     rbx, rcx
0x14003a3a4  mov     [rbp+phglobal], 0
0x14003a3ac  mov     [rbp+ppstm], 0
0x14003a3b4  call    cs:__imp_GetProcessHeap
0x14003a3bb  nop     dword ptr [rax+rax+00h]
0x14003a3c0  xor     edx, edx; dwFlags
0x14003a3c2  mov     r8d, 208h; dwBytes
0x14003a3c8  mov     rcx, rax; hHeap
0x14003a3cb  call    cs:__imp_HeapAlloc
0x14003a3d2  nop     dword ptr [rax+rax+00h]
0x14003a3d7  mov     rdi, rax
0x14003a3da  test    rax, rax
0x14003a3dd  jnz     short loc_14003A3F3
0x14003a3df  mov     ebx, 8007000Eh
0x14003a3e4  mov     r9d, 652h
0x14003a3ea  mov     [rsp+40h+var_20], ebx
0x14003a3ee  jmp     loc_14003A579
0x14003a3f3  mov     rdx, rdi; unsigned __int16 *
0x14003a3f6  mov     rcx, rbx; this
0x14003a3f9  call    ?GetSelectedFile@UploadFilePage@@IEAAJPEAG_K@Z; UploadFilePage::GetSelectedFile(ushort *,unsigned __int64)
0x14003a3fe  mov     ebx, eax
0x14003a400  test    eax, eax
0x14003a402  jns     short loc_14003A40F
0x14003a404  mov     r9d, 655h
0x14003a40a  jmp     loc_14003A575
0x14003a40f  lea     r8, [rbp+ppstm]; ppstm
0x14003a413  xor     edx, edx; fDeleteOnRelease
0x14003a415  xor     ecx, ecx; hGlobal
0x14003a417  call    cs:__imp_CreateStreamOnHGlobal
0x14003a41e  nop     dword ptr [rax+rax+00h]
0x14003a423  mov     ebx, eax
0x14003a425  test    eax, eax
0x14003a427  jns     short loc_14003A434
0x14003a429  mov     r9d, 65Bh
0x14003a42f  jmp     loc_14003A575
0x14003a434  lea     r8, pszSubIdList; " "
0x14003a43b  mov     edx, 104h; unsigned __int64
0x14003a440  mov     rcx, rdi; unsigned __int16 *
0x14003a443  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003a448  mov     ebx, eax
0x14003a44a  test    eax, eax
0x14003a44c  jns     short loc_14003A459
0x14003a44e  mov     r9d, 65Eh
0x14003a454  jmp     loc_14003A575
0x14003a459  lea     r8, [rbp+pcchLength]; pcchLength
0x14003a45d  mov     [rbp+pcchLength], 0
0x14003a465  mov     rcx, rdi; psz
0x14003a468  call    StringLengthWorkerW_0
0x14003a46d  mov     ebx, eax
0x14003a46f  test    eax, eax
0x14003a471  js      loc_14003A56F
0x14003a477  mov     rax, [rbp+pcchLength]
0x14003a47b  lea     rdx, [rbp+arg_10]; unsigned int *
0x14003a47f  lea     rcx, [rax+rax]; unsigned __int64
0x14003a483  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14003a488  mov     ebx, eax
0x14003a48a  test    eax, eax
0x14003a48c  jns     short loc_14003A499
0x14003a48e  mov     r9d, 664h
0x14003a494  jmp     loc_14003A575
0x14003a499  mov     rcx, [rbp+ppstm]
0x14003a49d  xor     r9d, r9d
0x14003a4a0  mov     r8d, [rbp+arg_10]
0x14003a4a4  mov     rdx, rdi
0x14003a4a7  mov     rax, [rcx]
0x14003a4aa  mov     rax, [rax+20h]
0x14003a4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a4b3  mov     ebx, eax
0x14003a4b5  test    eax, eax
0x14003a4b7  jns     short loc_14003A4C4
0x14003a4b9  mov     r9d, 667h
0x14003a4bf  jmp     loc_14003A575
0x14003a4c4  mov     rcx, rsi; hWndNewOwner
0x14003a4c7  call    cs:__imp_OpenClipboard
0x14003a4ce  nop     dword ptr [rax+rax+00h]
0x14003a4d3  test    eax, eax
0x14003a4d5  jnz     short loc_14003A502
0x14003a4d7  call    cs:__imp_GetLastError
0x14003a4de  nop     dword ptr [rax+rax+00h]
0x14003a4e3  mov     ebx, eax
0x14003a4e5  test    eax, eax
0x14003a4e7  jle     short loc_14003A4F2
0x14003a4e9  movzx   ebx, ax
0x14003a4ec  or      ebx, 80070000h
0x14003a4f2  test    ebx, ebx
0x14003a4f4  jns     short loc_14003A502
0x14003a4f6  mov     [rsp+40h+var_20], ebx
0x14003a4fa  mov     r9d, 66Eh
0x14003a500  jmp     short loc_14003A579
0x14003a502  call    cs:__imp_EmptyClipboard
0x14003a509  nop     dword ptr [rax+rax+00h]
0x14003a50e  mov     rcx, [rbp+ppstm]; pstm
0x14003a512  lea     rdx, [rbp+phglobal]; phglobal
0x14003a516  call    cs:__imp_GetHGlobalFromStream
0x14003a51d  nop     dword ptr [rax+rax+00h]
0x14003a522  mov     ebx, eax
0x14003a524  test    eax, eax
0x14003a526  jns     short loc_14003A54C
0x14003a528  mov     r9d, 675h
0x14003a52e  mov     [rsp+40h+var_20], eax
0x14003a532  lea     r8, aUploadfilepage_0; "UploadFilePage::Copy"
0x14003a539  mov     ecx, 1; Level
0x14003a53e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003a545  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003a54a  jmp     short loc_14003A561
0x14003a54c  mov     rdx, [rbp+phglobal]; hMem
0x14003a550  mov     ecx, 0Dh; uFormat
0x14003a555  call    cs:__imp_SetClipboardData
0x14003a55c  nop     dword ptr [rax+rax+00h]
0x14003a561  call    cs:__imp_CloseClipboard
0x14003a568  nop     dword ptr [rax+rax+00h]
0x14003a56d  jmp     short loc_14003A591
0x14003a56f  mov     r9d, 661h
0x14003a575  mov     [rsp+40h+var_20], eax
0x14003a579  lea     r8, aUploadfilepage_0; "UploadFilePage::Copy"
0x14003a580  mov     ecx, 1; Level
0x14003a585  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003a58c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003a591  mov     rcx, [rbp+ppstm]
0x14003a595  test    rcx, rcx
0x14003a598  jz      short loc_14003A5AE
0x14003a59a  mov     rax, [rcx]
0x14003a59d  mov     rax, [rax+10h]
0x14003a5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a5a6  mov     [rbp+ppstm], 0
0x14003a5ae  test    rdi, rdi
0x14003a5b1  jz      short loc_14003A5D3
0x14003a5b3  call    cs:__imp_GetProcessHeap
0x14003a5ba  nop     dword ptr [rax+rax+00h]
0x14003a5bf  mov     r8, rdi; lpMem
0x14003a5c2  xor     edx, edx; dwFlags
0x14003a5c4  mov     rcx, rax; hHeap
0x14003a5c7  call    cs:__imp_HeapFree
0x14003a5ce  nop     dword ptr [rax+rax+00h]
0x14003a5d3  mov     eax, ebx
0x14003a5d5  mov     rbx, [rsp+40h+arg_0]
0x14003a5da  add     rsp, 40h
0x14003a5de  pop     rdi
0x14003a5df  pop     rsi
0x14003a5e0  pop     rbp
0x14003a5e1  retn
```
