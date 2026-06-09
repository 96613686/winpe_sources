# _getch_nolock

- ea: `0x18001f0e0`
- end: `0x18001f1fd`
- name: `_getch_nolock`
- size: `285`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f0b0`
- `0x18001f240`

## callees

- `0x18001f0e0`
- `0x18001f28c`
- `0x180023ac0`
- `0x180079760`

## import_xrefs

- `api-ms-win-core-console-l1-1-0!ReadConsoleInputA` at `0x18001f1af`
- `api-ms-win-core-console-l1-1-0!ReadConsoleInputA` at `0x18001f1af`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18001f157`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18001f157`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001f166`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001f1ca`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001f166`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001f1ca`

## pseudocode

```c
int __cdecl getch_nolock()
{
  int result; // eax
  HANDLE v1; // rcx
  int AsciiChar; // ebx
  unsigned __int8 *v3; // rax
  DWORD NumberOfEventsRead; // [rsp+20h] [rbp-30h] BYREF
  DWORD Mode; // [rsp+24h] [rbp-2Ch] BYREF
  _INPUT_RECORD Buffer; // [rsp+28h] [rbp-28h] BYREF

  NumberOfEventsRead = 0;
  Mode = 0;
  memset(&Buffer, 0, 18);
  if ( dword_18009D2D0 == -1 )
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
        if ( !ReadConsoleInputA(coninpfh, &Buffer, 1u, &NumberOfEventsRead) || !NumberOfEventsRead )
        {
          AsciiChar = -1;
          goto LABEL_15;
        }
        if ( Buffer.EventType == 1 && Buffer.Event.KeyEvent.bKeyDown )
        {
          AsciiChar = (unsigned __int8)Buffer.Event.KeyEvent.uChar.AsciiChar;
          if ( Buffer.Event.KeyEvent.uChar.AsciiChar )
            goto LABEL_15;
          v3 = (unsigned __int8 *)getextendedkeycode(&Buffer.Event);
          if ( v3 )
            break;
        }
      }
      AsciiChar = *v3;
      dword_18009D2D0 = v3[1];
LABEL_15:
      if ( Mode )
        SetConsoleMode(coninpfh, Mode);
      return AsciiChar;
    }
  }
  else
  {
    result = (unsigned __int8)dword_18009D2D0;
    dword_18009D2D0 = -1;
  }
  return result;
}

```

## disassembly

```asm
0x18001f0e0  mov     [rsp-8+arg_0], rbx
0x18001f0e5  mov     [rsp-8+arg_8], r14
0x18001f0ea  push    rbp
0x18001f0eb  mov     rbp, rsp
0x18001f0ee  sub     rsp, 50h
0x18001f0f2  mov     rax, cs:__security_cookie
0x18001f0f9  xor     rax, rsp
0x18001f0fc  mov     [rbp+var_10], rax
0x18001f100  xor     eax, eax
0x18001f102  xorps   xmm0, xmm0
0x18001f105  mov     word ptr [rbp+Buffer.Event+0Ch], ax
0x18001f109  mov     [rbp+NumberOfEventsRead], eax
0x18001f10c  mov     [rbp+Mode], eax
0x18001f10f  mov     eax, cs:dword_18009D2D0
0x18001f115  movups  xmmword ptr [rbp+Buffer.EventType], xmm0
0x18001f119  cmp     eax, 0FFFFFFFFh
0x18001f11c  jz      short loc_18001F130
0x18001f11e  movzx   eax, al
0x18001f121  mov     cs:dword_18009D2D0, 0FFFFFFFFh
0x18001f12b  jmp     loc_18001F1D2
0x18001f130  mov     rcx, cs:_coninpfh
0x18001f137  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18001f13b  jnz     short loc_18001F149
0x18001f13d  call    __initconin
0x18001f142  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18001f149  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f14d  jnz     short loc_18001F153
0x18001f14f  or      eax, ecx
0x18001f151  jmp     short loc_18001F1D2
0x18001f153  lea     rdx, [rbp+Mode]; lpMode
0x18001f157  call    cs:__imp_GetConsoleMode
0x18001f15d  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18001f164  xor     edx, edx; dwMode
0x18001f166  call    cs:__imp_SetConsoleMode
0x18001f16c  mov     r14d, 1
0x18001f172  jmp     short loc_18001F19D
0x18001f174  cmp     [rbp+NumberOfEventsRead], 0
0x18001f178  jz      short loc_18001F1B9
0x18001f17a  cmp     [rbp+Buffer.EventType], r14w
0x18001f17f  jnz     short loc_18001F19D
0x18001f181  cmp     dword ptr [rbp+Buffer.Event], 0
0x18001f185  jz      short loc_18001F19D
0x18001f187  movzx   ebx, byte ptr [rbp+Buffer.Event+0Ah]
0x18001f18b  test    ebx, ebx
0x18001f18d  jnz     short loc_18001F1BC
0x18001f18f  lea     rcx, [rbp+Buffer.Event]
0x18001f193  call    _getextendedkeycode
0x18001f198  test    rax, rax
0x18001f19b  jnz     short loc_18001F1EE
0x18001f19d  mov     rcx, cs:_coninpfh; hConsoleInput
0x18001f1a4  lea     r9, [rbp+NumberOfEventsRead]; lpNumberOfEventsRead
0x18001f1a8  mov     r8d, r14d; nLength
0x18001f1ab  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001f1af  call    cs:__imp_ReadConsoleInputA
0x18001f1b5  test    eax, eax
0x18001f1b7  jnz     short loc_18001F174
0x18001f1b9  or      ebx, 0FFFFFFFFh
0x18001f1bc  mov     edx, [rbp+Mode]; dwMode
0x18001f1bf  test    edx, edx
0x18001f1c1  jz      short loc_18001F1D0
0x18001f1c3  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18001f1ca  call    cs:__imp_SetConsoleMode
0x18001f1d0  mov     eax, ebx
0x18001f1d2  mov     rcx, [rbp+var_10]
0x18001f1d6  xor     rcx, rsp; StackCookie
0x18001f1d9  call    __security_check_cookie
0x18001f1de  mov     rbx, [rsp+50h+arg_0]
0x18001f1e3  mov     r14, [rsp+50h+arg_8]
0x18001f1e8  add     rsp, 50h
0x18001f1ec  pop     rbp
0x18001f1ed  retn
0x18001f1ee  movzx   ebx, byte ptr [rax]
0x18001f1f1  movzx   eax, byte ptr [rax+1]
0x18001f1f5  mov     cs:dword_18009D2D0, eax
0x18001f1fb  jmp     short loc_18001F1BC
```
