# GetEscapementVector(HDC__ *,int,tagPOINT &)

- ea: `0x180021b90`
- end: `0x180021e49`
- name: `?GetEscapementVector@@YAJPEAUHDC__@@HAEAUtagPOINT@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(HDC hdc, int, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009d9e4`

## callees

- `0x180006a28`
- `0x1800200a0`
- `0x1800209d0`
- `0x180021b90`
- `0x180021e50`
- `0x180022b20`
- `0x18002ade0`
- `0x180032f20`
- `0x18007f800`

## import_xrefs

- `GDI32!DeleteDC` at `0x180021e0e`
- `GDI32!DeleteDC` at `0x180021e0e`
- `GDI32!ExtTextOutW` at `0x180021c75`
- `GDI32!ExtTextOutW` at `0x180021def`
- `GDI32!ExtTextOutW` at `0x180021c75`
- `GDI32!ExtTextOutW` at `0x180021def`
- `GDI32!MoveToEx` at `0x180021c2a`
- `GDI32!MoveToEx` at `0x180021ca0`
- `GDI32!MoveToEx` at `0x180021db4`
- `GDI32!MoveToEx` at `0x180021c2a`
- `GDI32!MoveToEx` at `0x180021ca0`
- `GDI32!MoveToEx` at `0x180021db4`
- `GDI32!SelectObject` at `0x180021d59`
- `GDI32!SelectObject` at `0x180021d59`
- `GDI32!SetBkMode` at `0x180021c13`
- `GDI32!SetBkMode` at `0x180021cd7`
- `GDI32!SetBkMode` at `0x180021d9d`
- `GDI32!SetBkMode` at `0x180021c13`
- `GDI32!SetBkMode` at `0x180021cd7`
- `GDI32!SetBkMode` at `0x180021d9d`
- `GDI32!SetTextAlign` at `0x180021bff`
- `GDI32!SetTextAlign` at `0x180021cb1`
- `GDI32!SetTextAlign` at `0x180021d89`
- `GDI32!SetTextAlign` at `0x180021bff`
- `GDI32!SetTextAlign` at `0x180021cb1`
- `GDI32!SetTextAlign` at `0x180021d89`

## pseudocode

```c
__int64 __fastcall GetEscapementVector(HDC hdc, __int64 a2, struct tagPOINT *a3)
{
  UINT TextAlign; // ebp
  int BkMode; // edi
  void *DCObject; // r15
  HDC CompatibleDC; // rax
  HDC v10; // r14
  UINT v11; // eax
  INT lpDx; // [rsp+40h] [rbp-58h] BYREF
  struct tagPOINT pt; // [rsp+48h] [rbp-50h] BYREF
  RECT rect; // [rsp+50h] [rbp-48h] BYREF

  lpDx = 1000;
  if ( !hdc )
    return 2147942487LL;
  pt = 0;
  TextAlign = GetTextAlign(hdc);
  GetCurrentPositionEx(hdc, &pt);
  BkMode = GetBkMode(hdc);
  SetTextAlign(hdc, TextAlign & 0xFFFFFFF8 | 1);
  SetBkMode(hdc, 1);
  MoveToEx(hdc, 0, 0, 0);
  rect = 0;
  ExtTextOutW(hdc, 0, 0, 0x1004u, &rect, L" ", 1u, &lpDx);
  GetCurrentPositionEx(hdc, a3);
  if ( !*(_QWORD *)a3 )
  {
    a3->x = lpDx;
    DCObject = (void *)GetDCObject(hdc, 655360);
    if ( DCObject )
    {
      CompatibleDC = CreateCompatibleDC(hdc);
      v10 = CompatibleDC;
      if ( CompatibleDC )
      {
        SelectObject(CompatibleDC, DCObject);
        if ( GetGraphicsMode(hdc) == 2 )
          SetGraphicsMode(v10, 2);
        v11 = GetTextAlign(v10);
        SetTextAlign(v10, v11 & 0xFFFFFFF8 | 1);
        SetBkMode(v10, 1);
        MoveToEx(v10, 0, 0, 0);
        ExtTextOutW(v10, 0, 0, 0x1000u, &rect, L" ", 1u, &lpDx);
        GetCurrentPositionEx(v10, a3);
        if ( !a3->x && !a3->y )
          a3->x = lpDx;
        DeleteDC(v10);
      }
    }
  }
  MoveToEx(hdc, pt.x, pt.y, 0);
  SetTextAlign(hdc, TextAlign);
  if ( BkMode != 1 )
    SetBkMode(hdc, BkMode);
  return 0;
}

```

