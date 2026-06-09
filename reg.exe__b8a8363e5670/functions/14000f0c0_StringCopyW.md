# StringCopyW

- ea: `0x14000f0c0`
- end: `0x14000f156`
- name: `StringCopyW`
- size: `150`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, __int64)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e90`
- `0x140002090`
- `0x1400022dc`
- `0x14000263c`
- `0x140002a78`
- `0x1400033d8`
- `0x14000426c`
- `0x140004e84`
- `0x140005910`
- `0x1400061e4`
- `0x1400064b0`
- `0x14000672c`
- `0x140006e6c`
- `0x14000799c`
- `0x1400080a4`
- `0x140009374`
- `0x14000957c`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000aa4c`
- `0x14000d3e8`
- `0x14000f15c`
- `0x14000f43c`
- `0x14000f638`

## callees

- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f13b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f13b`

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
0x14000f0c0  sub     rsp, 28h
0x14000f0c4  xor     r10d, r10d
0x14000f0c7  mov     r9, rcx
0x14000f0ca  test    rcx, rcx
0x14000f0cd  jz      short loc_14000F147
0x14000f0cf  test    rdx, rdx
0x14000f0d2  jz      short loc_14000F147
0x14000f0d4  test    r8d, r8d
0x14000f0d7  jle     short loc_14000F147
0x14000f0d9  movsxd  r8, r8d
0x14000f0dc  cmp     r8, 7FFFFFFFh
0x14000f0e3  jbe     short loc_14000F0F0
0x14000f0e5  mov     [rcx], r10w
0x14000f0e9  mov     edx, 80070057h
0x14000f0ee  jmp     short loc_14000F138
0x14000f0f0  mov     eax, 7FFFFFFEh
0x14000f0f5  test    rax, rax
0x14000f0f8  jz      short loc_14000F117
0x14000f0fa  movzx   ecx, word ptr [rdx]
0x14000f0fd  test    cx, cx
0x14000f100  jz      short loc_14000F117
0x14000f102  mov     [r9], cx
0x14000f106  add     rdx, 2
0x14000f10a  add     r9, 2
0x14000f10e  dec     rax
0x14000f111  sub     r8, 1
0x14000f115  jnz     short loc_14000F0F5
0x14000f117  mov     rax, r8
0x14000f11a  lea     rcx, [r9-2]
0x14000f11e  neg     rax
0x14000f121  sbb     edx, edx
0x14000f123  not     edx
0x14000f125  and     edx, 8007007Ah
0x14000f12b  test    r8, r8
0x14000f12e  cmovnz  rcx, r9
0x14000f132  mov     [rcx], r10w
0x14000f136  jnz     short loc_14000F14F
0x14000f138  movzx   ecx, dx; dwErrCode
0x14000f13b  call    cs:__imp_SetLastError
0x14000f142  nop     dword ptr [rax+rax+00h]
0x14000f147  xor     eax, eax
0x14000f149  add     rsp, 28h
0x14000f14d  retn
0x14000f14f  mov     eax, 1
0x14000f154  jmp     short loc_14000F149
```
