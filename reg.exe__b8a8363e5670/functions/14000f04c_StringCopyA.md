# StringCopyA

- ea: `0x14000f04c`
- end: `0x14000f0ba`
- name: `StringCopyA`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d3e8`

## callees

- `0x14000f04c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f09f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f09f`

## pseudocode

```c
__int64 __fastcall StringCopyA(_BYTE *a1)
{
  __int64 v1; // rax
  const char *v2; // r8
  __int64 v3; // rdx
  _BYTE *v4; // rax

  if ( !a1 )
    return 0;
  v1 = 2147483646;
  v2 = "BUFFER";
  v3 = 7;
  do
  {
    if ( !v1 )
      break;
    if ( !*v2 )
      break;
    *a1++ = *v2++;
    --v1;
    --v3;
  }
  while ( v3 );
  v4 = a1 - 1;
  if ( v3 )
    v4 = a1;
  *v4 = 0;
  if ( !v3 )
  {
    SetLastError(0x7Au);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14000f04c  sub     rsp, 28h
0x14000f050  test    rcx, rcx
0x14000f053  jz      short loc_14000F0AB
0x14000f055  mov     eax, 7FFFFFFEh
0x14000f05a  lea     r8, cszSignature; "BUFFER"
0x14000f061  mov     edx, 7
0x14000f066  test    rax, rax
0x14000f069  jz      short loc_14000F085
0x14000f06b  mov     r9b, [r8]
0x14000f06e  test    r9b, r9b
0x14000f071  jz      short loc_14000F085
0x14000f073  mov     [rcx], r9b
0x14000f076  inc     r8
0x14000f079  inc     rcx
0x14000f07c  dec     rax
0x14000f07f  sub     rdx, 1
0x14000f083  jnz     short loc_14000F066
0x14000f085  test    rdx, rdx
0x14000f088  lea     rax, [rcx-1]
0x14000f08c  cmovnz  rax, rcx
0x14000f090  mov     byte ptr [rax], 0
0x14000f093  jnz     short loc_14000F0B3
0x14000f095  neg     rdx
0x14000f098  sbb     ecx, ecx
0x14000f09a  not     ecx
0x14000f09c  and     ecx, 7Ah; dwErrCode
0x14000f09f  call    cs:__imp_SetLastError
0x14000f0a6  nop     dword ptr [rax+rax+00h]
0x14000f0ab  xor     eax, eax
0x14000f0ad  add     rsp, 28h
0x14000f0b1  retn
0x14000f0b3  mov     eax, 1
0x14000f0b8  jmp     short loc_14000F0AD
```
