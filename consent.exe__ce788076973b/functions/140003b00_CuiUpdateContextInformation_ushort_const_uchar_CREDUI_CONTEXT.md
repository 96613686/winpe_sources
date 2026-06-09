# CuiUpdateContextInformation(ushort const *,uchar,_CREDUI_CONTEXT *)

- ea: `0x140003b00`
- end: `0x140003c7b`
- name: `?CuiUpdateContextInformation@@YAJPEBGEPEAU_CREDUI_CONTEXT@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, char, struct _CREDUI_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140003820`

## callees

- `0x140003b00`
- `0x140003e40`
- `0x1400042e0`
- `0x14000f200`
- `0x14000fbec`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x140003bf5`
- `USER32!GetSystemMetrics` at `0x140003bf5`
- `SHELL32!__imp_SHDefExtractIconW` at `0x140003c13`
- `SHELL32!__imp_SHDefExtractIconW` at `0x140003c13`
- `SHLWAPI!PathFindFileNameW` at `0x140003c33`
- `SHLWAPI!PathFindFileNameW` at `0x140003c33`
- `SHLWAPI!SHStrDupW` at `0x140003c40`
- `SHLWAPI!SHStrDupW` at `0x140003c40`

## pseudocode

```c
__int64 __fastcall CuiUpdateContextInformation(LPCWSTR pszPath, char a2, struct _CREDUI_CONTEXT *a3)
{
  int BinarySignature; // edi
  __int64 v6; // rbx
  PCCERT_CONTEXT v7; // rax
  LPWSTR v8; // rcx
  void *v9; // rax
  unsigned __int16 SystemMetrics; // ax
  const WCHAR *FileNameW; // rax
  LPWSTR v13; // [rsp+60h] [rbp-48h] BYREF
  LPWSTR v14; // [rsp+68h] [rbp-40h] BYREF
  PCCERT_CONTEXT v15; // [rsp+70h] [rbp-38h] BYREF
  void *v16; // [rsp+78h] [rbp-30h] BYREF
  char v17; // [rsp+B8h] [rbp+10h] BYREF
  int v18; // [rsp+C8h] [rbp+20h] BYREF

  v17 = a2;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v18 = 0;
  v16 = 0;
  BinarySignature = CuiGetBinarySignature((__int64)pszPath, -1, a2, 0, 4096, &v18, &v17, &v13, &v14, &v15, &v16);
  if ( BinarySignature < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_D(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        19,
        WPP_bed9811735e730a365d52877ff824444_Traceguids,
        (unsigned int)BinarySignature);
  }
  else
  {
    v6 = *((_QWORD *)a3 + 4);
    *((_QWORD *)a3 + 4) = 0;
    CuiFreeContextInformation(a3);
    v7 = v15;
    *(_DWORD *)a3 = v18;
    *((_QWORD *)a3 + 3) = v13;
    v8 = v14;
    *((_QWORD *)a3 + 8) = v7;
    v9 = v16;
    *((_QWORD *)a3 + 2) = v8;
    *((_QWORD *)a3 + 4) = v6;
    *((_QWORD *)a3 + 9) = v9;
    *((_DWORD *)a3 + 15) = CuiGetBinaryLocation(pszPath);
    if ( *((_QWORD *)a3 + 2) )
    {
      SystemMetrics = GetSystemMetrics(11);
      SHDefExtractIconW(pszPath, 0, 0, (HICON *)a3 + 1, 0, SystemMetrics);
    }
    else
    {
      FileNameW = PathFindFileNameW(pszPath);
      SHStrDupW(FileNameW, (LPWSTR *)a3 + 2);
    }
  }
  return (unsigned int)BinarySignature;
}

