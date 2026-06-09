# LoadStandardOverlays(_IMAGELIST *,int,int *,int *)

- ea: `0x180004940`
- end: `0x180004be9`
- name: `?LoadStandardOverlays@@YAJPEAU_IMAGELIST@@HPEAH1@Z`
- size: `681`
- prototype: `__int64 __fastcall(HIMAGELIST himl, int cx, int *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004940`
- `0x180008630`
- `0x18000b980`
- `0x18000b9cc`
- `0x18000bd34`
- `0x180017f0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ace`
- `USER32!LoadImageW` at `0x180004a5f`
- `USER32!LoadImageW` at `0x180004a5f`
- `USER32!DestroyIcon` at `0x180004b64`
- `USER32!DestroyIcon` at `0x180004b64`
- `COMCTL32!ImageList_ReplaceIcon` at `0x180004ac1`
- `COMCTL32!ImageList_ReplaceIcon` at `0x180004ac1`
- `COMCTL32!ImageList_SetOverlayImage` at `0x180004b18`
- `COMCTL32!ImageList_SetOverlayImage` at `0x180004b18`

## pseudocode

```c
__int64 __fastcall LoadStandardOverlays(HIMAGELIST himl, unsigned int cx, int *a3, unsigned int *a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int i; // esi
  HINSTANCE v13; // r12
  const WCHAR *v14; // rbp
  HICON ImageW; // rax
  signed int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  int v20; // eax
  int v21; // ebp
  signed int LastError; // eax
  int v23; // ecx
  int v24; // [rsp+30h] [rbp-48h]
  HICON hIcon; // [rsp+38h] [rbp-40h]
  unsigned int v26; // [rsp+88h] [rbp+10h]
  int v27; // [rsp+90h] [rbp+18h]

  v26 = cx;
  if ( !a3 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      return 2147942487LL;
    v8 = 13;
LABEL_9:
    WPP_SF_(*(_QWORD *)(v7 + 16), v8, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      return 2147942487LL;
    v8 = 14;
    goto LABEL_9;
  }
  *a3 = 0;
  *a4 = 0;
  if ( !himl )
  {
    v10 = -2147024809;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids);
    return v10;
  }
  v11 = 0;
  v10 = 0;
  v24 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xA )
    {
      *a3 = v11;
      *a4 = i;
      return v10;
    }
    v13 = mmcerror::SC::s_hInst;
    v14 = (const WCHAR *)*((unsigned __int16 *)qword_180022F90 + 2 * (int)i);
    v27 = 0;
    ImageW = (HICON)LoadImageW(mmcerror::SC::s_hInst, v14, 1u, cx, cx, 0);
    hIcon = ImageW;
    if ( ImageW )
    {
      v20 = ImageList_ReplaceIcon(himl, -1, ImageW);
      v21 = v20;
      if ( v20 == -1 )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids, v10);
      }
      else if ( ImageList_SetOverlayImage(himl, v20, i + 1) )
      {
        v10 = 0;
        v27 = v21;
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            12,
            WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids,
            i + 1,
            v21);
        v10 = -2147023537;
      }
      DestroyIcon(hIcon);
      goto LABEL_36;
    }
    v16 = GetLastError();
    v10 = v16;
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0x80070000;
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_qqd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v17, v18, v14, v13, v10);
LABEL_36:
      v19 = WPP_GLOBAL_Control;
    }
    if ( (v10 & 0x80000000) != 0 )
      break;
    v23 = v27;
    cx = v26;
    if ( i )
      v23 = v24;
    v11 = v23;
    v24 = v23;
  }
  if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && *(_BYTE *)(v19 + 25) >= 2u )
    WPP_SF_ddd(*(_QWORD *)(v19 + 16), 16, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids, v26, i, v10);
  return v10;
}

```

## disassembly

