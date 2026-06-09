# StringCopyW

- ea: `0x14000e450`
- end: `0x14000e4df`
- name: `StringCopyW`
- size: `143`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, __int64)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e90`
- `0x140002070`
- `0x140002234`
- `0x1400024a4`
- `0x140002940`
- `0x14000329c`
- `0x14000406c`
- `0x140004bbc`
- `0x1400055f8`
- `0x140005e84`
- `0x14000612c`
- `0x140006394`
- `0x140006a5c`
- `0x14000752c`
- `0x140007be0`
- `0x140008dfc`
- `0x140008fe8`
- `0x140009ae4`
- `0x140009d40`
- `0x14000a3f8`
- `0x14000caa8`
- `0x14000e4e8`
- `0x14000e7a4`
- `0x14000e994`

## callees

- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e4cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e4cb`

## pseudocode

```c
__int64 __fastcall StringCopyW(_WORD *a1, _WORD *a2, __int64 a3)
{
  _WORD *v3; // r9
  unsigned int v4; // edx
  __int64 v5; // rax
  _WORD *v6; // rcx

  v3 = a1;
  if ( !a1 || !a2 || (int)a3 <= 0 )
    return 0;
  a3 = (int)a3;
  if ( (unsigned __int64)(int)a3 > 0x7FFFFFFF )
  {
    *a1 = 0;
    LOWORD(v4) = 87;
LABEL_13:
    SetLastError((unsigned __int16)v4);
    return 0;
  }
  v5 = 2147483646;
  do
  {
    if ( !v5 )
      break;
    if ( !*a2 )
      break;
    *v3++ = *a2++;
    --v5;
    --a3;
  }
  while ( a3 );
  v6 = v3 - 1;
  v4 = a3 == 0 ? 0x8007007A : 0;
  if ( a3 )
    v6 = v3;
  *v6 = 0;
  if ( !a3 )
    goto LABEL_13;
  return 1;
}

```

## disassembly

```asm
0x14000e450  sub     rsp, 28h
0x14000e454  xor     r10d, r10d
0x14000e457  mov     r9, rcx
0x14000e45a  test    rcx, rcx
0x14000e45d  jz      short loc_14000E4D1
0x14000e45f  test    rdx, rdx
0x14000e462  jz      short loc_14000E4D1
0x14000e464  test    r8d, r8d
0x14000e467  jle     short loc_14000E4D1
0x14000e469  movsxd  r8, r8d
0x14000e46c  cmp     r8, 7FFFFFFFh
0x14000e473  jbe     short loc_14000E480
0x14000e475  mov     [rcx], r10w
0x14000e479  mov     edx, 80070057h
0x14000e47e  jmp     short loc_14000E4C8
0x14000e480  mov     eax, 7FFFFFFEh
0x14000e485  test    rax, rax
0x14000e488  jz      short loc_14000E4A7
0x14000e48a  movzx   ecx, word ptr [rdx]
0x14000e48d  test    cx, cx
0x14000e490  jz      short loc_14000E4A7
0x14000e492  mov     [r9], cx
0x14000e496  add     rdx, 2
0x14000e49a  add     r9, 2
0x14000e49e  dec     rax
0x14000e4a1  sub     r8, 1
0x14000e4a5  jnz     short loc_14000E485
0x14000e4a7  mov     rax, r8
0x14000e4aa  lea     rcx, [r9-2]
0x14000e4ae  neg     rax
0x14000e4b1  sbb     edx, edx
0x14000e4b3  not     edx
0x14000e4b5  and     edx, 8007007Ah
0x14000e4bb  test    r8, r8
0x14000e4be  cmovnz  rcx, r9
0x14000e4c2  mov     [rcx], r10w
0x14000e4c6  jnz     short loc_14000E4D8
0x14000e4c8  movzx   ecx, dx; dwErrCode
0x14000e4cb  call    cs:__imp_SetLastError
0x14000e4d1  xor     eax, eax
0x14000e4d3  add     rsp, 28h
0x14000e4d7  retn
0x14000e4d8  mov     eax, 1
0x14000e4dd  jmp     short loc_14000E4D3
```
