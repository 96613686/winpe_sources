# CBrush::Draw(long,long,long,long,long,ulong,int,int)

- ea: `0x18014e580`
- end: `0x18014e712`
- name: `?Draw@CBrush@@QEAAXJJJJJKHH@Z`
- size: `402`
- prototype: `void __fastcall(CBrush *__hidden this, int, int, int, int, int, COLORREF color, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18012214c`

## callees

- `0x18004e140`
- `0x1800f3ae8`
- `0x18013ce80`
- `0x18014e580`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014e62b`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014e62b`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18014e5ff`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18014e5ff`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014e647`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014e647`

## pseudocode

```c
void __fastcall CBrush::Draw(CBrush *this, LONG a2, LONG a3, LONG a4, LONG a5, int a6, COLORREF color, int a8, int a9)
{
  int v9; // esi
  HBRUSH SolidBrush; // r13
  HDC v16; // rax
  HGDIOBJ v17; // rax
  LONG v18; // eax
  __int64 v20; // rcx
  struct tagRECT v21; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT v22; // [rsp+40h] [rbp-28h] BYREF

  v9 = a6;
  if ( !a6 )
  {
    if ( a8 )
      return;
    v9 = 1;
    color = 12632256;
  }
  *(_QWORD *)&v21.left = *((_QWORD *)this + 3);
  if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v21.left + 336LL) + 48LL))(*(_QWORD *)(*(_QWORD *)&v21.left + 336LL))
    && (!*((_QWORD *)this + 2) || *(_DWORD *)this != color) )
  {
    SolidBrush = CreateSolidBrush(color);
    v16 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v21.left + 336LL) + 48LL))(*(_QWORD *)(*(_QWORD *)&v21.left + 336LL));
    v17 = SelectObject(v16, SolidBrush);
    if ( *((_QWORD *)this + 2) )
      DeleteObject(v17);
    else
      *((_QWORD *)this + 1) = v17;
    *((_QWORD *)this + 2) = SolidBrush;
    *(_DWORD *)this = color;
  }
  v21.top = a3;
  v18 = a2;
  if ( a2 <= a4 )
  {
    v18 = a4;
    a4 = a2;
  }
  v21.left = a4;
  if ( a4 == v18 )
  {
    v21.right = a4 + v9;
  }
  else
  {
    v21.right = v18;
    a5 = a3 + v9;
  }
  v21.bottom = a5;
  if ( !a9
    || (unsigned int)CW32System::IntersectRect(&v21, &v21, (const struct tagRECT *)(*((_QWORD *)this + 3) + 376LL)) )
  {
    v20 = *((_QWORD *)this + 3);
    v22 = 0;
    CDisplay::RectFromRectuv(*(CDisplay **)(v20 + 152), &v22, (const struct RECTUV *)&v21, 1, 0);
    (*(void (__fastcall **)(_QWORD, struct tagRECT *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 336LL) + 248LL))(
      *(_QWORD *)(*((_QWORD *)this + 3) + 336LL),
      &v22,
      color);
  }
}

```

## disassembly

