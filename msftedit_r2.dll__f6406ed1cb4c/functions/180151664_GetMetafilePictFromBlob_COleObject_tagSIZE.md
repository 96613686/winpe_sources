# GetMetafilePictFromBlob(COleObject *,tagSIZE *)

- ea: `0x180151664`
- end: `0x18015183f`
- name: `?GetMetafilePictFromBlob@@YAPEAXPEAVCOleObject@@PEAUtagSIZE@@@Z`
- size: `475`
- prototype: `void *__fastcall(CTxtEdit **, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18015a674`

## callees

- `0x18008a518`
- `0x18013ce80`
- `0x18013dce6`
- `0x180150e38`
- `0x180151664`
- `0x1801a9ad0`
- `0x1801ac50c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801517b2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801517b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801517ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801517ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801517c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801517c9`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowOrgEx` at `0x180151711`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowOrgEx` at `0x180151711`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowExtEx` at `0x180151729`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowExtEx` at `0x180151729`
- `ext-ms-win-gdi-metafile-l1-1-1!CloseMetaFile` at `0x180151790`
- `ext-ms-win-gdi-metafile-l1-1-1!CloseMetaFile` at `0x180151790`
- `ext-ms-win-gdi-metafile-l1-1-1!CreateMetaFileA` at `0x1801516bb`
- `ext-ms-win-gdi-metafile-l1-1-1!CreateMetaFileA` at `0x1801516bb`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180151808`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180151808`

## pseudocode

