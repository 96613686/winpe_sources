# LoadStr(ulong,ushort *,ulong,ushort const *)

- ea: `0x140001bf0`
- end: `0x140001c61`
- name: `?LoadStr@@YAJKPEAGKPEBG@Z`
- size: `113`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001adc`
- `0x140001c68`
- `0x140001f30`

## callees

- `0x140001bf0`
- `0x140002168`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140001c0a`
- `KERNEL32!GetModuleHandleW` at `0x140001c0a`
- `KERNEL32!GetLastError` at `0x140001c25`
- `KERNEL32!GetLastError` at `0x140001c25`
- `USER32!LoadStringW` at `0x140001c1b`
- `USER32!LoadStringW` at `0x140001c1b`

## pseudocode

```c
__int64 __fastcall LoadStr(UINT uID, unsigned __int16 *a2, unsigned int a3, unsigned __int16 *a4)
{
  unsigned __int64 v5; // r14
  unsigned int v8; // edi
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax

  v5 = a3;
  v8 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  if ( !LoadStringW(ModuleHandleW, uID, a2, v5) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( a4 )
      StringCchCopyW(a2, v5, a4);
    else
      *a2 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x140001bf0  push    rbx
0x140001bf2  push    rbp
0x140001bf3  push    rsi
0x140001bf4  push    rdi
0x140001bf5  push    r14
0x140001bf7  sub     rsp, 20h
0x140001bfb  mov     ebx, ecx
0x140001bfd  mov     r14d, r8d
0x140001c00  xor     ecx, ecx; lpModuleName
0x140001c02  mov     rbp, r9
0x140001c05  mov     rsi, rdx
0x140001c08  xor     edi, edi
0x140001c0a  call    cs:__imp_GetModuleHandleW
0x140001c10  mov     r9d, r14d; cchBufferMax
0x140001c13  mov     r8, rsi; lpBuffer
0x140001c16  mov     rcx, rax; hInstance
0x140001c19  mov     edx, ebx; uID
0x140001c1b  call    cs:__imp_LoadStringW
0x140001c21  test    eax, eax
0x140001c23  jnz     short loc_140001C54
0x140001c25  call    cs:__imp_GetLastError
0x140001c2b  mov     edi, eax
0x140001c2d  test    eax, eax
0x140001c2f  jle     short loc_140001C3A
0x140001c31  movzx   edi, ax
0x140001c34  or      edi, 80070000h
0x140001c3a  test    rbp, rbp
0x140001c3d  jz      short loc_140001C4F
0x140001c3f  mov     rdx, r14; unsigned __int64
0x140001c42  mov     r8, rbp; unsigned __int16 *
0x140001c45  mov     rcx, rsi; unsigned __int16 *
0x140001c48  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001c4d  jmp     short loc_140001C54
0x140001c4f  xor     ecx, ecx
0x140001c51  mov     [rsi], cx
0x140001c54  mov     eax, edi
0x140001c56  add     rsp, 20h
0x140001c5a  pop     r14
0x140001c5c  pop     rdi
0x140001c5d  pop     rsi
0x140001c5e  pop     rbp
0x140001c5f  pop     rbx
0x140001c60  retn
```
