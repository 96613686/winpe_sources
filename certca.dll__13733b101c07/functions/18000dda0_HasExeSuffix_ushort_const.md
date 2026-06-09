# HasExeSuffix(ushort const *)

- ea: `0x18000dda0`
- end: `0x18000de08`
- name: `?HasExeSuffix@@YA_NPEBG@Z`
- size: `104`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d5d0`

## callees

- `0x18000dda0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000ddae`
- `msvcrt!wcsrchr` at `0x18000ddae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dde7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dde7`

## pseudocode

```c
_BOOL8 __fastcall HasExeSuffix(const unsigned __int16 *a1)
{
  wchar_t *v1; // rax

  v1 = wcsrchr(a1, 0x2Eu);
  return v1 && CompareStringW(0x7Fu, 1u, v1, -1, L".exe", -1) == 2;
}

```

## disassembly

```asm
0x18000dda0  push    rdi
0x18000dda2  sub     rsp, 30h
0x18000dda6  mov     edx, 2Eh ; '.'; Ch
0x18000ddab  xor     dil, dil
0x18000ddae  call    cs:__imp_wcsrchr
0x18000ddb4  test    rax, rax
0x18000ddb7  jz      short loc_18000DE02
0x18000ddb9  lea     rcx, aExe; ".exe"
0x18000ddc0  mov     [rsp+38h+arg_0], rbx
0x18000ddc5  mov     ebx, 1
0x18000ddca  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000ddd2  mov     [rsp+38h+lpString2], rcx; lpString2
0x18000ddd7  mov     edx, ebx; dwCmpFlags
0x18000ddd9  mov     ecx, 7Fh; Locale
0x18000ddde  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000dde4  mov     r8, rax; lpString1
0x18000dde7  call    cs:__imp_CompareStringW
0x18000dded  cmp     eax, 2
0x18000ddf0  movzx   eax, dil
0x18000ddf4  cmovz   eax, ebx
0x18000ddf7  mov     rbx, [rsp+38h+arg_0]
0x18000ddfc  add     rsp, 30h
0x18000de00  pop     rdi
0x18000de01  retn
0x18000de02  movzx   eax, dil
0x18000de06  jmp     short loc_18000DDFC
```
