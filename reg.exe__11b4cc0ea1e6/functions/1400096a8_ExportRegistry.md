# ExportRegistry

- ea: `0x1400096a8`
- end: `0x140009985`
- name: `ExportRegistry`
- size: `733`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002070`
- `0x140002234`
- `0x140002a28`
- `0x140002b70`
- `0x140002f30`
- `0x1400096a8`
- `0x140009ae4`
- `0x14000a934`
- `0x14000cd48`
- `0x14000da24`
- `0x14000dbe8`
- `0x14000dc24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009799`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009799`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400097b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400097b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000987b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000987b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009940`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400098d9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400098d9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400097f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400097f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009801`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1400098bf`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1400098bf`

## pseudocode

```c
__int64 __fastcall ExportRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // ebx
  BOOL v7; // r12d
  LSTATUS v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // esi
  const WCHAR *v12; // r14
  HANDLE FileW; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  const WCHAR *v16; // r15
  int v17; // eax
  __int64 v18; // rdx
  __int64 ResString2FromModule; // rax
  const WCHAR *TemporaryFileName; // rax
  const WCHAR *v21; // r15
  BOOL v22; // eax
  unsigned int v23; // r14d
  FILE *v24; // rax
  FILE *v25; // rax
  int v26; // [rsp+40h] [rbp-89h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v28[4]; // [rsp+50h] [rbp-79h] BYREF
  int v29; // [rsp+54h] [rbp-75h]
  HKEY hKey; // [rsp+58h] [rbp-71h]
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-29h]
  const WCHAR *v32; // [rsp+A8h] [rbp-21h]
  LPCWSTR lpFileName; // [rsp+B0h] [rbp-19h]
  const WCHAR *v34; // [rsp+B8h] [rbp-11h]
  int v35; // [rsp+DCh] [rbp+13h]

  phkResult = 0;
  v29 = 0;
  memset_0(v28, 0, 0x94u);
  v26 = 0;
  if ( a1 && a2 )
  {
    InitGlobalData(9, v28);
    if ( !(unsigned int)ParseExportCmdLine(a1, a2, v28, &v26) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_7:
      FreeGlobalData(v28);
      return v5;
    }
    if ( v26 == 1 )
    {
      Usage(9);
      v5 = 0;
      goto LABEL_7;
    }
    v7 = 1;
    v8 = RegOpenKeyExW(hKey, lpSubKey, 0, v35 | 0x20019, &phkResult);
    v10 = v8;
    v11 = 2;
    if ( v8 )
    {
      if ( v8 == 6 )
      {
        v18 = 801;
        goto LABEL_17;
      }
LABEL_15:
      if ( v10 != 1223 )
      {
        v18 = v10;
        if ( v7 )
        {
          SaveErrorMessage(v10);
          goto LABEL_30;
        }
LABEL_17:
        ResString2FromModule = GetResString2FromModule(v9, v18, 0);
        SetReason(ResString2FromModule);
LABEL_30:
        v23 = 1;
        goto LABEL_26;
      }
LABEL_25:
      SaveErrorMessage(v10);
      v23 = 0;
      v11 = 1;
LABEL_26:
      v24 = o___acrt_iob_func_0(v11);
      ShowLastErrorEx(v24);
      FreeGlobalData(v28);
      return v23;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v12 = lpFileName;
    FileW = CreateFileW(lpFileName, 0xC0010000, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( GetLastError() != 2 )
        goto LABEL_21;
      v10 = 0;
    }
    else
    {
      CloseHandle(FileW);
      GetResString2FromModule(v14, 206, 1);
      v16 = (const WCHAR *)GetResString2FromModule(v15, 207, 0);
      do
        v17 = Prompt(v16);
      while ( v17 > 2 );
      v9 = (unsigned int)(1 - v17);
      v10 = v17 != 1 ? 0x4C7 : 0;
      if ( v17 != 1 )
        goto LABEL_15;
    }
    v34 = v12;
    TemporaryFileName = (const WCHAR *)GetTemporaryFileName(v12);
    lpFileName = TemporaryFileName;
    v21 = TemporaryFileName;
    if ( TemporaryFileName )
    {
      ExportWinNT50RegFile(TemporaryFileName, v32, v35);
      v22 = CopyFileW(v21, v12, 0);
      if ( !v22 )
        v10 = 802;
      v7 = v22;
      DeleteFileW(v21);
      if ( !v10 )
        goto LABEL_25;
      goto LABEL_15;
    }
LABEL_21:
    v18 = 802;
    goto LABEL_17;
  }
  SetLastError(0x57u);
  v25 = o___acrt_iob_func_0(2u);
  ShowLastError(v25);
  return 1;
}

```

## disassembly

