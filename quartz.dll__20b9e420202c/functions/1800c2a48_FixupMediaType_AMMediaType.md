# FixupMediaType(_AMMediaType *)

- ea: `0x1800c2a48`
- end: `0x1800c2b19`
- name: `?FixupMediaType@@YAXPEAU_AMMediaType@@@Z`
- size: `209`
- prototype: `void __fastcall(struct _AMMediaType *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b58a0`
- `0x1800b5d80`
- `0x1800b8edc`
- `0x1800de90c`
- `0x1800e0700`
- `0x1800e0df8`

## callees

- `0x180026424`
- `0x1800c2a48`
- `0x1800c2ca0`
- `0x1800c2d0c`

## import_xrefs

- `USER32!SetRect` at `0x1800c2aac`
- `USER32!SetRect` at `0x1800c2afc`
- `USER32!SetRect` at `0x1800c2aac`
- `USER32!SetRect` at `0x1800c2afc`
- `USER32!IsRectEmpty` at `0x1800c2a7b`
- `USER32!IsRectEmpty` at `0x1800c2acb`
- `USER32!IsRectEmpty` at `0x1800c2a7b`
- `USER32!IsRectEmpty` at `0x1800c2acb`

## pseudocode

```c
void __fastcall FixupMediaType(struct _AMMediaType *a1, const struct _AMMediaType *a2)
{
  const struct _AMMediaType *v3; // rdx
  VMR9 *v4; // rcx
  struct tagBITMAPINFOHEADER *v5; // rdi
  const RECT *TargetRectFromMediaType; // rax
  struct tagRECT *v7; // rsi
  int yBottom; // ecx
  int biWidth; // r9d
  const RECT *SourceRectFromMediaType; // rax
  struct tagRECT *v11; // rbx
  int biHeight; // ecx
  int v13; // r9d

  v5 = VMR9::GetbmiHeader((VMR9 *)a1, a2);
  if ( v5 )
  {
    TargetRectFromMediaType = VMR9::GetTargetRectFromMediaType(v4, v3);
    v7 = (struct tagRECT *)TargetRectFromMediaType;
    if ( TargetRectFromMediaType && IsRectEmpty(TargetRectFromMediaType) )
    {
      yBottom = -v5->biHeight;
      if ( v5->biHeight > 0 )
        yBottom = v5->biHeight;
      biWidth = -v5->biWidth;
      if ( v5->biWidth > 0 )
        biWidth = v5->biWidth;
      SetRect(v7, 0, 0, biWidth, yBottom);
    }
    SourceRectFromMediaType = GetSourceRectFromMediaType(a1);
    v11 = (struct tagRECT *)SourceRectFromMediaType;
    if ( SourceRectFromMediaType && IsRectEmpty(SourceRectFromMediaType) )
    {
      biHeight = -v5->biHeight;
      if ( v5->biHeight > 0 )
        biHeight = v5->biHeight;
      v13 = -v5->biWidth;
      if ( v5->biWidth > 0 )
        v13 = v5->biWidth;
      SetRect(v11, 0, 0, v13, biHeight);
    }
  }
}

```

## disassembly

```asm
0x1800c2a48  mov     [rsp+arg_0], rbx
0x1800c2a4d  mov     [rsp+arg_8], rsi
0x1800c2a52  push    rdi
0x1800c2a53  sub     rsp, 30h
0x1800c2a57  mov     rbx, rcx
0x1800c2a5a  call    ?GetbmiHeader@VMR9@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; VMR9::GetbmiHeader(_AMMediaType const *)
0x1800c2a5f  mov     rdi, rax
0x1800c2a62  test    rax, rax
0x1800c2a65  jz      loc_1800C2B08
0x1800c2a6b  call    ?GetTargetRectFromMediaType@VMR9@@YAPEAUtagRECT@@PEBU_AMMediaType@@@Z; VMR9::GetTargetRectFromMediaType(_AMMediaType const *)
0x1800c2a70  mov     rsi, rax
0x1800c2a73  test    rax, rax
0x1800c2a76  jz      short loc_1800C2AB8
0x1800c2a78  mov     rcx, rax; lprc
0x1800c2a7b  call    cs:__imp_IsRectEmpty
0x1800c2a82  nop     dword ptr [rax+rax+00h]
0x1800c2a87  test    eax, eax
0x1800c2a89  jz      short loc_1800C2AB8
0x1800c2a8b  mov     ecx, [rdi+8]
0x1800c2a8e  mov     r9d, [rdi+4]
0x1800c2a92  neg     ecx
0x1800c2a94  cmovs   ecx, [rdi+8]
0x1800c2a98  neg     r9d
0x1800c2a9b  mov     [rsp+38h+yBottom], ecx; yBottom
0x1800c2a9f  mov     rcx, rsi; lprc
0x1800c2aa2  cmovs   r9d, [rdi+4]; xRight
0x1800c2aa7  xor     r8d, r8d; yTop
0x1800c2aaa  xor     edx, edx; xLeft
0x1800c2aac  call    cs:__imp_SetRect
0x1800c2ab3  nop     dword ptr [rax+rax+00h]
0x1800c2ab8  mov     rcx, rbx; struct _AMMediaType *
0x1800c2abb  call    ?GetSourceRectFromMediaType@@YAPEAUtagRECT@@PEBU_AMMediaType@@@Z; GetSourceRectFromMediaType(_AMMediaType const *)
0x1800c2ac0  mov     rbx, rax
0x1800c2ac3  test    rax, rax
0x1800c2ac6  jz      short loc_1800C2B08
0x1800c2ac8  mov     rcx, rax; lprc
0x1800c2acb  call    cs:__imp_IsRectEmpty
0x1800c2ad2  nop     dword ptr [rax+rax+00h]
0x1800c2ad7  test    eax, eax
0x1800c2ad9  jz      short loc_1800C2B08
0x1800c2adb  mov     ecx, [rdi+8]
0x1800c2ade  mov     r9d, [rdi+4]
0x1800c2ae2  neg     ecx
0x1800c2ae4  cmovs   ecx, [rdi+8]
0x1800c2ae8  neg     r9d
0x1800c2aeb  mov     [rsp+38h+yBottom], ecx; yBottom
0x1800c2aef  mov     rcx, rbx; lprc
0x1800c2af2  cmovs   r9d, [rdi+4]; xRight
0x1800c2af7  xor     r8d, r8d; yTop
0x1800c2afa  xor     edx, edx; xLeft
0x1800c2afc  call    cs:__imp_SetRect
0x1800c2b03  nop     dword ptr [rax+rax+00h]
0x1800c2b08  mov     rbx, [rsp+38h+arg_0]
0x1800c2b0d  mov     rsi, [rsp+38h+arg_8]
0x1800c2b12  add     rsp, 30h
0x1800c2b16  pop     rdi
0x1800c2b17  retn
```
