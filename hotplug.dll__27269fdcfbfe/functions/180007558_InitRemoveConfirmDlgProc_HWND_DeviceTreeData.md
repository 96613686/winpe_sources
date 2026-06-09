# InitRemoveConfirmDlgProc(HWND__ *,_DeviceTreeData *)

- ea: `0x180007558`
- end: `0x18000787f`
- name: `?InitRemoveConfirmDlgProc@@YAHPEAUHWND__@@PEAU_DeviceTreeData@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(HWND hDlg, struct _DeviceTreeData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007aa0`

## callees

- `0x180003048`
- `0x180007558`
- `0x18000873a`
- `0x180008760`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800076f6`
- `USER32!GetSystemMetrics` at `0x180007703`
- `USER32!GetSystemMetrics` at `0x1800076f6`
- `USER32!GetSystemMetrics` at `0x180007703`
- `USER32!DestroyIcon` at `0x180007752`
- `USER32!DestroyIcon` at `0x180007752`
- `USER32!LoadIconW` at `0x1800075af`
- `USER32!LoadIconW` at `0x1800075af`
- `USER32!SendMessageW` at `0x1800075d3`
- `USER32!SendMessageW` at `0x1800075e4`
- `USER32!SendMessageW` at `0x18000761e`
- `USER32!SendMessageW` at `0x180007632`
- `USER32!SendMessageW` at `0x180007656`
- `USER32!SendMessageW` at `0x180007669`
- `USER32!SendMessageW` at `0x1800077ca`
- `USER32!SendMessageW` at `0x18000780b`
- `USER32!SendMessageW` at `0x18000781f`
- `USER32!SendMessageW` at `0x180007836`
- `USER32!SendMessageW` at `0x18000784c`
- `USER32!SendMessageW` at `0x1800075d3`
- `USER32!SendMessageW` at `0x1800075e4`
- `USER32!SendMessageW` at `0x18000761e`
- `USER32!SendMessageW` at `0x180007632`
- `USER32!SendMessageW` at `0x180007656`
- `USER32!SendMessageW` at `0x180007669`
- `USER32!SendMessageW` at `0x1800077ca`
- `USER32!SendMessageW` at `0x18000780b`
- `USER32!SendMessageW` at `0x18000781f`
- `USER32!SendMessageW` at `0x180007836`
- `USER32!SendMessageW` at `0x18000784c`
- `USER32!GetDlgItem` at `0x180007606`
- `USER32!GetDlgItem` at `0x180007606`
- `COMCTL32!ImageList_ReplaceIcon` at `0x18000773e`
- `COMCTL32!ImageList_ReplaceIcon` at `0x18000773e`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800076b6`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800076b6`
- `SETUPAPI!SetupDiLoadDeviceIcon` at `0x180007728`
- `SETUPAPI!SetupDiLoadDeviceIcon` at `0x180007728`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800076e7`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800076e7`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000775b`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000775b`

## pseudocode

```c
__int64 __fastcall InitRemoveConfirmDlgProc(HWND hDlg, struct _DeviceTreeData *a2)
{
  HICON IconW; // rax
  LPARAM v5; // rbx
  _QWORD *v6; // rdi
  HWND DlgItem; // r15
  int v9; // r12d
  int v10; // ebx
  HWND v11; // rdx
  HDEVINFO DeviceInfoList; // r14
  HWND v13; // r8
  const WCHAR *v14; // rdx
  UINT SystemMetrics; // ebx
  UINT v16; // eax
  int v17; // eax
  unsigned __int16 *v18; // rax
  bool v19; // zf
  const WCHAR *v20; // rax
  HICON hicon; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v22[6]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+64h] [rbp-9Ch]
  _QWORD *v25; // [rsp+68h] [rbp-98h]
  LPARAM lParam[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v27; // [rsp+B0h] [rbp-50h]
  __int128 v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+D0h] [rbp-30h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v31[264]; // [rsp+100h] [rbp+0h] BYREF

  v29 = 0;
  *(_OWORD *)lParam = 0;
  v27 = 0;
  v28 = 0;
  IconW = LoadIconW(hHotPlug, (LPCWSTR)0x64);
  v5 = (LPARAM)IconW;
  if ( IconW )
  {
    SendMessageW(hDlg, 0x80u, 0, (LPARAM)IconW);
    SendMessageW(hDlg, 0x80u, 1u, v5);
  }
  v6 = (_QWORD *)*((_QWORD *)a2 + 6);
  if ( !v6 )
    return 0;
  *((_QWORD *)a2 + 3) = hDlg;
  DlgItem = GetDlgItem(hDlg, 321);
  SendMessageW(DlgItem, 0x1003u, 1u, *((_QWORD *)a2 + 11));
  SendMessageW(DlgItem, 0x1009u, 0, 0);
  lParam[0] = 3;
  HIDWORD(v27) = 0;
  SendMessageW(DlgItem, 0x1061u, 0, (LPARAM)lParam);
  SendMessageW(DlgItem, 0xBu, 0, 0);
  v9 = 0;
  do
  {
    v10 = v9++;
    memset_0(v22, 0, 0x58u);
    v11 = (HWND)*((_QWORD *)a2 + 2);
    hicon = 0;
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    v22[0] = 5;
    v22[1] = v10;
    v22[2] = 0;
    DeviceInfoList = SetupDiCreateDeviceInfoList(0, v11);
    if ( DeviceInfoList != (HDEVINFO)-1LL )
    {
      v13 = (HWND)*((_QWORD *)a2 + 2);
      v14 = (const WCHAR *)v6[4];
      DeviceInfoData.cbSize = 32;
      if ( SetupDiOpenDeviceInfoW(DeviceInfoList, v14, v13, 0, &DeviceInfoData) )
      {
        SystemMetrics = GetSystemMetrics(50);
        v16 = GetSystemMetrics(49);
        if ( SetupDiLoadDeviceIcon(DeviceInfoList, &DeviceInfoData, v16, SystemMetrics, 0, &hicon) )
        {
          v17 = ImageList_ReplaceIcon(*((HIMAGELIST *)a2 + 11), -1, hicon);
          v22[0] |= 2u;
          v24 = v17;
          DestroyIcon(hicon);
        }
      }
      SetupDiDestroyDeviceInfoList(DeviceInfoList);
    }
    v18 = (unsigned __int16 *)v6[5];
    if ( v18 || (v18 = (unsigned __int16 *)v6[6]) != 0 )
    {
      v23 = v18;
    }
    else
    {
      v19 = v6[8] == 0;
      v23 = v31;
      v20 = &String;
      if ( !v19 )
        v20 = (const WCHAR *)v6[8];
      StringCchPrintfW(v31, 0x104u, L"%s %s", &szUnknown, v20);
    }
    v25 = v6;
    SendMessageW(DlgItem, 0x104Du, 0, (LPARAM)v22);
    v6 = (_QWORD *)v6[10];
  }
  while ( v6 != *((_QWORD **)a2 + 6) );
  memset_0(v22, 0, 0x58u);
  v22[4] = 3;
  v22[3] = 3;
  SendMessageW(DlgItem, 0x102Bu, 0, (LPARAM)v22);
  SendMessageW(DlgItem, 0x1013u, 0, 0);
  SendMessageW(DlgItem, 0x101Eu, 0, 65534);
  SendMessageW(DlgItem, 0xBu, 1u, 0);
  return 1;
}

