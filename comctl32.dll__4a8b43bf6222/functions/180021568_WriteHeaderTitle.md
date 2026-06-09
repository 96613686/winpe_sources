# _WriteHeaderTitle

- ea: `0x180021568`
- end: `0x1800216bd`
- name: `_WriteHeaderTitle`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c47c`
- `0x18001ef50`

## callees

- `0x1800115f0`
- `0x180021568`

## import_xrefs

- `GDI32!SelectObject` at `0x180021603`
- `GDI32!SelectObject` at `0x180021695`
- `GDI32!SelectObject` at `0x180021603`
- `GDI32!SelectObject` at `0x180021695`
- `GDI32!ExtTextOutW` at `0x180021639`
- `GDI32!ExtTextOutW` at `0x180021639`
- `KERNEL32!lstrlenW` at `0x1800215cb`
- `KERNEL32!lstrlenW` at `0x1800215cb`
- `USER32!SendMessageW` at `0x1800215f7`
- `USER32!SendMessageW` at `0x1800215f7`
- `USER32!CopyRect` at `0x180021651`
- `USER32!CopyRect` at `0x180021651`
- `USER32!LoadStringW` at `0x1800215bd`
- `USER32!LoadStringW` at `0x1800215bd`
- `USER32!DrawTextW` at `0x180021682`
- `USER32!DrawTextW` at `0x180021682`

## pseudocode

```c
__int64 __fastcall WriteHeaderTitle(__int64 a1, HDC a2, const RECT *a3, unsigned __int64 a4, int a5, UINT format)
{
  WCHAR *lpString; // rbx
  int c; // r15d
  void *v11; // rax
  HGDIOBJ v12; // rbp
  unsigned int v13; // edi
  struct tagRECT rcDst; // [rsp+40h] [rbp-878h] BYREF
  WCHAR Buffer[1040]; // [rsp+50h] [rbp-868h] BYREF

  lpString = (WCHAR *)a4;
  if ( a4 < 0x10000 )
  {
    LoadStringW(
      *(HINSTANCE *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL * *(int *)(a1 + 120)) + 72LL),
      (unsigned __int16)a4,
      Buffer,
      1040);
    lpString = Buffer;
  }
  c = lstrlenW(lpString);
  if ( !a5 || (v11 = *(void **)(a1 + 192)) == 0 )
    v11 = (void *)SendMessageW(*(HWND *)a1, 0x31u, 0, 0);
  v12 = SelectObject(a2, v11);
  if ( a5 )
  {
    v13 = 0;
    ExtTextOutW(a2, 22, 10, 0, a3, lpString, c, 0);
  }
  else
  {
    rcDst = 0;
    CopyRect(&rcDst, a3);
    rcDst.top = *(_DWORD *)(a1 + 216);
    rcDst.left = 44;
    v13 = DrawTextW(a2, lpString, c, &rcDst, format);
  }
  if ( v12 )
    SelectObject(a2, v12);
  return v13;
}

