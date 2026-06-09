# StringConcatW

- ea: `0x14000e2f8`
- end: `0x14000e3da`
- name: `StringConcatW`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400024a4`
- `0x14000329c`
- `0x140004bbc`
- `0x1400055f8`
- `0x14000612c`
- `0x140007be0`
- `0x14000a3f8`

## callees

- `0x14000e2f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e32d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e32d`

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
0x14000e2f8  mov     [rsp+arg_0], rbx
0x14000e2fd  push    rdi
0x14000e2fe  sub     rsp, 20h
0x14000e302  xor     edi, edi
0x14000e304  mov     r10, rdx
0x14000e307  mov     rbx, rcx
0x14000e30a  test    rcx, rcx
0x14000e30d  jz      short loc_14000E333
0x14000e30f  test    rdx, rdx
0x14000e312  jz      short loc_14000E333
0x14000e314  test    r8d, r8d
0x14000e317  jle     short loc_14000E333
0x14000e319  movsxd  r8, r8d
0x14000e31c  cmp     r8, 7FFFFFFFh
0x14000e323  jbe     short loc_14000E340
0x14000e325  mov     edx, 80070057h
0x14000e32a  movzx   ecx, dx; dwErrCode
0x14000e32d  call    cs:__imp_SetLastError
0x14000e333  xor     eax, eax
0x14000e335  mov     rbx, [rsp+28h+arg_0]
0x14000e33a  add     rsp, 20h
0x14000e33e  pop     rdi
0x14000e33f  retn
0x14000e340  mov     r9, r8
0x14000e343  mov     rax, rbx
0x14000e346  mov     r11, r8
0x14000e349  cmp     [rax], di
0x14000e34c  jz      short loc_14000E358
0x14000e34e  add     rax, 2
0x14000e352  sub     r9, 1
0x14000e356  jnz     short loc_14000E349
0x14000e358  mov     rax, r9
0x14000e35b  mov     edx, 80070057h
0x14000e360  neg     rax
0x14000e363  sbb     ecx, ecx
0x14000e365  not     ecx
0x14000e367  and     edx, ecx
0x14000e369  test    r9, r9
0x14000e36c  jz      short loc_14000E373
0x14000e36e  sub     r11, r9
0x14000e371  jmp     short loc_14000E376
0x14000e373  mov     r11, rdi
0x14000e376  test    r9, r9
0x14000e379  jz      short loc_14000E32A
0x14000e37b  lea     r9, [rbx+r11*2]
0x14000e37f  mov     eax, 7FFFFFFEh
0x14000e384  sub     r8, r11
0x14000e387  jz      short loc_14000E3AC
0x14000e389  test    rax, rax
0x14000e38c  jz      short loc_14000E3AC
0x14000e38e  movzx   ecx, word ptr [r10]
0x14000e392  test    cx, cx
0x14000e395  jz      short loc_14000E3AC
0x14000e397  mov     [r9], cx
0x14000e39b  add     r10, 2
0x14000e39f  add     r9, 2
0x14000e3a3  dec     rax
0x14000e3a6  sub     r8, 1
0x14000e3aa  jnz     short loc_14000E389
0x14000e3ac  mov     rax, r8
0x14000e3af  lea     rcx, [r9-2]
0x14000e3b3  neg     rax
0x14000e3b6  sbb     edx, edx
0x14000e3b8  not     edx
0x14000e3ba  and     edx, 8007007Ah
0x14000e3c0  test    r8, r8
0x14000e3c3  cmovnz  rcx, r9
0x14000e3c7  mov     [rcx], di
0x14000e3ca  jz      loc_14000E32A
0x14000e3d0  mov     eax, 1
0x14000e3d5  jmp     loc_14000E335
```
