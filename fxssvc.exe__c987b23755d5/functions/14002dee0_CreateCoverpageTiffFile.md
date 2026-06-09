# CreateCoverpageTiffFile

- ea: `0x14002dee0`
- end: `0x14002e2d6`
- name: `CreateCoverpageTiffFile`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x14002e2dc`

## callees

- `0x140002c43`
- `0x140004a30`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14002dee0`
- `0x140030e88`
- `0x1400313d8`
- `0x140065dbc`
- `0x14006dddc`
- `0x14006e6dc`
- `0x140079000`
- `0x14007912c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002dfa9`
- `KERNEL32!GetLastError` at `0x14002e00a`
- `KERNEL32!GetLastError` at `0x14002e0c5`
- `KERNEL32!GetLastError` at `0x14002e1bb`
- `KERNEL32!GetLastError` at `0x14002e26f`
- `KERNEL32!GetLastError` at `0x14002dfa9`
- `KERNEL32!GetLastError` at `0x14002e00a`
- `KERNEL32!GetLastError` at `0x14002e0c5`
- `KERNEL32!GetLastError` at `0x14002e1bb`
- `KERNEL32!GetLastError` at `0x14002e26f`
- `KERNEL32!SetLastError` at `0x14002e2ad`
- `KERNEL32!SetLastError` at `0x14002e2ad`
- `KERNEL32!DeleteFileW` at `0x14002e18a`
- `KERNEL32!DeleteFileW` at `0x14002e24e`
- `KERNEL32!DeleteFileW` at `0x14002e18a`
- `KERNEL32!DeleteFileW` at `0x14002e24e`

## pseudocode

```c
__int64 __fastcall CreateCoverpageTiffFile(__int16 a1, __int64 a2, const wchar_t *a3, unsigned __int16 *a4)
{
  unsigned __int16 *v8; // rcx
  WCHAR *FaxPrinterName; // r15
  DWORD LastError; // eax
  DWORD v11; // edi
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // esi
  __int64 v15; // rcx
  DWORD v16; // eax
  __int64 v17; // rcx
  __int16 v18; // r9
  DWORD v19; // eax
  char v20; // al
  int v21; // edx
  int v22; // eax
  unsigned __int16 v23; // r14
  __int64 i; // rbx
  __int64 v26[30]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v27[20]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v28; // [rsp+134h] [rbp+34h]
  WCHAR FileName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v30[66]; // [rsp+3B0h] [rbp+2B0h] BYREF

  memset_0(v27, 0, 0x74u);
  memset_0(v26, 0, sizeof(v26));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v8 = *(unsigned __int16 **)(a2 + 8);
  if ( !a3 )
    a3 = L"tif";
  FileName[0] = 0;
  if ( !(unsigned int)ValidateCoverpage(v8) )
  {
    FaxPrinterName = 0;
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v13 = 35;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
LABEL_13:
    v14 = 0;
    goto LABEL_53;
  }
  FillCoverPageFields((const struct _FAX_COVERPAGE_INFOW2 *)a2, (struct _COVERPAGEFIELDS *)v26);
  FaxPrinterName = (WCHAR *)GetFaxPrinterName(v15);
  if ( !FaxPrinterName )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v13 = 36;
    goto LABEL_12;
  }
  v16 = PrintCoverPage(0);
  v11 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(a2 + 8),
        v16);
    }
    goto LABEL_13;
  }
  if ( !GenerateUniqueFileNameWithPrefix(v17, *((const wchar_t **)g_pFaxConfig + 12), 0, a3, FileName) )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v13 = 38;
    goto LABEL_12;
  }
  v18 = 1;
  if ( v28 == 2 )
    v18 = 2;
  v19 = PrintCoverPageToFile((__int64)v30, FileName, FaxPrinterName, v18, a1);
  v11 = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(a2 + 8),
        v19);
    }
    v14 = 0;
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = GetLastError();
      v21 = 40;
LABEL_41:
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)FileName,
        v20);
    }
  }
  else
  {
    v22 = StringCchCopyW(a4, 0x104u, FileName);
    v23 = v22;
    if ( v22 >= 0 )
    {
      v14 = 1;
      goto LABEL_53;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(a2 + 8),
        v22);
    }
    v11 = v23;
    v14 = 0;
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = GetLastError();
      v21 = 42;
      goto LABEL_41;
    }
  }
LABEL_53:
  pMemFree(FaxPrinterName);
  for ( i = 0; i != 29; ++i )
    pMemFree((LPVOID)v26[i + 1]);
  if ( !v14 )
  {
    if ( !v11 )
      v11 = 31;
    SetLastError(v11);
  }
  return v14;
}

```

