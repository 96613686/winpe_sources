# CAllocatorPresenter::UpdateOverlaySurface(void)

- ea: `0x1800c0084`
- end: `0x1800c02c5`
- name: `?UpdateOverlaySurface@CAllocatorPresenter@@AEAAJXZ`
- size: `577`
- prototype: `__int64 __fastcall(CAllocatorPresenter *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800bd0f0`
- `0x1800bd27c`
- `0x1800bda00`

## callees

- `0x1800388a0`
- `0x1800bbd60`
- `0x1800bfcdc`
- `0x1800c0020`
- `0x1800c0084`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800c02a1`
- `KERNEL32!LeaveCriticalSection` at `0x1800c02a1`
- `KERNEL32!EnterCriticalSection` at `0x1800c00a5`
- `KERNEL32!EnterCriticalSection` at `0x1800c00a5`
- `USER32!OffsetRect` at `0x1800c01f3`
- `USER32!OffsetRect` at `0x1800c01f3`
- `USER32!IsRectEmpty` at `0x1800c01b0`
- `USER32!IsRectEmpty` at `0x1800c01c8`
- `USER32!IsRectEmpty` at `0x1800c021e`
- `USER32!IsRectEmpty` at `0x1800c0232`
- `USER32!IsRectEmpty` at `0x1800c01b0`
- `USER32!IsRectEmpty` at `0x1800c01c8`
- `USER32!IsRectEmpty` at `0x1800c021e`
- `USER32!IsRectEmpty` at `0x1800c0232`

## pseudocode

```c
__int64 __fastcall CAllocatorPresenter::UpdateOverlaySurface(CAllocatorPresenter *this)
{
  __int64 v2; // r8
  RECT v3; // xmm1
  unsigned int v4; // edi
  LONG top; // ecx
  LONG bottom; // r8d
  int left; // r9d
  int right; // r10d
  RECT v10; // [rsp+40h] [rbp-38h] BYREF
  RECT rc; // [rsp+50h] [rbp-28h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = *((_QWORD *)this + 4287);
  if ( !v2 || !*((_QWORD *)this + 4294) )
    goto LABEL_18;
  v3 = *(RECT *)((char *)this + 34524);
  v4 = 0;
  rc = *(RECT *)((char *)this + 34492);
  v10 = v3;
  CAllocatorPresenter::ClipRectPair(&v10, &rc, (const struct tagRECT *)(v2 + 24));
  if ( (*((_BYTE *)this + 34664) & 3) == 3 )
  {
    top = v10.top / 2;
    v10.top /= 2;
    bottom = v10.bottom / 2;
    v10.bottom /= 2;
  }
  else
  {
    bottom = v10.bottom;
    top = v10.top;
  }
  if ( *((_DWORD *)this + 8613) )
  {
    left = v10.left / 2;
    v10.left /= 2;
    top /= 2;
    v10.top = top;
    right = v10.right / 2;
    v10.right /= 2;
    bottom /= 2;
    v10.bottom = bottom;
  }
  else
  {
    right = v10.right;
    left = v10.left;
  }
  if ( *((_DWORD *)this + 8614) )
  {
    v10.left = left / 2;
    v10.top = top / 2;
    v10.right = right / 2;
    v10.bottom = bottom / 2;
  }
  if ( *((_DWORD *)this + 8660) || IsRectEmpty(&rc) )
    goto LABEL_17;
  if ( IsRectEmpty(&v10) )
  {
LABEL_18:
    v4 = -2147467259;
    goto LABEL_19;
  }
  OffsetRect(&rc, -*(_DWORD *)(*((_QWORD *)this + 4287) + 24LL), -*(_DWORD *)(*((_QWORD *)this + 4287) + 28LL));
  CAllocatorPresenter::AlignOverlayRects((const struct _DDCAPS_DX7 *)(*((_QWORD *)this + 4287) + 656LL), &v10, &rc);
  if ( IsRectEmpty(&rc) || IsRectEmpty(&v10) )
  {
LABEL_17:
    CAllocatorPresenter::HideOverlaySurface(this);
    goto LABEL_19;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, RECT *, _QWORD, RECT *, _DWORD, _QWORD))(**((_QWORD **)this + 4294) + 264LL))(
         *((_QWORD *)this + 4294),
         &v10,
         *(_QWORD *)(*((_QWORD *)this + 4287) + 2120LL),
         &rc,
         *((_DWORD *)this + 8668),
         0);
  *((_DWORD *)this + 8659) = 1;
LABEL_19:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return v4;
}

