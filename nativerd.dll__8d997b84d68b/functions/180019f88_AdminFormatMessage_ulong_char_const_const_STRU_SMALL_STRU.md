# AdminFormatMessage(ulong,char const * * const,STRU *,SMALL_STRU *)

- ea: `0x180019f88`
- end: `0x18001a03d`
- name: `?AdminFormatMessage@@YAJKQEAPEBDPEAVSTRU@@PEAVSMALL_STRU@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(DWORD dwMessageId, va_list *Arguments, struct STRU *, struct SMALL_STRU *)`
- caller_count: `15`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800124bc`
- `0x18002fbf4`
- `0x180035114`
- `0x180036768`
- `0x18003eea4`
- `0x18003f510`
- `0x18003f5e0`
- `0x18003f700`
- `0x18003f7a0`
- `0x18003f990`
- `0x18003fb00`
- `0x18003fdc0`
- `0x18003fed0`
- `0x1800400b0`
- `0x180058c80`

## callees

- `0x180010468`
- `0x180019f88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fde`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019fd4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180019fd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a02a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a02a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001a00e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001a00e`

## pseudocode

```c
__int64 __fastcall AdminFormatMessage(DWORD dwMessageId, va_list *Arguments, struct STRU *a3, struct SMALL_STRU *a4)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned __int16 *Buffer; // [rsp+60h] [rbp+18h] BYREF

  Buffer = 0;
  if ( a3 )
  {
    if ( !a4 )
      goto LABEL_3;
    return (unsigned int)-2147024809;
  }
  if ( !a4 )
    return (unsigned int)-2147024809;
LABEL_3:
  if ( FormatMessageW(0x2900u, g_hResourceDll, dwMessageId, 0, (LPWSTR)&Buffer, 0, Arguments) )
  {
    if ( a3 )
      v8 = STRU::Copy(a3, Buffer);
    else
      v8 = SMALL_STRU::Copy(a4, Buffer);
    v7 = v8;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Buffer )
    LocalFree(Buffer);
  return v7;
}

```

## disassembly

```asm
0x180019f88  mov     [rsp+arg_0], rbx
0x180019f8d  push    rdi
0x180019f8e  sub     rsp, 40h
0x180019f92  mov     [rsp+48h+Buffer], 0
0x180019f9b  mov     rbx, r9
0x180019f9e  mov     rdi, r8
0x180019fa1  test    r8, r8
0x180019fa4  jnz     short loc_180019FF5
0x180019fa6  test    rbx, rbx
0x180019fa9  jz      short loc_180019FFA
0x180019fab  mov     [rsp+48h+Arguments], rdx; Arguments
0x180019fb0  lea     rax, [rsp+48h+Buffer]
0x180019fb5  mov     rdx, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; lpSource
0x180019fbc  mov     r8d, ecx; dwMessageId
0x180019fbf  mov     [rsp+48h+nSize], 0; nSize
0x180019fc7  mov     ecx, 2900h; dwFlags
0x180019fcc  xor     r9d, r9d; dwLanguageId
0x180019fcf  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180019fd4  call    cs:__imp_FormatMessageW
0x180019fda  test    eax, eax
0x180019fdc  jnz     short loc_18001A001
0x180019fde  call    cs:__imp_GetLastError
0x180019fe4  mov     ebx, eax
0x180019fe6  test    eax, eax
0x180019fe8  jle     short loc_18001A020
0x180019fea  movzx   ebx, ax
0x180019fed  or      ebx, 80070000h
0x180019ff3  jmp     short loc_18001A020
0x180019ff5  test    rbx, rbx
0x180019ff8  jz      short loc_180019FAB
0x180019ffa  mov     ebx, 80070057h
0x180019fff  jmp     short loc_18001A030
0x18001a001  mov     rdx, [rsp+48h+Buffer]; unsigned __int16 *
0x18001a006  test    rdi, rdi
0x18001a009  jz      short loc_18001A016
0x18001a00b  mov     rcx, rdi
0x18001a00e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001a014  jmp     short loc_18001A01E
0x18001a016  mov     rcx, rbx; this
0x18001a019  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18001a01e  mov     ebx, eax
0x18001a020  mov     rcx, [rsp+48h+Buffer]; hMem
0x18001a025  test    rcx, rcx
0x18001a028  jz      short loc_18001A030
0x18001a02a  call    cs:__imp_LocalFree
0x18001a030  mov     eax, ebx
0x18001a032  mov     rbx, [rsp+48h+arg_0]
0x18001a037  add     rsp, 40h
0x18001a03b  pop     rdi
0x18001a03c  retn
```
