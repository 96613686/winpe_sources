# CleanupMgrDlgInitList(HWND__ *)

- ea: `0x14000bd24`
- end: `0x14000c1ec`
- name: `?CleanupMgrDlgInitList@@YAHPEAUHWND__@@@Z`
- size: `1224`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000bae4`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x140005fa0`
- `0x14000bd24`
- `0x14000dde4`
- `0x14000eae4`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x14000bdac`
- `USER32!GetSystemMetrics` at `0x14000be87`
- `USER32!GetSystemMetrics` at `0x14000be94`
- `USER32!GetSystemMetrics` at `0x14000bdac`
- `USER32!GetSystemMetrics` at `0x14000be87`
- `USER32!GetSystemMetrics` at `0x14000be94`
- `USER32!LoadStringW` at `0x14000c08c`
- `USER32!LoadStringW` at `0x14000c08c`
- `USER32!GetDlgItem` at `0x14000bd8a`
- `USER32!GetDlgItem` at `0x14000bd8a`
- `USER32!SendMessageW` at `0x14000be1a`
- `USER32!SendMessageW` at `0x14000be5f`
- `USER32!SendMessageW` at `0x14000bec6`
- `USER32!SendMessageW` at `0x14000bedd`
- `USER32!SendMessageW` at `0x14000bfa2`
- `USER32!SendMessageW` at `0x14000c03d`
- `USER32!SendMessageW` at `0x14000c0d4`
- `USER32!SendMessageW` at `0x14000c120`
- `USER32!SendMessageW` at `0x14000c159`
- `USER32!SendMessageW` at `0x14000c1ba`
- `USER32!SendMessageW` at `0x14000be1a`
- `USER32!SendMessageW` at `0x14000be5f`
- `USER32!SendMessageW` at `0x14000bec6`
- `USER32!SendMessageW` at `0x14000bedd`
- `USER32!SendMessageW` at `0x14000bfa2`
- `USER32!SendMessageW` at `0x14000c03d`
- `USER32!SendMessageW` at `0x14000c0d4`
- `USER32!SendMessageW` at `0x14000c120`
- `USER32!SendMessageW` at `0x14000c159`
- `USER32!SendMessageW` at `0x14000c1ba`
- `USER32!GetClientRect` at `0x14000bda1`
- `USER32!GetClientRect` at `0x14000bda1`
- `USER32!GetWindowLongPtrW` at `0x14000bd67`
- `USER32!GetWindowLongPtrW` at `0x14000bd67`
- `USER32!GetWindowLongW` at `0x14000be6d`
- `USER32!GetWindowLongW` at `0x14000be6d`
- `COMCTL32!ImageList_ReplaceIcon` at `0x14000c025`
- `COMCTL32!ImageList_ReplaceIcon` at `0x14000c025`
- `COMCTL32!ImageList_Create` at `0x14000bead`
- `COMCTL32!ImageList_Create` at `0x14000bead`
- `SHLWAPI!StrFormatByteSizeW` at `0x14000c09e`
- `SHLWAPI!StrFormatByteSizeW` at `0x14000c09e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000bf54`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000bf54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000bf67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000bf67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c164`
- `KERNEL32!MulDiv` at `0x14000bdf8`
- `KERNEL32!MulDiv` at `0x14000be43`
- `KERNEL32!MulDiv` at `0x14000bdf8`
- `KERNEL32!MulDiv` at `0x14000be43`

## pseudocode

