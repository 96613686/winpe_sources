# CComponentData::SetServerFocus(ushort const *)

- ea: `0x180006fc0`
- end: `0x18000700e`
- name: `?SetServerFocus@CComponentData@@QEAAXPEBG@Z`
- size: `78`
- prototype: `void __fastcall(CComponentData *__hidden this, STRSAFE_PCNZWCH pszSrc)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008890`
- `0x180008958`
- `0x180021820`
- `0x180021ff0`

## callees

- `0x180006fc0`
- `0x1800070ec`
- `0x180008b70`

## pseudocode

```c
void __fastcall CComponentData::SetServerFocus(wchar_t *this, STRSAFE_PCNZWCH pszSrc, size_t *a3)
{
  if ( !pszSrc )
    goto LABEL_4;
  while ( *pszSrc == 92 )
  {
    if ( !++pszSrc )
      goto LABEL_4;
  }
  if ( *pszSrc )
    StringCopyWorkerW(this + 44, 0x106u, a3, pszSrc, 0x105u);
  else
LABEL_4:
    this[44] = 0;
  CComponentData::_UpdateCurFocusSystemRoot((CComponentData *)this);
}

```

## disassembly

```asm
0x180006fc0  push    rbx
0x180006fc2  sub     rsp, 30h
0x180006fc6  xor     eax, eax
0x180006fc8  mov     rbx, rcx
0x180006fcb  test    rdx, rdx
0x180006fce  jz      short loc_180006FDC
0x180006fd0  cmp     word ptr [rdx], 5Ch ; '\'
0x180006fd4  jnz     short loc_180006FED
0x180006fd6  add     rdx, 2
0x180006fda  jnz     short loc_180006FD0
0x180006fdc  mov     [rcx+58h], ax
0x180006fe0  mov     rcx, rbx; this
0x180006fe3  add     rsp, 30h
0x180006fe7  pop     rbx
0x180006fe8  jmp     ?_UpdateCurFocusSystemRoot@CComponentData@@AEAAXXZ; CComponentData::_UpdateCurFocusSystemRoot(void)
0x180006fed  cmp     [rdx], ax
0x180006ff0  jz      short loc_180006FDC
0x180006ff2  mov     r9, rdx; pszSrc
0x180006ff5  mov     [rsp+38h+cchToCopy], 105h; cchToCopy
0x180006ffe  mov     edx, 106h; cchDest
0x180007003  add     rcx, 58h ; 'X'; pszDest
0x180007007  call    StringCopyWorkerW
0x18000700c  jmp     short loc_180006FE0
```
