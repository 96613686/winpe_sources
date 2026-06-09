# StringConcatW

- ea: `0x14000ef5c`
- end: `0x14000f045`
- name: `StringConcatW`
- size: `233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000263c`
- `0x1400033d8`
- `0x140004e84`
- `0x140005910`
- `0x1400064b0`
- `0x1400080a4`
- `0x14000aa4c`

## callees

- `0x14000ef5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ef91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ef91`

## pseudocode

```c
__int64 __fastcall StringConcatW(_WORD *a1, _WORD *a2, int a3)
{
  _WORD *v3; // r10
  unsigned int v4; // edx
  __int64 v6; // r9
  _WORD *v7; // rax
  __int64 v8; // r11
  _WORD *v9; // r9
  __int64 v10; // rax
  __int64 i; // r8
  _WORD *v12; // rcx

  v3 = a2;
  if ( !a1 || !a2 || a3 <= 0 )
    return 0;
  if ( (unsigned __int64)a3 > 0x7FFFFFFF )
  {
    LOWORD(v4) = 87;
LABEL_6:
    SetLastError((unsigned __int16)v4);
    return 0;
  }
  v6 = a3;
  v7 = a1;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v4 = v6 == 0 ? 0x80070057 : 0;
  if ( v6 )
    v8 = a3 - v6;
  else
    v8 = 0;
  if ( !v6 )
    goto LABEL_6;
  v9 = &a1[v8];
  v10 = 2147483646;
  for ( i = a3 - v8; i; --i )
  {
    if ( !v10 )
      break;
    if ( !*v3 )
      break;
    *v9++ = *v3++;
    --v10;
  }
  v12 = v9 - 1;
  v4 = i == 0 ? 0x8007007A : 0;
  if ( i )
    v12 = v9;
  *v12 = 0;
  if ( !i )
    goto LABEL_6;
  return 1;
}

```

## disassembly

```asm
0x14000ef5c  mov     [rsp+arg_0], rbx
0x14000ef61  push    rdi
0x14000ef62  sub     rsp, 20h
0x14000ef66  xor     edi, edi
0x14000ef68  mov     r10, rdx
0x14000ef6b  mov     rbx, rcx
0x14000ef6e  test    rcx, rcx
0x14000ef71  jz      short loc_14000EF9D
0x14000ef73  test    rdx, rdx
0x14000ef76  jz      short loc_14000EF9D
0x14000ef78  test    r8d, r8d
0x14000ef7b  jle     short loc_14000EF9D
0x14000ef7d  movsxd  r8, r8d
0x14000ef80  cmp     r8, 7FFFFFFFh
0x14000ef87  jbe     short loc_14000EFAB
0x14000ef89  mov     edx, 80070057h
0x14000ef8e  movzx   ecx, dx; dwErrCode
0x14000ef91  call    cs:__imp_SetLastError
0x14000ef98  nop     dword ptr [rax+rax+00h]
0x14000ef9d  xor     eax, eax
0x14000ef9f  mov     rbx, [rsp+28h+arg_0]
0x14000efa4  add     rsp, 20h
0x14000efa8  pop     rdi
0x14000efa9  retn
0x14000efab  mov     r9, r8
0x14000efae  mov     rax, rbx
0x14000efb1  mov     r11, r8
0x14000efb4  cmp     [rax], di
0x14000efb7  jz      short loc_14000EFC3
0x14000efb9  add     rax, 2
0x14000efbd  sub     r9, 1
0x14000efc1  jnz     short loc_14000EFB4
0x14000efc3  mov     rax, r9
0x14000efc6  mov     edx, 80070057h
0x14000efcb  neg     rax
0x14000efce  sbb     ecx, ecx
0x14000efd0  not     ecx
0x14000efd2  and     edx, ecx
0x14000efd4  test    r9, r9
0x14000efd7  jz      short loc_14000EFDE
0x14000efd9  sub     r11, r9
0x14000efdc  jmp     short loc_14000EFE1
0x14000efde  mov     r11, rdi
0x14000efe1  test    r9, r9
0x14000efe4  jz      short loc_14000EF8E
0x14000efe6  lea     r9, [rbx+r11*2]
0x14000efea  mov     eax, 7FFFFFFEh
0x14000efef  sub     r8, r11
0x14000eff2  jz      short loc_14000F017
0x14000eff4  test    rax, rax
0x14000eff7  jz      short loc_14000F017
0x14000eff9  movzx   ecx, word ptr [r10]
0x14000effd  test    cx, cx
0x14000f000  jz      short loc_14000F017
0x14000f002  mov     [r9], cx
0x14000f006  add     r10, 2
0x14000f00a  add     r9, 2
0x14000f00e  dec     rax
0x14000f011  sub     r8, 1
0x14000f015  jnz     short loc_14000EFF4
0x14000f017  mov     rax, r8
0x14000f01a  lea     rcx, [r9-2]
0x14000f01e  neg     rax
0x14000f021  sbb     edx, edx
0x14000f023  not     edx
0x14000f025  and     edx, 8007007Ah
0x14000f02b  test    r8, r8
0x14000f02e  cmovnz  rcx, r9
0x14000f032  mov     [rcx], di
0x14000f035  jz      loc_14000EF8E
0x14000f03b  mov     eax, 1
0x14000f040  jmp     loc_14000EF9F
```