```c
void *__fastcall GetMetafilePictFromBlob(CTxtEdit **a1, struct tagSIZE *a2)
{
  __int64 v4; // rbx
  HDC MetaFileA; // rax
  HDC v6; // rdi
  LONG y; // r15d
  CTextMarkContainer *v8; // rcx
  CTextMarkContainer *v9; // rcx
  int v10; // r14d
  HMETAFILE v11; // rdi
  HGLOBAL v12; // rax
  void *v13; // rsi
  _QWORD *v14; // rax
  struct tagPOINT pt; // [rsp+30h] [rbp-59h] BYREF
  struct tagRECT v17; // [rsp+38h] [rbp-51h] BYREF
  tagSIZE sz; // [rsp+48h] [rbp-41h] BYREF
  struct tagRECT v19; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v20[10]; // [rsp+60h] [rbp-29h] BYREF

  if ( CTxtEdit::GetTextMarkContainer(a1[6]) )
  {
    v19 = 0;
    if ( a2 )
    {
      v4 = (__int64)*a2;
      pt = (struct tagPOINT)v4;
      MetaFileA = CreateMetaFileA(0);
      v6 = MetaFileA;
      if ( MetaFileA )
      {
        y = pt.y;
        v19.bottom = pt.y;
        v17.bottom = pt.y;
        pt = 0;
        *(_QWORD *)&v19.left = 0;
        v19.right = v4;
        *(_QWORD *)&v17.left = 0;
        v17.right = v4;
        sz = 0;
        SetWindowOrgEx(MetaFileA, 0, 0, &pt);
        SetWindowExtEx(v6, v4, y, &sz);
        memset_0(v20, 0, sizeof(v20));
        v20[0] = 80;
        CTextMarkContainer::SetBlobDrawInfo(
          v8,
          (const struct COleObject *)a1,
          (const struct ITextBlob::BLOB_DRAW_INFO *)v20);
        v10 = CTextMarkContainer::DrawBlob(v9, (const struct COleObject *)a1, v6, &v19, 0);
        if ( v10 == -2147467263 )
          v10 = DrawBlobD2D((struct COleObject *)a1, v6, &v17);
        v11 = CloseMetaFile(v6);
        if ( v11 && !v10 )
        {
          v12 = GlobalAlloc(0x2042u, 0x18u);
          v13 = v12;
          if ( v12 )
          {
            v14 = GlobalLock(v12);
            if ( v14 )
            {
              v14[2] = v11;
              *((_DWORD *)v14 + 1) = v4;
              *((_DWORD *)v14 + 2) = y;
              *(_DWORD *)v14 = 8;
              GlobalUnlock(v13);
            }
            return v13;
          }
          goto LABEL_13;
        }
      }
      else
      {
        v11 = 0;
      }
      v13 = 0;
      if ( !v11 )
        return v13;
LABEL_13:
      DeleteMetaFile(v11);
      return v13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180151664  mov     [rsp-8+arg_10], rbx
0x180151669  push    rbp
0x18015166a  push    rsi
0x18015166b  push    rdi
0x18015166c  push    r14
0x18015166e  push    r15
0x180151670  lea     rbp, [rsp-37h]
0x180151675  sub     rsp, 0C0h
0x18015167c  mov     rax, cs:__security_cookie
0x180151683  xor     rax, rsp
0x180151686  mov     [rbp+57h+var_30], rax
0x18015168a  mov     rsi, rcx
0x18015168d  mov     rbx, rdx
0x180151690  mov     rcx, [rcx+30h]; this
0x180151694  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x180151699  test    rax, rax
0x18015169c  jz      loc_180151819
0x1801516a2  xorps   xmm0, xmm0
0x1801516a5  movups  xmmword ptr [rbp+57h+var_90.left], xmm0
0x1801516a9  test    rbx, rbx
0x1801516ac  jz      loc_180151819
0x1801516b2  mov     rbx, [rbx]
0x1801516b5  xor     ecx, ecx; pszFile
0x1801516b7  mov     qword ptr [rbp+57h+pt.x], rbx
0x1801516bb  call    cs:__imp_CreateMetaFileA
0x1801516c2  nop     dword ptr [rax+rax+00h]
0x1801516c7  mov     rdi, rax
0x1801516ca  test    rax, rax
0x1801516cd  jz      loc_1801517FC
0x1801516d3  mov     r15d, [rbp+57h+pt.y]
0x1801516d7  lea     r9, [rbp+57h+pt]; lppt
0x1801516db  xor     r8d, r8d; y
0x1801516de  mov     [rbp+57h+var_90.bottom], r15d
0x1801516e2  xor     edx, edx; x
0x1801516e4  mov     [rbp+57h+var_A8.bottom], r15d
0x1801516e8  mov     rcx, rax; hdc
0x1801516eb  mov     qword ptr [rbp+57h+pt.x], 0
0x1801516f3  mov     qword ptr [rbp+57h+var_90.left], 0
0x1801516fb  mov     [rbp+57h+var_90.right], ebx
0x1801516fe  mov     qword ptr [rbp+57h+var_A8.left], 0
0x180151706  mov     [rbp+57h+var_A8.right], ebx
0x180151709  mov     qword ptr [rbp+57h+sz.cx], 0
0x180151711  call    cs:__imp_SetWindowOrgEx
0x180151718  nop     dword ptr [rax+rax+00h]
0x18015171d  lea     r9, [rbp+57h+sz]; lpsz
0x180151721  mov     r8d, r15d; y
0x180151724  mov     edx, ebx; x
0x180151726  mov     rcx, rdi; hdc
0x180151729  call    cs:__imp_SetWindowExtEx
0x180151730  nop     dword ptr [rax+rax+00h]
0x180151735  mov     r14d, 50h ; 'P'
0x18015173b  lea     rcx, [rbp+57h+var_80]; void *
0x18015173f  mov     r8d, r14d; Size
0x180151742  xor     edx, edx; Val
0x180151744  call    memset_0
0x180151749  lea     r8, [rbp+57h+var_80]; struct ITextBlob::BLOB_DRAW_INFO *
0x18015174d  mov     [rbp+57h+var_80], r14
0x180151751  mov     rdx, rsi; struct COleObject *
0x180151754  call    ?SetBlobDrawInfo@CTextMarkContainer@@QEAAXAEBVCOleObject@@AEBUBLOB_DRAW_INFO@ITextBlob@@@Z; CTextMarkContainer::SetBlobDrawInfo(COleObject const &,ITextBlob::BLOB_DRAW_INFO const &)
0x180151759  lea     r9, [rbp+57h+var_90]; struct tagRECT *
0x18015175d  mov     [rsp+0E0h+var_C0], 0; struct ITextRenderTarget *
0x180151766  mov     r8, rdi; HDC
0x180151769  mov     rdx, rsi; struct COleObject *
0x18015176c  call    ?DrawBlob@CTextMarkContainer@@QEAAJAEBVCOleObject@@PEAUHDC__@@PEBUtagRECT@@PEAUITextRenderTarget@@@Z; CTextMarkContainer::DrawBlob(COleObject const &,HDC__ *,tagRECT const *,ITextRenderTarget *)
0x180151771  mov     r14d, eax
0x180151774  cmp     eax, 80004001h
0x180151779  jnz     short loc_18015178D
0x18015177b  lea     r8, [rbp+57h+var_A8]; struct tagRECT *
0x18015177f  mov     rdx, rdi; hdcDest
0x180151782  mov     rcx, rsi; struct COleObject *
0x180151785  call    ?DrawBlobD2D@@YAJPEAVCOleObject@@PEAUHDC__@@PEAUtagRECT@@@Z; DrawBlobD2D(COleObject *,HDC__ *,tagRECT *)
0x18015178a  mov     r14d, eax
0x18015178d  mov     rcx, rdi; hdc
0x180151790  call    cs:__imp_CloseMetaFile
0x180151797  nop     dword ptr [rax+rax+00h]
0x18015179c  mov     rdi, rax
0x18015179f  test    rax, rax
0x1801517a2  jz      short loc_1801517FE
0x1801517a4  test    r14d, r14d
0x1801517a7  jnz     short loc_1801517FE
0x1801517a9  lea     edx, [r14+18h]; dwBytes
0x1801517ad  mov     ecx, 2042h; uFlags
0x1801517b2  call    cs:__imp_GlobalAlloc
0x1801517b9  nop     dword ptr [rax+rax+00h]
0x1801517be  mov     rsi, rax
0x1801517c1  test    rax, rax
0x1801517c4  jz      short loc_180151805
0x1801517c6  mov     rcx, rax; hMem
0x1801517c9  call    cs:__imp_GlobalLock
0x1801517d0  nop     dword ptr [rax+rax+00h]
0x1801517d5  test    rax, rax
0x1801517d8  jz      short loc_180151814
0x1801517da  mov     rcx, rsi; hMem
0x1801517dd  mov     [rax+10h], rdi
0x1801517e1  mov     [rax+4], ebx
0x1801517e4  mov     [rax+8], r15d
0x1801517e8  mov     dword ptr [rax], 8
0x1801517ee  call    cs:__imp_GlobalUnlock
0x1801517f5  nop     dword ptr [rax+rax+00h]
0x1801517fa  jmp     short loc_180151814
0x1801517fc  xor     edi, edi
0x1801517fe  xor     esi, esi
0x180151800  test    rdi, rdi
0x180151803  jz      short loc_180151814
0x180151805  mov     rcx, rdi; hmf
0x180151808  call    cs:__imp_DeleteMetaFile
0x18015180f  nop     dword ptr [rax+rax+00h]
0x180151814  mov     rax, rsi
0x180151817  jmp     short loc_18015181B
0x180151819  xor     eax, eax
0x18015181b  mov     rcx, [rbp+57h+var_30]
0x18015181f  xor     rcx, rsp; StackCookie
0x180151822  call    __security_check_cookie
0x180151827  mov     rbx, [rsp+0E0h+arg_10]
0x18015182f  add     rsp, 0C0h
0x180151836  pop     r15
0x180151838  pop     r14
0x18015183a  pop     rdi
0x18015183b  pop     rsi
0x18015183c  pop     rbp
0x18015183d  retn
```
