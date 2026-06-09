# PrvWriterIsFileSystemReadWrite

- ea: `0x180012548`
- end: `0x1800127e4`
- name: `PrvWriterIsFileSystemReadWrite`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014288`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180007ce0`
- `0x180012548`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180012721`
- `OLEAUT32!__imp_VariantClear` at `0x1800127d9`
- `OLEAUT32!__imp_VariantClear` at `0x180012721`
- `OLEAUT32!__imp_VariantClear` at `0x1800127d9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180012768`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180012768`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180012623`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180012623`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800125ce`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800125ce`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180012684`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180012684`
- `KERNEL32!GetVolumeInformationW` at `0x1800126e4`
- `KERNEL32!GetVolumeInformationW` at `0x1800126e4`

## pseudocode

```c
char __fastcall PrvWriterIsFileSystemReadWrite(__int64 *a1)
{
  __int64 v1; // rax
  char v2; // si
  int v3; // eax
  HRESULT LBound; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int i; // eax
  SAFEARRAY *psa; // [rsp+40h] [rbp-20h] BYREF
  VARIANTARG pv; // [rsp+48h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+80h] [rbp+20h] BYREF
  LONG plUbound; // [rsp+88h] [rbp+28h] BYREF
  LONG plLbound; // [rsp+90h] [rbp+30h] BYREF
  DWORD FileSystemFlags; // [rsp+98h] [rbp+38h] BYREF

  v1 = *a1;
  v2 = 0;
  psa = 0;
  plLbound = 0;
  plUbound = 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *, SAFEARRAY **))(v1 + 152))(a1, &psa);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        138,
        &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
        (unsigned int)v3);
    goto LABEL_27;
  }
  LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_27;
    v6 = 139;
    goto LABEL_9;
  }
  LBound = SafeArrayGetUBound(psa, 1u, &plUbound);
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_27;
    v6 = 140;
LABEL_9:
    WPP_SF_d(v5[7], v6, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, (unsigned int)LBound);
    goto LABEL_27;
  }
  for ( i = plLbound; ; i = rgIndices + 1 )
  {
    rgIndices = i;
    if ( i > plUbound )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 145, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      goto LABEL_27;
    }
    FileSystemFlags = 0;
    memset(&pv, 0, sizeof(pv));
    SafeArrayGetElement(psa, &rgIndices, &pv);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 141, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, pv.llVal);
    if ( GetVolumeInformationW(pv.bstrVal, 0, 0, 0, 0, &FileSystemFlags, 0, 0) )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 144, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, pv.llVal);
    VariantClear(&pv);
  }
  if ( (FileSystemFlags & 0x80000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 143, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 142, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
    v2 = 1;
  }
  VariantClear(&pv);
LABEL_27:
  if ( psa )
    SafeArrayDestroy(psa);
  return v2;
}

```

## disassembly

