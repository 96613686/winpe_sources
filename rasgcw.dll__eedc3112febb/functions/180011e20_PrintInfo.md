# PrintInfo

- ea: `0x180011e20`
- end: `0x180012013`
- name: `PrintInfo`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cf90`

## callees

- `0x180011e20`
- `0x18002edb8`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f9d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180011fd0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180011fdf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180011fd0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180011fdf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180011fb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180011fba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180011fb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180011fba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180011e9c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180011ec0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180011e9c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180011ec0`
- `GDI32!EndPage` at `0x180011f83`
- `GDI32!EndPage` at `0x180011f83`
- `GDI32!StartDocW` at `0x180011f1e`
- `GDI32!StartDocW` at `0x180011f1e`
- `GDI32!DeleteDC` at `0x180011fa6`
- `GDI32!DeleteDC` at `0x180011fe9`
- `GDI32!DeleteDC` at `0x180011fa6`
- `GDI32!DeleteDC` at `0x180011fe9`
- `GDI32!CreateDCW` at `0x180011ee2`
- `GDI32!CreateDCW` at `0x180011ee2`
- `GDI32!EndDoc` at `0x180011f95`
- `GDI32!EndDoc` at `0x180011f95`
- `GDI32!StartPage` at `0x180011f2c`
- `GDI32!StartPage` at `0x180011f2c`
- `USER32!DrawTextW` at `0x180011f6f`
- `USER32!DrawTextW` at `0x180011f6f`

## string_xrefs

- `0x180011ef8`: `Allow connections to this computer`

## pseudocode

```c
BOOL __fastcall PrintInfo(__int64 a1, const WCHAR *a2)
{
  BOOL result; // eax
  HGLOBAL hDevNames; // rcx
  char *v5; // rax
  const WCHAR *v6; // rdi
  __int16 *v7; // rbx
  HDC DCW; // rdi
  __int64 v9; // r8
  DOCINFOW v10; // [rsp+30h] [rbp-89h] BYREF
  tagPDW pPD; // [rsp+60h] [rbp-59h] BYREF
  tagRECT rc; // [rsp+E0h] [rbp+27h] BYREF

  memset_0(&pPD, 0, sizeof(pPD));
  pPD.lStructSize = 120;
  pPD.nCopies = 1;
  memset(&pPD.hwndOwner, 0, 24);
  pPD.Flags = 1310988;
  result = PrintDlgW(&pPD);
  if ( result )
  {
    hDevNames = pPD.hDevNames;
    if ( pPD.hDevNames )
    {
      v5 = (char *)GlobalLock(pPD.hDevNames);
      if ( v5 )
      {
        v6 = (const WCHAR *)&v5[2 * *((unsigned __int16 *)v5 + 1)];
        if ( v6 )
        {
          v7 = (__int16 *)GlobalLock(pPD.hDevMode);
          if ( v7 )
          {
            DCW = CreateDCW(L"WINSPOOL", v6, 0, 0);
            if ( DCW )
            {
              v10.lpszDocName = L"Allow connections to this computer";
              *(_QWORD *)&v10.cbSize = 40;
              memset(&v10.lpszOutput, 0, 24);
              if ( StartDocW(pPD.hDC, &v10) <= 0 )
              {
                GetLastError();
              }
              else
              {
                if ( StartPage(pPD.hDC) <= 0 )
                {
                  GetLastError();
                }
                else
                {
                  v9 = -1;
                  rc.left = 5;
                  rc.top = 5;
                  rc.right = v7[41];
                  rc.bottom = v7[40];
                  do
                    ++v9;
                  while ( a2[v9] );
                  if ( !DrawTextW(pPD.hDC, a2, v9, &rc, 0x100040u) )
                    GetLastError();
                  EndPage(pPD.hDC);
                }
                EndDoc(pPD.hDC);
              }
              DeleteDC(DCW);
            }
          }
        }
      }
      GlobalUnlock(pPD.hDevMode);
      GlobalUnlock(pPD.hDevNames);
      hDevNames = pPD.hDevNames;
    }
    if ( pPD.hDevMode )
    {
      GlobalFree(pPD.hDevMode);
      hDevNames = pPD.hDevNames;
    }
    if ( hDevNames )
      GlobalFree(hDevNames);
    return DeleteDC(pPD.hDC);
  }
  return result;
}

```

