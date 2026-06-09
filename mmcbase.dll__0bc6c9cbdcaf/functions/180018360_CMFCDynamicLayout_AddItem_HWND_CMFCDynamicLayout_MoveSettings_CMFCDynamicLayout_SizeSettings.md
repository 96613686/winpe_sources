# CMFCDynamicLayout::AddItem(HWND__ *,CMFCDynamicLayout::MoveSettings,CMFCDynamicLayout::SizeSettings)

- ea: `0x180018360`
- end: `0x18001844c`
- name: `?AddItem@CMFCDynamicLayout@@QEAAHPEAUHWND__@@UMoveSettings@1@USizeSettings@1@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800187a4`

## callees

- `0x180018360`
- `0x180018454`
- `0x1800188b0`
- `0x180018c44`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x1800183d1`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x1800183d1`
- `USER32!IsChild` at `0x1800183a7`
- `USER32!IsChild` at `0x1800183a7`
- `USER32!IsWindow` at `0x180018385`
- `USER32!IsWindow` at `0x180018385`

## pseudocode

```c
__int64 __fastcall CMFCDynamicLayout::AddItem(CMFCDynamicLayout *a1, HWND a2, HWND a3, HWND a4)
{
  __int64 v8; // rax
  HWND v9; // rcx
  __int64 **i; // rcx
  HWND *v11; // rax
  wchar_t *v12; // rcx
  HWND *v13; // rsi

  if ( !a2 || !IsWindow(a2) )
    return 0;
  v8 = *((_QWORD *)a1 + 1);
  v9 = v8 ? *(HWND *)(v8 + 64) : 0LL;
  if ( !IsChild(v9, a2) )
    return 0;
  for ( i = (__int64 **)*((_QWORD *)a1 + 3); i; i = (__int64 **)*i )
  {
    if ( (HWND)*i[2] == a2 )
      return 0;
  }
  v11 = (HWND *)operator new(0x38u);
  v13 = v11;
  if ( v11 )
  {
    *v11 = a2;
    v11[1] = 0;
    v11[2] = 0;
    v11[3] = 0;
    v11[4] = 0;
    v11[5] = a3;
    v11[6] = a4;
  }
  else
  {
    v13 = 0;
  }
  CMFCDynamicLayout::CorrectItem(v12, v13);
  if ( (unsigned int)CMFCDynamicLayout::PrepareItem(a1, (struct AFX_DYNAMIC_LAYOUT_ITEM *)v13) )
    CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::AddTail((__int64)a1 + 24, (__int64)v13);
  return 1;
}

```

## disassembly

```asm
0x180018360  push    rbx
0x180018362  push    rbp
0x180018363  push    rsi
0x180018364  push    rdi
0x180018365  push    r14
0x180018367  push    r15
0x180018369  sub     rsp, 28h
0x18001836d  mov     rbx, r9
0x180018370  mov     rdi, r8
0x180018373  mov     rbp, rdx
0x180018376  mov     r15, rcx
0x180018379  test    rdx, rdx
0x18001837c  jz      loc_18001843D
0x180018382  mov     rcx, rdx; hWnd
0x180018385  call    cs:__imp_IsWindow
0x18001838b  test    eax, eax
0x18001838d  jz      loc_18001843D
0x180018393  mov     rax, [r15+8]
0x180018397  test    rax, rax
0x18001839a  jnz     short loc_1800183A0
0x18001839c  xor     ecx, ecx
0x18001839e  jmp     short loc_1800183A4
0x1800183a0  mov     rcx, [rax+40h]; hWndParent
0x1800183a4  mov     rdx, rbp; hWnd
0x1800183a7  call    cs:__imp_IsChild
0x1800183ad  test    eax, eax
0x1800183af  jz      loc_18001843D
0x1800183b5  mov     rcx, [r15+18h]
0x1800183b9  jmp     short loc_1800183C7
0x1800183bb  mov     rax, [rcx+10h]
0x1800183bf  cmp     [rax], rbp
0x1800183c2  jz      short loc_18001843D
0x1800183c4  mov     rcx, [rcx]
0x1800183c7  test    rcx, rcx
0x1800183ca  jnz     short loc_1800183BB
0x1800183cc  mov     ecx, 38h ; '8'
0x1800183d1  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800183d7  mov     [rsp+58h+arg_8], rax
0x1800183dc  mov     rsi, rax
0x1800183df  test    rax, rax
0x1800183e2  jz      short loc_180018411
0x1800183e4  mov     [rax], rbp
0x1800183e7  mov     qword ptr [rax+8], 0
0x1800183ef  mov     qword ptr [rax+10h], 0
0x1800183f7  mov     qword ptr [rax+18h], 0
0x1800183ff  mov     qword ptr [rax+20h], 0
0x180018407  mov     [rax+28h], rdi
0x18001840b  mov     [rax+30h], rbx
0x18001840f  jmp     short loc_180018413
0x180018411  xor     esi, esi
0x180018413  mov     rdx, rsi; struct AFX_DYNAMIC_LAYOUT_ITEM *
0x180018416  call    ?CorrectItem@CMFCDynamicLayout@@IEBAXAEAUAFX_DYNAMIC_LAYOUT_ITEM@@@Z; CMFCDynamicLayout::CorrectItem(AFX_DYNAMIC_LAYOUT_ITEM &)
0x18001841b  mov     rdx, rsi; struct AFX_DYNAMIC_LAYOUT_ITEM *
0x18001841e  mov     rcx, r15; this
0x180018421  call    ?PrepareItem@CMFCDynamicLayout@@IEBAHAEAUAFX_DYNAMIC_LAYOUT_ITEM@@@Z; CMFCDynamicLayout::PrepareItem(AFX_DYNAMIC_LAYOUT_ITEM &)
0x180018426  test    eax, eax
0x180018428  jz      short loc_180018436
0x18001842a  mov     rdx, rsi
0x18001842d  lea     rcx, [r15+18h]
0x180018431  call    ?AddTail@?$CList@PEAUAFX_DYNAMIC_LAYOUT_ITEM@@PEAU1@@@QEAAPEAU__POSITION@@PEAUAFX_DYNAMIC_LAYOUT_ITEM@@@Z; CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::AddTail(AFX_DYNAMIC_LAYOUT_ITEM *)
0x180018436  mov     eax, 1
0x18001843b  jmp     short loc_18001843F
0x18001843d  xor     eax, eax
0x18001843f  add     rsp, 28h
0x180018443  pop     r15
0x180018445  pop     r14
0x180018447  pop     rdi
0x180018448  pop     rsi
0x180018449  pop     rbp
0x18001844a  pop     rbx
0x18001844b  retn
```
