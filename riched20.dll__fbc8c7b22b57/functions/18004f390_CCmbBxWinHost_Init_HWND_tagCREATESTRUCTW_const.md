# CCmbBxWinHost::Init(HWND__ *,tagCREATESTRUCTW const *)

- ea: `0x18004f390`
- end: `0x18004f695`
- name: `?Init@CCmbBxWinHost@@UEAAHPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, HWND hWnd, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18004f390`
- `0x1800616e8`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x18004f41e`
- `USER32!SetWindowLongPtrW` at `0x18004f4f7`
- `USER32!SetWindowLongPtrW` at `0x18004f50f`
- `USER32!SetWindowLongPtrW` at `0x18004f41e`
- `USER32!SetWindowLongPtrW` at `0x18004f4f7`
- `USER32!SetWindowLongPtrW` at `0x18004f50f`

## pseudocode

```c
__int64 __fastcall CCmbBxWinHost::Init(LONG_PTR dwNewLong, HWND hWnd, const struct tagCREATESTRUCTW *a3)
{
  int hMenu; // eax
  DWORD dwExStyle; // r8d
  LONG style; // edx
  unsigned int v10; // edi
  unsigned int v11; // edx
  int v12; // eax
  bool v13; // zf
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh]
  __int16 v18; // [rsp+3Ah] [rbp-C6h]
  __int16 v19; // [rsp+48h] [rbp-B8h]
  _DWORD v20[6]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v21; // [rsp+E8h] [rbp-18h]

  if ( !a3->lpszClass )
    return 0xFFFFFFFFLL;
  *(_DWORD *)(dwNewLong + 52) &= ~0x800u;
  *(_DWORD *)(dwNewLong + 120) &= 0xFFFFFF60;
  *(_DWORD *)(dwNewLong + 224) = 0;
  hMenu = (int)a3->hMenu;
  *(_DWORD *)(dwNewLong + 52) &= 0xFFFF8FFF;
  *(_DWORD *)(dwNewLong + 120) &= 0xFFFFF3FF;
  *(_DWORD *)(dwNewLong + 236) = hMenu;
  *(_DWORD *)(dwNewLong + 228) = -2;
  *(_QWORD *)(dwNewLong + 200) = 0;
  if ( hWnd )
    SetWindowLongPtrW(hWnd, 0, dwNewLong);
  *(_QWORD *)(dwNewLong + 16) = hWnd;
  *(_QWORD *)(dwNewLong + 24) = a3->hwndParent;
  dwExStyle = a3->dwExStyle;
  *(_DWORD *)(dwNewLong + 48) = dwExStyle;
  style = a3->style;
  v10 = dwExStyle & 0x7208;
  if ( (style & 2) != 0 )
  {
    *(_DWORD *)(dwNewLong + 240) = 2;
    if ( (style & 1) != 0 )
      *(_DWORD *)(dwNewLong + 240) = 3;
  }
  if ( (style & 0x10) != 0 )
    *(_DWORD *)(dwNewLong + 120) |= 4u;
  if ( (style & 0x8000000) != 0 )
    *(_DWORD *)(dwNewLong + 52) |= 0x800u;
  if ( (style & 0x400) != 0 )
    *(_DWORD *)(dwNewLong + 120) |= 0x80u;
  if ( (dwExStyle & 0x1000) != 0 )
  {
    *(_DWORD *)(dwNewLong + 120) |= 1u;
    style |= 2u;
  }
  v11 = style & 0xFFFFFF3F | 0x80;
  *(_DWORD *)(dwNewLong + 44) = v11;
  if ( (v11 & 0x800000) != 0 || (dwExStyle & 0x200) != 0 )
  {
    *(_DWORD *)(dwNewLong + 52) |= 1u;
    v11 &= ~0x800000u;
    *(_DWORD *)(dwNewLong + 48) = dwExStyle | 0x200;
    v10 |= 0x200u;
    *(_DWORD *)(dwNewLong + 44) = v11;
  }
  if ( (v11 & 0x8000000) != 0 )
    *(_DWORD *)(dwNewLong + 52) |= 0x800u;
  if ( (v11 & 0x200000) != 0 )
    v11 &= ~0x200000u;
  SetWindowLongPtrW(hWnd, -16, v11);
  SetWindowLongPtrW(*(HWND *)(dwNewLong + 16), -20, v10);
  if ( (int)CTxtWinHost::CreateTextServices((CTxtWinHost *)dwNewLong) < 0 )
    return 0;
  *(_WORD *)(dwNewLong + 102) = 257;
  memset_0(&v16, 0, 0x9Cu);
  v12 = 0;
  v13 = (*(_DWORD *)(dwNewLong + 48) & 0x1000) == 0;
  v17 = 0;
  if ( !v13 )
  {
    v12 = 8;
    v19 = 2;
    v17 = 8;
  }
  if ( (*(_DWORD *)(dwNewLong + 48) & 0x2000) != 0 )
  {
    v12 |= 0x10000u;
    v18 = 1;
    v17 = v12;
  }
  if ( v12 )
  {
    v14 = *(_QWORD *)(dwNewLong + 32);
    v16 = 188;
    (*(void (__fastcall **)(__int64, __int64, __int64, int *, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, 1095, 4, &v16, 0);
  }
  memset_0(v20, 0, 0x9Cu);
  if ( (*(_BYTE *)(dwNewLong + 120) & 1) != 0 )
  {
    v15 = *(_QWORD *)(dwNewLong + 32);
    v20[0] = 156;
    v20[1] = 8;
    v21 = 2;
    (*(void (__fastcall **)(__int64, __int64, __int64, _DWORD *, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, 1095, 4, v20, 0);
  }
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**(_QWORD **)(dwNewLong + 32) + 24LL))(
    *(_QWORD *)(dwNewLong + 32),
    1093,
    0,
    3,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**(_QWORD **)(dwNewLong + 32) + 24LL))(
    *(_QWORD *)(dwNewLong + 32),
    1144,
    0,
    59,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(dwNewLong + 32) + 24LL))(
    *(_QWORD *)(dwNewLong + 32),
    1192,
    0,
    0,
    0);
  return 1;
}

