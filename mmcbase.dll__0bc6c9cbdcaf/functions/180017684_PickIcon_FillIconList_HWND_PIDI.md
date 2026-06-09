# PickIcon_FillIconList(HWND__ *,PIDI *)

- ea: `0x180017684`
- end: `0x180017abc`
- name: `?PickIcon_FillIconList@@YAXPEAUHWND__@@PEAUPIDI@@@Z`
- size: `1080`
- prototype: `void __fastcall(HWND hDlg, struct PIDI *)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017b5c`
- `0x180017d5c`
- `0x180017e40`

## callees

- `0x1800023e0`
- `0x180003b60`
- `0x180003c40`
- `0x180003f10`
- `0x1800041f0`
- `0x1800064b4`
- `0x180007978`
- `0x1800082a0`
- `0x180008630`
- `0x180014820`
- `0x180014d60`
- `0x180017684`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800177c3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800177c3`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180017852`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180017852`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800179c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800179ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800179c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800179ec`
- `USER32!InvalidateRect` at `0x180017a6a`
- `USER32!InvalidateRect` at `0x180017a6a`
- `USER32!SetDlgItemTextW` at `0x180017a5b`
- `USER32!SetDlgItemTextW` at `0x180017a5b`
- `USER32!GetDlgItemTextW` at `0x1800177af`
- `USER32!GetDlgItemTextW` at `0x1800177af`
- `USER32!SendMessageW` at `0x18001777d`
- `USER32!SendMessageW` at `0x180017791`
- `USER32!SendMessageW` at `0x180017922`
- `USER32!SendMessageW` at `0x18001793e`
- `USER32!SendMessageW` at `0x18001795c`
- `USER32!SendMessageW` at `0x180017972`
- `USER32!SendMessageW` at `0x180017986`
- `USER32!SendMessageW` at `0x18001777d`
- `USER32!SendMessageW` at `0x180017791`
- `USER32!SendMessageW` at `0x180017922`
- `USER32!SendMessageW` at `0x18001793e`
- `USER32!SendMessageW` at `0x18001795c`
- `USER32!SendMessageW` at `0x180017972`
- `USER32!SendMessageW` at `0x180017986`
- `USER32!IsWindow` at `0x180017753`
- `USER32!IsWindow` at `0x180017753`
- `USER32!LoadCursorW` at `0x180017728`
- `USER32!LoadCursorW` at `0x180017728`
- `USER32!SetCursor` at `0x180017731`
- `USER32!SetCursor` at `0x180017a73`
- `USER32!SetCursor` at `0x180017731`
- `USER32!SetCursor` at `0x180017a73`
- `USER32!GetSystemMetrics` at `0x180017766`
- `USER32!GetSystemMetrics` at `0x180017766`
- `USER32!GetDlgItem` at `0x180017747`
- `USER32!GetDlgItem` at `0x180017747`
- `SHELL32!ExtractIconExW` at `0x1800178c2`
- `SHELL32!ExtractIconExW` at `0x180017901`
- `SHELL32!ExtractIconExW` at `0x1800178c2`
- `SHELL32!ExtractIconExW` at `0x180017901`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PickIcon_FillIconList(HWND hDlg, WCHAR *a2)
{
  int v4; // ecx
  HCURSOR CursorW; // rax
  HCURSOR v6; // r14
  HWND DlgItem; // rbx
  int SystemMetrics; // eax
  DWORD v9; // eax
  unsigned int v10; // eax
  unsigned __int16 *v11; // rdi
  signed int Icon; // eax
  unsigned int v13; // r8d
  UINT v14; // esi
  CHeapFactory *v15; // rcx
  HICON *v16; // rax
  HICON *v17; // r14
  signed int v18; // r15d
  CHeapFactory *v19; // rcx
  __int64 i; // rsi
  int v21; // eax
  int v22; // esi
  int v23; // eax
  int v24; // eax
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh]
  __int128 v27; // [rsp+38h] [rbp-C8h]
  HCURSOR v28; // [rsp+48h] [rbp-B8h]
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+54h] [rbp-ACh]
  __int128 v31; // [rsp+58h] [rbp-A8h]
  _DWORD v32[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h]
  WCHAR Dst[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR String[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v27 = 0;
  ++mmcerror::SC::s_CallDepth;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v25, L"PickIcon_FillIconList");
  v4 = -2147024809;
  if ( a2 )
    v4 = 0;
  v31 = 0;
  v29 = 3;
  v30 = v4;
  v25 = 3;
  v26 = v4;
  mmcerror::SC::Trace_((mmcerror::SC *)&v29);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(&v25) )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v6 = SetCursor(CursorW);
    v28 = v6;
    DlgItem = GetDlgItem(hDlg, 1006);
    if ( IsWindow(DlgItem) )
    {
      SystemMetrics = GetSystemMetrics(11);
      SendMessageW(DlgItem, 0x195u, SystemMetrics + 12, 0);
      SendMessageW(DlgItem, 0x184u, 0, 0);
      GetDlgItemTextW(hDlg, 1005, String, 260);
      v9 = ExpandEnvironmentStringsW(String, Dst, 0x104u);
      if ( !v9 )
      {
        mmcerror::SC::FromLastError((mmcerror::SC *)&v25);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v10 = mmcerror::SC::ToHr((mmcerror::SC *)&v25);
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_b07d5ff86492368aca710dc972e57768_Traceguids, v10);
        }
        goto LABEL_34;
      }
      if ( v9 > 0x104 )
        Dst[259] = 0;
      v11 = a2 + 12;
      if ( !SearchPathW(0, Dst, 0, 0x104u, a2 + 12, 0) )
      {
        v33 = 0;
        ++mmcerror::SC::s_CallDepth;
        v32[0] = 1;
        v32[1] = 2;
        v31 = 0;
        v29 = 1;
        v30 = 2;
        MMCErrorBox(&v29, 16);
        --mmcerror::SC::s_CallDepth;
        mmcerror::SC::Trace_((mmcerror::SC *)v32);
      }
      Icon = ExtractIconExW(a2 + 12, 0, 0, 0, 0);
      v14 = Icon;
      v15 = (CHeapFactory *)(unsigned int)(Icon - 1);
      if ( (unsigned int)v15 <= 0x7FFFFFFD )
      {
        v16 = (HICON *)CHeapFactory::Alloc(v15, 8LL * Icon, v13);
        v17 = v16;
        if ( v16 )
        {
          v18 = ExtractIconExW(a2 + 12, 0, v16, 0, v14);
          v19 = (CHeapFactory *)(unsigned int)(v18 - 1);
          if ( (unsigned int)v19 <= 0x7FFFFFFD )
          {
            SendMessageW(DlgItem, 0xBu, 0, 0);
            for ( i = 0; (int)i < v18; i = (unsigned int)(i + 1) )
              SendMessageW(DlgItem, 0x180u, 0, (LPARAM)v17[i]);
            if ( (unsigned int)SendMessageW(DlgItem, 0x186u, *((int *)a2 + 3), 0) == -1 )
              SendMessageW(DlgItem, 0x186u, 0, 0);
            SendMessageW(DlgItem, 0xBu, 1u, 0);
          }
          CHeapFactory::Free(v19, v17);
        }
        v6 = v28;
      }
      v21 = CompareStringW(0x400u, 0, Dst, 260, String, 260);
      v22 = v21;
      if ( v21 == 1004 || v21 == 87 || (v23 = CompareStringW(0x400u, 0, Dst, 260, v11, 260), v23 == 1004) || v23 == 87 )
      {
        v25 = 3;
        v26 = -2147418113;
      }
      else
      {
        if ( v22 == 2 )
          goto LABEL_33;
        if ( v23 != 2 )
          goto LABEL_33;
        v24 = StringCchCopyW(v11, 0x104u, String);
        v25 = 3;
        v26 = v24;
        if ( !(unsigned __int8)mmcerror::SC::operator bool(&v25) )
          goto LABEL_33;
      }
      mmcerror::SC::TraceAndClear((mmcerror::SC *)&v25);