```c
__int64 __fastcall CleanupMgrDlgInitList(HWND hDlg)
{
  HWND v1; // r15
  _DWORD *WindowLongPtrW; // rax
  _DWORD *v3; // rsi
  HWND DlgItem; // r14
  int v5; // ebx
  char v6; // r13
  int v7; // r13d
  int v8; // eax
  int v9; // edi
  int SystemMetrics; // ebx
  int v11; // eax
  int v12; // r12d
  __int64 v13; // rbx
  __int64 v14; // rax
  const WCHAR *v15; // r8
  unsigned int v16; // edi
  unsigned __int16 *v17; // rax
  int v18; // eax
  int v19; // edi
  int v20; // r15d
  __int64 ItemData; // rax
  __int64 v22; // r8
  int v23; // eax
  WPARAM v24; // rdi
  __int64 v25; // rcx
  LONGLONG v26; // rcx
  __int64 v27; // rax
  int v29; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *hMem; // [rsp+48h] [rbp-B8h]
  struct _IMAGELIST *himl; // [rsp+58h] [rbp-A8h]
  LPARAM lParam[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  LPARAM v37; // [rsp+A0h] [rbp-60h] BYREF
  int v38; // [rsp+A8h] [rbp-58h]
  int v39; // [rsp+ACh] [rbp-54h]
  int v40; // [rsp+B0h] [rbp-50h]
  WCHAR *v41; // [rsp+B8h] [rbp-48h]
  _DWORD v42[6]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v43; // [rsp+118h] [rbp+18h]
  int v44; // [rsp+124h] [rbp+24h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  tagRECT Rect; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Buffer[8]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v48; // [rsp+180h] [rbp+80h]
  int v49; // [rsp+190h] [rbp+90h]

  v1 = hDlg;
  if ( !hDlg )
    return 0;
  WindowLongPtrW = (_DWORD *)GetWindowLongPtrW(hDlg, 16);
  v3 = WindowLongPtrW;
  if ( !WindowLongPtrW || *WindowLongPtrW == 26 )
    return 0;
  DlgItem = GetDlgItem(v1, 1000);
  Rect = 0;
  GetClientRect(DlgItem, &Rect);
  v5 = Rect.right - GetSystemMetrics(2);
  v6 = v3[408];
  v29 = v3[408] & 0x18;
  v36 = 0;
  *(_OWORD *)lParam = 0;
  LODWORD(lParam[0]) = 10;
  v34 = 0;
  HIDWORD(v34) = 0;
  v35 = 0;
  v7 = v6 & 5;
  if ( v7 )
    LODWORD(lParam[1]) = v5;
  else
    LODWORD(lParam[1]) = MulDiv(v5, 75, 100);
  SendMessageW(DlgItem, 0x1061u, 0, (LPARAM)lParam);
  if ( !v7 )
  {
    LODWORD(lParam[0]) = 11;
    HIDWORD(v34) = 1;
    v8 = MulDiv(v5, 25, 100);
    HIDWORD(lParam[0]) = 1;
    LODWORD(lParam[1]) = v8;
    SendMessageW(DlgItem, 0x1061u, 1u, (LPARAM)lParam);
  }
  v9 = (GetWindowLongW(DlgItem, -20) & 0x400000) != 0 ? 0xA000 : 0;
  SystemMetrics = GetSystemMetrics(50);
  v11 = GetSystemMetrics(49);
  himl = ImageList_Create(v11, SystemMetrics, v9 + 33, 4, 4);
  SendMessageW(DlgItem, 0x1003u, 1u, (LPARAM)himl);
  SendMessageW(DlgItem, 0x1036u, 0x24u, 36);
  g_bIgnoreCheckStateChanges = 1;
  v12 = 0;
  if ( (int)v3[434] > 0 )
  {
    do
    {
      v13 = 616LL * v12;
      v14 = *((_QWORD *)v3 + 218);
      if ( *(_QWORD *)(v13 + v14 + 24) )
      {
        v15 = *(const WCHAR **)(v13 + v14 + 568);
        if ( v15 )
        {
          if ( *(_DWORD *)(v13 + v14 + 600) == 1 )
          {
            v16 = WideCharToMultiByte(0, 0, v15, -1, 0, 0, 0, 0);
            v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (v16 + 1));
            hMem = v17;
            if ( v17 )
            {
              StringCchCopyW(v17, v16, *(const unsigned __int16 **)(*((_QWORD *)v3 + 218) + v13 + 568));
              v18 = SendMessageW(DlgItem, 0x1004u, 0, 0);
              v19 = 0;
              if ( v18 > 0 )
              {
                v20 = v18;
                do
                {
                  ItemData = ListView_GetItemData(DlgItem, v19);
                  if ( !ItemData )
                    break;
                  if ( *(_DWORD *)(*((_QWORD *)v3 + 218) + v13 + 588) < *(_DWORD *)(ItemData + 588) )
                    break;
                  ++v19;
                }
                while ( v19 < v20 );
              }
              memset_0(v42, 0, 0x58u);
              v22 = *((_QWORD *)v3 + 218);
              v42[0] = 7;
              v42[1] = v19;
              v42[2] = 0;
              v43 = hMem;
              v45 = v13 + v22;
              v44 = ImageList_ReplaceIcon(himl, -1, *(HICON *)(v13 + v22));
              v23 = SendMessageW(DlgItem, 0x104Du, 0, (LPARAM)v42);
              LODWORD(v24) = v23;
              if ( v7 )
              {
                v24 = v23;
              }
              else
              {
                v25 = *((_QWORD *)v3 + 218);
                *(_OWORD *)Buffer = 0;
                v49 = 0;
                v48 = 0;
                v26 = *(_QWORD *)(v25 + v13 + 592);
                if ( v26 == -1 )
                  LoadStringW(g_hInstance, 0x1Du, Buffer, 18);
                else
                  StrFormatByteSizeW(v26, Buffer, 0x12u);
                memset_0(&v37, 0, 0x58u);
                v24 = (int)v24;
                v41 = Buffer;
                v38 = 1;
                SendMessageW(DlgItem, 0x1074u, (int)v24, (LPARAM)&v37);
              }
              memset_0(&v37, 0, 0x58u);
              v27 = *((_QWORD *)v3 + 218);
              v40 = 61440;
              v39 = *(_DWORD *)(v27 + v13 + 604) != 0 ? 0x2000 : 4096;
              SendMessageW(DlgItem, 0x102Bu, v24, (LPARAM)&v37);
              if ( v29 )
              {
                memset_0(&v37, 0, 0x58u);
                v40 = 61440;
                v39 = 0x2000;
                SendMessageW(DlgItem, 0x102Bu, v24, (LPARAM)&v37);
              }
              LocalFree(hMem);
            }
          }
        }
      }
      ++v12;
    }
    while ( v12 < v3[434] );
    v1 = hDlg;
  }
  g_bIgnoreCheckStateChanges = 0;
  UpdateTotalSpaceToBeFreed(v1);
  memset_0(&v37, 0, 0x58u);
  v40 = 2;
  v39 = 2;
  SendMessageW(DlgItem, 0x102Bu, 0, (LPARAM)&v37);
  return 1;
}

```

