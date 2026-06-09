# STRA::CopyWToUTF8Unescaped(ushort const *,ulong)

- ea: `0x180001c90`
- end: `0x180001cf7`
- name: `?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z`
- size: `103`
- prototype: `__int64 __fastcall(STRA *__hidden this, LPCWCH lpWideCharStr, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c10`
- `0x180001c60`
- `0x18001a7d0`
- `0x18001e0d0`

## callees

- `0x180001c90`
- `0x180014e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cdd`

## pseudocode

```c
signed int __fastcall STRA::CopyWToUTF8Unescaped(STRA *this, LPCWCH lpWideCharStr, unsigned int a3)
{
  int v4; // eax
  signed int result; // eax

  if ( !a3 )
  {
    **((_BYTE **)this + 4) = 0;
    *((_DWORD *)this + 12) = 0;
    return 0;
  }
  v4 = ConvertUnicodeToCodePage(lpWideCharStr, this, a3, 0xFDE9u, 0);
  if ( v4 != -1 )
  {
    *((_DWORD *)this + 12) = v4;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180001c90  push    rbx
0x180001c92  sub     rsp, 30h
0x180001c96  mov     rax, rdx
0x180001c99  mov     rbx, rcx
0x180001c9c  test    r8d, r8d
0x180001c9f  jz      short loc_180001CC6
0x180001ca1  mov     rdx, rcx; this
0x180001ca4  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180001cac  mov     rcx, rax; lpWideCharStr
0x180001caf  mov     r9d, 0FDE9h; CodePage
0x180001cb5  call    ?ConvertUnicodeToCodePage@@YAHPEBGPEAVBUFFER@@KIK@Z; ConvertUnicodeToCodePage(ushort const *,BUFFER *,ulong,uint,ulong)
0x180001cba  mov     ecx, eax
0x180001cbc  cmp     eax, 0FFFFFFFFh
0x180001cbf  jz      short loc_180001CDD
0x180001cc1  mov     [rbx+30h], eax
0x180001cc4  jmp     short loc_180001CD4
0x180001cc6  mov     rax, [rcx+20h]
0x180001cca  mov     byte ptr [rax], 0
0x180001ccd  mov     dword ptr [rcx+30h], 0
0x180001cd4  xor     eax, eax
0x180001cd6  add     rsp, 30h
0x180001cda  pop     rbx
0x180001cdb  retn
0x180001cdd  call    cs:__imp_GetLastError
0x180001ce4  nop     dword ptr [rax+rax+00h]
0x180001ce9  test    eax, eax
0x180001ceb  jle     short loc_180001CD6
0x180001ced  movzx   eax, ax
0x180001cf0  or      eax, 80070000h
0x180001cf5  jmp     short loc_180001CD6
```