LABEL_33:
      SetDlgItemTextW(hDlg, 1005, v11);
      InvalidateRect(DlgItem, 0, 1);
      SetCursor(v6);
    }
  }
LABEL_34:
  --mmcerror::SC::s_CallDepth;
  mmcerror::SC::Trace_((mmcerror::SC *)&v25);
}

```

## disassembly

```asm
0x180017684  mov     [rsp-8+arg_10], rbx
0x180017689  push    rbp
0x18001768a  push    rsi
0x18001768b  push    rdi
0x18001768c  push    r12
0x18001768e  push    r13
0x180017690  push    r14
0x180017692  push    r15
0x180017694  lea     rbp, [rsp-3C0h]
0x18001769c  sub     rsp, 4C0h
0x1800176a3  mov     rax, cs:__security_cookie
0x1800176aa  xor     rax, rsp
0x1800176ad  mov     [rbp+3F0h+var_40], rax
0x1800176b4  mov     r13, rdx
0x1800176b7  mov     r12, rcx
0x1800176ba  xorps   xmm0, xmm0
0x1800176bd  movdqu  [rsp+4F0h+var_4B8], xmm0
0x1800176c3  inc     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1800176c9  lea     rdx, aPickiconFillic; "PickIcon_FillIconList"
0x1800176d0  lea     rcx, [rsp+4F0h+var_4C0]; this
0x1800176d5  call    ?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800176da  mov     ecx, 80070057h
0x1800176df  xor     eax, eax
0x1800176e1  test    r13, r13
0x1800176e4  cmovnz  ecx, eax
0x1800176e7  xorps   xmm0, xmm0
0x1800176ea  movdqu  [rsp+4F0h+var_498], xmm0
0x1800176f0  mov     eax, 3
0x1800176f5  mov     [rsp+4F0h+var_4A0], eax
0x1800176f9  mov     [rsp+4F0h+var_49C], ecx
0x1800176fd  mov     [rsp+4F0h+var_4C0], eax
0x180017701  mov     [rsp+4F0h+var_4BC], ecx
0x180017705  lea     rcx, [rsp+4F0h+var_4A0]; this
0x18001770a  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x18001770f  lea     rcx, [rsp+4F0h+var_4C0]
0x180017714  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180017719  test    al, al
0x18001771b  jnz     loc_180017A7A
0x180017721  mov     edx, 7F02h; lpCursorName
0x180017726  xor     ecx, ecx; hInstance
0x180017728  call    cs:__imp_LoadCursorW
0x18001772e  mov     rcx, rax; hCursor
0x180017731  call    cs:__imp_SetCursor
0x180017737  mov     r14, rax
0x18001773a  mov     [rsp+4F0h+var_4A8], rax
0x18001773f  mov     edx, 3EEh; nIDDlgItem
0x180017744  mov     rcx, r12; hDlg
0x180017747  call    cs:__imp_GetDlgItem
0x18001774d  mov     rbx, rax
0x180017750  mov     rcx, rax; hWnd
0x180017753  call    cs:__imp_IsWindow
0x180017759  test    eax, eax
0x18001775b  jz      loc_180017A7A
0x180017761  mov     ecx, 0Bh; nIndex
0x180017766  call    cs:__imp_GetSystemMetrics
0x18001776c  add     eax, 0Ch
0x18001776f  movsxd  r8, eax; wParam
0x180017772  xor     r9d, r9d; lParam
0x180017775  mov     edx, 195h; Msg
0x18001777a  mov     rcx, rbx; hWnd
0x18001777d  call    cs:__imp_SendMessageW
0x180017783  xor     r9d, r9d; lParam
0x180017786  xor     r8d, r8d; wParam
0x180017789  mov     edx, 184h; Msg
0x18001778e  mov     rcx, rbx; hWnd
0x180017791  call    cs:__imp_SendMessageW
0x180017797  mov     r15d, 104h
0x18001779d  mov     r9d, r15d; cchMax
0x1800177a0  lea     r8, [rbp+3F0h+String]; lpString
0x1800177a7  mov     edx, 3EDh; nIDDlgItem
0x1800177ac  mov     rcx, r12; hDlg
0x1800177af  call    cs:__imp_GetDlgItemTextW
0x1800177b5  mov     r8d, r15d; nSize
0x1800177b8  lea     rdx, [rbp+3F0h+Dst]; lpDst
0x1800177bc  lea     rcx, [rbp+3F0h+String]; lpSrc
0x1800177c3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800177c9  test    eax, eax
0x1800177cb  jnz     short loc_180017826
0x1800177cd  lea     rcx, [rsp+4F0h+var_4C0]; this
0x1800177d2  call    ?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x1800177d7  lea     rcx, WPP_GLOBAL_Control
0x1800177de  mov     rax, cs:WPP_GLOBAL_Control
0x1800177e5  cmp     rax, rcx
0x1800177e8  jz      loc_180017A7A
0x1800177ee  cmp     byte ptr [rax+19h], 2
0x1800177f2  jb      loc_180017A7A
0x1800177f8  lea     rcx, [rsp+4F0h+var_4C0]; this
0x1800177fd  call    ?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180017802  mov     edx, 0Ah
0x180017807  mov     r9d, eax
0x18001780a  lea     r8, WPP_b07d5ff86492368aca710dc972e57768_Traceguids
0x180017811  mov     rcx, cs:WPP_GLOBAL_Control
0x180017818  mov     rcx, [rcx+10h]
0x18001781c  call    WPP_SF_d
0x180017821  jmp     loc_180017A7A
0x180017826  cmp     eax, r15d
0x180017829  jbe     short loc_180017834
0x18001782b  xor     eax, eax
0x18001782d  mov     [rbp+3F0h+var_25A], ax
0x180017834  lea     rdi, [r13+18h]
0x180017838  mov     [rsp+4F0h+lpFilePart], 0; lpFilePart
0x180017841  mov     [rsp+4F0h+lpBuffer], rdi; lpBuffer
0x180017846  mov     r9d, r15d; nBufferLength
0x180017849  xor     r8d, r8d; lpExtension
0x18001784c  lea     rdx, [rbp+3F0h+Dst]; lpFileName
0x180017850  xor     ecx, ecx; lpPath
0x180017852  call    cs:__imp_SearchPathW
0x180017858  test    eax, eax
0x18001785a  jnz     short loc_1800178AF
0x18001785c  xorps   xmm0, xmm0
0x18001785f  movdqu  [rsp+4F0h+var_480], xmm0
0x180017865  inc     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x18001786b  mov     [rsp+4F0h+var_488], 1
0x180017873  mov     [rsp+4F0h+var_484], 2
0x18001787b  movdqu  [rsp+4F0h+var_498], xmm0
0x180017881  mov     [rsp+4F0h+var_4A0], 1
0x180017889  mov     [rsp+4F0h+var_49C], 2
0x180017891  lea     edx, [rax+10h]
0x180017894  lea     rcx, [rsp+4F0h+var_4A0]
0x180017899  call    ?MMCErrorBox@@YAHVSC@mmcerror@@I@Z; MMCErrorBox(mmcerror::SC,uint)
0x18001789e  nop
0x18001789f  dec     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1800178a5  lea     rcx, [rsp+4F0h+var_488]; this
0x1800178aa  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x1800178af  mov     dword ptr [rsp+4F0h+lpBuffer], 0; nIcons
0x1800178b7  xor     r9d, r9d; phiconSmall
0x1800178ba  xor     r8d, r8d; phiconLarge
0x1800178bd  xor     edx, edx; nIconIndex
0x1800178bf  mov     rcx, rdi; lpszFile
0x1800178c2  call    cs:__imp_ExtractIconExW
0x1800178c8  movsxd  rsi, eax
0x1800178cb  lea     ecx, [rsi-1]; this
0x1800178ce  cmp     ecx, 7FFFFFFDh
0x1800178d4  ja      loc_18001799F
0x1800178da  mov     rdx, rsi
0x1800178dd  shl     rdx, 3; unsigned __int64
0x1800178e1  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x1800178e6  mov     r14, rax
0x1800178e9  test    rax, rax
0x1800178ec  jz      loc_18001799A
0x1800178f2  mov     dword ptr [rsp+4F0h+lpBuffer], esi; nIcons
0x1800178f6  xor     r9d, r9d; phiconSmall
0x1800178f9  mov     r8, rax; phiconLarge
0x1800178fc  xor     edx, edx; nIconIndex
0x1800178fe  mov     rcx, rdi; lpszFile
0x180017901  call    cs:__imp_ExtractIconExW
0x180017907  mov     r15d, eax
0x18001790a  lea     ecx, [rax-1]
0x18001790d  cmp     ecx, 7FFFFFFDh
0x180017913  ja      short loc_18001798C
0x180017915  xor     r9d, r9d; lParam
0x180017918  xor     r8d, r8d; wParam
0x18001791b  lea     edx, [r9+0Bh]; Msg
0x18001791f  mov     rcx, rbx; hWnd
0x180017922  call    cs:__imp_SendMessageW
0x180017928  xor     esi, esi
0x18001792a  test    r15d, r15d
0x18001792d  jle     short loc_18001794B
0x18001792f  mov     r9, [r14+rsi*8]; lParam
0x180017933  xor     r8d, r8d; wParam
0x180017936  mov     edx, 180h; Msg
0x18001793b  mov     rcx, rbx; hWnd
0x18001793e  call    cs:__imp_SendMessageW
0x180017944  inc     esi
0x180017946  cmp     esi, r15d
0x180017949  jl      short loc_18001792F
0x18001794b  movsxd  r8, dword ptr [r13+0Ch]; wParam
0x18001794f  xor     r9d, r9d; lParam
0x180017952  mov     esi, 186h
0x180017957  mov     edx, esi; Msg
0x180017959  mov     rcx, rbx; hWnd
0x18001795c  call    cs:__imp_SendMessageW
0x180017962  cmp     eax, 0FFFFFFFFh
0x180017965  jnz     short loc_180017978
0x180017967  xor     r9d, r9d; lParam
0x18001796a  xor     r8d, r8d; wParam
0x18001796d  mov     edx, esi; Msg
0x18001796f  mov     rcx, rbx; hWnd
0x180017972  call    cs:__imp_SendMessageW
0x180017978  xor     r9d, r9d; lParam
0x18001797b  lea     edx, [r9+0Bh]; Msg
0x18001797f  lea     r8d, [r9+1]; wParam
0x180017983  mov     rcx, rbx; hWnd
0x180017986  call    cs:__imp_SendMessageW
0x18001798c  mov     rdx, r14; void *
0x18001798f  call    ?Free@CHeapFactory@@QEAAHPEAX@Z; CHeapFactory::Free(void *)
0x180017994  mov     r15d, 104h
0x18001799a  mov     r14, [rsp+4F0h+var_4A8]
0x18001799f  mov     dword ptr [rsp+4F0h+lpFilePart], r15d; cchCount2
0x1800179a4  lea     rax, [rbp+3F0h+String]
0x1800179ab  mov     [rsp+4F0h+lpBuffer], rax; lpString2
0x1800179b0  mov     r9d, r15d; cchCount1
0x1800179b3  lea     r8, [rbp+3F0h+Dst]; lpString1
0x1800179b7  xor     edx, edx; dwCmpFlags
0x1800179b9  mov     r13d, 400h
0x1800179bf  mov     ecx, r13d; Locale
0x1800179c2  call    cs:__imp_CompareStringW
0x1800179c8  mov     esi, eax
0x1800179ca  cmp     eax, 3ECh
0x1800179cf  jz      short loc_180017A36
0x1800179d1  cmp     eax, 57h ; 'W'
0x1800179d4  jz      short loc_180017A36
0x1800179d6  mov     dword ptr [rsp+4F0h+lpFilePart], r15d; cchCount2
0x1800179db  mov     [rsp+4F0h+lpBuffer], rdi; lpString2
0x1800179e0  mov     r9d, r15d; cchCount1
0x1800179e3  lea     r8, [rbp+3F0h+Dst]; lpString1
0x1800179e7  xor     edx, edx; dwCmpFlags
0x1800179e9  mov     ecx, r13d; Locale
0x1800179ec  call    cs:__imp_CompareStringW
0x1800179f2  cmp     eax, 3ECh
0x1800179f7  jz      short loc_180017A36
0x1800179f9  cmp     eax, 57h ; 'W'
0x1800179fc  jz      short loc_180017A36
0x1800179fe  cmp     esi, 2
0x180017a01  jz      short loc_180017A50
0x180017a03  cmp     eax, 2
0x180017a06  jnz     short loc_180017A50
0x180017a08  lea     r8, [rbp+3F0h+String]; unsigned __int16 *
0x180017a0f  mov     rdx, r15; unsigned __int64
0x180017a12  mov     rcx, rdi; unsigned __int16 *
0x180017a15  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a1a  mov     [rsp+4F0h+var_4C0], 3
0x180017a22  mov     [rsp+4F0h+var_4BC], eax
0x180017a26  lea     rcx, [rsp+4F0h+var_4C0]
0x180017a2b  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180017a30  test    al, al
0x180017a32  jz      short loc_180017A50
0x180017a34  jmp     short loc_180017A46
0x180017a36  mov     [rsp+4F0h+var_4C0], 3
0x180017a3e  mov     [rsp+4F0h+var_4BC], 8000FFFFh
0x180017a46  lea     rcx, [rsp+4F0h+var_4C0]; this
0x180017a4b  call    ?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x180017a50  mov     r8, rdi; lpString
0x180017a53  mov     edx, 3EDh; nIDDlgItem
0x180017a58  mov     rcx, r12; hDlg
0x180017a5b  call    cs:__imp_SetDlgItemTextW
0x180017a61  xor     edx, edx; lpRect
0x180017a63  lea     r8d, [rdx+1]; bErase
0x180017a67  mov     rcx, rbx; hWnd
0x180017a6a  call    cs:__imp_InvalidateRect
0x180017a70  mov     rcx, r14; hCursor
0x180017a73  call    cs:__imp_SetCursor
0x180017a79  nop
0x180017a7a  mov     eax, cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180017a80  dec     eax
0x180017a82  lea     rcx, [rsp+4F0h+var_4C0]; this
0x180017a87  mov     cs:?s_CallDepth@SC@mmcerror@@0IA, eax; uint mmcerror::SC::s_CallDepth
0x180017a8d  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x180017a92  mov     rcx, [rbp+3F0h+var_40]
0x180017a99  xor     rcx, rsp; StackCookie
0x180017a9c  call    __security_check_cookie
0x180017aa1  mov     rbx, [rsp+4F0h+arg_10]
0x180017aa9  add     rsp, 4C0h
0x180017ab0  pop     r15
0x180017ab2  pop     r14
0x180017ab4  pop     r13
0x180017ab6  pop     r12
0x180017ab8  pop     rdi
0x180017ab9  pop     rsi
0x180017aba  pop     rbp
0x180017abb  retn
```
