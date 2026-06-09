# STBUFF::UnicodeToAnsi(ushort *)

- ea: `0x180002efc`
- end: `0x180002f7d`
- name: `?UnicodeToAnsi@STBUFF@@QEAAJPEAG@Z`
- size: `129`
- prototype: `int(STBUFF *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dd0`
- `0x1800057cc`

## callees

- `0x180001fa4`
- `0x180002efc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f56`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002f4c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002f4c`

## pseudocode

```c
__int64 __fastcall STBUFF::UnicodeToAnsi(STBUFF *this, unsigned __int16 *a2)
{
  __int64 cbMultiByte; // rdi
  int v5; // ebx
  signed int LastError; // eax

  cbMultiByte = -1;
  do
    ++cbMultiByte;
  while ( a2[cbMultiByte] );
  v5 = STBUFF::Resize((const void **)this, cbMultiByte);
  if ( v5 >= 0 )
  {
    if ( WideCharToMultiByte(0, 0, a2, cbMultiByte, *((LPSTR *)this + 1), cbMultiByte, 0, 0) )
    {
      *((_DWORD *)this + 4) = cbMultiByte;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002efc  push    rbx
0x180002efe  push    rbp
0x180002eff  push    rsi
0x180002f00  push    rdi
0x180002f01  push    r14
0x180002f03  sub     rsp, 40h
0x180002f07  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002f0b  mov     rbp, rdx
0x180002f0e  xor     r14d, r14d
0x180002f11  mov     rsi, rcx
0x180002f14  inc     rdi
0x180002f17  cmp     [rdx+rdi*2], r14w
0x180002f1c  jnz     short loc_180002F14
0x180002f1e  mov     edx, edi; unsigned int
0x180002f20  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x180002f25  mov     ebx, eax
0x180002f27  test    eax, eax
0x180002f29  js      short loc_180002F70
0x180002f2b  mov     rcx, [rsi+8]
0x180002f2f  mov     r9d, edi; cchWideChar
0x180002f32  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180002f37  mov     r8, rbp; lpWideCharStr
0x180002f3a  mov     [rsp+68h+lpDefaultChar], r14; lpDefaultChar
0x180002f3f  xor     edx, edx; dwFlags
0x180002f41  mov     [rsp+68h+cbMultiByte], edi; cbMultiByte
0x180002f45  mov     [rsp+68h+lpMultiByteStr], rcx; lpMultiByteStr
0x180002f4a  xor     ecx, ecx; CodePage
0x180002f4c  call    cs:__imp_WideCharToMultiByte
0x180002f52  test    eax, eax
0x180002f54  jnz     short loc_180002F6D
0x180002f56  call    cs:__imp_GetLastError
0x180002f5c  mov     ebx, eax
0x180002f5e  test    eax, eax
0x180002f60  jle     short loc_180002F70
0x180002f62  movzx   ebx, ax
0x180002f65  or      ebx, 80070000h
0x180002f6b  jmp     short loc_180002F70
0x180002f6d  mov     [rsi+10h], edi
0x180002f70  mov     eax, ebx
0x180002f72  add     rsp, 40h
0x180002f76  pop     r14
0x180002f78  pop     rdi
0x180002f79  pop     rsi
0x180002f7a  pop     rbp
0x180002f7b  pop     rbx
0x180002f7c  retn
```