```

## disassembly

```asm
0x18004f390  mov     [rsp-8+arg_10], rbx
0x18004f395  push    rbp
0x18004f396  push    rsi
0x18004f397  push    rdi
0x18004f398  push    r12
0x18004f39a  push    r15
0x18004f39c  lea     rbp, [rsp-80h]
0x18004f3a1  sub     rsp, 180h
0x18004f3a8  mov     rax, cs:__security_cookie
0x18004f3af  xor     rax, rsp
0x18004f3b2  mov     [rbp+0A0h+var_30], rax
0x18004f3b6  cmp     qword ptr [r8+40h], 0
0x18004f3bb  mov     rdi, r8
0x18004f3be  mov     rsi, rdx
0x18004f3c1  mov     rbx, rcx
0x18004f3c4  jnz     short loc_18004F3CE
0x18004f3c6  or      eax, 0FFFFFFFFh
0x18004f3c9  jmp     loc_18004F671
0x18004f3ce  btr     dword ptr [rcx+34h], 0Bh
0x18004f3d3  and     dword ptr [rcx+78h], 0FFFFFF60h
0x18004f3da  mov     dword ptr [rcx+0E0h], 0
0x18004f3e4  mov     eax, [r8+10h]
0x18004f3e8  and     dword ptr [rcx+34h], 0FFFF8FFFh
0x18004f3ef  and     dword ptr [rcx+78h], 0FFFFF3FFh
0x18004f3f6  mov     [rcx+0ECh], eax
0x18004f3fc  mov     dword ptr [rcx+0E4h], 0FFFFFFFEh
0x18004f406  mov     qword ptr [rcx+0C8h], 0
0x18004f411  test    rsi, rsi
0x18004f414  jz      short loc_18004F42A
0x18004f416  mov     r8, rbx; dwNewLong
0x18004f419  xor     edx, edx; nIndex
0x18004f41b  mov     rcx, rsi; hWnd
0x18004f41e  call    cs:__imp_SetWindowLongPtrW
0x18004f425  nop     dword ptr [rax+rax+00h]
0x18004f42a  mov     [rbx+10h], rsi
0x18004f42e  mov     r15d, 1
0x18004f434  mov     rax, [rdi+18h]
0x18004f438  mov     [rbx+18h], rax
0x18004f43c  mov     r8d, [rdi+48h]
0x18004f440  mov     [rbx+30h], r8d
0x18004f444  lea     r12d, [r15+1]
0x18004f448  mov     edx, [rdi+30h]
0x18004f44b  mov     edi, r8d
0x18004f44e  and     edi, 7208h
0x18004f454  test    r12b, dl
0x18004f457  jz      short loc_18004F46F
0x18004f459  mov     [rbx+0F0h], r12d
0x18004f460  test    r15b, dl
0x18004f463  jz      short loc_18004F46F
0x18004f465  mov     dword ptr [rbx+0F0h], 3
0x18004f46f  test    dl, 10h
0x18004f472  jz      short loc_18004F478
0x18004f474  or      dword ptr [rbx+78h], 4
0x18004f478  bt      edx, 1Bh
0x18004f47c  mov     r9d, 800h
0x18004f482  jnb     short loc_18004F488
0x18004f484  or      [rbx+34h], r9d
0x18004f488  mov     eax, 80h
0x18004f48d  bt      edx, 0Ah
0x18004f491  jnb     short loc_18004F496
0x18004f493  or      [rbx+78h], eax
0x18004f496  bt      r8d, 0Ch
0x18004f49b  jnb     short loc_18004F4A4
0x18004f49d  or      [rbx+78h], r15d
0x18004f4a1  or      edx, r12d
0x18004f4a4  and     edx, 0FFFFFFBFh
0x18004f4a7  or      edx, eax
0x18004f4a9  bt      edx, 17h
0x18004f4ad  mov     [rbx+2Ch], edx
0x18004f4b0  setnb   cl
0x18004f4b3  bt      r8d, 9
0x18004f4b8  setnb   al
0x18004f4bb  test    al, cl
0x18004f4bd  jnz     short loc_18004F4D8
0x18004f4bf  or      [rbx+34h], r15d
0x18004f4c3  mov     eax, 200h
0x18004f4c8  or      r8d, eax
0x18004f4cb  btr     edx, 17h
0x18004f4cf  mov     [rbx+30h], r8d
0x18004f4d3  or      edi, eax
0x18004f4d5  mov     [rbx+2Ch], edx
0x18004f4d8  bt      edx, 1Bh
0x18004f4dc  jnb     short loc_18004F4E2
0x18004f4de  or      [rbx+34h], r9d
0x18004f4e2  bt      edx, 15h
0x18004f4e6  jnb     short loc_18004F4EC
0x18004f4e8  btr     edx, 15h
0x18004f4ec  mov     r8d, edx; dwNewLong
0x18004f4ef  mov     rcx, rsi; hWnd
0x18004f4f2  mov     edx, 0FFFFFFF0h; nIndex
0x18004f4f7  call    cs:__imp_SetWindowLongPtrW
0x18004f4fe  nop     dword ptr [rax+rax+00h]
0x18004f503  mov     rcx, [rbx+10h]; hWnd
0x18004f507  mov     edx, 0FFFFFFECh; nIndex
0x18004f50c  mov     r8d, edi; dwNewLong
0x18004f50f  call    cs:__imp_SetWindowLongPtrW
0x18004f516  nop     dword ptr [rax+rax+00h]
0x18004f51b  mov     rcx, rbx; this
0x18004f51e  call    ?CreateTextServices@CTxtWinHost@@QEAAJXZ; CTxtWinHost::CreateTextServices(void)
0x18004f523  test    eax, eax
0x18004f525  jns     short loc_18004F52E
0x18004f527  xor     eax, eax
0x18004f529  jmp     loc_18004F671
0x18004f52e  mov     edi, 9Ch
0x18004f533  mov     word ptr [rbx+66h], 101h
0x18004f539  mov     r8d, edi; Size
0x18004f53c  lea     rcx, [rsp+1A0h+var_170]; void *
0x18004f541  xor     edx, edx; Val
0x18004f543  call    memset_0
0x18004f548  xor     eax, eax
0x18004f54a  test    dword ptr [rbx+30h], 1000h
0x18004f551  mov     [rsp+1A0h+var_16C], eax
0x18004f555  jz      short loc_18004F566
0x18004f557  mov     eax, 8
0x18004f55c  mov     [rsp+1A0h+var_158], r12w
0x18004f562  mov     [rsp+1A0h+var_16C], eax
0x18004f566  test    dword ptr [rbx+30h], 2000h
0x18004f56d  jz      short loc_18004F57D
0x18004f56f  bts     eax, 10h
0x18004f573  mov     [rsp+1A0h+var_166], r15w
0x18004f579  mov     [rsp+1A0h+var_16C], eax
0x18004f57d  mov     esi, 447h
0x18004f582  test    eax, eax
0x18004f584  jz      short loc_18004F5B4
0x18004f586  mov     rcx, [rbx+20h]
0x18004f58a  lea     r9, [rsp+1A0h+var_170]
0x18004f58f  mov     [rsp+1A0h+var_170], 0BCh
0x18004f597  mov     r8d, 4
0x18004f59d  mov     edx, esi
0x18004f59f  mov     [rsp+1A0h+var_180], 0
0x18004f5a8  mov     rax, [rcx]
0x18004f5ab  mov     rax, [rax+18h]
0x18004f5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5b4  mov     r8, rdi; Size
0x18004f5b7  lea     rcx, [rbp+0A0h+var_D0]; void *
0x18004f5bb  xor     edx, edx; Val
0x18004f5bd  call    memset_0
0x18004f5c2  test    [rbx+78h], r15b
0x18004f5c6  jz      short loc_18004F5FC
0x18004f5c8  mov     rcx, [rbx+20h]
0x18004f5cc  lea     r9, [rbp+0A0h+var_D0]
0x18004f5d0  mov     [rbp+0A0h+var_D0], edi
0x18004f5d3  mov     r8d, 4
0x18004f5d9  mov     [rbp+0A0h+var_CC], 8
0x18004f5e0  mov     edx, esi
0x18004f5e2  mov     [rbp+0A0h+var_B8], r12w
0x18004f5e7  mov     rax, [rcx]
0x18004f5ea  mov     [rsp+1A0h+var_180], 0
0x18004f5f3  mov     rax, [rax+18h]
0x18004f5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5fc  mov     rcx, [rbx+20h]
0x18004f600  mov     r9d, 3
0x18004f606  xor     r8d, r8d
0x18004f609  mov     [rsp+1A0h+var_180], 0
0x18004f612  mov     edx, 445h
0x18004f617  mov     rax, [rcx]
0x18004f61a  mov     rax, [rax+18h]
0x18004f61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f623  mov     rcx, [rbx+20h]
0x18004f627  mov     r9d, 3Bh ; ';'
0x18004f62d  xor     r8d, r8d
0x18004f630  mov     [rsp+1A0h+var_180], 0
0x18004f639  mov     edx, 478h
0x18004f63e  mov     rax, [rcx]
0x18004f641  mov     rax, [rax+18h]
0x18004f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f64a  mov     rcx, [rbx+20h]
0x18004f64e  xor     r9d, r9d
0x18004f651  xor     r8d, r8d
0x18004f654  mov     [rsp+1A0h+var_180], 0
0x18004f65d  mov     rdx, [rcx]
0x18004f660  mov     rax, [rdx+18h]
0x18004f664  mov     edx, 4A8h
0x18004f669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f66e  mov     eax, r15d
0x18004f671  mov     rcx, [rbp+0A0h+var_30]
0x18004f675  xor     rcx, rsp; StackCookie
0x18004f678  call    __security_check_cookie
0x18004f67d  mov     rbx, [rsp+1A0h+arg_10]
0x18004f685  add     rsp, 180h
0x18004f68c  pop     r15
0x18004f68e  pop     r12
0x18004f690  pop     rdi
0x18004f691  pop     rsi
0x18004f692  pop     rbp
0x18004f693  retn
```
