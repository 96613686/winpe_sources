# CopySubjectAlgorithmToString

- ea: `0x180005be0`
- end: `0x180005c65`
- name: `CopySubjectAlgorithmToString`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a50`
- `0x180005c6c`

## callees

- `0x180001f66`
- `0x180005be0`
- `0x180018908`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c2a`

## pseudocode

```c
unsigned __int16 *__fastcall CopySubjectAlgorithmToString(unsigned int *a1, __int64 a2, int *a3)
{
  bool v3; // zf
  int v6; // eax
  unsigned __int16 *v7; // rbx
  int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v11; // [rsp+38h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a2 + 96) == 0;
  v11 = 0;
  if ( v3 )
  {
    v9 = (unsigned __int16 *)LocalAlloc(0x40u, *a1);
    v7 = v9;
    if ( !v9 )
      return v7;
    memcpy_0(v9, *((const void **)a1 + 1), *a1);
    v8 = *a1 >> 1;
  }
  else
  {
    v6 = FormatHashTagToString(&v11, *((unsigned __int8 **)a1 + 1), *a1);
    v7 = v11;
    if ( !v6 )
      return v7;
    v8 = *a1 + 1;
  }
  if ( a3 )
    *a3 = v8;
  return v7;
}

```

## disassembly

```asm
0x180005be0  mov     rax, rsp
0x180005be3  mov     [rax+8], rbx
0x180005be7  mov     [rax+18h], rsi
0x180005beb  push    rdi
0x180005bec  sub     rsp, 20h
0x180005bf0  cmp     dword ptr [rdx+60h], 0
0x180005bf4  mov     rsi, r8
0x180005bf7  mov     rdi, rcx
0x180005bfa  mov     qword ptr [rax+10h], 0
0x180005c02  jz      short loc_180005C23
0x180005c04  mov     r8d, [rcx]; unsigned int
0x180005c07  mov     rdx, [rcx+8]; unsigned __int8 *
0x180005c0b  lea     rcx, [rax+10h]; unsigned __int16 **
0x180005c0f  call    ?FormatHashTagToString@@YAHPEAPEAGPEAEK@Z; FormatHashTagToString(ushort * *,uchar *,ulong)
0x180005c14  mov     rbx, [rsp+28h+arg_8]
0x180005c19  test    eax, eax
0x180005c1b  jz      short loc_180005C52
0x180005c1d  mov     eax, [rdi]
0x180005c1f  inc     eax
0x180005c21  jmp     short loc_180005C4B
0x180005c23  mov     edx, [rcx]; uBytes
0x180005c25  mov     ecx, 40h ; '@'; uFlags
0x180005c2a  call    cs:__imp_LocalAlloc
0x180005c30  mov     rbx, rax
0x180005c33  test    rax, rax
0x180005c36  jz      short loc_180005C52
0x180005c38  mov     r8d, [rdi]; Size
0x180005c3b  mov     rcx, rax; void *
0x180005c3e  mov     rdx, [rdi+8]; Src
0x180005c42  call    memcpy_0
0x180005c47  mov     eax, [rdi]
0x180005c49  shr     eax, 1
0x180005c4b  test    rsi, rsi
0x180005c4e  jz      short loc_180005C52
0x180005c50  mov     [rsi], eax
0x180005c52  mov     rsi, [rsp+28h+arg_10]
0x180005c57  mov     rax, rbx
0x180005c5a  mov     rbx, [rsp+28h+arg_0]
0x180005c5f  add     rsp, 20h
0x180005c63  pop     rdi
0x180005c64  retn
```
