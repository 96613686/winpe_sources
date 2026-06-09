# ColorDeviceShellExt::CanShowColorPage(void)

- ea: `0x180016650`
- end: `0x180016856`
- name: `?CanShowColorPage@ColorDeviceShellExt@@AEAAHXZ`
- size: `518`
- prototype: `__int64 __fastcall(ColorDeviceShellExt *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180016530`

## callees

- `0x180016650`
- `0x1800168b8`
- `0x1800184ce`
- `0x180019010`

## import_xrefs

- `SHELL32!SHGetDesktopFolder` at `0x18001672c`
- `SHELL32!SHGetDesktopFolder` at `0x18001672c`
- `WINSPOOL!ClosePrinter` at `0x1800167e8`
- `WINSPOOL!ClosePrinter` at `0x1800167e8`
- `WINSPOOL!OpenPrinterW` at `0x1800167d4`
- `WINSPOOL!OpenPrinterW` at `0x1800167d4`
- `USER32!RegisterClipboardFormatW` at `0x180016688`
- `USER32!RegisterClipboardFormatW` at `0x180016688`
- `ole32!CoTaskMemFree` at `0x1800167fa`
- `ole32!CoTaskMemFree` at `0x1800167fa`
- `ole32!ReleaseStgMedium` at `0x180016835`
- `ole32!ReleaseStgMedium` at `0x180016835`
- `SHLWAPI!StrRetToStrW` at `0x1800167a2`
- `SHLWAPI!StrRetToStrW` at `0x1800167a2`

## pseudocode

