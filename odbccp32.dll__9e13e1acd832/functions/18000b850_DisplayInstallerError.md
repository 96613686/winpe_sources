# DisplayInstallerError

- ea: `0x18000b850`
- end: `0x18000b9b3`
- name: `DisplayInstallerError`
- size: `355`
- prototype: `__int16 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b5f0`

## callees

- `0x180002e4c`
- `0x180004d40`
- `0x18000b850`
- `0x180014ae0`

## import_xrefs

- `USER32!MessageBoxW` at `0x18000b98a`
- `USER32!MessageBoxW` at `0x18000b98a`
- `USER32!LoadStringW` at `0x18000b8b6`
- `USER32!LoadStringW` at `0x18000b8d5`
- `USER32!LoadStringW` at `0x18000b8b6`
- `USER32!LoadStringW` at `0x18000b8d5`

## pseudocode

```c
__int16 __fastcall DisplayInstallerError(HWND hWnd)
{
  WORD v2; // bx
  DWORD v3; // edi
  unsigned __int16 v4; // si
  int v5; // r14d
  HRESULT v6; // eax
  WORD pcchErrorMsg[2]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pfErrorCode[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR Buffer[128]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szErrorMsg[392]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR pszDest[1216]; // [rsp+450h] [rbp+350h] BYREF

  pcchErrorMsg[0] = 0;
  pfErrorCode[0] = 0;
  v2 = 1;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  LoadStringW(g_hResDLL, 0x587u, Buffer, 128);
  LOWORD(v6) = LoadStringW(g_hResDLL, 0x77Au, pszDest, 1216);
  while ( v2 && v4 <= 1u && v2 <= 8u )
  {
    LOWORD(v6) = SQLInstallerErrorW(v2++, pfErrorCode, szErrorMsg, 0x184u, pcchErrorMsg);
    v4 = v6;
    if ( pfErrorCode[0] != 11 && pfErrorCode[0] != v3 )
    {
      v3 = pfErrorCode[0];
      if ( (unsigned __int16)v6 <= 1u )
      {
        if ( pfErrorCode[0] == 16 )
          return v6;
        v5 = 1;
        v6 = StringCchPrintfW(pszDest, 0x4C0u, L"%s\r\n\r\n%s", pszDest, szErrorMsg);
        if ( v6 )
        {
          pszDest[1215] = 0;
          goto LABEL_12;
        }
      }
    }
  }
  if ( !v5 )
    return v6;
LABEL_12:
  LOWORD(v6) = MessageBoxW(hWnd, pszDest, Buffer, 0);
  return v6;
}

```

## disassembly

```asm
0x18000b850  push    rbp
0x18000b852  push    rbx
0x18000b853  push    rsi
0x18000b854  push    rdi
0x18000b855  push    r12
0x18000b857  push    r13
0x18000b859  push    r14
0x18000b85b  push    r15
0x18000b85d  lea     rbp, [rsp-0CE8h]
0x18000b865  sub     rsp, 0DE8h
0x18000b86c  mov     rax, cs:__security_cookie
0x18000b873  xor     rax, rsp
0x18000b876  mov     [rbp+0D20h+var_50], rax
0x18000b87d  xor     r12d, r12d
0x18000b880  lea     r8, [rsp+0E20h+Buffer]; lpBuffer
0x18000b885  mov     r13d, 1
0x18000b88b  mov     [rsp+0E20h+var_DF0], r12w
0x18000b891  mov     r15, rcx
0x18000b894  mov     [rsp+0E20h+pfErrorCode], r12d
0x18000b899  mov     rcx, cs:g_hResDLL; hInstance
0x18000b8a0  mov     edx, 587h; uID
0x18000b8a5  movzx   ebx, r13w
0x18000b8a9  mov     edi, r12d
0x18000b8ac  lea     r9d, [r13+7Fh]; cchBufferMax
0x18000b8b0  mov     esi, r12d
0x18000b8b3  mov     r14d, r12d
0x18000b8b6  call    cs:__imp_LoadStringW
0x18000b8bc  mov     rcx, cs:g_hResDLL; hInstance
0x18000b8c3  lea     r8, [rbp+0D20h+pszDest]; lpBuffer
0x18000b8ca  mov     r9d, 4C0h; cchBufferMax
0x18000b8d0  mov     edx, 77Ah; uID
0x18000b8d5  call    cs:__imp_LoadStringW
0x18000b8db  test    bx, bx
0x18000b8de  jz      loc_18000B973
0x18000b8e4  cmp     si, r13w
0x18000b8e8  ja      loc_18000B973
0x18000b8ee  cmp     bx, 8
0x18000b8f2  ja      short loc_18000B973
0x18000b8f4  lea     rax, [rsp+0E20h+var_DF0]
0x18000b8f9  mov     r9d, 184h; cchErrorMsgMax
0x18000b8ff  lea     r8, [rbp+0D20h+szErrorMsg]; lpszErrorMsg
0x18000b903  mov     [rsp+0E20h+pcchErrorMsg], rax; pcchErrorMsg
0x18000b908  lea     rdx, [rsp+0E20h+pfErrorCode]; pfErrorCode
0x18000b90d  movzx   ecx, bx; iError
0x18000b910  call    SQLInstallerErrorW
0x18000b915  mov     ecx, [rsp+0E20h+pfErrorCode]
0x18000b919  add     bx, r13w
0x18000b91d  movzx   esi, ax
0x18000b920  cmp     ecx, 0Bh
0x18000b923  jz      short loc_18000B8DB
0x18000b925  cmp     ecx, edi
0x18000b927  jz      short loc_18000B8DB
0x18000b929  mov     edi, ecx
0x18000b92b  cmp     ax, r13w
0x18000b92f  ja      short loc_18000B8DB
0x18000b931  cmp     ecx, 10h
0x18000b934  jz      short loc_18000B990
0x18000b936  lea     rax, [rbp+0D20h+szErrorMsg]
0x18000b93a  mov     edx, 4C0h; cchDest
0x18000b93f  lea     r9, [rbp+0D20h+pszDest]
0x18000b946  mov     [rsp+0E20h+pcchErrorMsg], rax
0x18000b94b  lea     r8, aSS_2; "%s\r\n\r\n%s"
0x18000b952  mov     r14d, r13d
0x18000b955  lea     rcx, [rbp+0D20h+pszDest]; pszDest
0x18000b95c  call    StringCchPrintfW
0x18000b961  test    eax, eax
0x18000b963  jz      loc_18000B8DB
0x18000b969  mov     [rbp+0D20h+var_52], r12w
0x18000b971  jmp     short loc_18000B978
0x18000b973  test    r14d, r14d
0x18000b976  jz      short loc_18000B990
0x18000b978  xor     r9d, r9d; uType
0x18000b97b  lea     r8, [rsp+0E20h+Buffer]; lpCaption
0x18000b980  lea     rdx, [rbp+0D20h+pszDest]; lpText
0x18000b987  mov     rcx, r15; hWnd
0x18000b98a  call    cs:__imp_MessageBoxW
0x18000b990  mov     rcx, [rbp+0D20h+var_50]
0x18000b997  xor     rcx, rsp; StackCookie
0x18000b99a  call    __security_check_cookie
0x18000b99f  add     rsp, 0DE8h
0x18000b9a6  pop     r15
0x18000b9a8  pop     r14
0x18000b9aa  pop     r13
0x18000b9ac  pop     r12
0x18000b9ae  pop     rdi
0x18000b9af  pop     rsi
0x18000b9b0  pop     rbx
0x18000b9b1  pop     rbp
0x18000b9b2  retn
```