```asm
0x180012548  push    rbp
0x18001254a  push    rsi
0x18001254b  push    rdi
0x18001254c  mov     rbp, rsp
0x18001254f  sub     rsp, 60h
0x180012553  mov     rax, [rcx]
0x180012556  lea     rdx, [rbp+psa]
0x18001255a  xor     sil, sil
0x18001255d  mov     [rbp+psa], 0
0x180012565  mov     [rbp+plLbound], 0
0x18001256c  mov     [rbp+plUbound], 0
0x180012573  mov     rax, [rax+98h]
0x18001257a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001257f  test    eax, eax
0x180012581  jns     short loc_1800125C1
0x180012583  mov     rcx, cs:WPP_GLOBAL_Control
0x18001258a  lea     rdi, WPP_GLOBAL_Control
0x180012591  cmp     rcx, rdi
0x180012594  jz      loc_18001275F
0x18001259a  test    byte ptr [rcx+44h], 1
0x18001259e  jz      loc_18001275F
0x1800125a4  mov     rcx, [rcx+38h]
0x1800125a8  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800125af  mov     edx, 8Ah
0x1800125b4  mov     r9d, eax
0x1800125b7  call    WPP_SF_d
0x1800125bc  jmp     loc_18001275F
0x1800125c1  mov     rcx, [rbp+psa]; psa
0x1800125c5  lea     r8, [rbp+plLbound]; plLbound
0x1800125c9  mov     edx, 1; nDim
0x1800125ce  call    cs:__imp_SafeArrayGetLBound
0x1800125d4  test    eax, eax
0x1800125d6  jns     short loc_180012616
0x1800125d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125df  lea     rdi, WPP_GLOBAL_Control
0x1800125e6  cmp     rcx, rdi
0x1800125e9  jz      loc_18001275F
0x1800125ef  test    byte ptr [rcx+44h], 1
0x1800125f3  jz      loc_18001275F
0x1800125f9  mov     edx, 8Bh
0x1800125fe  mov     rcx, [rcx+38h]
0x180012602  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180012609  mov     r9d, eax
0x18001260c  call    WPP_SF_d
0x180012611  jmp     loc_18001275F
0x180012616  mov     rcx, [rbp+psa]; psa
0x18001261a  lea     r8, [rbp+plUbound]; plUbound
0x18001261e  mov     edx, 1; nDim
0x180012623  call    cs:__imp_SafeArrayGetUBound
0x180012629  test    eax, eax
0x18001262b  jns     short loc_180012655
0x18001262d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012634  lea     rdi, WPP_GLOBAL_Control
0x18001263b  cmp     rcx, rdi
0x18001263e  jz      loc_18001275F
0x180012644  test    byte ptr [rcx+44h], 1
0x180012648  jz      loc_18001275F
0x18001264e  mov     edx, 8Ch
0x180012653  jmp     short loc_1800125FE
0x180012655  mov     eax, [rbp+plLbound]
0x180012658  lea     rdi, WPP_GLOBAL_Control
0x18001265f  jmp     loc_18001272C
0x180012664  mov     rcx, [rbp+psa]; psa
0x180012668  lea     r8, [rbp+pv]; pv
0x18001266c  xorps   xmm0, xmm0
0x18001266f  mov     [rbp+FileSystemFlags], 0
0x180012676  xor     eax, eax
0x180012678  lea     rdx, [rbp+rgIndices]; rgIndices
0x18001267c  movups  [rbp+pv], xmm0
0x180012680  mov     [rbp+var_8], rax
0x180012684  call    cs:__imp_SafeArrayGetElement
0x18001268a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012691  cmp     rcx, rdi
0x180012694  jz      short loc_1800126B5
0x180012696  test    byte ptr [rcx+44h], 1
0x18001269a  jz      short loc_1800126B5
0x18001269c  mov     r9, qword ptr [rbp+pv+8]
0x1800126a0  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800126a7  mov     rcx, [rcx+38h]
0x1800126ab  mov     edx, 8Dh
0x1800126b0  call    WPP_SF_S
0x1800126b5  mov     rcx, qword ptr [rbp+pv+8]; lpRootPathName
0x1800126b9  lea     rax, [rbp+FileSystemFlags]
0x1800126bd  mov     [rsp+60h+nFileSystemNameSize], 0; nFileSystemNameSize
0x1800126c5  xor     r9d, r9d; lpVolumeSerialNumber
0x1800126c8  mov     [rsp+60h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x1800126d1  xor     r8d, r8d; nVolumeNameSize
0x1800126d4  mov     [rsp+60h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800126d9  xor     edx, edx; lpVolumeNameBuffer
0x1800126db  mov     [rsp+60h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x1800126e4  call    cs:__imp_GetVolumeInformationW
0x1800126ea  test    eax, eax
0x1800126ec  jnz     loc_180012779
0x1800126f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126f9  cmp     rcx, rdi
0x1800126fc  jz      short loc_18001271D
0x1800126fe  test    byte ptr [rcx+44h], 1
0x180012702  jz      short loc_18001271D
0x180012704  mov     r9, qword ptr [rbp+pv+8]
0x180012708  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001270f  mov     rcx, [rcx+38h]
0x180012713  mov     edx, 90h
0x180012718  call    WPP_SF_S
0x18001271d  lea     rcx, [rbp+pv]; pvarg
0x180012721  call    cs:__imp_VariantClear
0x180012727  mov     eax, [rbp+rgIndices]
0x18001272a  inc     eax
0x18001272c  mov     [rbp+rgIndices], eax
0x18001272f  cmp     eax, [rbp+plUbound]
0x180012732  jle     loc_180012664
0x180012738  mov     rcx, cs:WPP_GLOBAL_Control
0x18001273f  cmp     rcx, rdi
0x180012742  jz      short loc_18001275F
0x180012744  test    byte ptr [rcx+44h], 1
0x180012748  jz      short loc_18001275F
0x18001274a  mov     rcx, [rcx+38h]
0x18001274e  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180012755  mov     edx, 91h
0x18001275a  call    WPP_SF_
0x18001275f  mov     rcx, [rbp+psa]; psa
0x180012763  test    rcx, rcx
0x180012766  jz      short loc_18001276E
0x180012768  call    cs:__imp_SafeArrayDestroy
0x18001276e  mov     al, sil
0x180012771  add     rsp, 60h
0x180012775  pop     rdi
0x180012776  pop     rsi
0x180012777  pop     rbp
0x180012778  retn
0x180012779  test    [rbp+FileSystemFlags], 80000h
0x180012780  jnz     short loc_1800127AE
0x180012782  mov     rcx, cs:WPP_GLOBAL_Control
0x180012789  cmp     rcx, rdi
0x18001278c  jz      short loc_1800127A9
0x18001278e  test    byte ptr [rcx+44h], 1
0x180012792  jz      short loc_1800127A9
0x180012794  mov     rcx, [rcx+38h]
0x180012798  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001279f  mov     edx, 8Eh
0x1800127a4  call    WPP_SF_
0x1800127a9  mov     sil, 1
0x1800127ac  jmp     short loc_1800127D5
0x1800127ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127b5  cmp     rcx, rdi
0x1800127b8  jz      short loc_1800127D5
0x1800127ba  test    byte ptr [rcx+44h], 1
0x1800127be  jz      short loc_1800127D5
0x1800127c0  mov     rcx, [rcx+38h]
0x1800127c4  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800127cb  mov     edx, 8Fh
0x1800127d0  call    WPP_SF_
0x1800127d5  lea     rcx, [rbp+pv]; pvarg
0x1800127d9  call    cs:__imp_VariantClear
0x1800127df  jmp     loc_18001275F
```
