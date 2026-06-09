# RtlStringCchCopyA

- ea: `0x18000a9ac`
- end: `0x18000aa15`
- name: `RtlStringCchCopyA`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a90`

## callees

- `0x18000a9ac`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyA(_BYTE *a1, unsigned __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rax
  int *v4; // r8
  _BYTE *v5; // rax

  if ( !a2 )
    return 3221225485LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v3 = 2147483646;
    v4 = &dword_18000F424;
    do
    {
      if ( !v3 )
        break;
      if ( !*(_BYTE *)v4 )
        break;
      *a1 = *(_BYTE *)v4;
      v4 = (int *)((char *)v4 + 1);
      ++a1;
      --v3;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    return a2 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a9ac  test    rdx, rdx
0x18000a9af  jz      short loc_18000AA07
0x18000a9b1  cmp     rdx, 7FFFFFFFh
0x18000a9b8  jbe     short loc_18000A9C1
0x18000a9ba  mov     eax, 0C000000Dh
0x18000a9bf  jmp     short loc_18000AA11
0x18000a9c1  mov     eax, 7FFFFFFEh
0x18000a9c6  lea     r8, dword_18000F424
0x18000a9cd  test    rax, rax
0x18000a9d0  jz      short loc_18000A9EC
0x18000a9d2  mov     r9b, [r8]
0x18000a9d5  test    r9b, r9b
0x18000a9d8  jz      short loc_18000A9EC
0x18000a9da  mov     [rcx], r9b
0x18000a9dd  inc     r8
0x18000a9e0  inc     rcx
0x18000a9e3  dec     rax
0x18000a9e6  sub     rdx, 1
0x18000a9ea  jnz     short loc_18000A9CD
0x18000a9ec  test    rdx, rdx
0x18000a9ef  lea     rax, [rcx-1]
0x18000a9f3  cmovnz  rax, rcx
0x18000a9f7  neg     rdx
0x18000a9fa  mov     byte ptr [rax], 0
0x18000a9fd  sbb     eax, eax
0x18000a9ff  not     eax
0x18000aa01  and     eax, 80000005h
0x18000aa06  retn
0x18000aa07  mov     eax, 0C000000Dh
0x18000aa0c  test    rdx, rdx
0x18000aa0f  jz      short locret_18000AA14
0x18000aa11  mov     byte ptr [rcx], 0
0x18000aa14  retn
```
