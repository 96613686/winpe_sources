# BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)

- ea: `0x180003970`
- end: `0x180003a0b`
- name: `?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z`
- size: `155`
- prototype: `int(struct _objectinfo *, unsigned __int16 *, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a58`
- `0x18000683c`
- `0x18000745c`
- `0x18000828c`
- `0x180008fc0`
- `0x180009df0`
- `0x18000a94c`

## callees

- `0x180003970`
- `0x1800111ba`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180003998`
- `msvcrt!wcscat_s` at `0x1800039d1`
- `msvcrt!wcscat_s` at `0x1800039ee`
- `msvcrt!wcscat_s` at `0x180003998`
- `msvcrt!wcscat_s` at `0x1800039d1`
- `msvcrt!wcscat_s` at `0x1800039ee`

## pseudocode

```c
__int64 __fastcall BuildIISPathFromADsPath(struct _objectinfo *a1, unsigned __int16 *a2, rsize_t a3)
{
  unsigned int v3; // edi
  unsigned int v7; // ebx
  unsigned int v8; // esi
  const wchar_t *v9; // r15

  v3 = *((_DWORD *)a1 + 5);
  wcscat_s(a2, a3, L"/LM/");
  if ( v3 )
  {
    v7 = 0;
    v8 = v3 - 1;
    do
    {
      v9 = *(const wchar_t **)(*((_QWORD *)a1 + 4) + 16LL * v7);
      if ( !wcscmp_0(v9, L"[Root]") )
      {
        if ( v7 == v8 )
          goto LABEL_7;
      }
      else
      {
        wcscat_s(a2, a3, v9);
      }
      if ( v7 < v8 )
LABEL_7:
        wcscat_s(a2, a3, L"/");
      ++v7;
    }
    while ( v7 < v3 );
  }
  return 0;
}

```

## disassembly

```asm
0x180003970  push    rbx
0x180003972  push    rbp
0x180003973  push    rsi
0x180003974  push    rdi
0x180003975  push    r13
0x180003977  push    r14
0x180003979  push    r15
0x18000397b  sub     rsp, 20h
0x18000397f  mov     edi, [rcx+14h]
0x180003982  mov     rbp, r8
0x180003985  mov     r14, rdx
0x180003988  lea     r8, aLm; "/LM/"
0x18000398f  mov     r13, rcx
0x180003992  mov     rdx, rbp; SizeInWords
0x180003995  mov     rcx, r14; Destination
0x180003998  call    cs:__imp_wcscat_s
0x18000399e  cmp     edi, 1
0x1800039a1  jb      short loc_1800039FA
0x1800039a3  xor     ebx, ebx
0x1800039a5  lea     esi, [rdi-1]
0x1800039a8  mov     rax, [r13+20h]
0x1800039ac  lea     rdx, aRoot_0; "[Root]"
0x1800039b3  mov     ecx, ebx
0x1800039b5  add     rcx, rcx
0x1800039b8  mov     r15, [rax+rcx*8]
0x1800039bc  mov     rcx, r15; String1
0x1800039bf  call    wcscmp_0
0x1800039c4  test    eax, eax
0x1800039c6  jz      short loc_1800039D9
0x1800039c8  mov     r8, r15; Source
0x1800039cb  mov     rdx, rbp; SizeInWords
0x1800039ce  mov     rcx, r14; Destination
0x1800039d1  call    cs:__imp_wcscat_s
0x1800039d7  jmp     short loc_1800039DD
0x1800039d9  cmp     ebx, esi
0x1800039db  jz      short loc_1800039E1
0x1800039dd  cmp     ebx, esi
0x1800039df  jnb     short loc_1800039F4
0x1800039e1  lea     r8, asc_180014360; "/"
0x1800039e8  mov     rdx, rbp; SizeInWords
0x1800039eb  mov     rcx, r14; Destination
0x1800039ee  call    cs:__imp_wcscat_s
0x1800039f4  inc     ebx
0x1800039f6  cmp     ebx, edi
0x1800039f8  jb      short loc_1800039A8
0x1800039fa  xor     eax, eax
0x1800039fc  add     rsp, 20h
0x180003a00  pop     r15
0x180003a02  pop     r14
0x180003a04  pop     r13
0x180003a06  pop     rdi
0x180003a07  pop     rsi
0x180003a08  pop     rbp
0x180003a09  pop     rbx
0x180003a0a  retn
```