```

## disassembly

```asm
0x180007558  mov     [rsp-8+arg_10], rbx
0x18000755d  mov     [rsp-8+arg_18], rsi
0x180007562  push    rbp
0x180007563  push    rdi
0x180007564  push    r12
0x180007566  push    r14
0x180007568  push    r15
0x18000756a  lea     rbp, [rsp-220h]
0x180007572  sub     rsp, 320h
0x180007579  mov     rax, cs:__security_cookie
0x180007580  xor     rax, rsp
0x180007583  mov     [rbp+240h+var_30], rax
0x18000758a  xorps   xmm0, xmm0
0x18000758d  xor     eax, eax
0x18000758f  mov     rsi, rdx
0x180007592  mov     [rbp+240h+var_270], rax
0x180007596  mov     r14, rcx
0x180007599  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800075a0  movups  xmmword ptr [rbp+240h+lParam], xmm0
0x1800075a4  lea     edx, [rax+64h]; lpIconName
0x1800075a7  movups  [rbp+240h+var_290], xmm0
0x1800075ab  movups  [rbp+240h+var_280], xmm0
0x1800075af  call    cs:__imp_LoadIconW
0x1800075b5  mov     rbx, rax
0x1800075b8  mov     r12d, 1
0x1800075be  test    rax, rax
0x1800075c1  jz      short loc_1800075EA
0x1800075c3  lea     edi, [r12+7Fh]
0x1800075c8  mov     r9, rax; lParam
0x1800075cb  mov     edx, edi; Msg
0x1800075cd  xor     r8d, r8d; wParam
0x1800075d0  mov     rcx, r14; hWnd
0x1800075d3  call    cs:__imp_SendMessageW
0x1800075d9  mov     r9, rbx; lParam
0x1800075dc  mov     r8d, r12d; wParam
0x1800075df  mov     edx, edi; Msg
0x1800075e1  mov     rcx, r14; hWnd
0x1800075e4  call    cs:__imp_SendMessageW
0x1800075ea  mov     rdi, [rsi+30h]
0x1800075ee  test    rdi, rdi
0x1800075f1  jnz     short loc_1800075FA
0x1800075f3  xor     eax, eax
0x1800075f5  jmp     loc_180007854
0x1800075fa  mov     edx, 141h; nIDDlgItem
0x1800075ff  mov     [rsi+18h], r14
0x180007603  mov     rcx, r14; hDlg
0x180007606  call    cs:__imp_GetDlgItem
0x18000760c  mov     r9, [rsi+58h]; lParam
0x180007610  mov     r8, r12; wParam
0x180007613  mov     rcx, rax; hWnd
0x180007616  mov     edx, 1003h; Msg
0x18000761b  mov     r15, rax
0x18000761e  call    cs:__imp_SendMessageW
0x180007624  xor     r9d, r9d; lParam
0x180007627  xor     r8d, r8d; wParam
0x18000762a  mov     edx, 1009h; Msg
0x18000762f  mov     rcx, r15; hWnd
0x180007632  call    cs:__imp_SendMessageW
0x180007638  lea     r9, [rbp+240h+lParam]; lParam
0x18000763c  mov     [rbp+240h+lParam], 3
0x180007644  xor     r8d, r8d; wParam
0x180007647  mov     dword ptr [rbp+240h+var_290+0Ch], 0
0x18000764e  mov     edx, 1061h; Msg
0x180007653  mov     rcx, r15; hWnd
0x180007656  call    cs:__imp_SendMessageW
0x18000765c  xor     r9d, r9d; lParam
0x18000765f  xor     r8d, r8d; wParam
0x180007662  mov     rcx, r15; hWnd
0x180007665  lea     edx, [r9+0Bh]; Msg
0x180007669  call    cs:__imp_SendMessageW
0x18000766f  xor     r12d, r12d
0x180007672  xor     edx, edx; Val
0x180007674  lea     rcx, [rsp+340h+var_300]; void *
0x180007679  mov     ebx, r12d
0x18000767c  inc     r12d
0x18000767f  lea     r8d, [rdx+58h]; Size
0x180007683  call    memset_0
0x180007688  mov     rdx, [rsi+10h]; hwndParent
0x18000768c  xorps   xmm0, xmm0
0x18000768f  xor     ecx, ecx; ClassGuid
0x180007691  mov     [rsp+340h+hicon], 0
0x18000769a  movups  xmmword ptr [rbp+240h+var_268.cbSize], xmm0
0x18000769e  mov     dword ptr [rsp+340h+var_300], 5
0x1800076a6  movups  xmmword ptr [rbp+240h+var_268.ClassGuid.Data4+4], xmm0
0x1800076aa  mov     dword ptr [rsp+340h+var_300+4], ebx
0x1800076ae  mov     [rsp+340h+var_2F8], 0
0x1800076b6  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800076bc  mov     r14, rax
0x1800076bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800076c3  jz      loc_180007761
0x1800076c9  mov     r8, [rsi+10h]; hwndParent
0x1800076cd  lea     rax, [rbp+240h+var_268]
0x1800076d1  mov     rdx, [rdi+20h]; DeviceInstanceId
0x1800076d5  xor     r9d, r9d; OpenFlags
0x1800076d8  mov     rcx, r14; DeviceInfoSet
0x1800076db  mov     [rsp+340h+DeviceInfoData], rax; DeviceInfoData
0x1800076e0  mov     [rbp+240h+var_268.cbSize], 20h ; ' '
0x1800076e7  call    cs:__imp_SetupDiOpenDeviceInfoW
0x1800076ed  test    eax, eax
0x1800076ef  jz      short loc_180007758
0x1800076f1  mov     ecx, 32h ; '2'; nIndex
0x1800076f6  call    cs:__imp_GetSystemMetrics
0x1800076fc  mov     ecx, 31h ; '1'; nIndex
0x180007701  mov     ebx, eax
0x180007703  call    cs:__imp_GetSystemMetrics
0x180007709  lea     rcx, [rsp+340h+hicon]
0x18000770e  mov     r9d, ebx; cyIcon
0x180007711  mov     [rsp+340h+hIcon], rcx; hIcon
0x180007716  lea     rdx, [rbp+240h+var_268]; DeviceInfoData
0x18000771a  mov     rcx, r14; DeviceInfoSet
0x18000771d  mov     dword ptr [rsp+340h+DeviceInfoData], 0; Flags
0x180007725  mov     r8d, eax; cxIcon
0x180007728  call    cs:__imp_SetupDiLoadDeviceIcon
0x18000772e  test    eax, eax
0x180007730  jz      short loc_180007758
0x180007732  mov     r8, [rsp+340h+hicon]; hicon
0x180007737  or      edx, 0FFFFFFFFh; i
0x18000773a  mov     rcx, [rsi+58h]; himl
0x18000773e  call    cs:__imp_ImageList_ReplaceIcon
0x180007744  mov     rcx, [rsp+340h+hicon]; hIcon
0x180007749  or      dword ptr [rsp+340h+var_300], 2
0x18000774e  mov     [rsp+340h+var_2DC], eax
0x180007752  call    cs:__imp_DestroyIcon
0x180007758  mov     rcx, r14; DeviceInfoSet
0x18000775b  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180007761  mov     rax, [rdi+28h]
0x180007765  test    rax, rax
0x180007768  jz      short loc_180007771
0x18000776a  mov     [rsp+340h+var_2E8], rax
0x18000776f  jmp     short loc_1800077B5
0x180007771  mov     rax, [rdi+30h]
0x180007775  test    rax, rax
0x180007778  jnz     short loc_18000776A
0x18000777a  cmp     qword ptr [rdi+40h], 0
0x18000777f  lea     rax, [rbp+240h+var_240]
0x180007783  mov     [rsp+340h+var_2E8], rax
0x180007788  lea     r9, ?szUnknown@@3PAGA; ushort near * szUnknown
0x18000778f  lea     rax, String
0x180007796  mov     edx, 104h; unsigned __int64
0x18000779b  cmovnz  rax, [rdi+40h]
0x1800077a0  lea     r8, aSS; "%s %s"
0x1800077a7  lea     rcx, [rbp+240h+var_240]; unsigned __int16 *
0x1800077ab  mov     [rsp+340h+DeviceInfoData], rax
0x1800077b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800077b5  lea     r9, [rsp+340h+var_300]; lParam
0x1800077ba  mov     [rsp+340h+var_2D8], rdi
0x1800077bf  xor     r8d, r8d; wParam
0x1800077c2  mov     edx, 104Dh; Msg
0x1800077c7  mov     rcx, r15; hWnd
0x1800077ca  call    cs:__imp_SendMessageW
0x1800077d0  mov     rdi, [rdi+50h]
0x1800077d4  cmp     rdi, [rsi+30h]
0x1800077d8  jnz     loc_180007672
0x1800077de  xor     edx, edx; Val
0x1800077e0  lea     rcx, [rsp+340h+var_300]; void *
0x1800077e5  lea     r8d, [rdx+58h]; Size
0x1800077e9  call    memset_0
0x1800077ee  mov     eax, 3
0x1800077f3  lea     r9, [rsp+340h+var_300]; lParam
0x1800077f8  xor     r8d, r8d; wParam
0x1800077fb  mov     [rsp+340h+var_2F0], eax
0x1800077ff  mov     edx, 102Bh; Msg
0x180007804  mov     [rsp+340h+var_2F4], eax
0x180007808  mov     rcx, r15; hWnd
0x18000780b  call    cs:__imp_SendMessageW
0x180007811  xor     r9d, r9d; lParam
0x180007814  xor     r8d, r8d; wParam
0x180007817  mov     edx, 1013h; Msg
0x18000781c  mov     rcx, r15; hWnd
0x18000781f  call    cs:__imp_SendMessageW
0x180007825  mov     r9d, 0FFFEh; lParam
0x18000782b  xor     r8d, r8d; wParam
0x18000782e  mov     edx, 101Eh; Msg
0x180007833  mov     rcx, r15; hWnd
0x180007836  call    cs:__imp_SendMessageW
0x18000783c  xor     r9d, r9d; lParam
0x18000783f  mov     rcx, r15; hWnd
0x180007842  lea     ebx, [r9+1]
0x180007846  mov     r8d, ebx; wParam
0x180007849  lea     edx, [rbx+0Ah]; Msg
0x18000784c  call    cs:__imp_SendMessageW
0x180007852  mov     eax, ebx
0x180007854  mov     rcx, [rbp+240h+var_30]
0x18000785b  xor     rcx, rsp; StackCookie
0x18000785e  call    __security_check_cookie
0x180007863  lea     r11, [rsp+340h+var_20]
0x18000786b  mov     rbx, [r11+40h]
0x18000786f  mov     rsi, [r11+48h]
0x180007873  mov     rsp, r11
0x180007876  pop     r15
0x180007878  pop     r14
0x18000787a  pop     r12
0x18000787c  pop     rdi
0x18000787d  pop     rbp
0x18000787e  retn
```
