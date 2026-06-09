# StringCopyA

- ea: `0x14000e3e0`
- end: `0x14000e447`
- name: `StringCopyA`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000caa8`

## callees

- `0x14000e3e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e433`

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
0x14000e3e0  sub     rsp, 28h
0x14000e3e4  test    rcx, rcx
0x14000e3e7  jz      short loc_14000E439
0x14000e3e9  mov     eax, 7FFFFFFEh
0x14000e3ee  lea     r8, cszSignature; "BUFFER"
0x14000e3f5  mov     edx, 7
0x14000e3fa  test    rax, rax
0x14000e3fd  jz      short loc_14000E419
0x14000e3ff  mov     r9b, [r8]
0x14000e402  test    r9b, r9b
0x14000e405  jz      short loc_14000E419
0x14000e407  mov     [rcx], r9b
0x14000e40a  inc     r8
0x14000e40d  inc     rcx
0x14000e410  dec     rax
0x14000e413  sub     rdx, 1
0x14000e417  jnz     short loc_14000E3FA
0x14000e419  test    rdx, rdx
0x14000e41c  lea     rax, [rcx-1]
0x14000e420  cmovnz  rax, rcx
0x14000e424  mov     byte ptr [rax], 0
0x14000e427  jnz     short loc_14000E440
0x14000e429  neg     rdx
0x14000e42c  sbb     ecx, ecx
0x14000e42e  not     ecx
0x14000e430  and     ecx, 7Ah; dwErrCode
0x14000e433  call    cs:__imp_SetLastError
0x14000e439  xor     eax, eax
0x14000e43b  add     rsp, 28h
0x14000e43f  retn
0x14000e440  mov     eax, 1
0x14000e445  jmp     short loc_14000E43B
```
