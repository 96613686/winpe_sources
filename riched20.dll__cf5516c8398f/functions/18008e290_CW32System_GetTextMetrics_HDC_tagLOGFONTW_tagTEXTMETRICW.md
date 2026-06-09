# CW32System::GetTextMetrics(HDC__ *,tagLOGFONTW &,tagTEXTMETRICW &)

- ea: `0x18008e290`
- end: `0x18008e352`
- name: `?GetTextMetrics@CW32System@@SAHPEAUHDC__@@AEAUtagLOGFONTW@@AEAUtagTEXTMETRICW@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(HDC hdc, struct tagLOGFONTW *, struct tagTEXTMETRICW *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800766a4`

## callees

- `0x18008d830`
- `0x18008e1f8`
- `0x18008e290`
- `0x18008e358`
- `0x180090ff0`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `GDI32!DeleteObject` at `0x18008e32f`
- `GDI32!DeleteObject` at `0x18008e32f`
- `GDI32!SelectObject` at `0x18008e2cc`
- `GDI32!SelectObject` at `0x18008e326`
- `GDI32!SelectObject` at `0x18008e2cc`
- `GDI32!SelectObject` at `0x18008e326`

## pseudocode

```c
HFONT __fastcall CW32System::GetTextMetrics(HDC hdc, struct tagLOGFONTW *a2, struct tagTEXTMETRICW *a3)
{
  HFONT result; // rax
  HFONT v7; // rsi
  HGDIOBJ v8; // r14
  int v9; // edx
  BOOL v10; // ebx
  unsigned __int16 v11[40]; // [rsp+20h] [rbp-88h] BYREF

  result = CW32System::CreateFontIndirect(a2);
  v7 = result;
  if ( result )
  {
    v8 = SelectObject(hdc, result);
    memset_0(v11, 0, 0x42u);
    v10 = (unsigned int)CW32System::GetTextFace(hdc, v9, v11)
       && !(unsigned int)CW32System::wcsicmp(a2->lfFaceName, v11)
       && (unsigned int)CW32System::GetTextMetrics(hdc, a3);
    SelectObject(hdc, v8);
    DeleteObject(v7);
    return (HFONT)v10;
  }
  return result;
}

```

## disassembly

```asm
0x18008e290  push    rbx
0x18008e292  push    rbp
0x18008e293  push    rsi
0x18008e294  push    rdi
0x18008e295  push    r14
0x18008e297  sub     rsp, 80h
0x18008e29e  mov     rax, cs:__security_cookie
0x18008e2a5  xor     rax, rsp
0x18008e2a8  mov     [rsp+0A8h+var_38], rax
0x18008e2ad  mov     rdi, rcx
0x18008e2b0  mov     rbp, r8
0x18008e2b3  mov     rcx, rdx; struct tagLOGFONTW *
0x18008e2b6  mov     rbx, rdx
0x18008e2b9  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18008e2be  mov     rsi, rax
0x18008e2c1  test    rax, rax
0x18008e2c4  jz      short loc_18008E337
0x18008e2c6  mov     rdx, rsi; h
0x18008e2c9  mov     rcx, rdi; hdc
0x18008e2cc  call    cs:__imp_SelectObject
0x18008e2d2  xor     edx, edx; Val
0x18008e2d4  lea     rcx, [rsp+0A8h+var_88]; void *
0x18008e2d9  mov     r14, rax
0x18008e2dc  lea     r8d, [rdx+42h]; Size
0x18008e2e0  call    memset_0
0x18008e2e5  lea     r8, [rsp+0A8h+var_88]; unsigned __int16 *
0x18008e2ea  mov     rcx, rdi; hdc
0x18008e2ed  call    ?GetTextFace@CW32System@@SAHPEAUHDC__@@HPEAG@Z; CW32System::GetTextFace(HDC__ *,int,ushort *)
0x18008e2f2  test    eax, eax
0x18008e2f4  jz      short loc_18008E31E
0x18008e2f6  lea     rcx, [rbx+1Ch]; unsigned __int16 *
0x18008e2fa  lea     rdx, [rsp+0A8h+var_88]; unsigned __int16 *
0x18008e2ff  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x18008e304  test    eax, eax
0x18008e306  jnz     short loc_18008E31E
0x18008e308  mov     rdx, rbp; struct tagTEXTMETRICW *
0x18008e30b  mov     rcx, rdi; HDC
0x18008e30e  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x18008e313  test    eax, eax
0x18008e315  jz      short loc_18008E31E
0x18008e317  mov     ebx, 1
0x18008e31c  jmp     short loc_18008E320
0x18008e31e  xor     ebx, ebx
0x18008e320  mov     rdx, r14; h
0x18008e323  mov     rcx, rdi; hdc
0x18008e326  call    cs:__imp_SelectObject
0x18008e32c  mov     rcx, rsi; ho
0x18008e32f  call    cs:__imp_DeleteObject
0x18008e335  mov     eax, ebx
0x18008e337  mov     rcx, [rsp+0A8h+var_38]
0x18008e33c  xor     rcx, rsp; StackCookie
0x18008e33f  call    __security_check_cookie
0x18008e344  add     rsp, 80h
0x18008e34b  pop     r14
0x18008e34d  pop     rdi
0x18008e34e  pop     rsi
0x18008e34f  pop     rbp
0x18008e350  pop     rbx
0x18008e351  retn
```
