# STRA::CopyWToUTF8Unescaped(ushort const *,ulong)

- ea: `0x180001380`
- end: `0x1800013e0`
- name: `?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z`
- size: `96`
- prototype: `signed int __fastcall(STRA *this, LPCWCH lpWideCharStr, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001300`
- `0x180001350`
- `0x180019960`
- `0x18001d030`

## callees

- `0x180001380`
- `0x180014318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013cc`

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
0x180001380  push    rbx
0x180001382  sub     rsp, 30h
0x180001386  mov     rax, rdx
0x180001389  mov     rbx, rcx
0x18000138c  test    r8d, r8d
0x18000138f  jz      short loc_1800013B6
0x180001391  mov     rdx, rcx; this
0x180001394  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000139c  mov     rcx, rax; lpWideCharStr
0x18000139f  mov     r9d, 0FDE9h; CodePage
0x1800013a5  call    ?ConvertUnicodeToCodePage@@YAHPEBGPEAVBUFFER@@KIK@Z; ConvertUnicodeToCodePage(ushort const *,BUFFER *,ulong,uint,ulong)
0x1800013aa  mov     ecx, eax
0x1800013ac  cmp     eax, 0FFFFFFFFh
0x1800013af  jz      short loc_1800013CC
0x1800013b1  mov     [rbx+30h], eax
0x1800013b4  jmp     short loc_1800013C4
0x1800013b6  mov     rax, [rcx+20h]
0x1800013ba  mov     byte ptr [rax], 0
0x1800013bd  mov     dword ptr [rcx+30h], 0
0x1800013c4  xor     eax, eax
0x1800013c6  add     rsp, 30h
0x1800013ca  pop     rbx
0x1800013cb  retn
0x1800013cc  call    cs:__imp_GetLastError
0x1800013d2  test    eax, eax
0x1800013d4  jle     short loc_1800013C6
0x1800013d6  movzx   eax, ax
0x1800013d9  or      eax, 80070000h
0x1800013de  jmp     short loc_1800013C6
```