```

## disassembly

```asm
0x1800c0084  push    rbp
0x1800c0086  push    rbx
0x1800c0087  push    rsi
0x1800c0088  push    rdi
0x1800c0089  mov     rbp, rsp
0x1800c008c  sub     rsp, 78h
0x1800c0090  mov     rax, cs:__security_cookie
0x1800c0097  xor     rax, rsp
0x1800c009a  mov     [rbp+var_18], rax
0x1800c009e  mov     rbx, rcx
0x1800c00a1  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800c00a5  call    cs:__imp_EnterCriticalSection
0x1800c00ac  nop     dword ptr [rax+rax+00h]
0x1800c00b1  mov     r8, [rbx+85F8h]
0x1800c00b8  test    r8, r8
0x1800c00bb  jz      loc_1800C0298
0x1800c00c1  cmp     qword ptr [rbx+8630h], 0
0x1800c00c9  jz      loc_1800C0298
0x1800c00cf  movups  xmm0, xmmword ptr [rbx+86BCh]
0x1800c00d6  add     r8, 18h; struct tagRECT *
0x1800c00da  lea     rdx, [rbp+rc]; struct tagRECT *
0x1800c00de  movups  xmm1, xmmword ptr [rbx+86DCh]
0x1800c00e5  lea     rcx, [rbp+var_38]; struct tagRECT *
0x1800c00e9  xor     edi, edi
0x1800c00eb  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x1800c00f0  movdqu  xmmword ptr [rbp+var_38.left], xmm1
0x1800c00f5  call    ?ClipRectPair@CAllocatorPresenter@@CAXAEAUtagRECT@@0AEBU2@@Z; CAllocatorPresenter::ClipRectPair(tagRECT &,tagRECT &,tagRECT const &)
0x1800c00fa  mov     eax, [rbx+8768h]
0x1800c0100  lea     r11d, [rdi+2]
0x1800c0104  and     eax, 3
0x1800c0107  cmp     al, 3
0x1800c0109  jnz     short loc_1800C0126
0x1800c010b  mov     eax, [rbp+var_38.top]
0x1800c010e  cdq
0x1800c010f  idiv    r11d
0x1800c0112  mov     ecx, eax
0x1800c0114  mov     [rbp+var_38.top], eax
0x1800c0117  mov     eax, [rbp+var_38.bottom]
0x1800c011a  cdq
0x1800c011b  idiv    r11d
0x1800c011e  mov     r8d, eax
0x1800c0121  mov     [rbp+var_38.bottom], eax
0x1800c0124  jmp     short loc_1800C012D
0x1800c0126  mov     r8d, [rbp+var_38.bottom]
0x1800c012a  mov     ecx, [rbp+var_38.top]
0x1800c012d  cmp     [rbx+8694h], edi
0x1800c0133  jz      short loc_1800C0169
0x1800c0135  mov     eax, [rbp+var_38.left]
0x1800c0138  cdq
0x1800c0139  idiv    r11d
0x1800c013c  mov     r9d, eax
0x1800c013f  mov     [rbp+var_38.left], eax
0x1800c0142  mov     eax, ecx
0x1800c0144  cdq
0x1800c0145  idiv    r11d
0x1800c0148  mov     ecx, eax
0x1800c014a  mov     [rbp+var_38.top], eax
0x1800c014d  mov     eax, [rbp+var_38.right]
0x1800c0150  cdq
0x1800c0151  idiv    r11d
0x1800c0154  mov     r10d, eax
0x1800c0157  mov     [rbp+var_38.right], eax
0x1800c015a  mov     eax, r8d
0x1800c015d  cdq
0x1800c015e  idiv    r11d
0x1800c0161  mov     r8d, eax
0x1800c0164  mov     [rbp+var_38.bottom], eax
0x1800c0167  jmp     short loc_1800C0171
0x1800c0169  mov     r10d, [rbp+var_38.right]
0x1800c016d  mov     r9d, [rbp+var_38.left]
0x1800c0171  cmp     [rbx+8698h], edi
0x1800c0177  jz      short loc_1800C01A0
0x1800c0179  mov     eax, r9d
0x1800c017c  cdq
0x1800c017d  idiv    r11d
0x1800c0180  mov     [rbp+var_38.left], eax
0x1800c0183  mov     eax, ecx
0x1800c0185  cdq
0x1800c0186  idiv    r11d
0x1800c0189  mov     [rbp+var_38.top], eax
0x1800c018c  mov     eax, r10d
0x1800c018f  cdq
0x1800c0190  idiv    r11d
0x1800c0193  mov     [rbp+var_38.right], eax
0x1800c0196  mov     eax, r8d
0x1800c0199  cdq
0x1800c019a  idiv    r11d
0x1800c019d  mov     [rbp+var_38.bottom], eax
0x1800c01a0  cmp     [rbx+8750h], edi
0x1800c01a6  jnz     loc_1800C028E
0x1800c01ac  lea     rcx, [rbp+rc]; lprc
0x1800c01b0  call    cs:__imp_IsRectEmpty
0x1800c01b7  nop     dword ptr [rax+rax+00h]
0x1800c01bc  test    eax, eax
0x1800c01be  jnz     loc_1800C028E
0x1800c01c4  lea     rcx, [rbp+var_38]; lprc
0x1800c01c8  call    cs:__imp_IsRectEmpty
0x1800c01cf  nop     dword ptr [rax+rax+00h]
0x1800c01d4  test    eax, eax
0x1800c01d6  jnz     loc_1800C0298
0x1800c01dc  mov     rax, [rbx+85F8h]
0x1800c01e3  lea     rcx, [rbp+rc]; lprc
0x1800c01e7  mov     r8d, [rax+1Ch]
0x1800c01eb  mov     edx, [rax+18h]
0x1800c01ee  neg     r8d; dy
0x1800c01f1  neg     edx; dx
0x1800c01f3  call    cs:__imp_OffsetRect
0x1800c01fa  nop     dword ptr [rax+rax+00h]
0x1800c01ff  mov     rcx, [rbx+85F8h]
0x1800c0206  lea     r8, [rbp+rc]; struct tagRECT *
0x1800c020a  add     rcx, 290h; struct _DDCAPS_DX7 *
0x1800c0211  lea     rdx, [rbp+var_38]; struct tagRECT *
0x1800c0215  call    ?AlignOverlayRects@CAllocatorPresenter@@CAXAEBU_DDCAPS_DX7@@AEAUtagRECT@@1@Z; CAllocatorPresenter::AlignOverlayRects(_DDCAPS_DX7 const &,tagRECT &,tagRECT &)
0x1800c021a  lea     rcx, [rbp+rc]; lprc
0x1800c021e  call    cs:__imp_IsRectEmpty
0x1800c0225  nop     dword ptr [rax+rax+00h]
0x1800c022a  test    eax, eax
0x1800c022c  jnz     short loc_1800C028E
0x1800c022e  lea     rcx, [rbp+var_38]; lprc
0x1800c0232  call    cs:__imp_IsRectEmpty
0x1800c0239  nop     dword ptr [rax+rax+00h]
0x1800c023e  test    eax, eax
0x1800c0240  jnz     short loc_1800C028E
0x1800c0242  mov     rcx, [rbx+8630h]
0x1800c0249  lea     r9, [rbp+rc]
0x1800c024d  mov     r8, [rbx+85F8h]
0x1800c0254  lea     rdx, [rbp+var_38]
0x1800c0258  mov     [rsp+78h+var_50], rdi
0x1800c025d  mov     rax, [rcx]
0x1800c0260  mov     r8, [r8+848h]
0x1800c0267  mov     r10, [rax+108h]
0x1800c026e  mov     eax, [rbx+8770h]
0x1800c0274  mov     [rsp+78h+var_58], eax
0x1800c0278  mov     rax, r10
0x1800c027b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0280  mov     edi, eax
0x1800c0282  mov     dword ptr [rbx+874Ch], 1
0x1800c028c  jmp     short loc_1800C029D
0x1800c028e  mov     rcx, rbx; this
0x1800c0291  call    ?HideOverlaySurface@CAllocatorPresenter@@AEAAXXZ; CAllocatorPresenter::HideOverlaySurface(void)
0x1800c0296  jmp     short loc_1800C029D
0x1800c0298  mov     edi, 80004005h
0x1800c029d  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800c02a1  call    cs:__imp_LeaveCriticalSection
0x1800c02a8  nop     dword ptr [rax+rax+00h]
0x1800c02ad  mov     eax, edi
0x1800c02af  mov     rcx, [rbp+var_18]
0x1800c02b3  xor     rcx, rsp; StackCookie
0x1800c02b6  call    __security_check_cookie
0x1800c02bb  add     rsp, 78h
0x1800c02bf  pop     rdi
0x1800c02c0  pop     rsi
0x1800c02c1  pop     rbx
0x1800c02c2  pop     rbp
0x1800c02c3  retn
```