```c
__int64 __fastcall ColorDeviceShellExt::CanShowColorPage(ColorDeviceShellExt *this)
{
  unsigned int v2; // edi
  __int16 v3; // ax
  __int64 v4; // rcx
  int v5; // eax
  char *v6; // rsi
  const ITEMIDLIST *v7; // rbx
  ColorDeviceShellExt *v8; // rcx
  __int16 v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+32h] [rbp-CEh]
  __int16 v12; // [rsp+36h] [rbp-CAh]
  __int64 v13; // [rsp+38h] [rbp-C8h]
  int v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+44h] [rbp-BCh]
  __int64 v16; // [rsp+48h] [rbp-B8h]
  STGMEDIUM v17; // [rsp+50h] [rbp-B0h] BYREF
  STRRET pstr; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR ppsz; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v20; // [rsp+1B8h] [rbp+B8h] BYREF
  IShellFolder *ppshf; // [rsp+1C0h] [rbp+C0h] BYREF
  HANDLE phPrinter; // [rsp+1C8h] [rbp+C8h] BYREF

  v2 = 0;
  memset_0(&pstr, 0, sizeof(pstr));
  ppsz = 0;
  v3 = RegisterClipboardFormatW(L"Shell IDList Array");
  v4 = *((_QWORD *)this + 3);
  v10 = v3;
  v14 = 1;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v15 = -1;
  v16 = 1;
  memset(&v17, 0, sizeof(v17));
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int16 *, STGMEDIUM *))(*(_QWORD *)v4 + 24LL))(v4, &v10, &v17);
    if ( v5 < 0 )
    {
      return v5 == -2147221404;
    }
    else
    {
      if ( v17.hBitmap )
      {
        v6 = (char *)v17.hBitmap + *((unsigned int *)v17.hBitmap + 1);
        if ( v6 )
        {
          v7 = (const ITEMIDLIST *)((char *)v17.hBitmap + *((unsigned int *)v17.hBitmap + 2));
          if ( v7 )
          {
            ppshf = 0;
            v20 = 0;
            if ( SHGetDesktopFolder(&ppshf) >= 0
              && ((int (__fastcall *)(IShellFolder *, char *, _QWORD, GUID *, __int64 *))ppshf->lpVtbl->BindToObject)(
                   ppshf,
                   v6,
                   0,
                   &IID_IShellFolder,
                   &v20) >= 0
              && (*(int (__fastcall **)(__int64, const ITEMIDLIST *, __int64, STRRET *))(*(_QWORD *)v20 + 88LL))(
                   v20,
                   v7,
                   32769,
                   &pstr) >= 0
              && StrRetToStrW(&pstr, v7, &ppsz) >= 0 )
            {
              if ( ColorDeviceShellExt::IsLocal(v8, ppsz) )
              {
                phPrinter = 0;
                if ( OpenPrinterW(ppsz, &phPrinter, 0) )
                {
                  v2 = 1;
                  ClosePrinter(phPrinter);
                }
              }
            }
            if ( ppsz )
              CoTaskMemFree(ppsz);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            if ( ppshf )
              ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
          }
        }
      }
      ReleaseStgMedium(&v17);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180016650  push    rbp
0x180016652  push    rbx
0x180016653  push    rsi
0x180016654  push    rdi
0x180016655  push    r15
0x180016657  lea     rbp, [rsp-80h]
0x18001665c  sub     rsp, 180h
0x180016663  mov     rbx, rcx
0x180016666  xor     edx, edx; Val
0x180016668  lea     rcx, [rsp+1A0h+pstr]; void *
0x18001666d  mov     r8d, 110h; Size
0x180016673  xor     edi, edi
0x180016675  call    memset_0
0x18001667a  lea     rcx, szFormat; "Shell IDList Array"
0x180016681  mov     [rbp+0A0h+ppsz], rdi
0x180016688  call    cs:__imp_RegisterClipboardFormatW
0x18001668e  mov     rcx, [rbx+18h]
0x180016692  lea     r15d, [rdi+1]
0x180016696  mov     [rsp+1A0h+var_170], ax
0x18001669b  xorps   xmm0, xmm0
0x18001669e  xor     eax, eax
0x1800166a0  mov     [rsp+1A0h+var_160], r15d
0x1800166a5  mov     [rsp+1A0h+var_16E], eax
0x1800166a9  mov     [rsp+1A0h+var_16A], ax
0x1800166ae  mov     [rsp+1A0h+var_168], rax
0x1800166b3  mov     [rsp+1A0h+var_15C], 0FFFFFFFFh
0x1800166bb  mov     [rsp+1A0h+var_158], r15
0x1800166c0  mov     [rsp+1A0h+var_150.pUnkForRelease], rax
0x1800166c5  movups  xmmword ptr [rsp+1A0h+var_150.tymed], xmm0
0x1800166ca  test    rcx, rcx
0x1800166cd  jz      loc_180016846
0x1800166d3  mov     rax, [rcx]
0x1800166d6  lea     r8, [rsp+1A0h+var_150]
0x1800166db  lea     rdx, [rsp+1A0h+var_170]
0x1800166e0  mov     rax, [rax+18h]
0x1800166e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e9  test    eax, eax
0x1800166eb  js      loc_18001683D
0x1800166f1  mov     rcx, qword ptr [rsp+1A0h+var_150.8]
0x1800166f6  test    rcx, rcx
0x1800166f9  jz      loc_180016830
0x1800166ff  mov     esi, [rcx+4]
0x180016702  add     rsi, rcx
0x180016705  jz      loc_180016830
0x18001670b  mov     ebx, [rcx+8]
0x18001670e  add     rbx, rcx
0x180016711  jz      loc_180016830
0x180016717  lea     rcx, [rbp+0A0h+ppshf]; ppshf
0x18001671e  mov     [rbp+0A0h+ppshf], rdi
0x180016725  mov     [rbp+0A0h+arg_8], rdi
0x18001672c  call    cs:__imp_SHGetDesktopFolder
0x180016732  test    eax, eax
0x180016734  js      loc_1800167EE
0x18001673a  mov     rcx, [rbp+0A0h+ppshf]
0x180016741  lea     rdx, [rbp+0A0h+arg_8]
0x180016748  mov     [rsp+1A0h+var_180], rdx
0x18001674d  lea     r9, IID_IShellFolder
0x180016754  xor     r8d, r8d
0x180016757  mov     rdx, rsi
0x18001675a  mov     rax, [rcx]
0x18001675d  mov     rax, [rax+28h]
0x180016761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016766  test    eax, eax
0x180016768  js      loc_1800167EE
0x18001676e  mov     rcx, [rbp+0A0h+arg_8]
0x180016775  lea     r9, [rsp+1A0h+pstr]
0x18001677a  mov     r8d, 8001h
0x180016780  mov     rdx, rbx
0x180016783  mov     rax, [rcx]
0x180016786  mov     rax, [rax+58h]
0x18001678a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001678f  test    eax, eax
0x180016791  js      short loc_1800167EE
0x180016793  lea     r8, [rbp+0A0h+ppsz]; ppsz
0x18001679a  mov     rdx, rbx; pidl
0x18001679d  lea     rcx, [rsp+1A0h+pstr]; pstr
0x1800167a2  call    cs:__imp_StrRetToStrW
0x1800167a8  test    eax, eax
0x1800167aa  js      short loc_1800167EE
0x1800167ac  mov     rdx, [rbp+0A0h+ppsz]; unsigned __int16 *
0x1800167b3  call    ?IsLocal@ColorDeviceShellExt@@AEAAHPEBG@Z; ColorDeviceShellExt::IsLocal(ushort const *)
0x1800167b8  test    eax, eax
0x1800167ba  jz      short loc_1800167EE
0x1800167bc  mov     rcx, [rbp+0A0h+ppsz]; pPrinterName
0x1800167c3  lea     rdx, [rbp+0A0h+phPrinter]; phPrinter
0x1800167ca  xor     r8d, r8d; pDefault
0x1800167cd  mov     [rbp+0A0h+phPrinter], rdi
0x1800167d4  call    cs:__imp_OpenPrinterW
0x1800167da  test    eax, eax
0x1800167dc  jz      short loc_1800167EE
0x1800167de  mov     rcx, [rbp+0A0h+phPrinter]; hPrinter
0x1800167e5  mov     edi, r15d
0x1800167e8  call    cs:__imp_ClosePrinter
0x1800167ee  mov     rcx, [rbp+0A0h+ppsz]; pv
0x1800167f5  test    rcx, rcx
0x1800167f8  jz      short loc_180016800
0x1800167fa  call    cs:__imp_CoTaskMemFree
0x180016800  mov     rcx, [rbp+0A0h+arg_8]
0x180016807  test    rcx, rcx
0x18001680a  jz      short loc_180016818
0x18001680c  mov     rax, [rcx]
0x18001680f  mov     rax, [rax+10h]
0x180016813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016818  mov     rcx, [rbp+0A0h+ppshf]
0x18001681f  test    rcx, rcx
0x180016822  jz      short loc_180016830
0x180016824  mov     rax, [rcx]
0x180016827  mov     rax, [rax+10h]
0x18001682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016830  lea     rcx, [rsp+1A0h+var_150]; LPSTGMEDIUM
0x180016835  call    cs:__imp_ReleaseStgMedium
0x18001683b  jmp     short loc_180016846
0x18001683d  cmp     eax, 80040064h
0x180016842  cmovz   edi, r15d
0x180016846  mov     eax, edi
0x180016848  add     rsp, 180h
0x18001684f  pop     r15
0x180016851  pop     rdi
0x180016852  pop     rsi
0x180016853  pop     rbx
0x180016854  pop     rbp
0x180016855  retn
```
