# CDropCaret::DrawCaret(long)

- ea: `0x18005b090`
- end: `0x18005b342`
- name: `?DrawCaret@CDropCaret@@QEAAXJ@Z`
- size: `690`
- prototype: `void __fastcall(CDropCaret *__hidden this, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18005b000`

## callees

- `0x180009070`
- `0x18000b5e0`
- `0x18000da20`
- `0x18000e40c`
- `0x180039990`
- `0x18003a200`
- `0x18003b2a0`
- `0x18003be60`
- `0x18003eb5c`
- `0x18005b090`
- `0x18005b6c0`
- `0x18005b77c`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005b0c6`
- `KERNEL32!EnterCriticalSection` at `0x18005b0c6`
- `KERNEL32!LeaveCriticalSection` at `0x18005b30e`
- `KERNEL32!LeaveCriticalSection` at `0x18005b30e`
- `USER32!PtInRect` at `0x18005b254`
- `USER32!PtInRect` at `0x18005b254`
- `GDI32!BitBlt` at `0x18005b2f3`
- `GDI32!BitBlt` at `0x18005b2f3`
- `GDI32!DeleteObject` at `0x18005b2b1`
- `GDI32!DeleteObject` at `0x18005b2b1`
- `GDI32!SelectObject` at `0x18005b2a1`
- `GDI32!SelectObject` at `0x18005b2a1`
- `GDI32!CreateCompatibleBitmap` at `0x18005b286`
- `GDI32!CreateCompatibleBitmap` at `0x18005b286`

## pseudocode

```c
void __fastcall CDropCaret::DrawCaret(CDropCaret *this, int a2)
{
  __int16 *v4; // r15
  __int16 *CF; // r14
  int ZoomNumerator; // eax
  int v7; // r8d
  int v8; // r12d
  CCcs *Ccs; // rax
  CCcs *v10; // rsi
  int v11; // r8d
  int cy; // ebx
  struct CLine *Line; // rax
  __int64 v14; // r9
  __int16 v15; // ax
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v17; // rsi
  POINT pt; // [rsp+50h] [rbp-79h] BYREF
  int v19; // [rsp+58h] [rbp-71h] BYREF
  int v20; // [rsp+5Ch] [rbp-6Dh] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v22[80]; // [rsp+80h] [rbp-49h] BYREF
  RECT rc; // [rsp+D0h] [rbp+7h] BYREF

  EnterCriticalSection(&g_CriticalSection);
  v4 = *(__int16 **)(*(_QWORD *)this + 64LL);
  pt = 0;
  rc = 0;
  CLinePtr::CLinePtr((CLinePtr *)v21, (struct CDisplay *)v4);
  CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v22, *(struct CTxtEdit **)this, a2);
  CDropCaret::HideCaret(this);
  *((_DWORD *)this + 5) = -1;
  (*(void (__fastcall **)(__int16 *, _BYTE *, _QWORD, _QWORD, POINT *, _BYTE *, int, _QWORD))(*(_QWORD *)v4 + 240LL))(
    v4,
    v22,
    0,
    0,
    &pt,
    v21,
    0x2000,
    0);
  (*(void (__fastcall **)(_QWORD, RECT *))(**(_QWORD **)(*(_QWORD *)this + 48LL) + 192LL))(
    *(_QWORD *)(*(_QWORD *)this + 48LL),
    &rc);
  CF = (__int16 *)CRchTxtPtr::GetCF((CRchTxtPtr *)v22);
  CDisplay::GetZoomDenominator((CDisplay *)v4);
  ZoomNumerator = CDisplay::GetZoomNumerator((CDisplay *)v4);
  v8 = CW32System::MulDiv(*((_DWORD *)this + 4), ZoomNumerator, v7);
  Ccs = CFontCache::GetCcs(qword_1800A6FC0, (const struct CCharFormat *const)CF, v8, 0, 0);
  v10 = Ccs;
  if ( Ccs )
  {
    v11 = CF[4] * v4[18];
    v20 = 0;
    v19 = 0;
    cy = (v11 + 720) / 1440;
    CCcs::GetOffset(Ccs, (const struct CCharFormat *const)CF, v8, &v20, &v19);
    CLinePtr::GetLine((CLinePtr *)v21);
    Line = CLinePtr::GetLine((CLinePtr *)v21);
    pt.y += *((__int16 *)v10 + 46) - *(__int16 *)(v14 + 14) + *((__int16 *)Line + 6) - cy - v19 - v20;
    v15 = *((_WORD *)v10 + 5);
    if ( v15 )
      *((_WORD *)v10 + 5) = v15 - 1;
    if ( PtInRect(&rc, pt) )
    {
      *(POINT *)((char *)this + 28) = pt;
      *((_DWORD *)this + 5) = cy;
      if ( cy <= *((_DWORD *)this + 6) )
      {
LABEL_8:
        BitBlt(
          *((HDC *)this + 5),
          0,
          0,
          1,
          cy,
          *((HDC *)this + 1),
          *((_DWORD *)this + 7),
          *((_DWORD *)this + 8),
          0xCC0020u);
        CDropCaret::ShowCaret(this);
        goto LABEL_9;
      }
      CompatibleBitmap = CreateCompatibleBitmap(*((HDC *)this + 5), 1, cy);
      v17 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        SelectObject(*((HDC *)this + 5), CompatibleBitmap);
        DeleteObject(*((HGDIOBJ *)this + 7));
        *((_QWORD *)this + 7) = v17;
        *((_DWORD *)this + 6) = cy;
        goto LABEL_8;
      }
    }
  }
