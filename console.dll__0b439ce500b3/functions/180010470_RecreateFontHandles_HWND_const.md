# RecreateFontHandles(HWND__ * const)

- ea: `0x180010470`
- end: `0x18001059e`
- name: `?RecreateFontHandles@@YAXQEAUHWND__@@@Z`
- size: `302`
- prototype: `void __fastcall(HWND)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000752c`
- `0x180009980`
- `0x18000a5f0`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180005e60`
- `0x180010350`
- `0x180010380`
- `0x180010470`

## import_xrefs

- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18001053d`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18001053d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18001055c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18001055c`

## pseudocode

```c
void __fastcall RecreateFontHandles(HWND a1)
{
  __int64 i; // rbx
  __int16 *v3; // rsi
  HFONT v4; // rsi
  LOGFONTW lf; // [rsp+20h] [rbp-98h] BYREF

  if ( *((_DWORD *)gpStateInfo + 53) )
  {
    for ( i = 0; (unsigned int)i < NumberOfFonts; i = (unsigned int)(i + 1) )
    {
      v3 = (__int16 *)FontInfo;
      if ( (*((_BYTE *)FontInfo + 40 * i + 32) & 4) != 0 )
      {
        memset_0(&lf, 0, sizeof(lf));
        lf.lfWidth = GetDPIXScaledPixelSize(a1, v3[20 * i + 4]);
        lf.lfHeight = GetDPIYScaledPixelSize(a1, *((__int16 *)FontInfo + 20 * i + 5));
        lf.lfWeight = *((_DWORD *)FontInfo + 10 * i + 4);
        lf.lfCharSet = *((_BYTE *)FontInfo + 40 * i + 33);
        lf.lfPitchAndFamily = 49;
        if ( StringCchCopyW(lf.lfFaceName, 0x20u, *((const wchar_t **)FontInfo + 5 * i + 3)) >= 0 )
        {
          v4 = CreateFontIndirectW(&lf);
          if ( v4 )
          {
            DeleteObject(*((HGDIOBJ *)FontInfo + 5 * i));
            *((_QWORD *)FontInfo + 5 * i) = v4;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180010470  push    rbx
0x180010472  push    rbp
0x180010473  push    rsi
0x180010474  push    rdi
0x180010475  sub     rsp, 98h
0x18001047c  mov     rax, cs:__security_cookie
0x180010483  xor     rax, rsp
0x180010486  mov     [rsp+0B8h+var_38], rax
0x18001048e  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180010495  mov     rbp, rcx
0x180010498  cmp     dword ptr [rax+0D4h], 0
0x18001049f  jz      loc_180010581
0x1800104a5  xor     ebx, ebx
0x1800104a7  cmp     cs:?NumberOfFonts@@3KA, ebx; ulong NumberOfFonts
0x1800104ad  jbe     loc_180010581
0x1800104b3  mov     rsi, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x1800104ba  lea     rdi, [rbx+rbx*4]
0x1800104be  test    byte ptr [rsi+rdi*8+20h], 4
0x1800104c3  jz      loc_180010573
0x1800104c9  xor     edx, edx; Val
0x1800104cb  lea     rcx, [rsp+0B8h+lf]; void *
0x1800104d0  lea     r8d, [rdx+5Ch]; Size
0x1800104d4  call    memset_0
0x1800104d9  movsx   edx, word ptr [rsi+rdi*8+8]; int
0x1800104de  mov     rcx, rbp; HWND
0x1800104e1  call    ?GetDPIXScaledPixelSize@@YAHQEAUHWND__@@H@Z; GetDPIXScaledPixelSize(HWND__ * const,int)
0x1800104e6  mov     [rsp+0B8h+lf.lfWidth], eax
0x1800104ea  mov     rcx, rbp; HWND
0x1800104ed  mov     rax, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x1800104f4  movsx   edx, word ptr [rax+rdi*8+0Ah]; int
0x1800104f9  call    ?GetDPIYScaledPixelSize@@YAHQEAUHWND__@@H@Z; GetDPIYScaledPixelSize(HWND__ * const,int)
0x1800104fe  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180010505  lea     rcx, [rsp+0B8h+lf.lfFaceName]; wchar_t *
0x18001050a  mov     [rsp+0B8h+lf.lfHeight], eax
0x18001050e  mov     edx, 20h ; ' '; unsigned __int64
0x180010513  mov     eax, [r8+rdi*8+10h]
0x180010518  mov     [rsp+0B8h+lf.lfWeight], eax
0x18001051c  mov     al, [r8+rdi*8+21h]
0x180010521  mov     [rsp+0B8h+lf.lfCharSet], al
0x180010525  mov     [rsp+0B8h+lf.lfPitchAndFamily], 31h ; '1'
0x18001052a  mov     r8, [r8+rdi*8+18h]; wchar_t *
0x18001052f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180010534  test    eax, eax
0x180010536  js      short loc_180010573
0x180010538  lea     rcx, [rsp+0B8h+lf]; lplf
0x18001053d  call    cs:__imp_CreateFontIndirectW
0x180010544  nop     dword ptr [rax+rax+00h]
0x180010549  mov     rsi, rax
0x18001054c  test    rax, rax
0x18001054f  jz      short loc_180010573
0x180010551  mov     rcx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180010558  mov     rcx, [rcx+rdi*8]; ho
0x18001055c  call    cs:__imp_DeleteObject
0x180010563  nop     dword ptr [rax+rax+00h]
0x180010568  mov     rcx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18001056f  mov     [rcx+rdi*8], rsi
0x180010573  inc     ebx
0x180010575  cmp     ebx, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18001057b  jb      loc_1800104B3
0x180010581  mov     rcx, [rsp+0B8h+var_38]
0x180010589  xor     rcx, rsp; StackCookie
0x18001058c  call    __security_check_cookie
0x180010591  add     rsp, 98h
0x180010598  pop     rdi
0x180010599  pop     rsi
0x18001059a  pop     rbp
0x18001059b  pop     rbx
0x18001059c  retn
```
