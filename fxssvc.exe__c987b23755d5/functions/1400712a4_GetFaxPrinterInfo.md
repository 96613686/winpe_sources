# GetFaxPrinterInfo

- ea: `0x1400712a4`
- end: `0x1400714af`
- name: `GetFaxPrinterInfo`
- size: `523`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400714b8`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140065d14`
- `0x140065dbc`
- `0x1400712a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140071311`
- `KERNEL32!GetLastError` at `0x14007133d`
- `KERNEL32!GetLastError` at `0x140071388`
- `KERNEL32!GetLastError` at `0x140071408`
- `KERNEL32!GetLastError` at `0x14007147a`
- `KERNEL32!GetLastError` at `0x140071311`
- `KERNEL32!GetLastError` at `0x14007133d`
- `KERNEL32!GetLastError` at `0x140071388`
- `KERNEL32!GetLastError` at `0x140071408`
- `KERNEL32!GetLastError` at `0x14007147a`
- `KERNEL32!SetLastError` at `0x140071448`
- `KERNEL32!SetLastError` at `0x140071448`
- `WINSPOOL!OpenPrinterW` at `0x140071307`
- `WINSPOOL!OpenPrinterW` at `0x140071307`
- `WINSPOOL!GetPrinterW` at `0x14007137e`
- `WINSPOOL!GetPrinterW` at `0x1400713fe`
- `WINSPOOL!GetPrinterW` at `0x14007137e`
- `WINSPOOL!GetPrinterW` at `0x1400713fe`
- `WINSPOOL!ClosePrinter` at `0x140071458`
- `WINSPOOL!ClosePrinter` at `0x140071458`

## pseudocode

```c
void *__fastcall GetFaxPrinterInfo(LPWSTR pPrinterName)
{
  void *v2; // rdi
  DWORD v3; // ebx
  char v4; // al
  DWORD v5; // eax
  DWORD LastError; // eax
  DWORD v7; // eax
  DWORD cbBuf; // [rsp+68h] [rbp+10h] BYREF
  HANDLE phPrinter; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
  }
  v2 = 0;
  cbBuf = 0;
  phPrinter = 0;
  if ( OpenPrinterW(pPrinterName, &phPrinter, 0) )
  {
    v3 = 0;
    if ( GetPrinterW(phPrinter, 2u, 0, 0, &cbBuf) || (v5 = GetLastError(), v3 = v5, v5 == 122) )
    {
      v2 = (void *)pMemAlloc(cbBuf);
      if ( v2 )
      {
        if ( !GetPrinterW(phPrinter, 2u, (LPBYTE)v2, cbBuf, &cbBuf) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids,
              LastError);
          }
          pMemFree(v2);
          v2 = 0;
        }
      }
      else
      {
        v3 = 8;
      }
    }
    else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v5);
    }
  }
  else
  {
    v3 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids,
        (_DWORD)pPrinterName,
        v4);
    }
  }
  SetLastError(v3);
  if ( phPrinter
    && !ClosePrinter(phPrinter)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v7);
  }
  return v2;
}

```

## disassembly

