# CSaveAttachDlg::OnSave(void)

- ea: `0x1800cc2e8`
- end: `0x1800cc589`
- name: `?OnSave@CSaveAttachDlg@@AEAAJXZ`
- size: `673`
- prototype: `__int64 __fastcall(CSaveAttachDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800cbc1c`

## callees

- `0x1800055bc`
- `0x18000910c`
- `0x1800cc2e8`
- `0x1800cc62c`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!MessageBoxInstW` at `0x1800cc40d`
- `MSOERT2!MessageBoxInstW` at `0x1800cc543`
- `MSOERT2!MessageBoxInstW` at `0x1800cc40d`
- `MSOERT2!MessageBoxInstW` at `0x1800cc543`
- `SHLWAPI!PathIsDirectoryW` at `0x1800cc360`
- `SHLWAPI!PathIsDirectoryW` at `0x1800cc360`
- `USER32!MessageBoxW` at `0x1800cc3a9`
- `USER32!MessageBoxW` at `0x1800cc4e2`
- `USER32!LoadStringW` at `0x1800cc387`
- `USER32!LoadStringW` at `0x1800cc387`
- `USER32!LoadStringW` at `0x1800cc3f0`
- `USER32!LoadStringW` at `0x1800cc526`
- `USER32!SendMessageA` at `0x1800cc44f`
- `USER32!SendMessageA` at `0x1800cc44f`
- `USER32!GetDlgItem` at `0x1800cc343`
- `USER32!GetDlgItem` at `0x1800cc343`
- `USER32!GetWindowTextW` at `0x1800cc356`
- `USER32!GetWindowTextW` at `0x1800cc356`
- `USER32!SendMessageW` at `0x1800cc496`
- `USER32!SendMessageW` at `0x1800cc496`
- `USER32!LoadCursorA` at `0x1800cc429`
- `USER32!LoadCursorA` at `0x1800cc429`
- `USER32!SetCursor` at `0x1800cc432`
- `USER32!SetCursor` at `0x1800cc4d8`
- `USER32!SetCursor` at `0x1800cc432`
- `USER32!SetCursor` at `0x1800cc4d8`

## pseudocode

```c
__int64 __fastcall CSaveAttachDlg::OnSave(CSaveAttachDlg *this)
{
  HWND v2; // rcx
  HWND DlgItem; // rax
  unsigned int v5; // r14d
  int v6; // edi
  HCURSOR CursorA; // rax
  HCURSOR v8; // r15
  int v9; // r12d
  int v10; // esi
  HWND v11; // rcx
  int v12; // eax
  HCURSOR v13; // [rsp+60h] [rbp-A0h]
  _DWORD lParam[3]; // [rsp+70h] [rbp-90h] BYREF
  char v15; // [rsp+7Ch] [rbp-84h]
  int v16; // [rsp+80h] [rbp-80h]
  struct ATTACHDATA_tag *v17; // [rsp+98h] [rbp-68h]
  WCHAR String[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[512]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v20[776]; // [rsp+6E0h] [rbp+5E0h] BYREF

  memset_0(lParam, 0, 0x58u);
  v2 = (HWND)*((_QWORD *)this + 2);
  String[260] = 0;
  DlgItem = GetDlgItem(v2, 702);
  GetWindowTextW(DlgItem, String, 260);
  if ( PathIsDirectoryW(String) )
  {
    v5 = 0;
    v6 = 0;
    CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
    v13 = SetCursor(CursorA);
    v8 = v13;
    v9 = SendMessageA(*((HWND *)this + 3), 0x1004u, 0, 0);
    memset_0(lParam, 0, 0x58u);
    v10 = 0;
    lParam[0] = 12;
    v16 = 2;
    if ( v9 > 0 )
    {
      do
      {
        v11 = (HWND)*((_QWORD *)this + 3);
        lParam[1] = v10;
        SendMessageW(v11, 0x104Bu, 0, (LPARAM)lParam);
        if ( (v15 & 2) != 0 )
        {
          v12 = CSaveAttachDlg::SaveAttachment(this, String, v17);
          v5 = v12;
          if ( v12 == -2146691325 )
            break;
          if ( v12 < 0 )
            v6 = 1;
        }
        ++v10;
      }
      while ( v10 < v9 );
      v8 = v13;
    }
    if ( v8 )
      SetCursor(v8);
    if ( v6 )
      MessageBoxInstW(g_hLocRes, *((_QWORD *)this + 2), 1279, 1280, 0, 48, LoadStringW, MessageBoxW, 0, 0, 0, 0);
    StringCchCopyW((unsigned __int16 *)this + 20, 0x104u, String);
    return v5;
  }
  else
  {
    LoadStringW(g_hLocRes, 0x4FEu, Buffer, 512);
    StringCchPrintfW(v20, 0x304u, Buffer, String);
    MessageBoxInstW(g_hLocRes, *((_QWORD *)this + 2), 1279, v20, 0, 48, LoadStringW, MessageBoxW, 0, 0, 0, 0);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1800cc2e8  mov     [rsp-8+arg_8], rbx
0x1800cc2ed  mov     [rsp-8+arg_10], rsi
0x1800cc2f2  push    rbp
0x1800cc2f3  push    rdi
0x1800cc2f4  push    r12
0x1800cc2f6  push    r14
0x1800cc2f8  push    r15
0x1800cc2fa  lea     rbp, [rsp-0C00h]
0x1800cc302  sub     rsp, 0D00h
0x1800cc309  mov     rax, cs:__security_cookie
0x1800cc310  xor     rax, rsp
0x1800cc313  mov     [rbp+0C20h+var_30], rax
0x1800cc31a  mov     rbx, rcx
0x1800cc31d  mov     esi, 58h ; 'X'
0x1800cc322  mov     r8d, esi; Size
0x1800cc325  lea     rcx, [rsp+0D20h+lParam]; void *
0x1800cc32a  xor     edx, edx; Val
0x1800cc32c  call    memset_0
0x1800cc331  mov     rcx, [rbx+10h]; hDlg
0x1800cc335  xor     eax, eax
0x1800cc337  mov     edx, 2BEh; nIDDlgItem
0x1800cc33c  mov     [rbp+0C20h+var_A48], ax
0x1800cc343  call    cs:__imp_GetDlgItem
0x1800cc349  mov     r8d, 104h; nMaxCount
0x1800cc34f  lea     rdx, [rbp+0C20h+String]; lpString
0x1800cc353  mov     rcx, rax; hWnd
0x1800cc356  call    cs:__imp_GetWindowTextW
0x1800cc35c  lea     rcx, [rbp+0C20h+String]; pszPath
0x1800cc360  call    cs:__imp_PathIsDirectoryW
0x1800cc366  test    eax, eax
0x1800cc368  jnz     loc_1800CC41D
0x1800cc36e  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800cc375  lea     r8, [rbp+0C20h+Buffer]; lpBuffer
0x1800cc37c  mov     r9d, 200h; cchBufferMax
0x1800cc382  mov     edx, 4FEh; uID
0x1800cc387  call    cs:__imp_LoadStringW
0x1800cc38d  lea     r9, [rbp+0C20h+String]
0x1800cc391  mov     edx, 304h; unsigned __int64
0x1800cc396  lea     r8, [rbp+0C20h+Buffer]; unsigned __int16 *
0x1800cc39d  lea     rcx, [rbp+0C20h+var_640]; unsigned __int16 *
0x1800cc3a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cc3a9  mov     rax, cs:__imp_MessageBoxW
0x1800cc3b0  lea     r9, [rbp+0C20h+var_640]
0x1800cc3b7  mov     rdx, [rbx+10h]
0x1800cc3bb  mov     r8d, 4FFh
0x1800cc3c1  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x1800cc3c8  mov     [rsp+0D20h+var_CC8], 0
0x1800cc3d0  mov     [rsp+0D20h+var_CD0], 0
0x1800cc3d9  mov     [rsp+0D20h+var_CD8], 0
0x1800cc3e2  mov     [rsp+0D20h+var_CE0], 0
0x1800cc3eb  mov     [rsp+0D20h+var_CE8], rax
0x1800cc3f0  mov     rax, cs:__imp_LoadStringW
0x1800cc3f7  mov     [rsp+0D20h+var_CF0], rax
0x1800cc3fc  mov     [rsp+0D20h+var_CF8], 30h ; '0'
0x1800cc404  mov     [rsp+0D20h+var_D00], 0
0x1800cc40d  call    cs:__imp_MessageBoxInstW
0x1800cc413  mov     eax, 80004005h
0x1800cc418  jmp     loc_1800CC55E
0x1800cc41d  mov     edx, 7F02h; lpCursorName
0x1800cc422  xor     ecx, ecx; hInstance
0x1800cc424  xor     r14d, r14d
0x1800cc427  xor     edi, edi
0x1800cc429  call    cs:__imp_LoadCursorA
0x1800cc42f  mov     rcx, rax; hCursor
0x1800cc432  call    cs:__imp_SetCursor
0x1800cc438  mov     rcx, [rbx+18h]; hWnd
0x1800cc43c  xor     r9d, r9d; lParam
0x1800cc43f  xor     r8d, r8d; wParam
0x1800cc442  mov     [rsp+0D20h+var_CC0], rax
0x1800cc447  mov     edx, 1004h; Msg
0x1800cc44c  mov     r15, rax
0x1800cc44f  call    cs:__imp_SendMessageA
0x1800cc455  mov     r8, rsi; Size
0x1800cc458  lea     rcx, [rsp+0D20h+lParam]; void *
0x1800cc45d  xor     edx, edx; Val
0x1800cc45f  mov     r12, rax
0x1800cc462  call    memset_0
0x1800cc467  xor     esi, esi
0x1800cc469  mov     [rsp+0D20h+lParam], 0Ch
0x1800cc471  mov     [rbp+0C20h+var_CA0], 2
0x1800cc478  test    r12d, r12d
0x1800cc47b  jle     short loc_1800CC4D0
0x1800cc47d  lea     r15d, [r14+1]
0x1800cc481  mov     rcx, [rbx+18h]; hWnd
0x1800cc485  lea     r9, [rsp+0D20h+lParam]; lParam
0x1800cc48a  xor     r8d, r8d; wParam
0x1800cc48d  mov     [rsp+0D20h+lParam+4], esi
0x1800cc491  mov     edx, 104Bh; Msg
0x1800cc496  call    cs:__imp_SendMessageW
0x1800cc49c  test    [rsp+0D20h+var_CA4], 2
0x1800cc4a1  jz      short loc_1800CC4C3
0x1800cc4a3  mov     r8, [rbp+0C20h+var_C88]; struct ATTACHDATA_tag *
0x1800cc4a7  lea     rdx, [rbp+0C20h+String]; unsigned __int16 *
0x1800cc4ab  mov     rcx, rbx; this
0x1800cc4ae  call    ?SaveAttachment@CSaveAttachDlg@@AEAAJPEBGPEBUATTACHDATA_tag@@@Z; CSaveAttachDlg::SaveAttachment(ushort const *,ATTACHDATA_tag const *)
0x1800cc4b3  mov     r14d, eax
0x1800cc4b6  cmp     eax, 800C1703h
0x1800cc4bb  jz      short loc_1800CC4CB
0x1800cc4bd  test    eax, eax
0x1800cc4bf  cmovs   edi, r15d
0x1800cc4c3  add     esi, r15d
0x1800cc4c6  cmp     esi, r12d
0x1800cc4c9  jl      short loc_1800CC481
0x1800cc4cb  mov     r15, [rsp+0D20h+var_CC0]
0x1800cc4d0  test    r15, r15
0x1800cc4d3  jz      short loc_1800CC4DE
0x1800cc4d5  mov     rcx, r15; hCursor
0x1800cc4d8  call    cs:__imp_SetCursor
0x1800cc4de  test    edi, edi
0x1800cc4e0  jz      short loc_1800CC549
0x1800cc4e2  mov     rax, cs:__imp_MessageBoxW
0x1800cc4e9  mov     r9d, 500h
0x1800cc4ef  mov     rdx, [rbx+10h]
0x1800cc4f3  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x1800cc4fa  mov     [rsp+0D20h+var_CC8], 0
0x1800cc502  mov     [rsp+0D20h+var_CD0], 0
0x1800cc50b  lea     r8d, [r9-1]
0x1800cc50f  mov     [rsp+0D20h+var_CD8], 0
0x1800cc518  mov     [rsp+0D20h+var_CE0], 0
0x1800cc521  mov     [rsp+0D20h+var_CE8], rax
0x1800cc526  mov     rax, cs:__imp_LoadStringW
0x1800cc52d  mov     [rsp+0D20h+var_CF0], rax
0x1800cc532  mov     [rsp+0D20h+var_CF8], 30h ; '0'
0x1800cc53a  mov     [rsp+0D20h+var_D00], 0
0x1800cc543  call    cs:__imp_MessageBoxInstW
0x1800cc549  lea     rcx, [rbx+28h]; unsigned __int16 *
0x1800cc54d  mov     edx, 104h; unsigned __int64
0x1800cc552  lea     r8, [rbp+0C20h+String]; unsigned __int16 *
0x1800cc556  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cc55b  mov     eax, r14d
0x1800cc55e  mov     rcx, [rbp+0C20h+var_30]
0x1800cc565  xor     rcx, rsp; StackCookie
0x1800cc568  call    __security_check_cookie
0x1800cc56d  lea     r11, [rsp+0D20h+var_20]
0x1800cc575  mov     rbx, [r11+38h]
0x1800cc579  mov     rsi, [r11+40h]
0x1800cc57d  mov     rsp, r11
0x1800cc580  pop     r15
0x1800cc582  pop     r14
0x1800cc584  pop     r12
0x1800cc586  pop     rdi
0x1800cc587  pop     rbp
0x1800cc588  retn
```