```

## disassembly

```asm
0x180021568  push    rbx
0x18002156a  push    rbp
0x18002156b  push    rsi
0x18002156c  push    rdi
0x18002156d  push    r12
0x18002156f  push    r15
0x180021571  sub     rsp, 888h
0x180021578  mov     rax, cs:__security_cookie
0x18002157f  xor     rax, rsp
0x180021582  mov     [rsp+8B8h+var_48], rax
0x18002158a  mov     rbx, r9
0x18002158d  mov     r12, r8
0x180021590  mov     rsi, rdx
0x180021593  mov     rdi, rcx
0x180021596  cmp     r9, 10000h
0x18002159d  jnb     short loc_1800215C8
0x18002159f  movsxd  r8, dword ptr [rcx+78h]
0x1800215a3  mov     r9d, 410h; cchBufferMax
0x1800215a9  mov     rax, [rcx+40h]
0x1800215ad  movzx   edx, bx; uID
0x1800215b0  mov     rcx, [rax+r8*8]
0x1800215b4  lea     r8, [rsp+8B8h+Buffer]; lpBuffer
0x1800215b9  mov     rcx, [rcx+48h]; hInstance
0x1800215bd  call    cs:__imp_LoadStringW
0x1800215c3  lea     rbx, [rsp+8B8h+Buffer]
0x1800215c8  mov     rcx, rbx; lpString
0x1800215cb  call    cs:__imp_lstrlenW
0x1800215d1  cmp     [rsp+8B8h+arg_20], 0
0x1800215d9  mov     r15d, eax
0x1800215dc  jz      short loc_1800215EA
0x1800215de  mov     rax, [rdi+0C0h]
0x1800215e5  test    rax, rax
0x1800215e8  jnz     short loc_1800215FD
0x1800215ea  mov     rcx, [rdi]; hWnd
0x1800215ed  xor     r9d, r9d; lParam
0x1800215f0  xor     r8d, r8d; wParam
0x1800215f3  lea     edx, [r9+31h]; Msg
0x1800215f7  call    cs:__imp_SendMessageW
0x1800215fd  mov     rdx, rax; h
0x180021600  mov     rcx, rsi; hdc
0x180021603  call    cs:__imp_SelectObject
0x180021609  cmp     [rsp+8B8h+arg_20], 0
0x180021611  mov     rbp, rax
0x180021614  jz      short loc_180021641
0x180021616  xor     edi, edi
0x180021618  xor     r9d, r9d; options
0x18002161b  mov     [rsp+8B8h+lpDx], rdi; lpDx
0x180021620  mov     rcx, rsi; hdc
0x180021623  mov     [rsp+8B8h+c], r15d; c
0x180021628  mov     [rsp+8B8h+lpString], rbx; lpString
0x18002162d  lea     edx, [rdi+16h]; x
0x180021630  mov     [rsp+8B8h+lprect], r12; lprect
0x180021635  lea     r8d, [rdi+0Ah]; y
0x180021639  call    cs:__imp_ExtTextOutW
0x18002163f  jmp     short loc_18002168A
0x180021641  xorps   xmm0, xmm0
0x180021644  lea     rcx, [rsp+8B8h+rcDst]; lprcDst
0x180021649  mov     rdx, r12; lprcSrc
0x18002164c  movups  xmmword ptr [rsp+8B8h+rcDst.left], xmm0
0x180021651  call    cs:__imp_CopyRect
0x180021657  mov     eax, [rdi+0D8h]
0x18002165d  lea     r9, [rsp+8B8h+rcDst]; lprc
0x180021662  mov     [rsp+8B8h+rcDst.top], eax
0x180021666  mov     r8d, r15d; cchText
0x180021669  mov     eax, [rsp+8B8h+format]
0x180021670  mov     rdx, rbx; lpchText
0x180021673  mov     rcx, rsi; hdc
0x180021676  mov     dword ptr [rsp+8B8h+lprect], eax; format
0x18002167a  mov     [rsp+8B8h+rcDst.left], 2Ch ; ','
0x180021682  call    cs:__imp_DrawTextW
0x180021688  mov     edi, eax
0x18002168a  test    rbp, rbp
0x18002168d  jz      short loc_18002169B
0x18002168f  mov     rdx, rbp; h
0x180021692  mov     rcx, rsi; hdc
0x180021695  call    cs:__imp_SelectObject
0x18002169b  mov     eax, edi
0x18002169d  mov     rcx, [rsp+8B8h+var_48]
0x1800216a5  xor     rcx, rsp; StackCookie
0x1800216a8  call    __security_check_cookie
0x1800216ad  add     rsp, 888h
0x1800216b4  pop     r15
0x1800216b6  pop     r12
0x1800216b8  pop     rdi
0x1800216b9  pop     rsi
0x1800216ba  pop     rbp
0x1800216bb  pop     rbx
0x1800216bc  retn
```
