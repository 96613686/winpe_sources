# CMessageWebPage::_InlineImageBody(CMessageTree *,TREENODEINFO *)

- ea: `0x180061994`
- end: `0x180061cc7`
- name: `?_InlineImageBody@CMessageWebPage@@AEAAJPEAVCMessageTree@@PEAUTREENODEINFO@@@Z`
- size: `819`
- prototype: `__int64 __fastcall(CMessageWebPage *__hidden this, struct CMessageTree *, struct TREENODEINFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800608dc`

## callees

- `0x180035d18`
- `0x18005403c`
- `0x1800610fc`
- `0x180061538`
- `0x180061994`
- `0x180061ef4`
- `0x1800621d0`
- `0x1800621fc`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!PathFindExtensionA` at `0x180061a56`
- `SHLWAPI!PathFindExtensionA` at `0x180061a56`
- `SHLWAPI!__imp_IStream_Reset` at `0x180061bfd`
- `SHLWAPI!__imp_IStream_Reset` at `0x180061bfd`
- `KERNEL32!lstrcmpiA` at `0x180061a69`
- `KERNEL32!lstrcmpiA` at `0x180061a81`
- `KERNEL32!lstrcmpiA` at `0x180061a99`
- `KERNEL32!lstrcmpiA` at `0x180061ab1`
- `KERNEL32!lstrcmpiA` at `0x180061ac5`
- `KERNEL32!lstrcmpiA` at `0x180061ad9`
- `KERNEL32!lstrcmpiA` at `0x180061aed`
- `KERNEL32!lstrcmpiA` at `0x180061b01`
- `KERNEL32!lstrcmpiA` at `0x180061b15`
- `KERNEL32!lstrcmpiA` at `0x180061b29`
- `KERNEL32!lstrcmpiA` at `0x180061a69`
- `KERNEL32!lstrcmpiA` at `0x180061a81`
- `KERNEL32!lstrcmpiA` at `0x180061a99`
- `KERNEL32!lstrcmpiA` at `0x180061ab1`
- `KERNEL32!lstrcmpiA` at `0x180061ac5`
- `KERNEL32!lstrcmpiA` at `0x180061ad9`
- `KERNEL32!lstrcmpiA` at `0x180061aed`
- `KERNEL32!lstrcmpiA` at `0x180061b01`
- `KERNEL32!lstrcmpiA` at `0x180061b15`
- `KERNEL32!lstrcmpiA` at `0x180061b29`

## pseudocode

```c
__int64 __fastcall CMessageWebPage::_InlineImageBody(
        CMessageWebPage *this,
        struct CMessageTree *a2,
        struct TREENODEINFO *a3)
{
  LPCSTR v3; // rsi
  struct tagPAGESEGMENT *v4; // rdi
  bool v5; // zf
  int PropA; // eax
  int v9; // ebx
  const CHAR *ExtensionA; // rbx
  CMessageWebPage *v11; // rcx
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  char v16; // [rsp+20h] [rbp-E0h]
  struct tagPAGESEGMENT *v17; // [rsp+30h] [rbp-D0h] BYREF
  LPCSTR pszPath; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  char v21[256]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  v4 = 0;
  pszPath = 0;
  v5 = (*((_BYTE *)this + 60) & 1) == 0;
  v19 = 0;
  v20 = 0;
  LOWORD(v19) = 19;
  v17 = 0;
  if ( v5 )
    goto LABEL_24;
  v16 = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, const CHAR *, _QWORD, char))(**((_QWORD **)a3 + 16) + 144LL))(
         *((_QWORD *)a3 + 16),
         22,
         "inline",
         0,
         v16) )
  {
    if ( (*((_BYTE *)this + 60) & 2) == 0 )
      goto LABEL_24;
  }
  PropA = CMimePropertyContainer::GetPropA(*((CMimePropertyContainer **)a3 + 16), (const char *)0x2E, (char **)&pszPath);
  v3 = pszPath;
  v9 = PropA;
  if ( PropA < 0 )
    goto LABEL_25;
  ExtensionA = PathFindExtensionA(pszPath);
  if ( lstrcmpiA(ExtensionA, ".bmp")
    && lstrcmpiA(ExtensionA, ".jpg")
    && lstrcmpiA(ExtensionA, ".jpeg")
    && lstrcmpiA(ExtensionA, ".gif")
    && lstrcmpiA(ExtensionA, ".ico")
    && lstrcmpiA(ExtensionA, ".wmf")
    && lstrcmpiA(ExtensionA, ".png")
    && lstrcmpiA(ExtensionA, ".emf")
    && lstrcmpiA(ExtensionA, ".art")
    && lstrcmpiA(ExtensionA, ".xbm") )
  {
LABEL_24:
    v9 = -2147467259;
  }
  else
  {
    v9 = CMessageWebPage::_SetContentId(this, a3, v21);
    if ( v9 >= 0 )
    {
      CMessageWebPage::_DoSegmentSplitter(this);
      v12 = CMessageWebPage::_AllocateSegment(v11, &v17, 1);
      v4 = v17;
      v9 = v12;
      if ( v12 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)v17 + 2) + 32LL))(
               *((_QWORD *)v17 + 2),
               "<P>\n\r<CENTER><IMG SRC=\"CID:",
               27);
        if ( v9 >= 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v21[v13] );
          v9 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))(**((_QWORD **)v4 + 2) + 32LL))(
                 *((_QWORD *)v4 + 2),
                 v21,
                 v13,
                 0);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)v4 + 2) + 32LL))(
                   *((_QWORD *)v4 + 2),
                   "\"></CENTER>",
                   11);
            if ( v9 >= 0 )
            {
              v9 = IStream_Reset(*((IStream **)v4 + 2));
              if ( v9 >= 0 )
              {
                CMessageWebPage::_VAppendSegment(this, v4);
                v4 = 0;
                CActiveUrlRequest::OnBindingDataAvailable(*((CActiveUrlRequest **)this + 10));
                v14 = *((_QWORD *)a3 + 16);
                LOWORD(v19) = 19;
                DWORD2(v19) = 1;
                (*(void (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v14 + 96LL))(v14, 51, 0, &v19);
                (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int128 *))(**((_QWORD **)a3 + 16) + 96LL))(
                  *((_QWORD *)a3 + 16),
                  72,
                  0,
                  &v19);
                *((_DWORD *)a3 + 5) |= 0x10u;
              }
            }
          }
        }
      }
    }
  }
