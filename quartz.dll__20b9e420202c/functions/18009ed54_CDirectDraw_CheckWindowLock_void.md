# CDirectDraw::CheckWindowLock(void)

- ea: `0x18009ed54`
- end: `0x18009eec0`
- name: `?CheckWindowLock@CDirectDraw@@AEAAHXZ`
- size: `364`
- prototype: `__int64 __fastcall(CDirectDraw *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a21dc`

## callees

- `0x1800388a0`
- `0x18009ed54`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x18009eddd`
- `KERNEL32!CompareStringA` at `0x18009eddd`
- `GDI32!GetSystemPaletteEntries` at `0x18009ee2c`
- `GDI32!GetSystemPaletteEntries` at `0x18009ee2c`
- `GDI32!DeleteDC` at `0x18009ee51`
- `GDI32!DeleteDC` at `0x18009ee51`
- `GDI32!CreateDCA` at `0x18009ee0b`
- `GDI32!CreateDCA` at `0x18009ee0b`
- `GDI32!GetDeviceCaps` at `0x18009ee40`
- `GDI32!GetDeviceCaps` at `0x18009ee40`

## pseudocode

```c
__int64 __fastcall CDirectDraw::CheckWindowLock(CDirectDraw *this)
{
  __int64 v1; // rdi
  UINT v3; // ebp
  const CHAR *v4; // rdx
  const CHAR *v5; // rcx
  HDC DCA; // rax
  HDC v7; // rsi
  unsigned __int16 DeviceCaps; // bx
  unsigned __int16 i; // dx
  struct tagPALETTEENTRY pPalEntries[256]; // [rsp+30h] [rbp-428h] BYREF

  v1 = *((_QWORD *)this + 127);
  if ( *(_WORD *)(v1 + 62) <= 8u && !*(_DWORD *)(v1 + 64) && *(_DWORD *)(v1 + 80) <= 0x100u )
  {
    v3 = *(unsigned __int16 *)(v1 + 80);
    if ( *((_QWORD *)this + 115) == -4276
      || CompareStringA(0x7Fu, 1u, (PCNZCH)(*((_QWORD *)this + 115) + 4276LL), -1, "DISPLAY", -1) == 2 )
    {
      v4 = 0;
      v5 = "DISPLAY";
    }
    else
    {
      v4 = (const CHAR *)(*((_QWORD *)this + 115) + 4276LL);
      v5 = 0;
    }
    DCA = CreateDCA(v5, v4, 0, 0);
    v7 = DCA;
    if ( DCA )
    {
      GetSystemPaletteEntries(DCA, 0, v3, pPalEntries);
      DeviceCaps = GetDeviceCaps(v7, 104);
      DeleteDC(v7);
      if ( (unsigned __int16)v3 > DeviceCaps )
        return 1;
      for ( i = 0; i < (unsigned __int16)v3; ++i )
      {
        if ( pPalEntries[i].peRed != *(_BYTE *)(v1 + 4LL * i + 90)
          || pPalEntries[i].peGreen != *(_BYTE *)(v1 + 4LL * i + 89)
          || pPalEntries[i].peBlue != *(_BYTE *)(v1 + 4LL * i + 88) )
        {
          return 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18009ed54  mov     [rsp+arg_8], rbx
0x18009ed59  mov     [rsp+arg_10], rbp
0x18009ed5e  push    rsi
0x18009ed5f  push    rdi
0x18009ed60  push    r14
0x18009ed62  sub     rsp, 440h
0x18009ed69  mov     rax, cs:__security_cookie
0x18009ed70  xor     rax, rsp
0x18009ed73  mov     [rsp+458h+var_28], rax
0x18009ed7b  mov     rdi, [rcx+3F8h]
0x18009ed82  mov     rbx, rcx
0x18009ed85  cmp     word ptr [rdi+3Eh], 8
0x18009ed8a  ja      loc_18009EE95
0x18009ed90  cmp     dword ptr [rdi+40h], 0
0x18009ed94  jnz     loc_18009EE95
0x18009ed9a  cmp     dword ptr [rdi+50h], 100h
0x18009eda1  ja      loc_18009EE95
0x18009eda7  mov     r8, [rcx+398h]
0x18009edae  lea     rsi, pwszDriver; "DISPLAY"
0x18009edb5  movzx   ebp, word ptr [rdi+50h]
0x18009edb9  mov     r14d, 1
0x18009edbf  add     r8, 10B4h; lpString1
0x18009edc6  jz      short loc_18009EE00
0x18009edc8  or      r9d, 0FFFFFFFFh; cchCount1
0x18009edcc  lea     ecx, [r14+7Eh]; Locale
0x18009edd0  mov     [rsp+458h+cchCount2], r9d; cchCount2
0x18009edd5  mov     edx, r14d; dwCmpFlags
0x18009edd8  mov     [rsp+458h+lpString2], rsi; lpString2
0x18009eddd  call    cs:__imp_CompareStringA
0x18009ede4  nop     dword ptr [rax+rax+00h]
0x18009ede9  cmp     eax, 2
0x18009edec  jz      short loc_18009EE00
0x18009edee  mov     rdx, [rbx+398h]
0x18009edf5  add     rdx, 10B4h
0x18009edfc  xor     ecx, ecx
0x18009edfe  jmp     short loc_18009EE05
0x18009ee00  xor     edx, edx; pwszDevice
0x18009ee02  mov     rcx, rsi; pwszDriver
0x18009ee05  xor     r9d, r9d; pdm
0x18009ee08  xor     r8d, r8d; pszPort
0x18009ee0b  call    cs:__imp_CreateDCA
0x18009ee12  nop     dword ptr [rax+rax+00h]
0x18009ee17  mov     rsi, rax
0x18009ee1a  test    rax, rax
0x18009ee1d  jz      short loc_18009EE95
0x18009ee1f  mov     r8d, ebp; cEntries
0x18009ee22  lea     r9, [rsp+458h+pPalEntries]; pPalEntries
0x18009ee27  xor     edx, edx; iStart
0x18009ee29  mov     rcx, rax; hdc
0x18009ee2c  call    cs:__imp_GetSystemPaletteEntries
0x18009ee33  nop     dword ptr [rax+rax+00h]
0x18009ee38  mov     edx, 68h ; 'h'; index
0x18009ee3d  mov     rcx, rsi; hdc
0x18009ee40  call    cs:__imp_GetDeviceCaps
0x18009ee47  nop     dword ptr [rax+rax+00h]
0x18009ee4c  mov     rcx, rsi; hdc
0x18009ee4f  mov     ebx, eax
0x18009ee51  call    cs:__imp_DeleteDC
0x18009ee58  nop     dword ptr [rax+rax+00h]
0x18009ee5d  cmp     bp, bx
0x18009ee60  ja      short loc_18009EE90
0x18009ee62  xor     edx, edx
0x18009ee64  cmp     dx, bp
0x18009ee67  jnb     short loc_18009EE95
0x18009ee69  movzx   ecx, dx
0x18009ee6c  mov     al, [rdi+rcx*4+5Ah]
0x18009ee70  cmp     [rsp+rcx*4+458h+pPalEntries.peRed], al
0x18009ee74  jnz     short loc_18009EE90
0x18009ee76  mov     al, [rdi+rcx*4+59h]
0x18009ee7a  cmp     [rsp+rcx*4+458h+pPalEntries.peGreen], al
0x18009ee7e  jnz     short loc_18009EE90
0x18009ee80  mov     al, [rdi+rcx*4+58h]
0x18009ee84  cmp     [rsp+rcx*4+458h+pPalEntries.peBlue], al
0x18009ee88  jnz     short loc_18009EE90
0x18009ee8a  add     dx, r14w
0x18009ee8e  jmp     short loc_18009EE64
0x18009ee90  mov     eax, r14d
0x18009ee93  jmp     short loc_18009EE97
0x18009ee95  xor     eax, eax
0x18009ee97  mov     rcx, [rsp+458h+var_28]
0x18009ee9f  xor     rcx, rsp; StackCookie
0x18009eea2  call    __security_check_cookie
0x18009eea7  lea     r11, [rsp+458h+var_18]
0x18009eeaf  mov     rbx, [r11+28h]
0x18009eeb3  mov     rbp, [r11+30h]
0x18009eeb7  mov     rsp, r11
0x18009eeba  pop     r14
0x18009eebc  pop     rdi
0x18009eebd  pop     rsi
0x18009eebe  retn
```
