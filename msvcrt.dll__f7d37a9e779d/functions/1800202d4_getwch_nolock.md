# _getwch_nolock

- ea: `0x1800202d4`
- end: `0x1800203ec`
- name: `_getwch_nolock`
- size: `280`
- prototype: `wint_t __cdecl()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800202a0`
- `0x180020434`

## callees

- `0x18001f28c`
- `0x1800202d4`
- `0x180023ac0`
- `0x180079760`

## import_xrefs

- `api-ms-win-core-console-l1-1-0!ReadConsoleInputW` at `0x1800203a1`
- `api-ms-win-core-console-l1-1-0!ReadConsoleInputW` at `0x1800203a1`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18002034a`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18002034a`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x180020359`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x1800203b8`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x180020359`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x1800203b8`

## pseudocode

```c
wint_t __cdecl getwch_nolock()
{
  wint_t result; // ax
  HANDLE v1; // rcx
  wint_t UnicodeChar; // bx
  unsigned __int8 *v3; // rax
  DWORD NumberOfEventsRead; // [rsp+20h] [rbp-30h] BYREF
  DWORD Mode; // [rsp+24h] [rbp-2Ch] BYREF
  struct _INPUT_RECORD Buffer; // [rsp+28h] [rbp-28h] BYREF

  result = word_18009D2D4;
  NumberOfEventsRead = 0;
  Mode = 0;
  memset(&Buffer, 0, 18);
  if ( word_18009D2D4 == -1 )
  {
    v1 = coninpfh;
    if ( coninpfh == (HANDLE)-2LL )
    {
      _initconin();
      v1 = coninpfh;
    }
    if ( v1 == (HANDLE)-1LL )
    {
      return -1;
    }
    else
    {
      GetConsoleMode(v1, &Mode);
      SetConsoleMode(coninpfh, 0);
      while ( 1 )
      {
        if ( !ReadConsoleInputW(coninpfh, &Buffer, 1u, &NumberOfEventsRead) )
        {
          UnicodeChar = -1;
          goto LABEL_15;
        }
        if ( !NumberOfEventsRead )
          break;
        if ( Buffer.EventType == 1 && Buffer.Event.KeyEvent.bKeyDown )
        {
          UnicodeChar = Buffer.Event.KeyEvent.uChar.UnicodeChar;
          if ( Buffer.Event.KeyEvent.uChar.UnicodeChar )
            goto LABEL_15;
          v3 = (unsigned __int8 *)getextendedkeycode(&Buffer.Event);
          if ( v3 )
          {
            UnicodeChar = *v3;
            word_18009D2D4 = v3[1];
            goto LABEL_15;
          }
        }
      }
      UnicodeChar = -1;
LABEL_15:
      SetConsoleMode(coninpfh, Mode);
      return UnicodeChar;
    }
  }
  else
  {
    word_18009D2D4 = -1;
  }
  return result;
}

```

## disassembly

```asm
0x1800202d4  push    rbp
0x1800202d6  push    rbx
0x1800202d7  push    rsi
0x1800202d8  push    rdi
0x1800202d9  push    r14
0x1800202db  mov     rbp, rsp
0x1800202de  sub     rsp, 50h
0x1800202e2  mov     rax, cs:__security_cookie
0x1800202e9  xor     rax, rsp
0x1800202ec  mov     [rbp+var_10], rax
0x1800202f0  xor     eax, eax
0x1800202f2  xor     edi, edi
0x1800202f4  mov     word ptr [rbp+Buffer.Event+0Ch], ax
0x1800202f8  mov     esi, 0FFFFh
0x1800202fd  movzx   eax, cs:word_18009D2D4
0x180020304  xorps   xmm0, xmm0
0x180020307  mov     [rbp+NumberOfEventsRead], edi
0x18002030a  mov     [rbp+Mode], edi
0x18002030d  movups  xmmword ptr [rbp+Buffer.EventType], xmm0
0x180020311  cmp     ax, si
0x180020314  jz      short loc_180020322
0x180020316  mov     cs:word_18009D2D4, si
0x18002031d  jmp     loc_1800203C1
0x180020322  mov     rcx, cs:_coninpfh
0x180020329  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18002032d  jnz     short loc_18002033B
0x18002032f  call    __initconin
0x180020334  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18002033b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002033f  jnz     short loc_180020346
0x180020341  movzx   eax, si
0x180020344  jmp     short loc_1800203C1
0x180020346  lea     rdx, [rbp+Mode]; lpMode
0x18002034a  call    cs:__imp_GetConsoleMode
0x180020350  mov     rcx, cs:_coninpfh; hConsoleHandle
0x180020357  xor     edx, edx; dwMode
0x180020359  call    cs:__imp_SetConsoleMode
0x18002035f  mov     r14d, 1
0x180020365  jmp     short loc_18002038F
0x180020367  cmp     [rbp+NumberOfEventsRead], edi
0x18002036a  jz      short loc_1800203E8
0x18002036c  cmp     [rbp+Buffer.EventType], r14w
0x180020371  jnz     short loc_18002038F
0x180020373  cmp     dword ptr [rbp+Buffer.Event], edi
0x180020376  jz      short loc_18002038F
0x180020378  movzx   ebx, word ptr [rbp+Buffer.Event+0Ah]
0x18002037c  test    bx, bx
0x18002037f  jnz     short loc_1800203AE
0x180020381  lea     rcx, [rbp+Buffer.Event]
0x180020385  call    _getextendedkeycode
0x18002038a  test    rax, rax
0x18002038d  jnz     short loc_1800203D8
0x18002038f  mov     rcx, cs:_coninpfh; hConsoleInput
0x180020396  lea     r9, [rbp+NumberOfEventsRead]; lpNumberOfEventsRead
0x18002039a  mov     r8d, r14d; nLength
0x18002039d  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800203a1  call    cs:__imp_ReadConsoleInputW
0x1800203a7  test    eax, eax
0x1800203a9  jnz     short loc_180020367
0x1800203ab  movzx   ebx, si
0x1800203ae  mov     edx, [rbp+Mode]; dwMode
0x1800203b1  mov     rcx, cs:_coninpfh; hConsoleHandle
0x1800203b8  call    cs:__imp_SetConsoleMode
0x1800203be  movzx   eax, bx
0x1800203c1  mov     rcx, [rbp+var_10]
0x1800203c5  xor     rcx, rsp; StackCookie
0x1800203c8  call    __security_check_cookie
0x1800203cd  add     rsp, 50h
0x1800203d1  pop     r14
0x1800203d3  pop     rdi
0x1800203d4  pop     rsi
0x1800203d5  pop     rbx
0x1800203d6  pop     rbp
0x1800203d7  retn
0x1800203d8  movzx   ebx, byte ptr [rax]
0x1800203db  movzx   eax, byte ptr [rax+1]
0x1800203df  mov     cs:word_18009D2D4, ax
0x1800203e6  jmp     short loc_1800203AE
0x1800203e8  mov     ebx, esi
0x1800203ea  jmp     short loc_1800203AE
```