```asm
0x1400712a4  mov     [rsp+arg_0], rbx
0x1400712a9  push    rbp
0x1400712aa  push    rsi
0x1400712ab  push    rdi
0x1400712ac  push    r14
0x1400712ae  push    r15
0x1400712b0  sub     rsp, 30h
0x1400712b4  mov     rsi, rcx
0x1400712b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400712be  lea     r14, WPP_GLOBAL_Control
0x1400712c5  lea     r15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x1400712cc  mov     ebp, 2
0x1400712d1  cmp     rcx, r14
0x1400712d4  jz      short loc_1400712F1
0x1400712d6  test    [rcx+1Ch], bpl
0x1400712da  jz      short loc_1400712F1
0x1400712dc  cmp     byte ptr [rcx+19h], 5
0x1400712e0  jb      short loc_1400712F1
0x1400712e2  mov     rcx, [rcx+10h]
0x1400712e6  lea     edx, [rbp+0Bh]
0x1400712e9  mov     r8, r15
0x1400712ec  call    WPP_SF_
0x1400712f1  xor     edi, edi
0x1400712f3  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x1400712f8  xor     r8d, r8d; pDefault
0x1400712fb  mov     [rsp+58h+cbBuf], edi
0x1400712ff  mov     rcx, rsi; pPrinterName
0x140071302  mov     [rsp+58h+phPrinter], rdi
0x140071307  call    cs:__imp_OpenPrinterW
0x14007130d  test    eax, eax
0x14007130f  jnz     short loc_140071365
0x140071311  call    cs:__imp_GetLastError
0x140071317  mov     ebx, eax
0x140071319  mov     rax, cs:WPP_GLOBAL_Control
0x140071320  cmp     rax, r14
0x140071323  jz      loc_140071446
0x140071329  test    [rax+1Ch], bpl
0x14007132d  jz      loc_140071446
0x140071333  cmp     [rax+19h], bpl
0x140071337  jb      loc_140071446
0x14007133d  call    cs:__imp_GetLastError
0x140071343  mov     rcx, cs:WPP_GLOBAL_Control
0x14007134a  lea     edx, [rdi+0Eh]
0x14007134d  mov     r9, rsi
0x140071350  mov     dword ptr [rsp+58h+pcbNeeded], eax
0x140071354  mov     r8, r15
0x140071357  mov     rcx, [rcx+10h]
0x14007135b  call    WPP_SF_Sd
0x140071360  jmp     loc_140071446
0x140071365  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x14007136a  lea     rax, [rsp+58h+cbBuf]
0x14007136f  xor     r9d, r9d; cbBuf
0x140071372  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x140071377  xor     r8d, r8d; pPrinter
0x14007137a  mov     edx, ebp; Level
0x14007137c  xor     ebx, ebx
0x14007137e  call    cs:__imp_GetPrinterW
0x140071384  test    eax, eax
0x140071386  jnz     short loc_1400713CF
0x140071388  call    cs:__imp_GetLastError
0x14007138e  mov     ebx, eax
0x140071390  cmp     eax, 7Ah ; 'z'
0x140071393  jz      short loc_1400713CF
0x140071395  mov     rcx, cs:WPP_GLOBAL_Control
0x14007139c  cmp     rcx, r14
0x14007139f  jz      loc_140071446
0x1400713a5  test    [rcx+1Ch], bpl
0x1400713a9  jz      loc_140071446
0x1400713af  cmp     [rcx+19h], bpl
0x1400713b3  jb      loc_140071446
0x1400713b9  mov     rcx, [rcx+10h]
0x1400713bd  mov     edx, 0Fh
0x1400713c2  mov     r9d, eax
0x1400713c5  mov     r8, r15
0x1400713c8  call    WPP_SF_d
0x1400713cd  jmp     short loc_140071446
0x1400713cf  mov     ecx, [rsp+58h+cbBuf]; dwBytes
0x1400713d3  call    pMemAlloc
0x1400713d8  mov     rdi, rax
0x1400713db  test    rax, rax
0x1400713de  jnz     short loc_1400713E5
0x1400713e0  lea     ebx, [rax+8]
0x1400713e3  jmp     short loc_140071446
0x1400713e5  mov     r9d, [rsp+58h+cbBuf]; cbBuf
0x1400713ea  lea     rax, [rsp+58h+cbBuf]
0x1400713ef  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x1400713f4  mov     r8, rdi; pPrinter
0x1400713f7  mov     edx, ebp; Level
0x1400713f9  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x1400713fe  call    cs:__imp_GetPrinterW
0x140071404  test    eax, eax
0x140071406  jnz     short loc_140071446
0x140071408  call    cs:__imp_GetLastError
0x14007140e  mov     ebx, eax
0x140071410  mov     rcx, cs:WPP_GLOBAL_Control
0x140071417  cmp     rcx, r14
0x14007141a  jz      short loc_14007143C
0x14007141c  test    [rcx+1Ch], bpl
0x140071420  jz      short loc_14007143C
0x140071422  cmp     [rcx+19h], bpl
0x140071426  jb      short loc_14007143C
0x140071428  mov     rcx, [rcx+10h]
0x14007142c  mov     edx, 10h
0x140071431  mov     r9d, eax
0x140071434  mov     r8, r15
0x140071437  call    WPP_SF_d
0x14007143c  mov     rcx, rdi; lpMem
0x14007143f  call    pMemFree
0x140071444  xor     edi, edi
0x140071446  mov     ecx, ebx; dwErrCode
0x140071448  call    cs:__imp_SetLastError
0x14007144e  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x140071453  test    rcx, rcx
0x140071456  jz      short loc_14007149B
0x140071458  call    cs:__imp_ClosePrinter
0x14007145e  test    eax, eax
0x140071460  jnz     short loc_14007149B
0x140071462  mov     rax, cs:WPP_GLOBAL_Control
0x140071469  cmp     rax, r14
0x14007146c  jz      short loc_14007149B
0x14007146e  test    [rax+1Ch], bpl
0x140071472  jz      short loc_14007149B
0x140071474  cmp     [rax+19h], bpl
0x140071478  jb      short loc_14007149B
0x14007147a  call    cs:__imp_GetLastError
0x140071480  mov     rcx, cs:WPP_GLOBAL_Control
0x140071487  mov     edx, 11h
0x14007148c  mov     r9d, eax
0x14007148f  mov     r8, r15
0x140071492  mov     rcx, [rcx+10h]
0x140071496  call    WPP_SF_d
0x14007149b  mov     rbx, [rsp+58h+arg_0]
0x1400714a0  mov     rax, rdi
0x1400714a3  add     rsp, 30h
0x1400714a7  pop     r15
0x1400714a9  pop     r14
0x1400714ab  pop     rdi
0x1400714ac  pop     rsi
0x1400714ad  pop     rbp
0x1400714ae  retn
```
