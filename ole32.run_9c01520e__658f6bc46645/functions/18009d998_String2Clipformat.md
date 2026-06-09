# String2Clipformat

- ea: `0x18009d998`
- end: `0x18009dd58`
- name: `String2Clipformat`
- size: `960`
- prototype: `unsigned __int16 __fastcall(wchar_t *sz)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009d140`

## callees

- `0x1800077fc`
- `0x18009d998`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009da05`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009da3b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009da6e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009daa2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dad7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009db0c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009db41`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009db76`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dbab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dbe0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dc15`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dc4a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dc7f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dcb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dce6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dd18`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009da05`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009da3b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009da6e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009daa2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dad7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009db0c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009db41`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009db76`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dbab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dbe0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dc15`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dc4a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dc7f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dcb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dce6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009dd18`
- `USER32!RegisterClipboardFormatW` at `0x18009dd32`
- `USER32!RegisterClipboardFormatW` at `0x18009dd32`

## pseudocode

```c
UINT __fastcall String2Clipformat(wchar_t *sz)
{
  _DWORD *v2; // rcx
  int v3; // ecx

  if ( safe_lstrlenW(sz) < 3 )
    return RegisterClipboardFormatW(sz);
  v3 = *v2 - 4587587;
  if ( !v3 )
    v3 = sz[2] - 95;
  if ( v3 )
    return RegisterClipboardFormatW(sz);
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_TEXT", -1) == 2 )
    return 1;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_BITMAP", -1) == 2 )
    return 2;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_METAFILEPICT", -1) == 2 )
    return 3;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_SYLK", -1) == 2 )
    return 4;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DIF", -1) == 2 )
    return 5;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_TIFF", -1) == 2 )
    return 6;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_OEMTEXT", -1) == 2 )
    return 7;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DIB", -1) == 2 )
    return 8;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_PALETTE", -1) == 2 )
    return 9;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_PENDATA", -1) == 2 )
    return 10;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_RIFF", -1) == 2 )
    return 11;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_WAVE", -1) == 2 )
    return 12;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_OWNERDISPLAY", -1) == 2 )
    return 128;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DSPTEXT", -1) == 2 )
    return 129;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DSPBITMAP", -1) == 2 )
    return 130;
  if ( CompareStringW(0x7Fu, 1u, sz, -1, L"CF_DSPMETAFILEPICT", -1) != 2 )
    return RegisterClipboardFormatW(sz);
  else
    return 131;
}

```

## disassembly