## disassembly

```asm
0x180021b90  mov     r11, rsp
0x180021b93  push    rbx
0x180021b94  push    rsi
0x180021b95  sub     rsp, 88h
0x180021b9c  mov     rax, cs:__security_cookie
0x180021ba3  xor     rax, rsp
0x180021ba6  mov     [rsp+98h+var_38], rax
0x180021bab  mov     [rsp+98h+var_58], 3E8h
0x180021bb3  mov     rsi, r8
0x180021bb6  mov     rbx, rcx
0x180021bb9  test    rcx, rcx
0x180021bbc  jz      loc_180021D05
0x180021bc2  mov     [r11+10h], rbp
0x180021bc6  mov     [r11+20h], rdi
0x180021bca  mov     [r11-18h], r12
0x180021bce  mov     qword ptr [r11-50h], 0
0x180021bd6  call    GetTextAlign
0x180021bdb  lea     rdx, [rsp+98h+pt]; lppt
0x180021be0  mov     rcx, rbx; hdc
0x180021be3  mov     ebp, eax
0x180021be5  call    GetCurrentPositionEx
0x180021bea  mov     rcx, rbx; hdc
0x180021bed  call    GetBkMode
0x180021bf2  mov     edx, ebp
0x180021bf4  mov     rcx, rbx; hdc
0x180021bf7  and     edx, 0FFFFFFF9h
0x180021bfa  mov     edi, eax
0x180021bfc  or      edx, 1; align
0x180021bff  call    cs:__imp_SetTextAlign
0x180021c06  nop     dword ptr [rax+rax+00h]
0x180021c0b  mov     edx, 1; mode
0x180021c10  mov     rcx, rbx; hdc
0x180021c13  call    cs:__imp_SetBkMode
0x180021c1a  nop     dword ptr [rax+rax+00h]
0x180021c1f  xor     r9d, r9d; lppt
0x180021c22  xor     r8d, r8d; y
0x180021c25  xor     edx, edx; x
0x180021c27  mov     rcx, rbx; hdc
0x180021c2a  call    cs:__imp_MoveToEx
0x180021c31  nop     dword ptr [rax+rax+00h]
0x180021c36  lea     rax, [rsp+98h+var_58]
0x180021c3b  xorps   xmm0, xmm0
0x180021c3e  mov     [rsp+98h+lpDx], rax; lpDx
0x180021c43  lea     r12, String; " "
0x180021c4a  mov     [rsp+98h+c], 1; c
0x180021c52  lea     rax, [rsp+98h+rect]
0x180021c57  mov     [rsp+98h+lpString], r12; lpString
0x180021c5c  mov     r9d, 1004h; options
0x180021c62  xor     r8d, r8d; y
0x180021c65  mov     [rsp+98h+lprect], rax; lprect
0x180021c6a  xor     edx, edx; x
0x180021c6c  mov     rcx, rbx; hdc
0x180021c6f  movdqu  xmmword ptr [rsp+98h+rect.left], xmm0
0x180021c75  call    cs:__imp_ExtTextOutW
0x180021c7c  nop     dword ptr [rax+rax+00h]
0x180021c81  mov     rdx, rsi; lppt
0x180021c84  mov     rcx, rbx; hdc
0x180021c87  call    GetCurrentPositionEx
0x180021c8c  cmp     dword ptr [rsi], 0
0x180021c8f  jz      short loc_180021D0C
0x180021c91  mov     r8d, [rsp+98h+pt.y]; y
0x180021c96  xor     r9d, r9d; lppt
0x180021c99  mov     edx, [rsp+98h+pt.x]; x
0x180021c9d  mov     rcx, rbx; hdc
0x180021ca0  call    cs:__imp_MoveToEx
0x180021ca7  nop     dword ptr [rax+rax+00h]
0x180021cac  mov     edx, ebp; align
0x180021cae  mov     rcx, rbx; hdc
0x180021cb1  call    cs:__imp_SetTextAlign
0x180021cb8  nop     dword ptr [rax+rax+00h]
0x180021cbd  mov     r12, [rsp+98h+var_18]
0x180021cc5  mov     rbp, [rsp+98h+arg_8]
0x180021ccd  cmp     edi, 1
0x180021cd0  jz      short loc_180021CE3
0x180021cd2  mov     edx, edi; mode
0x180021cd4  mov     rcx, rbx; hdc
0x180021cd7  call    cs:__imp_SetBkMode
0x180021cde  nop     dword ptr [rax+rax+00h]
0x180021ce3  mov     rdi, [rsp+98h+arg_18]
0x180021ceb  xor     eax, eax
0x180021ced  mov     rcx, [rsp+98h+var_38]
0x180021cf2  xor     rcx, rsp; StackCookie
0x180021cf5  call    __security_check_cookie
0x180021cfa  add     rsp, 88h
0x180021d01  pop     rsi
0x180021d02  pop     rbx
0x180021d03  retn
0x180021d05  mov     eax, 80070057h
0x180021d0a  jmp     short loc_180021CED
0x180021d0c  cmp     dword ptr [rsi+4], 0
0x180021d10  jnz     loc_180021C91
0x180021d16  mov     eax, [rsp+98h+var_58]
0x180021d1a  mov     edx, 0A0000h
0x180021d1f  mov     rcx, rbx
0x180021d22  mov     [rsi], eax
0x180021d24  mov     [rsp+98h+var_28], r15
0x180021d29  call    GetDCObject
0x180021d2e  mov     r15, rax
0x180021d31  test    rax, rax
0x180021d34  jz      loc_180021E1F
0x180021d3a  mov     rcx, rbx; hdc
0x180021d3d  mov     [rsp+98h+var_20], r14
0x180021d42  call    CreateCompatibleDC
0x180021d47  mov     r14, rax
0x180021d4a  test    rax, rax
0x180021d4d  jz      loc_180021E1A
0x180021d53  mov     rdx, r15; h
0x180021d56  mov     rcx, rax; hdc
0x180021d59  call    cs:__imp_SelectObject
0x180021d60  nop     dword ptr [rax+rax+00h]
0x180021d65  mov     rcx, rbx; hdc
0x180021d68  call    GetGraphicsMode
0x180021d6d  cmp     eax, 2
0x180021d70  jz      loc_180021E29
0x180021d76  mov     rcx, r14; hdc
0x180021d79  call    GetTextAlign
0x180021d7e  and     eax, 0FFFFFFF9h
0x180021d81  mov     rcx, r14; hdc
0x180021d84  or      eax, 1
0x180021d87  mov     edx, eax; align
0x180021d89  call    cs:__imp_SetTextAlign
0x180021d90  nop     dword ptr [rax+rax+00h]
0x180021d95  mov     edx, 1; mode
0x180021d9a  mov     rcx, r14; hdc
0x180021d9d  call    cs:__imp_SetBkMode
0x180021da4  nop     dword ptr [rax+rax+00h]
0x180021da9  xor     r9d, r9d; lppt
0x180021dac  xor     r8d, r8d; y
0x180021daf  xor     edx, edx; x
0x180021db1  mov     rcx, r14; hdc
0x180021db4  call    cs:__imp_MoveToEx
0x180021dbb  nop     dword ptr [rax+rax+00h]
0x180021dc0  lea     rax, [rsp+98h+var_58]
0x180021dc5  mov     r9d, 1000h; options
0x180021dcb  mov     [rsp+98h+lpDx], rax; lpDx
0x180021dd0  xor     r8d, r8d; y
0x180021dd3  mov     [rsp+98h+c], 1; c
0x180021ddb  lea     rax, [rsp+98h+rect]
0x180021de0  mov     [rsp+98h+lpString], r12; lpString
0x180021de5  xor     edx, edx; x
0x180021de7  mov     rcx, r14; hdc
0x180021dea  mov     [rsp+98h+lprect], rax; lprect
0x180021def  call    cs:__imp_ExtTextOutW
0x180021df6  nop     dword ptr [rax+rax+00h]
0x180021dfb  mov     rdx, rsi; lppt
0x180021dfe  mov     rcx, r14; hdc
0x180021e01  call    GetCurrentPositionEx
0x180021e06  cmp     dword ptr [rsi], 0
0x180021e09  jz      short loc_180021E3B
0x180021e0b  mov     rcx, r14; hdc
0x180021e0e  call    cs:__imp_DeleteDC
0x180021e15  nop     dword ptr [rax+rax+00h]
0x180021e1a  mov     r14, [rsp+98h+var_20]
0x180021e1f  mov     r15, [rsp+98h+var_28]
0x180021e24  jmp     loc_180021C91
0x180021e29  mov     edx, 2; iMode
0x180021e2e  mov     rcx, r14; hdc
0x180021e31  call    SetGraphicsMode
0x180021e36  jmp     loc_180021D76
0x180021e3b  cmp     dword ptr [rsi+4], 0
0x180021e3f  jnz     short loc_180021E0B
0x180021e41  mov     eax, [rsp+98h+var_58]
0x180021e45  mov     [rsi], eax
0x180021e47  jmp     short loc_180021E0B
```
