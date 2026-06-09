# CW32System::GetTextMetrics(HDC__ *,tagLOGFONTW &,tagTEXTMETRICW &)

- ea: `0x180090b14`
- end: `0x180090bed`
- name: `?GetTextMetrics@CW32System@@SAHPEAUHDC__@@AEAUtagLOGFONTW@@AEAUtagTEXTMETRICW@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(HDC hdc, struct tagLOGFONTW *, struct tagTEXTMETRICW *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180078800`

## callees

- `0x180090024`
- `0x180090a6c`
- `0x180090b14`
- `0x180090bf4`
- `0x180093aa4`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `GDI32!DeleteObject` at `0x180090bc3`
- `GDI32!DeleteObject` at `0x180090bc3`
- `GDI32!SelectObject` at `0x180090b54`
- `GDI32!SelectObject` at `0x180090bb4`
- `GDI32!SelectObject` at `0x180090b54`
- `GDI32!SelectObject` at `0x180090bb4`

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
0x180090b14  push    rbx
0x180090b16  push    rbp
0x180090b17  push    rsi
0x180090b18  push    rdi
0x180090b19  push    r14
0x180090b1b  sub     rsp, 80h
0x180090b22  mov     rax, cs:__security_cookie
0x180090b29  xor     rax, rsp
0x180090b2c  mov     [rsp+0A8h+var_38], rax
0x180090b31  mov     rdi, rcx
0x180090b34  mov     rbp, r8
0x180090b37  mov     rcx, rdx; struct tagLOGFONTW *
0x180090b3a  mov     rbx, rdx
0x180090b3d  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180090b42  mov     rsi, rax
0x180090b45  test    rax, rax
0x180090b48  jz      loc_180090BD1
0x180090b4e  mov     rdx, rsi; h
0x180090b51  mov     rcx, rdi; hdc
0x180090b54  call    cs:__imp_SelectObject
0x180090b5b  nop     dword ptr [rax+rax+00h]
0x180090b60  xor     edx, edx; Val
0x180090b62  lea     rcx, [rsp+0A8h+var_88]; void *
0x180090b67  mov     r14, rax
0x180090b6a  lea     r8d, [rdx+42h]; Size
0x180090b6e  call    memset_0
0x180090b73  lea     r8, [rsp+0A8h+var_88]; unsigned __int16 *
0x180090b78  mov     rcx, rdi; hdc
0x180090b7b  call    ?GetTextFace@CW32System@@SAHPEAUHDC__@@HPEAG@Z; CW32System::GetTextFace(HDC__ *,int,ushort *)
0x180090b80  test    eax, eax
0x180090b82  jz      short loc_180090BAC
0x180090b84  lea     rcx, [rbx+1Ch]; unsigned __int16 *
0x180090b88  lea     rdx, [rsp+0A8h+var_88]; unsigned __int16 *
0x180090b8d  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180090b92  test    eax, eax
0x180090b94  jnz     short loc_180090BAC
0x180090b96  mov     rdx, rbp; struct tagTEXTMETRICW *
0x180090b99  mov     rcx, rdi; HDC
0x180090b9c  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x180090ba1  test    eax, eax
0x180090ba3  jz      short loc_180090BAC
0x180090ba5  mov     ebx, 1
0x180090baa  jmp     short loc_180090BAE
0x180090bac  xor     ebx, ebx
0x180090bae  mov     rdx, r14; h
0x180090bb1  mov     rcx, rdi; hdc
0x180090bb4  call    cs:__imp_SelectObject
0x180090bbb  nop     dword ptr [rax+rax+00h]
0x180090bc0  mov     rcx, rsi; ho
0x180090bc3  call    cs:__imp_DeleteObject
0x180090bca  nop     dword ptr [rax+rax+00h]
0x180090bcf  mov     eax, ebx
0x180090bd1  mov     rcx, [rsp+0A8h+var_38]
0x180090bd6  xor     rcx, rsp; StackCookie
0x180090bd9  call    __security_check_cookie
0x180090bde  add     rsp, 80h
0x180090be5  pop     r14
0x180090be7  pop     rdi
0x180090be8  pop     rsi
0x180090be9  pop     rbp
0x180090bea  pop     rbx
0x180090beb  retn
```