## disassembly

```asm
0x180011e20  mov     [rsp-8+arg_0], rbx
0x180011e25  mov     [rsp-8+arg_10], rsi
0x180011e2a  push    rbp
0x180011e2b  push    rdi
0x180011e2c  push    r14
0x180011e2e  lea     rbp, [rsp-47h]
0x180011e33  sub     rsp, 100h
0x180011e3a  mov     rax, cs:__security_cookie
0x180011e41  xor     rax, rsp
0x180011e44  mov     [rbp+57h+var_20], rax
0x180011e48  mov     rsi, rdx
0x180011e4b  lea     rcx, [rbp+57h+pPD]; void *
0x180011e4f  mov     ebx, 78h ; 'x'
0x180011e54  xor     edx, edx; Val
0x180011e56  mov     r8d, ebx; Size
0x180011e59  call    memset_0
0x180011e5e  xorps   xmm0, xmm0
0x180011e61  mov     [rbp+57h+pPD.lStructSize], ebx
0x180011e64  lea     eax, [rbx-77h]
0x180011e67  movdqa  xmmword ptr [rbp+57h+pPD.hDevMode], xmm0
0x180011e6c  xor     r14d, r14d
0x180011e6f  mov     [rbp+57h+pPD.nCopies], ax
0x180011e73  lea     rcx, [rbp+57h+pPD]; pPD
0x180011e77  mov     [rbp+57h+pPD.hwndOwner], r14
0x180011e7b  mov     [rbp+57h+pPD.Flags], 14010Ch
0x180011e82  call    PrintDlgW
0x180011e87  test    eax, eax
0x180011e89  jz      loc_180011FEF
0x180011e8f  mov     rcx, [rbp+57h+pPD.hDevNames]; hMem
0x180011e93  test    rcx, rcx
0x180011e96  jz      loc_180011FC4
0x180011e9c  call    cs:__imp_GlobalLock
0x180011ea2  test    rax, rax
0x180011ea5  jz      loc_180011FAC
0x180011eab  movzx   ecx, word ptr [rax+2]
0x180011eaf  lea     rdi, [rax+rcx*2]
0x180011eb3  test    rdi, rdi
0x180011eb6  jz      loc_180011FAC
0x180011ebc  mov     rcx, [rbp+57h+pPD.hDevMode]; hMem
0x180011ec0  call    cs:__imp_GlobalLock
0x180011ec6  mov     rbx, rax
0x180011ec9  test    rax, rax
0x180011ecc  jz      loc_180011FAC
0x180011ed2  xor     r9d, r9d; pdm
0x180011ed5  lea     rcx, pwszDriver; "WINSPOOL"
0x180011edc  xor     r8d, r8d; pszPort
0x180011edf  mov     rdx, rdi; pwszDevice
0x180011ee2  call    cs:__imp_CreateDCW
0x180011ee8  mov     rdi, rax
0x180011eeb  test    rax, rax
0x180011eee  jz      loc_180011FAC
0x180011ef4  mov     rcx, [rbp+57h+pPD.hDC]; hdc
0x180011ef8  lea     rax, aAllowConnectio; "Allow connections to this computer"
0x180011eff  xorps   xmm0, xmm0
0x180011f02  mov     [rsp+110h+var_E0.lpszDocName], rax
0x180011f07  lea     rdx, [rsp+110h+var_E0]; lpdi
0x180011f0c  mov     qword ptr [rsp+110h+var_E0.cbSize], 28h ; '('
0x180011f15  movdqu  xmmword ptr [rbp+57h+var_E0.lpszOutput], xmm0
0x180011f1a  mov     qword ptr [rbp+57h+var_E0.fwType], r14
0x180011f1e  call    cs:__imp_StartDocW
0x180011f24  test    eax, eax
0x180011f26  jle     short loc_180011F9D
0x180011f28  mov     rcx, [rbp+57h+pPD.hDC]; hdc
0x180011f2c  call    cs:__imp_StartPage
0x180011f32  test    eax, eax
0x180011f34  jle     short loc_180011F8B
0x180011f36  lea     eax, [r14+5]
0x180011f3a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011f3e  mov     [rbp+57h+rc.left], eax
0x180011f41  mov     [rbp+57h+rc.top], eax
0x180011f44  movsx   eax, word ptr [rbx+52h]
0x180011f48  mov     [rbp+57h+rc.right], eax
0x180011f4b  movsx   eax, word ptr [rbx+50h]
0x180011f4f  mov     [rbp+57h+rc.bottom], eax
0x180011f52  inc     r8; cchText
0x180011f55  cmp     [rsi+r8*2], r14w
0x180011f5a  jnz     short loc_180011F52
0x180011f5c  mov     rcx, [rbp+57h+pPD.hDC]; hdc
0x180011f60  lea     r9, [rbp+57h+rc]; lprc
0x180011f64  mov     rdx, rsi; lpchText
0x180011f67  mov     [rsp+110h+format], 100040h; format
0x180011f6f  call    cs:__imp_DrawTextW
0x180011f75  test    eax, eax
0x180011f77  jnz     short loc_180011F7F
0x180011f79  call    cs:__imp_GetLastError
0x180011f7f  mov     rcx, [rbp+57h+pPD.hDC]; hdc
0x180011f83  call    cs:__imp_EndPage
0x180011f89  jmp     short loc_180011F91
0x180011f8b  call    cs:__imp_GetLastError
0x180011f91  mov     rcx, [rbp+57h+pPD.hDC]; hdc
0x180011f95  call    cs:__imp_EndDoc
0x180011f9b  jmp     short loc_180011FA3
0x180011f9d  call    cs:__imp_GetLastError
0x180011fa3  mov     rcx, rdi; hdc
0x180011fa6  call    cs:__imp_DeleteDC
0x180011fac  mov     rcx, [rbp+57h+pPD.hDevMode]; hMem
0x180011fb0  call    cs:__imp_GlobalUnlock
0x180011fb6  mov     rcx, [rbp+57h+pPD.hDevNames]; hMem
0x180011fba  call    cs:__imp_GlobalUnlock
0x180011fc0  mov     rcx, [rbp+57h+pPD.hDevNames]
0x180011fc4  mov     rax, [rbp+57h+pPD.hDevMode]
0x180011fc8  test    rax, rax
0x180011fcb  jz      short loc_180011FDA
0x180011fcd  mov     rcx, rax; hMem
0x180011fd0  call    cs:__imp_GlobalFree
0x180011fd6  mov     rcx, [rbp+57h+pPD.hDevNames]; hMem
0x180011fda  test    rcx, rcx
0x180011fdd  jz      short loc_180011FE5
0x180011fdf  call    cs:__imp_GlobalFree
0x180011fe5  mov     rcx, [rbp+57h+pPD.hDC]; hdc
0x180011fe9  call    cs:__imp_DeleteDC
0x180011fef  mov     rcx, [rbp+57h+var_20]
0x180011ff3  xor     rcx, rsp; StackCookie
0x180011ff6  call    __security_check_cookie
0x180011ffb  lea     r11, [rsp+110h+var_10]
0x180012003  mov     rbx, [r11+20h]
0x180012007  mov     rsi, [r11+30h]
0x18001200b  mov     rsp, r11
0x18001200e  pop     r14
0x180012010  pop     rdi
0x180012011  pop     rbp
0x180012012  retn
```
