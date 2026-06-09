# DwmpUpdateDesktopThumbnail

- ea: `0x1800148b0`
- end: `0x180014941`
- name: `DwmpUpdateDesktopThumbnail`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005b5c`
- `0x1800148b0`
- `0x180014af0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014902`
- `USER32!UpdateDefaultDesktopThumbnail` at `0x1800148f4`
- `USER32!UpdateDefaultDesktopThumbnail` at `0x1800148f4`

## pseudocode

```c
__int64 __fastcall DwmpUpdateDesktopThumbnail(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  char v5; // bp
  unsigned int v9; // ebx
  signed int LastError; // eax

  v5 = a4;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0p_EtwEventWriteTransfer(a1, ApipUpdateDesktopThumbnail_Start, a1);
  LOBYTE(a4) = v5;
  if ( (unsigned int)UpdateDefaultDesktopThumbnail(a1, a2, a3, a4, a5) )
  {
    v9 = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApipUpdateDesktopThumbnail_Stop);
  return v9;
}

```

## disassembly

```asm
0x1800148b0  push    rbx
0x1800148b2  push    rbp
0x1800148b3  push    rsi
0x1800148b4  push    rdi
0x1800148b5  sub     rsp, 38h
0x1800148b9  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x1800148c0  mov     bpl, r9b
0x1800148c3  mov     rsi, r8
0x1800148c6  mov     rdi, rdx
0x1800148c9  mov     rbx, rcx
0x1800148cc  jz      short loc_1800148DD
0x1800148ce  mov     r8, rcx
0x1800148d1  lea     rdx, ApipUpdateDesktopThumbnail_Start
0x1800148d8  call    McTemplateU0p_EtwEventWriteTransfer
0x1800148dd  mov     eax, [rsp+58h+arg_20]
0x1800148e4  mov     r9b, bpl
0x1800148e7  mov     r8, rsi
0x1800148ea  mov     [rsp+58h+var_38], eax
0x1800148ee  mov     rdx, rdi
0x1800148f1  mov     rcx, rbx
0x1800148f4  call    cs:__imp_UpdateDefaultDesktopThumbnail
0x1800148fa  test    eax, eax
0x1800148fc  jz      short loc_180014902
0x1800148fe  xor     ebx, ebx
0x180014900  jmp     short loc_180014917
0x180014902  call    cs:__imp_GetLastError
0x180014908  mov     ebx, eax
0x18001490a  test    eax, eax
0x18001490c  jle     short loc_180014917
0x18001490e  movzx   ebx, ax
0x180014911  or      ebx, 80070000h
0x180014917  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18001491e  jz      short loc_180014936
0x180014920  mov     r8d, ebx
0x180014923  lea     rdx, ApipUpdateDesktopThumbnail_Stop
0x18001492a  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180014931  call    McTemplateU0q_EtwEventWriteTransfer
0x180014936  mov     eax, ebx
0x180014938  add     rsp, 38h
0x18001493c  pop     rdi
0x18001493d  pop     rsi
0x18001493e  pop     rbp
0x18001493f  pop     rbx
0x180014940  retn
```