## disassembly

```asm
0x14000bd24  push    rbp
0x14000bd26  push    rbx
0x14000bd27  push    rsi
0x14000bd28  push    rdi
0x14000bd29  push    r12
0x14000bd2b  push    r13
0x14000bd2d  push    r14
0x14000bd2f  push    r15
0x14000bd31  lea     rbp, [rsp-0A8h]
0x14000bd39  sub     rsp, 1A8h
0x14000bd40  mov     rax, cs:__security_cookie
0x14000bd47  xor     rax, rsp
0x14000bd4a  mov     [rbp+0E0h+var_48], rax
0x14000bd51  mov     [rsp+1E0h+var_180], rcx
0x14000bd56  mov     r15, rcx
0x14000bd59  test    rcx, rcx
0x14000bd5c  jz      loc_14000C1C7
0x14000bd62  mov     edx, 10h; nIndex
0x14000bd67  call    cs:__imp_GetWindowLongPtrW
0x14000bd6d  mov     rsi, rax
0x14000bd70  test    rax, rax
0x14000bd73  jz      loc_14000C1C7
0x14000bd79  cmp     dword ptr [rax], 1Ah
0x14000bd7c  jz      loc_14000C1C7
0x14000bd82  mov     edx, 3E8h; nIDDlgItem
0x14000bd87  mov     rcx, r15; hDlg
0x14000bd8a  call    cs:__imp_GetDlgItem
0x14000bd90  xorps   xmm0, xmm0
0x14000bd93  lea     rdx, [rbp+0E0h+Rect]; lpRect
0x14000bd97  mov     rcx, rax; hWnd
0x14000bd9a  mov     r14, rax
0x14000bd9d  movups  xmmword ptr [rbp+0E0h+Rect.left], xmm0
0x14000bda1  call    cs:__imp_GetClientRect
0x14000bda7  mov     ecx, 2; nIndex
0x14000bdac  call    cs:__imp_GetSystemMetrics
0x14000bdb2  mov     ebx, [rbp+0E0h+Rect.right]
0x14000bdb5  xorps   xmm0, xmm0
0x14000bdb8  sub     ebx, eax
0x14000bdba  mov     eax, [rsi+660h]
0x14000bdc0  mov     r13d, eax
0x14000bdc3  and     eax, 18h
0x14000bdc6  mov     [rsp+1E0h+var_1A0], eax
0x14000bdca  xor     eax, eax
0x14000bdcc  mov     [rbp+0E0h+var_148], rax
0x14000bdd0  movups  xmmword ptr [rsp+1E0h+lParam], xmm0
0x14000bdd5  mov     dword ptr [rsp+1E0h+lParam], 0Ah
0x14000bddd  movups  [rsp+1E0h+var_168], xmm0
0x14000bde2  mov     dword ptr [rbp+0E0h+var_168+0Ch], eax
0x14000bde5  movups  [rbp+0E0h+var_158], xmm0
0x14000bde9  and     r13d, 5
0x14000bded  jnz     short loc_14000BE04
0x14000bdef  lea     edx, [rax+4Bh]; nNumerator
0x14000bdf2  mov     ecx, ebx; nNumber
0x14000bdf4  lea     r8d, [rax+64h]; nDenominator
0x14000bdf8  call    cs:__imp_MulDiv
0x14000bdfe  mov     dword ptr [rsp+1E0h+lParam+8], eax
0x14000be02  jmp     short loc_14000BE08
0x14000be04  mov     dword ptr [rsp+1E0h+lParam+8], ebx
0x14000be08  mov     edi, 1061h
0x14000be0d  lea     r9, [rsp+1E0h+lParam]; lParam
0x14000be12  mov     edx, edi; Msg
0x14000be14  xor     r8d, r8d; wParam
0x14000be17  mov     rcx, r14; hWnd
0x14000be1a  call    cs:__imp_SendMessageW
0x14000be20  mov     r12d, 1
0x14000be26  test    r13d, r13d
0x14000be29  jnz     short loc_14000BE65
0x14000be2b  lea     edx, [r12+18h]; nNumerator
0x14000be30  mov     dword ptr [rsp+1E0h+lParam], 0Bh
0x14000be38  lea     r8d, [r12+63h]; nDenominator
0x14000be3d  mov     dword ptr [rbp+0E0h+var_168+0Ch], r12d
0x14000be41  mov     ecx, ebx; nNumber
0x14000be43  call    cs:__imp_MulDiv
0x14000be49  lea     r9, [rsp+1E0h+lParam]; lParam
0x14000be4e  mov     dword ptr [rsp+1E0h+lParam+4], r12d
0x14000be53  mov     r8d, r12d; wParam
0x14000be56  mov     dword ptr [rsp+1E0h+lParam+8], eax
0x14000be5a  mov     edx, edi; Msg
0x14000be5c  mov     rcx, r14; hWnd
0x14000be5f  call    cs:__imp_SendMessageW
0x14000be65  mov     edx, 0FFFFFFECh; nIndex
0x14000be6a  mov     rcx, r14; hWnd
0x14000be6d  call    cs:__imp_GetWindowLongW
0x14000be73  and     eax, 400000h
0x14000be78  mov     ecx, 32h ; '2'; nIndex
0x14000be7d  neg     eax
0x14000be7f  sbb     edi, edi
0x14000be81  and     edi, 0A000h
0x14000be87  call    cs:__imp_GetSystemMetrics
0x14000be8d  mov     ecx, 31h ; '1'; nIndex
0x14000be92  mov     ebx, eax
0x14000be94  call    cs:__imp_GetSystemMetrics
0x14000be9a  mov     r9d, 4; cInitial
0x14000bea0  lea     r8d, [rdi+21h]; flags
0x14000bea4  mov     ecx, eax; cx
0x14000bea6  mov     [rsp+1E0h+cGrow], r9d; cGrow
0x14000beab  mov     edx, ebx; cy
0x14000bead  call    cs:__imp_ImageList_Create
0x14000beb3  mov     r8, r12; wParam
0x14000beb6  mov     edx, 1003h; Msg
0x14000bebb  mov     r9, rax; lParam
0x14000bebe  mov     [rsp+1E0h+himl], rax
0x14000bec3  mov     rcx, r14; hWnd
0x14000bec6  call    cs:__imp_SendMessageW
0x14000becc  mov     r8d, 24h ; '$'; wParam
0x14000bed2  mov     edx, 1036h; Msg
0x14000bed7  mov     r9d, r8d; lParam
0x14000beda  mov     rcx, r14; hWnd
0x14000bedd  call    cs:__imp_SendMessageW
0x14000bee3  mov     cs:?g_bIgnoreCheckStateChanges@@3HA, r12d; int g_bIgnoreCheckStateChanges
0x14000beea  xor     r12d, r12d
0x14000beed  cmp     [rsi+6C8h], r12d
0x14000bef4  jle     loc_14000C17F
0x14000befa  xor     r15d, r15d
0x14000befd  movsxd  rax, r12d
0x14000bf00  imul    rbx, rax, 268h
0x14000bf07  mov     rax, [rsi+6D0h]
0x14000bf0e  cmp     [rbx+rax+18h], r15
0x14000bf13  jz      loc_14000C16A
0x14000bf19  mov     r8, [rbx+rax+238h]; lpWideCharStr
0x14000bf21  test    r8, r8
0x14000bf24  jz      loc_14000C16A
0x14000bf2a  cmp     dword ptr [rbx+rax+258h], 1
0x14000bf32  jnz     loc_14000C16A
0x14000bf38  mov     [rsp+1E0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x14000bf3d  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000bf41  mov     [rsp+1E0h+lpDefaultChar], r15; lpDefaultChar
0x14000bf46  xor     edx, edx; dwFlags
0x14000bf48  mov     [rsp+1E0h+cbMultiByte], r15d; cbMultiByte
0x14000bf4d  xor     ecx, ecx; CodePage
0x14000bf4f  mov     qword ptr [rsp+1E0h+cGrow], r15; lpMultiByteStr
0x14000bf54  call    cs:__imp_WideCharToMultiByte
0x14000bf5a  mov     edi, eax
0x14000bf5c  mov     ecx, 40h ; '@'; uFlags
0x14000bf61  lea     edx, [rdi+1]
0x14000bf64  add     rdx, rdx; uBytes
0x14000bf67  call    cs:__imp_LocalAlloc
0x14000bf6d  mov     [rsp+1E0h+hMem], rax
0x14000bf72  test    rax, rax
0x14000bf75  jz      loc_14000C16A
0x14000bf7b  mov     r8, [rsi+6D0h]
0x14000bf82  mov     edx, edi; unsigned __int64
0x14000bf84  mov     rcx, rax; unsigned __int16 *
0x14000bf87  mov     r8, [r8+rbx+238h]; unsigned __int16 *
0x14000bf8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000bf94  xor     r9d, r9d; lParam
0x14000bf97  xor     r8d, r8d; wParam
0x14000bf9a  mov     edx, 1004h; Msg
0x14000bf9f  mov     rcx, r14; hWnd
0x14000bfa2  call    cs:__imp_SendMessageW
0x14000bfa8  mov     [rsp+1E0h+var_190], rax
0x14000bfad  mov     edi, r15d
0x14000bfb0  test    eax, eax
0x14000bfb2  jle     short loc_14000BFE6
0x14000bfb4  mov     r15, rax
0x14000bfb7  mov     edx, edi; int
0x14000bfb9  mov     rcx, r14; hWnd
0x14000bfbc  call    ?ListView_GetItemData@@YA_JPEAUHWND__@@H@Z; ListView_GetItemData(HWND__ *,int)
0x14000bfc1  test    rax, rax
0x14000bfc4  jz      short loc_14000BFE3
0x14000bfc6  mov     rcx, [rsi+6D0h]
0x14000bfcd  mov     eax, [rax+24Ch]
0x14000bfd3  cmp     [rcx+rbx+24Ch], eax
0x14000bfda  jb      short loc_14000BFE3
0x14000bfdc  inc     edi
0x14000bfde  cmp     edi, r15d
0x14000bfe1  jl      short loc_14000BFB7
0x14000bfe3  xor     r15d, r15d
0x14000bfe6  xor     edx, edx; Val
0x14000bfe8  lea     rcx, [rbp+0E0h+var_E0]; void *
0x14000bfec  lea     r8d, [rdx+58h]; Size
0x14000bff0  call    memset_0
0x14000bff5  mov     r8, [rsi+6D0h]
0x14000bffc  or      edx, 0FFFFFFFFh; i
0x14000bfff  mov     rax, [rsp+1E0h+hMem]
0x14000c004  add     r8, rbx
0x14000c007  mov     rcx, [rsp+1E0h+himl]; himl
0x14000c00c  mov     dword ptr [rbp+0E0h+var_E0], 7
0x14000c013  mov     dword ptr [rbp+0E0h+var_E0+4], edi
0x14000c016  mov     [rbp+0E0h+var_D8], r15d
0x14000c01a  mov     [rbp+0E0h+var_C8], rax
0x14000c01e  mov     [rbp+0E0h+var_B8], r8
0x14000c022  mov     r8, [r8]; hicon
0x14000c025  call    cs:__imp_ImageList_ReplaceIcon
0x14000c02b  lea     r9, [rbp+0E0h+var_E0]; lParam
0x14000c02f  xor     r8d, r8d; wParam
0x14000c032  mov     edx, 104Dh; Msg
0x14000c037  mov     [rbp+0E0h+var_BC], eax
0x14000c03a  mov     rcx, r14; hWnd
0x14000c03d  call    cs:__imp_SendMessageW
0x14000c043  mov     rdi, rax
0x14000c046  test    r13d, r13d
0x14000c049  jnz     loc_14000C0DC
0x14000c04f  mov     rcx, [rsi+6D0h]
0x14000c056  xorps   xmm0, xmm0
0x14000c059  xor     eax, eax
0x14000c05b  movups  xmmword ptr [rbp+0E0h+Buffer], xmm0
0x14000c05f  mov     [rbp+0E0h+var_50], eax
0x14000c065  movups  [rbp+0E0h+var_60], xmm0
0x14000c06c  mov     rcx, [rcx+rbx+250h]; qdw
0x14000c074  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000c078  jnz     short loc_14000C094
0x14000c07a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14000c081  lea     r9d, [r13+12h]; cchBufferMax
0x14000c085  lea     r8, [rbp+0E0h+Buffer]; lpBuffer
0x14000c089  lea     edx, [rax+1Dh]; uID
0x14000c08c  call    cs:__imp_LoadStringW
0x14000c092  jmp     short loc_14000C0A4
0x14000c094  mov     r8d, 12h; cchBuf
0x14000c09a  lea     rdx, [rbp+0E0h+Buffer]; pszBuf
0x14000c09e  call    cs:__imp_StrFormatByteSizeW
0x14000c0a4  xor     edx, edx; Val
0x14000c0a6  lea     rcx, [rbp+0E0h+var_140]; void *
0x14000c0aa  lea     r8d, [rdx+58h]; Size
0x14000c0ae  call    memset_0
0x14000c0b3  lea     rax, [rbp+0E0h+Buffer]
0x14000c0b7  movsxd  rdi, edi
0x14000c0ba  mov     r8, rdi; wParam
0x14000c0bd  mov     [rbp+0E0h+var_128], rax
0x14000c0c1  lea     r9, [rbp+0E0h+var_140]; lParam
0x14000c0c5  mov     [rbp+0E0h+var_138], 1
0x14000c0cc  mov     edx, 1074h; Msg
0x14000c0d1  mov     rcx, r14; hWnd
0x14000c0d4  call    cs:__imp_SendMessageW
0x14000c0da  jmp     short loc_14000C0DF
0x14000c0dc  movsxd  rdi, edi
0x14000c0df  xor     edx, edx; Val
0x14000c0e1  lea     rcx, [rbp+0E0h+var_140]; void *
0x14000c0e5  lea     r8d, [rdx+58h]; Size
0x14000c0e9  call    memset_0
0x14000c0ee  mov     rax, [rsi+6D0h]
0x14000c0f5  lea     r9, [rbp+0E0h+var_140]; lParam
0x14000c0f9  mov     [rbp+0E0h+var_130], 0F000h
0x14000c100  mov     r8, rdi; wParam
0x14000c103  mov     ecx, [rax+rbx+25Ch]
0x14000c10a  neg     ecx
0x14000c10c  mov     ecx, 1000h
0x14000c111  sbb     eax, eax
0x14000c113  and     eax, ecx
0x14000c115  add     eax, ecx
0x14000c117  lea     edx, [rcx+2Bh]; Msg
0x14000c11a  mov     [rbp+0E0h+var_134], eax
0x14000c11d  mov     rcx, r14; hWnd
0x14000c120  call    cs:__imp_SendMessageW
0x14000c126  cmp     [rsp+1E0h+var_1A0], r15d
0x14000c12b  jz      short loc_14000C15F
0x14000c12d  xor     edx, edx; Val
0x14000c12f  lea     rcx, [rbp+0E0h+var_140]; void *
0x14000c133  lea     r8d, [rdx+58h]; Size
0x14000c137  call    memset_0
0x14000c13c  lea     r9, [rbp+0E0h+var_140]; lParam
0x14000c140  mov     [rbp+0E0h+var_130], 0F000h
0x14000c147  mov     r8, rdi; wParam
0x14000c14a  mov     [rbp+0E0h+var_134], 2000h
0x14000c151  mov     edx, 102Bh; Msg
0x14000c156  mov     rcx, r14; hWnd
0x14000c159  call    cs:__imp_SendMessageW
0x14000c15f  mov     rcx, [rsp+1E0h+hMem]; hMem
0x14000c164  call    cs:__imp_LocalFree
0x14000c16a  inc     r12d
0x14000c16d  cmp     r12d, [rsi+6C8h]
0x14000c174  jl      loc_14000BEFD
0x14000c17a  mov     r15, [rsp+1E0h+var_180]
0x14000c17f  mov     rcx, r15; hDlg
0x14000c182  mov     cs:?g_bIgnoreCheckStateChanges@@3HA, 0; int g_bIgnoreCheckStateChanges
0x14000c18c  call    ?UpdateTotalSpaceToBeFreed@@YAXPEAUHWND__@@@Z; UpdateTotalSpaceToBeFreed(HWND__ *)
0x14000c191  xor     edx, edx; Val
0x14000c193  lea     rcx, [rbp+0E0h+var_140]; void *
0x14000c197  lea     r8d, [rdx+58h]; Size
0x14000c19b  call    memset_0
0x14000c1a0  mov     eax, 2
0x14000c1a5  lea     r9, [rbp+0E0h+var_140]; lParam
0x14000c1a9  xor     r8d, r8d; wParam
0x14000c1ac  mov     [rbp+0E0h+var_130], eax
0x14000c1af  mov     edx, 102Bh; Msg
0x14000c1b4  mov     [rbp+0E0h+var_134], eax
0x14000c1b7  mov     rcx, r14; hWnd
0x14000c1ba  call    cs:__imp_SendMessageW
0x14000c1c0  mov     eax, 1
0x14000c1c5  jmp     short loc_14000C1C9
0x14000c1c7  xor     eax, eax
0x14000c1c9  mov     rcx, [rbp+0E0h+var_48]
0x14000c1d0  xor     rcx, rsp; StackCookie
0x14000c1d3  call    __security_check_cookie
0x14000c1d8  add     rsp, 1A8h
0x14000c1df  pop     r15
0x14000c1e1  pop     r14
0x14000c1e3  pop     r13
0x14000c1e5  pop     r12
0x14000c1e7  pop     rdi
0x14000c1e8  pop     rsi
0x14000c1e9  pop     rbx
0x14000c1ea  pop     rbp
0x14000c1eb  retn
```
