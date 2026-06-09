# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x14000a8ac`
- end: `0x14000a918`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `108`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140009e3c`
- `0x14000b7c4`
- `0x14000be64`
- `0x14000c350`
- `0x140014828`
- `0x140014fd8`
- `0x140016d70`
- `0x140017000`
- `0x140017880`
- `0x140017d90`
- `0x140019940`
- `0x140019e10`

## callees

- `0x14000a8ac`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rax
  unsigned __int16 *v6; // rax

  v3 = a2 >> 1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = a1 - 1;
    if ( v3 )
      v6 = a1;
    *v6 = 0;
    return v3 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a8ac  xor     r9d, r9d
0x14000a8af  shr     rdx, 1
0x14000a8b2  jz      short loc_14000A909
0x14000a8b4  cmp     rdx, 7FFFFFFFh
0x14000a8bb  jbe     short loc_14000A8C4
0x14000a8bd  mov     eax, 80070057h
0x14000a8c2  jmp     short loc_14000A913
0x14000a8c4  mov     eax, 7FFFFFFEh
0x14000a8c9  test    rax, rax
0x14000a8cc  jz      short loc_14000A8ED
0x14000a8ce  movzx   r10d, word ptr [r8]
0x14000a8d2  test    r10w, r10w
0x14000a8d6  jz      short loc_14000A8ED
0x14000a8d8  mov     [rcx], r10w
0x14000a8dc  add     r8, 2
0x14000a8e0  add     rcx, 2
0x14000a8e4  dec     rax
0x14000a8e7  sub     rdx, 1
0x14000a8eb  jnz     short loc_14000A8C9
0x14000a8ed  test    rdx, rdx
0x14000a8f0  lea     rax, [rcx-2]
0x14000a8f4  cmovnz  rax, rcx
0x14000a8f8  neg     rdx
0x14000a8fb  mov     [rax], r9w
0x14000a8ff  sbb     eax, eax
0x14000a901  not     eax
0x14000a903  and     eax, 8007007Ah
0x14000a908  retn
0x14000a909  mov     eax, 80070057h
0x14000a90e  test    rdx, rdx
0x14000a911  jz      short locret_14000A917
0x14000a913  mov     [rcx], r9w
0x14000a917  retn
```
