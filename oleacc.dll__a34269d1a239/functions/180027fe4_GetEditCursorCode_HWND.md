# GetEditCursorCode(HWND__ *)

- ea: `0x180027fe4`
- end: `0x18002808b`
- name: `?GetEditCursorCode@@YAGPEAUHWND__@@@Z`
- size: `167`
- prototype: `unsigned __int16 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180027e2c`

## callees

- `0x18001e4c0`
- `0x180027fe4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180028046`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180028046`
- `USER32!GetWindowThreadProcessId` at `0x180028001`
- `USER32!GetWindowThreadProcessId` at `0x180028001`
- `USER32!GetKeyboardLayout` at `0x180028009`
- `USER32!GetKeyboardLayout` at `0x180028009`

## pseudocode

```c
__int64 __fastcall GetEditCursorCode(HWND a1)
{
  DWORD WindowThreadProcessId; // eax
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  unsigned __int16 v6; // bx
  WCHAR LCData[80]; // [rsp+20h] [rbp-B8h] BYREF

  WindowThreadProcessId = GetWindowThreadProcessId(a1, 0);
  v2 = ((unsigned __int16)GetKeyboardLayout(WindowThreadProcessId) & 0x3FF) - 1;
  if ( !v2 )
    return (unsigned __int16)-4083;
  v3 = v2 - 12;
  if ( !v3 )
    return (unsigned __int16)-4083;
  v4 = v3 - 17;
  if ( !v4 )
    return (unsigned __int16)-4082;
  v5 = v4 - 2;
  if ( !v5 || v5 == 9 )
    return (unsigned __int16)-4083;
  v6 = -1;
  if ( GetLocaleInfoW(0x400u, 0x58u, LCData, 80) && (LCData[7] & 0x800) != 0 )
    return (unsigned __int16)-4084;
  return v6;
}

```

## disassembly

```asm
0x180027fe4  push    rbx
0x180027fe6  sub     rsp, 0D0h
0x180027fed  mov     rax, cs:__security_cookie
0x180027ff4  xor     rax, rsp
0x180027ff7  mov     [rsp+0D8h+var_18], rax
0x180027fff  xor     edx, edx; lpdwProcessId
0x180028001  call    cs:__imp_GetWindowThreadProcessId
0x180028007  mov     ecx, eax; idThread
0x180028009  call    cs:__imp_GetKeyboardLayout
0x18002800f  and     eax, 3FFh
0x180028014  sub     eax, 1
0x180028017  jz      short loc_18002806A
0x180028019  sub     eax, 0Ch
0x18002801c  jz      short loc_18002806A
0x18002801e  sub     eax, 11h
0x180028021  jz      short loc_180028063
0x180028023  sub     eax, 2
0x180028026  jz      short loc_18002806A
0x180028028  cmp     eax, 9
0x18002802b  jz      short loc_18002806A
0x18002802d  mov     r9d, 50h ; 'P'; cchData
0x180028033  lea     r8, [rsp+0D8h+LCData]; lpLCData
0x180028038  mov     ecx, 400h; Locale
0x18002803d  mov     ebx, 0FFFFh
0x180028042  lea     edx, [r9+8]; LCType
0x180028046  call    cs:__imp_GetLocaleInfoW
0x18002804c  test    eax, eax
0x18002804e  jz      short loc_18002806F
0x180028050  mov     eax, 800h
0x180028055  test    [rsp+0D8h+var_AA], ax
0x18002805a  jz      short loc_18002806F
0x18002805c  mov     ebx, 0F00Ch
0x180028061  jmp     short loc_18002806F
0x180028063  mov     ebx, 0F00Eh
0x180028068  jmp     short loc_18002806F
0x18002806a  mov     ebx, 0F00Dh
0x18002806f  movzx   eax, bx
0x180028072  mov     rcx, [rsp+0D8h+var_18]
0x18002807a  xor     rcx, rsp; StackCookie
0x18002807d  call    __security_check_cookie
0x180028082  add     rsp, 0D0h
0x180028089  pop     rbx
0x18002808a  retn
```