LABEL_25:
  if ( v3 )
    ((void (__fastcall *)(LPMALLOC, LPCSTR))g_pMalloc->lpVtbl->Free)(g_pMalloc, v3);
  if ( v4 )
    CMessageWebPage::_VFreeSegment(this, v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180061994  mov     [rsp-8+arg_8], rbx
0x180061999  mov     [rsp-8+arg_18], rsi
0x18006199e  push    rbp
0x18006199f  push    rdi
0x1800619a0  push    r13
0x1800619a2  push    r14
0x1800619a4  push    r15
0x1800619a6  lea     rbp, [rsp-70h]
0x1800619ab  sub     rsp, 170h
0x1800619b2  mov     rax, cs:__security_cookie
0x1800619b9  xor     rax, rsp
0x1800619bc  mov     [rbp+90h+var_30], rax
0x1800619c0  xor     esi, esi
0x1800619c2  xor     eax, eax
0x1800619c4  xor     edi, edi
0x1800619c6  mov     [rsp+190h+pszPath], rsi
0x1800619cb  test    byte ptr [rcx+3Ch], 1
0x1800619cf  xorps   xmm0, xmm0
0x1800619d2  movups  [rsp+190h+var_150], xmm0
0x1800619d7  lea     r13d, [rsi+13h]
0x1800619db  mov     [rsp+190h+var_140], rax
0x1800619e0  mov     word ptr [rsp+190h+var_150], r13w
0x1800619e6  mov     r15, r8
0x1800619e9  mov     r14, rcx
0x1800619ec  mov     [rsp+190h+var_160], rdi
0x1800619f1  jz      loc_180061C70
0x1800619f7  mov     rcx, [r8+80h]
0x1800619fe  lea     edx, [rsi+16h]
0x180061a01  xor     r9d, r9d
0x180061a04  mov     [rsp+190h+var_170], sil
0x180061a09  lea     r8, STR_DIS_INLINE; "inline"
0x180061a10  mov     rax, [rcx]
0x180061a13  mov     rax, [rax+90h]
0x180061a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a1f  test    eax, eax
0x180061a21  jz      short loc_180061A2E
0x180061a23  test    byte ptr [r14+3Ch], 2
0x180061a28  jz      loc_180061C70
0x180061a2e  mov     rcx, [r15+80h]; this
0x180061a35  lea     r8, [rsp+190h+pszPath]; char **
0x180061a3a  mov     edx, 2Eh ; '.'; char *
0x180061a3f  call    ?GetPropA@CMimePropertyContainer@@QEAAJPEBDPEAPEAD@Z; CMimePropertyContainer::GetPropA(char const *,char * *)
0x180061a44  mov     rsi, [rsp+190h+pszPath]
0x180061a49  mov     ebx, eax
0x180061a4b  test    eax, eax
0x180061a4d  js      loc_180061C75
0x180061a53  mov     rcx, rsi; pszPath
0x180061a56  call    cs:__imp_PathFindExtensionA
0x180061a5c  mov     rcx, rax; lpString1
0x180061a5f  lea     rdx, c_szBmpExt; ".bmp"
0x180061a66  mov     rbx, rax
0x180061a69  call    cs:__imp_lstrcmpiA
0x180061a6f  test    eax, eax
0x180061a71  jz      loc_180061B37
0x180061a77  lea     rdx, c_szJpgExt; ".jpg"
0x180061a7e  mov     rcx, rbx; lpString1
0x180061a81  call    cs:__imp_lstrcmpiA
0x180061a87  test    eax, eax
0x180061a89  jz      loc_180061B37
0x180061a8f  lea     rdx, c_szJpegExt; ".jpeg"
0x180061a96  mov     rcx, rbx; lpString1
0x180061a99  call    cs:__imp_lstrcmpiA
0x180061a9f  test    eax, eax
0x180061aa1  jz      loc_180061B37
0x180061aa7  lea     rdx, c_szGifExt; ".gif"
0x180061aae  mov     rcx, rbx; lpString1
0x180061ab1  call    cs:__imp_lstrcmpiA
0x180061ab7  test    eax, eax
0x180061ab9  jz      short loc_180061B37
0x180061abb  lea     rdx, c_szIcoExt; ".ico"
0x180061ac2  mov     rcx, rbx; lpString1
0x180061ac5  call    cs:__imp_lstrcmpiA
0x180061acb  test    eax, eax
0x180061acd  jz      short loc_180061B37
0x180061acf  lea     rdx, c_szWmfExt; ".wmf"
0x180061ad6  mov     rcx, rbx; lpString1
0x180061ad9  call    cs:__imp_lstrcmpiA
0x180061adf  test    eax, eax
0x180061ae1  jz      short loc_180061B37
0x180061ae3  lea     rdx, c_szPngExt; ".png"
0x180061aea  mov     rcx, rbx; lpString1
0x180061aed  call    cs:__imp_lstrcmpiA
0x180061af3  test    eax, eax
0x180061af5  jz      short loc_180061B37
0x180061af7  lea     rdx, c_szEmfExt; ".emf"
0x180061afe  mov     rcx, rbx; lpString1
0x180061b01  call    cs:__imp_lstrcmpiA
0x180061b07  test    eax, eax
0x180061b09  jz      short loc_180061B37
0x180061b0b  lea     rdx, c_szArtExt; ".art"
0x180061b12  mov     rcx, rbx; lpString1
0x180061b15  call    cs:__imp_lstrcmpiA
0x180061b1b  test    eax, eax
0x180061b1d  jz      short loc_180061B37
0x180061b1f  lea     rdx, c_szXbmExt; ".xbm"
0x180061b26  mov     rcx, rbx; lpString1
0x180061b29  call    cs:__imp_lstrcmpiA
0x180061b2f  test    eax, eax
0x180061b31  jnz     loc_180061C70
0x180061b37  lea     r8, [rsp+190h+var_130]; char *
0x180061b3c  mov     rdx, r15; struct TREENODEINFO *
0x180061b3f  mov     rcx, r14; this
0x180061b42  call    ?_SetContentId@CMessageWebPage@@AEAAJPEAUTREENODEINFO@@PEADK@Z; CMessageWebPage::_SetContentId(TREENODEINFO *,char *,ulong)
0x180061b47  mov     ebx, eax
0x180061b49  test    eax, eax
0x180061b4b  js      loc_180061C75
0x180061b51  mov     rcx, r14; this
0x180061b54  call    ?_DoSegmentSplitter@CMessageWebPage@@AEAAJXZ; CMessageWebPage::_DoSegmentSplitter(void)
0x180061b59  mov     r8d, 1; int
0x180061b5f  lea     rdx, [rsp+190h+var_160]; struct tagPAGESEGMENT **
0x180061b64  call    ?_AllocateSegment@CMessageWebPage@@AEAAJPEAPEAUtagPAGESEGMENT@@H@Z; CMessageWebPage::_AllocateSegment(tagPAGESEGMENT * *,int)
0x180061b69  mov     rdi, [rsp+190h+var_160]
0x180061b6e  mov     ebx, eax
0x180061b70  test    eax, eax
0x180061b72  js      loc_180061C75
0x180061b78  mov     rcx, [rdi+10h]
0x180061b7c  lea     rdx, STR_INLINE_IMAGE1; "<P>\n\r<CENTER><IMG SRC=\"CID:"
0x180061b83  xor     r9d, r9d
0x180061b86  mov     rax, [rcx]
0x180061b89  lea     r8d, [r9+1Bh]
0x180061b8d  mov     rax, [rax+20h]
0x180061b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b96  mov     ebx, eax
0x180061b98  test    eax, eax
0x180061b9a  js      loc_180061C75
0x180061ba0  mov     rcx, [rdi+10h]
0x180061ba4  lea     rdx, [rsp+190h+var_130]
0x180061ba9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180061bad  mov     rax, [rcx]
0x180061bb0  inc     r8
0x180061bb3  cmp     byte ptr [rdx+r8], 0
0x180061bb8  jnz     short loc_180061BB0
0x180061bba  mov     rax, [rax+20h]
0x180061bbe  lea     rdx, [rsp+190h+var_130]
0x180061bc3  xor     r9d, r9d
0x180061bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bcb  mov     ebx, eax
0x180061bcd  test    eax, eax
0x180061bcf  js      loc_180061C75
0x180061bd5  mov     rcx, [rdi+10h]
0x180061bd9  lea     rdx, STR_INLINE_IMAGE2; "\"></CENTER>"
0x180061be0  xor     r9d, r9d
0x180061be3  mov     rax, [rcx]
0x180061be6  lea     r8d, [r9+0Bh]
0x180061bea  mov     rax, [rax+20h]
0x180061bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bf3  mov     ebx, eax
0x180061bf5  test    eax, eax
0x180061bf7  js      short loc_180061C75
0x180061bf9  mov     rcx, [rdi+10h]; pstm
0x180061bfd  call    cs:__imp_IStream_Reset
0x180061c03  mov     ebx, eax
0x180061c05  test    eax, eax
0x180061c07  js      short loc_180061C75
0x180061c09  mov     rdx, rdi; struct tagPAGESEGMENT *
0x180061c0c  mov     rcx, r14; this
0x180061c0f  call    ?_VAppendSegment@CMessageWebPage@@AEAAXPEAUtagPAGESEGMENT@@@Z; CMessageWebPage::_VAppendSegment(tagPAGESEGMENT *)
0x180061c14  mov     rcx, [r14+50h]; this
0x180061c18  xor     edi, edi
0x180061c1a  call    ?OnBindingDataAvailable@CActiveUrlRequest@@QEAAXXZ; CActiveUrlRequest::OnBindingDataAvailable(void)
0x180061c1f  mov     rcx, [r15+80h]
0x180061c26  lea     r9, [rsp+190h+var_150]
0x180061c2b  mov     word ptr [rsp+190h+var_150], r13w
0x180061c31  lea     edx, [rdi+33h]
0x180061c34  mov     dword ptr [rsp+190h+var_150+8], 1
0x180061c3c  xor     r8d, r8d
0x180061c3f  mov     rax, [rcx]
0x180061c42  mov     rax, [rax+60h]
0x180061c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c4b  mov     rcx, [r15+80h]
0x180061c52  lea     r9, [rsp+190h+var_150]
0x180061c57  xor     r8d, r8d
0x180061c5a  lea     edx, [rdi+48h]
0x180061c5d  mov     rax, [rcx]
0x180061c60  mov     rax, [rax+60h]
0x180061c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c69  or      dword ptr [r15+14h], 10h
0x180061c6e  jmp     short loc_180061C75
0x180061c70  mov     ebx, 80004005h
0x180061c75  test    rsi, rsi
0x180061c78  jz      short loc_180061C90
0x180061c7a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180061c81  mov     rdx, rsi
0x180061c84  mov     rax, [rcx]
0x180061c87  mov     rax, [rax+28h]
0x180061c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c90  test    rdi, rdi
0x180061c93  jz      short loc_180061C9D
0x180061c95  mov     rdx, rdi; struct tagPAGESEGMENT *
0x180061c98  call    ?_VFreeSegment@CMessageWebPage@@AEAAXPEAUtagPAGESEGMENT@@@Z; CMessageWebPage::_VFreeSegment(tagPAGESEGMENT *)
0x180061c9d  mov     eax, ebx
0x180061c9f  mov     rcx, [rbp+90h+var_30]
0x180061ca3  xor     rcx, rsp; StackCookie
0x180061ca6  call    __security_check_cookie
0x180061cab  lea     r11, [rsp+190h+var_20]
0x180061cb3  mov     rbx, [r11+38h]
0x180061cb7  mov     rsi, [r11+48h]
0x180061cbb  mov     rsp, r11
0x180061cbe  pop     r15
0x180061cc0  pop     r14
0x180061cc2  pop     r13
0x180061cc4  pop     rdi
0x180061cc5  pop     rbp
0x180061cc6  retn
```