```asm
0x18009d998  mov     [rsp+arg_0], rbx
0x18009d99d  mov     [rsp+arg_8], rbp
0x18009d9a2  mov     [rsp+arg_10], rsi
0x18009d9a7  push    rdi
0x18009d9a8  push    r14
0x18009d9aa  push    r15
0x18009d9ac  sub     rsp, 30h
0x18009d9b0  mov     rbx, sz
0x18009d9b3  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18009d9b8  mov     r15d, 3
0x18009d9be  cmp     eax, r15d
0x18009d9c1  jl      loc_18009DD2F
0x18009d9c7  mov     ecx, [sz]
0x18009d9c9  sub     ecx, 460043h
0x18009d9cf  jnz     short loc_18009D9D8
0x18009d9d1  movzx   ecx, word ptr [rbx+4]
0x18009d9d5  sub     ecx, 5Fh ; '_'
0x18009d9d8  test    ecx, ecx
0x18009d9da  jnz     loc_18009DD2F
0x18009d9e0  lea     esi, [sz+1]
0x18009d9e3  or      edi, 0FFFFFFFFh
0x18009d9e6  lea     r14d, [sz+7Fh]
0x18009d9ea  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009d9ee  lea     rax, aCfText; "CF_TEXT"
0x18009d9f5  mov     r9d, edi; cchCount1
0x18009d9f8  mov     edx, esi; dwCmpFlags
0x18009d9fa  mov     [rsp+48h+lpString2], rax; lpString2
0x18009d9ff  mov     ecx, r14d; Locale
0x18009da02  mov     r8, rbx; lpString1
0x18009da05  call    cs:__imp_CompareStringW
0x18009da0c  nop     dword ptr [rax+rax+00h]
0x18009da11  lea     ebp, [rdi+3]
0x18009da14  cmp     eax, ebp
0x18009da16  jnz     short loc_18009DA20
0x18009da18  movzx   eax, si
0x18009da1b  jmp     loc_18009DD3E
0x18009da20  lea     sz, aCfBitmap; "CF_BITMAP"
0x18009da27  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009da2b  mov     [rsp+48h+lpString2], sz; lpString2
0x18009da30  mov     r9d, edi; cchCount1
0x18009da33  mov     ecx, r14d; Locale
0x18009da36  mov     r8, rbx; lpString1
0x18009da39  mov     edx, esi; dwCmpFlags
0x18009da3b  call    cs:__imp_CompareStringW
0x18009da42  nop     dword ptr [rax+rax+00h]
0x18009da47  cmp     eax, ebp
0x18009da49  jnz     short loc_18009DA53
0x18009da4b  movzx   eax, bp
0x18009da4e  jmp     loc_18009DD3E
0x18009da53  lea     sz, aCfMetafilepict; "CF_METAFILEPICT"
0x18009da5a  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009da5e  mov     [rsp+48h+lpString2], sz; lpString2
0x18009da63  mov     r9d, edi; cchCount1
0x18009da66  mov     ecx, r14d; Locale
0x18009da69  mov     r8, rbx; lpString1
0x18009da6c  mov     edx, esi; dwCmpFlags
0x18009da6e  call    cs:__imp_CompareStringW
0x18009da75  nop     dword ptr [rax+rax+00h]
0x18009da7a  cmp     eax, ebp
0x18009da7c  jnz     short loc_18009DA87
0x18009da7e  movzx   eax, r15w
0x18009da82  jmp     loc_18009DD3E
0x18009da87  lea     rax, aCfSylk; "CF_SYLK"
0x18009da8e  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009da92  mov     r9d, edi; cchCount1
0x18009da95  mov     [rsp+48h+lpString2], rax; lpString2
0x18009da9a  mov     r8, rbx; lpString1
0x18009da9d  mov     edx, esi; dwCmpFlags
0x18009da9f  mov     ecx, r14d; Locale
0x18009daa2  call    cs:__imp_CompareStringW
0x18009daa9  nop     dword ptr [rax+rax+00h]
0x18009daae  cmp     eax, ebp
0x18009dab0  jnz     short loc_18009DABC
0x18009dab2  mov     eax, 4
0x18009dab7  jmp     loc_18009DD3E
0x18009dabc  lea     rax, aCfDif; "CF_DIF"
0x18009dac3  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dac7  mov     r9d, edi; cchCount1
0x18009daca  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dacf  mov     r8, rbx; lpString1
0x18009dad2  mov     edx, esi; dwCmpFlags
0x18009dad4  mov     ecx, r14d; Locale
0x18009dad7  call    cs:__imp_CompareStringW
0x18009dade  nop     dword ptr [rax+rax+00h]
0x18009dae3  cmp     eax, ebp
0x18009dae5  jnz     short loc_18009DAF1
0x18009dae7  mov     eax, 5
0x18009daec  jmp     loc_18009DD3E
0x18009daf1  lea     rax, aCfTiff; "CF_TIFF"
0x18009daf8  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dafc  mov     r9d, edi; cchCount1
0x18009daff  mov     [rsp+48h+lpString2], rax; lpString2
0x18009db04  mov     r8, rbx; lpString1
0x18009db07  mov     edx, esi; dwCmpFlags
0x18009db09  mov     ecx, r14d; Locale
0x18009db0c  call    cs:__imp_CompareStringW
0x18009db13  nop     dword ptr [rax+rax+00h]
0x18009db18  cmp     eax, ebp
0x18009db1a  jnz     short loc_18009DB26
0x18009db1c  mov     eax, 6
0x18009db21  jmp     loc_18009DD3E
0x18009db26  lea     rax, aCfOemtext; "CF_OEMTEXT"
0x18009db2d  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009db31  mov     r9d, edi; cchCount1
0x18009db34  mov     [rsp+48h+lpString2], rax; lpString2
0x18009db39  mov     r8, rbx; lpString1
0x18009db3c  mov     edx, esi; dwCmpFlags
0x18009db3e  mov     ecx, r14d; Locale
0x18009db41  call    cs:__imp_CompareStringW
0x18009db48  nop     dword ptr [rax+rax+00h]
0x18009db4d  cmp     eax, ebp
0x18009db4f  jnz     short loc_18009DB5B
0x18009db51  mov     eax, 7
0x18009db56  jmp     loc_18009DD3E
0x18009db5b  lea     rax, aCfDib; "CF_DIB"
0x18009db62  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009db66  mov     r9d, edi; cchCount1
0x18009db69  mov     [rsp+48h+lpString2], rax; lpString2
0x18009db6e  mov     r8, rbx; lpString1
0x18009db71  mov     edx, esi; dwCmpFlags
0x18009db73  mov     ecx, r14d; Locale
0x18009db76  call    cs:__imp_CompareStringW
0x18009db7d  nop     dword ptr [rax+rax+00h]
0x18009db82  cmp     eax, ebp
0x18009db84  jnz     short loc_18009DB90
0x18009db86  mov     eax, 8
0x18009db8b  jmp     loc_18009DD3E
0x18009db90  lea     rax, aCfPalette; "CF_PALETTE"
0x18009db97  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009db9b  mov     r9d, edi; cchCount1
0x18009db9e  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dba3  mov     r8, rbx; lpString1
0x18009dba6  mov     edx, esi; dwCmpFlags
0x18009dba8  mov     ecx, r14d; Locale
0x18009dbab  call    cs:__imp_CompareStringW
0x18009dbb2  nop     dword ptr [rax+rax+00h]
0x18009dbb7  cmp     eax, ebp
0x18009dbb9  jnz     short loc_18009DBC5
0x18009dbbb  mov     eax, 9
0x18009dbc0  jmp     loc_18009DD3E
0x18009dbc5  lea     rax, aCfPendata; "CF_PENDATA"
0x18009dbcc  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dbd0  mov     r9d, edi; cchCount1
0x18009dbd3  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dbd8  mov     r8, rbx; lpString1
0x18009dbdb  mov     edx, esi; dwCmpFlags
0x18009dbdd  mov     ecx, r14d; Locale
0x18009dbe0  call    cs:__imp_CompareStringW
0x18009dbe7  nop     dword ptr [rax+rax+00h]
0x18009dbec  cmp     eax, ebp
0x18009dbee  jnz     short loc_18009DBFA
0x18009dbf0  mov     eax, 0Ah
0x18009dbf5  jmp     loc_18009DD3E
0x18009dbfa  lea     rax, aCfRiff; "CF_RIFF"
0x18009dc01  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dc05  mov     r9d, edi; cchCount1
0x18009dc08  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dc0d  mov     r8, rbx; lpString1
0x18009dc10  mov     edx, esi; dwCmpFlags
0x18009dc12  mov     ecx, r14d; Locale
0x18009dc15  call    cs:__imp_CompareStringW
0x18009dc1c  nop     dword ptr [rax+rax+00h]
0x18009dc21  cmp     eax, ebp
0x18009dc23  jnz     short loc_18009DC2F
0x18009dc25  mov     eax, 0Bh
0x18009dc2a  jmp     loc_18009DD3E
0x18009dc2f  lea     rax, aCfWave; "CF_WAVE"
0x18009dc36  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dc3a  mov     r9d, edi; cchCount1
0x18009dc3d  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dc42  mov     r8, rbx; lpString1
0x18009dc45  mov     edx, esi; dwCmpFlags
0x18009dc47  mov     ecx, r14d; Locale
0x18009dc4a  call    cs:__imp_CompareStringW
0x18009dc51  nop     dword ptr [rax+rax+00h]
0x18009dc56  cmp     eax, ebp
0x18009dc58  jnz     short loc_18009DC64
0x18009dc5a  mov     eax, 0Ch
0x18009dc5f  jmp     loc_18009DD3E
0x18009dc64  lea     rax, aCfOwnerdisplay; "CF_OWNERDISPLAY"
0x18009dc6b  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dc6f  mov     r9d, edi; cchCount1
0x18009dc72  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dc77  mov     r8, rbx; lpString1
0x18009dc7a  mov     edx, esi; dwCmpFlags
0x18009dc7c  mov     ecx, r14d; Locale
0x18009dc7f  call    cs:__imp_CompareStringW
0x18009dc86  nop     dword ptr [rax+rax+00h]
0x18009dc8b  cmp     eax, ebp
0x18009dc8d  jnz     short loc_18009DC99
0x18009dc8f  mov     eax, 80h
0x18009dc94  jmp     loc_18009DD3E
0x18009dc99  lea     rax, aCfDsptext; "CF_DSPTEXT"
0x18009dca0  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dca4  mov     r9d, edi; cchCount1
0x18009dca7  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dcac  mov     r8, rbx; lpString1
0x18009dcaf  mov     edx, esi; dwCmpFlags
0x18009dcb1  mov     ecx, r14d; Locale
0x18009dcb4  call    cs:__imp_CompareStringW
0x18009dcbb  nop     dword ptr [rax+rax+00h]
0x18009dcc0  cmp     eax, ebp
0x18009dcc2  jnz     short loc_18009DCCB
0x18009dcc4  mov     eax, 81h
0x18009dcc9  jmp     short loc_18009DD3E
0x18009dccb  lea     rax, aCfDspbitmap; "CF_DSPBITMAP"
0x18009dcd2  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dcd6  mov     r9d, edi; cchCount1
0x18009dcd9  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dcde  mov     r8, rbx; lpString1
0x18009dce1  mov     edx, esi; dwCmpFlags
0x18009dce3  mov     ecx, r14d; Locale
0x18009dce6  call    cs:__imp_CompareStringW
0x18009dced  nop     dword ptr [rax+rax+00h]
0x18009dcf2  cmp     eax, ebp
0x18009dcf4  jnz     short loc_18009DCFD
0x18009dcf6  mov     eax, 82h
0x18009dcfb  jmp     short loc_18009DD3E
0x18009dcfd  lea     rax, aCfDspmetafilep; "CF_DSPMETAFILEPICT"
0x18009dd04  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18009dd08  mov     r9d, edi; cchCount1
0x18009dd0b  mov     [rsp+48h+lpString2], rax; lpString2
0x18009dd10  mov     r8, rbx; lpString1
0x18009dd13  mov     edx, esi; dwCmpFlags
0x18009dd15  mov     ecx, r14d; Locale
0x18009dd18  call    cs:__imp_CompareStringW
0x18009dd1f  nop     dword ptr [rax+rax+00h]
0x18009dd24  cmp     eax, ebp
0x18009dd26  jnz     short loc_18009DD2F
0x18009dd28  mov     eax, 83h
0x18009dd2d  jmp     short loc_18009DD3E
0x18009dd2f  mov     sz, rbx; lpszFormat
0x18009dd32  call    cs:__imp_RegisterClipboardFormatW
0x18009dd39  nop     dword ptr [rax+rax+00h]
0x18009dd3e  mov     rbx, [rsp+48h+arg_0]
0x18009dd43  mov     rbp, [rsp+48h+arg_8]
0x18009dd48  mov     rsi, [rsp+48h+arg_10]
0x18009dd4d  add     rsp, 30h
0x18009dd51  pop     r15
0x18009dd53  pop     r14
0x18009dd55  pop     rdi
0x18009dd56  retn
```