```

## disassembly

```asm
0x140003b00  mov     [rsp+arg_8], dl
0x140003b04  mov     r11, rsp
0x140003b07  push    rbp
0x140003b08  push    rsi
0x140003b09  push    rdi
0x140003b0a  push    r14
0x140003b0c  sub     rsp, 88h
0x140003b13  xor     ebp, ebp
0x140003b15  lea     rax, [r11-30h]
0x140003b19  mov     [r11-58h], rax
0x140003b1d  mov     r14, r8
0x140003b20  lea     rax, [r11-38h]
0x140003b24  mov     [r11-48h], rbp
0x140003b28  mov     [r11-60h], rax
0x140003b2c  movzx   r8d, dl
0x140003b30  lea     rax, [r11-40h]
0x140003b34  mov     [r11-40h], rbp
0x140003b38  mov     [r11-68h], rax
0x140003b3c  xor     r9d, r9d
0x140003b3f  lea     rax, [r11-48h]
0x140003b43  mov     [r11-38h], rbp
0x140003b47  mov     [r11-70h], rax
0x140003b4b  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140003b52  lea     rax, [r11+10h]
0x140003b56  mov     [r11+20h], ebp
0x140003b5a  mov     [r11-78h], rax
0x140003b5e  mov     rsi, rcx
0x140003b61  lea     rax, [r11+20h]
0x140003b65  mov     [r11-30h], rbp
0x140003b69  mov     [r11-80h], rax
0x140003b6d  mov     dword ptr [rsp+0A8h+phiconSmall], 1000h
0x140003b75  call    ?CuiGetBinarySignature@@YAJPEBGPEAXEEW4SIGNATURE_INFO_FLAGS@@PEAW4_CONTEXT_SIGNATURE@@PEAEPEAPEAG5PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; CuiGetBinarySignature(ushort const *,void *,uchar,uchar,SIGNATURE_INFO_FLAGS,_CONTEXT_SIGNATURE *,uchar *,ushort * *,ushort * *,_CERT_CONTEXT const * *,void * *)
0x140003b7a  mov     edi, eax
0x140003b7c  test    eax, eax
0x140003b7e  js      loc_140003C48
0x140003b84  mov     [rsp+0A8h+arg_0], rbx
0x140003b8c  mov     rcx, r14; struct _CREDUI_CONTEXT *
0x140003b8f  mov     rbx, [r14+20h]
0x140003b93  mov     [r14+20h], rbp
0x140003b97  mov     [rsp+0A8h+var_28], r15
0x140003b9f  call    ?CuiFreeContextInformation@@YAXPEAU_CREDUI_CONTEXT@@@Z; CuiFreeContextInformation(_CREDUI_CONTEXT *)
0x140003ba4  mov     ecx, [rsp+0A8h+arg_18]
0x140003bab  mov     rax, [rsp+0A8h+var_38]
0x140003bb0  mov     [r14], ecx
0x140003bb3  mov     rcx, [rsp+0A8h+var_48]
0x140003bb8  mov     [r14+18h], rcx
0x140003bbc  mov     rcx, [rsp+0A8h+var_40]
0x140003bc1  mov     [r14+40h], rax
0x140003bc5  mov     rax, [rsp+0A8h+var_30]
0x140003bca  mov     [r14+10h], rcx
0x140003bce  mov     rcx, rsi
0x140003bd1  mov     [r14+20h], rbx
0x140003bd5  mov     [r14+48h], rax
0x140003bd9  call    ?CuiGetBinaryLocation@@YA?AW4_CONTEXT_FILE_LOCATION@@PEBG@Z; CuiGetBinaryLocation(ushort const *)
0x140003bde  mov     rbx, [rsp+0A8h+arg_0]
0x140003be6  mov     [r14+3Ch], eax
0x140003bea  cmp     [r14+10h], rbp
0x140003bee  jz      short loc_140003C30
0x140003bf0  mov     ecx, 0Bh; nIndex
0x140003bf5  call    cs:__imp_GetSystemMetrics
0x140003bfb  movzx   ecx, ax
0x140003bfe  lea     r9, [r14+8]; phiconLarge
0x140003c02  mov     [rsp+0A8h+nIconSize], ecx; nIconSize
0x140003c06  xor     r8d, r8d; uFlags
0x140003c09  mov     rcx, rsi; pszIconFile
0x140003c0c  mov     [rsp+0A8h+phiconSmall], rbp; phiconSmall
0x140003c11  xor     edx, edx; iIndex
0x140003c13  call    cs:__imp_SHDefExtractIconW
0x140003c19  mov     r15, [rsp+0A8h+var_28]
0x140003c21  mov     eax, edi
0x140003c23  add     rsp, 88h
0x140003c2a  pop     r14
0x140003c2c  pop     rdi
0x140003c2d  pop     rsi
0x140003c2e  pop     rbp
0x140003c2f  retn
0x140003c30  mov     rcx, rsi; pszPath
0x140003c33  call    cs:__imp_PathFindFileNameW
0x140003c39  mov     rcx, rax; psz
0x140003c3c  lea     rdx, [r14+10h]; ppwsz
0x140003c40  call    cs:__imp_SHStrDupW
0x140003c46  jmp     short loc_140003C19
0x140003c48  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c4f  lea     rax, WPP_GLOBAL_Control
0x140003c56  cmp     rcx, rax
0x140003c59  jz      short loc_140003C21
0x140003c5b  test    byte ptr [rcx+1Ch], 2
0x140003c5f  jz      short loc_140003C21
0x140003c61  mov     rcx, [rcx+10h]
0x140003c65  lea     r8, WPP_bed9811735e730a365d52877ff824444_Traceguids
0x140003c6c  mov     edx, 13h
0x140003c71  mov     r9d, edi
0x140003c74  call    WPP_SF_D
0x140003c79  jmp     short loc_140003C21
```