```asm
0x180004940  mov     [rsp+arg_0], rbx
0x180004945  mov     [rsp+arg_8], edx
0x180004949  push    rbp
0x18000494a  push    rsi
0x18000494b  push    rdi
0x18000494c  push    r12
0x18000494e  push    r13
0x180004950  push    r14
0x180004952  push    r15
0x180004954  sub     rsp, 40h
0x180004958  mov     r14, r9
0x18000495b  mov     r15, r8
0x18000495e  mov     r13, rcx
0x180004961  test    r8, r8
0x180004964  jnz     short loc_180004985
0x180004966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000496d  lea     rdi, WPP_GLOBAL_Control
0x180004974  cmp     rcx, rdi
0x180004977  jz      short loc_1800049B7
0x180004979  cmp     byte ptr [rcx+19h], 2
0x18000497d  jb      short loc_1800049B7
0x18000497f  lea     edx, [r8+0Dh]
0x180004983  jmp     short loc_1800049A7
0x180004985  test    r14, r14
0x180004988  jnz     short loc_1800049C1
0x18000498a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004991  lea     rdi, WPP_GLOBAL_Control
0x180004998  cmp     rcx, rdi
0x18000499b  jz      short loc_1800049B7
0x18000499d  cmp     byte ptr [rcx+19h], 2
0x1800049a1  jb      short loc_1800049B7
0x1800049a3  lea     edx, [r14+0Eh]
0x1800049a7  mov     rcx, [rcx+10h]
0x1800049ab  lea     r8, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids
0x1800049b2  call    WPP_SF_
0x1800049b7  mov     eax, 80070057h
0x1800049bc  jmp     loc_180004BD1
0x1800049c1  mov     dword ptr [r8], 0
0x1800049c8  mov     dword ptr [r9], 0
0x1800049cf  test    r13, r13
0x1800049d2  jnz     short loc_180004A13
0x1800049d4  mov     ebx, 80070057h
0x1800049d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049e0  lea     rdi, WPP_GLOBAL_Control
0x1800049e7  cmp     rcx, rdi
0x1800049ea  jz      loc_180004BCF
0x1800049f0  cmp     byte ptr [rcx+19h], 2
0x1800049f4  jb      loc_180004BCF
0x1800049fa  mov     rcx, [rcx+10h]
0x1800049fe  lea     edx, [r13+0Fh]
0x180004a02  lea     r8, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids
0x180004a09  call    WPP_SF_
0x180004a0e  jmp     loc_180004BCF
0x180004a13  xor     eax, eax
0x180004a15  lea     rdi, WPP_GLOBAL_Control
0x180004a1c  xor     ebx, ebx
0x180004a1e  mov     [rsp+78h+var_48], eax
0x180004a22  xor     esi, esi
0x180004a24  cmp     esi, 0Ah
0x180004a27  jnb     loc_180004BC9
0x180004a2d  mov     r12, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * mmcerror::SC::s_hInst
0x180004a34  lea     rcx, qword_180022F90
0x180004a3b  movsxd  rax, esi
0x180004a3e  mov     r9d, edx; cx
0x180004a41  movzx   ebp, word ptr [rcx+rax*4]
0x180004a45  xor     eax, eax
0x180004a47  mov     [rsp+78h+fuLoad], eax; fuLoad
0x180004a4b  mov     rcx, r12; hInst
0x180004a4e  mov     [rsp+78h+cy], edx; cy
0x180004a52  mov     edx, ebp; name
0x180004a54  mov     [rsp+78h+arg_10], eax
0x180004a5b  lea     r8d, [rax+1]; type
0x180004a5f  call    cs:__imp_LoadImageW
0x180004a65  mov     [rsp+78h+hIcon], rax
0x180004a6a  test    rax, rax
0x180004a6d  jnz     short loc_180004AB8
0x180004a6f  call    cs:__imp_GetLastError
0x180004a75  mov     ebx, eax
0x180004a77  test    eax, eax
0x180004a79  jle     short loc_180004A84
0x180004a7b  movzx   ebx, ax
0x180004a7e  or      ebx, 80070000h
0x180004a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a8b  cmp     rcx, rdi
0x180004a8e  jz      loc_180004B71
0x180004a94  cmp     byte ptr [rcx+19h], 2
0x180004a98  jb      loc_180004B71
0x180004a9e  mov     rcx, [rcx+10h]
0x180004aa2  mov     r9, rbp
0x180004aa5  mov     [rsp+78h+fuLoad], ebx
0x180004aa9  mov     qword ptr [rsp+78h+cy], r12
0x180004aae  call    WPP_SF_qqd
0x180004ab3  jmp     loc_180004B6A
0x180004ab8  mov     r8, rax; hicon
0x180004abb  or      edx, 0FFFFFFFFh; i
0x180004abe  mov     rcx, r13; himl
0x180004ac1  call    cs:__imp_ImageList_ReplaceIcon
0x180004ac7  mov     ebp, eax
0x180004ac9  cmp     eax, 0FFFFFFFFh
0x180004acc  jnz     short loc_180004B0F
0x180004ace  call    cs:__imp_GetLastError
0x180004ad4  mov     ebx, eax
0x180004ad6  test    eax, eax
0x180004ad8  jle     short loc_180004AE3
0x180004ada  movzx   ebx, ax
0x180004add  or      ebx, 80070000h
0x180004ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aea  cmp     rcx, rdi
0x180004aed  jz      short loc_180004B5F
0x180004aef  cmp     byte ptr [rcx+19h], 2
0x180004af3  jb      short loc_180004B5F
0x180004af5  mov     rcx, [rcx+10h]
0x180004af9  lea     r8, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids
0x180004b00  mov     edx, 0Bh
0x180004b05  mov     r9d, ebx
0x180004b08  call    WPP_SF_d
0x180004b0d  jmp     short loc_180004B5F
0x180004b0f  lea     r8d, [rsi+1]; iOverlay
0x180004b13  mov     edx, ebp; iImage
0x180004b15  mov     rcx, r13; himl
0x180004b18  call    cs:__imp_ImageList_SetOverlayImage
0x180004b1e  test    eax, eax
0x180004b20  jnz     short loc_180004B56
0x180004b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b29  cmp     rcx, rdi
0x180004b2c  jz      short loc_180004B4F
0x180004b2e  cmp     byte ptr [rcx+19h], 2
0x180004b32  jb      short loc_180004B4F
0x180004b34  mov     rcx, [rcx+10h]
0x180004b38  lea     edx, [rax+0Ch]
0x180004b3b  lea     r9d, [rsi+1]
0x180004b3f  mov     [rsp+78h+cy], ebp
0x180004b43  lea     r8, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids
0x180004b4a  call    WPP_SF_dd
0x180004b4f  mov     ebx, 8007054Fh
0x180004b54  jmp     short loc_180004B5F
0x180004b56  xor     ebx, ebx
0x180004b58  mov     [rsp+78h+arg_10], ebp
0x180004b5f  mov     rcx, [rsp+78h+hIcon]; hIcon
0x180004b64  call    cs:__imp_DestroyIcon
0x180004b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b71  test    ebx, ebx
0x180004b73  js      short loc_180004B97
0x180004b75  mov     ecx, [rsp+78h+arg_10]
0x180004b7c  test    esi, esi
0x180004b7e  mov     edx, [rsp+78h+arg_8]
0x180004b85  cmovnz  ecx, [rsp+78h+var_48]
0x180004b8a  inc     esi
0x180004b8c  mov     eax, ecx
0x180004b8e  mov     [rsp+78h+var_48], ecx
0x180004b92  jmp     loc_180004A24
0x180004b97  cmp     rcx, rdi
0x180004b9a  jz      short loc_180004BCF
0x180004b9c  cmp     byte ptr [rcx+19h], 2
0x180004ba0  jb      short loc_180004BCF
0x180004ba2  mov     r9d, [rsp+78h+arg_8]
0x180004baa  lea     r8, WPP_b71d8910e15c3651a632169dc59d8a4f_Traceguids
0x180004bb1  mov     rcx, [rcx+10h]
0x180004bb5  mov     edx, 10h
0x180004bba  mov     [rsp+78h+fuLoad], ebx
0x180004bbe  mov     [rsp+78h+cy], esi
0x180004bc2  call    WPP_SF_ddd
0x180004bc7  jmp     short loc_180004BCF
0x180004bc9  mov     [r15], eax
0x180004bcc  mov     [r14], esi
0x180004bcf  mov     eax, ebx
0x180004bd1  mov     rbx, [rsp+78h+arg_0]
0x180004bd9  add     rsp, 40h
0x180004bdd  pop     r15
0x180004bdf  pop     r14
0x180004be1  pop     r13
0x180004be3  pop     r12
0x180004be5  pop     rdi
0x180004be6  pop     rsi
0x180004be7  pop     rbp
0x180004be8  retn
```