```asm
0x1400096a8  mov     [rsp-8+arg_10], rbx
0x1400096ad  mov     [rsp-8+arg_18], rsi
0x1400096b2  push    rbp
0x1400096b3  push    rdi
0x1400096b4  push    r12
0x1400096b6  push    r14
0x1400096b8  push    r15
0x1400096ba  lea     rbp, [rsp-37h]
0x1400096bf  sub     rsp, 100h
0x1400096c6  mov     rax, cs:__security_cookie
0x1400096cd  xor     rax, rsp
0x1400096d0  mov     [rbp+57h+var_30], rax
0x1400096d4  mov     rbx, rdx
0x1400096d7  mov     [rsp+120h+var_D8], 0
0x1400096e0  mov     edi, ecx
0x1400096e2  xor     eax, eax
0x1400096e4  xor     edx, edx; Val
0x1400096e6  mov     [rbp+57h+var_CC], eax
0x1400096e9  lea     rcx, [rbp+57h+var_D0]; void *
0x1400096ed  mov     r8d, 94h; Size
0x1400096f3  call    memset_0
0x1400096f8  mov     [rsp+120h+var_E0], 0
0x140009700  test    edi, edi
0x140009702  jz      loc_14000993B
0x140009708  test    rbx, rbx
0x14000970b  jz      loc_14000993B
0x140009711  mov     esi, 9
0x140009716  lea     rdx, [rbp+57h+var_D0]
0x14000971a  mov     ecx, esi
0x14000971c  call    InitGlobalData
0x140009721  lea     r9, [rsp+120h+var_E0]
0x140009726  mov     rdx, rbx
0x140009729  lea     r8, [rbp+57h+var_D0]
0x14000972d  mov     ecx, edi
0x14000972f  call    ParseExportCmdLine
0x140009734  test    eax, eax
0x140009736  jnz     short loc_140009752
0x140009738  lea     ecx, [rsi-7]; Ix
0x14000973b  call    _o___acrt_iob_func_0
0x140009740  mov     rcx, rax
0x140009743  mov     edx, 20000h
0x140009748  call    ShowLastErrorEx
0x14000974d  lea     ebx, [rsi-8]
0x140009750  jmp     short loc_140009766
0x140009752  mov     ebx, 1
0x140009757  cmp     [rsp+120h+var_E0], ebx
0x14000975b  jnz     short loc_140009776
0x14000975d  mov     ecx, esi
0x14000975f  call    Usage
0x140009764  xor     ebx, ebx
0x140009766  lea     rcx, [rbp+57h+var_D0]
0x14000976a  call    FreeGlobalData
0x14000976f  mov     eax, ebx
0x140009771  jmp     loc_14000995D
0x140009776  mov     r9d, [rbp+57h+var_44]
0x14000977a  lea     rax, [rsp+120h+var_D8]
0x14000977f  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140009783  or      r9d, 20019h; samDesired
0x14000978a  mov     rcx, [rbp+57h+hKey]; hKey
0x14000978e  xor     r8d, r8d; ulOptions
0x140009791  mov     r12d, ebx
0x140009794  mov     [rsp+120h+phkResult], rax; phkResult
0x140009799  call    cs:__imp_RegOpenKeyExW
0x14000979f  mov     edi, eax
0x1400097a1  mov     esi, 2
0x1400097a6  test    eax, eax
0x1400097a8  jnz     loc_140009917
0x1400097ae  mov     rcx, [rsp+120h+var_D8]; hKey
0x1400097b3  test    rcx, rcx
0x1400097b6  jz      short loc_1400097C7
0x1400097b8  call    cs:__imp_RegCloseKey
0x1400097be  mov     [rsp+120h+var_D8], 0
0x1400097c7  mov     r14, [rbp+57h+lpFileName]
0x1400097cb  xor     r9d, r9d; lpSecurityAttributes
0x1400097ce  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x1400097d7  mov     rcx, r14; lpFileName
0x1400097da  mov     [rsp+120h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400097e2  xor     r8d, r8d; dwShareMode
0x1400097e5  mov     edx, 0C0010000h; dwDesiredAccess
0x1400097ea  mov     dword ptr [rsp+120h+phkResult], 3; dwCreationDisposition
0x1400097f2  call    cs:__imp_CreateFileW
0x1400097f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400097fc  jz      short loc_14000987B
0x1400097fe  mov     rcx, rax; hObject
0x140009801  call    cs:__imp_CloseHandle
0x140009807  mov     r8d, ebx
0x14000980a  mov     edx, 0CEh
0x14000980f  call    GetResString2FromModule
0x140009814  xor     r8d, r8d
0x140009817  mov     edx, 0CFh
0x14000981c  mov     rdi, rax
0x14000981f  call    GetResString2FromModule
0x140009824  mov     r15, rax
0x140009827  mov     r9d, [rbp+57h+var_B8]
0x14000982b  mov     r8, rdi
0x14000982e  mov     rdx, r14
0x140009831  mov     rcx, r15
0x140009834  call    Prompt
0x140009839  cmp     eax, esi
0x14000983b  jg      short loc_140009827
0x14000983d  mov     ecx, eax
0x14000983f  sub     ecx, ebx
0x140009841  neg     ecx
0x140009843  sbb     edi, edi
0x140009845  and     edi, 4C7h
0x14000984b  cmp     eax, ebx
0x14000984d  jz      short loc_140009887
0x14000984f  cmp     edi, 4C7h
0x140009855  jz      loc_1400098E7
0x14000985b  mov     edx, edi
0x14000985d  test    r12d, r12d
0x140009860  jnz     loc_14000992A
0x140009866  xor     r8d, r8d
0x140009869  call    GetResString2FromModule
0x14000986e  mov     rcx, rax
0x140009871  call    SetReason
0x140009876  jmp     loc_140009931
0x14000987b  call    cs:__imp_GetLastError
0x140009881  cmp     eax, esi
0x140009883  jnz     short loc_14000989F
0x140009885  xor     edi, edi
0x140009887  mov     rcx, r14; lpString
0x14000988a  mov     [rbp+57h+var_68], r14
0x14000988e  call    GetTemporaryFileName
0x140009893  mov     [rbp+57h+lpFileName], rax
0x140009897  mov     r15, rax
0x14000989a  test    rax, rax
0x14000989d  jnz     short loc_1400098A6
0x14000989f  mov     edx, 322h
0x1400098a4  jmp     short loc_140009866
0x1400098a6  mov     r8d, [rbp+57h+var_44]
0x1400098aa  mov     rcx, r15; lpFileName
0x1400098ad  mov     rdx, [rbp+57h+var_78]
0x1400098b1  call    ExportWinNT50RegFile
0x1400098b6  xor     r8d, r8d; bFailIfExists
0x1400098b9  mov     rdx, r14; lpNewFileName
0x1400098bc  mov     rcx, r15; lpExistingFileName
0x1400098bf  call    cs:__imp_CopyFileW
0x1400098c5  mov     edx, 322h
0x1400098ca  mov     rcx, r15; lpFileName
0x1400098cd  test    eax, eax
0x1400098cf  cmovz   edi, edx
0x1400098d2  neg     eax
0x1400098d4  sbb     eax, eax
0x1400098d6  and     r12d, eax
0x1400098d9  call    cs:__imp_DeleteFileW
0x1400098df  test    edi, edi
0x1400098e1  jnz     loc_14000984F
0x1400098e7  mov     ecx, edi
0x1400098e9  call    SaveErrorMessage
0x1400098ee  xor     r14d, r14d
0x1400098f1  mov     edi, 20000h
0x1400098f6  mov     esi, ebx
0x1400098f8  mov     ecx, esi; Ix
0x1400098fa  call    _o___acrt_iob_func_0
0x1400098ff  mov     rcx, rax
0x140009902  mov     edx, edi
0x140009904  call    ShowLastErrorEx
0x140009909  lea     rcx, [rbp+57h+var_D0]
0x14000990d  call    FreeGlobalData
0x140009912  mov     eax, r14d
0x140009915  jmp     short loc_14000995D
0x140009917  cmp     eax, 6
0x14000991a  jnz     loc_14000984F
0x140009920  mov     edx, 321h
0x140009925  jmp     loc_140009866
0x14000992a  mov     ecx, edi
0x14000992c  call    SaveErrorMessage
0x140009931  mov     r14d, ebx
0x140009934  mov     edi, 20001h
0x140009939  jmp     short loc_1400098F8
0x14000993b  mov     ecx, 57h ; 'W'; dwErrCode
0x140009940  call    cs:__imp_SetLastError
0x140009946  mov     ecx, 2; Ix
0x14000994b  call    _o___acrt_iob_func_0
0x140009950  mov     rcx, rax
0x140009953  call    ShowLastError
0x140009958  mov     eax, 1
0x14000995d  mov     rcx, [rbp+57h+var_30]
0x140009961  xor     rcx, rsp; StackCookie
0x140009964  call    __security_check_cookie
0x140009969  lea     r11, [rsp+120h+var_20]
0x140009971  mov     rbx, [r11+40h]
0x140009975  mov     rsi, [r11+48h]
0x140009979  mov     rsp, r11
0x14000997c  pop     r15
0x14000997e  pop     r14
0x140009980  pop     r12
0x140009982  pop     rdi
0x140009983  pop     rbp
0x140009984  retn
```