## disassembly

```asm
0x14002dee0  push    rbp
0x14002dee2  push    rbx
0x14002dee3  push    rsi
0x14002dee4  push    rdi
0x14002dee5  push    r12
0x14002dee7  push    r14
0x14002dee9  push    r15
0x14002deeb  lea     rbp, [rsp-4D0h]
0x14002def3  sub     rsp, 5D0h
0x14002defa  mov     rax, cs:__security_cookie
0x14002df01  xor     rax, rsp
0x14002df04  mov     [rbp+500h+var_40], rax
0x14002df0b  mov     rsi, rdx
0x14002df0e  mov     rbx, r8
0x14002df11  xor     edx, edx; Val
0x14002df13  movzx   r12d, cx
0x14002df17  lea     rcx, [rbp+500h+var_4E0]; void *
0x14002df1b  mov     r14, r9
0x14002df1e  lea     r8d, [rdx+74h]; Size
0x14002df22  call    memset_0
0x14002df27  xor     edx, edx; Val
0x14002df29  lea     rcx, [rsp+600h+var_5D0]; void *
0x14002df2e  mov     r8d, 0F0h; Size
0x14002df34  call    memset_0
0x14002df39  mov     rcx, cs:WPP_GLOBAL_Control
0x14002df40  lea     rax, WPP_GLOBAL_Control
0x14002df47  cmp     rcx, rax
0x14002df4a  jz      short loc_14002DF6D
0x14002df4c  test    byte ptr [rcx+1Ch], 4
0x14002df50  jz      short loc_14002DF6D
0x14002df52  cmp     byte ptr [rcx+19h], 5
0x14002df56  jb      short loc_14002DF6D
0x14002df58  mov     rcx, [rcx+10h]
0x14002df5c  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002df63  mov     edx, 22h ; '"'
0x14002df68  call    WPP_SF_
0x14002df6d  mov     r8d, [rsi+10h]
0x14002df71  lea     rax, aTif; "tif"
0x14002df78  mov     rcx, [rsi+8]; unsigned __int16 *
0x14002df7c  lea     r9, [rbp+500h+var_250]
0x14002df83  test    rbx, rbx
0x14002df86  mov     dword ptr [rsp+600h+var_5E0], 104h
0x14002df8e  cmovz   rbx, rax
0x14002df92  xor     eax, eax
0x14002df94  xor     edx, edx
0x14002df96  mov     [rbp+500h+FileName], ax
0x14002df9d  call    ValidateCoverpage
0x14002dfa2  test    eax, eax
0x14002dfa4  jnz     short loc_14002DFF0
0x14002dfa6  xor     r15d, r15d
0x14002dfa9  call    cs:__imp_GetLastError
0x14002dfaf  mov     edi, eax
0x14002dfb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dfb8  lea     r12, WPP_GLOBAL_Control
0x14002dfbf  cmp     rcx, r12
0x14002dfc2  jz      short loc_14002DFE9
0x14002dfc4  test    byte ptr [rcx+1Ch], 4
0x14002dfc8  jz      short loc_14002DFE9
0x14002dfca  lea     ebx, [r15+2]
0x14002dfce  cmp     [rcx+19h], bl
0x14002dfd1  jb      short loc_14002DFE9
0x14002dfd3  lea     edx, [rbx+21h]
0x14002dfd6  mov     rcx, [rcx+10h]
0x14002dfda  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002dfe1  mov     r9d, eax
0x14002dfe4  call    WPP_SF_d
0x14002dfe9  xor     esi, esi
0x14002dfeb  jmp     loc_14002E282
0x14002dff0  lea     rdx, [rsp+600h+var_5D0]; struct _COVERPAGEFIELDS *
0x14002dff5  mov     rcx, rsi; struct _FAX_COVERPAGE_INFOW2 *
0x14002dff8  call    ?FillCoverPageFields@@YAHPEBU_FAX_COVERPAGE_INFOW2@@PEAU_COVERPAGEFIELDS@@@Z; FillCoverPageFields(_FAX_COVERPAGE_INFOW2 const *,_COVERPAGEFIELDS *)
0x14002dffd  call    GetFaxPrinterName
0x14002e002  mov     r15, rax
0x14002e005  test    rax, rax
0x14002e008  jnz     short loc_14002E039
0x14002e00a  call    cs:__imp_GetLastError
0x14002e010  mov     edi, eax
0x14002e012  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e019  lea     r12, WPP_GLOBAL_Control
0x14002e020  cmp     rcx, r12
0x14002e023  jz      short loc_14002DFE9
0x14002e025  test    byte ptr [rcx+1Ch], 4
0x14002e029  jz      short loc_14002DFE9
0x14002e02b  lea     ebx, [r15+2]
0x14002e02f  cmp     [rcx+19h], bl
0x14002e032  jb      short loc_14002DFE9
0x14002e034  lea     edx, [rbx+22h]
0x14002e037  jmp     short loc_14002DFD6
0x14002e039  lea     r9, [rbp+500h+var_4E0]
0x14002e03d  xor     edx, edx
0x14002e03f  lea     r8, [rbp+500h+var_250]
0x14002e046  xor     ecx, ecx; hdc
0x14002e048  call    PrintCoverPage
0x14002e04d  mov     edi, eax
0x14002e04f  test    eax, eax
0x14002e051  jz      short loc_14002E09E
0x14002e053  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e05a  lea     r12, WPP_GLOBAL_Control
0x14002e061  cmp     rcx, r12
0x14002e064  jz      short loc_14002DFE9
0x14002e066  test    byte ptr [rcx+1Ch], 4
0x14002e06a  jz      loc_14002DFE9
0x14002e070  mov     ebx, 2
0x14002e075  cmp     [rcx+19h], bl
0x14002e078  jb      loc_14002DFE9
0x14002e07e  mov     r9, [rsi+8]
0x14002e082  lea     edx, [rbx+23h]
0x14002e085  mov     rcx, [rcx+10h]
0x14002e089  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e090  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002e094  call    WPP_SF_Sd
0x14002e099  jmp     loc_14002DFE9
0x14002e09e  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002e0a5  lea     rax, [rbp+500h+FileName]
0x14002e0ac  mov     r9, rbx
0x14002e0af  mov     qword ptr [rsp+600h+var_5E0], rax
0x14002e0b4  xor     r8d, r8d
0x14002e0b7  mov     rdx, [rdx+60h]
0x14002e0bb  call    GenerateUniqueFileNameWithPrefix
0x14002e0c0  test    rax, rax
0x14002e0c3  jnz     short loc_14002E104
0x14002e0c5  call    cs:__imp_GetLastError
0x14002e0cb  mov     edi, eax
0x14002e0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e0d4  lea     r12, WPP_GLOBAL_Control
0x14002e0db  cmp     rcx, r12
0x14002e0de  jz      loc_14002DFE9
0x14002e0e4  test    byte ptr [rcx+1Ch], 4
0x14002e0e8  jz      loc_14002DFE9
0x14002e0ee  mov     ebx, 2
0x14002e0f3  cmp     [rcx+19h], bl
0x14002e0f6  jb      loc_14002DFE9
0x14002e0fc  lea     edx, [rbx+24h]
0x14002e0ff  jmp     loc_14002DFD6
0x14002e104  mov     ebx, 2
0x14002e109  lea     r9d, [rbx-1]
0x14002e10d  cmp     [rbp+500h+var_4CC], bx
0x14002e111  jnz     short loc_14002E116
0x14002e113  mov     r9d, ebx
0x14002e116  lea     rax, [rsp+600h+var_5D0]
0x14002e11b  mov     r8, r15; pwszDevice
0x14002e11e  mov     [rsp+600h+var_5D8], rax; __int64
0x14002e123  lea     rdx, [rbp+500h+FileName]; __int64
0x14002e12a  lea     rcx, [rbp+500h+var_250]; __int64
0x14002e131  mov     [rsp+600h+var_5E0], r12w; __int16
0x14002e137  call    PrintCoverPageToFile
0x14002e13c  mov     edi, eax
0x14002e13e  test    eax, eax
0x14002e140  jz      loc_14002E1EB
0x14002e146  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e14d  lea     r12, WPP_GLOBAL_Control
0x14002e154  cmp     rcx, r12
0x14002e157  jz      short loc_14002E181
0x14002e159  test    byte ptr [rcx+1Ch], 4
0x14002e15d  jz      short loc_14002E181
0x14002e15f  cmp     [rcx+19h], bl
0x14002e162  jb      short loc_14002E181
0x14002e164  mov     r9, [rsi+8]
0x14002e168  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e16f  mov     rcx, [rcx+10h]
0x14002e173  mov     edx, 27h ; '''
0x14002e178  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002e17c  call    WPP_SF_Sd
0x14002e181  lea     rcx, [rbp+500h+FileName]; lpFileName
0x14002e188  xor     esi, esi
0x14002e18a  call    cs:__imp_DeleteFileW
0x14002e190  test    eax, eax
0x14002e192  jnz     loc_14002E282
0x14002e198  mov     rax, cs:WPP_GLOBAL_Control
0x14002e19f  cmp     rax, r12
0x14002e1a2  jz      loc_14002E282
0x14002e1a8  test    byte ptr [rax+1Ch], 4
0x14002e1ac  jz      loc_14002E282
0x14002e1b2  cmp     [rax+19h], bl
0x14002e1b5  jb      loc_14002E282
0x14002e1bb  call    cs:__imp_GetLastError
0x14002e1c1  lea     edx, [rsi+28h]
0x14002e1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1cb  lea     r9, [rbp+500h+FileName]
0x14002e1d2  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e1d9  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002e1dd  mov     rcx, [rcx+10h]
0x14002e1e1  call    WPP_SF_Sd
0x14002e1e6  jmp     loc_14002E282
0x14002e1eb  lea     r8, [rbp+500h+FileName]; unsigned __int16 *
0x14002e1f2  mov     edx, 104h; unsigned __int64
0x14002e1f7  mov     rcx, r14; unsigned __int16 *
0x14002e1fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002e1ff  mov     r14d, eax
0x14002e202  test    eax, eax
0x14002e204  jns     short loc_14002E27D
0x14002e206  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e20d  lea     r12, WPP_GLOBAL_Control
0x14002e214  cmp     rcx, r12
0x14002e217  jz      short loc_14002E241
0x14002e219  test    byte ptr [rcx+1Ch], 4
0x14002e21d  jz      short loc_14002E241
0x14002e21f  cmp     [rcx+19h], bl
0x14002e222  jb      short loc_14002E241
0x14002e224  mov     r9, [rsi+8]
0x14002e228  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e22f  mov     rcx, [rcx+10h]
0x14002e233  mov     edx, 29h ; ')'
0x14002e238  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002e23c  call    WPP_SF_Sd
0x14002e241  lea     rcx, [rbp+500h+FileName]; lpFileName
0x14002e248  movzx   edi, r14w
0x14002e24c  xor     esi, esi
0x14002e24e  call    cs:__imp_DeleteFileW
0x14002e254  test    eax, eax
0x14002e256  jnz     short loc_14002E282
0x14002e258  mov     rax, cs:WPP_GLOBAL_Control
0x14002e25f  cmp     rax, r12
0x14002e262  jz      short loc_14002E282
0x14002e264  test    byte ptr [rax+1Ch], 4
0x14002e268  jz      short loc_14002E282
0x14002e26a  cmp     [rax+19h], bl
0x14002e26d  jb      short loc_14002E282
0x14002e26f  call    cs:__imp_GetLastError
0x14002e275  lea     edx, [rsi+2Ah]
0x14002e278  jmp     loc_14002E1C4
0x14002e27d  mov     esi, 1
0x14002e282  mov     rcx, r15; lpMem
0x14002e285  call    pMemFree
0x14002e28a  xor     ebx, ebx
0x14002e28c  mov     rcx, [rsp+rbx*8+600h+lpMem]; lpMem
0x14002e291  call    pMemFree
0x14002e296  inc     rbx
0x14002e299  cmp     rbx, 1Dh
0x14002e29d  jnz     short loc_14002E28C
0x14002e29f  test    esi, esi
0x14002e2a1  jnz     short loc_14002E2B3
0x14002e2a3  test    edi, edi
0x14002e2a5  lea     eax, [rbx+2]
0x14002e2a8  cmovz   edi, eax
0x14002e2ab  mov     ecx, edi; dwErrCode
0x14002e2ad  call    cs:__imp_SetLastError
0x14002e2b3  mov     eax, esi
0x14002e2b5  mov     rcx, [rbp+500h+var_40]
0x14002e2bc  xor     rcx, rsp; StackCookie
0x14002e2bf  call    __security_check_cookie
0x14002e2c4  add     rsp, 5D0h
0x14002e2cb  pop     r15
0x14002e2cd  pop     r14
0x14002e2cf  pop     r12
0x14002e2d1  pop     rdi
0x14002e2d2  pop     rsi
0x14002e2d3  pop     rbx
0x14002e2d4  pop     rbp
0x14002e2d5  retn
```