LABEL_9:
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x18005b090  mov     [rsp-8+arg_10], rbx
0x18005b095  push    rbp
0x18005b096  push    rsi
0x18005b097  push    rdi
0x18005b098  push    r12
0x18005b09a  push    r13
0x18005b09c  push    r14
0x18005b09e  push    r15
0x18005b0a0  lea     rbp, [rsp-27h]
0x18005b0a5  sub     rsp, 0F0h
0x18005b0ac  mov     rax, cs:__security_cookie
0x18005b0b3  xor     rax, rsp
0x18005b0b6  mov     [rbp+57h+var_40], rax
0x18005b0ba  mov     rdi, rcx
0x18005b0bd  mov     ebx, edx
0x18005b0bf  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005b0c6  call    cs:__imp_EnterCriticalSection
0x18005b0cd  nop     dword ptr [rax+rax+00h]
0x18005b0d2  mov     rax, [rdi]
0x18005b0d5  lea     rcx, [rbp+57h+var_C0]; this
0x18005b0d9  xorps   xmm0, xmm0
0x18005b0dc  xor     r13d, r13d
0x18005b0df  mov     r15, [rax+40h]
0x18005b0e3  mov     rdx, r15; struct CDisplay *
0x18005b0e6  mov     qword ptr [rbp+57h+pt.x], r13
0x18005b0ea  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18005b0ee  call    ??0CLinePtr@@QEAA@PEAVCDisplay@@@Z; CLinePtr::CLinePtr(CDisplay *)
0x18005b0f3  mov     rdx, [rdi]; struct CTxtEdit *
0x18005b0f6  lea     rcx, [rbp+57h+var_A0]; this
0x18005b0fa  mov     r8d, ebx; int
0x18005b0fd  call    ??0CRchTxtPtr@@QEAA@PEAVCTxtEdit@@J@Z; CRchTxtPtr::CRchTxtPtr(CTxtEdit *,long)
0x18005b102  mov     rcx, rdi; this
0x18005b105  call    ?HideCaret@CDropCaret@@QEAAXXZ; CDropCaret::HideCaret(void)
0x18005b10a  mov     qword ptr [rsp+120h+y1], r13
0x18005b10f  lea     rcx, [rbp+57h+var_C0]
0x18005b113  mov     dword ptr [rdi+14h], 0FFFFFFFFh
0x18005b11a  lea     rdx, [rbp+57h+var_A0]
0x18005b11e  mov     rax, [r15]
0x18005b121  xor     r9d, r9d
0x18005b124  mov     [rsp+120h+x1], 2000h
0x18005b12c  xor     r8d, r8d
0x18005b12f  mov     [rsp+120h+hdcSrc], rcx
0x18005b134  lea     rcx, [rbp+57h+pt]
0x18005b138  mov     qword ptr [rsp+120h+cy], rcx
0x18005b13d  mov     rcx, r15
0x18005b140  mov     rax, [rax+0F0h]
0x18005b147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b14c  mov     rax, [rdi]
0x18005b14f  lea     rdx, [rbp+57h+rc]
0x18005b153  mov     rcx, [rax+30h]
0x18005b157  mov     rax, [rcx]
0x18005b15a  mov     rax, [rax+0C0h]
0x18005b161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b166  lea     rcx, [rbp+57h+var_A0]; this
0x18005b16a  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18005b16f  mov     rcx, r15; this
0x18005b172  mov     r14, rax
0x18005b175  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18005b17a  mov     rcx, r15; this
0x18005b17d  mov     r8d, eax
0x18005b180  call    ?GetZoomNumerator@CDisplay@@QEBAJXZ; CDisplay::GetZoomNumerator(void)
0x18005b185  mov     ecx, [rdi+10h]; int
0x18005b188  mov     edx, eax; int
0x18005b18a  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18005b18f  mov     rcx, cs:qword_1800A6FC0; this
0x18005b196  xor     r9d, r9d; HDC
0x18005b199  mov     r8d, eax; int
0x18005b19c  mov     [rsp+120h+cy], r13d; int
0x18005b1a1  mov     rdx, r14; struct CCharFormat *
0x18005b1a4  mov     r12d, eax
0x18005b1a7  call    ?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z; CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)
0x18005b1ac  mov     rsi, rax
0x18005b1af  test    rax, rax
0x18005b1b2  jz      loc_18005B307
0x18005b1b8  movsx   ecx, word ptr [r14+8]
0x18005b1bd  lea     r9, [rbp+57h+var_C4]; int *
0x18005b1c1  movsx   r8d, word ptr [r15+24h]
0x18005b1c6  mov     eax, 0B60B60B7h
0x18005b1cb  imul    r8d, ecx
0x18005b1cf  mov     rcx, rsi; this
0x18005b1d2  mov     [rbp+57h+var_C4], r13d
0x18005b1d6  mov     [rbp+57h+var_C8], r13d
0x18005b1da  add     r8d, 2D0h
0x18005b1e1  imul    r8d
0x18005b1e4  lea     ebx, [r8+rdx]
0x18005b1e8  mov     r8d, r12d; int
0x18005b1eb  sar     ebx, 0Ah
0x18005b1ee  mov     rdx, r14; struct CCharFormat *
0x18005b1f1  mov     eax, ebx
0x18005b1f3  shr     eax, 1Fh
0x18005b1f6  add     ebx, eax
0x18005b1f8  lea     rax, [rbp+57h+var_C8]
0x18005b1fc  mov     qword ptr [rsp+120h+cy], rax; int *
0x18005b201  call    ?GetOffset@CCcs@@QEAAXQEBVCCharFormat@@JPEAJ1@Z; CCcs::GetOffset(CCharFormat const * const,long,long *,long *)
0x18005b206  lea     rcx, [rbp+57h+var_C0]; this
0x18005b20a  call    ?GetLine@CLinePtr@@QEBAPEAVCLine@@XZ; CLinePtr::GetLine(void)
0x18005b20f  lea     rcx, [rbp+57h+var_C0]; this
0x18005b213  mov     r9, rax
0x18005b216  call    ?GetLine@CLinePtr@@QEBAPEAVCLine@@XZ; CLinePtr::GetLine(void)
0x18005b21b  movsx   ecx, word ptr [rsi+5Ch]
0x18005b21f  lea     r14d, [r13+1]
0x18005b223  movsx   edx, word ptr [rax+0Ch]
0x18005b227  movsx   eax, word ptr [r9+0Eh]
0x18005b22c  sub     ecx, eax
0x18005b22e  add     edx, ecx
0x18005b230  sub     edx, ebx
0x18005b232  sub     edx, [rbp+57h+var_C8]
0x18005b235  sub     edx, [rbp+57h+var_C4]
0x18005b238  add     [rbp+57h+pt.y], edx
0x18005b23b  movzx   eax, word ptr [rsi+0Ah]
0x18005b23f  test    ax, ax
0x18005b242  jz      short loc_18005B24C
0x18005b244  sub     ax, r14w
0x18005b248  mov     [rsi+0Ah], ax
0x18005b24c  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x18005b250  lea     rcx, [rbp+57h+rc]; lprc
0x18005b254  call    cs:__imp_PtInRect
0x18005b25b  nop     dword ptr [rax+rax+00h]
0x18005b260  test    eax, eax
0x18005b262  jz      loc_18005B307
0x18005b268  mov     eax, [rbp+57h+pt.x]
0x18005b26b  mov     [rdi+1Ch], eax
0x18005b26e  mov     eax, [rbp+57h+pt.y]
0x18005b271  mov     [rdi+20h], eax
0x18005b274  mov     [rdi+14h], ebx
0x18005b277  cmp     ebx, [rdi+18h]
0x18005b27a  jle     short loc_18005B2C4
0x18005b27c  mov     rcx, [rdi+28h]; hdc
0x18005b280  mov     r8d, ebx; cy
0x18005b283  mov     edx, r14d; cx
0x18005b286  call    cs:__imp_CreateCompatibleBitmap
0x18005b28d  nop     dword ptr [rax+rax+00h]
0x18005b292  mov     rsi, rax
0x18005b295  test    rax, rax
0x18005b298  jz      short loc_18005B307
0x18005b29a  mov     rcx, [rdi+28h]; hdc
0x18005b29e  mov     rdx, rax; h
0x18005b2a1  call    cs:__imp_SelectObject
0x18005b2a8  nop     dword ptr [rax+rax+00h]
0x18005b2ad  mov     rcx, [rdi+38h]; ho
0x18005b2b1  call    cs:__imp_DeleteObject
0x18005b2b8  nop     dword ptr [rax+rax+00h]
0x18005b2bd  mov     [rdi+38h], rsi
0x18005b2c1  mov     [rdi+18h], ebx
0x18005b2c4  mov     eax, [rdi+20h]
0x18005b2c7  mov     r9d, r14d; cx
0x18005b2ca  mov     rcx, [rdi+28h]; hdc
0x18005b2ce  xor     r8d, r8d; y
0x18005b2d1  mov     [rsp+120h+rop], 0CC0020h; rop
0x18005b2d9  xor     edx, edx; x
0x18005b2db  mov     [rsp+120h+y1], eax; y1
0x18005b2df  mov     eax, [rdi+1Ch]
0x18005b2e2  mov     [rsp+120h+x1], eax; x1
0x18005b2e6  mov     rax, [rdi+8]
0x18005b2ea  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x18005b2ef  mov     [rsp+120h+cy], ebx; cy
0x18005b2f3  call    cs:__imp_BitBlt
0x18005b2fa  nop     dword ptr [rax+rax+00h]
0x18005b2ff  mov     rcx, rdi; this
0x18005b302  call    ?ShowCaret@CDropCaret@@QEAAXXZ; CDropCaret::ShowCaret(void)
0x18005b307  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005b30e  call    cs:__imp_LeaveCriticalSection
0x18005b315  nop     dword ptr [rax+rax+00h]
0x18005b31a  mov     rcx, [rbp+57h+var_40]
0x18005b31e  xor     rcx, rsp; StackCookie
0x18005b321  call    __security_check_cookie
0x18005b326  mov     rbx, [rsp+120h+arg_10]
0x18005b32e  add     rsp, 0F0h
0x18005b335  pop     r15
0x18005b337  pop     r14
0x18005b339  pop     r13
0x18005b33b  pop     r12
0x18005b33d  pop     rdi
0x18005b33e  pop     rsi
0x18005b33f  pop     rbp
0x18005b340  retn
```