```asm
0x18014e580  push    rbp
0x18014e582  push    rbx
0x18014e583  push    rsi
0x18014e584  push    rdi
0x18014e585  push    r12
0x18014e587  push    r13
0x18014e589  push    r14
0x18014e58b  push    r15
0x18014e58d  mov     rbp, rsp
0x18014e590  sub     rsp, 68h
0x18014e594  mov     rax, cs:__security_cookie
0x18014e59b  xor     rax, rsp
0x18014e59e  mov     [rbp+var_18], rax
0x18014e5a2  mov     esi, [rbp+arg_28]
0x18014e5a5  mov     edi, r9d
0x18014e5a8  mov     r14d, [rbp+color]
0x18014e5ac  mov     r12d, r8d
0x18014e5af  mov     r15d, edx
0x18014e5b2  mov     rbx, rcx
0x18014e5b5  test    esi, esi
0x18014e5b7  jnz     short loc_18014E5D0
0x18014e5b9  cmp     [rbp+arg_38], esi
0x18014e5bf  jnz     loc_18014E6F4
0x18014e5c5  mov     esi, 1
0x18014e5ca  mov     r14d, 0C0C0C0h
0x18014e5d0  mov     rax, [rcx+18h]
0x18014e5d4  mov     qword ptr [rbp+var_38.left], rax
0x18014e5d8  mov     rcx, [rax+150h]
0x18014e5df  mov     rax, [rcx]
0x18014e5e2  mov     rax, [rax+30h]
0x18014e5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e5eb  test    rax, rax
0x18014e5ee  jz      short loc_18014E65A
0x18014e5f0  cmp     qword ptr [rbx+10h], 0
0x18014e5f5  jz      short loc_18014E5FC
0x18014e5f7  cmp     [rbx], r14d
0x18014e5fa  jz      short loc_18014E65A
0x18014e5fc  mov     ecx, r14d; color
0x18014e5ff  call    cs:__imp_CreateSolidBrush
0x18014e606  nop     dword ptr [rax+rax+00h]
0x18014e60b  mov     rcx, qword ptr [rbp+var_38.left]
0x18014e60f  mov     r13, rax
0x18014e612  mov     rcx, [rcx+150h]
0x18014e619  mov     rdx, [rcx]
0x18014e61c  mov     rax, [rdx+30h]
0x18014e620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e625  mov     rdx, r13; h
0x18014e628  mov     rcx, rax; hdc
0x18014e62b  call    cs:__imp_SelectObject
0x18014e632  nop     dword ptr [rax+rax+00h]
0x18014e637  cmp     qword ptr [rbx+10h], 0
0x18014e63c  jnz     short loc_18014E644
0x18014e63e  mov     [rbx+8], rax
0x18014e642  jmp     short loc_18014E653
0x18014e644  mov     rcx, rax; ho
0x18014e647  call    cs:__imp_DeleteObject
0x18014e64e  nop     dword ptr [rax+rax+00h]
0x18014e653  mov     [rbx+10h], r13
0x18014e657  mov     [rbx], r14d
0x18014e65a  cmp     r15d, edi
0x18014e65d  mov     [rbp+var_38.top], r12d
0x18014e661  mov     eax, r15d
0x18014e664  cmovle  eax, edi
0x18014e667  cmovle  edi, r15d
0x18014e66b  mov     [rbp+var_38.left], edi
0x18014e66e  cmp     edi, eax
0x18014e670  jnz     short loc_18014E67D
0x18014e672  lea     eax, [rdi+rsi]
0x18014e675  mov     [rbp+var_38.right], eax
0x18014e678  mov     eax, [rbp+arg_20]
0x18014e67b  jmp     short loc_18014E684
0x18014e67d  mov     [rbp+var_38.right], eax
0x18014e680  lea     eax, [r12+rsi]
0x18014e684  cmp     [rbp+arg_40], 0
0x18014e68b  mov     [rbp+var_38.bottom], eax
0x18014e68e  jz      short loc_18014E6AC
0x18014e690  mov     r8, [rbx+18h]
0x18014e694  lea     rdx, [rbp+var_38]; struct tagRECT *
0x18014e698  add     r8, 178h; struct tagRECT *
0x18014e69f  lea     rcx, [rbp+var_38]; struct tagRECT *
0x18014e6a3  call    ?IntersectRect@CW32System@@SAHPEAUtagRECT@@PEBU2@1@Z; CW32System::IntersectRect(tagRECT *,tagRECT const *,tagRECT const *)
0x18014e6a8  test    eax, eax
0x18014e6aa  jz      short loc_18014E6F4
0x18014e6ac  mov     rcx, [rbx+18h]
0x18014e6b0  lea     r8, [rbp+var_38]; struct RECTUV *
0x18014e6b4  xorps   xmm0, xmm0
0x18014e6b7  mov     [rsp+68h+var_48], 0; bool
0x18014e6bc  movups  xmmword ptr [rbp+var_28.left], xmm0
0x18014e6c0  mov     r9b, 1; bool
0x18014e6c3  lea     rdx, [rbp+var_28]; struct tagRECT *
0x18014e6c7  mov     rcx, [rcx+98h]; this
0x18014e6ce  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x18014e6d3  mov     rax, [rbx+18h]
0x18014e6d7  lea     rdx, [rbp+var_28]
0x18014e6db  mov     r8d, r14d
0x18014e6de  mov     rcx, [rax+150h]
0x18014e6e5  mov     rax, [rcx]
0x18014e6e8  mov     rax, [rax+0F8h]
0x18014e6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e6f4  mov     rcx, [rbp+var_18]
0x18014e6f8  xor     rcx, rsp; StackCookie
0x18014e6fb  call    __security_check_cookie
0x18014e700  add     rsp, 68h
0x18014e704  pop     r15
0x18014e706  pop     r14
0x18014e708  pop     r13
0x18014e70a  pop     r12
0x18014e70c  pop     rdi
0x18014e70d  pop     rsi
0x18014e70e  pop     rbx
0x18014e70f  pop     rbp
0x18014e710  retn
```
