# CDropCaret::DrawCaret(long)

- ea: `0x180059ab0`
- end: `0x180059d37`
- name: `?DrawCaret@CDropCaret@@QEAAXJ@Z`
- size: `647`
- prototype: `void __fastcall(CDropCaret *__hidden this, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180059a20`

## callees

- `0x180008f80`
- `0x18000b440`
- `0x18000d4a0`
- `0x18000df8c`
- `0x180038bd0`
- `0x180039500`
- `0x18003a130`
- `0x18003b4b0`
- `0x18003de64`
- `0x180059ab0`
- `0x18005a0a0`
- `0x18005a15c`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180059ae6`
- `KERNEL32!EnterCriticalSection` at `0x180059ae6`
- `KERNEL32!LeaveCriticalSection` at `0x180059d0a`
- `KERNEL32!LeaveCriticalSection` at `0x180059d0a`
- `USER32!PtInRect` at `0x180059c6e`
- `USER32!PtInRect` at `0x180059c6e`
- `GDI32!BitBlt` at `0x180059cf5`
- `GDI32!BitBlt` at `0x180059cf5`
- `GDI32!DeleteObject` at `0x180059cb9`
- `GDI32!DeleteObject` at `0x180059cb9`
- `GDI32!SelectObject` at `0x180059caf`
- `GDI32!SelectObject` at `0x180059caf`
- `GDI32!CreateCompatibleBitmap` at `0x180059c9a`
- `GDI32!CreateCompatibleBitmap` at `0x180059c9a`

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
  Ccs = CFontCache::GetCcs(qword_1800A3EE0, (const struct CCharFormat *const)CF, v8, 0, 0);
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
0x180059ab0  mov     [rsp-8+arg_10], rbx
0x180059ab5  push    rbp
0x180059ab6  push    rsi
0x180059ab7  push    rdi
0x180059ab8  push    r12
0x180059aba  push    r13
0x180059abc  push    r14
0x180059abe  push    r15
0x180059ac0  lea     rbp, [rsp-27h]
0x180059ac5  sub     rsp, 0F0h
0x180059acc  mov     rax, cs:__security_cookie
0x180059ad3  xor     rax, rsp
0x180059ad6  mov     [rbp+57h+var_40], rax
0x180059ada  mov     rdi, rcx
0x180059add  mov     ebx, edx
0x180059adf  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059ae6  call    cs:__imp_EnterCriticalSection
0x180059aec  mov     rax, [rdi]
0x180059aef  lea     rcx, [rbp+57h+var_C0]; this
0x180059af3  xorps   xmm0, xmm0
0x180059af6  xor     r13d, r13d
0x180059af9  mov     r15, [rax+40h]
0x180059afd  mov     rdx, r15; struct CDisplay *
0x180059b00  mov     qword ptr [rbp+57h+pt.x], r13
0x180059b04  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180059b08  call    ??0CLinePtr@@QEAA@PEAVCDisplay@@@Z; CLinePtr::CLinePtr(CDisplay *)
0x180059b0d  mov     rdx, [rdi]; struct CTxtEdit *
0x180059b10  lea     rcx, [rbp+57h+var_A0]; this
0x180059b14  mov     r8d, ebx; int
0x180059b17  call    ??0CRchTxtPtr@@QEAA@PEAVCTxtEdit@@J@Z; CRchTxtPtr::CRchTxtPtr(CTxtEdit *,long)
0x180059b1c  mov     rcx, rdi; this
0x180059b1f  call    ?HideCaret@CDropCaret@@QEAAXXZ; CDropCaret::HideCaret(void)
0x180059b24  mov     qword ptr [rsp+120h+y1], r13
0x180059b29  lea     rcx, [rbp+57h+var_C0]
0x180059b2d  mov     dword ptr [rdi+14h], 0FFFFFFFFh
0x180059b34  lea     rdx, [rbp+57h+var_A0]
0x180059b38  mov     rax, [r15]
0x180059b3b  xor     r9d, r9d
0x180059b3e  mov     [rsp+120h+x1], 2000h
0x180059b46  xor     r8d, r8d
0x180059b49  mov     [rsp+120h+hdcSrc], rcx
0x180059b4e  lea     rcx, [rbp+57h+pt]
0x180059b52  mov     qword ptr [rsp+120h+cy], rcx
0x180059b57  mov     rcx, r15
0x180059b5a  mov     rax, [rax+0F0h]
0x180059b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b66  mov     rax, [rdi]
0x180059b69  lea     rdx, [rbp+57h+rc]
0x180059b6d  mov     rcx, [rax+30h]
0x180059b71  mov     rax, [rcx]
0x180059b74  mov     rax, [rax+0C0h]
0x180059b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b80  lea     rcx, [rbp+57h+var_A0]; this
0x180059b84  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x180059b89  mov     rcx, r15; this
0x180059b8c  mov     r14, rax
0x180059b8f  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x180059b94  mov     rcx, r15; this
0x180059b97  mov     r8d, eax
0x180059b9a  call    ?GetZoomNumerator@CDisplay@@QEBAJXZ; CDisplay::GetZoomNumerator(void)
0x180059b9f  mov     ecx, [rdi+10h]; int
0x180059ba2  mov     edx, eax; int
0x180059ba4  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x180059ba9  mov     rcx, cs:qword_1800A3EE0; this
0x180059bb0  xor     r9d, r9d; HDC
0x180059bb3  mov     r8d, eax; int
0x180059bb6  mov     [rsp+120h+cy], r13d; int
0x180059bbb  mov     rdx, r14; struct CCharFormat *
0x180059bbe  mov     r12d, eax
0x180059bc1  call    ?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z; CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)
0x180059bc6  mov     rsi, rax
0x180059bc9  test    rax, rax
0x180059bcc  jz      loc_180059D03
0x180059bd2  movsx   ecx, word ptr [r14+8]
0x180059bd7  lea     r9, [rbp+57h+var_C4]; int *
0x180059bdb  movsx   r8d, word ptr [r15+24h]
0x180059be0  mov     eax, 0B60B60B7h
0x180059be5  imul    r8d, ecx
0x180059be9  mov     rcx, rsi; this
0x180059bec  mov     [rbp+57h+var_C4], r13d
0x180059bf0  mov     [rbp+57h+var_C8], r13d
0x180059bf4  add     r8d, 2D0h
0x180059bfb  imul    r8d
0x180059bfe  lea     ebx, [r8+rdx]
0x180059c02  mov     r8d, r12d; int
0x180059c05  sar     ebx, 0Ah
0x180059c08  mov     rdx, r14; struct CCharFormat *
0x180059c0b  mov     eax, ebx
0x180059c0d  shr     eax, 1Fh
0x180059c10  add     ebx, eax
0x180059c12  lea     rax, [rbp+57h+var_C8]
0x180059c16  mov     qword ptr [rsp+120h+cy], rax; int *
0x180059c1b  call    ?GetOffset@CCcs@@QEAAXQEBVCCharFormat@@JPEAJ1@Z; CCcs::GetOffset(CCharFormat const * const,long,long *,long *)
0x180059c20  lea     rcx, [rbp+57h+var_C0]; this
0x180059c24  call    ?GetLine@CLinePtr@@QEBAPEAVCLine@@XZ; CLinePtr::GetLine(void)
0x180059c29  lea     rcx, [rbp+57h+var_C0]; this
0x180059c2d  mov     r9, rax
0x180059c30  call    ?GetLine@CLinePtr@@QEBAPEAVCLine@@XZ; CLinePtr::GetLine(void)
0x180059c35  movsx   ecx, word ptr [rsi+5Ch]
0x180059c39  lea     r14d, [r13+1]
0x180059c3d  movsx   edx, word ptr [rax+0Ch]
0x180059c41  movsx   eax, word ptr [r9+0Eh]
0x180059c46  sub     ecx, eax
0x180059c48  add     edx, ecx
0x180059c4a  sub     edx, ebx
0x180059c4c  sub     edx, [rbp+57h+var_C8]
0x180059c4f  sub     edx, [rbp+57h+var_C4]
0x180059c52  add     [rbp+57h+pt.y], edx
0x180059c55  movzx   eax, word ptr [rsi+0Ah]
0x180059c59  test    ax, ax
0x180059c5c  jz      short loc_180059C66
0x180059c5e  sub     ax, r14w
0x180059c62  mov     [rsi+0Ah], ax
0x180059c66  mov     rdx, qword ptr [rbp+57h+pt.x]; pt
0x180059c6a  lea     rcx, [rbp+57h+rc]; lprc
0x180059c6e  call    cs:__imp_PtInRect
0x180059c74  test    eax, eax
0x180059c76  jz      loc_180059D03
0x180059c7c  mov     eax, [rbp+57h+pt.x]
0x180059c7f  mov     [rdi+1Ch], eax
0x180059c82  mov     eax, [rbp+57h+pt.y]
0x180059c85  mov     [rdi+20h], eax
0x180059c88  mov     [rdi+14h], ebx
0x180059c8b  cmp     ebx, [rdi+18h]
0x180059c8e  jle     short loc_180059CC6
0x180059c90  mov     rcx, [rdi+28h]; hdc
0x180059c94  mov     r8d, ebx; cy
0x180059c97  mov     edx, r14d; cx
0x180059c9a  call    cs:__imp_CreateCompatibleBitmap
0x180059ca0  mov     rsi, rax
0x180059ca3  test    rax, rax
0x180059ca6  jz      short loc_180059D03
0x180059ca8  mov     rcx, [rdi+28h]; hdc
0x180059cac  mov     rdx, rax; h
0x180059caf  call    cs:__imp_SelectObject
0x180059cb5  mov     rcx, [rdi+38h]; ho
0x180059cb9  call    cs:__imp_DeleteObject
0x180059cbf  mov     [rdi+38h], rsi
0x180059cc3  mov     [rdi+18h], ebx
0x180059cc6  mov     eax, [rdi+20h]
0x180059cc9  mov     r9d, r14d; cx
0x180059ccc  mov     rcx, [rdi+28h]; hdc
0x180059cd0  xor     r8d, r8d; y
0x180059cd3  mov     [rsp+120h+rop], 0CC0020h; rop
0x180059cdb  xor     edx, edx; x
0x180059cdd  mov     [rsp+120h+y1], eax; y1
0x180059ce1  mov     eax, [rdi+1Ch]
0x180059ce4  mov     [rsp+120h+x1], eax; x1
0x180059ce8  mov     rax, [rdi+8]
0x180059cec  mov     [rsp+120h+hdcSrc], rax; hdcSrc
0x180059cf1  mov     [rsp+120h+cy], ebx; cy
0x180059cf5  call    cs:__imp_BitBlt
0x180059cfb  mov     rcx, rdi; this
0x180059cfe  call    ?ShowCaret@CDropCaret@@QEAAXXZ; CDropCaret::ShowCaret(void)
0x180059d03  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059d0a  call    cs:__imp_LeaveCriticalSection
0x180059d10  mov     rcx, [rbp+57h+var_40]
0x180059d14  xor     rcx, rsp; StackCookie
0x180059d17  call    __security_check_cookie
0x180059d1c  mov     rbx, [rsp+120h+arg_10]
0x180059d24  add     rsp, 0F0h
0x180059d2b  pop     r15
0x180059d2d  pop     r14
0x180059d2f  pop     r13
0x180059d31  pop     r12
0x180059d33  pop     rdi
0x180059d34  pop     rsi
0x180059d35  pop     rbp
0x180059d36  retn
```
