# COSKKeyboardManager::GetSKBFolderPath(ushort *,int)

- ea: `0x140010c0c`
- end: `0x140010c4d`
- name: `?GetSKBFolderPath@COSKKeyboardManager@@AEAAJPEAGH@Z`
- size: `65`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400118d0`
- `0x140011d2c`

## callees

- `0x140010c0c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140010c30`
- `KERNEL32!GetLastError` at `0x140010c30`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140010c26`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140010c26`

## string_xrefs

- `0x140010c14`: `%CommonProgramFiles%\Microsoft Shared\Ink\`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::GetSKBFolderPath(COSKKeyboardManager *this, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  *a2 = 0;
  v2 = 0;
  if ( !ExpandEnvironmentStringsW(L"%CommonProgramFiles%\\Microsoft Shared\\Ink\\", a2, 0x104u) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x140010c0c  push    rbx
0x140010c0e  sub     rsp, 20h
0x140010c12  xor     eax, eax
0x140010c14  lea     rcx, Src; "%CommonProgramFiles%\\Microsoft Shared"...
0x140010c1b  mov     r8d, 104h; nSize
0x140010c21  mov     [rdx], ax
0x140010c24  xor     ebx, ebx
0x140010c26  call    cs:__imp_ExpandEnvironmentStringsW
0x140010c2c  test    eax, eax
0x140010c2e  jnz     short loc_140010C45
0x140010c30  call    cs:__imp_GetLastError
0x140010c36  mov     ebx, eax
0x140010c38  test    eax, eax
0x140010c3a  jle     short loc_140010C45
0x140010c3c  movzx   ebx, ax
0x140010c3f  or      ebx, 80070000h
0x140010c45  mov     eax, ebx
0x140010c47  add     rsp, 20h
0x140010c4b  pop     rbx
0x140010c4c  retn
```
